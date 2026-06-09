# CLanguageProfileHelper::CreateUserSid(ushort const *)

- ea: `0x18003be14`
- end: `0x18003bead`
- name: `?CreateUserSid@CLanguageProfileHelper@@CAPEAXPEBG@Z`
- size: `153`
- prototype: `void *__fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18002e18c`

## callees

- `0x180004c00`
- `0x18003be14`
- `0x18003bec0`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x18003be67`
- `KERNEL32!LocalAlloc` at `0x18003be67`
- `KERNEL32!LocalFree` at `0x18003be9a`
- `KERNEL32!LocalFree` at `0x18003be9a`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18003be4b`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18003be84`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18003be4b`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18003be84`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18003be2b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18003be2b`

## pseudocode

```c
PSID __fastcall CLanguageProfileHelper::CreateUserSid(const unsigned __int16 *a1)
{
  PSID result; // rax
  BOOL v2; // eax
  DWORD cbSid; // [rsp+30h] [rbp+8h] BYREF
  PSID Sid; // [rsp+38h] [rbp+10h] BYREF

  Sid = 0;
  if ( *a1 )
  {
    if ( !ConvertStringSidToSidW(a1, &Sid) )
      return 0;
  }
  else
  {
    cbSid = 0;
    if ( !CreateWellKnownSid(WinLocalSystemSid, 0, 0, &cbSid) && (unsigned int)ResultFromKnownLastError() == -2147024774 )
    {
      result = LocalAlloc(0, cbSid);
      Sid = result;
      if ( !result )
        return result;
      v2 = CreateWellKnownSid(WinLocalSystemSid, 0, result, &cbSid);
      if ( (int)ResultFromWin32Bool(v2) < 0 )
      {
        LocalFree(Sid);
        return 0;
      }
    }
  }
  return Sid;
}

```

## disassembly

```asm
0x18003be14  push    rbx
0x18003be16  sub     rsp, 20h
0x18003be1a  xor     ebx, ebx
0x18003be1c  mov     [rsp+28h+Sid], rbx
0x18003be21  cmp     [rcx], bx
0x18003be24  jz      short loc_18003BE3A
0x18003be26  lea     rdx, [rsp+28h+Sid]; Sid
0x18003be2b  call    cs:__imp_ConvertStringSidToSidW
0x18003be31  test    eax, eax
0x18003be33  jnz     short loc_18003BEA2
0x18003be35  mov     rax, rbx
0x18003be38  jmp     short loc_18003BEA7
0x18003be3a  xor     edx, edx; DomainSid
0x18003be3c  mov     [rsp+28h+cbSid], ebx
0x18003be40  lea     r9, [rsp+28h+cbSid]; cbSid
0x18003be45  xor     r8d, r8d; pSid
0x18003be48  lea     ecx, [rdx+16h]; WellKnownSidType
0x18003be4b  call    cs:__imp_CreateWellKnownSid
0x18003be51  test    eax, eax
0x18003be53  jnz     short loc_18003BEA2
0x18003be55  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18003be5a  cmp     eax, 8007007Ah
0x18003be5f  jnz     short loc_18003BEA2
0x18003be61  mov     edx, [rsp+28h+cbSid]; uBytes
0x18003be65  xor     ecx, ecx; uFlags
0x18003be67  call    cs:__imp_LocalAlloc
0x18003be6d  mov     [rsp+28h+Sid], rax
0x18003be72  test    rax, rax
0x18003be75  jz      short loc_18003BEA7
0x18003be77  xor     edx, edx; DomainSid
0x18003be79  lea     r9, [rsp+28h+cbSid]; cbSid
0x18003be7e  mov     r8, rax; pSid
0x18003be81  lea     ecx, [rdx+16h]; WellKnownSidType
0x18003be84  call    cs:__imp_CreateWellKnownSid
0x18003be8a  mov     ecx, eax; int
0x18003be8c  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x18003be91  test    eax, eax
0x18003be93  jns     short loc_18003BEA2
0x18003be95  mov     rcx, [rsp+28h+Sid]; hMem
0x18003be9a  call    cs:__imp_LocalFree
0x18003bea0  jmp     short loc_18003BE35
0x18003bea2  mov     rax, [rsp+28h+Sid]
0x18003bea7  add     rsp, 20h
0x18003beab  pop     rbx
0x18003beac  retn
```
