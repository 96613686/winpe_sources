# wil::test_token_membership_nothrow<ulong,ulong>(bool *,void *,_SID_IDENTIFIER_AUTHORITY const &,ulong &&,ulong &&)

- ea: `0x18000e84c`
- end: `0x18000e8ed`
- name: `??$test_token_membership_nothrow@KK@wil@@YAJPEA_NPEAXAEBU_SID_IDENTIFIER_AUTHORITY@@$$QEAK3@Z`
- size: `161`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800102b0`

## callees

- `0x180006f60`
- `0x18000aff4`
- `0x18000e84c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000e8a5`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000e8a5`

## string_xrefs

- `0x18000e8ba`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::test_token_membership_nothrow<unsigned long,unsigned long>(
        bool *a1,
        __int64 a2,
        int *a3,
        int *a4,
        int *a5)
{
  const char *v6; // r9
  WINBOOL IsMember; // [rsp+20h] [rbp-28h] BYREF
  __int16 SidToCheck; // [rsp+28h] [rbp-20h] BYREF
  int v10; // [rsp+2Ah] [rbp-1Eh]
  __int16 v11; // [rsp+2Eh] [rbp-1Ah]
  int v12; // [rsp+30h] [rbp-18h]
  int v13; // [rsp+34h] [rbp-14h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *a1 = 0;
  v10 = *a3;
  v11 = *((_WORD *)a3 + 2);
  v12 = *a4;
  SidToCheck = 513;
  IsMember = 0;
  v13 = *a5;
  if ( !CheckTokenMembership(0, &SidToCheck, &IsMember) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x27C,
             (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
             v6);
  *a1 = IsMember != 0;
  return 0;
}

```

## disassembly

```asm
0x18000e84c  push    rbx
0x18000e84e  sub     rsp, 40h
0x18000e852  mov     rax, cs:__security_cookie
0x18000e859  xor     rax, rsp
0x18000e85c  mov     [rsp+48h+var_10], rax
0x18000e861  mov     byte ptr [rcx], 0
0x18000e864  lea     rdx, [rsp+48h+SidToCheck]; SidToCheck
0x18000e869  mov     eax, [r8]
0x18000e86c  mov     rbx, rcx
0x18000e86f  mov     [rsp+48h+var_1E], eax
0x18000e873  movzx   eax, word ptr [r8+4]
0x18000e878  lea     r8, [rsp+48h+IsMember]; IsMember
0x18000e87d  mov     [rsp+48h+var_1A], ax
0x18000e882  mov     eax, [r9]
0x18000e885  mov     [rsp+48h+var_18], eax
0x18000e889  mov     rax, [rsp+48h+arg_20]
0x18000e88e  mov     [rsp+48h+SidToCheck], 201h
0x18000e895  mov     [rsp+48h+IsMember], 0
0x18000e89d  mov     ecx, [rax]
0x18000e89f  mov     [rsp+48h+var_14], ecx
0x18000e8a3  xor     ecx, ecx; TokenHandle
0x18000e8a5  call    cs:__imp_CheckTokenMembership
0x18000e8ac  nop     dword ptr [rax+rax+00h]
0x18000e8b1  test    eax, eax
0x18000e8b3  jnz     short loc_18000E8CD
0x18000e8b5  mov     rcx, [rsp+48h]; this
0x18000e8ba  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000e8c1  mov     edx, 27Ch; void *
0x18000e8c6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000e8cb  jmp     short loc_18000E8D9
0x18000e8cd  cmp     [rsp+48h+IsMember], 0
0x18000e8d2  setnz   al
0x18000e8d5  mov     [rbx], al
0x18000e8d7  xor     eax, eax
0x18000e8d9  mov     rcx, [rsp+48h+var_10]
0x18000e8de  xor     rcx, rsp; StackCookie
0x18000e8e1  call    __security_check_cookie
0x18000e8e6  add     rsp, 40h
0x18000e8ea  pop     rbx
0x18000e8eb  retn
```
