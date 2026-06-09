# CloudPrint::ImpersonateClientRAII::ImpersonateClientRAII(long (*)(void *),long (*)(void *),void *)

- ea: `0x18001227c`
- end: `0x1800122e7`
- name: `??0ImpersonateClientRAII@CloudPrint@@QEAA@P6AJPEAX@Z10@Z`
- size: `107`
- prototype: `CloudPrint::ImpersonateClientRAII *__fastcall(CloudPrint::ImpersonateClientRAII *this, int (*)(void *), int (*)(void *), void *)`
- caller_count: `8`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180013948`
- `0x18001463c`
- `0x1800146b8`
- `0x1800157bc`
- `0x180016184`
- `0x18001892c`
- `0x180018f08`
- `0x18001b128`

## callees

- `0x18001227c`
- `0x18001ba2c`
- `0x18001dae4`
- `0x18002b010`

## pseudocode

```c
CloudPrint::ImpersonateClientRAII *__fastcall CloudPrint::ImpersonateClientRAII::ImpersonateClientRAII(
        CloudPrint::ImpersonateClientRAII *this,
        int (*a2)(void *),
        int (*a3)(void *),
        void *a4)
{
  int v5; // eax
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a2 )
  {
    if ( !a3 )
      goto LABEL_3;
  }
  else if ( a3 )
  {
LABEL_3:
    wil::details::in1diag3::Throw_Hr(retaddr, a2, (unsigned int)a3, (const char *)0x80070057LL, v7);
  }
  *(_QWORD *)this = a2;
  *((_QWORD *)this + 1) = a3;
  *((_QWORD *)this + 2) = a4;
  if ( a2 )
  {
    v5 = ((__int64 (__fastcall *)(void *))a2)(a4);
    if ( v5 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x20,
        (unsigned int)"onecoreuap\\printscan\\Print\\Shared\\CloudPrintHelper\\inc\\CloudPrintHelperRAII.h",
        (const char *)(unsigned int)v5,
        v7);
  }
  return this;
}

```

## disassembly

```asm
0x18001227c  push    rbx; int
0x18001227e  sub     rsp, 20h
0x180012282  mov     rbx, rcx
0x180012285  test    rdx, rdx
0x180012288  jz      short loc_1800122A0
0x18001228a  test    r8, r8
0x18001228d  jnz     short loc_1800122A5
0x18001228f  mov     rcx, [rsp+28h]; this
0x180012294  mov     r9d, 80070057h; char *
0x18001229a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800122a0  test    r8, r8
0x1800122a3  jnz     short loc_18001228F
0x1800122a5  mov     [rcx], rdx
0x1800122a8  mov     [rcx+8], r8
0x1800122ac  mov     [rcx+10h], r9
0x1800122b0  test    rdx, rdx
0x1800122b3  jz      short loc_1800122DE
0x1800122b5  mov     rcx, r9
0x1800122b8  mov     rax, rdx
0x1800122bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800122c0  test    eax, eax
0x1800122c2  jns     short loc_1800122DE
0x1800122c4  mov     rcx, [rsp+28h]; this
0x1800122c9  lea     r8, aOnecoreuapPrin_4; "onecoreuap\\printscan\\Print\\Shared\\C"...
0x1800122d0  mov     r9d, eax; char *
0x1800122d3  mov     edx, 20h ; ' '; void *
0x1800122d8  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800122de  mov     rax, rbx
0x1800122e1  add     rsp, 20h
0x1800122e5  pop     rbx
0x1800122e6  retn
```
