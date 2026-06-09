# Microsoft::WRL2::ContextRuntimeClass::OnFinalRelease_NoLock(bool)

- ea: `0x1800120f0`
- end: `0x1800123dc`
- name: `?OnFinalRelease_NoLock@ContextRuntimeClass@WRL2@Microsoft@@MEAAX_N@Z`
- size: `748`
- prototype: `void __fastcall(Microsoft::WRL2::ContextRuntimeClass *__hidden this, bool)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800120f0`
- `0x180012da0`
- `0x180012ee8`
- `0x180013b30`
- `0x180014e14`
- `0x180036f90`
- `0x1800e77ac`
- `0x1800f6f34`
- `0x180182010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001221b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001221b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012161`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012161`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012122`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012399`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012122`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012399`

## pseudocode

```c
void __fastcall Microsoft::WRL2::ContextRuntimeClass::OnFinalRelease_NoLock(
        Microsoft::WRL2::ContextRuntimeClass *this,
        bool a2)
{
  Microsoft::WRL2::ContextRuntimeClass *v2; // rax
  int v5; // ebx
  volatile signed __int32 *v6; // rsi
  int v7; // ecx
  int v8; // edx
  int v9; // ecx
  void **v10; // rcx
  char *v11; // rbp
  char *v12; // rdi
  __int64 v13; // rdx
  char *v14; // rbx
  char *i; // rbx
  unsigned __int64 v16; // rdx
  char *v17; // rcx
  __int128 v18; // [rsp+20h] [rbp-28h] BYREF
  __int64 v19; // [rsp+30h] [rbp-18h]
  bool v20; // [rsp+50h] [rbp+8h] BYREF

  v2 = (Microsoft::WRL2::ContextRuntimeClass *)*((_QWORD *)this + 3);
  if ( v2 )
  {
    v5 = *(_DWORD *)(*((_QWORD *)v2 + 7) + 40LL);
    if ( v2 != this )
    {
      if ( v5 != GetCurrentThreadId() )
      {
        v6 = (volatile signed __int32 *)*((_QWORD *)this + 3);
        if ( _InterlockedIncrement(v6 + 4) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 80LL))(v6);
        if ( *((_DWORD *)v6 + 23) )
          Microsoft::WRL2::FailFast::Unexpected("ContextSession RIP");
        EnterCriticalSection((LPCRITICAL_SECTION)(*((_QWORD *)v6 + 7) + 24LL));
        v7 = *((_DWORD *)v6 + 16);
        if ( v7 != *((_DWORD *)v6 + 18) + *((_DWORD *)v6 + 17) )
          Microsoft::WRL2::FailFast::Unexpected("ContextSession begin counts");
        v20 = 0;
        *((_DWORD *)v6 + 16) = v7 + 1;
        Microsoft::WRL2::ContextRuntimeClass::ProcessDestroyWorkflow(this, a2, &v20);
        if ( v20 )
          (*(void (__fastcall **)(Microsoft::WRL2::ContextRuntimeClass *, __int64))(*(_QWORD *)this + 56LL))(this, 1);
        v8 = *((_DWORD *)v6 + 18);
        v9 = v8 + *((_DWORD *)v6 + 17);
        if ( --*((_DWORD *)v6 + 16) != v9 )
          Microsoft::WRL2::FailFast::Unexpected("ContextSession end counts");
        v19 = 0;
        v18 = 0;
        if ( v8 || (v10 = (void **)(v6 + 30), &v18 == (__int128 *)(v6 + 30)) )
        {
          v12 = (char *)*((_QWORD *)&v18 + 1);
          v11 = (char *)v18;
        }
        else
        {
          v11 = (char *)*v10;
          *v10 = 0;
          v12 = (char *)*((_QWORD *)v6 + 16);
          *((_QWORD *)v6 + 16) = 0;
          v19 = *((_QWORD *)v6 + 17);
          *(_QWORD *)&v18 = v11;
          *((_QWORD *)&v18 + 1) = v12;
          *((_QWORD *)v6 + 17) = 0;
        }
        LeaveCriticalSection((LPCRITICAL_SECTION)(*((_QWORD *)v6 + 7) + 24LL));
        if ( v11 != v12 )
        {
          Microsoft::WRL2::ContextSession::ProcessDeferredOperations_NoLock(&v18);
          v12 = (char *)*((_QWORD *)&v18 + 1);
          v11 = (char *)v18;
          if ( (_QWORD)v18 != *((_QWORD *)&v18 + 1) )
          {
            v14 = (char *)v18;
            do
            {
              std::_Func_class<void,>::_Tidy(v14);
              v14 += 64;
            }
            while ( v14 != v12 );
            v12 = v11;
          }
        }
        if ( v11 )
        {
          for ( i = v11; i != v12; i += 64 )
            std::_Func_class<void,>::_Tidy(i);
          v16 = (v19 - (_QWORD)v11) & 0xFFFFFFFFFFFFFFC0uLL;
          if ( v16 >= 0x1000 )
          {
            v17 = (char *)*((_QWORD *)v11 - 1);
            if ( (unsigned __int64)(v11 - v17 - 8) > 0x1F )
              __fastfail(5u);
            v16 += 39LL;
          }
          else
          {
            v17 = v11;
          }
          operator delete(v17, v16);
        }
        if ( _InterlockedExchangeAdd(v6 + 4, 0xFFFFFFFF) == 1 )
        {
          LOBYTE(v13) = 1;
          (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)v6 + 64LL))(v6, v13);
        }
        return;
      }
      v20 = 0;
      Microsoft::WRL2::ContextRuntimeClass::ProcessDestroyWorkflow(this, a2, &v20);
      goto LABEL_30;
    }
    if ( !v5 || v5 != GetCurrentThreadId() )
    {
      Microsoft::WRL2::ContextSession::BeginApiEntry(*((Microsoft::WRL2::ContextSession **)this + 3));
      v20 = 0;
      Microsoft::WRL2::ContextRuntimeClass::ProcessDestroyWorkflow(this, a2, &v20);
      Microsoft::WRL2::ContextSession::EndApiEntry(*((Microsoft::WRL2::ContextSession **)this + 3));
LABEL_30:
      if ( v20 )
        (*(void (__fastcall **)(Microsoft::WRL2::ContextRuntimeClass *, __int64))(*(_QWORD *)this + 56LL))(this, 1);
      return;
    }
    if ( (*(_BYTE *)(*((_QWORD *)this + 3) + 48LL) & 0x11) != 0x10 )
      Microsoft::WRL2::FailFast::Unexpected("FinalRelease session critsec");
  }
  else if ( (*((_BYTE *)this + 48) & 0x1F) != 0 )
  {
    Microsoft::WRL2::FailFast::Unexpected("FinalRelease preconditions");
  }
}

```

## disassembly

```asm
0x1800120f0  mov     [rsp+arg_18], rbp
0x1800120f5  push    rdi
0x1800120f6  sub     rsp, 40h
0x1800120fa  mov     rax, [rcx+18h]
0x1800120fe  movzx   ebp, dl
0x180012101  mov     rdi, rcx
0x180012104  test    rax, rax
0x180012107  jz      loc_18001232F
0x18001210d  mov     [rsp+48h+arg_8], rbx
0x180012112  mov     rbx, [rax+38h]
0x180012116  mov     ebx, [rbx+28h]
0x180012119  cmp     rax, rcx
0x18001211c  jz      loc_1800122CA
0x180012122  call    cs:__imp_GetCurrentThreadId
0x180012128  cmp     ebx, eax
0x18001212a  jz      loc_180012317
0x180012130  mov     [rsp+48h+arg_10], rsi
0x180012135  mov     eax, 1
0x18001213a  mov     rsi, [rdi+18h]
0x18001213e  lock xadd [rsi+10h], eax
0x180012143  inc     eax
0x180012145  cmp     eax, 1
0x180012148  jz      loc_18001236B
0x18001214e  mov     eax, [rsi+5Ch]
0x180012151  test    eax, eax
0x180012153  jnz     loc_18001238C
0x180012159  mov     rcx, [rsi+38h]
0x18001215d  add     rcx, 18h; lpCriticalSection
0x180012161  call    cs:__imp_EnterCriticalSection
0x180012167  mov     eax, [rsi+44h]
0x18001216a  add     eax, [rsi+48h]
0x18001216d  mov     ecx, [rsi+40h]
0x180012170  cmp     ecx, eax
0x180012172  jnz     loc_18001237F
0x180012178  lea     eax, [rcx+1]
0x18001217b  mov     [rsp+48h+arg_0], 0
0x180012180  mov     rcx, rdi; this
0x180012183  mov     [rsi+40h], eax
0x180012186  lea     r8, [rsp+48h+arg_0]; bool *
0x18001218b  movzx   edx, bpl; bool
0x18001218f  call    ?ProcessDestroyWorkflow@ContextRuntimeClass@WRL2@Microsoft@@AEAAX_NPEA_N@Z; Microsoft::WRL2::ContextRuntimeClass::ProcessDestroyWorkflow(bool,bool *)
0x180012194  cmp     [rsp+48h+arg_0], 0
0x180012199  jz      short loc_1800121AF
0x18001219b  mov     rax, [rdi]
0x18001219e  mov     edx, 1
0x1800121a3  mov     rcx, rdi
0x1800121a6  mov     rax, [rax+38h]
0x1800121aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800121af  mov     ecx, [rsi+44h]
0x1800121b2  mov     edx, [rsi+48h]
0x1800121b5  add     ecx, edx
0x1800121b7  dec     dword ptr [rsi+40h]
0x1800121ba  cmp     [rsi+40h], ecx
0x1800121bd  jnz     loc_1800123C8
0x1800121c3  xor     r8d, r8d
0x1800121c6  xorps   xmm0, xmm0
0x1800121c9  mov     [rsp+48h+var_18], r8
0x1800121ce  movdqu  [rsp+48h+var_28], xmm0
0x1800121d4  test    edx, edx
0x1800121d6  jnz     loc_180012342
0x1800121dc  lea     rcx, [rsi+78h]
0x1800121e0  lea     rax, [rsp+48h+var_28]
0x1800121e5  cmp     rax, rcx
0x1800121e8  jz      loc_180012342
0x1800121ee  mov     rbp, [rcx]
0x1800121f1  mov     [rcx], r8
0x1800121f4  mov     rdi, [rcx+8]
0x1800121f8  mov     [rcx+8], r8
0x1800121fc  mov     rax, [rcx+10h]
0x180012200  mov     [rsp+48h+var_18], rax
0x180012205  mov     qword ptr [rsp+48h+var_28], rbp
0x18001220a  mov     qword ptr [rsp+48h+var_28+8], rdi
0x18001220f  mov     [rcx+10h], r8
0x180012213  mov     rcx, [rsi+38h]
0x180012217  add     rcx, 18h; lpCriticalSection
0x18001221b  call    cs:__imp_LeaveCriticalSection
0x180012221  cmp     rbp, rdi
0x180012224  jz      short loc_180012256
0x180012226  lea     rcx, [rsp+48h+var_28]
0x18001222b  call    ?ProcessDeferredOperations_NoLock@ContextSession@WRL2@Microsoft@@CAXAEBV?$vector@V?$function@$$A6AXXZ@std@@V?$allocator@V?$function@$$A6AXXZ@std@@@2@@std@@@Z; Microsoft::WRL2::ContextSession::ProcessDeferredOperations_NoLock(std::vector<std::function<void (void)>> const &)
0x180012230  mov     rbp, qword ptr [rsp+48h+var_28]
0x180012235  mov     rdi, qword ptr [rsp+48h+var_28+8]
0x18001223a  cmp     rbp, rdi
0x18001223d  jz      short loc_180012256
0x18001223f  mov     rbx, rbp
0x180012242  mov     rcx, rbx
0x180012245  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x18001224a  add     rbx, 40h ; '@'
0x18001224e  cmp     rbx, rdi
0x180012251  jnz     short loc_180012242
0x180012253  mov     rdi, rbp
0x180012256  test    rbp, rbp
0x180012259  jz      short loc_180012295
0x18001225b  mov     rbx, rbp
0x18001225e  cmp     rbp, rdi
0x180012261  jz      short loc_180012274
0x180012263  mov     rcx, rbx
0x180012266  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x18001226b  add     rbx, 40h ; '@'
0x18001226f  cmp     rbx, rdi
0x180012272  jnz     short loc_180012263
0x180012274  mov     rdx, [rsp+48h+var_18]
0x180012279  sub     rdx, rbp
0x18001227c  and     rdx, 0FFFFFFFFFFFFFFC0h; unsigned __int64
0x180012280  cmp     rdx, 1000h
0x180012287  jnb     loc_180012351
0x18001228d  mov     rcx, rbp; void *
0x180012290  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180012295  mov     eax, 0FFFFFFFFh
0x18001229a  lock xadd [rsi+10h], eax
0x18001229f  cmp     eax, 1
0x1800122a2  jnz     short loc_1800122B5
0x1800122a4  mov     rax, [rsi]
0x1800122a7  mov     dl, 1
0x1800122a9  mov     rcx, rsi
0x1800122ac  mov     rax, [rax+40h]
0x1800122b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800122b5  mov     rsi, [rsp+48h+arg_10]
0x1800122ba  mov     rbx, [rsp+48h+arg_8]
0x1800122bf  mov     rbp, [rsp+48h+arg_18]
0x1800122c4  add     rsp, 40h
0x1800122c8  pop     rdi
0x1800122c9  retn
0x1800122ca  test    ebx, ebx
0x1800122cc  jnz     loc_180012399
0x1800122d2  mov     rcx, [rdi+18h]; this
0x1800122d6  call    ?BeginApiEntry@ContextSession@WRL2@Microsoft@@QEAAXXZ; Microsoft::WRL2::ContextSession::BeginApiEntry(void)
0x1800122db  lea     r8, [rsp+48h+arg_0]; bool *
0x1800122e0  mov     [rsp+48h+arg_0], 0
0x1800122e5  movzx   edx, bpl; bool
0x1800122e9  mov     rcx, rdi; this
0x1800122ec  call    ?ProcessDestroyWorkflow@ContextRuntimeClass@WRL2@Microsoft@@AEAAX_NPEA_N@Z; Microsoft::WRL2::ContextRuntimeClass::ProcessDestroyWorkflow(bool,bool *)
0x1800122f1  mov     rcx, [rdi+18h]; this
0x1800122f5  call    ?EndApiEntry@ContextSession@WRL2@Microsoft@@QEAAXXZ; Microsoft::WRL2::ContextSession::EndApiEntry(void)
0x1800122fa  cmp     [rsp+48h+arg_0], 0
0x1800122ff  jz      short loc_1800122BA
0x180012301  mov     rax, [rdi]
0x180012304  mov     edx, 1
0x180012309  mov     rcx, rdi
0x18001230c  mov     rax, [rax+38h]
0x180012310  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012315  jmp     short loc_1800122BA
0x180012317  lea     r8, [rsp+48h+arg_0]; bool *
0x18001231c  mov     [rsp+48h+arg_0], 0
0x180012321  movzx   edx, bpl; bool
0x180012325  mov     rcx, rdi; this
0x180012328  call    ?ProcessDestroyWorkflow@ContextRuntimeClass@WRL2@Microsoft@@AEAAX_NPEA_N@Z; Microsoft::WRL2::ContextRuntimeClass::ProcessDestroyWorkflow(bool,bool *)
0x18001232d  jmp     short loc_1800122FA
0x18001232f  test    byte ptr [rcx+30h], 1Fh
0x180012333  jz      short loc_1800122BF
0x180012335  lea     rcx, aFinalreleasePr; "FinalRelease preconditions"
0x18001233c  call    ?Unexpected@FailFast@WRL2@Microsoft@@SAXPEBD@Z; Microsoft::WRL2::FailFast::Unexpected(char const *)
0x180012342  mov     rdi, qword ptr [rsp+48h+var_28+8]
0x180012347  mov     rbp, qword ptr [rsp+48h+var_28]
0x18001234c  jmp     loc_180012213
0x180012351  mov     rcx, [rbp-8]
0x180012355  sub     rbp, rcx
0x180012358  sub     rbp, 8
0x18001235c  cmp     rbp, 1Fh
0x180012360  ja      short loc_1800123D5
0x180012362  add     rdx, 27h ; '''
0x180012366  jmp     loc_180012290
0x18001236b  mov     rax, [rsi]
0x18001236e  mov     rcx, rsi
0x180012371  mov     rax, [rax+50h]
0x180012375  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001237a  jmp     loc_18001214E
0x18001237f  lea     rcx, aContextsession; "ContextSession begin counts"
0x180012386  call    ?Unexpected@FailFast@WRL2@Microsoft@@SAXPEBD@Z; Microsoft::WRL2::FailFast::Unexpected(char const *)
0x18001238c  lea     rcx, aContextsession_0; "ContextSession RIP"
0x180012393  call    ?Unexpected@FailFast@WRL2@Microsoft@@SAXPEBD@Z; Microsoft::WRL2::FailFast::Unexpected(char const *)
0x180012399  call    cs:__imp_GetCurrentThreadId
0x18001239f  cmp     ebx, eax
0x1800123a1  jnz     loc_1800122D2
0x1800123a7  mov     rax, [rdi+18h]
0x1800123ab  movzx   ecx, byte ptr [rax+30h]
0x1800123af  and     cl, 11h
0x1800123b2  cmp     cl, 10h
0x1800123b5  jz      loc_1800122BA
0x1800123bb  lea     rcx, aFinalreleaseSe; "FinalRelease session critsec"
0x1800123c2  call    ?Unexpected@FailFast@WRL2@Microsoft@@SAXPEBD@Z; Microsoft::WRL2::FailFast::Unexpected(char const *)
0x1800123c8  lea     rcx, aContextsession_3; "ContextSession end counts"
0x1800123cf  call    ?Unexpected@FailFast@WRL2@Microsoft@@SAXPEBD@Z; Microsoft::WRL2::FailFast::Unexpected(char const *)
0x1800123d5  mov     ecx, 5
0x1800123da  int     29h; Win8: RtlFailFast(ecx)
```
