# sub_1801EADE0

- ea: `0x1801eade0`
- end: `0x1801eb957`
- name: `sub_1801EADE0`
- size: `2935`
- prototype: ``
- caller_count: `1`
- callee_count: `29`
- tags: `broker_com_uri`

## callers

- `0x1801eac7c`

## callees

- `0x180031ec0`
- `0x18005b44c`
- `0x18007ba55`
- `0x18007c6e0`
- `0x1800b4204`
- `0x180125f60`
- `0x1801a3c80`
- `0x1801d9d60`
- `0x1801e3310`
- `0x1801eade0`
- `0x1801eb958`
- `0x1801fa200`
- `0x180204200`
- `0x1802094f0`
- `0x18022acc4`
- `0x180234420`
- `0x1802660e8`
- `0x180269f54`
- `0x180295400`
- `0x18029c158`
- `0x1802be197`
- `0x1802d14e0`
- `0x1802d8ba0`
- `0x1802dd458`
- `0x1802de0c0`
- `0x1802de200`
- `0x1802de3a0`
- `0x180840720`
- `0x180cb18b0`

## import_xrefs

- `MSVCP140!_Mtx_unlock` at `0x1801eb927`
- `MSVCP140!_Mtx_unlock` at `0x1801eb927`
- `ole32!CoCreateGuid` at `0x1801eb027`
- `ole32!CoCreateGuid` at `0x1801eb08b`
- `ole32!CoCreateGuid` at `0x1801eb0ce`
- `ole32!CoCreateGuid` at `0x1801eb027`
- `ole32!CoCreateGuid` at `0x1801eb08b`
- `ole32!CoCreateGuid` at `0x1801eb0ce`
- `Mso20Win32Client!Mso20Win32Client_7228` at `0x1801eb279`
- `Mso20Win32Client!Mso20Win32Client_7228` at `0x1801eb390`
- `Mso20Win32Client!Mso20Win32Client_7228` at `0x1801eb41e`
- `Mso20Win32Client!Mso20Win32Client_7228` at `0x1801eb48f`
- `Mso20Win32Client!Mso20Win32Client_7228` at `0x1801eb4eb`
- `Mso20Win32Client!Mso20Win32Client_7228` at `0x1801eb279`
- `Mso20Win32Client!Mso20Win32Client_7228` at `0x1801eb390`
- `Mso20Win32Client!Mso20Win32Client_7228` at `0x1801eb41e`
- `Mso20Win32Client!Mso20Win32Client_7228` at `0x1801eb48f`
- `Mso20Win32Client!Mso20Win32Client_7228` at `0x1801eb4eb`
- `Mso20Win32Client!Mso20Win32Client_21217` at `0x1801eae61`
- `Mso20Win32Client!Mso20Win32Client_21217` at `0x1801eae61`
- `Mso20Win32Client!Mso20Win32Client_26547` at `0x1801eb03b`
- `Mso20Win32Client!Mso20Win32Client_26547` at `0x1801eb09c`
- `Mso20Win32Client!Mso20Win32Client_26547` at `0x1801eb0df`
- `Mso20Win32Client!Mso20Win32Client_26547` at `0x1801eb03b`
- `Mso20Win32Client!Mso20Win32Client_26547` at `0x1801eb09c`
- `Mso20Win32Client!Mso20Win32Client_26547` at `0x1801eb0df`

## pseudocode

```c
int __fastcall sub_1801EADE0(
        __int64 a1,
        __int64 a2,
        _DWORD *a3,
        __int64 a4,
        char a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        char a9,
        char a10,
        char a11,
        char a12)
{
  __int64 v15; // rsi
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r9
  __int64 v19; // rax
  __int64 v20; // r8
  __int64 v21; // rax
  char v22; // bl
  __int64 v23; // rax
  __int64 v24; // r9
  GUID v25; // xmm0
  __int128 v26; // xmm1
  HRESULT v27; // eax
  HRESULT v28; // eax
  HRESULT v29; // eax
  void (__fastcall *v30)(__int64, GUID *, _OWORD *, __int64); // r11
  void (__fastcall *v31)(__int64, GUID *, _QWORD *); // r10
  bool v32; // al
  unsigned int v33; // ecx
  _BYTE *v34; // rdx
  unsigned int v35; // ebx
  unsigned int v36; // eax
  __int64 v37; // rcx
  _OWORD *v38; // rax
  _OWORD *v39; // rcx
  __int64 v40; // rdx
  __int64 v41; // r8
  _OWORD *v42; // rax
  _OWORD *v43; // rcx
  __int64 v44; // r8
  _OWORD *v45; // rax
  _OWORD *v46; // rcx
  __int64 v47; // r8
  _OWORD *v48; // rax
  _OWORD *v49; // rcx
  __int64 v50; // rbx
  unsigned int v51; // eax
  __int64 v52; // xmm0_8
  int v53; // eax
  unsigned int v54; // eax
  __int64 v55; // rdi
  int result; // eax
  __int64 v57; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v58; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v59; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v60[3]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v61[1024]; // [rsp+60h] [rbp-A0h] BYREF
  GUID pguid; // [rsp+460h] [rbp+360h] BYREF
  _QWORD v63[4]; // [rsp+480h] [rbp+380h] BYREF
  _QWORD pExceptionObject[14]; // [rsp+4A0h] [rbp+3A0h] BYREF
  _BYTE v65[32]; // [rsp+510h] [rbp+410h] BYREF
  _BYTE v66[8]; // [rsp+530h] [rbp+430h] BYREF
  _BYTE v67[40]; // [rsp+538h] [rbp+438h] BYREF
  _OWORD Buf2[64]; // [rsp+560h] [rbp+460h] BYREF

  v57 = a2;
  v15 = a1 + 120;
  v60[1] = a1 + 120;
  sub_1802DE0C0(a1 + 2336);
  v60[2] = v15;
  sub_1801D9D60(v66, v16, v17, &v57);
  if ( *(_QWORD *)(a1 + 2416) )
  {
    Mso20Win32Client_21217(508375810, 0);
    __debugbreak();
  }
  (*(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v57 + 208LL))(v57, v60);
  if ( v60[0] )
  {
    v19 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *, _QWORD))(*(_QWORD *)v60[0] + 112LL))(v60[0], v65, 0);
    LOBYTE(v20) = 1;
    Jot::EDP::GetEnterpriseIdentity(v63, v19, v20);
    sub_1802D8BA0(v65);
    v21 = sub_1802660E8(&pguid);
    v22 = sub_180125F60(v21, v63);
    sub_1802D8BA0(&pguid);
    if ( v22 )
    {
      v23 = sub_180269F54(&pguid, v63);
      sub_180CB18B0(pExceptionObject, v23, 18434190);
      throw (Jot::ErrEDP_UnsupportedLocalFileIdentity *)pExceptionObject;
    }
    sub_1802D8BA0(v63);
  }
  *(_BYTE *)(a1 + 2514) = a12;
  *(_BYTE *)(a1 + 2513) = a11;
  v59 = 0;
  LOBYTE(v18) = 1;
  sub_18022ACC4(v57, a10 != 0 ? 11 : 1, &v59, v18);
  sub_180234420(Buf2);
  if ( a5 )
  {
    v63[0] = 0;
    LOBYTE(v24) = 1;
    sub_18022ACC4(v57, 15, v63, v24);
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v57 + 88LL))(v57, 1024);
    memset(Buf2, 0, sizeof(Buf2));
    if ( a8 )
    {
      v25 = *(GUID *)a8;
      Buf2[8] = *(_OWORD *)(a8 + 16);
      LODWORD(Buf2[9]) = *(_DWORD *)(a8 + 32);
      v26 = xmmword_18103F968;
    }
    else
    {
      pguid = 0;
      v27 = CoCreateGuid(&pguid);
      if ( v27 < 0 )
      {
        Mso20Win32Client_26547((unsigned int)v27, 523274437);
        __debugbreak();
      }
      v25 = pguid;
      v26 = xmmword_18103F968;
      memset(&Buf2[8], 0, 20);
    }
    Buf2[1] = v25;
    Buf2[0] = *(_OWORD *)a4;
    Buf2[2] = v26;
    pguid = 0;
    v28 = CoCreateGuid(&pguid);
    if ( v28 < 0 )
    {
      Mso20Win32Client_26547((unsigned int)v28, 523274437);
      __debugbreak();
    }
    *(GUID *)((char *)&Buf2[13] + 4) = pguid;
    *(_QWORD *)((char *)&Buf2[14] + 4) = 1;
    pguid = 0;
    v29 = CoCreateGuid(&pguid);
    if ( v29 < 0 )
    {
      Mso20Win32Client_26547((unsigned int)v29, 523274437);
      __debugbreak();
    }
    *(GUID *)((char *)&Buf2[14] + 12) = pguid;
    Buf2[3] = xmmword_1810E8E98;
    LODWORD(Buf2[4]) = *(_DWORD *)(a4 + 16);
    DWORD1(Buf2[4]) = Buf2[4];
    DWORD2(Buf2[4]) = Buf2[4];
    HIDWORD(Buf2[4]) = *(_DWORD *)(a4 + 20);
    *((_QWORD *)&Buf2[11] + 1) = qword_18151C3C8;
    LODWORD(Buf2[12]) = dword_18151C3D0;
    *(_QWORD *)((char *)&Buf2[12] + 12) = 0;
    *((_QWORD *)&Buf2[5] + 1) = qword_18151C3D8;
    LODWORD(Buf2[6]) = 0;
    *(_QWORD *)&Buf2[7] = qword_18151C3D8;
    *(_QWORD *)((char *)&Buf2[9] + 4) = qword_18151C3C8;
    HIDWORD(Buf2[9]) = dword_18151C3D0;
    *(_QWORD *)&Buf2[10] = qword_18151C3C8;
    DWORD2(Buf2[10]) = dword_18151C3D0;
    *(_QWORD *)((char *)&Buf2[10] + 12) = qword_18151C3C8;
    DWORD1(Buf2[11]) = dword_18151C3D0;
    DWORD2(Buf2[17]) = sub_18005B44C();
    HIDWORD(Buf2[17]) = sub_18005B44C();
    LODWORD(Buf2[18]) = sub_18005B44C();
    DWORD1(Buf2[18]) = sub_18005B44C();
    HIBYTE(Buf2[7]) = 0;
    v30 = *(void (__fastcall **)(__int64, GUID *, _OWORD *, __int64))(*(_QWORD *)v57 + 80LL);
    if ( *(_DWORD *)byte_18151C3E0 != -1 || dword_18151C3E4 )
    {
      *(_QWORD *)&pguid.Data1 = *(unsigned int *)byte_18151C3E0;
      *(_DWORD *)pguid.Data4 = dword_18151C3E4;
    }
    else
    {
      *(_QWORD *)&pguid.Data1 = -1;
      *(_DWORD *)pguid.Data4 = 0;
    }
    v30(v57, &pguid, Buf2, 1024);
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v57 + 128LL))(v57, 0);
    if ( v63[0] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v63[0] + 16LL))(v63[0]);
  }
  else
  {
    if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v57 + 96LL))(v57) )
    {
      Mso20Win32Client_7228(508375779);
      *(_QWORD *)&pguid.Data1 = &off_1810F3250;
      *(_QWORD *)pguid.Data4 = "FNFZeroByteFile";
      sub_1802DD458(508375778, &pguid, 100);
      sub_1801E3310(pExceptionObject, 21878030);
      pExceptionObject[0] = &off_1810ED440;
      throw (Jot::ErrFileNodeFileCorrupt_ZeroByteFile *)pExceptionObject;
    }
    v31 = *(void (__fastcall **)(__int64, GUID *, _QWORD *))(*(_QWORD *)v57 + 48LL);
    v63[0] = Buf2;
    v63[1] = 1024;
    if ( *(_DWORD *)byte_18151C3E0 != -1 || dword_18151C3E4 )
    {
      *(_QWORD *)&pguid.Data1 = *(unsigned int *)byte_18151C3E0;
      *(_DWORD *)pguid.Data4 = dword_18151C3E4;
    }
    else
    {
      *(_QWORD *)&pguid.Data1 = -1;
      *(_DWORD *)pguid.Data4 = 0;
    }
    v31(v57, &pguid, v63);
    v32 = 1;
    v33 = 0;
    v34 = &Buf2[3];
    while ( v32 )
    {
      v32 = LOBYTE(Buf2[3]) == *v34;
      ++v33;
      ++v34;
      if ( v33 >= 0x10 )
      {
        if ( v32 )
        {
          Mso20Win32Client_7228(508375777);
          *(_QWORD *)&pguid.Data1 = &off_1810F3250;
          *(_QWORD *)pguid.Data4 = "FNFZeroHeaderFile";
          sub_1802DD458(508375776, &pguid, 100);
          sub_1801E3310(pExceptionObject, 21878031);
          pExceptionObject[0] = &off_1810ED460;
          throw (Jot::ErrFileNodeFileCorrupt_ZeroHeaderFile *)pExceptionObject;
        }
        break;
      }
    }
    if ( memcmp(&Buf2[3], &xmmword_1810E8E98, 0x10u) )
    {
      Mso20Win32Client_7228(508375775);
      sub_180840720(pExceptionObject, 21878032);
      throw (Jot::ErrFileNodeFile_WrongFileFormat *)pExceptionObject;
    }
    v35 = Buf2[4];
    if ( a3 )
    {
      if ( memcmp(a3, &xmmword_18103F968, 0x10u) && memcmp(a3, Buf2, 0x10u) )
      {
        Mso20Win32Client_7228(508375774);
        sub_1801E3310(pExceptionObject, 21878033);
        pExceptionObject[0] = &off_1810ED400;
        throw (Jot::ErrFileNodeFile_WrongFileType *)pExceptionObject;
      }
      v36 = a3[4];
      if ( v36 != v35 )
      {
        if ( a3[6] > v35 )
        {
          if ( HIDWORD(Buf2[4]) > v35 )
          {
            Mso20Win32Client_7228(508375773);
            *(_QWORD *)&pguid.Data1 = &off_1810F3250;
            *(_QWORD *)pguid.Data4 = "FNFInconsistentFileVersions";
            sub_1802DD458(508375772, &pguid, 100);
            sub_1801E3310(pExceptionObject, 21878034);
            pExceptionObject[0] = &off_1810ED3E0;
            throw (Jot::ErrFileNodeFileCorrupt_InconsistentFileVersions *)pExceptionObject;
          }
          sub_1801E3310(pExceptionObject, 21878035);
          pExceptionObject[0] = &off_1810ED420;
          throw (Jot::ErrFileNodeFile_IncompatibleOldFileNodeFile *)pExceptionObject;
        }
        if ( v36 < HIDWORD(Buf2[4]) )
        {
          sub_1801E3310(pExceptionObject, 21878036);
          pExceptionObject[0] = &off_1810EC7E8;
          throw (Jot::ErrFileNodeFile_IncompatibleNewFileNodeFile *)pExceptionObject;
        }
      }
    }
    v37 = 8557;
    if ( v35 > 0x1B )
      v37 = 8558;
    CodeMarker(v37);
  }
  v38 = v61;
  v39 = Buf2;
  v40 = 8;
  v41 = 8;
  do
  {
    *v38 = *v39;
    v38[1] = v39[1];
    v38[2] = v39[2];
    v38[3] = v39[3];
    v38[4] = v39[4];
    v38[5] = v39[5];
    v38[6] = v39[6];
    v38 += 8;
    *(v38 - 1) = v39[7];
    v39 += 8;
    --v41;
  }
  while ( v41 );
  v42 = (_OWORD *)(v15 + 8);
  v43 = v61;
  v44 = 8;
  do
  {
    *v42 = *v43;
    v42[1] = v43[1];
    v42[2] = v43[2];
    v42[3] = v43[3];
    v42[4] = v43[4];
    v42[5] = v43[5];
    v42[6] = v43[6];
    v42 += 8;
    *(v42 - 1) = v43[7];
    v43 += 8;
    --v44;
  }
  while ( v44 );
  v45 = v61;
  v46 = Buf2;
  v47 = 8;
  do
  {
    *v45 = *v46;
    v45[1] = v46[1];
    v45[2] = v46[2];
    v45[3] = v46[3];
    v45[4] = v46[4];
    v45[5] = v46[5];
    v45[6] = v46[6];
    v45 += 8;
    *(v45 - 1) = v46[7];
    v46 += 8;
    --v47;
  }
  while ( v47 );
  v48 = (_OWORD *)(v15 + 1032);
  v49 = v61;
  do
  {
    *v48 = *v49;
    v48[1] = v49[1];
    v48[2] = v49[2];
    v48[3] = v49[3];
    v48[4] = v49[4];
    v48[5] = v49[5];
    v48[6] = v49[6];
    v48 += 8;
    *(v48 - 1) = v49[7];
    v49 += 8;
    --v40;
  }
  while ( v40 );
  *(_BYTE *)(a1 + 2523) = *(_BYTE *)(v15 + 1156) & 1;
  *(_BYTE *)(a1 + 2524) = *(_BYTE *)(v15 + 1158) & 1;
  sub_1801A3C80(a1 + 2416, v57);
  v50 = v59;
  sub_180031EC0(v15, v59);
  *(_BYTE *)(a1 + 2512) = a9;
  *(_BYTE *)(a1 + 2526) = a10;
  if ( a4 )
  {
    v51 = *(_DWORD *)(v15 + 1096);
    if ( v51 <= *(_DWORD *)(a4 + 16) )
      v51 = *(_DWORD *)(a4 + 16);
  }
  else
  {
    v51 = *(_DWORD *)(v15 + 1096);
  }
  *(_DWORD *)(v15 + 2056) = v51;
  if ( a4 )
  {
    v52 = *(_QWORD *)(a4 + 16);
    v53 = *(_DWORD *)(a4 + 24);
    *(_OWORD *)(v15 + 2060) = *(_OWORD *)a4;
    *(_QWORD *)(v15 + 2076) = v52;
    *(_DWORD *)(v15 + 2084) = v53;
  }
  if ( a5 )
  {
    sub_1802094F0(a1, &v58, 0);
    *(_QWORD *)&pguid.Data1 = 0;
    sub_1801EB958(&pguid);
    v54 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)()))off_18151C310[12])(&off_18151C310);
    v55 = *(_QWORD *)&pguid.Data1;
    sub_1801FA200(*(_QWORD *)&pguid.Data1, v58, v54);
    sub_18007C6E0(v58 + 264, v55);
    sub_180204200(v58, 0, 0, 0, 1);
    if ( v55 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 8LL))(v55);
    sub_1800B4204(v58);
    sub_1802094F0(a1, v63, 0);
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a1 + 56LL))(a1, v63[0]);
    sub_180204200(v63[0], 0, 0, 0, 1);
    sub_1800B4204(v63[0]);
  }
  if ( v50 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
  if ( v60[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v60[0] + 16LL))(v60[0]);
  result = sub_1802D8BA0(v67);
  if ( v15 )
    return Mtx_unlock((_Mtx_t)(v15 + 2216));
  return result;
}

```

## disassembly

```asm
0x1801eade0  mov     [rsp-8+arg_10], rbx
0x1801eade5  push    rbp
0x1801eade6  push    rsi
0x1801eade7  push    rdi
0x1801eade8  push    r12
0x1801eadea  push    r13
0x1801eadec  push    r14
0x1801eadee  push    r15
0x1801eadf0  lea     rbp, [rsp-870h]
0x1801eadf8  sub     rsp, 970h
0x1801eadff  mov     rax, cs:__security_cookie
0x1801eae06  xor     rax, rsp
0x1801eae09  mov     [rbp+8A0h+var_40], rax
0x1801eae10  mov     rdi, r9
0x1801eae13  mov     r15, r8
0x1801eae16  mov     r14, rcx
0x1801eae19  mov     r13, [rbp+8A0h+arg_38]
0x1801eae20  mov     [rsp+9A0h+var_970], rdx
0x1801eae25  lea     rsi, [rcx+78h]
0x1801eae29  mov     [rsp+9A0h+var_950], rsi
0x1801eae2e  lea     rcx, [rsi+8A8h]
0x1801eae35  call    sub_1802DE0C0
0x1801eae3a  mov     [rsp+9A0h+var_948], rsi
0x1801eae3f  lea     r9, [rsp+9A0h+var_970]
0x1801eae44  lea     rcx, [rbp+8A0h+var_470]
0x1801eae4b  call    sub_1801D9D60
0x1801eae50  cmp     qword ptr [r14+970h], 0
0x1801eae58  jz      short loc_1801EAE68
0x1801eae5a  xor     edx, edx
0x1801eae5c  mov     ecx, 1E4D3302h
0x1801eae61  call    cs:Mso20Win32Client_21217
0x1801eae67  int     3; Trap to Debugger
0x1801eae68  mov     rcx, [rsp+9A0h+var_970]
0x1801eae6d  mov     rax, [rcx]
0x1801eae70  lea     rdx, [rsp+9A0h+var_958]
0x1801eae75  mov     rax, [rax+0D0h]
0x1801eae7c  call    cs:__guard_dispatch_icall_fptr
0x1801eae82  mov     rcx, [rsp+9A0h+var_958]
0x1801eae87  test    rcx, rcx
0x1801eae8a  jz      loc_1801EAF3A
0x1801eae90  mov     rax, [rcx]
0x1801eae93  xor     r8d, r8d
0x1801eae96  lea     rdx, [rbp+8A0h+var_490]
0x1801eae9d  mov     rax, [rax+70h]
0x1801eaea1  call    cs:__guard_dispatch_icall_fptr
0x1801eaea7  mov     r8b, 1
0x1801eaeaa  mov     rdx, rax
0x1801eaead  lea     rcx, [rbp+8A0h+var_520]
0x1801eaeb4  call    ?GetEnterpriseIdentity@EDP@Jot@@YA?AVIdentity@12@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_N@Z; Jot::EDP::GetEnterpriseIdentity(std::wstring const &,bool)
0x1801eaeb9  lea     rcx, [rbp+8A0h+var_490]
0x1801eaec0  call    sub_1802D8BA0
0x1801eaec5  lea     rcx, [rbp+8A0h+pguid]
0x1801eaecc  call    sub_1802660E8
0x1801eaed1  lea     rdx, [rbp+8A0h+var_520]
0x1801eaed8  mov     rcx, rax
0x1801eaedb  call    sub_180125F60
0x1801eaee0  mov     bl, al
0x1801eaee2  lea     rcx, [rbp+8A0h+pguid]
0x1801eaee9  call    sub_1802D8BA0
0x1801eaeee  test    bl, bl
0x1801eaef0  jz      short loc_1801EAF2E
0x1801eaef2  lea     rdx, [rbp+8A0h+var_520]
0x1801eaef9  lea     rcx, [rbp+8A0h+pguid]
0x1801eaf00  call    sub_180269F54
0x1801eaf05  mov     r8d, 119488Eh
0x1801eaf0b  mov     rdx, rax
0x1801eaf0e  lea     rcx, [rbp+8A0h+pExceptionObject]
0x1801eaf15  call    sub_180CB18B0
0x1801eaf1a  lea     rdx, __TI3?AUErrEDP_UnsupportedLocalFileIdentity@Jot@@; pThrowInfo
0x1801eaf21  lea     rcx, [rbp+8A0h+pExceptionObject]; pExceptionObject
0x1801eaf28  call    _CxxThrowException
0x1801eaf2e  lea     rcx, [rbp+8A0h+var_520]
0x1801eaf35  call    sub_1802D8BA0
0x1801eaf3a  mov     al, [rbp+8A0h+arg_58]
0x1801eaf40  mov     [r14+9D2h], al
0x1801eaf47  mov     al, [rbp+8A0h+arg_50]
0x1801eaf4d  mov     [r14+9D1h], al
0x1801eaf54  mov     [rsp+9A0h+var_960], 0
0x1801eaf5d  mov     r12b, [rbp+8A0h+arg_48]
0x1801eaf64  mov     al, r12b
0x1801eaf67  neg     al
0x1801eaf69  sbb     edx, edx
0x1801eaf6b  and     edx, 0Ah
0x1801eaf6e  inc     edx
0x1801eaf70  mov     r9b, 1
0x1801eaf73  lea     r8, [rsp+9A0h+var_960]
0x1801eaf78  mov     rcx, [rsp+9A0h+var_970]
0x1801eaf7d  call    sub_18022ACC4
0x1801eaf82  lea     rcx, [rbp+8A0h+Buf2]
0x1801eaf89  call    sub_180234420
0x1801eaf8e  cmp     [rbp+8A0h+arg_20], 0
0x1801eaf95  jz      loc_1801EB25A
0x1801eaf9b  mov     [rbp+8A0h+var_520], 0
0x1801eafa6  mov     r9b, 1
0x1801eafa9  lea     r8, [rbp+8A0h+var_520]
0x1801eafb0  mov     edx, 0Fh
0x1801eafb5  mov     rcx, [rsp+9A0h+var_970]
0x1801eafba  call    sub_18022ACC4
0x1801eafbf  mov     rcx, [rsp+9A0h+var_970]
0x1801eafc4  mov     rax, [rcx]
0x1801eafc7  mov     ebx, 400h
0x1801eafcc  mov     edx, ebx
0x1801eafce  mov     rax, [rax+58h]
0x1801eafd2  call    cs:__guard_dispatch_icall_fptr
0x1801eafd8  mov     r8d, ebx; Size
0x1801eafdb  xor     edx, edx; Val
0x1801eafdd  lea     rcx, [rbp+8A0h+Buf2]; void *
0x1801eafe4  call    memset
0x1801eafe9  test    r13, r13
0x1801eafec  jz      short loc_1801EB016
0x1801eafee  movups  xmm0, xmmword ptr [r13+0]
0x1801eaff3  movups  xmm1, xmmword ptr [r13+10h]
0x1801eaff8  movdqu  [rbp+8A0h+var_3C0], xmm1
0x1801eb000  mov     eax, [r13+20h]
0x1801eb004  mov     [rbp+8A0h+var_3B0], eax
0x1801eb00a  movups  xmm1, cs:xmmword_18103F968
0x1801eb011  xor     r13d, r13d
0x1801eb014  jmp     short loc_1801EB05F
0x1801eb016  xorps   xmm0, xmm0
0x1801eb019  movups  xmmword ptr [rbp+8A0h+pguid.Data1], xmm0
0x1801eb020  lea     rcx, [rbp+8A0h+pguid]; pguid
0x1801eb027  call    cs:CoCreateGuid
0x1801eb02d  xor     r13d, r13d
0x1801eb030  test    eax, eax
0x1801eb032  jns     short loc_1801EB042
0x1801eb034  mov     edx, 1F3088C5h
0x1801eb039  mov     ecx, eax
0x1801eb03b  call    cs:Mso20Win32Client_26547
0x1801eb041  int     3; Trap to Debugger
0x1801eb042  movups  xmm0, xmmword ptr [rbp+8A0h+pguid.Data1]
0x1801eb049  movups  xmm1, cs:xmmword_18103F968
0x1801eb050  movdqu  [rbp+8A0h+var_3C0], xmm1
0x1801eb058  mov     [rbp+8A0h+var_3B0], r13d
0x1801eb05f  movdqu  [rbp+8A0h+var_430], xmm0
0x1801eb067  movups  xmm0, xmmword ptr [rdi]
0x1801eb06a  movdqu  [rbp+8A0h+Buf2], xmm0
0x1801eb072  movdqu  [rbp+8A0h+var_420], xmm1
0x1801eb07a  xorps   xmm0, xmm0
0x1801eb07d  movups  xmmword ptr [rbp+8A0h+pguid.Data1], xmm0
0x1801eb084  lea     rcx, [rbp+8A0h+pguid]; pguid
0x1801eb08b  call    cs:CoCreateGuid
0x1801eb091  test    eax, eax
0x1801eb093  jns     short loc_1801EB0A3
0x1801eb095  mov     edx, 1F3088C5h
0x1801eb09a  mov     ecx, eax
0x1801eb09c  call    cs:Mso20Win32Client_26547
0x1801eb0a2  int     3; Trap to Debugger
0x1801eb0a3  movups  xmm0, xmmword ptr [rbp+8A0h+pguid.Data1]
0x1801eb0aa  movdqu  [rbp+8A0h+var_36C], xmm0
0x1801eb0b2  mov     [rbp+8A0h+var_35C], 1
0x1801eb0bd  xorps   xmm1, xmm1
0x1801eb0c0  movups  xmmword ptr [rbp+8A0h+pguid.Data1], xmm1
0x1801eb0c7  lea     rcx, [rbp+8A0h+pguid]; pguid
0x1801eb0ce  call    cs:CoCreateGuid
0x1801eb0d4  test    eax, eax
0x1801eb0d6  jns     short loc_1801EB0E6
0x1801eb0d8  mov     edx, 1F3088C5h
0x1801eb0dd  mov     ecx, eax
0x1801eb0df  call    cs:Mso20Win32Client_26547
0x1801eb0e5  int     3; Trap to Debugger
0x1801eb0e6  movups  xmm0, xmmword ptr [rbp+8A0h+pguid.Data1]
0x1801eb0ed  movdqu  [rbp+8A0h+var_354], xmm0
0x1801eb0f5  movups  xmm1, cs:xmmword_1810E8E98
0x1801eb0fc  movdqu  [rbp+8A0h+Buf1], xmm1
0x1801eb104  mov     eax, [rdi+10h]
0x1801eb107  mov     [rbp+8A0h+var_400], eax
0x1801eb10d  mov     [rbp+8A0h+var_3FC], eax
0x1801eb113  mov     [rbp+8A0h+var_3F8], eax
0x1801eb119  mov     eax, [rdi+14h]
0x1801eb11c  mov     [rbp+8A0h+var_3F4], eax
0x1801eb122  movsd   xmm0, cs:qword_18151C3C8
0x1801eb12a  movsd   [rbp+8A0h+var_388], xmm0
0x1801eb132  mov     ecx, cs:dword_18151C3D0
0x1801eb138  mov     [rbp+8A0h+var_380], ecx
0x1801eb13e  mov     [rbp+8A0h+var_374], r13
0x1801eb145  mov     rax, cs:qword_18151C3D8
0x1801eb14c  mov     [rbp+8A0h+var_3E8], rax
0x1801eb153  mov     [rbp+8A0h+var_3E0], r13d
0x1801eb15a  mov     [rbp+8A0h+var_3D0], rax
0x1801eb161  movsd   [rbp+8A0h+var_3AC], xmm0
0x1801eb169  mov     [rbp+8A0h+var_3A4], ecx
0x1801eb16f  movsd   [rbp+8A0h+var_3A0], xmm0
0x1801eb177  mov     [rbp+8A0h+var_398], ecx
0x1801eb17d  movsd   [rbp+8A0h+var_394], xmm0
0x1801eb185  mov     [rbp+8A0h+var_38C], ecx
0x1801eb18b  call    sub_18005B44C
0x1801eb190  mov     [rbp+8A0h+var_328], eax
0x1801eb196  call    sub_18005B44C
0x1801eb19b  mov     [rbp+8A0h+var_324], eax
0x1801eb1a1  call    sub_18005B44C
0x1801eb1a6  mov     [rbp+8A0h+var_320], eax
0x1801eb1ac  call    sub_18005B44C
0x1801eb1b1  mov     [rbp+8A0h+var_31C], eax
0x1801eb1b7  mov     [rbp+8A0h+var_3C1], r13b
0x1801eb1be  mov     r10, [rsp+9A0h+var_970]
0x1801eb1c3  mov     rax, [r10]
0x1801eb1c6  mov     r11, [rax+50h]
0x1801eb1ca  mov     edx, cs:dword_18151C3E4
0x1801eb1d0  mov     rax, qword ptr cs:byte_18151C3E0
0x1801eb1d7  cmp     eax, 0FFFFFFFFh
0x1801eb1da  jnz     short loc_1801EB1F4
0x1801eb1dc  test    edx, edx
0x1801eb1de  jnz     short loc_1801EB1F4
0x1801eb1e0  mov     qword ptr [rbp+8A0h+pguid.Data1], 0FFFFFFFFFFFFFFFFh
0x1801eb1eb  mov     dword ptr [rbp+8A0h+pguid.Data4], r13d
0x1801eb1f2  jmp     short loc_1801EB203
0x1801eb1f4  mov     ecx, eax
0x1801eb1f6  mov     qword ptr [rbp+8A0h+pguid.Data1], rcx
0x1801eb1fd  mov     dword ptr [rbp+8A0h+pguid.Data4], edx
0x1801eb203  mov     r9d, ebx
0x1801eb206  lea     r8, [rbp+8A0h+Buf2]
0x1801eb20d  lea     rdx, [rbp+8A0h+pguid]
0x1801eb214  mov     rcx, r10
0x1801eb217  mov     rax, r11
0x1801eb21a  call    cs:__guard_dispatch_icall_fptr
0x1801eb220  mov     rcx, [rsp+9A0h+var_970]
0x1801eb225  mov     rax, [rcx]
0x1801eb228  xor     edx, edx
0x1801eb22a  mov     rax, [rax+80h]
0x1801eb231  call    cs:__guard_dispatch_icall_fptr
0x1801eb237  nop
0x1801eb238  mov     rcx, [rbp+8A0h+var_520]
0x1801eb23f  test    rcx, rcx
0x1801eb242  jz      loc_1801EB5D9
0x1801eb248  mov     rax, [rcx]
0x1801eb24b  mov     rax, [rax+10h]
0x1801eb24f  call    cs:__guard_dispatch_icall_fptr
0x1801eb255  jmp     loc_1801EB5D9
0x1801eb25a  mov     rcx, [rsp+9A0h+var_970]
0x1801eb25f  mov     rax, [rcx]
0x1801eb262  mov     rax, [rax+60h]
0x1801eb266  call    cs:__guard_dispatch_icall_fptr
0x1801eb26c  xor     r13d, r13d
0x1801eb26f  test    rax, rax
0x1801eb272  jnz     short loc_1801EB2E3
0x1801eb274  mov     ecx, 1E4D32E3h
0x1801eb279  call    cs:Mso20Win32Client_7228
0x1801eb27f  lea     rax, off_1810F3250
0x1801eb286  mov     qword ptr [rbp+8A0h+pguid.Data1], rax
0x1801eb28d  lea     rax, aFnfzerobytefil; "FNFZeroByteFile"
0x1801eb294  mov     qword ptr [rbp+8A0h+pguid.Data4], rax
0x1801eb29b  lea     r8d, [r13+64h]
0x1801eb29f  lea     rdx, [rbp+8A0h+pguid]
0x1801eb2a6  mov     ecx, 1E4D32E2h
0x1801eb2ab  call    sub_1802DD458
0x1801eb2b0  mov     edx, 14DD50Eh
0x1801eb2b5  lea     rcx, [rbp+8A0h+pExceptionObject]
0x1801eb2bc  call    sub_1801E3310
0x1801eb2c1  lea     rax, off_1810ED440
0x1801eb2c8  mov     [rbp+8A0h+pExceptionObject], rax
0x1801eb2cf  lea     rdx, __TI5?AUErrFileNodeFileCorrupt_ZeroByteFile@Jot@@; pThrowInfo
0x1801eb2d6  lea     rcx, [rbp+8A0h+pExceptionObject]; pExceptionObject
0x1801eb2dd  call    _CxxThrowException
0x1801eb2e3  mov     r9, [rsp+9A0h+var_970]
0x1801eb2e8  mov     rax, [r9]
0x1801eb2eb  mov     r10, [rax+30h]
0x1801eb2ef  lea     rax, [rbp+8A0h+Buf2]
0x1801eb2f6  mov     [rbp+8A0h+var_520], rax
0x1801eb2fd  mov     ebx, 400h
0x1801eb302  mov     [rbp+8A0h+var_518], rbx
0x1801eb309  mov     edx, cs:dword_18151C3E4
0x1801eb30f  mov     rax, qword ptr cs:byte_18151C3E0
0x1801eb316  cmp     eax, 0FFFFFFFFh
0x1801eb319  jnz     short loc_1801EB333
0x1801eb31b  test    edx, edx
0x1801eb31d  jnz     short loc_1801EB333
0x1801eb31f  mov     qword ptr [rbp+8A0h+pguid.Data1], 0FFFFFFFFFFFFFFFFh
0x1801eb32a  mov     dword ptr [rbp+8A0h+pguid.Data4], r13d
0x1801eb331  jmp     short loc_1801EB342
0x1801eb333  mov     ecx, eax
0x1801eb335  mov     qword ptr [rbp+8A0h+pguid.Data1], rcx
0x1801eb33c  mov     dword ptr [rbp+8A0h+pguid.Data4], edx
0x1801eb342  lea     r8, [rbp+8A0h+var_520]
0x1801eb349  lea     rdx, [rbp+8A0h+pguid]
0x1801eb350  mov     rcx, r9
0x1801eb353  mov     rax, r10
0x1801eb356  call    cs:__guard_dispatch_icall_fptr
0x1801eb35c  mov     al, 1
0x1801eb35e  mov     ecx, r13d
0x1801eb361  lea     rdx, [rbp+8A0h+Buf1]
0x1801eb368  mov     r8b, byte ptr [rbp+8A0h+Buf1]
0x1801eb36f  test    al, al
0x1801eb371  jz      loc_1801EB3FC
0x1801eb377  cmp     r8b, [rdx]
0x1801eb37a  setz    al
0x1801eb37d  inc     ecx
0x1801eb37f  inc     rdx
0x1801eb382  cmp     ecx, 10h
0x1801eb385  jb      short loc_1801EB36F
0x1801eb387  test    al, al
0x1801eb389  jz      short loc_1801EB3FC
0x1801eb38b  mov     ecx, 1E4D32E1h
0x1801eb390  call    cs:Mso20Win32Client_7228
0x1801eb396  lea     rax, off_1810F3250
0x1801eb39d  mov     qword ptr [rbp+8A0h+pguid.Data1], rax
0x1801eb3a4  lea     rax, aFnfzeroheaderf; "FNFZeroHeaderFile"
0x1801eb3ab  mov     qword ptr [rbp+8A0h+pguid.Data4], rax
0x1801eb3b2  mov     r8d, 64h ; 'd'
0x1801eb3b8  lea     rdx, [rbp+8A0h+pguid]
0x1801eb3bf  mov     ecx, 1E4D32E0h
  ... truncated ...
```
