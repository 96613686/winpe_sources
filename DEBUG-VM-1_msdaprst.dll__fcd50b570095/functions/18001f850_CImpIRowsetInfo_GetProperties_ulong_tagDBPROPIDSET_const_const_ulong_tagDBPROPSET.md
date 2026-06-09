# CImpIRowsetInfo::GetProperties(ulong,tagDBPROPIDSET const * const,ulong *,tagDBPROPSET * *)

- ea: `0x18001f850`
- end: `0x18001f94c`
- name: `?GetProperties@CImpIRowsetInfo@@UEAAJKQEBUtagDBPROPIDSET@@PEAKPEAPEAUtagDBPROPSET@@@Z`
- size: `252`
- prototype: `int(CImpIRowsetInfo *__hidden this, unsigned int, const struct tagDBPROPIDSET *const, unsigned int *, struct tagDBPROPSET **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180015fb4`
- `0x18001f850`
- `0x18002c3dc`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18001f897`
- `KERNEL32!GetCurrentThreadId` at `0x18001f897`
- `KERNEL32!LeaveCriticalSection` at `0x18001f929`
- `KERNEL32!LeaveCriticalSection` at `0x18001f929`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18001f8b6`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18001f8b6`
- `MSDART!UMSEnterCSWraper` at `0x18001f883`
- `MSDART!UMSEnterCSWraper` at `0x18001f883`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CImpIRowsetInfo::GetProperties(
        CImpIRowsetInfo *this,
        unsigned int a2,
        const struct tagDBPROPIDSET *const a3,
        unsigned int *a4,
        struct tagDBPROPSET **a5)
{
  __int64 v9; // rbx
  _DWORD *v10; // rdi
  _DWORD *v11; // rsi
  int Properties; // eax
  unsigned int v13; // r14d
  __int64 v15; // rcx
  int v17; // [rsp+30h] [rbp-58h] BYREF
  __int64 v18; // [rsp+38h] [rbp-50h]
  _DWORD *v19; // [rsp+40h] [rbp-48h]
  _DWORD *v20; // [rsp+48h] [rbp-40h]
  __int64 v21; // [rsp+50h] [rbp-38h]

  v9 = *((_QWORD *)this + 3) + 128LL;
  v18 = v9;
  UMSEnterCSWraper(v9);
  v10 = (_DWORD *)(v9 + 12);
  v19 = (_DWORD *)(v9 + 12);
  if ( !*(_DWORD *)(v9 + 12) )
    *(_DWORD *)(v9 + 8) = GetCurrentThreadId();
  ++*v10;
  v11 = (_DWORD *)(v9 + 16);
  v20 = (_DWORD *)(v9 + 16);
  ++*(_DWORD *)(v9 + 16);
  v21 = v9;
  SetErrorInfo(0, 0);
  try
  {
    Properties = CUtlProps::utlGetProperties(
                   (CUtlProps *)(*((_QWORD *)this + 3) + 400LL),
                   a2,
                   a3,
                   a4,
                   a5,
                   (const struct CBidGenericBase *)(*((_QWORD *)this + 3) + 112LL));
  }
  catch ( long v17 )
  {
    Properties = v17;
    v9 = v18;
    v10 = v19;
    v11 = v20;
  }
  v13 = Exit(Properties, 0xBB9u);
  --*v11;
  if ( (*v10)-- == 1 )
    *(_DWORD *)(v9 + 8) = -1;
  v15 = *(_QWORD *)v9;
  --*(_DWORD *)(v15 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v15 + 8));
  return v13;
}

```

## disassembly

```asm
0x18001f850  mov     [rsp+arg_8], rbx
0x18001f855  mov     [rsp+arg_10], rsi
0x18001f85a  push    rdi
0x18001f85b  push    r12
0x18001f85d  push    r13
0x18001f85f  push    r14
0x18001f861  push    r15
0x18001f863  sub     rsp, 60h
0x18001f867  mov     r15, r9
0x18001f86a  mov     r12, r8
0x18001f86d  mov     r13d, edx
0x18001f870  mov     r14, rcx
0x18001f873  mov     rbx, [rcx+18h]
0x18001f877  sub     rbx, 0FFFFFFFFFFFFFF80h
0x18001f87b  mov     [rsp+88h+var_50], rbx
0x18001f880  mov     rcx, rbx
0x18001f883  call    cs:__imp_UMSEnterCSWraper
0x18001f889  lea     rdi, [rbx+0Ch]
0x18001f88d  mov     [rsp+88h+var_48], rdi
0x18001f892  cmp     dword ptr [rdi], 0
0x18001f895  jnz     short loc_18001F8A0
0x18001f897  call    cs:__imp_GetCurrentThreadId
0x18001f89d  mov     [rbx+8], eax
0x18001f8a0  inc     dword ptr [rdi]
0x18001f8a2  lea     rsi, [rbx+10h]
0x18001f8a6  mov     [rsp+88h+var_40], rsi
0x18001f8ab  inc     dword ptr [rsi]
0x18001f8ad  mov     [rsp+88h+var_38], rbx
0x18001f8b2  xor     edx, edx; perrinfo
0x18001f8b4  xor     ecx, ecx; dwReserved
0x18001f8b6  call    cs:__imp_SetErrorInfo
0x18001f8bc  mov     rcx, [r14+18h]
0x18001f8c0  lea     rax, [rcx+70h]
0x18001f8c4  add     rcx, 190h; this
0x18001f8cb  mov     [rsp+88h+var_60], rax; struct CBidGenericBase *
0x18001f8d0  mov     rax, [rsp+88h+arg_20]
0x18001f8d8  mov     [rsp+88h+var_68], rax; struct tagDBPROPSET **
0x18001f8dd  mov     r9, r15; unsigned int *
0x18001f8e0  mov     r8, r12; struct tagDBPROPIDSET *
0x18001f8e3  mov     edx, r13d; unsigned int
0x18001f8e6  call    ?utlGetProperties@CUtlProps@@QEAAJKQEBUtagDBPROPIDSET@@PEAKPEAPEAUtagDBPROPSET@@AEBVCBidGenericBase@@@Z; CUtlProps::utlGetProperties(ulong,tagDBPROPIDSET const * const,ulong *,tagDBPROPSET * *,CBidGenericBase const &)
0x18001f8eb  nop
0x18001f8ec  jmp     short loc_18001F904
0x18001f8ee  mov     eax, [rsp+88h+arg_0]
0x18001f8f5  mov     rbx, [rsp+88h+var_50]
0x18001f8fa  mov     rdi, [rsp+88h+var_48]
0x18001f8ff  mov     rsi, [rsp+88h+var_40]
0x18001f904  mov     edx, 0BB9h; unsigned int
0x18001f909  mov     ecx, eax; int
0x18001f90b  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x18001f910  mov     r14d, eax
0x18001f913  or      eax, 0FFFFFFFFh
0x18001f916  add     [rsi], eax
0x18001f918  add     [rdi], eax
0x18001f91a  jnz     short loc_18001F91F
0x18001f91c  mov     [rbx+8], eax
0x18001f91f  mov     rcx, [rbx]
0x18001f922  dec     dword ptr [rcx+30h]
0x18001f925  add     rcx, 8; lpCriticalSection
0x18001f929  call    cs:__imp_LeaveCriticalSection
0x18001f92f  mov     eax, r14d
0x18001f932  lea     r11, [rsp+88h+var_28]
0x18001f937  mov     rbx, [r11+38h]
0x18001f93b  mov     rsi, [r11+40h]
0x18001f93f  mov     rsp, r11
0x18001f942  pop     r15
0x18001f944  pop     r14
0x18001f946  pop     r13
0x18001f948  pop     r12
0x18001f94a  pop     rdi
0x18001f94b  retn
```
