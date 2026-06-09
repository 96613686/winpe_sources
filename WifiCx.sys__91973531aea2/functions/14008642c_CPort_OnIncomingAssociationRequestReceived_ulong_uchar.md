# CPort::OnIncomingAssociationRequestReceived(ulong,uchar *)

- ea: `0x14008642c`
- end: `0x1400868e1`
- name: `?OnIncomingAssociationRequestReceived@CPort@@QEAAXKPEAE@Z`
- size: `1205`
- prototype: `void __fastcall(CPort *this, unsigned int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x140026010`

## callees

- `0x140009420`
- `0x14000c778`
- `0x14000c940`
- `0x14000d054`
- `0x140017130`
- `0x14001a630`
- `0x14001e2c0`
- `0x14001eed0`
- `0x14002a9f8`
- `0x14002c0b4`
- `0x14003895c`
- `0x14004102c`
- `0x140050660`
- `0x140050dc8`
- `0x1400761f8`
- `0x140083f80`
- `0x14008642c`
- `0x1400dfd00`
- `0x1400dfd40`

## pseudocode

```c
void __fastcall CPort::OnIncomingAssociationRequestReceived(CPort *this, unsigned int a2, unsigned __int8 *a3)
{
  unsigned __int8 v3; // r15
  unsigned int v5; // r13d
  int v7; // edx
  int v8; // edi
  int v9; // r8d
  int v10; // edx
  __int64 v11; // rsi
  int v12; // r8d
  int *v13; // rdx
  void (__fastcall ***v14)(_QWORD); // rcx
  unsigned int v15; // r14d
  _DWORD *v16; // rsi
  int v17; // r8d
  unsigned int v18; // edx
  CAdapter *v19; // rcx
  char v20; // al
  __int64 v21; // rdx
  CPropertyCache *v22; // rax
  CPropertyCache *v23; // rax
  int v24; // edx
  int v25; // r8d
  unsigned __int8 v26[4]; // [rsp+50h] [rbp-49h] BYREF
  unsigned int v27; // [rsp+54h] [rbp-45h] BYREF
  unsigned __int8 *v28; // [rsp+58h] [rbp-41h] BYREF
  int v29; // [rsp+60h] [rbp-39h] BYREF
  int v30; // [rsp+64h] [rbp-35h] BYREF
  __int16 v31; // [rsp+68h] [rbp-31h]
  char v32; // [rsp+6Ah] [rbp-2Fh]
  unsigned int v33; // [rsp+70h] [rbp-29h]
  __int64 v34; // [rsp+78h] [rbp-21h]
  char v35; // [rsp+80h] [rbp-19h]
  int v36; // [rsp+88h] [rbp-11h]
  __int64 v37; // [rsp+90h] [rbp-9h]
  char v38; // [rsp+98h] [rbp-1h]
  __int64 v39; // [rsp+A0h] [rbp+7h] BYREF
  __int16 v40; // [rsp+A8h] [rbp+Fh]

  v29 &= ~1u;
  v30 = 0;
  v33 = 0;
  v3 = 0;
  v34 = 0;
  v35 = 0;
  v5 = a2;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  v27 = 0;
  v28 = 0;
  v26[0] = 0;
  v31 = 0;
  v32 = 0;
  v39 = 0;
  v40 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      280,
      (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids);
  }
  v8 = ParseWdiIndicationApAssociationRequestReceivedFromIhv(v5 - 48, a3 + 48, *((_QWORD *)this + 17) + 5384LL, &v29);
  if ( v8 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_35;
    LOBYTE(v7) = 2;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v7,
      v9,
      281,
      (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
      (char)this,
      *((_WORD *)this + 74),
      v8);
  }
  else
  {
    v11 = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 59) + 16LL))(*((_QWORD *)this + 59), &v30);
    if ( v11 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
        && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
      {
        v13 = &v30;
        LOBYTE(v13) = 5;
        WPP_RECORDER_SF_qD_MAC_(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)v13,
          v12,
          282,
          (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
          (char)this,
          *((_WORD *)this + 74),
          (__int64)&v30);
      }
      CPort::IndicateSinglePeerDisassociated(this, v11, 7, 14);
      (*(void (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 59) + 8LL))(*((_QWORD *)this + 59), &v30);
      v14 = (void (__fastcall ***)(_QWORD))*((_QWORD *)this + 72);
      if ( v14 )
        (**v14)(v14);
    }
    v15 = v33 + 20;
    if ( v33 < 0xFFFFFFEC )
    {
      v16 = operator new(v15);
      if ( v16 )
      {
        v18 = *((_DWORD *)this + 36);
        HIDWORD(v39) = v30;
        v19 = (CAdapter *)*((_QWORD *)this + 17);
        v40 = v31;
        LODWORD(v39) = 655744;
        CAdapter::IndicateStatus(v19, v18, 1073938445, 0, &v39, 0xAu);
        *v16 = 1311104;
        v16[1] = v30;
        *((_WORD *)v16 + 4) = v31;
        v20 = v32;
        v16[3] = 20;
        *((_BYTE *)v16 + 10) = v20;
        v16[4] = v33;
        if ( !(unsigned int)CPropertyCache::GetPropertyBuffer((CPort *)((char *)this + 480), 0x47u, &v27, &v28)
          && v27 == 16
          && *(_DWORD *)v28 == 3 )
        {
          v22 = (CPropertyCache *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)this + 17) + 8LL) + 8LL))(*((_QWORD *)this + 17) + 8LL);
          CPropertyCache::GetPropertyBoolean(v22, 0x87u, v26);
          v3 = v26[0];
        }
        LOBYTE(v21) = v3;
        CopyMgmtFrameFromNetwork(0, v21, (char *)v16 + (unsigned int)v16[3], v34, v16[4]);
        v23 = (CPropertyCache *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)this + 17) + 8LL) + 8LL))(*((_QWORD *)this + 17) + 8LL);
        if ( CPropertyCache::SetPropertyBuffer(v23, 0x33u, v5, a3)
          && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v24) = 2;
          WPP_RECORDER_SF_qD(
            WPP_GLOBAL_Control->DeviceExtension,
            v24,
            v25,
            285,
            (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
            (char)this,
            *((_WORD *)this + 74));
        }
        CAdapter::IndicateStatus(*((CAdapter **)this + 17), *((_DWORD *)this + 36), 1073938446, 0, v16, v15);
        operator delete(v16);
      }
      else
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v10) = 2;
          WPP_RECORDER_SF_qD(
            WPP_GLOBAL_Control->DeviceExtension,
            v10,
            v17,
            284,
            (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
            (char)this,
            *((_WORD *)this + 74));
        }
        LOBYTE(v8) = -102;
      }
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v10) = 2;
        WPP_RECORDER_SF_qDddd(
          WPP_GLOBAL_Control->DeviceExtension,
          v10,
          v12,
          283,
          (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
          (char)this,
          *((_WORD *)this + 74),
          v33,
          -1,
          1);
      }
      LOBYTE(v8) = 1;
    }
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v10) = 5;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v10,
      1,
      286,
      (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
      v8);
  }
LABEL_35:
  _WDI_INDICATION_SAE_AUTH_PARAMS_NEEDED_PARAMETERS::~_WDI_INDICATION_SAE_AUTH_PARAMS_NEEDED_PARAMETERS((_WDI_INDICATION_SAE_AUTH_PARAMS_NEEDED_PARAMETERS *)&v29);
}

```

## disassembly

```asm
0x14008642c  mov     [rsp-8+arg_18], rbx
0x140086431  push    rbp
0x140086432  push    rsi
0x140086433  push    rdi
0x140086434  push    r12
0x140086436  push    r13
0x140086438  push    r14
0x14008643a  push    r15
0x14008643c  lea     rbp, [rsp-27h]
0x140086441  sub     rsp, 0C0h
0x140086448  mov     rax, cs:__security_cookie
0x14008644f  xor     rax, rsp
0x140086452  mov     [rbp+57h+var_40], rax
0x140086456  and     [rbp+57h+var_90], 0FFFFFFFEh
0x14008645a  xor     eax, eax
0x14008645c  xor     r14d, r14d
0x14008645f  mov     [rbp+57h+var_8C], eax
0x140086462  mov     [rbp+57h+var_80], r14d
0x140086466  mov     r15b, r14b
0x140086469  mov     [rbp+57h+var_78], r14
0x14008646d  mov     r12, r8
0x140086470  mov     [rbp+57h+var_70], r14b
0x140086474  mov     r13d, edx
0x140086477  mov     [rbp+57h+var_68], r14d
0x14008647b  mov     rbx, rcx
0x14008647e  mov     [rbp+57h+var_60], r14
0x140086482  mov     [rbp+57h+var_58], r14b
0x140086486  mov     [rbp+57h+var_9C], r14d
0x14008648a  mov     [rbp+57h+var_98], r14
0x14008648e  mov     [rbp+57h+var_A0], r14b
0x140086492  mov     [rbp+57h+var_88], ax
0x140086496  mov     [rbp+57h+var_86], al
0x140086499  mov     [rbp+57h+var_50], rax
0x14008649d  mov     [rbp+57h+var_48], ax
0x1400864a1  lea     rax, WPP_RECORDER_INITIALIZED
0x1400864a8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400864af  lea     rsi, WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids
0x1400864b6  jz      short loc_1400864E8
0x1400864b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400864bf  cmp     byte ptr [rcx+29h], 5
0x1400864c3  jnb     short loc_1400864CC
0x1400864c5  cmp     [rcx+48h], r14w
0x1400864ca  jz      short loc_1400864E8
0x1400864cc  mov     rcx, [rcx+40h]
0x1400864d0  mov     r9d, 118h
0x1400864d6  mov     r8d, 1
0x1400864dc  mov     [rsp+0F0h+var_D0], rsi
0x1400864e1  mov     dl, 5
0x1400864e3  call    WPP_RECORDER_SF_
0x1400864e8  mov     r8, [rbx+88h]
0x1400864ef  lea     rdx, [r12+30h]
0x1400864f4  add     r8, 1508h
0x1400864fb  lea     ecx, [r13-30h]
0x1400864ff  lea     r9, [rbp+57h+var_90]
0x140086503  call    ParseWdiIndicationApAssociationRequestReceivedFromIhv
0x140086508  mov     edi, eax
0x14008650a  test    eax, eax
0x14008650c  jz      short loc_140086558
0x14008650e  lea     rax, WPP_RECORDER_INITIALIZED
0x140086515  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14008651c  jz      loc_1400868B0
0x140086522  movzx   ecx, word ptr [rbx+94h]
0x140086529  mov     r9d, 119h
0x14008652f  mov     dword ptr [rsp+0F0h+var_B8], edi
0x140086533  mov     dl, 2
0x140086535  mov     [rsp+0F0h+var_C0], ecx
0x140086539  mov     rcx, cs:WPP_GLOBAL_Control
0x140086540  mov     qword ptr [rsp+0F0h+var_C8], rbx
0x140086545  mov     [rsp+0F0h+var_D0], rsi
0x14008654a  mov     rcx, [rcx+40h]
0x14008654e  call    WPP_RECORDER_SF_qDD
0x140086553  jmp     loc_14008686C
0x140086558  mov     rcx, [rbx+1D8h]
0x14008655f  lea     rdx, [rbp+57h+var_8C]
0x140086563  mov     rax, [rcx]
0x140086566  mov     rax, [rax+10h]
0x14008656a  call    _guard_dispatch_icall
0x14008656f  mov     rsi, rax
0x140086572  test    rax, rax
0x140086575  jz      loc_140086618
0x14008657b  lea     rax, WPP_RECORDER_INITIALIZED
0x140086582  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140086589  jz      short loc_1400865D5
0x14008658b  mov     rcx, cs:WPP_GLOBAL_Control
0x140086592  cmp     byte ptr [rcx+29h], 5
0x140086596  jnb     short loc_14008659F
0x140086598  cmp     [rcx+48h], r14w
0x14008659d  jz      short loc_1400865D5
0x14008659f  movzx   eax, word ptr [rbx+94h]
0x1400865a6  lea     rdx, [rbp+57h+var_8C]
0x1400865aa  mov     rcx, [rcx+40h]
0x1400865ae  mov     r9d, 11Ah
0x1400865b4  mov     [rsp+0F0h+var_B8], rdx
0x1400865b9  mov     dl, 5
0x1400865bb  mov     [rsp+0F0h+var_C0], eax
0x1400865bf  lea     rax, WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids
0x1400865c6  mov     qword ptr [rsp+0F0h+var_C8], rbx
0x1400865cb  mov     [rsp+0F0h+var_D0], rax
0x1400865d0  call    WPP_RECORDER_SF_qD_MAC_
0x1400865d5  mov     r8d, 7
0x1400865db  mov     rdx, rsi
0x1400865de  mov     rcx, rbx
0x1400865e1  lea     r9d, [r8+7]
0x1400865e5  call    ?IndicateSinglePeerDisassociated@CPort@@QEAAXPEAVCConnectedPeer@@GW4_WDI_ASSOC_STATUS@@@Z; CPort::IndicateSinglePeerDisassociated(CConnectedPeer *,ushort,_WDI_ASSOC_STATUS)
0x1400865ea  mov     rcx, [rbx+1D8h]
0x1400865f1  lea     rdx, [rbp+57h+var_8C]
0x1400865f5  mov     rax, [rcx]
0x1400865f8  mov     rax, [rax+8]
0x1400865fc  call    _guard_dispatch_icall
0x140086601  mov     rcx, [rbx+240h]
0x140086608  test    rcx, rcx
0x14008660b  jz      short loc_140086618
0x14008660d  mov     rax, [rcx]
0x140086610  mov     rax, [rax]
0x140086613  call    _guard_dispatch_icall
0x140086618  mov     ecx, [rbp+57h+var_80]
0x14008661b  lea     r14d, [rcx+14h]
0x14008661f  cmp     r14d, 14h
0x140086623  jnb     short loc_140086687
0x140086625  lea     rax, WPP_RECORDER_INITIALIZED
0x14008662c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140086633  lea     rsi, WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids
0x14008663a  jz      short loc_14008667D
0x14008663c  movzx   eax, word ptr [rbx+94h]
0x140086643  mov     r9d, 11Bh
0x140086649  mov     [rsp+0F0h+var_A8], 0C0000001h
0x140086651  mov     dl, 2
0x140086653  mov     [rsp+0F0h+var_B0], 0FFFFFFFFh
0x14008665b  mov     dword ptr [rsp+0F0h+var_B8], ecx
0x14008665f  mov     rcx, cs:WPP_GLOBAL_Control
0x140086666  mov     [rsp+0F0h+var_C0], eax
0x14008666a  mov     qword ptr [rsp+0F0h+var_C8], rbx
0x14008666f  mov     [rsp+0F0h+var_D0], rsi
0x140086674  mov     rcx, [rcx+40h]
0x140086678  call    WPP_RECORDER_SF_qDddd
0x14008667d  mov     edi, 0C0000001h
0x140086682  jmp     loc_140086869
0x140086687  mov     ecx, r14d; unsigned __int64
0x14008668a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14008668f  mov     rsi, rax
0x140086692  test    rax, rax
0x140086695  jnz     short loc_1400866E5
0x140086697  lea     rax, WPP_RECORDER_INITIALIZED
0x14008669e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400866a5  lea     rsi, WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids
0x1400866ac  jz      short loc_1400866DB
0x1400866ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1400866b5  mov     r9d, 11Ch
0x1400866bb  movzx   eax, word ptr [rbx+94h]
0x1400866c2  mov     dl, 2
0x1400866c4  mov     [rsp+0F0h+var_C0], eax
0x1400866c8  mov     qword ptr [rsp+0F0h+var_C8], rbx
0x1400866cd  mov     rcx, [rcx+40h]
0x1400866d1  mov     [rsp+0F0h+var_D0], rsi
0x1400866d6  call    WPP_RECORDER_SF_qD
0x1400866db  mov     edi, 0C000009Ah
0x1400866e0  jmp     loc_140086869
0x1400866e5  mov     eax, [rbp+57h+var_8C]
0x1400866e8  mov     ecx, 0Ah
0x1400866ed  mov     edx, [rbx+90h]; unsigned int
0x1400866f3  xor     r9d, r9d; void *
0x1400866f6  mov     dword ptr [rbp+57h+var_50+4], eax
0x1400866f9  mov     r8d, 4003000Dh; int
0x1400866ff  movzx   eax, [rbp+57h+var_88]
0x140086703  mov     [rsp+0F0h+var_C8], ecx; unsigned int
0x140086707  mov     rcx, [rbx+88h]; this
0x14008670e  mov     [rbp+57h+var_48], ax
0x140086712  lea     rax, [rbp+57h+var_50]
0x140086716  mov     [rsp+0F0h+var_D0], rax; void *
0x14008671b  mov     dword ptr [rbp+57h+var_50], 0A0180h
0x140086722  call    ?IndicateStatus@CAdapter@@QEAAXKHPEAX0K@Z; CAdapter::IndicateStatus(ulong,int,void *,void *,ulong)
0x140086727  mov     dword ptr [rsi], 140180h
0x14008672d  lea     r9, [rbp+57h+var_98]; unsigned __int8 **
0x140086731  mov     eax, [rbp+57h+var_8C]
0x140086734  lea     r8, [rbp+57h+var_9C]; unsigned int *
0x140086738  mov     [rsi+4], eax
0x14008673b  mov     ecx, 14h
0x140086740  movzx   eax, [rbp+57h+var_88]
0x140086744  mov     edx, 47h ; 'G'; unsigned int
0x140086749  mov     [rsi+8], ax
0x14008674d  mov     al, [rbp+57h+var_86]
0x140086750  mov     [rsi+0Ch], ecx
0x140086753  lea     rcx, [rbx+1E0h]; this
0x14008675a  mov     [rsi+0Ah], al
0x14008675d  mov     eax, [rbp+57h+var_80]
0x140086760  mov     [rsi+10h], eax
0x140086763  call    ?GetPropertyBuffer@CPropertyCache@@QEAAHKPEAKPEAPEAE@Z; CPropertyCache::GetPropertyBuffer(ulong,ulong *,uchar * *)
0x140086768  test    eax, eax
0x14008676a  jnz     short loc_1400867A7
0x14008676c  cmp     [rbp+57h+var_9C], 10h
0x140086770  jnz     short loc_1400867A7
0x140086772  mov     rax, [rbp+57h+var_98]
0x140086776  cmp     dword ptr [rax], 3
0x140086779  jnz     short loc_1400867A7
0x14008677b  mov     rcx, [rbx+88h]
0x140086782  add     rcx, 8
0x140086786  mov     rax, [rcx]
0x140086789  mov     rax, [rax+8]
0x14008678d  call    _guard_dispatch_icall
0x140086792  lea     r8, [rbp+57h+var_A0]; unsigned __int8 *
0x140086796  mov     edx, 87h; unsigned int
0x14008679b  mov     rcx, rax; this
0x14008679e  call    ?GetPropertyBoolean@CPropertyCache@@QEAAHKPEAE@Z; CPropertyCache::GetPropertyBoolean(ulong,uchar *)
0x1400867a3  mov     r15b, [rbp+57h+var_A0]
0x1400867a7  mov     r8d, [rsi+0Ch]
0x1400867ab  mov     dl, r15b
0x1400867ae  mov     eax, [rsi+10h]
0x1400867b1  add     r8, rsi
0x1400867b4  mov     r9, [rbp+57h+var_78]
0x1400867b8  xor     ecx, ecx
0x1400867ba  mov     dword ptr [rsp+0F0h+var_D0], eax
0x1400867be  call    ?CopyMgmtFrameFromNetwork@@YAHW4DOT11_MGMT_SUBTYPE@@EPEAE1K@Z; CopyMgmtFrameFromNetwork(DOT11_MGMT_SUBTYPE,uchar,uchar *,uchar *,ulong)
0x1400867c3  mov     rcx, [rbx+88h]
0x1400867ca  add     rcx, 8
0x1400867ce  mov     rax, [rcx]
0x1400867d1  mov     rax, [rax+8]
0x1400867d5  call    _guard_dispatch_icall
0x1400867da  mov     r9, r12; unsigned __int8 *
0x1400867dd  mov     r8d, r13d; unsigned int
0x1400867e0  mov     edx, 33h ; '3'; unsigned int
0x1400867e5  mov     rcx, rax; this
0x1400867e8  call    ?SetPropertyBuffer@CPropertyCache@@QEAAHKKPEBE@Z; CPropertyCache::SetPropertyBuffer(ulong,ulong,uchar const *)
0x1400867ed  test    eax, eax
0x1400867ef  jz      short loc_140086835
0x1400867f1  lea     rax, WPP_RECORDER_INITIALIZED
0x1400867f8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400867ff  jz      short loc_140086835
0x140086801  movzx   eax, word ptr [rbx+94h]
0x140086808  mov     r9d, 11Dh
0x14008680e  mov     rcx, cs:WPP_GLOBAL_Control
0x140086815  mov     dl, 2
0x140086817  mov     [rsp+0F0h+var_C0], eax
0x14008681b  lea     rax, WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids
0x140086822  mov     qword ptr [rsp+0F0h+var_C8], rbx
0x140086827  mov     [rsp+0F0h+var_D0], rax
0x14008682c  mov     rcx, [rcx+40h]
0x140086830  call    WPP_RECORDER_SF_qD
0x140086835  mov     edx, [rbx+90h]; unsigned int
0x14008683b  xor     r9d, r9d; void *
0x14008683e  mov     rcx, [rbx+88h]; this
0x140086845  mov     r8d, 4003000Eh; int
0x14008684b  mov     [rsp+0F0h+var_C8], r14d; unsigned int
0x140086850  mov     [rsp+0F0h+var_D0], rsi; void *
0x140086855  call    ?IndicateStatus@CAdapter@@QEAAXKHPEAX0K@Z; CAdapter::IndicateStatus(ulong,int,void *,void *,ulong)
0x14008685a  mov     rcx, rsi; void *
0x14008685d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140086862  lea     rsi, WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids
0x140086869  xor     r14d, r14d
0x14008686c  lea     rax, WPP_RECORDER_INITIALIZED
0x140086873  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14008687a  jz      short loc_1400868B0
0x14008687c  mov     rcx, cs:WPP_GLOBAL_Control
0x140086883  cmp     byte ptr [rcx+29h], 5
0x140086887  jnb     short loc_140086890
0x140086889  cmp     [rcx+48h], r14w
0x14008688e  jz      short loc_1400868B0
0x140086890  mov     rcx, [rcx+40h]
0x140086894  mov     r9d, 11Eh
0x14008689a  mov     [rsp+0F0h+var_C8], edi
0x14008689e  mov     r8d, 1
0x1400868a4  mov     dl, 5
0x1400868a6  mov     [rsp+0F0h+var_D0], rsi
0x1400868ab  call    WPP_RECORDER_SF_d
0x1400868b0  lea     rcx, [rbp+57h+var_90]; this
0x1400868b4  call    ??1_WDI_INDICATION_SAE_AUTH_PARAMS_NEEDED_PARAMETERS@@QEAA@XZ; _WDI_INDICATION_SAE_AUTH_PARAMS_NEEDED_PARAMETERS::~_WDI_INDICATION_SAE_AUTH_PARAMS_NEEDED_PARAMETERS(void)
0x1400868b9  mov     rcx, [rbp+57h+var_40]
0x1400868bd  xor     rcx, rsp; StackCookie
0x1400868c0  call    __security_check_cookie
0x1400868c5  mov     rbx, [rsp+0F0h+arg_18]
0x1400868cd  add     rsp, 0C0h
0x1400868d4  pop     r15
0x1400868d6  pop     r14
0x1400868d8  pop     r13
0x1400868da  pop     r12
0x1400868dc  pop     rdi
0x1400868dd  pop     rsi
0x1400868de  pop     rbp
0x1400868df  retn
```
