# BfGenerateDirectoryEntry

- ea: `0x14001bbb4`
- end: `0x14001c8fe`
- name: `BfGenerateDirectoryEntry`
- size: `3402`
- prototype: `__int64 __fastcall(int, int, int, int, void *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x14001ad80`

## callees

- `0x140002740`
- `0x140003140`
- `0x140004b90`
- `0x140004cc0`
- `0x140004fc0`
- `0x14001bbb4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001be0e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001be0e`
- `ntoskrnl!ExAllocatePool2` at `0x14001bc09`
- `ntoskrnl!ExAllocatePool2` at `0x14001bc09`
- `FLTMGR!FltQueryInformationFile` at `0x14001befb`
- `FLTMGR!FltQueryInformationFile` at `0x14001bf32`
- `FLTMGR!FltQueryInformationFile` at `0x14001bf79`
- `FLTMGR!FltQueryInformationFile` at `0x14001bff2`
- `FLTMGR!FltQueryInformationFile` at `0x14001c135`
- `FLTMGR!FltQueryInformationFile` at `0x14001c40d`
- `FLTMGR!FltQueryInformationFile` at `0x14001befb`
- `FLTMGR!FltQueryInformationFile` at `0x14001bf32`
- `FLTMGR!FltQueryInformationFile` at `0x14001bf79`
- `FLTMGR!FltQueryInformationFile` at `0x14001bff2`
- `FLTMGR!FltQueryInformationFile` at `0x14001c135`
- `FLTMGR!FltQueryInformationFile` at `0x14001c40d`

## pseudocode

```c
__int64 __fastcall BfGenerateDirectoryEntry(__int64 a1, char a2, int a3, unsigned int a4, char *a5, unsigned int *a6)
{
  __int64 Pool2; // rbx
  unsigned int v10; // r14d
  size_t v11; // rdi
  struct _FILE_OBJECT *v12; // rdx
  NTSTATUS v13; // r12d
  __int128 v14; // xmm0
  _DWORD *v15; // rdx
  unsigned int v16; // r15d
  NTSTATUS InformationFile; // eax
  int v19; // edx
  int v20; // ecx
  unsigned __int64 v21; // rax
  __int64 v22; // rcx
  NTSTATUS v23; // eax
  char *v24; // rcx
  __int128 v25; // xmm0
  __int128 v26; // xmm0
  __int128 v27; // xmm0
  _DWORD v29[2]; // [rsp+60h] [rbp-89h] BYREF
  int v30; // [rsp+68h] [rbp-81h]
  int v31; // [rsp+6Ch] [rbp-7Dh]
  _OWORD Src[8]; // [rsp+70h] [rbp-79h] BYREF

  Pool2 = ExAllocatePool2(256, 112, 1701070402);
  if ( !Pool2 )
    return (unsigned int)-1073741670;
  v10 = 0;
  if ( a3 > 60 )
  {
    switch ( a3 )
    {
      case '?':
        v11 = 114;
        goto LABEL_8;
      case 'N':
        goto LABEL_68;
      case 'O':
        v11 = 106;
        goto LABEL_8;
      case 'P':
        v11 = 96;
        goto LABEL_8;
      case 'Q':
        v11 = 122;
        goto LABEL_8;
    }
    goto LABEL_72;
  }
  switch ( a3 )
  {
    case 60:
      v11 = 88;
      goto LABEL_8;
    case 1:
      v11 = 64;
      goto LABEL_8;
    case 2:
      v11 = 68;
      goto LABEL_8;
  }
  if ( a3 != 3 )
  {
    switch ( a3 )
    {
      case 12:
        v11 = 12;
        goto LABEL_8;
      case 37:
        v10 = 104;
        v11 = 104;
        goto LABEL_9;
      case 38:
LABEL_68:
        v11 = 80;
        goto LABEL_8;
    }
LABEL_72:
    v11 = 0;
    goto LABEL_9;
  }
  v11 = 94;
LABEL_8:
  v10 = v11;
LABEL_9:
  if ( a4 >= v10 + *(unsigned __int16 *)(a1 + 80) || a2 )
  {
    if ( a4 < v10 )
    {
      v13 = -1073741820;
      goto LABEL_26;
    }
    v12 = *(struct _FILE_OBJECT **)(a1 + 104);
    v13 = 0;
    if ( v12 )
    {
      if ( a3 != 12 )
      {
        InformationFile = FltQueryInformationFile(
                            *(PFLT_INSTANCE *)(a1 + 72),
                            v12,
                            (PVOID)Pool2,
                            0x28u,
                            FileBasicInformation,
                            0);
        if ( InformationFile < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v19) = 3;
          WPP_RECORDER_SF_sDdd(
            WPP_GLOBAL_Control->DeviceExtension,
            v19,
            12,
            19,
            (__int64)WPP_7c51d40b00ec3a3e74a53df28c1d8c0d_Traceguids,
            (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\dirctrl.c",
            187,
            InformationFile,
            4);
        }
        *(_DWORD *)(Pool2 + 32) &= 0xFFFFFFF9;
        v13 = FltQueryInformationFile(
                *(PFLT_INSTANCE *)(a1 + 72),
                *(PFILE_OBJECT *)(a1 + 104),
                (PVOID)(Pool2 + 40),
                0x18u,
                FileStandardInformation,
                0);
        if ( v13 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v12) = 3;
          WPP_RECORDER_SF_sDdd(
            WPP_GLOBAL_Control->DeviceExtension,
            (_DWORD)v12,
            12,
            20,
            (__int64)WPP_7c51d40b00ec3a3e74a53df28c1d8c0d_Traceguids,
            (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\dirctrl.c",
            205,
            v13,
            5);
        }
        if ( (unsigned int)(a3 - 2) <= 1 || a3 == 38 )
          goto LABEL_41;
      }
      v21 = (unsigned int)(a3 - 37);
      if ( (unsigned int)v21 <= 0x2C )
      {
        v22 = 0x1E0004800001LL;
        if ( _bittest64(&v22, v21) )
        {
LABEL_41:
          v13 = FltQueryInformationFile(
                  *(PFLT_INSTANCE *)(a1 + 72),
                  *(PFILE_OBJECT *)(a1 + 104),
                  (PVOID)(Pool2 + 64),
                  4u,
                  FileEaInformation,
                  0);
          if ( v13 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v12) = 3;
            WPP_RECORDER_SF_sDdd(
              WPP_GLOBAL_Control->DeviceExtension,
              (_DWORD)v12,
              12,
              21,
              (__int64)WPP_7c51d40b00ec3a3e74a53df28c1d8c0d_Traceguids,
              (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\dirctrl.c",
              228,
              v13,
              7);
          }
          if ( (unsigned int)(a3 - 37) <= 1 || (unsigned int)(a3 - 78) <= 2 )
            goto LABEL_63;
        }
      }
      if ( a3 == 81 )
      {
LABEL_63:
        v13 = FltQueryInformationFile(
                *(PFLT_INSTANCE *)(a1 + 72),
                *(PFILE_OBJECT *)(a1 + 104),
                (PVOID)(Pool2 + 72),
                8u,
                FileInternalInformation,
                0);
        if ( v13 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v12) = 3;
          WPP_RECORDER_SF_sDdd(
            WPP_GLOBAL_Control->DeviceExtension,
            (_DWORD)v12,
            12,
            22,
            (__int64)WPP_7c51d40b00ec3a3e74a53df28c1d8c0d_Traceguids,
            (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\dirctrl.c",
            248,
            v13,
            6);
        }
      }
      if ( (unsigned int)(a3 - 60) <= 0x15 )
      {
        v20 = 3145737;
        if ( _bittest(&v20, a3 - 60) )
        {
          v13 = FltQueryInformationFile(
                  *(PFLT_INSTANCE *)(a1 + 72),
                  *(PFILE_OBJECT *)(a1 + 104),
                  (PVOID)(Pool2 + 88),
                  0x18u,
                  FileMaximumInformation|FileBothDirectoryInformation,
                  0);
          if ( v13 == -1073741637 )
          {
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v12) = 4;
              WPP_RECORDER_SF_sDdd(
                WPP_GLOBAL_Control->DeviceExtension,
                (_DWORD)v12,
                12,
                23,
                (__int64)WPP_7c51d40b00ec3a3e74a53df28c1d8c0d_Traceguids,
                (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\dirctrl.c",
                10,
                187,
                59);
            }
            *(_QWORD *)(Pool2 + 96) = -1;
            *(_QWORD *)(Pool2 + 104) = -1;
          }
          else if ( v13 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v12) = 3;
            WPP_RECORDER_SF_sDdd(
              WPP_GLOBAL_Control->DeviceExtension,
              (_DWORD)v12,
              12,
              24,
              (__int64)WPP_7c51d40b00ec3a3e74a53df28c1d8c0d_Traceguids,
              (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\dirctrl.c",
              14,
              v13,
              59);
          }
          if ( a3 == 60 || a3 == 63 )
            goto LABEL_92;
        }
      }
      if ( (unsigned int)(a3 - 78) <= 3 )
      {
LABEL_92:
        v23 = FltQueryInformationFile(
                *(PFLT_INSTANCE *)(a1 + 72),
                *(PFILE_OBJECT *)(a1 + 104),
                (PVOID)(Pool2 + 80),
                8u,
                FileAttributeTagInformation,
                0);
        v13 = v23;
        if ( v23 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v12) = 3;
          WPP_RECORDER_SF_sDdd(
            WPP_GLOBAL_Control->DeviceExtension,
            (_DWORD)v12,
            12,
            25,
            (__int64)WPP_7c51d40b00ec3a3e74a53df28c1d8c0d_Traceguids,
            (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\dirctrl.c",
            33,
            v23,
            35);
        }
      }
    }
    else
    {
      *(_QWORD *)(Pool2 + 24) = *(_QWORD *)(a1 + 184);
      *(_QWORD *)Pool2 = *(_QWORD *)(a1 + 160);
      *(_QWORD *)(Pool2 + 8) = *(_QWORD *)(a1 + 168);
      *(_QWORD *)(Pool2 + 16) = *(_QWORD *)(a1 + 176);
      *(_DWORD *)(Pool2 + 32) = *(_DWORD *)(a1 + 208);
      *(_QWORD *)(Pool2 + 40) = *(_QWORD *)(a1 + 200);
      *(_QWORD *)(Pool2 + 48) = *(_QWORD *)(a1 + 192);
      *(_DWORD *)(Pool2 + 64) = *(_DWORD *)(a1 + 216);
      *(_QWORD *)(Pool2 + 72) = *(_QWORD *)(a1 + 224);
      *(_OWORD *)(Pool2 + 96) = *(_OWORD *)(a1 + 232);
      *(_DWORD *)(Pool2 + 84) = *(_DWORD *)(a1 + 220);
    }
    if ( a3 > 60 )
    {
      if ( a3 == 63 )
      {
        memset(Src, 0, 0x78u);
        v27 = *(_OWORD *)(Pool2 + 96);
        HIDWORD(Src[3]) = *(unsigned __int16 *)(a1 + 80);
        LODWORD(Src[0]) = v10 + HIDWORD(Src[3]);
        *(_QWORD *)&Src[3] = *(_QWORD *)(Pool2 + 40);
        *(_QWORD *)&Src[2] = *(_QWORD *)(Pool2 + 24);
        *((_QWORD *)&Src[0] + 1) = *(_QWORD *)Pool2;
        LODWORD(Src[4]) = *(_DWORD *)(Pool2 + 64);
        *((_QWORD *)&Src[2] + 1) = *(_QWORD *)(Pool2 + 48);
        DWORD2(Src[3]) = *(_DWORD *)(Pool2 + 32);
        Src[1] = *(_OWORD *)(Pool2 + 8);
        DWORD1(Src[4]) = *(_DWORD *)(Pool2 + 84);
        BYTE8(Src[5]) = *(_BYTE *)(a1 + 120);
        *(_OWORD *)((char *)&Src[4] + 8) = v27;
        if ( SBYTE8(Src[5]) > 0 )
          memmove((char *)&Src[5] + 10, (const void *)(a1 + 124), *(unsigned int *)(a1 + 120));
        v15 = Src;
        goto LABEL_22;
      }
      if ( a3 != 78 )
      {
        if ( a3 != 79 )
        {
          if ( a3 != 80 )
          {
            if ( a3 == 81 )
            {
              memset(Src, 0, sizeof(Src));
              v14 = *(_OWORD *)(Pool2 + 96);
              HIDWORD(Src[3]) = *(unsigned __int16 *)(a1 + 80);
              LODWORD(Src[0]) = v10 + HIDWORD(Src[3]);
              *(_QWORD *)&Src[3] = *(_QWORD *)(Pool2 + 40);
              *(_QWORD *)&Src[2] = *(_QWORD *)(Pool2 + 24);
              *((_QWORD *)&Src[0] + 1) = *(_QWORD *)Pool2;
              LODWORD(Src[4]) = *(_DWORD *)(Pool2 + 64);
              *((_QWORD *)&Src[2] + 1) = *(_QWORD *)(Pool2 + 48);
              DWORD2(Src[3]) = *(_DWORD *)(Pool2 + 32);
              Src[1] = *(_OWORD *)(Pool2 + 8);
              *((_QWORD *)&Src[4] + 1) = *(_QWORD *)(Pool2 + 72);
              DWORD1(Src[4]) = *(_DWORD *)(Pool2 + 84);
              LOBYTE(Src[6]) = *(_BYTE *)(a1 + 120);
              Src[5] = v14;
              if ( SLOBYTE(Src[6]) > 0 )
                memmove((char *)&Src[6] + 2, (const void *)(a1 + 124), *(unsigned int *)(a1 + 120));
              v15 = Src;
              goto LABEL_22;
            }
LABEL_110:
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v12) = 2;
              WPP_RECORDER_SF_sDD(
                WPP_GLOBAL_Control->DeviceExtension,
                (_DWORD)v12,
                12,
                26,
                (__int64)WPP_7c51d40b00ec3a3e74a53df28c1d8c0d_Traceguids,
                (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\dirctrl.c",
                99,
                a3);
            }
            goto LABEL_23;
          }
          v26 = *(_OWORD *)(Pool2 + 96);
          v15 = Src;
          *(_QWORD *)&Src[6] = 0;
          HIDWORD(Src[3]) = *(unsigned __int16 *)(a1 + 80);
          *(_QWORD *)&Src[0] = v10 + HIDWORD(Src[3]);
          *(_QWORD *)&Src[3] = *(_QWORD *)(Pool2 + 40);
          *(_QWORD *)&Src[2] = *(_QWORD *)(Pool2 + 24);
          *((_QWORD *)&Src[0] + 1) = *(_QWORD *)Pool2;
          LODWORD(Src[4]) = *(_DWORD *)(Pool2 + 64);
          *((_QWORD *)&Src[2] + 1) = *(_QWORD *)(Pool2 + 48);
          DWORD2(Src[3]) = *(_DWORD *)(Pool2 + 32);
          Src[1] = *(_OWORD *)(Pool2 + 8);
          *((_QWORD *)&Src[4] + 1) = *(_QWORD *)(Pool2 + 72);
          DWORD1(Src[4]) = *(_DWORD *)(Pool2 + 84);
          Src[5] = v26;
LABEL_22:
          memmove(a5, v15, v11);
LABEL_23:
          *a6 = v10;
          v16 = *(unsigned __int16 *)(a1 + 80);
          if ( a4 < v10 + v16 )
          {
            v13 = -2147483643;
            v16 = a4 - v10;
          }
          memmove(&a5[v11], *(const void **)(a1 + 88), v16);
          *a6 += v16;
          goto LABEL_26;
        }
        memset(Src, 0, 0x70u);
        HIDWORD(Src[3]) = *(unsigned __int16 *)(a1 + 80);
        LODWORD(Src[0]) = v10 + HIDWORD(Src[3]);
        *(_QWORD *)&Src[3] = *(_QWORD *)(Pool2 + 40);
        *(_QWORD *)&Src[2] = *(_QWORD *)(Pool2 + 24);
        *((_QWORD *)&Src[0] + 1) = *(_QWORD *)Pool2;
        LODWORD(Src[4]) = *(_DWORD *)(Pool2 + 64);
        *((_QWORD *)&Src[2] + 1) = *(_QWORD *)(Pool2 + 48);
        DWORD2(Src[3]) = *(_DWORD *)(Pool2 + 32);
        Src[1] = *(_OWORD *)(Pool2 + 8);
        *((_QWORD *)&Src[4] + 1) = *(_QWORD *)(Pool2 + 72);
        DWORD1(Src[4]) = *(_DWORD *)(Pool2 + 84);
        LOBYTE(Src[5]) = *(_BYTE *)(a1 + 120);
        if ( SLOBYTE(Src[5]) > 0 )
        {
          v24 = (char *)&Src[5] + 2;
          goto LABEL_103;
        }
        goto LABEL_104;
      }
      *(_QWORD *)&Src[5] = 0;
      HIDWORD(Src[3]) = *(unsigned __int16 *)(a1 + 80);
      *(_QWORD *)&Src[0] = v10 + HIDWORD(Src[3]);
      *(_QWORD *)&Src[3] = *(_QWORD *)(Pool2 + 40);
      *(_QWORD *)&Src[2] = *(_QWORD *)(Pool2 + 24);
      *((_QWORD *)&Src[0] + 1) = *(_QWORD *)Pool2;
      LODWORD(Src[4]) = *(_DWORD *)(Pool2 + 64);
      *((_QWORD *)&Src[2] + 1) = *(_QWORD *)(Pool2 + 48);
      DWORD2(Src[3]) = *(_DWORD *)(Pool2 + 32);
      Src[1] = *(_OWORD *)(Pool2 + 8);
      *((_QWORD *)&Src[4] + 1) = *(_QWORD *)(Pool2 + 72);
      DWORD1(Src[4]) = *(_DWORD *)(Pool2 + 84);
      goto LABEL_100;
    }
    if ( a3 != 60 )
    {
      switch ( a3 )
      {
        case 1:
          HIDWORD(Src[3]) = *(unsigned __int16 *)(a1 + 80);
          LODWORD(Src[0]) = v10 + HIDWORD(Src[3]);
          *(_QWORD *)&Src[3] = *(_QWORD *)(Pool2 + 40);
          *(_QWORD *)&Src[2] = *(_QWORD *)(Pool2 + 24);
          *((_QWORD *)&Src[0] + 1) = *(_QWORD *)Pool2;
          *(_QWORD *)&Src[4] = 0;
          break;
        case 2:
          HIDWORD(Src[3]) = *(unsigned __int16 *)(a1 + 80);
          LODWORD(Src[0]) = v10 + HIDWORD(Src[3]);
          *(_QWORD *)&Src[3] = *(_QWORD *)(Pool2 + 40);
          *(_QWORD *)&Src[2] = *(_QWORD *)(Pool2 + 24);
          *((_QWORD *)&Src[0] + 1) = *(_QWORD *)Pool2;
          *(_QWORD *)&Src[4] = *(unsigned int *)(Pool2 + 64);
          break;
        case 3:
          memset(Src, 0, 0x60u);
          HIDWORD(Src[3]) = *(unsigned __int16 *)(a1 + 80);
          LODWORD(Src[0]) = v10 + HIDWORD(Src[3]);
          *(_QWORD *)&Src[3] = *(_QWORD *)(Pool2 + 40);
          *(_QWORD *)&Src[2] = *(_QWORD *)(Pool2 + 24);
          *((_QWORD *)&Src[0] + 1) = *(_QWORD *)Pool2;
          LODWORD(Src[4]) = *(_DWORD *)(Pool2 + 64);
          *((_QWORD *)&Src[2] + 1) = *(_QWORD *)(Pool2 + 48);
          DWORD2(Src[3]) = *(_DWORD *)(Pool2 + 32);
          Src[1] = *(_OWORD *)(Pool2 + 8);
          BYTE4(Src[4]) = *(_BYTE *)(a1 + 120);
          if ( SBYTE4(Src[4]) > 0 )
            memmove((char *)&Src[4] + 6, (const void *)(a1 + 124), *(unsigned int *)(a1 + 120));
LABEL_34:
          v15 = Src;
          goto LABEL_22;
        case 12:
          v15 = v29;
          v30 = *(unsigned __int16 *)(a1 + 80);
          v29[0] = v10 + v30;
          v31 = 0;
          v29[1] = 0;
          goto LABEL_22;
        case 37:
          memset(Src, 0, 0x70u);
          HIDWORD(Src[3]) = *(unsigned __int16 *)(a1 + 80);
          LODWORD(Src[0]) = v10 + HIDWORD(Src[3]);
          *(_QWORD *)&Src[3] = *(_QWORD *)(Pool2 + 40);
          *(_QWORD *)&Src[2] = *(_QWORD *)(Pool2 + 24);
          *((_QWORD *)&Src[0] + 1) = *(_QWORD *)Pool2;
          LODWORD(Src[4]) = *(_DWORD *)(Pool2 + 64);
          *((_QWORD *)&Src[2] + 1) = *(_QWORD *)(Pool2 + 48);
          DWORD2(Src[3]) = *(_DWORD *)(Pool2 + 32);
          Src[1] = *(_OWORD *)(Pool2 + 8);
          *(_QWORD *)&Src[6] = *(_QWORD *)(Pool2 + 72);
          BYTE4(Src[4]) = *(_BYTE *)(a1 + 120);
          if ( SBYTE4(Src[4]) > 0 )
          {
            v24 = (char *)&Src[4] + 6;
LABEL_103:
            memmove(v24, (const void *)(a1 + 124), *(unsigned int *)(a1 + 120));
          }
LABEL_104:
          v15 = Src;
          goto LABEL_22;
        case 38:
          DWORD1(Src[4]) = 0;
          *(_QWORD *)&Src[5] = 0;
          HIDWORD(Src[3]) = *(unsigned __int16 *)(a1 + 80);
          *(_QWORD *)&Src[0] = v10 + HIDWORD(Src[3]);
          *(_QWORD *)&Src[3] = *(_QWORD *)(Pool2 + 40);
          *(_QWORD *)&Src[2] = *(_QWORD *)(Pool2 + 24);
          *((_QWORD *)&Src[0] + 1) = *(_QWORD *)Pool2;
          LODWORD(Src[4]) = *(_DWORD *)(Pool2 + 64);
          *((_QWORD *)&Src[2] + 1) = *(_QWORD *)(Pool2 + 48);
          DWORD2(Src[3]) = *(_DWORD *)(Pool2 + 32);
          Src[1] = *(_OWORD *)(Pool2 + 8);
          *((_QWORD *)&Src[4] + 1) = *(_QWORD *)(Pool2 + 72);
LABEL_100:
          v15 = Src;
          goto LABEL_22;
        default:
          goto LABEL_110;
      }
      v15 = Src;
      *((_QWORD *)&Src[2] + 1) = *(_QWORD *)(Pool2 + 48);
      DWORD2(Src[3]) = *(_DWORD *)(Pool2 + 32);
      Src[1] = *(_OWORD *)(Pool2 + 8);
      DWORD1(Src[0]) = 0;
      goto LABEL_22;
    }
    v25 = *(_OWORD *)(Pool2 + 96);
    *((_QWORD *)&Src[5] + 1) = 0;
    HIDWORD(Src[3]) = *(unsigned __int16 *)(a1 + 80);
    *(_QWORD *)&Src[0] = v10 + HIDWORD(Src[3]);
    *(_QWORD *)&Src[3] = *(_QWORD *)(Pool2 + 40);
    *(_QWORD *)&Src[2] = *(_QWORD *)(Pool2 + 24);
    *((_QWORD *)&Src[0] + 1) = *(_QWORD *)Pool2;
    LODWORD(Src[4]) = *(_DWORD *)(Pool2 + 64);
    *((_QWORD *)&Src[2] + 1) = *(_QWORD *)(Pool2 + 48);
    DWORD2(Src[3]) = *(_DWORD *)(Pool2 + 32);
    Src[1] = *(_OWORD *)(Pool2 + 8);
    DWORD1(Src[4]) = *(_DWORD *)(Pool2 + 84);
    *(_OWORD *)((char *)&Src[4] + 8) = v25;
    goto LABEL_34;
  }
  v13 = -2147483643;
LABEL_26:
  ExFreePoolWithTag((PVOID)Pool2, 0x65644642u);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x14001bbb4  mov     [rsp-8+arg_8], rbx
0x14001bbb9  push    rbp
0x14001bbba  push    rsi
0x14001bbbb  push    rdi
0x14001bbbc  push    r12
0x14001bbbe  push    r13
0x14001bbc0  push    r14
0x14001bbc2  push    r15
0x14001bbc4  lea     rbp, [rsp-17h]
0x14001bbc9  sub     rsp, 100h
0x14001bbd0  mov     rax, cs:__security_cookie
0x14001bbd7  xor     rax, rsp
0x14001bbda  mov     [rbp+47h+var_40], rax
0x14001bbde  mov     rax, [rbp+47h+arg_28]
0x14001bbe2  mov     r15d, r8d
0x14001bbe5  mov     r13, [rbp+47h+arg_20]
0x14001bbe9  mov     r12b, dl
0x14001bbec  mov     rsi, rcx
0x14001bbef  mov     [rsp+130h+var_D8], rax
0x14001bbf4  mov     edx, 70h ; 'p'
0x14001bbf9  mov     [rsp+130h+var_E0], r9d
0x14001bbfe  mov     ecx, 100h
0x14001bc03  mov     r8d, 65644642h
0x14001bc09  call    cs:__imp_ExAllocatePool2
0x14001bc10  nop     dword ptr [rax+rax+00h]
0x14001bc15  mov     rbx, rax
0x14001bc18  test    rax, rax
0x14001bc1b  jz      loc_14001C1C7
0x14001bc21  xor     r14d, r14d
0x14001bc24  cmp     r15d, 3Ch ; '<'
0x14001bc28  jg      loc_14001C0B2
0x14001bc2e  jz      loc_14001C1DC
0x14001bc34  mov     ecx, r15d
0x14001bc37  sub     ecx, 1
0x14001bc3a  jz      loc_14001C1D2
0x14001bc40  sub     ecx, 1
0x14001bc43  jz      loc_14001C108
0x14001bc49  sub     ecx, 1
0x14001bc4c  jnz     loc_14001C0EA
0x14001bc52  lea     edi, [rcx+5Eh]
0x14001bc55  mov     r14d, edi
0x14001bc58  movzx   eax, word ptr [rsi+50h]
0x14001bc5c  mov     ecx, [rsp+130h+var_E0]
0x14001bc60  add     eax, r14d
0x14001bc63  cmp     ecx, eax
0x14001bc65  jb      loc_14001C20B
0x14001bc6b  cmp     ecx, r14d
0x14001bc6e  jb      loc_14001C21F
0x14001bc74  mov     rdx, [rsi+68h]; FileObject
0x14001bc78  lea     r8, WPP_RECORDER_INITIALIZED
0x14001bc7f  xor     r12d, r12d
0x14001bc82  lea     r10, aOnecoreBaseFsW_2; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x14001bc89  lea     r11, WPP_7c51d40b00ec3a3e74a53df28c1d8c0d_Traceguids
0x14001bc90  test    rdx, rdx
0x14001bc93  jnz     loc_14001BED7
0x14001bc99  mov     rax, [rsi+0B8h]
0x14001bca0  mov     [rbx+18h], rax
0x14001bca4  mov     rax, [rsi+0A0h]
0x14001bcab  mov     [rbx], rax
0x14001bcae  mov     rax, [rsi+0A8h]
0x14001bcb5  mov     [rbx+8], rax
0x14001bcb9  mov     rax, [rsi+0B0h]
0x14001bcc0  mov     [rbx+10h], rax
0x14001bcc4  mov     eax, [rsi+0D0h]
0x14001bcca  mov     [rbx+20h], eax
0x14001bccd  mov     rax, [rsi+0C8h]
0x14001bcd4  mov     [rbx+28h], rax
0x14001bcd8  mov     rax, [rsi+0C0h]
0x14001bcdf  mov     [rbx+30h], rax
0x14001bce3  mov     eax, [rsi+0D8h]
0x14001bce9  mov     [rbx+40h], eax
0x14001bcec  mov     rax, [rsi+0E0h]
0x14001bcf3  mov     [rbx+48h], rax
0x14001bcf7  movups  xmm0, xmmword ptr [rsi+0E8h]
0x14001bcfe  movdqu  xmmword ptr [rbx+60h], xmm0
0x14001bd03  mov     eax, [rsi+0DCh]
0x14001bd09  mov     [rbx+54h], eax
0x14001bd0c  cmp     r15d, 3Ch ; '<'
0x14001bd10  jle     loc_14001BE45
0x14001bd16  mov     ecx, r15d
0x14001bd19  sub     ecx, 3Fh ; '?'
0x14001bd1c  jz      loc_14001C863
0x14001bd22  sub     ecx, 0Fh
0x14001bd25  jz      loc_14001C4FE
0x14001bd2b  sub     ecx, 1
0x14001bd2e  jz      loc_14001C7EB
0x14001bd34  sub     ecx, 1
0x14001bd37  jz      loc_14001C77A
0x14001bd3d  cmp     ecx, 1
0x14001bd40  jnz     loc_14001C71F
0x14001bd46  lea     r8d, [rcx+7Fh]; Size
0x14001bd4a  xor     edx, edx; Val
0x14001bd4c  lea     rcx, [rbp+47h+Src]; void *
0x14001bd50  call    memset
0x14001bd55  movzx   eax, word ptr [rsi+50h]
0x14001bd59  movups  xmm0, xmmword ptr [rbx+60h]
0x14001bd5d  mov     [rbp+47h+var_84], eax
0x14001bd60  add     eax, r14d
0x14001bd63  mov     [rbp+47h+Src], eax
0x14001bd66  mov     rax, [rbx+28h]
0x14001bd6a  mov     [rbp+47h+var_90], rax
0x14001bd6e  mov     rax, [rbx+18h]
0x14001bd72  mov     [rbp+47h+var_A0], rax
0x14001bd76  mov     rax, [rbx]
0x14001bd79  mov     [rbp+47h+var_B8], rax
0x14001bd7d  mov     eax, [rbx+40h]
0x14001bd80  mov     dword ptr [rbp+47h+var_80], eax
0x14001bd83  mov     rax, [rbx+30h]
0x14001bd87  mov     [rbp+47h+var_98], rax
0x14001bd8b  mov     eax, [rbx+20h]
0x14001bd8e  mov     [rbp+47h+var_88], eax
0x14001bd91  mov     rax, [rbx+8]
0x14001bd95  mov     [rbp+47h+var_B0], rax
0x14001bd99  mov     rax, [rbx+10h]
0x14001bd9d  mov     [rbp+47h+var_A8], rax
0x14001bda1  mov     rax, [rbx+48h]
0x14001bda5  mov     qword ptr [rbp+47h+var_78], rax
0x14001bda9  mov     eax, [rbx+54h]
0x14001bdac  mov     dword ptr [rbp+47h+var_80+4], eax
0x14001bdaf  mov     al, [rsi+78h]
0x14001bdb2  mov     byte ptr [rbp+47h+var_60], al
0x14001bdb5  movdqu  [rbp+47h+var_78+8], xmm0
0x14001bdba  test    al, al
0x14001bdbc  jg      loc_14001C764
0x14001bdc2  lea     rdx, [rbp+47h+Src]; Src
0x14001bdc6  mov     r8, rdi; Size
0x14001bdc9  mov     rcx, r13; void *
0x14001bdcc  call    memmove
0x14001bdd1  mov     rax, [rsp+130h+var_D8]
0x14001bdd6  mov     ecx, [rsp+130h+var_E0]
0x14001bdda  mov     [rax], r14d
0x14001bddd  movzx   r15d, word ptr [rsi+50h]
0x14001bde2  lea     eax, [r14+r15]
0x14001bde6  cmp     ecx, eax
0x14001bde8  jb      loc_14001C8ED
0x14001bdee  mov     rdx, [rsi+58h]; Src
0x14001bdf2  lea     rcx, [rdi+r13]; void *
0x14001bdf6  mov     r8d, r15d; Size
0x14001bdf9  call    memmove
0x14001bdfe  mov     rax, [rsp+130h+var_D8]
0x14001be03  add     [rax], r15d
0x14001be06  mov     edx, 65644642h; Tag
0x14001be0b  mov     rcx, rbx; P
0x14001be0e  call    cs:__imp_ExFreePoolWithTag
0x14001be15  nop     dword ptr [rax+rax+00h]
0x14001be1a  mov     eax, r12d
0x14001be1d  mov     rcx, [rbp+47h+var_40]
0x14001be21  xor     rcx, rsp; StackCookie
0x14001be24  call    __security_check_cookie
0x14001be29  mov     rbx, [rsp+130h+arg_8]
0x14001be31  add     rsp, 100h
0x14001be38  pop     r15
0x14001be3a  pop     r14
0x14001be3c  pop     r13
0x14001be3e  pop     r12
0x14001be40  pop     rdi
0x14001be41  pop     rsi
0x14001be42  pop     rbp
0x14001be43  retn
0x14001be45  jz      loc_14001C6BA
0x14001be4b  mov     ecx, r15d
0x14001be4e  sub     ecx, 1
0x14001be51  jz      loc_14001C660
0x14001be57  sub     ecx, 1
0x14001be5a  jz      loc_14001C62D
0x14001be60  sub     ecx, 1
0x14001be63  jnz     loc_14001C485
0x14001be69  lea     r8d, [rcx+60h]; Size
0x14001be6d  xor     edx, edx; Val
0x14001be6f  lea     rcx, [rbp+47h+Src]; void *
0x14001be73  call    memset
0x14001be78  movzx   eax, word ptr [rsi+50h]
0x14001be7c  mov     [rbp+47h+var_84], eax
0x14001be7f  add     eax, r14d
0x14001be82  mov     [rbp+47h+Src], eax
0x14001be85  mov     rax, [rbx+28h]
0x14001be89  mov     [rbp+47h+var_90], rax
0x14001be8d  mov     rax, [rbx+18h]
0x14001be91  mov     [rbp+47h+var_A0], rax
0x14001be95  mov     rax, [rbx]
0x14001be98  mov     [rbp+47h+var_B8], rax
0x14001be9c  mov     eax, [rbx+40h]
0x14001be9f  mov     dword ptr [rbp+47h+var_80], eax
0x14001bea2  mov     rax, [rbx+30h]
0x14001bea6  mov     [rbp+47h+var_98], rax
0x14001beaa  mov     eax, [rbx+20h]
0x14001bead  mov     [rbp+47h+var_88], eax
0x14001beb0  mov     rax, [rbx+8]
0x14001beb4  mov     [rbp+47h+var_B0], rax
0x14001beb8  mov     rax, [rbx+10h]
0x14001bebc  mov     [rbp+47h+var_A8], rax
0x14001bec0  mov     al, [rsi+78h]
0x14001bec3  mov     byte ptr [rbp+47h+var_80+4], al
0x14001bec6  test    al, al
0x14001bec8  jg      loc_14001C617
0x14001bece  lea     rdx, [rbp+47h+Src]
0x14001bed2  jmp     loc_14001BDC6
0x14001bed7  cmp     r15d, 0Ch
0x14001bedb  jz      loc_14001C2F7
0x14001bee1  mov     rcx, [rsi+48h]; Instance
0x14001bee5  mov     r9d, 28h ; '('; Length
0x14001beeb  mov     [rsp+130h+LengthReturned], r12; LengthReturned
0x14001bef0  mov     r8, rbx; FileInformation
0x14001bef3  mov     [rsp+130h+FileInformationClass], 4; FileInformationClass
0x14001befb  call    cs:__imp_FltQueryInformationFile
0x14001bf02  nop     dword ptr [rax+rax+00h]
0x14001bf07  test    eax, eax
0x14001bf09  js      loc_14001C22A
0x14001bf0f  and     dword ptr [rbx+20h], 0FFFFFFF9h
0x14001bf13  lea     r8, [rbx+28h]; FileInformation
0x14001bf17  mov     rdx, [rsi+68h]; FileObject
0x14001bf1b  mov     r9d, 18h; Length
0x14001bf21  mov     rcx, [rsi+48h]; Instance
0x14001bf25  mov     [rsp+130h+LengthReturned], r12; LengthReturned
0x14001bf2a  mov     [rsp+130h+FileInformationClass], 5; FileInformationClass
0x14001bf32  call    cs:__imp_FltQueryInformationFile
0x14001bf39  nop     dword ptr [rax+rax+00h]
0x14001bf3e  mov     r12d, eax
0x14001bf41  test    eax, eax
0x14001bf43  js      loc_14001C28B
0x14001bf49  lea     eax, [r15-2]
0x14001bf4d  cmp     eax, 1
0x14001bf50  ja      loc_14001C2ED
0x14001bf56  mov     rdx, [rsi+68h]; FileObject
0x14001bf5a  lea     r8, [rbx+40h]; FileInformation
0x14001bf5e  mov     rcx, [rsi+48h]; Instance
0x14001bf62  mov     r9d, 4; Length
0x14001bf68  mov     [rsp+130h+LengthReturned], 0; LengthReturned
0x14001bf71  mov     [rsp+130h+FileInformationClass], 7; FileInformationClass
0x14001bf79  call    cs:__imp_FltQueryInformationFile
0x14001bf80  nop     dword ptr [rax+rax+00h]
0x14001bf85  mov     r12d, eax
0x14001bf88  test    eax, eax
0x14001bf8a  js      loc_14001C31D
0x14001bf90  lea     eax, [r15-25h]
0x14001bf94  cmp     eax, 1
0x14001bf97  jbe     loc_14001C112
0x14001bf9d  lea     eax, [r15-4Eh]
0x14001bfa1  cmp     eax, 2
0x14001bfa4  jbe     loc_14001C112
0x14001bfaa  cmp     r15d, 51h ; 'Q'
0x14001bfae  jz      loc_14001C112
0x14001bfb4  lea     eax, [r15-3Ch]
0x14001bfb8  cmp     eax, 15h
0x14001bfbb  ja      loc_14001C08B
0x14001bfc1  mov     ecx, 300009h
0x14001bfc6  bt      ecx, eax
0x14001bfc9  jnb     loc_14001C08B
0x14001bfcf  mov     rdx, [rsi+68h]; FileObject
0x14001bfd3  lea     r8, [rbx+58h]; FileInformation
0x14001bfd7  mov     rcx, [rsi+48h]; Instance
0x14001bfdb  mov     r9d, 18h; Length
0x14001bfe1  mov     [rsp+130h+LengthReturned], 0; LengthReturned
0x14001bfea  mov     [rsp+130h+FileInformationClass], 3Bh ; ';'; FileInformationClass
0x14001bff2  call    cs:__imp_FltQueryInformationFile
0x14001bff9  nop     dword ptr [rax+rax+00h]
0x14001bffe  mov     r12d, eax
0x14001c001  mov     eax, 0C00000BBh
0x14001c006  cmp     r12d, eax
0x14001c009  jnz     loc_14001C37F
0x14001c00f  lea     rcx, WPP_RECORDER_INITIALIZED
0x14001c016  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14001c01d  jz      short loc_14001C067
0x14001c01f  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c026  mov     r9d, 17h
0x14001c02c  mov     [rsp+130h+var_F0], 3Bh ; ';'
0x14001c034  mov     dl, 4
0x14001c036  mov     [rsp+130h+var_F8], eax
0x14001c03a  lea     rax, aOnecoreBaseFsW_2; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x14001c041  mov     [rsp+130h+var_100], 50Ah
0x14001c049  mov     rcx, [rcx+40h]
0x14001c04d  lea     r8d, [r9-0Bh]
0x14001c051  mov     [rsp+130h+LengthReturned], rax
0x14001c056  lea     rax, WPP_7c51d40b00ec3a3e74a53df28c1d8c0d_Traceguids
0x14001c05d  mov     qword ptr [rsp+130h+FileInformationClass], rax
0x14001c062  call    WPP_RECORDER_SF_sDdd
0x14001c067  mov     qword ptr [rbx+60h], 0FFFFFFFFFFFFFFFFh
0x14001c06f  mov     qword ptr [rbx+68h], 0FFFFFFFFFFFFFFFFh
0x14001c077  cmp     r15d, 3Ch ; '<'
0x14001c07b  jz      loc_14001C3EA
0x14001c081  cmp     r15d, 3Fh ; '?'
0x14001c085  jz      loc_14001C3EA
0x14001c08b  lea     eax, [r15-4Eh]
0x14001c08f  cmp     eax, 3
0x14001c092  jbe     loc_14001C3EA
0x14001c098  lea     r8, WPP_RECORDER_INITIALIZED
0x14001c09f  lea     r11, WPP_7c51d40b00ec3a3e74a53df28c1d8c0d_Traceguids
0x14001c0a6  lea     r10, aOnecoreBaseFsW_2; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x14001c0ad  jmp     loc_14001BD0C
0x14001c0b2  mov     ecx, r15d
0x14001c0b5  sub     ecx, 3Fh ; '?'
0x14001c0b8  jz      loc_14001C201
0x14001c0be  sub     ecx, 0Fh
0x14001c0c1  jz      loc_14001C1BD
0x14001c0c7  sub     ecx, 1
0x14001c0ca  jz      loc_14001C1F7
0x14001c0d0  sub     ecx, 1
0x14001c0d3  jz      loc_14001C1ED
0x14001c0d9  cmp     ecx, 1
0x14001c0dc  jnz     loc_14001C1E6
  ... truncated ...
```
