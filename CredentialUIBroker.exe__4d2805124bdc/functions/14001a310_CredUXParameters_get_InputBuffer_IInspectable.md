# CredUXParameters::get_InputBuffer(IInspectable * *)

- ea: `0x14001a310`
- end: `0x14001a369`
- name: `?get_InputBuffer@CredUXParameters@@UEAAJPEAPEAUIInspectable@@@Z`
- size: `89`
- prototype: `__int64 __fastcall(CredUXParameters *this, struct IInspectable **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400136fc`
- `0x14001a310`
- `0x14001f010`

## string_xrefs

- `0x14001a349`: `shellcommon\internal\shell\inc\creduxparameters.h`

## pseudocode

```c
__int64 __fastcall CredUXParameters::get_InputBuffer(CredUXParameters *this, struct IInspectable **a2)
{
  __int64 (__fastcall ***v2)(_QWORD, GUID *, struct IInspectable **); // rcx
  int v3; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *a2 = 0;
  v2 = (__int64 (__fastcall ***)(_QWORD, GUID *, struct IInspectable **))*((_QWORD *)this + 18);
  if ( !v2 )
    return 0;
  v3 = (**v2)(v2, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, a2);
  v4 = v3;
  if ( v3 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xE3,
    (unsigned int)"shellcommon\\internal\\shell\\inc\\creduxparameters.h",
    (const char *)(unsigned int)v3,
    v6);
  return v4;
}

```

## disassembly

```asm
0x14001a310  push    rbx; int
0x14001a312  sub     rsp, 20h
0x14001a316  mov     qword ptr [rdx], 0
0x14001a31d  mov     rcx, [rcx+90h]
0x14001a324  test    rcx, rcx
0x14001a327  jz      short loc_14001A361
0x14001a329  mov     rax, [rcx]
0x14001a32c  mov     r8, rdx
0x14001a32f  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x14001a336  mov     rax, [rax]
0x14001a339  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a33e  mov     ebx, eax
0x14001a340  test    eax, eax
0x14001a342  jns     short loc_14001A361
0x14001a344  mov     rcx, [rsp+28h]; this
0x14001a349  lea     r8, aShellcommonInt_0; "shellcommon\\internal\\shell\\inc\\cred"...
0x14001a350  mov     r9d, eax; char *
0x14001a353  mov     edx, 0E3h; void *
0x14001a358  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001a35d  mov     eax, ebx
0x14001a35f  jmp     short loc_14001A363
0x14001a361  xor     eax, eax
0x14001a363  add     rsp, 20h
0x14001a367  pop     rbx
0x14001a368  retn
```
