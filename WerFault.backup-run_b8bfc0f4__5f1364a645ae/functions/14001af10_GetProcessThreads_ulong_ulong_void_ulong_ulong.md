# GetProcessThreads(ulong,ulong,void * *,ulong,ulong *)

- ea: `0x14001af10`
- end: `0x14001b14c`
- name: `?GetProcessThreads@@YAJKKPEAPEAXKPEAK@Z`
- size: `572`
- prototype: `int(unsigned int, unsigned int, void **, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x140020c20`
- `0x140027624`

## callees

- `0x140002470`
- `0x1400030a8`
- `0x14000d2ec`
- `0x140014474`
- `0x14001af10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001afb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001b035`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001b0d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001afb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001b035`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001b0d0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x14001b026`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x14001b026`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001b120`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001b120`
- `api-ms-win-core-toolhelp-l1-1-0!Thread32Next` at `0x14001b0a5`
- `api-ms-win-core-toolhelp-l1-1-0!Thread32Next` at `0x14001b0a5`
- `api-ms-win-core-toolhelp-l1-1-0!Thread32First` at `0x14001afab`
- `api-ms-win-core-toolhelp-l1-1-0!Thread32First` at `0x14001afab`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x14001af82`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x14001af82`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetProcessThreads(int a1, DWORD a2, void **a3, unsigned int a4, unsigned int *a5)
{
  HANDLE Toolhelp32Snapshot; // rax
  void *v8; // r14
  unsigned __int64 v9; // r13
  signed int LastError; // eax
  unsigned int v11; // ebx
  CUserModeHangReport *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rdi
  HANDLE v15; // rax
  signed int v16; // eax
  unsigned int v17; // ecx
  signed int v18; // eax
  THREADENTRY32 te; // [rsp+48h] [rbp-28h] BYREF

  memset(&te, 0, sizeof(te));
  if ( a3 )
    memset_0(a3, 0, 8LL * a4);
  if ( a5 )
    *a5 = 0;
  Toolhelp32Snapshot = CreateToolhelp32Snapshot(4u, 0);
  v8 = Toolhelp32Snapshot;
  v9 = (unsigned __int64)Toolhelp32Snapshot + 1;
  if ( (unsigned __int64)Toolhelp32Snapshot + 1 > 1 )
  {
    te.dwSize = 28;
    if ( !Thread32First(Toolhelp32Snapshot, &te) )
    {
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_37;
      }
      v13 = 104;
LABEL_36:
      WPP_SF_d(*((_QWORD *)v12 + 2), v13, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids, v11);
      goto LABEL_37;
    }
    v14 = 0;
    while ( 1 )
    {
      if ( a3 && (unsigned int)v14 >= a4 )
      {
LABEL_26:
        v9 = (unsigned __int64)v8 + 1;
        if ( a5 )
          *a5 = v14;
        v11 = -2147023728;
        if ( (_DWORD)v14 )
          v11 = 0;
        goto LABEL_37;
      }
      if ( te.th32OwnerProcessID == a1 )
      {
        if ( a3 )
        {
          v15 = OpenThread(a2, 0, te.th32ThreadID);
          a3[v14] = v15;
          if ( !v15 )
          {
            v16 = GetLastError();
            v17 = v16;
            if ( v16 > 0 )
              v17 = (unsigned __int16)v16 | 0x80070000;
            if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_DDD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                105,
                WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids,
                te.th32ThreadID,
                v17,
                NtCurrentTeb()->LastStatusValue);
            }
            goto LABEL_25;
          }
        }
        v14 = (unsigned int)(v14 + 1);
      }
      te.dwSize = 28;
LABEL_25:
      if ( !Thread32Next(v8, &te) )
        goto LABEL_26;
    }
  }
  v18 = GetLastError();
  v11 = v18;
  if ( v18 > 0 )
    v11 = (unsigned __int16)v18 | 0x80070000;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v13 = 103;
    goto LABEL_36;
  }
LABEL_37:
  if ( v9 > 1 )
    CloseHandle(v8);
  return v11;
}

```

## disassembly

```asm
0x14001af10  mov     [rsp-38h+arg_0], rbx
0x14001af15  push    rbp
0x14001af16  push    rsi
0x14001af17  push    rdi
0x14001af18  push    r12
0x14001af1a  push    r13
0x14001af1c  push    r14
0x14001af1e  push    r15
0x14001af20  mov     rbp, rsp
0x14001af23  sub     rsp, 70h
0x14001af27  mov     rax, cs:__security_cookie
0x14001af2e  xor     rax, rsp
0x14001af31  mov     [rbp+var_8], rax
0x14001af35  mov     r12d, r9d
0x14001af38  mov     r15, r8
0x14001af3b  mov     [rbp+dwDesiredAccess], edx
0x14001af3e  mov     [rbp+var_40], ecx
0x14001af41  mov     rbx, [rbp+arg_20]
0x14001af45  mov     [rbp+var_30], rbx
0x14001af49  mov     [rbp+var_38], 0
0x14001af51  xorps   xmm0, xmm0
0x14001af54  movups  xmmword ptr [rbp+te.dwSize], xmm0
0x14001af58  movups  xmmword ptr [rbp+te.th32OwnerProcessID], xmm0
0x14001af5c  test    r8, r8
0x14001af5f  jz      short loc_14001AF72
0x14001af61  mov     r8d, r12d
0x14001af64  shl     r8, 3; Size
0x14001af68  xor     edx, edx; Val
0x14001af6a  mov     rcx, r15; void *
0x14001af6d  call    memset_0
0x14001af72  test    rbx, rbx
0x14001af75  jz      short loc_14001AF7D
0x14001af77  mov     dword ptr [rbx], 0
0x14001af7d  xor     edx, edx; th32ProcessID
0x14001af7f  lea     ecx, [rdx+4]; dwFlags
0x14001af82  call    cs:__imp_CreateToolhelp32Snapshot
0x14001af88  mov     r14, rax
0x14001af8b  mov     [rbp+var_38], rax
0x14001af8f  lea     r13, [rax+1]
0x14001af93  cmp     r13, 1
0x14001af97  jbe     loc_14001B0D0
0x14001af9d  mov     [rbp+te.dwSize], 1Ch
0x14001afa4  lea     rdx, [rbp+te]; lpte
0x14001afa8  mov     rcx, rax; hSnapshot
0x14001afab  call    cs:__imp_Thread32First
0x14001afb1  test    eax, eax
0x14001afb3  jnz     short loc_14001AFF5
0x14001afb5  call    cs:__imp_GetLastError
0x14001afbb  mov     ebx, eax
0x14001afbd  test    eax, eax
0x14001afbf  jle     short loc_14001AFCA
0x14001afc1  movzx   ebx, ax
0x14001afc4  or      ebx, 80070000h
0x14001afca  lea     rsi, WPP_GLOBAL_Control
0x14001afd1  mov     rcx, cs:WPP_GLOBAL_Control
0x14001afd8  cmp     rcx, rsi
0x14001afdb  jz      loc_14001B117
0x14001afe1  test    byte ptr [rcx+1Ch], 1
0x14001afe5  jz      loc_14001B117
0x14001afeb  mov     edx, 68h ; 'h'
0x14001aff0  jmp     loc_14001B103
0x14001aff5  xor     edi, edi
0x14001aff7  lea     rsi, WPP_GLOBAL_Control
0x14001affe  mov     r13d, [rbp+var_40]
0x14001b002  mov     ebx, [rbp+dwDesiredAccess]
0x14001b005  test    r15, r15
0x14001b008  jz      short loc_14001B013
0x14001b00a  cmp     edi, r12d
0x14001b00d  jnb     loc_14001B0B3
0x14001b013  cmp     [rbp+te.th32OwnerProcessID], r13d
0x14001b017  jnz     short loc_14001B097
0x14001b019  test    r15, r15
0x14001b01c  jz      short loc_14001B095
0x14001b01e  mov     r8d, [rbp+te.th32ThreadID]; dwThreadId
0x14001b022  xor     edx, edx; bInheritHandle
0x14001b024  mov     ecx, ebx; dwDesiredAccess
0x14001b026  call    cs:__imp_OpenThread
0x14001b02c  mov     [r15+rdi*8], rax
0x14001b030  test    rax, rax
0x14001b033  jnz     short loc_14001B095
0x14001b035  call    cs:__imp_GetLastError
0x14001b03b  mov     ecx, eax
0x14001b03d  test    eax, eax
0x14001b03f  jle     short loc_14001B04A
0x14001b041  movzx   ecx, ax
0x14001b044  or      ecx, 80070000h
0x14001b04a  mov     rax, cs:WPP_GLOBAL_Control
0x14001b051  cmp     rax, rsi
0x14001b054  jz      short loc_14001B09E
0x14001b056  test    byte ptr [rax+1Ch], 1
0x14001b05a  jz      short loc_14001B09E
0x14001b05c  mov     rax, gs:30h
0x14001b065  mov     edx, 69h ; 'i'
0x14001b06a  mov     eax, [rax+1250h]
0x14001b070  mov     [rsp+70h+var_48], eax
0x14001b074  mov     [rsp+70h+var_50], ecx
0x14001b078  mov     r9d, [rbp+te.th32ThreadID]
0x14001b07c  lea     r8, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids
0x14001b083  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b08a  mov     rcx, [rcx+10h]
0x14001b08e  call    WPP_SF_DDD
0x14001b093  jmp     short loc_14001B09E
0x14001b095  inc     edi
0x14001b097  mov     [rbp+te.dwSize], 1Ch
0x14001b09e  lea     rdx, [rbp+te]; lpte
0x14001b0a2  mov     rcx, r14; hSnapshot
0x14001b0a5  call    cs:__imp_Thread32Next
0x14001b0ab  test    eax, eax
0x14001b0ad  jnz     loc_14001B005
0x14001b0b3  mov     rbx, [rbp+var_30]
0x14001b0b7  test    rbx, rbx
0x14001b0ba  lea     r13, [r14+1]
0x14001b0be  jz      short loc_14001B0C2
0x14001b0c0  mov     [rbx], edi
0x14001b0c2  mov     ebx, 80070490h
0x14001b0c7  xor     eax, eax
0x14001b0c9  test    edi, edi
0x14001b0cb  cmovnz  ebx, eax
0x14001b0ce  jmp     short loc_14001B117
0x14001b0d0  call    cs:__imp_GetLastError
0x14001b0d6  mov     ebx, eax
0x14001b0d8  test    eax, eax
0x14001b0da  jle     short loc_14001B0E5
0x14001b0dc  movzx   ebx, ax
0x14001b0df  or      ebx, 80070000h
0x14001b0e5  lea     rsi, WPP_GLOBAL_Control
0x14001b0ec  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b0f3  cmp     rcx, rsi
0x14001b0f6  jz      short loc_14001B117
0x14001b0f8  test    byte ptr [rcx+1Ch], 1
0x14001b0fc  jz      short loc_14001B117
0x14001b0fe  mov     edx, 67h ; 'g'
0x14001b103  mov     r9d, ebx
0x14001b106  lea     r8, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids
0x14001b10d  mov     rcx, [rcx+10h]
0x14001b111  call    WPP_SF_d
0x14001b116  nop
0x14001b117  cmp     r13, 1
0x14001b11b  jbe     short loc_14001B126
0x14001b11d  mov     rcx, r14; hObject
0x14001b120  call    cs:__imp_CloseHandle
0x14001b126  mov     eax, ebx
0x14001b128  mov     rcx, [rbp+var_8]
0x14001b12c  xor     rcx, rsp; StackCookie
0x14001b12f  call    __security_check_cookie
0x14001b134  mov     rbx, [rsp+70h+arg_0]
0x14001b13c  add     rsp, 70h
0x14001b140  pop     r15
0x14001b142  pop     r14
0x14001b144  pop     r13
0x14001b146  pop     r12
0x14001b148  pop     rdi
0x14001b149  pop     rsi
0x14001b14a  pop     rbp
0x14001b14b  retn
```
