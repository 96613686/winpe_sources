# IkeCopyOldMMToNewMMIkeV2

- ea: `0x1800e1028`
- end: `0x1800e139e`
- name: `IkeCopyOldMMToNewMMIkeV2`
- size: `886`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config`

## callers

- `0x1800e1944`

## callees

- `0x180001008`
- `0x1800010c8`
- `0x180006910`
- `0x180008388`
- `0x18002aa10`
- `0x180035234`
- `0x1800488f0`
- `0x18004890c`
- `0x18004aa3c`
- `0x18004c3e8`
- `0x180050850`
- `0x18006e4f8`
- `0x1800e0b80`
- `0x1800e1028`
- `0x1800e13a4`
- `0x1800e1c98`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e1344`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e1344`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e1318`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e1318`

## string_xrefs

- `0x1800e105b`: `IkeCopyOldMMToNewMMIkeV2`
- `0x1800e135f`: `IkeCopyOldMMToNewMMIkeV2`
- `0x1800e136b`: `IkeCopyOldMMToNewMMIkeV2`
- `0x1800e1134`: `Copy old MM to new MM`

## pseudocode

```c
__int64 __fastcall IkeCopyOldMMToNewMMIkeV2(__int64 a1, __int64 a2)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // r9
  __int64 v7; // rcx
  __int64 v8; // rdi
  __int64 TlsPeerAddr; // rbx
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  int TlsMmLuid; // eax
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // r8
  __int64 v18; // r9
  __int64 inserted; // rbx
  int v20; // edx
  int v21; // ecx
  int v22; // edx
  unsigned int v23; // eax
  int v24; // ecx
  unsigned int v25; // eax
  __int64 v26; // rcx
  __int64 v28; // [rsp+40h] [rbp-59h] BYREF
  __int64 v29; // [rsp+48h] [rbp-51h] BYREF
  __int64 v30; // [rsp+50h] [rbp-49h] BYREF
  char v31[32]; // [rsp+60h] [rbp-39h] BYREF
  __int64 *v32; // [rsp+80h] [rbp-19h]
  __int64 v33; // [rsp+88h] [rbp-11h]
  char v34[16]; // [rsp+90h] [rbp-9h] BYREF
  const char *v35; // [rsp+A0h] [rbp+7h]
  __int64 v36; // [rsp+A8h] [rbp+Fh]
  __int64 *v37; // [rsp+B0h] [rbp+17h]
  __int64 v38; // [rsp+B8h] [rbp+1Fh]
  __int64 *v39; // [rsp+C0h] [rbp+27h]
  __int64 v40; // [rsp+C8h] [rbp+2Fh]

  TraceLogHelper("IkeCopyOldMMToNewMMIkeV2", 1);
  *(_QWORD *)(a2 + 744) = *(_QWORD *)(a1 + 744);
  v7 = *(_QWORD *)(a1 + 1104);
  *(_QWORD *)(a1 + 744) = *(_QWORD *)(v7 + 472);
  *(_QWORD *)(v7 + 472) = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v8 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    TlsPeerAddr = IkeGetTlsPeerAddr(v7);
    TlsMmLuid = IkeGetTlsMmLuid(v11, v10, v12, v13);
    WPP_SF_iSqq(v8, 19, (unsigned int)WPP_639729265dbb3b0803814a57dbffdef8_Traceguids, TlsMmLuid, TlsPeerAddr, a1, a2);
  }
  if ( (unsigned int)dword_180173278 > 4 )
  {
    v28 = IkeGetTlsMmLuid(v7, v4, v5, v6);
    v32 = &v28;
    v33 = 8;
    v16 = IkeGetTlsPeerAddr(v15);
    tlgCreate1Sz_wchar_t(v34, v16);
    v36 = 22;
    v37 = &v29;
    v35 = "Copy old MM to new MM";
    v39 = &v30;
    v29 = a1;
    v38 = 8;
    v30 = a2;
    v40 = 8;
    tlgWriteTransfer_EtwEventWriteTransfer(
      (__int64)&dword_180173278,
      (unsigned __int8 *)byte_180161223,
      v17,
      v18,
      7,
      (__int64)v31);
  }
  if ( *(_QWORD *)(a2 + 736) || (inserted = IkeFindMMPolicy((int)a1 + 376, (int)a1 + 584, 0, 0, a2 + 736)) == 0 )
  {
    inserted = IkeInsertFilterToSAEntry((_QWORD *)a2, 0, 1, *(_QWORD *)(*(_QWORD *)(a2 + 736) + 16LL));
    if ( !inserted )
    {
      v20 = *(_DWORD *)(a2 + 592);
      v21 = v20 & 1;
      *(_DWORD *)(a2 + 592) = *(_DWORD *)(a1 + 592);
      v22 = v20 & 0x20000;
      if ( (*(_DWORD *)(a1 + 592) & 0x20000000) != 0 )
        _InterlockedIncrement((volatile signed __int32 *)&gIkeExtGlobals[87]);
      v23 = *(_DWORD *)(a2 + 592) & 0xFFFFBFFC | ((v21 ^ 1) + 1);
      v24 = v23 | 0x20000;
      v25 = v23 & 0xFFFDFFFF;
      if ( !v22 )
        v24 = v25;
      *(_DWORD *)(a2 + 592) = v24 & 0xFFFFDFFF;
      *(_DWORD *)(a2 + 1064) = *(_DWORD *)(a1 + 1064);
      *(_DWORD *)(a2 + 1068) = *(_DWORD *)(a1 + 1068);
      **(_DWORD **)(a2 + 616) = 5;
      *(_DWORD *)(*(_QWORD *)(a2 + 616) + 4LL) = 6;
      *(_DWORD *)(*(_QWORD *)(a2 + 616) + 8LL) = *(_DWORD *)(*(_QWORD *)(a1 + 616) + 8LL);
      *(_DWORD *)(*(_QWORD *)(a2 + 1104) + 612LL) = *(_DWORD *)(*(_QWORD *)(a1 + 1104) + 612LL);
      inserted = IkeDeriveNewSaCryptoInplaceRekeyIkeV2(a1, a2);
      if ( !inserted )
      {
        inserted = IkeMigrateMobikeAndAcquireList(a1, a2);
        if ( !inserted )
        {
          inserted = IkeCopyIkeV2Sa(a1, a2);
          if ( !inserted )
          {
            *(_OWORD *)(a2 + 624) = *(_OWORD *)(a1 + 624);
            *(_QWORD *)(a2 + 640) = *(_QWORD *)(a1 + 640);
            if ( *(_QWORD *)(a2 + 640) )
              *(_QWORD *)(a2 + 640) = 0;
            EnterCriticalSection((LPCRITICAL_SECTION)(a2 + 48));
            v26 = *(_QWORD *)(a1 + 304);
            if ( v26 )
              inserted = IkeCopyIpsecId(v26, (_QWORD *)(a2 + 304));
            *(_DWORD *)(a2 + 296) |= 1u;
            LeaveCriticalSection((LPCRITICAL_SECTION)(a2 + 48));
            if ( !inserted )
              inserted = IkeMigrateQmList(a1, a2);
          }
        }
      }
    }
  }
  TraceLogHelper("IkeCopyOldMMToNewMMIkeV2", 0);
  return IkeReturnError(inserted, "IkeCopyOldMMToNewMMIkeV2");
}

```

## disassembly

```asm
0x1800e1028  mov     [rsp-8+arg_10], rbx
0x1800e102d  mov     [rsp-8+arg_18], rsi
0x1800e1032  push    rbp
0x1800e1033  push    rdi
0x1800e1034  push    r14
0x1800e1036  lea     rbp, [rsp-47h]
0x1800e103b  sub     rsp, 0E0h
0x1800e1042  mov     rax, cs:__security_cookie
0x1800e1049  xor     rax, rsp
0x1800e104c  mov     [rbp+57h+var_20], rax
0x1800e1050  mov     rsi, rdx
0x1800e1053  mov     r14, rcx
0x1800e1056  mov     edx, 1
0x1800e105b  lea     rcx, aIkecopyoldmmto; "IkeCopyOldMMToNewMMIkeV2"
0x1800e1062  call    TraceLogHelper
0x1800e1067  mov     rax, [r14+2E8h]
0x1800e106e  mov     [rsi+2E8h], rax
0x1800e1075  mov     rcx, [r14+450h]
0x1800e107c  mov     rax, [rcx+1D8h]
0x1800e1083  mov     [r14+2E8h], rax
0x1800e108a  mov     qword ptr [rcx+1D8h], 0
0x1800e1095  mov     rdi, cs:WPP_GLOBAL_Control
0x1800e109c  lea     rax, WPP_GLOBAL_Control
0x1800e10a3  cmp     rdi, rax
0x1800e10a6  jz      short loc_1800E10EB
0x1800e10a8  cmp     byte ptr [rdi+19h], 4
0x1800e10ac  jb      short loc_1800E10EB
0x1800e10ae  test    byte ptr [rdi+1Ch], 10h
0x1800e10b2  jz      short loc_1800E10EB
0x1800e10b4  mov     rdi, [rdi+10h]
0x1800e10b8  call    IkeGetTlsPeerAddr
0x1800e10bd  mov     rbx, rax
0x1800e10c0  call    IkeGetTlsMmLuid
0x1800e10c5  mov     [rsp+0F0h+var_C0], rsi
0x1800e10ca  lea     r8, WPP_639729265dbb3b0803814a57dbffdef8_Traceguids
0x1800e10d1  mov     r9, rax
0x1800e10d4  mov     [rsp+0F0h+var_C8], r14
0x1800e10d9  mov     edx, 13h
0x1800e10de  mov     [rsp+0F0h+var_D0], rbx
0x1800e10e3  mov     rcx, rdi
0x1800e10e6  call    WPP_SF_iSqq
0x1800e10eb  mov     eax, cs:dword_180173278
0x1800e10f1  cmp     eax, 4
0x1800e10f4  jbe     loc_1800E1183
0x1800e10fa  call    IkeGetTlsMmLuid
0x1800e10ff  mov     [rbp+57h+var_B0], rax
0x1800e1103  lea     rax, [rbp+57h+var_B0]
0x1800e1107  mov     [rbp+57h+var_70], rax
0x1800e110b  mov     [rbp+57h+var_68], 8
0x1800e1113  call    IkeGetTlsPeerAddr
0x1800e1118  mov     rdx, rax
0x1800e111b  lea     rcx, [rbp+57h+var_60]
0x1800e111f  call    _tlgCreate1Sz_wchar_t
0x1800e1124  lea     rax, [rbp+57h+var_A8]
0x1800e1128  mov     [rbp+57h+var_48], 16h
0x1800e1130  mov     [rbp+57h+var_40], rax
0x1800e1134  lea     rcx, aCopyOldMmToNew; "Copy old MM to new MM"
0x1800e113b  lea     rax, [rbp+57h+var_A0]
0x1800e113f  mov     [rbp+57h+var_50], rcx
0x1800e1143  mov     [rbp+57h+var_30], rax
0x1800e1147  lea     rdx, byte_180161223
0x1800e114e  lea     rax, [rbp+57h+var_90]
0x1800e1152  mov     [rbp+57h+var_A8], r14
0x1800e1156  mov     [rsp+0F0h+var_C8], rax
0x1800e115b  lea     rcx, dword_180173278
0x1800e1162  mov     dword ptr [rsp+0F0h+var_D0], 7
0x1800e116a  mov     [rbp+57h+var_38], 8
0x1800e1172  mov     [rbp+57h+var_A0], rsi
0x1800e1176  mov     [rbp+57h+var_28], 8
0x1800e117e  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x1800e1183  lea     rdi, [rsi+2E0h]
0x1800e118a  cmp     qword ptr [rdi], 0
0x1800e118e  jnz     short loc_1800E11BA
0x1800e1190  lea     rdx, [r14+248h]
0x1800e1197  mov     [rsp+0F0h+var_D0], rdi
0x1800e119c  lea     rcx, [r14+178h]
0x1800e11a3  xor     r9d, r9d
0x1800e11a6  xor     r8d, r8d
0x1800e11a9  call    IkeFindMMPolicy
0x1800e11ae  mov     rbx, rax
0x1800e11b1  test    rax, rax
0x1800e11b4  jnz     loc_1800E135D
0x1800e11ba  mov     r9, [rdi]
0x1800e11bd  mov     r8b, 1
0x1800e11c0  xor     edx, edx
0x1800e11c2  mov     rcx, rsi
0x1800e11c5  mov     r9, [r9+10h]
0x1800e11c9  call    IkeInsertFilterToSAEntry
0x1800e11ce  mov     rbx, rax
0x1800e11d1  test    rax, rax
0x1800e11d4  jnz     loc_1800E135D
0x1800e11da  mov     edx, [rsi+250h]
0x1800e11e0  mov     r8d, 20000h
0x1800e11e6  mov     eax, [r14+250h]
0x1800e11ed  mov     ecx, edx
0x1800e11ef  and     ecx, 1
0x1800e11f2  mov     [rsi+250h], eax
0x1800e11f8  and     edx, r8d
0x1800e11fb  test    dword ptr [r14+250h], 20000000h
0x1800e1206  jz      short loc_1800E1216
0x1800e1208  mov     rax, cs:gIkeExtGlobals
0x1800e120f  lock inc dword ptr [rax+0D98h]
0x1800e1216  mov     eax, [rsi+250h]
0x1800e121c  xor     ecx, 1
0x1800e121f  and     eax, 0FFFFBFFCh
0x1800e1224  inc     ecx
0x1800e1226  or      ecx, eax
0x1800e1228  mov     eax, ecx
0x1800e122a  or      ecx, r8d
0x1800e122d  btr     eax, 11h
0x1800e1231  test    edx, edx
0x1800e1233  mov     rdx, rsi
0x1800e1236  cmovz   ecx, eax
0x1800e1239  btr     ecx, 0Dh
0x1800e123d  mov     [rsi+250h], ecx
0x1800e1243  mov     eax, [r14+428h]
0x1800e124a  mov     [rsi+428h], eax
0x1800e1250  mov     eax, [r14+42Ch]
0x1800e1257  mov     [rsi+42Ch], eax
0x1800e125d  mov     rax, [rsi+268h]
0x1800e1264  mov     dword ptr [rax], 5
0x1800e126a  mov     rax, [rsi+268h]
0x1800e1271  mov     dword ptr [rax+4], 6
0x1800e1278  mov     rax, [r14+268h]
0x1800e127f  mov     rcx, [rsi+268h]
0x1800e1286  mov     eax, [rax+8]
0x1800e1289  mov     [rcx+8], eax
0x1800e128c  mov     rax, [r14+450h]
0x1800e1293  mov     rcx, [rsi+450h]
0x1800e129a  mov     eax, [rax+264h]
0x1800e12a0  mov     [rcx+264h], eax
0x1800e12a6  mov     rcx, r14
0x1800e12a9  call    IkeDeriveNewSaCryptoInplaceRekeyIkeV2
0x1800e12ae  mov     rbx, rax
0x1800e12b1  test    rax, rax
0x1800e12b4  jnz     loc_1800E135D
0x1800e12ba  mov     rdx, rsi
0x1800e12bd  mov     rcx, r14
0x1800e12c0  call    IkeMigrateMobikeAndAcquireList
0x1800e12c5  mov     rbx, rax
0x1800e12c8  test    rax, rax
0x1800e12cb  jnz     loc_1800E135D
0x1800e12d1  mov     rdx, rsi
0x1800e12d4  mov     rcx, r14
0x1800e12d7  call    IkeCopyIkeV2Sa
0x1800e12dc  mov     rbx, rax
0x1800e12df  test    rax, rax
0x1800e12e2  jnz     short loc_1800E135D
0x1800e12e4  movups  xmm0, xmmword ptr [r14+270h]
0x1800e12ec  movups  xmmword ptr [rsi+270h], xmm0
0x1800e12f3  movsd   xmm1, qword ptr [r14+280h]
0x1800e12fc  movsd   qword ptr [rsi+280h], xmm1
0x1800e1304  cmp     [rsi+280h], rax
0x1800e130b  jz      short loc_1800E1314
0x1800e130d  mov     [rsi+280h], rax
0x1800e1314  lea     rcx, [rsi+30h]; lpCriticalSection
0x1800e1318  call    cs:__imp_EnterCriticalSection
0x1800e131e  mov     rcx, [r14+130h]
0x1800e1325  test    rcx, rcx
0x1800e1328  jz      short loc_1800E1339
0x1800e132a  lea     rdx, [rsi+130h]
0x1800e1331  call    IkeCopyIpsecId
0x1800e1336  mov     rbx, rax
0x1800e1339  or      dword ptr [rsi+128h], 1
0x1800e1340  lea     rcx, [rsi+30h]; lpCriticalSection
0x1800e1344  call    cs:__imp_LeaveCriticalSection
0x1800e134a  test    rbx, rbx
0x1800e134d  jnz     short loc_1800E135D
0x1800e134f  mov     rdx, rsi
0x1800e1352  mov     rcx, r14
0x1800e1355  call    IkeMigrateQmList
0x1800e135a  mov     rbx, rax
0x1800e135d  xor     edx, edx
0x1800e135f  lea     rcx, aIkecopyoldmmto; "IkeCopyOldMMToNewMMIkeV2"
0x1800e1366  call    TraceLogHelper
0x1800e136b  lea     rdx, aIkecopyoldmmto; "IkeCopyOldMMToNewMMIkeV2"
0x1800e1372  mov     rcx, rbx
0x1800e1375  call    IkeReturnError
0x1800e137a  mov     rcx, [rbp+57h+var_20]
0x1800e137e  xor     rcx, rsp; StackCookie
0x1800e1381  call    __security_check_cookie
0x1800e1386  lea     r11, [rsp+0F0h+var_10]
0x1800e138e  mov     rbx, [r11+30h]
0x1800e1392  mov     rsi, [r11+38h]
0x1800e1396  mov     rsp, r11
0x1800e1399  pop     r14
0x1800e139b  pop     rdi
0x1800e139c  pop     rbp
0x1800e139d  retn
```
