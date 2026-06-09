# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140003c20`
- end: `0x1400040b5`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1173`
- prototype: `__int64 __fastcall(char *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x140004ce4`

## callees

- `0x140001460`
- `0x140001f5c`
- `0x1400036f0`
- `0x140003c20`
- `0x1400040e4`
- `0x140004380`
- `0x1400049c4`
- `0x140005f30`
- `0x1400063f0`
- `0x140006f24`
- `0x140007104`
- `0x1400076dc`
- `0x1400076ec`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140003ea7`
- `KERNEL32!HeapFree` at `0x140003ea7`
- `KERNEL32!GetProcessHeap` at `0x140003e99`
- `KERNEL32!GetProcessHeap` at `0x140003e99`
- `KERNEL32!GetCurrentProcessId` at `0x140003c59`
- `KERNEL32!GetCurrentProcessId` at `0x140003c59`
- `KERNEL32!CreateMutexExW` at `0x140003c98`
- `KERNEL32!CreateMutexExW` at `0x140003c98`
- `KERNEL32!CloseHandle` at `0x140003da0`
- `KERNEL32!CloseHandle` at `0x140003ef6`
- `KERNEL32!CloseHandle` at `0x140003f92`
- `KERNEL32!CloseHandle` at `0x140003da0`
- `KERNEL32!CloseHandle` at `0x140003ef6`
- `KERNEL32!CloseHandle` at `0x140003f92`
- `KERNEL32!WaitForSingleObjectEx` at `0x140003cb9`
- `KERNEL32!WaitForSingleObjectEx` at `0x140003cb9`
- `KERNEL32!ReleaseMutex` at `0x140003d8f`
- `KERNEL32!ReleaseMutex` at `0x140003ee5`
- `KERNEL32!ReleaseMutex` at `0x140003f7c`
- `KERNEL32!ReleaseMutex` at `0x140003d8f`
- `KERNEL32!ReleaseMutex` at `0x140003ee5`
- `KERNEL32!ReleaseMutex` at `0x140003f7c`

## string_xrefs

- `0x140003eb4`: `MakeAndInitialize( name, wistd::move(mutex), data)`
- `0x140003e79`: `semaphoreValue.CreateFromPointer(name, dataAlloc.get())`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        char *a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v6; // rcx
  void *v7; // rbx
  DWORD v9; // eax
  void *v10; // rdx
  unsigned int v11; // r8d
  char *v12; // r9
  void *v13; // rdi
  int ValueInternal; // eax
  unsigned __int64 v15; // r8
  unsigned int v16; // esi
  unsigned int v17; // r8d
  unsigned int v18; // r8d
  _DWORD *v19; // rcx
  unsigned __int64 v20; // rax
  wil::details::in1diag5 *v21; // rcx
  __int64 v22; // r8
  _QWORD *v23; // rsi
  unsigned int v24; // r14d
  int v25; // eax
  HANDLE ProcessHeap; // rax
  unsigned int v27; // r8d
  unsigned int v28; // r8d
  unsigned __int64 v29; // rax
  unsigned int v30; // r8d
  unsigned int v31; // r8d
  char *v32; // [rsp+20h] [rbp-E0h]
  char *v33; // [rsp+28h] [rbp-D8h]
  wil::details *v34; // [rsp+28h] [rbp-D8h]
  wil::details *v35; // [rsp+28h] [rbp-D8h]
  wil::details *v36; // [rsp+28h] [rbp-D8h]
  wil::details *v37; // [rsp+28h] [rbp-D8h]
  wil::details *v38; // [rsp+28h] [rbp-D8h]
  unsigned __int64 v39[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v33 = a1;
  LODWORD(v32) = 120;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  v7 = Mutex;
  if ( !Mutex )
    return wil::details::GetLastErrorFailHr(v6);
  v9 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
  if ( v9 == 258 )
  {
    v13 = 0;
  }
  else
  {
    if ( (v9 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag5::FailFast_Unexpected(retaddr, v10, v11, v12, v32, v33);
    v13 = v7;
  }
  v39[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v10, v39, (bool *)v12);
  v16 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    LODWORD(v33) = ValueInternal;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      "wil::details_abi::SemaphoreValue::TryGetValue",
      "TryGetValueInternal(name, (sizeof(T) > sizeof(unsigned long)), &value64, retrieved)",
      (wil::details *)v33,
      v39[0]);
    LODWORD(v34) = v16;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x6F,
      (unsigned int)"wil",
      "wil::details_abi::SemaphoreValue::TryGetPointer",
      "TryGetValue(name, &value)",
      v34,
      v39[0]);
    LODWORD(v35) = v16;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x12E,
      (unsigned int)"wil",
      "wil::details_abi::ProcessLocalStorageData<struct wil::details_abi::ProcessLocalData>::Acquire",
      "SemaphoreValue::TryGetPointer(name, &pointer)",
      v35,
      v39[0]);
    if ( v13 && !ReleaseMutex(v13) )
      wil::details::in1diag5::_FailFast_GetLastError(
        retaddr,
        (void *)0xA15,
        v17,
        "wil::details::ReleaseMutex",
        "::ReleaseMutex(mutex)",
        (const char *)v36);
    if ( !CloseHandle(v7) )
      wil::details::in1diag5::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        v18,
        "wil::details::CloseHandle",
        "::CloseHandle(handle)",
        (const char *)v36);
    return v16;
  }
  v19 = (_DWORD *)(4 * v39[0]);
  if ( 4 * v39[0] )
  {
    *a2 = v19;
    ++*v19;
    goto LABEL_24;
  }
  *a2 = 0;
  v20 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v15);
  v23 = (_QWORD *)v20;
  if ( v20 )
  {
    *(_OWORD *)v39 = 0;
    if ( (v20 & 3) != 0 )
      wil::details::in1diag5::_FailFastImmediate_Unexpected(v21);
    v25 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)v39,
            Name,
            v22,
            v20 >> 2);
    v24 = v25;
    if ( v25 >= 0 )
    {
      v23[2] = v39[0];
      v29 = v39[1];
      *(_DWORD *)v23 = 1;
      v23[1] = v7;
      v39[0] = 0;
      v23[3] = v29;
      v39[1] = 0;
      memset_0((char *)v23 + 34, 0, 0x56u);
      *((_WORD *)v23 + 16) = 88;
      *((_DWORD *)v23 + 9) = 1;
      memset_0(v23 + 5, 0, 0x50u);
      *a2 = v23;
      wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v39);
      v7 = 0;
LABEL_24:
      if ( v13 && !ReleaseMutex(v13) )
        wil::details::in1diag5::_FailFast_GetLastError(
          retaddr,
          (void *)0xA15,
          v30,
          "wil::details::ReleaseMutex",
          "::ReleaseMutex(mutex)",
          v33);
      if ( v7 && !CloseHandle(v7) )
        wil::details::in1diag5::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          v31,
          "wil::details::CloseHandle",
          "::CloseHandle(handle)",
          v33);
      return 0;
    }
    LODWORD(v33) = v25;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x14E,
      (unsigned int)"wil",
      "wil::details_abi::ProcessLocalStorageData<struct wil::details_abi::ProcessLocalData>::MakeAndInitialize",
      "semaphoreValue.CreateFromPointer(name, dataAlloc.get())",
      (wil::details *)v33,
      v39[0]);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v39);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v23);
  }
  else
  {
    v24 = -2147024882;
    LODWORD(v33) = -2147024882;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x14B,
      (unsigned int)"wil",
      "wil::details_abi::ProcessLocalStorageData<struct wil::details_abi::ProcessLocalData>::MakeAndInitialize",
      "dataAlloc",
      (wil::details *)v33,
      v39[0]);
  }
  LODWORD(v37) = v24;
  wil::details::in1diag5::Return_Hr(
    retaddr,
    (void *)0x137,
    (unsigned int)"wil",
    "wil::details_abi::ProcessLocalStorageData<struct wil::details_abi::ProcessLocalData>::Acquire",
    "MakeAndInitialize( name, wistd::move(mutex), data)",
    v37,
    v39[0]);
  if ( v13 && !ReleaseMutex(v13) )
    wil::details::in1diag5::_FailFast_GetLastError(
      retaddr,
      (void *)0xA15,
      v27,
      "wil::details::ReleaseMutex",
      "::ReleaseMutex(mutex)",
      (const char *)v38);
  if ( !CloseHandle(v7) )
    wil::details::in1diag5::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      v28,
      "wil::details::CloseHandle",
      "::CloseHandle(handle)",
      (const char *)v38);
  return v24;
}

```

## disassembly

```asm
0x140003c20  mov     [rsp-8+arg_10], rbx
0x140003c25  push    rbp
0x140003c26  push    rsi
0x140003c27  push    rdi
0x140003c28  push    r14
0x140003c2a  push    r15
0x140003c2c  lea     rbp, [rsp-160h]
0x140003c34  sub     rsp, 260h
0x140003c3b  mov     rax, cs:__security_cookie
0x140003c42  xor     rax, rsp
0x140003c45  mov     [rbp+180h+var_30], rax
0x140003c4c  mov     r15, rdx
0x140003c4f  mov     qword ptr [rdx], 0
0x140003c56  mov     rbx, rcx
0x140003c59  call    cs:__imp_GetCurrentProcessId
0x140003c5f  mov     r14d, 78h ; 'x'
0x140003c65  mov     [rsp+280h+var_258], rbx; char *
0x140003c6a  mov     r9d, eax
0x140003c6d  mov     dword ptr [rsp+280h+var_260], r14d; char *
0x140003c72  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140003c79  mov     edx, 104h; unsigned __int64
0x140003c7e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140003c83  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140003c88  mov     r9d, 1F0001h; dwDesiredAccess
0x140003c8e  lea     rdx, [rsp+280h+Name]; lpName
0x140003c93  xor     r8d, r8d; dwFlags
0x140003c96  xor     ecx, ecx; lpMutexAttributes
0x140003c98  call    cs:__imp_CreateMutexExW
0x140003c9e  mov     rbx, rax
0x140003ca1  test    rax, rax
0x140003ca4  jnz     short loc_140003CB0
0x140003ca6  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140003cab  jmp     loc_140003F9E
0x140003cb0  xor     r8d, r8d; bAlertable
0x140003cb3  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140003cb6  mov     rcx, rbx; hHandle
0x140003cb9  call    cs:__imp_WaitForSingleObjectEx
0x140003cbf  cmp     eax, 102h
0x140003cc4  jz      short loc_140003CD6
0x140003cc6  test    eax, 0FFFFFF7Fh
0x140003ccb  jnz     loc_140003FE9
0x140003cd1  mov     rdi, rbx
0x140003cd4  jmp     short loc_140003CD8
0x140003cd6  xor     edi, edi
0x140003cd8  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x140003cdd  mov     [rsp+280h+var_250], 0; int
0x140003ce6  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140003ceb  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x140003cf0  mov     esi, eax
0x140003cf2  test    eax, eax
0x140003cf4  jns     loc_140003DB5
0x140003cfa  mov     rcx, [rbp+188h]; this
0x140003d01  lea     r9, aWilDetailsAbiS_0; "wil::details_abi::SemaphoreValue::TryGe"...
0x140003d08  mov     dword ptr [rsp+280h+var_258], eax; wil::details *
0x140003d0c  lea     r8, aWil; "wil"
0x140003d13  lea     rax, aTrygetvalueint; "TryGetValueInternal(name, (sizeof(T) > "...
0x140003d1a  mov     edx, 66h ; 'f'; void *
0x140003d1f  mov     [rsp+280h+var_260], rax; char *
0x140003d24  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x140003d29  mov     rcx, [rbp+188h]; this
0x140003d30  lea     rax, aTrygetvalueNam; "TryGetValue(name, &value)"
0x140003d37  mov     dword ptr [rsp+280h+var_258], esi; wil::details *
0x140003d3b  lea     r9, aWilDetailsAbiS; "wil::details_abi::SemaphoreValue::TryGe"...
0x140003d42  lea     r8, aWil; "wil"
0x140003d49  mov     [rsp+280h+var_260], rax; char *
0x140003d4e  mov     edx, 6Fh ; 'o'; void *
0x140003d53  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x140003d58  mov     rcx, [rbp+188h]; this
0x140003d5f  lea     rax, aSemaphorevalue_0; "SemaphoreValue::TryGetPointer(name, &po"...
0x140003d66  mov     dword ptr [rsp+280h+var_258], esi; char *
0x140003d6a  lea     r9, aWilDetailsAbiP; "wil::details_abi::ProcessLocalStorageDa"...
0x140003d71  lea     r8, aWil; "wil"
0x140003d78  mov     [rsp+280h+var_260], rax; char *
0x140003d7d  mov     edx, 12Eh; void *
0x140003d82  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x140003d87  test    rdi, rdi
0x140003d8a  jz      short loc_140003D9D
0x140003d8c  mov     rcx, rdi; hMutex
0x140003d8f  call    cs:__imp_ReleaseMutex
0x140003d95  test    eax, eax
0x140003d97  jz      loc_140003FF6
0x140003d9d  mov     rcx, rbx; hObject
0x140003da0  call    cs:__imp_CloseHandle
0x140003da6  test    eax, eax
0x140003da8  jz      loc_14000401B
0x140003dae  mov     eax, esi
0x140003db0  jmp     loc_140003F9E
0x140003db5  mov     rax, [rsp+280h+var_250]
0x140003dba  lea     rcx, ds:0[rax*4]
0x140003dc2  test    rcx, rcx
0x140003dc5  jz      short loc_140003DD5
0x140003dc7  mov     [r15], rcx
0x140003dca  mov     eax, [rcx]
0x140003dcc  inc     eax
0x140003dce  mov     [rcx], eax
0x140003dd0  jmp     loc_140003F74
0x140003dd5  mov     rdx, r14; dwBytes
0x140003dd8  mov     qword ptr [r15], 0
0x140003ddf  mov     ecx, 8; dwFlags
0x140003de4  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140003de9  mov     rsi, rax
0x140003dec  test    rax, rax
0x140003def  jnz     short loc_140003E2C
0x140003df1  mov     rcx, [rbp+188h]; this
0x140003df8  lea     rax, aDataalloc; "dataAlloc"
0x140003dff  mov     r14d, 8007000Eh
0x140003e05  lea     r9, aWilDetailsAbiP_0; "wil::details_abi::ProcessLocalStorageDa"...
0x140003e0c  mov     dword ptr [rsp+280h+var_258], r14d; wil::details *
0x140003e11  lea     r8, aWil; "wil"
0x140003e18  mov     edx, 14Bh; void *
0x140003e1d  mov     [rsp+280h+var_260], rax; char *
0x140003e22  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x140003e27  jmp     loc_140003EAD
0x140003e2c  xorps   xmm0, xmm0
0x140003e2f  movdqu  xmmword ptr [rsp+280h+var_250], xmm0; int
0x140003e35  test    sil, 3
0x140003e39  jnz     loc_140004040
0x140003e3f  mov     r9, rsi
0x140003e42  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x140003e47  shr     r9, 2; unsigned __int64
0x140003e4b  lea     rcx, [rsp+280h+var_250]; this
0x140003e50  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x140003e55  mov     r14d, eax
0x140003e58  test    eax, eax
0x140003e5a  jns     loc_140003F0C
0x140003e60  mov     rcx, [rbp+188h]; this
0x140003e67  lea     r9, aWilDetailsAbiP_0; "wil::details_abi::ProcessLocalStorageDa"...
0x140003e6e  mov     dword ptr [rsp+280h+var_258], eax; wil::details *
0x140003e72  lea     r8, aWil; "wil"
0x140003e79  lea     rax, aSemaphorevalue; "semaphoreValue.CreateFromPointer(name, "...
0x140003e80  mov     edx, 14Eh; void *
0x140003e85  mov     [rsp+280h+var_260], rax; char *
0x140003e8a  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x140003e8f  lea     rcx, [rsp+280h+var_250]; this
0x140003e94  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x140003e99  call    cs:__imp_GetProcessHeap
0x140003e9f  mov     r8, rsi; lpMem
0x140003ea2  xor     edx, edx; dwFlags
0x140003ea4  mov     rcx, rax; hHeap
0x140003ea7  call    cs:__imp_HeapFree
0x140003ead  mov     rcx, [rbp+188h]; this
0x140003eb4  lea     rax, aMakeandinitial; "MakeAndInitialize( name, wistd::move(mu"...
0x140003ebb  mov     dword ptr [rsp+280h+var_258], r14d; char *
0x140003ec0  lea     r9, aWilDetailsAbiP; "wil::details_abi::ProcessLocalStorageDa"...
0x140003ec7  lea     r8, aWil; "wil"
0x140003ece  mov     [rsp+280h+var_260], rax; char *
0x140003ed3  mov     edx, 137h; void *
0x140003ed8  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x140003edd  test    rdi, rdi
0x140003ee0  jz      short loc_140003EF3
0x140003ee2  mov     rcx, rdi; hMutex
0x140003ee5  call    cs:__imp_ReleaseMutex
0x140003eeb  test    eax, eax
0x140003eed  jz      loc_140004046
0x140003ef3  mov     rcx, rbx; hObject
0x140003ef6  call    cs:__imp_CloseHandle
0x140003efc  test    eax, eax
0x140003efe  jz      loc_14000406B
0x140003f04  mov     eax, r14d
0x140003f07  jmp     loc_140003F9E
0x140003f0c  mov     rax, [rsp+280h+var_250]
0x140003f11  lea     rcx, [rsi+22h]; void *
0x140003f15  xor     edx, edx; Val
0x140003f17  mov     [rsi+10h], rax
0x140003f1b  mov     rax, [rsp+280h+var_250+8]
0x140003f20  mov     dword ptr [rsi], 1
0x140003f26  mov     [rsi+8], rbx
0x140003f2a  lea     r8d, [rdx+56h]; Size
0x140003f2e  mov     [rsp+280h+var_250], 0
0x140003f37  mov     [rsi+18h], rax
0x140003f3b  mov     [rsp+280h+var_250+8], 0
0x140003f44  call    memset_0
0x140003f49  xor     edx, edx; Val
0x140003f4b  mov     word ptr [rsi+20h], 58h ; 'X'
0x140003f51  lea     rcx, [rsi+28h]; void *
0x140003f55  mov     dword ptr [rsi+24h], 1
0x140003f5c  lea     r8d, [rdx+50h]; Size
0x140003f60  call    memset_0
0x140003f65  lea     rcx, [rsp+280h+var_250]; this
0x140003f6a  mov     [r15], rsi
0x140003f6d  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x140003f72  xor     ebx, ebx
0x140003f74  test    rdi, rdi
0x140003f77  jz      short loc_140003F8A
0x140003f79  mov     rcx, rdi; hMutex
0x140003f7c  call    cs:__imp_ReleaseMutex
0x140003f82  test    eax, eax
0x140003f84  jz      loc_140004090
0x140003f8a  test    rbx, rbx
0x140003f8d  jz      short loc_140003F9C
0x140003f8f  mov     rcx, rbx; hObject
0x140003f92  call    cs:__imp_CloseHandle
0x140003f98  test    eax, eax
0x140003f9a  jz      short loc_140003FC4
0x140003f9c  xor     eax, eax
0x140003f9e  mov     rcx, [rbp+180h+var_30]
0x140003fa5  xor     rcx, rsp; StackCookie
0x140003fa8  call    __security_check_cookie
0x140003fad  mov     rbx, [rsp+280h+arg_10]
0x140003fb5  add     rsp, 260h
0x140003fbc  pop     r15
0x140003fbe  pop     r14
0x140003fc0  pop     rdi
0x140003fc1  pop     rsi
0x140003fc2  pop     rbp
0x140003fc3  retn
0x140003fc4  mov     rcx, [rbp+188h]; this
0x140003fcb  lea     rax, aClosehandleHan; "::CloseHandle(handle)"
0x140003fd2  lea     r9, aWilDetailsClos; "wil::details::CloseHandle"
0x140003fd9  mov     [rsp+280h+var_260], rax; char *
0x140003fde  mov     edx, 0A0Bh; void *
0x140003fe3  call    ?_FailFast_GetLastError@in1diag5@details@wil@@YAXPEAXIPEBD11@Z; wil::details::in1diag5::_FailFast_GetLastError(void *,uint,char const *,char const *,char const *)
0x140003fe9  mov     rcx, [rbp+188h]; this
0x140003ff0  call    ?FailFast_Unexpected@in1diag5@details@wil@@YAXPEAXIPEBD11@Z; wil::details::in1diag5::FailFast_Unexpected(void *,uint,char const *,char const *,char const *)
0x140003ff6  mov     rcx, [rbp+188h]; this
0x140003ffd  lea     rax, aReleasemutexMu; "::ReleaseMutex(mutex)"
0x140004004  lea     r9, aWilDetailsRele; "wil::details::ReleaseMutex"
0x14000400b  mov     [rsp+280h+var_260], rax; char *
0x140004010  mov     edx, 0A15h; void *
0x140004015  call    ?_FailFast_GetLastError@in1diag5@details@wil@@YAXPEAXIPEBD11@Z; wil::details::in1diag5::_FailFast_GetLastError(void *,uint,char const *,char const *,char const *)
0x14000401b  mov     rcx, [rbp+188h]; this
0x140004022  lea     rax, aClosehandleHan; "::CloseHandle(handle)"
0x140004029  lea     r9, aWilDetailsClos; "wil::details::CloseHandle"
0x140004030  mov     [rsp+280h+var_260], rax; char *
0x140004035  mov     edx, 0A0Bh; void *
0x14000403a  call    ?_FailFast_GetLastError@in1diag5@details@wil@@YAXPEAXIPEBD11@Z; wil::details::in1diag5::_FailFast_GetLastError(void *,uint,char const *,char const *,char const *)
0x140004040  call    ?_FailFastImmediate_Unexpected@in1diag5@details@wil@@YAXXZ; wil::details::in1diag5::_FailFastImmediate_Unexpected(void)
0x140004046  mov     rcx, [rbp+188h]; this
0x14000404d  lea     rax, aReleasemutexMu; "::ReleaseMutex(mutex)"
0x140004054  lea     r9, aWilDetailsRele; "wil::details::ReleaseMutex"
0x14000405b  mov     [rsp+280h+var_260], rax; char *
0x140004060  mov     edx, 0A15h; void *
0x140004065  call    ?_FailFast_GetLastError@in1diag5@details@wil@@YAXPEAXIPEBD11@Z; wil::details::in1diag5::_FailFast_GetLastError(void *,uint,char const *,char const *,char const *)
0x14000406b  mov     rcx, [rbp+188h]; this
0x140004072  lea     rax, aClosehandleHan; "::CloseHandle(handle)"
0x140004079  lea     r9, aWilDetailsClos; "wil::details::CloseHandle"
0x140004080  mov     [rsp+280h+var_260], rax; char *
0x140004085  mov     edx, 0A0Bh; void *
0x14000408a  call    ?_FailFast_GetLastError@in1diag5@details@wil@@YAXPEAXIPEBD11@Z; wil::details::in1diag5::_FailFast_GetLastError(void *,uint,char const *,char const *,char const *)
0x140004090  mov     rcx, [rbp+188h]; this
0x140004097  lea     rax, aReleasemutexMu; "::ReleaseMutex(mutex)"
0x14000409e  lea     r9, aWilDetailsRele; "wil::details::ReleaseMutex"
0x1400040a5  mov     [rsp+280h+var_260], rax; char *
0x1400040aa  mov     edx, 0A15h; void *
0x1400040af  call    ?_FailFast_GetLastError@in1diag5@details@wil@@YAXPEAXIPEBD11@Z; wil::details::in1diag5::_FailFast_GetLastError(void *,uint,char const *,char const *,char const *)
```
