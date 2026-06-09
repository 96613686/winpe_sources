# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800737f0`
- end: `0x180073a04`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `532`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180072a30`

## callees

- `0x180046940`
- `0x1800707d0`
- `0x180070c00`
- `0x1800719d0`
- `0x180071a30`
- `0x180072360`
- `0x1800737f0`
- `0x180073c10`
- `0x1801f7110`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x18007381f`
- `KERNEL32!GetCurrentProcessId` at `0x18007381f`
- `KERNEL32!CloseHandle` at `0x18007387d`
- `KERNEL32!CloseHandle` at `0x18007387d`
- `KERNEL32!ReleaseMutex` at `0x18007396c`
- `KERNEL32!ReleaseMutex` at `0x18007396c`
- `KERNEL32!WaitForSingleObjectEx` at `0x1800738bc`
- `KERNEL32!WaitForSingleObjectEx` at `0x1800738bc`
- `KERNEL32!CreateMutexExW` at `0x18007385b`
- `KERNEL32!CreateMutexExW` at `0x18007385b`

## string_xrefs

- `0x1800739be`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.27\inc\wil\opensource\wil\resource.h`
- `0x1800739d8`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.27\inc\wil\opensource\wil\resource.h`
- `0x1800739f2`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.27\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // rbx
  unsigned int LastErrorFailHr; // edi
  const char *v8; // r9
  DWORD v10; // eax
  const char *v11; // r9
  void *v12; // rsi
  int ValueInternal; // eax
  __int64 v14; // rdx
  _DWORD *v15; // rcx
  const char *v16; // r9
  int v17; // [rsp+20h] [rbp-258h]
  int v18; // [rsp+20h] [rbp-258h]
  HANDLE v19; // [rsp+30h] [rbp-248h]
  unsigned __int64 v20; // [rsp+38h] [rbp-240h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v17 = 120;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  v19 = Mutex;
  v6 = Mutex;
  if ( !Mutex )
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
    goto LABEL_3;
  }
  v10 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
  if ( v10 == 258 )
  {
    v12 = 0;
  }
  else
  {
    if ( (v10 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(
        retaddr,
        (void *)0xC2D,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.27\\inc\\wil\\opensource\\wil\\resource.h",
        v11);
    v12 = v6;
  }
  v20 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, 1, &v20, 0);
  LastErrorFailHr = ValueInternal;
  if ( ValueInternal < 0 )
  {
    _mm_lfence();
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x64,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    _mm_lfence();
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6D, (unsigned int)"wil", (const char *)LastErrorFailHr, v18);
    v14 = 299;
LABEL_20:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)v14, (unsigned int)"wil", (const char *)LastErrorFailHr, v17);
    goto LABEL_15;
  }
  v15 = (_DWORD *)(4 * v20);
  if ( 4 * v20 )
  {
    *a2 = v15;
    ++*v15;
  }
  else
  {
    v6 = v19;
    LastErrorFailHr = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
    if ( (LastErrorFailHr & 0x80000000) != 0 )
    {
      v14 = 308;
      goto LABEL_20;
    }
  }
  LastErrorFailHr = 0;
LABEL_15:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x9DB,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.27\\inc\\wil\\opensource\\wil\\resource.h",
      v16);
LABEL_3:
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x9D1,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.27\\inc\\wil\\opensource\\wil\\resource.h",
      v8);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x1800737f0  mov     [rsp+arg_10], rbx
0x1800737f5  push    rsi
0x1800737f6  push    rdi
0x1800737f7  push    r14
0x1800737f9  sub     rsp, 260h
0x180073800  mov     rax, cs:__security_cookie
0x180073807  xor     rax, rsp
0x18007380a  mov     [rsp+278h+var_28], rax
0x180073812  mov     r14, rdx
0x180073815  mov     qword ptr [rdx], 0
0x18007381c  mov     rbx, rcx
0x18007381f  call    cs:__imp_GetCurrentProcessId
0x180073825  mov     [rsp+278h+var_250], rbx
0x18007382a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180073831  mov     r9d, eax
0x180073834  mov     [rsp+278h+var_258], 78h ; 'x'; int
0x18007383c  mov     edx, 104h; unsigned __int64
0x180073841  lea     rcx, [rsp+278h+Name]; Buffer
0x180073846  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18007384b  mov     r9d, 1F0001h; dwDesiredAccess
0x180073851  lea     rdx, [rsp+278h+Name]; lpName
0x180073856  xor     r8d, r8d; dwFlags
0x180073859  xor     ecx, ecx; lpMutexAttributes
0x18007385b  call    cs:__imp_CreateMutexExW
0x180073861  mov     [rsp+278h+var_248], rax
0x180073866  mov     rbx, rax
0x180073869  test    rax, rax
0x18007386c  jnz     short loc_1800738B1
0x18007386e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180073873  mov     edi, eax
0x180073875  test    rbx, rbx
0x180073878  jz      short loc_18007388B
0x18007387a  mov     rcx, rbx; hObject
0x18007387d  call    cs:__imp_CloseHandle
0x180073883  test    eax, eax
0x180073885  jz      loc_1800739EA
0x18007388b  mov     eax, edi
0x18007388d  mov     rcx, [rsp+278h+var_28]
0x180073895  xor     rcx, rsp; StackCookie
0x180073898  call    __security_check_cookie
0x18007389d  mov     rbx, [rsp+278h+arg_10]
0x1800738a5  add     rsp, 260h
0x1800738ac  pop     r14
0x1800738ae  pop     rdi
0x1800738af  pop     rsi
0x1800738b0  retn
0x1800738b1  xor     r8d, r8d; bAlertable
0x1800738b4  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x1800738b9  mov     rcx, rbx; hHandle
0x1800738bc  call    cs:__imp_WaitForSingleObjectEx
0x1800738c2  cmp     eax, 102h
0x1800738c7  jz      short loc_1800738D9
0x1800738c9  test    eax, 0FFFFFF7Fh
0x1800738ce  jnz     loc_1800739B6
0x1800738d4  mov     rsi, rbx
0x1800738d7  jmp     short loc_1800738DB
0x1800738d9  xor     esi, esi
0x1800738db  xor     r9d, r9d; bool *
0x1800738de  mov     [rsp+278h+var_240], 0
0x1800738e7  lea     r8, [rsp+278h+var_240]; unsigned __int64 *
0x1800738ec  mov     dl, 1; bool
0x1800738ee  lea     rcx, [rsp+278h+Name]; wchar_t *
0x1800738f3  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x1800738f8  mov     edi, eax
0x1800738fa  test    eax, eax
0x1800738fc  jns     short loc_180073943
0x1800738fe  lfence
0x180073901  mov     rcx, [rsp+278h]; this
0x180073909  lea     r8, aWil; "wil"
0x180073910  mov     r9d, eax; char *
0x180073913  mov     edx, 64h ; 'd'; void *
0x180073918  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007391d  lfence
0x180073920  mov     rcx, [rsp+278h]; this
0x180073928  lea     r8, aWil; "wil"
0x18007392f  mov     r9d, edi; char *
0x180073932  mov     edx, 6Dh ; 'm'; void *
0x180073937  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007393c  mov     edx, 12Bh
0x180073941  jmp     short loc_18007399D
0x180073943  mov     rax, [rsp+278h+var_240]
0x180073948  lea     rcx, ds:0[rax*4]
0x180073950  test    rcx, rcx
0x180073953  jz      short loc_18007397B
0x180073955  mov     [r14], rcx
0x180073958  mov     eax, [rcx]
0x18007395a  inc     eax
0x18007395c  mov     [rcx], eax
0x18007395e  xor     edi, edi
0x180073960  test    rsi, rsi
0x180073963  jz      loc_180073875
0x180073969  mov     rcx, rsi; hMutex
0x18007396c  call    cs:__imp_ReleaseMutex
0x180073972  test    eax, eax
0x180073974  jz      short loc_1800739D0
0x180073976  jmp     loc_180073875
0x18007397b  mov     r8, r14
0x18007397e  lea     rdx, [rsp+278h+var_248]
0x180073983  lea     rcx, [rsp+278h+Name]; wchar_t *
0x180073988  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18007398d  mov     rbx, [rsp+278h+var_248]
0x180073992  mov     edi, eax
0x180073994  test    eax, eax
0x180073996  jns     short loc_18007395E
0x180073998  mov     edx, 134h; void *
0x18007399d  mov     rcx, [rsp+278h]; this
0x1800739a5  lea     r8, aWil; "wil"
0x1800739ac  mov     r9d, edi; char *
0x1800739af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800739b4  jmp     short loc_180073960
0x1800739b6  mov     rcx, [rsp+278h]; this
0x1800739be  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x1800739c5  mov     edx, 0C2Dh; void *
0x1800739ca  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800739d0  mov     rcx, [rsp+278h]; this
0x1800739d8  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x1800739df  mov     edx, 9DBh; void *
0x1800739e4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800739ea  mov     rcx, [rsp+278h]; this
0x1800739f2  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x1800739f9  mov     edx, 9D1h; void *
0x1800739fe  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
