# sub_1400BCCF0

- ea: `0x1400bccf0`
- end: `0x1400bda48`
- name: `sub_1400BCCF0`
- size: `3416`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x14009a098`

## callees

- `0x14000d760`
- `0x140011860`
- `0x140012200`
- `0x140036780`
- `0x1400367a0`
- `0x14007f288`
- `0x140081450`
- `0x140097dcc`
- `0x14009f738`
- `0x1400bcac0`
- `0x1400bccf0`
- `0x1400eb87c`
- `0x1400ed030`
- `0x1400eedb0`
- `0x1401203c0`

## import_xrefs

- `MpClient!MpGetDeviceControlStatus` at `0x1400bd265`
- `MpClient!MpGetDeviceControlStatus` at `0x1400bd265`
- `MpClient!MpGetRunningMode` at `0x1400bcf88`
- `MpClient!MpGetRunningMode` at `0x1400bcf88`
- `MpClient!MpGetDeviceControlSecurityPolicies` at `0x1400bd584`
- `MpClient!MpGetDeviceControlSecurityPolicies` at `0x1400bd584`
- `MpClient!MpManagerStatusQueryEx` at `0x1400bcf3a`
- `MpClient!MpManagerStatusQueryEx` at `0x1400bcf3a`
- `MpClient!MpFreeMemory` at `0x1400bd5c8`
- `MpClient!MpFreeMemory` at `0x1400bd5dc`
- `MpClient!MpFreeMemory` at `0x1400bd6c2`
- `MpClient!MpFreeMemory` at `0x1400bd8f2`
- `MpClient!MpFreeMemory` at `0x1400bd902`
- `MpClient!MpFreeMemory` at `0x1400bd9ad`
- `MpClient!MpFreeMemory` at `0x1400bd9bd`
- `MpClient!MpFreeMemory` at `0x1400bd5c8`
- `MpClient!MpFreeMemory` at `0x1400bd5dc`
- `MpClient!MpFreeMemory` at `0x1400bd6c2`
- `MpClient!MpFreeMemory` at `0x1400bd8f2`
- `MpClient!MpFreeMemory` at `0x1400bd902`
- `MpClient!MpFreeMemory` at `0x1400bd9ad`
- `MpClient!MpFreeMemory` at `0x1400bd9bd`
- `MpClient!MpHandleClose` at `0x1400bcf0c`
- `MpClient!MpHandleClose` at `0x1400bd083`
- `MpClient!MpHandleClose` at `0x1400bd19b`
- `MpClient!MpHandleClose` at `0x1400bd222`
- `MpClient!MpHandleClose` at `0x1400bd92c`
- `MpClient!MpHandleClose` at `0x1400bd9e7`
- `MpClient!MpHandleClose` at `0x1400bcf0c`
- `MpClient!MpHandleClose` at `0x1400bd083`
- `MpClient!MpHandleClose` at `0x1400bd19b`
- `MpClient!MpHandleClose` at `0x1400bd222`
- `MpClient!MpHandleClose` at `0x1400bd92c`
- `MpClient!MpHandleClose` at `0x1400bd9e7`
- `MpClient!MpManagerOpen` at `0x1400bcec1`
- `MpClient!MpManagerOpen` at `0x1400bcec1`
- `KERNEL32!CloseHandle` at `0x1400bce8e`
- `KERNEL32!CloseHandle` at `0x1400bd094`
- `KERNEL32!CloseHandle` at `0x1400bd231`
- `KERNEL32!CloseHandle` at `0x1400bd93b`
- `KERNEL32!CloseHandle` at `0x1400bd9f6`
- `KERNEL32!CloseHandle` at `0x1400bce8e`
- `KERNEL32!CloseHandle` at `0x1400bd094`
- `KERNEL32!CloseHandle` at `0x1400bd231`
- `KERNEL32!CloseHandle` at `0x1400bd93b`
- `KERNEL32!CloseHandle` at `0x1400bd9f6`

## string_xrefs

- `0x1400bd385`: `DeviceControl status:\nPackageVersion: %d\nState: %ls\nDefaultEnforcement: %ls\nPoliciesLastUpdated: %ls\n`
- `0x1400bd0c1`: `Defender service running mode: %ls\n`

## pseudocode

```c
__int64 sub_1400BCCF0()
{
  int v0; // eax
  unsigned int v1; // ebx
  HANDLE v3; // rbx
  int v4; // eax
  unsigned int v5; // edi
  void *v6; // rdi
  int v7; // eax
  int v8; // esi
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  int RunningMode; // eax
  _QWORD *v12; // rsi
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  const wchar_t *v17; // r8
  int v18; // r15d
  void *v19; // rcx
  void *v20; // rsi
  int v21; // eax
  void *v22; // r15
  unsigned __int64 v23; // rcx
  HANDLE v24; // rcx
  HANDLE v25; // r14
  int v26; // eax
  const wchar_t *v27; // rdx
  int v28; // eax
  void *v29; // rcx
  void **v30; // rax
  HANDLE v31; // r12
  void *v32; // r13
  int v33; // eax
  HANDLE v34; // rcx
  void *v35; // r12
  unsigned __int64 v36; // rcx
  int v37; // eax
  int DeviceControlSecurityPolicies; // eax
  _QWORD *v39; // rcx
  __int64 v40; // rdx
  _QWORD *v41; // rcx
  __int64 v42; // rdx
  __int64 v43; // r8
  unsigned __int64 v44; // rcx
  __int64 v45; // rcx
  __int64 v46; // rcx
  __int64 v47; // rcx
  __int64 v48; // r8
  unsigned __int64 v49; // rcx
  void *Block; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v51; // [rsp+40h] [rbp-C8h] BYREF
  HANDLE hObject; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v53; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v54; // [rsp+58h] [rbp-B0h] BYREF
  void *v55; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v56; // [rsp+68h] [rbp-A0h] BYREF
  void *v57[3]; // [rsp+70h] [rbp-98h] BYREF
  __m128i si128; // [rsp+88h] [rbp-80h]
  __int128 v59; // [rsp+98h] [rbp-70h] BYREF
  _BYTE v60[432]; // [rsp+A8h] [rbp-60h] BYREF

  hObject = 0;
  v0 = sub_140097DCC((WCHAR **)&hObject);
  v1 = v0;
  if ( v0 < 0 )
  {
    if ( off_14018DE50 != (_UNKNOWN *)&off_14018DE50 && (*((_BYTE *)off_14018DE50 + 28) & 1) != 0 )
      sub_140081450(*((_QWORD *)off_14018DE50 + 2), 15, qword_140163DB8, (unsigned int)v0);
    sub_1400ED030(L"ERROR: GetSupportDir() failed (%#lx)\n", v1);
    if ( hObject )
      j_j_j__free_base(hObject);
    return v1;
  }
  v3 = hObject;
  Block = 0;
  v4 = sub_140011860(&Block, L"%ls\\%ls", hObject, L"DeviceControlInfo.txt");
  v5 = v4;
  if ( v4 < 0 )
  {
    if ( off_14018DE50 != (_UNKNOWN *)&off_14018DE50 && (*((_BYTE *)off_14018DE50 + 28) & 1) != 0 )
      sub_14009F738(*((_QWORD *)off_14018DE50 + 2), (__int64)L"DeviceControlInfo.txt", v4);
    sub_1400ED030(L"ERROR: NewSprintfW(%ls, %ls) failed (%#lx)\n", v3, L"DeviceControlInfo.txt", v5);
    if ( Block )
      j_j_j__free_base(Block);
    if ( v3 )
      j_j_j__free_base(v3);
    return v5;
  }
  v6 = Block;
  hObject = (HANDLE)-1LL;
  v7 = sub_1400BCAC0(&hObject, Block);
  v8 = v7;
  if ( v7 < 0 )
  {
    if ( off_14018DE50 != (_UNKNOWN *)&off_14018DE50 && (*((_BYTE *)off_14018DE50 + 28) & 1) != 0 )
      sub_140081450(*((_QWORD *)off_14018DE50 + 2), 17, qword_140163DB8, (unsigned int)v7);
LABEL_21:
    if ( hObject != (HANDLE)-1LL )
      CloseHandle(hObject);
    if ( v6 )
      j_j_j__free_base(v6);
    if ( v3 )
      j_j_j__free_base(v3);
    return (unsigned int)v8;
  }
  v51 = 0;
  v8 = MpManagerOpen(0, &v51);
  if ( v8 < 0 )
  {
    v9 = off_14018DE50;
    if ( off_14018DE50 != (_UNKNOWN *)&off_14018DE50 && (*((_BYTE *)off_14018DE50 + 28) & 1) != 0 )
    {
      v10 = 18;
LABEL_32:
      sub_140081450(v9[2], v10, qword_140163DB8, (unsigned int)v8);
      goto LABEL_33;
    }
    goto LABEL_33;
  }
  sub_1401203C0(v60, 0, 432);
  v8 = MpManagerStatusQueryEx(v51, 1, v60);
  if ( v8 < 0 )
  {
    v9 = off_14018DE50;
    if ( off_14018DE50 != (_UNKNOWN *)&off_14018DE50 && (*((_BYTE *)off_14018DE50 + 28) & 1) != 0 )
    {
      v10 = 19;
      goto LABEL_32;
    }
LABEL_33:
    if ( v51 )
      MpHandleClose(v51);
    goto LABEL_21;
  }
  LODWORD(v56) = 0;
  if ( (v60[0] & 1) != 0 )
    goto LABEL_44;
  RunningMode = MpGetRunningMode(v51, &v56);
  if ( RunningMode < 0 )
  {
    v12 = off_14018DE50;
    if ( off_14018DE50 == (_UNKNOWN *)&off_14018DE50 || (*((_BYTE *)off_14018DE50 + 28) & 1) == 0 )
      goto LABEL_45;
    sub_140081450(*((_QWORD *)off_14018DE50 + 2), 20, qword_140163DB8, (unsigned int)RunningMode);
LABEL_44:
    v12 = off_14018DE50;
LABEL_45:
    v13 = 3;
    LODWORD(v56) = 3;
    goto LABEL_46;
  }
  v13 = v56;
  v12 = off_14018DE50;
LABEL_46:
  Block = 0;
  if ( v13 )
  {
    v14 = v13 - 1;
    if ( v14 )
    {
      v15 = v14 - 1;
      if ( v15 )
      {
        v16 = v15 - 2;
        if ( v16 )
        {
          if ( v16 == 1 )
            v17 = L"Passive Audit Mode";
          else
            v17 = L"Not running";
        }
        else
        {
          v17 = L"EDR Block Mode";
        }
      }
      else
      {
        v17 = L"SxS Passive Mode";
      }
    }
    else
    {
      v17 = L"Passive Mode";
    }
  }
  else
  {
    v17 = L"Normal";
  }
  v18 = sub_140011860(&Block, L"%s", v17);
  if ( v18 < 0 )
  {
    if ( v12 != &off_14018DE50 && (*((_BYTE *)v12 + 28) & 1) != 0 )
      sub_140081450(v12[2], 21, qword_140163DB8, (unsigned int)v18);
    v19 = Block;
    if ( !Block )
      goto LABEL_64;
    goto LABEL_63;
  }
  v20 = Block;
  v57[0] = 0;
  v21 = sub_140011860(v57, L"Defender service running mode: %ls\r\n", Block);
  v18 = v21;
  if ( v21 < 0 )
  {
    if ( off_14018DE50 != (_UNKNOWN *)&off_14018DE50 && (*((_BYTE *)off_14018DE50 + 28) & 1) != 0 )
      sub_140081450(*((_QWORD *)off_14018DE50 + 2), 22, qword_140163DB8, (unsigned int)v21);
    if ( v57[0] )
      j_j_j__free_base(v57[0]);
    if ( !v20 )
      goto LABEL_64;
    v19 = v20;
LABEL_63:
    j_j_j__free_base(v19);
LABEL_64:
    if ( v51 )
      MpHandleClose(v51);
    if ( hObject != (HANDLE)-1LL )
      CloseHandle(hObject);
    if ( v6 )
      j_j_j__free_base(v6);
    if ( v3 )
      j_j_j__free_base(v3);
    return (unsigned int)v18;
  }
  v22 = v57[0];
  v23 = -1;
  do
    ++v23;
  while ( *((_WORD *)v57[0] + v23) );
  v55 = 0;
  if ( !is_mul_ok(v23, 2u) )
  {
    if ( off_14018DE50 != (_UNKNOWN *)&off_14018DE50 && (*((_BYTE *)off_14018DE50 + 28) & 1) != 0 )
      sub_140081450(*((_QWORD *)off_14018DE50 + 2), 23, qword_140163DB8, 2147942934LL);
    if ( v22 )
      j_j_j__free_base(v22);
    if ( v20 )
      j_j_j__free_base(v20);
    if ( v51 )
      MpHandleClose(v51);
    v24 = hObject;
    if ( hObject == (HANDLE)-1LL )
      goto LABEL_252;
    goto LABEL_251;
  }
  v25 = hObject;
  v26 = sub_14000D760(hObject);
  LODWORD(Block) = v26;
  if ( v26 < 0 )
  {
    if ( off_14018DE50 != (_UNKNOWN *)&off_14018DE50 && (*((_BYTE *)off_14018DE50 + 28) & 1) != 0 )
      sub_140081450(*((_QWORD *)off_14018DE50 + 2), 24, qword_140163DB8, (unsigned int)v26);
    goto LABEL_99;
  }
  v59 = 0;
  if ( (int)MpGetDeviceControlStatus(&v59) >= 0 )
  {
    v57[0] = 0;
    sub_1400EEDB0(DWORD1(v59), v57);
    hObject = 0;
    if ( (_DWORD)v59 )
    {
      switch ( (_DWORD)v59 )
      {
        case 1:
          v27 = L"Initialized";
          break;
        case 2:
          v27 = L"Disabled";
          break;
        case 3:
          v27 = L"Enabled";
          break;
        case 4:
          v27 = L"Shutdown";
          break;
        default:
          v27 = L"Unknown";
          break;
      }
    }
    else
    {
      v27 = L"Uninitialized";
    }
    sub_140012200(&hObject, v27);
    *(_OWORD *)&v57[1] = 0;
    LOWORD(v57[1]) = 0;
    si128 = _mm_load_si128((const __m128i *)&xmmword_14016CE20);
    v28 = sub_1400EB87C(&v57[1], (char *)&v59 + 8);
    LODWORD(Block) = v28;
    if ( v28 < 0 )
    {
      if ( off_14018DE50 != (_UNKNOWN *)&off_14018DE50 && (*((_BYTE *)off_14018DE50 + 28) & 1) != 0 )
        sub_140081450(*((_QWORD *)off_14018DE50 + 2), 25, qword_140163DB8, (unsigned int)v28);
      sub_14007F288(&v57[1]);
      if ( hObject )
        j_j_j__free_base(hObject);
      v29 = v57[0];
      if ( !v57[0] )
        goto LABEL_99;
      goto LABEL_131;
    }
    v30 = &v57[1];
    v31 = hObject;
    if ( si128.m128i_i64[1] > 7uLL )
      v30 = (void **)v57[1];
    v32 = v57[0];
    v55 = 0;
    v33 = sub_140011860(
            &v55,
            L"DeviceControl status:\r\n"
             "PackageVersion: %d\r\n"
             "State: %ls\r\n"
             "DefaultEnforcement: %ls\r\n"
             "PoliciesLastUpdated: %ls\r\n",
            10,
            hObject,
            v57[0],
            v30);
    LODWORD(Block) = v33;
    if ( v33 < 0 )
    {
      if ( off_14018DE50 != (_UNKNOWN *)&off_14018DE50 && (*((_BYTE *)off_14018DE50 + 28) & 1) != 0 )
        sub_140081450(*((_QWORD *)off_14018DE50 + 2), 26, qword_140163DB8, (unsigned int)v33);
      if ( v55 )
        j_j_j__free_base(v55);
      sub_14007F288(&v57[1]);
      if ( !v31 )
        goto LABEL_143;
      v34 = v31;
LABEL_142:
      j_j_j__free_base(v34);
LABEL_143:
      if ( !v32 )
        goto LABEL_99;
      v29 = v32;
LABEL_131:
      j_j_j__free_base(v29);
LABEL_99:
      if ( v22 )
        j_j_j__free_base(v22);
      if ( v20 )
        j_j_j__free_base(v20);
      if ( v51 )
        MpHandleClose(v51);
      if ( v25 != (HANDLE)-1LL )
        CloseHandle(v25);
      if ( v6 )
        j_j_j__free_base(v6);
      if ( v3 )
        j_j_j__free_base(v3);
      return (unsigned int)Block;
    }
    v35 = v55;
    v36 = -1;
    do
      ++v36;
    while ( *((_WORD *)v55 + v36) );
    if ( !is_mul_ok(v36, 2u) )
    {
      if ( off_14018DE50 != (_UNKNOWN *)&off_14018DE50 && (*((_BYTE *)off_14018DE50 + 28) & 1) != 0 )
        sub_140081450(*((_QWORD *)off_14018DE50 + 2), 27, qword_140163DB8, 2147942934LL);
      if ( v35 )
        j_j_j__free_base(v35);
      sub_14007F288(&v57[1]);
      if ( hObject )
        j_j_j__free_base(hObject);
      if ( v32 )
        j_j_j__free_base(v32);
      goto LABEL_243;
    }
    v37 = sub_14000D760(v25);
    LODWORD(Block) = v37;
    if ( v37 < 0 )
    {
      if ( off_14018DE50 != (_UNKNOWN *)&off_14018DE50 && (*((_BYTE *)off_14018DE50 + 28) & 1) != 0 )
        sub_140081450(*((_QWORD *)off_14018DE50 + 2), 28, qword_140163DB8, (unsigned int)v37);
      if ( v35 )
        j_j_j__free_base(v35);
      sub_14007F288(&v57[1]);
      v34 = hObject;
      if ( !hObject )
        goto LABEL_143;
      goto LABEL_142;
    }
    if ( v35 )
      j_j_j__free_base(v35);
    sub_14007F288(&v57[1]);
    if ( hObject )
      j_j_j__free_base(hObject);
    if ( v32 )
      j_j_j__free_base(v32);
  }
  v53 = 0;
  v54 = 0;
  DeviceControlSecurityPolicies = MpGetDeviceControlSecurityPolicies(&v53, &v54);
  LODWORD(Block) = DeviceControlSecurityPolicies;
  if ( DeviceControlSecurityPolicies < 0 )
  {
    v39 = off_14018DE50;
    if ( off_14018DE50 == (_UNKNOWN *)&off_14018DE50 || (*((_BYTE *)off_14018DE50 + 28) & 1) == 0 )
      goto LABEL_176;
    v40 = 29;
LABEL_175:
    sub_140081450(v39[2], v40, qword_140163DB8, (unsigned int)DeviceControlSecurityPolicies);
LABEL_176:
    if ( v54 )
      MpFreeMemory(v54);
    if ( v53 )
      MpFreeMemory(v53);
    goto LABEL_99;
  }
  if ( v53 )
  {
    if ( !is_mul_ok(0x3Bu, 2u) )
    {
      v41 = off_14018DE50;
      if ( off_14018DE50 == (_UNKNOWN *)&off_14018DE50 || (*((_BYTE *)off_14018DE50 + 28) & 1) == 0 )
        goto LABEL_238;
      v42 = 30;
      goto LABEL_236;
    }
    DeviceControlSecurityPolicies = sub_14000D760(v25);
    LODWORD(Block) = DeviceControlSecurityPolicies;
    if ( DeviceControlSecurityPolicies < 0 )
    {
      v39 = off_14018DE50;
      if ( off_14018DE50 == (_UNKNOWN *)&off_14018DE50 || (*((_BYTE *)off_14018DE50 + 28) & 1) == 0 )
        goto LABEL_176;
      v40 = 31;
      goto LABEL_175;
    }
    v43 = v53;
    v44 = -1;
    do
      ++v44;
    while ( *(_WORD *)(v53 + 2 * v44) );
    if ( !is_mul_ok(v44, 2u) )
    {
      if ( off_14018DE50 != (_UNKNOWN *)&off_14018DE50 && (*((_BYTE *)off_14018DE50 + 28) & 1) != 0 )
      {
        sub_140081450(*((_QWORD *)off_14018DE50 + 2), 32, qword_140163DB8, 2147942934LL);
        v43 = v53;
      }
      if ( v54 )
      {
        MpFreeMemory(v54);
        v43 = v53;
      }
      if ( !v43 )
        goto LABEL_243;
      v45 = v43;
      goto LABEL_242;
    }
    DeviceControlSecurityPolicies = sub_14000D760(v25);
    LODWORD(Block) = DeviceControlSecurityPolicies;
    if ( DeviceControlSecurityPolicies < 0 )
    {
      v39 = off_14018DE50;
      if ( off_14018DE50 == (_UNKNOWN *)&off_14018DE50 || (*((_BYTE *)off_14018DE50 + 28) & 1) == 0 )
        goto LABEL_176;
      v40 = 33;
      goto LABEL_175;
    }
    if ( !is_mul_ok(0x3Bu, 2u) )
    {
      v41 = off_14018DE50;
      if ( off_14018DE50 == (_UNKNOWN *)&off_14018DE50 || (*((_BYTE *)off_14018DE50 + 28) & 1) == 0 )
        goto LABEL_238;
      v42 = 34;
      goto LABEL_236;
    }
    DeviceControlSecurityPolicies = sub_14000D760(v25);
    LODWORD(Block) = DeviceControlSecurityPolicies;
    if ( DeviceControlSecurityPolicies < 0 )
    {
      v39 = off_14018DE50;
      if ( off_14018DE50 == (_UNKNOWN *)&off_14018DE50 || (*((_BYTE *)off_14018DE50 + 28) & 1) == 0 )
        goto LABEL_176;
      v40 = 35;
      goto LABEL_175;
    }
  }
  v46 = v54;
  if ( v54 )
  {
    if ( !is_mul_ok(0x3Au, 2u) )
    {
      if ( off_14018DE50 == (_UNKNOWN *)&off_14018DE50 || (*((_BYTE *)off_14018DE50 + 28) & 1) == 0 )
      {
LABEL_239:
        if ( !v46 )
          goto LABEL_241;
        goto LABEL_240;
      }
      v47 = *((_QWORD *)off_14018DE50 + 2);
      v42 = 36;
      goto LABEL_237;
    }
    DeviceControlSecurityPolicies = sub_14000D760(v25);
    LODWORD(Block) = DeviceControlSecurityPolicies;
    if ( DeviceControlSecurityPolicies < 0 )
    {
      v39 = off_14018DE50;
      if ( off_14018DE50 == (_UNKNOWN *)&off_14018DE50 || (*((_BYTE *)off_14018DE50 + 28) & 1) == 0 )
        goto LABEL_176;
      v40 = 37;
      goto LABEL_175;
    }
    v48 = v54;
    v49 = -1;
    do
      ++v49;
    while ( *(_WORD *)(v54 + 2 * v49) );
    if ( !is_mul_ok(v49, 2u) )
    {
      if ( off_14018DE50 != (_UNKNOWN *)&off_14018DE50 && (*((_BYTE *)off_14018DE50 + 28) & 1) != 0 )
      {
        sub_140081450(*((_QWORD *)off_14018DE50 + 2), 38, qword_140163DB8, 2147942934LL);
        v48 = v54;
      }
      if ( !v48 )
      {
LABEL_241:
        v45 = v53;
        if ( !v53 )
        {
LABEL_243:
          if ( v22 )
            j_j_j__free_base(v22);
          if ( v20 )
            j_j_j__free_base(v20);
          if ( v51 )
            MpHandleClose(v51);
          if ( v25 == (HANDLE)-1LL )
            goto LABEL_252;
          v24 = v25;
LABEL_251:
          CloseHandle(v24);
LABEL_252:
          if ( v6 )
            j_j_j__free_base(v6);
          if ( v3 )
            j_j_j__free_base(v3);
          return 2147942934LL;
        }
LABEL_242:
        MpFreeMemory(v45);
        goto LABEL_243;
      }
      v46 = v48;
LABEL_240:
      MpFreeMemory(v46);
      goto LABEL_241;
    }
    DeviceControlSecurityPolicies = sub_14000D760(v25);
    LODWORD(Block) = DeviceControlSecurityPolicies;
    if ( DeviceControlSecurityPolicies < 0 )
    {
      v39 = off_14018DE50;
      if ( off_14018DE50 == (_UNKNOWN *)&off_14018DE50 || (*((_BYTE *)off_14018DE50 + 28) & 1) == 0 )
        goto LABEL_176;
      v40 = 39;
      goto LABEL_175;
    }
    if ( !is_mul_ok(0x3Au, 2u) )
    {
      v41 = off_14018DE50;
      if ( off_14018DE50 == (_UNKNOWN *)&off_14018DE50 || (*((_BYTE *)off_14018DE50 + 28) & 1) == 0 )
        goto LABEL_238;
      v42 = 40;
LABEL_236:
      v47 = v41[2];
LABEL_237:
      sub_140081450(v47, v42, qword_140163DB8, 2147942934LL);
LABEL_238:
      v46 = v54;
      goto LABEL_239;
    }
    DeviceControlSecurityPolicies = sub_14000D760(v25);
    LODWORD(Block) = DeviceControlSecurityPolicies;
    if ( DeviceControlSecurityPolicies < 0 )
    {
      v39 = off_14018DE50;
      if ( off_14018DE50 == (_UNKNOWN *)&off_14018DE50 || (*((_BYTE *)off_14018DE50 + 28) & 1) == 0 )
        goto LABEL_176;
      v40 = 41;
      goto LABEL_175;
    }
    if ( v54 )
      MpFreeMemory(v54);
  }
  if ( v53 )
    MpFreeMemory(v53);
  if ( v22 )
    j_j_j__free_base(v22);
  if ( v20 )
    j_j_j__free_base(v20);
  if ( v51 )
    MpHandleClose(v51);
  if ( v25 != (HANDLE)-1LL )
    CloseHandle(v25);
  if ( v6 )
    j_j_j__free_base(v6);
  if ( v3 )
    j_j_j__free_base(v3);
  return 0;
}

```

## disassembly

```asm
0x1400bccf0  mov     rax, rsp
0x1400bccf3  mov     [rax+8], rbx
0x1400bccf7  mov     [rax+10h], rsi
0x1400bccfb  mov     [rax+18h], rdi
0x1400bccff  push    rbp
0x1400bcd00  push    r12
0x1400bcd02  push    r13
0x1400bcd04  push    r14
0x1400bcd06  push    r15
0x1400bcd08  lea     rbp, [rax-188h]
0x1400bcd0f  sub     rsp, 260h
0x1400bcd16  mov     rax, cs:__security_cookie
0x1400bcd1d  xor     rax, rsp
0x1400bcd20  mov     [rbp+180h+var_30], rax
0x1400bcd27  xor     r15d, r15d
0x1400bcd2a  lea     rcx, [rsp+280h+hObject]
0x1400bcd2f  mov     [rsp+280h+hObject], r15
0x1400bcd34  call    sub_140097DCC
0x1400bcd39  mov     ebx, eax
0x1400bcd3b  test    eax, eax
0x1400bcd3d  jns     short loc_1400BCD93
0x1400bcd3f  mov     rcx, cs:off_14018DE50
0x1400bcd46  lea     rdx, off_14018DE50
0x1400bcd4d  cmp     rcx, rdx
0x1400bcd50  jz      short loc_1400BCD6F
0x1400bcd52  test    byte ptr [rcx+1Ch], 1
0x1400bcd56  jz      short loc_1400BCD6F
0x1400bcd58  mov     rcx, [rcx+10h]
0x1400bcd5c  lea     edx, [r15+0Fh]
0x1400bcd60  mov     r9d, eax
0x1400bcd63  lea     r8, qword_140163DB8
0x1400bcd6a  call    sub_140081450
0x1400bcd6f  mov     edx, ebx
0x1400bcd71  lea     rcx, aErrorGetsuppor_0; "ERROR: GetSupportDir() failed (%#lx)\n"
0x1400bcd78  call    sub_1400ED030
0x1400bcd7d  mov     rcx, [rsp+280h+hObject]; Block
0x1400bcd82  test    rcx, rcx
0x1400bcd85  jz      short loc_1400BCD8C
0x1400bcd87  call    j_j_j__free_base
0x1400bcd8c  mov     eax, ebx
0x1400bcd8e  jmp     loc_1400BDA18
0x1400bcd93  mov     rbx, [rsp+280h+hObject]
0x1400bcd98  lea     rsi, aDevicecontroli; "DeviceControlInfo.txt"
0x1400bcd9f  mov     r9, rsi
0x1400bcda2  mov     [rsp+280h+Block], r15
0x1400bcda7  mov     r8, rbx
0x1400bcdaa  lea     rdx, aLsLs; "%ls\\%ls"
0x1400bcdb1  lea     rcx, [rsp+280h+Block]
0x1400bcdb6  call    sub_140011860
0x1400bcdbb  mov     edi, eax
0x1400bcdbd  test    eax, eax
0x1400bcdbf  jns     short loc_1400BCE33
0x1400bcdc1  mov     rcx, cs:off_14018DE50
0x1400bcdc8  lea     rdx, off_14018DE50
0x1400bcdcf  cmp     rcx, rdx
0x1400bcdd2  jz      short loc_1400BCDFB
0x1400bcdd4  test    byte ptr [rcx+1Ch], 1
0x1400bcdd8  jz      short loc_1400BCDFB
0x1400bcdda  mov     rcx, [rcx+10h]; LoggerHandle
0x1400bcdde  lea     r8, qword_140163DB8
0x1400bcde5  mov     dword ptr [rsp+280h+var_258], eax; char
0x1400bcde9  mov     edx, 10h
0x1400bcdee  mov     r9, rbx
0x1400bcdf1  mov     [rsp+280h+var_260], rsi; __int64
0x1400bcdf6  call    sub_14009F738
0x1400bcdfb  mov     r9d, edi
0x1400bcdfe  lea     rcx, aErrorNewsprint_0; "ERROR: NewSprintfW(%ls, %ls) failed (%#"...
0x1400bce05  mov     r8, rsi
0x1400bce08  mov     rdx, rbx
0x1400bce0b  call    sub_1400ED030
0x1400bce10  mov     rcx, [rsp+280h+Block]; Block
0x1400bce15  test    rcx, rcx
0x1400bce18  jz      short loc_1400BCE1F
0x1400bce1a  call    j_j_j__free_base
0x1400bce1f  test    rbx, rbx
0x1400bce22  jz      short loc_1400BCE2C
0x1400bce24  mov     rcx, rbx; Block
0x1400bce27  call    j_j_j__free_base
0x1400bce2c  mov     eax, edi
0x1400bce2e  jmp     loc_1400BDA18
0x1400bce33  mov     rdi, [rsp+280h+Block]
0x1400bce38  lea     rcx, [rsp+280h+hObject]
0x1400bce3d  or      r14, 0FFFFFFFFFFFFFFFFh
0x1400bce41  mov     rdx, rdi
0x1400bce44  mov     [rsp+280h+hObject], r14
0x1400bce49  call    sub_1400BCAC0
0x1400bce4e  mov     esi, eax
0x1400bce50  test    eax, eax
0x1400bce52  jns     short loc_1400BCEB5
0x1400bce54  mov     rcx, cs:off_14018DE50
0x1400bce5b  lea     rdx, off_14018DE50
0x1400bce62  cmp     rcx, rdx
0x1400bce65  jz      short loc_1400BCE84
0x1400bce67  test    byte ptr [rcx+1Ch], 1
0x1400bce6b  jz      short loc_1400BCE84
0x1400bce6d  mov     rcx, [rcx+10h]
0x1400bce71  lea     edx, [r14+12h]
0x1400bce75  mov     r9d, eax
0x1400bce78  lea     r8, qword_140163DB8
0x1400bce7f  call    sub_140081450
0x1400bce84  mov     rcx, [rsp+280h+hObject]; hObject
0x1400bce89  cmp     rcx, r14
0x1400bce8c  jz      short loc_1400BCE94
0x1400bce8e  call    cs:__imp_CloseHandle
0x1400bce94  test    rdi, rdi
0x1400bce97  jz      short loc_1400BCEA1
0x1400bce99  mov     rcx, rdi; Block
0x1400bce9c  call    j_j_j__free_base
0x1400bcea1  test    rbx, rbx
0x1400bcea4  jz      short loc_1400BCEAE
0x1400bcea6  mov     rcx, rbx; Block
0x1400bcea9  call    j_j_j__free_base
0x1400bceae  mov     eax, esi
0x1400bceb0  jmp     loc_1400BDA18
0x1400bceb5  lea     rdx, [rsp+280h+var_248]
0x1400bceba  mov     [rsp+280h+var_248], r15
0x1400bcebf  xor     ecx, ecx
0x1400bcec1  call    cs:MpManagerOpen
0x1400bcec7  mov     esi, eax
0x1400bcec9  test    eax, eax
0x1400bcecb  jns     short loc_1400BCF17
0x1400bcecd  mov     rcx, cs:off_14018DE50
0x1400bced4  lea     rdx, off_14018DE50
0x1400bcedb  cmp     rcx, rdx
0x1400bcede  jz      short loc_1400BCEFE
0x1400bcee0  test    byte ptr [rcx+1Ch], 1
0x1400bcee4  jz      short loc_1400BCEFE
0x1400bcee6  mov     edx, 12h
0x1400bceeb  mov     rcx, [rcx+10h]
0x1400bceef  lea     r8, qword_140163DB8
0x1400bcef6  mov     r9d, esi
0x1400bcef9  call    sub_140081450
0x1400bcefe  mov     rcx, [rsp+280h+var_248]
0x1400bcf03  test    rcx, rcx
0x1400bcf06  jz      loc_1400BCE84
0x1400bcf0c  call    cs:__imp_MpHandleClose
0x1400bcf12  jmp     loc_1400BCE84
0x1400bcf17  xor     edx, edx
0x1400bcf19  lea     rcx, [rbp+180h+var_1E0]
0x1400bcf1d  mov     r8d, 1B0h
0x1400bcf23  call    sub_1401203C0
0x1400bcf28  mov     rcx, [rsp+280h+var_248]
0x1400bcf2d  lea     r8, [rbp+180h+var_1E0]
0x1400bcf31  mov     r13d, 1
0x1400bcf37  mov     edx, r13d
0x1400bcf3a  call    cs:MpManagerStatusQueryEx
0x1400bcf40  mov     esi, eax
0x1400bcf42  test    eax, eax
0x1400bcf44  jns     short loc_1400BCF65
0x1400bcf46  mov     rcx, cs:off_14018DE50
0x1400bcf4d  lea     rdx, off_14018DE50
0x1400bcf54  cmp     rcx, rdx
0x1400bcf57  jz      short loc_1400BCEFE
0x1400bcf59  test    [rcx+1Ch], r13b
0x1400bcf5d  jz      short loc_1400BCEFE
0x1400bcf5f  lea     edx, [r13+12h]
0x1400bcf63  jmp     short loc_1400BCEEB
0x1400bcf65  lea     r12, off_14018DE50
0x1400bcf6c  mov     dword ptr [rsp+280h+var_220], r15d
0x1400bcf71  lea     r14, qword_140163DB8
0x1400bcf78  test    [rbp+180h+var_1E0], r13b
0x1400bcf7c  jnz     short loc_1400BCFB8
0x1400bcf7e  mov     rcx, [rsp+280h+var_248]
0x1400bcf83  lea     rdx, [rsp+280h+var_220]
0x1400bcf88  call    cs:MpGetRunningMode
0x1400bcf8e  test    eax, eax
0x1400bcf90  jns     short loc_1400BCFFA
0x1400bcf92  mov     rsi, cs:off_14018DE50
0x1400bcf99  cmp     rsi, r12
0x1400bcf9c  jz      short loc_1400BCFBF
0x1400bcf9e  test    [rsi+1Ch], r13b
0x1400bcfa2  jz      short loc_1400BCFBF
0x1400bcfa4  mov     rcx, [rsi+10h]
0x1400bcfa8  mov     edx, 14h
0x1400bcfad  mov     r9d, eax
0x1400bcfb0  mov     r8, r14
0x1400bcfb3  call    sub_140081450
0x1400bcfb8  mov     rsi, cs:off_14018DE50
0x1400bcfbf  mov     ecx, 3
0x1400bcfc4  mov     dword ptr [rsp+280h+var_220], ecx
0x1400bcfc8  mov     [rsp+280h+Block], r15
0x1400bcfcd  test    ecx, ecx
0x1400bcfcf  jz      short loc_1400BD02B
0x1400bcfd1  sub     ecx, r13d
0x1400bcfd4  jz      short loc_1400BD022
0x1400bcfd6  sub     ecx, r13d
0x1400bcfd9  jz      short loc_1400BD019
0x1400bcfdb  sub     ecx, 2
0x1400bcfde  jz      short loc_1400BD010
0x1400bcfe0  cmp     ecx, r13d
0x1400bcfe3  lea     rdx, aS_0; "%s"
0x1400bcfea  lea     rcx, [rsp+280h+Block]
0x1400bcfef  jz      short loc_1400BD007
0x1400bcff1  lea     r8, aNotRunning; "Not running"
0x1400bcff8  jmp     short loc_1400BD03E
0x1400bcffa  mov     ecx, dword ptr [rsp+280h+var_220]
0x1400bcffe  mov     rsi, cs:off_14018DE50
0x1400bd005  jmp     short loc_1400BCFC8
0x1400bd007  lea     r8, aPassiveAuditMo; "Passive Audit Mode"
0x1400bd00e  jmp     short loc_1400BD03E
0x1400bd010  lea     r8, aEdrBlockMode; "EDR Block Mode"
0x1400bd017  jmp     short loc_1400BD032
0x1400bd019  lea     r8, aSxsPassiveMode; "SxS Passive Mode"
0x1400bd020  jmp     short loc_1400BD032
0x1400bd022  lea     r8, aPassiveMode; "Passive Mode"
0x1400bd029  jmp     short loc_1400BD032
0x1400bd02b  lea     r8, aNormal; "Normal"
0x1400bd032  lea     rcx, [rsp+280h+Block]
0x1400bd037  lea     rdx, aS_0; "%s"
0x1400bd03e  call    sub_140011860
0x1400bd043  mov     r15d, eax
0x1400bd046  xor     eax, eax
0x1400bd048  test    r15d, r15d
0x1400bd04b  jns     short loc_1400BD0BC
0x1400bd04d  cmp     rsi, r12
0x1400bd050  jz      short loc_1400BD06A
0x1400bd052  test    [rsi+1Ch], r13b
0x1400bd056  jz      short loc_1400BD06A
0x1400bd058  mov     rcx, [rsi+10h]
0x1400bd05c  lea     edx, [rax+15h]
0x1400bd05f  mov     r9d, r15d
0x1400bd062  mov     r8, r14
0x1400bd065  call    sub_140081450
0x1400bd06a  mov     rcx, [rsp+280h+Block]; Block
0x1400bd06f  test    rcx, rcx
0x1400bd072  jz      short loc_1400BD079
0x1400bd074  call    j_j_j__free_base
0x1400bd079  mov     rcx, [rsp+280h+var_248]
0x1400bd07e  test    rcx, rcx
0x1400bd081  jz      short loc_1400BD089
0x1400bd083  call    cs:__imp_MpHandleClose
0x1400bd089  mov     rcx, [rsp+280h+hObject]; hObject
0x1400bd08e  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1400bd092  jz      short loc_1400BD09A
0x1400bd094  call    cs:__imp_CloseHandle
0x1400bd09a  test    rdi, rdi
0x1400bd09d  jz      short loc_1400BD0A7
0x1400bd09f  mov     rcx, rdi; Block
0x1400bd0a2  call    j_j_j__free_base
0x1400bd0a7  test    rbx, rbx
0x1400bd0aa  jz      short loc_1400BD0B4
0x1400bd0ac  mov     rcx, rbx; Block
0x1400bd0af  call    j_j_j__free_base
0x1400bd0b4  mov     eax, r15d
0x1400bd0b7  jmp     loc_1400BDA18
0x1400bd0bc  mov     rsi, [rsp+280h+Block]
0x1400bd0c1  lea     rdx, aDefenderServic; "Defender service running mode: %ls\r\n"
0x1400bd0c8  mov     r8, rsi
0x1400bd0cb  mov     qword ptr [rsp+280h+var_218], rax
0x1400bd0d0  lea     rcx, [rsp+280h+var_218]
0x1400bd0d5  call    sub_140011860
0x1400bd0da  xor     r8d, r8d
0x1400bd0dd  mov     r15d, eax
0x1400bd0e0  test    eax, eax
0x1400bd0e2  jns     short loc_1400BD129
0x1400bd0e4  mov     rcx, cs:off_14018DE50
0x1400bd0eb  cmp     rcx, r12
0x1400bd0ee  jz      short loc_1400BD109
0x1400bd0f0  test    [rcx+1Ch], r13b
0x1400bd0f4  jz      short loc_1400BD109
0x1400bd0f6  mov     rcx, [rcx+10h]
0x1400bd0fa  lea     edx, [r8+16h]
0x1400bd0fe  mov     r8, r14
0x1400bd101  mov     r9d, eax
0x1400bd104  call    sub_140081450
0x1400bd109  mov     rcx, qword ptr [rsp+280h+var_218]; Block
0x1400bd10e  test    rcx, rcx
0x1400bd111  jz      short loc_1400BD118
0x1400bd113  call    j_j_j__free_base
0x1400bd118  test    rsi, rsi
0x1400bd11b  jz      loc_1400BD079
0x1400bd121  mov     rcx, rsi
0x1400bd124  jmp     loc_1400BD074
0x1400bd129  mov     r15, qword ptr [rsp+280h+var_218]
0x1400bd12e  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400bd132  inc     rcx
0x1400bd135  cmp     [r15+rcx*2], r8w
0x1400bd13a  jnz     short loc_1400BD132
0x1400bd13c  mov     eax, 2
0x1400bd141  mov     [rsp+280h+var_228], r8
0x1400bd146  mul     rcx
0x1400bd149  test    rdx, rdx
0x1400bd14c  jz      short loc_1400BD1B5
0x1400bd14e  mov     rcx, cs:off_14018DE50
0x1400bd155  cmp     rcx, r12
0x1400bd158  jz      short loc_1400BD177
0x1400bd15a  test    [rcx+1Ch], r13b
0x1400bd15e  jz      short loc_1400BD177
0x1400bd160  mov     rcx, [rcx+10h]
0x1400bd164  mov     edx, 17h
0x1400bd169  mov     r9d, 80070216h
0x1400bd16f  mov     r8, r14
0x1400bd172  call    sub_140081450
0x1400bd177  test    r15, r15
0x1400bd17a  jz      short loc_1400BD184
0x1400bd17c  mov     rcx, r15; Block
0x1400bd17f  call    j_j_j__free_base
0x1400bd184  test    rsi, rsi
0x1400bd187  jz      short loc_1400BD191
0x1400bd189  mov     rcx, rsi; Block
  ... truncated ...
```
