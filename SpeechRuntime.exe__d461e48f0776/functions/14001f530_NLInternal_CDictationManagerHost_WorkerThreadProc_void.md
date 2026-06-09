# NLInternal::CDictationManagerHost::WorkerThreadProc(void *)

- ea: `0x14001f530`
- end: `0x14001f736`
- name: `?WorkerThreadProc@CDictationManagerHost@NLInternal@@CAIPEAX@Z`
- size: `518`
- prototype: `unsigned int __fastcall(void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000c32c`
- `0x14000e010`
- `0x14000e030`
- `0x140011ea8`
- `0x14001f530`
- `0x140031010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14001f713`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14001f713`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001f64a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001f64a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14001f6c5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14001f6c5`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x14001f55d`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x14001f55d`
- `CoreMessaging!CoreUICreate` at `0x14001f593`
- `CoreMessaging!CoreUICreate` at `0x14001f593`

## string_xrefs

- `0x14001f556`: `Windows.Speech.Dictation.dll`
- `0x14001f545`: `DictationManagerHost::WorkerThreadProc enter`
- `0x14001f63c`: `CreateCommandingEngine`
- `0x14001f6ad`: `DictationManagerHost create succeeded`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall NLInternal::CDictationManagerHost::WorkerThreadProc(void *a1)
{
  const char *v2; // r9
  int v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rcx
  int v7; // eax
  __int64 v8; // rcx
  FARPROC ProcAddress; // rax
  int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // rcx
  int v13; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+8h]
  __int64 v15; // [rsp+40h] [rbp+10h] BYREF
  __int64 v16; // [rsp+48h] [rbp+18h] BYREF

  DoTraceMessage(16, "DictationManagerHost::WorkerThreadProc enter");
  NLInternal::CDictationManagerHost::s_dmModule = LoadLibraryW(L"Windows.Speech.Dictation.dll");
  if ( !NLInternal::CDictationManagerHost::s_dmModule )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x5A,
             (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechruntime\\voiceenabledshellhost\\dictationmanagerhost.cpp",
             v2);
  v15 = 0;
  v4 = CoreUICreate(&v15);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5D,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechruntime\\voiceenabledshellhost\\dictationmanagerhost.cpp",
      (const char *)(unsigned int)v4,
      v13);
    v6 = v15;
    if ( v15 )
    {
      v15 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
    return v5;
  }
  v7 = (*(__int64 (__fastcall **)(__int64, void *, __int64 (__fastcall *)(void *, unsigned int, void *), __int64))(*(_QWORD *)v15 + 272LL))(
         v15,
         a1,
         NLInternal::CDictationManagerHost::OnEventSignaled,
         v15);
  v5 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5E,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechruntime\\voiceenabledshellhost\\dictationmanagerhost.cpp",
      (const char *)(unsigned int)v7,
      v13);
    v8 = v15;
    if ( v15 )
    {
      v15 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    return v5;
  }
  ProcAddress = GetProcAddress(NLInternal::CDictationManagerHost::s_dmModule, "CreateCommandingEngine");
  v16 = 0;
  v10 = ((__int64 (__fastcall *)(__int64 *))ProcAddress)(&v16);
  v5 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x62,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechruntime\\voiceenabledshellhost\\dictationmanagerhost.cpp",
      (const char *)(unsigned int)v10,
      v13);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v16);
    v11 = v15;
    if ( v15 )
    {
      v15 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
    return v5;
  }
  DoTraceMessage(16, "DictationManagerHost create succeeded");
  SetEvent(NLInternal::CDictationManagerHost::s_initializedEvent);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 232LL))(v15);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v16);
  v12 = v15;
  if ( v15 )
  {
    v15 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  }
  if ( NLInternal::CDictationManagerHost::s_dmModule )
  {
    FreeLibrary(NLInternal::CDictationManagerHost::s_dmModule);
    NLInternal::CDictationManagerHost::s_dmModule = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x14001f530  mov     [rsp-8+arg_10], rbx
0x14001f535  mov     [rsp-8+arg_18], rdi
0x14001f53a  push    rbp
0x14001f53b  mov     rbp, rsp
0x14001f53e  sub     rsp, 30h
0x14001f542  mov     rdi, rcx
0x14001f545  lea     rdx, aDictationmanag_1; "DictationManagerHost::WorkerThreadProc "...
0x14001f54c  mov     ecx, 10h; int
0x14001f551  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x14001f556  lea     rcx, aWindowsSpeechD; "Windows.Speech.Dictation.dll"
0x14001f55d  call    cs:__imp_LoadLibraryW
0x14001f563  mov     cs:?s_dmModule@CDictationManagerHost@NLInternal@@0PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * NLInternal::CDictationManagerHost::s_dmModule
0x14001f56a  test    rax, rax
0x14001f56d  jnz     short loc_14001F587
0x14001f56f  mov     rcx, [rbp+8]; this
0x14001f573  lea     r8, aOnecoreuapEndu_29; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x14001f57a  lea     edx, [rax+5Ah]; void *
0x14001f57d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14001f582  jmp     loc_14001F726
0x14001f587  mov     [rbp+arg_0], 0
0x14001f58f  lea     rcx, [rbp+arg_0]
0x14001f593  call    cs:__imp_CoreUICreate
0x14001f599  mov     ebx, eax
0x14001f59b  test    eax, eax
0x14001f59d  jns     short loc_14001F5DD
0x14001f59f  mov     rcx, [rbp+8]; this
0x14001f5a3  mov     r9d, eax; char *
0x14001f5a6  lea     r8, aOnecoreuapEndu_29; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x14001f5ad  mov     edx, 5Dh ; ']'; void *
0x14001f5b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001f5b7  nop
0x14001f5b8  mov     rcx, [rbp+arg_0]
0x14001f5bc  test    rcx, rcx
0x14001f5bf  jz      short loc_14001F5D6
0x14001f5c1  mov     [rbp+arg_0], 0
0x14001f5c9  mov     rax, [rcx]
0x14001f5cc  mov     rax, [rax+10h]
0x14001f5d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f5d5  nop
0x14001f5d6  mov     eax, ebx
0x14001f5d8  jmp     loc_14001F726
0x14001f5dd  mov     rcx, [rbp+arg_0]
0x14001f5e1  mov     rax, [rcx]
0x14001f5e4  mov     r9, rcx
0x14001f5e7  lea     r8, ?OnEventSignaled@CDictationManagerHost@NLInternal@@CAJPEAXK0@Z; NLInternal::CDictationManagerHost::OnEventSignaled(void *,ulong,void *)
0x14001f5ee  mov     rdx, rdi
0x14001f5f1  mov     rax, [rax+110h]
0x14001f5f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f5fd  mov     ebx, eax
0x14001f5ff  test    eax, eax
0x14001f601  jns     short loc_14001F63C
0x14001f603  mov     rcx, [rbp+8]; this
0x14001f607  mov     r9d, eax; char *
0x14001f60a  lea     r8, aOnecoreuapEndu_29; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x14001f611  mov     edx, 5Eh ; '^'; void *
0x14001f616  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001f61b  nop
0x14001f61c  mov     rcx, [rbp+arg_0]
0x14001f620  test    rcx, rcx
0x14001f623  jz      short loc_14001F63A
0x14001f625  mov     [rbp+arg_0], 0
0x14001f62d  mov     rax, [rcx]
0x14001f630  mov     rax, [rax+10h]
0x14001f634  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f639  nop
0x14001f63a  jmp     short loc_14001F5D6
0x14001f63c  lea     rdx, aCreatecommandi; "CreateCommandingEngine"
0x14001f643  mov     rcx, cs:?s_dmModule@CDictationManagerHost@NLInternal@@0PEAUHINSTANCE__@@EA; hModule
0x14001f64a  call    cs:__imp_GetProcAddress
0x14001f650  mov     [rbp+arg_8], 0
0x14001f658  lea     rcx, [rbp+arg_8]
0x14001f65c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f661  mov     ebx, eax
0x14001f663  test    eax, eax
0x14001f665  jns     short loc_14001F6AD
0x14001f667  mov     rcx, [rbp+8]; this
0x14001f66b  mov     r9d, eax; char *
0x14001f66e  lea     r8, aOnecoreuapEndu_29; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x14001f675  mov     edx, 62h ; 'b'; void *
0x14001f67a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001f67f  nop
0x14001f680  lea     rcx, [rbp+arg_8]
0x14001f684  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x14001f689  nop
0x14001f68a  mov     rcx, [rbp+arg_0]
0x14001f68e  test    rcx, rcx
0x14001f691  jz      short loc_14001F6A8
0x14001f693  mov     [rbp+arg_0], 0
0x14001f69b  mov     rax, [rcx]
0x14001f69e  mov     rax, [rax+10h]
0x14001f6a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f6a7  nop
0x14001f6a8  jmp     loc_14001F5D6
0x14001f6ad  lea     rdx, aDictationmanag_0; "DictationManagerHost create succeeded"
0x14001f6b4  mov     ecx, 10h; int
0x14001f6b9  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x14001f6be  mov     rcx, cs:?s_initializedEvent@CDictationManagerHost@NLInternal@@0PEAXEA; hEvent
0x14001f6c5  call    cs:__imp_SetEvent
0x14001f6cb  mov     rcx, [rbp+arg_0]
0x14001f6cf  mov     rax, [rcx]
0x14001f6d2  mov     rax, [rax+0E8h]
0x14001f6d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f6de  nop
0x14001f6df  lea     rcx, [rbp+arg_8]
0x14001f6e3  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x14001f6e8  nop
0x14001f6e9  mov     rcx, [rbp+arg_0]
0x14001f6ed  test    rcx, rcx
0x14001f6f0  jz      short loc_14001F707
0x14001f6f2  mov     [rbp+arg_0], 0
0x14001f6fa  mov     rax, [rcx]
0x14001f6fd  mov     rax, [rax+10h]
0x14001f701  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f706  nop
0x14001f707  mov     rcx, cs:?s_dmModule@CDictationManagerHost@NLInternal@@0PEAUHINSTANCE__@@EA; hLibModule
0x14001f70e  test    rcx, rcx
0x14001f711  jz      short loc_14001F724
0x14001f713  call    cs:__imp_FreeLibrary
0x14001f719  mov     cs:?s_dmModule@CDictationManagerHost@NLInternal@@0PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * NLInternal::CDictationManagerHost::s_dmModule
0x14001f724  xor     eax, eax
0x14001f726  mov     rbx, [rsp+30h+arg_10]
0x14001f72b  mov     rdi, [rsp+30h+arg_18]
0x14001f730  add     rsp, 30h
0x14001f734  pop     rbp
0x14001f735  retn
```
