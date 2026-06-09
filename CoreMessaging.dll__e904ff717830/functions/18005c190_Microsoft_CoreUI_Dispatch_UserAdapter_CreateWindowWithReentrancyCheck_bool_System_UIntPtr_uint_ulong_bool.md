# Microsoft::CoreUI::Dispatch::UserAdapter::CreateWindowWithReentrancyCheck(bool,System::UIntPtr *,uint *,ulong *,bool *)

- ea: `0x18005c190`
- end: `0x18005c2e6`
- name: `?CreateWindowWithReentrancyCheck@UserAdapter@Dispatch@CoreUI@Microsoft@@CAPEAUHWND__@@_NPEAUUIntPtr@System@@PEAIPEAKPEA_N@Z`
- size: `342`
- prototype: `HWND __fastcall(bool, struct System::UIntPtr *, unsigned int *, unsigned int *, bool *)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18005c084`

## callees

- `0x1800067f0`
- `0x180009750`
- `0x180048a20`
- `0x18005be40`
- `0x18005bed4`
- `0x18005c190`
- `0x18005c2ec`
- `0x18008f584`
- `0x1800a236c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c207`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c207`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18005c1cf`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18005c1cf`
- `ext-ms-win-rtcore-ntuser-integration-l1-1-0!__imp_InitThreadCoreMessagingIocp2` at `0x18005c247`
- `ext-ms-win-rtcore-ntuser-integration-l1-1-0!__imp_InitThreadCoreMessagingIocp2` at `0x18005c247`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!DestroyWindow` at `0x18005c2a7`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!DestroyWindow` at `0x18005c2a7`

## pseudocode

```c
HWND __fastcall Microsoft::CoreUI::Dispatch::UserAdapter::CreateWindowWithReentrancyCheck(
        char a1,
        struct System::UIntPtr *a2,
        unsigned int *a3,
        unsigned int *a4,
        bool *a5)
{
  _QWORD *Value; // rdi
  HWND Window; // rbx
  Cn::Engine::Lock *v11; // rcx
  char v12; // al
  __int64 inited; // rax

  *(_QWORD *)a2 = 0;
  *a3 = 0;
  *a4 = 0;
  *a5 = 1;
  Value = TlsGetValue(Cn::Context::s_tlsStorage);
  Value[2] = 0;
  CFlat::EntryExit::OnBeginCallToNative(Value);
  Window = Microsoft::CoreUI::Dispatch::UserAdapter::NoContext_CreateWindow();
  if ( Window )
  {
    v12 = Microsoft::CoreUI::Dispatch::UserAdapter::AreTlsFlagsSet(1) ^ 1;
    *a5 = v12;
    if ( v12 )
    {
      inited = InitThreadCoreMessagingIocp2(Window, a3);
      if ( !inited || *a3 >= 2 )
        Cn::FailFast::ForWin32();
      *(_QWORD *)a2 = inited;
      Microsoft::CoreUI::Dispatch::UserAdapter::SetBackupTimer(Window, 0x7FFFFFFFu);
    }
    else
    {
      DestroyWindow(Window);
      Window = 0;
    }
  }
  else
  {
    if ( !a1 )
      Cn::FailFast::ForWin32();
    *a4 = GetLastError();
  }
  v11 = (Cn::Engine::Lock *)Value[11];
  if ( v11 )
  {
    Cn::Engine::Lock::Enter(v11);
    Cn::Context::SetCurrentContext((struct Cn::Context *)Value);
  }
  Value[2] = 0;
  return Window;
}

```

## disassembly

```asm
0x18005c190  push    rbx
0x18005c192  push    rsi
0x18005c193  push    rdi
0x18005c194  push    r12
0x18005c196  push    r13
0x18005c198  push    r14
0x18005c19a  push    r15
0x18005c19c  sub     rsp, 40h
0x18005c1a0  mov     r14, r9
0x18005c1a3  mov     rsi, r8
0x18005c1a6  mov     r12, rdx
0x18005c1a9  mov     r15b, cl
0x18005c1ac  xor     ebx, ebx
0x18005c1ae  mov     [rsp+78h+var_58], rbx
0x18005c1b3  mov     [rdx], rbx
0x18005c1b6  mov     [r8], ebx
0x18005c1b9  mov     [r9], ebx
0x18005c1bc  mov     r13, [rsp+78h+arg_20]
0x18005c1c4  mov     byte ptr [r13+0], 1
0x18005c1c9  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18005c1cf  call    cs:__imp_TlsGetValue
0x18005c1d5  mov     rdi, rax
0x18005c1d8  mov     [rsp+78h+arg_10], rax
0x18005c1e0  mov     [rax+10h], rbx
0x18005c1e4  mov     rcx, rax; void *
0x18005c1e7  call    ?OnBeginCallToNative@EntryExit@CFlat@@SAXPEAX@Z; CFlat::EntryExit::OnBeginCallToNative(void *)
0x18005c1ec  call    ?NoContext_CreateWindow@UserAdapter@Dispatch@CoreUI@Microsoft@@CAPEAUHWND__@@XZ; Microsoft::CoreUI::Dispatch::UserAdapter::NoContext_CreateWindow(void)
0x18005c1f1  mov     rbx, rax
0x18005c1f4  mov     [rsp+78h+var_58], rax
0x18005c1f9  test    rax, rax
0x18005c1fc  jnz     short loc_18005C22F
0x18005c1fe  test    r15b, r15b
0x18005c201  jz      loc_18005C2B9
0x18005c207  call    cs:__imp_GetLastError
0x18005c20d  mov     [r14], eax
0x18005c210  mov     rcx, [rdi+58h]; this
0x18005c214  test    rcx, rcx
0x18005c217  jz      loc_18005C2C4
0x18005c21d  call    ?Enter@Lock@Engine@Cn@@QEAAXXZ; Cn::Engine::Lock::Enter(void)
0x18005c222  mov     rcx, rdi; lpTlsValue
0x18005c225  call    ?SetCurrentContext@Context@Cn@@CAXPEAV12@@Z; Cn::Context::SetCurrentContext(Cn::Context *)
0x18005c22a  jmp     loc_18005C2C4
0x18005c22f  mov     ecx, 1
0x18005c234  call    ?AreTlsFlagsSet@UserAdapter@Dispatch@CoreUI@Microsoft@@CA_NW4UserAdapter$TlsFlags@234@@Z; Microsoft::CoreUI::Dispatch::UserAdapter::AreTlsFlagsSet(Microsoft::CoreUI::Dispatch::UserAdapter$TlsFlags)
0x18005c239  xor     al, 1
0x18005c23b  mov     [r13+0], al
0x18005c23f  mov     rcx, rbx; hWnd
0x18005c242  jz      short loc_18005C2A7
0x18005c244  mov     rdx, rsi
0x18005c247  call    cs:__imp_InitThreadCoreMessagingIocp2
0x18005c24d  test    rax, rax
0x18005c250  jz      short loc_18005C2BE
0x18005c252  cmp     dword ptr [rsi], 2
0x18005c255  jnb     short loc_18005C2BE
0x18005c257  mov     [rsp+78h+arg_18], rax
0x18005c25f  mov     [rsp+78h+var_50], rax
0x18005c264  mov     [rsp+78h+arg_20], 0
0x18005c270  mov     [rsp+78h+arg_20], rax
0x18005c278  mov     [rsp+78h+arg_8], 0
0x18005c284  mov     [rsp+78h+arg_8], rax
0x18005c28c  mov     [rsp+78h+var_48], rax
0x18005c291  mov     [r12], rax
0x18005c295  mov     edx, 7FFFFFFFh; uElapse
0x18005c29a  mov     rcx, rbx; hWnd
0x18005c29d  call    ?SetBackupTimer@UserAdapter@Dispatch@CoreUI@Microsoft@@CAXPEAXI@Z; Microsoft::CoreUI::Dispatch::UserAdapter::SetBackupTimer(void *,uint)
0x18005c2a2  jmp     loc_18005C210
0x18005c2a7  call    cs:__imp_DestroyWindow
0x18005c2ad  xor     ebx, ebx
0x18005c2af  mov     [rsp+78h+var_58], rbx
0x18005c2b4  jmp     loc_18005C210
0x18005c2b9  call    ?ForWin32@FailFast@Cn@@SAXXZ; Cn::FailFast::ForWin32(void)
0x18005c2be  call    ?ForWin32@FailFast@Cn@@SAXXZ; Cn::FailFast::ForWin32(void)
0x18005c2c4  mov     qword ptr [rdi+10h], 0
0x18005c2cc  jmp     short loc_18005C2D3
0x18005c2ce  mov     rbx, [rsp+78h+var_58]
0x18005c2d3  mov     rax, rbx
0x18005c2d6  add     rsp, 40h
0x18005c2da  pop     r15
0x18005c2dc  pop     r14
0x18005c2de  pop     r13
0x18005c2e0  pop     r12
0x18005c2e2  pop     rdi
0x18005c2e3  pop     rsi
0x18005c2e4  pop     rbx
0x18005c2e5  retn
0x1800cbdc1  push    rbp
0x1800cbdc3  sub     rsp, 20h
0x1800cbdc7  mov     rbp, rdx
0x1800cbdca  mov     rdx, [rbp+90h]; this
0x1800cbdd1  call    ?UnexpectedStructuredExceptionFilter@ExceptionHandling@CFlat@@SAHPEAU_EXCEPTION_POINTERS@@PEAX@Z; CFlat::ExceptionHandling::UnexpectedStructuredExceptionFilter(_EXCEPTION_POINTERS *,void *)
0x1800cbdd6  nop
0x1800cbdd7  add     rsp, 20h
0x1800cbddb  pop     rbp
0x1800cbddc  retn
```
