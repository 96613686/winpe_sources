# CImpIRowsetInfo::GetReferencedRowset(unsigned __int64,_GUID const &,IUnknown * *)

- ea: `0x18001f960`
- end: `0x18001fa24`
- name: `?GetReferencedRowset@CImpIRowsetInfo@@UEAAJ_KAEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `196`
- prototype: `__int64 __fastcall(CImpIRowsetInfo *__hidden this, unsigned __int64, const struct _GUID *, struct IUnknown **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180015fb4`
- `0x18001f960`
- `0x180030010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18001f994`
- `KERNEL32!GetCurrentThreadId` at `0x18001f994`
- `KERNEL32!LeaveCriticalSection` at `0x18001fa0f`
- `KERNEL32!LeaveCriticalSection` at `0x18001fa0f`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18001f9ab`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18001f9ab`
- `MSDART!UMSEnterCSWraper` at `0x18001f984`
- `MSDART!UMSEnterCSWraper` at `0x18001f984`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CImpIRowsetInfo::GetReferencedRowset(
        CImpIRowsetInfo *this,
        unsigned __int64 a2,
        const struct _GUID *a3,
        struct IUnknown **a4)
{
  __int64 v8; // rbx
  DWORD *v9; // rdi
  unsigned int *v10; // rcx
  int v11; // ecx
  unsigned int v12; // eax
  unsigned int v13; // esi
  __int64 v15; // rcx

  v8 = *((_QWORD *)this + 3) + 128LL;
  UMSEnterCSWraper(v8);
  v9 = (DWORD *)(v8 + 8);
  if ( !*(_DWORD *)(v8 + 12) )
    *v9 = GetCurrentThreadId();
  ++*(_DWORD *)(v8 + 12);
  ++*(_DWORD *)(v8 + 16);
  SetErrorInfo(0, 0);
  if ( a4 )
  {
    *a4 = 0;
    v10 = (unsigned int *)*((_QWORD *)this + 3);
    if ( a2 <= v10[38] )
    {
      v12 = (*(__int64 (__fastcall **)(unsigned int *, _QWORD, const struct _GUID *, struct IUnknown **))(*(_QWORD *)v10 + 40LL))(
              v10,
              (unsigned int)a2,
              a3,
              a4);
      goto LABEL_9;
    }
    v11 = -2147217835;
  }
  else
  {
    v11 = -2147024809;
  }
  v12 = Exit(v11, 0);
LABEL_9:
  v13 = v12;
  --*(_DWORD *)(v8 + 16);
  if ( (*(_DWORD *)(v8 + 12))-- == 1 )
    *v9 = -1;
  v15 = *(_QWORD *)v8;
  --*(_DWORD *)(v15 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v15 + 8));
  return v13;
}

```

## disassembly

```asm
0x18001f960  push    rbx
0x18001f962  push    rbp
0x18001f963  push    rsi
0x18001f964  push    rdi
0x18001f965  push    r14
0x18001f967  push    r15
0x18001f969  sub     rsp, 38h
0x18001f96d  mov     rsi, r9
0x18001f970  mov     r15, r8
0x18001f973  mov     r14, rdx
0x18001f976  mov     rbp, rcx
0x18001f979  mov     rbx, [rcx+18h]
0x18001f97d  sub     rbx, 0FFFFFFFFFFFFFF80h
0x18001f981  mov     rcx, rbx
0x18001f984  call    cs:__imp_UMSEnterCSWraper
0x18001f98a  lea     rdi, [rbx+8]
0x18001f98e  cmp     dword ptr [rbx+0Ch], 0
0x18001f992  jnz     short loc_18001F99C
0x18001f994  call    cs:__imp_GetCurrentThreadId
0x18001f99a  mov     [rdi], eax
0x18001f99c  inc     dword ptr [rbx+0Ch]
0x18001f99f  inc     dword ptr [rbx+10h]
0x18001f9a2  mov     [rsp+68h+arg_0], rbx
0x18001f9a7  xor     edx, edx; perrinfo
0x18001f9a9  xor     ecx, ecx; dwReserved
0x18001f9ab  call    cs:__imp_SetErrorInfo
0x18001f9b1  test    rsi, rsi
0x18001f9b4  jz      short loc_18001F9EA
0x18001f9b6  mov     qword ptr [rsi], 0
0x18001f9bd  mov     rcx, [rbp+18h]
0x18001f9c1  mov     eax, [rcx+98h]
0x18001f9c7  cmp     r14, rax
0x18001f9ca  jbe     short loc_18001F9D3
0x18001f9cc  mov     ecx, 80040E55h
0x18001f9d1  jmp     short loc_18001F9EF
0x18001f9d3  mov     rax, [rcx]
0x18001f9d6  mov     edx, r14d
0x18001f9d9  mov     r9, rsi
0x18001f9dc  mov     r8, r15
0x18001f9df  mov     rax, [rax+28h]
0x18001f9e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f9e8  jmp     short loc_18001F9F6
0x18001f9ea  mov     ecx, 80070057h; int
0x18001f9ef  xor     edx, edx; unsigned int
0x18001f9f1  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x18001f9f6  mov     esi, eax
0x18001f9f8  or      edx, 0FFFFFFFFh
0x18001f9fb  add     [rbx+10h], edx
0x18001f9fe  add     [rbx+0Ch], edx
0x18001fa01  jnz     short loc_18001FA05
0x18001fa03  mov     [rdi], edx
0x18001fa05  mov     rcx, [rbx]
0x18001fa08  dec     dword ptr [rcx+30h]
0x18001fa0b  add     rcx, 8; lpCriticalSection
0x18001fa0f  call    cs:__imp_LeaveCriticalSection
0x18001fa15  mov     eax, esi
0x18001fa17  add     rsp, 38h
0x18001fa1b  pop     r15
0x18001fa1d  pop     r14
0x18001fa1f  pop     rdi
0x18001fa20  pop     rsi
0x18001fa21  pop     rbp
0x18001fa22  pop     rbx
0x18001fa23  retn
```
