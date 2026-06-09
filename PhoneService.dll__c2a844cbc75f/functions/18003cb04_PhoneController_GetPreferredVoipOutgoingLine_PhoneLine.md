# PhoneController::_GetPreferredVoipOutgoingLine(PhoneLine * *)

- ea: `0x18003cb04`
- end: `0x18003ccfb`
- name: `?_GetPreferredVoipOutgoingLine@PhoneController@@IEAAJPEAPEAVPhoneLine@@@Z`
- size: `503`
- prototype: `__int64 __fastcall(PhoneController *__hidden this, struct PhoneLine **)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180044484`

## callees

- `0x1800056a0`
- `0x180006e94`
- `0x1800272c8`
- `0x18002c574`
- `0x18002c580`
- `0x18003cb04`
- `0x180051e44`
- `0x18007f9ec`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18003cc2d`
- `msvcrt!wcscpy_s` at `0x18003cc2d`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18003cc43`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18003cc43`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003cb2c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003cb4c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003cb2c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003cb4c`

## string_xrefs

- `0x18003cb40`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x18003cbbb`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x18003cc7a`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`

## pseudocode

```c
__int64 __fastcall PhoneController::_GetPreferredVoipOutgoingLine(PhoneController *this, struct PhoneLine **a2)
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
    Log_AssertionEvent_3(v4, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 896);
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
         v5 + 1696,
         &Block);
  v8 = v6;
  if ( v6 < 0 )
  {
    BackTraceCollection::Capture(v7, v6);
    v9 = 903;
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
      v9 = 907;
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
        911);
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
0x18003cb04  mov     [rsp-8+arg_10], rbx
0x18003cb09  push    rbp
0x18003cb0a  push    rsi
0x18003cb0b  push    rdi
0x18003cb0c  lea     rbp, [rsp-47h]
0x18003cb11  sub     rsp, 0D0h
0x18003cb18  mov     rax, cs:__security_cookie
0x18003cb1f  xor     rax, rsp
0x18003cb22  mov     [rbp+57h+var_20], rax
0x18003cb26  mov     rsi, rdx
0x18003cb29  mov     rdi, rcx
0x18003cb2c  call    cs:__imp_GetCurrentThreadId
0x18003cb32  cmp     [rdi+0F0h], eax
0x18003cb38  jz      short loc_18003CB5F
0x18003cb3a  mov     r8d, 380h
0x18003cb40  lea     rdx, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18003cb47  call    Log_AssertionEvent_3
0x18003cb4c  call    cs:__imp_GetCurrentThreadId
0x18003cb52  cmp     [rdi+0F0h], eax
0x18003cb58  jz      short loc_18003CB5F
0x18003cb5a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003cb5f  xor     eax, eax
0x18003cb61  mov     qword ptr [rsi], 0
0x18003cb68  mov     rcx, [rdi+1E8h]
0x18003cb6f  lea     rdx, [rbp+57h+Block]
0x18003cb73  mov     [rbp+57h+var_8A], ax
0x18003cb77  add     rcx, 6A0h
0x18003cb7e  lea     rax, [rbp+57h+var_98]
0x18003cb82  mov     [rbp+57h+var_96], 0
0x18003cb8a  mov     [rbp+57h+Block], rax
0x18003cb8e  lea     rax, [rbp+57h+var_98]
0x18003cb92  mov     [rbp+57h+var_A0], rax
0x18003cb96  xor     eax, eax
0x18003cb98  mov     [rbp+57h+var_98], ax
0x18003cb9c  mov     [rbp+57h+var_8E], 0
0x18003cba3  call    ?Get@?$ConfigValueWithDefault@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@@QEAAJPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; ConfigValueWithDefault<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>::Get(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x18003cba8  mov     ebx, eax
0x18003cbaa  test    eax, eax
0x18003cbac  jns     short loc_18003CBEE
0x18003cbae  mov     edx, eax; int
0x18003cbb0  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18003cbb5  mov     r9d, 387h
0x18003cbbb  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18003cbc2  mov     edx, 1
0x18003cbc7  mov     ecx, ebx
0x18003cbc9  call    Log_HREvent_7
0x18003cbce  mov     rcx, [rbp+57h+Block]; Block
0x18003cbd2  lea     rax, [rbp+57h+var_98]
0x18003cbd6  cmp     rcx, rax
0x18003cbd9  jz      short loc_18003CBE7
0x18003cbdb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18003cbe2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003cbe7  mov     eax, ebx
0x18003cbe9  jmp     loc_18003CCC5
0x18003cbee  mov     rcx, [rbp+57h+Block]; this
0x18003cbf2  cmp     rcx, [rbp+57h+var_A0]
0x18003cbf6  jz      loc_18003CCAE
0x18003cbfc  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18003cc03  movdqu  xmmword ptr [rbp+57h+pclsid.Data1], xmm0
0x18003cc08  test    rcx, rcx
0x18003cc0b  jnz     short loc_18003CC17
0x18003cc0d  mov     ebx, 80070057h
0x18003cc12  jmp     loc_18003CCE9
0x18003cc17  cmp     word ptr [rcx], 7Bh ; '{'
0x18003cc1b  jnz     loc_18003CCE4
0x18003cc21  mov     r8, rcx; Source
0x18003cc24  mov     edx, 27h ; '''; SizeInWords
0x18003cc29  lea     rcx, [rbp+57h+Destination]; Destination
0x18003cc2d  call    cs:__imp_wcscpy_s
0x18003cc33  test    eax, eax
0x18003cc35  js      loc_18003CCE4
0x18003cc3b  lea     rdx, [rbp+57h+pclsid]; pclsid
0x18003cc3f  lea     rcx, [rbp+57h+Destination]; lpsz
0x18003cc43  call    cs:__imp_CLSIDFromString
0x18003cc49  test    eax, eax
0x18003cc4b  js      loc_18003CCE4
0x18003cc51  mov     rcx, [rdi+98h]; this
0x18003cc58  lea     r8, [rbp+57h+var_B0]; struct PhoneLine **
0x18003cc5c  xor     r9d, r9d; struct ISecurityToken *
0x18003cc5f  mov     [rbp+57h+var_B0], 0
0x18003cc67  lea     rdx, [rbp+57h+pclsid]; struct _GUID *
0x18003cc6b  call    ?GetPhoneLine@PhoneLineStorage@@QEAAJAEBU_GUID@@PEAPEAVPhoneLine@@PEAUISecurityToken@@@Z; PhoneLineStorage::GetPhoneLine(_GUID const &,PhoneLine * *,ISecurityToken *)
0x18003cc70  test    eax, eax
0x18003cc72  jns     short loc_18003CC90
0x18003cc74  mov     r9d, 38Fh
0x18003cc7a  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18003cc81  xor     edx, edx
0x18003cc83  mov     ecx, eax
0x18003cc85  call    Log_HREvent_7
0x18003cc8a  mov     rcx, [rbp+57h+var_B0]
0x18003cc8e  jmp     short loc_18003CC99
0x18003cc90  mov     rax, [rbp+57h+var_B0]
0x18003cc94  xor     ecx, ecx
0x18003cc96  mov     [rsi], rax
0x18003cc99  test    rcx, rcx
0x18003cc9c  jz      short loc_18003CCAA
0x18003cc9e  mov     rax, [rcx]
0x18003cca1  mov     rax, [rax+10h]
0x18003cca5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ccaa  mov     rcx, [rbp+57h+Block]; Block
0x18003ccae  lea     rax, [rbp+57h+var_98]
0x18003ccb2  cmp     rcx, rax
0x18003ccb5  jz      short loc_18003CCC3
0x18003ccb7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18003ccbe  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003ccc3  xor     eax, eax
0x18003ccc5  mov     rcx, [rbp+57h+var_20]
0x18003ccc9  xor     rcx, rsp; StackCookie
0x18003cccc  call    __security_check_cookie
0x18003ccd1  mov     rbx, [rsp+0E0h+arg_10]
0x18003ccd9  add     rsp, 0D0h
0x18003cce0  pop     rdi
0x18003cce1  pop     rsi
0x18003cce2  pop     rbp
0x18003cce3  retn
0x18003cce4  mov     ebx, 8007000Dh
0x18003cce9  mov     edx, ebx; int
0x18003cceb  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18003ccf0  mov     r9d, 38Bh
0x18003ccf6  jmp     loc_18003CBBB
```
