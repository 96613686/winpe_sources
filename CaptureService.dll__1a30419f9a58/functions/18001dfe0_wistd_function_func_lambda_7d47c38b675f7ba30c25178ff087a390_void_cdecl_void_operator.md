# wistd::__function::__func__lambda_7d47c38b675f7ba30c25178ff087a390__void___cdecl(void)_::operator()

- ea: `0x18001dfe0`
- end: `0x18001e054`
- name: `wistd::__function::__func__lambda_7d47c38b675f7ba30c25178ff087a390__void___cdecl(void)_::operator()`
- size: `116`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x180005548`
- `0x180017ac0`
- `0x18001c850`
- `0x18001dfe0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001dff8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001dff8`

## string_xrefs

- `0x18001e042`: `onecoreuap\windows\dwm\capture\svc\dll\capturesessionmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wistd::__function::__func__lambda_7d47c38b675f7ba30c25178ff087a390__void___cdecl_void__::operator()(
        __int64 a1)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  Windows::Graphics::Capture::Server::CaptureSession ***v3; // rax
  Windows::Graphics::Capture::Server::CaptureSession **v4; // rbx
  Windows::Graphics::Capture::Server::CaptureSession **v5; // rdi
  int v6; // eax
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  struct _RTL_CRITICAL_SECTION *v9; // [rsp+30h] [rbp+8h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)(*(_QWORD *)(a1 + 8) + 40LL);
  EnterCriticalSection(v2);
  v9 = v2;
  v3 = *(Windows::Graphics::Capture::Server::CaptureSession ****)(a1 + 8);
  v4 = *v3;
  v5 = v3[1];
  while ( v4 != v5 )
  {
    v6 = Windows::Graphics::Capture::Server::CaptureSession::ReevaluateBorderState(*v4);
    if ( v6 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x18,
        (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturesessionmanager.cpp",
        (const char *)(unsigned int)v6,
        v7);
    ++v4;
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v9);
}

```

## disassembly

```asm
0x18001dfe0  mov     [rsp+arg_8], rbx
0x18001dfe5  push    rdi
0x18001dfe6  sub     rsp, 20h
0x18001dfea  mov     rdi, rcx
0x18001dfed  mov     rbx, [rcx+8]
0x18001dff1  add     rbx, 28h ; '('
0x18001dff5  mov     rcx, rbx; lpCriticalSection
0x18001dff8  call    cs:__imp_EnterCriticalSection
0x18001dffe  mov     [rsp+28h+arg_0], rbx
0x18001e003  mov     rax, [rdi+8]
0x18001e007  mov     rbx, [rax]
0x18001e00a  mov     rdi, [rax+8]
0x18001e00e  jmp     short loc_18001E025
0x18001e010  mov     rcx, [rbx]; this
0x18001e013  call    ?ReevaluateBorderState@CaptureSession@Server@Capture@Graphics@Windows@@QEAAJXZ; Windows::Graphics::Capture::Server::CaptureSession::ReevaluateBorderState(void)
0x18001e018  mov     rcx, [rsp+28h]; this
0x18001e01d  test    eax, eax
0x18001e01f  js      short loc_18001E03F
0x18001e021  add     rbx, 8
0x18001e025  cmp     rbx, rdi
0x18001e028  jnz     short loc_18001E010
0x18001e02a  lea     rcx, [rsp+28h+arg_0]
0x18001e02f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18001e034  mov     rbx, [rsp+28h+arg_8]
0x18001e039  add     rsp, 20h
0x18001e03d  pop     rdi
0x18001e03e  retn
0x18001e03f  mov     r9d, eax; char *
0x18001e042  lea     r8, aOnecoreuapWind_0; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18001e049  mov     edx, 18h; void *
0x18001e04e  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
