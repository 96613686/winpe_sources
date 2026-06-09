# CSyncChangeWrapper::ReplaceForChangeIdOperation(ISyncKnowledge *,ILoggedConflict *,int,IAsynchronousNotifyingChangeApplierTarget *,unsigned __int64 *)

- ea: `0x18006c980`
- end: `0x18006caa4`
- name: `?ReplaceForChangeIdOperation@CSyncChangeWrapper@@QEAAJPEAUISyncKnowledge@@PEAUILoggedConflict@@HPEAUIAsynchronousNotifyingChangeApplierTarget@@PEA_K@Z`
- size: `292`
- prototype: `__int64 __usercall@<rax>(CSyncChangeWrapper *__hidden this@<rcx>, struct ISyncKnowledge *@<rdx>, struct ILoggedConflict *@<r8>, int@<r9d>, struct IAsynchronousNotifyingChangeApplierTarget *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180041bb4`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x18006c980`
- `0x18006e66c`
- `0x180094010`

## string_xrefs

- `0x18006c9bf`: `CSyncChangeWrapper::ReplaceForChangeIdOperation`
- `0x18006ca76`: `CSyncChangeWrapper::ReplaceForChangeIdOperation`

## pseudocode

```c
__int64 __fastcall CSyncChangeWrapper::ReplaceForChangeIdOperation(
        CSyncChangeWrapper *this,
        struct ISyncKnowledge *a2,
        struct ILoggedConflict *a3,
        int a4,
        struct IAsynchronousNotifyingChangeApplierTarget *a5,
        unsigned __int64 *a6)
{
  PVOID *v10; // rcx
  int v11; // ebx
  __int64 v12; // rcx

  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      109,
      WPP_1ce7e5fbf03e39cbecdc9dc9cb74efd7_Traceguids,
      "CSyncChangeWrapper::ReplaceForChangeIdOperation");
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  v11 = -2147467261;
  if ( a2 && a3 && (a5 && a6 || !a4) )
  {
    v12 = *((_QWORD *)this + 52);
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    v11 = ((__int64 (__fastcall *)(struct ISyncKnowledge *, char *))a2->lpVtbl->Clone)(a2, (char *)this + 416);
    if ( v11 >= 0 )
      v11 = CSyncChangeWrapper::SetWinnerChange(this, a3, a4, a5, a6);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 8) != 0 && *((_BYTE *)v10 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v10[2],
      110,
      (unsigned int)WPP_1ce7e5fbf03e39cbecdc9dc9cb74efd7_Traceguids,
      (unsigned int)"CSyncChangeWrapper::ReplaceForChangeIdOperation",
      v11);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18006c980  push    rbx
0x18006c982  push    rbp
0x18006c983  push    rdi
0x18006c984  push    r12
0x18006c986  push    r13
0x18006c988  push    r14
0x18006c98a  push    r15
0x18006c98c  sub     rsp, 30h
0x18006c990  mov     r15d, r9d
0x18006c993  mov     rbp, r8
0x18006c996  mov     r14, rdx
0x18006c999  mov     r13, rcx
0x18006c99c  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c9a3  lea     r12, WPP_GLOBAL_Control
0x18006c9aa  cmp     rcx, r12
0x18006c9ad  jz      short loc_18006C9DE
0x18006c9af  test    byte ptr [rcx+1Ch], 8
0x18006c9b3  jz      short loc_18006C9DE
0x18006c9b5  cmp     byte ptr [rcx+19h], 5
0x18006c9b9  jb      short loc_18006C9DE
0x18006c9bb  mov     rcx, [rcx+10h]
0x18006c9bf  lea     r9, aCsyncchangewra_53; "CSyncChangeWrapper::ReplaceForChangeIdO"...
0x18006c9c6  mov     edx, 6Dh ; 'm'
0x18006c9cb  lea     r8, WPP_1ce7e5fbf03e39cbecdc9dc9cb74efd7_Traceguids
0x18006c9d2  call    WPP_SF_s
0x18006c9d7  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c9de  mov     ebx, 80004003h
0x18006c9e3  test    r14, r14
0x18006c9e6  jz      short loc_18006CA61
0x18006c9e8  test    rbp, rbp
0x18006c9eb  jz      short loc_18006CA61
0x18006c9ed  cmp     [rsp+68h+arg_20], 0
0x18006c9f6  mov     rdi, [rsp+68h+arg_28]
0x18006c9fe  jz      short loc_18006CA05
0x18006ca00  test    rdi, rdi
0x18006ca03  jnz     short loc_18006CA0A
0x18006ca05  test    r15d, r15d
0x18006ca08  jnz     short loc_18006CA61
0x18006ca0a  lea     rbx, [r13+1A0h]
0x18006ca11  mov     rcx, [rbx]
0x18006ca14  test    rcx, rcx
0x18006ca17  jz      short loc_18006CA25
0x18006ca19  mov     rax, [rcx]
0x18006ca1c  mov     rax, [rax+10h]
0x18006ca20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ca25  mov     rax, [r14]
0x18006ca28  mov     rdx, rbx
0x18006ca2b  mov     rcx, r14
0x18006ca2e  mov     rax, [rax+50h]
0x18006ca32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ca37  mov     ebx, eax
0x18006ca39  test    eax, eax
0x18006ca3b  js      short loc_18006CA5A
0x18006ca3d  mov     r9, [rsp+68h+arg_20]; struct IAsynchronousNotifyingChangeApplierTarget *
0x18006ca45  mov     r8d, r15d; int
0x18006ca48  mov     rdx, rbp; struct ILoggedConflict *
0x18006ca4b  mov     [rsp+68h+var_48], rdi; unsigned __int64 *
0x18006ca50  mov     rcx, r13; this
0x18006ca53  call    ?SetWinnerChange@CSyncChangeWrapper@@AEAAJPEAUILoggedConflict@@HPEAUIAsynchronousNotifyingChangeApplierTarget@@PEA_K@Z; CSyncChangeWrapper::SetWinnerChange(ILoggedConflict *,int,IAsynchronousNotifyingChangeApplierTarget *,unsigned __int64 *)
0x18006ca58  mov     ebx, eax
0x18006ca5a  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ca61  cmp     rcx, r12
0x18006ca64  jz      short loc_18006CA92
0x18006ca66  test    byte ptr [rcx+1Ch], 8
0x18006ca6a  jz      short loc_18006CA92
0x18006ca6c  cmp     byte ptr [rcx+19h], 5
0x18006ca70  jb      short loc_18006CA92
0x18006ca72  mov     rcx, [rcx+10h]
0x18006ca76  lea     r9, aCsyncchangewra_53; "CSyncChangeWrapper::ReplaceForChangeIdO"...
0x18006ca7d  mov     edx, 6Eh ; 'n'
0x18006ca82  mov     dword ptr [rsp+68h+var_48], ebx
0x18006ca86  lea     r8, WPP_1ce7e5fbf03e39cbecdc9dc9cb74efd7_Traceguids
0x18006ca8d  call    WPP_SF_sD
0x18006ca92  mov     eax, ebx
0x18006ca94  add     rsp, 30h
0x18006ca98  pop     r15
0x18006ca9a  pop     r14
0x18006ca9c  pop     r13
0x18006ca9e  pop     r12
0x18006caa0  pop     rdi
0x18006caa1  pop     rbp
0x18006caa2  pop     rbx
0x18006caa3  retn
```
