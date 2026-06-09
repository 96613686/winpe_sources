# NtfsFindPrefixHashEntry

- ea: `0x14018b100`
- end: `0x14018be83`
- name: `NtfsFindPrefixHashEntry`
- size: `3459`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x14019f350`

## callees

- `0x14000549c`
- `0x14000c290`
- `0x14000cb80`
- `0x140012e70`
- `0x140021b10`
- `0x14003fe78`
- `0x140040180`
- `0x140059440`
- `0x140059c60`
- `0x14018b100`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14018b1cf`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14018b27e`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14018b720`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14018b78d`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14018bc47`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14018bd47`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1402ab117`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14018b1cf`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14018b27e`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14018b720`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14018b78d`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14018bc47`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14018bd47`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1402ab117`
- `ntoskrnl!FsRtlAreNamesEqual` at `0x14018b992`
- `ntoskrnl!FsRtlAreNamesEqual` at `0x14018b9fa`
- `ntoskrnl!FsRtlAreNamesEqual` at `0x14018baf0`
- `ntoskrnl!FsRtlAreNamesEqual` at `0x14018bb56`
- `ntoskrnl!FsRtlAreNamesEqual` at `0x14018b992`
- `ntoskrnl!FsRtlAreNamesEqual` at `0x14018b9fa`
- `ntoskrnl!FsRtlAreNamesEqual` at `0x14018baf0`
- `ntoskrnl!FsRtlAreNamesEqual` at `0x14018bb56`
- `ntoskrnl!ExReleasePushLockEx` at `0x14018b4d7`
- `ntoskrnl!ExReleasePushLockEx` at `0x14018b4e9`
- `ntoskrnl!ExReleasePushLockEx` at `0x14018b578`
- `ntoskrnl!ExReleasePushLockEx` at `0x14018b5c0`
- `ntoskrnl!ExReleasePushLockEx` at `0x14018b633`
- `ntoskrnl!ExReleasePushLockEx` at `0x14018b68e`
- `ntoskrnl!ExReleasePushLockEx` at `0x14018b8ff`
- `ntoskrnl!ExReleasePushLockEx` at `0x14018bc74`
- `ntoskrnl!ExReleasePushLockEx` at `0x14018bcca`
- `ntoskrnl!ExReleasePushLockEx` at `0x14018bcdc`
- `ntoskrnl!ExReleasePushLockEx` at `0x14018bd64`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402ab13c`
- `ntoskrnl!ExReleasePushLockEx` at `0x14018b4d7`
- `ntoskrnl!ExReleasePushLockEx` at `0x14018b4e9`
- `ntoskrnl!ExReleasePushLockEx` at `0x14018b578`
- `ntoskrnl!ExReleasePushLockEx` at `0x14018b5c0`
- `ntoskrnl!ExReleasePushLockEx` at `0x14018b633`
- `ntoskrnl!ExReleasePushLockEx` at `0x14018b68e`
- `ntoskrnl!ExReleasePushLockEx` at `0x14018b8ff`
- `ntoskrnl!ExReleasePushLockEx` at `0x14018bc74`
- `ntoskrnl!ExReleasePushLockEx` at `0x14018bcca`
- `ntoskrnl!ExReleasePushLockEx` at `0x14018bcdc`
- `ntoskrnl!ExReleasePushLockEx` at `0x14018bd64`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402ab13c`

## pseudocode

```c
__int64 __fastcall NtfsFindPrefixHashEntry(
        __int64 a1,
        _DWORD *a2,
        __int64 a3,
        char a4,
        __int64 a5,
        unsigned __int16 *a6)
{
  __int64 v6; // rdi
  __int64 v9; // r10
  __int64 *v10; // r12
  UNICODE_STRING *v11; // r14
  int v12; // edx
  unsigned __int16 *Buffer; // r9
  unsigned __int16 *v15; // r8
  int v16; // ecx
  int v17; // eax
  int v18; // eax
  __int64 i; // rbx
  int v20; // eax
  unsigned int v21; // edx
  int v22; // ecx
  unsigned int v23; // edx
  unsigned int v24; // ebx
  __int64 v25; // rax
  USHORT v26; // r15
  UNICODE_STRING *v27; // rdx
  USHORT v28; // cx
  __int64 v29; // rdx
  WCHAR *v30; // rdx
  unsigned __int16 v31; // cx
  _QWORD *v32; // r9
  __int64 v33; // rax
  int v34; // r15d
  __int64 v35; // rdi
  int v36; // ebx
  int Length; // ecx
  __int64 v38; // r12
  unsigned int v39; // edi
  __int64 v40; // rbx
  __int64 v41; // rcx
  __int64 v43; // rcx
  __int64 v44; // r10
  unsigned __int16 v45; // cx
  PWSTR v46; // r8
  WCHAR *j; // rdx
  bool v48; // zf
  unsigned __int16 *v49; // rcx
  int v50; // r11d
  unsigned __int64 v51; // r9
  int v52; // edx
  int v53; // r8d
  int v54; // eax
  unsigned int v55; // edx
  __int64 k; // rbx
  int v57; // edx
  unsigned int v58; // ecx
  unsigned int v59; // ebx
  __int64 v60; // r12
  __int64 v61; // rax
  USHORT v62; // r15
  UNICODE_STRING *v63; // rdx
  USHORT v64; // cx
  __int64 v65; // rdx
  WCHAR *v66; // rdx
  unsigned __int16 v67; // cx
  _QWORD *v68; // r9
  USHORT v69; // r15
  WCHAR *v70; // rcx
  __int64 v71; // rcx
  USHORT v72; // r15
  __int64 v73; // rcx
  __int16 *v74; // r8
  int v75; // ecx
  _DWORD *v76; // rdi
  int v77; // ecx
  __int16 *v78; // rdx
  int v79; // r8d
  int v80; // ecx
  __int16 v81; // [rsp+40h] [rbp-B8h] BYREF
  _BYTE v82[6]; // [rsp+42h] [rbp-B6h] BYREF
  __int128 v83; // [rsp+48h] [rbp-B0h] BYREF
  UNICODE_STRING ConstantNameB; // [rsp+58h] [rbp-A0h] BYREF
  _DWORD *v85; // [rsp+68h] [rbp-90h]
  _QWORD *v86; // [rsp+70h] [rbp-88h]
  __int64 v87; // [rsp+78h] [rbp-80h]
  UNICODE_STRING ConstantNameA; // [rsp+80h] [rbp-78h] BYREF
  UNICODE_STRING v89; // [rsp+90h] [rbp-68h] BYREF
  __int64 v90; // [rsp+A0h] [rbp-58h]
  __int64 v91; // [rsp+A8h] [rbp-50h]
  __int64 v92; // [rsp+B0h] [rbp-48h]
  __int64 v93; // [rsp+B8h] [rbp-40h]
  char v95; // [rsp+100h] [rbp+8h]
  __int64 v96; // [rsp+108h] [rbp+10h]
  _DWORD *v97; // [rsp+108h] [rbp+10h]
  __int64 ExistingLcb; // [rsp+108h] [rbp+10h]
  __int64 v99; // [rsp+110h] [rbp+18h]
  USHORT v101; // [rsp+120h] [rbp+28h]
  USHORT v102; // [rsp+120h] [rbp+28h]
  volatile signed __int32 *v103; // [rsp+120h] [rbp+28h]
  unsigned int v104; // [rsp+128h] [rbp+30h]

  v6 = a3;
  v9 = *(_QWORD *)(a1 + 104);
  v99 = v9;
  v92 = a3;
  v83 = 0;
  v81 = 92;
  v10 = (__int64 *)(v9 + 32);
  if ( !a3 )
    v6 = *v10;
  if ( (*(_DWORD *)(a1 + 16) & 0x100000) != 0
    || (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x80000000LL) == 0 )
  {
    v11 = (UNICODE_STRING *)a6;
  }
  else
  {
    v11 = (UNICODE_STRING *)a6;
    McTemplateU0ppww_EtwWriteTransfer(
      *a6 >> 1,
      (unsigned int)hashsup_c292,
      (_DWORD)a2,
      v6,
      *(_WORD *)(v6 + 656) >> 1,
      *(_QWORD *)(v6 + 664),
      *a6 >> 1,
      *((_QWORD *)a6 + 1));
    v9 = v99;
  }
  v12 = *(_DWORD *)(v6 + 672);
  *(_DWORD *)(a5 + 72) = v12;
  *(_DWORD *)(a5 + 80) = v12;
  if ( v6 != *v10 )
  {
    v74 = &v81;
    do
    {
      v75 = 37 * v12 + *(unsigned __int16 *)(*(_QWORD *)(v9 + 784) + 2LL * (unsigned __int16)*v74);
      v12 = v75;
      ++v74;
    }
    while ( v74 < (__int16 *)v82 );
    *(_DWORD *)(a5 + 72) = v75;
  }
  Buffer = v11->Buffer;
  v15 = (unsigned __int16 *)((char *)Buffer + v11->Length);
  if ( Buffer < v15 )
  {
    v44 = *(_QWORD *)(v9 + 784);
    do
      v12 = *(unsigned __int16 *)(v44 + 2LL * *Buffer++) + 37 * v12;
    while ( Buffer < v15 );
  }
  v16 = -314159269 * v12;
  if ( -314159269 * v12 < 0 )
    v16 = 314159269 * v12;
  *(_DWORD *)(a5 + 72) = v16 % 1000000007;
  ExAcquirePushLockSharedEx(a2 + 4, 0);
  v17 = *(unsigned __int16 *)(v6 + 656);
  if ( !(_WORD)v17 )
  {
    ExReleasePushLockEx(a2 + 4, 0);
    if ( (*(_DWORD *)(a1 + 16) & 0x100000) == 0
      && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x80000000LL) != 0 )
    {
      McTemplateU0_EtwWriteTransfer(v43, hashsup_c338);
    }
    return 0;
  }
  v96 = 0;
  v90 = 0;
  *(_DWORD *)(a5 + 84) = v17;
  *(_DWORD *)(a5 + 76) = v17;
  v18 = v17 + v11->Length;
  *(_DWORD *)(a5 + 76) = v18;
  if ( v6 != *v10 )
    *(_DWORD *)(a5 + 76) = v18 + 2;
  i = 0;
  v20 = *(_DWORD *)(a5 + 72);
  v21 = v20 & (*a2 - 1);
  v104 = v21;
  if ( v21 < a2[1] )
  {
    v21 = v20 & (2 * *a2 - 1);
    v104 = v21;
  }
  v87 = 16LL * (v21 & 0x3FF);
  v86 = &a2[2 * ((unsigned __int64)v21 >> 10) + 6];
  ExAcquirePushLockSharedEx(*v86 + 8LL + v87, 0);
  do
  {
    while ( 1 )
    {
      while ( 1 )
      {
        v22 = *(_DWORD *)(a5 + 72);
        v23 = 0;
        if ( !i )
        {
          v24 = v22 & (*a2 - 1);
          if ( v24 < a2[1] )
            v24 = v22 & (2 * *a2 - 1);
          i = *(_QWORD *)&a2[2 * ((unsigned __int64)v24 >> 10) + 6] + 16LL * (v24 & 0x3FF);
        }
        for ( i = *(_QWORD *)i; i; i = *(_QWORD *)i )
        {
          ++v23;
          if ( *(_DWORD *)(i + 16) == v22 )
            break;
        }
        if ( v23 > 5 && !a2[2] && *a2 < 0x8000u )
          a2[2] = 1;
        if ( !i )
        {
          v33 = 0;
          goto LABEL_33;
        }
        if ( *(_DWORD *)(i + 20) == *(_DWORD *)(a5 + 76) )
        {
          v85 = *(_DWORD **)(i + 8);
          v25 = *((_QWORD *)v85 + 3);
          v89 = 0;
          v26 = *(_WORD *)(v25 + 656);
          if ( v26 )
            break;
        }
      }
      v27 = v11;
      if ( v6 == v25 )
        break;
      ConstantNameB = 0;
      ConstantNameA = 0;
      v28 = *(_WORD *)(v6 + 656);
      v101 = v28;
      if ( v28 < v26 )
      {
        v29 = *(_QWORD *)(v6 + 192);
        v93 = v29;
        if ( v6 == *(_QWORD *)(v29 + 32) )
        {
          v31 = 2;
          v32 = (_QWORD *)(v25 + 664);
LABEL_96:
          v69 = v26 - v31;
          ConstantNameA.Length = v69;
          ConstantNameA.MaximumLength = v69;
          ConstantNameA.Buffer = (PWSTR)(*v32 + v31);
          if ( (unsigned __int64)v69 + 2 < v11->Length )
          {
            v70 = v11->Buffer;
            if ( v70[(unsigned __int64)v69 >> 1] == 92 )
            {
              ConstantNameB.Length = v69;
              ConstantNameB.MaximumLength = v69;
              ConstantNameB.Buffer = v70;
              if ( FsRtlAreNamesEqual(&ConstantNameA, &ConstantNameB, 1u, *(PCWCH *)(v29 + 784)) )
              {
                v71 = (unsigned __int16)(ConstantNameA.Length + 2);
                v89.Length = v11->Length - v71;
                v89.MaximumLength = v89.Length;
                v89.Buffer = (PWSTR)((char *)v11->Buffer + v71);
                v27 = &v89;
                break;
              }
            }
          }
        }
        else
        {
          v91 = v25 + 664;
          v30 = *(WCHAR **)(v25 + 664);
          if ( v30[(unsigned __int64)v28 >> 1] == 92 )
          {
            ConstantNameB.Length = v28;
            ConstantNameB.MaximumLength = v28;
            ConstantNameB.Buffer = v30;
            if ( !memcmp(*(const void **)(v6 + 664), v30, v28) )
            {
              v31 = v101 + 2;
              v29 = v93;
              v32 = (_QWORD *)v91;
              goto LABEL_96;
            }
          }
        }
      }
    }
  }
  while ( !FsRtlAreNamesEqual((PCUNICODE_STRING)(v85 + 18), v27, 1u, *(PCWCH *)(*(_QWORD *)(v6 + 192) + 784LL)) );
  v33 = *(_QWORD *)(i + 8);
  v96 = v33;
  v90 = (__int64)v11->Buffer + v11->Length;
  *(_DWORD *)(a5 + 84) = 0;
  *(_DWORD *)(a5 + 76) = 0;
LABEL_33:
  v34 = 0;
  if ( v33 )
  {
LABEL_34:
    v35 = v96;
    goto LABEL_35;
  }
  ExReleasePushLockEx(*v86 + v87 + 8, 0);
  LOWORD(v83) = v11->Length;
  v45 = v83;
  v46 = v11->Buffer;
  for ( j = &v46[((unsigned __int64)(unsigned __int16)v83 - 2) >> 1]; ; --j )
  {
    if ( v45 <= 2u )
    {
      *(_DWORD *)(a5 + 84) = 0;
      goto LABEL_34;
    }
    v45 -= 2;
    v48 = *j == 92;
    LOWORD(v83) = v45;
    if ( v48 )
      break;
  }
  *((_QWORD *)&v83 + 1) = v46;
  WORD1(v83) = v45;
  ExReleasePushLockEx(a2 + 4, 0);
  if ( v6 != *v10 )
  {
    v78 = &v81;
    v79 = *(_DWORD *)(a5 + 80);
    do
    {
      v80 = 37 * v79 + *(unsigned __int16 *)(*(_QWORD *)(v99 + 784) + 2LL * (unsigned __int16)*v78);
      v79 = v80;
      ++v78;
    }
    while ( v78 < (__int16 *)v82 );
    *(_DWORD *)(a5 + 80) = v80;
    *(_DWORD *)(a5 + 84) += 2;
  }
  v49 = (unsigned __int16 *)*((_QWORD *)&v83 + 1);
  v50 = (unsigned __int16)v83;
  v51 = *((_QWORD *)&v83 + 1) + (unsigned __int16)v83;
  v52 = *(_DWORD *)(a5 + 80);
  if ( *((_QWORD *)&v83 + 1) < v51 )
  {
    do
      v52 = *(unsigned __int16 *)(*(_QWORD *)(v99 + 784) + 2LL * *v49++) + 37 * v52;
    while ( (unsigned __int64)v49 < v51 );
  }
  v53 = -314159269 * v52;
  if ( -314159269 * v52 < 0 )
    v53 = 314159269 * v52;
  *(_DWORD *)(a5 + 80) = v53 % 1000000007;
  *(_DWORD *)(a5 + 84) += v50;
  ExAcquirePushLockSharedEx(a2 + 4, 0);
  v54 = *(_DWORD *)(a5 + 80);
  v55 = v54 & (*a2 - 1);
  v104 = v55;
  if ( v55 < a2[1] )
  {
    v55 = v54 & (2 * *a2 - 1);
    v104 = v55;
  }
  v85 = &a2[2 * ((unsigned __int64)v55 >> 10) + 6];
  v91 = 16LL * (v55 & 0x3FF);
  ExAcquirePushLockSharedEx(v91 + *(_QWORD *)v85 + 8LL, 0);
  k = 0;
  while ( 1 )
  {
    while ( 1 )
    {
LABEL_75:
      v57 = *(_DWORD *)(a5 + 80);
      v58 = 0;
      if ( !k )
      {
        v59 = v57 & (*a2 - 1);
        if ( v59 < a2[1] )
          v59 = v57 & (2 * *a2 - 1);
        k = *(_QWORD *)&a2[2 * ((unsigned __int64)v59 >> 10) + 6] + 16LL * (v59 & 0x3FF);
      }
      for ( k = *(_QWORD *)k; k; k = *(_QWORD *)k )
      {
        ++v58;
        if ( *(_DWORD *)(k + 16) == v57 )
          break;
      }
      if ( v58 > 5 && !a2[2] && *a2 < 0x8000u )
        a2[2] = 1;
      v34 = 0;
      if ( !k )
      {
        v35 = v96;
        goto LABEL_93;
      }
      if ( *(_DWORD *)(k + 20) == *(_DWORD *)(a5 + 84) )
      {
        v60 = *(_QWORD *)(k + 8);
        v61 = *(_QWORD *)(v60 + 24);
        v89 = 0;
        v62 = *(_WORD *)(v61 + 656);
        if ( v62 )
          break;
      }
    }
    v63 = (UNICODE_STRING *)&v83;
    if ( v6 == v61 )
      break;
    ConstantNameB = 0;
    ConstantNameA = 0;
    v64 = *(_WORD *)(v6 + 656);
    v102 = v64;
    if ( v64 >= v62 )
      goto LABEL_75;
    v65 = *(_QWORD *)(v6 + 192);
    v87 = v65;
    if ( v6 == *(_QWORD *)(v65 + 32) )
    {
      v67 = 2;
      v68 = (_QWORD *)(v61 + 664);
    }
    else
    {
      v86 = (_QWORD *)(v61 + 664);
      v66 = *(WCHAR **)(v61 + 664);
      if ( v66[(unsigned __int64)v64 >> 1] != 92 )
        goto LABEL_75;
      ConstantNameB.Length = v64;
      ConstantNameB.MaximumLength = v64;
      ConstantNameB.Buffer = v66;
      if ( memcmp(*(const void **)(v6 + 664), v66, v64) )
        goto LABEL_75;
      v67 = v102 + 2;
      v65 = v87;
      v68 = v86;
    }
    v72 = v62 - v67;
    ConstantNameA.Length = v72;
    ConstantNameA.MaximumLength = v72;
    ConstantNameA.Buffer = (PWSTR)(*v68 + v67);
    if ( (unsigned __int64)v72 + 2 < (unsigned __int16)v83
      && *(_WORD *)(*((_QWORD *)&v83 + 1) + 2 * ((unsigned __int64)v72 >> 1)) == 92 )
    {
      ConstantNameB.Length = v72;
      ConstantNameB.MaximumLength = v72;
      ConstantNameB.Buffer = (PWSTR)*((_QWORD *)&v83 + 1);
      if ( FsRtlAreNamesEqual(&ConstantNameA, &ConstantNameB, 1u, *(PCWCH *)(v65 + 784)) )
      {
        v73 = (unsigned __int16)(ConstantNameA.Length + 2);
        v89.Length = v83 - v73;
        v89.MaximumLength = v83 - v73;
        v89.Buffer = (PWSTR)(*((_QWORD *)&v83 + 1) + v73);
        v63 = &v89;
        break;
      }
    }
  }
  if ( !FsRtlAreNamesEqual((PCUNICODE_STRING)(v60 + 72), v63, 1u, *(PCWCH *)(*(_QWORD *)(v6 + 192) + 784LL)) )
    goto LABEL_75;
  v35 = *(_QWORD *)(k + 8);
  v96 = v35;
  v34 = v11->Length - (unsigned __int16)v83 - 2;
  v90 = (__int64)v11->Buffer + (unsigned __int16)v83 + 2;
  *(_DWORD *)(a5 + 84) = 0;
LABEL_93:
  if ( v35 )
    goto LABEL_36;
  ExReleasePushLockEx(*(_QWORD *)v85 + v91 + 8, 0);
LABEL_35:
  if ( v35 )
  {
LABEL_36:
    v87 = v99;
    v36 = v34 + *(unsigned __int16 *)(v35 + 72) + 2;
    if ( !v34 )
      v36 = *(unsigned __int16 *)(v35 + 72);
    *((_QWORD *)&v83 + 1) = (char *)v11->Buffer + (unsigned int)v11->Length - v36;
    LOWORD(v83) = *(_WORD *)(v35 + 72);
    WORD1(v83) = v83;
    memmove(*((void **)&v83 + 1), *(const void **)(v35 + 80), *(unsigned __int16 *)(v35 + 72));
    Length = v11->Length;
    if ( v36 != Length )
      memmove(
        v11->Buffer,
        (const void *)(*(_QWORD *)(*(_QWORD *)(v35 + 24) + 664LL)
                     + (unsigned int)*(unsigned __int16 *)(*(_QWORD *)(v35 + 24) + 656LL)
                     - (Length
                      - v36
                      - 2)),
        (unsigned int)(Length - v36 - 2));
    v38 = a1;
    if ( a4 == 1 && v34 && (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(a1 + 112) + 184LL) + 2LL) & 4) == 0 )
    {
      v39 = 16;
    }
    else
    {
      v39 = 0;
      *(_DWORD *)(a5 + 156) &= ~0x400u;
    }
    v40 = v96;
    if ( (unsigned __int8)NtfsAcquireFcbWithPaging(a1, *(_QWORD *)(v96 + 48), 0, v39 | 2) )
    {
      ExReleasePushLockEx(*(_QWORD *)&a2[2 * ((unsigned __int64)v104 >> 10) + 6] + 16LL * (v104 & 0x3FF) + 8, 0);
      ExReleasePushLockEx(a2 + 4, 0);
      if ( v92 )
        NtfsReleaseFcbEx(a1, *(_QWORD *)(v92 + 184), 0);
      v35 = v96;
      *(_QWORD *)(a5 + 96) = *(_QWORD *)(v96 + 48);
    }
    else
    {
      v86 = *(_QWORD **)(v96 + 48);
      v103 = (volatile signed __int32 *)v86;
      v85 = *(_DWORD **)(*(_QWORD *)(v96 + 24) + 184LL);
      v97 = v85;
      v95 = *(_BYTE *)(*(_QWORD *)(v40 + 192) + 65LL);
      ExAcquirePushLockSharedEx(v99 + 656, 0);
      _InterlockedIncrement(v103 + 7);
      _InterlockedIncrement(v97 + 7);
      ExReleasePushLockEx(v99 + 656, 0);
      if ( v92 )
      {
        NtfsReleaseFcbEx(v38, *(_QWORD *)(v92 + 184), 0);
        *(_QWORD *)(a5 + 96) = 0;
      }
      ExReleasePushLockEx(*(_QWORD *)&a2[2 * ((unsigned __int64)v104 >> 10) + 6] + 16LL * (v104 & 0x3FF) + 8, 0);
      ExReleasePushLockEx(a2 + 4, 0);
      NtfsAcquireFcbWithPaging(v38, v103, 0, v39);
      *(_QWORD *)(a5 + 96) = v103;
      v76 = v97;
      ExistingLcb = NtfsFindExistingLcb(v77, (_DWORD)v97, (_DWORD)v103, (unsigned int)&v83, v95, 0);
      ExAcquirePushLockSharedEx(v99 + 656, 0);
      _InterlockedDecrement(v103 + 7);
      _InterlockedDecrement(v76 + 7);
      ExReleasePushLockEx(v99 + 656, 0);
      v35 = ExistingLcb;
      if ( !ExistingLcb )
      {
        NtfsRaiseStatusInternal(v38, -1073741608, 0, 0, 3080892);
        __debugbreak();
      }
    }
    v11->Length = v34;
    v11->MaximumLength = v34;
    v11->Buffer = (PWSTR)v90;
  }
  else
  {
    ExReleasePushLockEx(a2 + 4, 0);
    v38 = a1;
  }
  if ( (*(_DWORD *)(v38 + 16) & 0x100000) == 0 )
  {
    if ( v35 )
    {
      if ( (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x80000000LL) != 0 )
        McTemplateU0pw_EtwWriteTransfer(
          v41,
          (unsigned int)hashsup_c741,
          v35,
          *(unsigned __int16 *)(v35 + 72) >> 1,
          *(_QWORD *)(v35 + 80));
    }
    else if ( (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x80000000LL) != 0 )
    {
      McTemplateU0_EtwWriteTransfer(v41, hashsup_c750);
    }
  }
  return v35;
}

```

## disassembly

```asm
0x14018b100  mov     [rsp+arg_18], r9b
0x14018b105  mov     [rsp+arg_0], rcx
0x14018b10a  push    rbx
0x14018b10b  push    rsi
0x14018b10c  push    rdi
0x14018b10d  push    r12
0x14018b10f  push    r13
0x14018b111  push    r14
0x14018b113  push    r15
0x14018b115  sub     rsp, 0C0h
0x14018b11c  mov     rdi, r8
0x14018b11f  mov     r13, rdx
0x14018b122  mov     rbx, rcx
0x14018b125  mov     r10, [rcx+68h]
0x14018b129  mov     [rsp+0F8h+arg_10], r10
0x14018b131  mov     [rsp+0F8h+var_48], r8
0x14018b139  xorps   xmm0, xmm0
0x14018b13c  movups  [rsp+0F8h+var_B0], xmm0
0x14018b141  mov     eax, 5Ch ; '\'
0x14018b146  mov     [rsp+0F8h+var_B8], ax
0x14018b14b  lea     r12, [r10+20h]
0x14018b14f  test    r8, r8
0x14018b152  jnz     short loc_14018B158
0x14018b154  mov     rdi, [r12]
0x14018b158  mov     eax, [rcx+10h]
0x14018b15b  bt      rax, 14h
0x14018b160  jnb     loc_14018BDA5
0x14018b166  mov     r14, [rsp+0F8h+arg_28]
0x14018b16e  mov     edx, [rdi+2A0h]
0x14018b174  mov     rsi, [rsp+0F8h+arg_20]
0x14018b17c  mov     [rsi+48h], edx
0x14018b17f  mov     [rsi+50h], edx
0x14018b182  cmp     rdi, [r12]
0x14018b186  jnz     loc_14018BBA5
0x14018b18c  mov     r9, [r14+8]
0x14018b190  movzx   r8d, word ptr [r14]
0x14018b194  add     r8, r9
0x14018b197  cmp     r9, r8
0x14018b19a  jb      loc_14018B596
0x14018b1a0  imul    eax, edx, 12B9B0A5h
0x14018b1a6  mov     ecx, eax
0x14018b1a8  neg     ecx
0x14018b1aa  cmovs   ecx, eax
0x14018b1ad  mov     eax, 44B82F99h
0x14018b1b2  imul    ecx
0x14018b1b4  sar     edx, 1Ch
0x14018b1b7  mov     eax, edx
0x14018b1b9  shr     eax, 1Fh
0x14018b1bc  add     edx, eax
0x14018b1be  imul    eax, edx, 3B9ACA07h
0x14018b1c4  sub     ecx, eax
0x14018b1c6  mov     [rsi+48h], ecx
0x14018b1c9  xor     edx, edx
0x14018b1cb  lea     rcx, [r13+10h]
0x14018b1cf  call    cs:__imp_ExAcquirePushLockSharedEx
0x14018b1d6  nop     dword ptr [rax+rax+00h]
0x14018b1db  movzx   eax, word ptr [rdi+290h]
0x14018b1e2  test    ax, ax
0x14018b1e5  jz      loc_14018B572
0x14018b1eb  mov     [rsp+0F8h+arg_8], 0
0x14018b1f7  mov     [rsp+0F8h+var_58], 0
0x14018b203  mov     ecx, eax
0x14018b205  mov     [rsi+54h], eax
0x14018b208  mov     [rsi+4Ch], eax
0x14018b20b  movzx   eax, word ptr [r14]
0x14018b20f  add     eax, ecx
0x14018b211  mov     [rsi+4Ch], eax
0x14018b214  cmp     rdi, [r12]
0x14018b218  jz      short loc_14018B220
0x14018b21a  add     eax, 2
0x14018b21d  mov     [rsi+4Ch], eax
0x14018b220  xor     ebx, ebx
0x14018b222  mov     eax, [rsi+48h]
0x14018b225  mov     ecx, [r13+0]
0x14018b229  lea     edx, [rcx-1]
0x14018b22c  and     edx, eax
0x14018b22e  mov     dword ptr [rsp+0F8h+arg_28], edx
0x14018b235  cmp     edx, [r13+4]
0x14018b239  jnb     short loc_14018B24B
0x14018b23b  lea     edx, ds:0FFFFFFFFFFFFFFFFh[rcx*2]
0x14018b242  and     edx, eax
0x14018b244  mov     dword ptr [rsp+0F8h+arg_28], edx
0x14018b24b  mov     ecx, edx
0x14018b24d  and     ecx, 3FFh
0x14018b253  shl     rcx, 4
0x14018b257  mov     [rsp+0F8h+var_80], rcx
0x14018b25c  mov     eax, edx
0x14018b25e  shr     rax, 0Ah
0x14018b262  lea     rax, ds:18h[rax*8]
0x14018b26a  add     rax, r13
0x14018b26d  mov     [rsp+0F8h+var_88], rax
0x14018b272  mov     rax, [rax]
0x14018b275  add     rax, 8
0x14018b279  add     rcx, rax
0x14018b27c  xor     edx, edx
0x14018b27e  call    cs:__imp_ExAcquirePushLockSharedEx
0x14018b285  nop     dword ptr [rax+rax+00h]
0x14018b28a  mov     ecx, [rsi+48h]
0x14018b28d  xor     edx, edx
0x14018b28f  test    rbx, rbx
0x14018b292  jnz     short loc_14018B2C1
0x14018b294  mov     eax, [r13+0]
0x14018b298  lea     ebx, [rax-1]
0x14018b29b  and     ebx, ecx
0x14018b29d  cmp     ebx, [r13+4]
0x14018b2a1  jnb     short loc_14018B2AC
0x14018b2a3  lea     ebx, ds:0FFFFFFFFFFFFFFFFh[rax*2]
0x14018b2aa  and     ebx, ecx
0x14018b2ac  mov     eax, ebx
0x14018b2ae  shr     rax, 0Ah
0x14018b2b2  and     ebx, 3FFh
0x14018b2b8  shl     rbx, 4
0x14018b2bc  add     rbx, [r13+rax*8+18h]
0x14018b2c1  mov     rbx, [rbx]
0x14018b2c4  test    rbx, rbx
0x14018b2c7  jz      short loc_14018B2D8
0x14018b2c9  inc     edx
0x14018b2cb  cmp     [rbx+10h], ecx
0x14018b2ce  jz      short loc_14018B2D8
0x14018b2d0  mov     rbx, [rbx]
0x14018b2d3  test    rbx, rbx
0x14018b2d6  jnz     short loc_14018B2C9
0x14018b2d8  cmp     edx, 5
0x14018b2db  ja      loc_14018BA3D
0x14018b2e1  test    rbx, rbx
0x14018b2e4  jz      loc_14018B3D2
0x14018b2ea  mov     eax, [rsi+4Ch]
0x14018b2ed  cmp     [rbx+14h], eax
0x14018b2f0  jnz     short loc_14018B28A
0x14018b2f2  mov     rax, [rbx+8]
0x14018b2f6  mov     [rsp+0F8h+var_90], rax
0x14018b2fb  mov     rax, [rax+18h]
0x14018b2ff  xorps   xmm0, xmm0
0x14018b302  movups  xmmword ptr [rsp+0F8h+var_68.Length], xmm0
0x14018b30a  movzx   r15d, word ptr [rax+290h]
0x14018b312  test    r15w, r15w
0x14018b316  jz      loc_14018B28A
0x14018b31c  mov     rdx, r14
0x14018b31f  cmp     rdi, rax
0x14018b322  jz      loc_14018B9E0
0x14018b328  movups  xmmword ptr [rsp+0F8h+ConstantNameB.Length], xmm0
0x14018b32d  xorps   xmm1, xmm1
0x14018b330  movups  xmmword ptr [rsp+0F8h+ConstantNameA.Length], xmm1
0x14018b338  movzx   ecx, word ptr [rdi+290h]
0x14018b33f  mov     dword ptr [rsp+0F8h+arg_20], ecx
0x14018b346  cmp     cx, r15w
0x14018b34a  jnb     loc_14018B28A
0x14018b350  mov     rdx, [rdi+0C0h]
0x14018b357  mov     [rsp+0F8h+var_40], rdx
0x14018b35f  cmp     rdi, [rdx+20h]
0x14018b363  jz      loc_14018B910
0x14018b369  movzx   r8d, cx; Size
0x14018b36d  add     rax, 298h
0x14018b373  mov     [rsp+0F8h+var_50], rax
0x14018b37b  mov     rdx, [rax]; Buf2
0x14018b37e  mov     eax, r8d
0x14018b381  shr     rax, 1
0x14018b384  cmp     word ptr [rdx+rax*2], 5Ch ; '\'
0x14018b389  jnz     loc_14018B28A
0x14018b38f  mov     [rsp+0F8h+ConstantNameB.Length], cx
0x14018b394  mov     [rsp+0F8h+ConstantNameB.MaximumLength], cx
0x14018b399  mov     [rsp+0F8h+ConstantNameB.Buffer], rdx
0x14018b39e  mov     rcx, [rdi+298h]; Buf1
0x14018b3a5  call    memcmp
0x14018b3aa  test    eax, eax
0x14018b3ac  jnz     loc_14018B28A
0x14018b3b2  mov     ecx, dword ptr [rsp+0F8h+arg_20]
0x14018b3b9  add     cx, 2
0x14018b3bd  mov     rdx, [rsp+0F8h+var_40]
0x14018b3c5  mov     r9, [rsp+0F8h+var_50]
0x14018b3cd  jmp     loc_14018B91C
0x14018b3d2  mov     rax, [rsp+0F8h+arg_8]
0x14018b3da  xor     r15d, r15d
0x14018b3dd  test    rax, rax
0x14018b3e0  jz      loc_14018B620
0x14018b3e6  mov     rdi, [rsp+0F8h+arg_8]
0x14018b3ee  test    rdi, rdi
0x14018b3f1  jz      loc_14018B5BA
0x14018b3f7  mov     rax, [rsp+0F8h+arg_10]
0x14018b3ff  mov     [rsp+0F8h+var_80], rax
0x14018b404  movzx   ecx, word ptr [rdi+48h]
0x14018b408  add     ecx, r15d
0x14018b40b  lea     ebx, [rcx+2]
0x14018b40e  test    r15d, r15d
0x14018b411  cmovz   ebx, ecx
0x14018b414  movzx   ecx, word ptr [r14]
0x14018b418  sub     ecx, ebx
0x14018b41a  add     rcx, [r14+8]; void *
0x14018b41e  mov     qword ptr [rsp+0F8h+var_B0+8], rcx
0x14018b423  movzx   eax, word ptr [rdi+48h]
0x14018b427  mov     word ptr [rsp+0F8h+var_B0], ax
0x14018b42c  mov     word ptr [rsp+0F8h+var_B0+2], ax
0x14018b431  movzx   r8d, word ptr [rdi+48h]; Size
0x14018b436  mov     rdx, [rdi+50h]; Src
0x14018b43a  call    memmove
0x14018b43f  movzx   ecx, word ptr [r14]
0x14018b443  cmp     ebx, ecx
0x14018b445  jz      short loc_14018B46D
0x14018b447  sub     ecx, ebx
0x14018b449  add     ecx, 0FFFFFFFEh
0x14018b44c  mov     r9, [rdi+18h]
0x14018b450  mov     r8d, ecx; Size
0x14018b453  movzx   edx, word ptr [r9+290h]
0x14018b45b  sub     edx, ecx
0x14018b45d  add     rdx, [r9+298h]; Src
0x14018b464  mov     rcx, [r14+8]; void *
0x14018b468  call    memmove
0x14018b46d  mov     r12, [rsp+0F8h+arg_0]
0x14018b475  cmp     [rsp+0F8h+arg_18], 1
0x14018b47d  jz      loc_14018B5D9
0x14018b483  xor     edi, edi
0x14018b485  and     dword ptr [rsi+9Ch], 0FFFFFBFFh
0x14018b48f  mov     r9d, edi
0x14018b492  or      r9d, 2
0x14018b496  xor     r8d, r8d
0x14018b499  mov     rbx, [rsp+0F8h+arg_8]
0x14018b4a1  mov     rdx, [rbx+30h]
0x14018b4a5  mov     rcx, r12
0x14018b4a8  call    NtfsAcquireFcbWithPaging
0x14018b4ad  xor     edx, edx
0x14018b4af  test    al, al
0x14018b4b1  jz      loc_14018BBFD
0x14018b4b7  mov     ecx, dword ptr [rsp+0F8h+arg_28]
0x14018b4be  mov     eax, ecx
0x14018b4c0  shr     rax, 0Ah
0x14018b4c4  and     ecx, 3FFh
0x14018b4ca  shl     rcx, 4
0x14018b4ce  add     rcx, 8
0x14018b4d2  add     rcx, [r13+rax*8+18h]
0x14018b4d7  call    cs:__imp_ExReleasePushLockEx
0x14018b4de  nop     dword ptr [rax+rax+00h]
0x14018b4e3  lea     rcx, [r13+10h]
0x14018b4e7  xor     edx, edx
0x14018b4e9  call    cs:__imp_ExReleasePushLockEx
0x14018b4f0  nop     dword ptr [rax+rax+00h]
0x14018b4f5  mov     rdx, [rsp+0F8h+var_48]
0x14018b4fd  test    rdx, rdx
0x14018b500  jz      short loc_14018B514
0x14018b502  xor     r8d, r8d
0x14018b505  mov     rdx, [rdx+0B8h]
0x14018b50c  mov     rcx, r12
0x14018b50f  call    NtfsReleaseFcbEx
0x14018b514  mov     rdi, [rsp+0F8h+arg_8]
0x14018b51c  mov     rax, [rdi+30h]
0x14018b520  mov     [rsi+60h], rax
0x14018b524  mov     [r14], r15w
0x14018b528  mov     [r14+2], r15w
0x14018b52d  mov     rax, [rsp+0F8h+var_58]
0x14018b535  mov     [r14+8], rax
0x14018b539  mov     eax, [r12+10h]
0x14018b53e  bt      rax, 14h
0x14018b543  jb      short loc_14018B55B
0x14018b545  test    rdi, rdi
0x14018b548  jz      loc_14018B602
0x14018b54e  cmp     byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits+3, 0
0x14018b555  jl      loc_14018BE40
0x14018b55b  mov     rax, rdi
0x14018b55e  add     rsp, 0C0h
0x14018b565  pop     r15
0x14018b567  pop     r14
0x14018b569  pop     r13
0x14018b56b  pop     r12
0x14018b56d  pop     rdi
0x14018b56e  pop     rsi
0x14018b56f  pop     rbx
0x14018b570  retn
0x14018b572  xor     edx, edx
0x14018b574  lea     rcx, [r13+10h]
0x14018b578  call    cs:__imp_ExReleasePushLockEx
0x14018b57f  nop     dword ptr [rax+rax+00h]
0x14018b584  mov     eax, [rbx+10h]
0x14018b587  bt      rax, 14h
0x14018b58c  jnb     loc_14018BE65
0x14018b592  xor     eax, eax
0x14018b594  jmp     short loc_14018B55E
0x14018b596  mov     r10, [r10+310h]
0x14018b59d  movzx   eax, word ptr [r9]
0x14018b5a1  movzx   ecx, word ptr [r10+rax*2]
0x14018b5a6  imul    edx, 25h ; '%'
0x14018b5a9  add     edx, ecx
0x14018b5ab  add     r9, 2
0x14018b5af  cmp     r9, r8
0x14018b5b2  jnb     loc_14018B1A0
0x14018b5b8  jmp     short loc_14018B59D
0x14018b5ba  lea     rcx, [r13+10h]
0x14018b5be  xor     edx, edx
0x14018b5c0  call    cs:__imp_ExReleasePushLockEx
0x14018b5c7  nop     dword ptr [rax+rax+00h]
0x14018b5cc  mov     r12, [rsp+0F8h+arg_0]
0x14018b5d4  jmp     loc_14018B539
0x14018b5d9  test    r15d, r15d
0x14018b5dc  jz      loc_14018B483
0x14018b5e2  mov     rax, [r12+70h]
0x14018b5e7  mov     rcx, [rax+0B8h]
0x14018b5ee  test    byte ptr [rcx+2], 4
0x14018b5f2  jnz     loc_14018B483
0x14018b5f8  mov     edi, 10h
0x14018b5fd  jmp     loc_14018B48F
0x14018b602  cmp     byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits+3, 0
0x14018b609  jge     loc_14018B55B
  ... truncated ...
```
