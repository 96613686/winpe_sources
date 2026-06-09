# RegHelpers::RegCreateKeyExW(HKEY__ *,wchar_t const *,wchar_t *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)

- ea: `0x18009a2d0`
- end: `0x18009a3e7`
- name: `?RegCreateKeyExW@RegHelpers@@YAJPEAUHKEY__@@PEB_WPEA_WKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU2@PEAK@Z`
- size: `279`
- prototype: `int(RegHelpers *__hidden this, HKEY, const wchar_t *, wchar_t *, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *, HKEY *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180098a38`

## callees

- `0x180042840`
- `0x180042dd0`
- `0x180099670`
- `0x18009a2d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009a369`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009a3da`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009a369`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009a3da`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x18009a2d9`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x18009a2d9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
LSTATUS __fastcall RegHelpers::RegCreateKeyExW(
        RegHelpers *this,
        const WCHAR *a2,
        const wchar_t *a3,
        wchar_t *a4,
        unsigned int a5,
        unsigned int a6,
        HKEY *phkResult,
        HKEY *lpdwDisposition)
{
  __int128 *HKUForCurrentOnlyUser; // rax
  LSTATUS Key; // ebx
  __int128 v12; // [rsp+50h] [rbp-28h] BYREF
  _BYTE v13[24]; // [rsp+60h] [rbp-18h] BYREF

  if ( !(unsigned __int8)RtlIsMultiUsersInSessionSku(this, a2, a3, a4) )
    return RegCreateKeyExW(HKEY_CURRENT_USER, a2, 0, 0, 0, 3u, 0, phkResult, (LPDWORD)lpdwDisposition);
  v12 = 0;
  HKUForCurrentOnlyUser = (__int128 *)UserHelpers::GetHKUForCurrentOnlyUser(v13);
  if ( &v12 != HKUForCurrentOnlyUser )
    std::shared_ptr<Windows::Globalization::Spelling::SpellerFromCsapi::CWordlist>::operator=(
      &v12,
      HKUForCurrentOnlyUser);
  std::shared_ptr<Windows::Internal::Spelling::TaskDispatcherInterface>::~shared_ptr<Windows::Internal::Spelling::TaskDispatcherInterface>(v13);
  if ( (_QWORD)v12 && *(_QWORD *)v12 )
  {
    Key = RegCreateKeyExW(*(HKEY *)v12, a2, 0, 0, 0, 3u, 0, phkResult, (LPDWORD)lpdwDisposition);
    std::shared_ptr<Windows::Internal::Spelling::TaskDispatcherInterface>::~shared_ptr<Windows::Internal::Spelling::TaskDispatcherInterface>(&v12);
    return Key;
  }
  else
  {
    std::shared_ptr<Windows::Internal::Spelling::TaskDispatcherInterface>::~shared_ptr<Windows::Internal::Spelling::TaskDispatcherInterface>(&v12);
    return 2;
  }
}

```

## disassembly

```asm
0x18009a2d0  push    rbx
0x18009a2d2  sub     rsp, 70h
0x18009a2d6  mov     rbx, rdx
0x18009a2d9  call    cs:__imp_RtlIsMultiUsersInSessionSku
0x18009a2df  test    al, al
0x18009a2e1  jz      loc_18009A397
0x18009a2e7  xorps   xmm1, xmm1
0x18009a2ea  movdqu  [rsp+78h+var_28], xmm1
0x18009a2f0  lea     rcx, [rsp+78h+var_18]
0x18009a2f5  call    ?GetHKUForCurrentOnlyUser@UserHelpers@@YA?AV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@XZ; UserHelpers::GetHKUForCurrentOnlyUser(void)
0x18009a2fa  lea     rcx, [rsp+78h+var_28]
0x18009a2ff  cmp     rcx, rax
0x18009a302  jz      short loc_18009A311
0x18009a304  mov     rdx, rax
0x18009a307  lea     rcx, [rsp+78h+var_28]
0x18009a30c  call    ??4?$shared_ptr@VCWordlist@SpellerFromCsapi@Spelling@Globalization@Windows@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Windows::Globalization::Spelling::SpellerFromCsapi::CWordlist>::operator=(std::shared_ptr<Windows::Globalization::Spelling::SpellerFromCsapi::CWordlist> &&)
0x18009a311  lea     rcx, [rsp+78h+var_18]; void *
0x18009a316  call    ??1?$shared_ptr@UTaskDispatcherInterface@Spelling@Internal@Windows@@@std@@QEAA@XZ; std::shared_ptr<Windows::Internal::Spelling::TaskDispatcherInterface>::~shared_ptr<Windows::Internal::Spelling::TaskDispatcherInterface>(void)
0x18009a31b  mov     rax, qword ptr [rsp+78h+var_28]
0x18009a320  test    rax, rax
0x18009a323  jz      short loc_18009A373
0x18009a325  mov     rcx, [rax]; hKey
0x18009a328  test    rcx, rcx
0x18009a32b  jz      short loc_18009A373
0x18009a32d  mov     rax, [rsp+78h+arg_38]
0x18009a335  mov     [rsp+78h+lpdwDisposition], rax; lpdwDisposition
0x18009a33a  mov     rax, [rsp+78h+arg_30]
0x18009a342  mov     [rsp+78h+phkResult], rax; phkResult
0x18009a347  mov     [rsp+78h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18009a350  mov     [rsp+78h+samDesired], 3; samDesired
0x18009a358  mov     [rsp+78h+dwOptions], 0; dwOptions
0x18009a360  xor     r9d, r9d; lpClass
0x18009a363  xor     r8d, r8d; Reserved
0x18009a366  mov     rdx, rbx; lpSubKey
0x18009a369  call    cs:__imp_RegCreateKeyExW
0x18009a36f  mov     ebx, eax
0x18009a371  jmp     short loc_18009A389
0x18009a373  lea     rcx, [rsp+78h+var_28]; void *
0x18009a378  call    ??1?$shared_ptr@UTaskDispatcherInterface@Spelling@Internal@Windows@@@std@@QEAA@XZ; std::shared_ptr<Windows::Internal::Spelling::TaskDispatcherInterface>::~shared_ptr<Windows::Internal::Spelling::TaskDispatcherInterface>(void)
0x18009a37d  mov     eax, 2
0x18009a382  jmp     short loc_18009A3E1
0x18009a384  mov     ebx, 2
0x18009a389  lea     rcx, [rsp+78h+var_28]; void *
0x18009a38e  call    ??1?$shared_ptr@UTaskDispatcherInterface@Spelling@Internal@Windows@@@std@@QEAA@XZ; std::shared_ptr<Windows::Internal::Spelling::TaskDispatcherInterface>::~shared_ptr<Windows::Internal::Spelling::TaskDispatcherInterface>(void)
0x18009a393  mov     eax, ebx
0x18009a395  jmp     short loc_18009A3E1
0x18009a397  mov     rax, [rsp+78h+arg_38]
0x18009a39f  mov     [rsp+78h+lpdwDisposition], rax; lpdwDisposition
0x18009a3a4  mov     rax, [rsp+78h+arg_30]
0x18009a3ac  mov     [rsp+78h+phkResult], rax; phkResult
0x18009a3b1  mov     [rsp+78h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18009a3ba  mov     [rsp+78h+samDesired], 3; samDesired
0x18009a3c2  mov     [rsp+78h+dwOptions], 0; dwOptions
0x18009a3ca  xor     r9d, r9d; lpClass
0x18009a3cd  xor     r8d, r8d; Reserved
0x18009a3d0  mov     rdx, rbx; lpSubKey
0x18009a3d3  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18009a3da  call    cs:__imp_RegCreateKeyExW
0x18009a3e0  nop
0x18009a3e1  add     rsp, 70h
0x18009a3e5  pop     rbx
0x18009a3e6  retn
```
