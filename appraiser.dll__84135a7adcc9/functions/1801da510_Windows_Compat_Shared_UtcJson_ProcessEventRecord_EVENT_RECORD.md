# Windows::Compat::Shared::UtcJson::ProcessEventRecord(_EVENT_RECORD *)

- ea: `0x1801da510`
- end: `0x1801daa93`
- name: `?ProcessEventRecord@UtcJson@Shared@Compat@Windows@@CAXPEAU_EVENT_RECORD@@@Z`
- size: `1411`
- prototype: `void __fastcall(PEVENT_RECORD Event)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180008570`
- `0x1800092dc`
- `0x1800fca34`
- `0x1801d95c0`
- `0x1801da510`
- `0x1801db028`
- `0x1801db0a0`
- `0x1802174cc`
- `0x18021f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1801da797`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1801da7c7`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1801da7dc`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1801da876`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1801da88b`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1801da797`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1801da7c7`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1801da7dc`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1801da876`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1801da88b`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x1801da6f9`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x1801da740`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x1801da752`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x1801da84a`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x1801da85c`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x1801da6f9`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x1801da740`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x1801da752`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x1801da84a`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x1801da85c`
- `KERNEL32!ResetEvent` at `0x1801da830`
- `KERNEL32!ResetEvent` at `0x1801da830`
- `KERNEL32!SetEvent` at `0x1801da826`
- `KERNEL32!SetEvent` at `0x1801da8d5`
- `KERNEL32!SetEvent` at `0x1801da826`
- `KERNEL32!SetEvent` at `0x1801da8d5`
- `KERNEL32!GetProcessHeap` at `0x1801da613`
- `KERNEL32!GetProcessHeap` at `0x1801daa60`
- `KERNEL32!GetProcessHeap` at `0x1801da613`
- `KERNEL32!GetProcessHeap` at `0x1801daa60`
- `KERNEL32!HeapAlloc` at `0x1801da621`
- `KERNEL32!HeapAlloc` at `0x1801da621`
- `KERNEL32!WaitForSingleObject` at `0x1801da8ea`
- `KERNEL32!WaitForSingleObject` at `0x1801da8ea`
- `KERNEL32!HeapFree` at `0x1801daa6e`
- `KERNEL32!HeapFree` at `0x1801daa6e`
- `tdh!TdhGetEventInformation` at `0x1801da602`
- `tdh!TdhGetEventInformation` at `0x1801da63f`
- `tdh!TdhGetEventInformation` at `0x1801da602`
- `tdh!TdhGetEventInformation` at `0x1801da63f`

## string_xrefs

- `0x1801da816`: `onecore\base\appcompat\shared\unmanaged\utclogger\lib\utcjson.cpp`
- `0x1801da8c5`: `onecore\base\appcompat\shared\unmanaged\utclogger\lib\utcjson.cpp`
- `0x1801da9af`: `onecore\base\appcompat\shared\unmanaged\utclogger\lib\utcjson.cpp`
- `0x1801daa4f`: `onecore\base\appcompat\shared\unmanaged\utclogger\lib\utcjson.cpp`
- `0x1801da7bd`: `StartUtcJsonTrace`
- `0x1801da736`: `StartUtcJsonTrace`
- `0x1801da804`: `Windows::Compat::Shared::UtcJson::ProcessEventRecord`
- `0x1801da8b3`: `Windows::Compat::Shared::UtcJson::ProcessEventRecord`
- `0x1801da9ba`: `Windows::Compat::Shared::UtcJson::ProcessEventRecord`
- `0x1801daa43`: `Windows::Compat::Shared::UtcJson::ProcessEventRecord`
- `0x1801da999`: `Error writing JSON %hs: [0x%x].`
- `0x1801da840`: `StopUtcJsonTrace`
- `0x1801da7f3`: `Starting UTC json trace.`
- `0x1801da8a2`: `Stopping UTC json trace.`
- `0x1801da86c`: `StopUtcJsonTrace`
- `0x1801da9ef`: `Error writing JSON %ls: [0x%x].`

## pseudocode

```c
void __fastcall Windows::Compat::Shared::UtcJson::ProcessEventRecord(PEVENT_RECORD Event)
{
  PVOID UserContext; // rdi
  TRACE_EVENT_INFO *v3; // r15
  const wchar_t *UserData; // rsi
  const char *v5; // rbx
  signed int EventInformation; // ecx
  ULONG v7; // ebx
  HANDLE ProcessHeap; // rax
  unsigned int v9; // eax
  unsigned __int64 v10; // rax
  unsigned __int64 i; // r14
  const char **v12; // rdx
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // rcx
  unsigned __int64 v15; // rax
  unsigned __int64 j; // r14
  const wchar_t **v17; // rdx
  unsigned __int64 v18; // rax
  unsigned __int64 v19; // rcx
  void *v20; // rcx
  const char *v21; // rdx
  int v22; // ecx
  struct IStream *v23; // rcx
  int v24; // eax
  int v25; // eax
  int v26; // eax
  HANDLE v27; // rax
  ULONG BufferSize; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v29; // [rsp+58h] [rbp-A8h]
  __int64 v30; // [rsp+68h] [rbp-98h]
  unsigned __int64 v31; // [rsp+70h] [rbp-90h]
  char SubStr[256]; // [rsp+80h] [rbp-80h] BYREF

  memset_0(SubStr, 0, sizeof(SubStr));
  UserContext = Event->UserContext;
  v3 = 0;
  BufferSize = 0;
  *(_QWORD *)&v29 = 0x4B5997E856DC463BLL;
  ++*((_DWORD *)UserContext + 40);
  *((_QWORD *)&v29 + 1) = 0x163B99B7CAB36E8LL;
  v30 = 0x4B5197CD43AC453BLL;
  v31 = 0xAC63B99B7CDB7643uLL;
  if ( v29 == *(_OWORD *)&Event->EventHeader.ProviderId && Event->EventHeader.EventDescriptor.Id == 755 )
  {
    UserData = (const wchar_t *)Event->UserData;
    v5 = 0;
    goto LABEL_16;
  }
  if ( v30 == *(_QWORD *)&Event->EventHeader.ProviderId.Data1 && v31 == *(_QWORD *)Event->EventHeader.ProviderId.Data4 )
  {
    EventInformation = TdhGetEventInformation(Event, 0, 0, 0, &BufferSize);
    if ( EventInformation == 122 )
    {
      v7 = BufferSize;
      ProcessHeap = GetProcessHeap();
      v3 = (TRACE_EVENT_INFO *)HeapAlloc(ProcessHeap, 0, v7);
      EventInformation = TdhGetEventInformation(Event, 0, 0, v3, &BufferSize);
    }
    if ( EventInformation )
    {
      if ( EventInformation > 0 )
        v9 = (unsigned __int16)EventInformation | 0x80070000;
      else
        v9 = EventInformation;
      if ( UtcHelperWriteLogCallback )
        UtcHelperWriteLogCallback(
          1,
          750,
          "onecore\\base\\appcompat\\shared\\unmanaged\\utclogger\\lib\\utcjson.cpp",
          "Windows::Compat::Shared::UtcJson::ProcessEventRecord",
          v9,
          "Failed to get tracelogging event info: [%d].",
          EventInformation);
      goto LABEL_73;
    }
    if ( wcscmp_0((const wchar_t *)((char *)v3 + v3->TaskNameOffset), L"AsimovUploader_PersistEvent") )
      goto LABEL_73;
    v5 = (const char *)Event->UserData;
    UserData = 0;
    if ( v5 )
    {
      v10 = *((_QWORD *)UserContext + 6);
      for ( i = 0; i < v10; ++i )
      {
        v12 = 0;
        if ( i < v10 )
        {
          v13 = *((_QWORD *)UserContext + 5) * i;
          if ( !is_mul_ok(*((_QWORD *)UserContext + 5), i)
            || (v14 = *((_QWORD *)UserContext + 9), v12 = (const char **)(v14 + v13), v14 + v13 < v14) )
          {
            v12 = 0;
          }
        }
        if ( strstr(v5, *v12) )
          break;
        v10 = *((_QWORD *)UserContext + 6);
      }
      if ( *((_QWORD *)UserContext + 6) == i )
        goto LABEL_73;
      StringCchPrintfA(SubStr, 0x100u, "%S", &Windows::Compat::Shared::UtcJson::s_key);
      if ( strstr(v5, "StartUtcJsonTrace") && strstr(v5, SubStr) )
        goto LABEL_40;
      goto LABEL_37;
    }
LABEL_16:
    if ( !UserData )
      goto LABEL_73;
    v15 = *((_QWORD *)UserContext + 12);
    for ( j = 0; j < v15; ++j )
    {
      v17 = 0;
      if ( j < v15 )
      {
        v18 = *((_QWORD *)UserContext + 11) * j;
        if ( !is_mul_ok(*((_QWORD *)UserContext + 11), j)
          || (v19 = *((_QWORD *)UserContext + 15), v17 = (const wchar_t **)(v19 + v18), v19 + v18 < v19) )
        {
          v17 = 0;
        }
      }
      if ( wcsstr(UserData, *v17) )
        break;
      v15 = *((_QWORD *)UserContext + 12);
    }
    if ( *((_QWORD *)UserContext + 12) == j )
      goto LABEL_73;
LABEL_37:
    if ( UserData
      && wcsstr(UserData, L"StartUtcJsonTrace")
      && wcsstr(UserData, &Windows::Compat::Shared::UtcJson::s_key) )
    {
LABEL_40:
      if ( UtcHelperWriteLogCallback )
        UtcHelperWriteLogCallback(
          0,
          817,
          "onecore\\base\\appcompat\\shared\\unmanaged\\utclogger\\lib\\utcjson.cpp",
          "Windows::Compat::Shared::UtcJson::ProcessEventRecord",
          0,
          "Starting UTC json trace.");
      SetEvent(*((HANDLE *)UserContext + 1));
      v20 = (void *)*((_QWORD *)UserContext + 2);
LABEL_43:
      ResetEvent(v20);
      goto LABEL_73;
    }
    if ( v5 && strstr(v5, "StopUtcJsonTrace") && strstr(v5, SubStr)
      || UserData && wcsstr(UserData, L"StopUtcJsonTrace") && wcsstr(UserData, &Windows::Compat::Shared::UtcJson::s_key) )
    {
      if ( UtcHelperWriteLogCallback )
        UtcHelperWriteLogCallback(
          0,
          827,
          "onecore\\base\\appcompat\\shared\\unmanaged\\utclogger\\lib\\utcjson.cpp",
          "Windows::Compat::Shared::UtcJson::ProcessEventRecord",
          0,
          "Stopping UTC json trace.");
      SetEvent(*((HANDLE *)UserContext + 2));
      v20 = (void *)*((_QWORD *)UserContext + 1);
      goto LABEL_43;
    }
    if ( !WaitForSingleObject(*((HANDLE *)UserContext + 1), 0)
      && (!(_QWORD)xmmword_1802D3F08 || !Windows::Compat::Shared::UtcJson::CheckAllowedProcesses(v5, UserData)) )
    {
      if ( !*((_BYTE *)UserContext + 25) )
        goto LABEL_62;
      v21 = "\r\n        ";
      if ( !*((_BYTE *)UserContext + 24) )
        v21 = ",\r\n        ";
      v22 = Windows::Compat::Shared::UtcJson::WriteStringToFile(*(struct IStream **)UserContext, v21);
      if ( v22 >= 0 )
      {
LABEL_62:
        v23 = *(struct IStream **)UserContext;
        *((_BYTE *)UserContext + 24) = 0;
        if ( v5 )
        {
          v24 = Windows::Compat::Shared::UtcJson::WriteStringToFile(v23, v5);
          if ( v24 < 0 )
          {
            if ( UtcHelperWriteLogCallback )
              UtcHelperWriteLogCallback(
                1,
                865,
                "onecore\\base\\appcompat\\shared\\unmanaged\\utclogger\\lib\\utcjson.cpp",
                "Windows::Compat::Shared::UtcJson::ProcessEventRecord",
                v24,
                "Error writing JSON %hs: [0x%x].",
                v5,
                v24);
            goto LABEL_73;
          }
        }
        else
        {
          v25 = Windows::Compat::Shared::UtcJson::WriteStringToFile(v23, UserData);
          if ( v25 < 0 )
          {
            if ( UtcHelperWriteLogCallback )
              UtcHelperWriteLogCallback(
                1,
                870,
                "onecore\\base\\appcompat\\shared\\unmanaged\\utclogger\\lib\\utcjson.cpp",
                "Windows::Compat::Shared::UtcJson::ProcessEventRecord",
                v25,
                "Error writing JSON %ls: [0x%x].",
                UserData,
                v25);
            goto LABEL_73;
          }
        }
        if ( !*((_BYTE *)UserContext + 25) )
        {
          v26 = Windows::Compat::Shared::UtcJson::WriteStringToFile(*(struct IStream **)UserContext, "\r\n");
          if ( v26 < 0 )
          {
            if ( UtcHelperWriteLogCallback )
              UtcHelperWriteLogCallback(
                1,
                876,
                "onecore\\base\\appcompat\\shared\\unmanaged\\utclogger\\lib\\utcjson.cpp",
                "Windows::Compat::Shared::UtcJson::ProcessEventRecord",
                v26,
                "Error writing formatting: [0x%x].",
                v26);
          }
        }
        goto LABEL_73;
      }
      if ( UtcHelperWriteLogCallback )
        UtcHelperWriteLogCallback(
          1,
          857,
          "onecore\\base\\appcompat\\shared\\unmanaged\\utclogger\\lib\\utcjson.cpp",
          "Windows::Compat::Shared::UtcJson::ProcessEventRecord",
          v22,
          "Error writing formatting: [0x%x].",
          v22);
    }
LABEL_73:
    if ( v3 )
    {
      v27 = GetProcessHeap();
      HeapFree(v27, 0, v3);
    }
  }
}

```

## disassembly

```asm
0x1801da510  push    rbp
0x1801da512  push    rbx
0x1801da513  push    rsi
0x1801da514  push    rdi
0x1801da515  push    r14
0x1801da517  push    r15
0x1801da519  lea     rbp, [rsp-98h]
0x1801da521  sub     rsp, 198h
0x1801da528  mov     rax, cs:__security_cookie
0x1801da52f  xor     rax, rsp
0x1801da532  mov     [rbp+0C0h+var_40], rax
0x1801da539  mov     r14, rcx
0x1801da53c  xor     edx, edx; Val
0x1801da53e  lea     rcx, [rbp+0C0h+SubStr]; void *
0x1801da542  mov     r8d, 100h; Size
0x1801da548  call    memset_0
0x1801da54d  mov     rdi, [r14+68h]
0x1801da551  xor     r15d, r15d
0x1801da554  mov     [rsp+1C0h+var_170], 0
0x1801da55c  mov     dword ptr [rsp+1C0h+var_168], 56DC463Bh
0x1801da564  mov     dword ptr [rsp+1C0h+var_168+4], 4B5997E8h
0x1801da56c  inc     dword ptr [rdi+0A0h]
0x1801da572  mov     rax, qword ptr [rsp+1C0h+var_168]
0x1801da577  mov     dword ptr [rsp+1C0h+var_168+8], 7CAB36E8h
0x1801da57f  mov     dword ptr [rsp+1C0h+var_168+0Ch], 163B99Bh
0x1801da587  mov     dword ptr [rsp+1C0h+var_158], 43AC453Bh
0x1801da58f  mov     dword ptr [rsp+1C0h+var_158+4], 4B5197CDh
0x1801da597  mov     dword ptr [rsp+1C0h+var_150], 7CDB7643h
0x1801da59f  mov     dword ptr [rsp+1C0h+var_150+4], 0AC63B99Bh
0x1801da5a7  cmp     rax, [r14+18h]
0x1801da5ab  jnz     short loc_1801DA5CF
0x1801da5ad  mov     rax, qword ptr [rsp+1C0h+var_168+8]
0x1801da5b2  cmp     rax, [r14+20h]
0x1801da5b6  jnz     short loc_1801DA5CF
0x1801da5b8  mov     eax, 2F3h
0x1801da5bd  cmp     ax, [r14+28h]
0x1801da5c2  jnz     short loc_1801DA5CF
0x1801da5c4  mov     rsi, [r14+60h]
0x1801da5c8  xor     ebx, ebx
0x1801da5ca  jmp     loc_1801DA6B3
0x1801da5cf  mov     rax, [rsp+1C0h+var_158]
0x1801da5d4  cmp     rax, [r14+18h]
0x1801da5d8  jnz     loc_1801DAA74
0x1801da5de  mov     rax, [rsp+1C0h+var_150]
0x1801da5e3  cmp     rax, [r14+20h]
0x1801da5e7  jnz     loc_1801DAA74
0x1801da5ed  lea     rax, [rsp+1C0h+var_170]
0x1801da5f2  xor     r9d, r9d; Buffer
0x1801da5f5  xor     r8d, r8d; TdhContext
0x1801da5f8  mov     [rsp+1C0h+BufferSize], rax; BufferSize
0x1801da5fd  xor     edx, edx; TdhContextCount
0x1801da5ff  mov     rcx, r14; Event
0x1801da602  call    cs:__imp_TdhGetEventInformation
0x1801da608  mov     ecx, eax
0x1801da60a  cmp     eax, 7Ah ; 'z'
0x1801da60d  jnz     short loc_1801DA647
0x1801da60f  mov     ebx, [rsp+1C0h+var_170]
0x1801da613  call    cs:__imp_GetProcessHeap
0x1801da619  mov     r8d, ebx; dwBytes
0x1801da61c  xor     edx, edx; dwFlags
0x1801da61e  mov     rcx, rax; hHeap
0x1801da621  call    cs:__imp_HeapAlloc
0x1801da627  xor     r8d, r8d; TdhContext
0x1801da62a  xor     edx, edx; TdhContextCount
0x1801da62c  mov     r15, rax
0x1801da62f  mov     rcx, r14; Event
0x1801da632  lea     rax, [rsp+1C0h+var_170]
0x1801da637  mov     r9, r15; Buffer
0x1801da63a  mov     [rsp+1C0h+BufferSize], rax; BufferSize
0x1801da63f  call    cs:__imp_TdhGetEventInformation
0x1801da645  mov     ecx, eax
0x1801da647  test    ecx, ecx
0x1801da649  jz      short loc_1801DA68D
0x1801da64b  jg      short loc_1801DA651
0x1801da64d  mov     eax, ecx
0x1801da64f  jmp     short loc_1801DA659
0x1801da651  movzx   eax, cx
0x1801da654  or      eax, 80070000h
0x1801da659  mov     r10, cs:UtcHelperWriteLogCallback
0x1801da660  test    eax, eax
0x1801da662  mov     edx, 80004005h
0x1801da667  cmovns  eax, edx
0x1801da66a  test    r10, r10
0x1801da66d  jz      loc_1801DAA5B
0x1801da673  lea     rdx, aFailedToGetTra; "Failed to get tracelogging event info: "...
0x1801da67a  mov     dword ptr [rsp+1C0h+var_190], ecx
0x1801da67e  mov     [rsp+1C0h+var_198], rdx
0x1801da683  mov     edx, 2EEh
0x1801da688  jmp     loc_1801DAA3C
0x1801da68d  mov     ecx, [r15+44h]
0x1801da691  lea     rdx, aAsimovuploader; "AsimovUploader_PersistEvent"
0x1801da698  add     rcx, r15; String1
0x1801da69b  call    wcscmp_0
0x1801da6a0  test    eax, eax
0x1801da6a2  jnz     loc_1801DAA5B
0x1801da6a8  mov     rbx, [r14+60h]
0x1801da6ac  xor     esi, esi
0x1801da6ae  test    rbx, rbx
0x1801da6b1  jnz     short loc_1801DA6C5
0x1801da6b3  test    rsi, rsi
0x1801da6b6  jz      loc_1801DAA5B
0x1801da6bc  test    rbx, rbx
0x1801da6bf  jz      loc_1801DA763
0x1801da6c5  mov     rax, [rdi+30h]
0x1801da6c9  xor     r14d, r14d
0x1801da6cc  test    rax, rax
0x1801da6cf  jz      short loc_1801DA710
0x1801da6d1  xor     edx, edx
0x1801da6d3  cmp     r14, rax
0x1801da6d6  jnb     short loc_1801DA6F3
0x1801da6d8  mov     rax, r14
0x1801da6db  mul     qword ptr [rdi+28h]
0x1801da6df  test    rdx, rdx
0x1801da6e2  jnz     short loc_1801DA6F1
0x1801da6e4  mov     rcx, [rdi+48h]
0x1801da6e8  lea     rdx, [rcx+rax]
0x1801da6ec  cmp     rdx, rcx
0x1801da6ef  jnb     short loc_1801DA6F3
0x1801da6f1  xor     edx, edx
0x1801da6f3  mov     rdx, [rdx]; SubStr
0x1801da6f6  mov     rcx, rbx; Str
0x1801da6f9  call    cs:__imp_strstr
0x1801da6ff  test    rax, rax
0x1801da702  jnz     short loc_1801DA710
0x1801da704  mov     rax, [rdi+30h]
0x1801da708  inc     r14
0x1801da70b  cmp     r14, rax
0x1801da70e  jb      short loc_1801DA6D1
0x1801da710  cmp     [rdi+30h], r14
0x1801da714  jz      loc_1801DAA5B
0x1801da71a  lea     r9, ?s_key@UtcJson@Shared@Compat@Windows@@0PAGA; ushort near * Windows::Compat::Shared::UtcJson::s_key
0x1801da721  mov     edx, 100h; unsigned __int64
0x1801da726  lea     r8, aS_0; "%S"
0x1801da72d  lea     rcx, [rbp+0C0h+SubStr]; char *
0x1801da731  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1801da736  lea     rdx, aStartutcjsontr_0; "StartUtcJsonTrace"
0x1801da73d  mov     rcx, rbx; Str
0x1801da740  call    cs:__imp_strstr
0x1801da746  test    rax, rax
0x1801da749  jz      short loc_1801DA7B8
0x1801da74b  lea     rdx, [rbp+0C0h+SubStr]; SubStr
0x1801da74f  mov     rcx, rbx; Str
0x1801da752  call    cs:__imp_strstr
0x1801da758  test    rax, rax
0x1801da75b  jnz     loc_1801DA7E7
0x1801da761  jmp     short loc_1801DA7B8
0x1801da763  mov     rax, [rdi+60h]
0x1801da767  xor     r14d, r14d
0x1801da76a  test    rax, rax
0x1801da76d  jz      short loc_1801DA7AE
0x1801da76f  xor     edx, edx
0x1801da771  cmp     r14, rax
0x1801da774  jnb     short loc_1801DA791
0x1801da776  mov     rax, r14
0x1801da779  mul     qword ptr [rdi+58h]
0x1801da77d  test    rdx, rdx
0x1801da780  jnz     short loc_1801DA78F
0x1801da782  mov     rcx, [rdi+78h]
0x1801da786  lea     rdx, [rcx+rax]
0x1801da78a  cmp     rdx, rcx
0x1801da78d  jnb     short loc_1801DA791
0x1801da78f  xor     edx, edx
0x1801da791  mov     rdx, [rdx]; SubStr
0x1801da794  mov     rcx, rsi; Str
0x1801da797  call    cs:__imp_wcsstr
0x1801da79d  test    rax, rax
0x1801da7a0  jnz     short loc_1801DA7AE
0x1801da7a2  mov     rax, [rdi+60h]
0x1801da7a6  inc     r14
0x1801da7a9  cmp     r14, rax
0x1801da7ac  jb      short loc_1801DA76F
0x1801da7ae  cmp     [rdi+60h], r14
0x1801da7b2  jz      loc_1801DAA5B
0x1801da7b8  test    rsi, rsi
0x1801da7bb  jz      short loc_1801DA83B
0x1801da7bd  lea     rdx, aStartutcjsontr; "StartUtcJsonTrace"
0x1801da7c4  mov     rcx, rsi; Str
0x1801da7c7  call    cs:__imp_wcsstr
0x1801da7cd  test    rax, rax
0x1801da7d0  jz      short loc_1801DA83B
0x1801da7d2  lea     rdx, ?s_key@UtcJson@Shared@Compat@Windows@@0PAGA; SubStr
0x1801da7d9  mov     rcx, rsi; Str
0x1801da7dc  call    cs:__imp_wcsstr
0x1801da7e2  test    rax, rax
0x1801da7e5  jz      short loc_1801DA83B
0x1801da7e7  mov     rax, cs:UtcHelperWriteLogCallback
0x1801da7ee  test    rax, rax
0x1801da7f1  jz      short loc_1801DA822
0x1801da7f3  lea     rcx, aStartingUtcJso; "Starting UTC json trace."
0x1801da7fa  mov     edx, 331h
0x1801da7ff  mov     [rsp+1C0h+var_198], rcx
0x1801da804  lea     r9, aWindowsCompatS_0; "Windows::Compat::Shared::UtcJson::Proce"...
0x1801da80b  xor     ecx, ecx
0x1801da80d  mov     [rsp+1C0h+BufferSize], 0
0x1801da816  lea     r8, aOnecoreBaseApp_106; "onecore\\base\\appcompat\\shared\\unman"...
0x1801da81d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801da822  mov     rcx, [rdi+8]; hEvent
0x1801da826  call    cs:__imp_SetEvent
0x1801da82c  mov     rcx, [rdi+10h]; hEvent
0x1801da830  call    cs:__imp_ResetEvent
0x1801da836  jmp     loc_1801DAA5B
0x1801da83b  test    rbx, rbx
0x1801da83e  jz      short loc_1801DA867
0x1801da840  lea     rdx, aStoputcjsontra; "StopUtcJsonTrace"
0x1801da847  mov     rcx, rbx; Str
0x1801da84a  call    cs:__imp_strstr
0x1801da850  test    rax, rax
0x1801da853  jz      short loc_1801DA867
0x1801da855  lea     rdx, [rbp+0C0h+SubStr]; SubStr
0x1801da859  mov     rcx, rbx; Str
0x1801da85c  call    cs:__imp_strstr
0x1801da862  test    rax, rax
0x1801da865  jnz     short loc_1801DA896
0x1801da867  test    rsi, rsi
0x1801da86a  jz      short loc_1801DA8E4
0x1801da86c  lea     rdx, aStoputcjsontra_0; "StopUtcJsonTrace"
0x1801da873  mov     rcx, rsi; Str
0x1801da876  call    cs:__imp_wcsstr
0x1801da87c  test    rax, rax
0x1801da87f  jz      short loc_1801DA8E4
0x1801da881  lea     rdx, ?s_key@UtcJson@Shared@Compat@Windows@@0PAGA; SubStr
0x1801da888  mov     rcx, rsi; Str
0x1801da88b  call    cs:__imp_wcsstr
0x1801da891  test    rax, rax
0x1801da894  jz      short loc_1801DA8E4
0x1801da896  mov     rax, cs:UtcHelperWriteLogCallback
0x1801da89d  test    rax, rax
0x1801da8a0  jz      short loc_1801DA8D1
0x1801da8a2  lea     rcx, aStoppingUtcJso; "Stopping UTC json trace."
0x1801da8a9  mov     edx, 33Bh
0x1801da8ae  mov     [rsp+1C0h+var_198], rcx
0x1801da8b3  lea     r9, aWindowsCompatS_0; "Windows::Compat::Shared::UtcJson::Proce"...
0x1801da8ba  xor     ecx, ecx
0x1801da8bc  mov     [rsp+1C0h+BufferSize], 0
0x1801da8c5  lea     r8, aOnecoreBaseApp_106; "onecore\\base\\appcompat\\shared\\unman"...
0x1801da8cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801da8d1  mov     rcx, [rdi+10h]; hEvent
0x1801da8d5  call    cs:__imp_SetEvent
0x1801da8db  mov     rcx, [rdi+8]
0x1801da8df  jmp     loc_1801DA830
0x1801da8e4  mov     rcx, [rdi+8]; hHandle
0x1801da8e8  xor     edx, edx; dwMilliseconds
0x1801da8ea  call    cs:__imp_WaitForSingleObject
0x1801da8f0  test    eax, eax
0x1801da8f2  jnz     loc_1801DAA5B
0x1801da8f8  cmp     qword ptr cs:xmmword_1802D3F08, 0
0x1801da900  jbe     short loc_1801DA915
0x1801da902  mov     rdx, rsi; unsigned __int16 *
0x1801da905  mov     rcx, rbx; char *
0x1801da908  call    ?CheckAllowedProcesses@UtcJson@Shared@Compat@Windows@@CAJPEBDPEBG@Z; Windows::Compat::Shared::UtcJson::CheckAllowedProcesses(char const *,ushort const *)
0x1801da90d  test    eax, eax
0x1801da90f  jnz     loc_1801DAA5B
0x1801da915  cmp     byte ptr [rdi+19h], 0
0x1801da919  jz      short loc_1801DA96D
0x1801da91b  cmp     byte ptr [rdi+18h], 0
0x1801da91f  lea     rax, asc_180285330; ",\r\n        "
0x1801da926  mov     rcx, [rdi]; struct IStream *
0x1801da929  lea     rdx, asc_180285340; "\r\n        "
0x1801da930  cmovz   rdx, rax; char *
0x1801da934  call    ?WriteStringToFile@UtcJson@Shared@Compat@Windows@@CAJPEAUIStream@@PEBD@Z; Windows::Compat::Shared::UtcJson::WriteStringToFile(IStream *,char const *)
0x1801da939  mov     ecx, eax
0x1801da93b  test    eax, eax
0x1801da93d  jns     short loc_1801DA96D
0x1801da93f  mov     rax, cs:UtcHelperWriteLogCallback
0x1801da946  test    rax, rax
0x1801da949  jz      loc_1801DAA5B
0x1801da94f  lea     rdx, aErrorWritingFo; "Error writing formatting: [0x%x]."
0x1801da956  mov     dword ptr [rsp+1C0h+var_190], ecx
0x1801da95a  mov     [rsp+1C0h+var_198], rdx
0x1801da95f  mov     edx, 359h
0x1801da964  mov     dword ptr [rsp+1C0h+BufferSize], ecx
0x1801da968  jmp     loc_1801DAA43
0x1801da96d  mov     rcx, [rdi]; struct IStream *
0x1801da970  mov     byte ptr [rdi+18h], 0
0x1801da974  test    rbx, rbx
0x1801da977  jz      short loc_1801DA9D3
0x1801da979  mov     rdx, rbx; char *
0x1801da97c  call    ?WriteStringToFile@UtcJson@Shared@Compat@Windows@@CAJPEAUIStream@@PEBD@Z; Windows::Compat::Shared::UtcJson::WriteStringToFile(IStream *,char const *)
0x1801da981  test    eax, eax
0x1801da983  jns     short loc_1801DAA02
0x1801da985  mov     r10, cs:UtcHelperWriteLogCallback
0x1801da98c  test    r10, r10
0x1801da98f  jz      loc_1801DAA5B
0x1801da995  mov     [rsp+1C0h+var_188], eax
0x1801da999  lea     rcx, aErrorWritingJs_0; "Error writing JSON %hs: [0x%x]."
0x1801da9a0  mov     [rsp+1C0h+var_190], rbx
0x1801da9a5  mov     edx, 361h
0x1801da9aa  mov     [rsp+1C0h+var_198], rcx
0x1801da9af  lea     r8, aOnecoreBaseApp_106; "onecore\\base\\appcompat\\shared\\unman"...
0x1801da9b6  mov     dword ptr [rsp+1C0h+BufferSize], eax
0x1801da9ba  lea     r9, aWindowsCompatS_0; "Windows::Compat::Shared::UtcJson::Proce"...
0x1801da9c1  mov     rax, r10
0x1801da9c4  mov     ecx, 1
0x1801da9c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801da9ce  jmp     loc_1801DAA5B
0x1801da9d3  mov     rdx, rsi; lpWideCharStr
0x1801da9d6  call    ?WriteStringToFile@UtcJson@Shared@Compat@Windows@@CAJPEAUIStream@@PEBG@Z; Windows::Compat::Shared::UtcJson::WriteStringToFile(IStream *,ushort const *)
0x1801da9db  test    eax, eax
0x1801da9dd  jns     short loc_1801DAA02
0x1801da9df  mov     r10, cs:UtcHelperWriteLogCallback
  ... truncated ...
```
