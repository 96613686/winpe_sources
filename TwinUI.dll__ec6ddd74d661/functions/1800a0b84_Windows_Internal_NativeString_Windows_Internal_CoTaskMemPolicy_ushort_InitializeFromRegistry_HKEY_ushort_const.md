# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_InitializeFromRegistry(HKEY__ *,ushort const *,bool)

- ea: `0x1800a0b84`
- end: `0x1800a0d77`
- name: `?_InitializeFromRegistry@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEAUHKEY__@@PEBG_N@Z`
- size: `499`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180062eac`

## callees

- `0x180041f54`
- `0x1800a0b84`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a0bcf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a0c55`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a0bcf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a0c55`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800a0c8f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800a0ccd`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800a0c8f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800a0ccd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a0cea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a0d3b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a0d51`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a0cea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a0d3b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a0d51`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a0c1d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a0ca6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a0c1d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a0ca6`

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
0x1800a0b84  mov     r11, rsp
0x1800a0b87  mov     [r11+8], rbx
0x1800a0b8b  mov     [r11+10h], rbp
0x1800a0b8f  mov     [r11+20h], r9b
0x1800a0b93  push    rsi
0x1800a0b94  push    rdi
0x1800a0b95  push    r12
0x1800a0b97  push    r14
0x1800a0b99  push    r15
0x1800a0b9b  sub     rsp, 40h
0x1800a0b9f  xor     r12d, r12d
0x1800a0ba2  lea     rax, [r11+20h]
0x1800a0ba6  mov     rsi, r8
0x1800a0ba9  mov     [r11-40h], rax
0x1800a0bad  mov     rbp, rdx
0x1800a0bb0  mov     [r11-48h], r12
0x1800a0bb4  mov     r15, rcx
0x1800a0bb7  mov     [r11-38h], r12d
0x1800a0bbb  mov     rdx, rsi; lpValueName
0x1800a0bbe  mov     [r11+20h], r12d
0x1800a0bc2  mov     rcx, rbp; hKey
0x1800a0bc5  lea     r9, [r11-38h]; lpType
0x1800a0bc9  xor     r8d, r8d; lpReserved
0x1800a0bcc  mov     edi, r12d
0x1800a0bcf  call    cs:__imp_RegQueryValueExW
0x1800a0bd6  nop     dword ptr [rax+rax+00h]
0x1800a0bdb  mov     ebx, eax
0x1800a0bdd  mov     r14d, 80070000h
0x1800a0be3  test    eax, eax
0x1800a0be5  jle     short loc_1800A0BED
0x1800a0be7  movzx   ebx, ax
0x1800a0bea  or      ebx, r14d
0x1800a0bed  test    ebx, ebx
0x1800a0bef  js      loc_1800A0D4E
0x1800a0bf5  mov     eax, [rsp+68h+Type]
0x1800a0bf9  dec     eax
0x1800a0bfb  cmp     eax, 1
0x1800a0bfe  ja      loc_1800A0D49
0x1800a0c04  mov     eax, dword ptr [rsp+68h+cb]
0x1800a0c0b  test    eax, eax
0x1800a0c0d  jz      loc_1800A0D49
0x1800a0c13  test    al, 1
0x1800a0c15  jnz     loc_1800A0D49
0x1800a0c1b  mov     ecx, eax; cb
0x1800a0c1d  call    cs:__imp_CoTaskMemAlloc
0x1800a0c24  nop     dword ptr [rax+rax+00h]
0x1800a0c29  mov     rdi, rax
0x1800a0c2c  test    rax, rax
0x1800a0c2f  jz      loc_1800A0CBA
0x1800a0c35  lea     rax, [rsp+68h+cb]
0x1800a0c3d  xor     r8d, r8d; lpReserved
0x1800a0c40  mov     [rsp+68h+lpcbData], rax; lpcbData
0x1800a0c45  lea     r9, [rsp+68h+Type]; lpType
0x1800a0c4a  mov     rdx, rsi; lpValueName
0x1800a0c4d  mov     [rsp+68h+lpData], rdi; lpData
0x1800a0c52  mov     rcx, rbp; hKey
0x1800a0c55  call    cs:__imp_RegQueryValueExW
0x1800a0c5c  nop     dword ptr [rax+rax+00h]
0x1800a0c61  mov     ebx, eax
0x1800a0c63  test    eax, eax
0x1800a0c65  jle     short loc_1800A0C6D
0x1800a0c67  movzx   ebx, ax
0x1800a0c6a  or      ebx, r14d
0x1800a0c6d  test    ebx, ebx
0x1800a0c6f  js      loc_1800A0D4E
0x1800a0c75  mov     esi, dword ptr [rsp+68h+cb]
0x1800a0c7c  shr     esi, 1
0x1800a0c7e  dec     esi
0x1800a0c80  cmp     [rsp+68h+Type], 2
0x1800a0c85  jnz     short loc_1800A0CFD
0x1800a0c87  xor     r8d, r8d; nSize
0x1800a0c8a  xor     edx, edx; lpDst
0x1800a0c8c  mov     rcx, rdi; lpSrc
0x1800a0c8f  call    cs:__imp_ExpandEnvironmentStringsW
0x1800a0c96  nop     dword ptr [rax+rax+00h]
0x1800a0c9b  mov     ebp, eax
0x1800a0c9d  test    eax, eax
0x1800a0c9f  jz      short loc_1800A0CFD
0x1800a0ca1  mov     ecx, ebp
0x1800a0ca3  add     rcx, rcx; cb
0x1800a0ca6  call    cs:__imp_CoTaskMemAlloc
0x1800a0cad  nop     dword ptr [rax+rax+00h]
0x1800a0cb2  mov     rsi, rax
0x1800a0cb5  test    rax, rax
0x1800a0cb8  jnz     short loc_1800A0CC4
0x1800a0cba  mov     ebx, 8007000Eh
0x1800a0cbf  jmp     loc_1800A0D4E
0x1800a0cc4  mov     r8d, ebp; nSize
0x1800a0cc7  mov     rdx, rsi; lpDst
0x1800a0cca  mov     rcx, rdi; lpSrc
0x1800a0ccd  call    cs:__imp_ExpandEnvironmentStringsW
0x1800a0cd4  nop     dword ptr [rax+rax+00h]
0x1800a0cd9  mov     r14d, eax
0x1800a0cdc  test    eax, eax
0x1800a0cde  jz      short loc_1800A0D33
0x1800a0ce0  cmp     eax, ebp
0x1800a0ce2  ja      short loc_1800A0D33
0x1800a0ce4  mov     rcx, rdi; pv
0x1800a0ce7  mov     ebx, r12d
0x1800a0cea  call    cs:__imp_CoTaskMemFree
0x1800a0cf1  nop     dword ptr [rax+rax+00h]
0x1800a0cf6  mov     rdi, rsi
0x1800a0cf9  lea     esi, [r14-1]
0x1800a0cfd  cmp     [rdi+rsi*2], r12w
0x1800a0d02  jnz     short loc_1800A0D49
0x1800a0d04  mov     rcx, r15
0x1800a0d07  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800a0d0c  test    rdi, rdi
0x1800a0d0f  jz      short loc_1800A0D2E
0x1800a0d11  lea     eax, [rsi+1]
0x1800a0d14  mov     ecx, eax
0x1800a0d16  test    eax, eax
0x1800a0d18  jz      short loc_1800A0D2E
0x1800a0d1a  dec     rax
0x1800a0d1d  mov     [r15], rdi
0x1800a0d20  mov     [r15+8], rax
0x1800a0d24  mov     [r15+10h], rcx
0x1800a0d28  mov     [rdi+rcx*2-2], r12w
0x1800a0d2e  mov     rdi, r12
0x1800a0d31  jmp     short loc_1800A0D4E
0x1800a0d33  mov     rcx, rsi; pv
0x1800a0d36  mov     ebx, 8007007Ah
0x1800a0d3b  call    cs:__imp_CoTaskMemFree
0x1800a0d42  nop     dword ptr [rax+rax+00h]
0x1800a0d47  jmp     short loc_1800A0D4E
0x1800a0d49  mov     ebx, 8007000Dh
0x1800a0d4e  mov     rcx, rdi; pv
0x1800a0d51  call    cs:__imp_CoTaskMemFree
0x1800a0d58  nop     dword ptr [rax+rax+00h]
0x1800a0d5d  mov     rbp, [rsp+68h+arg_8]
0x1800a0d62  mov     eax, ebx
0x1800a0d64  mov     rbx, [rsp+68h+arg_0]
0x1800a0d69  add     rsp, 40h
0x1800a0d6d  pop     r15
0x1800a0d6f  pop     r14
0x1800a0d71  pop     r12
0x1800a0d73  pop     rdi
0x1800a0d74  pop     rsi
0x1800a0d75  retn
```
