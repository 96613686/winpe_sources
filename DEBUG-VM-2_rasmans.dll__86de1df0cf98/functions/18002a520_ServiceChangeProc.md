# ServiceChangeProc

- ea: `0x18002a520`
- end: `0x18002a758`
- name: `ServiceChangeProc`
- size: `568`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x18002a520`
- `0x1800e7206`
- `0x1800e7260`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a5c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a62f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a5c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a62f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002a67c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002a67c`
- `api-ms-win-service-winsvc-l1-1-0!NotifyServiceStatusChangeA` at `0x18002a6c0`
- `api-ms-win-service-winsvc-l1-1-0!NotifyServiceStatusChangeA` at `0x18002a6c0`
- `api-ms-win-service-winsvc-l1-1-0!OpenSCManagerA` at `0x18002a5b3`
- `api-ms-win-service-winsvc-l1-1-0!OpenSCManagerA` at `0x18002a5b3`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x18002a61d`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x18002a61d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002a6fa`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002a708`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002a6fa`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002a708`

## string_xrefs

- `0x18002a5aa`: `ServicesActive`

## pseudocode

```c
__int64 __fastcall ServiceChangeProc(PVOID Parameter)
{
  SC_HANDLE v1; // rax
  SC_HANDLE v2; // rsi
  DWORD v3; // eax
  DWORD v4; // ebx
  struct _LIST_ENTRY *v5; // rcx
  SC_HANDLE v6; // rdi
  DWORD LastError; // eax
  struct _LIST_ENTRY *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r9
  DWORD v11; // eax
  DWORD v12; // eax
  SERVICE_NOTIFY_2A pNotifyBuffer; // [rsp+20h] [rbp-98h] BYREF

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 185, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
  }
  *(&pNotifyBuffer.dwVersion + 1) = 0;
  memset_0(&pNotifyBuffer, 0, 0x4Cu);
  pNotifyBuffer.dwVersion = 2;
  pNotifyBuffer.pfnNotifyCallback = (PFN_SC_NOTIFY_CALLBACK)MpssvcNotifcationCallBack;
  v1 = OpenSCManagerA(0, "ServicesActive", 1u);
  v2 = v1;
  if ( v1 )
  {
    v6 = OpenServiceA(v1, "MPSSVC", 4u);
    if ( v6 )
    {
      while ( 1 )
      {
        v12 = NotifyServiceStatusChangeA(v6, 4u, &pNotifyBuffer);
        v4 = v12;
        if ( v12 )
          break;
        v11 = WaitForSingleObjectEx(g_hExitServiceChangeThread, 0xFFFFFFFF, 1);
        v4 = v11;
        if ( !v11 )
          goto LABEL_28;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 189, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v11);
        }
      }
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
        goto LABEL_28;
      }
      v9 = 188;
      v10 = v12;
    }
    else
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( !LastError
        || (v8 = WPP_GLOBAL_Control, WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control)
        || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
LABEL_28:
        CloseServiceHandle(v2);
        if ( v6 )
          CloseServiceHandle(v6);
        goto LABEL_30;
      }
      v9 = 187;
      v10 = LastError;
    }
    WPP_SF_d(v8[1].Flink, v9, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v10);
    goto LABEL_28;
  }
  v3 = GetLastError();
  v4 = v3;
  if ( !v3 )
  {
LABEL_30:
    v5 = WPP_GLOBAL_Control;
    goto LABEL_31;
  }
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    return v4;
  if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 186, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v3);
    goto LABEL_30;
  }
LABEL_31:
  if ( v5 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v5[1].Blink) & 0x2000) != 0
    && BYTE1(v5[1].Blink) >= 6u )
  {
    WPP_SF_d(v5[1].Flink, 190, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v4);
  }
  return v4;
}

```

## disassembly

```asm
0x18002a520  push    rbx
0x18002a522  push    rbp
0x18002a523  push    rsi
0x18002a524  push    rdi
0x18002a525  push    r14
0x18002a527  push    r15
0x18002a529  sub     rsp, 88h
0x18002a530  mov     rax, cs:__security_cookie
0x18002a537  xor     rax, rsp
0x18002a53a  mov     [rsp+0B8h+var_48], rax
0x18002a53f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a546  lea     r14, WPP_GLOBAL_Control
0x18002a54d  lea     r15, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x18002a554  mov     ebp, 2000h
0x18002a559  cmp     rcx, r14
0x18002a55c  jz      short loc_18002A57A
0x18002a55e  test    [rcx+1Ch], ebp
0x18002a561  jz      short loc_18002A57A
0x18002a563  cmp     byte ptr [rcx+19h], 6
0x18002a567  jb      short loc_18002A57A
0x18002a569  mov     rcx, [rcx+10h]
0x18002a56d  mov     edx, 0B9h
0x18002a572  mov     r8, r15
0x18002a575  call    WPP_SF_
0x18002a57a  xor     eax, eax
0x18002a57c  lea     rcx, [rsp+0B8h+pNotifyBuffer]; void *
0x18002a581  xor     edx, edx; Val
0x18002a583  mov     dword ptr [rsp+0B8h+pNotifyBuffer+4], eax
0x18002a587  lea     r8d, [rax+4Ch]; Size
0x18002a58b  call    memset_0
0x18002a590  lea     rax, MpssvcNotifcationCallBack
0x18002a597  mov     [rsp+0B8h+pNotifyBuffer.dwVersion], 2
0x18002a59f  mov     r8d, 1; dwDesiredAccess
0x18002a5a5  mov     [rsp+0B8h+pNotifyBuffer.pfnNotifyCallback], rax
0x18002a5aa  lea     rdx, DatabaseName; "ServicesActive"
0x18002a5b1  xor     ecx, ecx; lpMachineName
0x18002a5b3  call    cs:__imp_OpenSCManagerA
0x18002a5b9  mov     rsi, rax
0x18002a5bc  test    rax, rax
0x18002a5bf  jnz     short loc_18002A60D
0x18002a5c1  call    cs:__imp_GetLastError
0x18002a5c7  mov     ebx, eax
0x18002a5c9  test    eax, eax
0x18002a5cb  jz      loc_18002A70E
0x18002a5d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a5d8  cmp     rcx, r14
0x18002a5db  jz      loc_18002A739
0x18002a5e1  test    [rcx+1Ch], ebp
0x18002a5e4  jz      loc_18002A715
0x18002a5ea  cmp     byte ptr [rcx+19h], 2
0x18002a5ee  jb      loc_18002A715
0x18002a5f4  mov     rcx, [rcx+10h]
0x18002a5f8  mov     edx, 0BAh
0x18002a5fd  mov     r9d, eax
0x18002a600  mov     r8, r15
0x18002a603  call    WPP_SF_d
0x18002a608  jmp     loc_18002A70E
0x18002a60d  mov     r8d, 4; dwDesiredAccess
0x18002a613  lea     rdx, ServiceName; "MPSSVC"
0x18002a61a  mov     rcx, rsi; hSCManager
0x18002a61d  call    cs:__imp_OpenServiceA
0x18002a623  mov     rdi, rax
0x18002a626  test    rax, rax
0x18002a629  jnz     loc_18002A6B3
0x18002a62f  call    cs:__imp_GetLastError
0x18002a635  mov     ebx, eax
0x18002a637  test    eax, eax
0x18002a639  jz      loc_18002A6F7
0x18002a63f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a646  cmp     rcx, r14
0x18002a649  jz      loc_18002A6F7
0x18002a64f  test    [rcx+1Ch], ebp
0x18002a652  jz      loc_18002A6F7
0x18002a658  cmp     byte ptr [rcx+19h], 2
0x18002a65c  jb      loc_18002A6F7
0x18002a662  mov     edx, 0BBh
0x18002a667  mov     r9d, eax
0x18002a66a  jmp     short loc_18002A6EB
0x18002a66c  mov     rcx, cs:g_hExitServiceChangeThread; hHandle
0x18002a673  mov     r8d, 1; bAlertable
0x18002a679  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002a67c  call    cs:__imp_WaitForSingleObjectEx
0x18002a682  mov     ebx, eax
0x18002a684  test    eax, eax
0x18002a686  jz      short loc_18002A6F7
0x18002a688  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a68f  cmp     rcx, r14
0x18002a692  jz      short loc_18002A6B3
0x18002a694  test    [rcx+1Ch], ebp
0x18002a697  jz      short loc_18002A6B3
0x18002a699  cmp     byte ptr [rcx+19h], 2
0x18002a69d  jb      short loc_18002A6B3
0x18002a69f  mov     rcx, [rcx+10h]
0x18002a6a3  mov     edx, 0BDh
0x18002a6a8  mov     r9d, eax
0x18002a6ab  mov     r8, r15
0x18002a6ae  call    WPP_SF_d
0x18002a6b3  lea     r8, [rsp+0B8h+pNotifyBuffer]; pNotifyBuffer
0x18002a6b8  mov     edx, 4; dwNotifyMask
0x18002a6bd  mov     rcx, rdi; hService
0x18002a6c0  call    cs:__imp_NotifyServiceStatusChangeA
0x18002a6c6  mov     ebx, eax
0x18002a6c8  test    eax, eax
0x18002a6ca  jz      short loc_18002A66C
0x18002a6cc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a6d3  cmp     rcx, r14
0x18002a6d6  jz      short loc_18002A6F7
0x18002a6d8  test    [rcx+1Ch], ebp
0x18002a6db  jz      short loc_18002A6F7
0x18002a6dd  cmp     byte ptr [rcx+19h], 2
0x18002a6e1  jb      short loc_18002A6F7
0x18002a6e3  mov     edx, 0BCh
0x18002a6e8  mov     r9d, eax
0x18002a6eb  mov     rcx, [rcx+10h]
0x18002a6ef  mov     r8, r15
0x18002a6f2  call    WPP_SF_d
0x18002a6f7  mov     rcx, rsi; hSCObject
0x18002a6fa  call    cs:__imp_CloseServiceHandle
0x18002a700  test    rdi, rdi
0x18002a703  jz      short loc_18002A70E
0x18002a705  mov     rcx, rdi; hSCObject
0x18002a708  call    cs:__imp_CloseServiceHandle
0x18002a70e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a715  cmp     rcx, r14
0x18002a718  jz      short loc_18002A739
0x18002a71a  test    [rcx+1Ch], ebp
0x18002a71d  jz      short loc_18002A739
0x18002a71f  cmp     byte ptr [rcx+19h], 6
0x18002a723  jb      short loc_18002A739
0x18002a725  mov     rcx, [rcx+10h]
0x18002a729  mov     edx, 0BEh
0x18002a72e  mov     r9d, ebx
0x18002a731  mov     r8, r15
0x18002a734  call    WPP_SF_d
0x18002a739  mov     eax, ebx
0x18002a73b  mov     rcx, [rsp+0B8h+var_48]
0x18002a740  xor     rcx, rsp; StackCookie
0x18002a743  call    __security_check_cookie
0x18002a748  add     rsp, 88h
0x18002a74f  pop     r15
0x18002a751  pop     r14
0x18002a753  pop     rdi
0x18002a754  pop     rsi
0x18002a755  pop     rbp
0x18002a756  pop     rbx
0x18002a757  retn
```
