# CRegistration::StartAcknowledgeMessageTimer(unsigned __int64,ulong)

- ea: `0x180038344`
- end: `0x1800385a3`
- name: `?StartAcknowledgeMessageTimer@CRegistration@@QEAAX_KK@Z`
- size: `607`
- prototype: `void __fastcall(CRegistration *__hidden this, unsigned __int64, unsigned int)`
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18003429c`
- `0x180034c5c`

## callees

- `0x180003a60`
- `0x180003a90`
- `0x18000498c`
- `0x180004998`
- `0x18000e8c0`
- `0x180013a10`
- `0x180027724`
- `0x180027cb4`
- `0x180027d40`
- `0x180038344`
- `0x18006f010`

## import_xrefs

- `api-ms-win-crt-time-l1-1-0!_time64` at `0x1800384ef`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x1800384ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003855a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003855a`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180038550`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180038550`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CRegistration::StartAcknowledgeMessageTimer(CRegistration *this, __int64 a2, unsigned int a3)
{
  __int64 v3; // r15
  __int64 v6; // rdi
  volatile signed __int32 *v7; // rbx
  CRegistration *v8; // rax
  __int64 v9; // rdx
  _WORD *v10; // rcx
  __int16 v11; // r8
  __int64 v12; // rbx
  void *v13; // rdx
  __int64 v14; // rdx
  _DWORD *v15; // [rsp+40h] [rbp-C0h]
  _BYTE v16[16]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v17; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v18[56]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v19; // [rsp+A8h] [rbp-58h]
  __time64_t Time; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v21[11]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 Src; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v23[88]; // [rsp+118h] [rbp+18h] BYREF

  v3 = a3;
  v17 = 0;
  v19 = 0;
  v6 = 40;
  v15 = operator new(0x28u);
  *(_OWORD *)v15 = 0;
  v15[2] = 1;
  v15[3] = 1;
  *(_QWORD *)v15 = &std::_Ref_count_obj2<std::vector<unsigned char>>::`vftable';
  *((_QWORD *)v15 + 2) = 0;
  *((_QWORD *)v15 + 3) = 0;
  *((_QWORD *)v15 + 4) = 0;
  *(_QWORD *)&v17 = v15 + 4;
  v7 = (volatile signed __int32 *)*((_QWORD *)&v17 + 1);
  *((_QWORD *)&v17 + 1) = v15;
  if ( v7 )
  {
    if ( _InterlockedExchangeAdd(v7 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
      if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
    }
  }
  std::vector<unsigned char>::resize(v17, 88);
  memset_0(v23, 0, 0x50u);
  Src = a2;
  if ( *((_QWORD *)this + 3) <= 7u )
    v8 = this;
  else
    v8 = *(CRegistration **)this;
  v9 = 2147483646;
  v10 = v23;
  while ( v9 )
  {
    v11 = *(_WORD *)v8;
    if ( *(_WORD *)v8 )
    {
      v8 = (CRegistration *)((char *)v8 + 2);
      *v10++ = v11;
      --v9;
      if ( --v6 )
        continue;
    }
    if ( !v6 )
      --v10;
    break;
  }
  *v10 = 0;
  std::vector<unsigned char>::resize(v17, 88);
  memmove_0(*(void **)v17, &Src, 0x58u);
  std::function<void (std::shared_ptr<std::vector<unsigned char>> &)>::operator=(v18, (char *)this + 368);
  v12 = *((_QWORD *)this + 45);
  (**(void (__fastcall ***)(__int64))(v12 + 8))(v12 + 8);
  if ( *(_DWORD *)(v12 + 88) )
  {
    v21[0] = 0;
    v21[1] = 0;
    v21[9] = 0;
    _time64(&Time);
    Time += v3;
    CSmsWorkItem::operator=(v21, &v17);
    std::_Tree<std::_Tset_traits<CSmsTimerItem,CSmsTimerCompare,std::allocator<CSmsTimerItem>,0>>::_Emplace<CSmsTimerItem const &>(
      (__int64 *)(v12 + 136),
      (__int64)v16,
      &Time);
    v13 = *(void **)(v12 + 72);
    if ( v13
      && !*(_QWORD *)(v12 + 80)
      && !CreateTimerQueueTimer(
            (PHANDLE)(v12 + 80),
            v13,
            CExecutionManager::StaticProcessTimer,
            (PVOID)v12,
            1000 * v3,
            0x4E20u,
            0) )
    {
      GetLastError();
    }
    CSmsWorkItem::~CSmsWorkItem((CSmsWorkItem *)v21, (__int64)v13);
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(v12 + 8) + 8LL))(v12 + 8);
  CSmsWorkItem::~CSmsWorkItem((CSmsWorkItem *)&v17, v14);
}

```

## disassembly

```asm
0x180038344  push    rbp
0x180038346  push    rbx
0x180038347  push    rsi
0x180038348  push    rdi
0x180038349  push    r12
0x18003834b  push    r14
0x18003834d  push    r15
0x18003834f  lea     rbp, [rsp-80h]
0x180038354  sub     rsp, 180h
0x18003835b  mov     rax, cs:__security_cookie
0x180038362  xor     rax, rsp
0x180038365  mov     [rbp+0B0h+var_40], rax
0x180038369  mov     r15d, r8d
0x18003836c  mov     r14, rdx
0x18003836f  mov     rsi, rcx
0x180038372  xor     r12d, r12d
0x180038375  xorps   xmm0, xmm0
0x180038378  movdqa  [rsp+1B0h+var_150], xmm0
0x18003837e  mov     [rbp+0B0h+var_108], r12
0x180038382  lea     edi, [r12+28h]
0x180038387  mov     ecx, edi; Size
0x180038389  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003838e  mov     [rsp+1B0h+var_170], rax
0x180038393  xorps   xmm0, xmm0
0x180038396  movups  xmmword ptr [rax], xmm0
0x180038399  mov     dword ptr [rax+8], 1
0x1800383a0  mov     dword ptr [rax+0Ch], 1
0x1800383a7  lea     rcx, ??_7?$_Ref_count_obj2@V?$vector@EV?$allocator@E@std@@@std@@@std@@6B@; const std::_Ref_count_obj2<std::vector<uchar>>::`vftable'
0x1800383ae  mov     [rax], rcx
0x1800383b1  lea     rcx, [rax+10h]
0x1800383b5  mov     [rcx], r12
0x1800383b8  mov     [rcx+8], r12
0x1800383bc  mov     [rcx+10h], r12
0x1800383c0  mov     qword ptr [rsp+1B0h+var_150], rcx
0x1800383c5  mov     rbx, qword ptr [rsp+1B0h+var_150+8]
0x1800383ca  mov     qword ptr [rsp+1B0h+var_150+8], rax
0x1800383cf  test    rbx, rbx
0x1800383d2  jz      short loc_18003840B
0x1800383d4  or      eax, 0FFFFFFFFh
0x1800383d7  lock xadd [rbx+8], eax
0x1800383dc  cmp     eax, 1
0x1800383df  jnz     short loc_18003840B
0x1800383e1  mov     rax, [rbx]
0x1800383e4  mov     rcx, rbx
0x1800383e7  mov     rax, [rax]
0x1800383ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800383ef  or      eax, 0FFFFFFFFh
0x1800383f2  lock xadd [rbx+0Ch], eax
0x1800383f7  cmp     eax, 1
0x1800383fa  jnz     short loc_18003840B
0x1800383fc  mov     rax, [rbx]
0x1800383ff  mov     rcx, rbx
0x180038402  mov     rax, [rax+8]
0x180038406  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003840b  mov     ebx, 58h ; 'X'
0x180038410  mov     edx, ebx
0x180038412  mov     rcx, qword ptr [rsp+1B0h+var_150]
0x180038417  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x18003841c  xor     edx, edx; Val
0x18003841e  lea     r8d, [rbx-8]; Size
0x180038422  lea     rcx, [rbp+0B0h+var_98]; void *
0x180038426  call    memset_0
0x18003842b  mov     [rbp+0B0h+Src], r14
0x18003842f  cmp     qword ptr [rsi+18h], 7
0x180038434  jbe     short loc_18003843B
0x180038436  mov     rax, [rsi]
0x180038439  jmp     short loc_18003843E
0x18003843b  mov     rax, rsi
0x18003843e  mov     edx, 7FFFFFFEh
0x180038443  lea     rcx, [rbp+0B0h+var_98]
0x180038447  test    rdx, rdx
0x18003844a  jz      short loc_180038474
0x18003844c  movzx   r8d, word ptr [rax]
0x180038450  test    r8w, r8w
0x180038454  jz      short loc_18003846B
0x180038456  add     rax, 2
0x18003845a  mov     [rcx], r8w
0x18003845e  add     rcx, 2
0x180038462  dec     rdx
0x180038465  sub     rdi, 1
0x180038469  jnz     short loc_180038447
0x18003846b  test    rdi, rdi
0x18003846e  jnz     short loc_180038474
0x180038470  sub     rcx, 2
0x180038474  mov     [rcx], r12w
0x180038478  mov     rdx, rbx
0x18003847b  mov     rcx, qword ptr [rsp+1B0h+var_150]
0x180038480  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x180038485  mov     r8, rbx; Size
0x180038488  lea     rdx, [rbp+0B0h+Src]; Src
0x18003848c  mov     rcx, qword ptr [rsp+1B0h+var_150]
0x180038491  mov     rcx, [rcx]; void *
0x180038494  call    memmove_0
0x180038499  lea     rdx, [rsi+170h]
0x1800384a0  lea     rcx, [rsp+1B0h+var_140]
0x1800384a5  call    ??4?$function@$$A6AXAEAV?$shared_ptr@V?$vector@EV?$allocator@E@std@@@std@@@std@@@Z@std@@QEAAAEAV01@AEBV01@@Z; std::function<void (std::shared_ptr<std::vector<uchar>> &)>::operator=(std::function<void (std::shared_ptr<std::vector<uchar>> &)> const &)
0x1800384aa  mov     rbx, [rsi+168h]
0x1800384b1  lea     rax, ??_7?$lock_guard@Vrecursive_mutex@Common@Sms@Windows@@@Common@Sms@Windows@@6B@; const Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable'
0x1800384b8  mov     [rsp+1B0h+var_170], rax
0x1800384bd  lea     rdi, [rbx+8]
0x1800384c1  mov     [rsp+1B0h+var_168], rdi
0x1800384c6  mov     rax, [rdi]
0x1800384c9  mov     rcx, rdi
0x1800384cc  mov     rax, [rax]
0x1800384cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800384d4  nop
0x1800384d5  cmp     [rbx+58h], r12d
0x1800384d9  jz      loc_18003856B
0x1800384df  mov     [rbp+0B0h+var_F8], r12
0x1800384e3  mov     [rbp+0B0h+var_F0], r12
0x1800384e7  mov     [rbp+0B0h+var_B0], r12
0x1800384eb  lea     rcx, [rbp+0B0h+Time]; Time
0x1800384ef  call    cs:__imp__time64
0x1800384f5  add     [rbp+0B0h+Time], r15
0x1800384f9  lea     rdx, [rsp+1B0h+var_150]
0x1800384fe  lea     rcx, [rbp+0B0h+var_F8]
0x180038502  call    ??4CSmsWorkItem@@QEAAAEAV0@AEBV0@@Z; CSmsWorkItem::operator=(CSmsWorkItem const &)
0x180038507  lea     rcx, [rbx+88h]
0x18003850e  lea     r8, [rbp+0B0h+Time]
0x180038512  lea     rdx, [rsp+1B0h+var_160]
0x180038517  call    ??$_Emplace@AEBVCSmsTimerItem@@@?$_Tree@V?$_Tset_traits@VCSmsTimerItem@@VCSmsTimerCompare@@V?$allocator@VCSmsTimerItem@@@std@@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@VCSmsTimerItem@@PEAX@std@@_N@1@AEBVCSmsTimerItem@@@Z; std::_Tree<std::_Tset_traits<CSmsTimerItem,CSmsTimerCompare,std::allocator<CSmsTimerItem>,0>>::_Emplace<CSmsTimerItem const &>(CSmsTimerItem const &)
0x18003851c  mov     rdx, [rbx+48h]; TimerQueue
0x180038520  test    rdx, rdx
0x180038523  jz      short loc_180038561
0x180038525  lea     rcx, [rbx+50h]; phNewTimer
0x180038529  cmp     [rcx], r12
0x18003852c  jnz     short loc_180038561
0x18003852e  imul    eax, r15d, 3E8h
0x180038535  mov     [rsp+1B0h+Flags], r12d; Flags
0x18003853a  mov     [rsp+1B0h+Period], 4E20h; Period
0x180038542  mov     [rsp+1B0h+DueTime], eax; DueTime
0x180038546  mov     r9, rbx; Parameter
0x180038549  lea     r8, ?StaticProcessTimer@CExecutionManager@@SAXPEAXE@Z; Callback
0x180038550  call    cs:__imp_CreateTimerQueueTimer
0x180038556  test    eax, eax
0x180038558  jnz     short loc_180038561
0x18003855a  call    cs:__imp_GetLastError
0x180038560  nop
0x180038561  lea     rcx, [rbp+0B0h+var_F8]; this
0x180038565  call    ??1CSmsWorkItem@@QEAA@XZ; CSmsWorkItem::~CSmsWorkItem(void)
0x18003856a  nop
0x18003856b  mov     rax, [rdi]
0x18003856e  mov     rcx, rdi
0x180038571  mov     rax, [rax+8]
0x180038575  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003857a  nop
0x18003857b  lea     rcx, [rsp+1B0h+var_150]; this
0x180038580  call    ??1CSmsWorkItem@@QEAA@XZ; CSmsWorkItem::~CSmsWorkItem(void)
0x180038585  mov     rcx, [rbp+0B0h+var_40]
0x180038589  xor     rcx, rsp; StackCookie
0x18003858c  call    __security_check_cookie
0x180038591  add     rsp, 180h
0x180038598  pop     r15
0x18003859a  pop     r14
0x18003859c  pop     r12
0x18003859e  pop     rdi
0x18003859f  pop     rsi
0x1800385a0  pop     rbx
0x1800385a1  pop     rbp
0x1800385a2  retn
```
