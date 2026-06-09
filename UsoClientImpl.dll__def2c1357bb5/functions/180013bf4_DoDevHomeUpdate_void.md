# DoDevHomeUpdate(void)

- ea: `0x180013bf4`
- end: `0x180013d8c`
- name: `?DoDevHomeUpdate@@YAXXZ`
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
- `0x180013bf4`
- `0x18001932c`
- `0x1800194f8`
- `0x180034a30`
- `0x18003a74c`
- `0x180056500`
- `0x18005c5e0`

## string_xrefs

- `0x180013cb7`: `IDockedClient3 is not present, skipping DevHomeUpdate`
- `0x180013d52`: `DevHomeUpdate`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void DoDevHomeUpdate(void)
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
      v1 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v7 + 96LL))(v7, &v8);
      if ( v1 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x45D,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\clientImpl\\ClientImpl.cpp",
          (const char *)(unsigned int)v1,
          v4[0]);
    }
    else
    {
      v4[2] = 0;
      v4[3] = 0;
      v4[4] = L"IDockedClient3 is not present, skipping DevHomeUpdate";
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
      (void *)0x465,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\clientImpl\\ClientImpl.cpp",
      v2);
  }
  Src[0] = v8;
  Src[1] = v9;
  v6 = v10;
  ReportExpeditedUpdateWorkCompleted(L"DevHomeUpdate", Src);
}

```

## disassembly

```asm
0x180013bf4  mov     r11, rsp
0x180013bf7  sub     rsp, 0C8h
0x180013bfe  mov     rax, cs:__security_cookie
0x180013c05  xor     rax, rsp
0x180013c08  mov     [rsp+0C8h+var_18], rax
0x180013c10  xorps   xmm0, xmm0
0x180013c13  xor     eax, eax
0x180013c15  movups  xmmword ptr [r11-40h], xmm0
0x180013c1a  movups  xmmword ptr [r11-30h], xmm0
0x180013c1f  mov     [r11-20h], eax
0x180013c23  mov     [r11-48h], rax
0x180013c27  lea     rcx, [rsp+0C8h+var_A8]
0x180013c2c  call    ?GetDockedClient@DockedHelpers@Windows@@YA?AV?$com_ptr_t@UIDockedClient2@@Uerr_exception_policy@wil@@@wil@@XZ; Windows::DockedHelpers::GetDockedClient(void)
0x180013c31  mov     rcx, [rax]
0x180013c34  mov     [rsp+0C8h+var_48], 0
0x180013c40  mov     rax, [rcx]
0x180013c43  lea     r8, [rsp+0C8h+var_48]
0x180013c4b  lea     rdx, _GUID_939a7ab6_3ea2_49ae_ab94_41244ce15af0
0x180013c52  mov     rax, [rax]
0x180013c55  call    _guard_dispatch_icall
0x180013c5a  nop
0x180013c5b  mov     rcx, [rsp+0C8h+var_A8]
0x180013c60  test    rcx, rcx
0x180013c63  jz      short loc_180013C72
0x180013c65  mov     rax, [rcx]
0x180013c68  mov     rax, [rax+10h]
0x180013c6c  call    _guard_dispatch_icall
0x180013c71  nop
0x180013c72  mov     rcx, [rsp+0C8h+var_48]
0x180013c7a  test    rcx, rcx
0x180013c7d  jz      short loc_180013CA5
0x180013c7f  mov     rax, [rcx]
0x180013c82  lea     rdx, [rsp+0C8h+var_40]
0x180013c8a  mov     rax, [rax+60h]
0x180013c8e  call    _guard_dispatch_icall
0x180013c93  mov     rcx, [rsp+0C8h]; this
0x180013c9b  test    eax, eax
0x180013c9d  js      loc_180013D76
0x180013ca3  jmp     short loc_180013D0E
0x180013ca5  mov     [rsp+0C8h+var_98], 0
0x180013cae  mov     [rsp+0C8h+var_90], 0
0x180013cb7  lea     rax, aIdockedclient3; "IDockedClient3 is not present, skipping"...
0x180013cbe  mov     [rsp+0C8h+var_88], rax
0x180013cc3  mov     [rsp+0C8h+var_80], 35h ; '5'
0x180013ccc  lea     r8, [rsp+0C8h+var_98]
0x180013cd1  lea     rdx, [rsp+0C8h+var_88]
0x180013cd6  lea     rcx, [rsp+0C8h+Src]; Src
0x180013cdb  call    ??$vformat@$0A@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@V?$basic_string_view@_WU?$char_traits@_W@std@@@0@V?$basic_format_args@V?$basic_format_context@V?$back_insert_iterator@V?$_Fmt_buffer@_W@std@@@std@@_W@std@@@0@@Z; std::vformat<0>(std::wstring_view,std::basic_format_args<std::basic_format_context<std::back_insert_iterator<std::_Fmt_buffer<wchar_t>>,wchar_t>>)
0x180013ce0  cmp     qword ptr [rax+18h], 7
0x180013ce5  jbe     short loc_180013CEA
0x180013ce7  mov     rax, [rax]
0x180013cea  mov     [rsp+0C8h+var_A8], rax
0x180013cef  lea     rcx, [rsp+0C8h+var_A8]
0x180013cf4  call    ??$Message@PEB_W@ClientTelemetry@@SAX$$QEAPEB_W@Z; ClientTelemetry::Message<wchar_t const *>(wchar_t const * &&)
0x180013cf9  lea     rcx, [rsp+0C8h+Src]; void *
0x180013cfe  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180013d03  mov     dword ptr [rsp+0C8h+var_40], 1
0x180013d0e  mov     rcx, [rsp+0C8h+var_48]
0x180013d16  test    rcx, rcx
0x180013d19  jz      short loc_180013D28
0x180013d1b  mov     rax, [rcx]
0x180013d1e  mov     rax, [rax+10h]
0x180013d22  call    _guard_dispatch_icall
0x180013d27  nop
0x180013d28  movups  xmm0, [rsp+0C8h+var_40]
0x180013d30  movaps  [rsp+0C8h+Src], xmm0
0x180013d35  movups  xmm1, [rsp+0C8h+var_30]
0x180013d3d  movaps  [rsp+0C8h+var_68], xmm1
0x180013d42  mov     eax, [rsp+0C8h+var_20]
0x180013d49  mov     [rsp+0C8h+var_58], eax
0x180013d4d  lea     rdx, [rsp+0C8h+Src]
0x180013d52  lea     rcx, aDevhomeupdate; "DevHomeUpdate"
0x180013d59  call    ?ReportExpeditedUpdateWorkCompleted@@YAXPEB_WUtagAppUpdateResult@@@Z; ReportExpeditedUpdateWorkCompleted(wchar_t const *,tagAppUpdateResult)
0x180013d5e  mov     rcx, [rsp+0C8h+var_18]
0x180013d66  xor     rcx, rsp; StackCookie
0x180013d69  call    __security_check_cookie
0x180013d6e  add     rsp, 0C8h
0x180013d75  retn
0x180013d76  mov     r9d, eax; char *
0x180013d79  lea     r8, aCW1SSrcOrchest_3; "C:\\__w\\1\\s\\src\\orchestrator\\clien"...
0x180013d80  mov     edx, 45Dh; void *
0x180013d85  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
