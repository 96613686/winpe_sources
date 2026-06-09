# SafeRegCreateKeyEx(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)

- ea: `0x180010a00`
- end: `0x180010db6`
- name: `?SafeRegCreateKeyEx@@YAJPEAUHKEY__@@PEBGKPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@Z`
- size: `950`
- prototype: `LSTATUS __fastcall(HKEY, const unsigned __int16 *, __int64, unsigned __int16 *, unsigned int, REGSAM samDesired, LPSECURITY_ATTRIBUTES lpSecurityAttributes, HKEY *)`
- caller_count: `4`
- callee_count: `7`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x18000f9d0`
- `0x1800101ac`
- `0x180010a00`
- `0x1800478e4`

## callees

- `0x180010a00`
- `0x180031960`
- `0x180031de0`
- `0x180031ff0`
- `0x180032058`
- `0x180047b98`
- `0x18004c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180010be6`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180010be6`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180010a6a`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180010a6a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180010d71`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180010d71`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180010aef`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180010aef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010aa9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010b33`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010aa9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010b33`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010b40`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010b8d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010c8d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010d32`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010d8b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010b40`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010b8d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010c8d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010d32`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010d8b`

## string_xrefs

- `0x180010ae8`: `SymbolicLinkValue`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LSTATUS __fastcall SafeRegCreateKeyEx(
        HKEY a1,
        const unsigned __int16 *a2,
        __int64 a3,
        unsigned __int16 *a4,
        unsigned int a5,
        REGSAM samDesired,
        LPSECURITY_ATTRIBUTES lpSecurityAttributes,
        HKEY *a8)
{
  const unsigned __int16 *v8; // rbx
  wchar_t *v10; // rax
  wchar_t *v11; // rdi
  BYTE *v12; // r14
  LSTATUS v13; // eax
  int v14; // edi
  LSTATUS v15; // eax
  LSTATUS v16; // edi
  CNtDeleteKey *v17; // rcx
  LSTATUS result; // eax
  int Key; // ebx
  int v20; // edi
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  DWORD dwDisposition; // [rsp+58h] [rbp-A8h] BYREF
  DWORD Type; // [rsp+5Ch] [rbp-A4h] BYREF
  DWORD cbData; // [rsp+60h] [rbp-A0h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-98h] BYREF
  HKEY v26; // [rsp+70h] [rbp-90h] BYREF
  BYTE v27[528]; // [rsp+80h] [rbp-80h] BYREF
  BYTE Data[528]; // [rsp+290h] [rbp+190h] BYREF

  v8 = a2;
  if ( a8 )
    *a8 = 0;
  if ( !a2 )
    return 87;
  v10 = wcschr(a2, 0x5Cu);
  v11 = v10;
  if ( !v10 )
  {
    v12 = (BYTE *)v8;
    goto LABEL_6;
  }
  if ( (unsigned __int64)(v10 - v8) >= 0x104 )
    return 87;
  _o_wcsncpy_s(v27, 260, v8);
  v12 = v27;
  v8 = v11 + 1;
LABEL_6:
  phkResult = 0;
  hKey = 0;
  v13 = RegOpenKeyExW(a1, (LPCWSTR)v12, 8u, samDesired, &phkResult);
  if ( v13 )
  {
    if ( v13 == 2 )
      v14 = 3;
    else
      v14 = (v13 != 5) + 4;
  }
  else
  {
    cbData = 520;
    v14 = 0;
    Type = 0;
    v15 = RegQueryValueExW(phkResult, L"SymbolicLinkValue", 0, &Type, Data, &cbData);
    if ( (!v15 || v15 == 234) && Type == 6 )
      v14 = 1;
    if ( v15 == 2 || v14 != 1 )
    {
      v26 = 0;
      v16 = RegOpenKeyExW(a1, (LPCWSTR)v12, 0, 0x20019u, &v26);
      RegCloseKey(v26);
      v14 = 2 - (v16 != 0);
    }
    hKey = phkResult;
  }
  v17 = (CNtDeleteKey *)*(unsigned int *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                        + 4LL);
  if ( dword_180064650 > (int)v17 )
  {
    Init_thread_header(&dword_180064650);
    if ( dword_180064650 == -1 )
    {
      atexit(SafeRegCreateKeyEx_::_2_::_dynamic_atexit_destructor_for__delKey__);
      Init_thread_footer(&dword_180064650);
    }
  }
  if ( v14 == 5 || !v14 )
    goto LABEL_14;
  v20 = v14 - 1;
  if ( !v20 )
  {
    if ( CNtDeleteKey::Init(v17) && qword_180064660 && !(unsigned int)qword_180064660(hKey) )
    {
      RegCloseKey(hKey);
      hKey = 0;
      dwDisposition = 0;
      goto LABEL_43;
    }
LABEL_14:
    if ( hKey )
      RegCloseKey(hKey);
    return 5;
  }
  if ( (unsigned int)(v20 - 1) > 1 )
    goto LABEL_14;
  dwDisposition = 0;
  if ( !hKey )
  {
LABEL_43:
    result = RegCreateKeyExW(a1, (LPCWSTR)v12, 0, 0, 0, samDesired, lpSecurityAttributes, &hKey, &dwDisposition);
    if ( result )
      return result;
    if ( dwDisposition != 1 )
    {
      RegCloseKey(hKey);
      return 5;
    }
    goto LABEL_25;
  }
  dwDisposition = 2;
LABEL_25:
  if ( v12 == (BYTE *)v8 )
  {
    if ( a8 )
      *a8 = hKey;
    return 0;
  }
  else
  {
    Key = SafeRegCreateKeyEx(hKey, v8, 0, 0, 0, samDesired, lpSecurityAttributes, a8, 0);
    RegCloseKey(hKey);
    return Key;
  }
}

```

## disassembly

```asm
0x180010a00  push    rbp
0x180010a02  push    rbx
0x180010a03  push    rsi
0x180010a04  push    r12
0x180010a06  push    r13
0x180010a08  push    r15
0x180010a0a  lea     rbp, [rsp-3B8h]
0x180010a12  sub     rsp, 4B8h
0x180010a19  mov     rax, cs:__security_cookie
0x180010a20  xor     rax, rsp
0x180010a23  mov     [rbp+3E0h+var_40], rax
0x180010a2a  mov     rsi, [rbp+3E0h+arg_38]
0x180010a31  xor     r12d, r12d
0x180010a34  mov     r13, [rbp+3E0h+arg_30]
0x180010a3b  mov     rbx, rdx
0x180010a3e  mov     r15, rcx
0x180010a41  test    rsi, rsi
0x180010a44  jz      short loc_180010A49
0x180010a46  mov     [rsi], r12
0x180010a49  mov     [rsp+4E0h+arg_10], rdi
0x180010a51  mov     [rsp+4E0h+var_30], r14
0x180010a59  test    rbx, rbx
0x180010a5c  jz      loc_180010C2F
0x180010a62  mov     edx, 5Ch ; '\'; Ch
0x180010a67  mov     rcx, rbx; Str
0x180010a6a  call    cs:__imp_wcschr
0x180010a70  mov     rdi, rax
0x180010a73  test    rax, rax
0x180010a76  jnz     loc_180010BC8
0x180010a7c  mov     r14, rbx
0x180010a7f  mov     [rsp+4E0h+var_478], r12
0x180010a84  lea     rax, [rsp+4E0h+var_478]
0x180010a89  mov     [rsp+4E0h+hKey], r12
0x180010a8e  mov     r8d, 8; ulOptions
0x180010a94  mov     r12d, [rbp+3E0h+samDesired]
0x180010a9b  mov     rdx, r14; lpSubKey
0x180010a9e  mov     r9d, r12d; samDesired
0x180010aa1  mov     [rsp+4E0h+phkResult], rax; phkResult
0x180010aa6  mov     rcx, r15; hKey
0x180010aa9  call    cs:__imp_RegOpenKeyExW
0x180010aaf  test    eax, eax
0x180010ab1  jnz     loc_180010C9A
0x180010ab7  mov     rcx, [rsp+4E0h+var_478]; hKey
0x180010abc  lea     rax, [rsp+4E0h+cbData]
0x180010ac1  mov     [rsp+4E0h+lpcbData], rax; lpcbData
0x180010ac6  lea     r9, [rsp+4E0h+Type]; lpType
0x180010acb  lea     rax, [rbp+3E0h+Data]
0x180010ad2  mov     [rsp+4E0h+cbData], 208h
0x180010ada  xor     edi, edi
0x180010adc  mov     [rsp+4E0h+phkResult], rax; lpData
0x180010ae1  xor     r8d, r8d; lpReserved
0x180010ae4  mov     [rsp+4E0h+Type], edi
0x180010ae8  lea     rdx, ValueName; "SymbolicLinkValue"
0x180010aef  call    cs:__imp_RegQueryValueExW
0x180010af5  test    eax, eax
0x180010af7  jz      loc_180010CBA
0x180010afd  cmp     eax, 0EAh
0x180010b02  jz      loc_180010CBA
0x180010b08  cmp     eax, 2
0x180010b0b  jnz     loc_180010CCC
0x180010b11  lea     rax, [rsp+4E0h+var_470]
0x180010b16  mov     [rsp+4E0h+var_470], 0
0x180010b1f  mov     r9d, 20019h; samDesired
0x180010b25  mov     [rsp+4E0h+phkResult], rax; phkResult
0x180010b2a  xor     r8d, r8d; ulOptions
0x180010b2d  mov     rdx, r14; lpSubKey
0x180010b30  mov     rcx, r15; hKey
0x180010b33  call    cs:__imp_RegOpenKeyExW
0x180010b39  mov     rcx, [rsp+4E0h+var_470]; hKey
0x180010b3e  mov     edi, eax
0x180010b40  call    cs:__imp_RegCloseKey
0x180010b46  neg     edi
0x180010b48  sbb     edi, edi
0x180010b4a  add     edi, 2
0x180010b4d  mov     rax, [rsp+4E0h+var_478]
0x180010b52  mov     [rsp+4E0h+hKey], rax
0x180010b57  mov     ecx, cs:_tls_index
0x180010b5d  mov     rax, gs:58h
0x180010b66  mov     edx, 4
0x180010b6b  mov     rax, [rax+rcx*8]
0x180010b6f  mov     ecx, [rdx+rax]; this
0x180010b72  cmp     cs:dword_180064650, ecx
0x180010b78  jg      short loc_180010BF9
0x180010b7a  cmp     edi, 5
0x180010b7d  jnz     loc_180010CDA
0x180010b83  mov     rcx, [rsp+4E0h+hKey]; hKey
0x180010b88  test    rcx, rcx
0x180010b8b  jz      short loc_180010B93
0x180010b8d  call    cs:__imp_RegCloseKey
0x180010b93  mov     eax, 5
0x180010b98  mov     r14, [rsp+4E0h+var_30]
0x180010ba0  mov     rdi, [rsp+4E0h+arg_10]
0x180010ba8  mov     rcx, [rbp+3E0h+var_40]
0x180010baf  xor     rcx, rsp; StackCookie
0x180010bb2  call    __security_check_cookie
0x180010bb7  add     rsp, 4B8h
0x180010bbe  pop     r15
0x180010bc0  pop     r13
0x180010bc2  pop     r12
0x180010bc4  pop     rsi
0x180010bc5  pop     rbx
0x180010bc6  pop     rbp
0x180010bc7  retn
0x180010bc8  mov     r9, rdi
0x180010bcb  sub     r9, rbx
0x180010bce  sar     r9, 1
0x180010bd1  cmp     r9, 104h
0x180010bd8  jnb     short loc_180010C2F
0x180010bda  mov     r8, rbx
0x180010bdd  lea     rcx, [rbp+3E0h+var_460]
0x180010be1  mov     edx, 104h
0x180010be6  call    cs:__imp__o_wcsncpy_s
0x180010bec  lea     r14, [rbp+3E0h+var_460]
0x180010bf0  lea     rbx, [rdi+2]
0x180010bf4  jmp     loc_180010A7F
0x180010bf9  lea     rcx, dword_180064650
0x180010c00  call    _Init_thread_header
0x180010c05  cmp     cs:dword_180064650, 0FFFFFFFFh
0x180010c0c  jnz     loc_180010B7A
0x180010c12  lea     rcx, _SafeRegCreateKeyEx____2____dynamic_atexit_destructor_for__delKey__; void (__cdecl *)()
0x180010c19  call    atexit
0x180010c1e  lea     rcx, dword_180064650
0x180010c25  call    _Init_thread_footer
0x180010c2a  jmp     loc_180010B7A
0x180010c2f  mov     eax, 57h ; 'W'
0x180010c34  jmp     loc_180010B98
0x180010c39  xor     ecx, ecx
0x180010c3b  mov     [rsp+4E0h+dwDisposition], ecx
0x180010c3f  cmp     [rsp+4E0h+hKey], rcx
0x180010c44  jz      loc_180010D43
0x180010c4a  mov     [rsp+4E0h+dwDisposition], 2
0x180010c52  cmp     r14, rbx
0x180010c55  jz      loc_180010DA2
0x180010c5b  mov     [rsp+4E0h+lpdwDisposition], rcx; unsigned int *
0x180010c60  xor     r9d, r9d; unsigned __int16 *
0x180010c63  mov     [rsp+4E0h+var_4A8], rsi; HKEY *
0x180010c68  xor     r8d, r8d; unsigned int
0x180010c6b  mov     [rsp+4E0h+lpSecurityAttributes], r13; LPSECURITY_ATTRIBUTES
0x180010c70  mov     rdx, rbx; unsigned __int16 *
0x180010c73  mov     dword ptr [rsp+4E0h+lpcbData], r12d; samDesired
0x180010c78  mov     dword ptr [rsp+4E0h+phkResult], ecx; unsigned int
0x180010c7c  mov     rcx, [rsp+4E0h+hKey]; HKEY
0x180010c81  call    ?SafeRegCreateKeyEx@@YAJPEAUHKEY__@@PEBGKPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@Z; SafeRegCreateKeyEx(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x180010c86  mov     rcx, [rsp+4E0h+hKey]; hKey
0x180010c8b  mov     ebx, eax
0x180010c8d  call    cs:__imp_RegCloseKey
0x180010c93  mov     eax, ebx
0x180010c95  jmp     loc_180010B98
0x180010c9a  cmp     eax, 2
0x180010c9d  jz      short loc_180010CB0
0x180010c9f  xor     edi, edi
0x180010ca1  cmp     eax, 5
0x180010ca4  setnz   dil
0x180010ca8  add     edi, 4
0x180010cab  jmp     loc_180010B57
0x180010cb0  mov     edi, 3
0x180010cb5  jmp     loc_180010B57
0x180010cba  cmp     [rsp+4E0h+Type], 6
0x180010cbf  mov     ecx, 1
0x180010cc4  cmovz   edi, ecx
0x180010cc7  jmp     loc_180010B08
0x180010ccc  cmp     edi, 1
0x180010ccf  jz      loc_180010B4D
0x180010cd5  jmp     loc_180010B11
0x180010cda  test    edi, edi
0x180010cdc  jz      loc_180010B83
0x180010ce2  sub     edi, 1
0x180010ce5  jz      short loc_180010CFE
0x180010ce7  sub     edi, 1
0x180010cea  jz      loc_180010C39
0x180010cf0  cmp     edi, 1
0x180010cf3  jnz     loc_180010B83
0x180010cf9  jmp     loc_180010C39
0x180010cfe  call    ?Init@CNtDeleteKey@@QEAA_NXZ; CNtDeleteKey::Init(void)
0x180010d03  test    al, al
0x180010d05  jz      loc_180010B83
0x180010d0b  mov     rax, cs:qword_180064660
0x180010d12  test    rax, rax
0x180010d15  jz      loc_180010B83
0x180010d1b  mov     rcx, [rsp+4E0h+hKey]
0x180010d20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d25  test    eax, eax
0x180010d27  jnz     loc_180010B83
0x180010d2d  mov     rcx, [rsp+4E0h+hKey]; hKey
0x180010d32  call    cs:__imp_RegCloseKey
0x180010d38  xor     ecx, ecx
0x180010d3a  mov     [rsp+4E0h+hKey], rcx
0x180010d3f  mov     [rsp+4E0h+dwDisposition], ecx
0x180010d43  lea     rax, [rsp+4E0h+dwDisposition]
0x180010d48  xor     r9d, r9d; lpClass
0x180010d4b  mov     [rsp+4E0h+lpdwDisposition], rax; lpdwDisposition
0x180010d50  xor     r8d, r8d; Reserved
0x180010d53  lea     rax, [rsp+4E0h+hKey]
0x180010d58  mov     rdx, r14; lpSubKey
0x180010d5b  mov     [rsp+4E0h+var_4A8], rax; phkResult
0x180010d60  mov     [rsp+4E0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x180010d65  mov     dword ptr [rsp+4E0h+lpcbData], r12d; samDesired
0x180010d6a  mov     dword ptr [rsp+4E0h+phkResult], ecx; dwOptions
0x180010d6e  mov     rcx, r15; hKey
0x180010d71  call    cs:__imp_RegCreateKeyExW
0x180010d77  test    eax, eax
0x180010d79  jnz     loc_180010B98
0x180010d7f  cmp     [rsp+4E0h+dwDisposition], 1
0x180010d84  jz      short loc_180010D9B
0x180010d86  mov     rcx, [rsp+4E0h+hKey]; hKey
0x180010d8b  call    cs:__imp_RegCloseKey
0x180010d91  mov     eax, 5
0x180010d96  jmp     loc_180010B98
0x180010d9b  xor     ecx, ecx
0x180010d9d  jmp     loc_180010C52
0x180010da2  test    rsi, rsi
0x180010da5  jz      short loc_180010DAF
0x180010da7  mov     rax, [rsp+4E0h+hKey]
0x180010dac  mov     [rsi], rax
0x180010daf  xor     eax, eax
0x180010db1  jmp     loc_180010B98
```
