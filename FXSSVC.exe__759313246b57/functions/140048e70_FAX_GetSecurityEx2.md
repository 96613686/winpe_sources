# FAX_GetSecurityEx2

- ea: `0x140048e70`
- end: `0x140049160`
- name: `FAX_GetSecurityEx2`
- size: `752`
- prototype: `__int64 __fastcall(__int64, SECURITY_INFORMATION, LPVOID *, DWORD *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x140047d20`
- `0x140048e70`
- `0x1400698ec`
- `0x14006998c`

## import_xrefs

- `ADVAPI32!IsValidSecurityDescriptor` at `0x140049009`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x140049009`
- `ADVAPI32!GetPrivateObjectSecurity` at `0x140049072`
- `ADVAPI32!GetPrivateObjectSecurity` at `0x1400490d3`
- `ADVAPI32!GetPrivateObjectSecurity` at `0x140049072`
- `ADVAPI32!GetPrivateObjectSecurity` at `0x1400490d3`
- `KERNEL32!GetLastError` at `0x1400490e3`
- `KERNEL32!GetLastError` at `0x1400490e3`
- `KERNEL32!EnterCriticalSection` at `0x140048f4b`
- `KERNEL32!EnterCriticalSection` at `0x140048f4b`
- `KERNEL32!LeaveCriticalSection` at `0x140049124`
- `KERNEL32!LeaveCriticalSection` at `0x140049124`

## pseudocode

```c
__int64 __fastcall FAX_GetSecurityEx2(__int64 a1, SECURITY_INFORMATION a2, LPVOID *a3, DWORD *a4)
{
  CMapDeviceId *v7; // rcx
  __int64 v8; // rdx
  DWORD v10; // ecx
  unsigned int LastError; // eax
  unsigned int v12; // ebx
  CMapDeviceId *v13; // rcx
  __int64 v14; // rdx
  CMapDeviceId *v15; // rcx
  __int64 v16; // rdx
  void *v17; // rax
  int v18[18]; // [rsp+30h] [rbp-48h] BYREF
  DWORD DescriptorLength; // [rsp+90h] [rbp+18h] BYREF

  DescriptorLength = 0;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids);
    v7 = WPP_GLOBAL_Control;
  }
  v18[0] = 0;
  if ( !a3 )
    return 87;
  if ( (a2 & 0xF) == 0 )
  {
    if ( v7 == (CMapDeviceId *)&WPP_GLOBAL_Control || (*((_BYTE *)v7 + 28) & 4) == 0 || *((_BYTE *)v7 + 25) < 2u )
      return 87;
    v8 = 73;
LABEL_11:
    WPP_SF_(*((_QWORD *)v7 + 2), v8, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids);
    return 87;
  }
  if ( (a2 & 0xFFFFFFF0) != 0 )
  {
    if ( v7 == (CMapDeviceId *)&WPP_GLOBAL_Control || (*((_BYTE *)v7 + 28) & 4) == 0 || *((_BYTE *)v7 + 25) < 2u )
      return 87;
    v8 = 74;
    goto LABEL_11;
  }
  *a3 = 0;
  *a4 = 0;
  EnterCriticalSection(&g_CsSecurity);
  v10 = ((a2 & 7) != 0 ? 0x20000 : 0) | 0x1000000;
  if ( (a2 & 8) == 0 )
    v10 = (a2 & 7) != 0 ? 0x20000 : 0;
  LastError = FaxSvcAccessCheck(v10, v18, 0, 1);
  v12 = LastError;
  if ( LastError )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_49;
    }
    v14 = 75;
    goto LABEL_25;
  }
  if ( !v18[0] )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids);
    }
    v12 = 5;
    goto LABEL_49;
  }
  if ( !IsValidSecurityDescriptor(g_pFaxSD) )
  {
    v12 = 1338;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_49;
    }
    v16 = 77;
    goto LABEL_37;
  }
  GetPrivateObjectSecurity(g_pFaxSD, a2, 0, 0, &DescriptorLength);
  v17 = (void *)pMemAlloc(DescriptorLength);
  *a3 = v17;
  if ( !v17 )
  {
    v12 = 8;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_49;
    }
    v16 = 78;
LABEL_37:
    WPP_SF_(*((_QWORD *)v15 + 2), v16, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids);
    goto LABEL_49;
  }
  if ( !GetPrivateObjectSecurity(g_pFaxSD, a2, v17, DescriptorLength, &DescriptorLength) )
  {
    LastError = GetLastError();
    v12 = LastError;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_49;
    }
    v14 = 79;
LABEL_25:
    WPP_SF_d(*((_QWORD *)v13 + 2), v14, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids, LastError);
    goto LABEL_49;
  }
  *a4 = DescriptorLength;
LABEL_49:
  LeaveCriticalSection(&g_CsSecurity);
  if ( v12 )
  {
    pMemFree(*a3);
    *a3 = 0;
    *a4 = 0;
    if ( v12 == 8 || v12 == 14 )
      return 7001;
  }
  return v12;
}

```

## disassembly

```asm
0x140048e70  mov     rax, rsp
0x140048e73  push    rbx
0x140048e74  push    rsi
0x140048e75  push    rdi
0x140048e76  push    r12
0x140048e78  push    r13
0x140048e7a  push    r14
0x140048e7c  sub     rsp, 48h
0x140048e80  mov     r14, r9
0x140048e83  mov     dword ptr [rax+18h], 0
0x140048e8a  mov     rsi, r8
0x140048e8d  mov     edi, edx
0x140048e8f  mov     rcx, cs:WPP_GLOBAL_Control
0x140048e96  lea     r12, WPP_GLOBAL_Control
0x140048e9d  lea     r13, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids
0x140048ea4  cmp     rcx, r12
0x140048ea7  jz      short loc_140048ECD
0x140048ea9  test    byte ptr [rcx+1Ch], 4
0x140048ead  jz      short loc_140048ECD
0x140048eaf  cmp     byte ptr [rcx+19h], 5
0x140048eb3  jb      short loc_140048ECD
0x140048eb5  mov     rcx, [rcx+10h]
0x140048eb9  mov     edx, 48h ; 'H'
0x140048ebe  mov     r8, r13
0x140048ec1  call    WPP_SF_
0x140048ec6  mov     rcx, cs:WPP_GLOBAL_Control
0x140048ecd  mov     [rsp+78h+var_48], 0
0x140048ed5  test    rsi, rsi
0x140048ed8  jz      short loc_140048F02
0x140048eda  test    dil, 0Fh
0x140048ede  jnz     short loc_140048F16
0x140048ee0  cmp     rcx, r12
0x140048ee3  jz      short loc_140048F02
0x140048ee5  test    byte ptr [rcx+1Ch], 4
0x140048ee9  jz      short loc_140048F02
0x140048eeb  cmp     byte ptr [rcx+19h], 2
0x140048eef  jb      short loc_140048F02
0x140048ef1  mov     edx, 49h ; 'I'
0x140048ef6  mov     rcx, [rcx+10h]
0x140048efa  mov     r8, r13
0x140048efd  call    WPP_SF_
0x140048f02  mov     eax, 57h ; 'W'
0x140048f07  add     rsp, 48h
0x140048f0b  pop     r14
0x140048f0d  pop     r13
0x140048f0f  pop     r12
0x140048f11  pop     rdi
0x140048f12  pop     rsi
0x140048f13  pop     rbx
0x140048f14  retn
0x140048f16  test    edi, 0FFFFFFF0h
0x140048f1c  jz      short loc_140048F36
0x140048f1e  cmp     rcx, r12
0x140048f21  jz      short loc_140048F02
0x140048f23  test    byte ptr [rcx+1Ch], 4
0x140048f27  jz      short loc_140048F02
0x140048f29  cmp     byte ptr [rcx+19h], 2
0x140048f2d  jb      short loc_140048F02
0x140048f2f  mov     edx, 4Ah ; 'J'
0x140048f34  jmp     short loc_140048EF6
0x140048f36  mov     qword ptr [rsi], 0
0x140048f3d  lea     rcx, ?g_CsSecurity@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140048f44  mov     dword ptr [r14], 0
0x140048f4b  call    cs:__imp_EnterCriticalSection
0x140048f52  nop     dword ptr [rax+rax+00h]
0x140048f57  mov     eax, edi
0x140048f59  mov     r9d, 1; int
0x140048f5f  and     al, 7
0x140048f61  neg     al
0x140048f63  sbb     edx, edx
0x140048f65  and     edx, 20000h
0x140048f6b  mov     ecx, edx
0x140048f6d  bts     ecx, 18h
0x140048f71  test    dil, 8
0x140048f75  cmovz   ecx, edx; unsigned int
0x140048f78  xor     r8d, r8d; unsigned int *
0x140048f7b  lea     rdx, [rsp+78h+var_48]; int *
0x140048f80  call    ?FaxSvcAccessCheck@@YAKKPEAHPEAKH@Z; FaxSvcAccessCheck(ulong,int *,ulong *,int)
0x140048f85  mov     ebx, eax
0x140048f87  test    eax, eax
0x140048f89  jz      short loc_140048FC8
0x140048f8b  mov     rcx, cs:WPP_GLOBAL_Control
0x140048f92  cmp     rcx, r12
0x140048f95  jz      loc_14004911D
0x140048f9b  test    byte ptr [rcx+1Ch], 4
0x140048f9f  jz      loc_14004911D
0x140048fa5  cmp     byte ptr [rcx+19h], 2
0x140048fa9  jb      loc_14004911D
0x140048faf  mov     edx, 4Bh ; 'K'
0x140048fb4  mov     rcx, [rcx+10h]
0x140048fb8  mov     r9d, eax
0x140048fbb  mov     r8, r13
0x140048fbe  call    WPP_SF_d
0x140048fc3  jmp     loc_14004911D
0x140048fc8  cmp     [rsp+78h+var_48], 0
0x140048fcd  jnz     short loc_140049002
0x140048fcf  mov     rcx, cs:WPP_GLOBAL_Control
0x140048fd6  cmp     rcx, r12
0x140048fd9  jz      short loc_140048FF8
0x140048fdb  test    byte ptr [rcx+1Ch], 4
0x140048fdf  jz      short loc_140048FF8
0x140048fe1  cmp     byte ptr [rcx+19h], 2
0x140048fe5  jb      short loc_140048FF8
0x140048fe7  mov     rcx, [rcx+10h]
0x140048feb  mov     edx, 4Ch ; 'L'
0x140048ff0  mov     r8, r13
0x140048ff3  call    WPP_SF_
0x140048ff8  mov     ebx, 5
0x140048ffd  jmp     loc_14004911D
0x140049002  mov     rcx, cs:?g_pFaxSD@@3PEAXEA; pSecurityDescriptor
0x140049009  call    cs:__imp_IsValidSecurityDescriptor
0x140049010  nop     dword ptr [rax+rax+00h]
0x140049015  test    eax, eax
0x140049017  jnz     short loc_140049056
0x140049019  mov     ebx, 53Ah
0x14004901e  mov     rcx, cs:WPP_GLOBAL_Control
0x140049025  cmp     rcx, r12
0x140049028  jz      loc_14004911D
0x14004902e  test    byte ptr [rcx+1Ch], 4
0x140049032  jz      loc_14004911D
0x140049038  cmp     byte ptr [rcx+19h], 2
0x14004903c  jb      loc_14004911D
0x140049042  lea     edx, [rax+4Dh]
0x140049045  mov     rcx, [rcx+10h]
0x140049049  mov     r8, r13
0x14004904c  call    WPP_SF_
0x140049051  jmp     loc_14004911D
0x140049056  mov     rcx, cs:?g_pFaxSD@@3PEAXEA; ObjectDescriptor
0x14004905d  lea     rax, [rsp+78h+DescriptorLength]
0x140049065  xor     r9d, r9d; DescriptorLength
0x140049068  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x14004906d  xor     r8d, r8d; ResultantDescriptor
0x140049070  mov     edx, edi; SecurityInformation
0x140049072  call    cs:__imp_GetPrivateObjectSecurity
0x140049079  nop     dword ptr [rax+rax+00h]
0x14004907e  mov     ecx, [rsp+78h+DescriptorLength]; dwBytes
0x140049085  call    pMemAlloc
0x14004908a  mov     [rsi], rax
0x14004908d  test    rax, rax
0x140049090  jnz     short loc_1400490B2
0x140049092  lea     ebx, [rax+8]
0x140049095  mov     rcx, cs:WPP_GLOBAL_Control
0x14004909c  cmp     rcx, r12
0x14004909f  jz      short loc_14004911D
0x1400490a1  test    byte ptr [rcx+1Ch], 4
0x1400490a5  jz      short loc_14004911D
0x1400490a7  cmp     byte ptr [rcx+19h], 2
0x1400490ab  jb      short loc_14004911D
0x1400490ad  lea     edx, [rax+4Eh]
0x1400490b0  jmp     short loc_140049045
0x1400490b2  mov     r9d, [rsp+78h+DescriptorLength]; DescriptorLength
0x1400490ba  lea     rcx, [rsp+78h+DescriptorLength]
0x1400490c2  mov     [rsp+78h+ReturnLength], rcx; ReturnLength
0x1400490c7  mov     r8, rax; ResultantDescriptor
0x1400490ca  mov     rcx, cs:?g_pFaxSD@@3PEAXEA; ObjectDescriptor
0x1400490d1  mov     edx, edi; SecurityInformation
0x1400490d3  call    cs:__imp_GetPrivateObjectSecurity
0x1400490da  nop     dword ptr [rax+rax+00h]
0x1400490df  test    eax, eax
0x1400490e1  jnz     short loc_140049113
0x1400490e3  call    cs:__imp_GetLastError
0x1400490ea  nop     dword ptr [rax+rax+00h]
0x1400490ef  mov     ebx, eax
0x1400490f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400490f8  cmp     rcx, r12
0x1400490fb  jz      short loc_14004911D
0x1400490fd  test    byte ptr [rcx+1Ch], 4
0x140049101  jz      short loc_14004911D
0x140049103  cmp     byte ptr [rcx+19h], 2
0x140049107  jb      short loc_14004911D
0x140049109  mov     edx, 4Fh ; 'O'
0x14004910e  jmp     loc_140048FB4
0x140049113  mov     eax, [rsp+78h+DescriptorLength]
0x14004911a  mov     [r14], eax
0x14004911d  lea     rcx, ?g_CsSecurity@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140049124  call    cs:__imp_LeaveCriticalSection
0x14004912b  nop     dword ptr [rax+rax+00h]
0x140049130  test    ebx, ebx
0x140049132  jz      short loc_140049159
0x140049134  mov     rcx, [rsi]; lpMem
0x140049137  call    pMemFree
0x14004913c  mov     qword ptr [rsi], 0
0x140049143  mov     dword ptr [r14], 0
0x14004914a  cmp     ebx, 8
0x14004914d  jz      short loc_140049154
0x14004914f  cmp     ebx, 0Eh
0x140049152  jnz     short loc_140049159
0x140049154  mov     ebx, 1B59h
0x140049159  mov     eax, ebx
0x14004915b  jmp     loc_140048F07
```
