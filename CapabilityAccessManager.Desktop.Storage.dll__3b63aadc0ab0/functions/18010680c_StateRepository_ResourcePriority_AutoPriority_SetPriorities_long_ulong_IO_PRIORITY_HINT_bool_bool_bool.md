# StateRepository::ResourcePriority::AutoPriority::SetPriorities(long,ulong,_IO_PRIORITY_HINT,bool,bool,bool *)

- ea: `0x18010680c`
- end: `0x180106bb1`
- name: `?SetPriorities@AutoPriority@ResourcePriority@StateRepository@@QEAAJJKW4_IO_PRIORITY_HINT@@_N1PEA_N@Z`
- size: `933`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800f8b68`

## callees

- `0x180003060`
- `0x1800eabf4`
- `0x1800f7630`
- `0x1800fb7f0`
- `0x1800fcde4`
- `0x18010680c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18010684a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801068c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180106943`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801069b6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180106a39`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180106aa7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180106b57`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18010684a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801068c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180106943`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801069b6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180106a39`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180106aa7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180106b57`
- `ntdll!NtSetInformationThread` at `0x1801068dc`
- `ntdll!NtSetInformationThread` at `0x1801069cd`
- `ntdll!NtSetInformationThread` at `0x180106abe`
- `ntdll!NtSetInformationThread` at `0x180106b6e`
- `ntdll!NtSetInformationThread` at `0x1801068dc`
- `ntdll!NtSetInformationThread` at `0x1801069cd`
- `ntdll!NtSetInformationThread` at `0x180106abe`
- `ntdll!NtSetInformationThread` at `0x180106b6e`
- `ntdll!NtQueryInformationThread` at `0x180106868`
- `ntdll!NtQueryInformationThread` at `0x18010695f`
- `ntdll!NtQueryInformationThread` at `0x180106a55`
- `ntdll!NtQueryInformationThread` at `0x180106868`
- `ntdll!NtQueryInformationThread` at `0x18010695f`
- `ntdll!NtQueryInformationThread` at `0x180106a55`

## string_xrefs

- `0x180106872`: `onecore\base\appmodel\StateRepository\DataAccessLayer\ResourcePriority.hpp`
- `0x180106918`: `onecore\base\appmodel\staterepository\dataaccesslayer\resourcepriority.cpp`
- `0x180106a09`: `onecore\base\appmodel\staterepository\dataaccesslayer\resourcepriority.cpp`
- `0x180106afe`: `onecore\base\appmodel\staterepository\dataaccesslayer\resourcepriority.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::ResourcePriority::AutoPriority::SetPriorities(char **a1)
{
  char *CurrentThread; // rcx
  NTSTATUS v3; // eax
  unsigned int v4; // r15d
  int v5; // ebx
  __int64 v6; // rdx
  HANDLE v7; // rcx
  NTSTATUS v8; // eax
  char *v9; // rcx
  NTSTATUS v10; // eax
  int v11; // esi
  __int64 v12; // rdx
  char *v13; // rcx
  NTSTATUS v14; // eax
  char *v15; // rcx
  NTSTATUS v16; // eax
  int v17; // esi
  char *v18; // rcx
  NTSTATUS v19; // eax
  int v20; // eax
  char *v21; // rcx
  NTSTATUS v22; // eax
  void *v23; // rdx
  unsigned int v24; // r8d
  int ReturnLength; // [rsp+20h] [rbp-40h]
  int ReturnLengtha; // [rsp+20h] [rbp-40h]
  int ReturnLengthb; // [rsp+20h] [rbp-40h]
  int ThreadInformation; // [rsp+30h] [rbp-30h] BYREF
  int v30; // [rsp+34h] [rbp-2Ch] BYREF
  _BYTE v31[12]; // [rsp+38h] [rbp-28h]
  __int64 v32; // [rsp+48h] [rbp-18h] BYREF
  int v33; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]

  CurrentThread = *a1;
  ThreadInformation = 0;
  if ( (unsigned __int64)(CurrentThread - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    CurrentThread = (char *)GetCurrentThread();
  v3 = NtQueryInformationThread(CurrentThread, ThreadActualBasePriority, &ThreadInformation, 4u, 0);
  v4 = 64;
  if ( v3 < 0 )
  {
    v5 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)0x7E,
           (unsigned int)"onecore\\base\\appmodel\\StateRepository\\DataAccessLayer\\ResourcePriority.hpp",
           (const char *)(unsigned int)v3,
           ReturnLength);
    if ( v5 < 0 )
    {
      v6 = 64;
LABEL_14:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v6,
        (unsigned int)"onecore\\base\\appmodel\\StateRepository\\DataAccessLayer\\ResourcePriority.hpp",
        (const char *)(unsigned int)v5,
        ReturnLength);
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x9F,
        (int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\resourcepriority.cpp",
        (const char *)(unsigned int)v5);
      goto LABEL_16;
    }
  }
  v30 = 8;
  if ( ThreadInformation < 8 )
  {
    if ( !*((_BYTE *)a1 + 8) )
    {
      *((_DWORD *)a1 + 3) = ThreadInformation;
      *((_BYTE *)a1 + 8) = 1;
    }
    v7 = *a1;
    if ( (unsigned __int64)(*a1 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      v7 = GetCurrentThread();
    v8 = NtSetInformationThread(v7, ThreadActualBasePriority, &v30, 4u);
    if ( v8 < 0 )
    {
      v5 = wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x8D,
             (unsigned int)"onecore\\base\\appmodel\\StateRepository\\DataAccessLayer\\ResourcePriority.hpp",
             (const char *)(unsigned int)v8,
             ReturnLength);
      if ( v5 < 0 )
      {
        v6 = 79;
        goto LABEL_14;
      }
    }
  }
  v5 = 0;
LABEL_16:
  v9 = a1[2];
  ThreadInformation = 0;
  if ( (unsigned __int64)(v9 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    v9 = (char *)GetCurrentThread();
  v10 = NtQueryInformationThread(v9, ThreadPagePriority, &ThreadInformation, 4u, 0);
  if ( v10 < 0 )
  {
    v11 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x7E,
            (unsigned int)"onecore\\base\\appmodel\\StateRepository\\DataAccessLayer\\ResourcePriority.hpp",
            (const char *)(unsigned int)v10,
            ReturnLengtha);
    if ( v11 < 0 )
    {
      v12 = 64;
LABEL_29:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"onecore\\base\\appmodel\\StateRepository\\DataAccessLayer\\ResourcePriority.hpp",
        (const char *)(unsigned int)v11,
        ReturnLengtha);
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xA5,
        (int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\resourcepriority.cpp",
        (const char *)(unsigned int)v11);
      goto LABEL_31;
    }
  }
  v30 = 5;
  if ( (unsigned int)ThreadInformation < 5 )
  {
    if ( !*((_BYTE *)a1 + 24) )
    {
      *((_DWORD *)a1 + 7) = ThreadInformation;
      *((_BYTE *)a1 + 24) = 1;
    }
    v13 = a1[2];
    if ( (unsigned __int64)(v13 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      v13 = (char *)GetCurrentThread();
    v14 = NtSetInformationThread(v13, ThreadPagePriority, &v30, 4u);
    if ( v14 < 0 )
    {
      v11 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0x8D,
              (unsigned int)"onecore\\base\\appmodel\\StateRepository\\DataAccessLayer\\ResourcePriority.hpp",
              (const char *)(unsigned int)v14,
              ReturnLengtha);
      if ( v11 < 0 )
      {
        v12 = 79;
        goto LABEL_29;
      }
    }
  }
  v11 = 0;
LABEL_31:
  v15 = a1[4];
  ThreadInformation = 0;
  if ( v5 >= 0 )
    v5 = v11;
  if ( (unsigned __int64)(v15 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    v15 = (char *)GetCurrentThread();
  v16 = NtQueryInformationThread(v15, ThreadIoPriority, &ThreadInformation, 4u, 0);
  if ( v16 < 0 )
  {
    v17 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x7E,
            (unsigned int)"onecore\\base\\appmodel\\StateRepository\\DataAccessLayer\\ResourcePriority.hpp",
            (const char *)(unsigned int)v16,
            ReturnLengthb);
    if ( v17 < 0 )
      goto LABEL_45;
  }
  v30 = 2;
  if ( ThreadInformation < 2 )
  {
    if ( !*((_BYTE *)a1 + 40) )
    {
      *((_DWORD *)a1 + 11) = ThreadInformation;
      *((_BYTE *)a1 + 40) = 1;
    }
    v18 = a1[4];
    if ( (unsigned __int64)(v18 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      v18 = (char *)GetCurrentThread();
    v19 = NtSetInformationThread(v18, ThreadIoPriority, &v30, 4u);
    if ( v19 < 0 )
    {
      v17 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0x8D,
              (unsigned int)"onecore\\base\\appmodel\\StateRepository\\DataAccessLayer\\ResourcePriority.hpp",
              (const char *)(unsigned int)v19,
              ReturnLengthb);
      if ( v17 < 0 )
      {
        v4 = 79;
LABEL_45:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v4,
          (unsigned int)"onecore\\base\\appmodel\\StateRepository\\DataAccessLayer\\ResourcePriority.hpp",
          (const char *)(unsigned int)v17,
          ReturnLengthb);
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xAB,
          (int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\resourcepriority.cpp",
          (const char *)(unsigned int)v17);
        goto LABEL_47;
      }
    }
  }
  v17 = 0;
LABEL_47:
  *(_QWORD *)&v31[4] = 0;
  v33 = 0;
  if ( v5 >= 0 )
    v5 = v17;
  *(_DWORD *)v31 = 1;
  v32 = 1;
  if ( !*((_BYTE *)a1 + 56) )
  {
    v20 = *(_DWORD *)&v31[8];
    *(char **)((char *)a1 + 60) = *(char **)v31;
    *((_DWORD *)a1 + 17) = v20;
    *((_BYTE *)a1 + 56) = 1;
  }
  v21 = a1[6];
  if ( (unsigned __int64)(v21 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    v21 = (char *)GetCurrentThread();
  v22 = NtSetInformationThread(v21, ThreadHideFromDebugger|0x20, &v32, 0xCu);
  if ( v22 < 0 )
    wil::details::in1diag3::_Log_NtStatus(retaddr, v23, v24, (const char *)(unsigned int)v22, ReturnLengthb);
  if ( v5 >= 0 )
    return 0;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18010680c  mov     [rsp-28h+arg_8], rbx
0x180106811  mov     [rsp-28h+arg_10], rsi
0x180106816  push    rbp
0x180106817  push    rdi
0x180106818  push    r12
0x18010681a  push    r14
0x18010681c  push    r15
0x18010681e  mov     rbp, rsp
0x180106821  sub     rsp, 60h
0x180106825  mov     rax, cs:__security_cookie
0x18010682c  xor     rax, rsp
0x18010682f  mov     [rbp+var_8], rax
0x180106833  xor     r12d, r12d
0x180106836  mov     rdi, rcx
0x180106839  mov     rcx, [rcx]
0x18010683c  mov     [rbp+ThreadInformation], r12d
0x180106840  lea     rax, [rcx-1]
0x180106844  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180106848  jbe     short loc_180106853
0x18010684a  call    cs:__imp_GetCurrentThread
0x180106850  mov     rcx, rax; ThreadHandle
0x180106853  mov     r9d, 4; ThreadInformationLength
0x180106859  mov     qword ptr [rsp+60h+ReturnLength], r12; int
0x18010685e  lea     r8, [rbp+ThreadInformation]; ThreadInformation
0x180106862  lea     esi, [r9+15h]
0x180106866  mov     edx, esi; ThreadInformationClass
0x180106868  call    cs:__imp_NtQueryInformationThread
0x18010686e  lea     r15d, [rsi+27h]
0x180106872  lea     r14, aOnecoreBaseApp_14; "onecore\\base\\appmodel\\StateRepositor"...
0x180106879  test    eax, eax
0x18010687b  jns     short loc_18010689A
0x18010687d  mov     rcx, [rbp+28h]; this
0x180106881  lea     edx, [rsi+65h]; void *
0x180106884  mov     r9d, eax; char *
0x180106887  mov     r8, r14; unsigned int
0x18010688a  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18010688f  mov     ebx, eax
0x180106891  test    eax, eax
0x180106893  jns     short loc_18010689A
0x180106895  mov     edx, r15d
0x180106898  jmp     short loc_180106905
0x18010689a  mov     eax, [rbp+ThreadInformation]
0x18010689d  mov     [rbp+var_2C], 8
0x1801068a4  cmp     eax, 8
0x1801068a7  jge     loc_18010692E
0x1801068ad  cmp     [rdi+8], r12b
0x1801068b1  jnz     short loc_1801068BA
0x1801068b3  mov     [rdi+0Ch], eax
0x1801068b6  mov     byte ptr [rdi+8], 1
0x1801068ba  mov     rcx, [rdi]
0x1801068bd  lea     rax, [rcx-1]
0x1801068c1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801068c5  jbe     short loc_1801068D0
0x1801068c7  call    cs:__imp_GetCurrentThread
0x1801068cd  mov     rcx, rax; ThreadHandle
0x1801068d0  mov     r9d, 4; ThreadInformationLength
0x1801068d6  lea     r8, [rbp+var_2C]; ThreadInformation
0x1801068da  mov     edx, esi; ThreadInformationClass
0x1801068dc  call    cs:__imp_NtSetInformationThread
0x1801068e2  test    eax, eax
0x1801068e4  jns     short loc_18010692E
0x1801068e6  mov     rcx, [rbp+28h]; this
0x1801068ea  mov     r9d, eax; char *
0x1801068ed  mov     r8, r14; unsigned int
0x1801068f0  mov     edx, 8Dh; void *
0x1801068f5  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1801068fa  mov     ebx, eax
0x1801068fc  test    eax, eax
0x1801068fe  jns     short loc_18010692E
0x180106900  mov     edx, 4Fh ; 'O'; void *
0x180106905  mov     rcx, [rbp+28h]; this
0x180106909  mov     r9d, ebx; char *
0x18010690c  mov     r8, r14; unsigned int
0x18010690f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180106914  mov     rcx, [rbp+28h]; this
0x180106918  lea     r8, aOnecoreBaseApp_5; "onecore\\base\\appmodel\\staterepositor"...
0x18010691f  mov     r9d, ebx; char *
0x180106922  mov     edx, 9Fh; void *
0x180106927  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18010692c  jmp     short loc_180106931
0x18010692e  mov     ebx, r12d
0x180106931  mov     rcx, [rdi+10h]
0x180106935  mov     [rbp+ThreadInformation], r12d
0x180106939  lea     rax, [rcx-1]
0x18010693d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180106941  jbe     short loc_18010694C
0x180106943  call    cs:__imp_GetCurrentThread
0x180106949  mov     rcx, rax; ThreadHandle
0x18010694c  mov     r9d, 4; ThreadInformationLength
0x180106952  mov     qword ptr [rsp+60h+ReturnLength], r12; int
0x180106957  lea     r8, [rbp+ThreadInformation]; ThreadInformation
0x18010695b  lea     edx, [r9+14h]; ThreadInformationClass
0x18010695f  call    cs:__imp_NtQueryInformationThread
0x180106965  test    eax, eax
0x180106967  jns     short loc_180106988
0x180106969  mov     rcx, [rbp+28h]; this
0x18010696d  mov     r9d, eax; char *
0x180106970  mov     r8, r14; unsigned int
0x180106973  mov     edx, 7Eh ; '~'; void *
0x180106978  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18010697d  mov     esi, eax
0x18010697f  test    eax, eax
0x180106981  jns     short loc_180106988
0x180106983  mov     edx, r15d
0x180106986  jmp     short loc_1801069F6
0x180106988  mov     eax, [rbp+ThreadInformation]
0x18010698b  mov     [rbp+var_2C], 5
0x180106992  cmp     eax, 5
0x180106995  jnb     loc_180106A1F
0x18010699b  cmp     [rdi+18h], r12b
0x18010699f  jnz     short loc_1801069A8
0x1801069a1  mov     [rdi+1Ch], eax
0x1801069a4  mov     byte ptr [rdi+18h], 1
0x1801069a8  mov     rcx, [rdi+10h]
0x1801069ac  lea     rax, [rcx-1]
0x1801069b0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801069b4  jbe     short loc_1801069BF
0x1801069b6  call    cs:__imp_GetCurrentThread
0x1801069bc  mov     rcx, rax; ThreadHandle
0x1801069bf  mov     r9d, 4; ThreadInformationLength
0x1801069c5  lea     r8, [rbp+var_2C]; ThreadInformation
0x1801069c9  lea     edx, [r9+14h]; ThreadInformationClass
0x1801069cd  call    cs:__imp_NtSetInformationThread
0x1801069d3  test    eax, eax
0x1801069d5  jns     short loc_180106A1F
0x1801069d7  mov     rcx, [rbp+28h]; this
0x1801069db  mov     r9d, eax; char *
0x1801069de  mov     r8, r14; unsigned int
0x1801069e1  mov     edx, 8Dh; void *
0x1801069e6  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1801069eb  mov     esi, eax
0x1801069ed  test    eax, eax
0x1801069ef  jns     short loc_180106A1F
0x1801069f1  mov     edx, 4Fh ; 'O'; void *
0x1801069f6  mov     rcx, [rbp+28h]; this
0x1801069fa  mov     r9d, esi; char *
0x1801069fd  mov     r8, r14; unsigned int
0x180106a00  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180106a05  mov     rcx, [rbp+28h]; this
0x180106a09  lea     r8, aOnecoreBaseApp_5; "onecore\\base\\appmodel\\staterepositor"...
0x180106a10  mov     r9d, esi; char *
0x180106a13  mov     edx, 0A5h; void *
0x180106a18  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180106a1d  jmp     short loc_180106A22
0x180106a1f  mov     esi, r12d
0x180106a22  mov     rcx, [rdi+20h]
0x180106a26  test    ebx, ebx
0x180106a28  mov     [rbp+ThreadInformation], r12d
0x180106a2c  cmovns  ebx, esi
0x180106a2f  lea     rax, [rcx-1]
0x180106a33  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180106a37  jbe     short loc_180106A42
0x180106a39  call    cs:__imp_GetCurrentThread
0x180106a3f  mov     rcx, rax; ThreadHandle
0x180106a42  mov     r9d, 4; ThreadInformationLength
0x180106a48  mov     qword ptr [rsp+60h+ReturnLength], r12; int
0x180106a4d  lea     r8, [rbp+ThreadInformation]; ThreadInformation
0x180106a51  lea     edx, [r9+12h]; ThreadInformationClass
0x180106a55  call    cs:__imp_NtQueryInformationThread
0x180106a5b  test    eax, eax
0x180106a5d  jns     short loc_180106A79
0x180106a5f  mov     rcx, [rbp+28h]; this
0x180106a63  mov     r9d, eax; char *
0x180106a66  mov     r8, r14; unsigned int
0x180106a69  mov     edx, 7Eh ; '~'; void *
0x180106a6e  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180106a73  mov     esi, eax
0x180106a75  test    eax, eax
0x180106a77  js      short loc_180106AE8
0x180106a79  mov     eax, [rbp+ThreadInformation]
0x180106a7c  mov     [rbp+var_2C], 2
0x180106a83  cmp     eax, 2
0x180106a86  jge     loc_180106B14
0x180106a8c  cmp     [rdi+28h], r12b
0x180106a90  jnz     short loc_180106A99
0x180106a92  mov     [rdi+2Ch], eax
0x180106a95  mov     byte ptr [rdi+28h], 1
0x180106a99  mov     rcx, [rdi+20h]
0x180106a9d  lea     rax, [rcx-1]
0x180106aa1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180106aa5  jbe     short loc_180106AB0
0x180106aa7  call    cs:__imp_GetCurrentThread
0x180106aad  mov     rcx, rax; ThreadHandle
0x180106ab0  mov     r9d, 4; ThreadInformationLength
0x180106ab6  lea     r8, [rbp+var_2C]; ThreadInformation
0x180106aba  lea     edx, [r9+12h]; ThreadInformationClass
0x180106abe  call    cs:__imp_NtSetInformationThread
0x180106ac4  test    eax, eax
0x180106ac6  jns     short loc_180106B14
0x180106ac8  mov     rcx, [rbp+28h]; this
0x180106acc  mov     r9d, eax; char *
0x180106acf  mov     r8, r14; unsigned int
0x180106ad2  mov     edx, 8Dh; void *
0x180106ad7  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180106adc  mov     esi, eax
0x180106ade  test    eax, eax
0x180106ae0  jns     short loc_180106B14
0x180106ae2  mov     r15d, 4Fh ; 'O'
0x180106ae8  mov     rcx, [rbp+28h]; this
0x180106aec  mov     r9d, esi; char *
0x180106aef  mov     r8, r14; unsigned int
0x180106af2  mov     edx, r15d; void *
0x180106af5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180106afa  mov     rcx, [rbp+28h]; this
0x180106afe  lea     r8, aOnecoreBaseApp_5; "onecore\\base\\appmodel\\staterepositor"...
0x180106b05  mov     r9d, esi; char *
0x180106b08  mov     edx, 0ABh; void *
0x180106b0d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180106b12  jmp     short loc_180106B17
0x180106b14  mov     esi, r12d
0x180106b17  test    ebx, ebx
0x180106b19  mov     [rbp+var_28+4], r12
0x180106b1d  mov     ecx, 1
0x180106b22  mov     [rbp+var_10], r12d
0x180106b26  cmovns  ebx, esi
0x180106b29  mov     dword ptr [rbp+var_28], ecx
0x180106b2c  mov     [rbp+var_18], rcx
0x180106b30  cmp     [rdi+38h], r12b
0x180106b34  jnz     short loc_180106B49
0x180106b36  movsd   xmm0, [rbp+var_28]
0x180106b3b  mov     eax, [rbp+var_20]
0x180106b3e  movsd   qword ptr [rdi+3Ch], xmm0
0x180106b43  mov     [rdi+44h], eax
0x180106b46  mov     [rdi+38h], cl
0x180106b49  mov     rcx, [rdi+30h]
0x180106b4d  lea     rax, [rcx-1]
0x180106b51  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180106b55  jbe     short loc_180106B60
0x180106b57  call    cs:__imp_GetCurrentThread
0x180106b5d  mov     rcx, rax; ThreadHandle
0x180106b60  mov     r9d, 0Ch; ThreadInformationLength
0x180106b66  lea     r8, [rbp+var_18]; ThreadInformation
0x180106b6a  lea     edx, [r9+25h]; ThreadInformationClass
0x180106b6e  call    cs:__imp_NtSetInformationThread
0x180106b74  test    eax, eax
0x180106b76  jns     short loc_180106B84
0x180106b78  mov     rcx, [rbp+28h]; this
0x180106b7c  mov     r9d, eax; char *
0x180106b7f  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x180106b84  test    ebx, ebx
0x180106b86  cmovns  ebx, r12d
0x180106b8a  mov     eax, ebx
0x180106b8c  mov     rcx, [rbp+var_8]
0x180106b90  xor     rcx, rsp; StackCookie
0x180106b93  call    __security_check_cookie
0x180106b98  lea     r11, [rsp+60h+var_s0]
0x180106b9d  mov     rbx, [r11+38h]
0x180106ba1  mov     rsi, [r11+40h]
0x180106ba5  mov     rsp, r11
0x180106ba8  pop     r15
0x180106baa  pop     r14
0x180106bac  pop     r12
0x180106bae  pop     rdi
0x180106baf  pop     rbp
0x180106bb0  retn
```
