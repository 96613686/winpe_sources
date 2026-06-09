# Microsoft::Bluetooth::Services::BthServ::BthpNextServiceCallback(ulong,uchar *,ulong,void *)

- ea: `0x1800257dc`
- end: `0x180025bca`
- name: `?BthpNextServiceCallback@BthServ@Services@Bluetooth@Microsoft@@YAHKPEAEKPEAX@Z`
- size: `1006`
- prototype: `int(Microsoft::Bluetooth::Services::BthServ *__hidden this, unsigned int, unsigned __int8 *, unsigned int, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180022f30`

## callees

- `0x180024ca8`
- `0x180025724`
- `0x1800257dc`
- `0x180026308`
- `0x180026390`
- `0x180029084`

## pseudocode

```c
__int64 __fastcall Microsoft::Bluetooth::Services::BthServ::BthpNextServiceCallback(
        Microsoft::Bluetooth::Services::BthServ *this,
        Microsoft::Bluetooth::Services::BthServ *a2,
        unsigned __int8 *a3,
        struct _GUID *a4)
{
  __int64 v4; // rbx
  struct _BLUETOOTH_SDP_RECORD *v6; // rbp
  int v7; // esi
  Microsoft::Bluetooth::Services::BthServ *v8; // rax
  void *v9; // r8
  Microsoft::Bluetooth::Services::BthServ *v10; // r14
  Microsoft::Bluetooth::Services::BthServ *Record; // rax
  void *v12; // r8
  Microsoft::Bluetooth::Services::BthServ *v13; // rax
  void *v14; // r8
  Microsoft::Bluetooth::Services::BthServ *v15; // rax
  void *v16; // r8
  struct _BLUETOOTH_SDP_RECORD *i; // rbp
  Microsoft::Bluetooth::Services::BthServ *v18; // rax
  void *v19; // r8
  Microsoft::Bluetooth::Services::BthServ *v20; // rax
  void *v21; // r8
  unsigned int Data1; // edx
  unsigned __int8 *v24; // rdx
  struct IMultiLanguage2 *v25; // rcx
  unsigned __int8 *v26; // rdx
  struct IMultiLanguage2 *v27; // rcx
  unsigned __int8 *v28; // rdx
  struct IMultiLanguage2 *v29; // rcx
  unsigned int v30; // [rsp+50h] [rbp+8h] BYREF

  v4 = *(_QWORD *)a4->Data4;
  v6 = (Microsoft::Bluetooth::Services::BthServ *)((char *)a2 + (unsigned int)a3);
  v7 = (int)a3;
  if ( (unsigned int)this > 7 )
  {
    switch ( (_DWORD)this )
    {
      case 8:
        if ( (*(_BYTE *)a2 & 0xF8) == 8
          && (unsigned int)Microsoft::Bluetooth::Services::BthServ::BthpTransposeAndExtendBytes(
                             a2,
                             v6,
                             (void *)(v4 + 112),
                             &a4->Data1) )
        {
          *(_DWORD *)(v4 + 20) |= 0x100u;
        }
        return 1;
      case 9:
        if ( (*(_BYTE *)a2 & 0xF8) == 0x30 )
        {
          *(_DWORD *)(v4 + 20) |= 0x200u;
          *(_QWORD *)(v4 + 120) = a2;
          *(_DWORD *)(v4 + 128) = (_DWORD)a3;
        }
        return 1;
      case 0xA:
        if ( (*(_BYTE *)a2 & 0xF8) == 0x40 )
        {
          *(_DWORD *)(v4 + 20) |= 0x400u;
          *(_QWORD *)(v4 + 136) = a2;
          *(_DWORD *)(v4 + 144) = (_DWORD)a3;
        }
        return 1;
      case 0xB:
        if ( (*(_BYTE *)a2 & 0xF8) == 0x40 )
        {
          *(_DWORD *)(v4 + 20) |= 0x800u;
          *(_QWORD *)(v4 + 152) = a2;
          *(_DWORD *)(v4 + 160) = (_DWORD)a3;
        }
        return 1;
      case 0xC:
        if ( (*(_BYTE *)a2 & 0xF8) == 0x40 )
        {
          *(_DWORD *)(v4 + 20) |= 0x1000u;
          *(_QWORD *)(v4 + 168) = a2;
          *(_DWORD *)(v4 + 176) = (_DWORD)a3;
        }
        return 1;
    }
    if ( (_DWORD)this != 13 )
    {
      Data1 = a4->Data1;
      if ( a4->Data1 == (_DWORD)this )
      {
        v24 = (unsigned __int8 *)*(unsigned int *)(v4 + 16);
        v25 = *(struct IMultiLanguage2 **)(v4 + 8);
        v30 = 248;
        if ( (unsigned int)Microsoft::Bluetooth::Services::BthServ::BluetoothSdpGetString(
                             v25,
                             v24,
                             (__int64)a3,
                             0,
                             v4 + 180,
                             (unsigned __int16 *)&v30) )
          *(_WORD *)(v4 + 180) = 0;
        else
          *(_DWORD *)(v4 + 20) |= 0x40000000u;
        return 1;
      }
      if ( Data1 + 1 == (_DWORD)this )
      {
        v26 = (unsigned __int8 *)*(unsigned int *)(v4 + 16);
        v27 = *(struct IMultiLanguage2 **)(v4 + 8);
        v30 = 200;
        if ( !(unsigned int)Microsoft::Bluetooth::Services::BthServ::BluetoothSdpGetString(
                              v27,
                              v26,
                              (__int64)a3,
                              (struct _SDP_STRING_TYPE_DATA *)1,
                              v4 + 676,
                              (unsigned __int16 *)&v30) )
        {
          *(_DWORD *)(v4 + 20) |= 0x20000000u;
          return 1;
        }
      }
      else
      {
        if ( Data1 + 2 != (_DWORD)this )
        {
          *(_DWORD *)(v4 + 20) |= 0x80000000;
          return 1;
        }
        v28 = (unsigned __int8 *)*(unsigned int *)(v4 + 16);
        v29 = *(struct IMultiLanguage2 **)(v4 + 8);
        v30 = 200;
        if ( !(unsigned int)Microsoft::Bluetooth::Services::BthServ::BluetoothSdpGetString(
                              v29,
                              v28,
                              (__int64)a3,
                              (struct _SDP_STRING_TYPE_DATA *)2,
                              v4 + 1076,
                              (unsigned __int16 *)&v30) )
        {
          *(_DWORD *)(v4 + 20) |= 0x10000000u;
          return 1;
        }
      }
      *(_WORD *)(v4 + 180) = 0;
    }
  }
  else if ( (_DWORD)this == 7 )
  {
    if ( (*(_BYTE *)a2 & 0xF8) == 8
      && (unsigned int)Microsoft::Bluetooth::Services::BthServ::BthpTransposeAndExtendBytes(
                         a2,
                         v6,
                         (void *)(v4 + 108),
                         &a4->Data1) )
    {
      *(_DWORD *)(v4 + 20) |= 0x80u;
    }
  }
  else if ( (_DWORD)this )
  {
    switch ( (_DWORD)this )
    {
      case 1:
        if ( (*(_BYTE *)a2 & 0xF8) == 0x30 )
        {
          *(_DWORD *)(v4 + 20) |= 2u;
          *(_QWORD *)(v4 + 32) = a2;
        }
        break;
      case 2:
        if ( (*(_BYTE *)a2 & 0xF8) == 8
          && (unsigned int)Microsoft::Bluetooth::Services::BthServ::BthpTransposeAndExtendBytes(
                             a2,
                             v6,
                             (void *)(v4 + 40),
                             &a4->Data1) )
        {
          *(_DWORD *)(v4 + 20) |= 4u;
        }
        break;
      case 3:
        if ( (*(_BYTE *)a2 & 0xF8) == 0x18
          && (unsigned int)Microsoft::Bluetooth::Services::BthServ::BthpTransposeToUUID(a2, a2, (void *)(v4 + 44), a4) )
        {
          *(_DWORD *)(v4 + 20) |= 8u;
        }
        break;
      case 4:
        if ( (unsigned __int8)((*(_BYTE *)a2 >> 3) - 6) <= 1u )
        {
          *(_DWORD *)(v4 + 20) |= 0x10u;
          *(_QWORD *)(v4 + 64) = a2;
          *(_DWORD *)(v4 + 72) = (_DWORD)a3;
        }
        break;
      case 5:
        if ( (*(_BYTE *)a2 & 0xF8) == 0x30 )
        {
          *(_DWORD *)(v4 + 20) |= 0x20u;
          *(_QWORD *)(v4 + 80) = a2;
          *(_DWORD *)(v4 + 88) = (_DWORD)a3;
        }
        break;
      default:
        if ( (*(_BYTE *)a2 & 0xF8) == 0x30 )
        {
          v30 = 0;
          v8 = Microsoft::Bluetooth::Services::BthServ::BthpInnerRecord(a2, v6, &v30, &a4->Data1);
          v10 = v8;
          if ( !v8 )
            return 0;
          Record = Microsoft::Bluetooth::Services::BthServ::BthpNextRecord(v8, v6, v9);
          if ( !Record )
            return 0;
          v13 = Microsoft::Bluetooth::Services::BthServ::BthpNextRecord(Record, v6, v12);
          if ( !v13 )
            return 0;
          v15 = Microsoft::Bluetooth::Services::BthServ::BthpNextRecord(v13, v6, v14);
          for ( i = (Microsoft::Bluetooth::Services::BthServ *)((char *)v10 + v30);
                v15 && v15 < i;
                v15 = Microsoft::Bluetooth::Services::BthServ::BthpNextRecord(v20, i, v21) )
          {
            v18 = Microsoft::Bluetooth::Services::BthServ::BthpNextRecord(v15, i, v16);
            if ( !v18 )
              return 0;
            v20 = Microsoft::Bluetooth::Services::BthServ::BthpNextRecord(v18, i, v19);
            if ( !v20 )
              return 0;
          }
          *(_DWORD *)(v4 + 20) |= 0x40u;
          *(_QWORD *)(v4 + 96) = a2;
          *(_DWORD *)(v4 + 104) = v7;
        }
        break;
    }
  }
  else if ( (*(_BYTE *)a2 & 0xF8) == 8
         && (unsigned int)Microsoft::Bluetooth::Services::BthServ::BthpTransposeAndExtendBytes(
                            a2,
                            v6,
                            (void *)(v4 + 24),
                            &a4->Data1) )
  {
    *(_DWORD *)(v4 + 20) |= 1u;
  }
  return 1;
}

```

## disassembly

```asm
0x1800257dc  mov     [rsp+arg_8], rbx
0x1800257e1  mov     [rsp+arg_10], rbp
0x1800257e6  push    rsi
0x1800257e7  push    rdi
0x1800257e8  push    r14; unsigned int *
0x1800257ea  sub     rsp, 30h
0x1800257ee  mov     rbx, [r9+8]
0x1800257f2  mov     rdi, rdx
0x1800257f5  mov     ebp, r8d
0x1800257f8  add     rbp, rdx
0x1800257fb  mov     esi, r8d
0x1800257fe  cmp     ecx, 7
0x180025801  ja      loc_1800259FB
0x180025807  jz      loc_1800259CE
0x18002580d  mov     eax, ecx
0x18002580f  test    ecx, ecx
0x180025811  jz      loc_1800259A2
0x180025817  sub     eax, 1
0x18002581a  jz      loc_180025989
0x180025820  sub     eax, 1
0x180025823  jz      loc_18002595D
0x180025829  sub     eax, 1
0x18002582c  jz      loc_180025934
0x180025832  sub     eax, 1
0x180025835  jz      loc_180025915
0x18002583b  sub     eax, 1
0x18002583e  jz      loc_1800258F9
0x180025844  cmp     eax, 1
0x180025847  jnz     loc_180025A33
0x18002584d  mov     al, [rdx]
0x18002584f  and     al, 0F8h
0x180025851  cmp     al, 30h ; '0'
0x180025853  jnz     loc_180025BB2
0x180025859  lea     r8, [rsp+48h+arg_0]; void *
0x18002585e  mov     [rsp+48h+arg_0], 0
0x180025866  mov     rdx, rbp; struct _BLUETOOTH_SDP_RECORD *
0x180025869  mov     rcx, rdi; this
0x18002586c  call    ?BthpInnerRecord@BthServ@Services@Bluetooth@Microsoft@@YAPEAU_BLUETOOTH_SDP_RECORD@@PEAU5@PEAXPEAK@Z; Microsoft::Bluetooth::Services::BthServ::BthpInnerRecord(_BLUETOOTH_SDP_RECORD *,void *,ulong *)
0x180025871  mov     r14, rax
0x180025874  test    rax, rax
0x180025877  jz      short loc_1800258F2
0x180025879  mov     rdx, rbp; struct _BLUETOOTH_SDP_RECORD *
0x18002587c  mov     rcx, rax; this
0x18002587f  call    ?BthpNextRecord@BthServ@Services@Bluetooth@Microsoft@@YAPEAU_BLUETOOTH_SDP_RECORD@@PEAU5@PEAX@Z; Microsoft::Bluetooth::Services::BthServ::BthpNextRecord(_BLUETOOTH_SDP_RECORD *,void *)
0x180025884  test    rax, rax
0x180025887  jz      short loc_1800258F2
0x180025889  mov     rdx, rbp; struct _BLUETOOTH_SDP_RECORD *
0x18002588c  mov     rcx, rax; this
0x18002588f  call    ?BthpNextRecord@BthServ@Services@Bluetooth@Microsoft@@YAPEAU_BLUETOOTH_SDP_RECORD@@PEAU5@PEAX@Z; Microsoft::Bluetooth::Services::BthServ::BthpNextRecord(_BLUETOOTH_SDP_RECORD *,void *)
0x180025894  test    rax, rax
0x180025897  jz      short loc_1800258F2
0x180025899  mov     rdx, rbp; struct _BLUETOOTH_SDP_RECORD *
0x18002589c  mov     rcx, rax; this
0x18002589f  call    ?BthpNextRecord@BthServ@Services@Bluetooth@Microsoft@@YAPEAU_BLUETOOTH_SDP_RECORD@@PEAU5@PEAX@Z; Microsoft::Bluetooth::Services::BthServ::BthpNextRecord(_BLUETOOTH_SDP_RECORD *,void *)
0x1800258a4  mov     ebp, [rsp+48h+arg_0]
0x1800258a8  add     rbp, r14
0x1800258ab  jmp     short loc_1800258DD
0x1800258ad  cmp     rax, rbp
0x1800258b0  jnb     short loc_1800258E2
0x1800258b2  mov     rdx, rbp; struct _BLUETOOTH_SDP_RECORD *
0x1800258b5  mov     rcx, rax; this
0x1800258b8  call    ?BthpNextRecord@BthServ@Services@Bluetooth@Microsoft@@YAPEAU_BLUETOOTH_SDP_RECORD@@PEAU5@PEAX@Z; Microsoft::Bluetooth::Services::BthServ::BthpNextRecord(_BLUETOOTH_SDP_RECORD *,void *)
0x1800258bd  test    rax, rax
0x1800258c0  jz      short loc_1800258F2
0x1800258c2  mov     rdx, rbp; struct _BLUETOOTH_SDP_RECORD *
0x1800258c5  mov     rcx, rax; this
0x1800258c8  call    ?BthpNextRecord@BthServ@Services@Bluetooth@Microsoft@@YAPEAU_BLUETOOTH_SDP_RECORD@@PEAU5@PEAX@Z; Microsoft::Bluetooth::Services::BthServ::BthpNextRecord(_BLUETOOTH_SDP_RECORD *,void *)
0x1800258cd  test    rax, rax
0x1800258d0  jz      short loc_1800258F2
0x1800258d2  mov     rdx, rbp; struct _BLUETOOTH_SDP_RECORD *
0x1800258d5  mov     rcx, rax; this
0x1800258d8  call    ?BthpNextRecord@BthServ@Services@Bluetooth@Microsoft@@YAPEAU_BLUETOOTH_SDP_RECORD@@PEAU5@PEAX@Z; Microsoft::Bluetooth::Services::BthServ::BthpNextRecord(_BLUETOOTH_SDP_RECORD *,void *)
0x1800258dd  test    rax, rax
0x1800258e0  jnz     short loc_1800258AD
0x1800258e2  or      dword ptr [rbx+14h], 40h
0x1800258e6  mov     [rbx+60h], rdi
0x1800258ea  mov     [rbx+68h], esi
0x1800258ed  jmp     loc_180025BB2
0x1800258f2  xor     eax, eax
0x1800258f4  jmp     loc_180025BB7
0x1800258f9  mov     al, [rdx]
0x1800258fb  and     al, 0F8h
0x1800258fd  cmp     al, 30h ; '0'
0x1800258ff  jnz     loc_180025BB2
0x180025905  or      dword ptr [rbx+14h], 20h
0x180025909  mov     [rbx+50h], rdi
0x18002590d  mov     [rbx+58h], esi
0x180025910  jmp     loc_180025BB2
0x180025915  mov     al, [rdx]
0x180025917  shr     al, 3
0x18002591a  sub     al, 6
0x18002591c  cmp     al, 1
0x18002591e  ja      loc_180025BB2
0x180025924  or      dword ptr [rbx+14h], 10h
0x180025928  mov     [rbx+40h], rdi
0x18002592c  mov     [rbx+48h], esi
0x18002592f  jmp     loc_180025BB2
0x180025934  mov     al, [rdx]
0x180025936  and     al, 0F8h
0x180025938  cmp     al, 18h
0x18002593a  jnz     loc_180025BB2
0x180025940  lea     r8, [rbx+2Ch]; void *
0x180025944  mov     rcx, rdi; this
0x180025947  call    ?BthpTransposeToUUID@BthServ@Services@Bluetooth@Microsoft@@YAHPEAU_BLUETOOTH_SDP_RECORD@@PEAXPEAU_GUID@@@Z; Microsoft::Bluetooth::Services::BthServ::BthpTransposeToUUID(_BLUETOOTH_SDP_RECORD *,void *,_GUID *)
0x18002594c  test    eax, eax
0x18002594e  jz      loc_180025BB2
0x180025954  or      dword ptr [rbx+14h], 8
0x180025958  jmp     loc_180025BB2
0x18002595d  mov     al, [rdx]
0x18002595f  and     al, 0F8h
0x180025961  cmp     al, 8
0x180025963  jnz     loc_180025BB2
0x180025969  lea     r8, [rbx+28h]; void *
0x18002596d  mov     rdx, rbp; struct _BLUETOOTH_SDP_RECORD *
0x180025970  mov     rcx, rdi; this
0x180025973  call    ?BthpTransposeAndExtendBytes@BthServ@Services@Bluetooth@Microsoft@@YAHPEAU_BLUETOOTH_SDP_RECORD@@PEAXPEAK@Z; Microsoft::Bluetooth::Services::BthServ::BthpTransposeAndExtendBytes(_BLUETOOTH_SDP_RECORD *,void *,ulong *)
0x180025978  test    eax, eax
0x18002597a  jz      loc_180025BB2
0x180025980  or      dword ptr [rbx+14h], 4
0x180025984  jmp     loc_180025BB2
0x180025989  mov     al, [rdx]
0x18002598b  and     al, 0F8h
0x18002598d  cmp     al, 30h ; '0'
0x18002598f  jnz     loc_180025BB2
0x180025995  or      dword ptr [rbx+14h], 2
0x180025999  mov     [rbx+20h], rdi
0x18002599d  jmp     loc_180025BB2
0x1800259a2  mov     al, [rdx]
0x1800259a4  and     al, 0F8h
0x1800259a6  cmp     al, 8
0x1800259a8  jnz     loc_180025BB2
0x1800259ae  lea     r8, [rbx+18h]; void *
0x1800259b2  mov     rdx, rbp; struct _BLUETOOTH_SDP_RECORD *
0x1800259b5  mov     rcx, rdi; this
0x1800259b8  call    ?BthpTransposeAndExtendBytes@BthServ@Services@Bluetooth@Microsoft@@YAHPEAU_BLUETOOTH_SDP_RECORD@@PEAXPEAK@Z; Microsoft::Bluetooth::Services::BthServ::BthpTransposeAndExtendBytes(_BLUETOOTH_SDP_RECORD *,void *,ulong *)
0x1800259bd  test    eax, eax
0x1800259bf  jz      loc_180025BB2
0x1800259c5  or      dword ptr [rbx+14h], 1
0x1800259c9  jmp     loc_180025BB2
0x1800259ce  mov     al, [rdx]
0x1800259d0  and     al, 0F8h
0x1800259d2  cmp     al, 8
0x1800259d4  jnz     loc_180025BB2
0x1800259da  lea     r8, [rbx+6Ch]; void *
0x1800259de  mov     rdx, rbp; struct _BLUETOOTH_SDP_RECORD *
0x1800259e1  mov     rcx, rdi; this
0x1800259e4  call    ?BthpTransposeAndExtendBytes@BthServ@Services@Bluetooth@Microsoft@@YAHPEAU_BLUETOOTH_SDP_RECORD@@PEAXPEAK@Z; Microsoft::Bluetooth::Services::BthServ::BthpTransposeAndExtendBytes(_BLUETOOTH_SDP_RECORD *,void *,ulong *)
0x1800259e9  test    eax, eax
0x1800259eb  jz      loc_180025BB2
0x1800259f1  bts     dword ptr [rbx+14h], 7
0x1800259f6  jmp     loc_180025BB2
0x1800259fb  mov     eax, ecx
0x1800259fd  sub     eax, 8
0x180025a00  jz      loc_180025B92
0x180025a06  sub     eax, 1
0x180025a09  jz      loc_180025B79
0x180025a0f  sub     eax, 1
0x180025a12  jz      loc_180025B5D
0x180025a18  sub     eax, 1
0x180025a1b  jz      loc_180025B41
0x180025a21  sub     eax, 1
0x180025a24  jz      loc_180025B21
0x180025a2a  cmp     eax, 1
0x180025a2d  jz      loc_180025BB2
0x180025a33  mov     edx, [r9]
0x180025a36  cmp     edx, ecx
0x180025a38  jnz     short loc_180025A7F
0x180025a3a  mov     edx, [rbx+10h]; unsigned __int8 *
0x180025a3d  lea     rax, [rsp+48h+arg_0]
0x180025a42  mov     rcx, [rbx+8]; this
0x180025a46  lea     rdi, [rbx+0B4h]
0x180025a4d  mov     [rsp+48h+var_20], rax; unsigned __int16 *
0x180025a52  xor     r9d, r9d; struct _SDP_STRING_TYPE_DATA *
0x180025a55  mov     qword ptr [rsp+48h+var_28], rdi; unsigned __int16
0x180025a5a  mov     [rsp+48h+arg_0], 0F8h
0x180025a62  call    ?BluetoothSdpGetString@BthServ@Services@Bluetooth@Microsoft@@YAKPEAEKPEAU_SDP_STRING_TYPE_DATA@@GPEAGPEAK@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothSdpGetString(uchar *,ulong,_SDP_STRING_TYPE_DATA *,ushort,ushort *,ulong *)
0x180025a67  test    eax, eax
0x180025a69  jnz     short loc_180025A75
0x180025a6b  bts     dword ptr [rbx+14h], 1Eh
0x180025a70  jmp     loc_180025BB2
0x180025a75  xor     eax, eax
0x180025a77  mov     [rdi], ax
0x180025a7a  jmp     loc_180025BB2
0x180025a7f  lea     eax, [rdx+1]
0x180025a82  cmp     eax, ecx
0x180025a84  jnz     short loc_180025AC4
0x180025a86  mov     edx, [rbx+10h]; unsigned __int8 *
0x180025a89  lea     rcx, [rsp+48h+arg_0]
0x180025a8e  mov     [rsp+48h+var_20], rcx; unsigned __int16 *
0x180025a93  lea     rax, [rbx+2A4h]
0x180025a9a  mov     rcx, [rbx+8]; this
0x180025a9e  mov     r9d, 1; struct _SDP_STRING_TYPE_DATA *
0x180025aa4  mov     [rsp+48h+arg_0], 0C8h
0x180025aac  mov     qword ptr [rsp+48h+var_28], rax; unsigned __int16
0x180025ab1  call    ?BluetoothSdpGetString@BthServ@Services@Bluetooth@Microsoft@@YAKPEAEKPEAU_SDP_STRING_TYPE_DATA@@GPEAGPEAK@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothSdpGetString(uchar *,ulong,_SDP_STRING_TYPE_DATA *,ushort,ushort *,ulong *)
0x180025ab6  test    eax, eax
0x180025ab8  jnz     short loc_180025B09
0x180025aba  bts     dword ptr [rbx+14h], 1Dh
0x180025abf  jmp     loc_180025BB2
0x180025ac4  lea     eax, [rdx+2]
0x180025ac7  cmp     eax, ecx
0x180025ac9  jnz     short loc_180025B17
0x180025acb  mov     edx, [rbx+10h]; unsigned __int8 *
0x180025ace  lea     rcx, [rsp+48h+arg_0]
0x180025ad3  mov     [rsp+48h+var_20], rcx; unsigned __int16 *
0x180025ad8  lea     rax, [rbx+434h]
0x180025adf  mov     rcx, [rbx+8]; this
0x180025ae3  mov     r9d, 2; struct _SDP_STRING_TYPE_DATA *
0x180025ae9  mov     [rsp+48h+arg_0], 0C8h
0x180025af1  mov     qword ptr [rsp+48h+var_28], rax; unsigned __int16
0x180025af6  call    ?BluetoothSdpGetString@BthServ@Services@Bluetooth@Microsoft@@YAKPEAEKPEAU_SDP_STRING_TYPE_DATA@@GPEAGPEAK@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothSdpGetString(uchar *,ulong,_SDP_STRING_TYPE_DATA *,ushort,ushort *,ulong *)
0x180025afb  test    eax, eax
0x180025afd  jnz     short loc_180025B09
0x180025aff  bts     dword ptr [rbx+14h], 1Ch
0x180025b04  jmp     loc_180025BB2
0x180025b09  xor     eax, eax
0x180025b0b  mov     [rbx+0B4h], ax
0x180025b12  jmp     loc_180025BB2
0x180025b17  bts     dword ptr [rbx+14h], 1Fh
0x180025b1c  jmp     loc_180025BB2
0x180025b21  mov     al, [rdx]
0x180025b23  and     al, 0F8h
0x180025b25  cmp     al, 40h ; '@'
0x180025b27  jnz     loc_180025BB2
0x180025b2d  bts     dword ptr [rbx+14h], 0Ch
0x180025b32  mov     [rbx+0A8h], rdi
0x180025b39  mov     [rbx+0B0h], esi
0x180025b3f  jmp     short loc_180025BB2
0x180025b41  mov     al, [rdx]
0x180025b43  and     al, 0F8h
0x180025b45  cmp     al, 40h ; '@'
0x180025b47  jnz     short loc_180025BB2
0x180025b49  bts     dword ptr [rbx+14h], 0Bh
0x180025b4e  mov     [rbx+98h], rdi
0x180025b55  mov     [rbx+0A0h], esi
0x180025b5b  jmp     short loc_180025BB2
0x180025b5d  mov     al, [rdx]
0x180025b5f  and     al, 0F8h
0x180025b61  cmp     al, 40h ; '@'
0x180025b63  jnz     short loc_180025BB2
0x180025b65  bts     dword ptr [rbx+14h], 0Ah
0x180025b6a  mov     [rbx+88h], rdi
0x180025b71  mov     [rbx+90h], esi
0x180025b77  jmp     short loc_180025BB2
0x180025b79  mov     al, [rdx]
0x180025b7b  and     al, 0F8h
0x180025b7d  cmp     al, 30h ; '0'
0x180025b7f  jnz     short loc_180025BB2
0x180025b81  bts     dword ptr [rbx+14h], 9
0x180025b86  mov     [rbx+78h], rdi
0x180025b8a  mov     [rbx+80h], esi
0x180025b90  jmp     short loc_180025BB2
0x180025b92  mov     al, [rdx]
0x180025b94  and     al, 0F8h
0x180025b96  cmp     al, 8
0x180025b98  jnz     short loc_180025BB2
0x180025b9a  lea     r8, [rbx+70h]; void *
0x180025b9e  mov     rdx, rbp; struct _BLUETOOTH_SDP_RECORD *
0x180025ba1  mov     rcx, rdi; this
0x180025ba4  call    ?BthpTransposeAndExtendBytes@BthServ@Services@Bluetooth@Microsoft@@YAHPEAU_BLUETOOTH_SDP_RECORD@@PEAXPEAK@Z; Microsoft::Bluetooth::Services::BthServ::BthpTransposeAndExtendBytes(_BLUETOOTH_SDP_RECORD *,void *,ulong *)
0x180025ba9  test    eax, eax
0x180025bab  jz      short loc_180025BB2
0x180025bad  bts     dword ptr [rbx+14h], 8
0x180025bb2  mov     eax, 1
0x180025bb7  mov     rbx, [rsp+48h+arg_8]
0x180025bbc  mov     rbp, [rsp+48h+arg_10]
0x180025bc1  add     rsp, 30h
0x180025bc5  pop     r14
0x180025bc7  pop     rdi
0x180025bc8  pop     rsi
0x180025bc9  retn
```
