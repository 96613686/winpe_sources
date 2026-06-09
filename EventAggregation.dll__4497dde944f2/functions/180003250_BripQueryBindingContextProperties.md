# BripQueryBindingContextProperties

- ea: `0x180003250`
- end: `0x1800035f5`
- name: `BripQueryBindingContextProperties`
- size: `933`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180003070`

## callees

- `0x180002e30`
- `0x180003250`
- `0x180003630`
- `0x180003660`
- `0x18000bde9`

## import_xrefs

- `ntdll!RtlGetLastWin32Error` at `0x1800034bb`
- `ntdll!RtlGetLastWin32Error` at `0x1800034bb`
- `ntdll!RtlLengthSid` at `0x180003427`
- `ntdll!RtlLengthSid` at `0x180003427`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180003330`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180003330`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000340f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000340f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003312`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800033fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800035c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003312`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800033fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800035c2`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x1800034ad`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x18000353a`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x1800034ad`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x18000353a`

## pseudocode

```c
__int64 __fastcall BripQueryBindingContextProperties(HANDLE KeyHandle, _QWORD *a2, __int64 a3, __int64 a4)
{
  WCHAR *v8; // rdi
  void *v9; // rsi
  int Value; // eax
  int v11; // ebx
  void *v12; // rax
  size_t v13; // r8
  HLOCAL v14; // rdx
  int v15; // eax
  void *v16; // rax
  size_t v17; // r8
  HLOCAL v18; // rdx
  int v19; // eax
  size_t v20; // rbx
  int v21; // eax
  ULONG SecurityDescriptorSize; // [rsp+30h] [rbp-28h] BYREF
  DWORD cbSid; // [rsp+34h] [rbp-24h] BYREF
  DWORD cchReferencedDomainName; // [rsp+38h] [rbp-20h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+3Ch] [rbp-1Ch] BYREF
  HLOCAL hMem[3]; // [rsp+40h] [rbp-18h] BYREF

  peUse = 0;
  hMem[0] = 0;
  SecurityDescriptorSize = 0;
  cchReferencedDomainName = 0;
  cbSid = 0;
  v8 = 0;
  v9 = 0;
  Value = BripQueryValue(KeyHandle, a4);
  v11 = Value;
  if ( Value < 0 )
  {
    if ( Value != -1073741772 )
      goto LABEL_46;
    v11 = BripQueryValue(KeyHandle, a4);
    if ( v11 < 0 )
      goto LABEL_46;
    SecurityDescriptorSize = 0;
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
            (LPCWSTR)(*(_QWORD *)a3 + 12LL),
            1u,
            hMem,
            &SecurityDescriptorSize) )
    {
      v11 = -1073741670;
      goto LABEL_46;
    }
    v12 = (void *)EaLibAllocate(SecurityDescriptorSize);
    a2[6] = v12;
    if ( !v12 )
    {
      v11 = -1073741670;
      goto LABEL_46;
    }
    v13 = SecurityDescriptorSize;
    v14 = hMem[0];
  }
  else
  {
    v12 = (void *)EaLibAllocate(*(unsigned int *)(*(_QWORD *)a3 + 8LL));
    a2[6] = v12;
    if ( !v12 )
    {
      v11 = -1073741670;
      goto LABEL_46;
    }
    v13 = *(unsigned int *)(*(_QWORD *)a3 + 8LL);
    v14 = (HLOCAL)(*(_QWORD *)a3 + 12LL);
  }
  memcpy_0(v12, v14, v13);
  v15 = BripQueryValue(KeyHandle, a4);
  v11 = v15;
  if ( v15 < 0 )
  {
    if ( v15 != -1073741772 )
      goto LABEL_46;
    v19 = BripQueryValue(KeyHandle, a4);
    v11 = v19;
    if ( v19 < 0 )
    {
      if ( v19 != -1073741772 )
        goto LABEL_46;
      v11 = BripQueryValue(KeyHandle, a4);
      if ( v11 < 0 )
        goto LABEL_46;
      v20 = 0;
      if ( !LookupAccountNameLocalW((LPCWSTR)(*(_QWORD *)a3 + 12LL), 0, &cbSid, 0, &cchReferencedDomainName, &peUse) )
      {
        if ( RtlGetLastWin32Error() != 122 )
        {
          v11 = -1073741811;
          goto LABEL_46;
        }
        if ( cbSid )
        {
          v9 = (void *)EaLibAllocate(cbSid);
          if ( !v9 )
          {
            v11 = -1073741801;
            goto LABEL_46;
          }
          v20 = cbSid;
        }
        if ( cchReferencedDomainName )
        {
          v8 = (WCHAR *)EaLibAllocate(2LL * (cchReferencedDomainName + 1));
          if ( !v8 )
          {
            v11 = -1073741801;
            goto LABEL_46;
          }
        }
        if ( !LookupAccountNameLocalW((LPCWSTR)(*(_QWORD *)a3 + 12LL), v9, &cbSid, v8, &cchReferencedDomainName, &peUse) )
        {
          v11 = -1073741811;
          goto LABEL_46;
        }
      }
      v16 = (void *)EaLibAllocate(v20);
      a2[5] = v16;
      if ( !v16 )
      {
        v11 = -1073741670;
        goto LABEL_46;
      }
      v17 = v20;
      v18 = v9;
    }
    else
    {
      SecurityDescriptorSize = 0;
      if ( hMem[0] )
      {
        LocalFree(hMem[0]);
        hMem[0] = 0;
      }
      if ( !ConvertStringSidToSidW((LPCWSTR)(*(_QWORD *)a3 + 12LL), hMem) )
      {
        v11 = -1073741670;
        goto LABEL_46;
      }
      SecurityDescriptorSize = RtlLengthSid(hMem[0]);
      v16 = (void *)EaLibAllocate(SecurityDescriptorSize);
      a2[5] = v16;
      if ( !v16 )
      {
        v11 = -1073741670;
        goto LABEL_46;
      }
      v17 = SecurityDescriptorSize;
      v18 = hMem[0];
    }
  }
  else
  {
    v16 = (void *)EaLibAllocate(*(unsigned int *)(*(_QWORD *)a3 + 8LL));
    a2[5] = v16;
    if ( !v16 )
    {
      v11 = -1073741670;
      goto LABEL_46;
    }
    v17 = *(unsigned int *)(*(_QWORD *)a3 + 8LL);
    v18 = (HLOCAL)(*(_QWORD *)a3 + 12LL);
  }
  memcpy_0(v16, v18, v17);
  v21 = BripQueryValue(KeyHandle, a4);
  v11 = v21;
  if ( v21 < 0 )
  {
    if ( v21 == -1073741772 )
    {
      v11 = 0;
      a2[7] = 0;
    }
  }
  else
  {
    memcpy_0(a2 + 7, (const void *)(*(_QWORD *)a3 + 12LL), *(unsigned int *)(*(_QWORD *)a3 + 8LL));
  }
LABEL_46:
  if ( hMem[0] )
    LocalFree(hMem[0]);
  if ( v9 )
    EaLibFree(v9);
  if ( v8 )
    EaLibFree(v8);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180003250  push    rbp
0x180003252  push    rbx
0x180003253  push    rsi
0x180003254  push    rdi
0x180003255  push    r12
0x180003257  push    r13
0x180003259  push    r14
0x18000325b  push    r15
0x18000325d  mov     rbp, rsp
0x180003260  sub     rsp, 58h
0x180003264  xor     eax, eax
0x180003266  mov     [rsp+58h+cchReferencedDomainName], r9; __int64
0x18000326b  mov     r12, r9
0x18000326e  mov     [rbp+var_1C], eax
0x180003271  mov     r9, r8
0x180003274  mov     [rbp+hMem], rax
0x180003278  mov     r14, r8
0x18000327b  mov     [rbp+SecurityDescriptorSize], eax
0x18000327e  mov     r15, rdx
0x180003281  mov     [rbp+var_20], eax
0x180003284  mov     r8d, 3
0x18000328a  mov     [rbp+cbSid], eax
0x18000328d  lea     rdx, aServerauth; "ServerAuth"
0x180003294  mov     r13, rcx
0x180003297  mov     edi, eax
0x180003299  mov     esi, eax
0x18000329b  call    BripQueryValue
0x1800032a0  mov     ebx, eax
0x1800032a2  test    eax, eax
0x1800032a4  js      short loc_1800032D4
0x1800032a6  mov     rax, [r14]
0x1800032a9  mov     ecx, [rax+8]
0x1800032ac  call    EaLibAllocate
0x1800032b1  mov     [r15+30h], rax
0x1800032b5  test    rax, rax
0x1800032b8  jnz     short loc_1800032C4
0x1800032ba  mov     ebx, 0C000009Ah
0x1800032bf  jmp     loc_1800035B9
0x1800032c4  mov     rdx, [r14]
0x1800032c7  mov     r8d, [rdx+8]
0x1800032cb  add     rdx, 0Ch
0x1800032cf  jmp     loc_180003367
0x1800032d4  cmp     eax, 0C0000034h
0x1800032d9  jnz     loc_1800035B9
0x1800032df  mov     r9, r14
0x1800032e2  mov     [rsp+58h+cchReferencedDomainName], r12; __int64
0x1800032e7  mov     r8d, 1
0x1800032ed  lea     rdx, aServerauthstri; "ServerAuthString"
0x1800032f4  mov     rcx, r13; KeyHandle
0x1800032f7  call    BripQueryValue
0x1800032fc  mov     ebx, eax
0x1800032fe  test    eax, eax
0x180003300  js      loc_1800035B9
0x180003306  mov     rcx, [rbp+hMem]; hMem
0x18000330a  mov     [rbp+SecurityDescriptorSize], esi
0x18000330d  test    rcx, rcx
0x180003310  jz      short loc_18000331C
0x180003312  call    cs:__imp_LocalFree
0x180003318  mov     [rbp+hMem], rsi
0x18000331c  mov     rcx, [r14]
0x18000331f  lea     r9, [rbp+SecurityDescriptorSize]; SecurityDescriptorSize
0x180003323  add     rcx, 0Ch; StringSecurityDescriptor
0x180003327  lea     r8, [rbp+hMem]; SecurityDescriptor
0x18000332b  mov     edx, 1; StringSDRevision
0x180003330  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180003336  test    eax, eax
0x180003338  jnz     short loc_180003344
0x18000333a  mov     ebx, 0C000009Ah
0x18000333f  jmp     loc_1800035B9
0x180003344  mov     ecx, [rbp+SecurityDescriptorSize]
0x180003347  call    EaLibAllocate
0x18000334c  mov     [r15+30h], rax
0x180003350  test    rax, rax
0x180003353  jnz     short loc_18000335F
0x180003355  mov     ebx, 0C000009Ah
0x18000335a  jmp     loc_1800035B9
0x18000335f  mov     r8d, [rbp+SecurityDescriptorSize]; Size
0x180003363  mov     rdx, [rbp+hMem]; Src
0x180003367  mov     rcx, rax; void *
0x18000336a  call    memcpy_0
0x18000336f  mov     r9, r14
0x180003372  mov     [rsp+58h+cchReferencedDomainName], r12; __int64
0x180003377  mov     r8d, 3
0x18000337d  lea     rdx, aServerprincipa_1; "ServerPrincipal"
0x180003384  mov     rcx, r13; KeyHandle
0x180003387  call    BripQueryValue
0x18000338c  mov     ebx, eax
0x18000338e  test    eax, eax
0x180003390  js      short loc_1800033C0
0x180003392  mov     rax, [r14]
0x180003395  mov     ecx, [rax+8]
0x180003398  call    EaLibAllocate
0x18000339d  mov     [r15+28h], rax
0x1800033a1  test    rax, rax
0x1800033a4  jnz     short loc_1800033B0
0x1800033a6  mov     ebx, 0C000009Ah
0x1800033ab  jmp     loc_1800035B9
0x1800033b0  mov     rdx, [r14]
0x1800033b3  mov     r8d, [rdx+8]
0x1800033b7  add     rdx, 0Ch
0x1800033bb  jmp     loc_180003569
0x1800033c0  cmp     eax, 0C0000034h
0x1800033c5  jnz     loc_1800035B9
0x1800033cb  mov     r9, r14
0x1800033ce  mov     [rsp+58h+cchReferencedDomainName], r12; __int64
0x1800033d3  mov     r8d, 1
0x1800033d9  lea     rdx, aServerprincipa; "ServerPrincipalString"
0x1800033e0  mov     rcx, r13; KeyHandle
0x1800033e3  call    BripQueryValue
0x1800033e8  mov     ebx, eax
0x1800033ea  test    eax, eax
0x1800033ec  js      short loc_180003457
0x1800033ee  mov     rcx, [rbp+hMem]; hMem
0x1800033f2  mov     [rbp+SecurityDescriptorSize], esi
0x1800033f5  test    rcx, rcx
0x1800033f8  jz      short loc_180003404
0x1800033fa  call    cs:__imp_LocalFree
0x180003400  mov     [rbp+hMem], rsi
0x180003404  mov     rcx, [r14]
0x180003407  lea     rdx, [rbp+hMem]; Sid
0x18000340b  add     rcx, 0Ch; StringSid
0x18000340f  call    cs:__imp_ConvertStringSidToSidW
0x180003415  test    eax, eax
0x180003417  jnz     short loc_180003423
0x180003419  mov     ebx, 0C000009Ah
0x18000341e  jmp     loc_1800035B9
0x180003423  mov     rcx, [rbp+hMem]; Sid
0x180003427  call    cs:__imp_RtlLengthSid
0x18000342d  mov     ecx, eax
0x18000342f  mov     [rbp+SecurityDescriptorSize], ecx
0x180003432  call    EaLibAllocate
0x180003437  mov     [r15+28h], rax
0x18000343b  test    rax, rax
0x18000343e  jnz     short loc_18000344A
0x180003440  mov     ebx, 0C000009Ah
0x180003445  jmp     loc_1800035B9
0x18000344a  mov     r8d, [rbp+SecurityDescriptorSize]
0x18000344e  mov     rdx, [rbp+hMem]
0x180003452  jmp     loc_180003569
0x180003457  cmp     eax, 0C0000034h
0x18000345c  jnz     loc_1800035B9
0x180003462  mov     r9, r14
0x180003465  mov     [rsp+58h+cchReferencedDomainName], r12; __int64
0x18000346a  mov     r8d, 1
0x180003470  lea     rdx, aServerprincipa_0; "ServerPrincipalName"
0x180003477  mov     rcx, r13; KeyHandle
0x18000347a  call    BripQueryValue
0x18000347f  mov     ebx, eax
0x180003481  test    eax, eax
0x180003483  js      loc_1800035B9
0x180003489  mov     rcx, [r14]
0x18000348c  lea     rax, [rbp+var_1C]
0x180003490  mov     [rsp+58h+peUse], rax; peUse
0x180003495  lea     r8, [rbp+cbSid]; cbSid
0x180003499  lea     rax, [rbp+var_20]
0x18000349d  add     rcx, 0Ch; lpAccountName
0x1800034a1  xor     r9d, r9d; ReferencedDomainName
0x1800034a4  mov     [rsp+58h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800034a9  xor     edx, edx; Sid
0x1800034ab  xor     ebx, ebx
0x1800034ad  call    cs:__imp_LookupAccountNameLocalW
0x1800034b3  test    eax, eax
0x1800034b5  jnz     loc_18000354B
0x1800034bb  call    cs:__imp_RtlGetLastWin32Error
0x1800034c1  cmp     eax, 7Ah ; 'z'
0x1800034c4  jz      short loc_1800034D0
0x1800034c6  mov     ebx, 0C000000Dh
0x1800034cb  jmp     loc_1800035B9
0x1800034d0  mov     eax, [rbp+cbSid]
0x1800034d3  test    eax, eax
0x1800034d5  jz      short loc_1800034F3
0x1800034d7  mov     ecx, eax
0x1800034d9  call    EaLibAllocate
0x1800034de  mov     rsi, rax
0x1800034e1  test    rax, rax
0x1800034e4  jnz     short loc_1800034F0
0x1800034e6  mov     ebx, 0C0000017h
0x1800034eb  jmp     loc_1800035B9
0x1800034f0  mov     ebx, [rbp+cbSid]
0x1800034f3  mov     eax, [rbp+var_20]
0x1800034f6  test    eax, eax
0x1800034f8  jz      short loc_180003517
0x1800034fa  lea     ecx, [rax+1]
0x1800034fd  add     rcx, rcx
0x180003500  call    EaLibAllocate
0x180003505  mov     rdi, rax
0x180003508  test    rax, rax
0x18000350b  jnz     short loc_180003517
0x18000350d  mov     ebx, 0C0000017h
0x180003512  jmp     loc_1800035B9
0x180003517  mov     rcx, [r14]
0x18000351a  lea     rax, [rbp+var_1C]
0x18000351e  mov     [rsp+58h+peUse], rax; peUse
0x180003523  lea     r8, [rbp+cbSid]; cbSid
0x180003527  lea     rax, [rbp+var_20]
0x18000352b  add     rcx, 0Ch; lpAccountName
0x18000352f  mov     r9, rdi; ReferencedDomainName
0x180003532  mov     [rsp+58h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180003537  mov     rdx, rsi; Sid
0x18000353a  call    cs:__imp_LookupAccountNameLocalW
0x180003540  test    eax, eax
0x180003542  jnz     short loc_18000354B
0x180003544  mov     ebx, 0C000000Dh
0x180003549  jmp     short loc_1800035B9
0x18000354b  mov     rcx, rbx
0x18000354e  call    EaLibAllocate
0x180003553  mov     [r15+28h], rax
0x180003557  test    rax, rax
0x18000355a  jnz     short loc_180003563
0x18000355c  mov     ebx, 0C000009Ah
0x180003561  jmp     short loc_1800035B9
0x180003563  mov     r8, rbx; Size
0x180003566  mov     rdx, rsi; Src
0x180003569  mov     rcx, rax; void *
0x18000356c  call    memcpy_0
0x180003571  mov     r9, r14
0x180003574  mov     [rsp+58h+cchReferencedDomainName], r12; __int64
0x180003579  mov     r8d, 0Bh
0x18000357f  lea     rdx, aAvailabilityst; "AvailabilityStateName"
0x180003586  mov     rcx, r13; KeyHandle
0x180003589  call    BripQueryValue
0x18000358e  mov     ebx, eax
0x180003590  test    eax, eax
0x180003592  js      short loc_1800035AA
0x180003594  mov     rdx, [r14]
0x180003597  lea     rcx, [r15+38h]; void *
0x18000359b  mov     r8d, [rdx+8]; Size
0x18000359f  add     rdx, 0Ch; Src
0x1800035a3  call    memcpy_0
0x1800035a8  jmp     short loc_1800035B9
0x1800035aa  cmp     eax, 0C0000034h
0x1800035af  jnz     short loc_1800035B9
0x1800035b1  xor     ebx, ebx
0x1800035b3  xor     eax, eax
0x1800035b5  mov     [r15+38h], rax
0x1800035b9  mov     rcx, [rbp+hMem]; hMem
0x1800035bd  test    rcx, rcx
0x1800035c0  jz      short loc_1800035C8
0x1800035c2  call    cs:__imp_LocalFree
0x1800035c8  test    rsi, rsi
0x1800035cb  jz      short loc_1800035D5
0x1800035cd  mov     rcx, rsi
0x1800035d0  call    EaLibFree
0x1800035d5  test    rdi, rdi
0x1800035d8  jz      short loc_1800035E2
0x1800035da  mov     rcx, rdi
0x1800035dd  call    EaLibFree
0x1800035e2  mov     eax, ebx
0x1800035e4  add     rsp, 58h
0x1800035e8  pop     r15
0x1800035ea  pop     r14
0x1800035ec  pop     r13
0x1800035ee  pop     r12
0x1800035f0  pop     rdi
0x1800035f1  pop     rsi
0x1800035f2  pop     rbx
0x1800035f3  pop     rbp
0x1800035f4  retn
```
