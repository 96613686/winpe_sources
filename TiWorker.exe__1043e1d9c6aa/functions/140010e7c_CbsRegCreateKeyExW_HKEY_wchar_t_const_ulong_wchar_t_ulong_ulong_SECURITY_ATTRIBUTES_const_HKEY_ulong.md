# CbsRegCreateKeyExW(HKEY__ *,wchar_t const *,ulong,wchar_t *,ulong,ulong,_SECURITY_ATTRIBUTES * const,HKEY__ * *,ulong *)

- ea: `0x140010e7c`
- end: `0x140010fd7`
- name: `?CbsRegCreateKeyExW@@YAKPEAUHKEY__@@PEB_WKPEA_WKKQEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@Z`
- size: `347`
- prototype: `LSTATUS __fastcall(HKEY, const wchar_t *, __int64, wchar_t *, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *const, HKEY *phkResult)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140011a30`

## callees

- `0x140002310`
- `0x140010e7c`
- `0x140024efc`
- `0x1400266a4`
- `0x1400269f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140010fb0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140010fb0`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyTransactedW` at `0x140010f7e`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyTransactedW` at `0x140010f7e`

## pseudocode

```c
LSTATUS __fastcall CbsRegCreateKeyExW(
        HKEY a1,
        const wchar_t *a2,
        __int64 a3,
        wchar_t *a4,
        unsigned int a5,
        unsigned int a6,
        struct _SECURITY_ATTRIBUTES *const a7,
        HKEY *phkResult)
{
  bool *v10; // rdx
  int CanSetSystemOwner; // eax
  struct _SECURITY_DESCRIPTOR **v12; // rdx
  struct _SECURITY_ATTRIBUTES *lpSecurityAttributes; // rax
  _BYTE v14[8]; // [rsp+60h] [rbp-21h] BYREF
  __int64 v15; // [rsp+68h] [rbp-19h] BYREF
  HANDLE hTransaction; // [rsp+70h] [rbp-11h] BYREF
  __int128 v17; // [rsp+78h] [rbp-9h]
  __int64 v18; // [rsp+88h] [rbp+7h]
  __int128 v19; // [rsp+90h] [rbp+Fh] BYREF
  __int64 v20; // [rsp+A0h] [rbp+1Fh]

  if ( !a2 )
    return 87;
  if ( !phkResult )
    return -2147467261;
  hTransaction = 0;
  CbsGetCurrentTransaction(&hTransaction);
  v20 = 0;
  v19 = 0;
  v14[0] = 0;
  CanSetSystemOwner = Windows::WCP::Implementation::Rtl::CanSetSystemOwner(
                        (Windows::WCP::Implementation::Rtl *)v14,
                        v10);
  if ( CanSetSystemOwner < 0 )
    return CanSetSystemOwner | 0x10000000;
  lpSecurityAttributes = 0;
  if ( v14[0] )
  {
    v15 = 0;
    CanSetSystemOwner = Windows::WCP::Implementation::Rtl::GetSystemSecurity(
                          (Windows::WCP::Implementation::Rtl *)&v15,
                          v12);
    if ( CanSetSystemOwner < 0 )
      return CanSetSystemOwner | 0x10000000;
    *((_QWORD *)&v17 + 1) = v15;
    v18 = 0;
    lpSecurityAttributes = (struct _SECURITY_ATTRIBUTES *)&v19;
    *(_QWORD *)&v17 = 24;
    v20 = 0;
    v19 = v17;
  }
  if ( hTransaction )
    return RegCreateKeyTransactedW(
             HKEY_LOCAL_MACHINE,
             a2,
             0,
             0,
             0,
             2u,
             lpSecurityAttributes,
             phkResult,
             0,
             hTransaction,
             0);
  else
    return RegCreateKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0, 0, 2u, lpSecurityAttributes, phkResult, 0);
}

```

## disassembly

```asm
0x140010e7c  mov     [rsp-8+arg_0], rbx
0x140010e81  mov     [rsp-8+arg_10], rdi
0x140010e86  push    rbp
0x140010e87  lea     rbp, [rsp-2Fh]
0x140010e8c  sub     rsp, 0B0h
0x140010e93  mov     rax, cs:__security_cookie
0x140010e9a  xor     rax, rsp
0x140010e9d  mov     [rbp+2Fh+var_8], rax
0x140010ea1  mov     rbx, [rbp+2Fh+arg_38]
0x140010ea5  mov     rdi, rdx
0x140010ea8  test    rdx, rdx
0x140010eab  jnz     short loc_140010EB5
0x140010ead  lea     eax, [rdx+57h]
0x140010eb0  jmp     loc_140010FB6
0x140010eb5  test    rbx, rbx
0x140010eb8  jnz     short loc_140010EC4
0x140010eba  mov     eax, 80004003h
0x140010ebf  jmp     loc_140010FB6
0x140010ec4  lea     rcx, [rbp+2Fh+var_40]; void **
0x140010ec8  mov     [rbp+2Fh+var_40], 0
0x140010ed0  call    ?CbsGetCurrentTransaction@@YAJPEAPEAX@Z; CbsGetCurrentTransaction(void * *)
0x140010ed5  xor     eax, eax
0x140010ed7  lea     rcx, [rbp+2Fh+var_50]; this
0x140010edb  xorps   xmm0, xmm0
0x140010ede  mov     [rbp+2Fh+var_10], rax
0x140010ee2  movups  [rbp+2Fh+var_20], xmm0
0x140010ee6  mov     [rbp+2Fh+var_50], al
0x140010ee9  call    ?CanSetSystemOwner@Rtl@Implementation@WCP@Windows@@YAJPEA_N@Z; Windows::WCP::Implementation::Rtl::CanSetSystemOwner(bool *)
0x140010eee  test    eax, eax
0x140010ef0  jns     short loc_140010EFB
0x140010ef2  bts     eax, 1Ch
0x140010ef6  jmp     loc_140010FB6
0x140010efb  xor     eax, eax
0x140010efd  cmp     [rbp+2Fh+var_50], al
0x140010f00  jz      short loc_140010F3F
0x140010f02  lea     rcx, [rbp+2Fh+var_48]; this
0x140010f06  mov     [rbp+2Fh+var_48], rax
0x140010f0a  call    ?GetSystemSecurity@Rtl@Implementation@WCP@Windows@@YAJPEAPEAU_SECURITY_DESCRIPTOR@@@Z; Windows::WCP::Implementation::Rtl::GetSystemSecurity(_SECURITY_DESCRIPTOR * *)
0x140010f0f  test    eax, eax
0x140010f11  js      short loc_140010EF2
0x140010f13  mov     rax, [rbp+2Fh+var_48]
0x140010f17  mov     qword ptr [rbp+2Fh+var_38+8], rax
0x140010f1b  xor     eax, eax
0x140010f1d  mov     [rbp+2Fh+var_28], rax
0x140010f21  lea     rax, [rbp+2Fh+var_20]
0x140010f25  movsd   xmm1, [rbp+2Fh+var_28]
0x140010f2a  mov     qword ptr [rbp+2Fh+var_38], 18h
0x140010f32  movups  xmm0, [rbp+2Fh+var_38]
0x140010f36  movsd   [rbp+2Fh+var_10], xmm1
0x140010f3b  movups  [rbp+2Fh+var_20], xmm0
0x140010f3f  mov     rcx, [rbp+2Fh+var_40]
0x140010f43  xor     r9d, r9d; lpClass
0x140010f46  xor     r8d, r8d; Reserved
0x140010f49  mov     rdx, rdi; lpSubKey
0x140010f4c  test    rcx, rcx
0x140010f4f  jz      short loc_140010F86
0x140010f51  mov     [rsp+0B0h+pExtendedParemeter], r8; pExtendedParemeter
0x140010f56  mov     [rsp+0B0h+hTransaction], rcx; hTransaction
0x140010f5b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140010f62  mov     [rsp+0B0h+lpdwDisposition], r8; lpdwDisposition
0x140010f67  mov     [rsp+0B0h+phkResult], rbx; phkResult
0x140010f6c  mov     [rsp+0B0h+lpSecurityAttributes], rax; lpSecurityAttributes
0x140010f71  mov     [rsp+0B0h+samDesired], 2; samDesired
0x140010f79  mov     [rsp+0B0h+dwOptions], r8d; dwOptions
0x140010f7e  call    cs:__imp_RegCreateKeyTransactedW
0x140010f84  jmp     short loc_140010FB6
0x140010f86  mov     [rsp+0B0h+lpdwDisposition], 0; lpdwDisposition
0x140010f8f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140010f96  mov     [rsp+0B0h+phkResult], rbx; phkResult
0x140010f9b  mov     [rsp+0B0h+lpSecurityAttributes], rax; lpSecurityAttributes
0x140010fa0  mov     [rsp+0B0h+samDesired], 2; samDesired
0x140010fa8  mov     [rsp+0B0h+dwOptions], 0; dwOptions
0x140010fb0  call    cs:__imp_RegCreateKeyExW
0x140010fb6  mov     rcx, [rbp+2Fh+var_8]
0x140010fba  xor     rcx, rsp; StackCookie
0x140010fbd  call    __security_check_cookie
0x140010fc2  lea     r11, [rsp+0B0h+var_s0]
0x140010fca  mov     rbx, [r11+10h]
0x140010fce  mov     rdi, [r11+20h]
0x140010fd2  mov     rsp, r11
0x140010fd5  pop     rbp
0x140010fd6  retn
```
