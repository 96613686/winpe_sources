# SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton::AllocAndCopySid(void *,void * *)

- ea: `0x180047fcc`
- end: `0x180048078`
- name: `?AllocAndCopySid@BackgroundCapabilitySingleton@BatteryUsageHandlers@SystemSettings@@AEAAJPEAXPEAPEAX@Z`
- size: `172`
- prototype: `int(SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton *__hidden this, void *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004884c`

## callees

- `0x180047fac`
- `0x180047fcc`
- `0x180048d80`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180048034`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180048034`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180048005`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180048005`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180047ff8`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180047ff8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180048019`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180048019`

## pseudocode

```c
__int64 __fastcall SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton::AllocAndCopySid(
        SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton *this,
        void *a2,
        SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton **a3)
{
  int Error; // edi
  SIZE_T LengthSid; // rbp
  SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton *v7; // rax
  SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton *v8; // rbx
  SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton *v10; // [rsp+40h] [rbp+8h] BYREF

  v10 = this;
  *a3 = 0;
  Error = -2147024809;
  if ( IsValidSid(a2) )
  {
    LengthSid = GetLengthSid(a2);
    Error = -2147024882;
    v7 = (SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton *)LocalAlloc(0x40u, LengthSid);
    v10 = v7;
    v8 = v7;
    if ( v7 )
    {
      if ( CopySid(LengthSid, v7, a2) )
      {
        Error = 0;
LABEL_6:
        v10 = 0;
        *a3 = v8;
        goto LABEL_7;
      }
      Error = ResultFromKnownLastError();
      if ( Error >= 0 )
        goto LABEL_6;
    }
LABEL_7:
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v10);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180047fcc  mov     [rsp+arg_8], rbx
0x180047fd1  mov     [rsp+arg_10], rbp
0x180047fd6  mov     [rsp+arg_0], rcx
0x180047fdb  push    rsi
0x180047fdc  push    rdi
0x180047fdd  push    r14
0x180047fdf  sub     rsp, 20h
0x180047fe3  mov     rcx, rdx; pSid
0x180047fe6  mov     qword ptr [r8], 0
0x180047fed  mov     r14, r8
0x180047ff0  mov     rsi, rdx
0x180047ff3  mov     edi, 80070057h
0x180047ff8  call    cs:__imp_IsValidSid
0x180047ffe  test    eax, eax
0x180048000  jz      short loc_180048063
0x180048002  mov     rcx, rsi; pSid
0x180048005  call    cs:__imp_GetLengthSid
0x18004800b  mov     edx, eax; uBytes
0x18004800d  mov     ecx, 40h ; '@'; uFlags
0x180048012  mov     ebp, eax
0x180048014  mov     edi, 8007000Eh
0x180048019  call    cs:__imp_LocalAlloc
0x18004801f  mov     [rsp+38h+arg_0], rax
0x180048024  mov     rbx, rax
0x180048027  test    rax, rax
0x18004802a  jz      short loc_180048059
0x18004802c  mov     r8, rsi; pSourceSid
0x18004802f  mov     rdx, rax; pDestinationSid
0x180048032  mov     ecx, ebp; nDestinationSidLength
0x180048034  call    cs:__imp_CopySid
0x18004803a  test    eax, eax
0x18004803c  jz      short loc_180048042
0x18004803e  xor     edi, edi
0x180048040  jmp     short loc_18004804D
0x180048042  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180048047  mov     edi, eax
0x180048049  test    eax, eax
0x18004804b  js      short loc_180048059
0x18004804d  mov     [rsp+38h+arg_0], 0
0x180048056  mov     [r14], rbx
0x180048059  lea     rcx, [rsp+38h+arg_0]
0x18004805e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180048063  mov     rbx, [rsp+38h+arg_8]
0x180048068  mov     eax, edi
0x18004806a  mov     rbp, [rsp+38h+arg_10]
0x18004806f  add     rsp, 20h
0x180048073  pop     r14
0x180048075  pop     rdi
0x180048076  pop     rsi
0x180048077  retn
```
