# GetLdapBinding(ushort const *,ldap * *)

- ea: `0x180003670`
- end: `0x1800038ae`
- name: `?GetLdapBinding@@YAJPEBGPEAPEAUldap@@@Z`
- size: `574`
- prototype: `__int64 __fastcall(const unsigned __int16 *lpMem, struct ldap **)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180003670`
- `0x18000f1a8`
- `0x180010950`
- `0x18001a450`

## import_xrefs

- `WLDAP32!__imp_ldap_unbind` at `0x180003877`
- `WLDAP32!__imp_ldap_unbind` at `0x180003877`
- `WLDAP32!__imp_ldap_set_optionW` at `0x18000375a`
- `WLDAP32!__imp_ldap_set_optionW` at `0x180003786`
- `WLDAP32!__imp_ldap_set_optionW` at `0x1800037b2`
- `WLDAP32!__imp_ldap_set_optionW` at `0x1800037e0`
- `WLDAP32!__imp_ldap_set_optionW` at `0x180003810`
- `WLDAP32!__imp_ldap_set_optionW` at `0x18000375a`
- `WLDAP32!__imp_ldap_set_optionW` at `0x180003786`
- `WLDAP32!__imp_ldap_set_optionW` at `0x1800037b2`
- `WLDAP32!__imp_ldap_set_optionW` at `0x1800037e0`
- `WLDAP32!__imp_ldap_set_optionW` at `0x180003810`
- `WLDAP32!__imp_LdapGetLastError` at `0x18000371a`
- `WLDAP32!__imp_LdapGetLastError` at `0x18000371a`
- `WLDAP32!__imp_ldap_bind_sW` at `0x180003842`
- `WLDAP32!__imp_ldap_bind_sW` at `0x180003842`
- `WLDAP32!__imp_ldap_initW` at `0x18000370c`
- `WLDAP32!__imp_ldap_initW` at `0x18000370c`

## string_xrefs

- `0x1800036e8`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdsad.cxx`
- `0x180003735`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdsad.cxx`

## pseudocode

```c
__int64 __fastcall GetLdapBinding(unsigned __int16 *lpMem, struct ldap **a2)
{
  int v2; // ebx
  unsigned __int16 *v5; // rsi
  signed int DomainControllerInfo; // eax
  LDAP *v7; // rax
  LDAP *v8; // rdi
  signed int LastError; // eax
  unsigned int v10; // r9d
  signed int v11; // eax
  signed int v12; // eax
  signed int v13; // eax
  signed int v14; // eax
  signed int v15; // eax
  signed int v16; // eax
  unsigned __int64 v18; // [rsp+40h] [rbp-10h] BYREF
  unsigned __int64 v19; // [rsp+48h] [rbp-8h] BYREF
  int v20; // [rsp+90h] [rbp+40h] BYREF
  unsigned __int16 *invalue; // [rsp+A0h] [rbp+50h] BYREF
  unsigned __int16 *v22; // [rsp+A8h] [rbp+58h] BYREF

  v2 = 0;
  v22 = lpMem;
  v20 = 0;
  v19 = 0;
  invalue = 0;
  v5 = lpMem;
  v18 = 0;
  if ( !lpMem )
  {
    DomainControllerInfo = GetDomainControllerInfo(1, 0, 0, &v22, &v19, &invalue, &v18, &v20);
    v2 = DomainControllerInfo;
    if ( DomainControllerInfo < 0 )
    {
      SidKeyDebugTraceError(
        DomainControllerInfo,
        "hr",
        "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsad.cxx",
        0x32u);
      goto LABEL_47;
    }
    v5 = v22;
  }
  v7 = ldap_initW(v5, 0x185u);
  v8 = v7;
  if ( !v7 )
  {
    LastError = LdapGetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    v10 = 60;
    goto LABEL_9;
  }
  v11 = ldap_set_optionW(v7, 152, (const void *)1);
  if ( v11 )
  {
    if ( v11 > 0 )
      v2 = (unsigned __int16)v11 | 0x80070000;
    else
      v2 = v11;
    v10 = 71;
LABEL_9:
    SidKeyDebugTraceError(v2, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsad.cxx", v10);
    goto LABEL_41;
  }
  v12 = ldap_set_optionW(v8, 150, (const void *)1);
  if ( v12 )
  {
    if ( v12 > 0 )
      v2 = (unsigned __int16)v12 | 0x80070000;
    else
      v2 = v12;
    v10 = 82;
    goto LABEL_9;
  }
  v13 = ldap_set_optionW(v8, 149, (const void *)1);
  if ( v13 )
  {
    if ( v13 > 0 )
      v2 = (unsigned __int16)v13 | 0x80070000;
    else
      v2 = v13;
    v10 = 93;
    goto LABEL_9;
  }
  v14 = ldap_set_optionW(v8, 8, 0);
  if ( v14 )
  {
    if ( v14 > 0 )
      v2 = (unsigned __int16)v14 | 0x80070000;
    else
      v2 = v14;
    v10 = 105;
    goto LABEL_9;
  }
  v15 = ldap_set_optionW(v8, 59, &invalue);
  if ( v15 )
  {
    if ( v15 > 0 )
      v2 = (unsigned __int16)v15 | 0x80070000;
    else
      v2 = v15;
    v10 = 118;
    goto LABEL_9;
  }
  v16 = ldap_bind_sW(v8, 0, 0, 0x486u);
  if ( v16 )
  {
    if ( v16 > 0 )
      v2 = (unsigned __int16)v16 | 0x80070000;
    else
      v2 = v16;
    v10 = 130;
    goto LABEL_9;
  }
  *a2 = v8;
  v8 = 0;
LABEL_41:
  if ( v2 < 0 && v8 )
    ldap_unbind(v8);
  if ( lpMem && v5 != lpMem )
    SIDKeyProvFree(v5);
LABEL_47:
  if ( invalue )
    SIDKeyProvFree(invalue);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180003670  mov     r11, rsp
0x180003673  push    rbp
0x180003674  push    rbx
0x180003675  push    rsi
0x180003676  push    rdi
0x180003677  push    r13
0x180003679  push    r14
0x18000367b  push    r15
0x18000367d  mov     rbp, rsp
0x180003680  sub     rsp, 50h
0x180003684  xor     ebx, ebx
0x180003686  mov     [rbp+arg_18], rcx
0x18000368a  mov     [rbp+arg_0], ebx
0x18000368d  mov     r15, rdx
0x180003690  mov     [rbp+var_8], rbx
0x180003694  mov     r14, rcx
0x180003697  mov     [rbp+invalue], rbx
0x18000369b  mov     rsi, rcx
0x18000369e  mov     [rbp+var_10], rbx
0x1800036a2  lea     r13d, [rbx+1]
0x1800036a6  test    rcx, rcx
0x1800036a9  jnz     short loc_180003704
0x1800036ab  lea     rax, [rbp+arg_0]
0x1800036af  xor     r8d, r8d; unsigned __int16 *
0x1800036b2  mov     [r11-50h], rax
0x1800036b6  lea     r9, [rbp+arg_18]; unsigned __int16 **
0x1800036ba  lea     rax, [rbp+var_10]
0x1800036be  xor     edx, edx; int
0x1800036c0  mov     [r11-58h], rax
0x1800036c4  mov     ecx, r13d; int
0x1800036c7  lea     rax, [rbp+invalue]
0x1800036cb  mov     [r11-60h], rax
0x1800036cf  lea     rax, [rbp+var_8]
0x1800036d3  mov     [r11-68h], rax
0x1800036d7  call    ?GetDomainControllerInfo@@YAJHHPEBGPEAPEAGPEA_K12PEAH@Z; GetDomainControllerInfo(int,int,ushort const *,ushort * *,unsigned __int64 *,ushort * *,unsigned __int64 *,int *)
0x1800036dc  mov     ebx, eax
0x1800036de  test    eax, eax
0x1800036e0  jns     short loc_180003700
0x1800036e2  lea     r9d, [rsi+32h]; unsigned int
0x1800036e6  mov     ecx, eax; unsigned int
0x1800036e8  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x1800036ef  lea     rdx, aHr; "hr"
0x1800036f6  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x1800036fb  jmp     loc_18000388F
0x180003700  mov     rsi, [rbp+arg_18]
0x180003704  mov     edx, 185h; PortNumber
0x180003709  mov     rcx, rsi; HostName
0x18000370c  call    cs:__imp_ldap_initW
0x180003712  mov     rdi, rax
0x180003715  test    rax, rax
0x180003718  jnz     short loc_18000374F
0x18000371a  call    cs:__imp_LdapGetLastError
0x180003720  mov     ebx, eax
0x180003722  test    eax, eax
0x180003724  jle     short loc_18000372F
0x180003726  movzx   ebx, ax
0x180003729  or      ebx, 80070000h
0x18000372f  mov     r9d, 3Ch ; '<'; unsigned int
0x180003735  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000373c  mov     ecx, ebx; unsigned int
0x18000373e  lea     rdx, aHr; "hr"
0x180003745  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000374a  jmp     loc_18000386B
0x18000374f  mov     r8, r13; invalue
0x180003752  mov     edx, 98h; option
0x180003757  mov     rcx, rdi; ld
0x18000375a  call    cs:__imp_ldap_set_optionW
0x180003760  test    eax, eax
0x180003762  jz      short loc_18000377B
0x180003764  jg      short loc_18000376A
0x180003766  mov     ebx, eax
0x180003768  jmp     short loc_180003773
0x18000376a  movzx   ebx, ax
0x18000376d  or      ebx, 80070000h
0x180003773  mov     r9d, 47h ; 'G'
0x180003779  jmp     short loc_180003735
0x18000377b  mov     r8, r13; invalue
0x18000377e  mov     edx, 96h; option
0x180003783  mov     rcx, rdi; ld
0x180003786  call    cs:__imp_ldap_set_optionW
0x18000378c  test    eax, eax
0x18000378e  jz      short loc_1800037A7
0x180003790  jg      short loc_180003796
0x180003792  mov     ebx, eax
0x180003794  jmp     short loc_18000379F
0x180003796  movzx   ebx, ax
0x180003799  or      ebx, 80070000h
0x18000379f  mov     r9d, 52h ; 'R'
0x1800037a5  jmp     short loc_180003735
0x1800037a7  mov     r8, r13; invalue
0x1800037aa  mov     edx, 95h; option
0x1800037af  mov     rcx, rdi; ld
0x1800037b2  call    cs:__imp_ldap_set_optionW
0x1800037b8  test    eax, eax
0x1800037ba  jz      short loc_1800037D6
0x1800037bc  jg      short loc_1800037C2
0x1800037be  mov     ebx, eax
0x1800037c0  jmp     short loc_1800037CB
0x1800037c2  movzx   ebx, ax
0x1800037c5  or      ebx, 80070000h
0x1800037cb  mov     r9d, 5Dh ; ']'
0x1800037d1  jmp     loc_180003735
0x1800037d6  xor     r8d, r8d; invalue
0x1800037d9  mov     rcx, rdi; ld
0x1800037dc  lea     edx, [r8+8]; option
0x1800037e0  call    cs:__imp_ldap_set_optionW
0x1800037e6  test    eax, eax
0x1800037e8  jz      short loc_180003804
0x1800037ea  jg      short loc_1800037F0
0x1800037ec  mov     ebx, eax
0x1800037ee  jmp     short loc_1800037F9
0x1800037f0  movzx   ebx, ax
0x1800037f3  or      ebx, 80070000h
0x1800037f9  mov     r9d, 69h ; 'i'
0x1800037ff  jmp     loc_180003735
0x180003804  lea     r8, [rbp+invalue]; invalue
0x180003808  mov     edx, 3Bh ; ';'; option
0x18000380d  mov     rcx, rdi; ld
0x180003810  call    cs:__imp_ldap_set_optionW
0x180003816  test    eax, eax
0x180003818  jz      short loc_180003834
0x18000381a  jg      short loc_180003820
0x18000381c  mov     ebx, eax
0x18000381e  jmp     short loc_180003829
0x180003820  movzx   ebx, ax
0x180003823  or      ebx, 80070000h
0x180003829  mov     r9d, 76h ; 'v'
0x18000382f  jmp     loc_180003735
0x180003834  mov     r9d, 486h; method
0x18000383a  xor     r8d, r8d; cred
0x18000383d  xor     edx, edx; dn
0x18000383f  mov     rcx, rdi; ld
0x180003842  call    cs:__imp_ldap_bind_sW
0x180003848  test    eax, eax
0x18000384a  jz      short loc_180003866
0x18000384c  jg      short loc_180003852
0x18000384e  mov     ebx, eax
0x180003850  jmp     short loc_18000385B
0x180003852  movzx   ebx, ax
0x180003855  or      ebx, 80070000h
0x18000385b  mov     r9d, 82h
0x180003861  jmp     loc_180003735
0x180003866  mov     [r15], rdi
0x180003869  xor     edi, edi
0x18000386b  test    ebx, ebx
0x18000386d  jns     short loc_18000387D
0x18000386f  test    rdi, rdi
0x180003872  jz      short loc_18000387D
0x180003874  mov     rcx, rdi; ld
0x180003877  call    cs:__imp_ldap_unbind
0x18000387d  test    r14, r14
0x180003880  jz      short loc_18000388F
0x180003882  cmp     rsi, r14
0x180003885  jz      short loc_18000388F
0x180003887  mov     rcx, rsi; lpMem
0x18000388a  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x18000388f  mov     rcx, [rbp+invalue]; lpMem
0x180003893  test    rcx, rcx
0x180003896  jz      short loc_18000389D
0x180003898  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x18000389d  mov     eax, ebx
0x18000389f  add     rsp, 50h
0x1800038a3  pop     r15
0x1800038a5  pop     r14
0x1800038a7  pop     r13
0x1800038a9  pop     rdi
0x1800038aa  pop     rsi
0x1800038ab  pop     rbx
0x1800038ac  pop     rbp
0x1800038ad  retn
```
