# HNS::Service::Util::details::ServiceMonitor::WorkerProc(void)

- ea: `0x180240720`
- end: `0x180240909`
- name: `?WorkerProc@ServiceMonitor@details@Util@Service@HNS@@AEAAXXZ`
- size: `489`
- prototype: `void __fastcall(HNS::Service::Util::details::ServiceMonitor *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180061dc4`
- `0x180240418`
- `0x1802404c8`
- `0x180240720`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18024074f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18024076c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18024074f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18024076c`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1802407d6`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1802407d6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18024080c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180240866`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1802408d4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18024080c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180240866`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1802408d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802407f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180240853`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802408c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802407f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180240853`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802408c1`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180240804`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18024085e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1802408cc`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180240804`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18024085e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1802408cc`

## string_xrefs

- `0x1802408f7`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
void __fastcall HNS::Service::Util::details::ServiceMonitor::WorkerProc(
        HNS::Service::Util::details::ServiceMonitor *this)
{
  HNS::Service::Util::details::ServiceMonitor *v1; // rdi
  void *v2; // rbx
  DWORD v3; // eax
  const char *v4; // r9
  DWORD v5; // r12d
  HNS::Service::Util::details::ServiceMonitor *v6; // r15
  SC_HANDLE *v7; // r14
  SC_HANDLE *v8; // rsi
  DWORD v9; // eax
  DWORD v10; // eax
  SC_HANDLE v11; // rsi
  DWORD LastError; // ebx
  const char *v13; // r9
  SC_HANDLE v14; // r12
  DWORD v15; // ebx
  SC_HANDLE v16; // rdi
  DWORD v17; // ebx
  DWORD v18; // edx
  int v19; // ecx
  DWORD v20; // edx
  int v21; // ecx
  HNS::Service::Util::details::ServiceMonitor *v22; // [rsp+30h] [rbp-58h]
  HANDLE Handles[10]; // [rsp+38h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  SC_HANDLE *v26; // [rsp+A8h] [rbp+20h]

  v1 = this;
  v2 = (void *)*((_QWORD *)this + 9);
  Handles[0] = v2;
  Handles[1] = *((HANDLE *)this + 10);
  v3 = WaitForSingleObjectEx(v2, 0, 0);
  if ( v3 != 258 )
  {
    if ( v3 || WaitForSingleObjectEx(v2, 0, 0) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xB07,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
        v4);
    return;
  }
  try
  {
    v5 = HNS::Service::Util::details::ServiceMonitor::WorkAndQueueNotification(v1);
    *((_DWORD *)v1 + 32) = *((_DWORD *)v1 + 34);
  }
  catch ( ... )
  {
    v18 = *((_DWORD *)this + 32);
    v19 = 2 * v18;
    if ( *((_DWORD *)this + 33) < 2 * v18 )
      v19 = *((_DWORD *)this + 33);
    *((_DWORD *)this + 32) = v19;
    v1 = this;
    v5 = v18;
  }
  v6 = v1;
  v22 = v1;
  v7 = (SC_HANDLE *)((char *)v1 + 8);
  v26 = (SC_HANDLE *)((char *)v1 + 8);
  v8 = (SC_HANDLE *)((char *)v1 + 8);
  while ( 1 )
  {
    v9 = WaitForMultipleObjectsEx(2u, Handles, 0, v5, 1);
    if ( !v9 )
      break;
    v10 = v9 - 1;
    if ( v10 )
    {
      if ( v10 == 257 )
        goto LABEL_13;
      v11 = (SC_HANDLE)*((_QWORD *)v1 + 1);
      if ( v11 )
      {
        LastError = GetLastError();
        CloseServiceHandle(v11);
        SetLastError(LastError);
      }
      *((_QWORD *)v1 + 1) = 0;
      v8 = (SC_HANDLE *)((char *)v6 + 8);
    }
    else
    {
      try
      {
        HNS::Service::Util::details::ServiceMonitor::TriggerCallbacks(v1);
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0xC6,
          (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\common\\helperlib\\src\\servicemonitor.cpp",
          v13);
        v1 = this;
        v7 = v26;
        v6 = v22;
      }
      v8 = v7;
LABEL_13:
      v14 = *v8;
      if ( *v8 )
      {
        v15 = GetLastError();
        CloseServiceHandle(v14);
        SetLastError(v15);
      }
      try
      {
        *v8 = 0;
        v5 = HNS::Service::Util::details::ServiceMonitor::WorkAndQueueNotification(v1);
        *((_DWORD *)v1 + 32) = *((_DWORD *)v1 + 34);
      }
      catch ( ... )
      {
        v20 = *((_DWORD *)this + 32);
        v21 = 2 * v20;
        if ( *((_DWORD *)this + 33) < 2 * v20 )
          v21 = *((_DWORD *)this + 33);
        *((_DWORD *)this + 32) = v21;
        v1 = this;
        v5 = v20;
        v7 = v26;
        v6 = v22;
        continue;
      }
    }
  }
  v16 = *v7;
  if ( *v7 )
  {
    v17 = GetLastError();
    CloseServiceHandle(v16);
    SetLastError(v17);
  }
  *v7 = 0;
}

```

## disassembly

```asm
0x180240720  mov     [rsp+arg_0], rcx
0x180240725  push    rbx
0x180240726  push    rsi
0x180240727  push    rdi
0x180240728  push    r12
0x18024072a  push    r14
0x18024072c  push    r15
0x18024072e  sub     rsp, 58h
0x180240732  mov     rdi, rcx
0x180240735  mov     rbx, [rcx+48h]
0x180240739  mov     [rsp+88h+Handles], rbx
0x18024073e  mov     rax, [rcx+50h]
0x180240742  mov     [rsp+88h+var_48], rax
0x180240747  xor     r8d, r8d; bAlertable
0x18024074a  xor     edx, edx; dwMilliseconds
0x18024074c  mov     rcx, rbx; hHandle
0x18024074f  call    cs:__imp_WaitForSingleObjectEx
0x180240755  cmp     eax, 102h
0x18024075a  jz      short loc_18024077F
0x18024075c  test    eax, eax
0x18024075e  jnz     loc_1802408EF
0x180240764  xor     r8d, r8d; bAlertable
0x180240767  xor     edx, edx; dwMilliseconds
0x180240769  mov     rcx, rbx; hHandle
0x18024076c  call    cs:__imp_WaitForSingleObjectEx
0x180240772  test    eax, eax
0x180240774  jnz     loc_1802408EF
0x18024077a  jmp     loc_1802408E1
0x18024077f  mov     rcx, rdi; this
0x180240782  call    ?WorkAndQueueNotification@ServiceMonitor@details@Util@Service@HNS@@AEAAKXZ; HNS::Service::Util::details::ServiceMonitor::WorkAndQueueNotification(void)
0x180240787  mov     r12d, eax
0x18024078a  mov     ecx, [rdi+88h]
0x180240790  mov     [rdi+80h], ecx
0x180240796  jmp     short loc_1802407A8
0x180240798  mov     rdi, [rsp+88h+arg_0]
0x1802407a0  mov     r12d, [rsp+88h+arg_8]
0x1802407a8  mov     r15, rdi
0x1802407ab  mov     [rsp+88h+var_58], rdi
0x1802407b0  lea     r14, [rdi+8]
0x1802407b4  mov     [rsp+88h+arg_18], r14
0x1802407bc  mov     rsi, r14
0x1802407bf  mov     [rsp+88h+bAlertable], 1; bAlertable
0x1802407c7  mov     r9d, r12d; dwMilliseconds
0x1802407ca  xor     r8d, r8d; bWaitAll
0x1802407cd  lea     rdx, [rsp+88h+Handles]; lpHandles
0x1802407d2  lea     ecx, [r8+2]; nCount
0x1802407d6  call    cs:__imp_WaitForMultipleObjectsEx
0x1802407dc  test    eax, eax
0x1802407de  jz      loc_1802408B9
0x1802407e4  sub     eax, 1
0x1802407e7  jz      short loc_180240820
0x1802407e9  cmp     eax, 101h
0x1802407ee  jz      short loc_180240843
0x1802407f0  mov     rsi, [rdi+8]
0x1802407f4  test    rsi, rsi
0x1802407f7  jz      short loc_180240812
0x1802407f9  call    cs:__imp_GetLastError
0x1802407ff  mov     ebx, eax
0x180240801  mov     rcx, rsi; hSCObject
0x180240804  call    cs:__imp_CloseServiceHandle
0x18024080a  mov     ecx, ebx; dwErrCode
0x18024080c  call    cs:__imp_SetLastError
0x180240812  mov     qword ptr [rdi+8], 0
0x18024081a  lea     rsi, [r15+8]
0x18024081e  jmp     short loc_1802407BF
0x180240820  mov     rcx, rdi; this
0x180240823  call    ?TriggerCallbacks@ServiceMonitor@details@Util@Service@HNS@@AEAAXXZ; HNS::Service::Util::details::ServiceMonitor::TriggerCallbacks(void)
0x180240828  nop
0x180240829  jmp     short loc_180240840
0x18024082b  mov     rdi, [rsp+88h+arg_0]
0x180240833  mov     r14, [rsp+88h+arg_18]
0x18024083b  mov     r15, [rsp+88h+var_58]
0x180240840  mov     rsi, r14
0x180240843  mov     [rsp+88h+arg_10], rsi
0x18024084b  mov     r12, [rsi]
0x18024084e  test    r12, r12
0x180240851  jz      short loc_18024086C
0x180240853  call    cs:__imp_GetLastError
0x180240859  mov     ebx, eax
0x18024085b  mov     rcx, r12; hSCObject
0x18024085e  call    cs:__imp_CloseServiceHandle
0x180240864  mov     ecx, ebx; dwErrCode
0x180240866  call    cs:__imp_SetLastError
0x18024086c  mov     qword ptr [rsi], 0
0x180240873  mov     rcx, rdi; this
0x180240876  call    ?WorkAndQueueNotification@ServiceMonitor@details@Util@Service@HNS@@AEAAKXZ; HNS::Service::Util::details::ServiceMonitor::WorkAndQueueNotification(void)
0x18024087b  mov     r12d, eax
0x18024087e  mov     eax, [rdi+88h]
0x180240884  mov     [rdi+80h], eax
0x18024088a  jmp     loc_1802407BF
0x18024088f  mov     rsi, [rsp+88h+arg_10]
0x180240897  mov     rdi, [rsp+88h+arg_0]
0x18024089f  mov     r12d, [rsp+88h+arg_8]
0x1802408a7  mov     r14, [rsp+88h+arg_18]
0x1802408af  mov     r15, [rsp+88h+var_58]
0x1802408b4  jmp     loc_1802407BF
0x1802408b9  mov     rdi, [r14]
0x1802408bc  test    rdi, rdi
0x1802408bf  jz      short loc_1802408DA
0x1802408c1  call    cs:__imp_GetLastError
0x1802408c7  mov     ebx, eax
0x1802408c9  mov     rcx, rdi; hSCObject
0x1802408cc  call    cs:__imp_CloseServiceHandle
0x1802408d2  mov     ecx, ebx; dwErrCode
0x1802408d4  call    cs:__imp_SetLastError
0x1802408da  mov     qword ptr [r14], 0
0x1802408e1  add     rsp, 58h
0x1802408e5  pop     r15
0x1802408e7  pop     r14
0x1802408e9  pop     r12
0x1802408eb  pop     rdi
0x1802408ec  pop     rsi
0x1802408ed  pop     rbx
0x1802408ee  retn
0x1802408ef  mov     rcx, [rsp+88h]; this
0x1802408f7  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1802408fe  mov     edx, 0B07h; void *
0x180240903  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
