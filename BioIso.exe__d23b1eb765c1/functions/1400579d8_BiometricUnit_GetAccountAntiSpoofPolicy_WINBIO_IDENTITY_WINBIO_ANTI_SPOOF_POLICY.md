# BiometricUnit::GetAccountAntiSpoofPolicy(_WINBIO_IDENTITY *,_WINBIO_ANTI_SPOOF_POLICY *)

- ea: `0x1400579d8`
- end: `0x140057aa3`
- name: `?GetAccountAntiSpoofPolicy@BiometricUnit@@QEAAJPEAU_WINBIO_IDENTITY@@PEAU_WINBIO_ANTI_SPOOF_POLICY@@@Z`
- size: `203`
- prototype: `int __fastcall(BiometricUnit *this, struct _WINBIO_IDENTITY *, struct _WINBIO_ANTI_SPOOF_POLICY *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140015a50`

## callees

- `0x14000a420`
- `0x14000d990`
- `0x14002ae40`
- `0x1400579d8`
- `0x140057aac`
- `0x140057b50`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x140057a3e`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x140057a3e`

## string_xrefs

- `0x1400579f4`: `onecore\ds\security\biometrics\service\trustlet\exe\biometricunit.cpp`
- `0x140057a82`: `onecore\ds\security\biometrics\service\trustlet\exe\biometricunit.cpp`

## pseudocode

```c
int __fastcall BiometricUnit::GetAccountAntiSpoofPolicy(
        BiometricUnit *this,
        struct _WINBIO_IDENTITY *a2,
        struct _WINBIO_ANTI_SPOOF_POLICY *a3)
{
  __int64 v5; // rdx
  _DWORD *v7; // rbx
  _DWORD *v8; // rbp
  WINBIO_IDENTITY_TYPE Type; // eax
  BioIsoProvider *v10; // rcx
  unsigned int v11; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( !a2 )
  {
    v5 = 93;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\biometricunit.cpp",
      (const char *)0x80004003LL,
      v11);
    return -2147467261;
  }
  if ( !a3 )
  {
    v5 = 94;
    goto LABEL_3;
  }
  v7 = (_DWORD *)*((_QWORD *)this + 9);
  v8 = (_DWORD *)*((_QWORD *)this + 10);
  while ( 1 )
  {
    if ( v7 == v8 )
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x6F,
               (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\biometricunit.cpp",
               (const char *)0x490,
               v11);
    Type = a2->Type;
    if ( a2->Type == *v7 && (Type == 1 || Type == 3 && EqualSid(a2->Value.AccountSid.Data, v7 + 2)) )
      break;
    v7 += 20;
  }
  *a3 = (struct _WINBIO_ANTI_SPOOF_POLICY)(unsigned int)v7[19];
  if ( BioIsoProvider::IsEnabled((unsigned __int8)this, (unsigned __int64)a2) )
  {
    BioIsoProvider::Instance();
    BioIsoProvider::GetAntiSpoofingPolicy_(v10, a2, a3);
  }
  return 0;
}

```

## disassembly

```asm
0x1400579d8  push    rbx
0x1400579da  push    rbp
0x1400579db  push    rsi
0x1400579dc  push    rdi
0x1400579dd  sub     rsp, 28h
0x1400579e1  mov     rdi, r8
0x1400579e4  mov     rsi, rdx
0x1400579e7  test    rdx, rdx
0x1400579ea  jnz     short loc_140057A0F
0x1400579ec  lea     edx, [rsi+5Dh]; void *
0x1400579ef  mov     rcx, [rsp+48h]; this
0x1400579f4  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\biometrics\\serv"...
0x1400579fb  mov     ebx, 80004003h
0x140057a00  mov     r9d, ebx; char *
0x140057a03  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140057a08  mov     eax, ebx
0x140057a0a  jmp     loc_140057A99
0x140057a0f  test    rdi, rdi
0x140057a12  jnz     short loc_140057A19
0x140057a14  lea     edx, [rdi+5Eh]
0x140057a17  jmp     short loc_1400579EF
0x140057a19  mov     rbx, [rcx+48h]
0x140057a1d  mov     rbp, [rcx+50h]
0x140057a21  cmp     rbx, rbp
0x140057a24  jz      short loc_140057A7D
0x140057a26  mov     eax, [rsi]
0x140057a28  cmp     eax, [rbx]
0x140057a2a  jnz     short loc_140057A4E
0x140057a2c  cmp     eax, 1
0x140057a2f  jz      short loc_140057A54
0x140057a31  cmp     eax, 3
0x140057a34  jnz     short loc_140057A4E
0x140057a36  lea     rdx, [rbx+8]; pSid2
0x140057a3a  lea     rcx, [rsi+8]; pSid1
0x140057a3e  call    cs:__imp_EqualSid
0x140057a45  nop     dword ptr [rax+rax+00h]
0x140057a4a  test    eax, eax
0x140057a4c  jnz     short loc_140057A54
0x140057a4e  add     rbx, 50h ; 'P'
0x140057a52  jmp     short loc_140057A21
0x140057a54  mov     eax, [rbx+4Ch]
0x140057a57  mov     [rdi], eax
0x140057a59  mov     dword ptr [rdi+4], 0
0x140057a60  call    ?IsEnabled@BioIsoProvider@@SA_NE_K@Z; BioIsoProvider::IsEnabled(uchar,unsigned __int64)
0x140057a65  test    al, al
0x140057a67  jz      short loc_140057A79
0x140057a69  call    ?Instance@BioIsoProvider@@KAPEAV1@XZ; BioIsoProvider::Instance(void)
0x140057a6e  mov     r8, rdi; struct _WINBIO_ANTI_SPOOF_POLICY *
0x140057a71  mov     rdx, rsi; struct _WINBIO_IDENTITY *
0x140057a74  call    ?GetAntiSpoofingPolicy_@BioIsoProvider@@QEAAXPEBU_WINBIO_IDENTITY@@PEBU_WINBIO_ANTI_SPOOF_POLICY@@@Z; BioIsoProvider::GetAntiSpoofingPolicy_(_WINBIO_IDENTITY const *,_WINBIO_ANTI_SPOOF_POLICY const *)
0x140057a79  xor     eax, eax
0x140057a7b  jmp     short loc_140057A99
0x140057a7d  mov     rcx, [rsp+48h]; this
0x140057a82  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\biometrics\\serv"...
0x140057a89  mov     r9d, 490h; char *
0x140057a8f  mov     edx, 6Fh ; 'o'; void *
0x140057a94  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140057a99  add     rsp, 28h
0x140057a9d  pop     rdi
0x140057a9e  pop     rsi
0x140057a9f  pop     rbp
0x140057aa0  pop     rbx
0x140057aa1  retn
```
