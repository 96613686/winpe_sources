# CApplicationFrameInputPaneWindowService::RegisterService(IApplicationFrameInternal *)

- ea: `0x18001b50c`
- end: `0x18001b5e2`
- name: `?RegisterService@CApplicationFrameInputPaneWindowService@@QEAAJPEAUIApplicationFrameInternal@@@Z`
- size: `214`
- prototype: `int(CApplicationFrameInputPaneWindowService *__hidden this, struct IApplicationFrameInternal *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180026580`

## callees

- `0x180003e30`
- `0x180004c98`
- `0x18001b50c`
- `0x18001b644`
- `0x180040270`
- `0x180072010`

## import_xrefs

- `TWINAPI!__imp_RegisterWindowService` at `0x18001b5a7`
- `TWINAPI!__imp_RegisterWindowService` at `0x18001b5a7`

## string_xrefs

- `0x18001b570`: `pcshell\shell\applicationframe\frame\lib\inputpanewindowservice.cpp`
- `0x18001b5b8`: `pcshell\shell\applicationframe\frame\lib\inputpanewindowservice.cpp`

## pseudocode

```c
__int64 __fastcall CApplicationFrameInputPaneWindowService::RegisterService(
        CApplicationFrameInputPaneWindowService *this,
        struct IApplicationFrameInternal *a2)
{
  int v4; // edi
  __int64 v5; // rdx
  int v7; // eax
  unsigned int v8; // ebx
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  struct IApplicationFrameInternal *v11; // [rsp+30h] [rbp+8h] BYREF

  if ( *((struct IApplicationFrameInternal **)this + 6) != a2 )
  {
    v11 = a2;
    Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>::InternalAddRef(&v11);
    v11 = (struct IApplicationFrameInternal *)*((_QWORD *)this + 6);
    *((_QWORD *)this + 6) = a2;
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v11);
  }
  v4 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 6) + 24LL))(
         *((_QWORD *)this + 6),
         (char *)this + 56);
  if ( v4 < 0 )
  {
    v5 = 28;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\inputpanewindowservice.cpp",
      (const char *)(unsigned int)v4,
      v9);
    return (unsigned int)v4;
  }
  v4 = Microsoft::WRL::Details::MakeAndInitialize<CreationThreadDispatcher,CreationThreadDispatcher,>((char *)this + 64);
  if ( v4 < 0 )
  {
    v5 = 31;
    goto LABEL_5;
  }
  v7 = RegisterWindowService(*((_QWORD *)this + 7), &SID_ApplicationFrameInputPaneEventHandler, this);
  v8 = v7;
  if ( v7 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x21,
    (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\inputpanewindowservice.cpp",
    (const char *)(unsigned int)v7,
    v9);
  return v8;
}

```

## disassembly

```asm
0x18001b50c  mov     rax, rsp
0x18001b50f  mov     [rax+10h], rbx
0x18001b513  mov     [rax+18h], rsi
0x18001b517  push    rdi; int
0x18001b518  sub     rsp, 20h
0x18001b51c  mov     rdi, rdx
0x18001b51f  mov     rbx, rcx
0x18001b522  cmp     [rcx+30h], rdx
0x18001b526  jz      short loc_18001B54C
0x18001b528  lea     rcx, [rax+8]
0x18001b52c  mov     [rax+8], rdx
0x18001b530  call    ?InternalAddRef@?$ComPtr@UIApplicationFrameTitleBarAccElementInternal@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>::InternalAddRef(void)
0x18001b535  mov     rax, [rbx+30h]
0x18001b539  lea     rcx, [rsp+28h+arg_0]
0x18001b53e  mov     [rsp+28h+arg_0], rax
0x18001b543  mov     [rbx+30h], rdi
0x18001b547  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18001b54c  mov     rcx, [rbx+30h]
0x18001b550  lea     rdx, [rbx+38h]
0x18001b554  mov     rax, [rcx]
0x18001b557  mov     rax, [rax+18h]
0x18001b55b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b560  mov     edi, eax
0x18001b562  test    eax, eax
0x18001b564  jns     short loc_18001B583
0x18001b566  mov     edx, 1Ch; void *
0x18001b56b  mov     rcx, [rsp+28h]; this
0x18001b570  lea     r8, aPcshellShellAp_9; "pcshell\\shell\\applicationframe\\frame"...
0x18001b577  mov     r9d, edi; char *
0x18001b57a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b57f  mov     eax, edi
0x18001b581  jmp     short loc_18001B5D2
0x18001b583  lea     rcx, [rbx+40h]
0x18001b587  call    ??$MakeAndInitialize@VCreationThreadDispatcher@@V1@$$V@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VCreationThreadDispatcher@@@WRL@Microsoft@@@012@@Z; Microsoft::WRL::Details::MakeAndInitialize<CreationThreadDispatcher,CreationThreadDispatcher,>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<CreationThreadDispatcher>>)
0x18001b58c  mov     edi, eax
0x18001b58e  test    eax, eax
0x18001b590  jns     short loc_18001B599
0x18001b592  mov     edx, 1Fh
0x18001b597  jmp     short loc_18001B56B
0x18001b599  mov     rcx, [rbx+38h]
0x18001b59d  lea     rdx, SID_ApplicationFrameInputPaneEventHandler
0x18001b5a4  mov     r8, rbx
0x18001b5a7  call    cs:__imp_RegisterWindowService
0x18001b5ad  mov     ebx, eax
0x18001b5af  test    eax, eax
0x18001b5b1  jns     short loc_18001B5D0
0x18001b5b3  mov     rcx, [rsp+28h]; this
0x18001b5b8  lea     r8, aPcshellShellAp_9; "pcshell\\shell\\applicationframe\\frame"...
0x18001b5bf  mov     r9d, eax; char *
0x18001b5c2  mov     edx, 21h ; '!'; void *
0x18001b5c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b5cc  mov     eax, ebx
0x18001b5ce  jmp     short loc_18001B5D2
0x18001b5d0  xor     eax, eax
0x18001b5d2  mov     rbx, [rsp+28h+arg_8]
0x18001b5d7  mov     rsi, [rsp+28h+arg_10]
0x18001b5dc  add     rsp, 20h
0x18001b5e0  pop     rdi
0x18001b5e1  retn
```
