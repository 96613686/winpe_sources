# CFileIoChannel::DequeuePendingIrp(WDFREQUEST__ * *,void * *,unsigned __int64 *)

- ea: `0x180033498`
- end: `0x1800335ab`
- name: `?DequeuePendingIrp@CFileIoChannel@@QEAA_NPEAPEAUWDFREQUEST__@@PEAPEAXPEA_K@Z`
- size: `275`
- prototype: `bool __fastcall(CFileIoChannel *__hidden this, struct WDFREQUEST__ **, void **, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180032398`
- `0x180033b70`

## callees

- `0x1800106b8`
- `0x180011584`
- `0x180033498`
- `0x18003f010`

## string_xrefs

- `0x1800334f8`: `Failed to retrieve pending Read Irp`
- `0x18003358a`: `Failed to retrieve Read Irp buffer`

## pseudocode

```c
char __fastcall CFileIoChannel::DequeuePendingIrp(
        CFileIoChannel *this,
        struct WDFREQUEST__ **a2,
        void **a3,
        unsigned __int64 *a4)
{
  __int64 v5; // rdx
  unsigned int v8; // eax
  int v10; // eax
  unsigned int v11; // edi
  const char *v12; // [rsp+28h] [rbp-10h]
  const char *v13; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  struct WDFREQUEST__ *v15; // [rsp+40h] [rbp+8h] BYREF

  v15 = 0;
  v5 = *((_QWORD *)this + 25);
  v8 = -1073741823;
  if ( v5 )
  {
    v8 = (*(__int64 (__fastcall **)(__int64, __int64, struct WDFREQUEST__ **))(WdfFunctions_02025 + 728))(
           WdfDriverGlobals,
           v5,
           &v15);
    if ( v8 == -2147483622 )
      return 0;
  }
  wil::details::in1diag3::Throw_IfNtStatusFailedMsg(
    retaddr,
    (void *)0x481,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\fileio.cpp",
    (const char *)v8,
    (int)"Failed to retrieve pending Read Irp",
    v12);
  v10 = (*(__int64 (__fastcall **)(__int64, struct WDFREQUEST__ *, _QWORD, void **, unsigned __int64 *))(WdfFunctions_02025 + 1352))(
          WdfDriverGlobals,
          v15,
          0,
          a3,
          a4);
  v11 = v10;
  if ( v10 < 0 )
  {
    (*(void (__fastcall **)(__int64, struct WDFREQUEST__ *, _QWORD))(WdfFunctions_02025 + 1304))(
      WdfDriverGlobals,
      v15,
      (unsigned int)v10);
    wil::details::in1diag3::Throw_NtStatusMsg(
      retaddr,
      (void *)0x494,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\fileio.cpp",
      (const char *)v11,
      (int)"Failed to retrieve Read Irp buffer",
      v13);
  }
  *a2 = v15;
  return 1;
}

```

## disassembly

```asm
0x180033498  mov     r11, rsp
0x18003349b  mov     [r11+10h], rbx
0x18003349f  mov     [r11+18h], rsi
0x1800334a3  push    rdi
0x1800334a4  sub     rsp, 30h
0x1800334a8  mov     rbx, rdx
0x1800334ab  mov     qword ptr [r11+8], 0
0x1800334b3  mov     rdx, [rcx+0C8h]
0x1800334ba  mov     rdi, r9
0x1800334bd  mov     rsi, r8
0x1800334c0  mov     eax, 0C0000001h
0x1800334c5  test    rdx, rdx
0x1800334c8  jz      short loc_1800334F3
0x1800334ca  mov     rax, cs:WdfFunctions_02025
0x1800334d1  lea     r8, [r11+8]
0x1800334d5  mov     rcx, cs:WdfDriverGlobals
0x1800334dc  mov     rax, [rax+2D8h]
0x1800334e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800334e8  cmp     eax, 8000001Ah
0x1800334ed  jnz     short loc_1800334F3
0x1800334ef  xor     al, al
0x1800334f1  jmp     short loc_180033552
0x1800334f3  mov     rcx, [rsp+38h]; this
0x1800334f8  lea     rdx, aFailedToRetrie; "Failed to retrieve pending Read Irp"
0x1800334ff  mov     qword ptr [rsp+38h+var_18], rdx; int
0x180033504  lea     r8, aOnecoreuapTerm_11; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18003350b  mov     edx, 481h; void *
0x180033510  mov     r9d, eax; char *
0x180033513  call    ?Throw_IfNtStatusFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfNtStatusFailedMsg(void *,uint,char const *,long,char const *,...)
0x180033518  mov     rax, cs:WdfFunctions_02025
0x18003351f  mov     r9, rsi
0x180033522  mov     rdx, [rsp+38h+arg_0]
0x180033527  xor     r8d, r8d
0x18003352a  mov     rcx, cs:WdfDriverGlobals
0x180033531  mov     qword ptr [rsp+38h+var_18], rdi
0x180033536  mov     rax, [rax+548h]
0x18003353d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033542  mov     edi, eax
0x180033544  test    eax, eax
0x180033546  js      short loc_180033563
0x180033548  mov     rax, [rsp+38h+arg_0]
0x18003354d  mov     [rbx], rax
0x180033550  mov     al, 1
0x180033552  mov     rbx, [rsp+38h+arg_8]
0x180033557  mov     rsi, [rsp+38h+arg_10]
0x18003355c  add     rsp, 30h
0x180033560  pop     rdi
0x180033561  retn
0x180033563  mov     rcx, cs:WdfFunctions_02025
0x18003356a  mov     r8d, edi
0x18003356d  mov     rdx, [rsp+38h+arg_0]
0x180033572  mov     rax, [rcx+518h]
0x180033579  mov     rcx, cs:WdfDriverGlobals
0x180033580  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033585  mov     rcx, [rsp+38h]; this
0x18003358a  lea     rax, aFailedToRetrie_2; "Failed to retrieve Read Irp buffer"
0x180033591  mov     r9d, edi; char *
0x180033594  mov     qword ptr [rsp+38h+var_18], rax; int
0x180033599  lea     r8, aOnecoreuapTerm_11; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x1800335a0  mov     edx, 494h; void *
0x1800335a5  call    ?Throw_NtStatusMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_NtStatusMsg(void *,uint,char const *,long,char const *,...)
```
