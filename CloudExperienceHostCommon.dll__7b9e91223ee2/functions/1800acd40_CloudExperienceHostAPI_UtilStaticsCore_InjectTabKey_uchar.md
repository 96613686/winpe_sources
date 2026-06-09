# CloudExperienceHostAPI::UtilStaticsCore::InjectTabKey(uchar)

- ea: `0x1800acd40`
- end: `0x1800aceda`
- name: `?InjectTabKey@UtilStaticsCore@CloudExperienceHostAPI@@UEAAJE@Z`
- size: `410`
- prototype: `__int64 __fastcall(CloudExperienceHostAPI::UtilStaticsCore *__hidden this, unsigned __int8)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800153f8`
- `0x18001a540`
- `0x18001b004`
- `0x180021170`
- `0x18009c274`
- `0x1800acd40`
- `0x1800b99f8`
- `0x1800dc010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ace02`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ace02`
- `ext-ms-win-ntuser-keyboard-l1-1-0!SendInput` at `0x1800acdb4`
- `ext-ms-win-ntuser-keyboard-l1-1-0!SendInput` at `0x1800ace98`
- `ext-ms-win-ntuser-keyboard-l1-1-0!SendInput` at `0x1800acdb4`
- `ext-ms-win-ntuser-keyboard-l1-1-0!SendInput` at `0x1800ace98`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x1800ace24`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x1800ace24`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CloudExperienceHostAPI::UtilStaticsCore::InjectTabKey(
        CloudExperienceHostAPI::UtilStaticsCore *this,
        char a2)
{
  const char *v3; // r9
  __int64 *v4; // rax
  __int64 v5; // rdi
  DWORD CurrentThreadId; // eax
  int v7; // ebx
  const char *v9; // r9
  int v10; // [rsp+20h] [rbp-59h]
  _BYTE v11[8]; // [rsp+30h] [rbp-49h] BYREF
  __int64 v12; // [rsp+38h] [rbp-41h] BYREF
  tagINPUT pInputs; // [rsp+40h] [rbp-39h] BYREF
  int v14; // [rsp+68h] [rbp-11h]
  __int16 v15; // [rsp+70h] [rbp-9h]
  int v16; // [rsp+74h] [rbp-5h]
  int v17; // [rsp+90h] [rbp+17h]
  __int16 v18; // [rsp+98h] [rbp+1Fh]
  int v19; // [rsp+9Ch] [rbp+23h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  if ( a2 )
  {
    memset_0(&pInputs, 0, 0x78u);
    pInputs.type = 1;
    pInputs.ki.wVk = 16;
    v14 = 1;
    v15 = 9;
    v17 = 1;
    v18 = 9;
    v19 = 2;
    if ( !SendInput(3u, &pInputs, 40) )
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0x2BD,
        (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\utilstaticscore.cpp",
        v3);
    v11[0] = a2;
    v4 = Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_5c4496f6916396a1f05f2e117c1d6456_>,_lambda_5c4496f6916396a1f05f2e117c1d6456_>(
           &v12,
           v11);
    v5 = *v4;
    *v4 = 0;
    if ( v12 )
    {
      v12 = 0;
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IElevationBrokerContext>::Release();
    }
    CurrentThreadId = GetCurrentThreadId();
    v7 = SHTaskPoolQueueTask(2, 0, CurrentThreadId, 150, v5, 0);
    if ( v5 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2CB,
        (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\utilstaticscore.cpp",
        (const char *)(unsigned int)v7,
        v10);
      return (unsigned int)v7;
    }
  }
  else
  {
    memset_0(&pInputs, 0, 0x50u);
    pInputs.type = 1;
    pInputs.ki.wVk = 9;
    v14 = 1;
    v15 = 9;
    v16 = 2;
    if ( !SendInput(2u, &pInputs, 40) )
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0x2D8,
        (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\utilstaticscore.cpp",
        v9);
  }
  return 0;
}

```

## disassembly

```asm
0x1800acd40  mov     [rsp-8+arg_0], rbx
0x1800acd45  mov     [rsp-8+arg_8], rdi
0x1800acd4a  push    rbp
0x1800acd4b  lea     rbp, [rsp-57h]
0x1800acd50  sub     rsp, 0D0h
0x1800acd57  mov     rax, cs:__security_cookie
0x1800acd5e  xor     rax, rsp
0x1800acd61  mov     [rbp+57h+var_10], rax
0x1800acd65  mov     bl, dl
0x1800acd67  test    dl, dl
0x1800acd69  jz      loc_1800ACE61
0x1800acd6f  xor     edx, edx; Val
0x1800acd71  lea     r8d, [rdx+78h]; Size
0x1800acd75  lea     rcx, [rbp+57h+pInputs]; void *
0x1800acd79  call    memset_0
0x1800acd7e  mov     eax, 1
0x1800acd83  mov     [rbp+57h+pInputs.type], eax
0x1800acd86  lea     ecx, [rax+0Fh]
0x1800acd89  mov     word ptr [rbp+57h+pInputs.8], cx
0x1800acd8d  mov     [rbp+57h+var_68], eax
0x1800acd90  lea     ecx, [rax+8]
0x1800acd93  mov     [rbp+57h+var_60], cx
0x1800acd97  mov     [rbp+57h+var_40], eax
0x1800acd9a  mov     [rbp+57h+var_38], cx
0x1800acd9e  mov     [rbp+57h+var_34], 2
0x1800acda5  mov     rdi, [rbp+5Fh]
0x1800acda9  lea     r8d, [rax+27h]; cbSize
0x1800acdad  lea     rdx, [rbp+57h+pInputs]; pInputs
0x1800acdb1  lea     ecx, [rax+2]; cInputs
0x1800acdb4  call    cs:__imp_SendInput
0x1800acdba  test    eax, eax
0x1800acdbc  jnz     short loc_1800ACDD2
0x1800acdbe  lea     r8, aOnecoreuapShel_9; "onecoreuap\\shell\\cloudexperiencehost"...
0x1800acdc5  mov     edx, 2BDh; void *
0x1800acdca  mov     rcx, rdi; this
0x1800acdcd  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1800acdd2  mov     [rbp+57h+var_A0], bl
0x1800acdd5  lea     rdx, [rbp+57h+var_A0]
0x1800acdd9  lea     rcx, [rbp+57h+var_98]
0x1800acddd  call    ??$Make@V?$CTaskWrapper@V_lambda_5c4496f6916396a1f05f2e117c1d6456_@@@ComTaskPool@Internal@Windows@@V_lambda_5c4496f6916396a1f05f2e117c1d6456_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@V_lambda_5c4496f6916396a1f05f2e117c1d6456_@@@ComTaskPool@Internal@Windows@@@12@$$QEAV_lambda_5c4496f6916396a1f05f2e117c1d6456_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_5c4496f6916396a1f05f2e117c1d6456_>,_lambda_5c4496f6916396a1f05f2e117c1d6456_>(_lambda_5c4496f6916396a1f05f2e117c1d6456_ &&)
0x1800acde2  mov     rdi, [rax]
0x1800acde5  mov     qword ptr [rax], 0
0x1800acdec  mov     rcx, [rbp+57h+var_98]
0x1800acdf0  test    rcx, rcx
0x1800acdf3  jz      short loc_1800ACE02
0x1800acdf5  mov     [rbp+57h+var_98], 0
0x1800acdfd  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIElevationBrokerContext@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IElevationBrokerContext>::Release(void)
0x1800ace02  call    cs:__imp_GetCurrentThreadId
0x1800ace08  mov     [rsp+0D0h+var_A8], 0
0x1800ace11  mov     qword ptr [rsp+0D0h+var_B0], rdi; int
0x1800ace16  mov     r9d, 96h
0x1800ace1c  mov     r8d, eax
0x1800ace1f  xor     edx, edx
0x1800ace21  lea     ecx, [rdx+2]
0x1800ace24  call    cs:__imp_SHTaskPoolQueueTask
0x1800ace2a  mov     ebx, eax
0x1800ace2c  test    rdi, rdi
0x1800ace2f  jz      short loc_1800ACE41
0x1800ace31  mov     rdx, [rdi]
0x1800ace34  mov     rcx, rdi
0x1800ace37  mov     rax, [rdx+10h]
0x1800ace3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ace40  nop
0x1800ace41  test    ebx, ebx
0x1800ace43  jns     short loc_1800ACEB7
0x1800ace45  mov     rcx, [rbp+5Fh]; this
0x1800ace49  mov     r9d, ebx; char *
0x1800ace4c  lea     r8, aOnecoreuapShel_9; "onecoreuap\\shell\\cloudexperiencehost"...
0x1800ace53  mov     edx, 2CBh; void *
0x1800ace58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ace5d  mov     eax, ebx
0x1800ace5f  jmp     short loc_1800ACEB9
0x1800ace61  xor     edx, edx; Val
0x1800ace63  lea     r8d, [rdx+50h]; Size
0x1800ace67  lea     rcx, [rbp+57h+pInputs]; void *
0x1800ace6b  call    memset_0
0x1800ace70  mov     eax, 1
0x1800ace75  mov     [rbp+57h+pInputs.type], eax
0x1800ace78  lea     ecx, [rax+8]
0x1800ace7b  mov     word ptr [rbp+57h+pInputs.8], cx
0x1800ace7f  mov     [rbp+57h+var_68], eax
0x1800ace82  mov     [rbp+57h+var_60], cx
0x1800ace86  mov     [rbp+57h+var_5C], 2
0x1800ace8d  lea     r8d, [rax+27h]; cbSize
0x1800ace91  lea     rdx, [rbp+57h+pInputs]; pInputs
0x1800ace95  lea     ecx, [rax+1]; cInputs
0x1800ace98  call    cs:__imp_SendInput
0x1800ace9e  test    eax, eax
0x1800acea0  jnz     short loc_1800ACEB7
0x1800acea2  mov     rcx, [rbp+5Fh]; this
0x1800acea6  lea     r8, aOnecoreuapShel_9; "onecoreuap\\shell\\cloudexperiencehost"...
0x1800acead  mov     edx, 2D8h; void *
0x1800aceb2  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1800aceb7  xor     eax, eax
0x1800aceb9  mov     rcx, [rbp+57h+var_10]
0x1800acebd  xor     rcx, rsp; StackCookie
0x1800acec0  call    __security_check_cookie
0x1800acec5  lea     r11, [rsp+0D0h+var_s0]
0x1800acecd  mov     rbx, [r11+10h]
0x1800aced1  mov     rdi, [r11+18h]
0x1800aced5  mov     rsp, r11
0x1800aced8  pop     rbp
0x1800aced9  retn
```
