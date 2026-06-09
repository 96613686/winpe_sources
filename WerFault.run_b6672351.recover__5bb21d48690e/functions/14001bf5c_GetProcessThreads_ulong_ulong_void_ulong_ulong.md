# GetProcessThreads(ulong,ulong,void * *,ulong,ulong *)

- ea: `0x14001bf5c`
- end: `0x14001c1d1`
- name: `?GetProcessThreads@@YAJKKPEAPEAXKPEAK@Z`
- size: `629`
- prototype: `int(unsigned int, unsigned int, void **, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1400221f4`
- `0x140029018`

## callees

- `0x140002490`
- `0x1400030f8`
- `0x14000d5ac`
- `0x140014f14`
- `0x14001bf5c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001c00d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001c0a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001c148`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001c00d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001c0a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001c148`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x14001c08c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x14001c08c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001c19e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001c19e`
- `api-ms-win-core-toolhelp-l1-1-0!Thread32Next` at `0x14001c117`
- `api-ms-win-core-toolhelp-l1-1-0!Thread32Next` at `0x14001c117`
- `api-ms-win-core-toolhelp-l1-1-0!Thread32First` at `0x14001bffd`
- `api-ms-win-core-toolhelp-l1-1-0!Thread32First` at `0x14001bffd`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x14001bfce`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x14001bfce`

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
0x14001bf5c  mov     [rsp-38h+arg_0], rbx
0x14001bf61  push    rbp
0x14001bf62  push    rsi
0x14001bf63  push    rdi
0x14001bf64  push    r12
0x14001bf66  push    r13
0x14001bf68  push    r14
0x14001bf6a  push    r15
0x14001bf6c  mov     rbp, rsp
0x14001bf6f  sub     rsp, 70h
0x14001bf73  mov     rax, cs:__security_cookie
0x14001bf7a  xor     rax, rsp
0x14001bf7d  mov     [rbp+var_8], rax
0x14001bf81  mov     r12d, r9d
0x14001bf84  mov     r15, r8
0x14001bf87  mov     [rbp+dwDesiredAccess], edx
0x14001bf8a  mov     [rbp+var_40], ecx
0x14001bf8d  mov     rbx, [rbp+arg_20]
0x14001bf91  mov     [rbp+var_30], rbx
0x14001bf95  mov     [rbp+var_38], 0
0x14001bf9d  xorps   xmm0, xmm0
0x14001bfa0  movups  xmmword ptr [rbp+te.dwSize], xmm0
0x14001bfa4  movups  xmmword ptr [rbp+te.th32OwnerProcessID], xmm0
0x14001bfa8  test    r8, r8
0x14001bfab  jz      short loc_14001BFBE
0x14001bfad  mov     r8d, r12d
0x14001bfb0  shl     r8, 3; Size
0x14001bfb4  xor     edx, edx; Val
0x14001bfb6  mov     rcx, r15; void *
0x14001bfb9  call    memset_0
0x14001bfbe  test    rbx, rbx
0x14001bfc1  jz      short loc_14001BFC9
0x14001bfc3  mov     dword ptr [rbx], 0
0x14001bfc9  xor     edx, edx; th32ProcessID
0x14001bfcb  lea     ecx, [rdx+4]; dwFlags
0x14001bfce  call    cs:__imp_CreateToolhelp32Snapshot
0x14001bfd5  nop     dword ptr [rax+rax+00h]
0x14001bfda  mov     r14, rax
0x14001bfdd  mov     [rbp+var_38], rax
0x14001bfe1  lea     r13, [rax+1]
0x14001bfe5  cmp     r13, 1
0x14001bfe9  jbe     loc_14001C148
0x14001bfef  mov     [rbp+te.dwSize], 1Ch
0x14001bff6  lea     rdx, [rbp+te]; lpte
0x14001bffa  mov     rcx, rax; hSnapshot
0x14001bffd  call    cs:__imp_Thread32First
0x14001c004  nop     dword ptr [rax+rax+00h]
0x14001c009  test    eax, eax
0x14001c00b  jnz     short loc_14001C053
0x14001c00d  call    cs:__imp_GetLastError
0x14001c014  nop     dword ptr [rax+rax+00h]
0x14001c019  mov     ebx, eax
0x14001c01b  test    eax, eax
0x14001c01d  jle     short loc_14001C028
0x14001c01f  movzx   ebx, ax
0x14001c022  or      ebx, 80070000h
0x14001c028  lea     rsi, WPP_GLOBAL_Control
0x14001c02f  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c036  cmp     rcx, rsi
0x14001c039  jz      loc_14001C195
0x14001c03f  test    byte ptr [rcx+1Ch], 1
0x14001c043  jz      loc_14001C195
0x14001c049  mov     edx, 68h ; 'h'
0x14001c04e  jmp     loc_14001C181
0x14001c053  xor     edi, edi
0x14001c055  lea     rsi, WPP_GLOBAL_Control
0x14001c05c  mov     r13d, [rbp+var_40]
0x14001c060  mov     ebx, [rbp+dwDesiredAccess]
0x14001c063  test    r15, r15
0x14001c066  jz      short loc_14001C071
0x14001c068  cmp     edi, r12d
0x14001c06b  jnb     loc_14001C12B
0x14001c071  cmp     [rbp+te.th32OwnerProcessID], r13d
0x14001c075  jnz     loc_14001C109
0x14001c07b  test    r15, r15
0x14001c07e  jz      loc_14001C107
0x14001c084  mov     r8d, [rbp+te.th32ThreadID]; dwThreadId
0x14001c088  xor     edx, edx; bInheritHandle
0x14001c08a  mov     ecx, ebx; dwDesiredAccess
0x14001c08c  call    cs:__imp_OpenThread
0x14001c093  nop     dword ptr [rax+rax+00h]
0x14001c098  mov     [r15+rdi*8], rax
0x14001c09c  test    rax, rax
0x14001c09f  jnz     short loc_14001C107
0x14001c0a1  call    cs:__imp_GetLastError
0x14001c0a8  nop     dword ptr [rax+rax+00h]
0x14001c0ad  mov     ecx, eax
0x14001c0af  test    eax, eax
0x14001c0b1  jle     short loc_14001C0BC
0x14001c0b3  movzx   ecx, ax
0x14001c0b6  or      ecx, 80070000h
0x14001c0bc  mov     rax, cs:WPP_GLOBAL_Control
0x14001c0c3  cmp     rax, rsi
0x14001c0c6  jz      short loc_14001C110
0x14001c0c8  test    byte ptr [rax+1Ch], 1
0x14001c0cc  jz      short loc_14001C110
0x14001c0ce  mov     rax, gs:30h
0x14001c0d7  mov     edx, 69h ; 'i'
0x14001c0dc  mov     eax, [rax+1250h]
0x14001c0e2  mov     [rsp+70h+var_48], eax
0x14001c0e6  mov     [rsp+70h+var_50], ecx
0x14001c0ea  mov     r9d, [rbp+te.th32ThreadID]
0x14001c0ee  lea     r8, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids
0x14001c0f5  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c0fc  mov     rcx, [rcx+10h]
0x14001c100  call    WPP_SF_DDD
0x14001c105  jmp     short loc_14001C110
0x14001c107  inc     edi
0x14001c109  mov     [rbp+te.dwSize], 1Ch
0x14001c110  lea     rdx, [rbp+te]; lpte
0x14001c114  mov     rcx, r14; hSnapshot
0x14001c117  call    cs:__imp_Thread32Next
0x14001c11e  nop     dword ptr [rax+rax+00h]
0x14001c123  test    eax, eax
0x14001c125  jnz     loc_14001C063
0x14001c12b  mov     rbx, [rbp+var_30]
0x14001c12f  test    rbx, rbx
0x14001c132  lea     r13, [r14+1]
0x14001c136  jz      short loc_14001C13A
0x14001c138  mov     [rbx], edi
0x14001c13a  mov     ebx, 80070490h
0x14001c13f  xor     eax, eax
0x14001c141  test    edi, edi
0x14001c143  cmovnz  ebx, eax
0x14001c146  jmp     short loc_14001C195
0x14001c148  call    cs:__imp_GetLastError
0x14001c14f  nop     dword ptr [rax+rax+00h]
0x14001c154  mov     ebx, eax
0x14001c156  test    eax, eax
0x14001c158  jle     short loc_14001C163
0x14001c15a  movzx   ebx, ax
0x14001c15d  or      ebx, 80070000h
0x14001c163  lea     rsi, WPP_GLOBAL_Control
0x14001c16a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c171  cmp     rcx, rsi
0x14001c174  jz      short loc_14001C195
0x14001c176  test    byte ptr [rcx+1Ch], 1
0x14001c17a  jz      short loc_14001C195
0x14001c17c  mov     edx, 67h ; 'g'
0x14001c181  mov     r9d, ebx
0x14001c184  lea     r8, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids
0x14001c18b  mov     rcx, [rcx+10h]
0x14001c18f  call    WPP_SF_d
0x14001c194  nop
0x14001c195  cmp     r13, 1
0x14001c199  jbe     short loc_14001C1AA
0x14001c19b  mov     rcx, r14; hObject
0x14001c19e  call    cs:__imp_CloseHandle
0x14001c1a5  nop     dword ptr [rax+rax+00h]
0x14001c1aa  mov     eax, ebx
0x14001c1ac  mov     rcx, [rbp+var_8]
0x14001c1b0  xor     rcx, rsp; StackCookie
0x14001c1b3  call    __security_check_cookie
0x14001c1b8  mov     rbx, [rsp+70h+arg_0]
0x14001c1c0  add     rsp, 70h
0x14001c1c4  pop     r15
0x14001c1c6  pop     r14
0x14001c1c8  pop     r13
0x14001c1ca  pop     r12
0x14001c1cc  pop     rdi
0x14001c1cd  pop     rsi
0x14001c1ce  pop     rbp
0x14001c1cf  retn
```
