# CDataCollection::IterateAndAddLoadedModuleInformation(void *,HPSS__ *,CXMLWriter *)

- ea: `0x18008d68c`
- end: `0x18008d955`
- name: `?IterateAndAddLoadedModuleInformation@CDataCollection@@AEAAJPEAXPEAUHPSS__@@PEAVCXMLWriter@@@Z`
- size: `713`
- prototype: `int(CDataCollection *__hidden this, void *, struct HPSS__ *, struct CXMLWriter *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18008bf00`

## callees

- `0x18000716c`
- `0x180007e10`
- `0x180007e34`
- `0x18001fe24`
- `0x18003bf14`
- `0x180050db0`
- `0x1800517cc`
- `0x18008c144`
- `0x18008d68c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18008d706`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18008d782`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18008d706`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18008d782`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d7d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d7fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d84f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d7d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d7fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d84f`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x18008d728`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x18008d728`
- `api-ms-win-core-toolhelp-l1-1-0!Module32NextW` at `0x18008d91c`
- `api-ms-win-core-toolhelp-l1-1-0!Module32NextW` at `0x18008d91c`
- `api-ms-win-core-toolhelp-l1-1-0!Module32FirstW` at `0x18008d81f`
- `api-ms-win-core-toolhelp-l1-1-0!Module32FirstW` at `0x18008d81f`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x18008d79a`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x18008d79a`

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
0x18008d68c  push    rbp
0x18008d68e  push    rbx
0x18008d68f  push    rsi
0x18008d690  push    rdi
0x18008d691  push    r15
0x18008d693  lea     rbp, [rsp-7C0h]
0x18008d69b  sub     rsp, 8C0h
0x18008d6a2  mov     rax, cs:__security_cookie
0x18008d6a9  xor     rax, rsp
0x18008d6ac  mov     [rbp+7E0h+var_30], rax
0x18008d6b3  mov     rsi, r9
0x18008d6b6  mov     rbx, r8
0x18008d6b9  mov     rdi, rdx
0x18008d6bc  mov     [rsp+8E0h+hSnapshot], 0
0x18008d6c5  mov     [rsp+8E0h+Process], 0
0x18008d6ce  mov     r15d, 438h
0x18008d6d4  mov     r8d, r15d; Size
0x18008d6d7  xor     edx, edx; Val
0x18008d6d9  lea     rcx, [rbp+7E0h+me]; void *
0x18008d6e0  call    memset_0
0x18008d6e5  xor     ecx, ecx
0x18008d6e7  test    rbx, rbx
0x18008d6ea  setnz   cl
0x18008d6ed  xor     eax, eax
0x18008d6ef  test    rdi, rdi
0x18008d6f2  setnz   al
0x18008d6f5  cmp     ecx, eax
0x18008d6f7  jnz     short loc_18008D6FE
0x18008d6f9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18008d6fe  test    rdi, rdi
0x18008d701  jz      short loc_18008D711
0x18008d703  mov     rcx, rdi; Process
0x18008d706  call    cs:__imp_GetProcessId
0x18008d70c  jmp     loc_18008D793
0x18008d711  test    rbx, rbx
0x18008d714  jz      short loc_18008D78F
0x18008d716  mov     r9d, 8
0x18008d71c  lea     r8, [rsp+8E0h+Process]
0x18008d721  lea     edx, [r9-7]
0x18008d725  mov     rcx, rbx
0x18008d728  call    cs:__imp_PssQuerySnapshot
0x18008d72e  mov     ebx, eax
0x18008d730  test    eax, eax
0x18008d732  jz      short loc_18008D77D
0x18008d734  jle     short loc_18008D73F
0x18008d736  movzx   ebx, ax
0x18008d739  or      ebx, 80070000h
0x18008d73f  lea     rax, WPP_GLOBAL_Control
0x18008d746  mov     rcx, cs:WPP_GLOBAL_Control
0x18008d74d  cmp     rcx, rax
0x18008d750  jz      loc_18008D92C
0x18008d756  test    byte ptr [rcx+1Ch], 1
0x18008d75a  jz      loc_18008D92C
0x18008d760  mov     edx, 85h
0x18008d765  mov     r9d, ebx
0x18008d768  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x18008d76f  mov     rcx, [rcx+10h]
0x18008d773  call    WPP_SF_d
0x18008d778  jmp     loc_18008D92C
0x18008d77d  mov     rcx, [rsp+8E0h+Process]; Process
0x18008d782  call    cs:__imp_GetProcessId
0x18008d788  mov     rdi, [rsp+8E0h+Process]
0x18008d78d  jmp     short loc_18008D793
0x18008d78f  xor     edi, edi
0x18008d791  xor     eax, eax
0x18008d793  mov     edx, eax; th32ProcessID
0x18008d795  mov     ecx, 8; dwFlags
0x18008d79a  call    cs:__imp_CreateToolhelp32Snapshot
0x18008d7a0  mov     rdx, rax
0x18008d7a3  lea     rcx, [rsp+8E0h+hSnapshot]
0x18008d7a8  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18008d7ad  mov     rbx, [rsp+8E0h+hSnapshot]
0x18008d7b2  lea     rax, [rbx+1]
0x18008d7b6  cmp     rax, 1
0x18008d7ba  ja      short loc_18008D80E
0x18008d7bc  lea     rax, WPP_GLOBAL_Control
0x18008d7c3  mov     rcx, cs:WPP_GLOBAL_Control
0x18008d7ca  cmp     rcx, rax
0x18008d7cd  jz      short loc_18008D7FA
0x18008d7cf  test    byte ptr [rcx+1Ch], 1
0x18008d7d3  jz      short loc_18008D7FA
0x18008d7d5  call    cs:__imp_GetLastError
0x18008d7db  mov     edx, 86h
0x18008d7e0  mov     r9d, eax
0x18008d7e3  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x18008d7ea  mov     rcx, cs:WPP_GLOBAL_Control
0x18008d7f1  mov     rcx, [rcx+10h]
0x18008d7f5  call    WPP_SF_d
0x18008d7fa  call    cs:__imp_GetLastError
0x18008d800  mov     ecx, eax; unsigned int
0x18008d802  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18008d807  mov     ebx, eax
0x18008d809  jmp     loc_18008D92C
0x18008d80e  mov     [rbp+7E0h+me.dwSize], r15d
0x18008d815  lea     rdx, [rbp+7E0h+me]; lpme
0x18008d81c  mov     rcx, rbx; hSnapshot
0x18008d81f  call    cs:__imp_Module32FirstW
0x18008d825  test    eax, eax
0x18008d827  jnz     short loc_18008D869
0x18008d829  mov     ebx, 80004005h
0x18008d82e  lea     rax, WPP_GLOBAL_Control
0x18008d835  mov     rcx, cs:WPP_GLOBAL_Control
0x18008d83c  cmp     rcx, rax
0x18008d83f  jz      loc_18008D92C
0x18008d845  test    byte ptr [rcx+1Ch], 1
0x18008d849  jz      loc_18008D92C
0x18008d84f  call    cs:__imp_GetLastError
0x18008d855  mov     edx, 87h
0x18008d85a  mov     r9d, eax
0x18008d85d  mov     rcx, cs:WPP_GLOBAL_Control
0x18008d864  jmp     loc_18008D768
0x18008d869  mov     r9, rsi; struct CXMLWriter *
0x18008d86c  mov     r8, [rbp+7E0h+me.hModule]; HINSTANCE
0x18008d873  mov     rdx, rdi; void *
0x18008d876  call    ?AddModuleInformation@CDataCollection@@AEAAJPEAXPEAUHINSTANCE__@@PEAVCXMLWriter@@@Z; CDataCollection::AddModuleInformation(void *,HINSTANCE__ *,CXMLWriter *)
0x18008d87b  mov     r8, r15; Size
0x18008d87e  xor     edx, edx; Val
0x18008d880  lea     rcx, [rsp+8E0h+var_8B0]; void *
0x18008d885  call    memset_0
0x18008d88a  lea     rcx, [rbp+7E0h+me]
0x18008d891  lea     rax, [rsp+8E0h+var_8B0]
0x18008d896  mov     edx, 8
0x18008d89b  movups  xmm0, xmmword ptr [rax]
0x18008d89e  movups  xmmword ptr [rcx], xmm0
0x18008d8a1  movups  xmm1, xmmword ptr [rax+10h]
0x18008d8a5  movups  xmmword ptr [rcx+10h], xmm1
0x18008d8a9  movups  xmm0, xmmword ptr [rax+20h]
0x18008d8ad  movups  xmmword ptr [rcx+20h], xmm0
0x18008d8b1  movups  xmm1, xmmword ptr [rax+30h]
0x18008d8b5  movups  xmmword ptr [rcx+30h], xmm1
0x18008d8b9  movups  xmm0, xmmword ptr [rax+40h]
0x18008d8bd  movups  xmmword ptr [rcx+40h], xmm0
0x18008d8c1  movups  xmm1, xmmword ptr [rax+50h]
0x18008d8c5  movups  xmmword ptr [rcx+50h], xmm1
0x18008d8c9  movups  xmm0, xmmword ptr [rax+60h]
0x18008d8cd  movups  xmmword ptr [rcx+60h], xmm0
0x18008d8d1  movups  xmm1, xmmword ptr [rax+70h]
0x18008d8d5  movups  xmmword ptr [rcx+70h], xmm1
0x18008d8d9  lea     rcx, [rcx+80h]
0x18008d8e0  lea     rax, [rax+80h]
0x18008d8e7  sub     rdx, 1
0x18008d8eb  jnz     short loc_18008D89B
0x18008d8ed  movups  xmm0, xmmword ptr [rax]
0x18008d8f0  movups  xmmword ptr [rcx], xmm0
0x18008d8f3  movups  xmm1, xmmword ptr [rax+10h]
0x18008d8f7  movups  xmmword ptr [rcx+10h], xmm1
0x18008d8fb  movups  xmm0, xmmword ptr [rax+20h]
0x18008d8ff  movups  xmmword ptr [rcx+20h], xmm0
0x18008d903  mov     rax, [rax+30h]
0x18008d907  mov     [rcx+30h], rax
0x18008d90b  mov     [rbp+7E0h+me.dwSize], r15d
0x18008d912  lea     rdx, [rbp+7E0h+me]; lpme
0x18008d919  mov     rcx, rbx; hSnapshot
0x18008d91c  call    cs:__imp_Module32NextW
0x18008d922  test    eax, eax
0x18008d924  jnz     loc_18008D869
0x18008d92a  xor     ebx, ebx
0x18008d92c  lea     rcx, [rsp+8E0h+hSnapshot]
0x18008d931  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18008d936  mov     eax, ebx
0x18008d938  mov     rcx, [rbp+7E0h+var_30]
0x18008d93f  xor     rcx, rsp; StackCookie
0x18008d942  call    __security_check_cookie
0x18008d947  add     rsp, 8C0h
0x18008d94e  pop     r15
0x18008d950  pop     rdi
0x18008d951  pop     rsi
0x18008d952  pop     rbx
0x18008d953  pop     rbp
0x18008d954  retn
```
