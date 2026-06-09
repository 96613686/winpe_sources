# NetpForceReplicateComputerObject

- ea: `0x180026448`
- end: `0x180026838`
- name: `NetpForceReplicateComputerObject`
- size: `1008`
- prototype: `__int64 __fastcall(LDAP *ld)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180026840`

## callees

- `0x180001594`
- `0x18001e420`
- `0x180026448`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180026673`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800266bc`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180026673`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800266bc`
- `netutils!NetApiBufferFree` at `0x1800267cf`
- `netutils!NetApiBufferFree` at `0x1800267cf`
- `netutils!NetApiBufferAllocate` at `0x180026718`
- `netutils!NetApiBufferAllocate` at `0x180026718`
- `WLDAP32!__imp_LdapGetLastError` at `0x180026585`
- `WLDAP32!__imp_LdapGetLastError` at `0x180026585`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x180026565`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x180026565`
- `WLDAP32!__imp_ldap_first_entry` at `0x18002657a`
- `WLDAP32!__imp_ldap_first_entry` at `0x180026628`
- `WLDAP32!__imp_ldap_first_entry` at `0x18002657a`
- `WLDAP32!__imp_ldap_first_entry` at `0x180026628`
- `WLDAP32!__imp_ldap_msgfree` at `0x1800265c5`
- `WLDAP32!__imp_ldap_msgfree` at `0x180026809`
- `WLDAP32!__imp_ldap_msgfree` at `0x1800265c5`
- `WLDAP32!__imp_ldap_msgfree` at `0x180026809`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x180026597`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x180026644`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18002668d`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x180026597`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x180026644`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18002668d`
- `WLDAP32!__imp_ldap_modify_sW` at `0x180026764`
- `WLDAP32!__imp_ldap_modify_sW` at `0x1800267b1`
- `WLDAP32!__imp_ldap_modify_sW` at `0x180026764`
- `WLDAP32!__imp_ldap_modify_sW` at `0x1800267b1`
- `WLDAP32!__imp_ldap_search_ext_sW` at `0x180026559`
- `WLDAP32!__imp_ldap_search_ext_sW` at `0x180026612`
- `WLDAP32!__imp_ldap_search_ext_sW` at `0x180026559`
- `WLDAP32!__imp_ldap_search_ext_sW` at `0x180026612`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800267dd`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800267eb`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800267f9`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800267dd`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800267eb`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800267f9`

## string_xrefs

- `0x180026479`: `dsServiceName`

## pseudocode

```c
__int64 __fastcall NetpForceReplicateComputerObject(LDAP *ld, LDAP *a2, WCHAR *a3, int a4)
{
  PWCHAR *v6; // r13
  PWCHAR *v7; // r12
  PWCHAR *v8; // r15
  ULONG LastError; // eax
  ULONG v10; // ebx
  LDAPMessage *entry; // rax
  PWCHAR *valuesW; // rax
  PWCHAR v13; // r14
  LDAPMessage *v14; // rax
  LDAPMessage *v15; // rdi
  PWCHAR *v16; // rax
  const wchar_t *v17; // rsi
  wchar_t *v18; // rax
  const wchar_t **v19; // rax
  const wchar_t *v20; // rdi
  wchar_t *v21; // rax
  __int64 v22; // rax
  unsigned __int64 v23; // rdx
  unsigned __int64 v24; // rcx
  bool v25; // cc
  const wchar_t *v26; // r8
  __int64 v27; // rcx
  LDAP *v28; // rsi
  PLDAPMessage res; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID Buffer; // [rsp+68h] [rbp-98h] BYREF
  unsigned int cchDest; // [rsp+70h] [rbp-90h]
  int cchDest_4; // [rsp+74h] [rbp-8Ch]
  __int128 v34; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v35[3]; // [rsp+88h] [rbp-78h] BYREF
  char v36; // [rsp+A0h] [rbp-60h]
  int v37; // [rsp+A1h] [rbp-5Fh]
  __int16 v38; // [rsp+A5h] [rbp-5Bh]
  char v39; // [rsp+A7h] [rbp-59h]
  LDAP *lda; // [rsp+A8h] [rbp-58h]
  PWSTR attr[2]; // [rsp+B0h] [rbp-50h] BYREF
  LDAPModW *mods[2]; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v43[3]; // [rsp+D0h] [rbp-30h] BYREF
  PLDAPControlW ServerControls[2]; // [rsp+E8h] [rbp-18h] BYREF
  PWSTR attrs; // [rsp+F8h] [rbp-8h] BYREF
  PWSTR v46; // [rsp+100h] [rbp+0h]
  __int64 v47; // [rsp+108h] [rbp+8h]

  cchDest_4 = a4;
  lda = a2;
  attr[0] = L"dsServiceName";
  attr[1] = 0;
  attrs = L"distinguishedName";
  v47 = 0;
  v46 = L"serverReferenceBL";
  v35[1] = 0;
  v35[0] = L"1.2.840.113556.1.4.529";
  v35[2] = 0;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  v6 = 0;
  v36 = 1;
  ServerControls[0] = (PLDAPControlW)v35;
  v7 = 0;
  res = 0;
  v43[1] = L"replicateSingleObject";
  v8 = 0;
  Buffer = 0;
  v43[2] = &v34;
  mods[0] = (LDAPModW *)v43;
  v34 = 0;
  v43[0] = 0;
  ServerControls[1] = 0;
  mods[1] = 0;
  LastError = ldap_search_ext_sW(
                ld,
                (const PWSTR)&base,
                0,
                (const PWSTR)L"(objectClass=*)",
                attr,
                0,
                0,
                0,
                0,
                0xFFFFFFFF,
                &res);
  if ( LastError )
    goto LABEL_2;
  entry = ldap_first_entry(ld, res);
  if ( !entry )
    goto LABEL_4;
  valuesW = ldap_get_valuesW(ld, entry, attr[0]);
  v6 = valuesW;
  if ( !valuesW )
    goto LABEL_4;
  v13 = *valuesW;
  if ( !*valuesW || !*v13 )
    goto LABEL_35;
  if ( res )
  {
    ldap_msgfree(res);
    res = 0;
  }
  LastError = ldap_search_ext_sW(
                ld,
                a3,
                0,
                (const PWSTR)L"(objectClass=*)",
                &attrs,
                0,
                ServerControls,
                0,
                0,
                0xFFFFFFFF,
                &res);
  if ( LastError )
    goto LABEL_2;
  v14 = ldap_first_entry(ld, res);
  v15 = v14;
  if ( !v14 )
    goto LABEL_4;
  v16 = ldap_get_valuesW(ld, v14, attrs);
  v7 = v16;
  if ( !v16 )
    goto LABEL_4;
  v17 = *v16;
  if ( !*v16 || !*v17 )
    goto LABEL_35;
  v18 = wcschr(v17, 0x3Bu);
  if ( v18 )
    *v18 = 0;
  v19 = (const wchar_t **)ldap_get_valuesW(ld, v15, v46);
  v8 = (PWCHAR *)v19;
  if ( !v19 )
  {
LABEL_4:
    LastError = LdapGetLastError();
LABEL_2:
    v10 = LdapMapErrorToWin32(LastError);
    goto LABEL_36;
  }
  v20 = *v19;
  if ( !*v19 || !*v20 )
  {
LABEL_35:
    v10 = 8316;
    goto LABEL_36;
  }
  v21 = wcschr(*v19, 0x3Bu);
  if ( v21 )
    *v21 = 0;
  v22 = -1;
  v23 = -1;
  do
    ++v23;
  while ( v20[v23] );
  v24 = -1;
  do
    ++v24;
  while ( v17[v24] );
  v25 = v24 <= v23;
  v26 = v20;
  v27 = -1;
  if ( !v25 )
    v26 = v17;
  do
    ++v27;
  while ( v26[v27] );
  do
    ++v22;
  while ( v13[v22] );
  cchDest = v27 + 2 + v22;
  v10 = NetApiBufferAllocate(2 * cchDest, &Buffer);
  if ( !v10 )
  {
    StringCchPrintfW((STRSAFE_LPWSTR)Buffer, cchDest, L"%ws:%ws", v13, v17);
    v28 = lda;
    v34 = (unsigned __int64)Buffer;
    LastError = ldap_modify_sW(lda, 0, mods);
    if ( LastError )
      goto LABEL_2;
    if ( cchDest_4 == 3 )
    {
      StringCchPrintfW((STRSAFE_LPWSTR)Buffer, cchDest, L"%ws:%ws", v13, v20);
      v34 = (unsigned __int64)Buffer;
      LastError = ldap_modify_sW(v28, 0, mods);
      if ( LastError )
        goto LABEL_2;
    }
  }
LABEL_36:
  if ( Buffer )
    NetApiBufferFree(Buffer);
  if ( v6 )
    ldap_value_freeW(v6);
  if ( v7 )
    ldap_value_freeW(v7);
  if ( v8 )
    ldap_value_freeW(v8);
  if ( res )
    ldap_msgfree(res);
  return v10;
}

```

## disassembly

```asm
0x180026448  mov     [rsp-8+arg_18], rbx
0x18002644d  push    rbp
0x18002644e  push    rsi
0x18002644f  push    rdi
0x180026450  push    r12
0x180026452  push    r13
0x180026454  push    r14
0x180026456  push    r15
0x180026458  lea     rbp, [rsp-20h]
0x18002645d  sub     rsp, 120h
0x180026464  mov     rax, cs:__security_cookie
0x18002646b  xor     rax, rsp
0x18002646e  mov     [rbp+50h+var_40], rax
0x180026472  xor     esi, esi
0x180026474  mov     dword ptr [rsp+150h+cchDest+4], r9d
0x180026479  lea     rax, aDsservicename; "dsServiceName"
0x180026480  mov     [rbp+50h+ld], rdx
0x180026484  mov     [rbp+50h+attr], rax
0x180026488  lea     r9, filter; "(objectClass=*)"
0x18002648f  lea     rax, aDistinguishedn; "distinguishedName"
0x180026496  mov     [rbp+50h+var_98], rsi
0x18002649a  mov     [rbp+50h+var_58], rax
0x18002649e  lea     rdx, base; base
0x1800264a5  lea     rax, aServerreferenc; "serverReferenceBL"
0x1800264ac  mov     [rbp+50h+var_48], rsi
0x1800264b0  mov     [rbp+50h+var_50], rax
0x1800264b4  mov     rdi, r8
0x1800264b7  lea     rax, a12840113556145; "1.2.840.113556.1.4.529"
0x1800264be  mov     [rbp+50h+var_C0], rsi
0x1800264c2  mov     [rbp+50h+var_C8], rax
0x1800264c6  xorps   xmm0, xmm0
0x1800264c9  xor     eax, eax
0x1800264cb  mov     [rbp+50h+var_B8], rsi
0x1800264cf  mov     [rbp+50h+var_AF], eax
0x1800264d2  xor     r8d, r8d; scope
0x1800264d5  mov     [rbp+50h+var_AB], ax
0x1800264d9  mov     rbx, rcx
0x1800264dc  mov     [rbp+50h+var_A9], al
0x1800264df  mov     r13d, esi
0x1800264e2  lea     rax, [rbp+50h+var_C8]
0x1800264e6  mov     [rbp+50h+var_B0], 1
0x1800264ea  mov     [rbp+50h+var_68], rax
0x1800264ee  mov     r12d, esi
0x1800264f1  lea     rax, aReplicatesingl; "replicateSingleObject"
0x1800264f8  mov     [rsp+150h+var_F0], rsi
0x1800264fd  mov     [rbp+50h+var_78], rax
0x180026501  mov     r15d, esi
0x180026504  lea     rax, [rsp+150h+var_D8]
0x180026509  mov     [rsp+150h+Buffer], rsi
0x18002650e  mov     [rbp+50h+var_70], rax
0x180026512  lea     rax, [rbp+50h+var_80]
0x180026516  mov     [rbp+50h+mods], rax
0x18002651a  lea     rax, [rsp+150h+var_F0]
0x18002651f  mov     [rsp+150h+res], rax; res
0x180026524  lea     rax, [rbp+50h+attr]
0x180026528  mov     [rsp+150h+SizeLimit], 0FFFFFFFFh; SizeLimit
0x180026530  mov     [rsp+150h+timeout], rsi; timeout
0x180026535  mov     [rsp+150h+ClientControls], rsi; ClientControls
0x18002653a  mov     [rsp+150h+ServerControls], rsi; ServerControls
0x18002653f  mov     [rsp+150h+attrsonly], esi; attrsonly
0x180026543  mov     [rsp+150h+attrs], rax; attrs
0x180026548  movups  [rsp+150h+var_D8], xmm0
0x18002654d  mov     [rbp+50h+var_80], rsi
0x180026551  mov     [rbp+50h+var_60], rsi
0x180026555  mov     [rbp+50h+var_88], rsi
0x180026559  call    cs:__imp_ldap_search_ext_sW
0x18002655f  test    eax, eax
0x180026561  jz      short loc_180026572
0x180026563  mov     ecx, eax; LdapError
0x180026565  call    cs:__imp_LdapMapErrorToWin32
0x18002656b  mov     ebx, eax
0x18002656d  jmp     loc_1800267C5
0x180026572  mov     rdx, [rsp+150h+var_F0]; res
0x180026577  mov     rcx, rbx; ld
0x18002657a  call    cs:__imp_ldap_first_entry
0x180026580  test    rax, rax
0x180026583  jnz     short loc_18002658D
0x180026585  call    cs:__imp_LdapGetLastError
0x18002658b  jmp     short loc_180026563
0x18002658d  mov     r8, [rbp+50h+attr]; attr
0x180026591  mov     rdx, rax; entry
0x180026594  mov     rcx, rbx; ld
0x180026597  call    cs:__imp_ldap_get_valuesW
0x18002659d  mov     r13, rax
0x1800265a0  test    rax, rax
0x1800265a3  jz      short loc_180026585
0x1800265a5  mov     r14, [rax]
0x1800265a8  test    r14, r14
0x1800265ab  jz      loc_1800267C0
0x1800265b1  cmp     [r14], si
0x1800265b5  jz      loc_1800267C0
0x1800265bb  mov     rcx, [rsp+150h+var_F0]; res
0x1800265c0  test    rcx, rcx
0x1800265c3  jz      short loc_1800265D0
0x1800265c5  call    cs:__imp_ldap_msgfree
0x1800265cb  mov     [rsp+150h+var_F0], rsi
0x1800265d0  lea     rax, [rsp+150h+var_F0]
0x1800265d5  xor     r8d, r8d; scope
0x1800265d8  mov     [rsp+150h+res], rax; res
0x1800265dd  lea     r9, filter; "(objectClass=*)"
0x1800265e4  mov     [rsp+150h+SizeLimit], 0FFFFFFFFh; SizeLimit
0x1800265ec  lea     rax, [rbp+50h+var_68]
0x1800265f0  mov     [rsp+150h+timeout], rsi; timeout
0x1800265f5  mov     rdx, rdi; base
0x1800265f8  mov     [rsp+150h+ClientControls], rsi; ClientControls
0x1800265fd  mov     rcx, rbx; ld
0x180026600  mov     [rsp+150h+ServerControls], rax; ServerControls
0x180026605  lea     rax, [rbp+50h+var_58]
0x180026609  mov     [rsp+150h+attrsonly], esi; attrsonly
0x18002660d  mov     [rsp+150h+attrs], rax; attrs
0x180026612  call    cs:__imp_ldap_search_ext_sW
0x180026618  test    eax, eax
0x18002661a  jnz     loc_180026563
0x180026620  mov     rdx, [rsp+150h+var_F0]; res
0x180026625  mov     rcx, rbx; ld
0x180026628  call    cs:__imp_ldap_first_entry
0x18002662e  mov     rdi, rax
0x180026631  test    rax, rax
0x180026634  jz      loc_180026585
0x18002663a  mov     r8, [rbp+50h+var_58]; attr
0x18002663e  mov     rdx, rax; entry
0x180026641  mov     rcx, rbx; ld
0x180026644  call    cs:__imp_ldap_get_valuesW
0x18002664a  mov     r12, rax
0x18002664d  test    rax, rax
0x180026650  jz      loc_180026585
0x180026656  mov     rsi, [rax]
0x180026659  xor     eax, eax
0x18002665b  test    rsi, rsi
0x18002665e  jz      loc_1800267C0
0x180026664  cmp     [rsi], ax
0x180026667  jz      loc_1800267C0
0x18002666d  lea     edx, [rax+3Bh]; Ch
0x180026670  mov     rcx, rsi; Str
0x180026673  call    cs:__imp_wcschr
0x180026679  xor     ecx, ecx
0x18002667b  test    rax, rax
0x18002667e  jz      short loc_180026683
0x180026680  mov     [rax], cx
0x180026683  mov     r8, [rbp+50h+var_50]; attr
0x180026687  mov     rdx, rdi; entry
0x18002668a  mov     rcx, rbx; ld
0x18002668d  call    cs:__imp_ldap_get_valuesW
0x180026693  xor     ebx, ebx
0x180026695  mov     r15, rax
0x180026698  test    rax, rax
0x18002669b  jz      loc_180026585
0x1800266a1  mov     rdi, [rax]
0x1800266a4  test    rdi, rdi
0x1800266a7  jz      loc_1800267C0
0x1800266ad  cmp     [rdi], bx
0x1800266b0  jz      loc_1800267C0
0x1800266b6  lea     edx, [rbx+3Bh]; Ch
0x1800266b9  mov     rcx, rdi; Str
0x1800266bc  call    cs:__imp_wcschr
0x1800266c2  test    rax, rax
0x1800266c5  jz      short loc_1800266CA
0x1800266c7  mov     [rax], bx
0x1800266ca  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800266ce  mov     rdx, rax
0x1800266d1  inc     rdx
0x1800266d4  cmp     [rdi+rdx*2], bx
0x1800266d8  jnz     short loc_1800266D1
0x1800266da  mov     rcx, rax
0x1800266dd  inc     rcx
0x1800266e0  cmp     [rsi+rcx*2], bx
0x1800266e4  jnz     short loc_1800266DD
0x1800266e6  cmp     rcx, rdx
0x1800266e9  mov     r8, rdi
0x1800266ec  mov     rcx, rax
0x1800266ef  cmova   r8, rsi
0x1800266f3  inc     rcx
0x1800266f6  cmp     [r8+rcx*2], bx
0x1800266fb  jnz     short loc_1800266F3
0x1800266fd  inc     rax
0x180026700  cmp     [r14+rax*2], bx
0x180026705  jnz     short loc_1800266FD
0x180026707  add     ecx, 2
0x18002670a  lea     rdx, [rsp+150h+Buffer]; Buffer
0x18002670f  add     eax, ecx
0x180026711  mov     dword ptr [rsp+150h+cchDest], eax
0x180026715  lea     ecx, [rax+rax]; ByteCount
0x180026718  call    cs:__imp_NetApiBufferAllocate
0x18002671e  mov     ebx, eax
0x180026720  test    eax, eax
0x180026722  jnz     loc_1800267C5
0x180026728  mov     edx, dword ptr [rsp+150h+cchDest]; cchDest
0x18002672c  lea     r8, aWsWs; "%ws:%ws"
0x180026733  mov     rcx, [rsp+150h+Buffer]; pszDest
0x180026738  mov     r9, r14
0x18002673b  mov     [rsp+150h+attrs], rsi
0x180026740  call    StringCchPrintfW
0x180026745  mov     rax, [rsp+150h+Buffer]
0x18002674a  lea     r8, [rbp+50h+mods]; mods
0x18002674e  mov     rsi, [rbp+50h+ld]
0x180026752  xor     edx, edx; dn
0x180026754  mov     rcx, rsi; ld
0x180026757  mov     qword ptr [rsp+150h+var_D8], rax
0x18002675c  mov     qword ptr [rbp+50h+var_D8+8], 0
0x180026764  call    cs:__imp_ldap_modify_sW
0x18002676a  test    eax, eax
0x18002676c  jnz     loc_180026563
0x180026772  cmp     dword ptr [rsp+150h+cchDest+4], 3
0x180026777  jnz     short loc_1800267C5
0x180026779  mov     edx, dword ptr [rsp+150h+cchDest]; cchDest
0x18002677d  lea     r8, aWsWs; "%ws:%ws"
0x180026784  mov     rcx, [rsp+150h+Buffer]; pszDest
0x180026789  mov     r9, r14
0x18002678c  mov     [rsp+150h+attrs], rdi
0x180026791  call    StringCchPrintfW
0x180026796  mov     rax, [rsp+150h+Buffer]
0x18002679b  lea     r8, [rbp+50h+mods]; mods
0x18002679f  xor     edx, edx; dn
0x1800267a1  mov     qword ptr [rsp+150h+var_D8], rax
0x1800267a6  mov     rcx, rsi; ld
0x1800267a9  mov     qword ptr [rbp+50h+var_D8+8], 0
0x1800267b1  call    cs:__imp_ldap_modify_sW
0x1800267b7  test    eax, eax
0x1800267b9  jz      short loc_1800267C5
0x1800267bb  jmp     loc_180026563
0x1800267c0  mov     ebx, 207Ch
0x1800267c5  mov     rcx, [rsp+150h+Buffer]; Buffer
0x1800267ca  test    rcx, rcx
0x1800267cd  jz      short loc_1800267D5
0x1800267cf  call    cs:__imp_NetApiBufferFree
0x1800267d5  test    r13, r13
0x1800267d8  jz      short loc_1800267E3
0x1800267da  mov     rcx, r13; vals
0x1800267dd  call    cs:__imp_ldap_value_freeW
0x1800267e3  test    r12, r12
0x1800267e6  jz      short loc_1800267F1
0x1800267e8  mov     rcx, r12; vals
0x1800267eb  call    cs:__imp_ldap_value_freeW
0x1800267f1  test    r15, r15
0x1800267f4  jz      short loc_1800267FF
0x1800267f6  mov     rcx, r15; vals
0x1800267f9  call    cs:__imp_ldap_value_freeW
0x1800267ff  mov     rcx, [rsp+150h+var_F0]; res
0x180026804  test    rcx, rcx
0x180026807  jz      short loc_18002680F
0x180026809  call    cs:__imp_ldap_msgfree
0x18002680f  mov     eax, ebx
0x180026811  mov     rcx, [rbp+50h+var_40]
0x180026815  xor     rcx, rsp; StackCookie
0x180026818  call    __security_check_cookie
0x18002681d  mov     rbx, [rsp+150h+arg_18]
0x180026825  add     rsp, 120h
0x18002682c  pop     r15
0x18002682e  pop     r14
0x180026830  pop     r13
0x180026832  pop     r12
0x180026834  pop     rdi
0x180026835  pop     rsi
0x180026836  pop     rbp
0x180026837  retn
```
