# CSendAssociationResponseJob::HandleCommandCompletion(void *,int,int,ulong,uchar *,bool *)

- ea: `0x1400c4c60`
- end: `0x1400c52a8`
- name: `?HandleCommandCompletion@CSendAssociationResponseJob@@UEAAHPEAXHHKPEAEPEA_N@Z`
- size: `1608`
- prototype: `__int64 __usercall@<rax>(CSendAssociationResponseJob *__hidden this@<rcx>, void *@<rdx>, int@<r8d>, int@<r9d>, unsigned int, unsigned __int8 *, bool *)`
- caller_count: `0`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140009420`
- `0x140017130`
- `0x14001a630`
- `0x14001e2c0`
- `0x14001eed0`
- `0x14002a684`
- `0x14002bd34`
- `0x14002ef48`
- `0x14004186c`
- `0x140050660`
- `0x140071720`
- `0x1400761f8`
- `0x1400b37b4`
- `0x1400c47ec`
- `0x1400c4c60`
- `0x1400dfd00`
- `0x1400dfd40`

## pseudocode

```c
__int64 __fastcall CSendAssociationResponseJob::HandleCommandCompletion(
        CSendAssociationResponseJob *this,
        void *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        unsigned __int8 *a6,
        bool *a7)
{
  char v7; // r15
  unsigned int v9; // edi
  __int64 *v11; // rdx
  int v12; // r9d
  unsigned int v13; // edx
  unsigned int v14; // r8d
  unsigned int v16; // eax
  int v17; // r9d
  unsigned __int64 v18; // rcx
  unsigned int v19; // eax
  int v20; // r9d
  unsigned int v21; // r13d
  _WORD *v22; // r14
  char *v23; // rax
  char *v24; // rsi
  CPropertyCache *PortPropertyCache; // rax
  CPropertyCache *v26; // rax
  unsigned int v27; // eax
  unsigned int v28; // r14d
  unsigned int v29; // eax
  unsigned int v30; // r14d
  unsigned int *v31; // r12
  unsigned int i; // r13d
  CAdapterPropertyCache *v33; // rax
  unsigned int v34; // ecx
  unsigned int v35; // eax
  unsigned __int16 v36; // dx
  CAdapter *v37; // rcx
  struct CPort *PortFromPortId; // rax
  int v39; // edx
  int v40; // r8d
  int v41; // [rsp+30h] [rbp-B1h]
  __int64 v42; // [rsp+38h] [rbp-A9h]
  unsigned int v43; // [rsp+38h] [rbp-A9h]
  int v44; // [rsp+38h] [rbp-A9h]
  char v45; // [rsp+40h] [rbp-A1h]
  char v46; // [rsp+48h] [rbp-99h]
  unsigned __int8 v47[4]; // [rsp+50h] [rbp-91h] BYREF
  unsigned int v48; // [rsp+54h] [rbp-8Dh] BYREF
  unsigned int v49; // [rsp+58h] [rbp-89h]
  unsigned __int8 *v50; // [rsp+60h] [rbp-81h] BYREF
  __int128 v51; // [rsp+70h] [rbp-71h] BYREF
  int v52; // [rsp+80h] [rbp-61h]
  unsigned int v53; // [rsp+88h] [rbp-59h]
  _WORD *v54; // [rsp+90h] [rbp-51h]
  char v55; // [rsp+98h] [rbp-49h]
  int v56; // [rsp+A0h] [rbp-41h]
  const void *v57; // [rsp+A8h] [rbp-39h]
  char v58; // [rsp+B0h] [rbp-31h]
  unsigned int v59; // [rsp+B8h] [rbp-29h]
  __int64 v60; // [rsp+C0h] [rbp-21h]
  char v61; // [rsp+C8h] [rbp-19h]

  v53 = 0;
  v54 = 0;
  v7 = 0;
  v55 = 0;
  v56 = 0;
  v9 = a3;
  v57 = 0;
  v58 = 0;
  v59 = 0;
  v60 = 0;
  v61 = 0;
  v48 = 0;
  v50 = 0;
  v47[0] = 0;
  v51 = 0;
  v52 = 0;
  v11 = WPP_0375a23a244f3148eb5ba69ebbd77fb2_Traceguids;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v11) = 5;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v11,
      a3,
      50,
      (__int64)WPP_0375a23a244f3148eb5ba69ebbd77fb2_Traceguids,
      (char)this,
      *((_DWORD *)this + 4));
    v11 = WPP_0375a23a244f3148eb5ba69ebbd77fb2_Traceguids;
  }
  *a7 = 0;
  if ( v9 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_13;
    v12 = 51;
    v43 = v9;
    goto LABEL_8;
  }
  if ( a4 )
  {
    v9 = a4;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_13;
    v12 = 52;
    v43 = a4;
LABEL_8:
    LOBYTE(v11) = 2;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v11,
      a3,
      v12,
      (__int64)WPP_0375a23a244f3148eb5ba69ebbd77fb2_Traceguids,
      (char)this,
      *((_DWORD *)this + 4),
      v43);
    goto LABEL_9;
  }
  v16 = ParseWdiIndicationSendApAssociationResponseCompleteFromIhv(
          a5 - 48,
          a6 + 48,
          *((_QWORD *)this + 67) + 5384LL,
          &v51);
  v9 = v16;
  if ( v16 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_13;
    v17 = 53;
    v44 = v16;
    v41 = *((_DWORD *)this + 4);
    goto LABEL_20;
  }
  LODWORD(v18) = *((_DWORD *)this + 294);
  v19 = v18 + 64;
  if ( (unsigned int)v18 >= 0xFFFFFFC0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
LABEL_27:
      v9 = -1073741823;
      goto LABEL_9;
    }
    v20 = 54;
    goto LABEL_24;
  }
  LOBYTE(v18) = v53;
  if ( v53 < 6 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v13) = 2;
      WPP_RECORDER_SF_qDdd(
        WPP_GLOBAL_Control->DeviceExtension,
        v13,
        v14,
        55,
        (__int64)WPP_0375a23a244f3148eb5ba69ebbd77fb2_Traceguids,
        (char)this,
        *((_DWORD *)this + 4),
        0,
        v53);
    }
    v9 = -1073676267;
    goto LABEL_9;
  }
  v13 = v19 + v53;
  if ( v19 + v53 < v19 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_27;
    v20 = 56;
LABEL_24:
    v46 = -1;
LABEL_25:
    v45 = v18;
LABEL_26:
    LOBYTE(v13) = 2;
    WPP_RECORDER_SF_qDddd(
      WPP_GLOBAL_Control->DeviceExtension,
      v13,
      v14,
      v20,
      (__int64)WPP_0375a23a244f3148eb5ba69ebbd77fb2_Traceguids,
      (char)this,
      *((_DWORD *)this + 4),
      1,
      v45,
      v46);
    goto LABEL_27;
  }
  v14 = v59;
  v18 = 4LL * v59;
  if ( v18 > 0xFFFFFFFF )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_27;
    v46 = 4;
    v20 = 57;
    v45 = v59;
    goto LABEL_26;
  }
  v14 = v18 + v13;
  if ( (unsigned int)v18 + v13 < v13 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_27;
    v20 = 58;
    goto LABEL_39;
  }
  LOBYTE(v18) = v56;
  v21 = v14 + v56;
  v49 = v14 + v56;
  if ( v14 + v56 < v14 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_27;
    v20 = 59;
LABEL_39:
    v46 = -1;
    goto LABEL_25;
  }
  v22 = v54;
  v23 = (char *)operator new(v21);
  v24 = v23;
  if ( v23 )
  {
    *(_DWORD *)v23 = 4194688;
    *((_DWORD *)v23 + 1) = v51;
    *((_WORD *)v23 + 4) = WORD2(v51);
    *((_DWORD *)v23 + 3) = (unsigned __int16)v22[1];
    if ( v22[1] )
      v23[16] = 1;
    *(_WORD *)(v23 + 17) = WORD3(v51);
    *(_QWORD *)(v23 + 36) = *((_QWORD *)&v51 + 1);
    *((_DWORD *)v23 + 11) = v52;
    PortPropertyCache = COidJobBase::GetPortPropertyCache(this);
    if ( !(unsigned int)CPropertyCache::GetPropertyBuffer(PortPropertyCache, 0x47u, &v48, &v50)
      && v48 == 16
      && *(_DWORD *)v50 == 3 )
    {
      v26 = (CPropertyCache *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)this + 67) + 8LL) + 8LL))(*((_QWORD *)this + 67) + 8LL);
      CPropertyCache::GetPropertyBoolean(v26, 0x87u, v47);
      v7 = v47[0];
    }
    *((_DWORD *)v24 + 5) = 64;
    v27 = *((_DWORD *)this + 294);
    *((_DWORD *)v24 + 6) = v27;
    if ( v27 )
      CopyMgmtFrameFromNetwork(0, v7, (__int16 *)v24 + 32, *((const void **)this + 148), v27);
    v28 = *((_DWORD *)v24 + 6) + 64;
    *((_DWORD *)v24 + 7) = v28;
    v29 = v53;
    *((_DWORD *)v24 + 8) = v53;
    if ( v29 )
      CopyMgmtFrameFromNetwork(1, v7, (__int16 *)&v24[v28], v54, v29);
    v30 = *((_DWORD *)v24 + 8) + v28;
    *((_DWORD *)v24 + 12) = v30;
    v31 = (unsigned int *)&v24[v30];
    *((_DWORD *)v24 + 13) = 4 * v59;
    v48 = 0;
    if ( v59 )
    {
      for ( i = v48; i < v59; ++i )
      {
        v33 = (CAdapterPropertyCache *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)this + 67) + 8LL)
                                                                          + 8LL))(*((_QWORD *)this + 67) + 8LL);
        CAdapterPropertyCache::GetDot11PhyIDFromPhyType(v33, *(_DWORD *)(v60 + 4LL * i), v31++);
      }
      v21 = v49;
    }
    v34 = v30 + *((_DWORD *)v24 + 13);
    *((_DWORD *)v24 + 14) = v34;
    v35 = v56;
    *((_DWORD *)v24 + 15) = v56;
    if ( v35 )
      CopyMgmtFrameFromNetwork(5, v7, (__int16 *)&v24[v34], v57, v35);
    v36 = *((_WORD *)this + 26);
    v37 = (CAdapter *)*((_QWORD *)this + 67);
    *((_QWORD *)this + 140) = v24;
    *((_DWORD *)this + 278) = v21;
    PortFromPortId = CAdapter::GetPortFromPortId(v37, v36);
    (***((void (__fastcall ****)(_QWORD, __int64, __int64))PortFromPortId + 59))(
      *((_QWORD *)PortFromPortId + 59),
      (__int64)(v24 + 4),
      3);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v39) = 4;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        v39,
        v40,
        61,
        (__int64)WPP_0375a23a244f3148eb5ba69ebbd77fb2_Traceguids,
        (char)this,
        *((_DWORD *)this + 4));
    }
    CAdapter::SetNextAllowedScanTime(*((CAdapter **)this + 67), 0x7530u);
    goto LABEL_9;
  }
  v9 = -1073741670;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v17 = 60;
    v44 = -1073741670;
    v41 = *((_DWORD *)this + 4);
LABEL_20:
    LOBYTE(v13) = 2;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v13,
      v14,
      v17,
      (__int64)WPP_0375a23a244f3148eb5ba69ebbd77fb2_Traceguids,
      (char)this,
      v41,
      v44);
  }
LABEL_9:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v13) = 5;
    LODWORD(v42) = v9;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v13,
      v14,
      62,
      (__int64)WPP_0375a23a244f3148eb5ba69ebbd77fb2_Traceguids,
      (char)this,
      *((_DWORD *)this + 4),
      v42);
  }
LABEL_13:
  _WDI_INDICATION_SEND_AP_ASSOCIATION_RESPONSE_COMPLETE_PARAMETERS::~_WDI_INDICATION_SEND_AP_ASSOCIATION_RESPONSE_COMPLETE_PARAMETERS((_WDI_INDICATION_SEND_AP_ASSOCIATION_RESPONSE_COMPLETE_PARAMETERS *)&v51);
  return v9;
}

```

## disassembly

```asm
0x1400c4c60  push    rbp
0x1400c4c62  push    rbx
0x1400c4c63  push    rsi
0x1400c4c64  push    rdi
0x1400c4c65  push    r12
0x1400c4c67  push    r13
0x1400c4c69  push    r14
0x1400c4c6b  push    r15
0x1400c4c6d  lea     rbp, [rsp-7]
0x1400c4c72  sub     rsp, 0E8h
0x1400c4c79  mov     rax, cs:__security_cookie
0x1400c4c80  xor     rax, rsp
0x1400c4c83  mov     [rbp+3Fh+var_50], rax
0x1400c4c87  mov     r13, [rbp+3Fh+arg_28]
0x1400c4c8b  xor     eax, eax
0x1400c4c8d  mov     r14, [rbp+3Fh+arg_30]
0x1400c4c91  xor     r12d, r12d
0x1400c4c94  xorps   xmm0, xmm0
0x1400c4c97  mov     [rbp+3Fh+var_98], r12d
0x1400c4c9b  mov     [rbp+3Fh+var_90], r12
0x1400c4c9f  mov     r15b, r12b
0x1400c4ca2  mov     [rbp+3Fh+var_88], r12b
0x1400c4ca6  mov     esi, r9d
0x1400c4ca9  mov     [rbp+3Fh+var_80], r12d
0x1400c4cad  mov     edi, r8d
0x1400c4cb0  mov     [rbp+3Fh+var_78], r12
0x1400c4cb4  mov     rbx, rcx
0x1400c4cb7  mov     [rbp+3Fh+var_70], r12b
0x1400c4cbb  mov     [rbp+3Fh+var_68], r12d
0x1400c4cbf  mov     [rbp+3Fh+var_60], r12
0x1400c4cc3  mov     [rbp+3Fh+var_58], r12b
0x1400c4cc7  mov     [rsp+120h+var_CC], r12d
0x1400c4ccc  mov     [rsp+120h+var_C0], r12
0x1400c4cd1  mov     [rsp+120h+var_D0], r12b
0x1400c4cd6  movups  [rbp+3Fh+var_B0], xmm0
0x1400c4cda  mov     [rbp+3Fh+var_A0], eax
0x1400c4cdd  lea     rax, WPP_RECORDER_INITIALIZED
0x1400c4ce4  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400c4ceb  lea     rdx, WPP_0375a23a244f3148eb5ba69ebbd77fb2_Traceguids
0x1400c4cf2  jz      short loc_1400C4D38
0x1400c4cf4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c4cfb  cmp     byte ptr [rcx+29h], 5
0x1400c4cff  jnb     short loc_1400C4D08
0x1400c4d01  cmp     [rcx+48h], r12w
0x1400c4d06  jz      short loc_1400C4D38
0x1400c4d08  mov     eax, [rbx+10h]
0x1400c4d0b  mov     r9d, 32h ; '2'
0x1400c4d11  mov     rcx, [rcx+40h]
0x1400c4d15  mov     [rsp+120h+var_F0], eax
0x1400c4d19  mov     [rsp+120h+var_F8], rbx
0x1400c4d1e  mov     [rsp+120h+var_100], rdx
0x1400c4d23  mov     dl, 5
0x1400c4d25  call    WPP_RECORDER_SF_qD
0x1400c4d2a  lea     rax, WPP_RECORDER_INITIALIZED
0x1400c4d31  lea     rdx, WPP_0375a23a244f3148eb5ba69ebbd77fb2_Traceguids
0x1400c4d38  mov     [r14], r12b
0x1400c4d3b  test    edi, edi
0x1400c4d3d  jz      loc_1400C4DF6
0x1400c4d43  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400c4d4a  jz      short loc_1400C4DCA
0x1400c4d4c  mov     r9d, 33h ; '3'
0x1400c4d52  mov     dword ptr [rsp+120h+var_E8], edi
0x1400c4d56  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c4d5d  mov     eax, [rbx+10h]
0x1400c4d60  mov     [rsp+120h+var_F0], eax
0x1400c4d64  mov     [rsp+120h+var_F8], rbx
0x1400c4d69  mov     rcx, [rcx+40h]
0x1400c4d6d  mov     [rsp+120h+var_100], rdx
0x1400c4d72  mov     dl, 2
0x1400c4d74  call    WPP_RECORDER_SF_qDD
0x1400c4d79  lea     rsi, WPP_RECORDER_INITIALIZED
0x1400c4d80  lea     r14, WPP_0375a23a244f3148eb5ba69ebbd77fb2_Traceguids
0x1400c4d87  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400c4d8e  jz      short loc_1400C4DCA
0x1400c4d90  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c4d97  cmp     byte ptr [rcx+29h], 5
0x1400c4d9b  jnb     short loc_1400C4DA4
0x1400c4d9d  cmp     [rcx+48h], r12w
0x1400c4da2  jz      short loc_1400C4DCA
0x1400c4da4  mov     eax, [rbx+10h]
0x1400c4da7  mov     r9d, 3Eh ; '>'
0x1400c4dad  mov     rcx, [rcx+40h]
0x1400c4db1  mov     dl, 5
0x1400c4db3  mov     dword ptr [rsp+120h+var_E8], edi
0x1400c4db7  mov     [rsp+120h+var_F0], eax
0x1400c4dbb  mov     [rsp+120h+var_F8], rbx
0x1400c4dc0  mov     [rsp+120h+var_100], r14
0x1400c4dc5  call    WPP_RECORDER_SF_qDD
0x1400c4dca  lea     rcx, [rbp+3Fh+var_B0]; this
0x1400c4dce  call    ??1_WDI_INDICATION_SEND_AP_ASSOCIATION_RESPONSE_COMPLETE_PARAMETERS@@QEAA@XZ; _WDI_INDICATION_SEND_AP_ASSOCIATION_RESPONSE_COMPLETE_PARAMETERS::~_WDI_INDICATION_SEND_AP_ASSOCIATION_RESPONSE_COMPLETE_PARAMETERS(void)
0x1400c4dd3  mov     eax, edi
0x1400c4dd5  mov     rcx, [rbp+3Fh+var_50]
0x1400c4dd9  xor     rcx, rsp; StackCookie
0x1400c4ddc  call    __security_check_cookie
0x1400c4de1  add     rsp, 0E8h
0x1400c4de8  pop     r15
0x1400c4dea  pop     r14
0x1400c4dec  pop     r13
0x1400c4dee  pop     r12
0x1400c4df0  pop     rdi
0x1400c4df1  pop     rsi
0x1400c4df2  pop     rbx
0x1400c4df3  pop     rbp
0x1400c4df4  retn
0x1400c4df6  test    esi, esi
0x1400c4df8  jz      short loc_1400C4E14
0x1400c4dfa  mov     edi, esi
0x1400c4dfc  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400c4e03  jz      short loc_1400C4DCA
0x1400c4e05  mov     r9d, 34h ; '4'
0x1400c4e0b  mov     dword ptr [rsp+120h+var_E8], esi
0x1400c4e0f  jmp     loc_1400C4D56
0x1400c4e14  mov     r8, [rbx+218h]
0x1400c4e1b  lea     rdx, [r13+30h]
0x1400c4e1f  mov     ecx, [rbp+3Fh+arg_20]
0x1400c4e22  lea     r9, [rbp+3Fh+var_B0]
0x1400c4e26  add     r8, 1508h
0x1400c4e2d  add     ecx, 0FFFFFFD0h
0x1400c4e30  call    ParseWdiIndicationSendApAssociationResponseCompleteFromIhv
0x1400c4e35  mov     edi, eax
0x1400c4e37  test    eax, eax
0x1400c4e39  jz      short loc_1400C4E88
0x1400c4e3b  lea     rsi, WPP_RECORDER_INITIALIZED
0x1400c4e42  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400c4e49  jz      loc_1400C4DCA
0x1400c4e4f  mov     ecx, [rbx+10h]
0x1400c4e52  mov     r9d, 35h ; '5'
0x1400c4e58  mov     dword ptr [rsp+120h+var_E8], eax
0x1400c4e5c  mov     [rsp+120h+var_F0], ecx
0x1400c4e60  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c4e67  lea     r14, WPP_0375a23a244f3148eb5ba69ebbd77fb2_Traceguids
0x1400c4e6e  mov     [rsp+120h+var_F8], rbx
0x1400c4e73  mov     dl, 2
0x1400c4e75  mov     [rsp+120h+var_100], r14
0x1400c4e7a  mov     rcx, [rcx+40h]
0x1400c4e7e  call    WPP_RECORDER_SF_qDD
0x1400c4e83  jmp     loc_1400C4D87
0x1400c4e88  mov     ecx, [rbx+498h]
0x1400c4e8e  lea     eax, [rcx+40h]
0x1400c4e91  cmp     eax, 40h ; '@'
0x1400c4e94  jnb     short loc_1400C4EF4
0x1400c4e96  lea     rsi, WPP_RECORDER_INITIALIZED
0x1400c4e9d  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400c4ea4  lea     r14, WPP_0375a23a244f3148eb5ba69ebbd77fb2_Traceguids
0x1400c4eab  jz      short loc_1400C4EEA
0x1400c4ead  mov     r9d, 36h ; '6'
0x1400c4eb3  mov     dword ptr [rsp+120h+var_D8], 0FFFFFFFFh
0x1400c4ebb  mov     dword ptr [rsp+120h+var_E0], ecx
0x1400c4ebf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c4ec6  mov     dl, 2
0x1400c4ec8  mov     eax, [rbx+10h]
0x1400c4ecb  mov     dword ptr [rsp+120h+var_E8], 0C0000001h
0x1400c4ed3  mov     [rsp+120h+var_F0], eax
0x1400c4ed7  mov     rcx, [rcx+40h]
0x1400c4edb  mov     [rsp+120h+var_F8], rbx
0x1400c4ee0  mov     [rsp+120h+var_100], r14
0x1400c4ee5  call    WPP_RECORDER_SF_qDddd
0x1400c4eea  mov     edi, 0C0000001h
0x1400c4eef  jmp     loc_1400C4D87
0x1400c4ef4  mov     ecx, [rbp+3Fh+var_98]
0x1400c4ef7  cmp     ecx, 6
0x1400c4efa  jnb     short loc_1400C4F4F
0x1400c4efc  lea     rsi, WPP_RECORDER_INITIALIZED
0x1400c4f03  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400c4f0a  lea     r14, WPP_0375a23a244f3148eb5ba69ebbd77fb2_Traceguids
0x1400c4f11  jz      short loc_1400C4F45
0x1400c4f13  mov     eax, [rbx+10h]
0x1400c4f16  mov     r9d, 37h ; '7'
0x1400c4f1c  mov     dword ptr [rsp+120h+var_E0], ecx
0x1400c4f20  mov     dl, 2
0x1400c4f22  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c4f29  mov     dword ptr [rsp+120h+var_E8], r12d
0x1400c4f2e  mov     [rsp+120h+var_F0], eax
0x1400c4f32  mov     [rsp+120h+var_F8], rbx
0x1400c4f37  mov     rcx, [rcx+40h]
0x1400c4f3b  mov     [rsp+120h+var_100], r14
0x1400c4f40  call    WPP_RECORDER_SF_qDdd
0x1400c4f45  mov     edi, 0C0010015h
0x1400c4f4a  jmp     loc_1400C4D87
0x1400c4f4f  lea     edx, [rax+rcx]
0x1400c4f52  cmp     edx, eax
0x1400c4f54  jnb     short loc_1400C4F7C
0x1400c4f56  lea     rsi, WPP_RECORDER_INITIALIZED
0x1400c4f5d  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400c4f64  lea     r14, WPP_0375a23a244f3148eb5ba69ebbd77fb2_Traceguids
0x1400c4f6b  jz      loc_1400C4EEA
0x1400c4f71  mov     r9d, 38h ; '8'
0x1400c4f77  jmp     loc_1400C4EB3
0x1400c4f7c  mov     r8d, [rbp+3Fh+var_68]
0x1400c4f80  mov     eax, 0FFFFFFFFh
0x1400c4f85  mov     ecx, r8d
0x1400c4f88  shl     rcx, 2
0x1400c4f8c  cmp     rcx, rax
0x1400c4f8f  ja      loc_1400C5275
0x1400c4f95  lea     r8d, [rcx+rdx]
0x1400c4f99  cmp     r8d, edx
0x1400c4f9c  jnb     short loc_1400C4FC8
0x1400c4f9e  lea     rsi, WPP_RECORDER_INITIALIZED
0x1400c4fa5  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400c4fac  lea     r14, WPP_0375a23a244f3148eb5ba69ebbd77fb2_Traceguids
0x1400c4fb3  jz      loc_1400C4EEA
0x1400c4fb9  mov     r9d, 3Ah ; ':'
0x1400c4fbf  mov     dword ptr [rsp+120h+var_D8], eax
0x1400c4fc3  jmp     loc_1400C4EBB
0x1400c4fc8  mov     ecx, [rbp+3Fh+var_80]
0x1400c4fcb  lea     r13d, [r8+rcx]
0x1400c4fcf  mov     [rsp+120h+var_C8], r13d
0x1400c4fd4  cmp     r13d, r8d
0x1400c4fd7  jnb     short loc_1400C4FFC
0x1400c4fd9  lea     rsi, WPP_RECORDER_INITIALIZED
0x1400c4fe0  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400c4fe7  lea     r14, WPP_0375a23a244f3148eb5ba69ebbd77fb2_Traceguids
0x1400c4fee  jz      loc_1400C4EEA
0x1400c4ff4  mov     r9d, 3Bh ; ';'
0x1400c4ffa  jmp     short loc_1400C4FBF
0x1400c4ffc  mov     r14, [rbp+3Fh+var_90]
0x1400c5000  mov     ecx, r13d; unsigned __int64
0x1400c5003  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400c5008  mov     rsi, rax
0x1400c500b  test    rax, rax
0x1400c500e  jnz     short loc_1400C5041
0x1400c5010  mov     edi, 0C000009Ah
0x1400c5015  lea     rsi, WPP_RECORDER_INITIALIZED
0x1400c501c  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400c5023  jz      loc_1400C4D80
0x1400c5029  lea     r9d, [rax+3Ch]
0x1400c502d  mov     dword ptr [rsp+120h+var_E8], 0C000009Ah
0x1400c5035  mov     eax, [rbx+10h]
0x1400c5038  mov     [rsp+120h+var_F0], eax
0x1400c503c  jmp     loc_1400C4E60
0x1400c5041  mov     dword ptr [rax], 400180h
0x1400c5047  mov     eax, dword ptr [rbp+3Fh+var_B0]
0x1400c504a  mov     [rsi+4], eax
0x1400c504d  movzx   eax, word ptr [rbp+3Fh+var_B0+4]
0x1400c5051  mov     [rsi+8], ax
0x1400c5055  movzx   eax, word ptr [r14+2]
0x1400c505a  mov     [rsi+0Ch], eax
0x1400c505d  cmp     [r14+2], r12w
0x1400c5062  jz      short loc_1400C5068
0x1400c5064  mov     byte ptr [rsi+10h], 1
0x1400c5068  mov     al, byte ptr [rbp+3Fh+var_B0+6]
0x1400c506b  mov     rcx, rbx; this
0x1400c506e  mov     [rsi+11h], al
0x1400c5071  mov     al, byte ptr [rbp+3Fh+var_B0+7]
0x1400c5074  mov     [rsi+12h], al
0x1400c5077  mov     eax, dword ptr [rbp+3Fh+var_B0+8]
0x1400c507a  mov     [rsi+24h], eax
0x1400c507d  mov     eax, dword ptr [rbp+3Fh+var_B0+0Ch]
0x1400c5080  mov     [rsi+28h], eax
0x1400c5083  mov     eax, [rbp+3Fh+var_A0]
0x1400c5086  mov     [rsi+2Ch], eax
0x1400c5089  call    ?GetPortPropertyCache@COidJobBase@@IEAAPEAVCPortPropertyCache@@XZ; COidJobBase::GetPortPropertyCache(void)
0x1400c508e  lea     r9, [rsp+120h+var_C0]; unsigned __int8 **
0x1400c5093  mov     edx, 47h ; 'G'; unsigned int
0x1400c5098  lea     r8, [rsp+120h+var_CC]; unsigned int *
0x1400c509d  mov     rcx, rax; this
0x1400c50a0  call    ?GetPropertyBuffer@CPropertyCache@@QEAAHKPEAKPEAPEAE@Z; CPropertyCache::GetPropertyBuffer(ulong,ulong *,uchar * *)
0x1400c50a5  test    eax, eax
0x1400c50a7  jnz     short loc_1400C50E8
0x1400c50a9  cmp     [rsp+120h+var_CC], 10h
0x1400c50ae  jnz     short loc_1400C50E8
0x1400c50b0  mov     rax, [rsp+120h+var_C0]
0x1400c50b5  cmp     dword ptr [rax], 3
0x1400c50b8  jnz     short loc_1400C50E8
0x1400c50ba  mov     rcx, [rbx+218h]
0x1400c50c1  add     rcx, 8
0x1400c50c5  mov     rax, [rcx]
0x1400c50c8  mov     rax, [rax+8]
0x1400c50cc  call    _guard_dispatch_icall
0x1400c50d1  lea     r8, [rsp+120h+var_D0]; unsigned __int8 *
0x1400c50d6  mov     edx, 87h; unsigned int
0x1400c50db  mov     rcx, rax; this
0x1400c50de  call    ?GetPropertyBoolean@CPropertyCache@@QEAAHKPEAE@Z; CPropertyCache::GetPropertyBoolean(ulong,uchar *)
0x1400c50e3  mov     r15b, [rsp+120h+var_D0]
0x1400c50e8  mov     dword ptr [rsi+14h], 40h ; '@'
0x1400c50ef  mov     eax, [rbx+498h]
0x1400c50f5  mov     [rsi+18h], eax
0x1400c50f8  test    eax, eax
0x1400c50fa  jz      short loc_1400C5115
0x1400c50fc  mov     r9, [rbx+4A0h]
0x1400c5103  lea     r8, [rsi+40h]
0x1400c5107  mov     dl, r15b
0x1400c510a  mov     dword ptr [rsp+120h+var_100], eax
0x1400c510e  xor     ecx, ecx
0x1400c5110  call    ?CopyMgmtFrameFromNetwork@@YAHW4DOT11_MGMT_SUBTYPE@@EPEAE1K@Z; CopyMgmtFrameFromNetwork(DOT11_MGMT_SUBTYPE,uchar,uchar *,uchar *,ulong)
0x1400c5115  mov     r14d, [rsi+18h]
0x1400c5119  add     r14d, 40h ; '@'
0x1400c511d  mov     [rsi+1Ch], r14d
0x1400c5121  mov     eax, [rbp+3Fh+var_98]
0x1400c5124  mov     [rsi+20h], eax
0x1400c5127  test    eax, eax
0x1400c5129  jz      short loc_1400C5146
0x1400c512b  mov     r9, [rbp+3Fh+var_90]
0x1400c512f  mov     dl, r15b
0x1400c5132  mov     r8d, r14d
0x1400c5135  mov     ecx, 1
0x1400c513a  add     r8, rsi
0x1400c513d  mov     dword ptr [rsp+120h+var_100], eax
0x1400c5141  call    ?CopyMgmtFrameFromNetwork@@YAHW4DOT11_MGMT_SUBTYPE@@EPEAE1K@Z; CopyMgmtFrameFromNetwork(DOT11_MGMT_SUBTYPE,uchar,uchar *,uchar *,ulong)
0x1400c5146  add     r14d, [rsi+20h]
  ... truncated ...
```
