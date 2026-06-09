# CallMsiAdvertiseScript(ushort const *,ulong,HKEY__ * *,int)

- ea: `0x180005a48`
- end: `0x180005c31`
- name: `?CallMsiAdvertiseScript@@YAKPEBGKPEAPEAUHKEY__@@H@Z`
- size: `489`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int, HKEY *, int)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180003370`
- `0x180005294`
- `0x180008fe4`

## callees

- `0x180005a48`
- `0x18001b1a0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180005aa5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180005aa5`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180005b3f`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180005b3f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180005abf`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180005abf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ac9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ad6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005bcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ac9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ad6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005bcd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005b5e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005be6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005bfc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005c1a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005b5e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005be6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005bfc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005c1a`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180005b07`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180005b07`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180005b11`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180005b11`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180005bbf`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180005bbf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005bd8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005bd8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005a7d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005a7d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180005b8c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180005b8c`

## pseudocode

```c
__int64 __fastcall CallMsiAdvertiseScript(const unsigned __int16 *a1, int a2, HKEY *a3, int a4)
{
  _DWORD *v8; // rax
  HLOCAL v9; // rdi
  DWORD LastError; // ebx
  HANDLE Thread; // rsi
  int v12; // ebp
  HANDLE CurrentThread; // rax
  HANDLE v14; // rax
  void *v15; // rcx
  HANDLE hObject; // [rsp+30h] [rbp-48h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-40h] BYREF

  TokenHandle = 0;
  hObject = 0;
  v8 = LocalAlloc(0x40u, 0x30u);
  v9 = v8;
  if ( !v8 )
  {
    LastError = 14;
    goto LABEL_25;
  }
  Thread = 0;
  v12 = 0;
  *(_QWORD *)v8 = a1;
  v8[2] = a2;
  *((_QWORD *)v8 + 2) = a3;
  v8[6] = a4;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xEu, 1, &TokenHandle) && GetLastError() != 1008 )
    goto LABEL_5;
  if ( !TokenHandle )
  {
LABEL_9:
    v14 = hObject;
    hObject = 0;
    *((_QWORD *)v9 + 4) = v14;
    Thread = CreateThread(0, 0, CallMsiAdvertiseScriptThread, v9, 0, 0);
    if ( Thread )
    {
      if ( *(_DWORD *)&gDebugLevel )
        _DebugMsg(4u, 0xCB7u);
      LastError = WaitForSingleObject(Thread, 0xFFFFFFFF);
      if ( *(_DWORD *)&gDebugLevel )
        _DebugMsg(4u, 0xCB8u);
    }
    else
    {
      LastError = GetLastError();
      v15 = (void *)*((_QWORD *)v9 + 4);
      if ( v15 )
      {
        CloseHandle(v15);
        *((_QWORD *)v9 + 4) = 0;
      }
    }
    goto LABEL_16;
  }
  if ( DuplicateTokenEx(TokenHandle, 0xEu, 0, SecurityImpersonation, TokenImpersonation, &hObject) )
  {
    RevertToSelf();
    v12 = 1;
    goto LABEL_9;
  }
LABEL_5:
  LastError = GetLastError();
LABEL_16:
  if ( !LastError )
    LastError = *((_DWORD *)v9 + 10);
  if ( v12 && TokenHandle && !ImpersonateLoggedOnUser(TokenHandle) && !LastError )
    LastError = GetLastError();
  LocalFree(v9);
  if ( Thread )
    CloseHandle(Thread);
LABEL_25:
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x180005a48  push    rbx
0x180005a4a  push    rbp
0x180005a4b  push    rsi
0x180005a4c  push    rdi
0x180005a4d  push    r12
0x180005a4f  push    r14
0x180005a51  push    r15
0x180005a53  sub     rsp, 40h
0x180005a57  mov     ebx, r9d
0x180005a5a  mov     r14, r8
0x180005a5d  mov     r15d, edx
0x180005a60  mov     r12, rcx
0x180005a63  mov     [rsp+78h+TokenHandle], 0
0x180005a6c  mov     [rsp+78h+hObject], 0
0x180005a75  mov     edx, 30h ; '0'; uBytes
0x180005a7a  lea     ecx, [rdx+10h]; uFlags
0x180005a7d  call    cs:__imp_LocalAlloc
0x180005a83  mov     rdi, rax
0x180005a86  test    rax, rax
0x180005a89  jnz     short loc_180005A93
0x180005a8b  lea     ebx, [rax+0Eh]
0x180005a8e  jmp     loc_180005BED
0x180005a93  xor     esi, esi
0x180005a95  xor     ebp, ebp
0x180005a97  mov     [rax], r12
0x180005a9a  mov     [rax+8], r15d
0x180005a9e  mov     [rax+10h], r14
0x180005aa2  mov     [rax+18h], ebx
0x180005aa5  call    cs:__imp_GetCurrentThread
0x180005aab  lea     r9, [rsp+78h+TokenHandle]; TokenHandle
0x180005ab0  lea     r14d, [rsi+1]
0x180005ab4  mov     r8d, r14d; OpenAsSelf
0x180005ab7  lea     ebx, [rsi+0Eh]
0x180005aba  mov     edx, ebx; DesiredAccess
0x180005abc  mov     rcx, rax; ThreadHandle
0x180005abf  call    cs:__imp_OpenThreadToken
0x180005ac5  test    eax, eax
0x180005ac7  jnz     short loc_180005AE3
0x180005ac9  call    cs:__imp_GetLastError
0x180005acf  cmp     eax, 3F0h
0x180005ad4  jz      short loc_180005AE3
0x180005ad6  call    cs:__imp_GetLastError
0x180005adc  mov     ebx, eax
0x180005ade  jmp     loc_180005BAA
0x180005ae3  mov     rcx, [rsp+78h+TokenHandle]; hExistingToken
0x180005ae8  test    rcx, rcx
0x180005aeb  jz      short loc_180005B1A
0x180005aed  lea     rax, [rsp+78h+hObject]
0x180005af2  mov     [rsp+78h+phNewToken], rax; phNewToken
0x180005af7  mov     r9d, 2; ImpersonationLevel
0x180005afd  mov     [rsp+78h+TokenType], r9d; TokenType
0x180005b02  xor     r8d, r8d; lpTokenAttributes
0x180005b05  mov     edx, ebx; dwDesiredAccess
0x180005b07  call    cs:__imp_DuplicateTokenEx
0x180005b0d  test    eax, eax
0x180005b0f  jz      short loc_180005AD6
0x180005b11  call    cs:__imp_RevertToSelf
0x180005b17  mov     ebp, r14d
0x180005b1a  mov     rax, [rsp+78h+hObject]
0x180005b1f  mov     [rsp+78h+hObject], rsi
0x180005b24  mov     [rdi+20h], rax
0x180005b28  mov     [rsp+78h+phNewToken], rsi; lpThreadId
0x180005b2d  mov     [rsp+78h+TokenType], esi; dwCreationFlags
0x180005b31  mov     r9, rdi; lpParameter
0x180005b34  lea     r8, ?CallMsiAdvertiseScriptThread@@YAKPEAUMSI_ADVERTISE_SCRIPT_PARAM@@@Z; lpStartAddress
0x180005b3b  xor     edx, edx; dwStackSize
0x180005b3d  xor     ecx, ecx; lpThreadAttributes
0x180005b3f  call    cs:__imp_CreateThread
0x180005b45  mov     rsi, rax
0x180005b48  test    rax, rax
0x180005b4b  jnz     short loc_180005B6A
0x180005b4d  call    cs:__imp_GetLastError
0x180005b53  mov     ebx, eax
0x180005b55  mov     rcx, [rdi+20h]; hObject
0x180005b59  test    rcx, rcx
0x180005b5c  jz      short loc_180005BAA
0x180005b5e  call    cs:__imp_CloseHandle
0x180005b64  mov     [rdi+20h], rsi
0x180005b68  jmp     short loc_180005BAA
0x180005b6a  mov     r14d, 4
0x180005b70  cmp     cs:?gDebugLevel@@3KA, 0; ulong gDebugLevel
0x180005b77  jz      short loc_180005B86
0x180005b79  mov     edx, 0CB7h; unsigned int
0x180005b7e  mov     ecx, r14d; unsigned int
0x180005b81  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x180005b86  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180005b89  mov     rcx, rsi; hHandle
0x180005b8c  call    cs:__imp_WaitForSingleObject
0x180005b92  mov     ebx, eax
0x180005b94  cmp     cs:?gDebugLevel@@3KA, 0; ulong gDebugLevel
0x180005b9b  jz      short loc_180005BAA
0x180005b9d  mov     edx, 0CB8h; unsigned int
0x180005ba2  mov     ecx, r14d; unsigned int
0x180005ba5  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x180005baa  test    ebx, ebx
0x180005bac  jnz     short loc_180005BB1
0x180005bae  mov     ebx, [rdi+28h]
0x180005bb1  test    ebp, ebp
0x180005bb3  jz      short loc_180005BD5
0x180005bb5  mov     rcx, [rsp+78h+TokenHandle]; hToken
0x180005bba  test    rcx, rcx
0x180005bbd  jz      short loc_180005BD5
0x180005bbf  call    cs:__imp_ImpersonateLoggedOnUser
0x180005bc5  test    eax, eax
0x180005bc7  jnz     short loc_180005BD5
0x180005bc9  test    ebx, ebx
0x180005bcb  jnz     short loc_180005BD5
0x180005bcd  call    cs:__imp_GetLastError
0x180005bd3  mov     ebx, eax
0x180005bd5  mov     rcx, rdi; hMem
0x180005bd8  call    cs:__imp_LocalFree
0x180005bde  test    rsi, rsi
0x180005be1  jz      short loc_180005BED
0x180005be3  mov     rcx, rsi; hObject
0x180005be6  call    cs:__imp_CloseHandle
0x180005bec  nop
0x180005bed  mov     rcx, [rsp+78h+hObject]; hObject
0x180005bf2  lea     rax, [rcx-1]
0x180005bf6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180005bfa  ja      short loc_180005C0B
0x180005bfc  call    cs:__imp_CloseHandle
0x180005c02  mov     [rsp+78h+hObject], 0
0x180005c0b  mov     rcx, [rsp+78h+TokenHandle]; hObject
0x180005c10  lea     rax, [rcx-1]
0x180005c14  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180005c18  ja      short loc_180005C20
0x180005c1a  call    cs:__imp_CloseHandle
0x180005c20  mov     eax, ebx
0x180005c22  add     rsp, 40h
0x180005c26  pop     r15
0x180005c28  pop     r14
0x180005c2a  pop     r12
0x180005c2c  pop     rdi
0x180005c2d  pop     rsi
0x180005c2e  pop     rbp
0x180005c2f  pop     rbx
0x180005c30  retn
```
