# CbsRegCreateKeyExW(HKEY__ *,wchar_t const *,ulong,wchar_t *,ulong,ulong,_SECURITY_ATTRIBUTES * const,HKEY__ * *,ulong *)

- ea: `0x140019c2c`
- end: `0x140019d7d`
- name: `?CbsRegCreateKeyExW@@YAKPEAUHKEY__@@PEB_WKPEA_WKKQEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@Z`
- size: `337`
- prototype: `LSTATUS __fastcall(HKEY hKey, LPCWSTR lpSubKey, __int64, wchar_t *, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *const, HKEY *phkResult)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001acbc`

## callees

- `0x1400023e0`
- `0x140019c2c`
- `0x140022498`
- `0x140026498`
- `0x1400267e4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140019d58`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140019d58`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyTransactedW` at `0x140019d2a`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyTransactedW` at `0x140019d2a`

## pseudocode

```c
LSTATUS __fastcall CbsRegCreateKeyExW(
        HKEY hKey,
        LPCWSTR lpSubKey,
        __int64 a3,
        wchar_t *a4,
        unsigned int a5,
        unsigned int a6,
        struct _SECURITY_ATTRIBUTES *const a7,
        HKEY *phkResult)
{
  bool *v11; // rdx
  int CanSetSystemOwner; // eax
  struct _SECURITY_DESCRIPTOR **v13; // rdx
  struct _SECURITY_ATTRIBUTES *lpSecurityAttributes; // rax
  _BYTE v15[8]; // [rsp+60h] [rbp-31h] BYREF
  __int64 v16; // [rsp+68h] [rbp-29h] BYREF
  HANDLE hTransaction; // [rsp+70h] [rbp-21h] BYREF
  __int128 v18; // [rsp+78h] [rbp-19h]
  __int64 v19; // [rsp+88h] [rbp-9h]
  __int128 v20; // [rsp+90h] [rbp-1h] BYREF
  __int64 v21; // [rsp+A0h] [rbp+Fh]

  if ( !lpSubKey )
    return 87;
  if ( !phkResult )
    return -2147467261;
  hTransaction = 0;
  CbsGetCurrentTransaction(&hTransaction);
  v21 = 0;
  v20 = 0;
  v15[0] = 0;
  CanSetSystemOwner = Windows::WCP::Implementation::Rtl::CanSetSystemOwner(
                        (Windows::WCP::Implementation::Rtl *)v15,
                        v11);
  if ( CanSetSystemOwner < 0 )
    return CanSetSystemOwner | 0x10000000;
  lpSecurityAttributes = 0;
  if ( v15[0] )
  {
    v16 = 0;
    CanSetSystemOwner = Windows::WCP::Implementation::Rtl::GetSystemSecurity(
                          (Windows::WCP::Implementation::Rtl *)&v16,
                          v13);
    if ( CanSetSystemOwner < 0 )
      return CanSetSystemOwner | 0x10000000;
    *((_QWORD *)&v18 + 1) = v16;
    v19 = 0;
    lpSecurityAttributes = (struct _SECURITY_ATTRIBUTES *)&v20;
    *(_QWORD *)&v18 = 24;
    v21 = 0;
    v20 = v18;
  }
  if ( hTransaction )
    return RegCreateKeyTransactedW(hKey, lpSubKey, 0, 0, 0, 2u, lpSecurityAttributes, phkResult, 0, hTransaction, 0);
  else
    return RegCreateKeyExW(hKey, lpSubKey, 0, 0, 0, 2u, lpSecurityAttributes, phkResult, 0);
}

```

## disassembly

```asm
0x140019c2c  mov     [rsp-8+arg_10], rbx
0x140019c31  push    rbp
0x140019c32  push    rsi
0x140019c33  push    rdi
0x140019c34  lea     rbp, [rsp-1Fh]
0x140019c39  sub     rsp, 0B0h
0x140019c40  mov     rax, cs:__security_cookie
0x140019c47  xor     rax, rsp
0x140019c4a  mov     [rbp+2Fh+var_18], rax
0x140019c4e  mov     rbx, [rbp+2Fh+arg_38]
0x140019c52  mov     rdi, rdx
0x140019c55  mov     rsi, rcx
0x140019c58  test    rdx, rdx
0x140019c5b  jnz     short loc_140019C65
0x140019c5d  lea     eax, [rdx+57h]
0x140019c60  jmp     loc_140019D5E
0x140019c65  test    rbx, rbx
0x140019c68  jnz     short loc_140019C74
0x140019c6a  mov     eax, 80004003h
0x140019c6f  jmp     loc_140019D5E
0x140019c74  lea     rcx, [rbp+2Fh+var_50]; void **
0x140019c78  mov     [rbp+2Fh+var_50], 0
0x140019c80  call    ?CbsGetCurrentTransaction@@YAJPEAPEAX@Z; CbsGetCurrentTransaction(void * *)
0x140019c85  xor     eax, eax
0x140019c87  lea     rcx, [rbp+2Fh+var_60]; this
0x140019c8b  xorps   xmm0, xmm0
0x140019c8e  mov     [rbp+2Fh+var_20], rax
0x140019c92  movups  [rbp+2Fh+var_30], xmm0
0x140019c96  mov     [rbp+2Fh+var_60], al
0x140019c99  call    ?CanSetSystemOwner@Rtl@Implementation@WCP@Windows@@YAJPEA_N@Z; Windows::WCP::Implementation::Rtl::CanSetSystemOwner(bool *)
0x140019c9e  test    eax, eax
0x140019ca0  jns     short loc_140019CAB
0x140019ca2  bts     eax, 1Ch
0x140019ca6  jmp     loc_140019D5E
0x140019cab  xor     eax, eax
0x140019cad  cmp     [rbp+2Fh+var_60], al
0x140019cb0  jz      short loc_140019CEF
0x140019cb2  lea     rcx, [rbp+2Fh+var_58]; this
0x140019cb6  mov     [rbp+2Fh+var_58], rax
0x140019cba  call    ?GetSystemSecurity@Rtl@Implementation@WCP@Windows@@YAJPEAPEAU_SECURITY_DESCRIPTOR@@@Z; Windows::WCP::Implementation::Rtl::GetSystemSecurity(_SECURITY_DESCRIPTOR * *)
0x140019cbf  test    eax, eax
0x140019cc1  js      short loc_140019CA2
0x140019cc3  mov     rax, [rbp+2Fh+var_58]
0x140019cc7  mov     qword ptr [rbp+2Fh+var_48+8], rax
0x140019ccb  xor     eax, eax
0x140019ccd  mov     [rbp+2Fh+var_38], rax
0x140019cd1  lea     rax, [rbp+2Fh+var_30]
0x140019cd5  movsd   xmm1, [rbp+2Fh+var_38]
0x140019cda  mov     qword ptr [rbp+2Fh+var_48], 18h
0x140019ce2  movups  xmm0, [rbp+2Fh+var_48]
0x140019ce6  movsd   [rbp+2Fh+var_20], xmm1
0x140019ceb  movups  [rbp+2Fh+var_30], xmm0
0x140019cef  mov     r8, [rbp+2Fh+var_50]
0x140019cf3  xor     r9d, r9d; lpClass
0x140019cf6  mov     rdx, rdi; lpSubKey
0x140019cf9  mov     rcx, rsi; hKey
0x140019cfc  test    r8, r8
0x140019cff  jz      short loc_140019D32
0x140019d01  mov     [rsp+0C0h+pExtendedParemeter], r9; pExtendedParemeter
0x140019d06  mov     [rsp+0C0h+hTransaction], r8; hTransaction
0x140019d0b  xor     r8d, r8d; Reserved
0x140019d0e  mov     [rsp+0C0h+lpdwDisposition], r9; lpdwDisposition
0x140019d13  mov     [rsp+0C0h+phkResult], rbx; phkResult
0x140019d18  mov     [rsp+0C0h+lpSecurityAttributes], rax; lpSecurityAttributes
0x140019d1d  mov     [rsp+0C0h+samDesired], 2; samDesired
0x140019d25  mov     [rsp+0C0h+dwOptions], r9d; dwOptions
0x140019d2a  call    cs:__imp_RegCreateKeyTransactedW
0x140019d30  jmp     short loc_140019D5E
0x140019d32  mov     [rsp+0C0h+lpdwDisposition], 0; lpdwDisposition
0x140019d3b  xor     r8d, r8d; Reserved
0x140019d3e  mov     [rsp+0C0h+phkResult], rbx; phkResult
0x140019d43  mov     [rsp+0C0h+lpSecurityAttributes], rax; lpSecurityAttributes
0x140019d48  mov     [rsp+0C0h+samDesired], 2; samDesired
0x140019d50  mov     [rsp+0C0h+dwOptions], 0; dwOptions
0x140019d58  call    cs:__imp_RegCreateKeyExW
0x140019d5e  mov     rcx, [rbp+2Fh+var_18]
0x140019d62  xor     rcx, rsp; StackCookie
0x140019d65  call    __security_check_cookie
0x140019d6a  mov     rbx, [rsp+0C0h+arg_10]
0x140019d72  add     rsp, 0B0h
0x140019d79  pop     rdi
0x140019d7a  pop     rsi
0x140019d7b  pop     rbp
0x140019d7c  retn
```
