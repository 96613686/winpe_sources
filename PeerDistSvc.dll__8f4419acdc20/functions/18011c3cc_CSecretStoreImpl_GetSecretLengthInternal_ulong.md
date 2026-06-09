# CSecretStoreImpl::GetSecretLengthInternal(ulong *)

- ea: `0x18011c3cc`
- end: `0x18011c683`
- name: `?GetSecretLengthInternal@CSecretStoreImpl@@AEAAJPEAK@Z`
- size: `695`
- prototype: `__int64 __fastcall(CSecretStoreImpl *__hidden this, unsigned int *)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18011bd00`
- `0x18011bf30`
- `0x18011c360`

## callees

- `0x180004374`
- `0x180008290`
- `0x1800082d0`
- `0x1800083bc`
- `0x18011c3cc`
- `0x180144882`
- `0x1801448c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18011c4ca`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18011c4ca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18011c5d4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18011c5d4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18011c54d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18011c54d`

## string_xrefs

- `0x18011c53c`: `SecurityManager\Restricted`

## pseudocode

```c
__int64 __fastcall CSecretStoreImpl::GetSecretLengthInternal(CSecretStoreImpl *this, unsigned int *a2)
{
  CHostedCacheMsgEncoding *v3; // rbx
  unsigned int v4; // edi
  int ValueW; // eax
  CHostedCacheMsgEncoding *v6; // rcx
  __int64 v7; // rdx
  LSTATUS v8; // eax
  const char *v9; // r9
  DWORD pdwType; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE pvData[528]; // [rsp+50h] [rbp-B0h] BYREF

  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 21, "z");
    v3 = WPP_GLOBAL_Control;
  }
  pdwType = 0;
  hkey = 0;
  memset_0(pvData, 0, 0x208u);
  pcbData = 520;
  if ( !a2 )
  {
    v4 = -2147024809;
    if ( v3 == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
      return v4;
    if ( (*((_DWORD *)v3 + 27) & 0x800000) == 0 || !*((_BYTE *)v3 + 105) )
      goto LABEL_44;
    WPP_SF_q(*((_QWORD *)v3 + 12), 22, "z");
    goto LABEL_33;
  }
  ValueW = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows NT\\CurrentVersion\\PeerDist",
             0,
             0x20119u,
             &hkey);
  if ( ValueW )
  {
    if ( ValueW > 0 )
      ValueW = (unsigned __int16)ValueW | 0x80070000;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800000) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      goto LABEL_18;
    }
    v7 = 23;
LABEL_17:
    WPP_SF_d(*((_QWORD *)v6 + 12), v7, "z", (unsigned int)ValueW);
LABEL_18:
    *a2 = 0;
LABEL_32:
    v4 = 0;
    goto LABEL_33;
  }
  ValueW = RegGetValueW(hkey, L"SecurityManager\\Restricted", L"Seed", 0x1000FFFFu, &pdwType, pvData, &pcbData);
  if ( ValueW )
  {
    if ( ValueW > 0 )
      ValueW = (unsigned __int16)ValueW | 0x80070000;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800000) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      goto LABEL_18;
    }
    v7 = 24;
    goto LABEL_17;
  }
  if ( pdwType == 3 )
  {
    *a2 = pcbData;
    goto LABEL_32;
  }
  v4 = -2147020833;
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 25, "z");
LABEL_33:
    v3 = WPP_GLOBAL_Control;
  }
  if ( hkey )
  {
    v8 = RegCloseKey(hkey);
    if ( !v8 )
    {
LABEL_43:
      v3 = WPP_GLOBAL_Control;
      goto LABEL_44;
    }
    if ( v8 > 0 )
      v4 = (unsigned __int16)v8 | 0x80070000;
    else
      v4 = v8;
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
      return v4;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800000) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 26, "z", v4);
      goto LABEL_43;
    }
  }
LABEL_44:
  if ( v3 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_DWORD *)v3 + 27) & 0x800000) != 0
    && *((_BYTE *)v3 + 105) >= 4u )
  {
    v9 = "success";
    if ( (v4 & 0x80000000) != 0 )
      v9 = "failure";
    WPP_SF_sd(*((_QWORD *)v3 + 12), 27, (unsigned int)"z", (_DWORD)v9, v4);
  }
  return v4;
}

```

## disassembly

```asm
0x18011c3cc  push    rbp
0x18011c3ce  push    rbx
0x18011c3cf  push    rsi
0x18011c3d0  push    rdi
0x18011c3d1  push    r12
0x18011c3d3  push    r15
0x18011c3d5  lea     rbp, [rsp-178h]
0x18011c3dd  sub     rsp, 278h
0x18011c3e4  mov     rax, cs:__security_cookie
0x18011c3eb  xor     rax, rsp
0x18011c3ee  mov     [rbp+1A0h+var_40], rax
0x18011c3f5  mov     rsi, rdx
0x18011c3f8  mov     rbx, cs:WPP_GLOBAL_Control
0x18011c3ff  lea     r12, WPP_GLOBAL_Control
0x18011c406  mov     r15d, 800000h
0x18011c40c  cmp     rbx, r12
0x18011c40f  jz      short loc_18011C439
0x18011c411  test    [rbx+6Ch], r15d
0x18011c415  jz      short loc_18011C439
0x18011c417  cmp     byte ptr [rbx+69h], 4
0x18011c41b  jb      short loc_18011C439
0x18011c41d  mov     rcx, [rbx+60h]
0x18011c421  lea     r8, WPP_1049007aec7c3d5a044c075193d085a0_Traceguids; "z"
0x18011c428  mov     edx, 15h
0x18011c42d  call    WPP_SF_
0x18011c432  mov     rbx, cs:WPP_GLOBAL_Control
0x18011c439  mov     edi, 208h
0x18011c43e  mov     [rsp+2A0h+pdwType], 0
0x18011c446  mov     r8d, edi; Size
0x18011c449  mov     [rsp+2A0h+hkey], 0
0x18011c452  xor     edx, edx; Val
0x18011c454  lea     rcx, [rsp+2A0h+var_250]; void *
0x18011c459  call    memset_0
0x18011c45e  mov     [rsp+2A0h+var_25C], edi
0x18011c462  mov     edi, 80070000h
0x18011c467  test    rsi, rsi
0x18011c46a  jnz     short loc_18011C4A9
0x18011c46c  mov     edi, 80070057h
0x18011c471  cmp     rbx, r12
0x18011c474  jz      loc_18011C662
0x18011c47a  test    [rbx+6Ch], r15d
0x18011c47e  jz      loc_18011C624
0x18011c484  cmp     byte ptr [rbx+69h], 1
0x18011c488  jb      loc_18011C624
0x18011c48e  mov     rcx, [rbx+60h]
0x18011c492  lea     edx, [rsi+16h]
0x18011c495  xor     r9d, r9d
0x18011c498  lea     r8, WPP_1049007aec7c3d5a044c075193d085a0_Traceguids; "z"
0x18011c49f  call    WPP_SF_q
0x18011c4a4  jmp     loc_18011C5C3
0x18011c4a9  lea     rax, [rsp+2A0h+hkey]
0x18011c4ae  mov     r9d, 20119h; samDesired
0x18011c4b4  xor     r8d, r8d; ulOptions
0x18011c4b7  mov     [rsp+2A0h+phkResult], rax; phkResult
0x18011c4bc  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows NT\\Curren"...
0x18011c4c3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18011c4ca  call    cs:__imp_RegOpenKeyExW
0x18011c4d0  test    eax, eax
0x18011c4d2  jz      short loc_18011C516
0x18011c4d4  jle     short loc_18011C4DB
0x18011c4d6  movzx   eax, ax
0x18011c4d9  or      eax, edi
0x18011c4db  mov     rcx, cs:WPP_GLOBAL_Control
0x18011c4e2  cmp     rcx, r12
0x18011c4e5  jz      short loc_18011C50B
0x18011c4e7  test    [rcx+6Ch], r15d
0x18011c4eb  jz      short loc_18011C50B
0x18011c4ed  cmp     byte ptr [rcx+69h], 1
0x18011c4f1  jb      short loc_18011C50B
0x18011c4f3  mov     edx, 17h
0x18011c4f8  mov     rcx, [rcx+60h]
0x18011c4fc  lea     r8, WPP_1049007aec7c3d5a044c075193d085a0_Traceguids; "z"
0x18011c503  mov     r9d, eax
0x18011c506  call    WPP_SF_d
0x18011c50b  mov     dword ptr [rsi], 0
0x18011c511  jmp     loc_18011C5C1
0x18011c516  mov     rcx, [rsp+2A0h+hkey]; hkey
0x18011c51b  lea     rax, [rsp+2A0h+var_25C]
0x18011c520  mov     [rsp+2A0h+pcbData], rax; pcbData
0x18011c525  lea     r8, Value; "Seed"
0x18011c52c  lea     rax, [rsp+2A0h+var_250]
0x18011c531  mov     r9d, 1000FFFFh; dwFlags
0x18011c537  mov     [rsp+2A0h+pvData], rax; pvData
0x18011c53c  lea     rdx, aSecuritymanage_1; "SecurityManager\\Restricted"
0x18011c543  lea     rax, [rsp+2A0h+pdwType]
0x18011c548  mov     [rsp+2A0h+phkResult], rax; pdwType
0x18011c54d  call    cs:__imp_RegGetValueW
0x18011c553  test    eax, eax
0x18011c555  jz      short loc_18011C580
0x18011c557  jle     short loc_18011C55E
0x18011c559  movzx   eax, ax
0x18011c55c  or      eax, edi
0x18011c55e  mov     rcx, cs:WPP_GLOBAL_Control
0x18011c565  cmp     rcx, r12
0x18011c568  jz      short loc_18011C50B
0x18011c56a  test    [rcx+6Ch], r15d
0x18011c56e  jz      short loc_18011C50B
0x18011c570  cmp     byte ptr [rcx+69h], 1
0x18011c574  jb      short loc_18011C50B
0x18011c576  mov     edx, 18h
0x18011c57b  jmp     loc_18011C4F8
0x18011c580  cmp     [rsp+2A0h+pdwType], 3
0x18011c585  jz      short loc_18011C5BB
0x18011c587  mov     edi, 80070FDFh
0x18011c58c  mov     rbx, cs:WPP_GLOBAL_Control
0x18011c593  cmp     rbx, r12
0x18011c596  jz      short loc_18011C5CA
0x18011c598  test    [rbx+6Ch], r15d
0x18011c59c  jz      short loc_18011C5CA
0x18011c59e  cmp     byte ptr [rbx+69h], 1
0x18011c5a2  jb      short loc_18011C5CA
0x18011c5a4  mov     rcx, [rbx+60h]
0x18011c5a8  lea     r8, WPP_1049007aec7c3d5a044c075193d085a0_Traceguids; "z"
0x18011c5af  mov     edx, 19h
0x18011c5b4  call    WPP_SF_
0x18011c5b9  jmp     short loc_18011C5C3
0x18011c5bb  mov     eax, [rsp+2A0h+var_25C]
0x18011c5bf  mov     [rsi], eax
0x18011c5c1  xor     edi, edi
0x18011c5c3  mov     rbx, cs:WPP_GLOBAL_Control
0x18011c5ca  mov     rcx, [rsp+2A0h+hkey]; hKey
0x18011c5cf  test    rcx, rcx
0x18011c5d2  jz      short loc_18011C624
0x18011c5d4  call    cs:__imp_RegCloseKey
0x18011c5da  test    eax, eax
0x18011c5dc  jz      short loc_18011C61D
0x18011c5de  jg      short loc_18011C5E4
0x18011c5e0  mov     edi, eax
0x18011c5e2  jmp     short loc_18011C5ED
0x18011c5e4  movzx   edi, ax
0x18011c5e7  or      edi, 80070000h
0x18011c5ed  mov     rbx, cs:WPP_GLOBAL_Control
0x18011c5f4  cmp     rbx, r12
0x18011c5f7  jz      short loc_18011C662
0x18011c5f9  test    [rbx+6Ch], r15d
0x18011c5fd  jz      short loc_18011C624
0x18011c5ff  cmp     byte ptr [rbx+69h], 1
0x18011c603  jb      short loc_18011C624
0x18011c605  mov     rcx, [rbx+60h]
0x18011c609  lea     r8, WPP_1049007aec7c3d5a044c075193d085a0_Traceguids; "z"
0x18011c610  mov     edx, 1Ah
0x18011c615  mov     r9d, edi
0x18011c618  call    WPP_SF_d
0x18011c61d  mov     rbx, cs:WPP_GLOBAL_Control
0x18011c624  cmp     rbx, r12
0x18011c627  jz      short loc_18011C662
0x18011c629  test    [rbx+6Ch], r15d
0x18011c62d  jz      short loc_18011C662
0x18011c62f  cmp     byte ptr [rbx+69h], 4
0x18011c633  jb      short loc_18011C662
0x18011c635  mov     rcx, [rbx+60h]
0x18011c639  lea     rax, aFailure; "failure"
0x18011c640  test    edi, edi
0x18011c642  mov     dword ptr [rsp+2A0h+phkResult], edi
0x18011c646  lea     r9, aSuccess; "success"
0x18011c64d  mov     edx, 1Bh
0x18011c652  cmovs   r9, rax
0x18011c656  lea     r8, WPP_1049007aec7c3d5a044c075193d085a0_Traceguids; "z"
0x18011c65d  call    WPP_SF_sd
0x18011c662  mov     eax, edi
0x18011c664  mov     rcx, [rbp+1A0h+var_40]
0x18011c66b  xor     rcx, rsp; StackCookie
0x18011c66e  call    __security_check_cookie
0x18011c673  add     rsp, 278h
0x18011c67a  pop     r15
0x18011c67c  pop     r12
0x18011c67e  pop     rdi
0x18011c67f  pop     rsi
0x18011c680  pop     rbx
0x18011c681  pop     rbp
0x18011c682  retn
```
