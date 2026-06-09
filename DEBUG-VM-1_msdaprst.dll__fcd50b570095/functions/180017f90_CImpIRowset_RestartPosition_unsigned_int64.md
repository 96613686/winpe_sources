# CImpIRowset::RestartPosition(unsigned __int64)

- ea: `0x180017f90`
- end: `0x18001804f`
- name: `?RestartPosition@CImpIRowset@@UEAAJ_K@Z`
- size: `191`
- prototype: `__int64 __fastcall(CImpIRowset *__hidden this, unsigned __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180011278`
- `0x180015fb4`
- `0x180017f90`
- `0x180030010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180017fba`
- `KERNEL32!GetCurrentThreadId` at `0x180017fba`
- `KERNEL32!LeaveCriticalSection` at `0x18001803e`
- `KERNEL32!LeaveCriticalSection` at `0x18001803e`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180017fd1`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180017fd1`
- `MSDART!UMSEnterCSWraper` at `0x180017faa`
- `MSDART!UMSEnterCSWraper` at `0x180017faa`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CImpIRowset::RestartPosition(CImpIRowset *this, __int64 a2)
{
  __int64 v4; // rbx
  DWORD *v5; // rdi
  __int64 v6; // r9
  int v7; // ecx
  unsigned int v8; // esi
  __int64 v10; // rcx

  v4 = *((_QWORD *)this + 3) + 128LL;
  UMSEnterCSWraper(v4);
  v5 = (DWORD *)(v4 + 8);
  if ( !*(_DWORD *)(v4 + 12) )
    *v5 = GetCurrentThreadId();
  ++*(_DWORD *)(v4 + 12);
  ++*(_DWORD *)(v4 + 16);
  SetErrorInfo(0, 0);
  if ( (unsigned int)CBitArray::ArrayEmpty(*(CBitArray **)(*((_QWORD *)this + 3) + 208LL)) )
  {
    v7 = -2147217883;
  }
  else
  {
    *(_DWORD *)(v6 + 248) &= ~0x100u;
    *(_DWORD *)(*((_QWORD *)this + 3) + 240LL) = 0;
    v7 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 3) + 72LL))(*((_QWORD *)this + 3), a2);
  }
  v8 = Exit(v7, 0);
  --*(_DWORD *)(v4 + 16);
  if ( (*(_DWORD *)(v4 + 12))-- == 1 )
    *v5 = -1;
  v10 = *(_QWORD *)v4;
  --*(_DWORD *)(v10 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v10 + 8));
  return v8;
}

```

## disassembly

```asm
0x180017f90  push    rbx
0x180017f92  push    rbp
0x180017f93  push    rsi
0x180017f94  push    rdi
0x180017f95  sub     rsp, 28h
0x180017f99  mov     rbp, rdx
0x180017f9c  mov     rsi, rcx
0x180017f9f  mov     rbx, [rcx+18h]
0x180017fa3  sub     rbx, 0FFFFFFFFFFFFFF80h
0x180017fa7  mov     rcx, rbx
0x180017faa  call    cs:__imp_UMSEnterCSWraper
0x180017fb0  lea     rdi, [rbx+8]
0x180017fb4  cmp     dword ptr [rbx+0Ch], 0
0x180017fb8  jnz     short loc_180017FC2
0x180017fba  call    cs:__imp_GetCurrentThreadId
0x180017fc0  mov     [rdi], eax
0x180017fc2  inc     dword ptr [rbx+0Ch]
0x180017fc5  inc     dword ptr [rbx+10h]
0x180017fc8  mov     [rsp+48h+arg_0], rbx
0x180017fcd  xor     edx, edx; perrinfo
0x180017fcf  xor     ecx, ecx; dwReserved
0x180017fd1  call    cs:__imp_SetErrorInfo
0x180017fd7  mov     r9, [rsi+18h]
0x180017fdb  mov     rcx, [r9+0D0h]; this
0x180017fe2  call    ?ArrayEmpty@CBitArray@@QEAAJXZ; CBitArray::ArrayEmpty(void)
0x180017fe7  test    eax, eax
0x180017fe9  jz      short loc_180017FF2
0x180017feb  mov     ecx, 80040E25h
0x180017ff0  jmp     short loc_18001801E
0x180017ff2  btr     dword ptr [r9+0F8h], 8
0x180017ffb  mov     rax, [rsi+18h]
0x180017fff  mov     dword ptr [rax+0F0h], 0
0x180018009  mov     rcx, [rsi+18h]
0x18001800d  mov     rax, [rcx]
0x180018010  mov     rdx, rbp
0x180018013  mov     rax, [rax+48h]
0x180018017  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001801c  mov     ecx, eax; int
0x18001801e  xor     edx, edx; unsigned int
0x180018020  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x180018025  mov     esi, eax
0x180018027  or      edx, 0FFFFFFFFh
0x18001802a  add     [rbx+10h], edx
0x18001802d  add     [rbx+0Ch], edx
0x180018030  jnz     short loc_180018034
0x180018032  mov     [rdi], edx
0x180018034  mov     rcx, [rbx]
0x180018037  dec     dword ptr [rcx+30h]
0x18001803a  add     rcx, 8; lpCriticalSection
0x18001803e  call    cs:__imp_LeaveCriticalSection
0x180018044  mov     eax, esi
0x180018046  add     rsp, 28h
0x18001804a  pop     rdi
0x18001804b  pop     rsi
0x18001804c  pop     rbp
0x18001804d  pop     rbx
0x18001804e  retn
```
