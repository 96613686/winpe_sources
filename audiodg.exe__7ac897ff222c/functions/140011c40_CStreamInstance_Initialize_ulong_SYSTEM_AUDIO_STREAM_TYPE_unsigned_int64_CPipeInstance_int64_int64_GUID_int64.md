# CStreamInstance::Initialize(ulong,SYSTEM_AUDIO_STREAM_TYPE,unsigned __int64,CPipeInstance *,__int64,__int64,_GUID,__int64)

- ea: `0x140011c40`
- end: `0x140011df9`
- name: `?Initialize@CStreamInstance@@UEAAJKW4SYSTEM_AUDIO_STREAM_TYPE@@_KPEAVCPipeInstance@@_J3U_GUID@@3@Z`
- size: `441`
- prototype: `int __high(unsigned int, enum SYSTEM_AUDIO_STREAM_TYPE, unsigned __int64, struct CPipeInstance *, __int64, __int64, struct _GUID, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x14000ad48`
- `0x14000c33c`
- `0x14000e11c`
- `0x14000e280`
- `0x14000e404`
- `0x140011c40`
- `0x140011e00`
- `0x14005d0e0`
- `0x140070fa0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140011df1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140011df1`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140011cb2`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140011cd5`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140011cb2`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140011cd5`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x140011c98`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x140011c98`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140011d15`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140011d15`

## pseudocode

```c
__int64 __fastcall CStreamInstance::Initialize(
        __int64 a1,
        DWORD a2,
        int a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int128 *a8,
        __int64 a9)
{
  const struct _tlgProvider_t *v13; // rax
  char *v14; // rbx
  char *v15; // rsi
  HRESULT v16; // eax
  unsigned int v17; // ebx
  const char *v18; // r9
  HANDLE v19; // rax
  __int128 v20; // xmm0
  int v22[4]; // [rsp+20h] [rbp-138h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+30h] [rbp-128h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+0h]

  v13 = AudioDgTelemetryProvider::Provider();
  CPerfTracker::CPerfTracker(&PerformanceCount, v13, "SrvStreamInstance_Initialize", 0);
  v14 = 0;
  v15 = 0;
  if ( a2 )
  {
    v16 = CoImpersonateClient();
    v17 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x34,
        (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\streaminstance.cpp",
        (const char *)(unsigned int)v16,
        v22[0]);
      goto LABEL_13;
    }
    v14 = (char *)OpenProcess(0x3000u, 0, a2);
    *(_QWORD *)v22 = v14;
    if ( ((unsigned __int64)(v14 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      v19 = OpenProcess(0x2400u, 0, a2);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        v22,
        v19);
      v14 = *(char **)v22;
    }
    v15 = v14;
    if ( ((unsigned __int64)(v14 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0x43,
        (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\streaminstance.cpp",
        v18);
    CoRevertToSelf();
  }
  *(_QWORD *)(a1 + 80) = a5;
  *(_QWORD *)(a1 + 192) = a6;
  *(_DWORD *)(a1 + 112) = a3;
  *(_QWORD *)(a1 + 88) = a4;
  if ( (int *)(a1 + 136) != v22 )
  {
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      a1 + 136,
      v14);
    v14 = 0;
    v15 = 0;
  }
  *(_QWORD *)(a1 + 200) = a7;
  v20 = *a8;
  *(_QWORD *)(a1 + 272) = a9;
  *(_OWORD *)(a1 + 208) = v20;
  PublishDeviceGraphWnfState();
  if ( (unsigned __int64)(v15 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v14);
  v17 = 0;
LABEL_13:
  CPerfTracker::~CPerfTracker((CPerfTracker *)&PerformanceCount);
  return v17;
}

```

## disassembly

```asm
0x140011c40  mov     [rsp+arg_10], rbx
0x140011c45  push    rbp
0x140011c46  push    rsi
0x140011c47  push    rdi
0x140011c48  push    r14
0x140011c4a  push    r15
0x140011c4c  sub     rsp, 130h
0x140011c53  mov     rax, cs:__security_cookie
0x140011c5a  xor     rax, rsp
0x140011c5d  mov     [rsp+158h+var_38], rax
0x140011c65  mov     r14, r9
0x140011c68  mov     r15d, r8d
0x140011c6b  mov     ebp, edx
0x140011c6d  mov     rdi, rcx
0x140011c70  call    ?Provider@AudioDgTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioDgTelemetryProvider::Provider(void)
0x140011c75  mov     rdx, rax; struct _tlgProvider_t *
0x140011c78  lea     r8, aSrvstreaminsta_1; "SrvStreamInstance_Initialize"
0x140011c7f  xor     r9d, r9d; char *
0x140011c82  lea     rcx, [rsp+158h+PerformanceCount]; lpPerformanceCount
0x140011c87  call    ??0CPerfTracker@@QEAA@PEBU_tlgProvider_t@@QEBD1@Z; CPerfTracker::CPerfTracker(_tlgProvider_t const *,char const * const,char const * const)
0x140011c8c  xor     ebx, ebx
0x140011c8e  xor     esi, esi
0x140011c90  test    ebp, ebp
0x140011c92  jz      loc_140011D1B
0x140011c98  call    cs:__imp_CoImpersonateClient
0x140011c9e  mov     ebx, eax
0x140011ca0  test    eax, eax
0x140011ca2  js      loc_140011DD0
0x140011ca8  mov     r8d, ebp; dwProcessId
0x140011cab  xor     edx, edx; bInheritHandle
0x140011cad  mov     ecx, 3000h; dwDesiredAccess
0x140011cb2  call    cs:__imp_OpenProcess
0x140011cb8  mov     rbx, rax
0x140011cbb  mov     qword ptr [rsp+158h+var_138], rax
0x140011cc0  inc     rax
0x140011cc3  test    rax, 0FFFFFFFFFFFFFFFEh
0x140011cc9  jnz     short loc_140011CED
0x140011ccb  mov     r8d, ebp; dwProcessId
0x140011cce  xor     edx, edx; bInheritHandle
0x140011cd0  mov     ecx, 2400h; dwDesiredAccess
0x140011cd5  call    cs:__imp_OpenProcess
0x140011cdb  mov     rdx, rax
0x140011cde  lea     rcx, [rsp+158h+var_138]
0x140011ce3  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x140011ce8  mov     rbx, qword ptr [rsp+158h+var_138]
0x140011ced  lea     rax, [rbx+1]
0x140011cf1  mov     rsi, rbx
0x140011cf4  test    rax, 0FFFFFFFFFFFFFFFEh
0x140011cfa  jnz     short loc_140011D15
0x140011cfc  mov     rcx, [rsp+158h]; this
0x140011d04  lea     r8, aAvcoreAudiocor_67; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140011d0b  mov     edx, 43h ; 'C'; void *
0x140011d10  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x140011d15  call    cs:__imp_CoRevertToSelf
0x140011d1b  mov     rax, [rsp+158h+arg_20]
0x140011d23  lea     rcx, [rdi+88h]
0x140011d2a  mov     [rdi+50h], rax
0x140011d2e  mov     rax, [rsp+158h+arg_28]
0x140011d36  mov     [rdi+0C0h], rax
0x140011d3d  lea     rax, [rsp+158h+var_138]
0x140011d42  mov     [rdi+70h], r15d
0x140011d46  mov     [rdi+58h], r14
0x140011d4a  cmp     rcx, rax
0x140011d4d  jz      short loc_140011D5B
0x140011d4f  mov     rdx, rbx
0x140011d52  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x140011d57  xor     ebx, ebx
0x140011d59  xor     esi, esi
0x140011d5b  mov     rax, [rsp+158h+arg_30]
0x140011d63  mov     [rdi+0C8h], rax
0x140011d6a  mov     rax, [rsp+158h+arg_38]
0x140011d72  movups  xmm0, xmmword ptr [rax]
0x140011d75  mov     rax, [rsp+158h+arg_40]
0x140011d7d  mov     [rdi+110h], rax
0x140011d84  movdqu  xmmword ptr [rdi+0D0h], xmm0
0x140011d8c  call    ?PublishDeviceGraphWnfState@@YAXXZ; PublishDeviceGraphWnfState(void)
0x140011d91  lea     rax, [rsi-1]
0x140011d95  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140011d99  jbe     short loc_140011DEE
0x140011d9b  xor     ebx, ebx
0x140011d9d  lea     rcx, [rsp+158h+PerformanceCount]; this
0x140011da2  call    ??1CPerfTracker@@QEAA@XZ; CPerfTracker::~CPerfTracker(void)
0x140011da7  mov     eax, ebx
0x140011da9  mov     rcx, [rsp+158h+var_38]
0x140011db1  xor     rcx, rsp; StackCookie
0x140011db4  call    __security_check_cookie
0x140011db9  mov     rbx, [rsp+158h+arg_10]
0x140011dc1  add     rsp, 130h
0x140011dc8  pop     r15
0x140011dca  pop     r14
0x140011dcc  pop     rdi
0x140011dcd  pop     rsi
0x140011dce  pop     rbp
0x140011dcf  retn
0x140011dd0  mov     rcx, [rsp+158h]; this
0x140011dd8  lea     r8, aAvcoreAudiocor_67; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140011ddf  mov     r9d, eax; char *
0x140011de2  mov     edx, 34h ; '4'; void *
0x140011de7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140011dec  jmp     short loc_140011D9D
0x140011dee  mov     rcx, rbx; hObject
0x140011df1  call    cs:__imp_CloseHandle
0x140011df7  jmp     short loc_140011D9B
```
