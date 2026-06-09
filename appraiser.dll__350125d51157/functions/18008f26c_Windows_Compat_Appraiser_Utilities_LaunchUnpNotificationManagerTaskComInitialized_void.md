# Windows::Compat::Appraiser::Utilities::LaunchUnpNotificationManagerTaskComInitialized(void)

- ea: `0x18008f26c`
- end: `0x18008f756`
- name: `?LaunchUnpNotificationManagerTaskComInitialized@Utilities@Appraiser@Compat@Windows@@SAJXZ`
- size: `1258`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1800df914`

## callees

- `0x18002ebb8`
- `0x1800301d0`
- `0x18008f26c`
- `0x18021f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008f606`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008f606`
- `OLE32!CoCreateInstance` at `0x18008f2e7`
- `OLE32!CoCreateInstance` at `0x18008f2e7`
- `OLEAUT32!__imp_SysAllocString` at `0x18008f407`
- `OLEAUT32!__imp_SysAllocString` at `0x18008f407`
- `OLEAUT32!__imp_SysFreeString` at `0x18008f6cf`
- `OLEAUT32!__imp_SysFreeString` at `0x18008f6cf`

## string_xrefs

- `0x18008f30a`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x18008f337`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x18008f2f7`: `Failed to create task scheduler instance: [0x%x].`
- `0x18008f346`: `Failed to create task scheduler instance: [0x%x].`
- `0x18008f43d`: `Failed to get task folder for UNP: [0x%x].`
- `0x18008f47a`: `Failed to get task folder for UNP: [0x%x].`
- `0x18008f303`: `Windows::Compat::Appraiser::Utilities::LaunchUnpNotificationManagerTaskComInitialized`
- `0x18008f330`: `Windows::Compat::Appraiser::Utilities::LaunchUnpNotificationManagerTaskComInitialized`
- `0x18008f3bc`: `Failed to connect to task service: [0x%x].`
- `0x18008f3e9`: `Failed to connect to task service: [0x%x].`
- `0x18008f59c`: `Failed to get task: [0x%x].`
- `0x18008f6ae`: `Failed to get task: [0x%x].`
- `0x18008f5e3`: `Failed to get task name: [0x%x].`
- `0x18008f694`: `Failed to get task name: [0x%x].`
- `0x18008f4ae`: `Failed to get tasks in folder: [0x%x].`
- `0x18008f4cd`: `Failed to get tasks in folder: [0x%x].`
- `0x18008f4fe`: `Failed to get count of tasks in folder: [0x%x].`
- `0x18008f520`: `Failed to get count of tasks in folder: [0x%x].`
- `0x18008f5ff`: `RunUpdateNotificationMgr`
- `0x18008f655`: `Failed to run task: [0x%x].`
- `0x18008f677`: `Failed to run task: [0x%x].`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 Windows::Compat::Appraiser::Utilities::LaunchUnpNotificationManagerTaskComInitialized(void)
{
  HRESULT v0; // eax
  int v1; // ebx
  char v2; // dl
  int v3; // eax
  OLECHAR *v4; // r15
  int v5; // eax
  const char *v6; // r9
  char v7; // dl
  int v8; // r14d
  __int64 v9; // xmm6_8
  int v10; // eax
  LPVOID *ppv; // [rsp+28h] [rbp-E0h]
  const char *v13; // [rsp+30h] [rbp-D8h]
  const char *v14; // [rsp+30h] [rbp-D8h]
  char *v15; // [rsp+38h] [rbp-D0h]
  __int64 v16; // [rsp+48h] [rbp-C0h] BYREF
  _QWORD v17[3]; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v18; // [rsp+68h] [rbp-A0h]
  __int128 v19; // [rsp+78h] [rbp-90h]
  __int64 v20; // [rsp+88h] [rbp-80h]
  __int64 v21; // [rsp+90h] [rbp-78h]
  __int128 v22; // [rsp+98h] [rbp-70h] BYREF
  __int64 v23; // [rsp+A8h] [rbp-60h]
  __int128 v24; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v25; // [rsp+C8h] [rbp-40h]
  __int128 v26; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v27; // [rsp+E8h] [rbp-20h]
  int v28; // [rsp+168h] [rbp+60h] BYREF
  __int64 v29; // [rsp+170h] [rbp+68h] BYREF
  __int64 v30; // [rsp+178h] [rbp+70h] BYREF
  LPVOID v31; // [rsp+180h] [rbp+78h] BYREF

  v21 = -2;
  v28 = 0;
  v19 = 0;
  v20 = 0;
  v17[0] = 0;
  v31 = 0;
  v16 = 0;
  v30 = 0;
  v29 = 0;
  v0 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &v31);
  v1 = v0;
  if ( v0 < 0 )
  {
    LODWORD(v15) = v0;
    v13 = "Failed to create task scheduler instance: [0x%x].";
    v2 = 64;
LABEL_3:
    LODWORD(ppv) = v1;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      v2,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
      "Windows::Compat::Appraiser::Utilities::LaunchUnpNotificationManagerTaskComInitialized",
      (const char *)ppv,
      (int)v13,
      v15);
    goto LABEL_46;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x1940u,
      "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
      "Windows::Compat::Appraiser::Utilities::LaunchUnpNotificationManagerTaskComInitialized",
      "Failed to create task scheduler instance: [0x%x].",
      v0);
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  *(_OWORD *)&v17[1] = 0;
  v18 = 0;
  v3 = (*(__int64 (__fastcall **)(LPVOID, _QWORD *, __int128 *, __int128 *, __int128 *))(*(_QWORD *)v31 + 80LL))(
         v31,
         &v17[1],
         &v26,
         &v24,
         &v22);
  v1 = v3;
  if ( v3 < 0 )
  {
    LODWORD(v15) = v3;
    v13 = "Failed to connect to task service: [0x%x].";
    v2 = 69;
    goto LABEL_3;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x1945u,
      "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
      "Windows::Compat::Appraiser::Utilities::LaunchUnpNotificationManagerTaskComInitialized",
      "Failed to connect to task service: [0x%x].",
      v3);
  v4 = SysAllocString(L"\\Microsoft\\Windows\\UNP");
  v5 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, __int64 *))(*(_QWORD *)v31 + 56LL))(v31, v4, &v16);
  v1 = v5;
  if ( (unsigned int)(v5 + 2147024894) <= 1 )
  {
LABEL_43:
    v1 = 1;
  }
  else
  {
    if ( v5 >= 0 )
    {
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x1953u,
          "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
          "Windows::Compat::Appraiser::Utilities::LaunchUnpNotificationManagerTaskComInitialized",
          "Failed to get task folder for UNP: [0x%x].",
          v5);
      v1 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v16 + 112LL))(v16, 0, &v30);
      if ( v1 >= 0 )
      {
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0x1956u,
            "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
            "Windows::Compat::Appraiser::Utilities::LaunchUnpNotificationManagerTaskComInitialized",
            "Failed to get tasks in folder: [0x%x].",
            v1);
        v1 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v30 + 56LL))(v30, &v28);
        if ( v1 >= 0 )
        {
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0x1959u,
              "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
              "Windows::Compat::Appraiser::Utilities::LaunchUnpNotificationManagerTaskComInitialized",
              "Failed to get count of tasks in folder: [0x%x].",
              v1);
          v8 = 1;
          if ( v28 >= 1 )
          {
            v9 = v20;
            while ( 1 )
            {
              LOWORD(v19) = 3;
              DWORD2(v19) = v8;
              *(_OWORD *)&v17[1] = v19;
              v18 = v9;
              v1 = (*(__int64 (__fastcall **)(__int64, _QWORD *, __int64 *))(*(_QWORD *)v30 + 64LL))(v30, &v17[1], &v29);
              if ( v1 < 0 )
              {
                LODWORD(v15) = v1;
                v14 = "Failed to get task: [0x%x].";
                v7 = 97;
                goto LABEL_14;
              }
              if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
                Windows::Compat::Appraiser::WicaFactory::RunPrintf(
                  0x1961u,
                  "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
                  "Windows::Compat::Appraiser::Utilities::LaunchUnpNotificationManagerTaskComInitialized",
                  "Failed to get task: [0x%x].",
                  v1);
              v1 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v29 + 56LL))(v29, v17);
              if ( v1 < 0 )
              {
                LODWORD(v15) = v1;
                v14 = "Failed to get task name: [0x%x].";
                v7 = 100;
                goto LABEL_14;
              }
              if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
                Windows::Compat::Appraiser::WicaFactory::RunPrintf(
                  0x1964u,
                  "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
                  "Windows::Compat::Appraiser::Utilities::LaunchUnpNotificationManagerTaskComInitialized",
                  "Failed to get task name: [0x%x].",
                  v1);
              if ( !(unsigned int)_o__wcsicmp(L"RunUpdateNotificationMgr", v17[0]) )
                break;
              if ( ++v8 > v28 )
                goto LABEL_35;
            }
            *(_OWORD *)&v17[1] = 0;
            v18 = 0;
            v10 = (*(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD))(*(_QWORD *)v29 + 96LL))(v29, &v17[1], 0);
            v1 = v10;
            if ( v10 == -2147216602 )
              goto LABEL_43;
            if ( v10 < 0 )
            {
              v6 = "Failed to run task: [0x%x].";
              v7 = 116;
              goto LABEL_13;
            }
            if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
              Windows::Compat::Appraiser::WicaFactory::RunPrintf(
                0x1974u,
                "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
                "Windows::Compat::Appraiser::Utilities::LaunchUnpNotificationManagerTaskComInitialized",
                "Failed to run task: [0x%x].",
                v10);
          }
LABEL_35:
          v1 = 0;
          goto LABEL_44;
        }
        v6 = "Failed to get count of tasks in folder: [0x%x].";
        v7 = 89;
      }
      else
      {
        v6 = "Failed to get tasks in folder: [0x%x].";
        v7 = 86;
      }
    }
    else
    {
      v6 = "Failed to get task folder for UNP: [0x%x].";
      v7 = 83;
    }
LABEL_13:
    LODWORD(v15) = v1;
    LODWORD(v14) = (_DWORD)v6;
LABEL_14:
    LODWORD(ppv) = v1;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      v7,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
      "Windows::Compat::Appraiser::Utilities::LaunchUnpNotificationManagerTaskComInitialized",
      (const char *)ppv,
      (int)v14,
      v15);
  }
LABEL_44:
  if ( v4 )
    SysFreeString(v4);
LABEL_46:
  if ( v29 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  if ( v30 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  if ( v31 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v31 + 16LL))(v31);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18008f26c  mov     rax, rsp
0x18008f26f  push    rbp
0x18008f270  push    rbx
0x18008f271  push    rsi
0x18008f272  push    rdi
0x18008f273  push    r13
0x18008f275  push    r14
0x18008f277  push    r15
0x18008f279  lea     rbp, [rax-58h]
0x18008f27d  sub     rsp, 120h
0x18008f284  mov     [rbp+50h+var_C8], 0FFFFFFFFFFFFFFFEh
0x18008f28c  movaps  xmmword ptr [rax-48h], xmm6
0x18008f290  movaps  xmmword ptr [rax-58h], xmm7
0x18008f294  movaps  xmmword ptr [rax-68h], xmm8
0x18008f299  xorps   xmm7, xmm7
0x18008f29c  xor     r14d, r14d
0x18008f29f  mov     [rbp+50h+arg_0], r14d
0x18008f2a3  xorps   xmm0, xmm0
0x18008f2a6  xor     eax, eax
0x18008f2a8  movups  [rsp+150h+var_E8+8], xmm0
0x18008f2ad  mov     [rbp+50h+var_D0], rax
0x18008f2b1  mov     qword ptr [rsp+150h+var_108], rax
0x18008f2b6  mov     [rbp+50h+arg_18], rax
0x18008f2ba  mov     [rsp+150h+var_110], rax
0x18008f2bf  mov     [rbp+50h+arg_10], rax
0x18008f2c3  mov     [rbp+50h+arg_8], rax
0x18008f2c7  lea     rax, [rbp+50h+arg_18]
0x18008f2cb  mov     [rsp+150h+ppv], rax; ppv
0x18008f2d0  lea     r9, IID_ITaskService; riid
0x18008f2d7  lea     r13d, [r14+1]
0x18008f2db  mov     r8d, r13d; dwClsContext
0x18008f2de  xor     edx, edx; pUnkOuter
0x18008f2e0  lea     rcx, CLSID_TaskScheduler; rclsid
0x18008f2e7  call    cs:__imp_CoCreateInstance
0x18008f2ed  mov     ebx, eax
0x18008f2ef  test    eax, eax
0x18008f2f1  jns     short loc_18008F327
0x18008f2f3  mov     dword ptr [rsp+150h+var_120], eax; char *
0x18008f2f7  lea     r9, aFailedToCreate_27; "Failed to create task scheduler instanc"...
0x18008f2fe  mov     [rsp+150h+var_128], r9; int
0x18008f303  lea     r9, aWindowsCompatA_754; "Windows::Compat::Appraiser::Utilities::"...
0x18008f30a  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appcompat\\appraiser\\he"...
0x18008f311  mov     edx, 1940h; bool
0x18008f316  mov     dword ptr [rsp+150h+ppv], ebx; char *
0x18008f31a  mov     ecx, r13d; this
0x18008f31d  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x18008f322  jmp     loc_18008F6D6
0x18008f327  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18008f32d  and     eax, r13d
0x18008f330  lea     rdi, aWindowsCompatA_754; "Windows::Compat::Appraiser::Utilities::"...
0x18008f337  lea     rsi, aOnecoreBaseApp_7; "onecore\\base\\appcompat\\appraiser\\he"...
0x18008f33e  test    al, al
0x18008f340  jz      short loc_18008F35D
0x18008f342  mov     dword ptr [rsp+150h+ppv], ebx
0x18008f346  lea     r9, aFailedToCreate_27; "Failed to create task scheduler instanc"...
0x18008f34d  mov     r8, rdi; char *
0x18008f350  mov     rdx, rsi; char *
0x18008f353  mov     ecx, 1940h; unsigned int
0x18008f358  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18008f35d  mov     rcx, [rbp+50h+arg_18]
0x18008f361  movaps  [rbp+50h+var_C0], xmm7
0x18008f365  movq    xmm8, r14
0x18008f36a  movsd   [rbp+50h+var_B0], xmm8
0x18008f370  movaps  [rbp+50h+var_A0], xmm7
0x18008f374  movsd   [rbp+50h+var_90], xmm8
0x18008f37a  movaps  [rbp+50h+var_80], xmm7
0x18008f37e  movsd   [rbp+50h+var_70], xmm8
0x18008f384  movaps  xmmword ptr [rsp+150h+var_108+8], xmm7
0x18008f389  movsd   [rsp+150h+var_F0], xmm8
0x18008f390  mov     rax, [rcx]
0x18008f393  lea     rdx, [rbp+50h+var_C0]
0x18008f397  mov     [rsp+150h+ppv], rdx
0x18008f39c  lea     r9, [rbp+50h+var_A0]
0x18008f3a0  lea     r8, [rbp+50h+var_80]
0x18008f3a4  lea     rdx, [rsp+150h+var_108+8]
0x18008f3a9  mov     rax, [rax+50h]
0x18008f3ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f3b2  mov     ebx, eax
0x18008f3b4  test    eax, eax
0x18008f3b6  jns     short loc_18008F3D8
0x18008f3b8  mov     dword ptr [rsp+150h+var_120], eax
0x18008f3bc  lea     r9, aFailedToConnec_1; "Failed to connect to task service: [0x%"...
0x18008f3c3  mov     [rsp+150h+var_128], r9
0x18008f3c8  mov     r9, rdi
0x18008f3cb  mov     r8, rsi
0x18008f3ce  mov     edx, 1945h
0x18008f3d3  jmp     loc_18008F316
0x18008f3d8  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18008f3de  and     eax, r13d
0x18008f3e1  test    al, al
0x18008f3e3  jz      short loc_18008F400
0x18008f3e5  mov     dword ptr [rsp+150h+ppv], ebx
0x18008f3e9  lea     r9, aFailedToConnec_1; "Failed to connect to task service: [0x%"...
0x18008f3f0  mov     r8, rdi; char *
0x18008f3f3  mov     rdx, rsi; char *
0x18008f3f6  mov     ecx, 1945h; unsigned int
0x18008f3fb  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18008f400  lea     rcx, aMicrosoftWindo; "\\Microsoft\\Windows\\UNP"
0x18008f407  call    cs:__imp_SysAllocString
0x18008f40d  mov     r15, rax
0x18008f410  mov     rcx, [rbp+50h+arg_18]
0x18008f414  mov     rdx, [rcx]
0x18008f417  mov     rax, [rdx+38h]
0x18008f41b  lea     r8, [rsp+150h+var_110]
0x18008f420  mov     rdx, r15
0x18008f423  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f428  mov     ebx, eax
0x18008f42a  lea     ecx, [rax+7FF8FFFEh]
0x18008f430  cmp     ecx, r13d
0x18008f433  jbe     loc_18008F6C4
0x18008f439  test    eax, eax
0x18008f43b  jns     short loc_18008F469
0x18008f43d  lea     r9, aFailedToGetTas_2; "Failed to get task folder for UNP: [0x%"...
0x18008f444  mov     edx, 1953h; bool
0x18008f449  mov     dword ptr [rsp+150h+var_120], ebx; char *
0x18008f44d  mov     [rsp+150h+var_128], r9; int
0x18008f452  mov     r8, rsi; unsigned int
0x18008f455  mov     r9, rdi; char *
0x18008f458  mov     dword ptr [rsp+150h+ppv], ebx; char *
0x18008f45c  mov     ecx, r13d; this
0x18008f45f  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x18008f464  jmp     loc_18008F6C7
0x18008f469  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18008f46f  and     eax, r13d
0x18008f472  test    al, al
0x18008f474  jz      short loc_18008F491
0x18008f476  mov     dword ptr [rsp+150h+ppv], ebx
0x18008f47a  lea     r9, aFailedToGetTas_2; "Failed to get task folder for UNP: [0x%"...
0x18008f481  mov     r8, rdi; char *
0x18008f484  mov     rdx, rsi; char *
0x18008f487  mov     ecx, 1953h; unsigned int
0x18008f48c  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18008f491  mov     rcx, [rsp+150h+var_110]
0x18008f496  mov     rax, [rcx]
0x18008f499  lea     r8, [rbp+50h+arg_10]
0x18008f49d  xor     edx, edx
0x18008f49f  mov     rax, [rax+70h]
0x18008f4a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f4a8  mov     ebx, eax
0x18008f4aa  test    eax, eax
0x18008f4ac  jns     short loc_18008F4BC
0x18008f4ae  lea     r9, aFailedToGetTas_1; "Failed to get tasks in folder: [0x%x]."
0x18008f4b5  mov     edx, 1956h
0x18008f4ba  jmp     short loc_18008F449
0x18008f4bc  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18008f4c2  and     eax, r13d
0x18008f4c5  test    al, al
0x18008f4c7  jz      short loc_18008F4E4
0x18008f4c9  mov     dword ptr [rsp+150h+ppv], ebx
0x18008f4cd  lea     r9, aFailedToGetTas_1; "Failed to get tasks in folder: [0x%x]."
0x18008f4d4  mov     r8, rdi; char *
0x18008f4d7  mov     rdx, rsi; char *
0x18008f4da  mov     ecx, 1956h; unsigned int
0x18008f4df  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18008f4e4  mov     rcx, [rbp+50h+arg_10]
0x18008f4e8  mov     rax, [rcx]
0x18008f4eb  lea     rdx, [rbp+50h+arg_0]
0x18008f4ef  mov     rax, [rax+38h]
0x18008f4f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f4f8  mov     ebx, eax
0x18008f4fa  test    eax, eax
0x18008f4fc  jns     short loc_18008F50F
0x18008f4fe  lea     r9, aFailedToGetCou; "Failed to get count of tasks in folder:"...
0x18008f505  mov     edx, 1959h
0x18008f50a  jmp     loc_18008F449
0x18008f50f  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18008f515  and     eax, r13d
0x18008f518  test    al, al
0x18008f51a  jz      short loc_18008F537
0x18008f51c  mov     dword ptr [rsp+150h+ppv], ebx
0x18008f520  lea     r9, aFailedToGetCou; "Failed to get count of tasks in folder:"...
0x18008f527  mov     r8, rdi; char *
0x18008f52a  mov     rdx, rsi; char *
0x18008f52d  mov     ecx, 1959h; unsigned int
0x18008f532  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18008f537  mov     r14d, r13d
0x18008f53a  cmp     [rbp+50h+arg_0], r13d
0x18008f53e  jl      loc_18008F61D
0x18008f544  movsd   xmm6, [rbp+50h+var_D0]
0x18008f549  mov     eax, 3
0x18008f54e  mov     word ptr [rsp+150h+var_E8+8], ax
0x18008f553  mov     [rsp+150h+var_D8], r14d
0x18008f558  mov     rcx, [rbp+50h+arg_10]
0x18008f55c  movups  xmm0, [rsp+150h+var_E8+8]
0x18008f561  movaps  xmmword ptr [rsp+150h+var_108+8], xmm0
0x18008f566  movsd   [rsp+150h+var_F0], xmm6
0x18008f56c  mov     rax, [rcx]
0x18008f56f  lea     r8, [rbp+50h+arg_8]
0x18008f573  lea     rdx, [rsp+150h+var_108+8]
0x18008f578  mov     rax, [rax+40h]
0x18008f57c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f581  mov     ebx, eax
0x18008f583  test    eax, eax
0x18008f585  js      loc_18008F6AA
0x18008f58b  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18008f591  and     eax, r13d
0x18008f594  test    al, al
0x18008f596  jz      short loc_18008F5B3
0x18008f598  mov     dword ptr [rsp+150h+ppv], ebx
0x18008f59c  lea     r9, aFailedToGetTas_0; "Failed to get task: [0x%x]."
0x18008f5a3  mov     r8, rdi; char *
0x18008f5a6  mov     rdx, rsi; char *
0x18008f5a9  mov     ecx, 1961h; unsigned int
0x18008f5ae  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18008f5b3  mov     rcx, [rbp+50h+arg_8]
0x18008f5b7  mov     rax, [rcx]
0x18008f5ba  lea     rdx, [rsp+150h+var_108]
0x18008f5bf  mov     rax, [rax+38h]
0x18008f5c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f5c8  mov     ebx, eax
0x18008f5ca  test    eax, eax
0x18008f5cc  js      loc_18008F690
0x18008f5d2  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18008f5d8  and     eax, r13d
0x18008f5db  test    al, al
0x18008f5dd  jz      short loc_18008F5FA
0x18008f5df  mov     dword ptr [rsp+150h+ppv], ebx
0x18008f5e3  lea     r9, aFailedToGetTas; "Failed to get task name: [0x%x]."
0x18008f5ea  mov     r8, rdi; char *
0x18008f5ed  mov     rdx, rsi; char *
0x18008f5f0  mov     ecx, 1964h; unsigned int
0x18008f5f5  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18008f5fa  mov     rdx, qword ptr [rsp+150h+var_108]
0x18008f5ff  lea     rcx, aRunupdatenotif; "RunUpdateNotificationMgr"
0x18008f606  call    cs:__imp__o__wcsicmp
0x18008f60c  test    eax, eax
0x18008f60e  jz      short loc_18008F624
0x18008f610  add     r14d, r13d
0x18008f613  cmp     r14d, [rbp+50h+arg_0]
0x18008f617  jle     loc_18008F549
0x18008f61d  xor     ebx, ebx
0x18008f61f  jmp     loc_18008F6C7
0x18008f624  mov     rcx, [rbp+50h+arg_8]
0x18008f628  movaps  xmmword ptr [rsp+150h+var_108+8], xmm7
0x18008f62d  movsd   [rsp+150h+var_F0], xmm8
0x18008f634  mov     rax, [rcx]
0x18008f637  xor     r8d, r8d
0x18008f63a  lea     rdx, [rsp+150h+var_108+8]
0x18008f63f  mov     rax, [rax+60h]
0x18008f643  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f648  mov     ebx, eax
0x18008f64a  cmp     eax, 80041326h
0x18008f64f  jz      short loc_18008F6C4
0x18008f651  test    eax, eax
0x18008f653  jns     short loc_18008F666
0x18008f655  lea     r9, aFailedToRunTas; "Failed to run task: [0x%x]."
0x18008f65c  mov     edx, 1974h
0x18008f661  jmp     loc_18008F449
0x18008f666  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18008f66c  and     eax, r13d
0x18008f66f  test    al, al
0x18008f671  jz      short loc_18008F61D
0x18008f673  mov     dword ptr [rsp+150h+ppv], ebx
0x18008f677  lea     r9, aFailedToRunTas; "Failed to run task: [0x%x]."
0x18008f67e  mov     r8, rdi; char *
0x18008f681  mov     rdx, rsi; char *
0x18008f684  mov     ecx, 1974h; unsigned int
0x18008f689  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18008f68e  jmp     short loc_18008F61D
0x18008f690  mov     dword ptr [rsp+150h+var_120], ebx
0x18008f694  lea     rax, aFailedToGetTas; "Failed to get task name: [0x%x]."
0x18008f69b  mov     [rsp+150h+var_128], rax
0x18008f6a0  mov     edx, 1964h
0x18008f6a5  jmp     loc_18008F452
0x18008f6aa  mov     dword ptr [rsp+150h+var_120], ebx
0x18008f6ae  lea     rax, aFailedToGetTas_0; "Failed to get task: [0x%x]."
0x18008f6b5  mov     [rsp+150h+var_128], rax
0x18008f6ba  mov     edx, 1961h
0x18008f6bf  jmp     loc_18008F452
0x18008f6c4  mov     ebx, r13d
0x18008f6c7  test    r15, r15
0x18008f6ca  jz      short loc_18008F6D6
0x18008f6cc  mov     rcx, r15; bstrString
0x18008f6cf  call    cs:__imp_SysFreeString
0x18008f6d5  nop
0x18008f6d6  mov     rcx, [rbp+50h+arg_8]
0x18008f6da  test    rcx, rcx
0x18008f6dd  jz      short loc_18008F6EC
0x18008f6df  mov     rax, [rcx]
0x18008f6e2  mov     rax, [rax+10h]
0x18008f6e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f6eb  nop
0x18008f6ec  mov     rcx, [rbp+50h+arg_10]
0x18008f6f0  test    rcx, rcx
0x18008f6f3  jz      short loc_18008F702
0x18008f6f5  mov     rax, [rcx]
0x18008f6f8  mov     rax, [rax+10h]
0x18008f6fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f701  nop
0x18008f702  mov     rcx, [rsp+150h+var_110]
0x18008f707  test    rcx, rcx
0x18008f70a  jz      short loc_18008F719
0x18008f70c  mov     rax, [rcx]
0x18008f70f  mov     rax, [rax+10h]
0x18008f713  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f718  nop
0x18008f719  mov     rcx, [rbp+50h+arg_18]
0x18008f71d  test    rcx, rcx
0x18008f720  jz      short loc_18008F72F
0x18008f722  mov     rax, [rcx]
  ... truncated ...
```
