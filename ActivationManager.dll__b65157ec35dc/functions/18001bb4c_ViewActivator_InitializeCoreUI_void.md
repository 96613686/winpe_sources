# ViewActivator::InitializeCoreUI(void)

- ea: `0x18001bb4c`
- end: `0x18001bdb7`
- name: `?InitializeCoreUI@ViewActivator@@AEAAJXZ`
- size: `619`
- prototype: `__int64 __fastcall(ViewActivator *__hidden this)`
- caller_count: `2`
- callee_count: `13`
- tags: `loader_planting`

## callers

- `0x18001c4e0`
- `0x180035040`

## callees

- `0x18000b5c0`
- `0x180015ba0`
- `0x180016d14`
- `0x18001baa4`
- `0x18001bb4c`
- `0x18001e3c4`
- `0x18001e5ac`
- `0x180041ca0`
- `0x180044408`
- `0x180047048`
- `0x180047068`
- `0x180050d50`
- `0x18005ae90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001bbca`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001bbca`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18001bce5`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18001bce5`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001bc6f`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001bc6f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bbfb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bc1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bca0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bcc2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bbfb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bc1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bca0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bcc2`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18001bd2a`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18001bd2a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ViewActivator::InitializeCoreUI(ViewActivator *this)
{
  char *EventW; // rdi
  const char *v4; // r9
  HANDLE *v5; // r14
  HANDLE v6; // rsi
  unsigned int LastError; // ebx
  char *Thread; // rsi
  const char *v9; // r9
  HANDLE *v10; // rdi
  HANDLE v11; // r15
  __int64 v12; // rdx
  DWORD dwCreationFlags; // [rsp+20h] [rbp-E0h]
  _BYTE v14[8]; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE Handles[2]; // [rsp+38h] [rbp-C8h] BYREF
  char v16; // [rsp+48h] [rbp-B8h] BYREF
  char v17; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v18[42]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+E8h]

  if ( *((_BYTE *)this + 80) )
    return 0;
  wil::ActivityBase<AAMTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AAMTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v18,
    "InitCoreUI");
  v18[0] = &AAMTraceProvider::InitCoreUI::`vftable';
  AAMTraceProvider::InitCoreUI::StartActivity((AAMTraceProvider::InitCoreUI *)v18);
  ViewActivator::ReleaseCoreUI(this);
  EventW = (char *)CreateEventW(0, 1, 0, 0);
  v5 = (HANDLE *)((char *)this + 40);
  if ( (char *)this + 40 == &v16 )
  {
    if ( (unsigned __int64)(EventW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(EventW);
  }
  else
  {
    v6 = *v5;
    if ( (char *)*v5 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)v14);
      CloseHandle(v6);
      wil::last_error_context::~last_error_context((wil::last_error_context *)v14);
    }
    *v5 = EventW;
  }
  if ( (((unsigned __int64)*v5 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    Thread = (char *)CreateThread(0, 0, ViewActivator::MessageSessionThreadProc, this, 0, 0);
    v10 = (HANDLE *)((char *)this + 48);
    if ( (char *)this + 48 == &v17 )
    {
      if ( (unsigned __int64)(Thread - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(Thread);
    }
    else
    {
      v11 = *v10;
      if ( (char *)*v10 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)v14);
        CloseHandle(v11);
        wil::last_error_context::~last_error_context((wil::last_error_context *)v14);
      }
      *v10 = Thread;
    }
    if ( (((unsigned __int64)*v10 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    {
      if ( SetThreadPriority(*v10, 2) )
      {
        Handles[0] = *v5;
        Handles[1] = *v10;
        if ( WaitForMultipleObjects(2u, Handles, 0, *((_DWORD *)this + 32)) )
        {
          LastError = -2147024638;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x85,
            (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\viewactivator.cpp",
            (const char *)0x80070102LL,
            dwCreationFlags);
          goto LABEL_24;
        }
        *((_BYTE *)this + 80) = 1;
        wil::ActivityBase<AAMTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v18);
        LastError = 0;
LABEL_26:
        v18[0] = &AAMTraceProvider::InitCoreUI::`vftable';
        wil::ActivityBase<AAMTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v18);
        wil::ActivityBase<AAMTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<AAMTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v18);
        return LastError;
      }
      v12 = 129;
    }
    else
    {
      v12 = 126;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v12,
                  (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\viewactivator.cpp",
                  v9);
    goto LABEL_26;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x7B,
                (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\viewactivator.cpp",
                v4);
LABEL_24:
  AAMTraceProvider::InitCoreUI::~InitCoreUI((AAMTraceProvider::InitCoreUI *)v18);
  return LastError;
}

```

## disassembly

```asm
0x18001bb4c  mov     [rsp-8+arg_8], rbx
0x18001bb51  mov     [rsp-8+arg_10], rsi
0x18001bb56  push    rbp
0x18001bb57  push    rdi
0x18001bb58  push    r13
0x18001bb5a  push    r14
0x18001bb5c  push    r15
0x18001bb5e  lea     rbp, [rsp-0C0h]
0x18001bb66  sub     rsp, 1C0h
0x18001bb6d  mov     rax, cs:__security_cookie
0x18001bb74  xor     rax, rsp
0x18001bb77  mov     [rbp+0E0h+var_30], rax
0x18001bb7e  mov     rbx, rcx
0x18001bb81  cmp     byte ptr [rcx+50h], 0
0x18001bb85  jz      short loc_18001BB8E
0x18001bb87  xor     eax, eax
0x18001bb89  jmp     loc_18001BD8C
0x18001bb8e  lea     rdx, aInitcoreui; "InitCoreUI"
0x18001bb95  lea     rcx, [rsp+1E0h+var_180]
0x18001bb9a  call    ??0?$ActivityBase@VAAMTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<AAMTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AAMTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18001bb9f  lea     r13, ??_7InitCoreUI@AAMTraceProvider@@6B@; const AAMTraceProvider::InitCoreUI::`vftable'
0x18001bba6  mov     [rsp+1E0h+var_180], r13
0x18001bbab  lea     rcx, [rsp+1E0h+var_180]; this
0x18001bbb0  call    ?StartActivity@InitCoreUI@AAMTraceProvider@@QEAAXXZ; AAMTraceProvider::InitCoreUI::StartActivity(void)
0x18001bbb5  nop
0x18001bbb6  mov     rcx, rbx; this
0x18001bbb9  call    ?ReleaseCoreUI@ViewActivator@@AEAAXXZ; ViewActivator::ReleaseCoreUI(void)
0x18001bbbe  xor     r9d, r9d; lpName
0x18001bbc1  xor     r8d, r8d; bInitialState
0x18001bbc4  lea     edx, [r9+1]; bManualReset
0x18001bbc8  xor     ecx, ecx; lpEventAttributes
0x18001bbca  call    cs:__imp_CreateEventW
0x18001bbd0  mov     rdi, rax
0x18001bbd3  lea     r14, [rbx+28h]
0x18001bbd7  lea     rax, [rsp+1E0h+var_198]
0x18001bbdc  cmp     r14, rax
0x18001bbdf  jz      short loc_18001BC10
0x18001bbe1  mov     rsi, [r14]
0x18001bbe4  lea     rdx, [rsi-1]
0x18001bbe8  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18001bbec  ja      short loc_18001BC0B
0x18001bbee  lea     rcx, [rsp+1E0h+var_1B0]; this
0x18001bbf3  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001bbf8  mov     rcx, rsi; hObject
0x18001bbfb  call    cs:__imp_CloseHandle
0x18001bc01  lea     rcx, [rsp+1E0h+var_1B0]; this
0x18001bc06  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001bc0b  mov     [r14], rdi
0x18001bc0e  jmp     short loc_18001BC23
0x18001bc10  lea     rax, [rdi-1]
0x18001bc14  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001bc18  ja      short loc_18001BC23
0x18001bc1a  mov     rcx, rdi; hObject
0x18001bc1d  call    cs:__imp_CloseHandle
0x18001bc23  mov     rax, [r14]
0x18001bc26  inc     rax
0x18001bc29  test    rax, 0FFFFFFFFFFFFFFFEh
0x18001bc2f  jnz     short loc_18001BC50
0x18001bc31  mov     rcx, [rbp+0E8h]; this
0x18001bc38  lea     r8, aOnecoreuapBase_20; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18001bc3f  mov     edx, 7Bh ; '{'; void *
0x18001bc44  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001bc49  mov     ebx, eax
0x18001bc4b  jmp     loc_18001BD55
0x18001bc50  mov     [rsp+1E0h+lpThreadId], 0; lpThreadId
0x18001bc59  mov     [rsp+1E0h+dwCreationFlags], 0; int
0x18001bc61  mov     r9, rbx; lpParameter
0x18001bc64  lea     r8, ?MessageSessionThreadProc@ViewActivator@@CAKPEAX@Z; lpStartAddress
0x18001bc6b  xor     edx, edx; dwStackSize
0x18001bc6d  xor     ecx, ecx; lpThreadAttributes
0x18001bc6f  call    cs:__imp_CreateThread
0x18001bc75  mov     rsi, rax
0x18001bc78  lea     rdi, [rbx+30h]
0x18001bc7c  lea     rax, [rsp+1E0h+var_190]
0x18001bc81  cmp     rdi, rax
0x18001bc84  jz      short loc_18001BCB5
0x18001bc86  mov     r15, [rdi]
0x18001bc89  lea     rdx, [r15-1]
0x18001bc8d  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18001bc91  ja      short loc_18001BCB0
0x18001bc93  lea     rcx, [rsp+1E0h+var_1B0]; this
0x18001bc98  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001bc9d  mov     rcx, r15; hObject
0x18001bca0  call    cs:__imp_CloseHandle
0x18001bca6  lea     rcx, [rsp+1E0h+var_1B0]; this
0x18001bcab  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001bcb0  mov     [rdi], rsi
0x18001bcb3  jmp     short loc_18001BCC8
0x18001bcb5  lea     rax, [rsi-1]
0x18001bcb9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001bcbd  ja      short loc_18001BCC8
0x18001bcbf  mov     rcx, rsi; hObject
0x18001bcc2  call    cs:__imp_CloseHandle
0x18001bcc8  mov     rcx, [rdi]; hThread
0x18001bccb  lea     rax, [rcx+1]
0x18001bccf  test    rax, 0FFFFFFFFFFFFFFFEh
0x18001bcd5  jnz     short loc_18001BCDE
0x18001bcd7  mov     edx, 7Eh ; '~'
0x18001bcdc  jmp     short loc_18001BCF2
0x18001bcde  mov     esi, 2
0x18001bce3  mov     edx, esi; nPriority
0x18001bce5  call    cs:__imp_SetThreadPriority
0x18001bceb  test    eax, eax
0x18001bced  jnz     short loc_18001BD09
0x18001bcef  lea     edx, [rsi+7Fh]; void *
0x18001bcf2  lea     r8, aOnecoreuapBase_20; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18001bcf9  mov     rcx, [rbp+0E8h]; this
0x18001bd00  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001bd05  mov     ebx, eax
0x18001bd07  jmp     short loc_18001BD71
0x18001bd09  mov     rax, [r14]
0x18001bd0c  mov     [rsp+1E0h+Handles], rax
0x18001bd11  mov     rax, [rdi]
0x18001bd14  mov     [rsp+1E0h+var_1A0], rax
0x18001bd19  mov     r9d, [rbx+80h]; dwMilliseconds
0x18001bd20  xor     r8d, r8d; bWaitAll
0x18001bd23  lea     rdx, [rsp+1E0h+Handles]; lpHandles
0x18001bd28  mov     ecx, esi; nCount
0x18001bd2a  call    cs:__imp_WaitForMultipleObjects
0x18001bd30  test    eax, eax
0x18001bd32  jz      short loc_18001BD61
0x18001bd34  mov     rcx, [rbp+0E8h]; this
0x18001bd3b  mov     ebx, 80070102h
0x18001bd40  mov     r9d, ebx; char *
0x18001bd43  lea     r8, aOnecoreuapBase_20; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18001bd4a  mov     edx, 85h; void *
0x18001bd4f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bd54  nop
0x18001bd55  lea     rcx, [rsp+1E0h+var_180]; this
0x18001bd5a  call    ??1InitCoreUI@AAMTraceProvider@@QEAA@XZ; AAMTraceProvider::InitCoreUI::~InitCoreUI(void)
0x18001bd5f  jmp     short loc_18001BD8A
0x18001bd61  mov     byte ptr [rbx+50h], 1
0x18001bd65  lea     rcx, [rsp+1E0h+var_180]
0x18001bd6a  call    ?Stop@?$ActivityBase@VAAMTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<AAMTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18001bd6f  xor     ebx, ebx
0x18001bd71  mov     [rsp+1E0h+var_180], r13
0x18001bd76  lea     rcx, [rsp+1E0h+var_180]
0x18001bd7b  call    ?Destroy@?$ActivityBase@VAAMTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<AAMTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001bd80  lea     rcx, [rsp+1E0h+var_180]
0x18001bd85  call    ??1?$ActivityBase@VAAMTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<AAMTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<AAMTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001bd8a  mov     eax, ebx
0x18001bd8c  mov     rcx, [rbp+0E0h+var_30]
0x18001bd93  xor     rcx, rsp; StackCookie
0x18001bd96  call    __security_check_cookie
0x18001bd9b  lea     r11, [rsp+1E0h+var_20]
0x18001bda3  mov     rbx, [r11+38h]
0x18001bda7  mov     rsi, [r11+40h]
0x18001bdab  mov     rsp, r11
0x18001bdae  pop     r15
0x18001bdb0  pop     r14
0x18001bdb2  pop     r13
0x18001bdb4  pop     rdi
0x18001bdb5  pop     rbp
0x18001bdb6  retn
```
