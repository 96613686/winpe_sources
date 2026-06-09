# pSetupIsLocalSystem

- ea: `0x14000ac68`
- end: `0x14000ad5d`
- name: `pSetupIsLocalSystem`
- size: `245`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140009820`
- `0x14002ccdc`

## callees

- `0x14000ac48`
- `0x14000ac68`
- `0x140045f30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000ac9f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000acea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000ad2f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000ac9f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000acea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000ad2f`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14000ad27`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14000ad27`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x14000acfa`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x14000acfa`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x14000acd3`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x14000acd3`

## pseudocode

```c
_BOOL8 pSetupIsLocalSystem()
{
  DWORD LastError; // ebx
  WINBOOL IsMember; // [rsp+60h] [rbp-20h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp-18h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp-10h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  IsMember = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  SidToCheck = 0;
  SetLastError(0);
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &SidToCheck)
    || (LastError = pSpUtilsGetLastError()) == 0 )
  {
    SetLastError(0);
    if ( CheckTokenMembership(0, SidToCheck, &IsMember) )
    {
      LastError = 0;
    }
    else
    {
      LastError = pSpUtilsGetLastError();
      if ( LastError )
        goto LABEL_8;
    }
    if ( !IsMember )
      LastError = 1321;
  }
LABEL_8:
  if ( SidToCheck )
    FreeSid(SidToCheck);
  SetLastError(LastError);
  return LastError == 0;
}

```

## disassembly

```asm
0x14000ac68  mov     [rsp-8+arg_0], rbx
0x14000ac6d  mov     [rsp-8+arg_8], rdi
0x14000ac72  push    rbp
0x14000ac73  mov     rbp, rsp
0x14000ac76  sub     rsp, 80h
0x14000ac7d  mov     rax, cs:__security_cookie
0x14000ac84  xor     rax, rsp
0x14000ac87  mov     [rbp+var_8], rax
0x14000ac8b  xor     edi, edi
0x14000ac8d  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x14000ac93  xor     ecx, ecx; dwErrCode
0x14000ac95  mov     [rbp+IsMember], edi
0x14000ac98  mov     dword ptr [rbp+pIdentifierAuthority.Value], edi
0x14000ac9b  mov     [rbp+SidToCheck], rdi
0x14000ac9f  call    cs:__imp_SetLastError
0x14000aca5  lea     rax, [rbp+SidToCheck]
0x14000aca9  xor     r9d, r9d; nSubAuthority1
0x14000acac  mov     [rsp+80h+pSid], rax; pSid
0x14000acb1  lea     r8d, [rdi+12h]; nSubAuthority0
0x14000acb5  mov     [rsp+80h+nSubAuthority7], edi; nSubAuthority7
0x14000acb9  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x14000acbd  mov     [rsp+80h+nSubAuthority6], edi; nSubAuthority6
0x14000acc1  mov     dl, 1; nSubAuthorityCount
0x14000acc3  mov     [rsp+80h+nSubAuthority5], edi; nSubAuthority5
0x14000acc7  mov     [rsp+80h+nSubAuthority4], edi; nSubAuthority4
0x14000accb  mov     [rsp+80h+nSubAuthority3], edi; nSubAuthority3
0x14000accf  mov     [rsp+80h+nSubAuthority2], edi; nSubAuthority2
0x14000acd3  call    cs:__imp_AllocateAndInitializeSid
0x14000acd9  test    eax, eax
0x14000acdb  jnz     short loc_14000ACE8
0x14000acdd  call    _pSpUtilsGetLastError
0x14000ace2  mov     ebx, eax
0x14000ace4  test    eax, eax
0x14000ace6  jnz     short loc_14000AD1E
0x14000ace8  xor     ecx, ecx; dwErrCode
0x14000acea  call    cs:__imp_SetLastError
0x14000acf0  mov     rdx, [rbp+SidToCheck]; SidToCheck
0x14000acf4  lea     r8, [rbp+IsMember]; IsMember
0x14000acf8  xor     ecx, ecx; TokenHandle
0x14000acfa  call    cs:__imp_CheckTokenMembership
0x14000ad00  test    eax, eax
0x14000ad02  jz      short loc_14000AD08
0x14000ad04  mov     ebx, edi
0x14000ad06  jmp     short loc_14000AD13
0x14000ad08  call    _pSpUtilsGetLastError
0x14000ad0d  mov     ebx, eax
0x14000ad0f  test    eax, eax
0x14000ad11  jnz     short loc_14000AD1E
0x14000ad13  cmp     [rbp+IsMember], edi
0x14000ad16  mov     eax, 529h
0x14000ad1b  cmovz   ebx, eax
0x14000ad1e  mov     rcx, [rbp+SidToCheck]; pSid
0x14000ad22  test    rcx, rcx
0x14000ad25  jz      short loc_14000AD2D
0x14000ad27  call    cs:__imp_FreeSid
0x14000ad2d  mov     ecx, ebx; dwErrCode
0x14000ad2f  call    cs:__imp_SetLastError
0x14000ad35  test    ebx, ebx
0x14000ad37  mov     eax, edi
0x14000ad39  setz    al
0x14000ad3c  mov     rcx, [rbp+var_8]
0x14000ad40  xor     rcx, rsp; StackCookie
0x14000ad43  call    __security_check_cookie
0x14000ad48  lea     r11, [rsp+80h+var_s0]
0x14000ad50  mov     rbx, [r11+10h]
0x14000ad54  mov     rdi, [r11+18h]
0x14000ad58  mov     rsp, r11
0x14000ad5b  pop     rbp
0x14000ad5c  retn
```
