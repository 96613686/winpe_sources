# ShieldProvider::AccountProtectionShield::IsCurrentUserBuiltInAdmin(bool *)

- ea: `0x1800c7ffc`
- end: `0x1800c827c`
- name: `?IsCurrentUserBuiltInAdmin@AccountProtectionShield@ShieldProvider@@AEAAJPEA_N@Z`
- size: `640`
- prototype: `__int64 __fastcall(ShieldProvider::AccountProtectionShield *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800c8b44`

## callees

- `0x180004710`
- `0x180004ae0`
- `0x18000517c`
- `0x18000d7fc`
- `0x1800c7ffc`
- `0x1800df1b0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800c8049`
- `KERNEL32!GetLastError` at `0x1800c80fa`
- `KERNEL32!GetLastError` at `0x1800c8176`
- `KERNEL32!GetLastError` at `0x1800c8049`
- `KERNEL32!GetLastError` at `0x1800c80fa`
- `KERNEL32!GetLastError` at `0x1800c8176`
- `KERNEL32!GetComputerNameW` at `0x1800c803f`
- `KERNEL32!GetComputerNameW` at `0x1800c803f`
- `KERNEL32!CompareStringW` at `0x1800c823b`
- `KERNEL32!CompareStringW` at `0x1800c823b`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800c816c`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800c816c`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x1800c80f0`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x1800c80f0`

## pseudocode

```c
__int64 __fastcall ShieldProvider::AccountProtectionShield::IsCurrentUserBuiltInAdmin(PCNZWCH *this, bool *a2)
{
  signed int LastError; // eax
  signed int v5; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  signed int v9; // eax
  void *v10; // r8
  signed int v11; // eax
  const struct std::nothrow_t *v12; // rdx
  WCHAR *v13; // rbx
  const struct std::nothrow_t *v14; // rdx
  DWORD nSize; // [rsp+40h] [rbp-C0h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cchReferencedDomainName; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cbSid; // [rsp+4Ch] [rbp-B4h] BYREF
  DWORD v19; // [rsp+50h] [rbp-B0h] BYREF
  PCNZWCH lpString1; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR Buffer[16]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE Sid[80]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE pSid[80]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR ReferencedDomainName[16]; // [rsp+120h] [rbp+20h] BYREF

  *a2 = 0;
  nSize = 16;
  if ( !GetComputerNameW(Buffer, &nSize) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( v5 < 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return (unsigned int)v5;
      v7 = 24;
LABEL_8:
      WPP_SF_d(v6[2], v7, WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids, (unsigned int)v5);
      return (unsigned int)v5;
    }
  }
  memset_0(Sid, 0, 0x44u);
  cbSid = 68;
  cchReferencedDomainName = 16;
  peUse = 0;
  if ( !LookupAccountNameW(0, Buffer, Sid, &cbSid, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
  {
    v9 = GetLastError();
    v5 = v9;
    if ( v9 > 0 )
      v5 = (unsigned __int16)v9 | 0x80070000;
    if ( v5 < 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return (unsigned int)v5;
      v7 = 25;
      goto LABEL_8;
    }
  }
  lpString1 = 0;
  memset_0(pSid, 0, 0x44u);
  v19 = 68;
  if ( !CreateWellKnownSid(WinAccountAdministratorSid, Sid, pSid, &v19) )
  {
    v11 = GetLastError();
    v5 = v11;
    if ( v11 > 0 )
      v5 = (unsigned __int16)v11 | 0x80070000;
    if ( v5 < 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return (unsigned int)v5;
      v7 = 26;
      goto LABEL_8;
    }
  }
  v5 = CommonUtil::UtilConvertSidToStringSid((CommonUtil *)&lpString1, pSid, v10);
  if ( v5 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        27,
        WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids,
        (unsigned int)v5);
    if ( lpString1 )
      operator delete((void *)lpString1, v12);
    return (unsigned int)v5;
  }
  v13 = (WCHAR *)lpString1;
  *a2 = CompareStringW(0x7Fu, 1u, lpString1, -1, this[21], -1) == 2;
  if ( v13 )
    operator delete(v13, v14);
  return 0;
}

```

## disassembly

```asm
0x1800c7ffc  mov     [rsp-8+arg_10], rbx
0x1800c8001  mov     [rsp-8+arg_18], rsi
0x1800c8006  push    rbp
0x1800c8007  push    rdi
0x1800c8008  push    r12
0x1800c800a  lea     rbp, [rsp-50h]
0x1800c800f  sub     rsp, 150h
0x1800c8016  mov     rax, cs:__security_cookie
0x1800c801d  xor     rax, rsp
0x1800c8020  mov     [rbp+60h+var_20], rax
0x1800c8024  mov     rdi, rdx
0x1800c8027  mov     byte ptr [rdx], 0
0x1800c802a  mov     rsi, rcx
0x1800c802d  mov     [rsp+160h+nSize], 10h
0x1800c8035  lea     rdx, [rsp+160h+nSize]; nSize
0x1800c803a  lea     rcx, [rsp+160h+Buffer]; lpBuffer
0x1800c803f  call    cs:__imp_GetComputerNameW
0x1800c8045  test    eax, eax
0x1800c8047  jnz     short loc_1800C809A
0x1800c8049  call    cs:__imp_GetLastError
0x1800c804f  mov     ebx, eax
0x1800c8051  test    eax, eax
0x1800c8053  jle     short loc_1800C805E
0x1800c8055  movzx   ebx, ax
0x1800c8058  or      ebx, 80070000h
0x1800c805e  test    ebx, ebx
0x1800c8060  jns     short loc_1800C809A
0x1800c8062  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c8069  lea     rax, WPP_GLOBAL_Control
0x1800c8070  cmp     rcx, rax
0x1800c8073  jz      short loc_1800C8093
0x1800c8075  test    byte ptr [rcx+1Ch], 1
0x1800c8079  jz      short loc_1800C8093
0x1800c807b  mov     edx, 18h
0x1800c8080  mov     rcx, [rcx+10h]
0x1800c8084  lea     r8, WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids
0x1800c808b  mov     r9d, ebx
0x1800c808e  call    WPP_SF_d
0x1800c8093  mov     eax, ebx
0x1800c8095  jmp     loc_1800C8258
0x1800c809a  mov     r12d, 44h ; 'D'
0x1800c80a0  lea     rcx, [rbp+60h+Sid]; void *
0x1800c80a4  mov     r8d, r12d; Size
0x1800c80a7  xor     edx, edx; Val
0x1800c80a9  call    memset_0
0x1800c80ae  lea     rax, [rsp+160h+var_11C]
0x1800c80b3  mov     [rsp+160h+cbSid], r12d
0x1800c80b8  mov     [rsp+160h+peUse], rax; peUse
0x1800c80bd  lea     r9, [rsp+160h+cbSid]; cbSid
0x1800c80c2  lea     rax, [rsp+160h+var_118]
0x1800c80c7  mov     [rsp+160h+var_118], 10h
0x1800c80cf  mov     [rsp+160h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800c80d4  lea     r8, [rbp+60h+Sid]; Sid
0x1800c80d8  lea     rax, [rbp+60h+var_40]
0x1800c80dc  mov     [rsp+160h+var_11C], 0
0x1800c80e4  lea     rdx, [rsp+160h+Buffer]; lpAccountName
0x1800c80e9  mov     [rsp+160h+ReferencedDomainName], rax; ReferencedDomainName
0x1800c80ee  xor     ecx, ecx; lpSystemName
0x1800c80f0  call    cs:__imp_LookupAccountNameW
0x1800c80f6  test    eax, eax
0x1800c80f8  jnz     short loc_1800C813E
0x1800c80fa  call    cs:__imp_GetLastError
0x1800c8100  mov     ebx, eax
0x1800c8102  test    eax, eax
0x1800c8104  jle     short loc_1800C810F
0x1800c8106  movzx   ebx, ax
0x1800c8109  or      ebx, 80070000h
0x1800c810f  test    ebx, ebx
0x1800c8111  jns     short loc_1800C813E
0x1800c8113  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c811a  lea     rax, WPP_GLOBAL_Control
0x1800c8121  cmp     rcx, rax
0x1800c8124  jz      loc_1800C8093
0x1800c812a  test    byte ptr [rcx+1Ch], 1
0x1800c812e  jz      loc_1800C8093
0x1800c8134  mov     edx, 19h
0x1800c8139  jmp     loc_1800C8080
0x1800c813e  mov     r8, r12; Size
0x1800c8141  mov     [rsp+160h+lpString1], 0
0x1800c814a  xor     edx, edx; Val
0x1800c814c  lea     rcx, [rbp+60h+pSid]; void *
0x1800c8150  call    memset_0
0x1800c8155  lea     r9, [rsp+160h+var_110]; cbSid
0x1800c815a  mov     [rsp+160h+var_110], r12d
0x1800c815f  lea     r8, [rbp+60h+pSid]; pSid
0x1800c8163  mov     ecx, 26h ; '&'; WellKnownSidType
0x1800c8168  lea     rdx, [rbp+60h+Sid]; DomainSid
0x1800c816c  call    cs:__imp_CreateWellKnownSid
0x1800c8172  test    eax, eax
0x1800c8174  jnz     short loc_1800C81BA
0x1800c8176  call    cs:__imp_GetLastError
0x1800c817c  mov     ebx, eax
0x1800c817e  test    eax, eax
0x1800c8180  jle     short loc_1800C818B
0x1800c8182  movzx   ebx, ax
0x1800c8185  or      ebx, 80070000h
0x1800c818b  test    ebx, ebx
0x1800c818d  jns     short loc_1800C81BA
0x1800c818f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c8196  lea     rax, WPP_GLOBAL_Control
0x1800c819d  cmp     rcx, rax
0x1800c81a0  jz      loc_1800C8093
0x1800c81a6  test    byte ptr [rcx+1Ch], 1
0x1800c81aa  jz      loc_1800C8093
0x1800c81b0  mov     edx, 1Ah
0x1800c81b5  jmp     loc_1800C8080
0x1800c81ba  lea     rdx, [rbp+60h+pSid]; Sid
0x1800c81be  lea     rcx, [rsp+160h+lpString1]; this
0x1800c81c3  call    ?UtilConvertSidToStringSid@CommonUtil@@YAJPEAPEAGPEAX@Z; CommonUtil::UtilConvertSidToStringSid(ushort * *,void *)
0x1800c81c8  mov     ebx, eax
0x1800c81ca  test    eax, eax
0x1800c81cc  jns     short loc_1800C8217
0x1800c81ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c81d5  lea     rax, WPP_GLOBAL_Control
0x1800c81dc  cmp     rcx, rax
0x1800c81df  jz      short loc_1800C81FF
0x1800c81e1  test    byte ptr [rcx+1Ch], 1
0x1800c81e5  jz      short loc_1800C81FF
0x1800c81e7  mov     rcx, [rcx+10h]
0x1800c81eb  lea     r8, WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids
0x1800c81f2  mov     edx, 1Bh
0x1800c81f7  mov     r9d, ebx
0x1800c81fa  call    WPP_SF_d
0x1800c81ff  mov     rcx, [rsp+160h+lpString1]; void *
0x1800c8204  test    rcx, rcx
0x1800c8207  jz      loc_1800C8093
0x1800c820d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800c8212  jmp     loc_1800C8093
0x1800c8217  mov     rax, [rsi+0A8h]
0x1800c821e  or      r9d, 0FFFFFFFFh; cchCount1
0x1800c8222  mov     rbx, [rsp+160h+lpString1]
0x1800c8227  mov     dword ptr [rsp+160h+cchReferencedDomainName], r9d; cchCount2
0x1800c822c  mov     r8, rbx; lpString1
0x1800c822f  mov     [rsp+160h+ReferencedDomainName], rax; lpString2
0x1800c8234  lea     edx, [r9+2]; dwCmpFlags
0x1800c8238  lea     ecx, [rdx+7Eh]; Locale
0x1800c823b  call    cs:__imp_CompareStringW
0x1800c8241  cmp     eax, 2
0x1800c8244  setz    al
0x1800c8247  mov     [rdi], al
0x1800c8249  test    rbx, rbx
0x1800c824c  jz      short loc_1800C8256
0x1800c824e  mov     rcx, rbx; void *
0x1800c8251  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800c8256  xor     eax, eax
0x1800c8258  mov     rcx, [rbp+60h+var_20]
0x1800c825c  xor     rcx, rsp; StackCookie
0x1800c825f  call    __security_check_cookie
0x1800c8264  lea     r11, [rsp+160h+var_10]
0x1800c826c  mov     rbx, [r11+30h]
0x1800c8270  mov     rsi, [r11+38h]
0x1800c8274  mov     rsp, r11
0x1800c8277  pop     r12
0x1800c8279  pop     rdi
0x1800c827a  pop     rbp
0x1800c827b  retn
```
