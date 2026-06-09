# CImpIAccessor::AddRefAccessor(unsigned __int64,ulong *)

- ea: `0x180001e30`
- end: `0x180001f30`
- name: `?AddRefAccessor@CImpIAccessor@@UEAAJ_KPEAK@Z`
- size: `256`
- prototype: `int(CImpIAccessor *__hidden this, unsigned __int64, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001e30`
- `0x180015fb4`
- `0x180016d94`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180001e62`
- `KERNEL32!GetCurrentThreadId` at `0x180001e62`
- `KERNEL32!LeaveCriticalSection` at `0x180001ee5`
- `KERNEL32!LeaveCriticalSection` at `0x180001f15`
- `KERNEL32!LeaveCriticalSection` at `0x180001ee5`
- `KERNEL32!LeaveCriticalSection` at `0x180001f15`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180001e83`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180001e83`
- `MSDART!UMSEnterCSWraper` at `0x180001e56`
- `MSDART!UMSEnterCSWraper` at `0x180001e56`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CImpIAccessor::AddRefAccessor(CImpIAccessor *this, unsigned int a2, unsigned int *a3)
{
  __int64 v6; // rbx
  unsigned int v7; // eax
  bool v8; // zf
  __int64 v9; // rcx
  unsigned int v11; // esi
  __int64 v12; // rcx
  __int64 v13; // [rsp+40h] [rbp+8h] BYREF
  __int64 v14; // [rsp+50h] [rbp+18h]

  v6 = *((_QWORD *)this + 3) + 128LL;
  UMSEnterCSWraper(v6);
  if ( !*(_DWORD *)(v6 + 12) )
    *(_DWORD *)(v6 + 8) = GetCurrentThreadId();
  ++*(_DWORD *)(v6 + 12);
  ++*(_DWORD *)(v6 + 16);
  v14 = v6;
  v13 = 0;
  SetErrorInfo(0, 0);
  if ( a3 )
    *a3 = 0;
  if ( CExtBuffer::GetItemOfExtBuffer(*(CExtBuffer **)(*((_QWORD *)this + 3) + 192LL), a2, &v13) >= 0 && v13 )
  {
    v7 = _InterlockedIncrement((volatile signed __int32 *)(v13 + 4));
    if ( a3 )
      *a3 = v7;
    --*(_DWORD *)(v6 + 16);
    v8 = (*(_DWORD *)(v6 + 12))-- == 1;
    if ( v8 )
      *(_DWORD *)(v6 + 8) = -1;
    v9 = *(_QWORD *)v6;
    --*(_DWORD *)(v9 + 48);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v9 + 8));
    return 0;
  }
  else
  {
    v11 = Exit(-2147217920, 0);
    --*(_DWORD *)(v6 + 16);
    v8 = (*(_DWORD *)(v6 + 12))-- == 1;
    if ( v8 )
      *(_DWORD *)(v6 + 8) = -1;
    v12 = *(_QWORD *)v6;
    --*(_DWORD *)(v12 + 48);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v12 + 8));
    return v11;
  }
}

```

## disassembly

```asm
0x180001e30  mov     [rsp+arg_8], rbx
0x180001e35  mov     [rsp+arg_18], rbp
0x180001e3a  push    rsi
0x180001e3b  push    rdi
0x180001e3c  push    r14
0x180001e3e  sub     rsp, 20h
0x180001e42  mov     rsi, r8
0x180001e45  mov     r14, rdx
0x180001e48  mov     rbp, rcx
0x180001e4b  mov     rbx, [rcx+18h]
0x180001e4f  sub     rbx, 0FFFFFFFFFFFFFF80h
0x180001e53  mov     rcx, rbx
0x180001e56  call    cs:__imp_UMSEnterCSWraper
0x180001e5c  cmp     dword ptr [rbx+0Ch], 0
0x180001e60  jnz     short loc_180001E6B
0x180001e62  call    cs:__imp_GetCurrentThreadId
0x180001e68  mov     [rbx+8], eax
0x180001e6b  inc     dword ptr [rbx+0Ch]
0x180001e6e  inc     dword ptr [rbx+10h]
0x180001e71  mov     [rsp+38h+arg_10], rbx
0x180001e76  mov     [rsp+38h+arg_0], 0
0x180001e7f  xor     edx, edx; perrinfo
0x180001e81  xor     ecx, ecx; dwReserved
0x180001e83  call    cs:__imp_SetErrorInfo
0x180001e89  test    rsi, rsi
0x180001e8c  jz      short loc_180001E94
0x180001e8e  mov     dword ptr [rsi], 0
0x180001e94  mov     edx, r14d; unsigned int
0x180001e97  mov     rcx, [rbp+18h]
0x180001e9b  lea     r8, [rsp+38h+arg_0]; void *
0x180001ea0  mov     rcx, [rcx+0C0h]; this
0x180001ea7  call    ?GetItemOfExtBuffer@CExtBuffer@@QEAAJKPEAX@Z; CExtBuffer::GetItemOfExtBuffer(ulong,void *)
0x180001eac  test    eax, eax
0x180001eae  js      short loc_180001EEF
0x180001eb0  mov     rcx, [rsp+38h+arg_0]
0x180001eb5  test    rcx, rcx
0x180001eb8  jz      short loc_180001EEF
0x180001eba  mov     eax, 1
0x180001ebf  lock xadd [rcx+4], eax
0x180001ec4  inc     eax
0x180001ec6  test    rsi, rsi
0x180001ec9  jz      short loc_180001ECD
0x180001ecb  mov     [rsi], eax
0x180001ecd  or      edx, 0FFFFFFFFh
0x180001ed0  add     [rbx+10h], edx
0x180001ed3  add     [rbx+0Ch], edx
0x180001ed6  jnz     short loc_180001EDB
0x180001ed8  mov     [rbx+8], edx
0x180001edb  mov     rcx, [rbx]
0x180001ede  dec     dword ptr [rcx+30h]
0x180001ee1  add     rcx, 8; lpCriticalSection
0x180001ee5  call    cs:__imp_LeaveCriticalSection
0x180001eeb  xor     eax, eax
0x180001eed  jmp     short loc_180001F1D
0x180001eef  xor     edx, edx; unsigned int
0x180001ef1  mov     ecx, 80040E00h; int
0x180001ef6  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x180001efb  mov     esi, eax
0x180001efd  or      edx, 0FFFFFFFFh
0x180001f00  add     [rbx+10h], edx
0x180001f03  add     [rbx+0Ch], edx
0x180001f06  jnz     short loc_180001F0B
0x180001f08  mov     [rbx+8], edx
0x180001f0b  mov     rcx, [rbx]
0x180001f0e  dec     dword ptr [rcx+30h]
0x180001f11  add     rcx, 8; lpCriticalSection
0x180001f15  call    cs:__imp_LeaveCriticalSection
0x180001f1b  mov     eax, esi
0x180001f1d  mov     rbx, [rsp+38h+arg_8]
0x180001f22  mov     rbp, [rsp+38h+arg_18]
0x180001f27  add     rsp, 20h
0x180001f2b  pop     r14
0x180001f2d  pop     rdi
0x180001f2e  pop     rsi
0x180001f2f  retn
```
