# ConvertSIDToSD(void *,_SECURITY_DESCRIPTOR * *,ulong *)

- ea: `0x180018520`
- end: `0x1800187e6`
- name: `?ConvertSIDToSD@@YAJPEAXPEAPEAU_SECURITY_DESCRIPTOR@@PEAK@Z`
- size: `710`
- prototype: `__int64 __fastcall(PSID pSid, struct _SECURITY_DESCRIPTOR **, unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180019a6c`
- `0x18001a034`

## callees

- `0x180010920`
- `0x180010950`
- `0x180018520`
- `0x18001a450`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800185a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800185f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001861c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018676`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800186c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800186e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001870c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800185a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800185f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001861c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018676`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800186c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800186e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001870c`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x1800186df`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x1800186df`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800185e8`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180018612`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800185e8`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180018612`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180018598`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180018598`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18001866c`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18001866c`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180018702`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180018702`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x1800186ba`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x1800186ba`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001853e`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001854d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001853e`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001854d`
- `ntdll!RtlMakeSelfRelativeSD` at `0x180018727`
- `ntdll!RtlMakeSelfRelativeSD` at `0x180018798`
- `ntdll!RtlMakeSelfRelativeSD` at `0x180018727`
- `ntdll!RtlMakeSelfRelativeSD` at `0x180018798`

## string_xrefs

- `0x180018570`: `onecore\ds\security\keyman\sidkeyprov\rpcclient\sidkeyrpcclient.cxx`
- `0x1800185ac`: `onecore\ds\security\keyman\sidkeyprov\rpcclient\sidkeyrpcclient.cxx`
- `0x180018645`: `onecore\ds\security\keyman\sidkeyprov\rpcclient\sidkeyrpcclient.cxx`
- `0x180018680`: `onecore\ds\security\keyman\sidkeyprov\rpcclient\sidkeyrpcclient.cxx`
- `0x18001873c`: `onecore\ds\security\keyman\sidkeyprov\rpcclient\sidkeyrpcclient.cxx`
- `0x18001876e`: `onecore\ds\security\keyman\sidkeyprov\rpcclient\sidkeyrpcclient.cxx`

## pseudocode

```c
__int64 __fastcall ConvertSIDToSD(PSID pSid, struct _SECURITY_DESCRIPTOR **a2, unsigned int *a3)
{
  DWORD LengthSid; // ebx
  DWORD v7; // ebx
  struct _ACL *v8; // rax
  struct _ACL *v9; // rbp
  int v10; // ebx
  struct _SECURITY_DESCRIPTOR *v11; // rsi
  DWORD LastError; // eax
  unsigned int v13; // r9d
  void *v14; // rax
  void *v15; // rdi
  DWORD v16; // eax
  unsigned int v17; // r9d
  NTSTATUS SelfRelativeSD; // ebx
  unsigned int v19; // r9d
  struct _SECURITY_DESCRIPTOR *v20; // rax
  ULONG v21; // eax
  ULONG BufferLength; // [rsp+78h] [rbp+20h] BYREF

  BufferLength = 0;
  LengthSid = GetLengthSid(pSid);
  v7 = GetLengthSid(qword_18001E6E0) + 24 + LengthSid;
  v8 = (struct _ACL *)SIDKeyProvAlloc(v7);
  v9 = v8;
  if ( !v8 )
  {
    v10 = -2147024882;
    SidKeyDebugTraceError(
      0x8007000E,
      "hr",
      "onecore\\ds\\security\\keyman\\sidkeyprov\\rpcclient\\sidkeyrpcclient.cxx",
      0x34u);
    return (unsigned int)v10;
  }
  v11 = 0;
  if ( !InitializeAcl(v8, v7, 2u) )
  {
    LastError = GetLastError();
    v13 = 63;
    goto LABEL_5;
  }
  if ( !AddAccessAllowedAce(v9, 2u, 3u, pSid) )
  {
    LastError = GetLastError();
    v13 = 77;
    goto LABEL_5;
  }
  if ( !AddAccessAllowedAce(v9, 2u, 2u, qword_18001E6E0) )
  {
    LastError = GetLastError();
    v13 = 90;
LABEL_5:
    v10 = LastError;
    SidKeyDebugTraceError(
      LastError,
      "dwReturn",
      "onecore\\ds\\security\\keyman\\sidkeyprov\\rpcclient\\sidkeyrpcclient.cxx",
      v13);
    if ( v10 > 0 )
      v10 = (unsigned __int16)v10 | 0x80070000;
    goto LABEL_32;
  }
  v14 = SIDKeyProvAlloc(0x28u);
  v15 = v14;
  if ( !v14 )
  {
    v10 = -2147024882;
    SidKeyDebugTraceError(
      0x8007000E,
      "hr",
      "onecore\\ds\\security\\keyman\\sidkeyprov\\rpcclient\\sidkeyrpcclient.cxx",
      0x63u);
    goto LABEL_32;
  }
  if ( !InitializeSecurityDescriptor(v14, 1u) )
  {
    v16 = GetLastError();
    v17 = 108;
    goto LABEL_15;
  }
  if ( !SetSecurityDescriptorOwner(v15, &qword_18001E6F0, 0) )
  {
    v16 = GetLastError();
    v17 = 121;
    goto LABEL_15;
  }
  if ( !SetSecurityDescriptorGroup(v15, &qword_18001E6F0, 0) )
  {
    v16 = GetLastError();
    v17 = 134;
    goto LABEL_15;
  }
  if ( !SetSecurityDescriptorDacl(v15, 1, v9, 0) )
  {
    v16 = GetLastError();
    v17 = 147;
LABEL_15:
    v10 = v16;
    SidKeyDebugTraceError(
      v16,
      "dwReturn",
      "onecore\\ds\\security\\keyman\\sidkeyprov\\rpcclient\\sidkeyrpcclient.cxx",
      v17);
    if ( v10 > 0 )
      v10 = (unsigned __int16)v10 | 0x80070000;
    goto LABEL_31;
  }
  SelfRelativeSD = RtlMakeSelfRelativeSD(v15, 0, &BufferLength);
  if ( SelfRelativeSD == -1073741789 )
  {
    v20 = (struct _SECURITY_DESCRIPTOR *)SIDKeyProvAlloc(BufferLength);
    v11 = v20;
    if ( !v20 )
    {
      v10 = -2147024882;
      SidKeyDebugTraceError(
        0x8007000E,
        "hr",
        "onecore\\ds\\security\\keyman\\sidkeyprov\\rpcclient\\sidkeyrpcclient.cxx",
        0xA8u);
      goto LABEL_31;
    }
    SelfRelativeSD = RtlMakeSelfRelativeSD(v15, v20, &BufferLength);
    if ( SelfRelativeSD >= 0 )
    {
      v21 = BufferLength;
      v10 = 0;
      *a2 = v11;
      v11 = 0;
      *a3 = v21;
      goto LABEL_31;
    }
    v19 = 178;
  }
  else
  {
    v19 = 159;
  }
  SidKeyDebugTraceError(
    SelfRelativeSD,
    "status",
    "onecore\\ds\\security\\keyman\\sidkeyprov\\rpcclient\\sidkeyrpcclient.cxx",
    v19);
  v10 = SelfRelativeSD | 0x10000000;
LABEL_31:
  SIDKeyProvFree(v15);
LABEL_32:
  SIDKeyProvFree(v9);
  if ( v11 )
    SIDKeyProvFree(v11);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180018520  push    rbx
0x180018522  push    rbp
0x180018523  push    rsi
0x180018524  push    rdi
0x180018525  push    r14
0x180018527  push    r15
0x180018529  sub     rsp, 28h
0x18001852d  mov     r14, r8
0x180018530  mov     [rsp+58h+BufferLength], 0
0x180018538  mov     r15, rdx
0x18001853b  mov     rdi, rcx
0x18001853e  call    cs:__imp_GetLengthSid
0x180018544  lea     rcx, qword_18001E6E0; pSid
0x18001854b  mov     ebx, eax
0x18001854d  call    cs:__imp_GetLengthSid
0x180018553  add     eax, 18h
0x180018556  add     ebx, eax
0x180018558  mov     ecx, ebx; unsigned __int64
0x18001855a  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x18001855f  mov     rbp, rax
0x180018562  test    rax, rax
0x180018565  jnz     short loc_18001858D
0x180018567  lea     r9d, [rax+34h]; unsigned int
0x18001856b  mov     ecx, 8007000Eh; unsigned int
0x180018570  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180018577  mov     ebx, 8007000Eh
0x18001857c  lea     rdx, aHr; "hr"
0x180018583  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180018588  jmp     loc_1800187D7
0x18001858d  xor     esi, esi
0x18001858f  mov     edx, ebx; nAclLength
0x180018591  mov     rcx, rbp; pAcl
0x180018594  lea     r8d, [rsi+2]; dwAclRevision
0x180018598  call    cs:__imp_InitializeAcl
0x18001859e  test    eax, eax
0x1800185a0  jnz     short loc_1800185D9
0x1800185a2  call    cs:__imp_GetLastError
0x1800185a8  lea     r9d, [rsi+3Fh]; unsigned int
0x1800185ac  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x1800185b3  mov     ecx, eax; unsigned int
0x1800185b5  lea     rdx, aDwreturn; "dwReturn"
0x1800185bc  mov     ebx, eax
0x1800185be  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x1800185c3  test    ebx, ebx
0x1800185c5  jle     loc_1800187C2
0x1800185cb  movzx   ebx, bx
0x1800185ce  or      ebx, 80070000h
0x1800185d4  jmp     loc_1800187C2
0x1800185d9  mov     edx, 2; dwAceRevision
0x1800185de  mov     r9, rdi; pSid
0x1800185e1  mov     rcx, rbp; pAcl
0x1800185e4  lea     r8d, [rdx+1]; AccessMask
0x1800185e8  call    cs:__imp_AddAccessAllowedAce
0x1800185ee  test    eax, eax
0x1800185f0  jnz     short loc_180018600
0x1800185f2  call    cs:__imp_GetLastError
0x1800185f8  mov     r9d, 4Dh ; 'M'
0x1800185fe  jmp     short loc_1800185AC
0x180018600  mov     edx, 2; dwAceRevision
0x180018605  lea     r9, qword_18001E6E0; pSid
0x18001860c  mov     r8d, edx; AccessMask
0x18001860f  mov     rcx, rbp; pAcl
0x180018612  call    cs:__imp_AddAccessAllowedAce
0x180018618  test    eax, eax
0x18001861a  jnz     short loc_18001862A
0x18001861c  call    cs:__imp_GetLastError
0x180018622  mov     r9d, 5Ah ; 'Z'
0x180018628  jmp     short loc_1800185AC
0x18001862a  mov     ecx, 28h ; '('; unsigned __int64
0x18001862f  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x180018634  mov     rdi, rax
0x180018637  test    rax, rax
0x18001863a  jnz     short loc_180018662
0x18001863c  lea     r9d, [rax+63h]; unsigned int
0x180018640  mov     ecx, 8007000Eh; unsigned int
0x180018645  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18001864c  mov     ebx, 8007000Eh
0x180018651  lea     rdx, aHr; "hr"
0x180018658  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18001865d  jmp     loc_1800187C2
0x180018662  mov     ebx, 1
0x180018667  mov     rcx, rdi; pSecurityDescriptor
0x18001866a  mov     edx, ebx; dwRevision
0x18001866c  call    cs:__imp_InitializeSecurityDescriptor
0x180018672  test    eax, eax
0x180018674  jnz     short loc_1800186AD
0x180018676  call    cs:__imp_GetLastError
0x18001867c  lea     r9d, [rbx+6Bh]; unsigned int
0x180018680  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180018687  mov     ecx, eax; unsigned int
0x180018689  lea     rdx, aDwreturn; "dwReturn"
0x180018690  mov     ebx, eax
0x180018692  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180018697  test    ebx, ebx
0x180018699  jle     loc_1800187BA
0x18001869f  movzx   ebx, bx
0x1800186a2  or      ebx, 80070000h
0x1800186a8  jmp     loc_1800187BA
0x1800186ad  xor     r8d, r8d; bOwnerDefaulted
0x1800186b0  lea     rdx, qword_18001E6F0; pOwner
0x1800186b7  mov     rcx, rdi; pSecurityDescriptor
0x1800186ba  call    cs:__imp_SetSecurityDescriptorOwner
0x1800186c0  test    eax, eax
0x1800186c2  jnz     short loc_1800186D2
0x1800186c4  call    cs:__imp_GetLastError
0x1800186ca  mov     r9d, 79h ; 'y'
0x1800186d0  jmp     short loc_180018680
0x1800186d2  xor     r8d, r8d; bGroupDefaulted
0x1800186d5  lea     rdx, qword_18001E6F0; pGroup
0x1800186dc  mov     rcx, rdi; pSecurityDescriptor
0x1800186df  call    cs:__imp_SetSecurityDescriptorGroup
0x1800186e5  test    eax, eax
0x1800186e7  jnz     short loc_1800186F7
0x1800186e9  call    cs:__imp_GetLastError
0x1800186ef  mov     r9d, 86h
0x1800186f5  jmp     short loc_180018680
0x1800186f7  xor     r9d, r9d; bDaclDefaulted
0x1800186fa  mov     r8, rbp; pDacl
0x1800186fd  mov     edx, ebx; bDaclPresent
0x1800186ff  mov     rcx, rdi; pSecurityDescriptor
0x180018702  call    cs:__imp_SetSecurityDescriptorDacl
0x180018708  test    eax, eax
0x18001870a  jnz     short loc_18001871D
0x18001870c  call    cs:__imp_GetLastError
0x180018712  mov     r9d, 93h
0x180018718  jmp     loc_180018680
0x18001871d  lea     r8, [rsp+58h+BufferLength]; BufferLength
0x180018722  xor     edx, edx; SelfRelativeSD
0x180018724  mov     rcx, rdi; AbsoluteSD
0x180018727  call    cs:__imp_RtlMakeSelfRelativeSD
0x18001872d  mov     ebx, eax
0x18001872f  cmp     eax, 0C0000023h
0x180018734  jz      short loc_180018757
0x180018736  mov     r9d, 9Fh; unsigned int
0x18001873c  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180018743  mov     ecx, ebx; unsigned int
0x180018745  lea     rdx, aStatus; "status"
0x18001874c  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180018751  bts     ebx, 1Ch
0x180018755  jmp     short loc_1800187BA
0x180018757  mov     ecx, [rsp+58h+BufferLength]; unsigned __int64
0x18001875b  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x180018760  mov     rsi, rax
0x180018763  test    rax, rax
0x180018766  jnz     short loc_18001878D
0x180018768  mov     r9d, 0A8h; unsigned int
0x18001876e  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180018775  lea     rdx, aHr; "hr"
0x18001877c  mov     ecx, 8007000Eh; unsigned int
0x180018781  mov     ebx, 8007000Eh
0x180018786  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18001878b  jmp     short loc_1800187BA
0x18001878d  lea     r8, [rsp+58h+BufferLength]; BufferLength
0x180018792  mov     rdx, rsi; SelfRelativeSD
0x180018795  mov     rcx, rdi; AbsoluteSD
0x180018798  call    cs:__imp_RtlMakeSelfRelativeSD
0x18001879e  mov     ebx, eax
0x1800187a0  test    eax, eax
0x1800187a2  jns     short loc_1800187AC
0x1800187a4  mov     r9d, 0B2h
0x1800187aa  jmp     short loc_18001873C
0x1800187ac  mov     eax, [rsp+58h+BufferLength]
0x1800187b0  xor     ebx, ebx
0x1800187b2  mov     [r15], rsi
0x1800187b5  xor     esi, esi
0x1800187b7  mov     [r14], eax
0x1800187ba  mov     rcx, rdi; lpMem
0x1800187bd  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x1800187c2  mov     rcx, rbp; lpMem
0x1800187c5  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x1800187ca  test    rsi, rsi
0x1800187cd  jz      short loc_1800187D7
0x1800187cf  mov     rcx, rsi; lpMem
0x1800187d2  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x1800187d7  mov     eax, ebx
0x1800187d9  add     rsp, 28h
0x1800187dd  pop     r15
0x1800187df  pop     r14
0x1800187e1  pop     rdi
0x1800187e2  pop     rsi
0x1800187e3  pop     rbp
0x1800187e4  pop     rbx
0x1800187e5  retn
```
