# Microsoft::CoreUI::Dispatch::TimeoutManager::Callback_OnDispatch(void)

- ea: `0x180017d80`
- end: `0x180018024`
- name: `?Callback_OnDispatch@TimeoutManager@Dispatch@CoreUI@Microsoft@@UEAAXXZ`
- size: `676`
- prototype: `void __fastcall(Microsoft::CoreUI::Dispatch::TimeoutManager *__hidden this)`
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001d38`
- `0x18000cb50`
- `0x18000ec10`
- `0x180010ed0`
- `0x180017d80`
- `0x18001802c`
- `0x1800180a4`
- `0x18001822c`
- `0x180018280`
- `0x18008ae1c`
- `0x18008f584`
- `0x1800a9824`
- `0x1800b6700`
- `0x1800cf010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x180017fcc`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x180017fcc`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x180017faa`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x180017faa`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Microsoft::CoreUI::Dispatch::TimeoutManager::Callback_OnDispatch(
        Microsoft::CoreUI::Dispatch::TimeoutManager *this)
{
  __int64 v2; // rcx
  LARGE_INTEGER v3; // rax
  System::Object *v4; // rbx
  Microsoft::CoreUI::Support::SkipList *v5; // rsi
  int v6; // ebp
  int v7; // ecx
  LARGE_INTEGER v8; // rsi
  int v9; // eax
  const char16_t *v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rdx
  int v13; // edx
  __int64 v14; // rcx
  LARGE_INTEGER v15; // rsi
  HANDLE WaitableTimer; // rax
  int v17; // edx
  __int64 v18; // rcx
  LARGE_INTEGER DueTime; // [rsp+50h] [rbp+8h] BYREF
  System::Object *v20; // [rsp+58h] [rbp+10h] BYREF

  while ( 1 )
  {
    v2 = *(_QWORD *)(*((_QWORD *)this + 9) + 32LL);
    if ( !*(_DWORD *)(v2 + 24) )
      CFlat::Abandonment::Fail((const char16_t *)v2);
    v11 = *(_QWORD *)(v2 + 32);
    if ( v11 )
    {
      if ( *(const char16_t **)(v11 + 8) != &qword_1800D0CE0 )
        CFlat::Abandonment::Fail((const char16_t *)v11);
      v12 = *(int *)(v11 + 24);
      if ( !(_DWORD)v12 )
        CFlat::Abandonment::Fail((const char16_t *)v11);
      v3 = *(LARGE_INTEGER *)(v11 + 8 * v12 + 24);
    }
    else
    {
      v3.QuadPart = 0;
    }
    DueTime = v3;
    CFlat::Cast::Checked<CFlat::SmartPtr<Microsoft::CoreUI::Dispatch::Timeout>,System::Object *>(&v20, &DueTime);
    v4 = v20;
    if ( !v20 )
      break;
    v5 = (Microsoft::CoreUI::Support::SkipList *)*((_QWORD *)this + 9);
    if ( v5 )
      ++*((_DWORD *)v5 + 4);
    Microsoft::CoreUI::Support::SkipList::RemoveFirstItem(v5);
    if ( v5 )
      System::Object::ReleaseNotFrozen$(v5);
    if ( *((_BYTE *)v4 + 96) )
    {
      v6 = *((_DWORD *)this + 20);
      v7 = 1;
      if ( v6 != -1 )
        v7 = v6 + 1;
      *((_DWORD *)this + 20) = v7;
      *((_BYTE *)v4 + 96) = 0;
      *((_DWORD *)v4 + 16) = v6;
      if ( *(_BYTE *)(*(_QWORD *)(*((_QWORD *)this + 7) + 32LL) + 32LL) )
      {
        if ( *((_QWORD *)v4 + 10) || *((_BYTE *)v4 + 98) )
          Microsoft::CoreUI::Dispatch::TimeoutManager::Schedule(this, v4, 1);
        if ( !Microsoft::CoreUI::Support::SkipList::get_FirstItem$FastReturn$(*((Microsoft::CoreUI::Support::SkipList **)this
                                                                              + 9)) )
          Microsoft::CoreUI::Dispatch::DispatchItem::ForceWakeLevel(this, 0);
      }
      v8 = *(LARGE_INTEGER *)((char *)v4 + 48);
      DueTime = v8;
      if ( v8.QuadPart )
      {
        v9 = *(_DWORD *)(v8.QuadPart + 16);
        if ( v9 > 0 )
          *(_DWORD *)(v8.QuadPart + 16) = v9 + 1;
      }
      if ( *(_DWORD *)(v8.QuadPart + 24) == 1 )
        (*(void (__fastcall **)(_QWORD))(v8.QuadPart + 40))(*(_QWORD *)(v8.QuadPart + 48));
      else
        ((void (__fastcall *)(_QWORD))CFlat::DelegateImpl<Microsoft::CoreUI::DispatchGroupHandler,0,void (void),long (void *),0>::MulticastInvoke)((LARGE_INTEGER)v8.QuadPart);
      if ( v8.QuadPart )
        System::Object::Release$((System::Object *)v8.QuadPart);
      if ( *((_DWORD *)v4 + 16) == v6 && (*((_QWORD *)v4 + 10) || *((_BYTE *)v4 + 98)) )
      {
        if ( *((_BYTE *)v4 + 96) )
          CFlat::Abandonment::Fail(v10);
        if ( *((_BYTE *)v4 + 97) )
        {
          v13 = *((_DWORD *)this + 20);
          v14 = 1;
          if ( v13 != -1 )
            v14 = (unsigned int)(v13 + 1);
          *((_DWORD *)this + 20) = v14;
          *((_BYTE *)v4 + 96) = 1;
          *((_DWORD *)v4 + 16) = v13;
          v15 = *(LARGE_INTEGER *)((char *)v4 + 80);
          WaitableTimer = (HANDLE)*((_QWORD *)v4 + 7);
          if ( !WaitableTimer )
          {
            WaitableTimer = CreateWaitableTimerExW(0, 0, 1u, 0x1F0003u);
            if ( !WaitableTimer )
              Cn::FailFast::ForWin32();
            *((_QWORD *)v4 + 7) = WaitableTimer;
          }
          DueTime = v15;
          if ( v15.QuadPart < 0 )
            CFlat::Abandonment::Fail((const char16_t *)v14);
          DueTime.QuadPart = -v15.QuadPart;
          if ( !SetWaitableTimer(WaitableTimer, &DueTime, 0, 0, 0, 0) )
            Cn::FailFast::ForWin32();
        }
        else
        {
          Microsoft::CoreUI::Dispatch::Timeout::UpdateAbsoluteDueTimeOnRepeat(v4);
          v17 = *((_DWORD *)this + 20);
          v18 = 1;
          if ( v17 != -1 )
            v18 = (unsigned int)(v17 + 1);
          *((_DWORD *)this + 20) = v18;
          *((_BYTE *)v4 + 96) = 1;
          *((_DWORD *)v4 + 16) = v17;
          Microsoft::CoreUI::Dispatch::TimeoutManager::EnableAbsoluteTimer(
            (Microsoft::CoreUI::Dispatch::TimeoutManager *)v18,
            v4);
        }
      }
    }
    if ( v4 )
      System::Object::ReleaseNotFrozen$(v4);
    if ( *((_BYTE *)this + 70) || *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 7) + 32LL) + 180LL) )
      return;
  }
  Microsoft::CoreUI::Dispatch::DispatchItem::ForceWakeLevel(this, 0);
}

```

## disassembly

```asm
0x180017d80  mov     [rsp+arg_10], rbx
0x180017d85  mov     [rsp+arg_18], rbp
0x180017d8a  push    rsi
0x180017d8b  push    rdi
0x180017d8c  push    r14
0x180017d8e  sub     rsp, 30h
0x180017d92  mov     rdi, rcx
0x180017d95  xor     r14d, r14d
0x180017d98  mov     rax, [rdi+48h]
0x180017d9c  mov     rcx, [rax+20h]; char16_t *
0x180017da0  cmp     [rcx+18h], r14d
0x180017da4  ja      loc_180017F19
0x180017daa  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x180017db0  mov     rax, r14
0x180017db3  mov     qword ptr [rsp+48h+DueTime], rax
0x180017db8  lea     rdx, [rsp+48h+DueTime]
0x180017dbd  lea     rcx, [rsp+48h+arg_8]
0x180017dc2  call    ??$Checked@V?$SmartPtr@VTimeout@Dispatch@CoreUI@Microsoft@@@CFlat@@PEAVObject@System@@@Cast@CFlat@@SA?A_P$$QEAPEAVObject@System@@@Z
0x180017dc7  nop
0x180017dc8  mov     rbx, [rsp+48h+arg_8]
0x180017dcd  test    rbx, rbx
0x180017dd0  jz      loc_180017E90
0x180017dd6  mov     rsi, [rdi+48h]
0x180017dda  test    rsi, rsi
0x180017ddd  jz      short loc_180017DE2
0x180017ddf  inc     dword ptr [rsi+10h]
0x180017de2  mov     rcx, rsi; this
0x180017de5  call    ?RemoveFirstItem@SkipList@Support@CoreUI@Microsoft@@QEAA_NXZ; Microsoft::CoreUI::Support::SkipList::RemoveFirstItem(void)
0x180017dea  test    rsi, rsi
0x180017ded  jz      short loc_180017DF7
0x180017def  mov     rcx, rsi; this
0x180017df2  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180017df7  cmp     [rbx+60h], r14b
0x180017dfb  jz      short loc_180017E6A
0x180017dfd  mov     ebp, [rdi+50h]
0x180017e00  lea     eax, [rbp+1]
0x180017e03  mov     ecx, 1
0x180017e08  cmp     ebp, 0FFFFFFFFh
0x180017e0b  cmovnz  ecx, eax
0x180017e0e  mov     [rdi+50h], ecx
0x180017e11  mov     [rbx+60h], r14b
0x180017e15  mov     [rbx+40h], ebp
0x180017e18  mov     rax, [rdi+38h]
0x180017e1c  mov     rcx, [rax+20h]
0x180017e20  cmp     [rcx+20h], r14b
0x180017e24  jnz     loc_180017EDC
0x180017e2a  mov     rsi, [rbx+30h]
0x180017e2e  mov     qword ptr [rsp+48h+DueTime], rsi
0x180017e33  test    rsi, rsi
0x180017e36  jz      short loc_180017E44
0x180017e38  mov     eax, [rsi+10h]
0x180017e3b  test    eax, eax
0x180017e3d  jle     short loc_180017E44
0x180017e3f  inc     eax
0x180017e41  mov     [rsi+10h], eax
0x180017e44  cmp     dword ptr [rsi+18h], 1
0x180017e48  jnz     short loc_180017E9D
0x180017e4a  mov     rcx, [rsi+30h]
0x180017e4e  mov     rax, [rsi+28h]
0x180017e52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017e57  nop
0x180017e58  test    rsi, rsi
0x180017e5b  jz      short loc_180017E65
0x180017e5d  mov     rcx, rsi; this
0x180017e60  call    ?Release$@Object@System@@AEAAXXZ; System::Object::Release$(void)
0x180017e65  cmp     [rbx+40h], ebp
0x180017e68  jz      short loc_180017EA7
0x180017e6a  test    rbx, rbx
0x180017e6d  jz      short loc_180017E77
0x180017e6f  mov     rcx, rbx; this
0x180017e72  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180017e77  cmp     [rdi+46h], r14b
0x180017e7b  jz      short loc_180017EBD
0x180017e7d  mov     rbx, [rsp+48h+arg_10]
0x180017e82  mov     rbp, [rsp+48h+arg_18]
0x180017e87  add     rsp, 30h
0x180017e8b  pop     r14
0x180017e8d  pop     rdi
0x180017e8e  pop     rsi
0x180017e8f  retn
0x180017e90  xor     edx, edx
0x180017e92  mov     rcx, rdi
0x180017e95  call    ?ForceWakeLevel@DispatchItem@Dispatch@CoreUI@Microsoft@@QEAAXW4InternalPriority@234@@Z; Microsoft::CoreUI::Dispatch::DispatchItem::ForceWakeLevel(Microsoft::CoreUI::Dispatch::InternalPriority)
0x180017e9a  nop
0x180017e9b  jmp     short loc_180017E7D
0x180017e9d  mov     rcx, rsi
0x180017ea0  call    ?MulticastInvoke@?$DelegateImpl@VDispatchGroupHandler@CoreUI@Microsoft@@$0A@$$A6AXXZ$$A6AJPEAX@Z$0A@@CFlat@@AEBAXXZ; CFlat::DelegateImpl<Microsoft::CoreUI::DispatchGroupHandler,0,void (void),long (void *),0>::MulticastInvoke(void)
0x180017ea5  jmp     short loc_180017E58
0x180017ea7  cmp     [rbx+50h], r14
0x180017eab  jz      short loc_180017ED4
0x180017ead  cmp     [rbx+60h], r14b
0x180017eb1  jz      loc_180017F4E
0x180017eb7  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x180017ebd  mov     rax, [rdi+38h]
0x180017ec1  mov     rcx, [rax+20h]
0x180017ec5  cmp     [rcx+0B4h], r14d
0x180017ecc  jbe     loc_180017D98
0x180017ed2  jmp     short loc_180017E7D
0x180017ed4  cmp     [rbx+62h], r14b
0x180017ed8  jz      short loc_180017E6A
0x180017eda  jmp     short loc_180017EAD
0x180017edc  cmp     [rbx+50h], r14
0x180017ee0  jz      short loc_180017EF2
0x180017ee2  mov     r8b, 1; bool
0x180017ee5  mov     rdx, rbx; struct Microsoft::CoreUI::Dispatch::Timeout *
0x180017ee8  mov     rcx, rdi; this
0x180017eeb  call    ?Schedule@TimeoutManager@Dispatch@CoreUI@Microsoft@@QEAAXPEAVTimeout@234@_N@Z; Microsoft::CoreUI::Dispatch::TimeoutManager::Schedule(Microsoft::CoreUI::Dispatch::Timeout *,bool)
0x180017ef0  jmp     short loc_180017EF8
0x180017ef2  cmp     [rbx+62h], r14b
0x180017ef6  jnz     short loc_180017EE2
0x180017ef8  mov     rcx, [rdi+48h]; this
0x180017efc  call    ?get_FirstItem$FastReturn$@SkipList@Support@CoreUI@Microsoft@@QEAAPEAVObject@System@@XZ; Microsoft::CoreUI::Support::SkipList::get_FirstItem$FastReturn$(void)
0x180017f01  test    rax, rax
0x180017f04  jnz     loc_180017E2A
0x180017f0a  xor     edx, edx
0x180017f0c  mov     rcx, rdi
0x180017f0f  call    ?ForceWakeLevel@DispatchItem@Dispatch@CoreUI@Microsoft@@QEAAXW4InternalPriority@234@@Z; Microsoft::CoreUI::Dispatch::DispatchItem::ForceWakeLevel(Microsoft::CoreUI::Dispatch::InternalPriority)
0x180017f14  jmp     loc_180017E2A
0x180017f19  mov     rcx, [rcx+20h]; char16_t *
0x180017f1d  test    rcx, rcx
0x180017f20  jz      loc_180017DB0
0x180017f26  lea     rax, qword_1800D0CE0
0x180017f2d  cmp     [rcx+8], rax
0x180017f31  jnz     short loc_180017F48
0x180017f33  movsxd  rdx, dword ptr [rcx+18h]
0x180017f37  lea     eax, [rdx-1]
0x180017f3a  cmp     eax, edx
0x180017f3c  jb      loc_180017FE9
0x180017f42  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x180017f48  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x180017f4e  cmp     [rbx+61h], r14b
0x180017f52  jz      loc_180017FF3
0x180017f58  mov     edx, [rdi+50h]
0x180017f5b  lea     eax, [rdx+1]
0x180017f5e  mov     ecx, 1
0x180017f63  cmp     edx, 0FFFFFFFFh
0x180017f66  cmovnz  ecx, eax; char16_t *
0x180017f69  mov     [rdi+50h], ecx
0x180017f6c  mov     byte ptr [rbx+60h], 1
0x180017f70  mov     [rbx+40h], edx
0x180017f73  mov     rsi, [rbx+50h]
0x180017f77  mov     rax, [rbx+38h]
0x180017f7b  test    rax, rax
0x180017f7e  jz      short loc_180017FBE
0x180017f80  mov     qword ptr [rsp+48h+DueTime], rsi
0x180017f85  test    rsi, rsi
0x180017f88  js      short loc_180017FDD
0x180017f8a  neg     rsi
0x180017f8d  mov     qword ptr [rsp+48h+DueTime], rsi
0x180017f92  mov     [rsp+48h+fResume], r14d; fResume
0x180017f97  mov     [rsp+48h+lpArgToCompletionRoutine], r14; lpArgToCompletionRoutine
0x180017f9c  xor     r9d, r9d; pfnCompletionRoutine
0x180017f9f  xor     r8d, r8d; lPeriod
0x180017fa2  lea     rdx, [rsp+48h+DueTime]; lpDueTime
0x180017fa7  mov     rcx, rax; hTimer
0x180017faa  call    cs:__imp_SetWaitableTimer
0x180017fb0  test    eax, eax
0x180017fb2  jnz     loc_180017E6A
0x180017fb8  call    ?ForWin32@FailFast@Cn@@SAXXZ; Cn::FailFast::ForWin32(void)
0x180017fbe  xor     edx, edx; lpTimerName
0x180017fc0  xor     ecx, ecx; lpTimerAttributes
0x180017fc2  mov     r9d, 1F0003h; dwDesiredAccess
0x180017fc8  lea     r8d, [rdx+1]; dwFlags
0x180017fcc  call    cs:__imp_CreateWaitableTimerExW
0x180017fd2  test    rax, rax
0x180017fd5  jnz     short loc_180017FE3
0x180017fd7  call    ?ForWin32@FailFast@Cn@@SAXXZ; Cn::FailFast::ForWin32(void)
0x180017fdd  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x180017fe3  mov     [rbx+38h], rax
0x180017fe7  jmp     short loc_180017F80
0x180017fe9  mov     rax, [rcx+rdx*8+18h]
0x180017fee  jmp     loc_180017DB3
0x180017ff3  mov     rcx, rbx; this
0x180017ff6  call    ?UpdateAbsoluteDueTimeOnRepeat@Timeout@Dispatch@CoreUI@Microsoft@@QEAAXXZ; Microsoft::CoreUI::Dispatch::Timeout::UpdateAbsoluteDueTimeOnRepeat(void)
0x180017ffb  mov     edx, [rdi+50h]
0x180017ffe  lea     eax, [rdx+1]
0x180018001  mov     ecx, 1
0x180018006  cmp     edx, 0FFFFFFFFh
0x180018009  cmovnz  ecx, eax; this
0x18001800c  mov     [rdi+50h], ecx
0x18001800f  mov     byte ptr [rbx+60h], 1
0x180018013  mov     [rbx+40h], edx
0x180018016  mov     rdx, rbx; struct Microsoft::CoreUI::Dispatch::Timeout *
0x180018019  call    ?EnableAbsoluteTimer@TimeoutManager@Dispatch@CoreUI@Microsoft@@AEAAXPEAVTimeout@234@@Z; Microsoft::CoreUI::Dispatch::TimeoutManager::EnableAbsoluteTimer(Microsoft::CoreUI::Dispatch::Timeout *)
0x18001801e  jmp     loc_180017E6A
```
