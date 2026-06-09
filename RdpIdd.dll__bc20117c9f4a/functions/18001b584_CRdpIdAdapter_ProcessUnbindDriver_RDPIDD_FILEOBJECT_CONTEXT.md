# CRdpIdAdapter::ProcessUnbindDriver(RDPIDD_FILEOBJECT_CONTEXT *)

- ea: `0x18001b584`
- end: `0x18001b63c`
- name: `?ProcessUnbindDriver@CRdpIdAdapter@@AEAAXPEAURDPIDD_FILEOBJECT_CONTEXT@@@Z`
- size: `184`
- prototype: `void __fastcall(CRdpIdAdapter *__hidden this, struct RDPIDD_FILEOBJECT_CONTEXT *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800185bc`

## callees

- `0x18001b584`
- `0x18001b644`
- `0x18001dd70`

## string_xrefs

- `0x18001b5a7`: `Driver has already been unbinded`

## pseudocode

```c
void __fastcall CRdpIdAdapter::ProcessUnbindDriver(CRdpIdAdapter *this, struct RDPIDD_FILEOBJECT_CONTEXT *a2)
{
  bool v4; // zf
  const char *v5; // [rsp+30h] [rbp-8h]
  const char *v6; // [rsp+30h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0xB9A,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
    (const char *)0x80070057LL,
    *((_BYTE *)this + 448) == 0,
    (bool)"Driver has already been unbinded",
    v5);
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0xB9F,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
    (const char *)0x80070005LL,
    *((_DWORD *)this + 135) != *((_DWORD *)a2 + 10),
    (bool)"Driver was binded by different process",
    v6);
  v4 = *((_QWORD *)this + 52) == 0;
  *((_QWORD *)this + 55) = 0;
  *((_DWORD *)this + 135) = 0;
  *((_BYTE *)this + 448) = 0;
  if ( !v4 )
    CRdpIdAdapter::ProcessUnloadAvenc(this);
}

```

## disassembly

```asm
0x18001b584  mov     [rsp+arg_0], rbx
0x18001b589  push    rdi; char *
0x18001b58a  sub     rsp, 30h
0x18001b58e  cmp     byte ptr [rcx+1C0h], 0
0x18001b595  lea     r8, aOnecoreuapTerm_15; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18001b59c  mov     rbx, rdx
0x18001b59f  mov     rdi, rcx
0x18001b5a2  mov     rcx, [rsp+38h]; this
0x18001b5a7  lea     rdx, aDriverHasAlrea; "Driver has already been unbinded"
0x18001b5ae  mov     qword ptr [rsp+38h+var_10], rdx; bool
0x18001b5b3  setz    al
0x18001b5b6  mov     edx, 0B9Ah; void *
0x18001b5bb  mov     [rsp+38h+var_18], al; char
0x18001b5bf  mov     r9d, 80070057h; char *
0x18001b5c5  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18001b5ca  mov     eax, [rbx+28h]
0x18001b5cd  lea     rdx, aDriverWasBinde; "Driver was binded by different process"
0x18001b5d4  cmp     [rdi+21Ch], eax
0x18001b5da  lea     r8, aOnecoreuapTerm_15; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18001b5e1  mov     rcx, [rsp+38h]; this
0x18001b5e6  mov     r9d, 80070005h; char *
0x18001b5ec  mov     qword ptr [rsp+38h+var_10], rdx; bool
0x18001b5f1  setnz   al
0x18001b5f4  mov     edx, 0B9Fh; void *
0x18001b5f9  mov     [rsp+38h+var_18], al; char
0x18001b5fd  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18001b602  cmp     qword ptr [rdi+1A0h], 0
0x18001b60a  mov     qword ptr [rdi+1B8h], 0
0x18001b615  mov     dword ptr [rdi+21Ch], 0
0x18001b61f  mov     byte ptr [rdi+1C0h], 0
0x18001b626  jz      short loc_18001B630
0x18001b628  mov     rcx, rdi; this
0x18001b62b  call    ?ProcessUnloadAvenc@CRdpIdAdapter@@AEAAXXZ; CRdpIdAdapter::ProcessUnloadAvenc(void)
0x18001b630  mov     rbx, [rsp+38h+arg_0]
0x18001b635  add     rsp, 30h
0x18001b639  pop     rdi
0x18001b63a  retn
```
