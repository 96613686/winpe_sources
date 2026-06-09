# CloudPrint::ImpersonateClientRAII::~ImpersonateClientRAII(void)

- ea: `0x180012a44`
- end: `0x180012a85`
- name: `??1ImpersonateClientRAII@CloudPrint@@QEAA@XZ`
- size: `65`
- prototype: `void __fastcall(CloudPrint::ImpersonateClientRAII *__hidden this)`
- caller_count: `12`
- callee_count: `3`
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
- `0x1800280ca`
- `0x180028286`
- `0x18002859f`
- `0x180028cdc`

## callees

- `0x180012a44`
- `0x180019c08`
- `0x18002b010`

## pseudocode

```c
void __fastcall CloudPrint::ImpersonateClientRAII::~ImpersonateClientRAII(CloudPrint::ImpersonateClientRAII *this)
{
  __int64 (__fastcall *v1)(_QWORD); // rax
  unsigned int v2; // eax
  const char *v3; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v1 = (__int64 (__fastcall *)(_QWORD))*((_QWORD *)this + 1);
  if ( v1 )
  {
    v2 = v1(*((_QWORD *)this + 2));
    wil::details::in1diag3::Log_IfFailedMsg(
      retaddr,
      (void *)0x28,
      (unsigned int)"onecoreuap\\printscan\\Print\\Shared\\CloudPrintHelper\\inc\\CloudPrintHelperRAII.h",
      (const char *)v2,
      (int)"Failed to revert to self",
      v3);
  }
}

```

## disassembly

```asm
0x180012a44  sub     rsp, 38h
0x180012a48  mov     rax, [rcx+8]
0x180012a4c  test    rax, rax
0x180012a4f  jz      short loc_180012A80
0x180012a51  mov     rcx, [rcx+10h]
0x180012a55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a5a  mov     rcx, [rsp+38h]; this
0x180012a5f  lea     rdx, aFailedToRevert; "Failed to revert to self"
0x180012a66  mov     qword ptr [rsp+38h+var_18], rdx; int
0x180012a6b  mov     r9d, eax; char *
0x180012a6e  lea     r8, aOnecoreuapPrin_4; "onecoreuap\\printscan\\Print\\Shared\\C"...
0x180012a75  mov     edx, 28h ; '('; void *
0x180012a7a  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180012a7f  nop
0x180012a80  add     rsp, 38h
0x180012a84  retn
```
