# std::_Ref_count_obj2<ConnectedStorage::ContextImpersonator>::_Ref_count_obj2<ConnectedStorage::ContextImpersonator>(void * &)

- ea: `0x1800282b0`
- end: `0x180028309`
- name: `??$?0AEAPEAX@?$_Ref_count_obj2@VContextImpersonator@ConnectedStorage@@@std@@QEAA@AEAPEAX@Z`
- size: `89`
- prototype: `__int64 __fastcall(__int64, HANDLE *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800295a4`

## callees

- `0x18000aae4`
- `0x1800282b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800282db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800282db`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800282d1`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800282d1`

## pseudocode

```c
__int64 __fastcall std::_Ref_count_obj2<ConnectedStorage::ContextImpersonator>::_Ref_count_obj2<ConnectedStorage::ContextImpersonator>(
        __int64 a1,
        HANDLE *a2)
{
  signed int LastError; // eax
  const unsigned __int16 *v4; // r8
  bool v5; // sf

  *(_DWORD *)(a1 + 8) = 1;
  *(_DWORD *)(a1 + 12) = 1;
  *(_QWORD *)a1 = &std::_Ref_count_obj2<ConnectedStorage::ContextImpersonator>::`vftable';
  if ( !ImpersonateLoggedOnUser(*a2) )
  {
    LastError = GetLastError();
    v5 = LastError < 0;
    if ( LastError > 0 )
    {
      LastError = (unsigned __int16)LastError | 0x80070000;
      v5 = LastError < 0;
    }
    if ( v5 )
      ConnectedStorage::ReportErrorAndThrow(
        (ConnectedStorage *)(unsigned int)LastError,
        (int)L"HRESULT_FROM_WIN32(GetLastError())",
        v4);
  }
  return a1;
}

```

## disassembly

```asm
0x1800282b0  push    rbx
0x1800282b2  sub     rsp, 20h
0x1800282b6  mov     eax, 1
0x1800282bb  mov     rbx, rcx
0x1800282be  mov     [rcx+8], eax
0x1800282c1  mov     [rcx+0Ch], eax
0x1800282c4  lea     rax, ??_7?$_Ref_count_obj2@VContextImpersonator@ConnectedStorage@@@std@@6B@; const std::_Ref_count_obj2<ConnectedStorage::ContextImpersonator>::`vftable'
0x1800282cb  mov     [rcx], rax
0x1800282ce  mov     rcx, [rdx]; hToken
0x1800282d1  call    cs:__imp_ImpersonateLoggedOnUser
0x1800282d7  test    eax, eax
0x1800282d9  jnz     short loc_1800282F1
0x1800282db  call    cs:__imp_GetLastError
0x1800282e1  test    eax, eax
0x1800282e3  jle     short loc_1800282EF
0x1800282e5  movzx   eax, ax
0x1800282e8  or      eax, 80070000h
0x1800282ed  test    eax, eax
0x1800282ef  js      short loc_1800282FA
0x1800282f1  mov     rax, rbx
0x1800282f4  add     rsp, 20h
0x1800282f8  pop     rbx
0x1800282f9  retn
0x1800282fa  lea     rdx, aHresultFromWin; "HRESULT_FROM_WIN32(GetLastError())"
0x180028301  mov     ecx, eax; this
0x180028303  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
```
