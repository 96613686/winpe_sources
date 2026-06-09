# SignInToMSATask::IsCurrentUserConnected(void)

- ea: `0x180025958`
- end: `0x180025a06`
- name: `?IsCurrentUserConnected@SignInToMSATask@@AEAA_NXZ`
- size: `174`
- prototype: `bool __fastcall(SignInToMSATask *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180025e40`

## callees

- `0x18000e330`
- `0x18001094c`
- `0x180025958`
- `0x180050010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180025988`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180025988`

## string_xrefs

- `0x18002599a`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\signintomsatask.cpp`
- `0x1800259d6`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\signintomsatask.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool __fastcall SignInToMSATask::IsCurrentUserConnected(SignInToMSATask *this)
{
  HRESULT v1; // eax
  int v2; // eax
  bool v3; // bl
  int v5; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  SignInToMSATask *v7; // [rsp+40h] [rbp+8h] BYREF
  LPVOID v8; // [rsp+48h] [rbp+10h] BYREF

  v7 = this;
  v8 = 0;
  v1 = CoCreateInstance(
         &GUID_30d49246_d217_465f_b00b_ac9ddd652eb7,
         0,
         1u,
         &GUID_7c0c01e3_b1d3_4823_8441_c39e08bf02fa,
         &v8);
  if ( v1 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF0,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\signintomsatask.cpp",
      (const char *)(unsigned int)v1,
      v5);
  LODWORD(v7) = 0;
  v2 = (*(__int64 (__fastcall **)(LPVOID, SignInToMSATask **))(*(_QWORD *)v8 + 48LL))(v8, &v7);
  if ( v2 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF2,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\signintomsatask.cpp",
      (const char *)(unsigned int)v2,
      v5);
  v3 = (unsigned int)((_DWORD)v7 - 1) <= 1;
  wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(&v8);
  return v3;
}

```

## disassembly

```asm
0x180025958  mov     r11, rsp
0x18002595b  mov     [r11+8], rcx
0x18002595f  push    rbx
0x180025960  sub     rsp, 30h
0x180025964  mov     qword ptr [r11+10h], 0
0x18002596c  lea     rax, [r11+10h]
0x180025970  mov     [r11-18h], rax
0x180025974  lea     r9, _GUID_7c0c01e3_b1d3_4823_8441_c39e08bf02fa; riid
0x18002597b  xor     edx, edx; pUnkOuter
0x18002597d  lea     r8d, [rdx+1]; dwClsContext
0x180025981  lea     rcx, _GUID_30d49246_d217_465f_b00b_ac9ddd652eb7; rclsid
0x180025988  call    cs:__imp_CoCreateInstance
0x18002598e  mov     rcx, [rsp+38h]; this
0x180025993  test    eax, eax
0x180025995  jns     short loc_1800259AC
0x180025997  mov     r9d, eax; char *
0x18002599a  lea     r8, aPcshellShellRe_18; "pcshell\\shell\\retaildemo\\desktoptask"...
0x1800259a1  mov     edx, 0F0h; void *
0x1800259a6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800259ac  mov     dword ptr [rsp+38h+arg_0], 0
0x1800259b4  mov     rcx, [rsp+38h+arg_8]
0x1800259b9  mov     rax, [rcx]
0x1800259bc  lea     rdx, [rsp+38h+arg_0]
0x1800259c1  mov     rax, [rax+30h]
0x1800259c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800259ca  mov     rcx, [rsp+38h]; this
0x1800259cf  test    eax, eax
0x1800259d1  jns     short loc_1800259E8
0x1800259d3  mov     r9d, eax; char *
0x1800259d6  lea     r8, aPcshellShellRe_18; "pcshell\\shell\\retaildemo\\desktoptask"...
0x1800259dd  mov     edx, 0F2h; void *
0x1800259e2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800259e8  mov     eax, dword ptr [rsp+38h+arg_0]
0x1800259ec  dec     eax
0x1800259ee  cmp     eax, 1
0x1800259f1  setbe   bl
0x1800259f4  lea     rcx, [rsp+38h+arg_8]
0x1800259f9  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x1800259fe  mov     al, bl
0x180025a00  add     rsp, 30h
0x180025a04  pop     rbx
0x180025a05  retn
```
