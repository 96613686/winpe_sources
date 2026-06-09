# PhoneController::_FindPreferredCallUpgradeLine(PhoneLine * *)

- ea: `0x18003abb0`
- end: `0x18003ada7`
- name: `?_FindPreferredCallUpgradeLine@PhoneController@@IEAAJPEAPEAVPhoneLine@@@Z`
- size: `503`
- prototype: `__int64 __fastcall(PhoneController *__hidden this, struct PhoneLine **)`
- caller_count: `5`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180029e40`
- `0x18002b8c0`
- `0x18003baf0`
- `0x180044484`
- `0x180048c34`

## callees

- `0x1800056a0`
- `0x180006e94`
- `0x1800272c8`
- `0x18002c574`
- `0x18002c580`
- `0x18003abb0`
- `0x180051e44`
- `0x18007f9ec`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18003acd9`
- `msvcrt!wcscpy_s` at `0x18003acd9`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18003acef`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18003acef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003abd8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003abf8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003abd8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003abf8`

## string_xrefs

- `0x18003abec`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x18003ac67`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x18003ad26`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`

## pseudocode

```c
__int64 __fastcall PhoneController::_FindPreferredCallUpgradeLine(PhoneController *this, struct PhoneLine **a2)
{
  __int64 v4; // rcx
  __int64 v5; // rcx
  int v6; // eax
  BackTraceCollection *v7; // rcx
  unsigned int v8; // ebx
  __int64 v9; // r9
  BackTraceCollection *v11; // rcx
  PhoneLineStorage *v12; // rcx
  int PhoneLine; // eax
  struct PhoneLine *v14; // rcx
  struct PhoneLine *v15; // [rsp+30h] [rbp-59h] BYREF
  void *Block; // [rsp+38h] [rbp-51h] BYREF
  __int16 *v17; // [rsp+40h] [rbp-49h]
  __int16 v18; // [rsp+48h] [rbp-41h] BYREF
  __int64 v19; // [rsp+4Ah] [rbp-3Fh]
  int v20; // [rsp+52h] [rbp-37h]
  __int16 v21; // [rsp+56h] [rbp-33h]
  GUID pclsid; // [rsp+58h] [rbp-31h] BYREF
  wchar_t Destination[40]; // [rsp+70h] [rbp-19h] BYREF

  if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
  {
    Log_AssertionEvent_3(v4, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 730);
    if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  *a2 = 0;
  v5 = *((_QWORD *)this + 61);
  v21 = 0;
  v19 = 0;
  Block = &v18;
  v17 = &v18;
  v18 = 0;
  v20 = 0;
  v6 = ConfigValueWithDefault<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>::Get(
         v5 + 1576,
         &Block);
  v8 = v6;
  if ( v6 < 0 )
  {
    BackTraceCollection::Capture(v7, v6);
    v9 = 737;
LABEL_6:
    Log_HREvent_7(v8, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", v9);
    if ( Block != &v18 )
      operator delete(Block);
    return v8;
  }
  v11 = (BackTraceCollection *)Block;
  if ( Block != v17 )
  {
    pclsid = GUID_00000000_0000_0000_0000_000000000000;
    if ( !Block )
    {
      v8 = -2147024809;
LABEL_25:
      BackTraceCollection::Capture(v11, v8);
      v9 = 741;
      goto LABEL_6;
    }
    if ( *(_WORD *)Block != 123
      || wcscpy_s(Destination, 0x27u, (const wchar_t *)Block) < 0
      || CLSIDFromString(Destination, &pclsid) < 0 )
    {
      v8 = -2147024883;
      goto LABEL_25;
    }
    v12 = (PhoneLineStorage *)*((_QWORD *)this + 19);
    v15 = 0;
    PhoneLine = PhoneLineStorage::GetPhoneLine(v12, &pclsid, &v15, 0);
    if ( PhoneLine >= 0 )
    {
      v14 = 0;
      *a2 = v15;
    }
    else
    {
      Log_HREvent_7(
        (unsigned int)PhoneLine,
        0,
        "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp",
        745);
      v14 = v15;
    }
    if ( v14 )
      (*(void (__fastcall **)(struct PhoneLine *))(*(_QWORD *)v14 + 16LL))(v14);
    v11 = (BackTraceCollection *)Block;
  }
  if ( v11 != (BackTraceCollection *)&v18 )
    operator delete(v11);
  return 0;
}

```

## disassembly

```asm
0x18003abb0  mov     [rsp-8+arg_10], rbx
0x18003abb5  push    rbp
0x18003abb6  push    rsi
0x18003abb7  push    rdi
0x18003abb8  lea     rbp, [rsp-47h]
0x18003abbd  sub     rsp, 0D0h
0x18003abc4  mov     rax, cs:__security_cookie
0x18003abcb  xor     rax, rsp
0x18003abce  mov     [rbp+57h+var_20], rax
0x18003abd2  mov     rsi, rdx
0x18003abd5  mov     rdi, rcx
0x18003abd8  call    cs:__imp_GetCurrentThreadId
0x18003abde  cmp     [rdi+0F0h], eax
0x18003abe4  jz      short loc_18003AC0B
0x18003abe6  mov     r8d, 2DAh
0x18003abec  lea     rdx, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18003abf3  call    Log_AssertionEvent_3
0x18003abf8  call    cs:__imp_GetCurrentThreadId
0x18003abfe  cmp     [rdi+0F0h], eax
0x18003ac04  jz      short loc_18003AC0B
0x18003ac06  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003ac0b  xor     eax, eax
0x18003ac0d  mov     qword ptr [rsi], 0
0x18003ac14  mov     rcx, [rdi+1E8h]
0x18003ac1b  lea     rdx, [rbp+57h+Block]
0x18003ac1f  mov     [rbp+57h+var_8A], ax
0x18003ac23  add     rcx, 628h
0x18003ac2a  lea     rax, [rbp+57h+var_98]
0x18003ac2e  mov     [rbp+57h+var_96], 0
0x18003ac36  mov     [rbp+57h+Block], rax
0x18003ac3a  lea     rax, [rbp+57h+var_98]
0x18003ac3e  mov     [rbp+57h+var_A0], rax
0x18003ac42  xor     eax, eax
0x18003ac44  mov     [rbp+57h+var_98], ax
0x18003ac48  mov     [rbp+57h+var_8E], 0
0x18003ac4f  call    ?Get@?$ConfigValueWithDefault@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@@QEAAJPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; ConfigValueWithDefault<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>::Get(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x18003ac54  mov     ebx, eax
0x18003ac56  test    eax, eax
0x18003ac58  jns     short loc_18003AC9A
0x18003ac5a  mov     edx, eax; int
0x18003ac5c  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18003ac61  mov     r9d, 2E1h
0x18003ac67  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18003ac6e  mov     edx, 1
0x18003ac73  mov     ecx, ebx
0x18003ac75  call    Log_HREvent_7
0x18003ac7a  mov     rcx, [rbp+57h+Block]; Block
0x18003ac7e  lea     rax, [rbp+57h+var_98]
0x18003ac82  cmp     rcx, rax
0x18003ac85  jz      short loc_18003AC93
0x18003ac87  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18003ac8e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003ac93  mov     eax, ebx
0x18003ac95  jmp     loc_18003AD71
0x18003ac9a  mov     rcx, [rbp+57h+Block]; this
0x18003ac9e  cmp     rcx, [rbp+57h+var_A0]
0x18003aca2  jz      loc_18003AD5A
0x18003aca8  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18003acaf  movdqu  xmmword ptr [rbp+57h+pclsid.Data1], xmm0
0x18003acb4  test    rcx, rcx
0x18003acb7  jnz     short loc_18003ACC3
0x18003acb9  mov     ebx, 80070057h
0x18003acbe  jmp     loc_18003AD95
0x18003acc3  cmp     word ptr [rcx], 7Bh ; '{'
0x18003acc7  jnz     loc_18003AD90
0x18003accd  mov     r8, rcx; Source
0x18003acd0  mov     edx, 27h ; '''; SizeInWords
0x18003acd5  lea     rcx, [rbp+57h+Destination]; Destination
0x18003acd9  call    cs:__imp_wcscpy_s
0x18003acdf  test    eax, eax
0x18003ace1  js      loc_18003AD90
0x18003ace7  lea     rdx, [rbp+57h+pclsid]; pclsid
0x18003aceb  lea     rcx, [rbp+57h+Destination]; lpsz
0x18003acef  call    cs:__imp_CLSIDFromString
0x18003acf5  test    eax, eax
0x18003acf7  js      loc_18003AD90
0x18003acfd  mov     rcx, [rdi+98h]; this
0x18003ad04  lea     r8, [rbp+57h+var_B0]; struct PhoneLine **
0x18003ad08  xor     r9d, r9d; struct ISecurityToken *
0x18003ad0b  mov     [rbp+57h+var_B0], 0
0x18003ad13  lea     rdx, [rbp+57h+pclsid]; struct _GUID *
0x18003ad17  call    ?GetPhoneLine@PhoneLineStorage@@QEAAJAEBU_GUID@@PEAPEAVPhoneLine@@PEAUISecurityToken@@@Z; PhoneLineStorage::GetPhoneLine(_GUID const &,PhoneLine * *,ISecurityToken *)
0x18003ad1c  test    eax, eax
0x18003ad1e  jns     short loc_18003AD3C
0x18003ad20  mov     r9d, 2E9h
0x18003ad26  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18003ad2d  xor     edx, edx
0x18003ad2f  mov     ecx, eax
0x18003ad31  call    Log_HREvent_7
0x18003ad36  mov     rcx, [rbp+57h+var_B0]
0x18003ad3a  jmp     short loc_18003AD45
0x18003ad3c  mov     rax, [rbp+57h+var_B0]
0x18003ad40  xor     ecx, ecx
0x18003ad42  mov     [rsi], rax
0x18003ad45  test    rcx, rcx
0x18003ad48  jz      short loc_18003AD56
0x18003ad4a  mov     rax, [rcx]
0x18003ad4d  mov     rax, [rax+10h]
0x18003ad51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ad56  mov     rcx, [rbp+57h+Block]; Block
0x18003ad5a  lea     rax, [rbp+57h+var_98]
0x18003ad5e  cmp     rcx, rax
0x18003ad61  jz      short loc_18003AD6F
0x18003ad63  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18003ad6a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003ad6f  xor     eax, eax
0x18003ad71  mov     rcx, [rbp+57h+var_20]
0x18003ad75  xor     rcx, rsp; StackCookie
0x18003ad78  call    __security_check_cookie
0x18003ad7d  mov     rbx, [rsp+0E0h+arg_10]
0x18003ad85  add     rsp, 0D0h
0x18003ad8c  pop     rdi
0x18003ad8d  pop     rsi
0x18003ad8e  pop     rbp
0x18003ad8f  retn
0x18003ad90  mov     ebx, 8007000Dh
0x18003ad95  mov     edx, ebx; int
0x18003ad97  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18003ad9c  mov     r9d, 2E5h
0x18003ada2  jmp     loc_18003AC67
```
