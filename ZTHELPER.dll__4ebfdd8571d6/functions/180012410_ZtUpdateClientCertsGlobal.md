# ZtUpdateClientCertsGlobal

- ea: `0x180012410`
- end: `0x18001255e`
- name: `ZtUpdateClientCertsGlobal`
- size: `334`
- prototype: `__int64 __fastcall(int, __int64, LPVOID **)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x180009420`
- `0x18000ddec`

## callees

- `0x18000da90`
- `0x180012284`
- `0x180012410`
- `0x180015008`
- `0x180015114`
- `0x1800167ec`
- `0x180016858`

## import_xrefs

- `CRYPT32!CertFreeCertificateContext` at `0x1800124c9`
- `CRYPT32!CertFreeCertificateContext` at `0x180012526`
- `CRYPT32!CertFreeCertificateContext` at `0x1800124c9`
- `CRYPT32!CertFreeCertificateContext` at `0x180012526`

## pseudocode

```c
__int64 __fastcall ZtUpdateClientCertsGlobal(int a1, __int64 a2, LPVOID **a3)
{
  unsigned int ClientCertContext; // ebx
  bool v7; // zf
  const CERT_CONTEXT *v8; // rsi
  int updated; // eax
  __int64 v11; // rdx
  __int64 v12; // r8
  const CERT_CONTEXT *v13; // rcx
  PCCERT_CONTEXT pCertContext[7]; // [rsp+40h] [rbp-38h] BYREF

  if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
    WPP_SF_dqqq(a1, a2, (_DWORD)a3, a1, a2, (__int64)a3);
  if ( !a2 )
  {
    ClientCertContext = 87;
    goto LABEL_15;
  }
  v7 = *(_DWORD *)(a2 + 40) == 0;
  pCertContext[0] = 0;
  if ( !v7 || *(_DWORD *)(a2 + 24) )
  {
    v8 = 0;
    ClientCertContext = GetClientCertContext(a2, pCertContext);
    if ( ClientCertContext )
    {
      v13 = pCertContext[0];
    }
    else
    {
      v8 = pCertContext[0];
      v13 = 0;
    }
    if ( v13 )
      CertFreeCertificateContext(v13);
    if ( ClientCertContext && ClientCertContext != 1168 )
    {
      if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
        WPP_SF_DD(v13, v11, v12, ClientCertContext, ClientCertContext);
      goto LABEL_13;
    }
  }
  else
  {
    if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
      WPP_SF_(1035, 0xCu, (ULONGLONG)WPP_9def979debf939f6192d96d7c9b80830_Traceguids);
    v8 = 0;
  }
  updated = ZtUpdateClientCertConfigGlobal(a1, a2, v8, a3);
  ClientCertContext = updated;
  if ( updated && (BYTE1(xmmword_18001F260) & 8) != 0 )
    WPP_SF_d(1035, 0x12u, (ULONGLONG)WPP_9def979debf939f6192d96d7c9b80830_Traceguids, updated);
LABEL_13:
  if ( v8 )
    CertFreeCertificateContext(v8);
LABEL_15:
  if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
    WPP_SF_d(1035, 0x13u, (ULONGLONG)WPP_9def979debf939f6192d96d7c9b80830_Traceguids, ClientCertContext);
  return ClientCertContext;
}

```

## disassembly

```asm
0x180012410  push    rbx
0x180012412  push    rbp
0x180012413  push    rsi
0x180012414  push    rdi
0x180012415  push    r14
0x180012417  sub     rsp, 50h
0x18001241b  mov     r14, r8
0x18001241e  mov     rdi, rdx
0x180012421  mov     ebp, ecx
0x180012423  test    byte ptr cs:xmmword_18001F260+1, 8
0x18001242a  jz      short loc_18001243E
0x18001242c  mov     [rsp+78h+var_50], r8
0x180012431  mov     r9d, ecx
0x180012434  mov     [rsp+78h+var_58], rdx
0x180012439  call    WPP_SF_dqqq
0x18001243e  test    rdi, rdi
0x180012441  jnz     short loc_18001244B
0x180012443  lea     ebx, [rdi+57h]
0x180012446  jmp     loc_1800124CF
0x18001244b  cmp     dword ptr [rdi+28h], 0
0x18001244f  mov     [rsp+78h+pCertContext], 0
0x180012458  jnz     loc_1800124FE
0x18001245e  cmp     dword ptr [rdi+18h], 0
0x180012462  jnz     loc_1800124FE
0x180012468  test    byte ptr cs:xmmword_18001F260+1, 8
0x18001246f  jz      short loc_180012487
0x180012471  mov     edx, 0Ch
0x180012476  lea     r8, WPP_9def979debf939f6192d96d7c9b80830_Traceguids
0x18001247d  mov     ecx, 40Bh
0x180012482  call    WPP_SF_
0x180012487  xor     esi, esi
0x180012489  mov     r9, r14
0x18001248c  mov     r8, rsi
0x18001248f  mov     rdx, rdi
0x180012492  mov     ecx, ebp
0x180012494  call    ZtUpdateClientCertConfigGlobal
0x180012499  mov     ebx, eax
0x18001249b  test    eax, eax
0x18001249d  jz      short loc_1800124C1
0x18001249f  test    byte ptr cs:xmmword_18001F260+1, 8
0x1800124a6  jz      short loc_1800124C1
0x1800124a8  mov     edx, 12h
0x1800124ad  lea     r8, WPP_9def979debf939f6192d96d7c9b80830_Traceguids
0x1800124b4  mov     ecx, 40Bh
0x1800124b9  mov     r9d, eax
0x1800124bc  call    WPP_SF_d
0x1800124c1  test    rsi, rsi
0x1800124c4  jz      short loc_1800124CF
0x1800124c6  mov     rcx, rsi; pCertContext
0x1800124c9  call    cs:__imp_CertFreeCertificateContext
0x1800124cf  test    byte ptr cs:xmmword_18001F260+1, 8
0x1800124d6  jz      short loc_1800124F1
0x1800124d8  mov     edx, 13h
0x1800124dd  lea     r8, WPP_9def979debf939f6192d96d7c9b80830_Traceguids
0x1800124e4  mov     ecx, 40Bh
0x1800124e9  mov     r9d, ebx
0x1800124ec  call    WPP_SF_d
0x1800124f1  mov     eax, ebx
0x1800124f3  add     rsp, 50h
0x1800124f7  pop     r14
0x1800124f9  pop     rdi
0x1800124fa  pop     rsi
0x1800124fb  pop     rbp
0x1800124fc  pop     rbx
0x1800124fd  retn
0x1800124fe  lea     rdx, [rsp+78h+pCertContext]
0x180012503  mov     rcx, rdi
0x180012506  call    GetClientCertContext
0x18001250b  xor     esi, esi
0x18001250d  mov     ebx, eax
0x18001250f  test    eax, eax
0x180012511  jnz     short loc_18001251C
0x180012513  mov     rsi, [rsp+78h+pCertContext]
0x180012518  xor     ecx, ecx
0x18001251a  jmp     short loc_180012521
0x18001251c  mov     rcx, [rsp+78h+pCertContext]; pCertContext
0x180012521  test    rcx, rcx
0x180012524  jz      short loc_18001252C
0x180012526  call    cs:__imp_CertFreeCertificateContext
0x18001252c  test    ebx, ebx
0x18001252e  jz      loc_180012489
0x180012534  cmp     ebx, 490h
0x18001253a  jz      loc_180012489
0x180012540  test    byte ptr cs:xmmword_18001F260+1, 8
0x180012547  jz      loc_1800124C1
0x18001254d  mov     r9d, ebx
0x180012550  mov     dword ptr [rsp+78h+var_58], ebx
0x180012554  call    WPP_SF_DD
0x180012559  jmp     loc_1800124C1
```
