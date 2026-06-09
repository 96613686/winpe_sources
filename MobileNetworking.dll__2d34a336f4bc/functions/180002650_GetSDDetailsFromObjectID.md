# GetSDDetailsFromObjectID

- ea: `0x180002650`
- end: `0x180002a31`
- name: `GetSDDetailsFromObjectID`
- size: `993`
- prototype: `__int64 __fastcall(unsigned int, _DWORD *, _QWORD *, LPWSTR *, ULONG *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002650`
- `0x180002a40`
- `0x180002b20`
- `0x180004cb0`
- `0x180008ff0`
- `0x180009130`
- `0x18000b774`
- `0x1800118f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800028aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002999`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800028aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002999`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002719`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002719`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800026fc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800026fc`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180002796`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180002796`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800026e8`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800026e8`

## pseudocode

```c
__int64 __fastcall GetSDDetailsFromObjectID(unsigned int a1, _DWORD *a2, _QWORD *a3, LPWSTR *a4, ULONG *a5)
{
  LPWSTR *v5; // rsi
  __int64 v8; // rbx
  unsigned int v9; // edi
  __int64 v10; // r13
  __int64 v11; // rbx
  void *v12; // rcx
  DWORD SecurityDescriptorLength; // eax
  SIZE_T v14; // r14
  unsigned int v15; // ebx
  HANDLE ProcessHeap; // rdi
  LPVOID v17; // rax
  int v18; // r8d
  void *v19; // rsi
  _QWORD *v21; // rcx
  __int64 v22; // rdx
  DWORD LastError; // eax
  int v24; // r8d
  __int64 v25; // r9
  ULONG StringSecurityDescriptorLen; // [rsp+40h] [rbp-38h] BYREF
  _DWORD v27[3]; // [rsp+44h] [rbp-34h] BYREF

  v5 = a4;
  v8 = a1;
  StringSecurityDescriptorLen = 0;
  v27[0] = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 137, WPP_fd6184a389643c6486807174a58ed414_Traceguids);
  v9 = AcquireLockSecurityObject(v27);
  if ( v9 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_L(*((_QWORD *)WPP_GLOBAL_Control + 2), 138, WPP_fd6184a389643c6486807174a58ed414_Traceguids, v9);
    goto LABEL_22;
  }
  if ( (unsigned int)v8 >= 0x14
    || (v10 = v8, v11 = *(_QWORD *)&g_pSecurity, (v12 = *(void **)(*(_QWORD *)&g_pSecurity + 8 * v10 + 120)) == 0) )
  {
    v9 = 87;
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_22;
    v22 = 139;
LABEL_51:
    v25 = v9;
    goto LABEL_52;
  }
  if ( !a3 )
    goto LABEL_16;
  SecurityDescriptorLength = GetSecurityDescriptorLength(v12);
  v14 = SecurityDescriptorLength;
  if ( SecurityDescriptorLength < 0x28 )
  {
    v9 = 5023;
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_22;
    v22 = 140;
    goto LABEL_51;
  }
  v15 = 0;
  ProcessHeap = GetProcessHeap();
  if ( !ProcessHeap )
  {
    LastError = GetLastError();
    v15 = LastError;
    if ( LastError )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_sdd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          v24,
          (unsigned int)"GetSDDetailsFromObjectID",
          60,
          LastError);
      *a3 = 0;
      v9 = v15;
      goto LABEL_41;
    }
  }
  v17 = HeapAlloc(ProcessHeap, 8u, v14);
  v19 = v17;
  if ( v17 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_sdqd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        v18,
        (unsigned int)"GetSDDetailsFromObjectID",
        60,
        (char)v17,
        v14);
    *a3 = v19;
    v9 = v15;
    if ( !v15 )
    {
      v11 = *(_QWORD *)&g_pSecurity;
      memcpy_0(v19, *(const void **)(*(_QWORD *)&g_pSecurity + 8 * v10 + 120), v14);
      v5 = a4;
LABEL_16:
      if ( v5 )
      {
        if ( !ConvertSecurityDescriptorToStringSecurityDescriptorW(
                *(PSECURITY_DESCRIPTOR *)(v11 + 8 * v10 + 120),
                1u,
                7u,
                v5,
                &StringSecurityDescriptorLen) )
        {
          v9 = GetLastError();
          if ( v9 )
          {
            v21 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
              goto LABEL_22;
            v22 = 142;
            goto LABEL_51;
          }
        }
        v11 = *(_QWORD *)&g_pSecurity;
        if ( a5 )
          *a5 = StringSecurityDescriptorLen;
      }
      if ( a2 )
        *a2 = *(_DWORD *)(v11 + 4 * v10 + 280);
      goto LABEL_22;
    }
  }
  else
  {
    v9 = 14;
    v15 = 14;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_sdd(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, v18, (unsigned int)"GetSDDetailsFromObjectID", 60, v14);
    *a3 = 0;
  }
LABEL_41:
  v21 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v22 = 141;
    v25 = v15;
LABEL_52:
    WPP_SF_L(v21[2], v22, WPP_fd6184a389643c6486807174a58ed414_Traceguids, v25);
  }
LABEL_22:
  ReleaseLockSecurityObject(v27);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_L(*((_QWORD *)WPP_GLOBAL_Control + 2), 143, WPP_fd6184a389643c6486807174a58ed414_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x180002650  mov     rax, rsp
0x180002653  mov     [rax+20h], r9
0x180002657  push    rdi
0x180002658  sub     rsp, 70h
0x18000265c  mov     [rax+8], rbx
0x180002660  mov     [rax+10h], rbp
0x180002664  xor     ebp, ebp
0x180002666  mov     [rax+18h], rsi
0x18000266a  mov     rsi, r9
0x18000266d  mov     [rax-10h], r12
0x180002671  mov     r12, rdx
0x180002674  mov     [rax-28h], r15
0x180002678  mov     r15, r8
0x18000267b  mov     ebx, ecx
0x18000267d  mov     [rax-38h], ebp
0x180002680  mov     [rax-34h], ebp
0x180002683  mov     rcx, cs:WPP_GLOBAL_Control
0x18000268a  lea     rax, WPP_GLOBAL_Control
0x180002691  cmp     rcx, rax
0x180002694  jz      short loc_1800026A0
0x180002696  test    byte ptr [rcx+1Ch], 8
0x18000269a  jnz     loc_180002860
0x1800026a0  lea     rcx, [rsp+78h+var_34]
0x1800026a5  mov     [rsp+78h+var_20], r14
0x1800026aa  call    AcquireLockSecurityObject
0x1800026af  mov     edi, eax
0x1800026b1  test    eax, eax
0x1800026b3  jnz     loc_18000282A
0x1800026b9  mov     [rsp+78h+var_18], r13
0x1800026be  cmp     ebx, 14h
0x1800026c1  jnb     loc_1800029D1
0x1800026c7  mov     r13, rbx
0x1800026ca  mov     rbx, cs:g_pSecurity
0x1800026d1  mov     rcx, [rbx+r13*8+78h]; pSecurityDescriptor
0x1800026d6  test    rcx, rcx
0x1800026d9  jz      loc_1800029D1
0x1800026df  test    r15, r15
0x1800026e2  jz      loc_180002774
0x1800026e8  call    cs:__imp_GetSecurityDescriptorLength
0x1800026ee  mov     r14d, eax
0x1800026f1  cmp     eax, 28h ; '('
0x1800026f4  jb      loc_18000287A
0x1800026fa  mov     ebx, ebp
0x1800026fc  call    cs:__imp_GetProcessHeap
0x180002702  mov     rdi, rax
0x180002705  test    rax, rax
0x180002708  jz      loc_1800028AA
0x18000270e  mov     r8, r14; dwBytes
0x180002711  mov     edx, 8; dwFlags
0x180002716  mov     rcx, rdi; hHeap
0x180002719  call    cs:__imp_HeapAlloc
0x18000271f  mov     rsi, rax
0x180002722  test    rax, rax
0x180002725  jz      loc_1800028FB
0x18000272b  mov     rcx, cs:WPP_GLOBAL_Control
0x180002732  lea     rdi, WPP_GLOBAL_Control
0x180002739  cmp     rcx, rdi
0x18000273c  jz      short loc_180002748
0x18000273e  test    byte ptr [rcx+1Ch], 2
0x180002742  jnz     loc_180002942
0x180002748  mov     [r15], rsi
0x18000274b  mov     edi, ebx
0x18000274d  test    ebx, ebx
0x18000274f  jnz     loc_18000296E
0x180002755  mov     rbx, cs:g_pSecurity
0x18000275c  mov     r8, r14; Size
0x18000275f  mov     rcx, rsi; void *
0x180002762  mov     rdx, [rbx+r13*8+78h]; Src
0x180002767  call    memcpy_0
0x18000276c  mov     rsi, [rsp+78h+arg_18]
0x180002774  test    rsi, rsi
0x180002777  jz      short loc_1800027BE
0x180002779  mov     rcx, [rbx+r13*8+78h]; SecurityDescriptor
0x18000277e  lea     rax, [rsp+78h+var_38]
0x180002783  mov     r9, rsi; StringSecurityDescriptor
0x180002786  mov     [rsp+78h+StringSecurityDescriptorLen], rax; StringSecurityDescriptorLen
0x18000278b  mov     edx, 1; RequestedStringSDRevision
0x180002790  mov     r8d, 7; SecurityInformation
0x180002796  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x18000279c  test    eax, eax
0x18000279e  jz      loc_180002999
0x1800027a4  mov     rcx, [rsp+78h+arg_20]
0x1800027ac  mov     rbx, cs:g_pSecurity
0x1800027b3  test    rcx, rcx
0x1800027b6  jz      short loc_1800027BE
0x1800027b8  mov     eax, [rsp+78h+var_38]
0x1800027bc  mov     [rcx], eax
0x1800027be  test    r12, r12
0x1800027c1  jz      short loc_1800027CF
0x1800027c3  mov     eax, [rbx+r13*4+118h]
0x1800027cb  mov     [r12], eax
0x1800027cf  mov     r13, [rsp+78h+var_18]
0x1800027d4  lea     rcx, [rsp+78h+var_34]
0x1800027d9  call    ReleaseLockSecurityObject
0x1800027de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800027e5  lea     rax, WPP_GLOBAL_Control
0x1800027ec  mov     r15, [rsp+78h+var_28]
0x1800027f1  mov     r14, [rsp+78h+var_20]
0x1800027f6  mov     r12, [rsp+78h+var_10]
0x1800027fb  mov     rsi, [rsp+78h+arg_10]
0x180002803  mov     rbp, [rsp+78h+arg_8]
0x18000280b  mov     rbx, [rsp+78h+arg_0]
0x180002813  cmp     rcx, rax
0x180002816  jz      short loc_180002822
0x180002818  test    byte ptr [rcx+1Ch], 8
0x18000281c  jnz     loc_180002A14
0x180002822  mov     eax, edi
0x180002824  add     rsp, 70h
0x180002828  pop     rdi
0x180002829  retn
0x18000282a  mov     rcx, cs:WPP_GLOBAL_Control
0x180002831  lea     rax, WPP_GLOBAL_Control
0x180002838  cmp     rcx, rax
0x18000283b  jz      short loc_1800027D4
0x18000283d  test    byte ptr [rcx+1Ch], 4
0x180002841  jz      short loc_1800027D4
0x180002843  mov     rcx, [rcx+10h]
0x180002847  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x18000284e  mov     edx, 8Ah
0x180002853  mov     r9d, edi
0x180002856  call    WPP_SF_L
0x18000285b  jmp     loc_1800027D4
0x180002860  mov     rcx, [rcx+10h]
0x180002864  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x18000286b  mov     edx, 89h
0x180002870  call    WPP_SF_
0x180002875  jmp     loc_1800026A0
0x18000287a  mov     edi, 139Fh
0x18000287f  mov     rcx, cs:WPP_GLOBAL_Control
0x180002886  lea     rax, WPP_GLOBAL_Control
0x18000288d  cmp     rcx, rax
0x180002890  jz      loc_1800027CF
0x180002896  test    byte ptr [rcx+1Ch], 4
0x18000289a  jz      loc_1800027CF
0x1800028a0  mov     edx, 8Ch
0x1800028a5  jmp     loc_1800029FC
0x1800028aa  call    cs:__imp_GetLastError
0x1800028b0  mov     ebx, eax
0x1800028b2  test    eax, eax
0x1800028b4  jz      loc_18000270E
0x1800028ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800028c1  lea     r12, WPP_GLOBAL_Control
0x1800028c8  cmp     rcx, r12
0x1800028cb  jz      short loc_1800028F4
0x1800028cd  test    byte ptr [rcx+1Ch], 4
0x1800028d1  jz      short loc_1800028F4
0x1800028d3  mov     rcx, [rcx+10h]
0x1800028d7  lea     r9, aGetsddetailsfr_0; "GetSDDetailsFromObjectID"
0x1800028de  mov     dword ptr [rsp+78h+var_50], eax
0x1800028e2  mov     edx, 0Ah
0x1800028e7  mov     dword ptr [rsp+78h+StringSecurityDescriptorLen], 53Ch
0x1800028ef  call    WPP_SF_sdd
0x1800028f4  mov     [r15], rbp
0x1800028f7  mov     edi, ebx
0x1800028f9  jmp     short loc_180002975
0x1800028fb  mov     edi, 0Eh
0x180002900  mov     ebx, edi
0x180002902  mov     rcx, cs:WPP_GLOBAL_Control
0x180002909  lea     r12, WPP_GLOBAL_Control
0x180002910  cmp     rcx, r12
0x180002913  jz      short loc_18000293D
0x180002915  test    byte ptr [rcx+1Ch], 4
0x180002919  jz      short loc_18000293D
0x18000291b  mov     rcx, [rcx+10h]
0x18000291f  lea     r9, aGetsddetailsfr_0; "GetSDDetailsFromObjectID"
0x180002926  mov     edx, 0Bh
0x18000292b  mov     dword ptr [rsp+78h+var_50], r14d
0x180002930  mov     dword ptr [rsp+78h+StringSecurityDescriptorLen], 53Ch
0x180002938  call    WPP_SF_sdd
0x18000293d  mov     [r15], rsi
0x180002940  jmp     short loc_180002975
0x180002942  mov     rcx, [rcx+10h]
0x180002946  lea     r9, aGetsddetailsfr_0; "GetSDDetailsFromObjectID"
0x18000294d  mov     [rsp+78h+var_48], r14d
0x180002952  mov     edx, 0Ch
0x180002957  mov     [rsp+78h+var_50], rsi
0x18000295c  mov     dword ptr [rsp+78h+StringSecurityDescriptorLen], 53Ch
0x180002964  call    WPP_SF_sdqd
0x180002969  jmp     loc_180002748
0x18000296e  lea     r12, WPP_GLOBAL_Control
0x180002975  mov     rcx, cs:WPP_GLOBAL_Control
0x18000297c  cmp     rcx, r12
0x18000297f  jz      loc_1800027CF
0x180002985  test    byte ptr [rcx+1Ch], 4
0x180002989  jz      loc_1800027CF
0x18000298f  mov     edx, 8Dh
0x180002994  mov     r9d, ebx
0x180002997  jmp     short loc_1800029FF
0x180002999  call    cs:__imp_GetLastError
0x18000299f  mov     edi, eax
0x1800029a1  test    eax, eax
0x1800029a3  jz      loc_1800027A4
0x1800029a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800029b0  lea     rax, WPP_GLOBAL_Control
0x1800029b7  cmp     rcx, rax
0x1800029ba  jz      loc_1800027CF
0x1800029c0  test    byte ptr [rcx+1Ch], 4
0x1800029c4  jz      loc_1800027CF
0x1800029ca  mov     edx, 8Eh
0x1800029cf  jmp     short loc_1800029FC
0x1800029d1  mov     edi, 57h ; 'W'
0x1800029d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800029dd  lea     rax, WPP_GLOBAL_Control
0x1800029e4  cmp     rcx, rax
0x1800029e7  jz      loc_1800027CF
0x1800029ed  test    byte ptr [rcx+1Ch], 4
0x1800029f1  jz      loc_1800027CF
0x1800029f7  mov     edx, 8Bh
0x1800029fc  mov     r9d, edi
0x1800029ff  mov     rcx, [rcx+10h]
0x180002a03  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x180002a0a  call    WPP_SF_L
0x180002a0f  jmp     loc_1800027CF
0x180002a14  mov     rcx, [rcx+10h]
0x180002a18  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x180002a1f  mov     edx, 8Fh
0x180002a24  mov     r9d, edi
0x180002a27  call    WPP_SF_L
0x180002a2c  jmp     loc_180002822
```
