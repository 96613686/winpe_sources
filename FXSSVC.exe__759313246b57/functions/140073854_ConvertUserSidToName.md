# ConvertUserSidToName

- ea: `0x140073854`
- end: `0x140073b48`
- name: `ConvertUserSidToName`
- size: `756`
- prototype: `__int64 __fastcall(PSID Sid)`
- caller_count: `5`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x14000d52c`
- `0x14000d91c`
- `0x1400105e0`
- `0x140048010`
- `0x1400799cc`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x14000cae8`
- `0x1400698ec`
- `0x14006998c`
- `0x140073854`

## import_xrefs

- `ADVAPI32!LookupAccountSidW` at `0x1400738e4`
- `ADVAPI32!LookupAccountSidW` at `0x140073a09`
- `ADVAPI32!LookupAccountSidW` at `0x1400738e4`
- `ADVAPI32!LookupAccountSidW` at `0x140073a09`
- `KERNEL32!GetLastError` at `0x1400738f4`
- `KERNEL32!GetLastError` at `0x140073a19`
- `KERNEL32!GetLastError` at `0x1400738f4`
- `KERNEL32!GetLastError` at `0x140073a19`

## pseudocode

```c
__int64 __fastcall ConvertUserSidToName(PSID Sid, unsigned __int16 **a2, __int64 a3)
{
  unsigned __int16 *v3; // r15
  unsigned int v5; // ebx
  unsigned __int16 *v6; // r14
  DWORD LastError; // eax
  CMapDeviceId *v9; // rcx
  __int64 v10; // r9
  __int64 v11; // rdx
  DWORD v12; // edi
  WCHAR *ReferencedDomainName; // rax
  unsigned __int64 v14; // rsi
  int v15; // eax
  unsigned int v16; // edi
  int v17; // eax
  enum _SID_NAME_USE peUse[4]; // [rsp+40h] [rbp-10h] BYREF
  DWORD cchName; // [rsp+A0h] [rbp+50h] BYREF
  int v21; // [rsp+A4h] [rbp+54h]
  DWORD cchReferencedDomainName; // [rsp+A8h] [rbp+58h] BYREF

  v21 = HIDWORD(a3);
  v3 = 0;
  v5 = 0;
  cchReferencedDomainName = 0;
  v6 = 0;
  cchName = 0;
  peUse[0] = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_987eb3bb399c3a7d72322ad52d5235ad_Traceguids);
  }
  if ( !LookupAccountSidW(0, Sid, 0, &cchName, 0, &cchReferencedDomainName, peUse) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError == 122 )
    {
      v5 = 0;
    }
    else if ( LastError )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_45;
      }
      v11 = 31;
      goto LABEL_18;
    }
  }
  v3 = (unsigned __int16 *)pMemAlloc(2LL * cchName);
  if ( v3 )
  {
    v12 = 2 * (cchName + cchReferencedDomainName) + 4;
    ReferencedDomainName = (WCHAR *)pMemAlloc(v12);
    v6 = ReferencedDomainName;
    if ( !ReferencedDomainName )
    {
      v5 = 8;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v11 = 33;
        v10 = v12;
        goto LABEL_19;
      }
      goto LABEL_45;
    }
    if ( LookupAccountSidW(0, Sid, v3, &cchName, ReferencedDomainName, &cchReferencedDomainName, peUse) )
    {
      v14 = (unsigned __int64)v12 >> 1;
      v15 = StringCchCatW(v6, v14, L"\\");
      v16 = v15;
      if ( v15 >= 0 )
      {
        v17 = StringCchCatW(v6, v14, v3);
        if ( v17 >= 0 )
        {
          *a2 = v6;
        }
        else
        {
          if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              36,
              WPP_987eb3bb399c3a7d72322ad52d5235ad_Traceguids,
              (unsigned int)v17);
          }
          v5 = 668;
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            35,
            WPP_987eb3bb399c3a7d72322ad52d5235ad_Traceguids,
            (unsigned int)v15);
        }
        if ( (v16 & 0x1FFF0000) == 0x70000 )
          v5 = (unsigned __int16)v16;
        else
          v5 = v16;
      }
      goto LABEL_45;
    }
    LastError = GetLastError();
    v5 = LastError;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_45;
    }
    v11 = 34;
LABEL_18:
    v10 = LastError;
    goto LABEL_19;
  }
  v5 = 8;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v10 = cchName;
    v11 = 32;
LABEL_19:
    WPP_SF_d(*((_QWORD *)v9 + 2), v11, WPP_987eb3bb399c3a7d72322ad52d5235ad_Traceguids, v10);
  }
LABEL_45:
  pMemFree(v3);
  if ( v5 )
    pMemFree(v6);
  return v5;
}

```

## disassembly

```asm
0x140073854  mov     [rsp-38h+arg_0], rbx
0x140073859  mov     qword ptr [rsp-38h+cchName], r8
0x14007385e  push    rbp
0x14007385f  push    rsi
0x140073860  push    rdi
0x140073861  push    r12
0x140073863  push    r13
0x140073865  push    r14
0x140073867  push    r15
0x140073869  mov     rbp, rsp
0x14007386c  sub     rsp, 50h
0x140073870  xor     r15d, r15d
0x140073873  mov     r13, rdx
0x140073876  mov     ebx, r15d
0x140073879  mov     [rbp+arg_18], r15d
0x14007387d  mov     r14d, r15d
0x140073880  mov     [rbp+cchName], r15d
0x140073884  mov     [rbp+var_10], r15d
0x140073888  mov     r12, rcx
0x14007388b  mov     rcx, cs:WPP_GLOBAL_Control
0x140073892  lea     rsi, WPP_GLOBAL_Control
0x140073899  mov     dil, 2
0x14007389c  cmp     rcx, rsi
0x14007389f  jz      short loc_1400738C1
0x1400738a1  test    [rcx+1Ch], dil
0x1400738a5  jz      short loc_1400738C1
0x1400738a7  cmp     byte ptr [rcx+19h], 5
0x1400738ab  jb      short loc_1400738C1
0x1400738ad  mov     rcx, [rcx+10h]
0x1400738b1  lea     edx, [r15+1Eh]
0x1400738b5  lea     r8, WPP_987eb3bb399c3a7d72322ad52d5235ad_Traceguids
0x1400738bc  call    WPP_SF_
0x1400738c1  lea     rax, [rbp+var_10]
0x1400738c5  xor     r8d, r8d; Name
0x1400738c8  mov     [rsp+50h+peUse], rax; peUse
0x1400738cd  lea     r9, [rbp+cchName]; cchName
0x1400738d1  lea     rax, [rbp+arg_18]
0x1400738d5  mov     rdx, r12; Sid
0x1400738d8  mov     [rsp+50h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1400738dd  xor     ecx, ecx; lpSystemName
0x1400738df  mov     [rsp+50h+ReferencedDomainName], r15; ReferencedDomainName
0x1400738e4  call    cs:__imp_LookupAccountSidW
0x1400738eb  nop     dword ptr [rax+rax+00h]
0x1400738f0  test    eax, eax
0x1400738f2  jnz     short loc_14007390A
0x1400738f4  call    cs:__imp_GetLastError
0x1400738fb  nop     dword ptr [rax+rax+00h]
0x140073900  mov     ebx, eax
0x140073902  cmp     eax, 7Ah ; 'z'
0x140073905  jnz     short loc_14007394D
0x140073907  mov     ebx, r15d
0x14007390a  mov     ecx, [rbp+cchName]
0x14007390d  add     rcx, rcx; dwBytes
0x140073910  call    pMemAlloc
0x140073915  mov     r15, rax
0x140073918  test    rax, rax
0x14007391b  jnz     short loc_140073992
0x14007391d  lea     ebx, [rax+8]
0x140073920  mov     rcx, cs:WPP_GLOBAL_Control
0x140073927  cmp     rcx, rsi
0x14007392a  jz      loc_140073B19
0x140073930  test    [rcx+1Ch], dil
0x140073934  jz      loc_140073B19
0x14007393a  cmp     [rcx+19h], dil
0x14007393e  jb      loc_140073B19
0x140073944  mov     r9d, [rbp+cchName]
0x140073948  lea     edx, [rax+20h]
0x14007394b  jmp     short loc_14007397D
0x14007394d  test    eax, eax
0x14007394f  jz      short loc_14007390A
0x140073951  mov     rcx, cs:WPP_GLOBAL_Control
0x140073958  cmp     rcx, rsi
0x14007395b  jz      loc_140073B19
0x140073961  test    [rcx+1Ch], dil
0x140073965  jz      loc_140073B19
0x14007396b  cmp     [rcx+19h], dil
0x14007396f  jb      loc_140073B19
0x140073975  mov     edx, 1Fh
0x14007397a  mov     r9d, eax
0x14007397d  mov     rcx, [rcx+10h]
0x140073981  lea     r8, WPP_987eb3bb399c3a7d72322ad52d5235ad_Traceguids
0x140073988  call    WPP_SF_d
0x14007398d  jmp     loc_140073B19
0x140073992  mov     ecx, [rbp+arg_18]
0x140073995  add     ecx, [rbp+cchName]
0x140073998  lea     edi, ds:4[rcx*2]
0x14007399f  mov     ecx, edi; dwBytes
0x1400739a1  mov     esi, edi
0x1400739a3  call    pMemAlloc
0x1400739a8  mov     r14, rax
0x1400739ab  test    rax, rax
0x1400739ae  jnz     short loc_1400739E6
0x1400739b0  lea     ebx, [rax+8]
0x1400739b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400739ba  lea     rdx, WPP_GLOBAL_Control
0x1400739c1  cmp     rcx, rdx
0x1400739c4  jz      loc_140073B19
0x1400739ca  test    byte ptr [rcx+1Ch], 2
0x1400739ce  jz      loc_140073B19
0x1400739d4  cmp     byte ptr [rcx+19h], 2
0x1400739d8  jb      loc_140073B19
0x1400739de  lea     edx, [rax+21h]
0x1400739e1  mov     r9d, edi
0x1400739e4  jmp     short loc_14007397D
0x1400739e6  lea     rax, [rbp+var_10]
0x1400739ea  mov     r8, r15; Name
0x1400739ed  mov     [rsp+50h+peUse], rax; peUse
0x1400739f2  lea     r9, [rbp+cchName]; cchName
0x1400739f6  lea     rax, [rbp+arg_18]
0x1400739fa  mov     rdx, r12; Sid
0x1400739fd  mov     [rsp+50h+cchReferencedDomainName], rax; cchReferencedDomainName
0x140073a02  xor     ecx, ecx; lpSystemName
0x140073a04  mov     [rsp+50h+ReferencedDomainName], r14; ReferencedDomainName
0x140073a09  call    cs:__imp_LookupAccountSidW
0x140073a10  nop     dword ptr [rax+rax+00h]
0x140073a15  test    eax, eax
0x140073a17  jnz     short loc_140073A5C
0x140073a19  call    cs:__imp_GetLastError
0x140073a20  nop     dword ptr [rax+rax+00h]
0x140073a25  mov     ebx, eax
0x140073a27  mov     rcx, cs:WPP_GLOBAL_Control
0x140073a2e  lea     rdx, WPP_GLOBAL_Control
0x140073a35  cmp     rcx, rdx
0x140073a38  jz      loc_140073B19
0x140073a3e  test    byte ptr [rcx+1Ch], 2
0x140073a42  jz      loc_140073B19
0x140073a48  cmp     byte ptr [rcx+19h], 2
0x140073a4c  jb      loc_140073B19
0x140073a52  mov     edx, 22h ; '"'
0x140073a57  jmp     loc_14007397A
0x140073a5c  shr     rsi, 1
0x140073a5f  lea     r8, SubBlock; "\\"
0x140073a66  mov     rdx, rsi; unsigned __int64
0x140073a69  mov     rcx, r14; unsigned __int16 *
0x140073a6c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140073a71  mov     edi, eax
0x140073a73  test    eax, eax
0x140073a75  jns     short loc_140073AC5
0x140073a77  mov     rcx, cs:WPP_GLOBAL_Control
0x140073a7e  lea     rdx, WPP_GLOBAL_Control
0x140073a85  cmp     rcx, rdx
0x140073a88  jz      short loc_140073AAE
0x140073a8a  test    byte ptr [rcx+1Ch], 2
0x140073a8e  jz      short loc_140073AAE
0x140073a90  cmp     byte ptr [rcx+19h], 2
0x140073a94  jb      short loc_140073AAE
0x140073a96  mov     rcx, [rcx+10h]
0x140073a9a  lea     r8, WPP_987eb3bb399c3a7d72322ad52d5235ad_Traceguids
0x140073aa1  mov     edx, 23h ; '#'
0x140073aa6  mov     r9d, eax
0x140073aa9  call    WPP_SF_d
0x140073aae  mov     eax, edi
0x140073ab0  and     eax, 1FFF0000h
0x140073ab5  cmp     eax, 70000h
0x140073aba  jnz     short loc_140073AC1
0x140073abc  movzx   ebx, di
0x140073abf  jmp     short loc_140073B19
0x140073ac1  mov     ebx, edi
0x140073ac3  jmp     short loc_140073B19
0x140073ac5  mov     r8, r15; unsigned __int16 *
0x140073ac8  mov     rdx, rsi; unsigned __int64
0x140073acb  mov     rcx, r14; unsigned __int16 *
0x140073ace  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140073ad3  test    eax, eax
0x140073ad5  jns     short loc_140073B15
0x140073ad7  mov     rcx, cs:WPP_GLOBAL_Control
0x140073ade  lea     rdx, WPP_GLOBAL_Control
0x140073ae5  cmp     rcx, rdx
0x140073ae8  jz      short loc_140073B0E
0x140073aea  test    byte ptr [rcx+1Ch], 2
0x140073aee  jz      short loc_140073B0E
0x140073af0  cmp     byte ptr [rcx+19h], 2
0x140073af4  jb      short loc_140073B0E
0x140073af6  mov     rcx, [rcx+10h]
0x140073afa  lea     r8, WPP_987eb3bb399c3a7d72322ad52d5235ad_Traceguids
0x140073b01  mov     edx, 24h ; '$'
0x140073b06  mov     r9d, eax
0x140073b09  call    WPP_SF_d
0x140073b0e  mov     ebx, 29Ch
0x140073b13  jmp     short loc_140073B19
0x140073b15  mov     [r13+0], r14
0x140073b19  mov     rcx, r15; lpMem
0x140073b1c  call    pMemFree
0x140073b21  test    ebx, ebx
0x140073b23  jz      short loc_140073B2D
0x140073b25  mov     rcx, r14; lpMem
0x140073b28  call    pMemFree
0x140073b2d  mov     eax, ebx
0x140073b2f  mov     rbx, [rsp+50h+arg_0]
0x140073b37  add     rsp, 50h
0x140073b3b  pop     r15
0x140073b3d  pop     r14
0x140073b3f  pop     r13
0x140073b41  pop     r12
0x140073b43  pop     rdi
0x140073b44  pop     rsi
0x140073b45  pop     rbp
0x140073b46  retn
```
