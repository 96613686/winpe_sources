# Microsoft::CoreUI::Dispatch::Win32EventLoopBridge::Callback_Run(Microsoft::CoreUI::Dispatch::RunMode)

- ea: `0x180013ca0`
- end: `0x180014130`
- name: `?Callback_Run@Win32EventLoopBridge@Dispatch@CoreUI@Microsoft@@UEAAXW4RunMode@234@@Z`
- size: `1168`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000b130`
- `0x18000cb50`
- `0x18000ec10`
- `0x180012900`
- `0x180013ca0`
- `0x180015ab0`
- `0x18002e654`
- `0x18004705c`
- `0x18005bbdc`
- `0x18005bf00`
- `0x18005d9a0`
- `0x18005da8c`
- `0x18005de28`
- `0x180066260`
- `0x180085348`
- `0x18008a584`
- `0x18008ae1c`
- `0x18009bb88`
- `0x1800a6298`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001408b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001408b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013de5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013de5`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!IsGUIThread` at `0x180013e8a`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!IsGUIThread` at `0x180013e8a`

## string_xrefs

- `0x180014084`: `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall Microsoft::CoreUI::Dispatch::Win32EventLoopBridge::Callback_Run(__int64 a1, unsigned int a2)
{
  __int64 *v4; // rax
  __int64 v5; // rdx
  __int64 v6; // r13
  char v7; // r12
  System::Object *v8; // rbx
  unsigned int v9; // r15d
  System::Object *v10; // rbx
  int v11; // esi
  System::Object *v12; // rbx
  bool v13; // al
  DWORD CurrentThreadId; // eax
  __int64 v15; // rbx
  __int64 v16; // rcx
  __int64 result; // rax
  __int64 v18; // rbx
  System::Object *v19; // rax
  System::Object *v20; // rcx
  Microsoft::CoreUI::Dispatch::WaitController *v21; // rbx
  System::Object *v22; // rbx
  __int64 v23; // rcx
  System::Object *v24; // rbx
  System::Object *v25; // rbx
  __int64 v26; // rdx
  _BYTE *v27; // [rsp+20h] [rbp-88h]
  unsigned __int8 *v28; // [rsp+28h] [rbp-80h]
  System::Object *v29; // [rsp+30h] [rbp-78h]
  __int64 v30; // [rsp+38h] [rbp-70h] BYREF
  char v31; // [rsp+50h] [rbp-58h]
  __int64 v32; // [rsp+58h] [rbp-50h]
  _BYTE *v33; // [rsp+60h] [rbp-48h]
  _BYTE *v34; // [rsp+68h] [rbp-40h]
  char v35; // [rsp+B0h] [rbp+8h] BYREF
  char v36; // [rsp+C0h] [rbp+18h] BYREF
  System::Object *v37; // [rsp+C8h] [rbp+20h] BYREF

  v36 = *(_BYTE *)(a1 + 70);
  v35 = *(_BYTE *)(a1 + 71);
  *(_WORD *)(a1 + 70) = 0;
  v4 = (__int64 *)lambda_f7e478493cd4c7e6a5c3d3065f952319_::_lambda_f7e478493cd4c7e6a5c3d3065f952319_(
                    &v30,
                    a1,
                    &v36,
                    &v35);
  try
  {
    v31 = 0;
    v6 = *v4;
    v32 = *v4;
    v27 = (_BYTE *)v4[1];
    v33 = v27;
    v28 = (unsigned __int8 *)v4[2];
    v34 = v28;
    if ( *(_BYTE *)(*(_QWORD *)(v5 + 32) + 176LL) || a2 == 4 )
    {
      v7 = 0;
    }
    else
    {
      if ( *(_QWORD *)(a1 + 56) )
        goto LABEL_73;
      v7 = 1;
    }
    v8 = *(System::Object **)(a1 + 40);
    v29 = v8;
    if ( v8 )
      ++*((_DWORD *)v8 + 4);
    v9 = *((_DWORD *)v8 + 16);
    if ( a2 != 4 )
      Microsoft::CoreUI::Dispatch::DispatchItem::Activate(v8, 2);
    while ( 1 )
    {
      if ( v8 )
        System::Object::ReleaseNotFrozen$(v8);
      v10 = *(System::Object **)(a1 + 32);
      v37 = v10;
      if ( v10 )
        ++*((_DWORD *)v10 + 4);
      v11 = Microsoft::CoreUI::Dispatch::EventLoop::Callback_RunCoreLoop(v10, a2);
      if ( v10 )
        System::Object::ReleaseNotFrozen$(v10);
      v12 = *(System::Object **)(a1 + 40);
      v37 = v12;
      if ( v12 )
        ++*((_DWORD *)v12 + 4);
      if ( *((_DWORD *)v12 + 16) < (signed int)v9 )
        Microsoft::CoreUI::Dispatch::DispatchItem::ForceWakeLevel(v12, v9);
      if ( v12 )
        System::Object::ReleaseNotFrozen$(v12);
      if ( v11 != 1 )
        break;
      if ( *(_QWORD *)(a1 + 56) )
        goto LABEL_23;
      v22 = *(System::Object **)(*(_QWORD *)(a1 + 40) + 80LL);
      v37 = v22;
      if ( v22 )
        ++*((_DWORD *)v22 + 4);
      Microsoft::CoreUI::Dispatch::WaitCollection::UnregisterWait(v22, *(_QWORD *)(*(_QWORD *)(a1 + 32) + 144LL), 0);
      if ( v22 )
        System::Object::ReleaseNotFrozen$(v22);
      while ( 1 )
      {
        v23 = *(_QWORD *)(a1 + 32);
        if ( !*(_DWORD *)(v23 + 180) )
          break;
        Microsoft::CoreUI::Support::EventWaiter::DoWait(*(_QWORD *)(v23 + 144));
      }
      v8 = *(System::Object **)(*(_QWORD *)(a1 + 40) + 80LL);
      v37 = v8;
      if ( v8 )
        ++*((_DWORD *)v8 + 4);
      Microsoft::CoreUI::Dispatch::WaitCollection::RegisterWait(v8, *(_QWORD *)(*(_QWORD *)(a1 + 32) + 144LL), 0, 0);
    }
    if ( (unsigned int)(v11 - 3) <= 1 )
      v7 = 0;
LABEL_23:
    v13 = a2 == 1
       && !Microsoft::CoreUI::Dispatch::EventLoop::get_IsStopping(*(Microsoft::CoreUI::Dispatch::EventLoop **)(a1 + 32))
       && v7;
    *(_BYTE *)(a1 + 69) = v13;
    CurrentThreadId = GetCurrentThreadId();
    v15 = *(_QWORD *)(a1 + 32);
    v16 = *(_QWORD *)(v15 + 48);
    if ( CurrentThreadId != *(_DWORD *)(v16 + 176) )
      CFlat::Abandonment::Fail((const char16_t *)v16);
    if ( !*(_QWORD *)(a1 + 56)
      && !*(_BYTE *)(v15 + 176)
      && *(_DWORD *)(v15 + 68) != 4
      && !Microsoft::CoreUI::Dispatch::UserAdapter::s_disabled )
    {
      if ( v15 )
      {
        ++*(_DWORD *)(v15 + 16);
        Microsoft::CoreUI::Dispatch::UserAdapter::EnsureSharedTebInitialized((struct Microsoft::CoreUI::Dispatch::EventLoop *)v15);
        System::Object::ReleaseNotFrozen$((System::Object *)v15);
      }
      else
      {
        Microsoft::CoreUI::Dispatch::UserAdapter::EnsureSharedTebInitialized(0);
      }
      if ( !Microsoft::CoreUI::Dispatch::UserAdapter::s_userLoaded )
      {
        if ( !GetModuleHandleW(L"ext-ms-win-rtcore-ntuser-window-ext-l1-1-0.dll") )
        {
          Microsoft::CoreUI::Dispatch::UserAdapter::s_userLoaded = 0;
          goto LABEL_28;
        }
        Microsoft::CoreUI::Dispatch::UserAdapter::s_userLoaded = 1;
      }
      if ( IsGUIThread(0) )
      {
        v18 = *(_QWORD *)(a1 + 32);
        if ( *(_DWORD *)(v18 + 72) )
        {
          v24 = *(System::Object **)(v18 + 56);
          v29 = v24;
          if ( v24 )
            ++*((_DWORD *)v24 + 4);
          if ( !*((_DWORD *)v24 + 26) )
            Microsoft::CoreUI::Dispatch::Dispatcher::AbandonLoop(v24, 2);
          System::Object::ReleaseNotFrozen$(v24);
        }
        else
        {
          v37 = 0;
          if ( (unsigned __int8)Microsoft::CoreUI::Dispatch::UserAdapter::CreateForThread(a1, 0, &v37) )
          {
            v19 = v37;
            if ( v37 )
              ++*((_DWORD *)v37 + 4);
            v20 = *(System::Object **)(a1 + 56);
            *(_QWORD *)(a1 + 56) = v19;
            if ( v20 )
              System::Object::ReleaseNotFrozen$(v20);
            v21 = *(Microsoft::CoreUI::Dispatch::WaitController **)(a1 + 40);
            v29 = v21;
            if ( v21 )
              ++*((_DWORD *)v21 + 4);
            Microsoft::CoreUI::Dispatch::WaitController::OnUserIntegrationEnabled(v21);
            if ( v21 )
              System::Object::ReleaseNotFrozen$(v21);
            if ( *(_BYTE *)(a1 + 72) )
            {
              *(_BYTE *)(a1 + 72) = 0;
              Microsoft::CoreUI::Dispatch::Win32EventLoopBridge::ExitAtQuitPriorityWithoutUser((Microsoft::CoreUI::Dispatch::Win32EventLoopBridge *)a1);
            }
          }
          if ( v37 )
            System::Object::ReleaseNotFrozen$(v37);
        }
      }
    }
LABEL_28:
    *(_BYTE *)(a1 + 69) = 0;
    if ( !v7 )
    {
LABEL_29:
      if ( a2 == 1
        && (*(_BYTE *)(*(_QWORD *)(a1 + 32) + 84LL) & 4) != 0
        && (!*(_BYTE *)(a1 + 70) || *(_BYTE *)(a1 + 71)) )
      {
        Microsoft::CoreUI::Dispatch::Win32EventLoopBridge::ExitAtQuitPriorityWithoutUser((Microsoft::CoreUI::Dispatch::Win32EventLoopBridge *)a1);
      }
      *(_BYTE *)(v6 + 70) = *v27;
      result = *v28;
      *(_BYTE *)(v6 + 71) = result;
      return result;
    }
LABEL_73:
    v25 = *(System::Object **)(a1 + 56);
    if ( v25 )
    {
      v37 = *(System::Object **)(a1 + 56);
      ++*((_DWORD *)v25 + 4);
      Microsoft::CoreUI::Dispatch::UserAdapter::Callback_HostModeRun(v25, a2);
      System::Object::ReleaseNotFrozen$(v25);
    }
    goto LABEL_29;
  }
  catch ( ... )
  {
    v31 = 1;
    v26 = v32;
    *(_BYTE *)(v32 + 70) = *v33;
    *(_BYTE *)(v26 + 71) = *v34;
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x180013ca0  mov     r11, rsp
0x180013ca3  push    rbx
0x180013ca4  push    rsi
0x180013ca5  push    rdi
0x180013ca6  push    r12
0x180013ca8  push    r13
0x180013caa  push    r14
0x180013cac  push    r15
0x180013cae  sub     rsp, 70h
0x180013cb2  mov     r14d, edx
0x180013cb5  mov     rdi, rcx
0x180013cb8  movzx   eax, byte ptr [rcx+46h]
0x180013cbc  mov     [r11+18h], al
0x180013cc0  movzx   eax, byte ptr [rcx+47h]
0x180013cc4  mov     [r11+8], al
0x180013cc8  mov     word ptr [rcx+46h], 0
0x180013cce  lea     r9, [r11+8]
0x180013cd2  lea     r8, [r11+18h]
0x180013cd6  mov     rdx, rcx
0x180013cd9  lea     rcx, [r11-70h]
0x180013cdd  call    _lambda_f7e478493cd4c7e6a5c3d3065f952319____lambda_f7e478493cd4c7e6a5c3d3065f952319_
0x180013ce2  mov     [rsp+0A8h+var_58], 0
0x180013ce7  mov     r13, [rax]
0x180013cea  mov     [rsp+0A8h+var_50], r13
0x180013cef  mov     rcx, [rax+8]
0x180013cf3  mov     [rsp+0A8h+var_88], rcx
0x180013cf8  mov     [rsp+0A8h+var_48], rcx
0x180013cfd  mov     rax, [rax+10h]
0x180013d01  mov     [rsp+0A8h+var_80], rax
0x180013d06  mov     [rsp+0A8h+var_40], rax
0x180013d0b  mov     rax, [rdx+20h]
0x180013d0f  cmp     byte ptr [rax+0B0h], 0
0x180013d16  jz      loc_18001403E
0x180013d1c  xor     r12b, r12b
0x180013d1f  xor     edx, edx
0x180013d21  cmp     r14d, 4
0x180013d25  setz    dl
0x180013d28  mov     rbx, [rdi+28h]
0x180013d2c  mov     [rsp+0A8h+var_78], rbx
0x180013d31  test    rbx, rbx
0x180013d34  jz      short loc_180013D39
0x180013d36  inc     dword ptr [rbx+10h]
0x180013d39  test    edx, edx
0x180013d3b  jnz     loc_180013F36
0x180013d41  mov     r15d, [rbx+40h]
0x180013d45  mov     edx, 2
0x180013d4a  mov     rcx, rbx
0x180013d4d  call    ?Activate@DispatchItem@Dispatch@CoreUI@Microsoft@@QEAAXW4InternalPriority@234@@Z; Microsoft::CoreUI::Dispatch::DispatchItem::Activate(Microsoft::CoreUI::Dispatch::InternalPriority)
0x180013d52  nop
0x180013d53  test    rbx, rbx
0x180013d56  jz      short loc_180013D60
0x180013d58  mov     rcx, rbx; this
0x180013d5b  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180013d60  mov     rbx, [rdi+20h]
0x180013d64  mov     [rsp+0A8h+arg_18], rbx
0x180013d6c  test    rbx, rbx
0x180013d6f  jz      short loc_180013D74
0x180013d71  inc     dword ptr [rbx+10h]
0x180013d74  mov     edx, r14d
0x180013d77  mov     rcx, rbx
0x180013d7a  call    ?Callback_RunCoreLoop@EventLoop@Dispatch@CoreUI@Microsoft@@QEAA?AW4Dispatcher$LoopExitState@234@W4RunMode@234@@Z; Microsoft::CoreUI::Dispatch::EventLoop::Callback_RunCoreLoop(Microsoft::CoreUI::Dispatch::RunMode)
0x180013d7f  mov     esi, eax
0x180013d81  test    rbx, rbx
0x180013d84  jz      short loc_180013D8E
0x180013d86  mov     rcx, rbx; this
0x180013d89  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180013d8e  mov     rbx, [rdi+28h]
0x180013d92  mov     [rsp+0A8h+arg_18], rbx
0x180013d9a  test    rbx, rbx
0x180013d9d  jz      short loc_180013DA2
0x180013d9f  inc     dword ptr [rbx+10h]
0x180013da2  cmp     [rbx+40h], r15d
0x180013da6  jge     short loc_180013DB4
0x180013da8  mov     edx, r15d
0x180013dab  mov     rcx, rbx
0x180013dae  call    ?ForceWakeLevel@DispatchItem@Dispatch@CoreUI@Microsoft@@QEAAXW4InternalPriority@234@@Z; Microsoft::CoreUI::Dispatch::DispatchItem::ForceWakeLevel(Microsoft::CoreUI::Dispatch::InternalPriority)
0x180013db3  nop
0x180013db4  test    rbx, rbx
0x180013db7  jz      short loc_180013DC1
0x180013db9  mov     rcx, rbx; this
0x180013dbc  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180013dc1  cmp     esi, 1
0x180013dc4  jz      loc_180013F48
0x180013dca  lea     eax, [rsi-3]
0x180013dcd  cmp     eax, 1
0x180013dd0  jbe     loc_1800140FF
0x180013dd6  cmp     r14d, 1
0x180013dda  jz      loc_1800140A2
0x180013de0  xor     al, al
0x180013de2  mov     [rdi+45h], al
0x180013de5  call    cs:__imp_GetCurrentThreadId
0x180013deb  mov     rbx, [rdi+20h]
0x180013def  mov     rcx, [rbx+30h]; char16_t *
0x180013df3  cmp     eax, [rcx+0B0h]
0x180013df9  jz      short loc_180013E01
0x180013dfb  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x180013e01  cmp     qword ptr [rdi+38h], 0
0x180013e06  jz      short loc_180013E47
0x180013e08  mov     byte ptr [rdi+45h], 0
0x180013e0c  test    r12b, r12b
0x180013e0f  jnz     loc_180014053
0x180013e15  cmp     r14d, 1
0x180013e19  jz      loc_180014013
0x180013e1f  mov     rax, [rsp+0A8h+var_88]
0x180013e24  movzx   eax, byte ptr [rax]
0x180013e27  mov     [r13+46h], al
0x180013e2b  mov     rax, [rsp+0A8h+var_80]
0x180013e30  movzx   eax, byte ptr [rax]
0x180013e33  mov     [r13+47h], al
0x180013e37  add     rsp, 70h
0x180013e3b  pop     r15
0x180013e3d  pop     r14
0x180013e3f  pop     r13
0x180013e41  pop     r12
0x180013e43  pop     rdi
0x180013e44  pop     rsi
0x180013e45  pop     rbx
0x180013e46  retn
0x180013e47  cmp     byte ptr [rbx+0B0h], 0
0x180013e4e  jnz     short loc_180013E08
0x180013e50  cmp     dword ptr [rbx+44h], 4
0x180013e54  jz      short loc_180013E08
0x180013e56  cmp     cs:?s_disabled@UserAdapter@Dispatch@CoreUI@Microsoft@@0_NA, 0; bool Microsoft::CoreUI::Dispatch::UserAdapter::s_disabled
0x180013e5d  jnz     short loc_180013E08
0x180013e5f  mov     rcx, rbx; struct Microsoft::CoreUI::Dispatch::EventLoop *
0x180013e62  test    rbx, rbx
0x180013e65  jz      loc_180014107
0x180013e6b  inc     dword ptr [rbx+10h]
0x180013e6e  call    ?EnsureSharedTebInitialized@UserAdapter@Dispatch@CoreUI@Microsoft@@SAXPEAVEventLoop@234@@Z; Microsoft::CoreUI::Dispatch::UserAdapter::EnsureSharedTebInitialized(Microsoft::CoreUI::Dispatch::EventLoop *)
0x180013e73  mov     rcx, rbx; this
0x180013e76  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180013e7b  cmp     cs:?s_userLoaded@UserAdapter@Dispatch@CoreUI@Microsoft@@2_NA, 0; bool Microsoft::CoreUI::Dispatch::UserAdapter::s_userLoaded
0x180013e82  jz      loc_180014084
0x180013e88  xor     ecx, ecx; bConvert
0x180013e8a  call    cs:__imp_IsGUIThread
0x180013e90  test    eax, eax
0x180013e92  jz      loc_180013E08
0x180013e98  mov     rbx, [rdi+20h]
0x180013e9c  cmp     dword ptr [rbx+48h], 0
0x180013ea0  jnz     loc_180013FE1
0x180013ea6  mov     [rsp+0A8h+arg_18], 0
0x180013eb2  lea     r8, [rsp+0A8h+arg_18]
0x180013eba  xor     edx, edx
0x180013ebc  mov     rcx, rdi
0x180013ebf  call    ?CreateForThread@UserAdapter@Dispatch@CoreUI@Microsoft@@SA_NPEAVWin32EventLoopBridge@234@_NU?$Ref@V?$SmartPtr@VUserAdapter@Dispatch@CoreUI@Microsoft@@@CFlat@@@CFlat@@@Z; Microsoft::CoreUI::Dispatch::UserAdapter::CreateForThread(Microsoft::CoreUI::Dispatch::Win32EventLoopBridge *,bool,CFlat::Ref<CFlat::SmartPtr<Microsoft::CoreUI::Dispatch::UserAdapter>>)
0x180013ec4  test    al, al
0x180013ec6  jz      short loc_180013F1B
0x180013ec8  mov     rax, [rsp+0A8h+arg_18]
0x180013ed0  test    rax, rax
0x180013ed3  jz      short loc_180013ED8
0x180013ed5  inc     dword ptr [rax+10h]
0x180013ed8  mov     rcx, [rdi+38h]; this
0x180013edc  mov     [rdi+38h], rax
0x180013ee0  test    rcx, rcx
0x180013ee3  jz      short loc_180013EEA
0x180013ee5  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180013eea  mov     rbx, [rdi+28h]
0x180013eee  mov     [rsp+0A8h+var_78], rbx
0x180013ef3  test    rbx, rbx
0x180013ef6  jz      short loc_180013EFB
0x180013ef8  inc     dword ptr [rbx+10h]
0x180013efb  mov     rcx, rbx; this
0x180013efe  call    ?OnUserIntegrationEnabled@WaitController@Dispatch@CoreUI@Microsoft@@QEAAXXZ; Microsoft::CoreUI::Dispatch::WaitController::OnUserIntegrationEnabled(void)
0x180013f03  nop
0x180013f04  test    rbx, rbx
0x180013f07  jz      short loc_180013F11
0x180013f09  mov     rcx, rbx; this
0x180013f0c  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180013f11  cmp     byte ptr [rdi+48h], 0
0x180013f15  jnz     loc_18001411D
0x180013f1b  mov     rcx, [rsp+0A8h+arg_18]; this
0x180013f23  test    rcx, rcx
0x180013f26  jz      loc_180013E08
0x180013f2c  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180013f31  jmp     loc_180013E08
0x180013f36  cmp     edx, 1
0x180013f39  jnz     loc_1800140C3
0x180013f3f  mov     r15d, [rbx+40h]
0x180013f43  jmp     loc_180013D53
0x180013f48  cmp     qword ptr [rdi+38h], 0
0x180013f4d  jnz     loc_180013DD6
0x180013f53  mov     rax, [rdi+28h]
0x180013f57  mov     rbx, [rax+50h]
0x180013f5b  mov     [rsp+0A8h+arg_18], rbx
0x180013f63  test    rbx, rbx
0x180013f66  jz      short loc_180013F6B
0x180013f68  inc     dword ptr [rbx+10h]
0x180013f6b  mov     rdx, [rdi+20h]
0x180013f6f  xor     r8d, r8d
0x180013f72  mov     rdx, [rdx+90h]
0x180013f79  mov     rcx, rbx
0x180013f7c  call    ?UnregisterWait@WaitCollection@Dispatch@CoreUI@Microsoft@@QEAAXUWin32Handle@Support@34@_N@Z; Microsoft::CoreUI::Dispatch::WaitCollection::UnregisterWait(Microsoft::CoreUI::Support::Win32Handle,bool)
0x180013f81  nop
0x180013f82  test    rbx, rbx
0x180013f85  jz      short loc_180013F8F
0x180013f87  mov     rcx, rbx; this
0x180013f8a  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180013f8f  mov     rcx, [rdi+20h]
0x180013f93  cmp     dword ptr [rcx+0B4h], 0
0x180013f9a  ja      short loc_180013FD3
0x180013f9c  mov     rax, [rdi+28h]
0x180013fa0  mov     rbx, [rax+50h]
0x180013fa4  mov     [rsp+0A8h+arg_18], rbx
0x180013fac  test    rbx, rbx
0x180013faf  jz      short loc_180013FB4
0x180013fb1  inc     dword ptr [rbx+10h]
0x180013fb4  mov     rdx, [rdi+20h]
0x180013fb8  xor     r9d, r9d
0x180013fbb  xor     r8d, r8d
0x180013fbe  mov     rdx, [rdx+90h]
0x180013fc5  mov     rcx, rbx
0x180013fc8  call    ?RegisterWait@WaitCollection@Dispatch@CoreUI@Microsoft@@QEAAXUWin32Handle@Support@34@PEAVWaitCallback@234@_N@Z; Microsoft::CoreUI::Dispatch::WaitCollection::RegisterWait(Microsoft::CoreUI::Support::Win32Handle,Microsoft::CoreUI::Dispatch::WaitCallback *,bool)
0x180013fcd  nop
0x180013fce  jmp     loc_180013D53
0x180013fd3  mov     rcx, [rcx+90h]
0x180013fda  call    ?DoWait@EventWaiter@Support@CoreUI@Microsoft@@SAXUWin32Handle@234@@Z; Microsoft::CoreUI::Support::EventWaiter::DoWait(Microsoft::CoreUI::Support::Win32Handle)
0x180013fdf  jmp     short loc_180013F8F
0x180013fe1  mov     rbx, [rbx+38h]
0x180013fe5  mov     [rsp+0A8h+var_78], rbx
0x180013fea  test    rbx, rbx
0x180013fed  jz      short loc_180013FF2
0x180013fef  inc     dword ptr [rbx+10h]
0x180013ff2  cmp     dword ptr [rbx+68h], 0
0x180013ff6  jnz     short loc_180014006
0x180013ff8  mov     edx, 2
0x180013ffd  mov     rcx, rbx
0x180014000  call    ?AbandonLoop@Dispatcher@Dispatch@CoreUI@Microsoft@@QEAAXW4Dispatcher$LoopExitState@234@@Z; Microsoft::CoreUI::Dispatch::Dispatcher::AbandonLoop(Microsoft::CoreUI::Dispatch::Dispatcher$LoopExitState)
0x180014005  nop
0x180014006  mov     rcx, rbx; this
0x180014009  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18001400e  jmp     loc_180013E08
0x180014013  mov     rax, [rdi+20h]
0x180014017  test    byte ptr [rax+54h], 4
0x18001401b  jz      loc_180013E1F
0x180014021  cmp     byte ptr [rdi+46h], 0
0x180014025  jz      short loc_180014031
0x180014027  cmp     byte ptr [rdi+47h], 0
0x18001402b  jz      loc_180013E1F
0x180014031  mov     rcx, rdi; this
0x180014034  call    ?ExitAtQuitPriorityWithoutUser@Win32EventLoopBridge@Dispatch@CoreUI@Microsoft@@AEAAXXZ; Microsoft::CoreUI::Dispatch::Win32EventLoopBridge::ExitAtQuitPriorityWithoutUser(void)
0x180014039  jmp     loc_180013E1F
0x18001403e  cmp     r14d, 4
0x180014042  jz      loc_180013D1C
0x180014048  cmp     qword ptr [rdi+38h], 0
0x18001404d  jz      loc_1800140F7
0x180014053  mov     rbx, [rdi+38h]
0x180014057  test    rbx, rbx
0x18001405a  jz      loc_180013E15
0x180014060  mov     [rsp+0A8h+arg_18], rbx
0x180014068  inc     dword ptr [rbx+10h]
0x18001406b  mov     edx, r14d
0x18001406e  mov     rcx, rbx
0x180014071  call    ?Callback_HostModeRun@UserAdapter@Dispatch@CoreUI@Microsoft@@QEAAXW4RunMode@234@@Z; Microsoft::CoreUI::Dispatch::UserAdapter::Callback_HostModeRun(Microsoft::CoreUI::Dispatch::RunMode)
0x180014076  nop
0x180014077  mov     rcx, rbx; this
0x18001407a  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18001407f  jmp     loc_180013E15
0x180014084  lea     rcx, ModuleName; "ext-ms-win-rtcore-ntuser-window-ext-l1-"...
0x18001408b  call    cs:__imp_GetModuleHandleW
0x180014091  test    rax, rax
0x180014094  jz      short loc_180014111
0x180014096  mov     cs:?s_userLoaded@UserAdapter@Dispatch@CoreUI@Microsoft@@2_NA, 1; bool Microsoft::CoreUI::Dispatch::UserAdapter::s_userLoaded
0x18001409d  jmp     loc_180013E88
0x1800140a2  mov     rcx, [rdi+20h]; this
0x1800140a6  call    ?get_IsStopping@EventLoop@Dispatch@CoreUI@Microsoft@@QEAA_NXZ; Microsoft::CoreUI::Dispatch::EventLoop::get_IsStopping(void)
0x1800140ab  test    al, al
0x1800140ad  jnz     loc_180013DE0
0x1800140b3  test    r12b, r12b
0x1800140b6  jz      loc_180013DE0
0x1800140bc  mov     al, 1
0x1800140be  jmp     loc_180013DE2
0x1800140c3  lea     r8, ?TypeId$@RunnablePriorityMask$StaticType$@Dispatch@CoreUI@Microsoft@@2U?$EnumTypeIdField@W4RunnablePriorityMask@Dispatch@CoreUI@Microsoft@@@CFlat@@B; CFlat::EnumTypeIdField<Microsoft::CoreUI::Dispatch::RunnablePriorityMask> const Microsoft::CoreUI::Dispatch::RunnablePriorityMask$StaticType$::TypeId$
0x1800140ca  lea     rcx, [rsp+0A8h+arg_18]
0x1800140d2  call    ??$EnumToString@H@Generics@CFlat@@SA?AV?$SmartPtr@VString@System@@@1@HPEBUEnumTypeId@1@@Z; CFlat::Generics::EnumToString<int>(int,CFlat::EnumTypeId const *)
0x1800140d7  nop
0x1800140d8  mov     r8, [rsp+0A8h+arg_18]
0x1800140e0  lea     rdx, off_1800D7460
0x1800140e7  lea     rcx, [rsp+0A8h+var_80]
0x1800140ec  call    ?Concat@String@System@@SA?AV?$SmartPtr@VString@System@@@CFlat@@PEAV12@0@Z; System::String::Concat(System::String *,System::String *)
0x1800140f1  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x1800140f7  mov     r12b, 1
0x1800140fa  jmp     loc_180013D1F
0x1800140ff  xor     r12b, r12b
0x180014102  jmp     loc_180013DD6
0x180014107  call    ?EnsureSharedTebInitialized@UserAdapter@Dispatch@CoreUI@Microsoft@@SAXPEAVEventLoop@234@@Z; Microsoft::CoreUI::Dispatch::UserAdapter::EnsureSharedTebInitialized(Microsoft::CoreUI::Dispatch::EventLoop *)
0x18001410c  jmp     loc_180013E7B
0x180014111  mov     cs:?s_userLoaded@UserAdapter@Dispatch@CoreUI@Microsoft@@2_NA, 0; bool Microsoft::CoreUI::Dispatch::UserAdapter::s_userLoaded
0x180014118  jmp     loc_180013E08
0x18001411d  mov     byte ptr [rdi+48h], 0
0x180014121  mov     rcx, rdi; this
0x180014124  call    ?ExitAtQuitPriorityWithoutUser@Win32EventLoopBridge@Dispatch@CoreUI@Microsoft@@AEAAXXZ; Microsoft::CoreUI::Dispatch::Win32EventLoopBridge::ExitAtQuitPriorityWithoutUser(void)
0x180014129  jmp     loc_180013F1B
```
