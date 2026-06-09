# SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CCollectionSetting>::s_GetValueAsyncThread(void *)

- ea: `0x18003a890`
- end: `0x18003a93b`
- name: `?s_GetValueAsyncThread@?$CGetValueAsyncHelper@VCCollectionSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@CAKPEAX@Z`
- size: `171`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18002ff6c`
- `0x180031854`
- `0x18003a890`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a8d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a8d6`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18003a8bc`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18003a8bc`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003a91c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003a91c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CCollectionSetting>::s_GetValueAsyncThread(
        _QWORD *Parameter)
{
  char v2; // bl
  void *v3; // rcx
  DWORD LastError; // edi

  v2 = 0;
  v3 = (void *)Parameter[3];
  if ( (((unsigned __int64)v3 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    if ( ImpersonateLoggedOnUser(v3) )
    {
      LastError = 0;
      v2 = 1;
    }
    else
    {
      LastError = GetLastError();
    }
  }
  else
  {
    LastError = 0;
  }
  if ( LastError )
    (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)Parameter[1] + 168LL))(Parameter[1], 0);
  else
    SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CCollectionSetting>::DoAsyncWorkInternal(
      *Parameter,
      Parameter[1],
      Parameter[2]);
  SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CCollectionSetting>::ASYNC_PARAMS::`scalar deleting destructor'(Parameter);
  if ( v2 )
    RevertToSelf();
  return LastError;
}

```

## disassembly

```asm
0x18003a890  mov     [rsp+arg_8], rbx
0x18003a895  mov     [rsp+arg_10], rsi
0x18003a89a  push    rdi
0x18003a89b  sub     rsp, 20h
0x18003a89f  mov     rsi, rcx
0x18003a8a2  xor     bl, bl
0x18003a8a4  mov     [rsp+28h+arg_0], bl
0x18003a8a8  mov     rcx, [rcx+18h]; hToken
0x18003a8ac  lea     rax, [rcx+1]
0x18003a8b0  test    rax, 0FFFFFFFFFFFFFFFEh
0x18003a8b6  jnz     short loc_18003A8BC
0x18003a8b8  xor     edi, edi
0x18003a8ba  jmp     short loc_18003A8E4
0x18003a8bc  call    cs:__imp_ImpersonateLoggedOnUser
0x18003a8c3  nop     dword ptr [rax+rax+00h]
0x18003a8c8  test    eax, eax
0x18003a8ca  jz      short loc_18003A8D6
0x18003a8cc  xor     edi, edi
0x18003a8ce  mov     bl, 1
0x18003a8d0  mov     [rsp+28h+arg_0], bl
0x18003a8d4  jmp     short loc_18003A8E4
0x18003a8d6  call    cs:__imp_GetLastError
0x18003a8dd  nop     dword ptr [rax+rax+00h]
0x18003a8e2  mov     edi, eax
0x18003a8e4  test    edi, edi
0x18003a8e6  jnz     short loc_18003A8FA
0x18003a8e8  mov     r8, [rsi+10h]
0x18003a8ec  mov     rdx, [rsi+8]
0x18003a8f0  mov     rcx, [rsi]
0x18003a8f3  call    ?DoAsyncWorkInternal@?$CGetValueAsyncHelper@VCCollectionSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@AEAAXPEAVCSettingBase@23@PEBG@Z; SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CCollectionSetting>::DoAsyncWorkInternal(SystemSettings::DataModel::CSettingBase *,ushort const *)
0x18003a8f8  jmp     short loc_18003A90F
0x18003a8fa  mov     rcx, [rsi+8]
0x18003a8fe  mov     rax, [rcx]
0x18003a901  xor     edx, edx
0x18003a903  mov     rax, [rax+0A8h]
0x18003a90a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a90f  mov     rcx, rsi; void *
0x18003a912  call    ??_GASYNC_PARAMS@?$CGetValueAsyncHelper@VCCollectionSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@QEAAPEAXI@Z; SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CCollectionSetting>::ASYNC_PARAMS::`scalar deleting destructor'(uint)
0x18003a917  nop
0x18003a918  test    bl, bl
0x18003a91a  jz      short loc_18003A928
0x18003a91c  call    cs:__imp_RevertToSelf
0x18003a923  nop     dword ptr [rax+rax+00h]
0x18003a928  mov     eax, edi
0x18003a92a  mov     rbx, [rsp+28h+arg_8]
0x18003a92f  mov     rsi, [rsp+28h+arg_10]
0x18003a934  add     rsp, 20h
0x18003a938  pop     rdi
0x18003a939  retn
```
