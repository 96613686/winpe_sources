# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_InitializeFromRegistry(HKEY__ *,ushort const *,bool)

- ea: `0x180045ad4`
- end: `0x180045c89`
- name: `?_InitializeFromRegistry@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEAUHKEY__@@PEBG_N@Z`
- size: `437`
- prototype: `__int64 __fastcall(BYTE **, HKEY, const WCHAR *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18007e6c0`
- `0x18008523c`

## callees

- `0x18002bc20`
- `0x180045ad4`

## import_xrefs

- `KERNEL32!ExpandEnvironmentStringsW` at `0x180045bc9`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180045bf8`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180045bc9`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180045bf8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180045b67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180045bda`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180045b67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180045bda`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045c0f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045c5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045c6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045c0f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045c5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045c6a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180045b1f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180045b95`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180045b1f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180045b95`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_InitializeFromRegistry(
        BYTE **a1,
        HKEY a2,
        const WCHAR *a3)
{
  BYTE *lpData; // rdi
  LSTATUS Value; // eax
  signed int v8; // ebx
  LSTATUS v9; // eax
  __int64 v10; // rsi
  DWORD v11; // eax
  DWORD v12; // ebp
  WCHAR *v13; // rax
  WCHAR *v14; // rsi
  DWORD v15; // eax
  DWORD v16; // r14d
  __int64 v17; // rax
  DWORD Type[14]; // [rsp+30h] [rbp-38h] BYREF
  SIZE_T cb; // [rsp+88h] [rbp+20h] BYREF

  Type[0] = 0;
  LODWORD(cb) = 0;
  lpData = 0;
  Value = RegQueryValueExW(a2, a3, 0, Type, 0, (LPDWORD)&cb);
  v8 = Value;
  if ( Value > 0 )
    v8 = (unsigned __int16)Value | 0x80070000;
  if ( v8 >= 0 )
  {
    if ( Type[0] - 1 > 1 || !(_DWORD)cb || (cb & 1) != 0 )
      goto LABEL_24;
    lpData = (BYTE *)CoTaskMemAlloc((unsigned int)cb);
    if ( !lpData )
    {
LABEL_14:
      v8 = -2147024882;
      goto LABEL_25;
    }
    v9 = RegQueryValueExW(a2, a3, 0, Type, lpData, (LPDWORD)&cb);
    v8 = v9;
    if ( v9 > 0 )
      v8 = (unsigned __int16)v9 | 0x80070000;
    if ( v8 >= 0 )
    {
      v10 = ((unsigned int)cb >> 1) - 1;
      if ( Type[0] == 2 )
      {
        v11 = ExpandEnvironmentStringsW((LPCWSTR)lpData, 0, 0);
        v12 = v11;
        if ( v11 )
        {
          v13 = (WCHAR *)CoTaskMemAlloc(2LL * v11);
          v14 = v13;
          if ( !v13 )
            goto LABEL_14;
          v15 = ExpandEnvironmentStringsW((LPCWSTR)lpData, v13, v12);
          v16 = v15;
          if ( !v15 || v15 > v12 )
          {
            v8 = -2147024774;
            CoTaskMemFree(v14);
            goto LABEL_25;
          }
          v8 = 0;
          CoTaskMemFree(lpData);
          lpData = (BYTE *)v14;
          v10 = v16 - 1;
        }
      }
      if ( !*(_WORD *)&lpData[2 * v10] )
      {
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(a1);
        if ( lpData )
        {
          v17 = (unsigned int)(v10 + 1);
          if ( (_DWORD)v10 != -1 )
          {
            *a1 = lpData;
            a1[1] = (BYTE *)(v17 - 1);
            a1[2] = (BYTE *)(unsigned int)v17;
            *(_WORD *)&lpData[2 * (unsigned int)v17 - 2] = 0;
          }
        }
        lpData = 0;
        goto LABEL_25;
      }
LABEL_24:
      v8 = -2147024883;
    }
  }
LABEL_25:
  CoTaskMemFree(lpData);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180045ad4  mov     r11, rsp
0x180045ad7  mov     [r11+8], rbx
0x180045adb  mov     [r11+10h], rbp
0x180045adf  mov     [r11+20h], r9b
0x180045ae3  push    rsi
0x180045ae4  push    rdi
0x180045ae5  push    r12
0x180045ae7  push    r14
0x180045ae9  push    r15
0x180045aeb  sub     rsp, 40h
0x180045aef  xor     r12d, r12d
0x180045af2  lea     rax, [r11+20h]
0x180045af6  mov     rsi, r8
0x180045af9  mov     [r11-40h], rax
0x180045afd  mov     rbp, rdx
0x180045b00  mov     [r11-48h], r12
0x180045b04  mov     r15, rcx
0x180045b07  mov     [r11-38h], r12d
0x180045b0b  mov     rdx, rsi; lpValueName
0x180045b0e  mov     [r11+20h], r12d
0x180045b12  mov     rcx, rbp; hKey
0x180045b15  lea     r9, [r11-38h]; lpType
0x180045b19  xor     r8d, r8d; lpReserved
0x180045b1c  mov     edi, r12d
0x180045b1f  call    cs:__imp_RegQueryValueExW
0x180045b25  mov     ebx, eax
0x180045b27  mov     r14d, 80070000h
0x180045b2d  test    eax, eax
0x180045b2f  jle     short loc_180045B37
0x180045b31  movzx   ebx, ax
0x180045b34  or      ebx, r14d
0x180045b37  test    ebx, ebx
0x180045b39  js      loc_180045C67
0x180045b3f  mov     eax, [rsp+68h+Type]
0x180045b43  dec     eax
0x180045b45  cmp     eax, 1
0x180045b48  ja      loc_180045C62
0x180045b4e  mov     eax, dword ptr [rsp+68h+cb]
0x180045b55  test    eax, eax
0x180045b57  jz      loc_180045C62
0x180045b5d  test    al, 1
0x180045b5f  jnz     loc_180045C62
0x180045b65  mov     ecx, eax; cb
0x180045b67  call    cs:__imp_CoTaskMemAlloc
0x180045b6d  mov     rdi, rax
0x180045b70  test    rax, rax
0x180045b73  jz      short loc_180045BE8
0x180045b75  lea     rax, [rsp+68h+cb]
0x180045b7d  xor     r8d, r8d; lpReserved
0x180045b80  mov     [rsp+68h+lpcbData], rax; lpcbData
0x180045b85  lea     r9, [rsp+68h+Type]; lpType
0x180045b8a  mov     rdx, rsi; lpValueName
0x180045b8d  mov     [rsp+68h+lpData], rdi; lpData
0x180045b92  mov     rcx, rbp; hKey
0x180045b95  call    cs:__imp_RegQueryValueExW
0x180045b9b  mov     ebx, eax
0x180045b9d  test    eax, eax
0x180045b9f  jle     short loc_180045BA7
0x180045ba1  movzx   ebx, ax
0x180045ba4  or      ebx, r14d
0x180045ba7  test    ebx, ebx
0x180045ba9  js      loc_180045C67
0x180045baf  mov     esi, dword ptr [rsp+68h+cb]
0x180045bb6  shr     esi, 1
0x180045bb8  dec     esi
0x180045bba  cmp     [rsp+68h+Type], 2
0x180045bbf  jnz     short loc_180045C1C
0x180045bc1  xor     r8d, r8d; nSize
0x180045bc4  xor     edx, edx; lpDst
0x180045bc6  mov     rcx, rdi; lpSrc
0x180045bc9  call    cs:__imp_ExpandEnvironmentStringsW
0x180045bcf  mov     ebp, eax
0x180045bd1  test    eax, eax
0x180045bd3  jz      short loc_180045C1C
0x180045bd5  mov     ecx, ebp
0x180045bd7  add     rcx, rcx; cb
0x180045bda  call    cs:__imp_CoTaskMemAlloc
0x180045be0  mov     rsi, rax
0x180045be3  test    rax, rax
0x180045be6  jnz     short loc_180045BEF
0x180045be8  mov     ebx, 8007000Eh
0x180045bed  jmp     short loc_180045C67
0x180045bef  mov     r8d, ebp; nSize
0x180045bf2  mov     rdx, rsi; lpDst
0x180045bf5  mov     rcx, rdi; lpSrc
0x180045bf8  call    cs:__imp_ExpandEnvironmentStringsW
0x180045bfe  mov     r14d, eax
0x180045c01  test    eax, eax
0x180045c03  jz      short loc_180045C52
0x180045c05  cmp     eax, ebp
0x180045c07  ja      short loc_180045C52
0x180045c09  mov     rcx, rdi; pv
0x180045c0c  mov     ebx, r12d
0x180045c0f  call    cs:__imp_CoTaskMemFree
0x180045c15  mov     rdi, rsi
0x180045c18  lea     esi, [r14-1]
0x180045c1c  cmp     [rdi+rsi*2], r12w
0x180045c21  jnz     short loc_180045C62
0x180045c23  mov     rcx, r15
0x180045c26  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180045c2b  test    rdi, rdi
0x180045c2e  jz      short loc_180045C4D
0x180045c30  lea     eax, [rsi+1]
0x180045c33  mov     ecx, eax
0x180045c35  test    eax, eax
0x180045c37  jz      short loc_180045C4D
0x180045c39  dec     rax
0x180045c3c  mov     [r15], rdi
0x180045c3f  mov     [r15+8], rax
0x180045c43  mov     [r15+10h], rcx
0x180045c47  mov     [rdi+rcx*2-2], r12w
0x180045c4d  mov     rdi, r12
0x180045c50  jmp     short loc_180045C67
0x180045c52  mov     rcx, rsi; pv
0x180045c55  mov     ebx, 8007007Ah
0x180045c5a  call    cs:__imp_CoTaskMemFree
0x180045c60  jmp     short loc_180045C67
0x180045c62  mov     ebx, 8007000Dh
0x180045c67  mov     rcx, rdi; pv
0x180045c6a  call    cs:__imp_CoTaskMemFree
0x180045c70  mov     rbp, [rsp+68h+arg_8]
0x180045c75  mov     eax, ebx
0x180045c77  mov     rbx, [rsp+68h+arg_0]
0x180045c7c  add     rsp, 40h
0x180045c80  pop     r15
0x180045c82  pop     r14
0x180045c84  pop     r12
0x180045c86  pop     rdi
0x180045c87  pop     rsi
0x180045c88  retn
```
