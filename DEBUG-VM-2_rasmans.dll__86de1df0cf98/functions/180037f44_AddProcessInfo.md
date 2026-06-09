# AddProcessInfo

- ea: `0x180037f44`
- end: `0x1800382e1`
- name: `AddProcessInfo`
- size: `925`
- prototype: `__int64 __fastcall(DWORD dwProcessId)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x180028210`
- `0x180047198`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x180005e74`
- `0x18003705c`
- `0x180037f44`
- `0x18003eb54`
- `0x180040dec`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180038118`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003812b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180038118`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003812b`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18003801e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800380aa`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18003801e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800380aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037fd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038031`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800380b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037fd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038031`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800380b9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180038100`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180038100`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003826f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e7796`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003826f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e7796`
- `RPCRT4!RpcImpersonateClient` at `0x180038068`
- `RPCRT4!RpcImpersonateClient` at `0x180038068`
- `RPCRT4!RpcRevertToSelf` at `0x1800380ee`
- `RPCRT4!RpcRevertToSelf` at `0x1800380ee`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180037f98`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180037f98`

## pseudocode

```c
_QWORD *__fastcall AddProcessInfo(DWORD dwProcessId)
{
  _QWORD *v2; // rax
  _QWORD *v3; // r15
  struct _LIST_ENTRY *v4; // rcx
  struct _LIST_ENTRY *Flink; // rbx
  DWORD v6; // eax
  HANDLE v7; // rax
  DWORD LastError; // eax
  unsigned int v9; // eax
  HANDLE v10; // rax
  DWORD v11; // eax
  DWORD CurrentProcessId; // eax
  BOOL v13; // ecx
  _QWORD *v14; // rax
  __int64 v15; // r9

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 82, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, dwProcessId);
  }
  v2 = LocalAlloc(0x40u, 0x58u);
  v3 = v2;
  if ( v2 )
  {
    *((_DWORD *)v2 + 6) = dwProcessId;
    InitializeEventQueue(v2 + 4, dwProcessId);
    v7 = OpenProcess(0x1000u, 0, dwProcessId);
    v3[2] = v7;
    if ( !v7 )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 3u )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 84, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, LastError);
      }
      v9 = RpcImpersonateClient(0);
      if ( v9 )
      {
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 3u )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 85, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, v9);
        }
      }
      else
      {
        v10 = OpenProcess(0x1000u, 0, dwProcessId);
        v3[2] = v10;
        if ( !v10 )
        {
          v11 = GetLastError();
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 86, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, v11);
          }
        }
        RpcRevertToSelf();
      }
    }
    EnterCriticalSection(&g_csClientProcessBlock);
    v13 = 1;
    if ( g_dwAttachedCount || GetCurrentProcessId() == dwProcessId )
    {
      if ( g_dwAttachedCount != 1 || (CurrentProcessId = GetCurrentProcessId(), !FindProcess(CurrentProcessId)) )
        v13 = 0;
    }
    v14 = (_QWORD *)qword_18010FE58;
    *v3 = &ClientProcessBlockList;
    v3[1] = v14;
    *v14 = v3;
    qword_18010FE58 = (__int64)v3;
    if ( v13 && !g_pDeadClientTimeoutElement )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
      {
        WPP_SF_(WPP_GLOBAL_Control[1].Flink, 87, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids);
      }
      g_pDeadClientTimeoutElement = AddTimeoutElement(BackGroundCleanUp, 0, 0, 10);
    }
    v15 = (unsigned int)++g_dwAttachedCount;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 88, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, v15);
    }
    LeaveCriticalSection(&g_csClientProcessBlock);
    goto LABEL_44;
  }
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    return v3;
  if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
  {
    Flink = WPP_GLOBAL_Control[1].Flink;
    v6 = GetLastError();
    WPP_SF_Dd(Flink, 83, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, dwProcessId, v6);
LABEL_44:
    v4 = WPP_GLOBAL_Control;
  }
  if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v4[1].Blink) & 0x2000) != 0
    && BYTE1(v4[1].Blink) >= 6u )
  {
    WPP_SF_(v4[1].Flink, 91, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids);
  }
  return v3;
}

```

## disassembly

```asm
0x180037f44  push    rbx
0x180037f46  push    rsi
0x180037f47  push    rdi
0x180037f48  push    r12
0x180037f4a  push    r14
0x180037f4c  push    r15
0x180037f4e  sub     rsp, 48h
0x180037f52  mov     r14d, ecx
0x180037f55  lea     rsi, WPP_GLOBAL_Control
0x180037f5c  mov     rcx, cs:WPP_GLOBAL_Control
0x180037f63  mov     edi, 2000h
0x180037f68  cmp     rcx, rsi
0x180037f6b  jz      short loc_180037F90
0x180037f6d  test    [rcx+1Ch], edi
0x180037f70  jz      short loc_180037F90
0x180037f72  cmp     byte ptr [rcx+19h], 6
0x180037f76  jb      short loc_180037F90
0x180037f78  mov     edx, 52h ; 'R'
0x180037f7d  mov     r9d, r14d
0x180037f80  lea     r8, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x180037f87  mov     rcx, [rcx+10h]
0x180037f8b  call    WPP_SF_d
0x180037f90  mov     edx, 58h ; 'X'; uBytes
0x180037f95  lea     ecx, [rdx-18h]; uFlags
0x180037f98  call    cs:__imp_LocalAlloc
0x180037f9e  mov     r15, rax
0x180037fa1  mov     [rsp+78h+arg_8], rax
0x180037fa9  test    rax, rax
0x180037fac  jnz     short loc_180037FFA
0x180037fae  mov     rcx, cs:WPP_GLOBAL_Control
0x180037fb5  cmp     rcx, rsi
0x180037fb8  jz      loc_1800382D0
0x180037fbe  test    [rcx+1Ch], edi
0x180037fc1  jz      loc_1800382AB
0x180037fc7  cmp     byte ptr [rcx+19h], 2
0x180037fcb  jb      loc_1800382AB
0x180037fd1  mov     rbx, [rcx+10h]
0x180037fd5  call    cs:__imp_GetLastError
0x180037fdb  lea     edx, [r15+53h]
0x180037fdf  mov     [rsp+78h+var_58], eax
0x180037fe3  mov     r9d, r14d
0x180037fe6  lea     r8, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x180037fed  mov     rcx, rbx
0x180037ff0  call    WPP_SF_Dd
0x180037ff5  jmp     loc_1800382A4
0x180037ffa  xor     r12d, r12d
0x180037ffd  mov     [rsp+78h+var_44], r12d
0x180038002  mov     [rax+18h], r14d
0x180038006  lea     rcx, [rax+20h]
0x18003800a  mov     edx, r14d
0x18003800d  call    InitializeEventQueue
0x180038012  mov     r8d, r14d; dwProcessId
0x180038015  xor     edx, edx; bInheritHandle
0x180038017  mov     ebx, 1000h
0x18003801c  mov     ecx, ebx; dwDesiredAccess
0x18003801e  call    cs:__imp_OpenProcess
0x180038024  mov     [r15+10h], rax
0x180038028  test    rax, rax
0x18003802b  jnz     loc_1800380F4
0x180038031  call    cs:__imp_GetLastError
0x180038037  mov     rcx, cs:WPP_GLOBAL_Control
0x18003803e  cmp     rcx, rsi
0x180038041  jz      short loc_180038066
0x180038043  test    [rcx+1Ch], edi
0x180038046  jz      short loc_180038066
0x180038048  cmp     byte ptr [rcx+19h], 3
0x18003804c  jb      short loc_180038066
0x18003804e  lea     edx, [r12+54h]
0x180038053  mov     r9d, eax
0x180038056  lea     r8, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x18003805d  mov     rcx, [rcx+10h]
0x180038061  call    WPP_SF_d
0x180038066  xor     ecx, ecx; BindingHandle
0x180038068  call    cs:__imp_RpcImpersonateClient
0x18003806e  test    eax, eax
0x180038070  jz      short loc_1800380A3
0x180038072  mov     rcx, cs:WPP_GLOBAL_Control
0x180038079  cmp     rcx, rsi
0x18003807c  jz      short loc_1800380F4
0x18003807e  test    [rcx+1Ch], edi
0x180038081  jz      short loc_1800380F4
0x180038083  cmp     byte ptr [rcx+19h], 3
0x180038087  jb      short loc_1800380F4
0x180038089  mov     edx, 55h ; 'U'
0x18003808e  mov     r9d, eax
0x180038091  lea     r8, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x180038098  mov     rcx, [rcx+10h]
0x18003809c  call    WPP_SF_d
0x1800380a1  jmp     short loc_1800380F4
0x1800380a3  mov     r8d, r14d; dwProcessId
0x1800380a6  xor     edx, edx; bInheritHandle
0x1800380a8  mov     ecx, ebx; dwDesiredAccess
0x1800380aa  call    cs:__imp_OpenProcess
0x1800380b0  mov     [r15+10h], rax
0x1800380b4  test    rax, rax
0x1800380b7  jnz     short loc_1800380EE
0x1800380b9  call    cs:__imp_GetLastError
0x1800380bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800380c6  cmp     rcx, rsi
0x1800380c9  jz      short loc_1800380EE
0x1800380cb  test    [rcx+1Ch], edi
0x1800380ce  jz      short loc_1800380EE
0x1800380d0  cmp     byte ptr [rcx+19h], 2
0x1800380d4  jb      short loc_1800380EE
0x1800380d6  mov     edx, 56h ; 'V'
0x1800380db  mov     r9d, eax
0x1800380de  lea     r8, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x1800380e5  mov     rcx, [rcx+10h]
0x1800380e9  call    WPP_SF_d
0x1800380ee  call    cs:__imp_RpcRevertToSelf
0x1800380f4  mov     [rsp+78h+var_48], r12d
0x1800380f9  lea     rcx, g_csClientProcessBlock; lpCriticalSection
0x180038100  call    cs:__imp_EnterCriticalSection
0x180038106  mov     ebx, 1
0x18003810b  mov     [rsp+78h+var_48], ebx
0x18003810f  cmp     cs:g_dwAttachedCount, 0
0x180038116  jnz     short loc_180038123
0x180038118  call    cs:__imp_GetCurrentProcessId
0x18003811e  cmp     eax, r14d
0x180038121  jnz     short loc_18003813D
0x180038123  cmp     cs:g_dwAttachedCount, ebx
0x180038129  jnz     short loc_180038141
0x18003812b  call    cs:__imp_GetCurrentProcessId
0x180038131  mov     ecx, eax
0x180038133  call    FindProcess
0x180038138  test    rax, rax
0x18003813b  jz      short loc_180038141
0x18003813d  mov     ecx, ebx
0x18003813f  jmp     short loc_180038143
0x180038141  xor     ecx, ecx
0x180038143  mov     rax, cs:qword_18010FE58
0x18003814a  lea     rdx, ClientProcessBlockList
0x180038151  mov     [r15], rdx
0x180038154  mov     [r15+8], rax
0x180038158  mov     [rax], r15
0x18003815b  mov     cs:qword_18010FE58, r15
0x180038162  test    ecx, ecx
0x180038164  jz      short loc_1800381BA
0x180038166  cmp     cs:g_pDeadClientTimeoutElement, 0
0x18003816e  jnz     short loc_1800381BA
0x180038170  mov     rcx, cs:WPP_GLOBAL_Control
0x180038177  cmp     rcx, rsi
0x18003817a  jz      short loc_18003819C
0x18003817c  test    [rcx+1Ch], edi
0x18003817f  jz      short loc_18003819C
0x180038181  cmp     byte ptr [rcx+19h], 5
0x180038185  jb      short loc_18003819C
0x180038187  mov     edx, 57h ; 'W'
0x18003818c  lea     r8, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x180038193  mov     rcx, [rcx+10h]
0x180038197  call    WPP_SF_
0x18003819c  mov     r9d, 0Ah
0x1800381a2  xor     r8d, r8d
0x1800381a5  xor     edx, edx
0x1800381a7  lea     rcx, BackGroundCleanUp
0x1800381ae  call    AddTimeoutElement
0x1800381b3  mov     cs:g_pDeadClientTimeoutElement, rax
0x1800381ba  mov     r9d, cs:g_dwAttachedCount
0x1800381c1  add     r9d, ebx
0x1800381c4  mov     cs:g_dwAttachedCount, r9d
0x1800381cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800381d2  cmp     rcx, rsi
0x1800381d5  jz      short loc_1800381FE
0x1800381d7  test    [rcx+1Ch], edi
0x1800381da  jz      short loc_1800381FE
0x1800381dc  cmp     byte ptr [rcx+19h], 4
0x1800381e0  jb      short loc_1800381FE
0x1800381e2  mov     edx, 58h ; 'X'
0x1800381e7  lea     r8, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x1800381ee  mov     rcx, [rcx+10h]
0x1800381f2  call    WPP_SF_d
0x1800381f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800381fe  jmp     short loc_180038264
0x180038200  mov     r12d, eax
0x180038203  mov     [rsp+78h+var_44], eax
0x180038207  test    eax, eax
0x180038209  jz      short loc_180038245
0x18003820b  lea     rax, WPP_GLOBAL_Control
0x180038212  mov     rcx, cs:WPP_GLOBAL_Control
0x180038219  cmp     rcx, rax
0x18003821c  jz      short loc_18003824C
0x18003821e  test    dword ptr [rcx+1Ch], 2000h
0x180038225  jz      short loc_18003824C
0x180038227  cmp     byte ptr [rcx+19h], 2
0x18003822b  jb      short loc_18003824C
0x18003822d  mov     edx, 59h ; 'Y'
0x180038232  mov     r9d, r12d
0x180038235  lea     r8, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x18003823c  mov     rcx, [rcx+10h]
0x180038240  call    WPP_SF_d
0x180038245  mov     rcx, cs:WPP_GLOBAL_Control
0x18003824c  lea     rsi, WPP_GLOBAL_Control
0x180038253  mov     edi, 2000h
0x180038258  mov     ebx, [rsp+78h+var_48]
0x18003825c  mov     r15, [rsp+78h+arg_8]
0x180038264  test    ebx, ebx
0x180038266  jz      short loc_180038277
0x180038268  lea     rcx, g_csClientProcessBlock; lpCriticalSection
0x18003826f  call    cs:__imp_LeaveCriticalSection
0x180038275  jmp     short loc_1800382A4
0x180038277  test    r12d, r12d
0x18003827a  jz      short loc_1800382AB
0x18003827c  cmp     rcx, rsi
0x18003827f  jz      short loc_1800382D0
0x180038281  test    [rcx+1Ch], edi
0x180038284  jz      short loc_1800382AB
0x180038286  cmp     byte ptr [rcx+19h], 2
0x18003828a  jb      short loc_1800382AB
0x18003828c  mov     edx, 5Ah ; 'Z'
0x180038291  mov     r9d, r12d
0x180038294  lea     r8, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x18003829b  mov     rcx, [rcx+10h]
0x18003829f  call    WPP_SF_d
0x1800382a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800382ab  cmp     rcx, rsi
0x1800382ae  jz      short loc_1800382D0
0x1800382b0  test    [rcx+1Ch], edi
0x1800382b3  jz      short loc_1800382D0
0x1800382b5  cmp     byte ptr [rcx+19h], 6
0x1800382b9  jb      short loc_1800382D0
0x1800382bb  mov     edx, 5Bh ; '['
0x1800382c0  lea     r8, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x1800382c7  mov     rcx, [rcx+10h]
0x1800382cb  call    WPP_SF_
0x1800382d0  mov     rax, r15
0x1800382d3  add     rsp, 48h
0x1800382d7  pop     r15
0x1800382d9  pop     r14
0x1800382db  pop     r12
0x1800382dd  pop     rdi
0x1800382de  pop     rsi
0x1800382df  pop     rbx
0x1800382e0  retn
0x1800e7780  push    rbp
0x1800e7782  sub     rsp, 30h
0x1800e7786  mov     rbp, rdx
0x1800e7789  cmp     dword ptr [rbp+30h], 0
0x1800e778d  jz      short loc_1800E779E
0x1800e778f  lea     rcx, g_csClientProcessBlock; lpCriticalSection
0x1800e7796  call    cs:__imp_LeaveCriticalSection
0x1800e779c  jmp     short loc_1800E77DF
0x1800e779e  mov     r9d, [rbp+34h]
0x1800e77a2  test    r9d, r9d
0x1800e77a5  jz      short loc_1800E77DF
0x1800e77a7  lea     rax, WPP_GLOBAL_Control
0x1800e77ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e77b5  cmp     rcx, rax
0x1800e77b8  jz      short loc_1800E77DF
0x1800e77ba  test    dword ptr [rcx+1Ch], 2000h
0x1800e77c1  jz      short loc_1800E77DF
0x1800e77c3  cmp     byte ptr [rcx+19h], 2
0x1800e77c7  jb      short loc_1800E77DF
0x1800e77c9  mov     edx, 5Ah ; 'Z'
0x1800e77ce  lea     r8, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x1800e77d5  mov     rcx, [rcx+10h]
0x1800e77d9  call    WPP_SF_d
0x1800e77de  nop
0x1800e77df  add     rsp, 30h
0x1800e77e3  pop     rbp
0x1800e77e4  retn
```
