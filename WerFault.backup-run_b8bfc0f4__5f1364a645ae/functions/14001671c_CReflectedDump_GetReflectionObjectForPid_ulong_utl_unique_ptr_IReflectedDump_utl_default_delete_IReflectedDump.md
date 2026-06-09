# CReflectedDump::GetReflectionObjectForPid(ulong,utl::unique_ptr<IReflectedDump,utl::default_delete<IReflectedDump>> *)

- ea: `0x14001671c`
- end: `0x140016ad7`
- name: `?GetReflectionObjectForPid@CReflectedDump@@SAJKPEAV?$unique_ptr@VIReflectedDump@@U?$default_delete@VIReflectedDump@@@utl@@@utl@@@Z`
- size: `955`
- prototype: `__int64 __fastcall(DWORD dwProcessId, void (__fastcall ****)(_QWORD, __int64))`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation`

## callers

- `0x140016b70`

## callees

- `0x140002494`
- `0x140002728`
- `0x1400030a8`
- `0x1400032ef`
- `0x140003313`
- `0x140003343`
- `0x14001444c`
- `0x140014474`
- `0x140015d00`
- `0x1400160a8`
- `0x14001671c`
- `0x14005d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400168d5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400168d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400168ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140016a88`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400168ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140016a88`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x140016805`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x140016822`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x140016805`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x140016822`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CReflectedDump::GetReflectionObjectForPid(
        DWORD dwProcessId,
        void (__fastcall ****a2)(_QWORD, __int64))
{
  void (__fastcall ***v4)(_QWORD, __int64); // rcx
  HANDLE v5; // r15
  signed int LastError_0; // eax
  unsigned int v7; // ebx
  HANDLE CurrentProcess_0; // rax
  _QWORD *v9; // rsi
  HANDLE EventW; // rax
  void *v11; // rcx
  signed int v12; // eax
  CUserModeHangReport *v13; // rcx
  void (__fastcall ***v14)(_QWORD, __int64); // rcx
  DWORD v15; // eax
  _QWORD *v16; // rbx
  WINBOOL Wow64Process; // [rsp+50h] [rbp+8h] BYREF
  WINBOOL v19; // [rsp+60h] [rbp+18h] BYREF

  if ( dwProcessId && a2 )
  {
    v4 = *a2;
    *a2 = 0;
    if ( v4 )
      (**v4)(v4, 1);
    v5 = OpenProcess_0(0x1FFFFFu, 0, dwProcessId);
    if ( (unsigned __int64)v5 + 1 <= 1 )
    {
      if ( GetLastError_0() != 5 )
      {
        LastError_0 = GetLastError_0();
        v7 = LastError_0;
        if ( LastError_0 > 0 )
          v7 = (unsigned __int16)LastError_0 | 0x80070000;
        if ( (v7 & 0x80000000) == 0 )
          v7 = -2147467259;
        if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids, v7);
        }
        return v7;
      }
      goto LABEL_18;
    }
    v19 = 0;
    Wow64Process = 0;
    CurrentProcess_0 = GetCurrentProcess_0();
    if ( IsWow64Process(CurrentProcess_0, &Wow64Process) && IsWow64Process(v5, &v19) )
    {
      if ( Wow64Process && !v19 )
      {
LABEL_18:
        v9 = operator new(0x440u, (const struct std::nothrow_t *)&std::nothrow);
        if ( v9 )
        {
          v9[1] = 0;
          *v9 = &CReflectedDumpClient::`vftable';
          v9[2] = 0;
          v9[3] = 0;
          *((_DWORD *)v9 + 8) = 0;
          memset_0((char *)v9 + 36, 0, 0x208u);
          memset_0((char *)v9 + 556, 0, 0x208u);
          *(_QWORD *)((char *)v9 + 1076) = 0;
          CReflectedDumpClient::Cleanup((CReflectedDumpClient *)v9);
          EventW = CreateEventW(0, 1, 0, 0);
          v11 = (void *)v9[1];
          v9[1] = EventW;
          if ( (unsigned __int64)v11 + 1 > 1 )
            CloseHandle(v11);
          if ( v9[1] == -1 || v9[1] == 0 )
          {
            v12 = GetLastError_0();
            v7 = v12;
            if ( v12 > 0 )
              v7 = (unsigned __int16)v12 | 0x80070000;
            if ( (v7 & 0x80000000) == 0 )
              v7 = -2147467259;
            v13 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids, v7);
              v13 = WPP_GLOBAL_Control;
            }
            if ( v13 != (CUserModeHangReport *)&WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 1) != 0 )
              WPP_SF_d(*((_QWORD *)v13 + 2), 48, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids, v7);
            CReflectedDumpClient::~CReflectedDumpClient((CReflectedDumpClient *)v9);
            operator delete(v9, (const struct std::nothrow_t *)0x440);
LABEL_49:
            if ( (unsigned __int64)v5 + 1 > 1 )
              CloseHandle(v5);
            return v7;
          }
        }
        else
        {
          v9 = 0;
        }
        v14 = *a2;
        *a2 = (void (__fastcall ***)(_QWORD, __int64))v9;
LABEL_42:
        if ( v14 )
          (**v14)(v14, 1);
        if ( *a2 )
        {
          v7 = 0;
        }
        else
        {
          v7 = -2147024882;
          if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids);
          }
        }
        goto LABEL_49;
      }
    }
    else if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v15 = GetLastError_0();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids, v15);
    }
    v16 = operator new(0x228u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v16 )
    {
      *v16 = &CReflectedDump::`vftable';
      memset_0(v16 + 1, 0, 0x208u);
      v16[66] = 0;
      v16[67] = 0;
      v16[68] = 0;
    }
    else
    {
      v16 = 0;
    }
    v14 = *a2;
    *a2 = (void (__fastcall ***)(_QWORD, __int64))v16;
    goto LABEL_42;
  }
  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids);
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x14001671c  mov     [rsp+arg_8], rbx
0x140016721  push    rbp
0x140016722  push    rsi
0x140016723  push    r13
0x140016725  push    r14
0x140016727  push    r15
0x140016729  sub     rsp, 20h
0x14001672d  mov     r14, rdx
0x140016730  mov     ebx, ecx
0x140016732  test    ecx, ecx
0x140016734  jz      loc_140016A92
0x14001673a  test    rdx, rdx
0x14001673d  jz      loc_140016A92
0x140016743  mov     rcx, [rdx]
0x140016746  mov     qword ptr [rdx], 0
0x14001674d  test    rcx, rcx
0x140016750  jz      short loc_140016762
0x140016752  mov     rax, [rcx]
0x140016755  mov     edx, 1
0x14001675a  mov     rax, [rax]
0x14001675d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016762  mov     r8d, ebx; dwProcessId
0x140016765  xor     edx, edx; bInheritHandle
0x140016767  mov     ecx, 1FFFFFh; dwDesiredAccess
0x14001676c  call    OpenProcess_0
0x140016771  mov     r15, rax
0x140016774  lea     r13, [rax+1]
0x140016778  cmp     r13, 1
0x14001677c  ja      short loc_1400167E8
0x14001677e  call    GetLastError_0
0x140016783  cmp     eax, 5
0x140016786  jz      loc_140016846
0x14001678c  call    GetLastError_0
0x140016791  mov     ebx, eax
0x140016793  test    eax, eax
0x140016795  jle     short loc_1400167A0
0x140016797  movzx   ebx, ax
0x14001679a  or      ebx, 80070000h
0x1400167a0  test    ebx, ebx
0x1400167a2  mov     eax, 80004005h
0x1400167a7  cmovns  ebx, eax
0x1400167aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400167b1  lea     rbp, WPP_GLOBAL_Control
0x1400167b8  cmp     rcx, rbp
0x1400167bb  jz      loc_140016A8E
0x1400167c1  test    byte ptr [rcx+1Ch], 1
0x1400167c5  jz      loc_140016A8E
0x1400167cb  mov     rcx, [rcx+10h]
0x1400167cf  lea     r8, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids
0x1400167d6  mov     edx, 31h ; '1'
0x1400167db  mov     r9d, ebx
0x1400167de  call    WPP_SF_d
0x1400167e3  jmp     loc_140016A8E
0x1400167e8  mov     [rsp+48h+arg_10], 0
0x1400167f0  mov     [rsp+48h+Wow64Process], 0
0x1400167f8  call    GetCurrentProcess_0
0x1400167fd  mov     rcx, rax; hProcess
0x140016800  lea     rdx, [rsp+48h+Wow64Process]; Wow64Process
0x140016805  call    cs:__imp_IsWow64Process
0x14001680b  lea     rbp, WPP_GLOBAL_Control
0x140016812  test    eax, eax
0x140016814  jz      loc_1400169A1
0x14001681a  lea     rdx, [rsp+48h+arg_10]; Wow64Process
0x14001681f  mov     rcx, r15; hProcess
0x140016822  call    cs:__imp_IsWow64Process
0x140016828  test    eax, eax
0x14001682a  jz      loc_1400169A1
0x140016830  cmp     [rsp+48h+Wow64Process], 0
0x140016835  jz      loc_1400169D7
0x14001683b  cmp     [rsp+48h+arg_10], 0
0x140016840  jnz     loc_1400169D7
0x140016846  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001684d  mov     ecx, 440h; unsigned __int64
0x140016852  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140016857  lea     rbp, WPP_GLOBAL_Control
0x14001685e  mov     rsi, rax
0x140016861  test    rax, rax
0x140016864  jz      loc_140016994
0x14001686a  lea     rax, ??_7CReflectedDumpClient@@6B@; const CReflectedDumpClient::`vftable'
0x140016871  mov     qword ptr [rsi+8], 0
0x140016879  lea     rcx, [rsi+24h]; void *
0x14001687d  mov     [rsi], rax
0x140016880  xor     edx, edx; Val
0x140016882  mov     qword ptr [rsi+10h], 0
0x14001688a  mov     r8d, 208h; Size
0x140016890  mov     qword ptr [rsi+18h], 0
0x140016898  mov     dword ptr [rsi+20h], 0
0x14001689f  call    memset_0
0x1400168a4  lea     rcx, [rsi+22Ch]; void *
0x1400168ab  xor     edx, edx; Val
0x1400168ad  mov     r8d, 208h; Size
0x1400168b3  call    memset_0
0x1400168b8  xor     eax, eax
0x1400168ba  mov     rcx, rsi; this
0x1400168bd  mov     [rsi+434h], rax
0x1400168c4  call    ?Cleanup@CReflectedDumpClient@@QEAAXXZ; CReflectedDumpClient::Cleanup(void)
0x1400168c9  xor     r9d, r9d; lpName
0x1400168cc  xor     r8d, r8d; bInitialState
0x1400168cf  xor     ecx, ecx; lpEventAttributes
0x1400168d1  lea     edx, [r9+1]; bManualReset
0x1400168d5  call    cs:__imp_CreateEventW
0x1400168db  mov     rcx, [rsi+8]; hObject
0x1400168df  mov     [rsi+8], rax
0x1400168e3  lea     rax, [rcx+1]
0x1400168e7  cmp     rax, 1
0x1400168eb  jbe     short loc_1400168F3
0x1400168ed  call    cs:__imp_CloseHandle
0x1400168f3  mov     rax, [rsi+8]
0x1400168f7  inc     rax
0x1400168fa  cmp     rax, 1
0x1400168fe  ja      loc_140016996
0x140016904  call    GetLastError_0
0x140016909  mov     ebx, eax
0x14001690b  test    eax, eax
0x14001690d  jle     short loc_140016918
0x14001690f  movzx   ebx, ax
0x140016912  or      ebx, 80070000h
0x140016918  test    ebx, ebx
0x14001691a  mov     eax, 80004005h
0x14001691f  cmovns  ebx, eax
0x140016922  mov     rcx, cs:WPP_GLOBAL_Control
0x140016929  cmp     rcx, rbp
0x14001692c  jz      short loc_140016953
0x14001692e  test    byte ptr [rcx+1Ch], 1
0x140016932  jz      short loc_140016953
0x140016934  mov     rcx, [rcx+10h]
0x140016938  lea     r8, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids
0x14001693f  mov     edx, 4Fh ; 'O'
0x140016944  mov     r9d, ebx
0x140016947  call    WPP_SF_d
0x14001694c  mov     rcx, cs:WPP_GLOBAL_Control
0x140016953  test    ebx, ebx
0x140016955  jns     short loc_140016996
0x140016957  cmp     rcx, rbp
0x14001695a  jz      short loc_14001697A
0x14001695c  test    byte ptr [rcx+1Ch], 1
0x140016960  jz      short loc_14001697A
0x140016962  mov     rcx, [rcx+10h]
0x140016966  lea     r8, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids
0x14001696d  mov     edx, 30h ; '0'
0x140016972  mov     r9d, ebx
0x140016975  call    WPP_SF_d
0x14001697a  mov     rcx, rsi; this
0x14001697d  call    ??1CReflectedDumpClient@@UEAA@XZ; CReflectedDumpClient::~CReflectedDumpClient(void)
0x140016982  mov     edx, 440h; struct std::nothrow_t *
0x140016987  mov     rcx, rsi; void *
0x14001698a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001698f  jmp     loc_140016A7F
0x140016994  xor     esi, esi
0x140016996  mov     rcx, [r14]
0x140016999  mov     [r14], rsi
0x14001699c  jmp     loc_140016A34
0x1400169a1  mov     rax, cs:WPP_GLOBAL_Control
0x1400169a8  cmp     rax, rbp
0x1400169ab  jz      short loc_1400169D7
0x1400169ad  test    byte ptr [rax+1Ch], 4
0x1400169b1  jz      short loc_1400169D7
0x1400169b3  call    GetLastError_0
0x1400169b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400169bf  lea     r8, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids
0x1400169c6  mov     edx, 2Eh ; '.'
0x1400169cb  mov     r9d, eax
0x1400169ce  mov     rcx, [rcx+10h]
0x1400169d2  call    WPP_SF_d
0x1400169d7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400169de  mov     ecx, 228h; unsigned __int64
0x1400169e3  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400169e8  mov     rbx, rax
0x1400169eb  test    rax, rax
0x1400169ee  jz      short loc_140016A2C
0x1400169f0  lea     rax, ??_7CReflectedDump@@6B@; const CReflectedDump::`vftable'
0x1400169f7  xor     edx, edx; Val
0x1400169f9  lea     rcx, [rbx+8]; void *
0x1400169fd  mov     [rbx], rax
0x140016a00  mov     r8d, 208h; Size
0x140016a06  call    memset_0
0x140016a0b  xor     eax, eax
0x140016a0d  mov     qword ptr [rbx+210h], 0
0x140016a18  mov     qword ptr [rbx+218h], 0
0x140016a23  mov     [rbx+220h], rax
0x140016a2a  jmp     short loc_140016A2E
0x140016a2c  xor     ebx, ebx
0x140016a2e  mov     rcx, [r14]
0x140016a31  mov     [r14], rbx
0x140016a34  test    rcx, rcx
0x140016a37  jz      short loc_140016A49
0x140016a39  mov     rax, [rcx]
0x140016a3c  mov     edx, 1
0x140016a41  mov     rax, [rax]
0x140016a44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016a49  cmp     qword ptr [r14], 0
0x140016a4d  jnz     short loc_140016A7D
0x140016a4f  mov     ebx, 8007000Eh
0x140016a54  mov     rcx, cs:WPP_GLOBAL_Control
0x140016a5b  cmp     rcx, rbp
0x140016a5e  jz      short loc_140016A7F
0x140016a60  test    byte ptr [rcx+1Ch], 1
0x140016a64  jz      short loc_140016A7F
0x140016a66  mov     rcx, [rcx+10h]
0x140016a6a  lea     r8, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids
0x140016a71  mov     edx, 32h ; '2'
0x140016a76  call    WPP_SF_
0x140016a7b  jmp     short loc_140016A7F
0x140016a7d  xor     ebx, ebx
0x140016a7f  cmp     r13, 1
0x140016a83  jbe     short loc_140016A8E
0x140016a85  mov     rcx, r15; hObject
0x140016a88  call    cs:__imp_CloseHandle
0x140016a8e  mov     eax, ebx
0x140016a90  jmp     short loc_140016AC5
0x140016a92  mov     rcx, cs:WPP_GLOBAL_Control
0x140016a99  lea     rbp, WPP_GLOBAL_Control
0x140016aa0  cmp     rcx, rbp
0x140016aa3  jz      short loc_140016AC0
0x140016aa5  test    byte ptr [rcx+1Ch], 1
0x140016aa9  jz      short loc_140016AC0
0x140016aab  mov     rcx, [rcx+10h]
0x140016aaf  lea     r8, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids
0x140016ab6  mov     edx, 2Fh ; '/'
0x140016abb  call    WPP_SF_
0x140016ac0  mov     eax, 80070057h
0x140016ac5  mov     rbx, [rsp+48h+arg_8]
0x140016aca  add     rsp, 20h
0x140016ace  pop     r15
0x140016ad0  pop     r14
0x140016ad2  pop     r13
0x140016ad4  pop     rsi
0x140016ad5  pop     rbp
0x140016ad6  retn
```
