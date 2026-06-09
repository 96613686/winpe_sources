# IsUserAdmin(bool &,void *)

- ea: `0x180025860`
- end: `0x180025971`
- name: `?IsUserAdmin@@YAKAEA_NPEAX@Z`
- size: `273`
- prototype: `unsigned int __fastcall(bool *, void *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180021070`
- `0x1800213a4`

## callees

- `0x18001b790`
- `0x180025860`
- `0x18002fb50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025909`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025928`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025909`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025928`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800258f9`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800258f9`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800258e7`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800258e7`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800258cd`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800258cd`

## string_xrefs

- `0x18002593c`: `base\winsat\common\winsatutilities.cpp`

## pseudocode

```c
__int64 __fastcall IsUserAdmin(bool *a1, void *a2)
{
  BOOL v3; // ebx
  DWORD LastError; // eax
  unsigned int v5; // edx
  char nSubAuthority2; // [rsp+20h] [rbp-60h]
  WINBOOL IsMember; // [rsp+60h] [rbp-20h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp-18h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp-10h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  SidToCheck = 0;
  IsMember = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &SidToCheck) )
  {
    v3 = CheckTokenMembership(0, SidToCheck, &IsMember);
    FreeSid(SidToCheck);
    if ( v3 )
    {
      *a1 = IsMember != 0;
      return 0;
    }
    LastError = GetLastError();
    v5 = 1548;
  }
  else
  {
    LastError = GetLastError();
    v5 = 1560;
  }
  return Record_Win32Error_w("base\\winsat\\common\\winsatutilities.cpp", v5, LastError, nSubAuthority2);
}

```

## disassembly

```asm
0x180025860  mov     r11, rsp
0x180025863  mov     [r11+10h], rbx
0x180025867  mov     [r11+18h], rsi
0x18002586b  mov     [r11+20h], rdi
0x18002586f  push    rbp
0x180025870  mov     rbp, rsp
0x180025873  sub     rsp, 80h
0x18002587a  mov     rax, cs:__security_cookie
0x180025881  xor     rax, rsp
0x180025884  mov     [rbp+var_8], rax
0x180025888  xor     esi, esi
0x18002588a  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x180025890  lea     rax, [rbp+SidToCheck]
0x180025894  mov     dword ptr [rbp+pIdentifierAuthority.Value], esi
0x180025897  mov     [r11-38h], rax
0x18002589b  mov     rdi, rcx
0x18002589e  mov     [rsp+80h+nSubAuthority7], esi; nSubAuthority7
0x1800258a2  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x1800258a6  mov     [rsp+80h+nSubAuthority6], esi; nSubAuthority6
0x1800258aa  lea     r8d, [rsi+20h]; nSubAuthority0
0x1800258ae  mov     [rsp+80h+nSubAuthority5], esi; nSubAuthority5
0x1800258b2  mov     r9d, 220h; nSubAuthority1
0x1800258b8  mov     [rsp+80h+nSubAuthority4], esi; nSubAuthority4
0x1800258bc  mov     dl, 2; nSubAuthorityCount
0x1800258be  mov     [rsp+80h+nSubAuthority3], esi; nSubAuthority3
0x1800258c2  mov     dword ptr [rsp+80h+nSubAuthority2], esi; char
0x1800258c6  mov     [rbp+SidToCheck], rsi
0x1800258ca  mov     [rbp+IsMember], esi
0x1800258cd  call    cs:__imp_AllocateAndInitializeSid
0x1800258d4  nop     dword ptr [rax+rax+00h]
0x1800258d9  test    eax, eax
0x1800258db  jz      short loc_180025928
0x1800258dd  mov     rdx, [rbp+SidToCheck]; SidToCheck
0x1800258e1  lea     r8, [rbp+IsMember]; IsMember
0x1800258e5  xor     ecx, ecx; TokenHandle
0x1800258e7  call    cs:__imp_CheckTokenMembership
0x1800258ee  nop     dword ptr [rax+rax+00h]
0x1800258f3  mov     rcx, [rbp+SidToCheck]; pSid
0x1800258f7  mov     ebx, eax
0x1800258f9  call    cs:__imp_FreeSid
0x180025900  nop     dword ptr [rax+rax+00h]
0x180025905  test    ebx, ebx
0x180025907  jnz     short loc_18002591C
0x180025909  call    cs:__imp_GetLastError
0x180025910  nop     dword ptr [rax+rax+00h]
0x180025915  mov     edx, 60Ch
0x18002591a  jmp     short loc_180025939
0x18002591c  cmp     [rbp+IsMember], esi
0x18002591f  setnz   al
0x180025922  mov     [rdi], al
0x180025924  xor     eax, eax
0x180025926  jmp     short loc_18002594B
0x180025928  call    cs:__imp_GetLastError
0x18002592f  nop     dword ptr [rax+rax+00h]
0x180025934  mov     edx, 618h; unsigned int
0x180025939  xor     r9d, r9d
0x18002593c  lea     rcx, aBaseWinsatComm; "base\\winsat\\common\\winsatutilities.c"...
0x180025943  mov     r8d, eax; unsigned int
0x180025946  call    Record_Win32Error_w
0x18002594b  mov     rcx, [rbp+var_8]
0x18002594f  xor     rcx, rsp; StackCookie
0x180025952  call    __security_check_cookie
0x180025957  lea     r11, [rsp+80h+var_s0]
0x18002595f  mov     rbx, [r11+18h]
0x180025963  mov     rsi, [r11+20h]
0x180025967  mov     rdi, [r11+28h]
0x18002596b  mov     rsp, r11
0x18002596e  pop     rbp
0x18002596f  retn
```
