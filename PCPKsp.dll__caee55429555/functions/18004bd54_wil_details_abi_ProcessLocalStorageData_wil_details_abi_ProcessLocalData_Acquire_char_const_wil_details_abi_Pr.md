# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18004bd54`
- end: `0x18004bf3f`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `491`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18004bc90`

## callees

- `0x180011bd0`
- `0x1800133c4`
- `0x180049db4`
- `0x18004bd54`
- `0x18004bf48`
- `0x18004bf68`
- `0x18005a254`
- `0x18005a284`
- `0x18006beac`
- `0x18006d0a0`
- `0x1800764d0`
- `0x180078bf8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18004bdfd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18004bdfd`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18004bdd1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18004bdd1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004bd8f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004bd8f`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  wil::details *Mutex; // rax
  wil::details *v5; // rcx
  wil::details *v6; // rbx
  DWORD v8; // eax
  void *v9; // rdx
  unsigned int v10; // r8d
  char *v11; // r9
  wil::details *v12; // rsi
  int ValueInternal; // eax
  void *v14; // rdx
  unsigned int v15; // edi
  unsigned __int64 v16; // r9
  __int64 v17; // rdx
  _DWORD *v18; // rcx
  int v19; // eax
  int v20; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+20h] [rbp-E0h]
  wil::details *v22; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v23; // [rsp+38h] [rbp-C8h] BYREF
  wil::details *v24; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v20 = 120;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = (wil::details *)CreateMutexExW(0, Name, 0, 0x1F0001u);
  v22 = Mutex;
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
  v24 = v12;
  v23 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, &v23, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v21);
    v16 = v15;
    v17 = 302;
LABEL_14:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)v17, (unsigned int)"wil", (const char *)v16, v20);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v24);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v22);
    return v15;
  }
  v18 = (_DWORD *)(4 * v23);
  if ( 4 * v23 )
  {
    *a2 = v18;
    ++*v18;
  }
  else
  {
    v19 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
    v15 = v19;
    if ( v19 < 0 )
    {
      v16 = (unsigned int)v19;
      v17 = 311;
      goto LABEL_14;
    }
    v6 = v22;
  }
  if ( v12 )
    wil::details::ReleaseMutex(v12, v14);
  if ( v6 )
    wil::details::CloseHandle(v6, v14);
  return 0;
}

```

## disassembly

```asm
0x18004bd54  mov     [rsp-8+arg_10], rbx
0x18004bd59  mov     [rsp-8+arg_18], rsi
0x18004bd5e  push    rbp
0x18004bd5f  push    rdi
0x18004bd60  push    r14
0x18004bd62  lea     rbp, [rsp-170h]
0x18004bd6a  sub     rsp, 270h
0x18004bd71  mov     rax, cs:__security_cookie
0x18004bd78  xor     rax, rsp
0x18004bd7b  mov     [rbp+180h+var_20], rax
0x18004bd82  mov     r14, rdx
0x18004bd85  mov     qword ptr [rdx], 0
0x18004bd8c  mov     rbx, rcx
0x18004bd8f  call    cs:__imp_GetCurrentProcessId
0x18004bd96  nop     dword ptr [rax+rax+00h]
0x18004bd9b  mov     [rsp+280h+var_258], rbx
0x18004bda0  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18004bda7  mov     r9d, eax
0x18004bdaa  mov     [rsp+280h+var_260], 78h ; 'x'; int
0x18004bdb2  mov     edx, 104h; unsigned __int64
0x18004bdb7  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18004bdbc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004bdc1  mov     r9d, 1F0001h; dwDesiredAccess
0x18004bdc7  lea     rdx, [rsp+280h+Name]; lpName
0x18004bdcc  xor     r8d, r8d; dwFlags
0x18004bdcf  xor     ecx, ecx; lpMutexAttributes
0x18004bdd1  call    cs:__imp_CreateMutexExW
0x18004bdd8  nop     dword ptr [rax+rax+00h]
0x18004bddd  mov     [rsp+280h+var_250], rax
0x18004bde2  mov     rbx, rax
0x18004bde5  test    rax, rax
0x18004bde8  jnz     short loc_18004BDF4
0x18004bdea  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18004bdef  jmp     loc_18004BF17
0x18004bdf4  xor     r8d, r8d; bAlertable
0x18004bdf7  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18004bdfa  mov     rcx, rbx; hHandle
0x18004bdfd  call    cs:__imp_WaitForSingleObjectEx
0x18004be04  nop     dword ptr [rax+rax+00h]
0x18004be09  cmp     eax, 102h
0x18004be0e  jz      short loc_18004BE29
0x18004be10  test    eax, 0FFFFFF7Fh
0x18004be15  jz      short loc_18004BE24
0x18004be17  mov     rcx, [rbp+188h]; this
0x18004be1e  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18004be24  mov     rsi, rbx
0x18004be27  jmp     short loc_18004BE2B
0x18004be29  xor     esi, esi
0x18004be2b  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x18004be30  mov     [rsp+280h+var_240], rsi
0x18004be35  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18004be3a  mov     [rsp+280h+var_248], 0
0x18004be43  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18004be48  mov     edi, eax
0x18004be4a  test    eax, eax
0x18004be4c  jns     short loc_18004BE8E
0x18004be4e  mov     rcx, [rbp+188h]; this
0x18004be55  lea     r8, aWil; "wil"
0x18004be5c  mov     r9d, eax; char *
0x18004be5f  mov     edx, 66h ; 'f'; void *
0x18004be64  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004be69  mov     rcx, [rbp+188h]; this
0x18004be70  lea     r8, aWil; "wil"
0x18004be77  mov     r9d, edi; char *
0x18004be7a  mov     edx, 6Fh ; 'o'; void *
0x18004be7f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004be84  mov     r9d, edi
0x18004be87  mov     edx, 12Eh
0x18004be8c  jmp     short loc_18004BECB
0x18004be8e  mov     rax, [rsp+280h+var_248]
0x18004be93  lea     rcx, ds:0[rax*4]
0x18004be9b  test    rcx, rcx
0x18004be9e  jz      short loc_18004BEAB
0x18004bea0  mov     [r14], rcx
0x18004bea3  mov     eax, [rcx]
0x18004bea5  inc     eax
0x18004bea7  mov     [rcx], eax
0x18004bea9  jmp     short loc_18004BEFB
0x18004beab  mov     r8, r14
0x18004beae  lea     rdx, [rsp+280h+var_250]
0x18004beb3  lea     rcx, [rsp+280h+Name]
0x18004beb8  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18004bebd  mov     edi, eax
0x18004bebf  test    eax, eax
0x18004bec1  jns     short loc_18004BEF6
0x18004bec3  mov     r9d, eax; char *
0x18004bec6  mov     edx, 137h; void *
0x18004becb  mov     rcx, [rbp+188h]; this
0x18004bed2  lea     r8, aWil; "wil"
0x18004bed9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004bede  lea     rcx, [rsp+280h+var_240]
0x18004bee3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004bee8  lea     rcx, [rsp+280h+var_250]
0x18004beed  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004bef2  mov     eax, edi
0x18004bef4  jmp     short loc_18004BF17
0x18004bef6  mov     rbx, [rsp+280h+var_250]
0x18004befb  test    rsi, rsi
0x18004befe  jz      short loc_18004BF08
0x18004bf00  mov     rcx, rsi; this
0x18004bf03  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x18004bf08  test    rbx, rbx
0x18004bf0b  jz      short loc_18004BF15
0x18004bf0d  mov     rcx, rbx; this
0x18004bf10  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18004bf15  xor     eax, eax
0x18004bf17  mov     rcx, [rbp+180h+var_20]
0x18004bf1e  xor     rcx, rsp; StackCookie
0x18004bf21  call    __security_check_cookie
0x18004bf26  lea     r11, [rsp+280h+var_10]
0x18004bf2e  mov     rbx, [r11+30h]
0x18004bf32  mov     rsi, [r11+38h]
0x18004bf36  mov     rsp, r11
0x18004bf39  pop     r14
0x18004bf3b  pop     rdi
0x18004bf3c  pop     rbp
0x18004bf3d  retn
```
