# CConnectJob::FillConnectionProfileParameters(CPortPropertyCache *,_WFC_CONNECTION_PROFILE_PARAMETERS *)

- ea: `0x1400a73d4`
- end: `0x1400a77e2`
- name: `?FillConnectionProfileParameters@CConnectJob@@AEAAHPEAVCPortPropertyCache@@PEAU_WFC_CONNECTION_PROFILE_PARAMETERS@@@Z`
- size: `1038`
- prototype: `int(CConnectJob *__hidden this, struct CPortPropertyCache *, struct _WFC_CONNECTION_PROFILE_PARAMETERS *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x1400aced0`

## callees

- `0x14001a630`
- `0x14001e2c0`
- `0x14001eed0`
- `0x14002ef48`
- `0x1400565c4`
- `0x1400683ac`
- `0x1400a73d4`
- `0x1400a93a8`
- `0x1400b0448`
- `0x1400b6b68`
- `0x1400b6c38`

## pseudocode

```c
__int64 __fastcall CConnectJob::FillConnectionProfileParameters(
        CConnectJob *this,
        struct CPortPropertyCache *a2,
        struct _WFC_CONNECTION_PROFILE_PARAMETERS *a3)
{
  struct _WFC_CONNECTION_PROFILE_PARAMETERS *v6; // r8
  struct CPort *PortFromPortId; // r15
  const struct _DOT11_SSID *v8; // rdx
  int v9; // edx
  unsigned int v10; // esi
  int v11; // r8d
  int PropertyBuffer; // eax
  int v13; // edx
  int v14; // r8d
  int v15; // r9d
  unsigned __int8 *v16; // rax
  unsigned __int8 *v17; // rcx
  __int64 v18; // r8
  int i; // edx
  int v20; // eax
  int v21; // edx
  int v22; // r8d
  __int16 v23; // ax
  int v24; // edx
  int v25; // r8d
  __int16 v26; // ax
  int v27; // edx
  int v28; // r8d
  __int16 v29; // ax
  int v31; // [rsp+20h] [rbp-30h]
  int v32; // [rsp+20h] [rbp-30h]
  int v33; // [rsp+20h] [rbp-30h]
  int v34; // [rsp+20h] [rbp-30h]
  __int64 v35; // [rsp+38h] [rbp-18h]
  unsigned __int8 *v36[2]; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v37; // [rsp+90h] [rbp+40h] BYREF
  unsigned __int8 *v38; // [rsp+A8h] [rbp+58h] BYREF

  PortFromPortId = CAdapter::GetPortFromPortId(*((CAdapter **)this + 67), *((_WORD *)this + 26));
  v8 = &WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v8) = 5;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v8,
      (_DWORD)v6,
      246,
      (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
      (char)this,
      *((_DWORD *)this + 4));
  }
  v10 = CConnectHelpers::PopulateConnectionParameters(a2, a3, v6);
  if ( v10 )
    goto LABEL_31;
  CConnectJob::GetMloConfiguration(this, a3);
  if ( *((_BYTE *)this + 2784) )
  {
    v38 = 0;
    v36[0] = 0;
    v37 = 0;
    *(_WORD *)a3 = 0;
    *((_QWORD *)a3 + 1) = 0;
    *((_BYTE *)a3 + 108) = 0;
    PropertyBuffer = CPropertyCache::GetPropertyBuffer(a2, v10 + 58, &v37, &v38);
    v10 = PropertyBuffer;
    if ( PropertyBuffer )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return v10;
      v15 = 247;
      goto LABEL_10;
    }
    v16 = v38;
    *(_OWORD *)((char *)this + 2788) = *(_OWORD *)v38;
    *(_OWORD *)((char *)this + 2804) = *((_OWORD *)v16 + 1);
    *((_OWORD *)this + 176) = *(_OWORD *)(v16 + 28);
    *(_WORD *)a3 = 1;
    *((_QWORD *)a3 + 1) = (char *)this + 2796;
    PropertyBuffer = CPropertyCache::GetPropertyBuffer(a2, 0x3Fu, &v37, v36);
    v10 = PropertyBuffer;
    if ( PropertyBuffer )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return v10;
      v15 = 248;
LABEL_10:
      LOBYTE(v13) = 2;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        v13,
        v14,
        v15,
        (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
        (char)this,
        *((_DWORD *)this + 4),
        PropertyBuffer);
LABEL_31:
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
        && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
      {
        LOBYTE(v9) = 5;
        LODWORD(v35) = v10;
        WPP_RECORDER_SF_qDD(
          WPP_GLOBAL_Control->DeviceExtension,
          v9,
          v11,
          254,
          (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
          (char)this,
          *((_DWORD *)this + 4),
          v35);
      }
      return v10;
    }
    v17 = v36[0];
    *((_BYTE *)this + 2832) = v36[0][17] != 0;
    *((_BYTE *)this + 2833) = v17[16] != 0;
    if ( (*((_DWORD *)this + 158) & 1) != 0 )
    {
      *(_DWORD *)((char *)this + 2834) = *((_DWORD *)v17 + 1);
      *((_BYTE *)this + 2838) = v17[8];
    }
  }
  v18 = *((unsigned __int16 *)a3 + 28);
  for ( i = 0; (unsigned __int16)i < (unsigned __int16)v18; LOWORD(i) = i + 1 )
  {
    v20 = *(_DWORD *)(*((_QWORD *)a3 + 8) + 4LL * (unsigned __int16)i);
    if ( v20 == 6 || (unsigned int)(v20 - 8) <= 3 )
    {
      LOBYTE(v18) = 1;
      v10 = CPropertyCache::SetPropertyBoolean(a2, 48, v18);
      if ( v10 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(i) = 2;
        WPP_RECORDER_SF_qDD(
          WPP_GLOBAL_Control->DeviceExtension,
          i,
          v18,
          249,
          (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
          (char)this,
          *((_DWORD *)this + 4));
      }
      break;
    }
  }
  if ( *((_DWORD *)PortFromPortId + 38) == 16 )
    v10 = CAdapter::SetConnectedBssList(*((CAdapter **)this + 67), PortFromPortId, a3, WDI_OPERATION_MODE_STA, 1);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(i) = 4;
    WPP_RECORDER_SF__SSID_(WPP_GLOBAL_Control->DeviceExtension, i, v18, 250, v31, *((_QWORD *)a3 + 1));
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v23 = *((_WORD *)a3 + 28);
      *(_OWORD *)v36 = 0;
      LOBYTE(v21) = 4;
      LOWORD(v36[0]) = 4 * v23;
      v36[1] = *((unsigned __int8 **)a3 + 8);
      WPP_RECORDER_SF__HEX_(WPP_GLOBAL_Control->DeviceExtension, v21, v22, 251, v32, (__int64)v36);
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v26 = *((_WORD *)a3 + 36);
        *(_OWORD *)v36 = 0;
        LOBYTE(v24) = 4;
        LOWORD(v36[0]) = 4 * v26;
        v36[1] = *((unsigned __int8 **)a3 + 10);
        WPP_RECORDER_SF__HEX_(WPP_GLOBAL_Control->DeviceExtension, v24, v25, 252, v33, (__int64)v36);
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v29 = *((_WORD *)a3 + 44);
          *(_OWORD *)v36 = 0;
          LOBYTE(v27) = 4;
          LOWORD(v36[0]) = 4 * v29;
          v36[1] = *((unsigned __int8 **)a3 + 12);
          WPP_RECORDER_SF__HEX_(WPP_GLOBAL_Control->DeviceExtension, v27, v28, 253, v34, (__int64)v36);
          goto LABEL_31;
        }
      }
    }
  }
  return v10;
}

```

## disassembly

```asm
0x1400a73d4  mov     [rsp-38h+arg_8], rbx
0x1400a73d9  push    rbp
0x1400a73da  push    rsi
0x1400a73db  push    rdi
0x1400a73dc  push    r12
0x1400a73de  push    r13
0x1400a73e0  push    r14
0x1400a73e2  push    r15
0x1400a73e4  mov     rbp, rsp
0x1400a73e7  sub     rsp, 50h
0x1400a73eb  mov     r14, rdx
0x1400a73ee  mov     rbx, rcx
0x1400a73f1  movzx   edx, word ptr [rcx+34h]; unsigned __int16
0x1400a73f5  mov     rdi, r8
0x1400a73f8  mov     rcx, [rcx+218h]; this
0x1400a73ff  call    ?GetPortFromPortId@CAdapter@@QEAAPEAVCPort@@G@Z; CAdapter::GetPortFromPortId(ushort)
0x1400a7404  mov     r15, rax
0x1400a7407  lea     r13, WPP_RECORDER_INITIALIZED
0x1400a740e  xor     r12d, r12d
0x1400a7411  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400a7418  lea     rdx, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400a741f  jz      short loc_1400A7457
0x1400a7421  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a7428  cmp     byte ptr [rcx+29h], 5
0x1400a742c  jnb     short loc_1400A7435
0x1400a742e  cmp     [rcx+48h], r12w
0x1400a7433  jz      short loc_1400A7457
0x1400a7435  mov     eax, [rbx+10h]
0x1400a7438  mov     r9d, 0F6h
0x1400a743e  mov     rcx, [rcx+40h]
0x1400a7442  mov     [rsp+50h+var_20], eax
0x1400a7446  mov     [rsp+50h+var_28], rbx
0x1400a744b  mov     qword ptr [rsp+50h+var_30], rdx
0x1400a7450  mov     dl, 5
0x1400a7452  call    WPP_RECORDER_SF_qD
0x1400a7457  mov     rdx, rdi; struct CPortPropertyCache *
0x1400a745a  mov     rcx, r14; this
0x1400a745d  call    ?PopulateConnectionParameters@CConnectHelpers@@YAHPEAVCPortPropertyCache@@PEAU_WFC_CONNECTION_PROFILE_PARAMETERS@@@Z; CConnectHelpers::PopulateConnectionParameters(CPortPropertyCache *,_WFC_CONNECTION_PROFILE_PARAMETERS *)
0x1400a7462  mov     esi, eax
0x1400a7464  test    eax, eax
0x1400a7466  jnz     loc_1400A777D
0x1400a746c  mov     rdx, rdi; struct _WFC_CONNECTION_PROFILE_PARAMETERS *
0x1400a746f  mov     rcx, rbx; this
0x1400a7472  call    ?GetMloConfiguration@CConnectJob@@AEAAXPEAU_WFC_CONNECTION_PROFILE_PARAMETERS@@@Z; CConnectJob::GetMloConfiguration(_WFC_CONNECTION_PROFILE_PARAMETERS *)
0x1400a7477  lea     r9d, [rsi+1]
0x1400a747b  cmp     [rbx+0AE0h], r12b
0x1400a7482  jz      loc_1400A75A7
0x1400a7488  lea     r9, [rbp+arg_18]; unsigned __int8 **
0x1400a748c  mov     [rbp+arg_18], r12
0x1400a7490  lea     r8, [rbp+arg_0]; unsigned int *
0x1400a7494  mov     [rbp+var_10], r12
0x1400a7498  lea     edx, [rsi+3Ah]; unsigned int
0x1400a749b  mov     [rbp+arg_0], r12d
0x1400a749f  mov     rcx, r14; this
0x1400a74a2  mov     [rdi], r12w
0x1400a74a6  mov     [rdi+8], r12
0x1400a74aa  mov     [rdi+6Ch], r12b
0x1400a74ae  call    ?GetPropertyBuffer@CPropertyCache@@QEAAHKPEAKPEAPEAE@Z; CPropertyCache::GetPropertyBuffer(ulong,ulong *,uchar * *)
0x1400a74b3  mov     esi, eax
0x1400a74b5  test    eax, eax
0x1400a74b7  jz      short loc_1400A74FF
0x1400a74b9  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400a74c0  jz      loc_1400A77C7
0x1400a74c6  mov     r9d, 0F7h
0x1400a74cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a74d3  lea     r14, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400a74da  mov     dword ptr [rsp+50h+var_18], eax
0x1400a74de  mov     dl, 2
0x1400a74e0  mov     eax, [rbx+10h]
0x1400a74e3  mov     [rsp+50h+var_20], eax
0x1400a74e7  mov     rcx, [rcx+40h]
0x1400a74eb  mov     [rsp+50h+var_28], rbx
0x1400a74f0  mov     qword ptr [rsp+50h+var_30], r14
0x1400a74f5  call    WPP_RECORDER_SF_qDD
0x1400a74fa  jmp     loc_1400A7784
0x1400a74ff  mov     rax, [rbp+arg_18]
0x1400a7503  lea     r9, [rbp+var_10]; unsigned __int8 **
0x1400a7507  lea     r8, [rbp+arg_0]; unsigned int *
0x1400a750b  mov     edx, 3Fh ; '?'; unsigned int
0x1400a7510  mov     rcx, r14; this
0x1400a7513  movups  xmm0, xmmword ptr [rax]
0x1400a7516  movups  xmmword ptr [rbx+0AE4h], xmm0
0x1400a751d  movups  xmm1, xmmword ptr [rax+10h]
0x1400a7521  movups  xmmword ptr [rbx+0AF4h], xmm1
0x1400a7528  movups  xmm0, xmmword ptr [rax+1Ch]
0x1400a752c  lea     rax, [rbx+0AECh]
0x1400a7533  movups  xmmword ptr [rbx+0B00h], xmm0
0x1400a753a  mov     word ptr [rdi], 1
0x1400a753f  mov     [rdi+8], rax
0x1400a7543  call    ?GetPropertyBuffer@CPropertyCache@@QEAAHKPEAKPEAPEAE@Z; CPropertyCache::GetPropertyBuffer(ulong,ulong *,uchar * *)
0x1400a7548  mov     esi, eax
0x1400a754a  test    eax, eax
0x1400a754c  jz      short loc_1400A7566
0x1400a754e  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400a7555  jz      loc_1400A77C7
0x1400a755b  mov     r9d, 0F8h
0x1400a7561  jmp     loc_1400A74CC
0x1400a7566  mov     rcx, [rbp+var_10]
0x1400a756a  mov     r9d, 1
0x1400a7570  cmp     [rcx+11h], r12b
0x1400a7574  setnz   al
0x1400a7577  mov     [rbx+0B10h], al
0x1400a757d  cmp     [rcx+10h], r12b
0x1400a7581  setnz   al
0x1400a7584  mov     [rbx+0B11h], al
0x1400a758a  mov     eax, [rbx+278h]
0x1400a7590  test    r9b, al
0x1400a7593  jz      short loc_1400A75A7
0x1400a7595  mov     eax, [rcx+4]
0x1400a7598  mov     [rbx+0B12h], eax
0x1400a759e  mov     al, [rcx+8]
0x1400a75a1  mov     [rbx+0B16h], al
0x1400a75a7  movzx   r8d, word ptr [rdi+38h]
0x1400a75ac  mov     edx, r12d
0x1400a75af  cmp     dx, r8w
0x1400a75b3  jnb     short loc_1400A7627
0x1400a75b5  mov     rax, [rdi+40h]
0x1400a75b9  movzx   ecx, dx
0x1400a75bc  mov     eax, [rax+rcx*4]
0x1400a75bf  cmp     eax, 6
0x1400a75c2  jz      short loc_1400A75D2
0x1400a75c4  add     eax, 0FFFFFFF8h
0x1400a75c7  cmp     eax, 3
0x1400a75ca  jbe     short loc_1400A75D2
0x1400a75cc  add     dx, r9w
0x1400a75d0  jmp     short loc_1400A75AF
0x1400a75d2  mov     r8b, r9b; unsigned __int8
0x1400a75d5  mov     edx, 30h ; '0'; unsigned int
0x1400a75da  mov     rcx, r14; this
0x1400a75dd  call    ?SetPropertyBoolean@CPropertyCache@@QEAAHKE@Z; CPropertyCache::SetPropertyBoolean(ulong,uchar)
0x1400a75e2  mov     esi, eax
0x1400a75e4  test    eax, eax
0x1400a75e6  jz      short loc_1400A7627
0x1400a75e8  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400a75ef  lea     r14, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400a75f6  jz      short loc_1400A762E
0x1400a75f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a75ff  mov     r9d, 0F9h
0x1400a7605  mov     dword ptr [rsp+50h+var_18], eax
0x1400a7609  mov     dl, 2
0x1400a760b  mov     eax, [rbx+10h]
0x1400a760e  mov     [rsp+50h+var_20], eax
0x1400a7612  mov     rcx, [rcx+40h]
0x1400a7616  mov     [rsp+50h+var_28], rbx
0x1400a761b  mov     qword ptr [rsp+50h+var_30], r14
0x1400a7620  call    WPP_RECORDER_SF_qDD
0x1400a7625  jmp     short loc_1400A762E
0x1400a7627  lea     r14, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400a762e  cmp     dword ptr [r15+98h], 10h
0x1400a7636  jnz     short loc_1400A7657
0x1400a7638  mov     rcx, [rbx+218h]; this
0x1400a763f  mov     r9d, 1; enum _WDI_OPERATION_MODE
0x1400a7645  mov     r8, rdi; struct _WFC_CONNECTION_PROFILE_PARAMETERS *
0x1400a7648  mov     [rsp+50h+var_30], r9d; int
0x1400a764d  mov     rdx, r15; struct CPort *
0x1400a7650  call    ?SetConnectedBssList@CAdapter@@QEAAHPEAVCPort@@PEAU_WFC_CONNECTION_PROFILE_PARAMETERS@@W4_WDI_OPERATION_MODE@@H@Z; CAdapter::SetConnectedBssList(CPort *,_WFC_CONNECTION_PROFILE_PARAMETERS *,_WDI_OPERATION_MODE,int)
0x1400a7655  mov     esi, eax
0x1400a7657  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400a765e  jz      loc_1400A77C7
0x1400a7664  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a766b  mov     r9d, 0FAh
0x1400a7671  mov     rax, [rdi+8]
0x1400a7675  mov     dl, 4
0x1400a7677  mov     [rsp+50h+var_28], rax
0x1400a767c  mov     rcx, [rcx+40h]
0x1400a7680  call    WPP_RECORDER_SF__SSID_
0x1400a7685  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400a768c  jz      loc_1400A77C7
0x1400a7692  movzx   eax, word ptr [rdi+38h]
0x1400a7696  xorps   xmm0, xmm0
0x1400a7699  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a76a0  mov     r9d, 0FBh
0x1400a76a6  movups  xmmword ptr [rbp+var_10], xmm0
0x1400a76aa  shl     ax, 2
0x1400a76ae  mov     dl, 4
0x1400a76b0  mov     word ptr [rbp+var_10], ax
0x1400a76b4  mov     rax, [rdi+40h]
0x1400a76b8  mov     [rbp+var_10+8], rax
0x1400a76bc  lea     rax, [rbp+var_10]
0x1400a76c0  movaps  xmm0, xmmword ptr [rbp+var_10]
0x1400a76c4  movdqa  xmmword ptr [rbp+var_10], xmm0
0x1400a76c9  mov     rcx, [rcx+40h]
0x1400a76cd  mov     [rsp+50h+var_28], rax
0x1400a76d2  call    WPP_RECORDER_SF__HEX_
0x1400a76d7  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400a76de  jz      loc_1400A77C7
0x1400a76e4  movzx   eax, word ptr [rdi+48h]
0x1400a76e8  xorps   xmm0, xmm0
0x1400a76eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a76f2  mov     r9d, 0FCh
0x1400a76f8  movups  xmmword ptr [rbp+var_10], xmm0
0x1400a76fc  shl     ax, 2
0x1400a7700  mov     dl, 4
0x1400a7702  mov     word ptr [rbp+var_10], ax
0x1400a7706  mov     rax, [rdi+50h]
0x1400a770a  mov     [rbp+var_10+8], rax
0x1400a770e  lea     rax, [rbp+var_10]
0x1400a7712  movaps  xmm0, xmmword ptr [rbp+var_10]
0x1400a7716  movdqa  xmmword ptr [rbp+var_10], xmm0
0x1400a771b  mov     rcx, [rcx+40h]
0x1400a771f  mov     [rsp+50h+var_28], rax
0x1400a7724  call    WPP_RECORDER_SF__HEX_
0x1400a7729  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400a7730  jz      loc_1400A77C7
0x1400a7736  movzx   eax, word ptr [rdi+58h]
0x1400a773a  xorps   xmm0, xmm0
0x1400a773d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a7744  mov     r9d, 0FDh
0x1400a774a  movups  xmmword ptr [rbp+var_10], xmm0
0x1400a774e  shl     ax, 2
0x1400a7752  mov     dl, 4
0x1400a7754  mov     word ptr [rbp+var_10], ax
0x1400a7758  mov     rax, [rdi+60h]
0x1400a775c  mov     [rbp+var_10+8], rax
0x1400a7760  lea     rax, [rbp+var_10]
0x1400a7764  movaps  xmm0, xmmword ptr [rbp+var_10]
0x1400a7768  movdqa  xmmword ptr [rbp+var_10], xmm0
0x1400a776d  mov     rcx, [rcx+40h]
0x1400a7771  mov     [rsp+50h+var_28], rax
0x1400a7776  call    WPP_RECORDER_SF__HEX_
0x1400a777b  jmp     short loc_1400A7784
0x1400a777d  lea     r14, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400a7784  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400a778b  jz      short loc_1400A77C7
0x1400a778d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a7794  cmp     byte ptr [rcx+29h], 5
0x1400a7798  jnb     short loc_1400A77A1
0x1400a779a  cmp     [rcx+48h], r12w
0x1400a779f  jz      short loc_1400A77C7
0x1400a77a1  mov     eax, [rbx+10h]
0x1400a77a4  mov     r9d, 0FEh
0x1400a77aa  mov     rcx, [rcx+40h]
0x1400a77ae  mov     dl, 5
0x1400a77b0  mov     dword ptr [rsp+50h+var_18], esi
0x1400a77b4  mov     [rsp+50h+var_20], eax
0x1400a77b8  mov     [rsp+50h+var_28], rbx
0x1400a77bd  mov     qword ptr [rsp+50h+var_30], r14
0x1400a77c2  call    WPP_RECORDER_SF_qDD
0x1400a77c7  mov     rbx, [rsp+50h+arg_8]
0x1400a77cf  mov     eax, esi
0x1400a77d1  add     rsp, 50h
0x1400a77d5  pop     r15
0x1400a77d7  pop     r14
0x1400a77d9  pop     r13
0x1400a77db  pop     r12
0x1400a77dd  pop     rdi
0x1400a77de  pop     rsi
0x1400a77df  pop     rbp
0x1400a77e0  retn
```
