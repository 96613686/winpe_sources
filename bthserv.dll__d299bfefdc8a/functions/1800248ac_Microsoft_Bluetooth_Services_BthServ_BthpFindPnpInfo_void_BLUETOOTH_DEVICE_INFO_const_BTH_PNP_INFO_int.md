# Microsoft::Bluetooth::Services::BthServ::BthpFindPnpInfo(void *,_BLUETOOTH_DEVICE_INFO const *,_BTH_PNP_INFO *,int)

- ea: `0x1800248ac`
- end: `0x180024bcb`
- name: `?BthpFindPnpInfo@BthServ@Services@Bluetooth@Microsoft@@YAXPEAXPEBU_BLUETOOTH_DEVICE_INFO@@PEAU_BTH_PNP_INFO@@H@Z`
- size: `799`
- prototype: `void __fastcall(Microsoft::Bluetooth::Services::BthServ *this, void *, const struct _BLUETOOTH_DEVICE_INFO *, struct _BTH_PNP_INFO *)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800237e8`
- `0x180025e24`

## callees

- `0x180001790`
- `0x1800024ac`
- `0x180022af0`
- `0x180022b34`
- `0x180022d0c`
- `0x180022f30`
- `0x1800231ac`
- `0x180023f44`
- `0x1800248ac`
- `0x180024ca8`
- `0x180025724`
- `0x180026308`
- `0x180032c44`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800249ae`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800249ae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002499f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024a1b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002499f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024a1b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024a29`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024a29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024a02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024a02`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024964`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024974`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024a31`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024a7c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024b37`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024964`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024974`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024a31`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024a7c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024b37`

## pseudocode

```c
void __fastcall Microsoft::Bluetooth::Services::BthServ::BthpFindPnpInfo(
        Microsoft::Bluetooth::Services::BthServ *this,
        void *a2,
        const struct _BLUETOOTH_DEVICE_INFO *a3,
        struct _BTH_PNP_INFO *a4)
{
  int v7; // esi
  int v8; // r15d
  void **FirstServiceInternal; // r12
  struct _BLUETOOTH_SERVICE_RECORD *v10; // r8
  Microsoft::Bluetooth::Services::BthServ *v11; // rdi
  HANDLE ProcessHeap; // rax
  Microsoft::Bluetooth::Services::BthServ *v13; // rbx
  unsigned int *v14; // r9
  struct _BLUETOOTH_SDP_RECORD *v15; // rax
  struct _GUID *v16; // r8
  struct _GUID *v17; // r9
  DWORD LastError; // edi
  Microsoft::Bluetooth::Services::BthServ *v19; // r14
  HANDLE v20; // rax
  struct _GUID *v21; // r8
  struct _GUID *v22; // r9
  Microsoft::Bluetooth::Services::BthServ *v23; // rbx
  __int64 v24; // rdi
  Microsoft::Bluetooth::Services::BthServ *v25; // rdx
  struct _BLUETOOTH_SDP_RECORD *v26; // rax
  Microsoft::Bluetooth::Services::BthServ *v27; // rdi
  struct _BLUETOOTH_SDP_RECORD *v28; // rbx
  Microsoft::Bluetooth::Services::BthServ *Record; // rax
  Microsoft::Bluetooth::Services::BthServ *v30; // r15
  struct _BLUETOOTH_SDP_RECORD *v31; // rax
  unsigned int v32; // esi
  Microsoft::Bluetooth::Services::BthServ *v33; // rcx
  void *v34; // rdx
  unsigned int v35; // [rsp+20h] [rbp-E0h] BYREF
  unsigned int v36; // [rsp+24h] [rbp-DCh] BYREF
  int v37; // [rsp+28h] [rbp-D8h]
  __int128 Buf2; // [rsp+30h] [rbp-D0h] BYREF
  Microsoft::Bluetooth::Services::BthServ *v39; // [rsp+40h] [rbp-C0h]
  __int64 v40; // [rsp+48h] [rbp-B8h]
  int v41; // [rsp+50h] [rbp-B0h] BYREF
  char v42[4]; // [rsp+54h] [rbp-ACh] BYREF
  Microsoft::Bluetooth::Services::BthServ *v43; // [rsp+58h] [rbp-A8h]
  unsigned int v44; // [rsp+60h] [rbp-A0h]
  char v45; // [rsp+64h] [rbp-9Ch]
  Microsoft::Bluetooth::Services::BthServ *v46; // [rsp+70h] [rbp-90h]

  v7 = (int)a4;
  memset_0(v42, 0, 0x5C4u);
  v8 = 0;
  *(_QWORD *)&Buf2 = 32;
  v40 = 0;
  v37 = 0;
  *((_QWORD *)&Buf2 + 1) = a2;
  v39 = this;
  v41 = 1480;
  FirstServiceInternal = (void **)Microsoft::Bluetooth::Services::BthServ::BluetoothFindFirstServiceInternal(
                                    (__int64)&Buf2,
                                    &v41,
                                    v7 == 0 ? 2 : 0);
  if ( FirstServiceInternal )
  {
    while ( 1 )
    {
      Buf2 = 0;
      if ( v41 != 1480 )
      {
        SetLastError(0x51Au);
        goto LABEL_35;
      }
      SetLastError(0xDu);
      if ( (v45 & 2) != 0 )
      {
        v11 = v46;
        if ( v46 )
        {
          if ( (*(_BYTE *)v46 & 0xF8) == 0x30 )
          {
            ProcessHeap = GetProcessHeap();
            v13 = (Microsoft::Bluetooth::Services::BthServ *)HeapAlloc(ProcessHeap, 0, 0x18u);
            if ( v13 )
              break;
          }
        }
      }
LABEL_35:
      if ( !(unsigned int)Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextService(
                            (Microsoft::Bluetooth::Services::BthServ *)FirstServiceInternal,
                            (char *)&v41,
                            v10)
        || v8 )
      {
        Microsoft::Bluetooth::Services::BthServ::BluetoothFindServiceClose(FirstServiceInternal, v34);
        return;
      }
    }
    v35 = 0;
    v15 = Microsoft::Bluetooth::Services::BthServ::BthpInnerRecord(
            v11,
            (Microsoft::Bluetooth::Services::BthServ *)((char *)v43 + v44),
            &v35,
            v14);
    *(_QWORD *)v13 = v15;
    if ( v15 )
    {
      *((_QWORD *)v13 + 1) = (char *)v15 + v35;
      if ( (unsigned int)Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextClassId(
                           (Microsoft::Bluetooth::Services::BthServ **)v13,
                           (struct _BLUETOOTH_SDP_RECORD *)&Buf2,
                           v16,
                           v17) )
      {
        LastError = 0;
        v19 = v13;
        goto LABEL_14;
      }
      LastError = GetLastError();
    }
    else
    {
      LastError = 1168;
    }
    v19 = 0;
    v20 = GetProcessHeap();
    HeapFree(v20, 0, v13);
LABEL_14:
    SetLastError(LastError);
    if ( !v19 )
      goto LABEL_35;
    while ( 1 )
    {
      if ( !memcmp_0(&PnPInformationServiceClass_UUID, &Buf2, 0x10u) )
      {
        v23 = v43;
        if ( v43 && (v24 = v44) != 0 )
        {
          SetLastError(0xDu);
          if ( (*(_BYTE *)v23 & 0xF8) == 0x30 )
          {
            v35 = 0;
            v26 = Microsoft::Bluetooth::Services::BthServ::BthpInnerRecord(
                    v23,
                    (Microsoft::Bluetooth::Services::BthServ *)((char *)v23 + v24),
                    &v35,
                    &v22->Data1);
            v27 = v26;
            if ( v26 )
            {
              v28 = (struct _BLUETOOTH_SDP_RECORD *)((char *)v26 + v35);
              while ( v27 < v28 )
              {
                Record = Microsoft::Bluetooth::Services::BthServ::BthpNextRecord(v27, v28, v21);
                v30 = Record;
                if ( Record )
                {
                  v31 = Microsoft::Bluetooth::Services::BthServ::BthpNextRecord(Record, v28, v21);
                  if ( !v31 )
                    break;
                  v32 = (_DWORD)v31 - (_DWORD)v30;
                  v25 = v27;
                  v33 = v27;
                  v27 = v31;
                  if ( (int)v31 - (int)v30 < v35 )
                  {
                    LOBYTE(v25) = *(_BYTE *)v33 & 0xF8;
                    if ( (_BYTE)v25 != 8 )
                      break;
                    v36 = 0;
                    if ( !(unsigned int)Microsoft::Bluetooth::Services::BthServ::BthpTransposeAndExtendBytes(
                                          v33,
                                          v28,
                                          &v36,
                                          &v22->Data1)
                      || !(unsigned int)Microsoft::Bluetooth::Services::BthServ::BthpExtractPNPAttributes(
                                          (Microsoft::Bluetooth::Services::BthServ *)v36,
                                          v30,
                                          (unsigned __int8 *)v32,
                                          (__int64)a3) )
                    {
                      break;
                    }
                  }
                }
              }
            }
          }
        }
        else
        {
          SetLastError(0x57u);
        }
        if ( (a3->fRemembered & 0xF) == 0xF )
        {
          v8 = 1;
          v37 = 1;
LABEL_34:
          Microsoft::Bluetooth::Services::BthServ::BluetoothFindClassIdClose(v19, v25);
          goto LABEL_35;
        }
        a3->fRemembered = 0;
      }
      if ( !(unsigned int)Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextClassId(
                            (Microsoft::Bluetooth::Services::BthServ **)v19,
                            (struct _BLUETOOTH_SDP_RECORD *)&Buf2,
                            v21,
                            v22) )
      {
        v8 = v37;
        goto LABEL_34;
      }
    }
  }
}

```

## disassembly

```asm
0x1800248ac  mov     [rsp-8+arg_18], rbx
0x1800248b1  push    rbp
0x1800248b2  push    rsi
0x1800248b3  push    rdi
0x1800248b4  push    r12
0x1800248b6  push    r13
0x1800248b8  push    r14
0x1800248ba  push    r15
0x1800248bc  lea     rbp, [rsp-530h]
0x1800248c4  sub     rsp, 630h
0x1800248cb  mov     rax, cs:__security_cookie
0x1800248d2  xor     rax, rsp
0x1800248d5  mov     [rbp+560h+var_40], rax
0x1800248dc  mov     r13, r8
0x1800248df  mov     rdi, rdx
0x1800248e2  mov     rbx, rcx
0x1800248e5  xor     edx, edx; Val
0x1800248e7  mov     r8d, 5C4h; Size
0x1800248ed  lea     rcx, [rsp+660h+var_60C]; void *
0x1800248f2  mov     esi, r9d
0x1800248f5  call    memset_0
0x1800248fa  xor     r15d, r15d
0x1800248fd  mov     qword ptr [rsp+660h+Buf2], 20h ; ' '
0x180024906  neg     esi
0x180024908  mov     [rsp+660h+var_618], 0
0x180024911  lea     rdx, [rsp+660h+var_610]
0x180024916  mov     [rsp+660h+var_638], r15d
0x18002491b  sbb     r8d, r8d
0x18002491e  mov     qword ptr [rsp+660h+Buf2+8], rdi
0x180024923  not     r8d
0x180024926  mov     [rsp+660h+var_620], rbx
0x18002492b  and     r8d, 2
0x18002492f  mov     [rsp+660h+var_610], 5C8h
0x180024937  lea     rcx, [rsp+660h+Buf2]
0x18002493c  call    ?BluetoothFindFirstServiceInternal@BthServ@Services@Bluetooth@Microsoft@@YAPEAXPEBU_BLUETOOTH_SDP_SEARCH_PARAMS@@PEAU_BLUETOOTH_SERVICE_RECORD@@W4_BTHSERV_QUERY_TYPE@@@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindFirstServiceInternal(_BLUETOOTH_SDP_SEARCH_PARAMS const *,_BLUETOOTH_SERVICE_RECORD *,_BTHSERV_QUERY_TYPE)
0x180024941  mov     r12, rax
0x180024944  test    rax, rax
0x180024947  jz      loc_180024B94
0x18002494d  cmp     [rsp+660h+var_610], 5C8h
0x180024955  xorps   xmm0, xmm0
0x180024958  movups  [rsp+660h+Buf2], xmm0
0x18002495d  jz      short loc_18002496F
0x18002495f  mov     ecx, 51Ah; dwErrCode
0x180024964  call    cs:__imp_SetLastError
0x18002496a  jmp     loc_180024B72
0x18002496f  mov     ecx, 0Dh; dwErrCode
0x180024974  call    cs:__imp_SetLastError
0x18002497a  test    [rsp+660h+var_5FC], 2
0x18002497f  jz      loc_180024B72
0x180024985  mov     rdi, [rsp+660h+var_5F0]
0x18002498a  test    rdi, rdi
0x18002498d  jz      loc_180024B72
0x180024993  mov     al, [rdi]
0x180024995  and     al, 0F8h
0x180024997  cmp     al, 30h ; '0'
0x180024999  jnz     loc_180024B72
0x18002499f  call    cs:__imp_GetProcessHeap
0x1800249a5  xor     edx, edx; dwFlags
0x1800249a7  mov     rcx, rax; hHeap
0x1800249aa  lea     r8d, [rdx+18h]; dwBytes
0x1800249ae  call    cs:__imp_HeapAlloc
0x1800249b4  mov     rbx, rax
0x1800249b7  test    rax, rax
0x1800249ba  jz      loc_180024B72
0x1800249c0  mov     edx, [rsp+660h+var_600]
0x1800249c4  lea     r8, [rsp+660h+var_640]; void *
0x1800249c9  add     rdx, [rsp+660h+var_608]; struct _BLUETOOTH_SDP_RECORD *
0x1800249ce  mov     rcx, rdi; this
0x1800249d1  mov     dword ptr [rsp+660h+var_640], 0
0x1800249d9  call    ?BthpInnerRecord@BthServ@Services@Bluetooth@Microsoft@@YAPEAU_BLUETOOTH_SDP_RECORD@@PEAU5@PEAXPEAK@Z; Microsoft::Bluetooth::Services::BthServ::BthpInnerRecord(_BLUETOOTH_SDP_RECORD *,void *,ulong *)
0x1800249de  mov     [rbx], rax
0x1800249e1  test    rax, rax
0x1800249e4  jz      short loc_180024A13
0x1800249e6  mov     ecx, dword ptr [rsp+660h+var_640]
0x1800249ea  lea     rdx, [rsp+660h+Buf2]; void *
0x1800249ef  add     rcx, rax
0x1800249f2  mov     [rbx+8], rcx
0x1800249f6  mov     rcx, rbx; this
0x1800249f9  call    ?BluetoothFindNextClassId@BthServ@Services@Bluetooth@Microsoft@@YAHPEAXPEAU_GUID@@@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextClassId(void *,_GUID *)
0x1800249fe  test    eax, eax
0x180024a00  jnz     short loc_180024A0C
0x180024a02  call    cs:__imp_GetLastError
0x180024a08  mov     edi, eax
0x180024a0a  jmp     short loc_180024A18
0x180024a0c  xor     edi, edi
0x180024a0e  mov     r14, rbx
0x180024a11  jmp     short loc_180024A2F
0x180024a13  mov     edi, 490h
0x180024a18  xor     r14d, r14d
0x180024a1b  call    cs:__imp_GetProcessHeap
0x180024a21  mov     r8, rbx; lpMem
0x180024a24  xor     edx, edx; dwFlags
0x180024a26  mov     rcx, rax; hHeap
0x180024a29  call    cs:__imp_HeapFree
0x180024a2f  mov     ecx, edi; dwErrCode
0x180024a31  call    cs:__imp_SetLastError
0x180024a37  test    r14, r14
0x180024a3a  jz      loc_180024B72
0x180024a40  mov     r8d, 10h; Size
0x180024a46  lea     rdx, [rsp+660h+Buf2]; Buf2
0x180024a4b  lea     rcx, PnPInformationServiceClass_UUID; Buf1
0x180024a52  call    memcmp_0
0x180024a57  test    eax, eax
0x180024a59  jnz     loc_180024B50
0x180024a5f  mov     rbx, [rsp+660h+var_608]
0x180024a64  test    rbx, rbx
0x180024a67  jz      loc_180024B32
0x180024a6d  mov     edi, [rsp+660h+var_600]
0x180024a71  test    edi, edi
0x180024a73  jz      loc_180024B32
0x180024a79  lea     ecx, [rax+0Dh]; dwErrCode
0x180024a7c  call    cs:__imp_SetLastError
0x180024a82  mov     al, [rbx]
0x180024a84  and     al, 0F8h
0x180024a86  cmp     al, 30h ; '0'
0x180024a88  jnz     loc_180024B3D
0x180024a8e  lea     rdx, [rbx+rdi]; struct _BLUETOOTH_SDP_RECORD *
0x180024a92  mov     dword ptr [rsp+660h+var_640], 0; void *
0x180024a9a  lea     r8, [rsp+660h+var_640]; void *
0x180024a9f  mov     rcx, rbx; this
0x180024aa2  call    ?BthpInnerRecord@BthServ@Services@Bluetooth@Microsoft@@YAPEAU_BLUETOOTH_SDP_RECORD@@PEAU5@PEAXPEAK@Z; Microsoft::Bluetooth::Services::BthServ::BthpInnerRecord(_BLUETOOTH_SDP_RECORD *,void *,ulong *)
0x180024aa7  mov     rdi, rax
0x180024aaa  test    rax, rax
0x180024aad  jz      loc_180024B3D
0x180024ab3  mov     ebx, dword ptr [rsp+660h+var_640]
0x180024ab7  add     rbx, rax
0x180024aba  cmp     rdi, rbx
0x180024abd  jnb     short loc_180024B3D
0x180024abf  mov     rdx, rbx; struct _BLUETOOTH_SDP_RECORD *
0x180024ac2  mov     rcx, rdi; this
0x180024ac5  call    ?BthpNextRecord@BthServ@Services@Bluetooth@Microsoft@@YAPEAU_BLUETOOTH_SDP_RECORD@@PEAU5@PEAX@Z; Microsoft::Bluetooth::Services::BthServ::BthpNextRecord(_BLUETOOTH_SDP_RECORD *,void *)
0x180024aca  mov     r15, rax
0x180024acd  test    rax, rax
0x180024ad0  jz      short loc_180024ABA
0x180024ad2  mov     rdx, rbx; struct _BLUETOOTH_SDP_RECORD *
0x180024ad5  mov     rcx, rax; this
0x180024ad8  call    ?BthpNextRecord@BthServ@Services@Bluetooth@Microsoft@@YAPEAU_BLUETOOTH_SDP_RECORD@@PEAU5@PEAX@Z; Microsoft::Bluetooth::Services::BthServ::BthpNextRecord(_BLUETOOTH_SDP_RECORD *,void *)
0x180024add  mov     rsi, rax
0x180024ae0  test    rax, rax
0x180024ae3  jz      short loc_180024B3D
0x180024ae5  sub     esi, r15d
0x180024ae8  mov     rdx, rdi
0x180024aeb  mov     rcx, rdi; this
0x180024aee  mov     rdi, rax
0x180024af1  cmp     esi, dword ptr [rsp+660h+var_640]
0x180024af5  jnb     short loc_180024ABA
0x180024af7  mov     dl, [rcx]
0x180024af9  and     dl, 0F8h
0x180024afc  cmp     dl, 8
0x180024aff  jnz     short loc_180024B3D
0x180024b01  lea     r8, [rsp+660h+var_640+4]; void *
0x180024b06  mov     dword ptr [rsp+660h+var_640+4], 0
0x180024b0e  mov     rdx, rbx; struct _BLUETOOTH_SDP_RECORD *
0x180024b11  call    ?BthpTransposeAndExtendBytes@BthServ@Services@Bluetooth@Microsoft@@YAHPEAU_BLUETOOTH_SDP_RECORD@@PEAXPEAK@Z; Microsoft::Bluetooth::Services::BthServ::BthpTransposeAndExtendBytes(_BLUETOOTH_SDP_RECORD *,void *,ulong *)
0x180024b16  test    eax, eax
0x180024b18  jz      short loc_180024B3D
0x180024b1a  mov     ecx, dword ptr [rsp+660h+var_640+4]; this
0x180024b1e  mov     r9, r13; unsigned int
0x180024b21  mov     r8d, esi; unsigned __int8 *
0x180024b24  mov     rdx, r15; unsigned int
0x180024b27  call    ?BthpExtractPNPAttributes@BthServ@Services@Bluetooth@Microsoft@@YAHKPEAEKPEAX@Z; Microsoft::Bluetooth::Services::BthServ::BthpExtractPNPAttributes(ulong,uchar *,ulong,void *)
0x180024b2c  test    eax, eax
0x180024b2e  jnz     short loc_180024ABA
0x180024b30  jmp     short loc_180024B3D
0x180024b32  mov     ecx, 57h ; 'W'; dwErrCode
0x180024b37  call    cs:__imp_SetLastError
0x180024b3d  mov     eax, [r13+18h]
0x180024b41  and     eax, 0Fh
0x180024b44  cmp     al, 0Fh
0x180024b46  jz      short loc_180024BBE
0x180024b48  mov     dword ptr [r13+18h], 0
0x180024b50  lea     rdx, [rsp+660h+Buf2]; void *
0x180024b55  mov     rcx, r14; this
0x180024b58  call    ?BluetoothFindNextClassId@BthServ@Services@Bluetooth@Microsoft@@YAHPEAXPEAU_GUID@@@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextClassId(void *,_GUID *)
0x180024b5d  test    eax, eax
0x180024b5f  jnz     loc_180024A40
0x180024b65  mov     r15d, [rsp+660h+var_638]
0x180024b6a  mov     rcx, r14; this
0x180024b6d  call    ?BluetoothFindClassIdClose@BthServ@Services@Bluetooth@Microsoft@@YAHPEAX@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindClassIdClose(void *)
0x180024b72  lea     rdx, [rsp+660h+var_610]; void *
0x180024b77  mov     rcx, r12; this
0x180024b7a  call    ?BluetoothFindNextService@BthServ@Services@Bluetooth@Microsoft@@YAHPEAXPEAU_BLUETOOTH_SERVICE_RECORD@@@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextService(void *,_BLUETOOTH_SERVICE_RECORD *)
0x180024b7f  test    eax, eax
0x180024b81  jz      short loc_180024B8C
0x180024b83  test    r15d, r15d
0x180024b86  jz      loc_18002494D
0x180024b8c  mov     rcx, r12; this
0x180024b8f  call    ?BluetoothFindServiceClose@BthServ@Services@Bluetooth@Microsoft@@YAHPEAX@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindServiceClose(void *)
0x180024b94  mov     rcx, [rbp+560h+var_40]
0x180024b9b  xor     rcx, rsp; StackCookie
0x180024b9e  call    __security_check_cookie
0x180024ba3  mov     rbx, [rsp+660h+arg_18]
0x180024bab  add     rsp, 630h
0x180024bb2  pop     r15
0x180024bb4  pop     r14
0x180024bb6  pop     r13
0x180024bb8  pop     r12
0x180024bba  pop     rdi
0x180024bbb  pop     rsi
0x180024bbc  pop     rbp
0x180024bbd  retn
0x180024bbe  mov     r15d, 1
0x180024bc4  mov     [rsp+660h+var_638], r15d
0x180024bc9  jmp     short loc_180024B6A
```
