# DoCrossDeviceUpdate(void)

- ea: `0x180013d94`
- end: `0x180013f2c`
- name: `?DoCrossDeviceUpdate@@YAXXZ`
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
- `0x180013d94`
- `0x18001932c`
- `0x1800194f8`
- `0x180034a30`
- `0x18003a74c`
- `0x180056500`
- `0x18005c5e0`

## string_xrefs

- `0x180013e57`: `IDockedClient4 is not present, skipping CrossDeviceUpdate`
- `0x180013ef2`: `CrossDeviceUpdate`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void DoCrossDeviceUpdate(void)
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
    (**v0)(v0, &GUID_2ea728dc_7610_4573_bb57_c23ad25345ef, &v7);
    if ( v4[0] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v4[0] + 16LL))(v4[0]);
    if ( v7 )
    {
      v1 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v7 + 104LL))(v7, &v8);
      if ( v1 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x471,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\clientImpl\\ClientImpl.cpp",
          (const char *)(unsigned int)v1,
          v4[0]);
    }
    else
    {
      v4[2] = 0;
      v4[3] = 0;
      v4[4] = L"IDockedClient4 is not present, skipping CrossDeviceUpdate";
      v4[5] = 57;
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
      (void *)0x479,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\clientImpl\\ClientImpl.cpp",
      v2);
  }
  Src[0] = v8;
  Src[1] = v9;
  v6 = v10;
  ReportExpeditedUpdateWorkCompleted(L"CrossDeviceUpdate", Src);
}

```

## disassembly

```asm
0x180013d94  mov     r11, rsp
0x180013d97  sub     rsp, 0C8h
0x180013d9e  mov     rax, cs:__security_cookie
0x180013da5  xor     rax, rsp
0x180013da8  mov     [rsp+0C8h+var_18], rax
0x180013db0  xorps   xmm0, xmm0
0x180013db3  xor     eax, eax
0x180013db5  movups  xmmword ptr [r11-40h], xmm0
0x180013dba  movups  xmmword ptr [r11-30h], xmm0
0x180013dbf  mov     [r11-20h], eax
0x180013dc3  mov     [r11-48h], rax
0x180013dc7  lea     rcx, [rsp+0C8h+var_A8]
0x180013dcc  call    ?GetDockedClient@DockedHelpers@Windows@@YA?AV?$com_ptr_t@UIDockedClient2@@Uerr_exception_policy@wil@@@wil@@XZ; Windows::DockedHelpers::GetDockedClient(void)
0x180013dd1  mov     rcx, [rax]
0x180013dd4  mov     [rsp+0C8h+var_48], 0
0x180013de0  mov     rax, [rcx]
0x180013de3  lea     r8, [rsp+0C8h+var_48]
0x180013deb  lea     rdx, _GUID_2ea728dc_7610_4573_bb57_c23ad25345ef
0x180013df2  mov     rax, [rax]
0x180013df5  call    _guard_dispatch_icall
0x180013dfa  nop
0x180013dfb  mov     rcx, [rsp+0C8h+var_A8]
0x180013e00  test    rcx, rcx
0x180013e03  jz      short loc_180013E12
0x180013e05  mov     rax, [rcx]
0x180013e08  mov     rax, [rax+10h]
0x180013e0c  call    _guard_dispatch_icall
0x180013e11  nop
0x180013e12  mov     rcx, [rsp+0C8h+var_48]
0x180013e1a  test    rcx, rcx
0x180013e1d  jz      short loc_180013E45
0x180013e1f  mov     rax, [rcx]
0x180013e22  lea     rdx, [rsp+0C8h+var_40]
0x180013e2a  mov     rax, [rax+68h]
0x180013e2e  call    _guard_dispatch_icall
0x180013e33  mov     rcx, [rsp+0C8h]; this
0x180013e3b  test    eax, eax
0x180013e3d  js      loc_180013F16
0x180013e43  jmp     short loc_180013EAE
0x180013e45  mov     [rsp+0C8h+var_98], 0
0x180013e4e  mov     [rsp+0C8h+var_90], 0
0x180013e57  lea     rax, aIdockedclient4; "IDockedClient4 is not present, skipping"...
0x180013e5e  mov     [rsp+0C8h+var_88], rax
0x180013e63  mov     [rsp+0C8h+var_80], 39h ; '9'
0x180013e6c  lea     r8, [rsp+0C8h+var_98]
0x180013e71  lea     rdx, [rsp+0C8h+var_88]
0x180013e76  lea     rcx, [rsp+0C8h+Src]; Src
0x180013e7b  call    ??$vformat@$0A@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@V?$basic_string_view@_WU?$char_traits@_W@std@@@0@V?$basic_format_args@V?$basic_format_context@V?$back_insert_iterator@V?$_Fmt_buffer@_W@std@@@std@@_W@std@@@0@@Z; std::vformat<0>(std::wstring_view,std::basic_format_args<std::basic_format_context<std::back_insert_iterator<std::_Fmt_buffer<wchar_t>>,wchar_t>>)
0x180013e80  cmp     qword ptr [rax+18h], 7
0x180013e85  jbe     short loc_180013E8A
0x180013e87  mov     rax, [rax]
0x180013e8a  mov     [rsp+0C8h+var_A8], rax
0x180013e8f  lea     rcx, [rsp+0C8h+var_A8]
0x180013e94  call    ??$Message@PEB_W@ClientTelemetry@@SAX$$QEAPEB_W@Z; ClientTelemetry::Message<wchar_t const *>(wchar_t const * &&)
0x180013e99  lea     rcx, [rsp+0C8h+Src]; void *
0x180013e9e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180013ea3  mov     dword ptr [rsp+0C8h+var_40], 1
0x180013eae  mov     rcx, [rsp+0C8h+var_48]
0x180013eb6  test    rcx, rcx
0x180013eb9  jz      short loc_180013EC8
0x180013ebb  mov     rax, [rcx]
0x180013ebe  mov     rax, [rax+10h]
0x180013ec2  call    _guard_dispatch_icall
0x180013ec7  nop
0x180013ec8  movups  xmm0, [rsp+0C8h+var_40]
0x180013ed0  movaps  [rsp+0C8h+Src], xmm0
0x180013ed5  movups  xmm1, [rsp+0C8h+var_30]
0x180013edd  movaps  [rsp+0C8h+var_68], xmm1
0x180013ee2  mov     eax, [rsp+0C8h+var_20]
0x180013ee9  mov     [rsp+0C8h+var_58], eax
0x180013eed  lea     rdx, [rsp+0C8h+Src]
0x180013ef2  lea     rcx, aCrossdeviceupd; "CrossDeviceUpdate"
0x180013ef9  call    ?ReportExpeditedUpdateWorkCompleted@@YAXPEB_WUtagAppUpdateResult@@@Z; ReportExpeditedUpdateWorkCompleted(wchar_t const *,tagAppUpdateResult)
0x180013efe  mov     rcx, [rsp+0C8h+var_18]
0x180013f06  xor     rcx, rsp; StackCookie
0x180013f09  call    __security_check_cookie
0x180013f0e  add     rsp, 0C8h
0x180013f15  retn
0x180013f16  mov     r9d, eax; char *
0x180013f19  lea     r8, aCW1SSrcOrchest_3; "C:\\__w\\1\\s\\src\\orchestrator\\clien"...
0x180013f20  mov     edx, 471h; void *
0x180013f25  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
