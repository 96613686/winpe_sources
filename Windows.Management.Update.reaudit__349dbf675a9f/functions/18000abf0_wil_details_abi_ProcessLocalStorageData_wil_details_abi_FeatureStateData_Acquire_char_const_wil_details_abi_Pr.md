# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18000abf0`
- end: `0x18000afc2`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `978`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000b1a4`

## callees

- `0x180002880`
- `0x1800035cc`
- `0x180009b58`
- `0x18000a35c`
- `0x18000abf0`
- `0x18000afc8`
- `0x18000b408`
- `0x18000c1b8`
- `0x18000d154`
- `0x18000eb04`
- `0x18000f648`
- `0x18000fb7c`
- `0x180010474`
- `0x18001080c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000ac6d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000ac6d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000aec3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000aec3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000aca3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000aca3`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000ad28`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000ae35`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000aef4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000ad28`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000ae35`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000aef4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000adf9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000adf9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ae0d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ae0d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000ac26`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000ac26`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ad3f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ae51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000af10`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ad3f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ae51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000af10`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  HANDLE v6; // rbx
  DWORD v8; // eax
  void *v9; // rdx
  unsigned int v10; // r8d
  char *v11; // r9
  void *v12; // r14
  int ValueInternal; // eax
  unsigned __int64 v14; // r8
  unsigned int v15; // edi
  unsigned int v16; // r8d
  unsigned int v17; // r8d
  unsigned int v18; // r8d
  const char *v19; // r9
  unsigned int v20; // r8d
  const char *v21; // r9
  _DWORD *v22; // rcx
  HANDLE v23; // rbx
  char *v24; // rax
  unsigned int v25; // r8d
  char *v26; // rdi
  unsigned int v27; // esi
  unsigned int v28; // r8d
  int v29; // eax
  unsigned int v30; // r8d
  HANDLE ProcessHeap; // rax
  unsigned int v32; // r8d
  const char *v33; // r9
  unsigned int v34; // r8d
  const char *v35; // r9
  __int64 v36; // rax
  unsigned int v37; // r8d
  const char *v38; // r9
  unsigned int v39; // r8d
  const char *v40; // r9
  int v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+20h] [rbp-E0h]
  int v43; // [rsp+20h] [rbp-E0h]
  HANDLE hHandle; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v45; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v46; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  hHandle = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &hHandle,
    Mutex);
  v6 = hHandle;
  if ( !hHandle )
    return wil::details::GetLastErrorFailHr(v5);
  v8 = WaitForSingleObjectEx(hHandle, 0xFFFFFFFF, 0);
  if ( v8 == 258 )
  {
    v12 = 0;
  }
  else
  {
    if ( (v8 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(retaddr, v9, v10, v11);
    v12 = v6;
  }
  v46 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, &v46, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x64, v14, (const char *)(unsigned int)ValueInternal, 304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6D, v16, (const char *)v15, v41);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12B, v17, (const char *)v15, v42);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9E7, v18, v19);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DD, v20, v21);
    return v15;
  }
  v22 = (_DWORD *)(4 * v46);
  if ( 4 * v46 )
  {
    *a2 = v22;
    v23 = hHandle;
    *(_DWORD *)*a2 = *v22 + 1;
    goto LABEL_24;
  }
  *a2 = 0;
  v24 = (char *)wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v26 = v24;
  if ( v24 )
  {
    v45 = 0;
    v29 = wil::details_abi::SemaphoreValue::CreateFromPointer(
            (wil::details_abi::SemaphoreValue *)&v45,
            (char *)Name,
            (unsigned __int64)v24);
    v27 = v29;
    if ( v29 >= 0 )
    {
      *((_QWORD *)v26 + 2) = v45;
      v36 = *((_QWORD *)&v45 + 1);
      *((_QWORD *)v26 + 1) = v6;
      v23 = 0;
      v45 = 0u;
      *((_QWORD *)v26 + 3) = v36;
      *(_DWORD *)v26 = 1;
      memset_0(v26 + 40, 0, 0x108u);
      *((_QWORD *)v26 + 4) = 0;
      wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v26 + 40));
      InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v26 + 232), 0, 0);
      *((_QWORD *)v26 + 34) = 0;
      *((_QWORD *)v26 + 35) = 0;
      *((_QWORD *)v26 + 36) = 0;
      *((_QWORD *)v26 + 37) = 0;
      *a2 = v26;
      wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)&v45);
LABEL_24:
      if ( v12 && !ReleaseMutex(v12) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9E7, v37, v38);
      if ( v23 && !CloseHandle(v23) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DD, v39, v40);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v30, (const char *)(unsigned int)v29, 304);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)&v45);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v26);
  }
  else
  {
    v27 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x148, v25, (const char *)0x8007000ELL, 304);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x134, v28, (const char *)v27, v43);
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9E7, v32, v33);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DD, v34, v35);
  return v27;
}

```

## disassembly

```asm
0x18000abf0  mov     [rsp-8+arg_10], rbx
0x18000abf5  push    rbp
0x18000abf6  push    rsi
0x18000abf7  push    rdi
0x18000abf8  push    r14
0x18000abfa  push    r15
0x18000abfc  lea     rbp, [rsp-170h]
0x18000ac04  sub     rsp, 270h
0x18000ac0b  mov     rax, cs:__security_cookie
0x18000ac12  xor     rax, rsp
0x18000ac15  mov     [rbp+190h+var_30], rax
0x18000ac1c  and     qword ptr [rdx], 0
0x18000ac20  mov     r15, rdx
0x18000ac23  mov     rbx, rcx
0x18000ac26  call    cs:__imp_GetCurrentProcessId
0x18000ac2d  nop     dword ptr [rax+rax+00h]
0x18000ac32  mov     esi, 130h
0x18000ac37  mov     [rsp+290h+var_268], rbx
0x18000ac3c  mov     r9d, eax
0x18000ac3f  mov     [rsp+290h+var_270], esi; int
0x18000ac43  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000ac4a  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x18000ac4f  lea     edx, [rsi-2Ch]; unsigned __int64
0x18000ac52  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000ac57  and     [rsp+290h+hHandle], 0
0x18000ac5d  lea     rdx, [rsp+290h+Name]; lpName
0x18000ac62  mov     r9d, 1F0001h; dwDesiredAccess
0x18000ac68  xor     r8d, r8d; dwFlags
0x18000ac6b  xor     ecx, ecx; lpMutexAttributes
0x18000ac6d  call    cs:__imp_CreateMutexExW
0x18000ac74  nop     dword ptr [rax+rax+00h]
0x18000ac79  mov     rdx, rax
0x18000ac7c  lea     rcx, [rsp+290h+hHandle]
0x18000ac81  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000ac86  mov     rbx, [rsp+290h+hHandle]
0x18000ac8b  test    rbx, rbx
0x18000ac8e  jnz     short loc_18000AC9A
0x18000ac90  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000ac95  jmp     loc_18000AF22
0x18000ac9a  xor     r8d, r8d; bAlertable
0x18000ac9d  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000aca0  mov     rcx, rbx; hHandle
0x18000aca3  call    cs:__imp_WaitForSingleObjectEx
0x18000acaa  nop     dword ptr [rax+rax+00h]
0x18000acaf  cmp     eax, 102h
0x18000acb4  jz      short loc_18000ACC6
0x18000acb6  test    eax, 0FFFFFF7Fh
0x18000acbb  jnz     loc_18000AF5B
0x18000acc1  mov     r14, rbx
0x18000acc4  jmp     short loc_18000ACC9
0x18000acc6  xor     r14d, r14d
0x18000acc9  and     [rsp+290h+var_248], 0
0x18000accf  lea     r8, [rsp+290h+var_248]; unsigned __int64 *
0x18000acd4  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x18000acd9  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000acde  mov     edi, eax
0x18000ace0  test    eax, eax
0x18000ace2  jns     short loc_18000AD5A
0x18000ace4  mov     rcx, [rbp+198h]; this
0x18000aceb  mov     r9d, eax; char *
0x18000acee  mov     edx, 64h ; 'd'; void *
0x18000acf3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000acf8  mov     rcx, [rbp+198h]; this
0x18000acff  mov     r9d, edi; char *
0x18000ad02  mov     edx, 6Dh ; 'm'; void *
0x18000ad07  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ad0c  mov     rcx, [rbp+198h]; this
0x18000ad13  mov     r9d, edi; char *
0x18000ad16  mov     edx, 12Bh; void *
0x18000ad1b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ad20  test    r14, r14
0x18000ad23  jz      short loc_18000AD3C
0x18000ad25  mov     rcx, r14; hMutex
0x18000ad28  call    cs:__imp_ReleaseMutex
0x18000ad2f  nop     dword ptr [rax+rax+00h]
0x18000ad34  test    eax, eax
0x18000ad36  jz      loc_18000AF68
0x18000ad3c  mov     rcx, rbx; hObject
0x18000ad3f  call    cs:__imp_CloseHandle
0x18000ad46  nop     dword ptr [rax+rax+00h]
0x18000ad4b  test    eax, eax
0x18000ad4d  jz      loc_18000AF7A
0x18000ad53  mov     eax, edi
0x18000ad55  jmp     loc_18000AF22
0x18000ad5a  mov     rax, [rsp+290h+var_248]
0x18000ad5f  lea     rcx, ds:0[rax*4]
0x18000ad67  test    rcx, rcx
0x18000ad6a  jz      short loc_18000AD82
0x18000ad6c  mov     [r15], rcx
0x18000ad6f  mov     ecx, [rcx]
0x18000ad71  mov     rax, [r15]
0x18000ad74  inc     ecx
0x18000ad76  mov     rbx, [rsp+290h+hHandle]
0x18000ad7b  mov     [rax], ecx
0x18000ad7d  jmp     loc_18000AEEC
0x18000ad82  and     qword ptr [r15], 0
0x18000ad86  mov     rdx, rsi; dwBytes
0x18000ad89  mov     ecx, 8; dwFlags
0x18000ad8e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000ad93  mov     rdi, rax
0x18000ad96  test    rax, rax
0x18000ad99  jnz     short loc_18000ADB6
0x18000ad9b  mov     rcx, [rbp+198h]; this
0x18000ada2  mov     esi, 8007000Eh
0x18000ada7  mov     r9d, esi; char *
0x18000adaa  mov     edx, 148h; void *
0x18000adaf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000adb4  jmp     short loc_18000AE19
0x18000adb6  xorps   xmm0, xmm0
0x18000adb9  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x18000adbe  mov     r8, rdi; void *
0x18000adc1  lea     rcx, [rsp+290h+var_258]; this
0x18000adc6  movdqu  [rsp+290h+var_258], xmm0
0x18000adcc  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x18000add1  mov     esi, eax
0x18000add3  test    eax, eax
0x18000add5  jns     loc_18000AE6C
0x18000addb  mov     rcx, [rbp+198h]; this
0x18000ade2  mov     r9d, eax; char *
0x18000ade5  mov     edx, 14Bh; void *
0x18000adea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000adef  lea     rcx, [rsp+290h+var_258]; this
0x18000adf4  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000adf9  call    cs:__imp_GetProcessHeap
0x18000ae00  nop     dword ptr [rax+rax+00h]
0x18000ae05  mov     r8, rdi; lpMem
0x18000ae08  xor     edx, edx; dwFlags
0x18000ae0a  mov     rcx, rax; hHeap
0x18000ae0d  call    cs:__imp_HeapFree
0x18000ae14  nop     dword ptr [rax+rax+00h]
0x18000ae19  mov     rcx, [rbp+198h]; this
0x18000ae20  mov     r9d, esi; char *
0x18000ae23  mov     edx, 134h; void *
0x18000ae28  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ae2d  test    r14, r14
0x18000ae30  jz      short loc_18000AE49
0x18000ae32  mov     rcx, r14; hMutex
0x18000ae35  call    cs:__imp_ReleaseMutex
0x18000ae3c  nop     dword ptr [rax+rax+00h]
0x18000ae41  test    eax, eax
0x18000ae43  jz      loc_18000AF8C
0x18000ae49  test    rbx, rbx
0x18000ae4c  jz      short loc_18000AE65
0x18000ae4e  mov     rcx, rbx; hObject
0x18000ae51  call    cs:__imp_CloseHandle
0x18000ae58  nop     dword ptr [rax+rax+00h]
0x18000ae5d  test    eax, eax
0x18000ae5f  jz      loc_18000AF9E
0x18000ae65  mov     eax, esi
0x18000ae67  jmp     loc_18000AF22
0x18000ae6c  mov     rax, qword ptr [rsp+290h+var_258]
0x18000ae71  lea     rcx, [rdi+28h]; void *
0x18000ae75  mov     [rdi+10h], rax
0x18000ae79  xor     edx, edx; Val
0x18000ae7b  mov     rax, qword ptr [rsp+290h+var_258+8]
0x18000ae80  mov     r8d, 108h; Size
0x18000ae86  mov     [rdi+8], rbx
0x18000ae8a  xor     ebx, ebx
0x18000ae8c  and     qword ptr [rsp+290h+var_258], rbx
0x18000ae91  and     qword ptr [rsp+290h+var_258+8], rbx
0x18000ae96  mov     [rdi+18h], rax
0x18000ae9a  mov     dword ptr [rdi], 1
0x18000aea0  call    memset_0
0x18000aea5  xor     eax, eax
0x18000aea7  lea     rcx, [rdi+28h]; this
0x18000aeab  mov     [rdi+20h], rax
0x18000aeaf  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000aeb4  lea     rsi, [rdi+0E8h]
0x18000aebb  xor     r8d, r8d; Flags
0x18000aebe  mov     rcx, rsi; lpCriticalSection
0x18000aec1  xor     edx, edx; dwSpinCount
0x18000aec3  call    cs:__imp_InitializeCriticalSectionEx
0x18000aeca  nop     dword ptr [rax+rax+00h]
0x18000aecf  and     [rsi+28h], rbx
0x18000aed3  lea     rcx, [rsp+290h+var_258]; this
0x18000aed8  and     [rsi+30h], rbx
0x18000aedc  and     [rsi+38h], rbx
0x18000aee0  and     [rsi+40h], rbx
0x18000aee4  mov     [r15], rdi
0x18000aee7  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000aeec  test    r14, r14
0x18000aeef  jz      short loc_18000AF08
0x18000aef1  mov     rcx, r14; hMutex
0x18000aef4  call    cs:__imp_ReleaseMutex
0x18000aefb  nop     dword ptr [rax+rax+00h]
0x18000af00  test    eax, eax
0x18000af02  jz      loc_18000AFB0
0x18000af08  test    rbx, rbx
0x18000af0b  jz      short loc_18000AF20
0x18000af0d  mov     rcx, rbx; hObject
0x18000af10  call    cs:__imp_CloseHandle
0x18000af17  nop     dword ptr [rax+rax+00h]
0x18000af1c  test    eax, eax
0x18000af1e  jz      short loc_18000AF49
0x18000af20  xor     eax, eax
0x18000af22  mov     rcx, [rbp+190h+var_30]
0x18000af29  xor     rcx, rsp; StackCookie
0x18000af2c  call    __security_check_cookie
0x18000af31  mov     rbx, [rsp+290h+arg_10]
0x18000af39  add     rsp, 270h
0x18000af40  pop     r15
0x18000af42  pop     r14
0x18000af44  pop     rdi
0x18000af45  pop     rsi
0x18000af46  pop     rbp
0x18000af47  retn
0x18000af49  mov     rcx, [rbp+198h]; this
0x18000af50  mov     edx, 9DDh; void *
0x18000af55  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000af5b  mov     rcx, [rbp+198h]; this
0x18000af62  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000af68  mov     rcx, [rbp+198h]; this
0x18000af6f  mov     edx, 9E7h; void *
0x18000af74  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000af7a  mov     rcx, [rbp+198h]; this
0x18000af81  mov     edx, 9DDh; void *
0x18000af86  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000af8c  mov     rcx, [rbp+198h]; this
0x18000af93  mov     edx, 9E7h; void *
0x18000af98  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000af9e  mov     rcx, [rbp+198h]; this
0x18000afa5  mov     edx, 9DDh; void *
0x18000afaa  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000afb0  mov     rcx, [rbp+198h]; this
0x18000afb7  mov     edx, 9E7h; void *
0x18000afbc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
