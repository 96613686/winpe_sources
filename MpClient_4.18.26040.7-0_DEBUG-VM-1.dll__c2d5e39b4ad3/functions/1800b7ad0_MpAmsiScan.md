# MpAmsiScan

- ea: `0x1800b7ad0`
- end: `0x1800b8ef7`
- name: `MpAmsiScan`
- size: `5159`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: `service_task, installer_update`

## callers

- `0x1800b78e0`

## callees

- `0x1800016c0`
- `0x180001e54`
- `0x180002110`
- `0x18001bb0c`
- `0x18001bb14`
- `0x18003b830`
- `0x18003bcc8`
- `0x180072da4`
- `0x180073384`
- `0x1800733a8`
- `0x180078030`
- `0x180078724`
- `0x18007ad18`
- `0x18007b188`
- `0x18007c484`
- `0x180089aa8`
- `0x18008e8e4`
- `0x1800b63fc`
- `0x1800b642c`
- `0x1800b6fb4`
- `0x1800b7ad0`
- `0x1800b9c58`
- `0x1800cdfec`
- `0x180105a1c`
- `0x180112ee0`
- `0x180125920`
- `0x1801259a0`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x1800b8872`
- `KERNEL32!GetCurrentProcess` at `0x1800b8872`
- `RPCRT4!NdrClientCall3` at `0x1800b8bc6`
- `RPCRT4!NdrClientCall3` at `0x1800b8e0f`
- `RPCRT4!NdrClientCall3` at `0x1800b8bc6`
- `RPCRT4!NdrClientCall3` at `0x1800b8e0f`

## string_xrefs

- `0x1800b8c90`: `MpService_ForceHips`

## pseudocode

```c
__int64 __fastcall MpAmsiScan(__int64 a1, __int64 a2, __int64 a3)
{
  volatile signed __int32 *v7; // r12
  int v8; // ebx
  void *v9; // rsi
  unsigned int v10; // r15d
  void *v11; // rbx
  int v12; // edi
  _WORD *v13; // rdi
  unsigned int v14; // eax
  unsigned int v15; // r15d
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  int v18; // r15d
  void *v19; // rcx
  unsigned int v20; // eax
  _QWORD *v21; // rcx
  unsigned __int64 v22; // rax
  struct _RTL_CRITICAL_SECTION *v23; // rsi
  int v24; // esi
  _QWORD *v25; // rcx
  __int64 v26; // rdx
  unsigned int v27; // eax
  __int64 v28; // r8
  _QWORD *v29; // rcx
  unsigned int v30; // eax
  __int64 v31; // r8
  _QWORD *v32; // rcx
  signed int Pointer; // r14d
  unsigned int v34; // eax
  unsigned int v35; // eax
  HANDLE CurrentProcess; // rax
  struct _RTL_CRITICAL_SECTION *v37; // r14
  int v38; // eax
  volatile signed __int32 *v39; // r15
  _QWORD *v40; // rcx
  __int64 v41; // rdx
  _QWORD *v42; // rax
  _DWORD *v43; // rcx
  int v44; // [rsp+D0h] [rbp-80h] BYREF
  int v45; // [rsp+D4h] [rbp-7Ch] BYREF
  __int64 v46; // [rsp+D8h] [rbp-78h] BYREF
  __int64 v47; // [rsp+E0h] [rbp-70h] BYREF
  __int64 v48; // [rsp+E8h] [rbp-68h] BYREF
  LPVOID v49; // [rsp+F0h] [rbp-60h] BYREF
  __int64 v50; // [rsp+F8h] [rbp-58h] BYREF
  __int64 v51; // [rsp+100h] [rbp-50h] BYREF
  __int64 v52; // [rsp+108h] [rbp-48h] BYREF
  __int64 v53; // [rsp+110h] [rbp-40h] BYREF
  __int64 v54; // [rsp+118h] [rbp-38h] BYREF
  __int64 v55; // [rsp+120h] [rbp-30h] BYREF
  __int64 v56; // [rsp+128h] [rbp-28h] BYREF
  __int64 v57; // [rsp+130h] [rbp-20h] BYREF
  __int64 v58; // [rsp+138h] [rbp-18h] BYREF
  __int64 v59; // [rsp+140h] [rbp-10h] BYREF
  __int64 v60; // [rsp+148h] [rbp-8h] BYREF
  __int64 v61; // [rsp+150h] [rbp+0h] BYREF
  __int64 v62; // [rsp+158h] [rbp+8h] BYREF
  _QWORD v63[2]; // [rsp+160h] [rbp+10h] BYREF
  int v64; // [rsp+170h] [rbp+20h] BYREF
  void *v65; // [rsp+178h] [rbp+28h] BYREF
  unsigned __int64 v66; // [rsp+180h] [rbp+30h] BYREF
  void *v67; // [rsp+188h] [rbp+38h]
  _WORD *v68; // [rsp+190h] [rbp+40h]
  __int64 v69; // [rsp+198h] [rbp+48h]
  __int64 v70; // [rsp+1A0h] [rbp+50h] BYREF
  __int64 v71; // [rsp+1A8h] [rbp+58h] BYREF
  __int64 v72; // [rsp+1B0h] [rbp+60h] BYREF
  __int64 v73; // [rsp+1B8h] [rbp+68h] BYREF
  __int64 v74; // [rsp+1C0h] [rbp+70h] BYREF
  int v75; // [rsp+1D0h] [rbp+80h] BYREF
  int *v76; // [rsp+1D8h] [rbp+88h]
  _BYTE v77[16]; // [rsp+210h] [rbp+C0h] BYREF
  unsigned int v78; // [rsp+220h] [rbp+D0h] BYREF
  _BYTE v79[4]; // [rsp+224h] [rbp+D4h] BYREF
  LPVOID lpMem; // [rsp+228h] [rbp+D8h] BYREF
  int v81; // [rsp+230h] [rbp+E0h] BYREF
  int v82; // [rsp+234h] [rbp+E4h] BYREF
  __int64 v83; // [rsp+238h] [rbp+E8h] BYREF
  __int128 v84; // [rsp+240h] [rbp+F0h] BYREF

  if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 4) != 0 )
    sub_180073384(*((_QWORD *)off_18019DE80 + 2), 41, &stru_180147768);
  if ( !a1 || !a2 || !a3 )
    return 2147942487LL;
  if ( *(_DWORD *)a1 != 1 )
    return 2147942406LL;
  *(_QWORD *)a3 = 1;
  v50 = 0;
  v63[0] = 0;
  v57 = 0;
  v7 = *(volatile signed __int32 **)(a1 + 8);
  _InterlockedIncrement(v7);
  v8 = sub_180078724(0, v7, &v50);
  if ( v8 < 0 )
    goto LABEL_10;
  sub_1801259A0(&v75, 0, 72);
  sub_1801259A0(&v64, 0, 80);
  v9 = 0;
  v49 = 0;
  v75 = 4;
  v76 = &v64;
  v64 = 80;
  v78 = 0;
  v79[0] = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _BYTE *, unsigned int *))(*(_QWORD *)a2 + 24LL))(
         a2,
         0,
         1,
         v79,
         &v78);
  if ( v8 != -2147024774 )
  {
    if ( v8 >= 0 )
      v8 = -2147024809;
    goto LABEL_245;
  }
  if ( (v78 & 1) != 0 || v78 <= 2 )
  {
LABEL_245:
    if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
      sub_1800733A8(*((_QWORD *)off_18019DE80 + 2), 42, &stru_180147768, (unsigned int)v8);
    goto LABEL_10;
  }
  lpMem = 0;
  v10 = v78 >> 1;
  v8 = sub_1800B642C(&lpMem, v78 >> 1);
  if ( v8 < 0 )
  {
    if ( lpMem )
      sub_18003BCC8(lpMem);
LABEL_10:
    if ( v7 )
      MpClose((LPVOID)v7);
    return (unsigned int)v8;
  }
  v11 = lpMem;
  v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, LPVOID, unsigned int *))(*(_QWORD *)a2 + 24LL))(
          a2,
          0,
          v78,
          lpMem,
          &v78);
  if ( v12 < 0 )
  {
    if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
      sub_1800733A8(*((_QWORD *)off_18019DE80 + 2), 43, &stru_180147768, (unsigned int)v12);
LABEL_23:
    if ( v11 )
      sub_18003BCC8(v11);
    if ( v7 )
      MpClose((LPVOID)v7);
    return (unsigned int)v12;
  }
  if ( *((_WORD *)v11 + v10 - 1) )
  {
    if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
      sub_1800733A8(*((_QWORD *)off_18019DE80 + 2), 44, &stru_180147768, 2147942487LL);
LABEL_89:
    if ( v11 )
      sub_18003BCC8(v11);
    if ( v7 )
      MpClose((LPVOID)v7);
    return 2147942487LL;
  }
  v67 = v11;
  if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 4) != 0 )
    sub_18007AD18(*((_QWORD *)off_18019DE80 + 2), 45, &stru_180147768, v11);
  v13 = 0;
  lpMem = 0;
  v78 = 0;
  v14 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _BYTE *, unsigned int *))(*(_QWORD *)a2 + 24LL))(
          a2,
          1,
          1,
          v79,
          &v78);
  if ( v14 != -2147024774 || (v78 & 1) != 0 || v78 <= 2 )
  {
    v16 = off_18019DE80;
    if ( off_18019DE80 == (_UNKNOWN *)&off_18019DE80 || (*((_BYTE *)off_18019DE80 + 28) & 4) == 0 )
      goto LABEL_53;
    v17 = 48;
LABEL_52:
    sub_1800733A8(v16[2], v17, &stru_180147768, v14);
    goto LABEL_53;
  }
  v15 = v78 >> 1;
  v12 = sub_1800B642C(&lpMem, v78 >> 1);
  if ( v12 < 0 )
  {
    if ( lpMem )
      sub_18003BCC8(lpMem);
    goto LABEL_23;
  }
  v13 = lpMem;
  v14 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, LPVOID, unsigned int *))(*(_QWORD *)a2 + 24LL))(
          a2,
          1,
          v78,
          lpMem,
          &v78);
  if ( v14 || v13[v15 - 1] )
  {
    v16 = off_18019DE80;
    if ( off_18019DE80 == (_UNKNOWN *)&off_18019DE80 || (*((_BYTE *)off_18019DE80 + 28) & 4) == 0 )
      goto LABEL_53;
    v17 = 47;
    goto LABEL_52;
  }
  v68 = v13;
  if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 4) != 0 )
    sub_18007AD18(*((_QWORD *)off_18019DE80 + 2), 46, &stru_180147768, v13);
LABEL_53:
  v18 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, unsigned __int64 *, unsigned int *))(*(_QWORD *)a2 + 24LL))(
          a2,
          2,
          8,
          &v66,
          &v78);
  if ( v18 < 0 )
  {
    if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
      sub_1800733A8(*((_QWORD *)off_18019DE80 + 2), 49, &stru_180147768, (unsigned int)v18);
    if ( v13 )
      sub_18003BCC8(v13);
    if ( !v11 )
      goto LABEL_62;
    v19 = v11;
LABEL_61:
    sub_18003BCC8(v19);
LABEL_62:
    if ( v7 )
      MpClose((LPVOID)v7);
    return (unsigned int)v18;
  }
  if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 4) != 0 )
    sub_180089AA8(*((_QWORD *)off_18019DE80 + 2), 50, &stru_180147768, v66);
  v20 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, void **, unsigned int *))(*(_QWORD *)a2 + 24LL))(
          a2,
          3,
          8,
          &v65,
          &v78);
  if ( v20 )
  {
    v21 = off_18019DE80;
    if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 4) != 0 )
    {
      sub_1800733A8(*((_QWORD *)off_18019DE80 + 2), 51, &stru_180147768, v20);
LABEL_75:
      v21 = off_18019DE80;
    }
  }
  else
  {
    v21 = off_18019DE80;
    if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 4) != 0 )
    {
      sub_180089AA8(*((_QWORD *)off_18019DE80 + 2), 52, &stru_180147768, v65);
      goto LABEL_75;
    }
  }
  if ( !v65 )
  {
    v22 = v66;
    v23 = lpCriticalSection;
    if ( v66 > 0x1000000 )
    {
      if ( lpCriticalSection )
      {
        EnterCriticalSection(lpCriticalSection);
        if ( (unsigned int)dword_18019D000 > 5
          && (*(_QWORD *)algn_18019D010 & 0x400000000000LL) != 0
          && (*(_QWORD *)&algn_18019D010[8] & 0x400000000000LL) == *(_QWORD *)&algn_18019D010[8] )
        {
          v57 = 0x1000000;
          v50 = v66;
          lpMem = v67;
          v81 = *(_DWORD *)(qword_1801A6308 + 72);
          v44 = *(_DWORD *)(qword_1801A6308 + 68);
          v45 = *(_DWORD *)(qword_1801A6308 + 64);
          LODWORD(v46) = *(unsigned __int8 *)(qword_1801A6308 + 60);
          HIDWORD(v46) = *(unsigned __int8 *)(qword_1801A6308 + 59);
          LODWORD(v47) = *(unsigned __int8 *)(qword_1801A6308 + 58);
          HIDWORD(v47) = *(unsigned __int8 *)(qword_1801A6308 + 57);
          LODWORD(v48) = *(unsigned __int8 *)(qword_1801A6308 + 56);
          v49 = *(LPVOID *)(qword_1801A6308 + 48);
          v51 = *(_QWORD *)(qword_1801A6308 + 40);
          v52 = *(_QWORD *)(qword_1801A6308 + 32);
          v53 = *(_QWORD *)(qword_1801A6308 + 24);
          v54 = *(_QWORD *)(qword_1801A6308 + 16);
          v55 = *(_QWORD *)(qword_1801A6308 + 8);
          v56 = 0x2000000;
          sub_180001E54(
            (int)&dword_18019D000,
            (int)&dword_18017D214,
            (__int64)&v56,
            (__int64)&v55,
            (__int64)&v54,
            (__int64)&v53,
            (__int64)&v52,
            (__int64)&v51,
            (__int64)&v49,
            (__int64)&v48,
            (__int64)&v47 + 4,
            (__int64)&v47,
            (__int64)&v46 + 4,
            (__int64)&v46,
            (__int64)&v45,
            (__int64)&v44,
            (__int64)&v81,
            (__int64)&lpMem,
            (__int64)&v50,
            (__int64)&v57);
        }
        LeaveCriticalSection(v23);
        v22 = v66;
        v21 = off_18019DE80;
      }
      if ( v21 != &off_18019DE80 && (*((_BYTE *)v21 + 28) & 2) != 0 )
        sub_18007B188(v21[2], 53, &stru_180147768, v22, 0x1000000);
      if ( v13 )
        sub_18003BCC8(v13);
      goto LABEL_89;
    }
    if ( lpCriticalSection )
    {
      EnterCriticalSection(lpCriticalSection);
      if ( (unsigned int)dword_18019D000 > 5
        && (*(_QWORD *)algn_18019D010 & 0x400000000000LL) != 0
        && (*(_QWORD *)&algn_18019D010[8] & 0x400000000000LL) == *(_QWORD *)&algn_18019D010[8] )
      {
        v56 = (__int64)v67;
        LODWORD(v48) = *(_DWORD *)(qword_1801A6308 + 72);
        v47 = *(_QWORD *)(qword_1801A6308 + 64);
        HIDWORD(v46) = *(unsigned __int8 *)(qword_1801A6308 + 60);
        LODWORD(v46) = *(unsigned __int8 *)(qword_1801A6308 + 59);
        v45 = *(unsigned __int8 *)(qword_1801A6308 + 58);
        v44 = *(unsigned __int8 *)(qword_1801A6308 + 57);
        v81 = *(unsigned __int8 *)(qword_1801A6308 + 56);
        v55 = *(_QWORD *)(qword_1801A6308 + 48);
        v54 = *(_QWORD *)(qword_1801A6308 + 40);
        v53 = *(_QWORD *)(qword_1801A6308 + 32);
        v52 = *(_QWORD *)(qword_1801A6308 + 24);
        v51 = *(_QWORD *)(qword_1801A6308 + 16);
        lpMem = *(LPVOID *)(qword_1801A6308 + 8);
        v58 = 0x2000000;
        sub_1800016C0(
          (int)&dword_18019D000,
          (int)&dword_18017D326,
          (__int64)&v58,
          (__int64)&lpMem,
          (__int64)&v51,
          (__int64)&v52,
          (__int64)&v53,
          (__int64)&v54,
          (__int64)&v55,
          (__int64)&v81,
          (__int64)&v44,
          (__int64)&v45,
          (__int64)&v46,
          (__int64)&v46 + 4,
          (__int64)&v47,
          (__int64)&v47 + 4,
          (__int64)&v48,
          (__int64)&v56);
      }
      LeaveCriticalSection(v23);
      v22 = v66;
    }
    v24 = sub_1800B63FC(&v49, v22);
    if ( v24 < 0 )
    {
      if ( v13 )
        sub_18003BCC8(v13);
      if ( v11 )
        sub_18003BCC8(v11);
      if ( v49 )
        sub_18003BCC8(v49);
      if ( v7 )
        MpClose((LPVOID)v7);
      return (unsigned int)v24;
    }
    v9 = v49;
    v18 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, LPVOID, unsigned int *))(*(_QWORD *)a2 + 32LL))(
            a2,
            0,
            (unsigned int)v66,
            v49,
            &v78);
    if ( v18 < 0 )
    {
      v25 = off_18019DE80;
      if ( off_18019DE80 == (_UNKNOWN *)&off_18019DE80 || (*((_BYTE *)off_18019DE80 + 28) & 1) == 0 )
        goto LABEL_115;
      v26 = 54;
LABEL_114:
      sub_1800733A8(v25[2], v26, &stru_180147768, (unsigned int)v18);
LABEL_115:
      if ( v13 )
        sub_18003BCC8(v13);
      if ( v11 )
        sub_18003BCC8(v11);
      if ( !v9 )
        goto LABEL_62;
      v19 = v9;
      goto LABEL_61;
    }
    v65 = v9;
  }
  v74 = 0;
  v18 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *, unsigned int *))(*(_QWORD *)a2 + 24LL))(
          a2,
          4,
          8,
          &v74,
          &v78);
  if ( v18 < 0 )
  {
    v25 = off_18019DE80;
    if ( off_18019DE80 == (_UNKNOWN *)&off_18019DE80 || (*((_BYTE *)off_18019DE80 + 28) & 1) == 0 )
      goto LABEL_115;
    v26 = 55;
    goto LABEL_114;
  }
  v69 = v74;
  v27 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *, unsigned int *))(*(_QWORD *)a2 + 24LL))(
          a2,
          6,
          8,
          &v70,
          &v78);
  if ( !v27 )
  {
    v34 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *, unsigned int *))(*(_QWORD *)a2 + 24LL))(
            a2,
            5,
            8,
            &v71,
            &v78);
    if ( v34 )
    {
      v29 = off_18019DE80;
      if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 4) != 0 )
      {
        sub_1800733A8(*((_QWORD *)off_18019DE80 + 2), 57, &stru_180147768, v34);
        v29 = off_18019DE80;
      }
    }
    else
    {
      if ( (unsigned __int64)(v71 - 1) <= 0xFFFFFF )
        goto LABEL_130;
      v29 = off_18019DE80;
      if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 2) != 0 )
      {
        sub_180089AA8(*((_QWORD *)off_18019DE80 + 2), 58, &stru_180147768, v71);
        v29 = off_18019DE80;
      }
      v71 = 0;
    }
    v70 = 0;
    goto LABEL_131;
  }
  v29 = off_18019DE80;
  if ( off_18019DE80 == (_UNKNOWN *)&off_18019DE80 )
    goto LABEL_134;
  if ( (*((_BYTE *)off_18019DE80 + 28) & 4) != 0 )
  {
    sub_1800733A8(*((_QWORD *)off_18019DE80 + 2), 56, &stru_180147768, v27);
LABEL_130:
    v29 = off_18019DE80;
  }
LABEL_131:
  if ( v29 != &off_18019DE80 && (*((_BYTE *)v29 + 28) & 4) != 0 )
    sub_1800B9C58(v29[2], 59, v28, v70, v71);
LABEL_134:
  v30 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *, unsigned int *))(*(_QWORD *)a2 + 24LL))(
          a2,
          8,
          8,
          &v72,
          &v78);
  if ( !v30 )
  {
    v35 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *, unsigned int *))(*(_QWORD *)a2 + 24LL))(
            a2,
            7,
            8,
            &v73,
            &v78);
    if ( v35 )
    {
      v32 = off_18019DE80;
      if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 4) != 0 )
      {
        sub_1800733A8(*((_QWORD *)off_18019DE80 + 2), 61, &stru_180147768, v35);
        v32 = off_18019DE80;
      }
    }
    else
    {
      if ( (unsigned __int64)(v73 - 1) <= 0xFFFFFF )
        goto LABEL_138;
      v32 = off_18019DE80;
      if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 2) != 0 )
      {
        sub_180089AA8(*((_QWORD *)off_18019DE80 + 2), 62, &stru_180147768, v73);
        v32 = off_18019DE80;
      }
      v73 = 0;
    }
    v72 = 0;
    goto LABEL_139;
  }
  v32 = off_18019DE80;
  if ( off_18019DE80 == (_UNKNOWN *)&off_18019DE80 )
    goto LABEL_142;
  if ( (*((_BYTE *)off_18019DE80 + 28) & 4) != 0 )
  {
    sub_1800733A8(*((_QWORD *)off_18019DE80 + 2), 60, &stru_180147768, v30);
LABEL_138:
    v32 = off_18019DE80;
  }
LABEL_139:
  if ( v32 != &off_18019DE80 && (*((_BYTE *)v32 + 28) & 4) != 0 )
    sub_1800B9C58(v32[2], 63, v31, v72, v73);
LABEL_142:
  Pointer = sub_1800B6FB4(v77);
  if ( Pointer >= 0 )
  {
    v83 = 0;
    CurrentProcess = GetCurrentProcess();
    Pointer = sub_1800CDFEC(CurrentProcess, &v83);
    if ( Pointer >= 0 )
    {
      v37 = lpCriticalSection;
      if ( lpCriticalSection )
      {
        EnterCriticalSection(lpCriticalSection);
        if ( (unsigned int)dword_18019D000 > 5
          && (*(_QWORD *)algn_18019D010 & 0x400000000000LL) != 0
          && (*(_QWORD *)&algn_18019D010[8] & 0x400000000000LL) == *(_QWORD *)&algn_18019D010[8] )
        {
          v58 = v73;
          v56 = v71;
          v55 = v69;
          LODWORD(v48) = v68 != 0;
          v54 = (__int64)v67;
          HIDWORD(v47) = (v64 & 1) == 0;
          LODWORD(v47) = *(_DWORD *)(qword_1801A6308 + 72);
          v46 = *(_QWORD *)(qword_1801A6308 + 64);
          v45 = *(unsigned __int8 *)(qword_1801A6308 + 60);
          v44 = *(unsigned __int8 *)(qword_1801A6308 + 59);
          v81 = *(unsigned __int8 *)(qword_1801A6308 + 58);
          LODWORD(v49) = *(unsigned __int8 *)(qword_1801A6308 + 57);
          LODWORD(lpMem) = *(unsigned __int8 *)(qword_1801A6308 + 56);
          v53 = *(_QWORD *)(qword_1801A6308 + 48);
          v52 = *(_QWORD *)(qword_1801A6308 + 40);
          v51 = *(_QWORD *)(qword_1801A6308 + 32);
          v59 = *(_QWORD *)(qword_1801A6308 + 24);
          v60 = *(_QWORD *)(qword_1801A6308 + 16);
          v61 = *(_QWORD *)(qword_1801A6308 + 8);
          v62 = 0x2000000;
          sub_180002110(
            (int)&dword_18019D000,
            (int)&dword_18017D419,
            (__int64)&v62,
            (__int64)&v61,
            (__int64)&v60,
            (__int64)&v59,
            (__int64)&v51,
            (__int64)&v52,
            (__int64)&v53,
            (__int64)&lpMem,
            (__int64)&v49,
            (__int64)&v81,
            (__int64)&v44,
            (__int64)&v45,
            (__int64)&v46,
            (__int64)&v46 + 4,
            (__int64)&v47,
            (__int64)&v47 + 4,
            (__int64)&v54,
            (__int64)&v48,
            (__int64)&v55,
            (__int64)&v56,
            (__int64)&v58);
        }
        LeaveCriticalSection(v37);
      }
      v84 = 0;
      v82 = 0;
      Pointer = sub_180105A1C(
                  v50,
                  (unsigned int)&v83,
                  0,
                  (unsigned int)&v75,
                  (__int64)&v84,
                  (__int64)v63,
                  (__int64)&v82);
      if ( v82 )
        Pointer = v82 | 0x80010000;
      if ( Pointer >= 0 )
      {
        v38 = sub_18008E8E4(&v57, &v84);
        Pointer = v38;
        v39 = (volatile signed __int32 *)v57;
        if ( v38 >= 0 )
        {
          while ( 1 )
          {
            v38 = (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v39 + 8LL))(v39);
            Pointer = v38;
            if ( v38 < 0 )
              break;
            lpMem = 0;
            v82 = 0;
            Pointer = (unsigned int)NdrClientCall3(
                                      (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                                      0x5Fu,
                                      0,
                                      v63[0],
                                      &lpMem,
                                      &v82).Pointer;
            if ( v82 )
              Pointer = v82 | 0x80010000;
            if ( Pointer < 0 )
            {
              if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
                sub_1800733A8(*((_QWORD *)off_18019DE80 + 2), 69, &stru_180147768, (unsigned int)Pointer);
LABEL_221:
              v43 = lpMem;
LABEL_222:
              if ( v43 )
                sub_18007C484(v43);
              goto LABEL_228;
            }
            v42 = off_18019DE80;
            if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 4) != 0 )
            {
              sub_1800733A8(*((_QWORD *)off_18019DE80 + 2), 70, &stru_180147768, *(unsigned int *)lpMem);
              v42 = off_18019DE80;
            }
            v43 = lpMem;
            if ( *(_DWORD *)lpMem == 16392 )
            {
              if ( v42 != &off_18019DE80 && (*((_BYTE *)v42 + 28) & 4) != 0 )
              {
                sub_180073384(v42[2], 71, &stru_180147768);
                v43 = lpMem;
              }
              *(_DWORD *)a3 = 0x8000;
              v42 = off_18019DE80;
            }
            Pointer = 0;
            if ( *v43 == 16400 )
            {
              v81 = 0;
              if ( (int)sub_180112EE0(L"MpService_ForceHips", 0, &v81) < 0 )
                v81 = 0;
              if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 4) != 0 )
                sub_180073384(*((_QWORD *)off_18019DE80 + 2), 72, &stru_180147768);
              *(_DWORD *)a3 = 0x4000;
              v42 = off_18019DE80;
              v43 = lpMem;
            }
            if ( *v43 == 16401 )
            {
              if ( v42 != &off_18019DE80 && (*((_BYTE *)v42 + 28) & 4) != 0 )
              {
                sub_180073384(v42[2], 73, &stru_180147768);
                v43 = lpMem;
              }
              *(_DWORD *)(a3 + 4) = 1;
              v42 = off_18019DE80;
            }
            if ( *v43 == 16389 )
            {
              if ( v42 != &off_18019DE80 && (*((_BYTE *)v42 + 28) & 4) != 0 )
              {
                sub_180073384(v42[2], 74, &stru_180147768);
                goto LABEL_221;
              }
              goto LABEL_222;
            }
            sub_18007C484(v43);
          }
          v40 = off_18019DE80;
          if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
          {
            v41 = 68;
            goto LABEL_227;
          }
        }
        else
        {
          v40 = off_18019DE80;
          if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
          {
            v41 = 67;
LABEL_227:
            sub_1800733A8(v40[2], v41, &stru_180147768, (unsigned int)v38);
          }
        }
LABEL_228:
        if ( v63[0] )
        {
          NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x60u, 0, v50, v63, &v82);
          if ( v82 )
          {
            if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
              sub_1800733A8(*((_QWORD *)off_18019DE80 + 2), 75, &stru_180147768, v82 | 0x80010000);
            sub_180072DA4(v63[0]);
          }
        }
        if ( v13 )
          sub_18003BCC8(v13);
        if ( v11 )
          sub_18003BCC8(v11);
        if ( v9 )
          sub_18003BCC8(v9);
        if ( v39 && _InterlockedExchangeAdd(v39 + 2, 0xFFFFFFFF) <= 1 )
        {
          _mm_lfence();
          (**(void (__fastcall ***)(volatile signed __int32 *, __int64))v39)(v39, 1);
        }
        goto LABEL_149;
      }
      if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
        sub_1800733A8(*((_QWORD *)off_18019DE80 + 2), 66, &stru_180147768, (unsigned int)Pointer);
    }
  }
  if ( v13 )
    sub_18003BCC8(v13);
  if ( v11 )
    sub_18003BCC8(v11);
  if ( v9 )
    sub_18003BCC8(v9);
LABEL_149:
  if ( v7 )
    MpClose((LPVOID)v7);
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x1800b7ad0  mov     [rsp-8+arg_18], rbx
0x1800b7ad5  push    rbp
0x1800b7ad6  push    rsi
0x1800b7ad7  push    rdi
0x1800b7ad8  push    r12
0x1800b7ada  push    r13
0x1800b7adc  push    r14
0x1800b7ade  push    r15
0x1800b7ae0  lea     rbp, [rsp-110h]
0x1800b7ae8  sub     rsp, 260h
0x1800b7aef  mov     rax, cs:__security_cookie
0x1800b7af6  xor     rax, rsp
0x1800b7af9  mov     [rbp+140h+var_40], rax
0x1800b7b00  mov     r13, r8
0x1800b7b03  mov     r14, rdx
0x1800b7b06  mov     r12, rcx
0x1800b7b09  lea     r15, off_18019DE80
0x1800b7b10  mov     rcx, cs:off_18019DE80
0x1800b7b17  cmp     rcx, r15
0x1800b7b1a  jz      short loc_1800B7B37
0x1800b7b1c  test    byte ptr [rcx+1Ch], 4
0x1800b7b20  jz      short loc_1800B7B37
0x1800b7b22  mov     edx, 29h ; ')'
0x1800b7b27  lea     r8, stru_180147768
0x1800b7b2e  mov     rcx, [rcx+10h]
0x1800b7b32  call    sub_180073384
0x1800b7b37  xor     edi, edi
0x1800b7b39  test    r12, r12
0x1800b7b3c  jz      loc_1800B827A
0x1800b7b42  test    r14, r14
0x1800b7b45  jz      loc_1800B827A
0x1800b7b4b  test    r13, r13
0x1800b7b4e  jz      loc_1800B827A
0x1800b7b54  cmp     dword ptr [r12], 1
0x1800b7b59  jz      short loc_1800B7B65
0x1800b7b5b  mov     eax, 80070006h
0x1800b7b60  jmp     loc_1800B827F
0x1800b7b65  mov     qword ptr [r13+0], 1
0x1800b7b6d  mov     [rbp+140h+var_198], rdi
0x1800b7b71  mov     [rbp+140h+var_130], rdi
0x1800b7b75  mov     [rbp+140h+var_160], rdi
0x1800b7b79  mov     r12, [r12+8]
0x1800b7b7e  lock inc dword ptr [r12]
0x1800b7b83  lea     r8, [rbp+140h+var_198]
0x1800b7b87  mov     rdx, r12
0x1800b7b8a  xor     ecx, ecx
0x1800b7b8c  call    sub_180078724
0x1800b7b91  mov     ebx, eax
0x1800b7b93  test    eax, eax
0x1800b7b95  jns     short loc_1800B7BAB
0x1800b7b97  test    r12, r12
0x1800b7b9a  jz      short loc_1800B7BA4
0x1800b7b9c  mov     rcx, r12; lpMem
0x1800b7b9f  call    MpClose
0x1800b7ba4  mov     eax, ebx
0x1800b7ba6  jmp     loc_1800B827F
0x1800b7bab  xor     edx, edx
0x1800b7bad  lea     r8d, [rdx+48h]
0x1800b7bb1  lea     rcx, [rbp+140h+var_C0]
0x1800b7bb8  call    sub_1801259A0
0x1800b7bbd  mov     ebx, 50h ; 'P'
0x1800b7bc2  mov     r8d, ebx
0x1800b7bc5  xor     edx, edx
0x1800b7bc7  lea     rcx, [rbp+140h+var_120]
0x1800b7bcb  call    sub_1801259A0
0x1800b7bd0  mov     rsi, rdi
0x1800b7bd3  mov     [rbp+140h+var_1A0], rdi
0x1800b7bd7  mov     [rbp+140h+var_C0], 4
0x1800b7be1  lea     rax, [rbp+140h+var_120]
0x1800b7be5  mov     [rbp+140h+var_B8], rax
0x1800b7bec  mov     [rbp+140h+var_120], ebx
0x1800b7bef  mov     [rbp+140h+var_70], edi
0x1800b7bf5  mov     [rbp+140h+var_6C], dil
0x1800b7bfc  mov     rax, [r14]
0x1800b7bff  lea     rcx, [rbp+140h+var_70]
0x1800b7c06  mov     [rsp+290h+var_270], rcx
0x1800b7c0b  lea     r9, [rbp+140h+var_6C]
0x1800b7c12  xor     edx, edx
0x1800b7c14  lea     r8d, [rbx-4Fh]
0x1800b7c18  mov     rcx, r14
0x1800b7c1b  mov     rax, [rax+18h]
0x1800b7c1f  call    cs:__guard_dispatch_icall_fptr
0x1800b7c25  mov     ebx, eax
0x1800b7c27  cmp     eax, 8007007Ah
0x1800b7c2c  jnz     loc_1800B8EB6
0x1800b7c32  mov     eax, [rbp+140h+var_70]
0x1800b7c38  test    al, 1
0x1800b7c3a  jnz     loc_1800B8EC0
0x1800b7c40  cmp     eax, 2
0x1800b7c43  jbe     loc_1800B8EC0
0x1800b7c49  mov     [rbp+140h+lpMem], rdi
0x1800b7c50  shr     eax, 1
0x1800b7c52  mov     r15d, eax
0x1800b7c55  mov     edx, eax
0x1800b7c57  lea     rcx, [rbp+140h+lpMem]
0x1800b7c5e  call    sub_1800B642C
0x1800b7c63  mov     ebx, eax
0x1800b7c65  test    eax, eax
0x1800b7c67  jns     short loc_1800B7C83
0x1800b7c69  mov     rcx, [rbp+140h+lpMem]; lpMem
0x1800b7c70  test    rcx, rcx
0x1800b7c73  jz      loc_1800B7B97
0x1800b7c79  call    sub_18003BCC8
0x1800b7c7e  jmp     loc_1800B7B97
0x1800b7c83  mov     rax, [r14]
0x1800b7c86  lea     rcx, [rbp+140h+var_70]
0x1800b7c8d  mov     [rsp+290h+var_270], rcx
0x1800b7c92  mov     rbx, [rbp+140h+lpMem]
0x1800b7c99  mov     r9, rbx
0x1800b7c9c  mov     r8d, [rbp+140h+var_70]
0x1800b7ca3  xor     edx, edx
0x1800b7ca5  mov     rcx, r14
0x1800b7ca8  mov     rax, [rax+18h]
0x1800b7cac  call    cs:__guard_dispatch_icall_fptr
0x1800b7cb2  mov     edi, eax
0x1800b7cb4  test    eax, eax
0x1800b7cb6  jns     short loc_1800B7D0A
0x1800b7cb8  mov     rcx, cs:off_18019DE80
0x1800b7cbf  lea     rax, off_18019DE80
0x1800b7cc6  cmp     rcx, rax
0x1800b7cc9  jz      short loc_1800B7CE9
0x1800b7ccb  test    byte ptr [rcx+1Ch], 1
0x1800b7ccf  jz      short loc_1800B7CE9
0x1800b7cd1  mov     edx, 2Bh ; '+'
0x1800b7cd6  mov     r9d, edi
0x1800b7cd9  lea     r8, stru_180147768
0x1800b7ce0  mov     rcx, [rcx+10h]
0x1800b7ce4  call    sub_1800733A8
0x1800b7ce9  test    rbx, rbx
0x1800b7cec  jz      short loc_1800B7CF6
0x1800b7cee  mov     rcx, rbx; lpMem
0x1800b7cf1  call    sub_18003BCC8
0x1800b7cf6  test    r12, r12
0x1800b7cf9  jz      short loc_1800B7D03
0x1800b7cfb  mov     rcx, r12; lpMem
0x1800b7cfe  call    MpClose
0x1800b7d03  mov     eax, edi
0x1800b7d05  jmp     loc_1800B827F
0x1800b7d0a  lea     eax, [r15-1]
0x1800b7d0e  xor     r15d, r15d
0x1800b7d11  cmp     [rbx+rax*2], r15w
0x1800b7d16  jz      short loc_1800B7D58
0x1800b7d18  mov     rcx, cs:off_18019DE80
0x1800b7d1f  lea     rax, off_18019DE80
0x1800b7d26  cmp     rcx, rax
0x1800b7d29  jz      loc_1800B8260
0x1800b7d2f  test    byte ptr [rcx+1Ch], 1
0x1800b7d33  jz      loc_1800B8260
0x1800b7d39  lea     edx, [r15+2Ch]
0x1800b7d3d  mov     r9d, 80070057h
0x1800b7d43  lea     r8, stru_180147768
0x1800b7d4a  mov     rcx, [rcx+10h]
0x1800b7d4e  call    sub_1800733A8
0x1800b7d53  jmp     loc_1800B8260
0x1800b7d58  mov     [rbp+140h+var_108], rbx
0x1800b7d5c  mov     rcx, cs:off_18019DE80
0x1800b7d63  lea     rax, off_18019DE80
0x1800b7d6a  cmp     rcx, rax
0x1800b7d6d  jz      short loc_1800B7D8D
0x1800b7d6f  test    byte ptr [rcx+1Ch], 4
0x1800b7d73  jz      short loc_1800B7D8D
0x1800b7d75  mov     edx, 2Dh ; '-'
0x1800b7d7a  mov     r9, rbx
0x1800b7d7d  lea     r8, stru_180147768
0x1800b7d84  mov     rcx, [rcx+10h]
0x1800b7d88  call    sub_18007AD18
0x1800b7d8d  mov     rdi, r15
0x1800b7d90  mov     [rbp+140h+lpMem], r15
0x1800b7d97  mov     [rbp+140h+var_70], r15d
0x1800b7d9e  mov     rax, [r14]
0x1800b7da1  lea     rcx, [rbp+140h+var_70]
0x1800b7da8  mov     [rsp+290h+var_270], rcx
0x1800b7dad  lea     r9, [rbp+140h+var_6C]
0x1800b7db4  mov     r15d, 1
0x1800b7dba  mov     r8d, r15d
0x1800b7dbd  mov     edx, r15d
0x1800b7dc0  mov     rcx, r14
0x1800b7dc3  mov     rax, [rax+18h]
0x1800b7dc7  call    cs:__guard_dispatch_icall_fptr
0x1800b7dcd  cmp     eax, 8007007Ah
0x1800b7dd2  jnz     loc_1800B7EBD
0x1800b7dd8  mov     ecx, [rbp+140h+var_70]
0x1800b7dde  test    r15b, cl
0x1800b7de1  jnz     loc_1800B7EBD
0x1800b7de7  cmp     ecx, 2
0x1800b7dea  jbe     loc_1800B7EBD
0x1800b7df0  shr     ecx, 1
0x1800b7df2  mov     r15d, ecx
0x1800b7df5  mov     edx, ecx
0x1800b7df7  lea     rcx, [rbp+140h+lpMem]
0x1800b7dfe  call    sub_1800B642C
0x1800b7e03  mov     edi, eax
0x1800b7e05  test    eax, eax
0x1800b7e07  jns     short loc_1800B7E23
0x1800b7e09  mov     rcx, [rbp+140h+lpMem]; lpMem
0x1800b7e10  test    rcx, rcx
0x1800b7e13  jz      loc_1800B7CE9
0x1800b7e19  call    sub_18003BCC8
0x1800b7e1e  jmp     loc_1800B7CE9
0x1800b7e23  mov     rax, [r14]
0x1800b7e26  lea     rcx, [rbp+140h+var_70]
0x1800b7e2d  mov     [rsp+290h+var_270], rcx
0x1800b7e32  mov     rdi, [rbp+140h+lpMem]
0x1800b7e39  mov     r9, rdi
0x1800b7e3c  mov     r8d, [rbp+140h+var_70]
0x1800b7e43  mov     edx, 1
0x1800b7e48  mov     rcx, r14
0x1800b7e4b  mov     rax, [rax+18h]
0x1800b7e4f  call    cs:__guard_dispatch_icall_fptr
0x1800b7e55  xor     r8d, r8d
0x1800b7e58  test    eax, eax
0x1800b7e5a  jnz     short loc_1800B7E9D
0x1800b7e5c  lea     ecx, [r15-1]
0x1800b7e60  cmp     [rdi+rcx*2], r8w
0x1800b7e65  jnz     short loc_1800B7E9D
0x1800b7e67  mov     [rbp+140h+var_100], rdi
0x1800b7e6b  mov     rcx, cs:off_18019DE80
0x1800b7e72  lea     rax, off_18019DE80
0x1800b7e79  cmp     rcx, rax
0x1800b7e7c  jz      short loc_1800B7EEE
0x1800b7e7e  test    byte ptr [rcx+1Ch], 4
0x1800b7e82  jz      short loc_1800B7EEE
0x1800b7e84  lea     edx, [r8+2Eh]
0x1800b7e88  mov     r9, rdi
0x1800b7e8b  lea     r8, stru_180147768
0x1800b7e92  mov     rcx, [rcx+10h]
0x1800b7e96  call    sub_18007AD18
0x1800b7e9b  jmp     short loc_1800B7EEE
0x1800b7e9d  mov     rcx, cs:off_18019DE80
0x1800b7ea4  lea     rdx, off_18019DE80
0x1800b7eab  cmp     rcx, rdx
0x1800b7eae  jz      short loc_1800B7EEE
0x1800b7eb0  test    byte ptr [rcx+1Ch], 4
0x1800b7eb4  jz      short loc_1800B7EEE
0x1800b7eb6  mov     edx, 2Fh ; '/'
0x1800b7ebb  jmp     short loc_1800B7EDB
0x1800b7ebd  mov     rcx, cs:off_18019DE80
0x1800b7ec4  lea     rdx, off_18019DE80
0x1800b7ecb  cmp     rcx, rdx
0x1800b7ece  jz      short loc_1800B7EEE
0x1800b7ed0  test    byte ptr [rcx+1Ch], 4
0x1800b7ed4  jz      short loc_1800B7EEE
0x1800b7ed6  mov     edx, 30h ; '0'
0x1800b7edb  mov     r9d, eax
0x1800b7ede  lea     r8, stru_180147768
0x1800b7ee5  mov     rcx, [rcx+10h]
0x1800b7ee9  call    sub_1800733A8
0x1800b7eee  mov     rax, [r14]
0x1800b7ef1  lea     rcx, [rbp+140h+var_70]
0x1800b7ef8  mov     [rsp+290h+var_270], rcx
0x1800b7efd  lea     r9, [rbp+140h+var_110]
0x1800b7f01  mov     edx, 2
0x1800b7f06  lea     r8d, [rdx+6]
0x1800b7f0a  mov     rcx, r14
0x1800b7f0d  mov     rax, [rax+18h]
0x1800b7f11  call    cs:__guard_dispatch_icall_fptr
0x1800b7f17  mov     r15d, eax
0x1800b7f1a  test    eax, eax
0x1800b7f1c  jns     short loc_1800B7F7E
0x1800b7f1e  mov     rcx, cs:off_18019DE80
0x1800b7f25  lea     rax, off_18019DE80
0x1800b7f2c  cmp     rcx, rax
0x1800b7f2f  jz      short loc_1800B7F4F
0x1800b7f31  test    byte ptr [rcx+1Ch], 1
0x1800b7f35  jz      short loc_1800B7F4F
0x1800b7f37  mov     edx, 31h ; '1'
0x1800b7f3c  mov     r9d, r15d
0x1800b7f3f  lea     r8, stru_180147768
0x1800b7f46  mov     rcx, [rcx+10h]
0x1800b7f4a  call    sub_1800733A8
0x1800b7f4f  test    rdi, rdi
0x1800b7f52  jz      short loc_1800B7F5C
0x1800b7f54  mov     rcx, rdi; lpMem
0x1800b7f57  call    sub_18003BCC8
0x1800b7f5c  test    rbx, rbx
0x1800b7f5f  jz      short loc_1800B7F69
0x1800b7f61  mov     rcx, rbx; lpMem
0x1800b7f64  call    sub_18003BCC8
0x1800b7f69  test    r12, r12
0x1800b7f6c  jz      short loc_1800B7F76
0x1800b7f6e  mov     rcx, r12; lpMem
0x1800b7f71  call    MpClose
0x1800b7f76  mov     eax, r15d
0x1800b7f79  jmp     loc_1800B827F
0x1800b7f7e  mov     rcx, cs:off_18019DE80
0x1800b7f85  lea     rax, off_18019DE80
0x1800b7f8c  cmp     rcx, rax
0x1800b7f8f  jz      short loc_1800B7FB0
0x1800b7f91  test    byte ptr [rcx+1Ch], 4
0x1800b7f95  jz      short loc_1800B7FB0
0x1800b7f97  mov     edx, 32h ; '2'
0x1800b7f9c  mov     r9, [rbp+140h+var_110]
0x1800b7fa0  lea     r8, stru_180147768
0x1800b7fa7  mov     rcx, [rcx+10h]
0x1800b7fab  call    sub_180089AA8
0x1800b7fb0  mov     rax, [r14]
0x1800b7fb3  lea     rcx, [rbp+140h+var_70]
0x1800b7fba  mov     [rsp+290h+var_270], rcx
0x1800b7fbf  lea     r9, [rbp+140h+var_118]
0x1800b7fc3  mov     edx, 3
  ... truncated ...
```
