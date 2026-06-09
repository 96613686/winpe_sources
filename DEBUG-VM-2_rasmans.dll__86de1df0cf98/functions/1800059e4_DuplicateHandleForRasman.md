# DuplicateHandleForRasman

- ea: `0x1800059e4`
- end: `0x180005c65`
- name: `DuplicateHandleForRasman`
- size: `641`
- prototype: `__int64 __fastcall(HANDLE hSourceHandle, DWORD dwProcessId)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x180005d18`
- `0x180025a60`

## callees

- `0x1800059e4`
- `0x180005e0c`
- `0x180005e34`
- `0x180005e74`
- `0x180005ec0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005a4a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005bdd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005a4a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005bdd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180005b69`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180005c1e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180005b69`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180005c1e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005bef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005bef`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180005b98`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180005b98`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180005a60`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180005aed`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180005a60`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180005aed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005afb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ba2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005c30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005afb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ba2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005c30`
- `RPCRT4!RpcImpersonateClient` at `0x180005aa8`
- `RPCRT4!RpcImpersonateClient` at `0x180005aa8`
- `RPCRT4!RpcRevertToSelf` at `0x180005bf9`
- `RPCRT4!RpcRevertToSelf` at `0x180005bf9`

## pseudocode

```c
HANDLE __fastcall DuplicateHandleForRasman(HANDLE hSourceHandle, DWORD dwProcessId)
{
  int v4; // esi
  HANDLE v5; // rbx
  DWORD LastError; // eax
  DWORD v7; // eax
  struct _LIST_ENTRY *v8; // rcx
  __int64 v9; // rdx
  DWORD v10; // eax
  HANDLE CurrentProcess; // rax
  DWORD v12; // eax
  HANDLE TargetHandle; // [rsp+80h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 10, WPP_51703e5ea2af3e423ed22f24729f7d2b_Traceguids);
  }
  TargetHandle = 0;
  v4 = 0;
  if ( dwProcessId != GetCurrentProcessId() )
  {
    v5 = OpenProcess(0x40u, 0, dwProcessId);
    if ( !v5 )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 3u )
      {
        WPP_SF_Dd(
          WPP_GLOBAL_Control[1].Flink,
          11,
          WPP_51703e5ea2af3e423ed22f24729f7d2b_Traceguids,
          dwProcessId,
          LastError);
      }
      v7 = RpcImpersonateClient(0);
      if ( v7 )
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 3u )
        {
          v9 = 12;
LABEL_41:
          WPP_SF_d(v8[1].Flink, v9, WPP_51703e5ea2af3e423ed22f24729f7d2b_Traceguids, v7);
          goto LABEL_30;
        }
        goto LABEL_30;
      }
      v4 = 1;
      v5 = OpenProcess(0x40u, 0, dwProcessId);
      if ( !v5 )
      {
        v10 = GetLastError();
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 3u )
        {
          WPP_SF_Dd(WPP_GLOBAL_Control[1].Flink, 13, WPP_51703e5ea2af3e423ed22f24729f7d2b_Traceguids, dwProcessId, v10);
        }
        goto LABEL_30;
      }
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
      {
        WPP_SF_(WPP_GLOBAL_Control[1].Flink, 14, WPP_51703e5ea2af3e423ed22f24729f7d2b_Traceguids);
      }
    }
LABEL_25:
    CurrentProcess = GetCurrentProcess();
    if ( !DuplicateHandle(v5, hSourceHandle, CurrentProcess, &TargetHandle, 0, 0, 2u) )
    {
      v12 = GetLastError();
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        WPP_SF_dqD(
          WPP_GLOBAL_Control[1].Flink,
          16,
          WPP_51703e5ea2af3e423ed22f24729f7d2b_Traceguids,
          dwProcessId,
          hSourceHandle,
          v12);
      }
    }
    goto LABEL_30;
  }
  v5 = GetCurrentProcess();
  if ( v5 )
    goto LABEL_25;
  v7 = GetLastError();
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
  {
    v9 = 15;
    goto LABEL_41;
  }
LABEL_30:
  if ( dwProcessId != GetCurrentProcessId() && v5 )
    CloseHandle(v5);
  if ( v4 )
    RpcRevertToSelf();
  return TargetHandle;
}

```

## disassembly

```asm
0x1800059e4  mov     [rsp+arg_0], rbx
0x1800059e9  mov     [rsp+arg_8], rbp
0x1800059ee  push    rsi
0x1800059ef  push    rdi
0x1800059f0  push    r12
0x1800059f2  push    r13
0x1800059f4  push    r15
0x1800059f6  sub     rsp, 40h
0x1800059fa  mov     edi, edx
0x1800059fc  mov     rbp, rcx
0x1800059ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a06  lea     r12, WPP_GLOBAL_Control
0x180005a0d  lea     r13, WPP_51703e5ea2af3e423ed22f24729f7d2b_Traceguids
0x180005a14  mov     r15d, 2000h
0x180005a1a  cmp     rcx, r12
0x180005a1d  jz      short loc_180005A3C
0x180005a1f  test    [rcx+1Ch], r15d
0x180005a23  jz      short loc_180005A3C
0x180005a25  cmp     byte ptr [rcx+19h], 6
0x180005a29  jb      short loc_180005A3C
0x180005a2b  mov     rcx, [rcx+10h]
0x180005a2f  mov     edx, 0Ah
0x180005a34  mov     r8, r13
0x180005a37  call    WPP_SF_
0x180005a3c  mov     [rsp+68h+TargetHandle], 0
0x180005a48  xor     esi, esi
0x180005a4a  call    cs:__imp_GetCurrentProcessId
0x180005a50  cmp     edi, eax
0x180005a52  jz      loc_180005C1E
0x180005a58  mov     r8d, edi; dwProcessId
0x180005a5b  lea     ecx, [rsi+40h]; dwDesiredAccess
0x180005a5e  xor     edx, edx; bInheritHandle
0x180005a60  call    cs:__imp_OpenProcess
0x180005a66  mov     rbx, rax
0x180005a69  test    rax, rax
0x180005a6c  jnz     loc_180005B69
0x180005a72  call    cs:__imp_GetLastError
0x180005a78  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a7f  cmp     rcx, r12
0x180005a82  jz      short loc_180005AA6
0x180005a84  test    [rcx+1Ch], r15d
0x180005a88  jz      short loc_180005AA6
0x180005a8a  cmp     byte ptr [rcx+19h], 3
0x180005a8e  jb      short loc_180005AA6
0x180005a90  mov     rcx, [rcx+10h]
0x180005a94  lea     edx, [rsi+0Bh]
0x180005a97  mov     r9d, edi
0x180005a9a  mov     [rsp+68h+dwDesiredAccess], eax
0x180005a9e  mov     r8, r13
0x180005aa1  call    WPP_SF_Dd
0x180005aa6  xor     ecx, ecx; BindingHandle
0x180005aa8  call    cs:__imp_RpcImpersonateClient
0x180005aae  test    eax, eax
0x180005ab0  jz      short loc_180005AE0
0x180005ab2  mov     rcx, cs:WPP_GLOBAL_Control
0x180005ab9  cmp     rcx, r12
0x180005abc  jz      loc_180005BDD
0x180005ac2  test    [rcx+1Ch], r15d
0x180005ac6  jz      loc_180005BDD
0x180005acc  cmp     byte ptr [rcx+19h], 3
0x180005ad0  jb      loc_180005BDD
0x180005ad6  mov     edx, 0Ch
0x180005adb  jmp     loc_180005C51
0x180005ae0  mov     esi, 1
0x180005ae5  mov     r8d, edi; dwProcessId
0x180005ae8  xor     edx, edx; bInheritHandle
0x180005aea  lea     ecx, [rsi+3Fh]; dwDesiredAccess
0x180005aed  call    cs:__imp_OpenProcess
0x180005af3  mov     rbx, rax
0x180005af6  test    rax, rax
0x180005af9  jnz     short loc_180005B40
0x180005afb  call    cs:__imp_GetLastError
0x180005b01  mov     rcx, cs:WPP_GLOBAL_Control
0x180005b08  cmp     rcx, r12
0x180005b0b  jz      loc_180005BDD
0x180005b11  test    [rcx+1Ch], r15d
0x180005b15  jz      loc_180005BDD
0x180005b1b  cmp     byte ptr [rcx+19h], 3
0x180005b1f  jb      loc_180005BDD
0x180005b25  mov     rcx, [rcx+10h]
0x180005b29  lea     edx, [rsi+0Ch]
0x180005b2c  mov     r9d, edi
0x180005b2f  mov     [rsp+68h+dwDesiredAccess], eax
0x180005b33  mov     r8, r13
0x180005b36  call    WPP_SF_Dd
0x180005b3b  jmp     loc_180005BDD
0x180005b40  mov     rcx, cs:WPP_GLOBAL_Control
0x180005b47  cmp     rcx, r12
0x180005b4a  jz      short loc_180005B69
0x180005b4c  test    [rcx+1Ch], r15d
0x180005b50  jz      short loc_180005B69
0x180005b52  cmp     byte ptr [rcx+19h], 4
0x180005b56  jb      short loc_180005B69
0x180005b58  mov     rcx, [rcx+10h]
0x180005b5c  mov     edx, 0Eh
0x180005b61  mov     r8, r13
0x180005b64  call    WPP_SF_
0x180005b69  call    cs:__imp_GetCurrentProcess
0x180005b6f  mov     [rsp+68h+dwOptions], 2; dwOptions
0x180005b77  lea     r9, [rsp+68h+TargetHandle]; lpTargetHandle
0x180005b7f  mov     r8, rax; hTargetProcessHandle
0x180005b82  mov     [rsp+68h+bInheritHandle], 0; bInheritHandle
0x180005b8a  mov     rdx, rbp; hSourceHandle
0x180005b8d  mov     [rsp+68h+dwDesiredAccess], 0; dwDesiredAccess
0x180005b95  mov     rcx, rbx; hSourceProcessHandle
0x180005b98  call    cs:__imp_DuplicateHandle
0x180005b9e  test    eax, eax
0x180005ba0  jnz     short loc_180005BDD
0x180005ba2  call    cs:__imp_GetLastError
0x180005ba8  mov     rcx, cs:WPP_GLOBAL_Control
0x180005baf  cmp     rcx, r12
0x180005bb2  jz      short loc_180005BDD
0x180005bb4  test    [rcx+1Ch], r15d
0x180005bb8  jz      short loc_180005BDD
0x180005bba  cmp     byte ptr [rcx+19h], 2
0x180005bbe  jb      short loc_180005BDD
0x180005bc0  mov     rcx, [rcx+10h]
0x180005bc4  mov     edx, 10h
0x180005bc9  mov     [rsp+68h+bInheritHandle], eax
0x180005bcd  mov     r9d, edi
0x180005bd0  mov     r8, r13
0x180005bd3  mov     qword ptr [rsp+68h+dwDesiredAccess], rbp
0x180005bd8  call    WPP_SF_dqD
0x180005bdd  call    cs:__imp_GetCurrentProcessId
0x180005be3  cmp     edi, eax
0x180005be5  jz      short loc_180005BF5
0x180005be7  test    rbx, rbx
0x180005bea  jz      short loc_180005BF5
0x180005bec  mov     rcx, rbx; hObject
0x180005bef  call    cs:__imp_CloseHandle
0x180005bf5  test    esi, esi
0x180005bf7  jz      short loc_180005BFF
0x180005bf9  call    cs:__imp_RpcRevertToSelf
0x180005bff  mov     rax, [rsp+68h+TargetHandle]
0x180005c07  mov     rbx, [rsp+68h+arg_0]
0x180005c0c  mov     rbp, [rsp+68h+arg_8]
0x180005c11  add     rsp, 40h
0x180005c15  pop     r15
0x180005c17  pop     r13
0x180005c19  pop     r12
0x180005c1b  pop     rdi
0x180005c1c  pop     rsi
0x180005c1d  retn
0x180005c1e  call    cs:__imp_GetCurrentProcess
0x180005c24  mov     rbx, rax
0x180005c27  test    rax, rax
0x180005c2a  jnz     loc_180005B69
0x180005c30  call    cs:__imp_GetLastError
0x180005c36  mov     rcx, cs:WPP_GLOBAL_Control
0x180005c3d  cmp     rcx, r12
0x180005c40  jz      short loc_180005BDD
0x180005c42  test    [rcx+1Ch], r15d
0x180005c46  jz      short loc_180005BDD
0x180005c48  cmp     byte ptr [rcx+19h], 2
0x180005c4c  jb      short loc_180005BDD
0x180005c4e  lea     edx, [rbx+0Fh]
0x180005c51  mov     rcx, [rcx+10h]
0x180005c55  mov     r9d, eax
0x180005c58  mov     r8, r13
0x180005c5b  call    WPP_SF_d
0x180005c60  jmp     loc_180005BDD
```
