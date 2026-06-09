# DoPCManagerUpdate(void)

- ea: `0x180013f34`
- end: `0x1800140cc`
- name: `?DoPCManagerUpdate@@YAXXZ`
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
- `0x180013f34`
- `0x18001932c`
- `0x1800194f8`
- `0x180034a30`
- `0x18003a74c`
- `0x180056500`
- `0x18005c5e0`

## string_xrefs

- `0x180013ff7`: `IDockedClient5 is not present, skipping PCManagerUpdate`
- `0x180014092`: `PCManagerUpdate`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void DoPCManagerUpdate(void)
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
    (**v0)(v0, &GUID_aa2b3e71_09bc_482d_a4a7_6cba805d8cd4, &v7);
    if ( v4[0] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v4[0] + 16LL))(v4[0]);
    if ( v7 )
    {
      v1 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v7 + 112LL))(v7, &v8);
      if ( v1 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x485,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\clientImpl\\ClientImpl.cpp",
          (const char *)(unsigned int)v1,
          v4[0]);
    }
    else
    {
      v4[2] = 0;
      v4[3] = 0;
      v4[4] = L"IDockedClient5 is not present, skipping PCManagerUpdate";
      v4[5] = 55;
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
      (void *)0x48D,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\clientImpl\\ClientImpl.cpp",
      v2);
  }
  Src[0] = v8;
  Src[1] = v9;
  v6 = v10;
  ReportExpeditedUpdateWorkCompleted(L"PCManagerUpdate", Src);
}

```

## disassembly

```asm
0x180013f34  mov     r11, rsp
0x180013f37  sub     rsp, 0C8h
0x180013f3e  mov     rax, cs:__security_cookie
0x180013f45  xor     rax, rsp
0x180013f48  mov     [rsp+0C8h+var_18], rax
0x180013f50  xorps   xmm0, xmm0
0x180013f53  xor     eax, eax
0x180013f55  movups  xmmword ptr [r11-40h], xmm0
0x180013f5a  movups  xmmword ptr [r11-30h], xmm0
0x180013f5f  mov     [r11-20h], eax
0x180013f63  mov     [r11-48h], rax
0x180013f67  lea     rcx, [rsp+0C8h+var_A8]
0x180013f6c  call    ?GetDockedClient@DockedHelpers@Windows@@YA?AV?$com_ptr_t@UIDockedClient2@@Uerr_exception_policy@wil@@@wil@@XZ; Windows::DockedHelpers::GetDockedClient(void)
0x180013f71  mov     rcx, [rax]
0x180013f74  mov     [rsp+0C8h+var_48], 0
0x180013f80  mov     rax, [rcx]
0x180013f83  lea     r8, [rsp+0C8h+var_48]
0x180013f8b  lea     rdx, _GUID_aa2b3e71_09bc_482d_a4a7_6cba805d8cd4
0x180013f92  mov     rax, [rax]
0x180013f95  call    _guard_dispatch_icall
0x180013f9a  nop
0x180013f9b  mov     rcx, [rsp+0C8h+var_A8]
0x180013fa0  test    rcx, rcx
0x180013fa3  jz      short loc_180013FB2
0x180013fa5  mov     rax, [rcx]
0x180013fa8  mov     rax, [rax+10h]
0x180013fac  call    _guard_dispatch_icall
0x180013fb1  nop
0x180013fb2  mov     rcx, [rsp+0C8h+var_48]
0x180013fba  test    rcx, rcx
0x180013fbd  jz      short loc_180013FE5
0x180013fbf  mov     rax, [rcx]
0x180013fc2  lea     rdx, [rsp+0C8h+var_40]
0x180013fca  mov     rax, [rax+70h]
0x180013fce  call    _guard_dispatch_icall
0x180013fd3  mov     rcx, [rsp+0C8h]; this
0x180013fdb  test    eax, eax
0x180013fdd  js      loc_1800140B6
0x180013fe3  jmp     short loc_18001404E
0x180013fe5  mov     [rsp+0C8h+var_98], 0
0x180013fee  mov     [rsp+0C8h+var_90], 0
0x180013ff7  lea     rax, aIdockedclient5; "IDockedClient5 is not present, skipping"...
0x180013ffe  mov     [rsp+0C8h+var_88], rax
0x180014003  mov     [rsp+0C8h+var_80], 37h ; '7'
0x18001400c  lea     r8, [rsp+0C8h+var_98]
0x180014011  lea     rdx, [rsp+0C8h+var_88]
0x180014016  lea     rcx, [rsp+0C8h+Src]; Src
0x18001401b  call    ??$vformat@$0A@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@V?$basic_string_view@_WU?$char_traits@_W@std@@@0@V?$basic_format_args@V?$basic_format_context@V?$back_insert_iterator@V?$_Fmt_buffer@_W@std@@@std@@_W@std@@@0@@Z; std::vformat<0>(std::wstring_view,std::basic_format_args<std::basic_format_context<std::back_insert_iterator<std::_Fmt_buffer<wchar_t>>,wchar_t>>)
0x180014020  cmp     qword ptr [rax+18h], 7
0x180014025  jbe     short loc_18001402A
0x180014027  mov     rax, [rax]
0x18001402a  mov     [rsp+0C8h+var_A8], rax
0x18001402f  lea     rcx, [rsp+0C8h+var_A8]
0x180014034  call    ??$Message@PEB_W@ClientTelemetry@@SAX$$QEAPEB_W@Z; ClientTelemetry::Message<wchar_t const *>(wchar_t const * &&)
0x180014039  lea     rcx, [rsp+0C8h+Src]; void *
0x18001403e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180014043  mov     dword ptr [rsp+0C8h+var_40], 1
0x18001404e  mov     rcx, [rsp+0C8h+var_48]
0x180014056  test    rcx, rcx
0x180014059  jz      short loc_180014068
0x18001405b  mov     rax, [rcx]
0x18001405e  mov     rax, [rax+10h]
0x180014062  call    _guard_dispatch_icall
0x180014067  nop
0x180014068  movups  xmm0, [rsp+0C8h+var_40]
0x180014070  movaps  [rsp+0C8h+Src], xmm0
0x180014075  movups  xmm1, [rsp+0C8h+var_30]
0x18001407d  movaps  [rsp+0C8h+var_68], xmm1
0x180014082  mov     eax, [rsp+0C8h+var_20]
0x180014089  mov     [rsp+0C8h+var_58], eax
0x18001408d  lea     rdx, [rsp+0C8h+Src]
0x180014092  lea     rcx, aPcmanagerupdat; "PCManagerUpdate"
0x180014099  call    ?ReportExpeditedUpdateWorkCompleted@@YAXPEB_WUtagAppUpdateResult@@@Z; ReportExpeditedUpdateWorkCompleted(wchar_t const *,tagAppUpdateResult)
0x18001409e  mov     rcx, [rsp+0C8h+var_18]
0x1800140a6  xor     rcx, rsp; StackCookie
0x1800140a9  call    __security_check_cookie
0x1800140ae  add     rsp, 0C8h
0x1800140b5  retn
0x1800140b6  mov     r9d, eax; char *
0x1800140b9  lea     r8, aCW1SSrcOrchest_3; "C:\\__w\\1\\s\\src\\orchestrator\\clien"...
0x1800140c0  mov     edx, 485h; void *
0x1800140c5  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
