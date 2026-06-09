# CImpIRowsetInfo::GetSpecification(_GUID const &,IUnknown * *)

- ea: `0x18001fa30`
- end: `0x18001fae7`
- name: `?GetSpecification@CImpIRowsetInfo@@UEAAJAEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `183`
- prototype: `__int64 __fastcall(CImpIRowsetInfo *__hidden this, const struct _GUID *, struct IUnknown **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180015fb4`
- `0x18001fa30`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18001fa5d`
- `KERNEL32!GetCurrentThreadId` at `0x18001fa5d`
- `KERNEL32!LeaveCriticalSection` at `0x18001faa4`
- `KERNEL32!LeaveCriticalSection` at `0x18001facc`
- `KERNEL32!LeaveCriticalSection` at `0x18001faa4`
- `KERNEL32!LeaveCriticalSection` at `0x18001facc`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18001fa74`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18001fa74`
- `MSDART!UMSEnterCSWraper` at `0x18001fa4d`
- `MSDART!UMSEnterCSWraper` at `0x18001fa4d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CImpIRowsetInfo::GetSpecification(
        CImpIRowsetInfo *this,
        const struct _GUID *a2,
        struct IUnknown **a3)
{
  __int64 v4; // rbx
  DWORD *v5; // rdi
  unsigned int v6; // esi
  bool v7; // zf
  __int64 v8; // rcx
  __int64 v10; // rcx

  v4 = *((_QWORD *)this + 3) + 128LL;
  UMSEnterCSWraper(v4);
  v5 = (DWORD *)(v4 + 8);
  if ( !*(_DWORD *)(v4 + 12) )
    *v5 = GetCurrentThreadId();
  ++*(_DWORD *)(v4 + 12);
  ++*(_DWORD *)(v4 + 16);
  SetErrorInfo(0, 0);
  if ( a3 )
  {
    *a3 = 0;
    --*(_DWORD *)(v4 + 16);
    v7 = (*(_DWORD *)(v4 + 12))-- == 1;
    if ( v7 )
      *v5 = -1;
    v10 = *(_QWORD *)v4;
    --*(_DWORD *)(v10 + 48);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v10 + 8));
    return 1;
  }
  else
  {
    v6 = Exit(-2147024809, 0);
    --*(_DWORD *)(v4 + 16);
    v7 = (*(_DWORD *)(v4 + 12))-- == 1;
    if ( v7 )
      *v5 = -1;
    v8 = *(_QWORD *)v4;
    --*(_DWORD *)(v8 + 48);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v8 + 8));
    return v6;
  }
}

```

## disassembly

```asm
0x18001fa30  mov     [rsp+arg_8], rbx
0x18001fa35  mov     [rsp+arg_10], rsi
0x18001fa3a  push    rdi
0x18001fa3b  sub     rsp, 20h
0x18001fa3f  mov     rsi, r8
0x18001fa42  mov     rbx, [rcx+18h]
0x18001fa46  sub     rbx, 0FFFFFFFFFFFFFF80h
0x18001fa4a  mov     rcx, rbx
0x18001fa4d  call    cs:__imp_UMSEnterCSWraper
0x18001fa53  lea     rdi, [rbx+8]
0x18001fa57  cmp     dword ptr [rbx+0Ch], 0
0x18001fa5b  jnz     short loc_18001FA65
0x18001fa5d  call    cs:__imp_GetCurrentThreadId
0x18001fa63  mov     [rdi], eax
0x18001fa65  inc     dword ptr [rbx+0Ch]
0x18001fa68  inc     dword ptr [rbx+10h]
0x18001fa6b  mov     [rsp+28h+arg_0], rbx
0x18001fa70  xor     edx, edx; perrinfo
0x18001fa72  xor     ecx, ecx; dwReserved
0x18001fa74  call    cs:__imp_SetErrorInfo
0x18001fa7a  test    rsi, rsi
0x18001fa7d  jnz     short loc_18001FAAE
0x18001fa7f  xor     edx, edx; unsigned int
0x18001fa81  mov     ecx, 80070057h; int
0x18001fa86  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x18001fa8b  mov     esi, eax
0x18001fa8d  or      edx, 0FFFFFFFFh
0x18001fa90  add     [rbx+10h], edx
0x18001fa93  add     [rbx+0Ch], edx
0x18001fa96  jnz     short loc_18001FA9A
0x18001fa98  mov     [rdi], edx
0x18001fa9a  mov     rcx, [rbx]
0x18001fa9d  dec     dword ptr [rcx+30h]
0x18001faa0  add     rcx, 8; lpCriticalSection
0x18001faa4  call    cs:__imp_LeaveCriticalSection
0x18001faaa  mov     eax, esi
0x18001faac  jmp     short loc_18001FAD7
0x18001faae  mov     qword ptr [rsi], 0
0x18001fab5  or      edx, 0FFFFFFFFh
0x18001fab8  add     [rbx+10h], edx
0x18001fabb  add     [rbx+0Ch], edx
0x18001fabe  jnz     short loc_18001FAC2
0x18001fac0  mov     [rdi], edx
0x18001fac2  mov     rcx, [rbx]
0x18001fac5  dec     dword ptr [rcx+30h]
0x18001fac8  add     rcx, 8; lpCriticalSection
0x18001facc  call    cs:__imp_LeaveCriticalSection
0x18001fad2  mov     eax, 1
0x18001fad7  mov     rbx, [rsp+28h+arg_8]
0x18001fadc  mov     rsi, [rsp+28h+arg_10]
0x18001fae1  add     rsp, 20h
0x18001fae5  pop     rdi
0x18001fae6  retn
```
