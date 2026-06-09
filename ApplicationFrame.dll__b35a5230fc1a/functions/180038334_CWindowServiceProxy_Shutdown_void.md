# CWindowServiceProxy::Shutdown(void)

- ea: `0x180038334`
- end: `0x180038399`
- name: `?Shutdown@CWindowServiceProxy@@QEAAXXZ`
- size: `101`
- prototype: `void __fastcall(CWindowServiceProxy *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800032e4`

## callees

- `0x180004c98`
- `0x180038334`
- `0x18004bb84`
- `0x180072010`

## import_xrefs

- `TWINAPI!__imp_UnregisterWindowService` at `0x180038385`
- `TWINAPI!__imp_UnregisterWindowService` at `0x180038385`

## string_xrefs

- `0x180038364`: `pcshell\shell\applicationframe\frame\lib\windowserviceproxy.cpp`

## pseudocode

```c
void __fastcall CWindowServiceProxy::Shutdown(CWindowServiceProxy *this)
{
  char *v1; // rbx
  int v2; // eax
  int v3; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v5; // [rsp+30h] [rbp+8h] BYREF

  v1 = (char *)this + 16;
  v5 = 0;
  v2 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 2) + 24LL))(*((_QWORD *)this + 2), &v5);
  if ( v2 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1C,
      (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\windowserviceproxy.cpp",
      (const char *)(unsigned int)v2,
      v3);
  UnregisterWindowService(v5, &IID_IWindowServiceProxy);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(v1);
}

```

## disassembly

```asm
0x180038334  push    rbx; int
0x180038336  sub     rsp, 20h
0x18003833a  lea     rbx, [rcx+10h]
0x18003833e  mov     [rsp+28h+arg_0], 0
0x180038347  mov     rcx, [rbx]
0x18003834a  lea     rdx, [rsp+28h+arg_0]
0x18003834f  mov     rax, [rcx]
0x180038352  mov     rax, [rax+18h]
0x180038356  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003835b  test    eax, eax
0x18003835d  jns     short loc_180038379
0x18003835f  mov     rcx, [rsp+28h]; this
0x180038364  lea     r8, aPcshellShellAp_4; "pcshell\\shell\\applicationframe\\frame"...
0x18003836b  mov     r9d, eax; char *
0x18003836e  mov     edx, 1Ch; void *
0x180038373  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180038379  mov     rcx, [rsp+28h+arg_0]
0x18003837e  lea     rdx, IID_IWindowServiceProxy
0x180038385  call    cs:__imp_UnregisterWindowService
0x18003838b  mov     rcx, rbx
0x18003838e  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180038393  add     rsp, 20h
0x180038397  pop     rbx
0x180038398  retn
```
