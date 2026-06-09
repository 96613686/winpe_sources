# SetObjectSD(ushort const *,_SE_OBJECT_TYPE,void *)

- ea: `0x14000578c`
- end: `0x140005928`
- name: `?SetObjectSD@@YAJPEBGW4_SE_OBJECT_TYPE@@PEAX@Z`
- size: `412`
- prototype: `__int64 __fastcall(LPWSTR pObjectName, enum _SE_OBJECT_TYPE, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140004c20`
- `0x14000563c`

## callees

- `0x140001008`
- `0x14000578c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x14000584f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x14000584f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x1400057e6`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x1400057e6`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x140005807`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x140005807`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x14000582a`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x14000582a`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x14000588a`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x14000588a`

## pseudocode

```c
__int64 __fastcall SetObjectSD(LPWSTR pObjectName, enum _SE_OBJECT_TYPE a2, void *a3)
{
  SECURITY_INFORMATION v5; // ebx
  signed int v6; // ebx
  int v7; // r8d
  int v8; // r9d
  signed int v10; // [rsp+40h] [rbp-30h] BYREF
  int v11; // [rsp+44h] [rbp-2Ch] BYREF
  PSID pGroup; // [rsp+48h] [rbp-28h] BYREF
  PSID pOwner; // [rsp+50h] [rbp-20h] BYREF
  PACL pSacl; // [rsp+58h] [rbp-18h] BYREF
  PACL pDacl; // [rsp+60h] [rbp-10h] BYREF
  const char *v16; // [rsp+68h] [rbp-8h] BYREF
  WINBOOL bOwnerDefaulted; // [rsp+98h] [rbp+28h] BYREF
  WINBOOL bDaclPresent; // [rsp+A8h] [rbp+38h] BYREF

  pOwner = 0;
  pGroup = 0;
  pDacl = 0;
  pSacl = 0;
  bDaclPresent = 0;
  bOwnerDefaulted = 0;
  v5 = 0;
  if ( GetSecurityDescriptorOwner(a3, &pOwner, &bOwnerDefaulted) )
    v5 = pOwner != 0;
  if ( GetSecurityDescriptorGroup(a3, &pGroup, &bOwnerDefaulted) && pGroup )
    v5 |= 2u;
  if ( GetSecurityDescriptorDacl(a3, &bDaclPresent, &pDacl, &bOwnerDefaulted) && bDaclPresent )
    v5 |= 0x80000004;
  if ( GetSecurityDescriptorSacl(a3, &bDaclPresent, &pSacl, &bOwnerDefaulted) && bDaclPresent )
    v5 |= 8u;
  v6 = SetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, v5, pOwner, pGroup, pDacl, pSacl);
  if ( !v6 )
    return 0;
  if ( (unsigned int)dword_14000E000 > 2
    && (qword_14000E010 & 0x800) != 0
    && (qword_14000E018 & 0x800) == qword_14000E018 )
  {
    v10 = v6;
    v16 = "onecore\\xbox\\gameinput\\published\\svc\\sfpmodify.cpp";
    v11 = 81;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      qword_14000E018,
      (unsigned int)&byte_14000B727,
      v7,
      v8,
      (__int64)&v16,
      (__int64)&v11,
      (__int64)&v10);
  }
  if ( v6 > 0 )
    return (unsigned __int16)v6 | 0x80070000;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14000578c  mov     [rsp-18h+arg_0], rbx
0x140005791  mov     [rsp-18h+arg_10], rsi
0x140005796  mov     [rsp-18h+bOwnerDefaulted], edx
0x14000579a  push    rbp
0x14000579b  push    rdi
0x14000579c  push    r15
0x14000579e  mov     rbp, rsp
0x1400057a1  sub     rsp, 70h
0x1400057a5  mov     rdi, r8
0x1400057a8  mov     [rbp+pOwner], 0
0x1400057b0  mov     rsi, rcx
0x1400057b3  mov     [rbp+pGroup], 0
0x1400057bb  mov     rcx, rdi; pSecurityDescriptor
0x1400057be  mov     [rbp+pDacl], 0
0x1400057c6  lea     r8, [rbp+bOwnerDefaulted]; lpbOwnerDefaulted
0x1400057ca  mov     [rbp+pSacl], 0
0x1400057d2  lea     rdx, [rbp+pOwner]; pOwner
0x1400057d6  mov     [rbp+bDaclPresent], 0
0x1400057dd  mov     [rbp+bOwnerDefaulted], 0
0x1400057e4  xor     ebx, ebx
0x1400057e6  call    cs:__imp_GetSecurityDescriptorOwner
0x1400057ec  lea     r15d, [rbx+1]
0x1400057f0  test    eax, eax
0x1400057f2  jz      short loc_1400057FC
0x1400057f4  cmp     [rbp+pOwner], rbx
0x1400057f8  cmovnz  ebx, r15d
0x1400057fc  lea     r8, [rbp+bOwnerDefaulted]; lpbGroupDefaulted
0x140005800  mov     rcx, rdi; pSecurityDescriptor
0x140005803  lea     rdx, [rbp+pGroup]; pGroup
0x140005807  call    cs:__imp_GetSecurityDescriptorGroup
0x14000580d  test    eax, eax
0x14000580f  jz      short loc_14000581B
0x140005811  cmp     [rbp+pGroup], 0
0x140005816  jz      short loc_14000581B
0x140005818  or      ebx, 2
0x14000581b  lea     r9, [rbp+bOwnerDefaulted]; lpbDaclDefaulted
0x14000581f  mov     rcx, rdi; pSecurityDescriptor
0x140005822  lea     r8, [rbp+pDacl]; pDacl
0x140005826  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x14000582a  call    cs:__imp_GetSecurityDescriptorDacl
0x140005830  test    eax, eax
0x140005832  jz      short loc_140005840
0x140005834  cmp     [rbp+bDaclPresent], 0
0x140005838  jz      short loc_140005840
0x14000583a  or      ebx, 80000004h
0x140005840  lea     r9, [rbp+bOwnerDefaulted]; lpbSaclDefaulted
0x140005844  mov     rcx, rdi; pSecurityDescriptor
0x140005847  lea     r8, [rbp+pSacl]; pSacl
0x14000584b  lea     rdx, [rbp+bDaclPresent]; lpbSaclPresent
0x14000584f  call    cs:__imp_GetSecurityDescriptorSacl
0x140005855  test    eax, eax
0x140005857  jz      short loc_140005862
0x140005859  cmp     [rbp+bDaclPresent], 0
0x14000585d  jz      short loc_140005862
0x14000585f  or      ebx, 8
0x140005862  mov     rax, [rbp+pSacl]
0x140005866  mov     r8d, ebx; SecurityInfo
0x140005869  mov     r9, [rbp+pOwner]; psidOwner
0x14000586d  mov     edx, r15d; ObjectType
0x140005870  mov     [rsp+70h+var_40], rax; pSacl
0x140005875  mov     rcx, rsi; pObjectName
0x140005878  mov     rax, [rbp+pDacl]
0x14000587c  mov     [rsp+70h+var_48], rax; pDacl
0x140005881  mov     rax, [rbp+pGroup]
0x140005885  mov     [rsp+70h+psidGroup], rax; psidGroup
0x14000588a  call    cs:__imp_SetNamedSecurityInfoW
0x140005890  mov     ebx, eax
0x140005892  test    eax, eax
0x140005894  jz      short loc_140005911
0x140005896  mov     eax, cs:dword_14000E000
0x14000589c  cmp     eax, 2
0x14000589f  jbe     short loc_140005900
0x1400058a1  mov     rcx, cs:qword_14000E018
0x1400058a8  mov     edx, 800h
0x1400058ad  mov     rax, cs:qword_14000E010
0x1400058b4  test    rdx, rax
0x1400058b7  jz      short loc_140005900
0x1400058b9  mov     rax, rcx
0x1400058bc  and     rax, rdx
0x1400058bf  cmp     rax, rcx
0x1400058c2  jnz     short loc_140005900
0x1400058c4  lea     rax, aOnecoreXboxGam_5; "onecore\\xbox\\gameinput\\published\\sv"...
0x1400058cb  mov     [rbp+var_30], ebx
0x1400058ce  mov     [rbp+var_8], rax
0x1400058d2  lea     rdx, byte_14000B727
0x1400058d9  lea     rax, [rbp+var_30]
0x1400058dd  mov     [rbp+var_2C], 51h ; 'Q'
0x1400058e4  mov     [rsp+70h+var_40], rax
0x1400058e9  lea     rax, [rbp+var_2C]
0x1400058ed  mov     [rsp+70h+var_48], rax
0x1400058f2  lea     rax, [rbp+var_8]
0x1400058f6  mov     [rsp+70h+psidGroup], rax
0x1400058fb  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140005900  test    ebx, ebx
0x140005902  jle     short loc_14000590D
0x140005904  movzx   ebx, bx
0x140005907  or      ebx, 80070000h
0x14000590d  mov     eax, ebx
0x14000590f  jmp     short loc_140005913
0x140005911  xor     eax, eax
0x140005913  lea     r11, [rsp+70h+var_s0]
0x140005918  mov     rbx, [r11+20h]
0x14000591c  mov     rsi, [r11+30h]
0x140005920  mov     rsp, r11
0x140005923  pop     r15
0x140005925  pop     rdi
0x140005926  pop     rbp
0x140005927  retn
```
