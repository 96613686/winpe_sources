# IsStringSid(ushort const *,KnownSid *)

- ea: `0x1800512a8`
- end: `0x1800513ca`
- name: `?IsStringSid@@YA_NPEBGPEAUKnownSid@@@Z`
- size: `290`
- prototype: `bool __fastcall(LPCWSTR StringSid, PSID *Sid)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180056220`

## callees

- `0x180044f30`
- `0x180050bc8`
- `0x180050c00`
- `0x1800512a8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800512f6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800512f6`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180051382`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180051382`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18005131e`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18005131e`

## pseudocode

```c
char __fastcall IsStringSid(LPCWSTR StringSid, PSID *Sid)
{
  unsigned int v2; // ebx
  char v5; // r15
  DWORD nSubAuthority4; // ebx
  DWORD nSubAuthority3; // edi
  DWORD nSubAuthority2; // esi
  DWORD Data1; // r14d
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+60h] [rbp-20h] BYREF
  GUID iid; // [rsp+68h] [rbp-18h] BYREF

  v2 = 0;
  v5 = 1;
  while ( v2 < 4 )
  {
    if ( !(unsigned int)_o__wcsicmp(StringSid, off_180079CC0[2 * v2]) )
    {
      KnownSid::ConvertSid(Sid, off_180079CC0[2 * v2 + 1]);
      return v5;
    }
    ++v2;
  }
  if ( IIDFromString(StringSid, &iid) >= 0 )
  {
    nSubAuthority4 = *(_DWORD *)&iid.Data4[4];
    nSubAuthority3 = *(_DWORD *)iid.Data4;
    nSubAuthority2 = *(_DWORD *)&iid.Data2;
    Data1 = iid.Data1;
    *(_DWORD *)pIdentifierAuthority.Value = 0;
    *(_WORD *)&pIdentifierAuthority.Value[4] = 3840;
    KnownSid::Cleanup((KnownSid *)Sid);
    if ( !AllocateAndInitializeSid(
            &pIdentifierAuthority,
            5u,
            3u,
            Data1,
            nSubAuthority2,
            nSubAuthority3,
            nSubAuthority4,
            0,
            0,
            0,
            Sid) )
      return 0;
    *((_BYTE *)Sid + 8) = 1;
    return v5;
  }
  return KnownSid::ConvertSid(Sid, StringSid);
}

```

## disassembly

```asm
0x1800512a8  mov     [rsp-28h+arg_10], rbx
0x1800512ad  mov     [rsp-28h+arg_18], rsi
0x1800512b2  push    rbp
0x1800512b3  push    rdi
0x1800512b4  push    r13
0x1800512b6  push    r14
0x1800512b8  push    r15
0x1800512ba  mov     rbp, rsp
0x1800512bd  sub     rsp, 80h
0x1800512c4  mov     rax, cs:__security_cookie
0x1800512cb  xor     rax, rsp
0x1800512ce  mov     [rbp+var_8], rax
0x1800512d2  xor     ebx, ebx
0x1800512d4  lea     r14, off_180079CC0; "location"
0x1800512db  mov     r13, rdx
0x1800512de  mov     rdi, rcx
0x1800512e1  lea     r15d, [rbx+1]
0x1800512e5  mov     rcx, rdi; lpsz
0x1800512e8  cmp     ebx, 4
0x1800512eb  jnb     short loc_18005131A
0x1800512ed  mov     esi, ebx
0x1800512ef  add     rsi, rsi
0x1800512f2  mov     rdx, [r14+rsi*8]
0x1800512f6  call    cs:__imp__o__wcsicmp
0x1800512fc  test    eax, eax
0x1800512fe  jz      short loc_180051305
0x180051300  add     ebx, r15d
0x180051303  jmp     short loc_1800512E5
0x180051305  mov     rdx, [r14+rsi*8+8]; StringSid
0x18005130a  mov     rcx, r13; Sid
0x18005130d  call    ?ConvertSid@KnownSid@@QEAA_NPEBG@Z; KnownSid::ConvertSid(ushort const *)
0x180051312  mov     al, r15b
0x180051315  jmp     loc_1800513A2
0x18005131a  lea     rdx, [rbp+iid]; lpiid
0x18005131e  call    cs:__imp_IIDFromString
0x180051324  mov     rcx, r13; Sid
0x180051327  test    eax, eax
0x180051329  js      short loc_18005139A
0x18005132b  mov     ebx, dword ptr [rbp+iid.Data4+4]
0x18005132e  mov     edi, dword ptr [rbp+iid.Data4]
0x180051331  mov     esi, dword ptr [rbp+iid.Data2]
0x180051334  mov     r14d, [rbp+iid.Data1]
0x180051338  mov     dword ptr [rbp+pIdentifierAuthority.Value], 0
0x18005133f  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 0F00h
0x180051345  call    ?Cleanup@KnownSid@@QEAAXXZ; KnownSid::Cleanup(void)
0x18005134a  mov     [rsp+80h+pSid], r13; pSid
0x18005134f  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x180051353  mov     [rsp+80h+nSubAuthority7], 0; nSubAuthority7
0x18005135b  mov     r9d, r14d; nSubAuthority1
0x18005135e  mov     [rsp+80h+nSubAuthority6], 0; nSubAuthority6
0x180051366  mov     r8d, 3; nSubAuthority0
0x18005136c  mov     [rsp+80h+nSubAuthority5], 0; nSubAuthority5
0x180051374  mov     dl, 5; nSubAuthorityCount
0x180051376  mov     [rsp+80h+nSubAuthority4], ebx; nSubAuthority4
0x18005137a  mov     [rsp+80h+nSubAuthority3], edi; nSubAuthority3
0x18005137e  mov     [rsp+80h+nSubAuthority2], esi; nSubAuthority2
0x180051382  call    cs:__imp_AllocateAndInitializeSid
0x180051388  test    eax, eax
0x18005138a  jnz     short loc_180051391
0x18005138c  xor     r15b, r15b
0x18005138f  jmp     short loc_180051312
0x180051391  mov     [r13+8], r15b
0x180051395  jmp     loc_180051312
0x18005139a  mov     rdx, rdi; StringSid
0x18005139d  call    ?ConvertSid@KnownSid@@QEAA_NPEBG@Z; KnownSid::ConvertSid(ushort const *)
0x1800513a2  mov     rcx, [rbp+var_8]
0x1800513a6  xor     rcx, rsp; StackCookie
0x1800513a9  call    __security_check_cookie
0x1800513ae  lea     r11, [rsp+80h+var_s0]
0x1800513b6  mov     rbx, [r11+40h]
0x1800513ba  mov     rsi, [r11+48h]
0x1800513be  mov     rsp, r11
0x1800513c1  pop     r15
0x1800513c3  pop     r14
0x1800513c5  pop     r13
0x1800513c7  pop     rdi
0x1800513c8  pop     rbp
0x1800513c9  retn
```
