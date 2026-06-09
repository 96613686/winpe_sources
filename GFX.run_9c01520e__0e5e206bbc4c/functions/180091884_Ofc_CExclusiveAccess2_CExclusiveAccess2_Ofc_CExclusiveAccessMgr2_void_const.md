# Ofc::CExclusiveAccess2::CExclusiveAccess2(Ofc::CExclusiveAccessMgr2 &,void const *)

- ea: `0x180091884`
- end: `0x1800919f0`
- name: `??0CExclusiveAccess2@Ofc@@QEAA@AEAVCExclusiveAccessMgr2@1@PEBX@Z`
- size: `364`
- prototype: `_QWORD(Ofc::CExclusiveAccess2 *__hidden this, struct Ofc::CExclusiveAccessMgr2 *, const void *)`
- caller_count: `12`
- callee_count: `4`
- tags: ``

## callers

- `0x180057330`
- `0x1800aedf0`
- `0x1800b059c`
- `0x1800fa9d0`
- `0x1800faccc`
- `0x1800fc88c`
- `0x180102954`
- `0x180172f10`
- `0x180173940`
- `0x18018dbd0`
- `0x18018ed80`
- `0x1801b3020`

## callees

- `0x180091884`
- `0x1800926b4`
- `0x1800e38d0`
- `0x180161450`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800918ae`
- `KERNEL32!GetCurrentThreadId` at `0x1800918ae`
- `KERNEL32!WaitForSingleObjectEx` at `0x18009199b`
- `KERNEL32!WaitForSingleObjectEx` at `0x18009199b`
- `KERNEL32!ResetEvent` at `0x180091977`
- `KERNEL32!ResetEvent` at `0x180091977`
- `MSVCP140!_Mtx_unlock` at `0x180091944`
- `MSVCP140!_Mtx_unlock` at `0x180091987`
- `MSVCP140!_Mtx_unlock` at `0x180091944`
- `MSVCP140!_Mtx_unlock` at `0x180091987`
- `MSVCP140!_Mtx_lock` at `0x1800918c3`
- `MSVCP140!_Mtx_lock` at `0x1800918c3`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800918d2`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800918ee`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800918d2`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800918ee`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
Ofc::CExclusiveAccess2 *__fastcall Ofc::CExclusiveAccess2::CExclusiveAccess2(
        Ofc::CExclusiveAccess2 *this,
        struct Ofc::CExclusiveAccessMgr2 *a2,
        const void *a3)
{
  DWORD CurrentThreadId; // ebp
  char v6; // di
  unsigned __int64 v7; // rdx
  unsigned __int64 v8; // r8
  __int64 v9; // rax

  *(_QWORD *)this = a2;
  *((_QWORD *)this + 1) = a3;
  if ( a3 )
  {
    CurrentThreadId = GetCurrentThreadId();
    v6 = 1;
LABEL_3:
    if ( _Mtx_lock(a2) )
    {
      std::_Throw_Cpp_error(5);
      __debugbreak();
    }
    if ( *((_DWORD *)a2 + 19) == 0x7FFFFFFF )
    {
      *((_DWORD *)a2 + 19) = 2147483646;
      std::_Throw_Cpp_error(6);
    }
    if ( (v6 & 0x3F) == 0 || *((_DWORD *)a2 + 22) > 8u )
      Ofc::CExclusiveAccessMgr2::CleanupOrphanedAccs(a2);
    v7 = *((_QWORD *)a2 + 10);
    v8 = v7 + 24LL * *((unsigned int *)a2 + 22);
    while ( v7 < v8 )
    {
      if ( *(_QWORD *)v7 == *((_QWORD *)this + 1) )
      {
        if ( *(_DWORD *)(v7 + 16) == CurrentThreadId )
          goto LABEL_13;
        ResetEvent(*((HANDLE *)a2 + 36));
        _InterlockedIncrement((volatile signed __int32 *)a2 + 74);
        _Mtx_unlock(a2);
        WaitForSingleObjectEx(*((HANDLE *)a2 + 36), 0x32u, 0);
        _InterlockedDecrement((volatile signed __int32 *)a2 + 74);
        ++v6;
        goto LABEL_3;
      }
      v7 += 24LL;
    }
    if ( *((_DWORD *)a2 + 22) == 8
      && *((struct Ofc::CExclusiveAccessMgr2 **)a2 + 10) == (struct Ofc::CExclusiveAccessMgr2 *)((char *)a2 + 96) )
    {
      Ofc::CArrayImpl::ConvertFixedToVarBuffer(
        (struct Ofc::CExclusiveAccessMgr2 *)((char *)a2 + 80),
        0x18u,
        9u,
        (void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int))Ofc::TMoveConstructRange<GEL::PANLINK,1>::Do);
    }
    v9 = Ofc::CArrayImpl::NewTop<Ofc::CExclusiveAccessMgr2::AccData>((char *)a2 + 80);
    *(_QWORD *)v9 = *((_QWORD *)this + 1);
    *(_QWORD *)(v9 + 8) = this;
    *(_DWORD *)(v9 + 16) = CurrentThreadId;
LABEL_13:
    _Mtx_unlock(a2);
  }
  return this;
}

```

## disassembly

```asm
0x180091884  mov     [rsp+arg_8], rbx
0x180091889  mov     [rsp+arg_10], rbp
0x18009188e  mov     [rsp+arg_18], rsi
0x180091893  push    rdi
0x180091894  sub     rsp, 20h
0x180091898  mov     rbx, rdx
0x18009189b  mov     rsi, rcx
0x18009189e  mov     [rcx], rdx
0x1800918a1  mov     [rcx+8], r8
0x1800918a5  test    r8, r8
0x1800918a8  jz      loc_18009194A
0x1800918ae  call    cs:__imp_GetCurrentThreadId
0x1800918b4  mov     ebp, eax
0x1800918b6  mov     edi, 1
0x1800918bb  mov     [rsp+28h+arg_0], rbx
0x1800918c0  mov     rcx, rbx; _Mtx_t
0x1800918c3  call    cs:__imp__Mtx_lock
0x1800918c9  test    eax, eax
0x1800918cb  jz      short loc_1800918D9
0x1800918cd  mov     ecx, 5
0x1800918d2  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800918d8  int     3; Trap to Debugger
0x1800918d9  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x1800918e0  jnz     short loc_1800918F5
0x1800918e2  mov     dword ptr [rbx+4Ch], 7FFFFFFEh
0x1800918e9  mov     ecx, 6
0x1800918ee  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800918f4  nop
0x1800918f5  test    dil, 3Fh
0x1800918f9  jz      loc_1800919B8
0x1800918ff  cmp     dword ptr [rbx+58h], 8
0x180091903  ja      loc_1800919B8
0x180091909  mov     rdx, [rbx+50h]
0x18009190d  mov     eax, [rbx+58h]
0x180091910  lea     rcx, [rax+rax*2]
0x180091914  lea     r8, [rdx+rcx*8]
0x180091918  cmp     rdx, r8
0x18009191b  jb      short loc_180091962
0x18009191d  lea     rdi, [rbx+50h]
0x180091921  cmp     dword ptr [rdi+8], 8
0x180091925  jz      loc_1800919C5
0x18009192b  mov     rcx, rdi
0x18009192e  call    ??$NewTop@UAccData@CExclusiveAccessMgr2@Ofc@@@CArrayImpl@Ofc@@IEAAAEAUAccData@CExclusiveAccessMgr2@1@XZ; Ofc::CArrayImpl::NewTop<Ofc::CExclusiveAccessMgr2::AccData>(void)
0x180091933  mov     rcx, [rsi+8]
0x180091937  mov     [rax], rcx
0x18009193a  mov     [rax+8], rsi
0x18009193e  mov     [rax+10h], ebp
0x180091941  mov     rcx, rbx; _Mtx_t
0x180091944  call    cs:__imp__Mtx_unlock
0x18009194a  mov     rax, rsi
0x18009194d  mov     rbx, [rsp+28h+arg_8]
0x180091952  mov     rbp, [rsp+28h+arg_10]
0x180091957  mov     rsi, [rsp+28h+arg_18]
0x18009195c  add     rsp, 20h
0x180091960  pop     rdi
0x180091961  retn
0x180091962  mov     rax, [rsi+8]
0x180091966  cmp     [rdx], rax
0x180091969  jnz     short loc_1800919AF
0x18009196b  cmp     [rdx+10h], ebp
0x18009196e  jz      short loc_180091941
0x180091970  mov     rcx, [rbx+120h]; hEvent
0x180091977  call    cs:__imp_ResetEvent
0x18009197d  lock inc dword ptr [rbx+128h]
0x180091984  mov     rcx, rbx; _Mtx_t
0x180091987  call    cs:__imp__Mtx_unlock
0x18009198d  xor     r8d, r8d; bAlertable
0x180091990  lea     edx, [r8+32h]; dwMilliseconds
0x180091994  mov     rcx, [rbx+120h]; hHandle
0x18009199b  call    cs:__imp_WaitForSingleObjectEx
0x1800919a1  lock dec dword ptr [rbx+128h]
0x1800919a8  inc     edi
0x1800919aa  jmp     loc_1800918C0
0x1800919af  add     rdx, 18h
0x1800919b3  jmp     loc_180091918
0x1800919b8  mov     rcx, rbx; this
0x1800919bb  call    ?CleanupOrphanedAccs@CExclusiveAccessMgr2@Ofc@@AEAAXXZ; Ofc::CExclusiveAccessMgr2::CleanupOrphanedAccs(void)
0x1800919c0  jmp     loc_180091909
0x1800919c5  lea     rax, [rdi+10h]
0x1800919c9  cmp     [rdi], rax
0x1800919cc  jnz     loc_18009192B
0x1800919d2  lea     r9, ?Do@?$TMoveConstructRange@UPANLINK@GEL@@$00@Ofc@@SAXPEAE0K@Z; void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int)
0x1800919d9  mov     edx, 18h; unsigned int
0x1800919de  lea     r8d, [rdx-0Fh]; unsigned int
0x1800919e2  mov     rcx, rdi; this
0x1800919e5  call    ?ConvertFixedToVarBuffer@CArrayImpl@Ofc@@IEAAXKKP6AXPEAE0K@Z@Z; Ofc::CArrayImpl::ConvertFixedToVarBuffer(ulong,ulong,void (*)(uchar *,uchar *,ulong))
0x1800919ea  jmp     loc_18009192B
```
