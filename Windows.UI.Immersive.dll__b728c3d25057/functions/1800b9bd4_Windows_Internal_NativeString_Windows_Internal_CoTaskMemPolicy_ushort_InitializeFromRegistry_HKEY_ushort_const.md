# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_InitializeFromRegistry(HKEY__ *,ushort const *,bool)

- ea: `0x1800b9bd4`
- end: `0x1800b9d89`
- name: `?_InitializeFromRegistry@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEAUHKEY__@@PEBG_N@Z`
- size: `437`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180009ce4`
- `0x180036a6c`
- `0x18004b080`

## callees

- `0x18000a910`
- `0x1800b9bd4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b9c1f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b9c95`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b9c1f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b9c95`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800b9cc9`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800b9cf8`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800b9cc9`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800b9cf8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b9c67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b9cda`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b9c67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b9cda`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b9d0f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b9d5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b9d6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b9d0f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b9d5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b9d6a`

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
0x1800b9bd4  mov     r11, rsp
0x1800b9bd7  mov     [r11+8], rbx
0x1800b9bdb  mov     [r11+10h], rbp
0x1800b9bdf  mov     [r11+20h], r9b
0x1800b9be3  push    rsi
0x1800b9be4  push    rdi
0x1800b9be5  push    r12
0x1800b9be7  push    r14
0x1800b9be9  push    r15
0x1800b9beb  sub     rsp, 40h
0x1800b9bef  xor     r12d, r12d
0x1800b9bf2  lea     rax, [r11+20h]
0x1800b9bf6  mov     rsi, r8
0x1800b9bf9  mov     [r11-40h], rax
0x1800b9bfd  mov     rbp, rdx
0x1800b9c00  mov     [r11-48h], r12
0x1800b9c04  mov     r15, rcx
0x1800b9c07  mov     [r11-38h], r12d
0x1800b9c0b  mov     rdx, rsi; lpValueName
0x1800b9c0e  mov     [r11+20h], r12d
0x1800b9c12  mov     rcx, rbp; hKey
0x1800b9c15  lea     r9, [r11-38h]; lpType
0x1800b9c19  xor     r8d, r8d; lpReserved
0x1800b9c1c  mov     edi, r12d
0x1800b9c1f  call    cs:__imp_RegQueryValueExW
0x1800b9c25  mov     ebx, eax
0x1800b9c27  mov     r14d, 80070000h
0x1800b9c2d  test    eax, eax
0x1800b9c2f  jle     short loc_1800B9C37
0x1800b9c31  movzx   ebx, ax
0x1800b9c34  or      ebx, r14d
0x1800b9c37  test    ebx, ebx
0x1800b9c39  js      loc_1800B9D67
0x1800b9c3f  mov     eax, [rsp+68h+Type]
0x1800b9c43  dec     eax
0x1800b9c45  cmp     eax, 1
0x1800b9c48  ja      loc_1800B9D62
0x1800b9c4e  mov     eax, dword ptr [rsp+68h+cb]
0x1800b9c55  test    eax, eax
0x1800b9c57  jz      loc_1800B9D62
0x1800b9c5d  test    al, 1
0x1800b9c5f  jnz     loc_1800B9D62
0x1800b9c65  mov     ecx, eax; cb
0x1800b9c67  call    cs:__imp_CoTaskMemAlloc
0x1800b9c6d  mov     rdi, rax
0x1800b9c70  test    rax, rax
0x1800b9c73  jz      short loc_1800B9CE8
0x1800b9c75  lea     rax, [rsp+68h+cb]
0x1800b9c7d  xor     r8d, r8d; lpReserved
0x1800b9c80  mov     [rsp+68h+lpcbData], rax; lpcbData
0x1800b9c85  lea     r9, [rsp+68h+Type]; lpType
0x1800b9c8a  mov     rdx, rsi; lpValueName
0x1800b9c8d  mov     [rsp+68h+lpData], rdi; lpData
0x1800b9c92  mov     rcx, rbp; hKey
0x1800b9c95  call    cs:__imp_RegQueryValueExW
0x1800b9c9b  mov     ebx, eax
0x1800b9c9d  test    eax, eax
0x1800b9c9f  jle     short loc_1800B9CA7
0x1800b9ca1  movzx   ebx, ax
0x1800b9ca4  or      ebx, r14d
0x1800b9ca7  test    ebx, ebx
0x1800b9ca9  js      loc_1800B9D67
0x1800b9caf  mov     esi, dword ptr [rsp+68h+cb]
0x1800b9cb6  shr     esi, 1
0x1800b9cb8  dec     esi
0x1800b9cba  cmp     [rsp+68h+Type], 2
0x1800b9cbf  jnz     short loc_1800B9D1C
0x1800b9cc1  xor     r8d, r8d; nSize
0x1800b9cc4  xor     edx, edx; lpDst
0x1800b9cc6  mov     rcx, rdi; lpSrc
0x1800b9cc9  call    cs:__imp_ExpandEnvironmentStringsW
0x1800b9ccf  mov     ebp, eax
0x1800b9cd1  test    eax, eax
0x1800b9cd3  jz      short loc_1800B9D1C
0x1800b9cd5  mov     ecx, ebp
0x1800b9cd7  add     rcx, rcx; cb
0x1800b9cda  call    cs:__imp_CoTaskMemAlloc
0x1800b9ce0  mov     rsi, rax
0x1800b9ce3  test    rax, rax
0x1800b9ce6  jnz     short loc_1800B9CEF
0x1800b9ce8  mov     ebx, 8007000Eh
0x1800b9ced  jmp     short loc_1800B9D67
0x1800b9cef  mov     r8d, ebp; nSize
0x1800b9cf2  mov     rdx, rsi; lpDst
0x1800b9cf5  mov     rcx, rdi; lpSrc
0x1800b9cf8  call    cs:__imp_ExpandEnvironmentStringsW
0x1800b9cfe  mov     r14d, eax
0x1800b9d01  test    eax, eax
0x1800b9d03  jz      short loc_1800B9D52
0x1800b9d05  cmp     eax, ebp
0x1800b9d07  ja      short loc_1800B9D52
0x1800b9d09  mov     rcx, rdi; pv
0x1800b9d0c  mov     ebx, r12d
0x1800b9d0f  call    cs:__imp_CoTaskMemFree
0x1800b9d15  mov     rdi, rsi
0x1800b9d18  lea     esi, [r14-1]
0x1800b9d1c  cmp     [rdi+rsi*2], r12w
0x1800b9d21  jnz     short loc_1800B9D62
0x1800b9d23  mov     rcx, r15
0x1800b9d26  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800b9d2b  test    rdi, rdi
0x1800b9d2e  jz      short loc_1800B9D4D
0x1800b9d30  lea     eax, [rsi+1]
0x1800b9d33  mov     ecx, eax
0x1800b9d35  test    eax, eax
0x1800b9d37  jz      short loc_1800B9D4D
0x1800b9d39  dec     rax
0x1800b9d3c  mov     [r15], rdi
0x1800b9d3f  mov     [r15+8], rax
0x1800b9d43  mov     [r15+10h], rcx
0x1800b9d47  mov     [rdi+rcx*2-2], r12w
0x1800b9d4d  mov     rdi, r12
0x1800b9d50  jmp     short loc_1800B9D67
0x1800b9d52  mov     rcx, rsi; pv
0x1800b9d55  mov     ebx, 8007007Ah
0x1800b9d5a  call    cs:__imp_CoTaskMemFree
0x1800b9d60  jmp     short loc_1800B9D67
0x1800b9d62  mov     ebx, 8007000Dh
0x1800b9d67  mov     rcx, rdi; pv
0x1800b9d6a  call    cs:__imp_CoTaskMemFree
0x1800b9d70  mov     rbp, [rsp+68h+arg_8]
0x1800b9d75  mov     eax, ebx
0x1800b9d77  mov     rbx, [rsp+68h+arg_0]
0x1800b9d7c  add     rsp, 40h
0x1800b9d80  pop     r15
0x1800b9d82  pop     r14
0x1800b9d84  pop     r12
0x1800b9d86  pop     rdi
0x1800b9d87  pop     rsi
0x1800b9d88  retn
```
