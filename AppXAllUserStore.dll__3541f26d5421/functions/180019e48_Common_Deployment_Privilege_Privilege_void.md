# Common::Deployment::Privilege::~Privilege(void)

- ea: `0x180019e48`
- end: `0x180019eae`
- name: `??1Privilege@Deployment@Common@@QEAA@XZ`
- size: `102`
- prototype: `void __fastcall(HANDLE *this)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180019b04`
- `0x180049ff8`
- `0x18004a9a4`

## callees

- `0x180019e48`
- `0x1800466e4`
- `0x1800475bc`
- `0x18004b2ac`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019e7c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019e7c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180019e9b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180019e9b`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180019e65`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180019e65`

## pseudocode

```c
void __fastcall Common::Deployment::Privilege::~Privilege(HANDLE *this)
{
  HANDLE v2; // rcx

  Common::Deployment::Privilege::Revert((Common::Deployment::Privilege *)this);
  if ( *((_BYTE *)this + 24) )
  {
    v2 = this[4];
    if ( v2 )
    {
      if ( !ImpersonateLoggedOnUser(v2) )
      {
        Common::HandleInternalFailure(2);
        __debugbreak();
      }
      CloseHandle(this[4]);
      this[4] = 0;
    }
    else if ( !RevertToSelf() )
    {
      Common::HandleInternalFailure(2);
      JUMPOUT(0x180019EADLL);
    }
    *((_BYTE *)this + 24) = 0;
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(this);
}

```

## disassembly

```asm
0x180019e48  push    rbx
0x180019e4a  sub     rsp, 20h
0x180019e4e  mov     rbx, rcx
0x180019e51  call    ?Revert@Privilege@Deployment@Common@@QEAAJXZ; Common::Deployment::Privilege::Revert(void)
0x180019e56  cmp     byte ptr [rbx+18h], 0
0x180019e5a  jz      short loc_180019E8E
0x180019e5c  mov     rcx, [rbx+20h]; hToken
0x180019e60  test    rcx, rcx
0x180019e63  jz      short loc_180019E9B
0x180019e65  call    cs:__imp_ImpersonateLoggedOnUser
0x180019e6b  test    eax, eax
0x180019e6d  jnz     short loc_180019E78
0x180019e6f  lea     ecx, [rax+2]
0x180019e72  call    ?HandleInternalFailure@Common@@YAXW4FATAL_FAILURE_REASON_TYPE@1@_KK@Z; Common::HandleInternalFailure(Common::FATAL_FAILURE_REASON_TYPE,unsigned __int64,ulong)
0x180019e77  int     3; Trap to Debugger
0x180019e78  mov     rcx, [rbx+20h]; hObject
0x180019e7c  call    cs:__imp_CloseHandle
0x180019e82  mov     qword ptr [rbx+20h], 0
0x180019e8a  mov     byte ptr [rbx+18h], 0
0x180019e8e  mov     rcx, rbx
0x180019e91  add     rsp, 20h
0x180019e95  pop     rbx
0x180019e96  jmp     ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180019e9b  call    cs:__imp_RevertToSelf
0x180019ea1  test    eax, eax
0x180019ea3  jnz     short loc_180019E8A
0x180019ea5  lea     ecx, [rax+2]
0x180019ea8  call    ?HandleInternalFailure@Common@@YAXW4FATAL_FAILURE_REASON_TYPE@1@_KK@Z; Common::HandleInternalFailure(Common::FATAL_FAILURE_REASON_TYPE,unsigned __int64,ulong)
```
