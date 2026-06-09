# DoOutlookUpdate(void)

- ea: `0x180013a54`
- end: `0x180013bec`
- name: `?DoOutlookUpdate@@YAXXZ`
- size: `408`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800150a0`

## callees

- `0x180009380`
- `0x18000f1a8`
- `0x180013a54`
- `0x18001932c`
- `0x1800194f8`
- `0x180034a30`
- `0x18003a74c`
- `0x180056500`
- `0x18005c5e0`

## string_xrefs

- `0x180013bb2`: `OutlookUpdate`
- `0x180013b17`: `IDockedClient3 is not present, skipping OutlookUpdate`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void DoOutlookUpdate(void)
{
  void (__fastcall ***v0)(_QWORD, GUID *, __int64 *); // rcx
  int v1; // eax
  const char *v2; // r9
  _QWORD *v3; // rax
  _QWORD v4[6]; // [rsp+20h] [rbp-A8h] BYREF
  _OWORD Src[2]; // [rsp+50h] [rbp-78h] BYREF
  int v6; // [rsp+70h] [rbp-58h]
  __int64 v7; // [rsp+80h] [rbp-48h] BYREF
  __int128 v8; // [rsp+88h] [rbp-40h] BYREF
  __int128 v9; // [rsp+98h] [rbp-30h]
  int v10; // [rsp+A8h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  v8 = 0;
  v9 = 0;
  v10 = 0;
  v7 = 0;
  try
  {
    v0 = *(void (__fastcall ****)(_QWORD, GUID *, __int64 *))Windows::DockedHelpers::GetDockedClient(v4);
    v7 = 0;
    (**v0)(v0, &GUID_939a7ab6_3ea2_49ae_ab94_41244ce15af0, &v7);
    if ( v4[0] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v4[0] + 16LL))(v4[0]);
    if ( v7 )
    {
      v1 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v7 + 88LL))(v7, &v8);
      if ( v1 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x449,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\clientImpl\\ClientImpl.cpp",
          (const char *)(unsigned int)v1,
          v4[0]);
    }
    else
    {
      v4[2] = 0;
      v4[3] = 0;
      v4[4] = L"IDockedClient3 is not present, skipping OutlookUpdate";
      v4[5] = 53;
      v3 = (_QWORD *)std::vformat<0>(Src);
      if ( v3[3] > 7u )
        v3 = (_QWORD *)*v3;
      v4[0] = v3;
      ClientTelemetry::Message<wchar_t const *>(v4);
      std::wstring::~wstring(Src);
      LODWORD(v8) = 1;
    }
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x451,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\clientImpl\\ClientImpl.cpp",
      v2);
  }
  Src[0] = v8;
  Src[1] = v9;
  v6 = v10;
  ReportExpeditedUpdateWorkCompleted(L"OutlookUpdate", Src);
}

```

## disassembly

```asm
0x180013a54  mov     r11, rsp
0x180013a57  sub     rsp, 0C8h
0x180013a5e  mov     rax, cs:__security_cookie
0x180013a65  xor     rax, rsp
0x180013a68  mov     [rsp+0C8h+var_18], rax
0x180013a70  xorps   xmm0, xmm0
0x180013a73  xor     eax, eax
0x180013a75  movups  xmmword ptr [r11-40h], xmm0
0x180013a7a  movups  xmmword ptr [r11-30h], xmm0
0x180013a7f  mov     [r11-20h], eax
0x180013a83  mov     [r11-48h], rax
0x180013a87  lea     rcx, [rsp+0C8h+var_A8]
0x180013a8c  call    ?GetDockedClient@DockedHelpers@Windows@@YA?AV?$com_ptr_t@UIDockedClient2@@Uerr_exception_policy@wil@@@wil@@XZ; Windows::DockedHelpers::GetDockedClient(void)
0x180013a91  mov     rcx, [rax]
0x180013a94  mov     [rsp+0C8h+var_48], 0
0x180013aa0  mov     rax, [rcx]
0x180013aa3  lea     r8, [rsp+0C8h+var_48]
0x180013aab  lea     rdx, _GUID_939a7ab6_3ea2_49ae_ab94_41244ce15af0
0x180013ab2  mov     rax, [rax]
0x180013ab5  call    _guard_dispatch_icall
0x180013aba  nop
0x180013abb  mov     rcx, [rsp+0C8h+var_A8]
0x180013ac0  test    rcx, rcx
0x180013ac3  jz      short loc_180013AD2
0x180013ac5  mov     rax, [rcx]
0x180013ac8  mov     rax, [rax+10h]
0x180013acc  call    _guard_dispatch_icall
0x180013ad1  nop
0x180013ad2  mov     rcx, [rsp+0C8h+var_48]
0x180013ada  test    rcx, rcx
0x180013add  jz      short loc_180013B05
0x180013adf  mov     rax, [rcx]
0x180013ae2  lea     rdx, [rsp+0C8h+var_40]
0x180013aea  mov     rax, [rax+58h]
0x180013aee  call    _guard_dispatch_icall
0x180013af3  mov     rcx, [rsp+0C8h]; this
0x180013afb  test    eax, eax
0x180013afd  js      loc_180013BD6
0x180013b03  jmp     short loc_180013B6E
0x180013b05  mov     [rsp+0C8h+var_98], 0
0x180013b0e  mov     [rsp+0C8h+var_90], 0
0x180013b17  lea     rax, aIdockedclient3_0; "IDockedClient3 is not present, skipping"...
0x180013b1e  mov     [rsp+0C8h+var_88], rax
0x180013b23  mov     [rsp+0C8h+var_80], 35h ; '5'
0x180013b2c  lea     r8, [rsp+0C8h+var_98]
0x180013b31  lea     rdx, [rsp+0C8h+var_88]
0x180013b36  lea     rcx, [rsp+0C8h+Src]; Src
0x180013b3b  call    ??$vformat@$0A@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@V?$basic_string_view@_WU?$char_traits@_W@std@@@0@V?$basic_format_args@V?$basic_format_context@V?$back_insert_iterator@V?$_Fmt_buffer@_W@std@@@std@@_W@std@@@0@@Z; std::vformat<0>(std::wstring_view,std::basic_format_args<std::basic_format_context<std::back_insert_iterator<std::_Fmt_buffer<wchar_t>>,wchar_t>>)
0x180013b40  cmp     qword ptr [rax+18h], 7
0x180013b45  jbe     short loc_180013B4A
0x180013b47  mov     rax, [rax]
0x180013b4a  mov     [rsp+0C8h+var_A8], rax
0x180013b4f  lea     rcx, [rsp+0C8h+var_A8]
0x180013b54  call    ??$Message@PEB_W@ClientTelemetry@@SAX$$QEAPEB_W@Z; ClientTelemetry::Message<wchar_t const *>(wchar_t const * &&)
0x180013b59  lea     rcx, [rsp+0C8h+Src]; void *
0x180013b5e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180013b63  mov     dword ptr [rsp+0C8h+var_40], 1
0x180013b6e  mov     rcx, [rsp+0C8h+var_48]
0x180013b76  test    rcx, rcx
0x180013b79  jz      short loc_180013B88
0x180013b7b  mov     rax, [rcx]
0x180013b7e  mov     rax, [rax+10h]
0x180013b82  call    _guard_dispatch_icall
0x180013b87  nop
0x180013b88  movups  xmm0, [rsp+0C8h+var_40]
0x180013b90  movaps  [rsp+0C8h+Src], xmm0
0x180013b95  movups  xmm1, [rsp+0C8h+var_30]
0x180013b9d  movaps  [rsp+0C8h+var_68], xmm1
0x180013ba2  mov     eax, [rsp+0C8h+var_20]
0x180013ba9  mov     [rsp+0C8h+var_58], eax
0x180013bad  lea     rdx, [rsp+0C8h+Src]
0x180013bb2  lea     rcx, aOutlookupdate; "OutlookUpdate"
0x180013bb9  call    ?ReportExpeditedUpdateWorkCompleted@@YAXPEB_WUtagAppUpdateResult@@@Z; ReportExpeditedUpdateWorkCompleted(wchar_t const *,tagAppUpdateResult)
0x180013bbe  mov     rcx, [rsp+0C8h+var_18]
0x180013bc6  xor     rcx, rsp; StackCookie
0x180013bc9  call    __security_check_cookie
0x180013bce  add     rsp, 0C8h
0x180013bd5  retn
0x180013bd6  mov     r9d, eax; char *
0x180013bd9  lea     r8, aCW1SSrcOrchest_3; "C:\\__w\\1\\s\\src\\orchestrator\\clien"...
0x180013be0  mov     edx, 449h; void *
0x180013be5  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
