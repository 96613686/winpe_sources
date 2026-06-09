# CredUXParameters::get_IsOnSecureDesktop(uchar *)

- ea: `0x14001a3a0`
- end: `0x14001a3fb`
- name: `?get_IsOnSecureDesktop@CredUXParameters@@UEAAJPEAE@Z`
- size: `91`
- prototype: `__int64 __fastcall(CredUXParameters *this, bool *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400136fc`
- `0x14001a3a0`
- `0x14001f010`

## string_xrefs

- `0x14001a3db`: `shellcommon\internal\shell\inc\creduxparameters.h`

## pseudocode

```c
__int64 __fastcall CredUXParameters::get_IsOnSecureDesktop(CredUXParameters *this, bool *a2)
{
  int v2; // r8d
  __int64 v3; // rcx
  int v4; // eax
  unsigned int v5; // ebx
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = *((_DWORD *)this + 18) & 2;
  *a2 = v2 != 0;
  v3 = *((_QWORD *)this + 24);
  if ( !v3 )
    return 0;
  if ( v2 )
    return 0;
  v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 64LL))(v3);
  v5 = v4;
  if ( v4 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x118,
    (unsigned int)"shellcommon\\internal\\shell\\inc\\creduxparameters.h",
    (const char *)(unsigned int)v4,
    v7);
  return v5;
}

```

## disassembly

```asm
0x14001a3a0  push    rbx; int
0x14001a3a2  sub     rsp, 20h
0x14001a3a6  mov     r8d, [rcx+48h]
0x14001a3aa  and     r8d, 2
0x14001a3ae  setnz   al
0x14001a3b1  mov     [rdx], al
0x14001a3b3  mov     rcx, [rcx+0C0h]
0x14001a3ba  test    rcx, rcx
0x14001a3bd  jz      short loc_14001A3F3
0x14001a3bf  test    r8d, r8d
0x14001a3c2  jnz     short loc_14001A3F3
0x14001a3c4  mov     rax, [rcx]
0x14001a3c7  mov     rax, [rax+40h]
0x14001a3cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a3d0  mov     ebx, eax
0x14001a3d2  test    eax, eax
0x14001a3d4  jns     short loc_14001A3F3
0x14001a3d6  mov     rcx, [rsp+28h]; this
0x14001a3db  lea     r8, aShellcommonInt_0; "shellcommon\\internal\\shell\\inc\\cred"...
0x14001a3e2  mov     r9d, eax; char *
0x14001a3e5  mov     edx, 118h; void *
0x14001a3ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001a3ef  mov     eax, ebx
0x14001a3f1  jmp     short loc_14001A3F5
0x14001a3f3  xor     eax, eax
0x14001a3f5  add     rsp, 20h
0x14001a3f9  pop     rbx
0x14001a3fa  retn
```
