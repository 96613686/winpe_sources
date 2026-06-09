# Microsoft::CoreUI::Dispatch::Win32EventLoopBridge::CheckForUserIntegration(bool)

- ea: `0x18005cd50`
- end: `0x18005ced4`
- name: `?CheckForUserIntegration@Win32EventLoopBridge@Dispatch@CoreUI@Microsoft@@UEAAX_N@Z`
- size: `388`
- prototype: `void __fastcall(Microsoft::CoreUI::Dispatch::Win32EventLoopBridge *__hidden this, bool)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18005cc10`

## callees

- `0x18000ec10`
- `0x18005bbdc`
- `0x18005bf00`
- `0x18005cd50`
- `0x18005d9a0`
- `0x18005de28`
- `0x18008ae1c`
- `0x18009bb88`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005cea7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005cea7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005cd65`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005cd65`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!IsGUIThread` at `0x18005cddd`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!IsGUIThread` at `0x18005cddd`

## string_xrefs

- `0x18005cea0`: `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Microsoft::CoreUI::Dispatch::Win32EventLoopBridge::CheckForUserIntegration(
        Microsoft::CoreUI::Dispatch::Win32EventLoopBridge *this,
        char a2)
{
  DWORD CurrentThreadId; // eax
  const char16_t *v5; // rcx
  __int64 v6; // rbx
  __int64 v7; // rdx
  __int64 v8; // rbx
  System::Object *v9; // rax
  System::Object *v10; // rcx
  Microsoft::CoreUI::Dispatch::WaitController *v11; // rbx
  System::Object *v12; // rcx
  Microsoft::CoreUI::Dispatch::WaitController *v13; // rbx
  HMODULE ModuleHandleW; // rax
  System::Object *v15; // [rsp+30h] [rbp+8h] BYREF
  Microsoft::CoreUI::Dispatch::WaitController *v16; // [rsp+40h] [rbp+18h]

  CurrentThreadId = GetCurrentThreadId();
  v6 = *((_QWORD *)this + 4);
  if ( CurrentThreadId != *(_DWORD *)(*(_QWORD *)(v6 + 48) + 176LL) )
    CFlat::Abandonment::Fail(v5);
  if ( !*((_QWORD *)this + 7)
    && !*(_BYTE *)(v6 + 176)
    && *(_DWORD *)(v6 + 68) != 4
    && !Microsoft::CoreUI::Dispatch::UserAdapter::s_disabled )
  {
    if ( v6 )
      ++*(_DWORD *)(v6 + 16);
    Microsoft::CoreUI::Dispatch::UserAdapter::EnsureSharedTebInitialized((struct Microsoft::CoreUI::Dispatch::EventLoop *)v6);
    if ( v6 )
      System::Object::ReleaseNotFrozen$((System::Object *)v6);
    if ( Microsoft::CoreUI::Dispatch::UserAdapter::s_userLoaded
      || (ModuleHandleW = GetModuleHandleW(L"ext-ms-win-rtcore-ntuser-window-ext-l1-1-0.dll"),
          Microsoft::CoreUI::Dispatch::UserAdapter::s_userLoaded = ModuleHandleW != 0,
          ModuleHandleW) )
    {
      if ( IsGUIThread(0) )
      {
        v8 = *((_QWORD *)this + 4);
        if ( *(_DWORD *)(v8 + 72) )
        {
          v13 = *(Microsoft::CoreUI::Dispatch::WaitController **)(v8 + 56);
          v16 = v13;
          if ( v13 )
            ++*((_DWORD *)v13 + 4);
          if ( !*((_DWORD *)v13 + 26) )
            Microsoft::CoreUI::Dispatch::Dispatcher::AbandonLoop(v13, 2);
          v12 = v13;
          goto LABEL_27;
        }
        v15 = 0;
        LOBYTE(v7) = a2;
        if ( (unsigned __int8)Microsoft::CoreUI::Dispatch::UserAdapter::CreateForThread(this, v7, &v15) )
        {
          v9 = v15;
          if ( v15 )
            ++*((_DWORD *)v15 + 4);
          v10 = (System::Object *)*((_QWORD *)this + 7);
          *((_QWORD *)this + 7) = v9;
          if ( v10 )
            System::Object::ReleaseNotFrozen$(v10);
          v11 = (Microsoft::CoreUI::Dispatch::WaitController *)*((_QWORD *)this + 5);
          v16 = v11;
          if ( v11 )
            ++*((_DWORD *)v11 + 4);
          Microsoft::CoreUI::Dispatch::WaitController::OnUserIntegrationEnabled(v11);
          if ( v11 )
            System::Object::ReleaseNotFrozen$(v11);
          if ( *((_BYTE *)this + 72) )
          {
            *((_BYTE *)this + 72) = 0;
            Microsoft::CoreUI::Dispatch::Win32EventLoopBridge::ExitAtQuitPriorityWithoutUser(this);
          }
        }
        v12 = v15;
        if ( v15 )
LABEL_27:
          System::Object::ReleaseNotFrozen$(v12);
      }
    }
  }
}

```

## disassembly

```asm
0x18005cd50  mov     [rsp+arg_8], rbx
0x18005cd55  mov     [rsp+arg_18], rsi
0x18005cd5a  push    rdi
0x18005cd5b  sub     rsp, 20h
0x18005cd5f  mov     sil, dl
0x18005cd62  mov     rdi, rcx
0x18005cd65  call    cs:__imp_GetCurrentThreadId
0x18005cd6b  mov     rbx, [rdi+20h]
0x18005cd6f  mov     r8, [rbx+30h]
0x18005cd73  cmp     eax, [r8+0B0h]
0x18005cd7a  jz      short loc_18005CD82
0x18005cd7c  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x18005cd82  cmp     qword ptr [rdi+38h], 0
0x18005cd87  jnz     short loc_18005CD98
0x18005cd89  cmp     byte ptr [rbx+0B0h], 0
0x18005cd90  jnz     short loc_18005CD98
0x18005cd92  cmp     dword ptr [rbx+44h], 4
0x18005cd96  jnz     short loc_18005CDA8
0x18005cd98  mov     rbx, [rsp+28h+arg_8]
0x18005cd9d  mov     rsi, [rsp+28h+arg_18]
0x18005cda2  add     rsp, 20h
0x18005cda6  pop     rdi
0x18005cda7  retn
0x18005cda8  cmp     cs:?s_disabled@UserAdapter@Dispatch@CoreUI@Microsoft@@0_NA, 0; bool Microsoft::CoreUI::Dispatch::UserAdapter::s_disabled
0x18005cdaf  jnz     short loc_18005CD98
0x18005cdb1  test    rbx, rbx
0x18005cdb4  jz      short loc_18005CDB9
0x18005cdb6  inc     dword ptr [rbx+10h]
0x18005cdb9  mov     rcx, rbx; struct Microsoft::CoreUI::Dispatch::EventLoop *
0x18005cdbc  call    ?EnsureSharedTebInitialized@UserAdapter@Dispatch@CoreUI@Microsoft@@SAXPEAVEventLoop@234@@Z; Microsoft::CoreUI::Dispatch::UserAdapter::EnsureSharedTebInitialized(Microsoft::CoreUI::Dispatch::EventLoop *)
0x18005cdc1  test    rbx, rbx
0x18005cdc4  jz      short loc_18005CDCE
0x18005cdc6  mov     rcx, rbx; this
0x18005cdc9  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18005cdce  cmp     cs:?s_userLoaded@UserAdapter@Dispatch@CoreUI@Microsoft@@2_NA, 0; bool Microsoft::CoreUI::Dispatch::UserAdapter::s_userLoaded
0x18005cdd5  jz      loc_18005CEA0
0x18005cddb  xor     ecx, ecx; bConvert
0x18005cddd  call    cs:__imp_IsGUIThread
0x18005cde3  test    eax, eax
0x18005cde5  jz      short loc_18005CD98
0x18005cde7  mov     rbx, [rdi+20h]
0x18005cdeb  cmp     dword ptr [rbx+48h], 0
0x18005cdef  jnz     loc_18005CE76
0x18005cdf5  mov     [rsp+28h+arg_0], 0
0x18005cdfe  lea     r8, [rsp+28h+arg_0]
0x18005ce03  mov     dl, sil
0x18005ce06  mov     rcx, rdi
0x18005ce09  call    ?CreateForThread@UserAdapter@Dispatch@CoreUI@Microsoft@@SA_NPEAVWin32EventLoopBridge@234@_NU?$Ref@V?$SmartPtr@VUserAdapter@Dispatch@CoreUI@Microsoft@@@CFlat@@@CFlat@@@Z; Microsoft::CoreUI::Dispatch::UserAdapter::CreateForThread(Microsoft::CoreUI::Dispatch::Win32EventLoopBridge *,bool,CFlat::Ref<CFlat::SmartPtr<Microsoft::CoreUI::Dispatch::UserAdapter>>)
0x18005ce0e  test    al, al
0x18005ce10  jz      short loc_18005CE5E
0x18005ce12  mov     rax, [rsp+28h+arg_0]
0x18005ce17  test    rax, rax
0x18005ce1a  jz      short loc_18005CE1F
0x18005ce1c  inc     dword ptr [rax+10h]
0x18005ce1f  mov     rcx, [rdi+38h]; this
0x18005ce23  mov     [rdi+38h], rax
0x18005ce27  test    rcx, rcx
0x18005ce2a  jz      short loc_18005CE31
0x18005ce2c  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18005ce31  mov     rbx, [rdi+28h]
0x18005ce35  mov     [rsp+28h+arg_10], rbx
0x18005ce3a  test    rbx, rbx
0x18005ce3d  jz      short loc_18005CE42
0x18005ce3f  inc     dword ptr [rbx+10h]
0x18005ce42  mov     rcx, rbx; this
0x18005ce45  call    ?OnUserIntegrationEnabled@WaitController@Dispatch@CoreUI@Microsoft@@QEAAXXZ; Microsoft::CoreUI::Dispatch::WaitController::OnUserIntegrationEnabled(void)
0x18005ce4a  nop
0x18005ce4b  test    rbx, rbx
0x18005ce4e  jz      short loc_18005CE58
0x18005ce50  mov     rcx, rbx; this
0x18005ce53  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18005ce58  cmp     byte ptr [rdi+48h], 0
0x18005ce5c  jnz     short loc_18005CEC5
0x18005ce5e  mov     rcx, [rsp+28h+arg_0]; this
0x18005ce63  test    rcx, rcx
0x18005ce66  jz      loc_18005CD98
0x18005ce6c  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18005ce71  jmp     loc_18005CD98
0x18005ce76  mov     rbx, [rbx+38h]
0x18005ce7a  mov     [rsp+28h+arg_10], rbx
0x18005ce7f  test    rbx, rbx
0x18005ce82  jz      short loc_18005CE87
0x18005ce84  inc     dword ptr [rbx+10h]
0x18005ce87  cmp     dword ptr [rbx+68h], 0
0x18005ce8b  jnz     short loc_18005CE9B
0x18005ce8d  mov     edx, 2
0x18005ce92  mov     rcx, rbx
0x18005ce95  call    ?AbandonLoop@Dispatcher@Dispatch@CoreUI@Microsoft@@QEAAXW4Dispatcher$LoopExitState@234@@Z; Microsoft::CoreUI::Dispatch::Dispatcher::AbandonLoop(Microsoft::CoreUI::Dispatch::Dispatcher$LoopExitState)
0x18005ce9a  nop
0x18005ce9b  mov     rcx, rbx
0x18005ce9e  jmp     short loc_18005CE6C
0x18005cea0  lea     rcx, ModuleName; "ext-ms-win-rtcore-ntuser-window-ext-l1-"...
0x18005cea7  call    cs:__imp_GetModuleHandleW
0x18005cead  test    rax, rax
0x18005ceb0  setnz   cs:?s_userLoaded@UserAdapter@Dispatch@CoreUI@Microsoft@@2_NA; bool Microsoft::CoreUI::Dispatch::UserAdapter::s_userLoaded
0x18005ceb7  test    rax, rax
0x18005ceba  jnz     loc_18005CDDB
0x18005cec0  jmp     loc_18005CD98
0x18005cec5  mov     byte ptr [rdi+48h], 0
0x18005cec9  mov     rcx, rdi; this
0x18005cecc  call    ?ExitAtQuitPriorityWithoutUser@Win32EventLoopBridge@Dispatch@CoreUI@Microsoft@@AEAAXXZ; Microsoft::CoreUI::Dispatch::Win32EventLoopBridge::ExitAtQuitPriorityWithoutUser(void)
0x18005ced1  jmp     short loc_18005CE5E
```
