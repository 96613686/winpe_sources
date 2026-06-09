# UbpmpCreatePartiallyInitializedTaskHostContextBlock

- ea: `0x18001cee4`
- end: `0x18001d0e5`
- name: `UbpmpCreatePartiallyInitializedTaskHostContextBlock`
- size: `513`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x18001d230`

## callees

- `0x18000fbf0`
- `0x1800150c0`
- `0x18001cee4`
- `0x1800351ec`
- `0x18003f5b4`

## import_xrefs

- `ntdll!RtlInitializeSRWLock` at `0x18001cf3f`
- `ntdll!RtlInitializeSRWLock` at `0x18001cf4f`
- `ntdll!RtlInitializeSRWLock` at `0x18001cf3f`
- `ntdll!RtlInitializeSRWLock` at `0x18001cf4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cfd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d034`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cfd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d034`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001cfab`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001cfab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d078`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d078`

## pseudocode

```c
__int64 __fastcall UbpmpCreatePartiallyInitializedTaskHostContextBlock(int a1, _QWORD *a2)
{
  _BYTE *v4; // rbx
  signed __int32 v5; // eax
  __int64 v6; // r8
  HANDLE EventW; // rax
  DWORD v8; // edi
  DWORD v10; // eax
  DWORD LastError; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  void *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r9
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // r9
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // r9
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // r9
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // r9
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // r9

  v4 = UbpmAlloc(0x1B8u);
  if ( v4 )
  {
    v5 = _InterlockedExchangeAdd((volatile signed __int32 *)&g_dwInstanceId, 1u);
    v4[104] |= 0x31u;
    *(_DWORD *)v4 = 1665679957;
    *((_DWORD *)v4 + 68) = v5 + 1;
    *((_QWORD *)v4 + 12) = 1;
    v4[432] = a1 != 0;
    RtlInitializeSRWLock(v4 + 80);
    RtlInitializeSRWLock(v4 + 64);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 180, v6, v4, (unsigned __int8)v4[104]);
    *((_QWORD *)v4 + 2) = v4 + 8;
    *((_QWORD *)v4 + 1) = v4 + 8;
    *((_QWORD *)v4 + 26) = v4 + 200;
    *((_QWORD *)v4 + 25) = v4 + 200;
    *((_QWORD *)v4 + 28) = v4 + 216;
    *((_QWORD *)v4 + 27) = v4 + 216;
    EventW = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)v4 + 29) = EventW;
    if ( EventW )
    {
      v8 = 0;
      *a2 = v4;
    }
    else
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 181, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, LastError);
      v15 = (void *)*((_QWORD *)v4 + 29);
      if ( v15 )
        CloseHandle(v15);
      UBPM_MIDL_user_free(*((_QWORD *)v4 + 45), v12, v13, v14);
      UBPM_MIDL_user_free(*((_QWORD *)v4 + 47), v16, v17, v18);
      UBPM_MIDL_user_free(*((_QWORD *)v4 + 43), v19, v20, v21);
      UBPM_MIDL_user_free(*((_QWORD *)v4 + 18), v22, v23, v24);
      UBPM_MIDL_user_free(*((_QWORD *)v4 + 19), v25, v26, v27);
      UBPM_MIDL_user_free(*((_QWORD *)v4 + 20), v28, v29, v30);
      UBPM_MIDL_user_free(*((_QWORD *)v4 + 50), v31, v32, v33);
      UBPM_MIDL_user_free(v4, v34, v35, v36);
    }
  }
  else
  {
    v10 = GetLastError();
    v8 = v10;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 179, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, v10);
  }
  return v8;
}

```

## disassembly

```asm
0x18001cee4  push    rbx
0x18001cee6  push    rsi
0x18001cee7  push    rdi
0x18001cee8  push    r14
0x18001ceea  sub     rsp, 38h
0x18001ceee  mov     edi, ecx
0x18001cef0  mov     r14, rdx
0x18001cef3  mov     ecx, 1B8h; Size
0x18001cef8  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x18001cefd  mov     rbx, rax
0x18001cf00  test    rax, rax
0x18001cf03  jz      loc_18001CFD5
0x18001cf09  mov     eax, 1
0x18001cf0e  lock xadd cs:?g_dwInstanceId@@3KC, eax; ulong volatile g_dwInstanceId
0x18001cf16  or      byte ptr [rbx+68h], 31h
0x18001cf1a  lea     rcx, [rbx+50h]
0x18001cf1e  inc     eax
0x18001cf20  mov     dword ptr [rbx], 63484255h
0x18001cf26  mov     [rbx+110h], eax
0x18001cf2c  test    edi, edi
0x18001cf2e  mov     qword ptr [rbx+60h], 1
0x18001cf36  setnz   al
0x18001cf39  mov     [rbx+1B0h], al
0x18001cf3f  call    cs:__imp_RtlInitializeSRWLock
0x18001cf46  nop     dword ptr [rax+rax+00h]
0x18001cf4b  lea     rcx, [rbx+40h]
0x18001cf4f  call    cs:__imp_RtlInitializeSRWLock
0x18001cf56  nop     dword ptr [rax+rax+00h]
0x18001cf5b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cf62  lea     rsi, WPP_GLOBAL_Control
0x18001cf69  cmp     rcx, rsi
0x18001cf6c  jz      short loc_18001CF78
0x18001cf6e  test    byte ptr [rcx+1Ch], 80h
0x18001cf72  jnz     loc_18001D016
0x18001cf78  lea     rax, [rbx+8]
0x18001cf7c  xor     r9d, r9d; lpName
0x18001cf7f  mov     [rax+8], rax
0x18001cf83  xor     r8d, r8d; bInitialState
0x18001cf86  mov     [rax], rax
0x18001cf89  xor     ecx, ecx; lpEventAttributes
0x18001cf8b  lea     rax, [rbx+0C8h]
0x18001cf92  mov     [rax+8], rax
0x18001cf96  lea     edx, [r9+1]; bManualReset
0x18001cf9a  mov     [rax], rax
0x18001cf9d  lea     rax, [rbx+0D8h]
0x18001cfa4  mov     [rax+8], rax
0x18001cfa8  mov     [rax], rax
0x18001cfab  call    cs:__imp_CreateEventW
0x18001cfb2  nop     dword ptr [rax+rax+00h]
0x18001cfb7  mov     [rbx+0E8h], rax
0x18001cfbe  test    rax, rax
0x18001cfc1  jz      short loc_18001D034
0x18001cfc3  xor     edi, edi
0x18001cfc5  mov     [r14], rbx
0x18001cfc8  mov     eax, edi
0x18001cfca  add     rsp, 38h
0x18001cfce  pop     r14
0x18001cfd0  pop     rdi
0x18001cfd1  pop     rsi
0x18001cfd2  pop     rbx
0x18001cfd3  retn
0x18001cfd5  call    cs:__imp_GetLastError
0x18001cfdc  nop     dword ptr [rax+rax+00h]
0x18001cfe1  mov     edi, eax
0x18001cfe3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cfea  lea     rsi, WPP_GLOBAL_Control
0x18001cff1  cmp     rcx, rsi
0x18001cff4  jz      short loc_18001CFC8
0x18001cff6  test    byte ptr [rcx+1Ch], 1
0x18001cffa  jz      short loc_18001CFC8
0x18001cffc  mov     rcx, [rcx+10h]
0x18001d000  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x18001d007  mov     edx, 0B3h
0x18001d00c  mov     r9d, eax
0x18001d00f  call    WPP_SF_d
0x18001d014  jmp     short loc_18001CFC8
0x18001d016  movzx   eax, byte ptr [rbx+68h]
0x18001d01a  mov     edx, 0B4h
0x18001d01f  mov     rcx, [rcx+10h]
0x18001d023  mov     r9, rbx
0x18001d026  mov     [rsp+58h+var_38], eax
0x18001d02a  call    WPP_SF_qd
0x18001d02f  jmp     loc_18001CF78
0x18001d034  call    cs:__imp_GetLastError
0x18001d03b  nop     dword ptr [rax+rax+00h]
0x18001d040  mov     edi, eax
0x18001d042  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d049  cmp     rcx, rsi
0x18001d04c  jz      short loc_18001D06C
0x18001d04e  test    byte ptr [rcx+1Ch], 1
0x18001d052  jz      short loc_18001D06C
0x18001d054  mov     rcx, [rcx+10h]
0x18001d058  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x18001d05f  mov     edx, 0B5h
0x18001d064  mov     r9d, eax
0x18001d067  call    WPP_SF_d
0x18001d06c  mov     rcx, [rbx+0E8h]; hObject
0x18001d073  test    rcx, rcx
0x18001d076  jz      short loc_18001D084
0x18001d078  call    cs:__imp_CloseHandle
0x18001d07f  nop     dword ptr [rax+rax+00h]
0x18001d084  mov     rcx, [rbx+168h]
0x18001d08b  call    UBPM_MIDL_user_free
0x18001d090  mov     rcx, [rbx+178h]
0x18001d097  call    UBPM_MIDL_user_free
0x18001d09c  mov     rcx, [rbx+158h]
0x18001d0a3  call    UBPM_MIDL_user_free
0x18001d0a8  mov     rcx, [rbx+90h]
0x18001d0af  call    UBPM_MIDL_user_free
0x18001d0b4  mov     rcx, [rbx+98h]
0x18001d0bb  call    UBPM_MIDL_user_free
0x18001d0c0  mov     rcx, [rbx+0A0h]
0x18001d0c7  call    UBPM_MIDL_user_free
0x18001d0cc  mov     rcx, [rbx+190h]
0x18001d0d3  call    UBPM_MIDL_user_free
0x18001d0d8  mov     rcx, rbx
0x18001d0db  call    UBPM_MIDL_user_free
0x18001d0e0  jmp     loc_18001CFC8
```
