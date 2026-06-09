# CUpdateDeploymentJob::Cancel(tagDeploymentOperationCancelContext)

- ea: `0x180031740`
- end: `0x180031932`
- name: `?Cancel@CUpdateDeploymentJob@@UEAAJW4tagDeploymentOperationCancelContext@@@Z`
- size: `498`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180002214`
- `0x180003180`
- `0x180007b6c`
- `0x1800110fc`
- `0x180011b44`
- `0x180031740`
- `0x18003843c`
- `0x180068ea0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180031897`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180031897`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031764`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031764`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031917`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031917`

## string_xrefs

- `0x18003180d`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`
- `0x180031873`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`
- `0x1800318a9`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`
- `0x1800318e8`: `Deployment job Id %ws : Cancel request processing complete. Job status = %ws`

## pseudocode

```c
__int64 __fastcall CUpdateDeploymentJob::Cancel(__int64 a1, int a2)
{
  __int64 v2; // rbx
  int v5; // edi
  __int64 v6; // rdx
  unsigned int LastError; // edi
  __int64 v8; // rcx
  int v9; // eax
  const char *v10; // r9
  __int64 DeploymentJobStatusAsString; // rdi
  __int64 v12; // rax
  int v14; // [rsp+20h] [rbp-98h]
  _BYTE v15[104]; // [rsp+50h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  v2 = a1 + 880;
  if ( a1 != -880 )
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 888));
  GetDeploymentJobStatusAsString(*(unsigned int *)(a1 + 872));
  Trace::GuidToString::GuidToString((Trace::GuidToString *)v15, (const struct _GUID *)(a1 + 16));
  WUTrace(0, 0, 0x1000000, 4, 0, L"Deployment job Id %ws : Cancel request received with context = %d. Job status = %ws");
  v5 = *(_DWORD *)(a1 + 872);
  if ( v5 == 2 || v5 == 7 || !v5 )
  {
    if ( !v5 && !*(_QWORD *)(a1 + 784) )
    {
      v6 = 3983;
      goto LABEL_12;
    }
    *(_DWORD *)(a1 + 828) = a2;
    *(_BYTE *)(a1 + 832) = 1;
    *(_DWORD *)(a1 + 872) = 1;
    if ( v5 == 2 || v5 == 7 )
    {
      v8 = *(_QWORD *)(a1 + 840);
      if ( v8 )
      {
        v9 = (*(__int64 (__fastcall **)(__int64, bool))(*(_QWORD *)v8 + 64LL))(v8, a2 == 1);
        if ( v9 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xF9A,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
            (const char *)(unsigned int)v9,
            v14);
      }
    }
    if ( (!v5 || v5 == 7) && !SetEvent(*(HANDLE *)(a1 + 784)) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0xFA1,
                    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
                    v10);
      goto LABEL_24;
    }
    DeploymentJobStatusAsString = GetDeploymentJobStatusAsString(*(unsigned int *)(a1 + 872));
    v12 = Trace::GuidToString::GuidToString((Trace::GuidToString *)v15, (const struct _GUID *)(a1 + 16));
    WUTrace(
      0,
      0,
      0x1000000,
      4,
      0,
      L"Deployment job Id %ws : Cancel request processing complete. Job status = %ws",
      v12,
      DeploymentJobStatusAsString);
  }
  else if ( v5 != 4 && v5 != 1 )
  {
    v6 = 3981;
LABEL_12:
    LastError = -2145124298;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
      (const char *)0x80240036LL,
      v14);
    goto LABEL_24;
  }
  LastError = 0;
LABEL_24:
  if ( v2 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v2 + 8));
  return LastError;
}

```

## disassembly

```asm
0x180031740  mov     [rsp+arg_10], rbx
0x180031745  push    rbp
0x180031746  push    rsi
0x180031747  push    rdi
0x180031748  sub     rsp, 0A0h
0x18003174f  lea     rbx, [rcx+370h]
0x180031756  mov     ebp, edx
0x180031758  mov     rsi, rcx
0x18003175b  test    rbx, rbx
0x18003175e  jz      short loc_18003176A
0x180031760  lea     rcx, [rbx+8]; lpCriticalSection
0x180031764  call    cs:__imp_EnterCriticalSection
0x18003176a  mov     ecx, [rsi+368h]
0x180031770  call    GetDeploymentJobStatusAsString
0x180031775  lea     rcx, [rsp+0B8h+var_68]; this
0x18003177a  mov     rdi, rax
0x18003177d  lea     rdx, [rsi+10h]; struct _GUID *
0x180031781  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x180031786  mov     [rsp+0B8h+var_78], rdi
0x18003178b  xor     edx, edx
0x18003178d  mov     dword ptr [rsp+0B8h+var_80], ebp
0x180031791  xor     ecx, ecx
0x180031793  mov     [rsp+0B8h+var_88], rax
0x180031798  mov     r8d, 1000000h
0x18003179e  lea     rax, aDeploymentJobI_60; "Deployment job Id %ws : Cancel request "...
0x1800317a5  mov     [rsp+0B8h+var_90], rax
0x1800317aa  lea     r9d, [rdx+4]
0x1800317ae  mov     qword ptr [rsp+0B8h+var_98], 0; int
0x1800317b7  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800317bc  mov     edi, [rsi+368h]
0x1800317c2  cmp     edi, 2
0x1800317c5  jz      short loc_1800317E9
0x1800317c7  cmp     edi, 7
0x1800317ca  jz      short loc_1800317E9
0x1800317cc  test    edi, edi
0x1800317ce  jz      short loc_1800317E9
0x1800317d0  cmp     edi, 4
0x1800317d3  jz      loc_18003190C
0x1800317d9  cmp     edi, 1
0x1800317dc  jz      loc_18003190C
0x1800317e2  mov     edx, 0F8Dh
0x1800317e7  jmp     short loc_180031805
0x1800317e9  cmp     edi, 1
0x1800317ec  jz      loc_18003190C
0x1800317f2  test    edi, edi
0x1800317f4  jnz     short loc_180031826
0x1800317f6  cmp     qword ptr [rsi+310h], 0
0x1800317fe  jnz     short loc_180031826
0x180031800  mov     edx, 0F8Fh; void *
0x180031805  mov     rcx, [rsp+0B8h]; this
0x18003180d  lea     r8, aCW1SSrcClientU_10; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180031814  mov     edi, 80240036h
0x180031819  mov     r9d, edi; char *
0x18003181c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031821  jmp     loc_18003190E
0x180031826  mov     [rsi+33Ch], ebp
0x18003182c  mov     byte ptr [rsi+340h], 1
0x180031833  mov     dword ptr [rsi+368h], 1
0x18003183d  cmp     edi, 2
0x180031840  jz      short loc_180031847
0x180031842  cmp     edi, 7
0x180031845  jnz     short loc_180031887
0x180031847  mov     rcx, [rsi+348h]
0x18003184e  test    rcx, rcx
0x180031851  jz      short loc_180031887
0x180031853  mov     rax, [rcx]
0x180031856  xor     edx, edx
0x180031858  cmp     ebp, 1
0x18003185b  setz    dl
0x18003185e  mov     rax, [rax+40h]
0x180031862  call    _guard_dispatch_icall
0x180031867  test    eax, eax
0x180031869  jns     short loc_180031887
0x18003186b  mov     rcx, [rsp+0B8h]; this
0x180031873  lea     r8, aCW1SSrcClientU_10; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x18003187a  mov     r9d, eax; char *
0x18003187d  mov     edx, 0F9Ah; void *
0x180031882  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180031887  test    edi, edi
0x180031889  jz      short loc_180031890
0x18003188b  cmp     edi, 7
0x18003188e  jnz     short loc_1800318BE
0x180031890  mov     rcx, [rsi+310h]; hEvent
0x180031897  call    cs:__imp_SetEvent
0x18003189d  test    eax, eax
0x18003189f  jnz     short loc_1800318BE
0x1800318a1  mov     rcx, [rsp+0B8h]; this
0x1800318a9  lea     r8, aCW1SSrcClientU_10; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x1800318b0  mov     edx, 0FA1h; void *
0x1800318b5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800318ba  mov     edi, eax
0x1800318bc  jmp     short loc_18003190E
0x1800318be  mov     ecx, [rsi+368h]
0x1800318c4  call    GetDeploymentJobStatusAsString
0x1800318c9  lea     rcx, [rsp+0B8h+var_68]; this
0x1800318ce  mov     rdi, rax
0x1800318d1  lea     rdx, [rsi+10h]; struct _GUID *
0x1800318d5  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x1800318da  mov     [rsp+0B8h+var_80], rdi
0x1800318df  xor     edx, edx
0x1800318e1  mov     [rsp+0B8h+var_88], rax
0x1800318e6  xor     ecx, ecx
0x1800318e8  lea     rax, aDeploymentJobI_72; "Deployment job Id %ws : Cancel request "...
0x1800318ef  mov     r8d, 1000000h
0x1800318f5  mov     [rsp+0B8h+var_90], rax
0x1800318fa  lea     r9d, [rdx+4]
0x1800318fe  mov     qword ptr [rsp+0B8h+var_98], 0
0x180031907  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18003190c  xor     edi, edi
0x18003190e  test    rbx, rbx
0x180031911  jz      short loc_18003191D
0x180031913  lea     rcx, [rbx+8]; lpCriticalSection
0x180031917  call    cs:__imp_LeaveCriticalSection
0x18003191d  mov     rbx, [rsp+0B8h+arg_10]
0x180031925  mov     eax, edi
0x180031927  add     rsp, 0A0h
0x18003192e  pop     rdi
0x18003192f  pop     rsi
0x180031930  pop     rbp
0x180031931  retn
```
