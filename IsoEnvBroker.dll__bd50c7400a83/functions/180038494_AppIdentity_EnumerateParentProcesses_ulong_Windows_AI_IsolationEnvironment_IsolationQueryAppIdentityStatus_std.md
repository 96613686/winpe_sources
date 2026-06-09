# AppIdentity::EnumerateParentProcesses(ulong,Windows::AI::IsolationEnvironment::IsolationQueryAppIdentityStatus &,std::shared_ptr<AppIdentity> &)

- ea: `0x180038494`
- end: `0x180038866`
- name: `?EnumerateParentProcesses@AppIdentity@@CAJKAEAW4IsolationQueryAppIdentityStatus@IsolationEnvironment@AI@Windows@@AEAV?$shared_ptr@VAppIdentity@@@std@@@Z`
- size: `978`
- prototype: `__int64 __fastcall(char *, _DWORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180039b3c`

## callees

- `0x1800029cc`
- `0x180002ee8`
- `0x18000a464`
- `0x180013230`
- `0x180038114`
- `0x180038494`
- `0x18003886c`
- `0x180039cb8`
- `0x180039d90`
- `0x180039fc0`

## import_xrefs

- `ntdll!NtQueryInformationProcess` at `0x180038630`
- `ntdll!NtQueryInformationProcess` at `0x180038630`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038679`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038679`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038671`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800386c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038671`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800386c7`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800385f3`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800385f3`

## string_xrefs

- `0x180038655`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\appidentity.cpp`
- `0x1800386a9`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\appidentity.cpp`
- `0x180038700`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\appidentity.cpp`
- `0x180038757`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\appidentity.cpp`
- `0x1800387f5`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\appidentity.cpp`
- `0x18003869a`: `[QueryAppIdentity] Failed to open process %d to get parent PID.`
- `0x1800386ec`: `[QueryAppIdentity] Found cycle. Process %d has already been visited.`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall AppIdentity::EnumerateParentProcesses(char *a1, _DWORD *a2)
{
  DWORD v3; // esi
  _QWORD *v4; // rax
  _QWORD *v5; // rcx
  int v6; // eax
  signed int v7; // edi
  void *v8; // rdi
  _QWORD *v9; // rax
  int v10; // ebx
  _BYTE *v11; // rcx
  _QWORD *v12; // r14
  _DWORD *v13; // rax
  DWORD v14; // r14d
  char *v15; // rbx
  NTSTATUS v16; // eax
  signed int LastError; // eax
  void *v18; // rcx
  _QWORD *v19; // rbx
  void *v20; // rcx
  _QWORD *v21; // rbx
  void *v22; // rcx
  void *v23; // rcx
  _QWORD *v24; // rbx
  void *v25; // rcx
  _QWORD *v27; // rbx
  void *v28; // rcx
  int ReturnLength; // [rsp+20h] [rbp-79h]
  char *v30; // [rsp+28h] [rbp-71h]
  void *v31; // [rsp+48h] [rbp-51h] BYREF
  __int64 v32; // [rsp+50h] [rbp-49h]
  _QWORD *v33; // [rsp+60h] [rbp-39h] BYREF
  int v34; // [rsp+68h] [rbp-31h]
  int v35; // [rsp+6Ch] [rbp-2Dh]
  void **v36; // [rsp+70h] [rbp-29h]
  __int64 v37; // [rsp+78h] [rbp-21h]
  _OWORD ProcessInformation[2]; // [rsp+80h] [rbp-19h] BYREF
  __int128 v39; // [rsp+A0h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]
  ULONG v41; // [rsp+118h] [rbp+7Fh] BYREF

  v3 = (unsigned int)a1;
  v32 = 0;
  v4 = operator new(0x20u);
  *v4 = v4;
  v4[1] = v4;
  v4[2] = v4;
  *((_WORD *)v4 + 12) = 257;
  v31 = v4;
  *a2 = 1;
  while ( 1 )
  {
    v5 = (_QWORD *)v4[1];
    HIDWORD(ProcessInformation[0]) = 0;
    while ( !*((_BYTE *)v5 + 25) )
    {
      if ( *((_DWORD *)v5 + 7) >= v3 )
      {
        v4 = v5;
        v5 = (_QWORD *)*v5;
      }
      else
      {
        v5 = (_QWORD *)v5[2];
      }
    }
    if ( !*((_BYTE *)v4 + 25) && v3 >= *((_DWORD *)v4 + 7) )
    {
      *a2 = 3;
      LODWORD(v30) = v3;
      v7 = -2147418113;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x1A9,
        (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\appidentity.cpp",
        (const char *)0x8000FFFFLL,
        (int)"[QueryAppIdentity] Found cycle. Process %d has already been visited.",
        v30);
      v18 = v31;
      v19 = (_QWORD *)*((_QWORD *)v31 + 1);
      if ( *((_BYTE *)v19 + 25) )
        goto LABEL_47;
      do
      {
        std::_Tree_val<std::_Tree_simple_types<unsigned long>>::_Erase_tree<std::allocator<std::_Tree_node<unsigned long,void *>>>(
          &v31,
          &v31,
          v19[2]);
        v20 = v19;
        v19 = (_QWORD *)*v19;
        operator delete(v20, (const struct std::nothrow_t *)0x20);
      }
      while ( !*((_BYTE *)v19 + 25) );
LABEL_46:
      v18 = v31;
      goto LABEL_47;
    }
    v6 = AppIdentity::EvaluateCandidateClientProcess((char *)v3);
    v7 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1B0,
        (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\appidentity.cpp",
        (const char *)(unsigned int)v6,
        ReturnLength);
      v18 = v31;
      v27 = (_QWORD *)*((_QWORD *)v31 + 1);
      if ( *((_BYTE *)v27 + 25) )
        goto LABEL_47;
      do
      {
        std::_Tree_val<std::_Tree_simple_types<unsigned long>>::_Erase_tree<std::allocator<std::_Tree_node<unsigned long,void *>>>(
          &v31,
          &v31,
          v27[2]);
        v28 = v27;
        v27 = (_QWORD *)*v27;
        operator delete(v28, (const struct std::nothrow_t *)0x20);
      }
      while ( !*((_BYTE *)v27 + 25) );
      goto LABEL_46;
    }
    if ( !*a2 )
      break;
    v8 = v31;
    v9 = (_QWORD *)*((_QWORD *)v31 + 1);
    v10 = 0;
    v11 = v31;
    if ( *((_BYTE *)v9 + 25) )
    {
      v12 = (_QWORD *)*((_QWORD *)v31 + 1);
    }
    else
    {
      do
      {
        v12 = v9;
        *(_QWORD *)&ProcessInformation[0] = v9;
        if ( *((_DWORD *)v9 + 7) >= v3 )
        {
          v10 = 1;
          v11 = v9;
          v9 = (_QWORD *)*v9;
        }
        else
        {
          v10 = 0;
          v9 = (_QWORD *)v9[2];
        }
      }
      while ( !*((_BYTE *)v9 + 25) );
    }
    if ( v11[25] || v3 < *((_DWORD *)v11 + 7) )
    {
      if ( v32 == 0x7FFFFFFFFFFFFFFLL )
        std::_Throw_tree_length_error();
      v36 = &v31;
      v37 = 0;
      v13 = operator new(0x20u);
      v13[7] = v3;
      *(_QWORD *)v13 = v8;
      *((_QWORD *)v13 + 1) = v8;
      *((_QWORD *)v13 + 2) = v8;
      *((_WORD *)v13 + 12) = 0;
      v37 = 0;
      v33 = v12;
      v34 = v10;
      v35 = 0;
      std::_Tree_val<std::_Tree_simple_types<unsigned long>>::_Insert_node(&v31, &v33, v13);
    }
    v14 = 0;
    v15 = (char *)OpenProcess(0x400u, 0, v3);
    if ( (unsigned __int64)(v15 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      memset(ProcessInformation, 0, sizeof(ProcessInformation));
      v39 = 0;
      v41 = 0;
      v16 = NtQueryInformationProcess(v15, ProcessBasicInformation, ProcessInformation, 0x30u, &v41);
      if ( v16 >= 0 )
      {
        v14 = DWORD2(v39);
        CloseHandle(v15);
        goto LABEL_33;
      }
      LODWORD(v30) = v3;
      v7 = wil::details::in1diag3::Return_NtStatusMsg(
             retaddr,
             (void *)0x189,
             (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\appidentity.cpp",
             (const char *)(unsigned int)v16,
             (int)"[QueryAppIdentity] NtQueryInformationProcess failed for process %d to get parent PID. NTSTATUS: 0x%08X",
             v30);
LABEL_31:
      CloseHandle(v15);
      goto LABEL_32;
    }
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    if ( v7 < 0 )
    {
      LODWORD(v30) = v3;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x17C,
        (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\appidentity.cpp",
        (const char *)(unsigned int)v7,
        (int)"[QueryAppIdentity] Failed to open process %d to get parent PID.",
        v30);
    }
    if ( (unsigned __int64)(v15 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      goto LABEL_31;
LABEL_32:
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1BC,
        (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\appidentity.cpp",
        (const char *)(unsigned int)v7,
        ReturnLength);
      v18 = v31;
      v21 = (_QWORD *)*((_QWORD *)v31 + 1);
      if ( !*((_BYTE *)v21 + 25) )
      {
        do
        {
          std::_Tree_val<std::_Tree_simple_types<unsigned long>>::_Erase_tree<std::allocator<std::_Tree_node<unsigned long,void *>>>(
            &v31,
            &v31,
            v21[2]);
          v22 = v21;
          v21 = (_QWORD *)*v21;
          operator delete(v22, (const struct std::nothrow_t *)0x20);
        }
        while ( !*((_BYTE *)v21 + 25) );
        goto LABEL_46;
      }
LABEL_47:
      operator delete(v18, (const struct std::nothrow_t *)0x20);
      return (unsigned int)v7;
    }
LABEL_33:
    v3 = v14;
    v4 = v31;
  }
  v23 = v31;
  v24 = (_QWORD *)*((_QWORD *)v31 + 1);
  if ( !*((_BYTE *)v24 + 25) )
  {
    do
    {
      std::_Tree_val<std::_Tree_simple_types<unsigned long>>::_Erase_tree<std::allocator<std::_Tree_node<unsigned long,void *>>>(
        &v31,
        &v31,
        v24[2]);
      v25 = v24;
      v24 = (_QWORD *)*v24;
      operator delete(v25, (const struct std::nothrow_t *)0x20);
    }
    while ( !*((_BYTE *)v24 + 25) );
    v23 = v31;
  }
  operator delete(v23, (const struct std::nothrow_t *)0x20);
  return 0;
}

```

## disassembly

```asm
0x180038494  push    rbp
0x180038496  push    rbx
0x180038497  push    rsi
0x180038498  push    rdi
0x180038499  push    r12
0x18003849b  push    r13
0x18003849d  push    r14
0x18003849f  push    r15
0x1800384a1  lea     rbp, [rsp-1Fh]
0x1800384a6  sub     rsp, 0B8h
0x1800384ad  mov     r12, r8
0x1800384b0  mov     r15, rdx
0x1800384b3  mov     esi, ecx
0x1800384b5  xor     r13d, r13d
0x1800384b8  mov     [rbp+57h+var_A8], r13
0x1800384bc  mov     [rbp+57h+var_A0], r13
0x1800384c0  lea     ecx, [r13+20h]; Size
0x1800384c4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800384c9  mov     [rax], rax
0x1800384cc  mov     [rax+8], rax
0x1800384d0  mov     [rax+10h], rax
0x1800384d4  mov     word ptr [rax+18h], 101h
0x1800384da  mov     [rbp+57h+var_A8], rax
0x1800384de  mov     dword ptr [r15], 1
0x1800384e5  mov     rcx, [rax+8]
0x1800384e9  xor     edx, edx
0x1800384eb  mov     dword ptr [rbp+57h+ProcessInformation+0Ch], edx
0x1800384ee  jmp     short loc_180038501
0x1800384f0  cmp     [rcx+1Ch], esi
0x1800384f3  jnb     short loc_1800384FB
0x1800384f5  mov     rcx, [rcx+10h]
0x1800384f9  jmp     short loc_180038501
0x1800384fb  mov     rax, rcx
0x1800384fe  mov     rcx, [rcx]
0x180038501  cmp     [rcx+19h], r13b
0x180038505  jz      short loc_1800384F0
0x180038507  cmp     [rax+19h], r13b
0x18003850b  jnz     short loc_180038516
0x18003850d  cmp     esi, [rax+1Ch]
0x180038510  jnb     loc_1800386DD
0x180038516  mov     r8, r12
0x180038519  mov     rdx, r15
0x18003851c  mov     ecx, esi; char *
0x18003851e  call    ?EvaluateCandidateClientProcess@AppIdentity@@CAJKAEAW4IsolationQueryAppIdentityStatus@IsolationEnvironment@AI@Windows@@AEAV?$shared_ptr@VAppIdentity@@@std@@@Z; AppIdentity::EvaluateCandidateClientProcess(ulong,Windows::AI::IsolationEnvironment::IsolationQueryAppIdentityStatus &,std::shared_ptr<AppIdentity> &)
0x180038523  mov     edi, eax
0x180038525  test    eax, eax
0x180038527  js      loc_1800387EE
0x18003852d  cmp     [r15], r13d
0x180038530  jz      loc_1800387A7
0x180038536  mov     rdi, [rbp+57h+var_A8]
0x18003853a  mov     rax, [rdi+8]
0x18003853e  mov     ebx, r13d
0x180038541  xor     ecx, ecx
0x180038543  mov     [rbp+57h+var_B0], rcx
0x180038547  mov     rcx, rdi
0x18003854a  cmp     [rax+19h], r13b
0x18003854e  jnz     short loc_180038578
0x180038550  mov     r14, rax
0x180038553  mov     qword ptr [rbp+57h+ProcessInformation], rax
0x180038557  cmp     [rax+1Ch], esi
0x18003855a  jnb     short loc_180038565
0x18003855c  mov     ebx, r13d
0x18003855f  mov     rax, [rax+10h]
0x180038563  jmp     short loc_180038570
0x180038565  mov     ebx, 1
0x18003856a  mov     rcx, rax
0x18003856d  mov     rax, [rax]
0x180038570  cmp     [rax+19h], r13b
0x180038574  jz      short loc_180038550
0x180038576  jmp     short loc_18003857B
0x180038578  mov     r14, rax
0x18003857b  cmp     [rcx+19h], r13b
0x18003857f  jnz     short loc_180038586
0x180038581  cmp     esi, [rcx+1Ch]
0x180038584  jnb     short loc_1800385E6
0x180038586  mov     rax, 7FFFFFFFFFFFFFFh
0x180038590  cmp     [rbp+57h+var_A0], rax
0x180038594  jz      loc_180038860
0x18003859a  lea     rax, [rbp+57h+var_A8]
0x18003859e  mov     [rbp+57h+var_80], rax
0x1800385a2  mov     [rbp+57h+var_78], r13
0x1800385a6  mov     ecx, 20h ; ' '; Size
0x1800385ab  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800385b0  nop
0x1800385b1  mov     [rax+1Ch], esi
0x1800385b4  mov     [rax], rdi
0x1800385b7  mov     [rax+8], rdi
0x1800385bb  mov     [rax+10h], rdi
0x1800385bf  mov     [rax+18h], r13w
0x1800385c4  mov     [rbp+57h+var_78], r13
0x1800385c8  mov     [rbp+57h+var_90], r14
0x1800385cc  mov     [rbp+57h+var_88], ebx
0x1800385cf  mov     rcx, [rbp+57h+var_B0]
0x1800385d3  mov     [rbp+57h+var_84], ecx
0x1800385d6  mov     r8, rax
0x1800385d9  lea     rdx, [rbp+57h+var_90]
0x1800385dd  lea     rcx, [rbp+57h+var_A8]
0x1800385e1  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@K@std@@@std@@QEAAPEAU?$_Tree_node@KPEAX@2@U?$_Tree_id@PEAU?$_Tree_node@KPEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<ulong>>::_Insert_node(std::_Tree_id<std::_Tree_node<ulong,void *> *>,std::_Tree_node<ulong,void *> * const)
0x1800385e6  mov     r14d, r13d
0x1800385e9  mov     r8d, esi; dwProcessId
0x1800385ec  xor     edx, edx; bInheritHandle
0x1800385ee  mov     ecx, 400h; dwDesiredAccess
0x1800385f3  call    cs:__imp_OpenProcess
0x1800385f9  mov     rbx, rax
0x1800385fc  dec     rax
0x1800385ff  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180038603  ja      short loc_180038679
0x180038605  xorps   xmm0, xmm0
0x180038608  movups  [rbp+57h+ProcessInformation], xmm0
0x18003860c  movups  [rbp+57h+var_60], xmm0
0x180038610  movups  [rbp+57h+var_50], xmm0
0x180038614  mov     [rbp+57h+arg_18], r13d
0x180038618  lea     rax, [rbp+57h+arg_18]
0x18003861c  mov     [rsp+0F0h+ReturnLength], rax; ReturnLength
0x180038621  mov     r9d, 30h ; '0'; ProcessInformationLength
0x180038627  lea     r8, [rbp+57h+ProcessInformation]; ProcessInformation
0x18003862b  xor     edx, edx; ProcessInformationClass
0x18003862d  mov     rcx, rbx; ProcessHandle
0x180038630  call    cs:__imp_NtQueryInformationProcess
0x180038636  test    eax, eax
0x180038638  jns     short loc_18003866A
0x18003863a  mov     rcx, [rbp+5Fh]; this
0x18003863e  mov     [rsp+0F0h+var_C0], eax
0x180038642  mov     dword ptr [rsp+0F0h+var_C8], esi; char *
0x180038646  lea     rdx, aQueryappidenti_36; "[QueryAppIdentity] NtQueryInformationPr"...
0x18003864d  mov     [rsp+0F0h+ReturnLength], rdx; int
0x180038652  mov     r9d, eax; char *
0x180038655  lea     r8, aOnecoreuapWind_0; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18003865c  mov     edx, 189h; void *
0x180038661  call    ?Return_NtStatusMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x180038666  mov     edi, eax
0x180038668  jmp     short loc_1800386C4
0x18003866a  mov     r14d, dword ptr [rbp+57h+var_50+8]
0x18003866e  mov     rcx, rbx; hObject
0x180038671  call    cs:__imp_CloseHandle
0x180038677  jmp     short loc_1800386D1
0x180038679  call    cs:__imp_GetLastError
0x18003867f  mov     edi, eax
0x180038681  test    eax, eax
0x180038683  jle     short loc_18003868E
0x180038685  movzx   edi, ax
0x180038688  or      edi, 80070000h
0x18003868e  test    edi, edi
0x180038690  jns     short loc_1800386BA
0x180038692  mov     rcx, [rbp+5Fh]; this
0x180038696  mov     dword ptr [rsp+0F0h+var_C8], esi; char *
0x18003869a  lea     rax, aQueryappidenti_32; "[QueryAppIdentity] Failed to open proce"...
0x1800386a1  mov     [rsp+0F0h+ReturnLength], rax; int
0x1800386a6  mov     r9d, edi; char *
0x1800386a9  lea     r8, aOnecoreuapWind_0; "onecoreuap\\windows\\core\\isoenvbroker"...
0x1800386b0  mov     edx, 17Ch; void *
0x1800386b5  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800386ba  lea     rax, [rbx-1]
0x1800386be  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800386c2  ja      short loc_1800386CD
0x1800386c4  mov     rcx, rbx; hObject
0x1800386c7  call    cs:__imp_CloseHandle
0x1800386cd  test    edi, edi
0x1800386cf  js      short loc_180038750
0x1800386d1  mov     esi, r14d
0x1800386d4  mov     rax, [rbp+57h+var_A8]
0x1800386d8  jmp     loc_1800384E5
0x1800386dd  mov     dword ptr [r15], 3
0x1800386e4  mov     rcx, [rbp+5Fh]; this
0x1800386e8  mov     dword ptr [rsp+0F0h+var_C8], esi; char *
0x1800386ec  lea     rax, aQueryappidenti_22; "[QueryAppIdentity] Found cycle. Process"...
0x1800386f3  mov     [rsp+0F0h+ReturnLength], rax; int
0x1800386f8  mov     edi, 8000FFFFh
0x1800386fd  mov     r9d, edi; char *
0x180038700  lea     r8, aOnecoreuapWind_0; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180038707  mov     edx, 1A9h; void *
0x18003870c  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180038711  nop
0x180038712  mov     rcx, [rbp+57h+var_A8]
0x180038716  mov     rbx, [rcx+8]
0x18003871a  cmp     [rbx+19h], r13b
0x18003871e  jnz     loc_180038840
0x180038724  mov     r8, [rbx+10h]
0x180038728  lea     rdx, [rbp+57h+var_A8]
0x18003872c  lea     rcx, [rbp+57h+var_A8]
0x180038730  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@KPEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@K@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@KPEAX@std@@@1@PEAU?$_Tree_node@KPEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<ulong>>::_Erase_tree<std::allocator<std::_Tree_node<ulong,void *>>>(std::allocator<std::_Tree_node<ulong,void *>> &,std::_Tree_node<ulong,void *> *)
0x180038735  mov     rcx, rbx; void *
0x180038738  mov     rbx, [rbx]
0x18003873b  mov     edx, 20h ; ' '; struct std::nothrow_t *
0x180038740  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180038745  cmp     [rbx+19h], r13b
0x180038749  jz      short loc_180038724
0x18003874b  jmp     loc_18003883C
0x180038750  mov     rcx, [rbp+5Fh]; this
0x180038754  mov     r9d, edi; char *
0x180038757  lea     r8, aOnecoreuapWind_0; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18003875e  mov     edx, 1BCh; void *
0x180038763  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038768  nop
0x180038769  mov     rcx, [rbp+57h+var_A8]
0x18003876d  mov     rbx, [rcx+8]
0x180038771  cmp     [rbx+19h], r13b
0x180038775  jnz     loc_180038840
0x18003877b  mov     r8, [rbx+10h]
0x18003877f  lea     rdx, [rbp+57h+var_A8]
0x180038783  lea     rcx, [rbp+57h+var_A8]
0x180038787  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@KPEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@K@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@KPEAX@std@@@1@PEAU?$_Tree_node@KPEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<ulong>>::_Erase_tree<std::allocator<std::_Tree_node<ulong,void *>>>(std::allocator<std::_Tree_node<ulong,void *>> &,std::_Tree_node<ulong,void *> *)
0x18003878c  mov     rcx, rbx; void *
0x18003878f  mov     rbx, [rbx]
0x180038792  mov     edx, 20h ; ' '; struct std::nothrow_t *
0x180038797  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003879c  cmp     [rbx+19h], r13b
0x1800387a0  jz      short loc_18003877B
0x1800387a2  jmp     loc_18003883C
0x1800387a7  mov     rcx, [rbp+57h+var_A8]
0x1800387ab  mov     rbx, [rcx+8]
0x1800387af  cmp     [rbx+19h], r13b
0x1800387b3  jnz     short loc_1800387E0
0x1800387b5  mov     r8, [rbx+10h]
0x1800387b9  lea     rdx, [rbp+57h+var_A8]
0x1800387bd  lea     rcx, [rbp+57h+var_A8]
0x1800387c1  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@KPEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@K@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@KPEAX@std@@@1@PEAU?$_Tree_node@KPEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<ulong>>::_Erase_tree<std::allocator<std::_Tree_node<ulong,void *>>>(std::allocator<std::_Tree_node<ulong,void *>> &,std::_Tree_node<ulong,void *> *)
0x1800387c6  mov     rcx, rbx; void *
0x1800387c9  mov     rbx, [rbx]
0x1800387cc  mov     edx, 20h ; ' '; struct std::nothrow_t *
0x1800387d1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800387d6  cmp     [rbx+19h], r13b
0x1800387da  jz      short loc_1800387B5
0x1800387dc  mov     rcx, [rbp+57h+var_A8]; void *
0x1800387e0  mov     edx, 20h ; ' '; struct std::nothrow_t *
0x1800387e5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800387ea  xor     eax, eax
0x1800387ec  jmp     short loc_18003884C
0x1800387ee  mov     rcx, [rbp+5Fh]; this
0x1800387f2  mov     r9d, edi; char *
0x1800387f5  lea     r8, aOnecoreuapWind_0; "onecoreuap\\windows\\core\\isoenvbroker"...
0x1800387fc  mov     edx, 1B0h; void *
0x180038801  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038806  nop
0x180038807  mov     rcx, [rbp+57h+var_A8]
0x18003880b  mov     rbx, [rcx+8]
0x18003880f  cmp     [rbx+19h], r13b
0x180038813  jnz     short loc_180038840
0x180038815  mov     r8, [rbx+10h]
0x180038819  lea     rdx, [rbp+57h+var_A8]
0x18003881d  lea     rcx, [rbp+57h+var_A8]
0x180038821  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@KPEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@K@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@KPEAX@std@@@1@PEAU?$_Tree_node@KPEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<ulong>>::_Erase_tree<std::allocator<std::_Tree_node<ulong,void *>>>(std::allocator<std::_Tree_node<ulong,void *>> &,std::_Tree_node<ulong,void *> *)
0x180038826  mov     rcx, rbx; void *
0x180038829  mov     rbx, [rbx]
0x18003882c  mov     edx, 20h ; ' '; struct std::nothrow_t *
0x180038831  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180038836  cmp     [rbx+19h], r13b
0x18003883a  jz      short loc_180038815
0x18003883c  mov     rcx, [rbp+57h+var_A8]; void *
0x180038840  mov     edx, 20h ; ' '; struct std::nothrow_t *
0x180038845  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003884a  mov     eax, edi
0x18003884c  add     rsp, 0B8h
0x180038853  pop     r15
0x180038855  pop     r14
0x180038857  pop     r13
0x180038859  pop     r12
0x18003885b  pop     rdi
0x18003885c  pop     rsi
0x18003885d  pop     rbx
0x18003885e  pop     rbp
0x18003885f  retn
0x180038860  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
```
