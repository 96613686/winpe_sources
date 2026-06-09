# CImpIUpdateInfo::GetUpdateCriteria(ulong *)

- ea: `0x180022a50`
- end: `0x180022ad2`
- name: `?GetUpdateCriteria@CImpIUpdateInfo@@UEAAJPEAK@Z`
- size: `130`
- prototype: `__int64 __fastcall(CImpIUpdateInfo *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x180015fb4`
- `0x180022a50`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180022a76`
- `KERNEL32!GetCurrentThreadId` at `0x180022a76`
- `KERNEL32!LeaveCriticalSection` at `0x180022aba`
- `KERNEL32!LeaveCriticalSection` at `0x180022aba`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180022a8e`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180022a8e`
- `MSDART!UMSEnterCSWraper` at `0x180022a6a`
- `MSDART!UMSEnterCSWraper` at `0x180022a6a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CImpIUpdateInfo::GetUpdateCriteria(CImpIUpdateInfo *this, unsigned int *a2)
{
  __int64 v2; // rbx
  unsigned int v3; // esi
  __int64 v5; // rcx

  v2 = *((_QWORD *)this + 3) + 128LL;
  UMSEnterCSWraper(v2);
  if ( !*(_DWORD *)(v2 + 12) )
    *(_DWORD *)(v2 + 8) = GetCurrentThreadId();
  ++*(_DWORD *)(v2 + 12);
  ++*(_DWORD *)(v2 + 16);
  SetErrorInfo(0, 0);
  v3 = Exit(-2147467263, 0);
  --*(_DWORD *)(v2 + 16);
  if ( (*(_DWORD *)(v2 + 12))-- == 1 )
    *(_DWORD *)(v2 + 8) = -1;
  v5 = *(_QWORD *)v2;
  --*(_DWORD *)(v5 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v5 + 8));
  return v3;
}

```

## disassembly

```asm
0x180022a50  mov     [rsp+arg_8], rbx
0x180022a55  mov     [rsp+arg_10], rsi
0x180022a5a  push    rdi
0x180022a5b  sub     rsp, 20h
0x180022a5f  mov     rbx, [rcx+18h]
0x180022a63  sub     rbx, 0FFFFFFFFFFFFFF80h
0x180022a67  mov     rcx, rbx
0x180022a6a  call    cs:__imp_UMSEnterCSWraper
0x180022a70  cmp     dword ptr [rbx+0Ch], 0
0x180022a74  jnz     short loc_180022A7F
0x180022a76  call    cs:__imp_GetCurrentThreadId
0x180022a7c  mov     [rbx+8], eax
0x180022a7f  inc     dword ptr [rbx+0Ch]
0x180022a82  inc     dword ptr [rbx+10h]
0x180022a85  mov     [rsp+28h+arg_0], rbx
0x180022a8a  xor     edx, edx; perrinfo
0x180022a8c  xor     ecx, ecx; dwReserved
0x180022a8e  call    cs:__imp_SetErrorInfo
0x180022a94  xor     edx, edx; unsigned int
0x180022a96  mov     ecx, 80004001h; int
0x180022a9b  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x180022aa0  mov     esi, eax
0x180022aa2  or      eax, 0FFFFFFFFh
0x180022aa5  add     [rbx+10h], eax
0x180022aa8  add     [rbx+0Ch], eax
0x180022aab  jnz     short loc_180022AB0
0x180022aad  mov     [rbx+8], eax
0x180022ab0  mov     rcx, [rbx]
0x180022ab3  dec     dword ptr [rcx+30h]
0x180022ab6  add     rcx, 8; lpCriticalSection
0x180022aba  call    cs:__imp_LeaveCriticalSection
0x180022ac0  mov     eax, esi
0x180022ac2  mov     rbx, [rsp+28h+arg_8]
0x180022ac7  mov     rsi, [rsp+28h+arg_10]
0x180022acc  add     rsp, 20h
0x180022ad0  pop     rdi
0x180022ad1  retn
```
