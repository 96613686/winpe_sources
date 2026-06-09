# IsMsaDefaultAccount

- ea: `0x18003e048`
- end: `0x18003e0f3`
- name: `IsMsaDefaultAccount`
- size: `171`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180039fa0`

## callees

- `0x18000e330`
- `0x18001094c`
- `0x18003e048`
- `0x180050010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003e075`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003e075`

## string_xrefs

- `0x18003e087`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x18003e0c3`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool IsMsaDefaultAccount()
{
  HRESULT v0; // eax
  int v1; // eax
  bool v2; // bl
  int ppv; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int v6; // [rsp+40h] [rbp+8h] BYREF
  LPVOID v7; // [rsp+48h] [rbp+10h] BYREF

  v7 = 0;
  v0 = CoCreateInstance(
         &GUID_30d49246_d217_465f_b00b_ac9ddd652eb7,
         0,
         1u,
         &GUID_7c0c01e3_b1d3_4823_8441_c39e08bf02fa,
         &v7);
  if ( v0 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x7D1,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
      (const char *)(unsigned int)v0,
      ppv);
  v6 = 0;
  v1 = (*(__int64 (__fastcall **)(LPVOID, int *))(*(_QWORD *)v7 + 48LL))(v7, &v6);
  if ( v1 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x7D3,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
      (const char *)(unsigned int)v1,
      ppv);
  v2 = (unsigned int)(v6 - 1) <= 1;
  wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(&v7);
  return v2;
}

```

## disassembly

```asm
0x18003e048  push    rbx
0x18003e04a  sub     rsp, 30h
0x18003e04e  mov     [rsp+38h+arg_8], 0
0x18003e057  lea     rax, [rsp+38h+arg_8]
0x18003e05c  mov     qword ptr [rsp+38h+ppv], rax; int
0x18003e061  lea     r9, _GUID_7c0c01e3_b1d3_4823_8441_c39e08bf02fa; riid
0x18003e068  xor     edx, edx; pUnkOuter
0x18003e06a  lea     r8d, [rdx+1]; dwClsContext
0x18003e06e  lea     rcx, _GUID_30d49246_d217_465f_b00b_ac9ddd652eb7; rclsid
0x18003e075  call    cs:__imp_CoCreateInstance
0x18003e07b  mov     rcx, [rsp+38h]; this
0x18003e080  test    eax, eax
0x18003e082  jns     short loc_18003E099
0x18003e084  mov     r9d, eax; char *
0x18003e087  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18003e08e  mov     edx, 7D1h; void *
0x18003e093  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003e099  mov     [rsp+38h+arg_0], 0
0x18003e0a1  mov     rcx, [rsp+38h+arg_8]
0x18003e0a6  mov     rax, [rcx]
0x18003e0a9  lea     rdx, [rsp+38h+arg_0]
0x18003e0ae  mov     rax, [rax+30h]
0x18003e0b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e0b7  mov     rcx, [rsp+38h]; this
0x18003e0bc  test    eax, eax
0x18003e0be  jns     short loc_18003E0D5
0x18003e0c0  mov     r9d, eax; char *
0x18003e0c3  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18003e0ca  mov     edx, 7D3h; void *
0x18003e0cf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003e0d5  mov     eax, [rsp+38h+arg_0]
0x18003e0d9  dec     eax
0x18003e0db  cmp     eax, 1
0x18003e0de  setbe   bl
0x18003e0e1  lea     rcx, [rsp+38h+arg_8]
0x18003e0e6  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x18003e0eb  mov     al, bl
0x18003e0ed  add     rsp, 30h
0x18003e0f1  pop     rbx
0x18003e0f2  retn
```
