# ConvertUserSidToName

- ea: `0x14006f350`
- end: `0x14006f62b`
- name: `ConvertUserSidToName`
- size: `731`
- prototype: `__int64 __fastcall(PSID Sid)`
- caller_count: `5`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x14000ce5c`
- `0x14000d244`
- `0x14000ff1c`
- `0x140045560`
- `0x140074e28`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x14000c450`
- `0x140065d14`
- `0x140065dbc`
- `0x14006f350`

## import_xrefs

- `ADVAPI32!LookupAccountSidW` at `0x14006f3e0`
- `ADVAPI32!LookupAccountSidW` at `0x14006f4f9`
- `ADVAPI32!LookupAccountSidW` at `0x14006f3e0`
- `ADVAPI32!LookupAccountSidW` at `0x14006f4f9`
- `KERNEL32!GetLastError` at `0x14006f3ea`
- `KERNEL32!GetLastError` at `0x14006f503`
- `KERNEL32!GetLastError` at `0x14006f3ea`
- `KERNEL32!GetLastError` at `0x14006f503`

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
0x14006f350  mov     [rsp-38h+arg_0], rbx
0x14006f355  mov     qword ptr [rsp-38h+cchName], r8
0x14006f35a  push    rbp
0x14006f35b  push    rsi
0x14006f35c  push    rdi
0x14006f35d  push    r12
0x14006f35f  push    r13
0x14006f361  push    r14
0x14006f363  push    r15
0x14006f365  mov     rbp, rsp
0x14006f368  sub     rsp, 50h
0x14006f36c  xor     r15d, r15d
0x14006f36f  mov     r13, rdx
0x14006f372  mov     ebx, r15d
0x14006f375  mov     [rbp+arg_18], r15d
0x14006f379  mov     r14d, r15d
0x14006f37c  mov     [rbp+cchName], r15d
0x14006f380  mov     [rbp+var_10], r15d
0x14006f384  mov     r12, rcx
0x14006f387  mov     rcx, cs:WPP_GLOBAL_Control
0x14006f38e  lea     rsi, WPP_GLOBAL_Control
0x14006f395  mov     dil, 2
0x14006f398  cmp     rcx, rsi
0x14006f39b  jz      short loc_14006F3BD
0x14006f39d  test    [rcx+1Ch], dil
0x14006f3a1  jz      short loc_14006F3BD
0x14006f3a3  cmp     byte ptr [rcx+19h], 5
0x14006f3a7  jb      short loc_14006F3BD
0x14006f3a9  mov     rcx, [rcx+10h]
0x14006f3ad  lea     edx, [r15+1Eh]
0x14006f3b1  lea     r8, WPP_987eb3bb399c3a7d72322ad52d5235ad_Traceguids
0x14006f3b8  call    WPP_SF_
0x14006f3bd  lea     rax, [rbp+var_10]
0x14006f3c1  xor     r8d, r8d; Name
0x14006f3c4  mov     [rsp+50h+peUse], rax; peUse
0x14006f3c9  lea     r9, [rbp+cchName]; cchName
0x14006f3cd  lea     rax, [rbp+arg_18]
0x14006f3d1  mov     rdx, r12; Sid
0x14006f3d4  mov     [rsp+50h+cchReferencedDomainName], rax; cchReferencedDomainName
0x14006f3d9  xor     ecx, ecx; lpSystemName
0x14006f3db  mov     [rsp+50h+ReferencedDomainName], r15; ReferencedDomainName
0x14006f3e0  call    cs:__imp_LookupAccountSidW
0x14006f3e6  test    eax, eax
0x14006f3e8  jnz     short loc_14006F3FA
0x14006f3ea  call    cs:__imp_GetLastError
0x14006f3f0  mov     ebx, eax
0x14006f3f2  cmp     eax, 7Ah ; 'z'
0x14006f3f5  jnz     short loc_14006F43D
0x14006f3f7  mov     ebx, r15d
0x14006f3fa  mov     ecx, [rbp+cchName]
0x14006f3fd  add     rcx, rcx; dwBytes
0x14006f400  call    pMemAlloc
0x14006f405  mov     r15, rax
0x14006f408  test    rax, rax
0x14006f40b  jnz     short loc_14006F482
0x14006f40d  lea     ebx, [rax+8]
0x14006f410  mov     rcx, cs:WPP_GLOBAL_Control
0x14006f417  cmp     rcx, rsi
0x14006f41a  jz      loc_14006F5FD
0x14006f420  test    [rcx+1Ch], dil
0x14006f424  jz      loc_14006F5FD
0x14006f42a  cmp     [rcx+19h], dil
0x14006f42e  jb      loc_14006F5FD
0x14006f434  mov     r9d, [rbp+cchName]
0x14006f438  lea     edx, [rax+20h]
0x14006f43b  jmp     short loc_14006F46D
0x14006f43d  test    eax, eax
0x14006f43f  jz      short loc_14006F3FA
0x14006f441  mov     rcx, cs:WPP_GLOBAL_Control
0x14006f448  cmp     rcx, rsi
0x14006f44b  jz      loc_14006F5FD
0x14006f451  test    [rcx+1Ch], dil
0x14006f455  jz      loc_14006F5FD
0x14006f45b  cmp     [rcx+19h], dil
0x14006f45f  jb      loc_14006F5FD
0x14006f465  mov     edx, 1Fh
0x14006f46a  mov     r9d, eax
0x14006f46d  mov     rcx, [rcx+10h]
0x14006f471  lea     r8, WPP_987eb3bb399c3a7d72322ad52d5235ad_Traceguids
0x14006f478  call    WPP_SF_d
0x14006f47d  jmp     loc_14006F5FD
0x14006f482  mov     ecx, [rbp+arg_18]
0x14006f485  add     ecx, [rbp+cchName]
0x14006f488  lea     edi, ds:4[rcx*2]
0x14006f48f  mov     ecx, edi; dwBytes
0x14006f491  mov     esi, edi
0x14006f493  call    pMemAlloc
0x14006f498  mov     r14, rax
0x14006f49b  test    rax, rax
0x14006f49e  jnz     short loc_14006F4D6
0x14006f4a0  lea     ebx, [rax+8]
0x14006f4a3  mov     rcx, cs:WPP_GLOBAL_Control
0x14006f4aa  lea     rdx, WPP_GLOBAL_Control
0x14006f4b1  cmp     rcx, rdx
0x14006f4b4  jz      loc_14006F5FD
0x14006f4ba  test    byte ptr [rcx+1Ch], 2
0x14006f4be  jz      loc_14006F5FD
0x14006f4c4  cmp     byte ptr [rcx+19h], 2
0x14006f4c8  jb      loc_14006F5FD
0x14006f4ce  lea     edx, [rax+21h]
0x14006f4d1  mov     r9d, edi
0x14006f4d4  jmp     short loc_14006F46D
0x14006f4d6  lea     rax, [rbp+var_10]
0x14006f4da  mov     r8, r15; Name
0x14006f4dd  mov     [rsp+50h+peUse], rax; peUse
0x14006f4e2  lea     r9, [rbp+cchName]; cchName
0x14006f4e6  lea     rax, [rbp+arg_18]
0x14006f4ea  mov     rdx, r12; Sid
0x14006f4ed  mov     [rsp+50h+cchReferencedDomainName], rax; cchReferencedDomainName
0x14006f4f2  xor     ecx, ecx; lpSystemName
0x14006f4f4  mov     [rsp+50h+ReferencedDomainName], r14; ReferencedDomainName
0x14006f4f9  call    cs:__imp_LookupAccountSidW
0x14006f4ff  test    eax, eax
0x14006f501  jnz     short loc_14006F540
0x14006f503  call    cs:__imp_GetLastError
0x14006f509  mov     ebx, eax
0x14006f50b  mov     rcx, cs:WPP_GLOBAL_Control
0x14006f512  lea     rdx, WPP_GLOBAL_Control
0x14006f519  cmp     rcx, rdx
0x14006f51c  jz      loc_14006F5FD
0x14006f522  test    byte ptr [rcx+1Ch], 2
0x14006f526  jz      loc_14006F5FD
0x14006f52c  cmp     byte ptr [rcx+19h], 2
0x14006f530  jb      loc_14006F5FD
0x14006f536  mov     edx, 22h ; '"'
0x14006f53b  jmp     loc_14006F46A
0x14006f540  shr     rsi, 1
0x14006f543  lea     r8, SubBlock; "\\"
0x14006f54a  mov     rdx, rsi; unsigned __int64
0x14006f54d  mov     rcx, r14; unsigned __int16 *
0x14006f550  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14006f555  mov     edi, eax
0x14006f557  test    eax, eax
0x14006f559  jns     short loc_14006F5A9
0x14006f55b  mov     rcx, cs:WPP_GLOBAL_Control
0x14006f562  lea     rdx, WPP_GLOBAL_Control
0x14006f569  cmp     rcx, rdx
0x14006f56c  jz      short loc_14006F592
0x14006f56e  test    byte ptr [rcx+1Ch], 2
0x14006f572  jz      short loc_14006F592
0x14006f574  cmp     byte ptr [rcx+19h], 2
0x14006f578  jb      short loc_14006F592
0x14006f57a  mov     rcx, [rcx+10h]
0x14006f57e  lea     r8, WPP_987eb3bb399c3a7d72322ad52d5235ad_Traceguids
0x14006f585  mov     edx, 23h ; '#'
0x14006f58a  mov     r9d, eax
0x14006f58d  call    WPP_SF_d
0x14006f592  mov     eax, edi
0x14006f594  and     eax, 1FFF0000h
0x14006f599  cmp     eax, 70000h
0x14006f59e  jnz     short loc_14006F5A5
0x14006f5a0  movzx   ebx, di
0x14006f5a3  jmp     short loc_14006F5FD
0x14006f5a5  mov     ebx, edi
0x14006f5a7  jmp     short loc_14006F5FD
0x14006f5a9  mov     r8, r15; unsigned __int16 *
0x14006f5ac  mov     rdx, rsi; unsigned __int64
0x14006f5af  mov     rcx, r14; unsigned __int16 *
0x14006f5b2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14006f5b7  test    eax, eax
0x14006f5b9  jns     short loc_14006F5F9
0x14006f5bb  mov     rcx, cs:WPP_GLOBAL_Control
0x14006f5c2  lea     rdx, WPP_GLOBAL_Control
0x14006f5c9  cmp     rcx, rdx
0x14006f5cc  jz      short loc_14006F5F2
0x14006f5ce  test    byte ptr [rcx+1Ch], 2
0x14006f5d2  jz      short loc_14006F5F2
0x14006f5d4  cmp     byte ptr [rcx+19h], 2
0x14006f5d8  jb      short loc_14006F5F2
0x14006f5da  mov     rcx, [rcx+10h]
0x14006f5de  lea     r8, WPP_987eb3bb399c3a7d72322ad52d5235ad_Traceguids
0x14006f5e5  mov     edx, 24h ; '$'
0x14006f5ea  mov     r9d, eax
0x14006f5ed  call    WPP_SF_d
0x14006f5f2  mov     ebx, 29Ch
0x14006f5f7  jmp     short loc_14006F5FD
0x14006f5f9  mov     [r13+0], r14
0x14006f5fd  mov     rcx, r15; lpMem
0x14006f600  call    pMemFree
0x14006f605  test    ebx, ebx
0x14006f607  jz      short loc_14006F611
0x14006f609  mov     rcx, r14; lpMem
0x14006f60c  call    pMemFree
0x14006f611  mov     eax, ebx
0x14006f613  mov     rbx, [rsp+50h+arg_0]
0x14006f61b  add     rsp, 50h
0x14006f61f  pop     r15
0x14006f621  pop     r14
0x14006f623  pop     r13
0x14006f625  pop     r12
0x14006f627  pop     rdi
0x14006f628  pop     rsi
0x14006f629  pop     rbp
0x14006f62a  retn
```
