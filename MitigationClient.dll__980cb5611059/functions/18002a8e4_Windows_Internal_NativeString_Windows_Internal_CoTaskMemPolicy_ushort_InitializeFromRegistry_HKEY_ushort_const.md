# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_InitializeFromRegistry(HKEY__ *,ushort const *,bool)

- ea: `0x18002a8e4`
- end: `0x18002aa99`
- name: `?_InitializeFromRegistry@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEAUHKEY__@@PEBG_N@Z`
- size: `437`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002a144`
- `0x18002a73c`

## callees

- `0x18002407c`
- `0x18002a8e4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a977`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a9ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a977`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a9ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002aa1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002aa6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002aa7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002aa1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002aa6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002aa7a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a92f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a9a5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a92f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a9a5`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002a9d9`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002aa08`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002a9d9`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002aa08`

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
0x18002a8e4  mov     r11, rsp
0x18002a8e7  mov     [r11+8], rbx
0x18002a8eb  mov     [r11+10h], rbp
0x18002a8ef  mov     [r11+20h], r9b
0x18002a8f3  push    rsi
0x18002a8f4  push    rdi
0x18002a8f5  push    r12
0x18002a8f7  push    r14
0x18002a8f9  push    r15
0x18002a8fb  sub     rsp, 40h
0x18002a8ff  xor     r12d, r12d
0x18002a902  lea     rax, [r11+20h]
0x18002a906  mov     rsi, r8
0x18002a909  mov     [r11-40h], rax
0x18002a90d  mov     rbp, rdx
0x18002a910  mov     [r11-48h], r12
0x18002a914  mov     r15, rcx
0x18002a917  mov     [r11-38h], r12d
0x18002a91b  mov     rdx, rsi; lpValueName
0x18002a91e  mov     [r11+20h], r12d
0x18002a922  mov     rcx, rbp; hKey
0x18002a925  lea     r9, [r11-38h]; lpType
0x18002a929  xor     r8d, r8d; lpReserved
0x18002a92c  mov     edi, r12d
0x18002a92f  call    cs:__imp_RegQueryValueExW
0x18002a935  mov     ebx, eax
0x18002a937  mov     r14d, 80070000h
0x18002a93d  test    eax, eax
0x18002a93f  jle     short loc_18002A947
0x18002a941  movzx   ebx, ax
0x18002a944  or      ebx, r14d
0x18002a947  test    ebx, ebx
0x18002a949  js      loc_18002AA77
0x18002a94f  mov     eax, [rsp+68h+Type]
0x18002a953  dec     eax
0x18002a955  cmp     eax, 1
0x18002a958  ja      loc_18002AA72
0x18002a95e  mov     eax, dword ptr [rsp+68h+cb]
0x18002a965  test    eax, eax
0x18002a967  jz      loc_18002AA72
0x18002a96d  test    al, 1
0x18002a96f  jnz     loc_18002AA72
0x18002a975  mov     ecx, eax; cb
0x18002a977  call    cs:__imp_CoTaskMemAlloc
0x18002a97d  mov     rdi, rax
0x18002a980  test    rax, rax
0x18002a983  jz      short loc_18002A9F8
0x18002a985  lea     rax, [rsp+68h+cb]
0x18002a98d  xor     r8d, r8d; lpReserved
0x18002a990  mov     [rsp+68h+lpcbData], rax; lpcbData
0x18002a995  lea     r9, [rsp+68h+Type]; lpType
0x18002a99a  mov     rdx, rsi; lpValueName
0x18002a99d  mov     [rsp+68h+lpData], rdi; lpData
0x18002a9a2  mov     rcx, rbp; hKey
0x18002a9a5  call    cs:__imp_RegQueryValueExW
0x18002a9ab  mov     ebx, eax
0x18002a9ad  test    eax, eax
0x18002a9af  jle     short loc_18002A9B7
0x18002a9b1  movzx   ebx, ax
0x18002a9b4  or      ebx, r14d
0x18002a9b7  test    ebx, ebx
0x18002a9b9  js      loc_18002AA77
0x18002a9bf  mov     esi, dword ptr [rsp+68h+cb]
0x18002a9c6  shr     esi, 1
0x18002a9c8  dec     esi
0x18002a9ca  cmp     [rsp+68h+Type], 2
0x18002a9cf  jnz     short loc_18002AA2C
0x18002a9d1  xor     r8d, r8d; nSize
0x18002a9d4  xor     edx, edx; lpDst
0x18002a9d6  mov     rcx, rdi; lpSrc
0x18002a9d9  call    cs:__imp_ExpandEnvironmentStringsW
0x18002a9df  mov     ebp, eax
0x18002a9e1  test    eax, eax
0x18002a9e3  jz      short loc_18002AA2C
0x18002a9e5  mov     ecx, ebp
0x18002a9e7  add     rcx, rcx; cb
0x18002a9ea  call    cs:__imp_CoTaskMemAlloc
0x18002a9f0  mov     rsi, rax
0x18002a9f3  test    rax, rax
0x18002a9f6  jnz     short loc_18002A9FF
0x18002a9f8  mov     ebx, 8007000Eh
0x18002a9fd  jmp     short loc_18002AA77
0x18002a9ff  mov     r8d, ebp; nSize
0x18002aa02  mov     rdx, rsi; lpDst
0x18002aa05  mov     rcx, rdi; lpSrc
0x18002aa08  call    cs:__imp_ExpandEnvironmentStringsW
0x18002aa0e  mov     r14d, eax
0x18002aa11  test    eax, eax
0x18002aa13  jz      short loc_18002AA62
0x18002aa15  cmp     eax, ebp
0x18002aa17  ja      short loc_18002AA62
0x18002aa19  mov     rcx, rdi; pv
0x18002aa1c  mov     ebx, r12d
0x18002aa1f  call    cs:__imp_CoTaskMemFree
0x18002aa25  mov     rdi, rsi
0x18002aa28  lea     esi, [r14-1]
0x18002aa2c  cmp     [rdi+rsi*2], r12w
0x18002aa31  jnz     short loc_18002AA72
0x18002aa33  mov     rcx, r15
0x18002aa36  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18002aa3b  test    rdi, rdi
0x18002aa3e  jz      short loc_18002AA5D
0x18002aa40  lea     eax, [rsi+1]
0x18002aa43  mov     ecx, eax
0x18002aa45  test    eax, eax
0x18002aa47  jz      short loc_18002AA5D
0x18002aa49  dec     rax
0x18002aa4c  mov     [r15], rdi
0x18002aa4f  mov     [r15+8], rax
0x18002aa53  mov     [r15+10h], rcx
0x18002aa57  mov     [rdi+rcx*2-2], r12w
0x18002aa5d  mov     rdi, r12
0x18002aa60  jmp     short loc_18002AA77
0x18002aa62  mov     rcx, rsi; pv
0x18002aa65  mov     ebx, 8007007Ah
0x18002aa6a  call    cs:__imp_CoTaskMemFree
0x18002aa70  jmp     short loc_18002AA77
0x18002aa72  mov     ebx, 8007000Dh
0x18002aa77  mov     rcx, rdi; pv
0x18002aa7a  call    cs:__imp_CoTaskMemFree
0x18002aa80  mov     rbp, [rsp+68h+arg_8]
0x18002aa85  mov     eax, ebx
0x18002aa87  mov     rbx, [rsp+68h+arg_0]
0x18002aa8c  add     rsp, 40h
0x18002aa90  pop     r15
0x18002aa92  pop     r14
0x18002aa94  pop     r12
0x18002aa96  pop     rdi
0x18002aa97  pop     rsi
0x18002aa98  retn
```
