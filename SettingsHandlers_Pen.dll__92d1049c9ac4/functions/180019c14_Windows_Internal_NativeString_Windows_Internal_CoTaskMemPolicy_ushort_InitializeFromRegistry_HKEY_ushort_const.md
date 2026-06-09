# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_InitializeFromRegistry(HKEY__ *,ushort const *,bool)

- ea: `0x180019c14`
- end: `0x180019dc6`
- name: `?_InitializeFromRegistry@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEAUHKEY__@@PEBG_N@Z`
- size: `434`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180016400`

## callees

- `0x180019a40`
- `0x180019c14`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019d4c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019d97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019da7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019d4c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019d97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019da7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019ca7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019d17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019ca7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019d17`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180019c64`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180019cd6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180019c64`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180019cd6`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180019d06`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180019d35`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180019d06`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180019d35`

## string_xrefs

- `0x180019c5a`: `CustomProtocol`
- `0x180019cc7`: `CustomProtocol`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_InitializeFromRegistry(
        BYTE **a1,
        HKEY a2,
        __int64 a3)
{
  BYTE *lpData; // rdi
  LSTATUS v6; // eax
  signed int v7; // ebx
  LSTATUS v8; // eax
  __int64 v9; // rsi
  DWORD v10; // eax
  DWORD v11; // ebp
  WCHAR *v12; // rax
  WCHAR *v13; // rsi
  DWORD v14; // eax
  DWORD v15; // r14d
  __int64 v16; // rax
  DWORD Type; // [rsp+70h] [rbp+18h] BYREF
  int v19; // [rsp+74h] [rbp+1Ch]
  SIZE_T cb; // [rsp+78h] [rbp+20h] BYREF

  v19 = HIDWORD(a3);
  Type = 0;
  LODWORD(cb) = 0;
  lpData = 0;
  v6 = RegQueryValueExW(a2, L"CustomProtocol", 0, &Type, 0, (LPDWORD)&cb);
  v7 = v6;
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x80070000;
  if ( v7 >= 0 )
  {
    if ( Type - 1 > 1 || !(_DWORD)cb || (cb & 1) != 0 )
      goto LABEL_24;
    lpData = (BYTE *)CoTaskMemAlloc((unsigned int)cb);
    if ( !lpData )
    {
LABEL_14:
      v7 = -2147024882;
      goto LABEL_25;
    }
    v8 = RegQueryValueExW(a2, L"CustomProtocol", 0, &Type, lpData, (LPDWORD)&cb);
    v7 = v8;
    if ( v8 > 0 )
      v7 = (unsigned __int16)v8 | 0x80070000;
    if ( v7 >= 0 )
    {
      v9 = ((unsigned int)cb >> 1) - 1;
      if ( Type == 2 )
      {
        v10 = ExpandEnvironmentStringsW((LPCWSTR)lpData, 0, 0);
        v11 = v10;
        if ( v10 )
        {
          v12 = (WCHAR *)CoTaskMemAlloc(2LL * v10);
          v13 = v12;
          if ( !v12 )
            goto LABEL_14;
          v14 = ExpandEnvironmentStringsW((LPCWSTR)lpData, v12, v11);
          v15 = v14;
          if ( !v14 || v14 > v11 )
          {
            v7 = -2147024774;
            CoTaskMemFree(v13);
            goto LABEL_25;
          }
          v7 = 0;
          CoTaskMemFree(lpData);
          lpData = (BYTE *)v13;
          v9 = v15 - 1;
        }
      }
      if ( !*(_WORD *)&lpData[2 * v9] )
      {
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(a1);
        if ( lpData )
        {
          v16 = (unsigned int)(v9 + 1);
          if ( (_DWORD)v9 != -1 )
          {
            *a1 = lpData;
            a1[1] = (BYTE *)(v16 - 1);
            a1[2] = (BYTE *)(unsigned int)v16;
            *(_WORD *)&lpData[2 * (unsigned int)v16 - 2] = 0;
          }
        }
        lpData = 0;
        goto LABEL_25;
      }
LABEL_24:
      v7 = -2147024883;
    }
  }
LABEL_25:
  CoTaskMemFree(lpData);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180019c14  mov     r11, rsp
0x180019c17  mov     [r11+8], rbx
0x180019c1b  mov     [r11+10h], rbp
0x180019c1f  mov     [r11+20h], r9b
0x180019c23  mov     [r11+18h], r8
0x180019c27  push    rsi
0x180019c28  push    rdi
0x180019c29  push    r12
0x180019c2b  push    r14
0x180019c2d  push    r15
0x180019c2f  sub     rsp, 30h
0x180019c33  xor     r12d, r12d
0x180019c36  lea     rax, [r11+20h]
0x180019c3a  mov     rsi, rdx
0x180019c3d  mov     [r11-30h], rax
0x180019c41  mov     r15, rcx
0x180019c44  mov     [r11-38h], r12
0x180019c48  mov     rcx, rsi; hKey
0x180019c4b  mov     [r11+18h], r12d
0x180019c4f  lea     r9, [r11+18h]; lpType
0x180019c53  mov     [r11+20h], r12d
0x180019c57  xor     r8d, r8d; lpReserved
0x180019c5a  lea     rdx, ValueName; "CustomProtocol"
0x180019c61  mov     edi, r12d
0x180019c64  call    cs:__imp_RegQueryValueExW
0x180019c6a  mov     ebx, eax
0x180019c6c  mov     ebp, 80070000h
0x180019c71  test    eax, eax
0x180019c73  jle     short loc_180019C7A
0x180019c75  movzx   ebx, ax
0x180019c78  or      ebx, ebp
0x180019c7a  test    ebx, ebx
0x180019c7c  js      loc_180019DA4
0x180019c82  mov     eax, [rsp+58h+Type]
0x180019c86  dec     eax
0x180019c88  cmp     eax, 1
0x180019c8b  ja      loc_180019D9F
0x180019c91  mov     eax, dword ptr [rsp+58h+cb]
0x180019c95  test    eax, eax
0x180019c97  jz      loc_180019D9F
0x180019c9d  test    al, 1
0x180019c9f  jnz     loc_180019D9F
0x180019ca5  mov     ecx, eax; cb
0x180019ca7  call    cs:__imp_CoTaskMemAlloc
0x180019cad  mov     rdi, rax
0x180019cb0  test    rax, rax
0x180019cb3  jz      short loc_180019D25
0x180019cb5  lea     rax, [rsp+58h+cb]
0x180019cba  xor     r8d, r8d; lpReserved
0x180019cbd  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180019cc2  lea     r9, [rsp+58h+Type]; lpType
0x180019cc7  lea     rdx, ValueName; "CustomProtocol"
0x180019cce  mov     [rsp+58h+lpData], rdi; lpData
0x180019cd3  mov     rcx, rsi; hKey
0x180019cd6  call    cs:__imp_RegQueryValueExW
0x180019cdc  mov     ebx, eax
0x180019cde  test    eax, eax
0x180019ce0  jle     short loc_180019CE7
0x180019ce2  movzx   ebx, ax
0x180019ce5  or      ebx, ebp
0x180019ce7  test    ebx, ebx
0x180019ce9  js      loc_180019DA4
0x180019cef  mov     esi, dword ptr [rsp+58h+cb]
0x180019cf3  shr     esi, 1
0x180019cf5  dec     esi
0x180019cf7  cmp     [rsp+58h+Type], 2
0x180019cfc  jnz     short loc_180019D59
0x180019cfe  xor     r8d, r8d; nSize
0x180019d01  xor     edx, edx; lpDst
0x180019d03  mov     rcx, rdi; lpSrc
0x180019d06  call    cs:__imp_ExpandEnvironmentStringsW
0x180019d0c  mov     ebp, eax
0x180019d0e  test    eax, eax
0x180019d10  jz      short loc_180019D59
0x180019d12  mov     ecx, ebp
0x180019d14  add     rcx, rcx; cb
0x180019d17  call    cs:__imp_CoTaskMemAlloc
0x180019d1d  mov     rsi, rax
0x180019d20  test    rax, rax
0x180019d23  jnz     short loc_180019D2C
0x180019d25  mov     ebx, 8007000Eh
0x180019d2a  jmp     short loc_180019DA4
0x180019d2c  mov     r8d, ebp; nSize
0x180019d2f  mov     rdx, rsi; lpDst
0x180019d32  mov     rcx, rdi; lpSrc
0x180019d35  call    cs:__imp_ExpandEnvironmentStringsW
0x180019d3b  mov     r14d, eax
0x180019d3e  test    eax, eax
0x180019d40  jz      short loc_180019D8F
0x180019d42  cmp     eax, ebp
0x180019d44  ja      short loc_180019D8F
0x180019d46  mov     rcx, rdi; pv
0x180019d49  mov     ebx, r12d
0x180019d4c  call    cs:__imp_CoTaskMemFree
0x180019d52  mov     rdi, rsi
0x180019d55  lea     esi, [r14-1]
0x180019d59  cmp     [rdi+rsi*2], r12w
0x180019d5e  jnz     short loc_180019D9F
0x180019d60  mov     rcx, r15
0x180019d63  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180019d68  test    rdi, rdi
0x180019d6b  jz      short loc_180019D8A
0x180019d6d  lea     eax, [rsi+1]
0x180019d70  mov     ecx, eax
0x180019d72  test    eax, eax
0x180019d74  jz      short loc_180019D8A
0x180019d76  dec     rax
0x180019d79  mov     [r15], rdi
0x180019d7c  mov     [r15+8], rax
0x180019d80  mov     [r15+10h], rcx
0x180019d84  mov     [rdi+rcx*2-2], r12w
0x180019d8a  mov     rdi, r12
0x180019d8d  jmp     short loc_180019DA4
0x180019d8f  mov     rcx, rsi; pv
0x180019d92  mov     ebx, 8007007Ah
0x180019d97  call    cs:__imp_CoTaskMemFree
0x180019d9d  jmp     short loc_180019DA4
0x180019d9f  mov     ebx, 8007000Dh
0x180019da4  mov     rcx, rdi; pv
0x180019da7  call    cs:__imp_CoTaskMemFree
0x180019dad  mov     rbp, [rsp+58h+arg_8]
0x180019db2  mov     eax, ebx
0x180019db4  mov     rbx, [rsp+58h+arg_0]
0x180019db9  add     rsp, 30h
0x180019dbd  pop     r15
0x180019dbf  pop     r14
0x180019dc1  pop     r12
0x180019dc3  pop     rdi
0x180019dc4  pop     rsi
0x180019dc5  retn
```
