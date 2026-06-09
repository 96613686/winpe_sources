# CreateSystemObjectTask::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x140007ad0`
- end: `0x140007b76`
- name: `?CreateInstance@CreateSystemObjectTask@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `166`
- prototype: `__int64 __fastcall(CreateSystemObjectTask *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x140004340`
- `0x140004d74`
- `0x140006680`
- `0x140007ad0`
- `0x14000a010`

## string_xrefs

- `0x140007af5`: `shellcommon\shell\cloudexperiencehost\onecore\exe\cloudexperiencehostbroker.cpp`
- `0x140007b35`: `shellcommon\shell\cloudexperiencehost\onecore\exe\cloudexperiencehostbroker.cpp`

## pseudocode

```c
__int64 __fastcall CreateSystemObjectTask::CreateInstance(
        CreateSystemObjectTask *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  int v6; // ebx
  __int64 v7; // rdx
  _QWORD *v9; // rbx
  int SystemObject; // eax
  unsigned int v11; // edi
  int v12; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *a4 = 0;
  if ( a2 )
  {
    v6 = -2147221232;
    v7 = 58;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"shellcommon\\shell\\cloudexperiencehost\\onecore\\exe\\cloudexperiencehostbroker.cpp",
      (const char *)(unsigned int)v6,
      v12);
    return (unsigned int)v6;
  }
  v9 = (_QWORD *)((char *)this + 72);
  if ( *((_QWORD *)this + 9)
    || (Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 72),
        SystemObject = Microsoft::WRL::Details::MakeAndInitialize<CreateSystemObjectServer,ICreateObject,>(v9),
        v11 = SystemObject,
        SystemObject >= 0) )
  {
    v6 = (**(__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **))*v9)(*v9, a3, a4);
    if ( v6 < 0 )
    {
      v7 = 64;
      goto LABEL_3;
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3E,
      (unsigned int)"shellcommon\\shell\\cloudexperiencehost\\onecore\\exe\\cloudexperiencehostbroker.cpp",
      (const char *)(unsigned int)SystemObject,
      v12);
    return v11;
  }
}

```

## disassembly

```asm
0x140007ad0  push    rbx
0x140007ad2  push    rbp
0x140007ad3  push    rsi
0x140007ad4  push    rdi
0x140007ad5  sub     rsp, 28h
0x140007ad9  mov     rsi, r9
0x140007adc  mov     rbp, r8
0x140007adf  mov     qword ptr [r9], 0
0x140007ae6  test    rdx, rdx
0x140007ae9  jz      short loc_140007B0D
0x140007aeb  mov     ebx, 80040110h
0x140007af0  mov     edx, 3Ah ; ':'; void *
0x140007af5  lea     r8, aShellcommonShe; "shellcommon\\shell\\cloudexperiencehost"...
0x140007afc  mov     r9d, ebx; char *
0x140007aff  mov     rcx, [rsp+48h]; this
0x140007b04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140007b09  mov     eax, ebx
0x140007b0b  jmp     short loc_140007B6D
0x140007b0d  lea     rbx, [rcx+48h]
0x140007b11  cmp     qword ptr [rbx], 0
0x140007b15  jnz     short loc_140007B4A
0x140007b17  mov     rcx, rbx
0x140007b1a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140007b1f  mov     rcx, rbx
0x140007b22  call    ??$MakeAndInitialize@VCreateSystemObjectServer@@UICreateObject@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUICreateObject@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CreateSystemObjectServer,ICreateObject,>(ICreateObject * *)
0x140007b27  mov     edi, eax
0x140007b29  test    eax, eax
0x140007b2b  jns     short loc_140007B4A
0x140007b2d  mov     rcx, [rsp+48h]; this
0x140007b32  mov     r9d, eax; char *
0x140007b35  lea     r8, aShellcommonShe; "shellcommon\\shell\\cloudexperiencehost"...
0x140007b3c  mov     edx, 3Eh ; '>'; void *
0x140007b41  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140007b46  mov     eax, edi
0x140007b48  jmp     short loc_140007B6D
0x140007b4a  mov     rcx, [rbx]
0x140007b4d  mov     rax, [rcx]
0x140007b50  mov     r8, rsi
0x140007b53  mov     rdx, rbp
0x140007b56  mov     rax, [rax]
0x140007b59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007b5e  mov     ebx, eax
0x140007b60  test    eax, eax
0x140007b62  jns     short loc_140007B6B
0x140007b64  mov     edx, 40h ; '@'
0x140007b69  jmp     short loc_140007AF5
0x140007b6b  xor     eax, eax
0x140007b6d  add     rsp, 28h
0x140007b71  pop     rdi
0x140007b72  pop     rsi
0x140007b73  pop     rbp
0x140007b74  pop     rbx
0x140007b75  retn
```
