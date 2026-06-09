# RegHelpers::RegSetKeyValueW(HKEY__ *,wchar_t const *,wchar_t const *,ulong,void const *,ulong)

- ea: `0x18009a518`
- end: `0x18009a605`
- name: `?RegSetKeyValueW@RegHelpers@@YAJPEAUHKEY__@@PEB_W1KPEBXK@Z`
- size: `237`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, HKEY@<rdx>, const wchar_t *@<r8>, const wchar_t *@<r9>, unsigned int, const void *, unsigned int)`
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x18009aa94`
- `0x18009ac30`
- `0x18009ad00`
- `0x18009ae50`
- `0x18009af90`

## callees

- `0x180042840`
- `0x180042dd0`
- `0x180099670`
- `0x18009a518`

## import_xrefs

- `ntdll!RtlIsMultiUsersInSessionSku` at `0x18009a528`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x18009a528`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18009a5b6`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18009a5f3`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18009a5b6`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18009a5f3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
LSTATUS __fastcall RegHelpers::RegSetKeyValueW(
        HKEY hKey,
        HKEY a2,
        const wchar_t *a3,
        const wchar_t *a4,
        LPCVOID lpData)
{
  HKEY v6; // rbx
  __int128 *HKUForCurrentOnlyUser; // rax
  LSTATUS v9; // ebx
  __int128 v10; // [rsp+30h] [rbp-28h] BYREF
  _BYTE v11[24]; // [rsp+40h] [rbp-18h] BYREF

  v6 = hKey;
  if ( !(unsigned __int8)RtlIsMultiUsersInSessionSku(hKey, a2, a3, a4) )
    return RegSetKeyValueW(v6, 0, a3, 4u, lpData, 4u);
  v10 = 0;
  if ( v6 != HKEY_CURRENT_USER )
    goto LABEL_8;
  HKUForCurrentOnlyUser = (__int128 *)UserHelpers::GetHKUForCurrentOnlyUser(v11);
  if ( &v10 != HKUForCurrentOnlyUser )
    std::shared_ptr<Windows::Globalization::Spelling::SpellerFromCsapi::CWordlist>::operator=(
      &v10,
      HKUForCurrentOnlyUser);
  std::shared_ptr<Windows::Internal::Spelling::TaskDispatcherInterface>::~shared_ptr<Windows::Internal::Spelling::TaskDispatcherInterface>(v11);
  if ( (_QWORD)v10 && (v6 = *(HKEY *)v10) != 0 )
  {
LABEL_8:
    v9 = RegSetKeyValueW(v6, 0, a3, 4u, lpData, 4u);
    std::shared_ptr<Windows::Internal::Spelling::TaskDispatcherInterface>::~shared_ptr<Windows::Internal::Spelling::TaskDispatcherInterface>(&v10);
    return v9;
  }
  else
  {
    std::shared_ptr<Windows::Internal::Spelling::TaskDispatcherInterface>::~shared_ptr<Windows::Internal::Spelling::TaskDispatcherInterface>(&v10);
    return 2;
  }
}

```

## disassembly

```asm
0x18009a518  mov     [rsp+arg_0], rbx
0x18009a51d  push    rdi
0x18009a51e  sub     rsp, 50h
0x18009a522  mov     rdi, r8
0x18009a525  mov     rbx, rcx
0x18009a528  call    cs:__imp_RtlIsMultiUsersInSessionSku
0x18009a52e  test    al, al
0x18009a530  jz      loc_18009A5D3
0x18009a536  xorps   xmm1, xmm1
0x18009a539  movdqu  [rsp+58h+var_28], xmm1
0x18009a53f  cmp     rbx, 0FFFFFFFF80000001h
0x18009a546  jnz     short loc_18009A596
0x18009a548  lea     rcx, [rsp+58h+var_18]
0x18009a54d  call    ?GetHKUForCurrentOnlyUser@UserHelpers@@YA?AV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@XZ; UserHelpers::GetHKUForCurrentOnlyUser(void)
0x18009a552  lea     rcx, [rsp+58h+var_28]
0x18009a557  cmp     rcx, rax
0x18009a55a  jz      short loc_18009A569
0x18009a55c  mov     rdx, rax
0x18009a55f  lea     rcx, [rsp+58h+var_28]
0x18009a564  call    ??4?$shared_ptr@VCWordlist@SpellerFromCsapi@Spelling@Globalization@Windows@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Windows::Globalization::Spelling::SpellerFromCsapi::CWordlist>::operator=(std::shared_ptr<Windows::Globalization::Spelling::SpellerFromCsapi::CWordlist> &&)
0x18009a569  lea     rcx, [rsp+58h+var_18]; void *
0x18009a56e  call    ??1?$shared_ptr@UTaskDispatcherInterface@Spelling@Internal@Windows@@@std@@QEAA@XZ; std::shared_ptr<Windows::Internal::Spelling::TaskDispatcherInterface>::~shared_ptr<Windows::Internal::Spelling::TaskDispatcherInterface>(void)
0x18009a573  mov     rbx, qword ptr [rsp+58h+var_28]
0x18009a578  test    rbx, rbx
0x18009a57b  jz      short loc_18009A585
0x18009a57d  mov     rbx, [rbx]
0x18009a580  test    rbx, rbx
0x18009a583  jnz     short loc_18009A596
0x18009a585  lea     rcx, [rsp+58h+var_28]; void *
0x18009a58a  call    ??1?$shared_ptr@UTaskDispatcherInterface@Spelling@Internal@Windows@@@std@@QEAA@XZ; std::shared_ptr<Windows::Internal::Spelling::TaskDispatcherInterface>::~shared_ptr<Windows::Internal::Spelling::TaskDispatcherInterface>(void)
0x18009a58f  mov     eax, 2
0x18009a594  jmp     short loc_18009A5FA
0x18009a596  mov     r9d, 4; dwType
0x18009a59c  mov     [rsp+58h+cbData], r9d; cbData
0x18009a5a1  mov     rax, [rsp+58h+arg_20]
0x18009a5a9  mov     [rsp+58h+lpData], rax; lpData
0x18009a5ae  mov     r8, rdi; lpValueName
0x18009a5b1  xor     edx, edx; lpSubKey
0x18009a5b3  mov     rcx, rbx; hKey
0x18009a5b6  call    cs:__imp_RegSetKeyValueW
0x18009a5bc  mov     ebx, eax
0x18009a5be  jmp     short loc_18009A5C5
0x18009a5c0  mov     ebx, 2
0x18009a5c5  lea     rcx, [rsp+58h+var_28]; void *
0x18009a5ca  call    ??1?$shared_ptr@UTaskDispatcherInterface@Spelling@Internal@Windows@@@std@@QEAA@XZ; std::shared_ptr<Windows::Internal::Spelling::TaskDispatcherInterface>::~shared_ptr<Windows::Internal::Spelling::TaskDispatcherInterface>(void)
0x18009a5cf  mov     eax, ebx
0x18009a5d1  jmp     short loc_18009A5FA
0x18009a5d3  mov     r9d, 4; dwType
0x18009a5d9  mov     [rsp+58h+cbData], r9d; cbData
0x18009a5de  mov     rax, [rsp+58h+arg_20]
0x18009a5e6  mov     [rsp+58h+lpData], rax; lpData
0x18009a5eb  mov     r8, rdi; lpValueName
0x18009a5ee  xor     edx, edx; lpSubKey
0x18009a5f0  mov     rcx, rbx; hKey
0x18009a5f3  call    cs:__imp_RegSetKeyValueW
0x18009a5f9  nop
0x18009a5fa  mov     rbx, [rsp+58h+arg_0]
0x18009a5ff  add     rsp, 50h
0x18009a603  pop     rdi
0x18009a604  retn
```
