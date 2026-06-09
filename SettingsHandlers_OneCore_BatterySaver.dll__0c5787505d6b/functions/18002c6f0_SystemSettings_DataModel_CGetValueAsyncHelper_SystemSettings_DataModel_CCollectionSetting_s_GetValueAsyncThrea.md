# SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CCollectionSetting>::s_GetValueAsyncThread(void *)

- ea: `0x18002c6f0`
- end: `0x18002c788`
- name: `?s_GetValueAsyncThread@?$CGetValueAsyncHelper@VCCollectionSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@CAKPEAX@Z`
- size: `152`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18001b6c0`
- `0x18001d5d4`
- `0x18002c6f0`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c730`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c730`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002c770`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002c770`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002c71c`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002c71c`

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
0x18002c6f0  mov     [rsp+arg_8], rbx
0x18002c6f5  mov     [rsp+arg_10], rsi
0x18002c6fa  push    rdi
0x18002c6fb  sub     rsp, 20h
0x18002c6ff  mov     rsi, rcx
0x18002c702  xor     bl, bl
0x18002c704  mov     [rsp+28h+arg_0], bl
0x18002c708  mov     rcx, [rcx+18h]; hToken
0x18002c70c  lea     rax, [rcx+1]
0x18002c710  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002c716  jnz     short loc_18002C71C
0x18002c718  xor     edi, edi
0x18002c71a  jmp     short loc_18002C738
0x18002c71c  call    cs:__imp_ImpersonateLoggedOnUser
0x18002c722  test    eax, eax
0x18002c724  jz      short loc_18002C730
0x18002c726  xor     edi, edi
0x18002c728  mov     bl, 1
0x18002c72a  mov     [rsp+28h+arg_0], bl
0x18002c72e  jmp     short loc_18002C738
0x18002c730  call    cs:__imp_GetLastError
0x18002c736  mov     edi, eax
0x18002c738  test    edi, edi
0x18002c73a  jnz     short loc_18002C74E
0x18002c73c  mov     r8, [rsi+10h]
0x18002c740  mov     rdx, [rsi+8]
0x18002c744  mov     rcx, [rsi]
0x18002c747  call    ?DoAsyncWorkInternal@?$CGetValueAsyncHelper@VCCollectionSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@AEAAXPEAVCSettingBase@23@PEBG@Z; SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CCollectionSetting>::DoAsyncWorkInternal(SystemSettings::DataModel::CSettingBase *,ushort const *)
0x18002c74c  jmp     short loc_18002C763
0x18002c74e  mov     rcx, [rsi+8]
0x18002c752  mov     rax, [rcx]
0x18002c755  xor     edx, edx
0x18002c757  mov     rax, [rax+0A8h]
0x18002c75e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c763  mov     rcx, rsi; void *
0x18002c766  call    ??_GASYNC_PARAMS@?$CGetValueAsyncHelper@VCCollectionSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@QEAAPEAXI@Z; SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CCollectionSetting>::ASYNC_PARAMS::`scalar deleting destructor'(uint)
0x18002c76b  nop
0x18002c76c  test    bl, bl
0x18002c76e  jz      short loc_18002C776
0x18002c770  call    cs:__imp_RevertToSelf
0x18002c776  mov     eax, edi
0x18002c778  mov     rbx, [rsp+28h+arg_8]
0x18002c77d  mov     rsi, [rsp+28h+arg_10]
0x18002c782  add     rsp, 20h
0x18002c786  pop     rdi
0x18002c787  retn
```
