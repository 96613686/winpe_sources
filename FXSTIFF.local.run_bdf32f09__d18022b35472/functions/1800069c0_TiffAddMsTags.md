# TiffAddMsTags

- ea: `0x1800069c0`
- end: `0x180007cbb`
- name: `TiffAddMsTags`
- size: `4859`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, __int64, int)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops`

## callees

- `0x1800043d8`
- `0x1800069c0`
- `0x180008c80`
- `0x180009a7c`
- `0x180009aa4`
- `0x18000ea18`
- `0x18000eac0`
- `0x180017bce`
- `0x180017c00`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180006aaa`
- `KERNEL32!GetLastError` at `0x180006ba9`
- `KERNEL32!GetLastError` at `0x180006c1c`
- `KERNEL32!GetLastError` at `0x180006c6e`
- `KERNEL32!GetLastError` at `0x18000743f`
- `KERNEL32!GetLastError` at `0x1800074d1`
- `KERNEL32!GetLastError` at `0x180007563`
- `KERNEL32!GetLastError` at `0x180007699`
- `KERNEL32!GetLastError` at `0x18000772d`
- `KERNEL32!GetLastError` at `0x1800077b4`
- `KERNEL32!GetLastError` at `0x180007817`
- `KERNEL32!GetLastError` at `0x18000794a`
- `KERNEL32!GetLastError` at `0x180007994`
- `KERNEL32!GetLastError` at `0x180007a06`
- `KERNEL32!GetLastError` at `0x180007aa6`
- `KERNEL32!GetLastError` at `0x180007b1d`
- `KERNEL32!GetLastError` at `0x180007b82`
- `KERNEL32!GetLastError` at `0x180007be3`
- `KERNEL32!GetLastError` at `0x180007c38`
- `KERNEL32!GetLastError` at `0x180007c9e`
- `KERNEL32!GetLastError` at `0x180006aaa`
- `KERNEL32!GetLastError` at `0x180006ba9`
- `KERNEL32!GetLastError` at `0x180006c1c`
- `KERNEL32!GetLastError` at `0x180006c6e`
- `KERNEL32!GetLastError` at `0x18000743f`
- `KERNEL32!GetLastError` at `0x1800074d1`
- `KERNEL32!GetLastError` at `0x180007563`
- `KERNEL32!GetLastError` at `0x180007699`
- `KERNEL32!GetLastError` at `0x18000772d`
- `KERNEL32!GetLastError` at `0x1800077b4`
- `KERNEL32!GetLastError` at `0x180007817`
- `KERNEL32!GetLastError` at `0x18000794a`
- `KERNEL32!GetLastError` at `0x180007994`
- `KERNEL32!GetLastError` at `0x180007a06`
- `KERNEL32!GetLastError` at `0x180007aa6`
- `KERNEL32!GetLastError` at `0x180007b1d`
- `KERNEL32!GetLastError` at `0x180007b82`
- `KERNEL32!GetLastError` at `0x180007be3`
- `KERNEL32!GetLastError` at `0x180007c38`
- `KERNEL32!GetLastError` at `0x180007c9e`
- `KERNEL32!SetFilePointer` at `0x180006c34`
- `KERNEL32!SetFilePointer` at `0x1800073d5`
- `KERNEL32!SetFilePointer` at `0x18000746a`
- `KERNEL32!SetFilePointer` at `0x1800074fc`
- `KERNEL32!SetFilePointer` at `0x180007631`
- `KERNEL32!SetFilePointer` at `0x1800076c6`
- `KERNEL32!SetFilePointer` at `0x180007773`
- `KERNEL32!SetFilePointer` at `0x180007b48`
- `KERNEL32!SetFilePointer` at `0x180007bfe`
- `KERNEL32!SetFilePointer` at `0x180006c34`
- `KERNEL32!SetFilePointer` at `0x1800073d5`
- `KERNEL32!SetFilePointer` at `0x18000746a`
- `KERNEL32!SetFilePointer` at `0x1800074fc`
- `KERNEL32!SetFilePointer` at `0x180007631`
- `KERNEL32!SetFilePointer` at `0x1800076c6`
- `KERNEL32!SetFilePointer` at `0x180007773`
- `KERNEL32!SetFilePointer` at `0x180007b48`
- `KERNEL32!SetFilePointer` at `0x180007bfe`
- `KERNEL32!WriteFile` at `0x180007406`
- `KERNEL32!WriteFile` at `0x180007498`
- `KERNEL32!WriteFile` at `0x18000752a`
- `KERNEL32!WriteFile` at `0x180007660`
- `KERNEL32!WriteFile` at `0x1800076f4`
- `KERNEL32!WriteFile` at `0x1800077de`
- `KERNEL32!WriteFile` at `0x180007883`
- `KERNEL32!WriteFile` at `0x1800078de`
- `KERNEL32!WriteFile` at `0x1800079cd`
- `KERNEL32!WriteFile` at `0x180007a6d`
- `KERNEL32!WriteFile` at `0x180007ae4`
- `KERNEL32!WriteFile` at `0x180007baa`
- `KERNEL32!WriteFile` at `0x180007c65`
- `KERNEL32!WriteFile` at `0x180007406`
- `KERNEL32!WriteFile` at `0x180007498`
- `KERNEL32!WriteFile` at `0x18000752a`
- `KERNEL32!WriteFile` at `0x180007660`
- `KERNEL32!WriteFile` at `0x1800076f4`
- `KERNEL32!WriteFile` at `0x1800077de`
- `KERNEL32!WriteFile` at `0x180007883`
- `KERNEL32!WriteFile` at `0x1800078de`
- `KERNEL32!WriteFile` at `0x1800079cd`
- `KERNEL32!WriteFile` at `0x180007a6d`
- `KERNEL32!WriteFile` at `0x180007ae4`
- `KERNEL32!WriteFile` at `0x180007baa`
- `KERNEL32!WriteFile` at `0x180007c65`
- `KERNEL32!ReadFile` at `0x180006b7c`
- `KERNEL32!ReadFile` at `0x180006be3`
- `KERNEL32!ReadFile` at `0x180006b7c`
- `KERNEL32!ReadFile` at `0x180006be3`
- `KERNEL32!CloseHandle` at `0x180006b35`
- `KERNEL32!CloseHandle` at `0x180006b35`

## pseudocode

```c
__int64 __fastcall TiffAddMsTags(LPCWSTR lpFileName, __int64 a2, int a3)
{
  int v3; // r15d
  __int64 v7; // rbx
  DWORD LastError; // eax
  DWORD v10; // ebx
  char *v11; // rax
  HANDLE v12; // rdi
  char *v13; // r13
  void *v14; // r14
  __int64 v15; // rbx
  DWORD v16; // eax
  __int64 v17; // rdx
  const WCHAR *v18; // rdx
  unsigned int v19; // ebx
  const WCHAR *v20; // rdx
  const WCHAR *v21; // rdx
  const WCHAR *v22; // rdx
  const WCHAR *v23; // rdx
  const WCHAR *v24; // rdx
  const WCHAR *v25; // rdx
  const WCHAR *v26; // rdx
  const WCHAR *v27; // rdx
  const WCHAR *v28; // rdx
  const WCHAR *v29; // rdx
  const WCHAR *v30; // rdx
  const WCHAR *v31; // rdx
  const WCHAR *v32; // rdx
  const WCHAR *v33; // rdx
  const WCHAR *v34; // rdx
  const WCHAR *v35; // rdx
  const WCHAR *v36; // rdx
  const WCHAR *v37; // rdx
  const WCHAR *v38; // rdx
  const WCHAR *v39; // rdx
  const WCHAR *v40; // rdx
  const WCHAR *v41; // rdx
  const WCHAR *v42; // rdx
  const WCHAR *v43; // rdx
  const WCHAR *v44; // rdx
  const WCHAR *v45; // rdx
  const WCHAR *v46; // rdx
  const WCHAR *v47; // rdx
  const WCHAR *v48; // rdx
  const WCHAR *v49; // rdx
  const WCHAR *v50; // rdx
  const WCHAR *v51; // rdx
  const WCHAR *v52; // rdx
  const WCHAR *v53; // rdx
  const WCHAR *v54; // rdx
  const WCHAR *v55; // rdx
  __int64 v56; // rax
  __int64 v57; // rbx
  __int64 v58; // rcx
  __int64 v59; // r14
  __int64 v60; // rcx
  DWORD v61; // eax
  __int64 v62; // r14
  DWORD v63; // eax
  __int64 v64; // r14
  DWORD v65; // eax
  const WCHAR *v66; // rdx
  __int64 v67; // rax
  __int64 v68; // rbx
  __int64 v69; // rcx
  __int64 v70; // rcx
  __int64 v71; // rbx
  __int64 v72; // rcx
  __int64 v73; // rbx
  __int64 v74; // rcx
  __int64 v75; // rbx
  DWORD v76; // eax
  __int64 v77; // r14
  DWORD v78; // eax
  __int64 v79; // rbx
  __int64 v80; // rcx
  LONG v81; // r12d
  unsigned int v82; // ebx
  unsigned int v83; // esi
  unsigned int v84; // r14d
  char *v85; // r13
  _WORD *v86; // r12
  __int16 v87; // cx
  int v88; // eax
  unsigned int v89; // eax
  __int64 v90; // rbx
  DWORD v91; // eax
  __int64 v92; // rdx
  __int64 v93; // rbx
  DWORD v94; // eax
  __int64 v95; // rdx
  char *v96; // [rsp+30h] [rbp-D0h]
  _WORD v97[2]; // [rsp+38h] [rbp-C8h] BYREF
  DWORD NumberOfBytesRead; // [rsp+3Ch] [rbp-C4h] BYREF
  int v99; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v100; // [rsp+44h] [rbp-BCh]
  HANDLE hObject; // [rsp+48h] [rbp-B8h]
  int Buffer; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v103; // [rsp+58h] [rbp-A8h] BYREF
  _DWORD v104[160]; // [rsp+60h] [rbp-A0h] BYREF

  v3 = 0;
  hObject = 0;
  v100 = 0;
  v103 = 0;
  v97[0] = 0;
  NumberOfBytesRead = 0;
  Buffer = 0;
  memset_0(v104, 0, 0x27Cu);
  v99 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids);
  }
  if ( !(unsigned int)TiffOpenFile(lpFileName, v97) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      LastError = GetLastError();
      WPP_SF_d(v7, 36, &WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids, LastError);
    }
    return 0;
  }
  v100 = 0;
  v10 = 12 * v97[0];
  v11 = (char *)pMemAlloc(v10);
  v12 = hObject;
  v13 = v11;
  v96 = v11;
  if ( !v11 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids);
    }
    goto LABEL_16;
  }
  if ( !ReadFile(hObject, v11, v10, &NumberOfBytesRead, 0) )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_16;
    }
    v15 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v16 = GetLastError();
    v17 = 38;
    goto LABEL_23;
  }
  if ( !ReadFile(v12, &Buffer, 4u, &NumberOfBytesRead, 0) )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_16;
    }
    v15 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v16 = GetLastError();
    v17 = 39;
    goto LABEL_23;
  }
  if ( SetFilePointer(v12, 0, 0, 2u) == -1 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_16;
    }
    v15 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v16 = GetLastError();
    v17 = 40;
    goto LABEL_23;
  }
  v18 = *(const WCHAR **)(a2 + 40);
  v19 = 0;
  if ( v18 )
    v19 = AddStringTag(v12, v18) != 0;
  v20 = *(const WCHAR **)(a2 + 48);
  if ( v20 && (unsigned int)AddStringTag(v12, v20) )
    ++v19;
  v21 = *(const WCHAR **)(a2 + 96);
  if ( v21 && (unsigned int)AddStringTag(v12, v21) )
    ++v19;
  if ( !a3 )
  {
    v22 = *(const WCHAR **)(a2 + 24);
    if ( v22 && (unsigned int)AddStringTag(v12, v22) )
      ++v19;
    v23 = *(const WCHAR **)(a2 + 32);
    if ( v23 && (unsigned int)AddStringTag(v12, v23) )
      ++v19;
    goto LABEL_167;
  }
  if ( *(_QWORD *)a2 && (unsigned int)AddStringTag(v12, *(LPCWCH *)a2) )
    ++v19;
  v24 = *(const WCHAR **)(a2 + 8);
  if ( v24 && (unsigned int)AddStringTag(v12, v24) )
    ++v19;
  v25 = *(const WCHAR **)(a2 + 112);
  if ( v25 && (unsigned int)AddStringTag(v12, v25) )
    ++v19;
  v26 = *(const WCHAR **)(a2 + 120);
  if ( v26 && (unsigned int)AddStringTag(v12, v26) )
    ++v19;
  v27 = *(const WCHAR **)(a2 + 128);
  if ( v27 && (unsigned int)AddStringTag(v12, v27) )
    ++v19;
  v28 = *(const WCHAR **)(a2 + 136);
  if ( v28 && (unsigned int)AddStringTag(v12, v28) )
    ++v19;
  v29 = *(const WCHAR **)(a2 + 144);
  if ( v29 && (unsigned int)AddStringTag(v12, v29) )
    ++v19;
  v30 = *(const WCHAR **)(a2 + 152);
  if ( v30 && (unsigned int)AddStringTag(v12, v30) )
    ++v19;
  v31 = *(const WCHAR **)(a2 + 160);
  if ( v31 && (unsigned int)AddStringTag(v12, v31) )
    ++v19;
  v32 = *(const WCHAR **)(a2 + 168);
  if ( v32 && (unsigned int)AddStringTag(v12, v32) )
    ++v19;
  v33 = *(const WCHAR **)(a2 + 176);
  if ( v33 && (unsigned int)AddStringTag(v12, v33) )
    ++v19;
  v34 = *(const WCHAR **)(a2 + 184);
  if ( v34 && (unsigned int)AddStringTag(v12, v34) )
    ++v19;
  v35 = *(const WCHAR **)(a2 + 192);
  if ( v35 && (unsigned int)AddStringTag(v12, v35) )
    ++v19;
  v36 = *(const WCHAR **)(a2 + 200);
  if ( v36 && (unsigned int)AddStringTag(v12, v36) )
    ++v19;
  v37 = *(const WCHAR **)(a2 + 16);
  if ( v37 && (unsigned int)AddStringTag(v12, v37) )
    ++v19;
  v38 = *(const WCHAR **)(a2 + 208);
  if ( v38 && (unsigned int)AddStringTag(v12, v38) )
    ++v19;
  v39 = *(const WCHAR **)(a2 + 216);
  if ( v39 && (unsigned int)AddStringTag(v12, v39) )
    ++v19;
  v40 = *(const WCHAR **)(a2 + 224);
  if ( v40 && (unsigned int)AddStringTag(v12, v40) )
    ++v19;
  v41 = *(const WCHAR **)(a2 + 232);
  if ( v41 && (unsigned int)AddStringTag(v12, v41) )
    ++v19;
  v42 = *(const WCHAR **)(a2 + 240);
  if ( v42 && (unsigned int)AddStringTag(v12, v42) )
    ++v19;
  v43 = *(const WCHAR **)(a2 + 248);
  if ( v43 && (unsigned int)AddStringTag(v12, v43) )
    ++v19;
  v44 = *(const WCHAR **)(a2 + 256);
  if ( v44 && (unsigned int)AddStringTag(v12, v44) )
    ++v19;
  v45 = *(const WCHAR **)(a2 + 264);
  if ( v45 && (unsigned int)AddStringTag(v12, v45) )
    ++v19;
  v46 = *(const WCHAR **)(a2 + 272);
  if ( v46 && (unsigned int)AddStringTag(v12, v46) )
    ++v19;
  v47 = *(const WCHAR **)(a2 + 280);
  if ( v47 && (unsigned int)AddStringTag(v12, v47) )
    ++v19;
  v48 = *(const WCHAR **)(a2 + 288);
  if ( v48 && (unsigned int)AddStringTag(v12, v48) )
    ++v19;
  v49 = *(const WCHAR **)(a2 + 296);
  if ( v49 && (unsigned int)AddStringTag(v12, v49) )
    ++v19;
  v50 = *(const WCHAR **)(a2 + 304);
  if ( v50 && (unsigned int)AddStringTag(v12, v50) )
    ++v19;
  v51 = *(const WCHAR **)(a2 + 312);
  if ( v51 && (unsigned int)AddStringTag(v12, v51) )
    ++v19;
  v52 = *(const WCHAR **)(a2 + 336);
  if ( v52 && (unsigned int)AddStringTag(v12, v52) )
    ++v19;
  v53 = *(const WCHAR **)(a2 + 344);
  if ( v53 && (unsigned int)AddStringTag(v12, v53) )
    ++v19;
  v54 = *(const WCHAR **)(a2 + 320);
  if ( v54 && (unsigned int)AddStringTag(v12, v54) )
    ++v19;
  v55 = *(const WCHAR **)(a2 + 328);
  if ( v55 && (unsigned int)AddStringTag(v12, v55) )
    ++v19;
  v56 = v19;
  v57 = v19 + 1;
  v58 = 3 * v56;
  v104[v58 + 2] = *(_DWORD *)(a2 + 108);
  v59 = (unsigned int)(v57 + 1);
  LODWORD(v56) = *(_DWORD *)(a2 + 352);
  v104[v58] = 302185;
  v104[v58 + 1] = 1;
  v60 = 3 * v57;
  v104[v60] = 302186;
  v104[v60 + 2] = v56;
  v104[v60 + 1] = 1;
  v61 = SetFilePointer(v12, 0, 0, 1u);
  v104[3 * v59 + 2] = v61;
  if ( v61 == -1 )
    goto LABEL_16;
  if ( !WriteFile(v12, (LPCVOID)(a2 + 376), 8u, &NumberOfBytesRead, 0) )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_16;
    }
    v15 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v16 = GetLastError();
    v17 = 41;
    goto LABEL_23;
  }
  v104[3 * v59] = 695403;
  v104[3 * v59 + 1] = 1;
  v62 = (unsigned int)(v57 + 2);
  v63 = SetFilePointer(v12, 0, 0, 1u);
  v104[3 * (unsigned int)v62 + 2] = v63;
  if ( v63 == -1 )
    goto LABEL_16;
  if ( !WriteFile(v12, (LPCVOID)(a2 + 72), 8u, &NumberOfBytesRead, 0) )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_16;
    }
    v15 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v16 = GetLastError();
    v17 = 42;
    goto LABEL_23;
  }
  v104[3 * v62] = 695404;
  v104[3 * v62 + 1] = 1;
  v64 = (unsigned int)(v57 + 3);
  v65 = SetFilePointer(v12, 0, 0, 1u);
  v104[3 * (unsigned int)v64 + 2] = v65;
  if ( v65 == -1 )
    goto LABEL_16;
  if ( !WriteFile(v12, (LPCVOID)(a2 + 80), 8u, &NumberOfBytesRead, 0) )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_16;
    }
    v15 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v16 = GetLastError();
    v17 = 43;
LABEL_23:
    WPP_SF_d(v15, v17, &WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids, v16);
LABEL_16:
    v14 = v13;
    goto LABEL_17;
  }
  v104[3 * v64] = 695405;
  v104[3 * v64 + 1] = 1;
  v19 = v57 + 4;
LABEL_167:
  v66 = *(const WCHAR **)(a2 + 368);
  v67 = v19;
  v68 = v19 + 1;
  v69 = 3 * v67;
  v104[v69 + 2] = *(_DWORD *)(a2 + 104);
  LODWORD(v67) = *(_DWORD *)(a2 + 88);
  v104[v69] = 302190;
  v104[v69 + 1] = 1;
  v70 = 3 * v68;
  v104[v70 + 2] = v67;
  v71 = (unsigned int)(v68 + 1);
  LODWORD(v67) = *(_DWORD *)(a2 + 356);
  v104[v70] = 302191;
  v104[v70 + 1] = 1;
  v72 = 3 * v71;
  v73 = (unsigned int)(v71 + 1);
  v104[v72 + 2] = v67;
  LODWORD(v67) = *(_DWORD *)(a2 + 360);
  v104[v72] = 302192;
  v104[v72 + 1] = 1;
  v74 = 3 * v73;
  v75 = (unsigned int)(v73 + 1);
  v104[v74] = 302193;
  v104[v74 + 2] = v67;
  v104[v74 + 1] = 1;
  if ( v66 && (unsigned int)AddStringTag(v12, v66) )
    v75 = (unsigned int)(v75 + 1);
  v76 = SetFilePointer(v12, 0, 0, 1u);
  v104[3 * v75 + 2] = v76;
  if ( v76 == -1 )
    goto LABEL_16;
  if ( !WriteFile(v12, (LPCVOID)(a2 + 56), 8u, &NumberOfBytesRead, 0) )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_16;
    }
    v15 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v16 = GetLastError();
    v17 = 44;
    goto LABEL_23;
  }
  v104[3 * v75] = 695411;
  v104[3 * v75 + 1] = 1;
  v77 = (unsigned int)(v75 + 1);
  v78 = SetFilePointer(v12, 0, 0, 1u);
  v104[3 * v77 + 2] = v78;
  if ( v78 == -1 )
    goto LABEL_16;
  if ( !WriteFile(v12, (LPCVOID)(a2 + 64), 8u, &NumberOfBytesRead, 0) )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_16;
    }
    v15 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v16 = GetLastError();
    v17 = 45;
    goto LABEL_23;
  }
  v104[3 * v77] = 695412;
  v104[3 * v77 + 1] = 1;
  v79 = (unsigned int)(v75 + 2);
  v80 = 3 * v79;
  v104[v80] = 302197;
  v104[v80 + 2] = 2;
  v104[v80 + 1] = 1;
  LODWORD(hObject) = SetFilePointer(v12, 0, 0, 1u);
  v81 = (int)hObject;
  if ( (_DWORD)hObject == -1 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_16;
    }
    v15 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v16 = GetLastError();
    v17 = 46;
    goto LABEL_23;
  }
  v82 = v79 + 1;
  v97[0] += v82;
  if ( !WriteFile(v12, v97, 2u, &NumberOfBytesRead, 0) )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_16;
    }
    v15 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v16 = GetLastError();
    v17 = 47;
    goto LABEL_23;
  }
  v99 = 0;
  v83 = 0;
  v84 = 0;
  if ( !v97[0] )
  {
    v14 = v13;
    goto LABEL_233;
  }
  while ( 1 )
  {
    v85 = &v13[12 * v83];
    v86 = &v104[3 * v84];
    if ( *(_WORD *)v85 < *v86 )
    {
      if ( (unsigned __int16)(*(_WORD *)v85 + 25535) > 0x34u )
      {
        if ( !WriteFile(v12, v85, 0xCu, &NumberOfBytesRead, 0) )
        {
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_213;
          }
          v90 = *((_QWORD *)WPP_GLOBAL_Control + 2);
          v91 = GetLastError();
          v92 = 49;
          goto LABEL_212;
        }
        ++v99;
      }
      ++v83;
    }
    else
    {
      if ( !WriteFile(v12, &v104[3 * v84], 0xCu, &NumberOfBytesRead, 0) )
      {
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_213;
        }
        v90 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v91 = GetLastError();
        v92 = 48;
        goto LABEL_212;
      }
      v87 = *(_WORD *)v85;
      v88 = v3 + 1;
      ++v99;
      ++v84;
      if ( v87 != *v86 )
        v88 = v3;
      v3 = v88;
      v89 = v83 + 1;
      if ( v87 != *v86 )
        v89 = v83;
      v83 = v89;
    }
    if ( v83 >= v97[0] - v82 )
    {
      if ( WriteFile(v12, &v104[3 * v84], 12 * (v82 - v84), &NumberOfBytesRead, 0) )
      {
        v99 += v82 - v84;
LABEL_231:
        v81 = (int)hObject;
        v14 = v96;
        goto LABEL_233;
      }
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_213:
        v14 = v96;
        goto LABEL_17;
      }
      v90 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v91 = GetLastError();
      v92 = 50;
LABEL_212:
      WPP_SF_d(v90, v92, &WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids, v91);
      goto LABEL_213;
    }
    if ( v84 >= v82 )
      break;
    if ( ++v3 >= (unsigned int)v97[0] )
      goto LABEL_231;
    v13 = v96;
  }
  v14 = v96;
  if ( !WriteFile(v12, &v96[12 * v83], 12 * (v97[0] - v83 - v82), &NumberOfBytesRead, 0) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v93 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v94 = GetLastError();
      v95 = 51;
      goto LABEL_223;
    }
    goto LABEL_17;
  }
  v81 = (int)hObject;
  v99 += v97[0] - v83 - v82;
LABEL_233:
  if ( !WriteFile(v12, &Buffer, 4u, &NumberOfBytesRead, 0) )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_17;
    }
    v93 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v94 = GetLastError();
    v95 = 52;
    goto LABEL_223;
  }
  if ( v99 != v97[0] )
  {
    if ( SetFilePointer(v12, v81, 0, 0) == -1 )
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_17;
      }
      v93 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v94 = GetLastError();
      v95 = 53;
      goto LABEL_223;
    }
    if ( !WriteFile(v12, &v99, 2u, &NumberOfBytesRead, 0) )
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_17;
      }
      v93 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v94 = GetLastError();
      v95 = 54;
      goto LABEL_223;
    }
  }
  if ( SetFilePointer(v12, 0, 0, 0) == -1 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_17;
    }
    v93 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v94 = GetLastError();
    v95 = 55;
LABEL_223:
    WPP_SF_d(v93, v95, &WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids, v94);
    goto LABEL_17;
  }
  HIDWORD(v103) = v81;
  if ( WriteFile(v12, &v103, 8u, &NumberOfBytesRead, 0) )
  {
    v100 = 1;
    goto LABEL_17;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v93 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v94 = GetLastError();
    v95 = 56;
    goto LABEL_223;
  }
LABEL_17:
  pMemFree(v14);
  CloseHandle(v12);
  return v100;
}

```

## disassembly

```asm
0x1800069c0  mov     [rsp-8+arg_10], rbx
0x1800069c5  push    rbp
0x1800069c6  push    rsi
0x1800069c7  push    rdi
0x1800069c8  push    r12
0x1800069ca  push    r13
0x1800069cc  push    r14
0x1800069ce  push    r15
0x1800069d0  lea     rbp, [rsp-1F0h]
0x1800069d8  sub     rsp, 2F0h
0x1800069df  mov     rax, cs:__security_cookie
0x1800069e6  xor     rax, rsp
0x1800069e9  mov     [rbp+220h+var_40], rax
0x1800069f0  xor     r15d, r15d
0x1800069f3  mov     r14d, r8d
0x1800069f6  mov     rsi, rdx
0x1800069f9  mov     [rsp+320h+hObject], r15
0x1800069fe  mov     rbx, rcx
0x180006a01  mov     [rsp+320h+var_2DC], r15d
0x180006a06  xor     edx, edx; Val
0x180006a08  mov     [rsp+320h+var_2C8], r15
0x180006a0d  mov     r8d, 27Ch; Size
0x180006a13  mov     [rsp+320h+var_2E8], r15w
0x180006a19  lea     rcx, [rsp+320h+var_2C0]; void *
0x180006a1e  mov     [rsp+320h+NumberOfBytesRead], r15d
0x180006a23  mov     [rsp+320h+Buffer], r15d
0x180006a28  call    memset_0
0x180006a2d  mov     [rsp+320h+var_2E0], r15d
0x180006a32  mov     rcx, cs:WPP_GLOBAL_Control
0x180006a39  lea     rdi, WPP_GLOBAL_Control
0x180006a40  lea     r12d, [r15+2]
0x180006a44  cmp     rcx, rdi
0x180006a47  jz      short loc_180006A69
0x180006a49  test    [rcx+1Ch], r12b
0x180006a4d  jz      short loc_180006A69
0x180006a4f  cmp     byte ptr [rcx+19h], 5
0x180006a53  jb      short loc_180006A69
0x180006a55  mov     rcx, [rcx+10h]
0x180006a59  lea     edx, [r15+23h]
0x180006a5d  lea     r8, WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids
0x180006a64  call    WPP_SF_
0x180006a69  lea     rax, [rsp+320h+var_2E8]
0x180006a6e  mov     rcx, rbx; lpFileName
0x180006a71  lea     r9, [rsp+320h+var_2C8]
0x180006a76  mov     [rsp+320h+lpOverlapped], rax; lpBuffer
0x180006a7b  lea     r8, [rsp+320h+var_2DC]
0x180006a80  lea     rdx, [rsp+320h+hObject]
0x180006a85  call    TiffOpenFile
0x180006a8a  test    eax, eax
0x180006a8c  jnz     short loc_180006ACB
0x180006a8e  mov     rbx, cs:WPP_GLOBAL_Control
0x180006a95  cmp     rbx, rdi
0x180006a98  jz      short loc_180006AC7
0x180006a9a  test    [rbx+1Ch], r12b
0x180006a9e  jz      short loc_180006AC7
0x180006aa0  cmp     [rbx+19h], r12b
0x180006aa4  jb      short loc_180006AC7
0x180006aa6  mov     rbx, [rbx+10h]
0x180006aaa  call    cs:__imp_GetLastError
0x180006ab0  mov     edx, 24h ; '$'
0x180006ab5  lea     r8, WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids
0x180006abc  mov     r9d, eax
0x180006abf  mov     rcx, rbx
0x180006ac2  call    WPP_SF_d
0x180006ac7  xor     eax, eax
0x180006ac9  jmp     short loc_180006B3F
0x180006acb  movzx   eax, [rsp+320h+var_2E8]
0x180006ad0  mov     [rsp+320h+var_2DC], r15d
0x180006ad5  lea     ecx, [rax+rax*2]
0x180006ad8  shl     ecx, 2; dwBytes
0x180006adb  mov     ebx, ecx
0x180006add  call    pMemAlloc
0x180006ae2  mov     rdi, [rsp+320h+hObject]
0x180006ae7  mov     r13, rax
0x180006aea  mov     [rsp+320h+var_2F0], rax
0x180006aef  test    rax, rax
0x180006af2  jnz     short loc_180006B69
0x180006af4  mov     rcx, cs:WPP_GLOBAL_Control
0x180006afb  lea     rax, WPP_GLOBAL_Control
0x180006b02  cmp     rcx, rax
0x180006b05  jz      short loc_180006B27
0x180006b07  test    [rcx+1Ch], r12b
0x180006b0b  jz      short loc_180006B27
0x180006b0d  cmp     [rcx+19h], r12b
0x180006b11  jb      short loc_180006B27
0x180006b13  mov     rcx, [rcx+10h]
0x180006b17  lea     edx, [r13+25h]
0x180006b1b  lea     r8, WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids
0x180006b22  call    WPP_SF_
0x180006b27  mov     r14, r13
0x180006b2a  mov     rcx, r14; lpMem
0x180006b2d  call    pMemFree
0x180006b32  mov     rcx, rdi; hObject
0x180006b35  call    cs:__imp_CloseHandle
0x180006b3b  mov     eax, [rsp+320h+var_2DC]
0x180006b3f  mov     rcx, [rbp+220h+var_40]
0x180006b46  xor     rcx, rsp; StackCookie
0x180006b49  call    __security_check_cookie
0x180006b4e  mov     rbx, [rsp+320h+arg_10]
0x180006b56  add     rsp, 2F0h
0x180006b5d  pop     r15
0x180006b5f  pop     r14
0x180006b61  pop     r13
0x180006b63  pop     r12
0x180006b65  pop     rdi
0x180006b66  pop     rsi
0x180006b67  pop     rbp
0x180006b68  retn
0x180006b69  lea     r9, [rsp+320h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180006b6e  mov     [rsp+320h+lpOverlapped], r15; lpOverlapped
0x180006b73  mov     r8d, ebx; nNumberOfBytesToRead
0x180006b76  mov     rdx, rax; lpBuffer
0x180006b79  mov     rcx, rdi; hFile
0x180006b7c  call    cs:__imp_ReadFile
0x180006b82  test    eax, eax
0x180006b84  jnz     short loc_180006BCB
0x180006b86  mov     rbx, cs:WPP_GLOBAL_Control
0x180006b8d  lea     rax, WPP_GLOBAL_Control
0x180006b94  cmp     rbx, rax
0x180006b97  jz      short loc_180006B27
0x180006b99  test    [rbx+1Ch], r12b
0x180006b9d  jz      short loc_180006B27
0x180006b9f  cmp     [rbx+19h], r12b
0x180006ba3  jb      short loc_180006B27
0x180006ba5  mov     rbx, [rbx+10h]
0x180006ba9  call    cs:__imp_GetLastError
0x180006baf  mov     edx, 26h ; '&'
0x180006bb4  mov     r9d, eax
0x180006bb7  lea     r8, WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids
0x180006bbe  mov     rcx, rbx
0x180006bc1  call    WPP_SF_d
0x180006bc6  jmp     loc_180006B27
0x180006bcb  lea     r9, [rsp+320h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180006bd0  mov     [rsp+320h+lpOverlapped], r15; lpOverlapped
0x180006bd5  mov     r8d, 4; nNumberOfBytesToRead
0x180006bdb  lea     rdx, [rsp+320h+Buffer]; lpBuffer
0x180006be0  mov     rcx, rdi; hFile
0x180006be3  call    cs:__imp_ReadFile
0x180006be9  test    eax, eax
0x180006beb  jnz     short loc_180006C29
0x180006bed  mov     rbx, cs:WPP_GLOBAL_Control
0x180006bf4  lea     rax, WPP_GLOBAL_Control
0x180006bfb  cmp     rbx, rax
0x180006bfe  jz      loc_180006B27
0x180006c04  test    [rbx+1Ch], r12b
0x180006c08  jz      loc_180006B27
0x180006c0e  cmp     [rbx+19h], r12b
0x180006c12  jb      loc_180006B27
0x180006c18  mov     rbx, [rbx+10h]
0x180006c1c  call    cs:__imp_GetLastError
0x180006c22  mov     edx, 27h ; '''
0x180006c27  jmp     short loc_180006BB4
0x180006c29  mov     r9d, r12d; dwMoveMethod
0x180006c2c  xor     r8d, r8d; lpDistanceToMoveHigh
0x180006c2f  xor     edx, edx; lDistanceToMove
0x180006c31  mov     rcx, rdi; hFile
0x180006c34  call    cs:__imp_SetFilePointer
0x180006c3a  cmp     eax, 0FFFFFFFFh
0x180006c3d  jnz     short loc_180006C7E
0x180006c3f  mov     rbx, cs:WPP_GLOBAL_Control
0x180006c46  lea     rax, WPP_GLOBAL_Control
0x180006c4d  cmp     rbx, rax
0x180006c50  jz      loc_180006B27
0x180006c56  test    [rbx+1Ch], r12b
0x180006c5a  jz      loc_180006B27
0x180006c60  cmp     [rbx+19h], r12b
0x180006c64  jb      loc_180006B27
0x180006c6a  mov     rbx, [rbx+10h]
0x180006c6e  call    cs:__imp_GetLastError
0x180006c74  mov     edx, 28h ; '('
0x180006c79  jmp     loc_180006BB4
0x180006c7e  mov     rdx, [rsi+28h]; lpWideCharStr
0x180006c82  mov     ebx, r15d
0x180006c85  mov     r12d, 1
0x180006c8b  test    rdx, rdx
0x180006c8e  jz      short loc_180006CA8
0x180006c90  lea     r9, [rsp+320h+var_2C0]
0x180006c95  mov     r8w, 9C41h
0x180006c9a  mov     rcx, rdi; hFile
0x180006c9d  call    AddStringTag
0x180006ca2  test    eax, eax
0x180006ca4  cmovnz  ebx, r12d
0x180006ca8  mov     rdx, [rsi+30h]; lpWideCharStr
0x180006cac  test    rdx, rdx
0x180006caf  jz      short loc_180006CD5
0x180006cb1  mov     eax, ebx
0x180006cb3  lea     r9, [rsp+320h+var_2C0]
0x180006cb8  mov     r8d, 9C42h
0x180006cbe  lea     rcx, [rax+rax*2]
0x180006cc2  lea     r9, [r9+rcx*4]
0x180006cc6  mov     rcx, rdi; hFile
0x180006cc9  call    AddStringTag
0x180006cce  test    eax, eax
0x180006cd0  jz      short loc_180006CD5
0x180006cd2  add     ebx, r12d
0x180006cd5  mov     rdx, [rsi+60h]; lpWideCharStr
0x180006cd9  test    rdx, rdx
0x180006cdc  jz      short loc_180006D02
0x180006cde  mov     eax, ebx
0x180006ce0  lea     r9, [rsp+320h+var_2C0]
0x180006ce5  mov     r8d, 9C43h
0x180006ceb  lea     rcx, [rax+rax*2]
0x180006cef  lea     r9, [r9+rcx*4]
0x180006cf3  mov     rcx, rdi; hFile
0x180006cf6  call    AddStringTag
0x180006cfb  test    eax, eax
0x180006cfd  jz      short loc_180006D02
0x180006cff  add     ebx, r12d
0x180006d02  test    r14d, r14d
0x180006d05  jnz     short loc_180006D6E
0x180006d07  mov     rdx, [rsi+18h]; lpWideCharStr
0x180006d0b  test    rdx, rdx
0x180006d0e  jz      short loc_180006D34
0x180006d10  mov     eax, ebx
0x180006d12  lea     r9, [rsp+320h+var_2C0]
0x180006d17  mov     r8d, 9C44h
0x180006d1d  lea     rcx, [rax+rax*2]
0x180006d21  lea     r9, [r9+rcx*4]
0x180006d25  mov     rcx, rdi; hFile
0x180006d28  call    AddStringTag
0x180006d2d  test    eax, eax
0x180006d2f  jz      short loc_180006D34
0x180006d31  add     ebx, r12d
0x180006d34  mov     rdx, [rsi+20h]; lpWideCharStr
0x180006d38  test    rdx, rdx
0x180006d3b  jz      loc_180007584
0x180006d41  mov     eax, ebx
0x180006d43  lea     r9, [rsp+320h+var_2C0]
0x180006d48  mov     r8d, 9C45h
0x180006d4e  lea     rcx, [rax+rax*2]
0x180006d52  lea     r9, [r9+rcx*4]
0x180006d56  mov     rcx, rdi; hFile
0x180006d59  call    AddStringTag
0x180006d5e  test    eax, eax
0x180006d60  jz      loc_180007584
0x180006d66  add     ebx, r12d
0x180006d69  jmp     loc_180007584
0x180006d6e  mov     rdx, [rsi]; lpWideCharStr
0x180006d71  test    rdx, rdx
0x180006d74  jz      short loc_180006D9A
0x180006d76  mov     eax, ebx
0x180006d78  lea     r9, [rsp+320h+var_2C0]
0x180006d7d  mov     r8d, 9C46h
0x180006d83  lea     rcx, [rax+rax*2]
0x180006d87  lea     r9, [r9+rcx*4]
0x180006d8b  mov     rcx, rdi; hFile
0x180006d8e  call    AddStringTag
0x180006d93  test    eax, eax
0x180006d95  jz      short loc_180006D9A
0x180006d97  add     ebx, r12d
0x180006d9a  mov     rdx, [rsi+8]; lpWideCharStr
0x180006d9e  test    rdx, rdx
0x180006da1  jz      short loc_180006DC7
0x180006da3  mov     eax, ebx
0x180006da5  lea     r9, [rsp+320h+var_2C0]
0x180006daa  mov     r8d, 9C47h
0x180006db0  lea     rcx, [rax+rax*2]
0x180006db4  lea     r9, [r9+rcx*4]
0x180006db8  mov     rcx, rdi; hFile
0x180006dbb  call    AddStringTag
0x180006dc0  test    eax, eax
0x180006dc2  jz      short loc_180006DC7
0x180006dc4  add     ebx, r12d
0x180006dc7  mov     rdx, [rsi+70h]; lpWideCharStr
0x180006dcb  test    rdx, rdx
0x180006dce  jz      short loc_180006DF4
0x180006dd0  mov     eax, ebx
0x180006dd2  lea     r9, [rsp+320h+var_2C0]
0x180006dd7  mov     r8d, 9C48h
0x180006ddd  lea     rcx, [rax+rax*2]
0x180006de1  lea     r9, [r9+rcx*4]
0x180006de5  mov     rcx, rdi; hFile
0x180006de8  call    AddStringTag
0x180006ded  test    eax, eax
0x180006def  jz      short loc_180006DF4
0x180006df1  add     ebx, r12d
0x180006df4  mov     rdx, [rsi+78h]; lpWideCharStr
0x180006df8  test    rdx, rdx
0x180006dfb  jz      short loc_180006E21
0x180006dfd  mov     eax, ebx
0x180006dff  lea     r9, [rsp+320h+var_2C0]
0x180006e04  mov     r8d, 9C49h
0x180006e0a  lea     rcx, [rax+rax*2]
0x180006e0e  lea     r9, [r9+rcx*4]
0x180006e12  mov     rcx, rdi; hFile
0x180006e15  call    AddStringTag
0x180006e1a  test    eax, eax
0x180006e1c  jz      short loc_180006E21
0x180006e1e  add     ebx, r12d
0x180006e21  mov     rdx, [rsi+80h]; lpWideCharStr
0x180006e28  test    rdx, rdx
0x180006e2b  jz      short loc_180006E51
0x180006e2d  mov     eax, ebx
0x180006e2f  lea     r9, [rsp+320h+var_2C0]
0x180006e34  mov     r8d, 9C4Ah
0x180006e3a  lea     rcx, [rax+rax*2]
0x180006e3e  lea     r9, [r9+rcx*4]
0x180006e42  mov     rcx, rdi; hFile
0x180006e45  call    AddStringTag
0x180006e4a  test    eax, eax
  ... truncated ...
```
