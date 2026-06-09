# Tsf3OverrideUtil::IsRunningAsSystem(void)

- ea: `0x18004f4a0`
- end: `0x18004f559`
- name: `?IsRunningAsSystem@Tsf3OverrideUtil@@YA_NXZ`
- size: `185`
- prototype: `bool __fastcall(Tsf3OverrideUtil *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18000a398`
- `0x180099c20`

## callees

- `0x18004f4a0`
- `0x1800664d8`
- `0x180066a54`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x18004f4b4`
- `KERNEL32!LocalAlloc` at `0x18004f4b4`
- `KERNEL32!LocalFree` at `0x18004f544`
- `KERNEL32!LocalFree` at `0x18004f544`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18004f4ed`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18004f4ed`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18004f513`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18004f513`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall Tsf3OverrideUtil::IsRunningAsSystem(Tsf3OverrideUtil *this)
{
  bool v1; // di
  HLOCAL v2; // rax
  const char *v3; // r9
  void *v4; // rbx
  BOOL v5; // eax
  const char *v6; // r9
  wil::details::in1diag3 *v7; // rcx
  __int64 v8; // rdx
  BOOL v9; // eax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  WINBOOL IsMember; // [rsp+30h] [rbp+8h] BYREF
  DWORD cbSid; // [rsp+38h] [rbp+10h] BYREF

  v1 = 0;
  v2 = LocalAlloc(0, 0x44u);
  v4 = v2;
  if ( !v2 )
  {
    wil::details::in1diag3::_Log_NullAlloc(
      retaddr,
      (void *)0x75,
      (unsigned int)"onecore\\internal\\shell\\inc\\Tsf3OverrideUtil.h",
      v3);
    goto LABEL_9;
  }
  cbSid = 68;
  v5 = CreateWellKnownSid(WinLocalSystemSid, 0, v2, &cbSid);
  v7 = retaddr;
  if ( !v5 )
  {
    v8 = 124;
LABEL_7:
    wil::details::in1diag3::_Log_GetLastError(
      v7,
      (void *)v8,
      (unsigned int)"onecore\\internal\\shell\\inc\\Tsf3OverrideUtil.h",
      v6);
    goto LABEL_9;
  }
  IsMember = 0;
  v9 = CheckTokenMembership(0, v4, &IsMember);
  v7 = retaddr;
  if ( !v9 )
  {
    v8 = 127;
    goto LABEL_7;
  }
  v1 = IsMember != 0;
LABEL_9:
  if ( v4 )
    LocalFree(v4);
  return v1;
}

```

## disassembly

```asm
0x18004f4a0  mov     [rsp+arg_10], rbx
0x18004f4a5  push    rdi
0x18004f4a6  sub     rsp, 20h
0x18004f4aa  xor     dil, dil
0x18004f4ad  mov     edx, 44h ; 'D'; uBytes
0x18004f4b2  xor     ecx, ecx; uFlags
0x18004f4b4  call    cs:__imp_LocalAlloc
0x18004f4ba  mov     rbx, rax
0x18004f4bd  mov     rcx, [rsp+28h]; this
0x18004f4c2  test    rax, rax
0x18004f4c5  jnz     short loc_18004F4D8
0x18004f4c7  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\Tsf3Over"...
0x18004f4ce  lea     edx, [rax+75h]; void *
0x18004f4d1  call    ?_Log_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_NullAlloc(void *,uint,char const *)
0x18004f4d6  jmp     short loc_18004F53C
0x18004f4d8  mov     [rsp+28h+cbSid], 44h ; 'D'
0x18004f4e0  lea     r9, [rsp+28h+cbSid]; cbSid
0x18004f4e5  mov     r8, rbx; pSid
0x18004f4e8  xor     edx, edx; DomainSid
0x18004f4ea  lea     ecx, [rdx+16h]; WellKnownSidType
0x18004f4ed  call    cs:__imp_CreateWellKnownSid
0x18004f4f3  mov     rcx, [rsp+28h]
0x18004f4f8  test    eax, eax
0x18004f4fa  jnz     short loc_18004F501
0x18004f4fc  lea     edx, [rax+7Ch]
0x18004f4ff  jmp     short loc_18004F525
0x18004f501  mov     [rsp+28h+IsMember], 0
0x18004f509  lea     r8, [rsp+28h+IsMember]; IsMember
0x18004f50e  mov     rdx, rbx; SidToCheck
0x18004f511  xor     ecx, ecx; TokenHandle
0x18004f513  call    cs:__imp_CheckTokenMembership
0x18004f519  mov     rcx, [rsp+28h]; this
0x18004f51e  test    eax, eax
0x18004f520  jnz     short loc_18004F533
0x18004f522  lea     edx, [rax+7Fh]; void *
0x18004f525  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\Tsf3Over"...
0x18004f52c  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18004f531  jmp     short loc_18004F53C
0x18004f533  cmp     [rsp+28h+IsMember], 0
0x18004f538  setnz   dil
0x18004f53c  test    rbx, rbx
0x18004f53f  jz      short loc_18004F54B
0x18004f541  mov     rcx, rbx; hMem
0x18004f544  call    cs:__imp_LocalFree
0x18004f54a  nop
0x18004f54b  mov     al, dil
0x18004f54e  mov     rbx, [rsp+28h+arg_10]
0x18004f553  add     rsp, 20h
0x18004f557  pop     rdi
0x18004f558  retn
```
