# CURLExecutionContextService::CreateReuseTabId(void)

- ea: `0x1800170c0`
- end: `0x180017187`
- name: `?CreateReuseTabId@CURLExecutionContextService@@UEAAJXZ`
- size: `199`
- prototype: `__int64 __fastcall(CURLExecutionContextService *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x1800120dc`
- `0x1800170c0`
- `0x180076c50`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800170df`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800170df`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180017169`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180017169`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18001711e`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18001711e`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800170f2`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800170f2`

## pseudocode

```c
__int64 __fastcall CURLExecutionContextService::CreateReuseTabId(CURLExecutionContextService *this)
{
  HRESULT v2; // ebx
  __int64 v3; // rcx
  __int16 v5; // [rsp+20h] [rbp-58h] BYREF
  __int64 v6; // [rsp+28h] [rbp-50h]
  GUID pguid; // [rsp+38h] [rbp-40h] BYREF

  AcquireSRWLockExclusive((PSRWLOCK)this + 2);
  pguid = 0;
  v2 = CoCreateGuid(&pguid);
  if ( v2 >= 0 )
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 32);
    *((_QWORD *)this + 5) = -1;
    *((_QWORD *)this + 6) = -1;
    v2 = StringFromCLSID(&pguid, (LPOLESTR *)this + 4);
    if ( v2 >= 0 )
    {
      v3 = *((_QWORD *)this + 7);
      v5 = 31;
      v6 = *((_QWORD *)this + 4);
      v2 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int16 *))(*(_QWORD *)v3 + 32LL))(
             v3,
             L"Tab Reuse Identifier",
             &v5);
      if ( v2 >= 0 )
        *((_DWORD *)this + 6) = 0;
    }
  }
  ReleaseSRWLockExclusive((PSRWLOCK)this + 2);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800170c0  push    rbx
0x1800170c2  push    rbp
0x1800170c3  push    rsi
0x1800170c4  push    rdi
0x1800170c5  sub     rsp, 58h
0x1800170c9  mov     rax, cs:__security_cookie
0x1800170d0  xor     rax, rsp
0x1800170d3  mov     [rsp+78h+var_30], rax
0x1800170d8  mov     rsi, rcx
0x1800170db  add     rcx, 10h; SRWLock
0x1800170df  call    cs:__imp_AcquireSRWLockExclusive
0x1800170e5  xorps   xmm0, xmm0
0x1800170e8  lea     rcx, [rsp+78h+pguid]; pguid
0x1800170ed  movups  xmmword ptr [rsp+78h+pguid.Data1], xmm0
0x1800170f2  call    cs:__imp_CoCreateGuid
0x1800170f8  mov     ebx, eax
0x1800170fa  test    eax, eax
0x1800170fc  js      short loc_180017165
0x1800170fe  lea     rdi, [rsi+20h]
0x180017102  mov     rcx, rdi
0x180017105  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001710a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001710e  lea     rcx, [rsp+78h+pguid]; rclsid
0x180017113  mov     rdx, rdi; lplpsz
0x180017116  mov     [rdi+8], rax
0x18001711a  mov     [rdi+10h], rax
0x18001711e  call    cs:__imp_StringFromCLSID
0x180017124  mov     ebx, eax
0x180017126  test    eax, eax
0x180017128  js      short loc_180017165
0x18001712a  mov     rcx, [rsi+38h]
0x18001712e  lea     r8, [rsp+78h+var_58]
0x180017133  mov     eax, 1Fh
0x180017138  lea     rdx, aTabReuseIdenti; "Tab Reuse Identifier"
0x18001713f  mov     [rsp+78h+var_58], ax
0x180017144  mov     rax, [rdi]
0x180017147  mov     [rsp+78h+var_50], rax
0x18001714c  mov     rax, [rcx]
0x18001714f  mov     rax, [rax+20h]
0x180017153  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017158  mov     ebx, eax
0x18001715a  test    eax, eax
0x18001715c  js      short loc_180017165
0x18001715e  mov     dword ptr [rsi+18h], 0
0x180017165  lea     rcx, [rsi+10h]; SRWLock
0x180017169  call    cs:__imp_ReleaseSRWLockExclusive
0x18001716f  mov     eax, ebx
0x180017171  mov     rcx, [rsp+78h+var_30]
0x180017176  xor     rcx, rsp; StackCookie
0x180017179  call    __security_check_cookie
0x18001717e  add     rsp, 58h
0x180017182  pop     rdi
0x180017183  pop     rsi
0x180017184  pop     rbp
0x180017185  pop     rbx
0x180017186  retn
```
