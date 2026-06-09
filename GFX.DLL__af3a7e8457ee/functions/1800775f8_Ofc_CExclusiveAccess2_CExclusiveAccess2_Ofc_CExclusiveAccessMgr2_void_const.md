# Ofc::CExclusiveAccess2::CExclusiveAccess2(Ofc::CExclusiveAccessMgr2 &,void const *)

- ea: `0x1800775f8`
- end: `0x180077761`
- name: `??0CExclusiveAccess2@Ofc@@QEAA@AEAVCExclusiveAccessMgr2@1@PEBX@Z`
- size: `361`
- prototype: `_QWORD(Ofc::CExclusiveAccess2 *__hidden this, struct Ofc::CExclusiveAccessMgr2 *, const void *)`
- caller_count: `12`
- callee_count: `4`
- tags: ``

## callers

- `0x180056950`
- `0x18008d5b0`
- `0x18008d75c`
- `0x18008e138`
- `0x180099cc0`
- `0x18009c46c`
- `0x1801048dc`
- `0x18016eca8`
- `0x18016f5b0`
- `0x18018a100`
- `0x18018b2b0`
- `0x1801af400`

## callees

- `0x1800775f8`
- `0x180078444`
- `0x1800bd910`
- `0x18015ee1c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180077622`
- `KERNEL32!GetCurrentThreadId` at `0x180077622`
- `KERNEL32!WaitForSingleObjectEx` at `0x180077715`
- `KERNEL32!WaitForSingleObjectEx` at `0x180077715`
- `KERNEL32!ResetEvent` at `0x1800776f1`
- `KERNEL32!ResetEvent` at `0x1800776f1`
- `MSVCP140!_Mtx_unlock` at `0x1800776b8`
- `MSVCP140!_Mtx_unlock` at `0x180077701`
- `MSVCP140!_Mtx_unlock` at `0x1800776b8`
- `MSVCP140!_Mtx_unlock` at `0x180077701`
- `MSVCP140!_Mtx_lock` at `0x180077637`
- `MSVCP140!_Mtx_lock` at `0x180077637`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180077646`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180077662`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180077646`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180077662`

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
0x1800775f8  mov     [rsp+arg_8], rbx
0x1800775fd  mov     [rsp+arg_10], rbp
0x180077602  mov     [rsp+arg_18], rsi
0x180077607  push    rdi
0x180077608  sub     rsp, 20h
0x18007760c  mov     rbx, rdx
0x18007760f  mov     rsi, rcx
0x180077612  mov     [rcx], rdx
0x180077615  mov     [rcx+8], r8
0x180077619  test    r8, r8
0x18007761c  jz      loc_1800776BE
0x180077622  call    cs:__imp_GetCurrentThreadId
0x180077628  mov     ebp, eax
0x18007762a  mov     edi, 1
0x18007762f  mov     [rsp+28h+arg_0], rbx
0x180077634  mov     rcx, rbx; _Mtx_t
0x180077637  call    cs:__imp__Mtx_lock
0x18007763d  test    eax, eax
0x18007763f  jz      short loc_18007764D
0x180077641  mov     ecx, 5
0x180077646  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18007764c  int     3; Trap to Debugger
0x18007764d  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x180077654  jnz     short loc_180077669
0x180077656  mov     dword ptr [rbx+4Ch], 7FFFFFFEh
0x18007765d  mov     ecx, 6
0x180077662  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180077668  nop
0x180077669  test    dil, 3Fh
0x18007766d  jz      loc_180077729
0x180077673  cmp     dword ptr [rbx+58h], 8
0x180077677  ja      loc_180077729
0x18007767d  mov     rdx, [rbx+50h]
0x180077681  mov     eax, [rbx+58h]
0x180077684  lea     rcx, [rax+rax*2]
0x180077688  lea     r8, [rdx+rcx*8]
0x18007768c  cmp     rdx, r8
0x18007768f  jb      short loc_1800776D6
0x180077691  lea     rdi, [rbx+50h]
0x180077695  cmp     dword ptr [rdi+8], 8
0x180077699  jz      loc_180077736
0x18007769f  mov     rcx, rdi
0x1800776a2  call    ??$NewTop@UAccData@CExclusiveAccessMgr2@Ofc@@@CArrayImpl@Ofc@@IEAAAEAUAccData@CExclusiveAccessMgr2@1@XZ; Ofc::CArrayImpl::NewTop<Ofc::CExclusiveAccessMgr2::AccData>(void)
0x1800776a7  mov     rcx, [rsi+8]
0x1800776ab  mov     [rax], rcx
0x1800776ae  mov     [rax+8], rsi
0x1800776b2  mov     [rax+10h], ebp
0x1800776b5  mov     rcx, rbx; _Mtx_t
0x1800776b8  call    cs:__imp__Mtx_unlock
0x1800776be  mov     rax, rsi
0x1800776c1  mov     rbx, [rsp+28h+arg_8]
0x1800776c6  mov     rbp, [rsp+28h+arg_10]
0x1800776cb  mov     rsi, [rsp+28h+arg_18]
0x1800776d0  add     rsp, 20h
0x1800776d4  pop     rdi
0x1800776d5  retn
0x1800776d6  mov     rax, [rsi+8]
0x1800776da  cmp     [rdx], rax
0x1800776dd  jz      short loc_1800776E5
0x1800776df  add     rdx, 18h
0x1800776e3  jmp     short loc_18007768C
0x1800776e5  cmp     [rdx+10h], ebp
0x1800776e8  jz      short loc_1800776B5
0x1800776ea  mov     rcx, [rbx+120h]; hEvent
0x1800776f1  call    cs:__imp_ResetEvent
0x1800776f7  lock inc dword ptr [rbx+128h]
0x1800776fe  mov     rcx, rbx; _Mtx_t
0x180077701  call    cs:__imp__Mtx_unlock
0x180077707  xor     r8d, r8d; bAlertable
0x18007770a  lea     edx, [r8+32h]; dwMilliseconds
0x18007770e  mov     rcx, [rbx+120h]; hHandle
0x180077715  call    cs:__imp_WaitForSingleObjectEx
0x18007771b  lock dec dword ptr [rbx+128h]
0x180077722  inc     edi
0x180077724  jmp     loc_180077634
0x180077729  mov     rcx, rbx; this
0x18007772c  call    ?CleanupOrphanedAccs@CExclusiveAccessMgr2@Ofc@@AEAAXXZ; Ofc::CExclusiveAccessMgr2::CleanupOrphanedAccs(void)
0x180077731  jmp     loc_18007767D
0x180077736  lea     rax, [rdi+10h]
0x18007773a  cmp     [rdi], rax
0x18007773d  jnz     loc_18007769F
0x180077743  lea     r9, ?Do@?$TMoveConstructRange@UPANLINK@GEL@@$00@Ofc@@SAXPEAE0K@Z; void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int)
0x18007774a  mov     edx, 18h; unsigned int
0x18007774f  lea     r8d, [rdx-0Fh]; unsigned int
0x180077753  mov     rcx, rdi; this
0x180077756  call    ?ConvertFixedToVarBuffer@CArrayImpl@Ofc@@IEAAXKKP6AXPEAE0K@Z@Z; Ofc::CArrayImpl::ConvertFixedToVarBuffer(ulong,ulong,void (*)(uchar *,uchar *,ulong))
0x18007775b  jmp     loc_18007769F
```
