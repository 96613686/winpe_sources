# KerbCheckStrongIssuerSidMapping(ulong,_KERB_INTERNAL_NAME *,KERB_ERR_REASON &)

- ea: `0x1800560a4`
- end: `0x18005617b`
- name: `?KerbCheckStrongIssuerSidMapping@@YAEKPEAU_KERB_INTERNAL_NAME@@AEAUKERB_ERR_REASON@@@Z`
- size: `215`
- prototype: `unsigned __int8 __fastcall(unsigned int, struct _KERB_INTERNAL_NAME *, struct KERB_ERR_REASON *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180055d28`

## callees

- `0x180002ad0`
- `0x180003908`
- `0x1800101c4`
- `0x18001cdc4`
- `0x180053900`
- `0x1800560a4`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x180056166`
- `ntdll!RtlEqualSid` at `0x180056166`

## pseudocode

```c
unsigned __int8 __fastcall KerbCheckStrongIssuerSidMapping(
        ULONG a1,
        struct _KERB_INTERNAL_NAME *a2,
        struct KERB_ERR_REASON *a3)
{
  PSID Sid2; // [rsp+20h] [rbp-78h] BYREF
  _BYTE Sid1[80]; // [rsp+30h] [rbp-68h] BYREF

  memset_0(Sid1, 0, 0x48u);
  Sid2 = 0;
  KdcMakeAccountSid(Sid1, a1);
  if ( (int)KdcGetSidFromAltSecId((struct _UNICODE_STRING *)((char *)a2 + 8), &Sid2) < 0 )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids);
    return 0;
  }
  if ( !RtlEqualSid(Sid1, Sid2) )
    return 0;
  *(_QWORD *)a3 = 8;
  return 1;
}

```

## disassembly

```asm
0x1800560a4  mov     [rsp+arg_0], rbx
0x1800560a9  mov     [rsp+arg_18], rsi
0x1800560ae  push    rdi
0x1800560af  sub     rsp, 90h
0x1800560b6  mov     rax, cs:__security_cookie
0x1800560bd  xor     rax, rsp
0x1800560c0  mov     [rsp+98h+var_18], rax
0x1800560c8  mov     rdi, rdx
0x1800560cb  mov     rsi, r8
0x1800560ce  xor     edx, edx; Val
0x1800560d0  mov     ebx, ecx
0x1800560d2  lea     rcx, [rsp+98h+Sid1]; void *
0x1800560d7  lea     r8d, [rdx+48h]; Size
0x1800560db  call    memset_0
0x1800560e0  mov     edx, ebx; unsigned int
0x1800560e2  mov     [rsp+98h+Sid2], 0
0x1800560eb  lea     rcx, [rsp+98h+Sid1]; Sid
0x1800560f0  call    ?KdcMakeAccountSid@@YAXPEAXK@Z; KdcMakeAccountSid(void *,ulong)
0x1800560f5  lea     rcx, [rdi+8]; struct _UNICODE_STRING *
0x1800560f9  lea     rdx, [rsp+98h+Sid2]; void **
0x1800560fe  call    ?KdcGetSidFromAltSecId@@YAJAEAU_UNICODE_STRING@@PEAPEAX@Z; KdcGetSidFromAltSecId(_UNICODE_STRING &,void * *)
0x180056103  test    eax, eax
0x180056105  jns     short loc_18005615C
0x180056107  mov     rcx, cs:WPP_GLOBAL_Control
0x18005610e  lea     rax, WPP_GLOBAL_Control
0x180056115  cmp     rcx, rax
0x180056118  jz      short loc_180056135
0x18005611a  test    byte ptr [rcx+1Ch], 2
0x18005611e  jz      short loc_180056135
0x180056120  mov     rcx, [rcx+10h]
0x180056124  lea     r8, WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids
0x18005612b  mov     edx, 26h ; '&'
0x180056130  call    WPP_SF_
0x180056135  xor     al, al
0x180056137  mov     rcx, [rsp+98h+var_18]
0x18005613f  xor     rcx, rsp; StackCookie
0x180056142  call    __security_check_cookie
0x180056147  lea     r11, [rsp+98h+var_8]
0x18005614f  mov     rbx, [r11+10h]
0x180056153  mov     rsi, [r11+28h]
0x180056157  mov     rsp, r11
0x18005615a  pop     rdi
0x18005615b  retn
0x18005615c  mov     rdx, [rsp+98h+Sid2]; Sid2
0x180056161  lea     rcx, [rsp+98h+Sid1]; Sid1
0x180056166  call    cs:__imp_RtlEqualSid
0x18005616c  test    al, al
0x18005616e  jz      short loc_180056135
0x180056170  mov     qword ptr [rsi], 8
0x180056177  mov     al, 1
0x180056179  jmp     short loc_180056137
```
