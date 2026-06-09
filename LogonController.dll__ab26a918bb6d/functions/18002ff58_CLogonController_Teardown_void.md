# CLogonController::_Teardown(void)

- ea: `0x18002ff58`
- end: `0x1800302e4`
- name: `?_Teardown@CLogonController@@AEAAJXZ`
- size: `908`
- prototype: `__int64 __fastcall(CLogonController *__hidden this)`
- caller_count: `2`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001fec0`
- `0x18002fef4`

## callees

- `0x180008094`
- `0x18000cd1c`
- `0x18000df10`
- `0x18001329c`
- `0x180015920`
- `0x18002ff58`
- `0x1800302ec`
- `0x1800304a8`
- `0x180030540`
- `0x180030854`
- `0x18006f0d8`
- `0x18009d010`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x180030181`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180030181`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800300cd`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800300cd`
- `SHCORE!SHTaskPoolQueueTask` at `0x180030006`
- `SHCORE!SHTaskPoolQueueTask` at `0x180030070`
- `SHCORE!SHTaskPoolQueueTask` at `0x180030006`
- `SHCORE!SHTaskPoolQueueTask` at `0x180030070`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CLogonController::_Teardown(CLogonController *this)
{
  int v2; // eax
  unsigned int v3; // edi
  void *v4; // rax
  void *v5; // rbx
  unsigned int v6; // edi
  void *v7; // rax
  void *v8; // rbx
  int v9; // eax
  __int64 v10; // rdi
  __int64 v11; // rbx
  __int64 v12; // rsi
  __int64 v13; // r15
  __int64 v14; // r15
  __int64 v15; // r15
  int SignInAnimationIfRunning; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v23; // [rsp+20h] [rbp-10h]
  int v24; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+38h]
  __int64 v26; // [rsp+70h] [rbp+40h] BYREF
  __int64 v27; // [rsp+78h] [rbp+48h]
  __int64 v28; // [rsp+80h] [rbp+50h]
  __int64 v29; // [rsp+88h] [rbp+58h]

  v2 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(*((_QWORD *)this + 18) + 16LL) + 320LL))(
         *((_QWORD *)this + 18) + 16LL,
         *((_QWORD *)this + 25));
  if ( v2 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x999,
      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
      (const char *)(unsigned int)v2,
      v23);
  v3 = *((_DWORD *)this + 52);
  v4 = operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
  v5 = v4;
  if ( v4 )
  {
    Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>(v4);
    *(_QWORD *)v5 = &off_1800A2598;
  }
  else
  {
    v5 = 0;
  }
  SHTaskPoolQueueTask(3, 290, v3, 0, v5, 0);
  if ( v5 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v5 + 16LL))(v5);
  v6 = *((_DWORD *)this + 53);
  v7 = operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
  v8 = v7;
  if ( v7 )
  {
    Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>(v7);
    *(_QWORD *)v8 = &off_1800A2598;
  }
  else
  {
    v8 = 0;
  }
  SHTaskPoolQueueTask(3, 290, v6, 0, v8, 0);
  if ( v8 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v8 + 16LL))(v8);
  v9 = CLogonController::Abort((CLogonController *)((char *)this + 32));
  if ( v9 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x9A0,
      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
      (const char *)(unsigned int)v9,
      v24);
  v10 = 0;
  v27 = 0;
  v11 = 0;
  v28 = 0;
  v12 = 0;
  v29 = 0;
  AcquireSRWLockExclusive((PSRWLOCK)this + 43);
  *((_BYTE *)this + 352) = 1;
  v13 = *((_QWORD *)this + 45);
  *((_QWORD *)this + 45) = 0;
  if ( v13 )
  {
    v26 = v13;
    Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v26);
    v26 = 0;
    v10 = v13;
    v27 = v13;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
  }
  v14 = *((_QWORD *)this + 46);
  *((_QWORD *)this + 46) = 0;
  if ( v14 )
  {
    v26 = v14;
    Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v26);
    v26 = 0;
    v11 = v14;
    v28 = v14;
    Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v26);
  }
  v15 = *((_QWORD *)this + 47);
  *((_QWORD *)this + 47) = 0;
  if ( v15 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
    v12 = v15;
    v29 = v15;
  }
  if ( this != (CLogonController *)-344LL )
    ReleaseSRWLockExclusive((PSRWLOCK)this + 43);
  SignInAnimationIfRunning = CLogonController::_CancelFirstSignInAnimationIfRunning(this);
  if ( SignInAnimationIfRunning < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x9AF,
      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
      (const char *)(unsigned int)SignInAnimationIfRunning,
      v24);
  if ( v10 )
  {
    v17 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 184LL))(v10);
    if ( v17 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x9B3,
        (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
        (const char *)(unsigned int)v17,
        v24);
  }
  if ( v11 )
  {
    v18 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v11 + 96LL))(v11, *((_QWORD *)this + 24));
    if ( v18 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x9B8,
        (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
        (const char *)(unsigned int)v18,
        v24);
    v19 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 112LL))(v11);
    if ( v19 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x9B9,
        (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
        (const char *)(unsigned int)v19,
        v24);
  }
  if ( v12 )
  {
    v20 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 72LL))(v12);
    if ( v20 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x9BE,
        (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
        (const char *)(unsigned int)v20,
        v24);
  }
  v21 = SilentTSAutologonManager::Shutdown(*((SilentTSAutologonManager **)this + 23));
  if ( v21 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x9C1,
      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
      (const char *)(unsigned int)v21,
      v24);
  CProcessStateManager::Shutdown(*((CProcessStateManager **)this + 18));
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  return 0;
}

```

## disassembly

```asm
0x18002ff58  push    rbp
0x18002ff5a  push    rbx
0x18002ff5b  push    rsi
0x18002ff5c  push    rdi
0x18002ff5d  push    r12
0x18002ff5f  push    r14
0x18002ff61  push    r15
0x18002ff63  mov     rbp, rsp
0x18002ff66  sub     rsp, 30h
0x18002ff6a  mov     r14, rcx
0x18002ff6d  mov     rcx, [rcx+90h]
0x18002ff74  add     rcx, 10h
0x18002ff78  mov     rax, [rcx]
0x18002ff7b  mov     rdx, [r14+0C8h]
0x18002ff82  mov     rax, [rax+140h]
0x18002ff89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ff8e  mov     rcx, [rbp+38h]; this
0x18002ff92  test    eax, eax
0x18002ff94  jns     short loc_18002FFAA
0x18002ff96  mov     r9d, eax; char *
0x18002ff99  lea     r8, aPcshellShellAu_14; "pcshell\\shell\\auth\\authux\\controlle"...
0x18002ffa0  mov     edx, 999h; void *
0x18002ffa5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002ffaa  mov     edi, [r14+0D0h]
0x18002ffb1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002ffb8  mov     esi, 18h
0x18002ffbd  mov     ecx, esi; unsigned __int64
0x18002ffbf  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002ffc4  mov     rbx, rax
0x18002ffc7  test    rax, rax
0x18002ffca  jz      short loc_18002FFE0
0x18002ffcc  mov     rcx, rax
0x18002ffcf  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIComPoolTask@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>(void)
0x18002ffd4  lea     rax, off_1800A2598
0x18002ffdb  mov     [rbx], rax
0x18002ffde  jmp     short loc_18002FFE2
0x18002ffe0  xor     ebx, ebx
0x18002ffe2  mov     [rsp+30h+var_8], 0
0x18002ffeb  mov     qword ptr [rsp+30h+var_10], rbx
0x18002fff0  xor     r9d, r9d
0x18002fff3  mov     r8d, edi
0x18002fff6  mov     r15d, 122h
0x18002fffc  mov     edx, r15d
0x18002ffff  lea     r12d, [r9+3]
0x180030003  mov     ecx, r12d
0x180030006  call    cs:__imp_SHTaskPoolQueueTask
0x18003000c  nop
0x18003000d  test    rbx, rbx
0x180030010  jz      short loc_180030022
0x180030012  mov     rax, [rbx]
0x180030015  mov     rcx, rbx
0x180030018  mov     rax, [rax+10h]
0x18003001c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030021  nop
0x180030022  mov     edi, [r14+0D4h]
0x180030029  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180030030  mov     rcx, rsi; unsigned __int64
0x180030033  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180030038  mov     rbx, rax
0x18003003b  test    rax, rax
0x18003003e  jz      short loc_180030054
0x180030040  mov     rcx, rax
0x180030043  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIComPoolTask@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>(void)
0x180030048  lea     rax, off_1800A2598
0x18003004f  mov     [rbx], rax
0x180030052  jmp     short loc_180030056
0x180030054  xor     ebx, ebx
0x180030056  mov     [rsp+30h+var_8], 0
0x18003005f  mov     qword ptr [rsp+30h+var_10], rbx; int
0x180030064  xor     r9d, r9d
0x180030067  mov     r8d, edi
0x18003006a  mov     edx, r15d
0x18003006d  mov     ecx, r12d
0x180030070  call    cs:__imp_SHTaskPoolQueueTask
0x180030076  nop
0x180030077  test    rbx, rbx
0x18003007a  jz      short loc_18003008C
0x18003007c  mov     rax, [rbx]
0x18003007f  mov     rcx, rbx
0x180030082  mov     rax, [rax+10h]
0x180030086  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003008b  nop
0x18003008c  lea     rcx, [r14+20h]; this
0x180030090  call    ?Abort@CLogonController@@UEAAJXZ; CLogonController::Abort(void)
0x180030095  mov     rcx, [rbp+38h]; this
0x180030099  test    eax, eax
0x18003009b  jns     short loc_1800300B1
0x18003009d  mov     r9d, eax; char *
0x1800300a0  lea     r8, aPcshellShellAu_14; "pcshell\\shell\\auth\\authux\\controlle"...
0x1800300a7  mov     edx, 9A0h; void *
0x1800300ac  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800300b1  xor     edi, edi
0x1800300b3  mov     [rbp+arg_8], rdi
0x1800300b7  xor     ebx, ebx
0x1800300b9  mov     [rbp+arg_10], rbx
0x1800300bd  xor     esi, esi
0x1800300bf  mov     [rbp+arg_18], rsi
0x1800300c3  lea     r12, [r14+158h]
0x1800300ca  mov     rcx, r12; SRWLock
0x1800300cd  call    cs:__imp_AcquireSRWLockExclusive
0x1800300d3  mov     byte ptr [r14+160h], 1
0x1800300db  mov     r15, [r14+168h]
0x1800300e2  mov     [r14+168h], rsi
0x1800300e9  test    r15, r15
0x1800300ec  jz      short loc_18003010F
0x1800300ee  mov     [rbp+arg_0], r15
0x1800300f2  lea     rcx, [rbp+arg_0]
0x1800300f6  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x1800300fb  mov     [rbp+arg_0], rsi
0x1800300ff  mov     rdi, r15
0x180030102  mov     [rbp+arg_8], r15
0x180030106  lea     rcx, [rbp+arg_0]
0x18003010a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003010f  mov     r15, [r14+170h]
0x180030116  mov     qword ptr [r14+170h], 0
0x180030121  test    r15, r15
0x180030124  jz      short loc_18003014B
0x180030126  mov     [rbp+arg_0], r15
0x18003012a  lea     rcx, [rbp+arg_0]
0x18003012e  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180030133  mov     [rbp+arg_0], 0
0x18003013b  mov     rbx, r15
0x18003013e  mov     [rbp+arg_10], rbx
0x180030142  lea     rcx, [rbp+arg_0]
0x180030146  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x18003014b  mov     r15, [r14+178h]
0x180030152  mov     qword ptr [r14+178h], 0
0x18003015d  test    r15, r15
0x180030160  jz      short loc_180030179
0x180030162  mov     rax, [r15]
0x180030165  mov     rcx, r15
0x180030168  mov     rax, [rax+8]
0x18003016c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030171  nop
0x180030172  mov     rsi, r15
0x180030175  mov     [rbp+arg_18], r15
0x180030179  test    r12, r12
0x18003017c  jz      short loc_180030187
0x18003017e  mov     rcx, r12; SRWLock
0x180030181  call    cs:__imp_ReleaseSRWLockExclusive
0x180030187  mov     rcx, r14; this
0x18003018a  call    ?_CancelFirstSignInAnimationIfRunning@CLogonController@@AEAAJXZ; CLogonController::_CancelFirstSignInAnimationIfRunning(void)
0x18003018f  mov     rcx, [rbp+38h]; this
0x180030193  lea     r15, aPcshellShellAu_14; "pcshell\\shell\\auth\\authux\\controlle"...
0x18003019a  test    eax, eax
0x18003019c  jns     short loc_1800301AE
0x18003019e  mov     r9d, eax; char *
0x1800301a1  mov     r8, r15; unsigned int
0x1800301a4  mov     edx, 9AFh; void *
0x1800301a9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800301ae  test    rdi, rdi
0x1800301b1  jz      short loc_1800301DD
0x1800301b3  mov     rax, [rdi]
0x1800301b6  mov     rcx, rdi
0x1800301b9  mov     rax, [rax+0B8h]
0x1800301c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800301c5  mov     rcx, [rbp+38h]; this
0x1800301c9  test    eax, eax
0x1800301cb  jns     short loc_1800301DD
0x1800301cd  mov     r9d, eax; char *
0x1800301d0  mov     r8, r15; unsigned int
0x1800301d3  mov     edx, 9B3h; void *
0x1800301d8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800301dd  test    rbx, rbx
0x1800301e0  jz      short loc_180030237
0x1800301e2  mov     rax, [rbx]
0x1800301e5  mov     rdx, [r14+0C0h]
0x1800301ec  mov     rcx, rbx
0x1800301ef  mov     rax, [rax+60h]
0x1800301f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800301f8  mov     rcx, [rbp+38h]; this
0x1800301fc  test    eax, eax
0x1800301fe  jns     short loc_180030210
0x180030200  mov     r9d, eax; char *
0x180030203  mov     r8, r15; unsigned int
0x180030206  mov     edx, 9B8h; void *
0x18003020b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180030210  mov     rax, [rbx]
0x180030213  mov     rcx, rbx
0x180030216  mov     rax, [rax+70h]
0x18003021a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003021f  mov     rcx, [rbp+38h]; this
0x180030223  test    eax, eax
0x180030225  jns     short loc_180030237
0x180030227  mov     r9d, eax; char *
0x18003022a  mov     r8, r15; unsigned int
0x18003022d  mov     edx, 9B9h; void *
0x180030232  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180030237  test    rsi, rsi
0x18003023a  jz      short loc_180030263
0x18003023c  mov     rax, [rsi]
0x18003023f  mov     rcx, rsi
0x180030242  mov     rax, [rax+48h]
0x180030246  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003024b  mov     rcx, [rbp+38h]; this
0x18003024f  test    eax, eax
0x180030251  jns     short loc_180030263
0x180030253  mov     r9d, eax; char *
0x180030256  mov     r8, r15; unsigned int
0x180030259  mov     edx, 9BEh; void *
0x18003025e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180030263  mov     rcx, [r14+0B8h]; this
0x18003026a  call    ?Shutdown@SilentTSAutologonManager@@QEAAJXZ; SilentTSAutologonManager::Shutdown(void)
0x18003026f  mov     rcx, [rbp+38h]; this
0x180030273  test    eax, eax
0x180030275  jns     short loc_180030287
0x180030277  mov     r9d, eax; char *
0x18003027a  mov     r8, r15; unsigned int
0x18003027d  mov     edx, 9C1h; void *
0x180030282  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180030287  mov     rcx, [r14+90h]; this
0x18003028e  call    ?Shutdown@CProcessStateManager@@QEAAXXZ; CProcessStateManager::Shutdown(void)
0x180030293  nop
0x180030294  test    rsi, rsi
0x180030297  jz      short loc_1800302A9
0x180030299  mov     rax, [rsi]
0x18003029c  mov     rcx, rsi
0x18003029f  mov     rax, [rax+10h]
0x1800302a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800302a8  nop
0x1800302a9  test    rbx, rbx
0x1800302ac  jz      short loc_1800302BE
0x1800302ae  mov     rax, [rbx]
0x1800302b1  mov     rcx, rbx
0x1800302b4  mov     rax, [rax+10h]
0x1800302b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800302bd  nop
0x1800302be  test    rdi, rdi
0x1800302c1  jz      short loc_1800302D3
0x1800302c3  mov     rax, [rdi]
0x1800302c6  mov     rcx, rdi
0x1800302c9  mov     rax, [rax+10h]
0x1800302cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800302d2  nop
0x1800302d3  xor     eax, eax
0x1800302d5  add     rsp, 30h
0x1800302d9  pop     r15
0x1800302db  pop     r14
0x1800302dd  pop     r12
0x1800302df  pop     rdi
0x1800302e0  pop     rsi
0x1800302e1  pop     rbx
0x1800302e2  pop     rbp
0x1800302e3  retn
```
