# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x14006c8f4`
- end: `0x14006ccc6`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `978`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x14006d07c`

## callees

- `0x140002c73`
- `0x140004be4`
- `0x14006bd54`
- `0x14006c234`
- `0x14006c8f4`
- `0x14006ce4c`
- `0x14006d1f8`
- `0x14006da90`
- `0x14006ea30`
- `0x14006fdf4`
- `0x140070cac`
- `0x1400714b0`
- `0x140086ec0`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x14006c971`
- `KERNEL32!CreateMutexExW` at `0x14006c971`
- `KERNEL32!WaitForSingleObjectEx` at `0x14006c998`
- `KERNEL32!WaitForSingleObjectEx` at `0x14006c998`
- `KERNEL32!ReleaseMutex` at `0x14006ca1f`
- `KERNEL32!ReleaseMutex` at `0x14006cb27`
- `KERNEL32!ReleaseMutex` at `0x14006cbf8`
- `KERNEL32!ReleaseMutex` at `0x14006ca1f`
- `KERNEL32!ReleaseMutex` at `0x14006cb27`
- `KERNEL32!ReleaseMutex` at `0x14006cbf8`
- `KERNEL32!GetCurrentProcessId` at `0x14006c92d`
- `KERNEL32!GetCurrentProcessId` at `0x14006c92d`
- `KERNEL32!InitializeCriticalSectionEx` at `0x14006cbb5`
- `KERNEL32!InitializeCriticalSectionEx` at `0x14006cbb5`
- `KERNEL32!GetProcessHeap` at `0x14006caeb`
- `KERNEL32!GetProcessHeap` at `0x14006caeb`
- `KERNEL32!CloseHandle` at `0x14006ca36`
- `KERNEL32!CloseHandle` at `0x14006cb3e`
- `KERNEL32!CloseHandle` at `0x14006cc14`
- `KERNEL32!CloseHandle` at `0x14006ca36`
- `KERNEL32!CloseHandle` at `0x14006cb3e`
- `KERNEL32!CloseHandle` at `0x14006cc14`
- `KERNEL32!HeapFree` at `0x14006caff`
- `KERNEL32!HeapFree` at `0x14006caff`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // rbx
  DWORD v8; // eax
  void *v9; // rdx
  unsigned int v10; // r8d
  char *v11; // r9
  void *v12; // rdi
  int ValueInternal; // eax
  unsigned __int64 v14; // r8
  unsigned int v15; // esi
  unsigned int v16; // r8d
  unsigned int v17; // r8d
  unsigned int v18; // r8d
  const char *v19; // r9
  unsigned int v20; // r8d
  const char *v21; // r9
  _DWORD *v22; // rcx
  _DWORD *v23; // rax
  unsigned int v24; // r8d
  _DWORD *v25; // r14
  unsigned int v26; // r8d
  int v27; // eax
  unsigned int v28; // r8d
  HANDLE ProcessHeap; // rax
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  unsigned int v34; // r8d
  const char *v35; // r9
  unsigned int v36; // r8d
  const char *v37; // r9
  int v38; // [rsp+20h] [rbp-E0h]
  int v39; // [rsp+20h] [rbp-E0h]
  int v40; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v41[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  v6 = Mutex;
  if ( !Mutex )
    return wil::details::GetLastErrorFailHr(v5);
  v8 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
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
  v41[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, v41, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v14, (const char *)(unsigned int)ValueInternal, 304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v16, (const char *)v15, v38);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v17, (const char *)v15, v39);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v18, v19);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v20, v21);
    return v15;
  }
  v22 = (_DWORD *)(4 * v41[0]);
  if ( 4 * v41[0] )
  {
    *a2 = v22;
    ++*v22;
    goto LABEL_23;
  }
  *a2 = 0;
  v23 = wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v25 = v23;
  if ( !v23 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v24, (const char *)0x8007000ELL, 304);
    goto LABEL_18;
  }
  *(_OWORD *)v41 = 0;
  v27 = wil::details_abi::SemaphoreValue::CreateFromPointer((wil::details_abi::SemaphoreValue *)v41, Name, v23);
  v15 = v27;
  if ( v27 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v28, (const char *)(unsigned int)v27, 304);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v41);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v25);
LABEL_18:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v26, (const char *)v15, v40);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v30, v31);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    return v15;
  }
  *((_QWORD *)v25 + 2) = v41[0];
  *((_QWORD *)v25 + 3) = v41[1];
  *v25 = 1;
  *((_QWORD *)v25 + 1) = v6;
  v41[0] = 0;
  v41[1] = 0;
  memset_0(v25 + 10, 0, 0x108u);
  *((_QWORD *)v25 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v25 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v25 + 58), 0, 0);
  *((_QWORD *)v25 + 34) = 0;
  *((_QWORD *)v25 + 35) = 0;
  *((_QWORD *)v25 + 36) = 0;
  *((_QWORD *)v25 + 37) = 0;
  *a2 = v25;
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v41);
  v6 = 0;
LABEL_23:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v34, v35);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v36, v37);
  return 0;
}

```

## disassembly

```asm
0x14006c8f4  mov     [rsp-8+arg_10], rbx
0x14006c8f9  push    rbp
0x14006c8fa  push    rsi
0x14006c8fb  push    rdi
0x14006c8fc  push    r14
0x14006c8fe  push    r15
0x14006c900  lea     rbp, [rsp-160h]
0x14006c908  sub     rsp, 260h
0x14006c90f  mov     rax, cs:__security_cookie
0x14006c916  xor     rax, rsp
0x14006c919  mov     [rbp+180h+var_30], rax
0x14006c920  mov     r15, rdx
0x14006c923  mov     qword ptr [rdx], 0
0x14006c92a  mov     rbx, rcx
0x14006c92d  call    cs:__imp_GetCurrentProcessId
0x14006c934  nop     dword ptr [rax+rax+00h]
0x14006c939  mov     r14d, 130h
0x14006c93f  mov     [rsp+280h+var_258], rbx
0x14006c944  mov     r9d, eax
0x14006c947  mov     [rsp+280h+var_260], r14d; int
0x14006c94c  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x14006c953  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14006c958  lea     edx, [r14-2Ch]; unsigned __int64
0x14006c95c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14006c961  mov     r9d, 1F0001h; dwDesiredAccess
0x14006c967  lea     rdx, [rsp+280h+Name]; lpName
0x14006c96c  xor     r8d, r8d; dwFlags
0x14006c96f  xor     ecx, ecx; lpMutexAttributes
0x14006c971  call    cs:__imp_CreateMutexExW
0x14006c978  nop     dword ptr [rax+rax+00h]
0x14006c97d  mov     rbx, rax
0x14006c980  test    rax, rax
0x14006c983  jnz     short loc_14006C98F
0x14006c985  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14006c98a  jmp     loc_14006CC26
0x14006c98f  xor     r8d, r8d; bAlertable
0x14006c992  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14006c995  mov     rcx, rbx; hHandle
0x14006c998  call    cs:__imp_WaitForSingleObjectEx
0x14006c99f  nop     dword ptr [rax+rax+00h]
0x14006c9a4  cmp     eax, 102h
0x14006c9a9  jz      short loc_14006C9BB
0x14006c9ab  test    eax, 0FFFFFF7Fh
0x14006c9b0  jnz     loc_14006CC71
0x14006c9b6  mov     rdi, rbx
0x14006c9b9  jmp     short loc_14006C9BD
0x14006c9bb  xor     edi, edi
0x14006c9bd  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x14006c9c2  mov     [rsp+280h+var_250], 0
0x14006c9cb  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14006c9d0  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x14006c9d5  mov     esi, eax
0x14006c9d7  test    eax, eax
0x14006c9d9  jns     short loc_14006CA51
0x14006c9db  mov     rcx, [rbp+188h]; this
0x14006c9e2  mov     r9d, eax; char *
0x14006c9e5  mov     edx, 66h ; 'f'; void *
0x14006c9ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14006c9ef  mov     rcx, [rbp+188h]; this
0x14006c9f6  mov     r9d, esi; char *
0x14006c9f9  mov     edx, 6Fh ; 'o'; void *
0x14006c9fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14006ca03  mov     rcx, [rbp+188h]; this
0x14006ca0a  mov     r9d, esi; char *
0x14006ca0d  mov     edx, 12Eh; void *
0x14006ca12  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14006ca17  test    rdi, rdi
0x14006ca1a  jz      short loc_14006CA33
0x14006ca1c  mov     rcx, rdi; hMutex
0x14006ca1f  call    cs:__imp_ReleaseMutex
0x14006ca26  nop     dword ptr [rax+rax+00h]
0x14006ca2b  test    eax, eax
0x14006ca2d  jz      loc_14006CC7E
0x14006ca33  mov     rcx, rbx; hObject
0x14006ca36  call    cs:__imp_CloseHandle
0x14006ca3d  nop     dword ptr [rax+rax+00h]
0x14006ca42  test    eax, eax
0x14006ca44  jz      loc_14006CC90
0x14006ca4a  mov     eax, esi
0x14006ca4c  jmp     loc_14006CC26
0x14006ca51  mov     rax, [rsp+280h+var_250]
0x14006ca56  lea     rcx, ds:0[rax*4]
0x14006ca5e  test    rcx, rcx
0x14006ca61  jz      short loc_14006CA71
0x14006ca63  mov     [r15], rcx
0x14006ca66  mov     eax, [rcx]
0x14006ca68  inc     eax
0x14006ca6a  mov     [rcx], eax
0x14006ca6c  jmp     loc_14006CBF0
0x14006ca71  mov     rdx, r14; dwBytes
0x14006ca74  mov     qword ptr [r15], 0
0x14006ca7b  mov     ecx, 8; dwFlags
0x14006ca80  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14006ca85  mov     r14, rax
0x14006ca88  test    rax, rax
0x14006ca8b  jnz     short loc_14006CAA8
0x14006ca8d  mov     rcx, [rbp+188h]; this
0x14006ca94  mov     esi, 8007000Eh
0x14006ca99  mov     r9d, esi; char *
0x14006ca9c  mov     edx, 14Bh; void *
0x14006caa1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14006caa6  jmp     short loc_14006CB0B
0x14006caa8  xorps   xmm0, xmm0
0x14006caab  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x14006cab0  mov     r8, r14; void *
0x14006cab3  lea     rcx, [rsp+280h+var_250]; this
0x14006cab8  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x14006cabe  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x14006cac3  mov     esi, eax
0x14006cac5  test    eax, eax
0x14006cac7  jns     loc_14006CB57
0x14006cacd  mov     rcx, [rbp+188h]; this
0x14006cad4  mov     r9d, eax; char *
0x14006cad7  mov     edx, 14Eh; void *
0x14006cadc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14006cae1  lea     rcx, [rsp+280h+var_250]; this
0x14006cae6  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x14006caeb  call    cs:__imp_GetProcessHeap
0x14006caf2  nop     dword ptr [rax+rax+00h]
0x14006caf7  mov     r8, r14; lpMem
0x14006cafa  xor     edx, edx; dwFlags
0x14006cafc  mov     rcx, rax; hHeap
0x14006caff  call    cs:__imp_HeapFree
0x14006cb06  nop     dword ptr [rax+rax+00h]
0x14006cb0b  mov     rcx, [rbp+188h]; this
0x14006cb12  mov     r9d, esi; char *
0x14006cb15  mov     edx, 137h; void *
0x14006cb1a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14006cb1f  test    rdi, rdi
0x14006cb22  jz      short loc_14006CB3B
0x14006cb24  mov     rcx, rdi; hMutex
0x14006cb27  call    cs:__imp_ReleaseMutex
0x14006cb2e  nop     dword ptr [rax+rax+00h]
0x14006cb33  test    eax, eax
0x14006cb35  jz      loc_14006CCA2
0x14006cb3b  mov     rcx, rbx; hObject
0x14006cb3e  call    cs:__imp_CloseHandle
0x14006cb45  nop     dword ptr [rax+rax+00h]
0x14006cb4a  test    eax, eax
0x14006cb4c  jz      loc_14006CC5F
0x14006cb52  jmp     loc_14006CA4A
0x14006cb57  mov     rax, [rsp+280h+var_250]
0x14006cb5c  lea     rcx, [r14+28h]; void *
0x14006cb60  mov     [r14+10h], rax
0x14006cb64  xor     edx, edx; Val
0x14006cb66  mov     rax, [rsp+280h+var_250+8]
0x14006cb6b  mov     r8d, 108h; Size
0x14006cb71  mov     [r14+18h], rax
0x14006cb75  mov     dword ptr [r14], 1
0x14006cb7c  mov     [r14+8], rbx
0x14006cb80  mov     [rsp+280h+var_250], 0
0x14006cb89  mov     [rsp+280h+var_250+8], 0
0x14006cb92  call    memset_0
0x14006cb97  xor     eax, eax
0x14006cb99  lea     rcx, [r14+28h]; this
0x14006cb9d  mov     [r14+20h], rax
0x14006cba1  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x14006cba6  lea     rbx, [r14+0E8h]
0x14006cbad  xor     r8d, r8d; Flags
0x14006cbb0  mov     rcx, rbx; lpCriticalSection
0x14006cbb3  xor     edx, edx; dwSpinCount
0x14006cbb5  call    cs:__imp_InitializeCriticalSectionEx
0x14006cbbc  nop     dword ptr [rax+rax+00h]
0x14006cbc1  mov     qword ptr [rbx+28h], 0
0x14006cbc9  lea     rcx, [rsp+280h+var_250]; this
0x14006cbce  mov     qword ptr [rbx+30h], 0
0x14006cbd6  mov     qword ptr [rbx+38h], 0
0x14006cbde  mov     qword ptr [rbx+40h], 0
0x14006cbe6  mov     [r15], r14
0x14006cbe9  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x14006cbee  xor     ebx, ebx
0x14006cbf0  test    rdi, rdi
0x14006cbf3  jz      short loc_14006CC0C
0x14006cbf5  mov     rcx, rdi; hMutex
0x14006cbf8  call    cs:__imp_ReleaseMutex
0x14006cbff  nop     dword ptr [rax+rax+00h]
0x14006cc04  test    eax, eax
0x14006cc06  jz      loc_14006CCB4
0x14006cc0c  test    rbx, rbx
0x14006cc0f  jz      short loc_14006CC24
0x14006cc11  mov     rcx, rbx; hObject
0x14006cc14  call    cs:__imp_CloseHandle
0x14006cc1b  nop     dword ptr [rax+rax+00h]
0x14006cc20  test    eax, eax
0x14006cc22  jz      short loc_14006CC4D
0x14006cc24  xor     eax, eax
0x14006cc26  mov     rcx, [rbp+180h+var_30]
0x14006cc2d  xor     rcx, rsp; StackCookie
0x14006cc30  call    __security_check_cookie
0x14006cc35  mov     rbx, [rsp+280h+arg_10]
0x14006cc3d  add     rsp, 260h
0x14006cc44  pop     r15
0x14006cc46  pop     r14
0x14006cc48  pop     rdi
0x14006cc49  pop     rsi
0x14006cc4a  pop     rbp
0x14006cc4b  retn
0x14006cc4d  mov     rcx, [rbp+188h]; this
0x14006cc54  mov     edx, 0A0Bh; void *
0x14006cc59  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14006cc5f  mov     rcx, [rbp+188h]; this
0x14006cc66  mov     edx, 0A0Bh; void *
0x14006cc6b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14006cc71  mov     rcx, [rbp+188h]; this
0x14006cc78  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x14006cc7e  mov     rcx, [rbp+188h]; this
0x14006cc85  mov     edx, 0A15h; void *
0x14006cc8a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14006cc90  mov     rcx, [rbp+188h]; this
0x14006cc97  mov     edx, 0A0Bh; void *
0x14006cc9c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14006cca2  mov     rcx, [rbp+188h]; this
0x14006cca9  mov     edx, 0A15h; void *
0x14006ccae  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14006ccb4  mov     rcx, [rbp+188h]; this
0x14006ccbb  mov     edx, 0A15h; void *
0x14006ccc0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
