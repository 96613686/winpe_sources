# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1400056f4`
- end: `0x140005aca`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `982`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config`

## callers

- `0x14000c6b0`

## callees

- `0x140002116`
- `0x140003960`
- `0x140004918`
- `0x1400056f4`
- `0x140009c54`
- `0x14000d15c`
- `0x14000f8a4`
- `0x14001b1b8`
- `0x14001d240`
- `0x14001f7a0`
- `0x14001ffc0`
- `0x140020ff8`
- `0x1400213a8`
- `0x140080d70`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14000584c`
- `KERNEL32!CloseHandle` at `0x140005959`
- `KERNEL32!CloseHandle` at `0x140005a18`
- `KERNEL32!CloseHandle` at `0x14000584c`
- `KERNEL32!CloseHandle` at `0x140005959`
- `KERNEL32!CloseHandle` at `0x140005a18`
- `KERNEL32!CreateMutexExW` at `0x140005777`
- `KERNEL32!CreateMutexExW` at `0x140005777`
- `KERNEL32!GetCurrentProcessId` at `0x14000572d`
- `KERNEL32!GetCurrentProcessId` at `0x14000572d`
- `KERNEL32!HeapFree` at `0x140005915`
- `KERNEL32!HeapFree` at `0x140005915`
- `KERNEL32!GetProcessHeap` at `0x140005901`
- `KERNEL32!GetProcessHeap` at `0x140005901`
- `KERNEL32!WaitForSingleObjectEx` at `0x1400057ad`
- `KERNEL32!WaitForSingleObjectEx` at `0x1400057ad`
- `KERNEL32!ReleaseMutex` at `0x140005835`
- `KERNEL32!ReleaseMutex` at `0x14000593d`
- `KERNEL32!ReleaseMutex` at `0x1400059fc`
- `KERNEL32!ReleaseMutex` at `0x140005835`
- `KERNEL32!ReleaseMutex` at `0x14000593d`
- `KERNEL32!ReleaseMutex` at `0x1400059fc`
- `KERNEL32!InitializeCriticalSectionEx` at `0x1400059cb`
- `KERNEL32!InitializeCriticalSectionEx` at `0x1400059cb`

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
  char *v23; // rax
  unsigned int v24; // r8d
  char *v25; // rdi
  unsigned int v26; // esi
  unsigned int v27; // r8d
  int v28; // eax
  unsigned int v29; // r8d
  HANDLE ProcessHeap; // rax
  unsigned int v31; // r8d
  const char *v32; // r9
  unsigned int v33; // r8d
  const char *v34; // r9
  HANDLE v35; // rax
  unsigned int v36; // r8d
  const char *v37; // r9
  unsigned int v38; // r8d
  const char *v39; // r9
  int v40; // [rsp+20h] [rbp-E0h]
  int v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+20h] [rbp-E0h]
  HANDLE hHandle[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  hHandle[0] = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    hHandle,
    Mutex);
  v6 = hHandle[0];
  if ( !hHandle[0] )
    return wil::details::GetLastErrorFailHr(v5);
  v8 = WaitForSingleObjectEx(hHandle[0], 0xFFFFFFFF, 0);
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
  hHandle[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(
                    Name,
                    (bool)v9,
                    (unsigned __int64 *)hHandle,
                    (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x64, v14, (const char *)(unsigned int)ValueInternal, 304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6D, v16, (const char *)v15, v40);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12B, v17, (const char *)v15, v41);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9EC, v18, v19);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9E2, v20, v21);
    return v15;
  }
  v22 = (_DWORD *)(4 * (__int64)hHandle[0]);
  if ( 4 * (__int64)hHandle[0] )
  {
    *a2 = v22;
    ++*v22;
    goto LABEL_24;
  }
  *a2 = 0;
  v23 = (char *)wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v25 = v23;
  if ( v23 )
  {
    *(_OWORD *)hHandle = 0;
    v28 = wil::details_abi::SemaphoreValue::CreateFromPointer((wil::details_abi::SemaphoreValue *)hHandle, Name, v23);
    v26 = v28;
    if ( v28 >= 0 )
    {
      *((HANDLE *)v25 + 2) = hHandle[0];
      v35 = hHandle[1];
      *((_QWORD *)v25 + 1) = v6;
      v6 = 0;
      *((_QWORD *)v25 + 3) = v35;
      *(_DWORD *)v25 = 1;
      hHandle[0] = 0;
      hHandle[1] = 0;
      memset_0(v25 + 40, 0, 0x108u);
      *((_QWORD *)v25 + 4) = 0;
      wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v25 + 40));
      InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v25 + 232), 0, 0);
      *((_QWORD *)v25 + 34) = 0;
      *((_QWORD *)v25 + 35) = 0;
      *((_QWORD *)v25 + 36) = 0;
      *((_QWORD *)v25 + 37) = 0;
      *a2 = v25;
      wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)hHandle);
LABEL_24:
      if ( v12 && !ReleaseMutex(v12) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9EC, v36, v37);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9E2, v38, v39);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v29, (const char *)(unsigned int)v28, 304);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)hHandle);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v25);
  }
  else
  {
    v26 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x148, v24, (const char *)0x8007000ELL, 304);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x134, v27, (const char *)v26, v42);
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9EC, v31, v32);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9E2, v33, v34);
  return v26;
}

```

## disassembly

```asm
0x1400056f4  mov     [rsp-8+arg_10], rbx
0x1400056f9  push    rbp
0x1400056fa  push    rsi
0x1400056fb  push    rdi
0x1400056fc  push    r14
0x1400056fe  push    r15
0x140005700  lea     rbp, [rsp-160h]
0x140005708  sub     rsp, 260h
0x14000570f  mov     rax, cs:__security_cookie
0x140005716  xor     rax, rsp
0x140005719  mov     [rbp+180h+var_30], rax
0x140005720  mov     r15, rdx
0x140005723  mov     qword ptr [rdx], 0
0x14000572a  mov     rbx, rcx
0x14000572d  call    cs:__imp_GetCurrentProcessId
0x140005734  nop     dword ptr [rax+rax+00h]
0x140005739  mov     esi, 130h
0x14000573e  mov     [rsp+280h+var_258], rbx
0x140005743  mov     r9d, eax
0x140005746  mov     [rsp+280h+var_260], esi; int
0x14000574a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140005751  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140005756  lea     edx, [rsi-2Ch]; unsigned __int64
0x140005759  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000575e  mov     r9d, 1F0001h; dwDesiredAccess
0x140005764  mov     [rsp+280h+hHandle], 0
0x14000576d  xor     r8d, r8d; dwFlags
0x140005770  lea     rdx, [rsp+280h+Name]; lpName
0x140005775  xor     ecx, ecx; lpMutexAttributes
0x140005777  call    cs:__imp_CreateMutexExW
0x14000577e  nop     dword ptr [rax+rax+00h]
0x140005783  mov     rdx, rax
0x140005786  lea     rcx, [rsp+280h+hHandle]
0x14000578b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140005790  mov     rbx, [rsp+280h+hHandle]
0x140005795  test    rbx, rbx
0x140005798  jnz     short loc_1400057A4
0x14000579a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000579f  jmp     loc_140005A2A
0x1400057a4  xor     r8d, r8d; bAlertable
0x1400057a7  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1400057aa  mov     rcx, rbx; hHandle
0x1400057ad  call    cs:__imp_WaitForSingleObjectEx
0x1400057b4  nop     dword ptr [rax+rax+00h]
0x1400057b9  cmp     eax, 102h
0x1400057be  jz      short loc_1400057D0
0x1400057c0  test    eax, 0FFFFFF7Fh
0x1400057c5  jnz     loc_140005A63
0x1400057cb  mov     r14, rbx
0x1400057ce  jmp     short loc_1400057D3
0x1400057d0  xor     r14d, r14d
0x1400057d3  lea     r8, [rsp+280h+hHandle]; unsigned __int64 *
0x1400057d8  mov     [rsp+280h+hHandle], 0
0x1400057e1  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1400057e6  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1400057eb  mov     edi, eax
0x1400057ed  test    eax, eax
0x1400057ef  jns     short loc_140005867
0x1400057f1  mov     rcx, [rbp+188h]; this
0x1400057f8  mov     r9d, eax; char *
0x1400057fb  mov     edx, 64h ; 'd'; void *
0x140005800  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005805  mov     rcx, [rbp+188h]; this
0x14000580c  mov     r9d, edi; char *
0x14000580f  mov     edx, 6Dh ; 'm'; void *
0x140005814  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005819  mov     rcx, [rbp+188h]; this
0x140005820  mov     r9d, edi; char *
0x140005823  mov     edx, 12Bh; void *
0x140005828  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000582d  test    r14, r14
0x140005830  jz      short loc_140005849
0x140005832  mov     rcx, r14; hMutex
0x140005835  call    cs:__imp_ReleaseMutex
0x14000583c  nop     dword ptr [rax+rax+00h]
0x140005841  test    eax, eax
0x140005843  jz      loc_140005A70
0x140005849  mov     rcx, rbx; hObject
0x14000584c  call    cs:__imp_CloseHandle
0x140005853  nop     dword ptr [rax+rax+00h]
0x140005858  test    eax, eax
0x14000585a  jz      loc_140005A82
0x140005860  mov     eax, edi
0x140005862  jmp     loc_140005A2A
0x140005867  mov     rax, [rsp+280h+hHandle]
0x14000586c  lea     rcx, ds:0[rax*4]
0x140005874  test    rcx, rcx
0x140005877  jz      short loc_140005887
0x140005879  mov     [r15], rcx
0x14000587c  mov     eax, [rcx]
0x14000587e  inc     eax
0x140005880  mov     [rcx], eax
0x140005882  jmp     loc_1400059F4
0x140005887  mov     rdx, rsi; dwBytes
0x14000588a  mov     qword ptr [r15], 0
0x140005891  mov     ecx, 8; dwFlags
0x140005896  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000589b  mov     rdi, rax
0x14000589e  test    rax, rax
0x1400058a1  jnz     short loc_1400058BE
0x1400058a3  mov     rcx, [rbp+188h]; this
0x1400058aa  mov     esi, 8007000Eh
0x1400058af  mov     r9d, esi; char *
0x1400058b2  mov     edx, 148h; void *
0x1400058b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400058bc  jmp     short loc_140005921
0x1400058be  xorps   xmm0, xmm0
0x1400058c1  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1400058c6  mov     r8, rdi; void *
0x1400058c9  lea     rcx, [rsp+280h+hHandle]; this
0x1400058ce  movdqu  xmmword ptr [rsp+280h+hHandle], xmm0
0x1400058d4  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x1400058d9  mov     esi, eax
0x1400058db  test    eax, eax
0x1400058dd  jns     loc_140005974
0x1400058e3  mov     rcx, [rbp+188h]; this
0x1400058ea  mov     r9d, eax; char *
0x1400058ed  mov     edx, 14Bh; void *
0x1400058f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400058f7  lea     rcx, [rsp+280h+hHandle]; this
0x1400058fc  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x140005901  call    cs:__imp_GetProcessHeap
0x140005908  nop     dword ptr [rax+rax+00h]
0x14000590d  mov     r8, rdi; lpMem
0x140005910  xor     edx, edx; dwFlags
0x140005912  mov     rcx, rax; hHeap
0x140005915  call    cs:__imp_HeapFree
0x14000591c  nop     dword ptr [rax+rax+00h]
0x140005921  mov     rcx, [rbp+188h]; this
0x140005928  mov     r9d, esi; char *
0x14000592b  mov     edx, 134h; void *
0x140005930  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005935  test    r14, r14
0x140005938  jz      short loc_140005951
0x14000593a  mov     rcx, r14; hMutex
0x14000593d  call    cs:__imp_ReleaseMutex
0x140005944  nop     dword ptr [rax+rax+00h]
0x140005949  test    eax, eax
0x14000594b  jz      loc_140005A94
0x140005951  test    rbx, rbx
0x140005954  jz      short loc_14000596D
0x140005956  mov     rcx, rbx; hObject
0x140005959  call    cs:__imp_CloseHandle
0x140005960  nop     dword ptr [rax+rax+00h]
0x140005965  test    eax, eax
0x140005967  jz      loc_140005AA6
0x14000596d  mov     eax, esi
0x14000596f  jmp     loc_140005A2A
0x140005974  mov     rax, [rsp+280h+hHandle]
0x140005979  lea     rcx, [rdi+28h]; void *
0x14000597d  mov     [rdi+10h], rax
0x140005981  xor     edx, edx; Val
0x140005983  mov     rax, [rsp+280h+hHandle+8]
0x140005988  mov     r8d, 108h; Size
0x14000598e  mov     [rdi+8], rbx
0x140005992  xor     ebx, ebx
0x140005994  mov     [rdi+18h], rax
0x140005998  mov     dword ptr [rdi], 1
0x14000599e  mov     [rsp+280h+hHandle], rbx
0x1400059a3  mov     [rsp+280h+hHandle+8], rbx
0x1400059a8  call    memset_0
0x1400059ad  xor     eax, eax
0x1400059af  lea     rcx, [rdi+28h]; this
0x1400059b3  mov     [rdi+20h], rax
0x1400059b7  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1400059bc  lea     rsi, [rdi+0E8h]
0x1400059c3  xor     r8d, r8d; Flags
0x1400059c6  mov     rcx, rsi; lpCriticalSection
0x1400059c9  xor     edx, edx; dwSpinCount
0x1400059cb  call    cs:__imp_InitializeCriticalSectionEx
0x1400059d2  nop     dword ptr [rax+rax+00h]
0x1400059d7  mov     [rsi+28h], rbx
0x1400059db  lea     rcx, [rsp+280h+hHandle]; this
0x1400059e0  mov     [rsi+30h], rbx
0x1400059e4  mov     [rsi+38h], rbx
0x1400059e8  mov     [rsi+40h], rbx
0x1400059ec  mov     [r15], rdi
0x1400059ef  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x1400059f4  test    r14, r14
0x1400059f7  jz      short loc_140005A10
0x1400059f9  mov     rcx, r14; hMutex
0x1400059fc  call    cs:__imp_ReleaseMutex
0x140005a03  nop     dword ptr [rax+rax+00h]
0x140005a08  test    eax, eax
0x140005a0a  jz      loc_140005AB8
0x140005a10  test    rbx, rbx
0x140005a13  jz      short loc_140005A28
0x140005a15  mov     rcx, rbx; hObject
0x140005a18  call    cs:__imp_CloseHandle
0x140005a1f  nop     dword ptr [rax+rax+00h]
0x140005a24  test    eax, eax
0x140005a26  jz      short loc_140005A51
0x140005a28  xor     eax, eax
0x140005a2a  mov     rcx, [rbp+180h+var_30]
0x140005a31  xor     rcx, rsp; StackCookie
0x140005a34  call    __security_check_cookie
0x140005a39  mov     rbx, [rsp+280h+arg_10]
0x140005a41  add     rsp, 260h
0x140005a48  pop     r15
0x140005a4a  pop     r14
0x140005a4c  pop     rdi
0x140005a4d  pop     rsi
0x140005a4e  pop     rbp
0x140005a4f  retn
0x140005a51  mov     rcx, [rbp+188h]; this
0x140005a58  mov     edx, 9E2h; void *
0x140005a5d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005a63  mov     rcx, [rbp+188h]; this
0x140005a6a  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x140005a70  mov     rcx, [rbp+188h]; this
0x140005a77  mov     edx, 9ECh; void *
0x140005a7c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005a82  mov     rcx, [rbp+188h]; this
0x140005a89  mov     edx, 9E2h; void *
0x140005a8e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005a94  mov     rcx, [rbp+188h]; this
0x140005a9b  mov     edx, 9ECh; void *
0x140005aa0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005aa6  mov     rcx, [rbp+188h]; this
0x140005aad  mov     edx, 9E2h; void *
0x140005ab2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005ab8  mov     rcx, [rbp+188h]; this
0x140005abf  mov     edx, 9ECh; void *
0x140005ac4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
