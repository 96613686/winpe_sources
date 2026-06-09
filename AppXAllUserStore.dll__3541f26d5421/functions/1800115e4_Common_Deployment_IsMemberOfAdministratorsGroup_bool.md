# Common::Deployment::IsMemberOfAdministratorsGroup(bool *)

- ea: `0x1800115e4`
- end: `0x1800116b4`
- name: `?IsMemberOfAdministratorsGroup@Deployment@Common@@YAJPEA_N@Z`
- size: `208`
- prototype: `__int64 __fastcall(Common::Deployment *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001187c`

## callees

- `0x1800115e4`
- `0x18001a324`
- `0x18001a604`
- `0x18004c9d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001165d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001165d`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180011653`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180011653`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18001161c`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18001161c`

## string_xrefs

- `0x18001162e`: `onecore\admin\appmodel\common\admincheck.cpp`
- `0x180011674`: `onecore\admin\appmodel\common\admincheck.cpp`

## pseudocode

```c
int __fastcall Common::Deployment::IsMemberOfAdministratorsGroup(Common::Deployment *this, bool *a2)
{
  const char *v3; // r9
  DWORD LastError; // eax
  char v6; // al
  WINBOOL IsMember; // [rsp+20h] [rbp-78h] BYREF
  DWORD cbSid[3]; // [rsp+24h] [rbp-74h] BYREF
  _BYTE pSid[80]; // [rsp+30h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  *(_BYTE *)this = 0;
  cbSid[0] = 68;
  if ( !CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, pSid, cbSid) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x21,
             (unsigned int)"onecore\\admin\\appmodel\\common\\admincheck.cpp",
             v3);
  IsMember = 0;
  if ( CheckTokenMembership(0, pSid, &IsMember) )
  {
    v6 = 1;
    if ( IsMember == 1 )
    {
LABEL_9:
      *(_BYTE *)this = v6;
      return 0;
    }
LABEL_8:
    v6 = 0;
    goto LABEL_9;
  }
  LastError = GetLastError();
  if ( LastError == 5 )
    goto LABEL_8;
  if ( LastError )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x30,
             (unsigned int)"onecore\\admin\\appmodel\\common\\admincheck.cpp",
             (const char *)LastError,
             IsMember);
  return 0;
}

```

## disassembly

```asm
0x1800115e4  push    rbx
0x1800115e6  sub     rsp, 90h
0x1800115ed  mov     rax, cs:__security_cookie
0x1800115f4  xor     rax, rsp
0x1800115f7  mov     [rsp+98h+var_18], rax
0x1800115ff  xor     edx, edx; DomainSid
0x180011601  mov     byte ptr [rcx], 0
0x180011604  mov     rbx, rcx
0x180011607  mov     [rsp+98h+cbSid], 44h ; 'D'
0x18001160f  lea     r9, [rsp+98h+cbSid]; cbSid
0x180011614  lea     r8, [rsp+98h+pSid]; pSid
0x180011619  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x18001161c  call    cs:__imp_CreateWellKnownSid
0x180011622  test    eax, eax
0x180011624  jnz     short loc_18001163F
0x180011626  mov     rcx, [rsp+98h]; this
0x18001162e  lea     r8, aOnecoreAdminAp_3; "onecore\\admin\\appmodel\\common\\admin"...
0x180011635  lea     edx, [rax+21h]; void *
0x180011638  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001163d  jmp     short loc_18001169B
0x18001163f  lea     r8, [rsp+98h+IsMember]; IsMember
0x180011644  mov     [rsp+98h+IsMember], 0; unsigned int
0x18001164c  lea     rdx, [rsp+98h+pSid]; SidToCheck
0x180011651  xor     ecx, ecx; TokenHandle
0x180011653  call    cs:__imp_CheckTokenMembership
0x180011659  test    eax, eax
0x18001165b  jnz     short loc_18001168A
0x18001165d  call    cs:__imp_GetLastError
0x180011663  cmp     eax, 5
0x180011666  jz      short loc_180011695
0x180011668  test    eax, eax
0x18001166a  jz      short loc_180011699
0x18001166c  mov     rcx, [rsp+98h]; this
0x180011674  lea     r8, aOnecoreAdminAp_3; "onecore\\admin\\appmodel\\common\\admin"...
0x18001167b  mov     r9d, eax; char *
0x18001167e  mov     edx, 30h ; '0'; void *
0x180011683  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180011688  jmp     short loc_18001169B
0x18001168a  mov     eax, 1
0x18001168f  cmp     [rsp+98h+IsMember], eax
0x180011693  jz      short loc_180011697
0x180011695  xor     al, al
0x180011697  mov     [rbx], al
0x180011699  xor     eax, eax
0x18001169b  mov     rcx, [rsp+98h+var_18]
0x1800116a3  xor     rcx, rsp; StackCookie
0x1800116a6  call    __security_check_cookie
0x1800116ab  add     rsp, 90h
0x1800116b2  pop     rbx
0x1800116b3  retn
```
