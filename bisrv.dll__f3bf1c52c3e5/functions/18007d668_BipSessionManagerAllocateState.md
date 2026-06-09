# BipSessionManagerAllocateState

- ea: `0x18007d668`
- end: `0x18007d6ff`
- name: `BipSessionManagerAllocateState`
- size: `151`
- prototype: `__int64 __fastcall(struct _BI_GLOBALS *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18007a320`

## callees

- `0x180050978`
- `0x18006d864`
- `0x18007d668`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d6ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d6b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d6be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d6ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d6b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d6be`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18007d6a2`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18007d6e7`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18007d6a2`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18007d6e7`

## pseudocode

```c
signed int __fastcall BipSessionManagerAllocateState(struct _BI_GLOBALS *a1)
{
  signed int result; // eax
  DWORD cbSid; // [rsp+30h] [rbp+8h] BYREF

  cbSid = 0;
  result = BipSessionNotifyContextAllocateState((struct _BI_GLOBALS *)((char *)a1 + 1832));
  if ( result >= 0 )
  {
    cbSid = 68;
    if ( CreateWellKnownSid(WinLocalSystemSid, 0, (char *)a1 + 2036, &cbSid)
      && (cbSid = 68, CreateWellKnownSid(WinLocalServiceSid, 0, (char *)a1 + 2104, &cbSid)) )
    {
      return BipInitializeSessionManagerDsmaSid(a1);
    }
    else if ( (int)GetLastError() > 0 )
    {
      return (unsigned __int16)GetLastError() | 0xC0070000;
    }
    else
    {
      return GetLastError();
    }
  }
  return result;
}

```

## disassembly

```asm
0x18007d668  push    rbx
0x18007d66a  sub     rsp, 20h
0x18007d66e  mov     rbx, rcx
0x18007d671  mov     [rsp+28h+cbSid], 0
0x18007d679  add     rcx, 728h; struct _BI_SESSION_NOTIFY_CONTEXT *
0x18007d680  call    ?BipSessionNotifyContextAllocateState@@YAJPEAU_BI_SESSION_NOTIFY_CONTEXT@@@Z; BipSessionNotifyContextAllocateState(_BI_SESSION_NOTIFY_CONTEXT *)
0x18007d685  test    eax, eax
0x18007d687  js      short loc_18007D6F9
0x18007d689  xor     edx, edx; DomainSid
0x18007d68b  mov     [rsp+28h+cbSid], 44h ; 'D'
0x18007d693  lea     r8, [rbx+7F4h]; pSid
0x18007d69a  lea     r9, [rsp+28h+cbSid]; cbSid
0x18007d69f  lea     ecx, [rdx+16h]; WellKnownSidType
0x18007d6a2  call    cs:__imp_CreateWellKnownSid
0x18007d6a8  test    eax, eax
0x18007d6aa  jnz     short loc_18007D6CE
0x18007d6ac  call    cs:__imp_GetLastError
0x18007d6b2  test    eax, eax
0x18007d6b4  jg      short loc_18007D6BE
0x18007d6b6  call    cs:__imp_GetLastError
0x18007d6bc  jmp     short loc_18007D6F9
0x18007d6be  call    cs:__imp_GetLastError
0x18007d6c4  movzx   eax, ax
0x18007d6c7  or      eax, 0C0070000h
0x18007d6cc  jmp     short loc_18007D6F9
0x18007d6ce  xor     edx, edx; DomainSid
0x18007d6d0  mov     [rsp+28h+cbSid], 44h ; 'D'
0x18007d6d8  lea     r8, [rbx+838h]; pSid
0x18007d6df  lea     r9, [rsp+28h+cbSid]; cbSid
0x18007d6e4  lea     ecx, [rdx+17h]; WellKnownSidType
0x18007d6e7  call    cs:__imp_CreateWellKnownSid
0x18007d6ed  test    eax, eax
0x18007d6ef  jz      short loc_18007D6AC
0x18007d6f1  mov     rcx, rbx; struct _BI_GLOBALS *
0x18007d6f4  call    ?BipInitializeSessionManagerDsmaSid@@YAJPEAU_BI_GLOBALS@@@Z; BipInitializeSessionManagerDsmaSid(_BI_GLOBALS *)
0x18007d6f9  add     rsp, 20h
0x18007d6fd  pop     rbx
0x18007d6fe  retn
```
