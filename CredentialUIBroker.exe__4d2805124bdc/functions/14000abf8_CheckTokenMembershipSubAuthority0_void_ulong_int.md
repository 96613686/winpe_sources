# CheckTokenMembershipSubAuthority0(void *,ulong,int *)

- ea: `0x14000abf8`
- end: `0x14000acc3`
- name: `?CheckTokenMembershipSubAuthority0@@YAJPEAXKPEAH@Z`
- size: `203`
- prototype: `__int64 __fastcall(void *, DWORD, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400137d4`

## callees

- `0x140003620`
- `0x1400091b4`
- `0x14000abf8`
- `0x1400136dc`

## import_xrefs

- `ADVAPI32!CheckTokenMembership` at `0x14000ac72`
- `ADVAPI32!CheckTokenMembership` at `0x14000ac72`
- `ADVAPI32!AllocateAndInitializeSid` at `0x14000ac59`
- `ADVAPI32!AllocateAndInitializeSid` at `0x14000ac59`

## string_xrefs

- `0x14000ac87`: `shellcommon\internal\shell\inc\CredUIApiCommon.h`

## pseudocode

```c
__int64 __fastcall CheckTokenMembershipSubAuthority0(void *a1, DWORD a2, int *a3)
{
  const char *v4; // r9
  __int64 v5; // rdx
  unsigned int LastError; // ebx
  PSID SidToCheck; // [rsp+60h] [rbp-28h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v9; // [rsp+68h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  *(_WORD *)&v9.Value[4] = 1280;
  *a3 = 0;
  *(_DWORD *)v9.Value = 0;
  SidToCheck = 0;
  if ( AllocateAndInitializeSid(&v9, 1u, a2, 0, 0, 0, 0, 0, 0, 0, &SidToCheck) )
  {
    if ( CheckTokenMembership(0, SidToCheck, a3) )
    {
      LastError = 0;
      goto LABEL_7;
    }
    v5 = 73;
  }
  else
  {
    v5 = 71;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)v5,
                (unsigned int)"shellcommon\\internal\\shell\\inc\\CredUIApiCommon.h",
                v4);
LABEL_7:
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&SidToCheck);
  return LastError;
}

```

## disassembly

```asm
0x14000abf8  mov     r11, rsp
0x14000abfb  mov     [r11+8], rbx
0x14000abff  push    rdi
0x14000ac00  sub     rsp, 80h
0x14000ac07  mov     rax, cs:__security_cookie
0x14000ac0e  xor     rax, rsp
0x14000ac11  mov     [rsp+88h+var_18], rax
0x14000ac16  xor     edi, edi
0x14000ac18  mov     [rsp+88h+var_1C], 500h
0x14000ac1f  lea     rax, [r11-28h]
0x14000ac23  mov     [r8], edi
0x14000ac26  mov     [r11-38h], rax
0x14000ac2a  lea     rcx, [r11-20h]; pIdentifierAuthority
0x14000ac2e  mov     [rsp+88h+nSubAuthority7], edi; nSubAuthority7
0x14000ac32  mov     rbx, r8
0x14000ac35  mov     [rsp+88h+nSubAuthority6], edi; nSubAuthority6
0x14000ac39  mov     r8d, edx; nSubAuthority0
0x14000ac3c  mov     [rsp+88h+nSubAuthority5], edi; nSubAuthority5
0x14000ac40  xor     r9d, r9d; nSubAuthority1
0x14000ac43  mov     [rsp+88h+nSubAuthority4], edi; nSubAuthority4
0x14000ac47  mov     dl, 1; nSubAuthorityCount
0x14000ac49  mov     [rsp+88h+nSubAuthority3], edi; nSubAuthority3
0x14000ac4d  mov     [rsp+88h+nSubAuthority2], edi; nSubAuthority2
0x14000ac51  mov     [rsp+88h+var_20], edi
0x14000ac55  mov     [r11-28h], rdi
0x14000ac59  call    cs:__imp_AllocateAndInitializeSid
0x14000ac5f  test    eax, eax
0x14000ac61  jnz     short loc_14000AC68
0x14000ac63  lea     edx, [rdi+47h]
0x14000ac66  jmp     short loc_14000AC7F
0x14000ac68  mov     rdx, [rsp+88h+SidToCheck]; SidToCheck
0x14000ac6d  mov     r8, rbx; IsMember
0x14000ac70  xor     ecx, ecx; TokenHandle
0x14000ac72  call    cs:__imp_CheckTokenMembership
0x14000ac78  test    eax, eax
0x14000ac7a  jnz     short loc_14000AC97
0x14000ac7c  lea     edx, [rax+49h]; void *
0x14000ac7f  mov     rcx, [rsp+88h]; this
0x14000ac87  lea     r8, aShellcommonInt; "shellcommon\\internal\\shell\\inc\\Cred"...
0x14000ac8e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000ac93  mov     ebx, eax
0x14000ac95  jmp     short loc_14000AC99
0x14000ac97  mov     ebx, edi
0x14000ac99  lea     rcx, [rsp+88h+SidToCheck]
0x14000ac9e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14000aca3  mov     eax, ebx
0x14000aca5  mov     rcx, [rsp+88h+var_18]
0x14000acaa  xor     rcx, rsp; StackCookie
0x14000acad  call    __security_check_cookie
0x14000acb2  mov     rbx, [rsp+88h+arg_0]
0x14000acba  add     rsp, 80h
0x14000acc1  pop     rdi
0x14000acc2  retn
```
