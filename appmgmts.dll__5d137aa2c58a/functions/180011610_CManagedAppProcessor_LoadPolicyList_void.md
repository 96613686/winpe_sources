# CManagedAppProcessor::LoadPolicyList(void)

- ea: `0x180011610`
- end: `0x1800116de`
- name: `?LoadPolicyList@CManagedAppProcessor@@QEAAKXZ`
- size: `206`
- prototype: `__int64 __fastcall(CManagedAppProcessor *this)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000239c`
- `0x18001069c`

## callees

- `0x180011610`
- `0x1800117c4`
- `0x180011e44`
- `0x1800126ec`
- `0x18001b1a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011659`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011671`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011659`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011671`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180011697`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180011697`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180011647`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180011647`
- `USERENV!FreeGPOListW` at `0x1800116ba`
- `USERENV!FreeGPOListW` at `0x1800116ba`

## pseudocode

```c
__int64 __fastcall CManagedAppProcessor::LoadPolicyList(CManagedAppProcessor *this)
{
  bool v1; // zf
  _DWORD *v2; // rbx
  DWORD LastError; // eax
  DWORD CurrentUserGPOList; // edi
  PGROUP_POLICY_OBJECTW pGPOList; // [rsp+30h] [rbp+8h] BYREF

  v1 = *((_DWORD *)this + 99) == 1;
  v2 = (_DWORD *)((char *)this + 296);
  pGPOList = 0;
  if ( v1 || !*v2 || ImpersonateLoggedOnUser(*((HANDLE *)this + 33)) )
    goto LABEL_7;
  if ( *(_DWORD *)&gDebugLevel )
  {
    LastError = GetLastError();
    _DebugMsg(2, 0xBC4u, LastError);
  }
  CurrentUserGPOList = GetLastError();
  if ( !CurrentUserGPOList )
  {
LABEL_7:
    CurrentUserGPOList = GetCurrentUserGPOList(&pGPOList);
    if ( *((_DWORD *)this + 99) != 1 && *v2 )
      RevertToSelf();
    if ( !CurrentUserGPOList )
      CurrentUserGPOList = CManagedAppProcessor::SetPolicyListFromGPOList(this, pGPOList);
  }
  if ( pGPOList )
    FreeGPOListW(pGPOList);
  if ( !CurrentUserGPOList )
    CManagedAppProcessor::MergePolicyList(this);
  return CurrentUserGPOList;
}

```

## disassembly

```asm
0x180011610  mov     [rsp+arg_8], rbx
0x180011615  mov     [rsp+arg_10], rsi
0x18001161a  push    rdi
0x18001161b  sub     rsp, 20h
0x18001161f  cmp     dword ptr [rcx+18Ch], 1
0x180011626  lea     rbx, [rcx+128h]
0x18001162d  mov     rsi, rcx
0x180011630  mov     [rsp+28h+pGPOList], 0
0x180011639  jz      short loc_18001167D
0x18001163b  cmp     dword ptr [rbx], 0
0x18001163e  jz      short loc_18001167D
0x180011640  mov     rcx, [rcx+108h]; hToken
0x180011647  call    cs:__imp_ImpersonateLoggedOnUser
0x18001164d  test    eax, eax
0x18001164f  jnz     short loc_18001167D
0x180011651  cmp     cs:?gDebugLevel@@3KA, eax; ulong gDebugLevel
0x180011657  jz      short loc_180011671
0x180011659  call    cs:__imp_GetLastError
0x18001165f  mov     edx, 0BC4h; unsigned int
0x180011664  mov     ecx, 2; unsigned int
0x180011669  mov     r8d, eax
0x18001166c  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x180011671  call    cs:__imp_GetLastError
0x180011677  mov     edi, eax
0x180011679  test    eax, eax
0x18001167b  jnz     short loc_1800116B0
0x18001167d  lea     rcx, [rsp+28h+pGPOList]; ppGPOList
0x180011682  call    ?GetCurrentUserGPOList@@YAKPEAPEAU_GROUP_POLICY_OBJECTW@@@Z; GetCurrentUserGPOList(_GROUP_POLICY_OBJECTW * *)
0x180011687  cmp     dword ptr [rsi+18Ch], 1
0x18001168e  mov     edi, eax
0x180011690  jz      short loc_18001169D
0x180011692  cmp     dword ptr [rbx], 0
0x180011695  jz      short loc_18001169D
0x180011697  call    cs:__imp_RevertToSelf
0x18001169d  test    edi, edi
0x18001169f  jnz     short loc_1800116B0
0x1800116a1  mov     rdx, [rsp+28h+pGPOList]; struct _GROUP_POLICY_OBJECTW *
0x1800116a6  mov     rcx, rsi; this
0x1800116a9  call    ?SetPolicyListFromGPOList@CManagedAppProcessor@@QEAAKPEAU_GROUP_POLICY_OBJECTW@@@Z; CManagedAppProcessor::SetPolicyListFromGPOList(_GROUP_POLICY_OBJECTW *)
0x1800116ae  mov     edi, eax
0x1800116b0  mov     rcx, [rsp+28h+pGPOList]; pGPOList
0x1800116b5  test    rcx, rcx
0x1800116b8  jz      short loc_1800116C0
0x1800116ba  call    cs:__imp_FreeGPOListW
0x1800116c0  test    edi, edi
0x1800116c2  jnz     short loc_1800116CC
0x1800116c4  mov     rcx, rsi; this
0x1800116c7  call    ?MergePolicyList@CManagedAppProcessor@@QEAAKXZ; CManagedAppProcessor::MergePolicyList(void)
0x1800116cc  mov     rbx, [rsp+28h+arg_8]
0x1800116d1  mov     eax, edi
0x1800116d3  mov     rsi, [rsp+28h+arg_10]
0x1800116d8  add     rsp, 20h
0x1800116dc  pop     rdi
0x1800116dd  retn
```
