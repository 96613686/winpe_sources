# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_InitializeFromRegistry(HKEY__ *,ushort const *,bool)

- ea: `0x180009be0`
- end: `0x180009da9`
- name: `?_InitializeFromRegistry@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEAUHKEY__@@PEBG_N@Z`
- size: `457`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800083d0`
- `0x18000b52c`

## callees

- `0x180009be0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180009c2b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180009ca1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180009c2b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180009ca1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009d1e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009d3a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009d7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009d8a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009d1e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009d3a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009d7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009d8a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009c73`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009ce6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009c73`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009ce6`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180009cd5`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180009d07`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180009cd5`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180009d07`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_InitializeFromRegistry(
        __int64 a1,
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
  DWORD v16; // r15d
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
      goto LABEL_26;
    lpData = (BYTE *)CoTaskMemAlloc((unsigned int)cb);
    if ( !lpData )
    {
LABEL_14:
      v8 = -2147024882;
      goto LABEL_27;
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
            goto LABEL_27;
          }
          v8 = 0;
          CoTaskMemFree(lpData);
          lpData = (BYTE *)v14;
          v10 = v16 - 1;
        }
      }
      if ( !*(_WORD *)&lpData[2 * v10] )
      {
        if ( *(_QWORD *)a1 )
        {
          CoTaskMemFree(*(LPVOID *)a1);
          *(_QWORD *)a1 = 0;
        }
        *(_QWORD *)(a1 + 8) = 0;
        *(_QWORD *)(a1 + 16) = 0;
        if ( lpData )
        {
          v17 = (unsigned int)(v10 + 1);
          if ( (_DWORD)v10 != -1 )
          {
            *(_QWORD *)a1 = lpData;
            *(_QWORD *)(a1 + 8) = v17 - 1;
            *(_QWORD *)(a1 + 16) = (unsigned int)v17;
            *(_WORD *)&lpData[2 * (unsigned int)v17 - 2] = 0;
          }
        }
        lpData = 0;
        goto LABEL_27;
      }
LABEL_26:
      v8 = -2147024883;
    }
  }
LABEL_27:
  CoTaskMemFree(lpData);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180009be0  mov     r11, rsp
0x180009be3  mov     [r11+8], rbx
0x180009be7  mov     [r11+10h], rbp
0x180009beb  mov     [r11+20h], r9b
0x180009bef  push    rsi
0x180009bf0  push    rdi
0x180009bf1  push    r12
0x180009bf3  push    r14
0x180009bf5  push    r15
0x180009bf7  sub     rsp, 40h
0x180009bfb  xor     r12d, r12d
0x180009bfe  lea     rax, [r11+20h]
0x180009c02  mov     rsi, r8
0x180009c05  mov     [r11-40h], rax
0x180009c09  mov     rbp, rdx
0x180009c0c  mov     [r11-48h], r12
0x180009c10  mov     r14, rcx
0x180009c13  mov     [r11-38h], r12d
0x180009c17  mov     rdx, rsi; lpValueName
0x180009c1a  mov     [r11+20h], r12d
0x180009c1e  mov     rcx, rbp; hKey
0x180009c21  lea     r9, [r11-38h]; lpType
0x180009c25  xor     r8d, r8d; lpReserved
0x180009c28  mov     edi, r12d
0x180009c2b  call    cs:__imp_RegQueryValueExW
0x180009c31  mov     ebx, eax
0x180009c33  mov     r15d, 80070000h
0x180009c39  test    eax, eax
0x180009c3b  jle     short loc_180009C43
0x180009c3d  movzx   ebx, ax
0x180009c40  or      ebx, r15d
0x180009c43  test    ebx, ebx
0x180009c45  js      loc_180009D87
0x180009c4b  mov     eax, [rsp+68h+Type]
0x180009c4f  dec     eax
0x180009c51  cmp     eax, 1
0x180009c54  ja      loc_180009D82
0x180009c5a  mov     eax, dword ptr [rsp+68h+cb]
0x180009c61  test    eax, eax
0x180009c63  jz      loc_180009D82
0x180009c69  test    al, 1
0x180009c6b  jnz     loc_180009D82
0x180009c71  mov     ecx, eax; cb
0x180009c73  call    cs:__imp_CoTaskMemAlloc
0x180009c79  mov     rdi, rax
0x180009c7c  test    rax, rax
0x180009c7f  jz      short loc_180009CF4
0x180009c81  lea     rax, [rsp+68h+cb]
0x180009c89  xor     r8d, r8d; lpReserved
0x180009c8c  mov     [rsp+68h+lpcbData], rax; lpcbData
0x180009c91  lea     r9, [rsp+68h+Type]; lpType
0x180009c96  mov     rdx, rsi; lpValueName
0x180009c99  mov     [rsp+68h+lpData], rdi; lpData
0x180009c9e  mov     rcx, rbp; hKey
0x180009ca1  call    cs:__imp_RegQueryValueExW
0x180009ca7  mov     ebx, eax
0x180009ca9  test    eax, eax
0x180009cab  jle     short loc_180009CB3
0x180009cad  movzx   ebx, ax
0x180009cb0  or      ebx, r15d
0x180009cb3  test    ebx, ebx
0x180009cb5  js      loc_180009D87
0x180009cbb  mov     esi, dword ptr [rsp+68h+cb]
0x180009cc2  shr     esi, 1
0x180009cc4  dec     esi
0x180009cc6  cmp     [rsp+68h+Type], 2
0x180009ccb  jnz     short loc_180009D2B
0x180009ccd  xor     r8d, r8d; nSize
0x180009cd0  xor     edx, edx; lpDst
0x180009cd2  mov     rcx, rdi; lpSrc
0x180009cd5  call    cs:__imp_ExpandEnvironmentStringsW
0x180009cdb  mov     ebp, eax
0x180009cdd  test    eax, eax
0x180009cdf  jz      short loc_180009D2B
0x180009ce1  mov     ecx, ebp
0x180009ce3  add     rcx, rcx; cb
0x180009ce6  call    cs:__imp_CoTaskMemAlloc
0x180009cec  mov     rsi, rax
0x180009cef  test    rax, rax
0x180009cf2  jnz     short loc_180009CFE
0x180009cf4  mov     ebx, 8007000Eh
0x180009cf9  jmp     loc_180009D87
0x180009cfe  mov     r8d, ebp; nSize
0x180009d01  mov     rdx, rsi; lpDst
0x180009d04  mov     rcx, rdi; lpSrc
0x180009d07  call    cs:__imp_ExpandEnvironmentStringsW
0x180009d0d  mov     r15d, eax
0x180009d10  test    eax, eax
0x180009d12  jz      short loc_180009D72
0x180009d14  cmp     eax, ebp
0x180009d16  ja      short loc_180009D72
0x180009d18  mov     rcx, rdi; pv
0x180009d1b  mov     ebx, r12d
0x180009d1e  call    cs:__imp_CoTaskMemFree
0x180009d24  mov     rdi, rsi
0x180009d27  lea     esi, [r15-1]
0x180009d2b  cmp     [rdi+rsi*2], r12w
0x180009d30  jnz     short loc_180009D82
0x180009d32  mov     rcx, [r14]; pv
0x180009d35  test    rcx, rcx
0x180009d38  jz      short loc_180009D43
0x180009d3a  call    cs:__imp_CoTaskMemFree
0x180009d40  mov     [r14], r12
0x180009d43  mov     [r14+8], r12
0x180009d47  mov     [r14+10h], r12
0x180009d4b  test    rdi, rdi
0x180009d4e  jz      short loc_180009D6D
0x180009d50  lea     eax, [rsi+1]
0x180009d53  mov     ecx, eax
0x180009d55  test    eax, eax
0x180009d57  jz      short loc_180009D6D
0x180009d59  dec     rax
0x180009d5c  mov     [r14], rdi
0x180009d5f  mov     [r14+8], rax
0x180009d63  mov     [r14+10h], rcx
0x180009d67  mov     [rdi+rcx*2-2], r12w
0x180009d6d  mov     rdi, r12
0x180009d70  jmp     short loc_180009D87
0x180009d72  mov     rcx, rsi; pv
0x180009d75  mov     ebx, 8007007Ah
0x180009d7a  call    cs:__imp_CoTaskMemFree
0x180009d80  jmp     short loc_180009D87
0x180009d82  mov     ebx, 8007000Dh
0x180009d87  mov     rcx, rdi; pv
0x180009d8a  call    cs:__imp_CoTaskMemFree
0x180009d90  mov     rbp, [rsp+68h+arg_8]
0x180009d95  mov     eax, ebx
0x180009d97  mov     rbx, [rsp+68h+arg_0]
0x180009d9c  add     rsp, 40h
0x180009da0  pop     r15
0x180009da2  pop     r14
0x180009da4  pop     r12
0x180009da6  pop     rdi
0x180009da7  pop     rsi
0x180009da8  retn
```
