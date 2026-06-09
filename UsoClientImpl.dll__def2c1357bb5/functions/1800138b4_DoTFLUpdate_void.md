# DoTFLUpdate(void)

- ea: `0x1800138b4`
- end: `0x180013a4c`
- name: `?DoTFLUpdate@@YAXXZ`
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
- `0x1800138b4`
- `0x18001932c`
- `0x1800194f8`
- `0x180034a30`
- `0x18003a74c`
- `0x180056500`
- `0x18005c5e0`

## string_xrefs

- `0x180013a12`: `TFLUpdate`
- `0x180013977`: `IDockedClient3 is not present, skipping TFLUpdate`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void DoTFLUpdate(void)
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
      v1 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v7 + 80LL))(v7, &v8);
      if ( v1 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x435,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\clientImpl\\ClientImpl.cpp",
          (const char *)(unsigned int)v1,
          v4[0]);
    }
    else
    {
      v4[2] = 0;
      v4[3] = 0;
      v4[4] = L"IDockedClient3 is not present, skipping TFLUpdate";
      v4[5] = 49;
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
      (void *)0x43D,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\clientImpl\\ClientImpl.cpp",
      v2);
  }
  Src[0] = v8;
  Src[1] = v9;
  v6 = v10;
  ReportExpeditedUpdateWorkCompleted(L"TFLUpdate", Src);
}

```

## disassembly

```asm
0x1800138b4  mov     r11, rsp
0x1800138b7  sub     rsp, 0C8h
0x1800138be  mov     rax, cs:__security_cookie
0x1800138c5  xor     rax, rsp
0x1800138c8  mov     [rsp+0C8h+var_18], rax
0x1800138d0  xorps   xmm0, xmm0
0x1800138d3  xor     eax, eax
0x1800138d5  movups  xmmword ptr [r11-40h], xmm0
0x1800138da  movups  xmmword ptr [r11-30h], xmm0
0x1800138df  mov     [r11-20h], eax
0x1800138e3  mov     [r11-48h], rax
0x1800138e7  lea     rcx, [rsp+0C8h+var_A8]
0x1800138ec  call    ?GetDockedClient@DockedHelpers@Windows@@YA?AV?$com_ptr_t@UIDockedClient2@@Uerr_exception_policy@wil@@@wil@@XZ; Windows::DockedHelpers::GetDockedClient(void)
0x1800138f1  mov     rcx, [rax]
0x1800138f4  mov     [rsp+0C8h+var_48], 0
0x180013900  mov     rax, [rcx]
0x180013903  lea     r8, [rsp+0C8h+var_48]
0x18001390b  lea     rdx, _GUID_939a7ab6_3ea2_49ae_ab94_41244ce15af0
0x180013912  mov     rax, [rax]
0x180013915  call    _guard_dispatch_icall
0x18001391a  nop
0x18001391b  mov     rcx, [rsp+0C8h+var_A8]
0x180013920  test    rcx, rcx
0x180013923  jz      short loc_180013932
0x180013925  mov     rax, [rcx]
0x180013928  mov     rax, [rax+10h]
0x18001392c  call    _guard_dispatch_icall
0x180013931  nop
0x180013932  mov     rcx, [rsp+0C8h+var_48]
0x18001393a  test    rcx, rcx
0x18001393d  jz      short loc_180013965
0x18001393f  mov     rax, [rcx]
0x180013942  lea     rdx, [rsp+0C8h+var_40]
0x18001394a  mov     rax, [rax+50h]
0x18001394e  call    _guard_dispatch_icall
0x180013953  mov     rcx, [rsp+0C8h]; this
0x18001395b  test    eax, eax
0x18001395d  js      loc_180013A36
0x180013963  jmp     short loc_1800139CE
0x180013965  mov     [rsp+0C8h+var_98], 0
0x18001396e  mov     [rsp+0C8h+var_90], 0
0x180013977  lea     rax, aIdockedclient3_1; "IDockedClient3 is not present, skipping"...
0x18001397e  mov     [rsp+0C8h+var_88], rax
0x180013983  mov     [rsp+0C8h+var_80], 31h ; '1'
0x18001398c  lea     r8, [rsp+0C8h+var_98]
0x180013991  lea     rdx, [rsp+0C8h+var_88]
0x180013996  lea     rcx, [rsp+0C8h+Src]; Src
0x18001399b  call    ??$vformat@$0A@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@V?$basic_string_view@_WU?$char_traits@_W@std@@@0@V?$basic_format_args@V?$basic_format_context@V?$back_insert_iterator@V?$_Fmt_buffer@_W@std@@@std@@_W@std@@@0@@Z; std::vformat<0>(std::wstring_view,std::basic_format_args<std::basic_format_context<std::back_insert_iterator<std::_Fmt_buffer<wchar_t>>,wchar_t>>)
0x1800139a0  cmp     qword ptr [rax+18h], 7
0x1800139a5  jbe     short loc_1800139AA
0x1800139a7  mov     rax, [rax]
0x1800139aa  mov     [rsp+0C8h+var_A8], rax
0x1800139af  lea     rcx, [rsp+0C8h+var_A8]
0x1800139b4  call    ??$Message@PEB_W@ClientTelemetry@@SAX$$QEAPEB_W@Z; ClientTelemetry::Message<wchar_t const *>(wchar_t const * &&)
0x1800139b9  lea     rcx, [rsp+0C8h+Src]; void *
0x1800139be  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800139c3  mov     dword ptr [rsp+0C8h+var_40], 1
0x1800139ce  mov     rcx, [rsp+0C8h+var_48]
0x1800139d6  test    rcx, rcx
0x1800139d9  jz      short loc_1800139E8
0x1800139db  mov     rax, [rcx]
0x1800139de  mov     rax, [rax+10h]
0x1800139e2  call    _guard_dispatch_icall
0x1800139e7  nop
0x1800139e8  movups  xmm0, [rsp+0C8h+var_40]
0x1800139f0  movaps  [rsp+0C8h+Src], xmm0
0x1800139f5  movups  xmm1, [rsp+0C8h+var_30]
0x1800139fd  movaps  [rsp+0C8h+var_68], xmm1
0x180013a02  mov     eax, [rsp+0C8h+var_20]
0x180013a09  mov     [rsp+0C8h+var_58], eax
0x180013a0d  lea     rdx, [rsp+0C8h+Src]
0x180013a12  lea     rcx, aTflupdate; "TFLUpdate"
0x180013a19  call    ?ReportExpeditedUpdateWorkCompleted@@YAXPEB_WUtagAppUpdateResult@@@Z; ReportExpeditedUpdateWorkCompleted(wchar_t const *,tagAppUpdateResult)
0x180013a1e  mov     rcx, [rsp+0C8h+var_18]
0x180013a26  xor     rcx, rsp; StackCookie
0x180013a29  call    __security_check_cookie
0x180013a2e  add     rsp, 0C8h
0x180013a35  retn
0x180013a36  mov     r9d, eax; char *
0x180013a39  lea     r8, aCW1SSrcOrchest_3; "C:\\__w\\1\\s\\src\\orchestrator\\clien"...
0x180013a40  mov     edx, 435h; void *
0x180013a45  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
