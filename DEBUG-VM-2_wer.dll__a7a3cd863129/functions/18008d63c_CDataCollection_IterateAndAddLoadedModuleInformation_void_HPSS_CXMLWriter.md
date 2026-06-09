# CDataCollection::IterateAndAddLoadedModuleInformation(void *,HPSS__ *,CXMLWriter *)

- ea: `0x18008d63c`
- end: `0x18008d905`
- name: `?IterateAndAddLoadedModuleInformation@CDataCollection@@AEAAJPEAXPEAUHPSS__@@PEAVCXMLWriter@@@Z`
- size: `713`
- prototype: `int(CDataCollection *__hidden this, void *, struct HPSS__ *, struct CXMLWriter *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18008beb0`

## callees

- `0x18000716c`
- `0x180007e10`
- `0x180007e34`
- `0x18001fe24`
- `0x18003bf14`
- `0x180050db0`
- `0x1800517cc`
- `0x18008c0f4`
- `0x18008d63c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18008d6b6`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18008d732`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18008d6b6`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18008d732`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d785`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d7aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d7ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d785`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d7aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d7ff`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x18008d6d8`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x18008d6d8`
- `api-ms-win-core-toolhelp-l1-1-0!Module32NextW` at `0x18008d8cc`
- `api-ms-win-core-toolhelp-l1-1-0!Module32NextW` at `0x18008d8cc`
- `api-ms-win-core-toolhelp-l1-1-0!Module32FirstW` at `0x18008d7cf`
- `api-ms-win-core-toolhelp-l1-1-0!Module32FirstW` at `0x18008d7cf`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x18008d74a`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x18008d74a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDataCollection::IterateAndAddLoadedModuleInformation(
        CDataCollection *this,
        HANDLE a2,
        struct HPSS__ *a3,
        struct CXMLWriter *a4)
{
  __int64 v7; // rdx
  __int64 v8; // r8
  _BOOL8 v9; // rcx
  DWORD ProcessId; // eax
  int v11; // eax
  unsigned int v12; // ebx
  wchar_t *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  HANDLE Toolhelp32Snapshot; // rax
  HANDLE v17; // rbx
  DWORD LastError; // eax
  DWORD v19; // eax
  CDataCollection *v20; // rcx
  DWORD v21; // eax
  MODULEENTRY32W *p_me; // rcx
  _OWORD *v23; // rax
  __int64 v24; // rdx
  HANDLE Process; // [rsp+20h] [rbp-E0h] BYREF
  HANDLE hSnapshot; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v28[1088]; // [rsp+30h] [rbp-D0h] BYREF
  MODULEENTRY32W me; // [rsp+470h] [rbp+370h] BYREF

  hSnapshot = 0;
  Process = 0;
  memset_0(&me, 0, sizeof(me));
  v9 = a3 != 0;
  if ( v9 == (a2 != 0) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v9, v7, v8);
  if ( a2 )
  {
    ProcessId = GetProcessId(a2);
LABEL_15:
    Toolhelp32Snapshot = CreateToolhelp32Snapshot(8u, ProcessId);
    tlx::unique_any<tlx::file_handle_traits>::reset(&hSnapshot, Toolhelp32Snapshot);
    v17 = hSnapshot;
    if ( (unsigned __int64)hSnapshot + 1 <= 1 )
    {
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 134, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids, LastError);
      }
      v19 = GetLastError();
      v12 = ERROR_HR_FROM_WIN32(v19);
      goto LABEL_28;
    }
    me.dwSize = 1080;
    if ( !Module32FirstW(hSnapshot, &me) )
    {
      v12 = -2147467259;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_28;
      v21 = GetLastError();
      v14 = 135;
      v15 = v21;
      v13 = WPP_GLOBAL_Control;
LABEL_12:
      WPP_SF_d(*((_QWORD *)v13 + 2), v14, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids, v15);
      goto LABEL_28;
    }
    do
    {
      CDataCollection::AddModuleInformation(v20, a2, me.hModule, a4);
      memset_0(v28, 0, 0x438u);
      p_me = &me;
      v23 = v28;
      v24 = 8;
      do
      {
        *(_OWORD *)&p_me->dwSize = *v23;
        *(_OWORD *)&p_me->ProccntUsage = v23[1];
        *(_OWORD *)&p_me->modBaseSize = v23[2];
        *(_OWORD *)p_me->szModule = v23[3];
        *(_OWORD *)&p_me->szModule[8] = v23[4];
        *(_OWORD *)&p_me->szModule[16] = v23[5];
        *(_OWORD *)&p_me->szModule[24] = v23[6];
        *(_OWORD *)&p_me->szModule[32] = v23[7];
        p_me = (MODULEENTRY32W *)((char *)p_me + 128);
        v23 += 8;
        --v24;
      }
      while ( v24 );
      *(_OWORD *)&p_me->dwSize = *v23;
      *(_OWORD *)&p_me->ProccntUsage = v23[1];
      *(_OWORD *)&p_me->modBaseSize = v23[2];
      *(_QWORD *)p_me->szModule = *((_QWORD *)v23 + 6);
      me.dwSize = 1080;
    }
    while ( Module32NextW(v17, &me) );
    v12 = 0;
    goto LABEL_28;
  }
  if ( !a3 )
  {
    a2 = 0;
    ProcessId = 0;
    goto LABEL_15;
  }
  v11 = PssQuerySnapshot(a3, 1, &Process);
  v12 = v11;
  if ( !v11 )
  {
    ProcessId = GetProcessId(Process);
    a2 = Process;
    goto LABEL_15;
  }
  if ( v11 > 0 )
    v12 = (unsigned __int16)v11 | 0x80070000;
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v14 = 133;
    v15 = v12;
    goto LABEL_12;
  }
LABEL_28:
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hSnapshot);
  return v12;
}

```

## disassembly

```asm
0x18008d63c  push    rbp
0x18008d63e  push    rbx
0x18008d63f  push    rsi
0x18008d640  push    rdi
0x18008d641  push    r15
0x18008d643  lea     rbp, [rsp-7C0h]
0x18008d64b  sub     rsp, 8C0h
0x18008d652  mov     rax, cs:__security_cookie
0x18008d659  xor     rax, rsp
0x18008d65c  mov     [rbp+7E0h+var_30], rax
0x18008d663  mov     rsi, r9
0x18008d666  mov     rbx, r8
0x18008d669  mov     rdi, rdx
0x18008d66c  mov     [rsp+8E0h+hSnapshot], 0
0x18008d675  mov     [rsp+8E0h+Process], 0
0x18008d67e  mov     r15d, 438h
0x18008d684  mov     r8d, r15d; Size
0x18008d687  xor     edx, edx; Val
0x18008d689  lea     rcx, [rbp+7E0h+me]; void *
0x18008d690  call    memset_0
0x18008d695  xor     ecx, ecx
0x18008d697  test    rbx, rbx
0x18008d69a  setnz   cl
0x18008d69d  xor     eax, eax
0x18008d69f  test    rdi, rdi
0x18008d6a2  setnz   al
0x18008d6a5  cmp     ecx, eax
0x18008d6a7  jnz     short loc_18008D6AE
0x18008d6a9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18008d6ae  test    rdi, rdi
0x18008d6b1  jz      short loc_18008D6C1
0x18008d6b3  mov     rcx, rdi; Process
0x18008d6b6  call    cs:__imp_GetProcessId
0x18008d6bc  jmp     loc_18008D743
0x18008d6c1  test    rbx, rbx
0x18008d6c4  jz      short loc_18008D73F
0x18008d6c6  mov     r9d, 8
0x18008d6cc  lea     r8, [rsp+8E0h+Process]
0x18008d6d1  lea     edx, [r9-7]
0x18008d6d5  mov     rcx, rbx
0x18008d6d8  call    cs:__imp_PssQuerySnapshot
0x18008d6de  mov     ebx, eax
0x18008d6e0  test    eax, eax
0x18008d6e2  jz      short loc_18008D72D
0x18008d6e4  jle     short loc_18008D6EF
0x18008d6e6  movzx   ebx, ax
0x18008d6e9  or      ebx, 80070000h
0x18008d6ef  lea     rax, WPP_GLOBAL_Control
0x18008d6f6  mov     rcx, cs:WPP_GLOBAL_Control
0x18008d6fd  cmp     rcx, rax
0x18008d700  jz      loc_18008D8DC
0x18008d706  test    byte ptr [rcx+1Ch], 1
0x18008d70a  jz      loc_18008D8DC
0x18008d710  mov     edx, 85h
0x18008d715  mov     r9d, ebx
0x18008d718  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x18008d71f  mov     rcx, [rcx+10h]
0x18008d723  call    WPP_SF_d
0x18008d728  jmp     loc_18008D8DC
0x18008d72d  mov     rcx, [rsp+8E0h+Process]; Process
0x18008d732  call    cs:__imp_GetProcessId
0x18008d738  mov     rdi, [rsp+8E0h+Process]
0x18008d73d  jmp     short loc_18008D743
0x18008d73f  xor     edi, edi
0x18008d741  xor     eax, eax
0x18008d743  mov     edx, eax; th32ProcessID
0x18008d745  mov     ecx, 8; dwFlags
0x18008d74a  call    cs:__imp_CreateToolhelp32Snapshot
0x18008d750  mov     rdx, rax
0x18008d753  lea     rcx, [rsp+8E0h+hSnapshot]
0x18008d758  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18008d75d  mov     rbx, [rsp+8E0h+hSnapshot]
0x18008d762  lea     rax, [rbx+1]
0x18008d766  cmp     rax, 1
0x18008d76a  ja      short loc_18008D7BE
0x18008d76c  lea     rax, WPP_GLOBAL_Control
0x18008d773  mov     rcx, cs:WPP_GLOBAL_Control
0x18008d77a  cmp     rcx, rax
0x18008d77d  jz      short loc_18008D7AA
0x18008d77f  test    byte ptr [rcx+1Ch], 1
0x18008d783  jz      short loc_18008D7AA
0x18008d785  call    cs:__imp_GetLastError
0x18008d78b  mov     edx, 86h
0x18008d790  mov     r9d, eax
0x18008d793  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x18008d79a  mov     rcx, cs:WPP_GLOBAL_Control
0x18008d7a1  mov     rcx, [rcx+10h]
0x18008d7a5  call    WPP_SF_d
0x18008d7aa  call    cs:__imp_GetLastError
0x18008d7b0  mov     ecx, eax; unsigned int
0x18008d7b2  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18008d7b7  mov     ebx, eax
0x18008d7b9  jmp     loc_18008D8DC
0x18008d7be  mov     [rbp+7E0h+me.dwSize], r15d
0x18008d7c5  lea     rdx, [rbp+7E0h+me]; lpme
0x18008d7cc  mov     rcx, rbx; hSnapshot
0x18008d7cf  call    cs:__imp_Module32FirstW
0x18008d7d5  test    eax, eax
0x18008d7d7  jnz     short loc_18008D819
0x18008d7d9  mov     ebx, 80004005h
0x18008d7de  lea     rax, WPP_GLOBAL_Control
0x18008d7e5  mov     rcx, cs:WPP_GLOBAL_Control
0x18008d7ec  cmp     rcx, rax
0x18008d7ef  jz      loc_18008D8DC
0x18008d7f5  test    byte ptr [rcx+1Ch], 1
0x18008d7f9  jz      loc_18008D8DC
0x18008d7ff  call    cs:__imp_GetLastError
0x18008d805  mov     edx, 87h
0x18008d80a  mov     r9d, eax
0x18008d80d  mov     rcx, cs:WPP_GLOBAL_Control
0x18008d814  jmp     loc_18008D718
0x18008d819  mov     r9, rsi; struct CXMLWriter *
0x18008d81c  mov     r8, [rbp+7E0h+me.hModule]; HINSTANCE
0x18008d823  mov     rdx, rdi; void *
0x18008d826  call    ?AddModuleInformation@CDataCollection@@AEAAJPEAXPEAUHINSTANCE__@@PEAVCXMLWriter@@@Z; CDataCollection::AddModuleInformation(void *,HINSTANCE__ *,CXMLWriter *)
0x18008d82b  mov     r8, r15; Size
0x18008d82e  xor     edx, edx; Val
0x18008d830  lea     rcx, [rsp+8E0h+var_8B0]; void *
0x18008d835  call    memset_0
0x18008d83a  lea     rcx, [rbp+7E0h+me]
0x18008d841  lea     rax, [rsp+8E0h+var_8B0]
0x18008d846  mov     edx, 8
0x18008d84b  movups  xmm0, xmmword ptr [rax]
0x18008d84e  movups  xmmword ptr [rcx], xmm0
0x18008d851  movups  xmm1, xmmword ptr [rax+10h]
0x18008d855  movups  xmmword ptr [rcx+10h], xmm1
0x18008d859  movups  xmm0, xmmword ptr [rax+20h]
0x18008d85d  movups  xmmword ptr [rcx+20h], xmm0
0x18008d861  movups  xmm1, xmmword ptr [rax+30h]
0x18008d865  movups  xmmword ptr [rcx+30h], xmm1
0x18008d869  movups  xmm0, xmmword ptr [rax+40h]
0x18008d86d  movups  xmmword ptr [rcx+40h], xmm0
0x18008d871  movups  xmm1, xmmword ptr [rax+50h]
0x18008d875  movups  xmmword ptr [rcx+50h], xmm1
0x18008d879  movups  xmm0, xmmword ptr [rax+60h]
0x18008d87d  movups  xmmword ptr [rcx+60h], xmm0
0x18008d881  movups  xmm1, xmmword ptr [rax+70h]
0x18008d885  movups  xmmword ptr [rcx+70h], xmm1
0x18008d889  lea     rcx, [rcx+80h]
0x18008d890  lea     rax, [rax+80h]
0x18008d897  sub     rdx, 1
0x18008d89b  jnz     short loc_18008D84B
0x18008d89d  movups  xmm0, xmmword ptr [rax]
0x18008d8a0  movups  xmmword ptr [rcx], xmm0
0x18008d8a3  movups  xmm1, xmmword ptr [rax+10h]
0x18008d8a7  movups  xmmword ptr [rcx+10h], xmm1
0x18008d8ab  movups  xmm0, xmmword ptr [rax+20h]
0x18008d8af  movups  xmmword ptr [rcx+20h], xmm0
0x18008d8b3  mov     rax, [rax+30h]
0x18008d8b7  mov     [rcx+30h], rax
0x18008d8bb  mov     [rbp+7E0h+me.dwSize], r15d
0x18008d8c2  lea     rdx, [rbp+7E0h+me]; lpme
0x18008d8c9  mov     rcx, rbx; hSnapshot
0x18008d8cc  call    cs:__imp_Module32NextW
0x18008d8d2  test    eax, eax
0x18008d8d4  jnz     loc_18008D819
0x18008d8da  xor     ebx, ebx
0x18008d8dc  lea     rcx, [rsp+8E0h+hSnapshot]
0x18008d8e1  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18008d8e6  mov     eax, ebx
0x18008d8e8  mov     rcx, [rbp+7E0h+var_30]
0x18008d8ef  xor     rcx, rsp; StackCookie
0x18008d8f2  call    __security_check_cookie
0x18008d8f7  add     rsp, 8C0h
0x18008d8fe  pop     r15
0x18008d900  pop     rdi
0x18008d901  pop     rsi
0x18008d902  pop     rbx
0x18008d903  pop     rbp
0x18008d904  retn
```
