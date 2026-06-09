# MsoCrashMainThread(void const *)

- ea: `0x180640af0`
- end: `0x180640d6e`
- name: `?MsoCrashMainThread@@YAKPEBX@Z`
- size: `638`
- prototype: `unsigned int __fastcall(const void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1806409c0`

## callees

- `0x180190732`
- `0x180192520`
- `0x180192560`
- `0x180640af0`
- `0x1807583b8`
- `0x180758484`
- `0x180758568`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180640be4`
- `KERNEL32!GetLastError` at `0x180640c69`
- `KERNEL32!GetLastError` at `0x180640be4`
- `KERNEL32!GetLastError` at `0x180640c69`
- `KERNEL32!Sleep` at `0x180640cb4`
- `KERNEL32!Sleep` at `0x180640cf5`
- `KERNEL32!Sleep` at `0x180640cb4`
- `KERNEL32!Sleep` at `0x180640cf5`
- `KERNEL32!GetCurrentThreadId` at `0x180640b3e`
- `KERNEL32!GetCurrentThreadId` at `0x180640b3e`
- `KERNEL32!CloseHandle` at `0x180640d0d`
- `KERNEL32!CloseHandle` at `0x180640d29`
- `KERNEL32!CloseHandle` at `0x180640d0d`
- `KERNEL32!CloseHandle` at `0x180640d29`
- `KERNEL32!RaiseException` at `0x180640d20`
- `KERNEL32!RaiseException` at `0x180640d20`
- `KERNEL32!SuspendThread` at `0x180640bc4`
- `KERNEL32!SuspendThread` at `0x180640d38`
- `KERNEL32!SuspendThread` at `0x180640bc4`
- `KERNEL32!SuspendThread` at `0x180640d38`
- `KERNEL32!GetThreadContext` at `0x180640bda`
- `KERNEL32!GetThreadContext` at `0x180640bda`
- `KERNEL32!ResumeThread` at `0x180640c7d`
- `KERNEL32!ResumeThread` at `0x180640c7d`
- `KERNEL32!OpenThread` at `0x180640b54`
- `KERNEL32!OpenThread` at `0x180640b7f`
- `KERNEL32!OpenThread` at `0x180640b54`
- `KERNEL32!OpenThread` at `0x180640b7f`
- `KERNEL32!SetThreadContext` at `0x180640c5f`
- `KERNEL32!SetThreadContext` at `0x180640c5f`
- `KERNEL32!SetThreadPriority` at `0x180640c90`
- `KERNEL32!SetThreadPriority` at `0x180640c90`
- `KERNEL32!QueueUserAPC` at `0x180640cdf`
- `KERNEL32!QueueUserAPC` at `0x180640cdf`
- `KERNEL32!GetCurrentThread` at `0x180640d2f`
- `KERNEL32!GetCurrentThread` at `0x180640d2f`
- `KERNEL32!ExitThread` at `0x180640d40`
- `KERNEL32!ExitThread` at `0x180640d40`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180640ba0`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180640bef`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180640c74`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180640ba0`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180640bef`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180640c74`
- `Mso20Win32Client!__imp_?IsMainThread@Threadpool@Mso@@YA_NXZ` at `0x180640b63`
- `Mso20Win32Client!__imp_?IsMainThread@Threadpool@Mso@@YA_NXZ` at `0x180640b63`
- `Mso20Win32Client!__imp_MsoWaitForSingleObject` at `0x180640ca7`
- `Mso20Win32Client!__imp_MsoWaitForSingleObject` at `0x180640ca7`
- `Mso20Win32Client!__imp_?GetMainThreadId@Threadpool@Mso@@YAKXZ` at `0x180640b71`
- `Mso20Win32Client!__imp_?GetMainThreadId@Threadpool@Mso@@YAKXZ` at `0x180640b71`

## pseudocode

```c
__int64 __fastcall MsoCrashMainThread(DWORD *a1)
{
  Mso::Threadpool *v2; // rcx
  char v3; // si
  DWORD v4; // ebx
  HANDLE v5; // rbx
  Mso::Threadpool *v6; // rcx
  DWORD MainThreadId; // eax
  HANDLE CurrentThread; // rax
  struct _CONTEXT Context; // [rsp+30h] [rbp-4E8h] BYREF

  memset_0(&Context, 0, sizeof(Context));
  v3 = 0;
  if ( a1 )
  {
    v4 = *a1;
    if ( v4 )
    {
      if ( v4 == GetCurrentThreadId() )
        return 0;
      v5 = OpenThread(0x5Au, 0, v4);
      if ( v5 != (HANDLE)-1LL )
        goto LABEL_7;
    }
  }
  if ( !Mso::Threadpool::IsMainThread(v2) )
  {
    MainThreadId = Mso::Threadpool::GetMainThreadId(v6);
    v5 = OpenThread(0x5Au, 0, MainThreadId);
    if ( v5 != (HANDLE)-1LL )
    {
LABEL_7:
      if ( v5 )
      {
        MsoShipAssertTagProc(17129620);
        if ( _InterlockedIncrement(&dword_180FB076C) == 1 )
        {
          v3 = 1;
          SuspendThread(v5);
          Context.ContextFlags = 1048577;
          if ( !GetThreadContext(v5, &Context) )
          {
            GetLastError();
            MsoShipAssertTagProc(2894036);
          }
          sub_1807583B8();
          if ( (unsigned __int8)sub_180758568() )
          {
            ((void (__fastcall *)(void (__stdcall *)(ULONG_PTR), HANDLE, _QWORD, __int64))pQueueUserAPC2)(
              CrashNowAPCProc,
              v5,
              0,
              1);
          }
          else
          {
            Context.Rsp = (Context.Rsp - 16) | 8;
            *(_QWORD *)Context.Rsp = sub_180758560;
            Context.Rip = (DWORD64)sub_180758430;
            if ( !SetThreadContext(v5, &Context) )
            {
              GetLastError();
              MsoShipAssertTagProc(2894037);
            }
          }
          while ( ResumeThread(v5) > 1 )
            ;
          SetThreadPriority(v5, 15);
          if ( hFirstCrashAttemptComplete )
            MsoWaitForSingleObject(hFirstCrashAttemptComplete, 1000);
          else
            Sleep(0x3E8u);
          if ( !(unsigned __int8)sub_180758568() && !(unsigned __int8)sub_180758484(v5) )
            QueueUserAPC(CrashNowAPCProc, v5, 0);
        }
        if ( v3 )
        {
          Sleep(0x2710u);
          if ( !(unsigned __int8)sub_180758484(v5) )
          {
            CloseHandle(v5);
            RaiseException(0xE0000003, 0, 0, 0);
          }
        }
        CloseHandle(v5);
        CurrentThread = GetCurrentThread();
        SuspendThread(CurrentThread);
        ExitThread(0);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180640af0  mov     [rsp+arg_8], rbx
0x180640af5  mov     [rsp+arg_10], rsi
0x180640afa  push    rdi
0x180640afb  sub     rsp, 510h
0x180640b02  mov     rax, cs:__security_cookie
0x180640b09  xor     rax, rsp
0x180640b0c  mov     [rsp+518h+var_18], rax
0x180640b14  mov     rbx, rcx
0x180640b17  xor     edx, edx; Val
0x180640b19  mov     r8d, 4D0h; Size
0x180640b1f  lea     rcx, [rsp+518h+Context]; void *
0x180640b24  call    memset_0
0x180640b29  xor     sil, sil
0x180640b2c  lea     rdi, sub_180758430
0x180640b33  test    rbx, rbx
0x180640b36  jz      short loc_180640B63
0x180640b38  mov     ebx, [rbx]
0x180640b3a  test    ebx, ebx
0x180640b3c  jz      short loc_180640B63
0x180640b3e  call    cs:__imp_GetCurrentThreadId
0x180640b44  cmp     ebx, eax
0x180640b46  jz      loc_180640D47
0x180640b4c  mov     r8d, ebx; dwThreadId
0x180640b4f  xor     edx, edx; bInheritHandle
0x180640b51  lea     ecx, [rdx+5Ah]; dwDesiredAccess
0x180640b54  call    cs:__imp_OpenThread
0x180640b5a  mov     rbx, rax
0x180640b5d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180640b61  jnz     short loc_180640B92
0x180640b63  call    cs:__imp_?IsMainThread@Threadpool@Mso@@YA_NXZ; Mso::Threadpool::IsMainThread(void)
0x180640b69  test    al, al
0x180640b6b  jnz     loc_180640D47
0x180640b71  call    cs:__imp_?GetMainThreadId@Threadpool@Mso@@YAKXZ; Mso::Threadpool::GetMainThreadId(void)
0x180640b77  mov     r8d, eax; dwThreadId
0x180640b7a  xor     edx, edx; bInheritHandle
0x180640b7c  lea     ecx, [rdx+5Ah]; dwDesiredAccess
0x180640b7f  call    cs:__imp_OpenThread
0x180640b85  mov     rbx, rax
0x180640b88  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180640b8c  jz      loc_180640D47
0x180640b92  test    rbx, rbx
0x180640b95  jz      loc_180640D47
0x180640b9b  mov     ecx, 1056094h
0x180640ba0  call    cs:__imp_MsoShipAssertTagProc
0x180640ba6  mov     eax, 1
0x180640bab  lock xadd cs:dword_180FB076C, eax
0x180640bb3  inc     eax
0x180640bb5  cmp     eax, 1
0x180640bb8  jnz     loc_180640CE5
0x180640bbe  mov     sil, al
0x180640bc1  mov     rcx, rbx; hThread
0x180640bc4  call    cs:__imp_SuspendThread
0x180640bca  mov     [rsp+518h+Context.ContextFlags], 100001h
0x180640bd2  lea     rdx, [rsp+518h+Context]; lpContext
0x180640bd7  mov     rcx, rbx; hThread
0x180640bda  call    cs:__imp_GetThreadContext
0x180640be0  test    eax, eax
0x180640be2  jnz     short loc_180640BF5
0x180640be4  call    cs:__imp_GetLastError
0x180640bea  mov     ecx, 2C28D4h
0x180640bef  call    cs:__imp_MsoShipAssertTagProc
0x180640bf5  call    sub_1807583B8
0x180640bfa  call    sub_180758568
0x180640bff  test    al, al
0x180640c01  jz      short loc_180640C2D
0x180640c03  mov     r9d, 1
0x180640c09  xor     r8d, r8d
0x180640c0c  mov     rdx, rbx
0x180640c0f  lea     rcx, ?CrashNowAPCProc@@YAX_K@Z; CrashNowAPCProc(unsigned __int64)
0x180640c16  mov     rax, cs:?pQueueUserAPC2@@3P6AHP6AX_K@ZPEAX0W4_QUEUE_USER_APC_FLAGS@@@ZEA; int (*pQueueUserAPC2)(void (*)(unsigned __int64),void *,unsigned __int64,_QUEUE_USER_APC_FLAGS)
0x180640c1d  call    cs:__guard_dispatch_icall_fptr
0x180640c23  mov     rdi, [rsp+518h+Context.Rip]
0x180640c2b  jmp     short loc_180640C7A
0x180640c2d  mov     rax, [rsp+518h+Context.Rsp]
0x180640c35  add     rax, 0FFFFFFFFFFFFFFF0h
0x180640c39  or      rax, 8
0x180640c3d  mov     [rsp+518h+Context.Rsp], rax
0x180640c45  lea     rcx, sub_180758560
0x180640c4c  mov     [rax], rcx
0x180640c4f  mov     [rsp+518h+Context.Rip], rdi
0x180640c57  lea     rdx, [rsp+518h+Context]; lpContext
0x180640c5c  mov     rcx, rbx; hThread
0x180640c5f  call    cs:__imp_SetThreadContext
0x180640c65  test    eax, eax
0x180640c67  jnz     short loc_180640C7A
0x180640c69  call    cs:__imp_GetLastError
0x180640c6f  mov     ecx, 2C28D5h
0x180640c74  call    cs:__imp_MsoShipAssertTagProc
0x180640c7a  mov     rcx, rbx; hThread
0x180640c7d  call    cs:__imp_ResumeThread
0x180640c83  cmp     eax, 1
0x180640c86  ja      short loc_180640C7A
0x180640c88  mov     edx, 0Fh; nPriority
0x180640c8d  mov     rcx, rbx; hThread
0x180640c90  call    cs:__imp_SetThreadPriority
0x180640c96  mov     rcx, cs:?hFirstCrashAttemptComplete@@3PEAXEA; void * hFirstCrashAttemptComplete
0x180640c9d  test    rcx, rcx
0x180640ca0  jz      short loc_180640CAF
0x180640ca2  mov     edx, 3E8h
0x180640ca7  call    cs:__imp_MsoWaitForSingleObject
0x180640cad  jmp     short loc_180640CBA
0x180640caf  mov     ecx, 3E8h; dwMilliseconds
0x180640cb4  call    cs:__imp_Sleep
0x180640cba  call    sub_180758568
0x180640cbf  test    al, al
0x180640cc1  jnz     short loc_180640CE5
0x180640cc3  mov     rdx, rdi
0x180640cc6  mov     rcx, rbx; hThread
0x180640cc9  call    sub_180758484
0x180640cce  test    al, al
0x180640cd0  jnz     short loc_180640CE5
0x180640cd2  xor     r8d, r8d; dwData
0x180640cd5  mov     rdx, rbx; hThread
0x180640cd8  lea     rcx, ?CrashNowAPCProc@@YAX_K@Z; pfnAPC
0x180640cdf  call    cs:__imp_QueueUserAPC
0x180640ce5  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180640ce9  jz      short loc_180640D2F
0x180640ceb  test    sil, sil
0x180640cee  jz      short loc_180640D26
0x180640cf0  mov     ecx, 2710h; dwMilliseconds
0x180640cf5  call    cs:__imp_Sleep
0x180640cfb  mov     rdx, rdi
0x180640cfe  mov     rcx, rbx; hThread
0x180640d01  call    sub_180758484
0x180640d06  test    al, al
0x180640d08  jnz     short loc_180640D26
0x180640d0a  mov     rcx, rbx; hObject
0x180640d0d  call    cs:__imp_CloseHandle
0x180640d13  xor     r9d, r9d; lpArguments
0x180640d16  xor     r8d, r8d; nNumberOfArguments
0x180640d19  xor     edx, edx; dwExceptionFlags
0x180640d1b  mov     ecx, 0E0000003h; dwExceptionCode
0x180640d20  call    cs:__imp_RaiseException
0x180640d26  mov     rcx, rbx; hObject
0x180640d29  call    cs:__imp_CloseHandle
0x180640d2f  call    cs:__imp_GetCurrentThread
0x180640d35  mov     rcx, rax; hThread
0x180640d38  call    cs:__imp_SuspendThread
0x180640d3e  xor     ecx, ecx; dwExitCode
0x180640d40  call    cs:__imp_ExitThread
0x180640d47  xor     eax, eax
0x180640d49  mov     rcx, [rsp+518h+var_18]
0x180640d51  xor     rcx, rsp; StackCookie
0x180640d54  call    __security_check_cookie
0x180640d59  lea     r11, [rsp+518h+var_8]
0x180640d61  mov     rbx, [r11+18h]
0x180640d65  mov     rsi, [r11+20h]
0x180640d69  mov     rsp, r11
0x180640d6c  pop     rdi
0x180640d6d  retn
```
