# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_InitializeFromRegistry(HKEY__ *,ushort const *,bool)

- ea: `0x180020a50`
- end: `0x180020c05`
- name: `?_InitializeFromRegistry@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEAUHKEY__@@PEBG_N@Z`
- size: `437`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800202c4`

## callees

- `0x18001c6f4`
- `0x180020a50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180020a9b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180020b11`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180020a9b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180020b11`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180020b45`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180020b74`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180020b45`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180020b74`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020b8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020bd6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020be6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020b8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020bd6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020be6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180020ae3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180020b56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180020ae3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180020b56`

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
0x180020a50  mov     r11, rsp
0x180020a53  mov     [r11+8], rbx
0x180020a57  mov     [r11+10h], rbp
0x180020a5b  mov     [r11+20h], r9b
0x180020a5f  push    rsi
0x180020a60  push    rdi
0x180020a61  push    r12
0x180020a63  push    r14
0x180020a65  push    r15
0x180020a67  sub     rsp, 40h
0x180020a6b  xor     r12d, r12d
0x180020a6e  lea     rax, [r11+20h]
0x180020a72  mov     rsi, r8
0x180020a75  mov     [r11-40h], rax
0x180020a79  mov     rbp, rdx
0x180020a7c  mov     [r11-48h], r12
0x180020a80  mov     r15, rcx
0x180020a83  mov     [r11-38h], r12d
0x180020a87  mov     rdx, rsi; lpValueName
0x180020a8a  mov     [r11+20h], r12d
0x180020a8e  mov     rcx, rbp; hKey
0x180020a91  lea     r9, [r11-38h]; lpType
0x180020a95  xor     r8d, r8d; lpReserved
0x180020a98  mov     edi, r12d
0x180020a9b  call    cs:__imp_RegQueryValueExW
0x180020aa1  mov     ebx, eax
0x180020aa3  mov     r14d, 80070000h
0x180020aa9  test    eax, eax
0x180020aab  jle     short loc_180020AB3
0x180020aad  movzx   ebx, ax
0x180020ab0  or      ebx, r14d
0x180020ab3  test    ebx, ebx
0x180020ab5  js      loc_180020BE3
0x180020abb  mov     eax, [rsp+68h+Type]
0x180020abf  dec     eax
0x180020ac1  cmp     eax, 1
0x180020ac4  ja      loc_180020BDE
0x180020aca  mov     eax, dword ptr [rsp+68h+cb]
0x180020ad1  test    eax, eax
0x180020ad3  jz      loc_180020BDE
0x180020ad9  test    al, 1
0x180020adb  jnz     loc_180020BDE
0x180020ae1  mov     ecx, eax; cb
0x180020ae3  call    cs:__imp_CoTaskMemAlloc
0x180020ae9  mov     rdi, rax
0x180020aec  test    rax, rax
0x180020aef  jz      short loc_180020B64
0x180020af1  lea     rax, [rsp+68h+cb]
0x180020af9  xor     r8d, r8d; lpReserved
0x180020afc  mov     [rsp+68h+lpcbData], rax; lpcbData
0x180020b01  lea     r9, [rsp+68h+Type]; lpType
0x180020b06  mov     rdx, rsi; lpValueName
0x180020b09  mov     [rsp+68h+lpData], rdi; lpData
0x180020b0e  mov     rcx, rbp; hKey
0x180020b11  call    cs:__imp_RegQueryValueExW
0x180020b17  mov     ebx, eax
0x180020b19  test    eax, eax
0x180020b1b  jle     short loc_180020B23
0x180020b1d  movzx   ebx, ax
0x180020b20  or      ebx, r14d
0x180020b23  test    ebx, ebx
0x180020b25  js      loc_180020BE3
0x180020b2b  mov     esi, dword ptr [rsp+68h+cb]
0x180020b32  shr     esi, 1
0x180020b34  dec     esi
0x180020b36  cmp     [rsp+68h+Type], 2
0x180020b3b  jnz     short loc_180020B98
0x180020b3d  xor     r8d, r8d; nSize
0x180020b40  xor     edx, edx; lpDst
0x180020b42  mov     rcx, rdi; lpSrc
0x180020b45  call    cs:__imp_ExpandEnvironmentStringsW
0x180020b4b  mov     ebp, eax
0x180020b4d  test    eax, eax
0x180020b4f  jz      short loc_180020B98
0x180020b51  mov     ecx, ebp
0x180020b53  add     rcx, rcx; cb
0x180020b56  call    cs:__imp_CoTaskMemAlloc
0x180020b5c  mov     rsi, rax
0x180020b5f  test    rax, rax
0x180020b62  jnz     short loc_180020B6B
0x180020b64  mov     ebx, 8007000Eh
0x180020b69  jmp     short loc_180020BE3
0x180020b6b  mov     r8d, ebp; nSize
0x180020b6e  mov     rdx, rsi; lpDst
0x180020b71  mov     rcx, rdi; lpSrc
0x180020b74  call    cs:__imp_ExpandEnvironmentStringsW
0x180020b7a  mov     r14d, eax
0x180020b7d  test    eax, eax
0x180020b7f  jz      short loc_180020BCE
0x180020b81  cmp     eax, ebp
0x180020b83  ja      short loc_180020BCE
0x180020b85  mov     rcx, rdi; pv
0x180020b88  mov     ebx, r12d
0x180020b8b  call    cs:__imp_CoTaskMemFree
0x180020b91  mov     rdi, rsi
0x180020b94  lea     esi, [r14-1]
0x180020b98  cmp     [rdi+rsi*2], r12w
0x180020b9d  jnz     short loc_180020BDE
0x180020b9f  mov     rcx, r15
0x180020ba2  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180020ba7  test    rdi, rdi
0x180020baa  jz      short loc_180020BC9
0x180020bac  lea     eax, [rsi+1]
0x180020baf  mov     ecx, eax
0x180020bb1  test    eax, eax
0x180020bb3  jz      short loc_180020BC9
0x180020bb5  dec     rax
0x180020bb8  mov     [r15], rdi
0x180020bbb  mov     [r15+8], rax
0x180020bbf  mov     [r15+10h], rcx
0x180020bc3  mov     [rdi+rcx*2-2], r12w
0x180020bc9  mov     rdi, r12
0x180020bcc  jmp     short loc_180020BE3
0x180020bce  mov     rcx, rsi; pv
0x180020bd1  mov     ebx, 8007007Ah
0x180020bd6  call    cs:__imp_CoTaskMemFree
0x180020bdc  jmp     short loc_180020BE3
0x180020bde  mov     ebx, 8007000Dh
0x180020be3  mov     rcx, rdi; pv
0x180020be6  call    cs:__imp_CoTaskMemFree
0x180020bec  mov     rbp, [rsp+68h+arg_8]
0x180020bf1  mov     eax, ebx
0x180020bf3  mov     rbx, [rsp+68h+arg_0]
0x180020bf8  add     rsp, 40h
0x180020bfc  pop     r15
0x180020bfe  pop     r14
0x180020c00  pop     r12
0x180020c02  pop     rdi
0x180020c03  pop     rsi
0x180020c04  retn
```
