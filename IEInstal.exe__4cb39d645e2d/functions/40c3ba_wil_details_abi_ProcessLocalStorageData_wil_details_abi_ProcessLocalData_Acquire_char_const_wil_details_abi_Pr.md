# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x40c3ba`
- end: `0x40c519`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SGJPBDPAPAV123@@Z`
- size: `351`
- prototype: `int __fastcall(int, _DWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x40b3a7`

## callees

- `0x402df9`
- `0x40a9c3`
- `0x40adfa`
- `0x40ae71`
- `0x40ae9e`
- `0x40b08b`
- `0x40c066`
- `0x40c3ba`
- `0x40c61e`
- `0x40c73c`
- `0x40cb60`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x40c3db`
- `KERNEL32!GetCurrentProcessId` at `0x40c3db`
- `KERNEL32!CreateMutexExW` at `0x40c40f`
- `KERNEL32!CreateMutexExW` at `0x40c40f`

## pseudocode

```c
int __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        int a1,
        _DWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // eax
  HANDLE v5; // esi
  void *v6; // edi
  bool v7; // cl
  void *ValueInternal; // eax
  wil::details::in1diag3 *v9; // ecx
  wil::details::in1diag3 *v10; // ecx
  wil::details::in1diag3 *v11; // ecx
  _DWORD *v12; // eax
  void *v13; // eax
  wil::details::in1diag3 *v14; // ecx
  int v16; // [esp-Ch] [ebp-234h]
  int v17; // [esp-8h] [ebp-230h]
  int v19; // [esp-4h] [ebp-22Ch]
  wil::details *v20; // [esp+0h] [ebp-228h]
  void *v21; // [esp+0h] [ebp-228h]
  unsigned int v22; // [esp+0h] [ebp-228h]
  unsigned int v23; // [esp+0h] [ebp-228h]
  bool *v24; // [esp+4h] [ebp-224h]
  const char *v25; // [esp+4h] [ebp-224h]
  const char *v26; // [esp+4h] [ebp-224h]
  const char *v27; // [esp+4h] [ebp-224h]
  int v28; // [esp+8h] [ebp-220h]
  int v29; // [esp+8h] [ebp-220h]
  int v30; // [esp+8h] [ebp-220h]
  unsigned __int16 v31[4]; // [esp+Ch] [ebp-21Ch] BYREF
  wil::details *v32; // [esp+14h] [ebp-214h] BYREF
  HANDLE hObject; // [esp+18h] [ebp-210h] BYREF
  WCHAR Name[260]; // [esp+1Ch] [ebp-20Ch] BYREF

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, (wchar_t *)L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId, 64, a1);
  hObject = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PAXP6GXPAX__E_1_CloseHandle_details_wil__YGX0_ZU__integral_constant_I_0A__wistd__PAXPAX_0A___T_details_wil___details_wil__QAEXPAX_Z(
    &hObject,
    Mutex);
  v5 = hObject;
  if ( !hObject )
    return wil::details::GetLastErrorFailHr(v20);
  _acquire___mutex_t_V__unique_storage_U__resource_policy_PAXP6GXPAX__E_1_CloseHandle_details_wil__YGX0_ZU__integral_constant_I_0A__wistd__PAXPAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QBE_AV__unique_any_t_V__unique_storage_U__resource_policy_PAXP6GXPAX__E_1_ReleaseMutex_details_wil__YGX0_ZU__integral_constant_I_01_wistd__PAXPAX_0A___T_details_wil___details_wil___2_PAKKH_Z(
    &hObject,
    &v32,
    v16,
    v17,
    v19);
  *(_QWORD *)v31 = 0;
  ValueInternal = (void *)wil::details_abi::SemaphoreValue::TryGetValueInternal(v31, v7, (unsigned __int64 *)v20, v24);
  v6 = ValueInternal;
  if ( (int)ValueInternal >= 0 )
  {
    v12 = (_DWORD *)(4 * *(_DWORD *)v31);
    if ( 4 * *(_DWORD *)v31 )
    {
      *a2 = v12;
      *(_DWORD *)*a2 = *v12 + 1;
    }
    else
    {
      v13 = (void *)wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(
                      Name,
                      (int)a2);
      v6 = v13;
      if ( (int)v13 < 0 )
      {
        wil::details::in1diag3::Return_Hr(v14, v13, (unsigned int)v21, v25, v28);
        v5 = hObject;
        goto LABEL_11;
      }
      v5 = hObject;
    }
    v6 = 0;
    goto LABEL_11;
  }
  wil::details::in1diag3::Return_Hr(v9, ValueInternal, (unsigned int)v21, v25, v28);
  wil::details::in1diag3::Return_Hr(v10, v6, v22, v26, v29);
  wil::details::in1diag3::Return_Hr(v11, v6, v23, v27, v30);
LABEL_11:
  if ( v32 )
    wil::details::ReleaseMutex(v32, v21);
  if ( v5 )
    wil::details::CloseHandle(v5, v21);
  return (int)v6;
}

```

## disassembly

```asm
0x40c3ba  mov     edi, edi
0x40c3bc  push    ebp
0x40c3bd  mov     ebp, esp
0x40c3bf  sub     esp, 21Ch
0x40c3c5  mov     eax, ___security_cookie
0x40c3ca  xor     eax, ebp
0x40c3cc  mov     [ebp+var_4], eax
0x40c3cf  push    ebx; int
0x40c3d0  push    esi; char *
0x40c3d1  push    edi; void *
0x40c3d2  mov     ebx, edx
0x40c3d4  xor     esi, esi
0x40c3d6  push    ecx
0x40c3d7  push    40h ; '@'
0x40c3d9  mov     [ebx], esi
0x40c3db  call    ds:__imp__GetCurrentProcessId@0; GetCurrentProcessId()
0x40c3e1  push    eax
0x40c3e2  push    offset aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x40c3e7  lea     eax, [ebp+Name]
0x40c3ed  push    104h; unsigned int
0x40c3f2  push    eax; Buffer
0x40c3f3  call    ?StringCchPrintfW@@YAJPAGIPBGZZ; StringCchPrintfW(ushort *,uint,ushort const *,...)
0x40c3f8  add     esp, 18h
0x40c3fb  mov     [ebp+hObject], esi
0x40c401  lea     eax, [ebp+Name]
0x40c407  push    1F0001h; dwDesiredAccess
0x40c40c  push    esi; dwFlags
0x40c40d  push    eax; lpName
0x40c40e  push    esi; lpMutexAttributes
0x40c40f  call    ds:__imp__CreateMutexExW@16; CreateMutexExW(x,x,x,x)
0x40c415  push    eax
0x40c416  lea     ecx, [ebp+hObject]
0x40c41c  call    ?reset@?$unique_storage@U?$resource_policy@PAXP6GXPAX@_E$1?CloseHandle@details@wil@@YGX0@ZU?$integral_constant@I$0A@@wistd@@PAXPAX$0A@$$T@details@wil@@@details@wil@@QAEXPAX@Z
0x40c421  mov     esi, [ebp+hObject]
0x40c427  test    esi, esi
0x40c429  jnz     short loc_40C437
0x40c42b  call    ?GetLastErrorFailHr@details@wil@@YGJXZ; wil::details::GetLastErrorFailHr(void)
0x40c430  mov     edi, eax
0x40c432  jmp     loc_40C508
0x40c437  sub     esp, 0Ch
0x40c43a  lea     eax, [ebp+var_214]
0x40c440  lea     ecx, [ebp+hObject]
0x40c446  push    eax
0x40c447  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PAXP6GXPAX@_E$1?CloseHandle@details@wil@@YGX0@ZU?$integral_constant@I$0A@@wistd@@PAXPAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QBE?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PAXP6GXPAX@_E$1?ReleaseMutex@details@wil@@YGX0@ZU?$integral_constant@I$01@wistd@@PAXPAX$0A@$$T@details@wil@@@details@wil@@@2@PAKKH@Z
0x40c44c  push    ecx; bool
0x40c44d  lea     eax, [ebp+var_21C]
0x40c453  xorps   xmm0, xmm0
0x40c456  push    eax; unsigned __int16 *
0x40c457  lea     ecx, [ebp+Name]
0x40c45d  movlpd  qword ptr [ebp+var_21C], xmm0
0x40c465  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CGJPBG_NPA_KPA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x40c46a  mov     edi, eax
0x40c46c  test    edi, edi
0x40c46e  jns     short loc_40C49B
0x40c470  push    edi; void *
0x40c471  push    ecx; this
0x40c472  mov     ecx, [ebp+4]
0x40c475  push    66h ; 'f'
0x40c477  pop     edx
0x40c478  call    ?Return_Hr@in1diag3@details@wil@@YGXPAXIPBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x40c47d  push    edi; void *
0x40c47e  push    ecx; this
0x40c47f  mov     ecx, [ebp+4]
0x40c482  push    6Fh ; 'o'
0x40c484  pop     edx
0x40c485  call    ?Return_Hr@in1diag3@details@wil@@YGXPAXIPBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x40c48a  push    edi; void *
0x40c48b  push    ecx; this
0x40c48c  mov     ecx, [ebp+4]
0x40c48f  mov     edx, 12Eh
0x40c494  call    ?Return_Hr@in1diag3@details@wil@@YGXPAXIPBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x40c499  jmp     short loc_40C4EA
0x40c49b  mov     eax, dword ptr [ebp+var_21C]
0x40c4a1  shl     eax, 2
0x40c4a4  test    eax, eax
0x40c4a6  jz      short loc_40C4B3
0x40c4a8  mov     [ebx], eax
0x40c4aa  mov     ecx, [eax]
0x40c4ac  mov     eax, [ebx]
0x40c4ae  inc     ecx
0x40c4af  mov     [eax], ecx
0x40c4b1  jmp     short loc_40C4E8
0x40c4b3  push    ebx; int
0x40c4b4  lea     edx, [ebp+hObject]
0x40c4ba  lea     ecx, [ebp+Name]; unsigned __int16 *
0x40c4c0  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CGJPBG$$QAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PAXP6GXPAX@_E$1?CloseHandle@details@wil@@YGX0@ZU?$integral_constant@I$0A@@wistd@@PAXPAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PAPAV123@@Z
0x40c4c5  mov     edi, eax
0x40c4c7  test    edi, edi
0x40c4c9  jns     short loc_40C4E2
0x40c4cb  push    edi; void *
0x40c4cc  push    ecx; this
0x40c4cd  mov     ecx, [ebp+4]
0x40c4d0  mov     edx, 137h
0x40c4d5  call    ?Return_Hr@in1diag3@details@wil@@YGXPAXIPBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x40c4da  mov     esi, [ebp+hObject]
0x40c4e0  jmp     short loc_40C4EA
0x40c4e2  mov     esi, [ebp+hObject]
0x40c4e8  xor     edi, edi
0x40c4ea  cmp     [ebp+var_214], 0
0x40c4f1  jz      short loc_40C4FE
0x40c4f3  push    [ebp+var_214]; this
0x40c4f9  call    ?ReleaseMutex@details@wil@@YGXPAX@Z; wil::details::ReleaseMutex(void *)
0x40c4fe  test    esi, esi
0x40c500  jz      short loc_40C508
0x40c502  push    esi; hObject
0x40c503  call    ?CloseHandle@details@wil@@YGXPAX@Z; wil::details::CloseHandle(void *)
0x40c508  mov     ecx, [ebp+var_4]
0x40c50b  mov     eax, edi
0x40c50d  pop     edi
0x40c50e  pop     esi
0x40c50f  xor     ecx, ebp; StackCookie
0x40c511  pop     ebx
0x40c512  call    @__security_check_cookie@4; __security_check_cookie(x)
0x40c517  leave
0x40c518  retn
```
