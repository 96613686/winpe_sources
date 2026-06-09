# CCreateMacOidJob::OnJobStarted(void)

- ea: `0x140071ea0`
- end: `0x1400721b2`
- name: `?OnJobStarted@CCreateMacOidJob@@UEAAXXZ`
- size: `786`
- prototype: `void __fastcall(CCreateMacOidJob *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140004a7c`
- `0x140004c3c`
- `0x1400122e0`
- `0x14002aa28`
- `0x14002e878`
- `0x140043d30`
- `0x14006e610`
- `0x140071ea0`
- `0x1400721b8`

## import_xrefs

- `NDIS!NdisMFreePort` at `0x140071fd6`
- `NDIS!NdisMFreePort` at `0x140071fd6`

## pseudocode

```c
void __fastcall CCreateMacOidJob::OnJobStarted(CCreateMacOidJob *this, __int64 a2, int a3)
{
  unsigned int m_Dot11MacParamsOpmodeMask; // eax
  __int16 v5; // bp
  enum _WFC_PORT_TYPE v6; // r12d
  CPort *m_pPortToRecreate; // rax
  unsigned int *p_m_CreatedNdisPortNumber; // r15
  int NdisPort; // eax
  int v10; // edx
  int v11; // esi
  CAdapter **p_m_pAdapter; // r14
  IActivityId *v13; // rdi
  NDIS_PORT_NUMBER v14; // edx
  NDIS_STATUS v15; // eax
  int v16; // edx
  int v17; // edx
  int started; // eax
  int v19; // r9d
  __int64 v20; // [rsp+38h] [rbp-70h]

  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      a3,
      211,
      (__int64)WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids,
      (char)this,
      this->m_ActivityId);
  }
  m_Dot11MacParamsOpmodeMask = this->m_Dot11MacParamsOpmodeMask;
  if ( (m_Dot11MacParamsOpmodeMask & 0x10) != 0 )
  {
    v5 = 8;
    v6 = WfcPortTypeWFDDevice;
  }
  else if ( (m_Dot11MacParamsOpmodeMask & 0x60) != 0 )
  {
    v5 = 48;
    v6 = WfcPortTypeWFDRole;
  }
  else
  {
    v6 = WfcPortTypeExtSTA;
    v5 = 1;
  }
  m_pPortToRecreate = this->m_pPortToRecreate;
  p_m_CreatedNdisPortNumber = &this->m_CreatedNdisPortNumber;
  if ( m_pPortToRecreate )
  {
    *p_m_CreatedNdisPortNumber = m_pPortToRecreate->m_NdisPortNumber;
  }
  else
  {
    NdisPort = CCreateMacOidJob::AllocateNdisPort(this, &this->m_CreatedNdisPortNumber);
    v11 = NdisPort;
    if ( NdisPort )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v10) = 2;
        WPP_RECORDER_SF_qDD(
          WPP_GLOBAL_Control->DeviceExtension,
          v10,
          a3,
          212,
          (__int64)WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids,
          (char)this,
          this->m_ActivityId,
          NdisPort);
      }
      p_m_pAdapter = &this->m_pAdapter;
      v13 = &this->IActivityId;
      goto LABEL_15;
    }
  }
  v13 = &this->IActivityId;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qDDDDD(
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      a3,
      213,
      (__int64)WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids,
      (char)this,
      v13->m_ActivityId,
      this->m_Dot11MacParamsOpmodeMask,
      v6,
      v5,
      *p_m_CreatedNdisPortNumber);
  p_m_pAdapter = &this->m_pAdapter;
  started = CCreatePortJob::InitializeFromJob(
              &this->m_CreatePortChildJob,
              this->m_pAdapter,
              v6,
              v5,
              *p_m_CreatedNdisPortNumber,
              this->m_pPortToRecreate != 0);
  v11 = started;
  if ( started )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      goto LABEL_15;
    v19 = 214;
    goto LABEL_31;
  }
  this->m_CreatePortOidState = CreatePortOidStateWaitingForCreatePortChildJob;
  started = CJobBase::StartChildJob(this, &this->m_CreatePortChildJob);
  v11 = started;
  if ( !started )
    goto LABEL_32;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v19 = 215;
LABEL_31:
    LOBYTE(v17) = 2;
    LODWORD(v20) = started;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v17,
      a3,
      v19,
      (__int64)WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids,
      (char)this,
      v13->m_ActivityId,
      v20);
  }
LABEL_15:
  if ( !this->m_pPortToRecreate )
  {
    CAdapter::CompleteOidRequest(*p_m_pAdapter, this->m_pOidRequest, v11);
    v14 = *p_m_CreatedNdisPortNumber;
    this->m_OidIsCompleted = 1;
    if ( v14 != -1 )
    {
      v15 = NdisMFreePort((*p_m_pAdapter)->m_MiniportAdapterHandle, v14);
      if ( v15 && *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LODWORD(v20) = v15;
        LOBYTE(v16) = 4;
        WPP_RECORDER_SF_qDD(
          WPP_GLOBAL_Control->DeviceExtension,
          v16,
          a3,
          216,
          (__int64)WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids,
          (char)this,
          v13->m_ActivityId,
          v20);
      }
      *p_m_CreatedNdisPortNumber = -1;
    }
  }
  CJobBase::CompleteJob(this, v11, a3);
LABEL_32:
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v17) = 5;
    LODWORD(v20) = v11;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v17,
      a3,
      217,
      (__int64)WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids,
      (char)this,
      v13->m_ActivityId,
      v20);
  }
}

```

## disassembly

```asm
0x140071ea0  push    rbx
0x140071ea2  push    rbp
0x140071ea3  push    rsi
0x140071ea4  push    rdi
0x140071ea5  push    r12
0x140071ea7  push    r13
0x140071ea9  push    r14
0x140071eab  push    r15
0x140071ead  sub     rsp, 68h
0x140071eb1  mov     rbx, rcx
0x140071eb4  lea     r13, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140071ebb  xor     edi, edi
0x140071ebd  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140071ec4  lea     r14, WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids
0x140071ecb  jz      short loc_140071F02
0x140071ecd  mov     rcx, cs:WPP_GLOBAL_Control
0x140071ed4  cmp     byte ptr [rcx+29h], 5
0x140071ed8  jnb     short loc_140071EE0
0x140071eda  cmp     [rcx+48h], di
0x140071ede  jz      short loc_140071F02
0x140071ee0  mov     eax, [rbx+10h]
0x140071ee3  mov     r9d, 0D3h
0x140071ee9  mov     rcx, [rcx+40h]
0x140071eed  mov     dl, 5
0x140071eef  mov     [rsp+0A8h+var_78], eax
0x140071ef3  mov     qword ptr [rsp+0A8h+var_80], rbx
0x140071ef8  mov     qword ptr [rsp+0A8h+var_88], r14
0x140071efd  call    WPP_RECORDER_SF_qD
0x140071f02  mov     eax, [rbx+1308h]
0x140071f08  mov     ecx, 1
0x140071f0d  test    al, 10h
0x140071f0f  jz      short loc_140071F1A
0x140071f11  lea     ebp, [rcx+7]
0x140071f14  lea     r12d, [rcx+3]
0x140071f18  jmp     short loc_140071F2F
0x140071f1a  test    al, 60h
0x140071f1c  jnz     short loc_140071F26
0x140071f1e  mov     r12d, ecx
0x140071f21  movzx   ebp, cx
0x140071f24  jmp     short loc_140071F2F
0x140071f26  mov     ebp, 30h ; '0'
0x140071f2b  lea     r12d, [rbp-28h]
0x140071f2f  mov     rax, [rbx+1318h]
0x140071f36  lea     r15, [rbx+1310h]
0x140071f3d  test    rax, rax
0x140071f40  jnz     loc_140072031
0x140071f46  mov     rdx, r15; unsigned int *
0x140071f49  mov     rcx, rbx; this
0x140071f4c  call    ?AllocateNdisPort@CCreateMacOidJob@@QEAAHPEAK@Z; CCreateMacOidJob::AllocateNdisPort(ulong *)
0x140071f51  mov     esi, eax
0x140071f53  test    eax, eax
0x140071f55  jz      loc_140072037
0x140071f5b  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140071f62  jz      short loc_140071F91
0x140071f64  mov     ecx, [rbx+10h]
0x140071f67  mov     r9d, 0D4h
0x140071f6d  mov     dword ptr [rsp+0A8h+var_70], eax
0x140071f71  mov     dl, 2
0x140071f73  mov     [rsp+0A8h+var_78], ecx
0x140071f77  mov     rcx, cs:WPP_GLOBAL_Control
0x140071f7e  mov     qword ptr [rsp+0A8h+var_80], rbx
0x140071f83  mov     qword ptr [rsp+0A8h+var_88], r14
0x140071f88  mov     rcx, [rcx+40h]
0x140071f8c  call    WPP_RECORDER_SF_qDD
0x140071f91  lea     r14, [rbx+200h]
0x140071f98  xor     ebp, ebp
0x140071f9a  lea     rdi, [rbx+10h]
0x140071f9e  lea     r12, WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids
0x140071fa5  cmp     [rbx+1318h], rbp
0x140071fac  jnz     short loc_140072022
0x140071fae  mov     rdx, [rbx+210h]; struct _NDIS_OID_REQUEST *
0x140071fb5  mov     r8d, esi; int
0x140071fb8  mov     rcx, [r14]; this
0x140071fbb  call    ?CompleteOidRequest@CAdapter@@QEAAXPEAU_NDIS_OID_REQUEST@@H@Z; CAdapter::CompleteOidRequest(_NDIS_OID_REQUEST *,int)
0x140071fc0  mov     edx, [r15]; PortNumber
0x140071fc3  mov     byte ptr [rbx+1314h], 1
0x140071fca  cmp     edx, 0FFFFFFFFh
0x140071fcd  jz      short loc_140072022
0x140071fcf  mov     rcx, [r14]
0x140071fd2  mov     rcx, [rcx+58h]; NdisMiniportHandle
0x140071fd6  call    cs:__imp_NdisMFreePort
0x140071fdd  nop     dword ptr [rax+rax+00h]
0x140071fe2  test    eax, eax
0x140071fe4  jz      short loc_14007201B
0x140071fe6  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140071fed  jz      short loc_14007201B
0x140071fef  mov     rcx, cs:WPP_GLOBAL_Control
0x140071ff6  mov     r9d, 0D8h
0x140071ffc  mov     dword ptr [rsp+0A8h+var_70], eax
0x140072000  mov     dl, 4
0x140072002  mov     eax, [rdi]
0x140072004  mov     [rsp+0A8h+var_78], eax
0x140072008  mov     rcx, [rcx+40h]
0x14007200c  mov     qword ptr [rsp+0A8h+var_80], rbx
0x140072011  mov     qword ptr [rsp+0A8h+var_88], r12
0x140072016  call    WPP_RECORDER_SF_qDD
0x14007201b  mov     dword ptr [r15], 0FFFFFFFFh
0x140072022  mov     edx, esi; int
0x140072024  mov     rcx, rbx; this
0x140072027  call    ?CompleteJob@CJobBase@@IEAAHH@Z; CJobBase::CompleteJob(int)
0x14007202c  jmp     loc_140072158
0x140072031  mov     eax, [rax+60h]
0x140072034  mov     [r15], eax
0x140072037  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14007203e  lea     rdi, [rbx+10h]
0x140072042  jz      short loc_140072089
0x140072044  mov     eax, [r15]
0x140072047  mov     r9d, 0D5h
0x14007204d  mov     [rsp+0A8h+var_58], eax
0x140072051  mov     dl, 4
0x140072053  mov     eax, [rbx+1308h]
0x140072059  movzx   ecx, bp
0x14007205c  mov     [rsp+0A8h+var_60], ecx
0x140072060  mov     rcx, cs:WPP_GLOBAL_Control
0x140072067  mov     [rsp+0A8h+var_68], r12d
0x14007206c  mov     dword ptr [rsp+0A8h+var_70], eax
0x140072070  mov     eax, [rdi]
0x140072072  mov     rcx, [rcx+40h]
0x140072076  mov     [rsp+0A8h+var_78], eax
0x14007207a  mov     qword ptr [rsp+0A8h+var_80], rbx
0x14007207f  mov     qword ptr [rsp+0A8h+var_88], r14
0x140072084  call    WPP_RECORDER_SF_qDDDDD
0x140072089  cmp     qword ptr [rbx+1318h], 0
0x140072091  lea     r13, [rbx+228h]
0x140072098  lea     r14, [rbx+200h]
0x14007209f  movzx   r9d, bp; unsigned __int16
0x1400720a3  mov     rdx, [r14]; CAdapter *
0x1400720a6  setnz   al
0x1400720a9  mov     [rsp+0A8h+var_80], al; unsigned __int8
0x1400720ad  mov     r8d, r12d; enum _WFC_PORT_TYPE
0x1400720b0  mov     eax, [r15]
0x1400720b3  mov     rcx, r13; this
0x1400720b6  mov     [rsp+0A8h+var_88], eax; unsigned int
0x1400720ba  call    ?InitializeFromJob@CCreatePortJob@@QEAAHPEAVCAdapter@@W4_WFC_PORT_TYPE@@GKE@Z; CCreatePortJob::InitializeFromJob(CAdapter *,_WFC_PORT_TYPE,ushort,ulong,uchar)
0x1400720bf  xor     ebp, ebp
0x1400720c1  mov     esi, eax
0x1400720c3  test    eax, eax
0x1400720c5  jz      short loc_1400720EA
0x1400720c7  lea     r13, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400720ce  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400720d5  lea     r12, WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids
0x1400720dc  jz      loc_140071FA5
0x1400720e2  mov     r9d, 0D6h
0x1400720e8  jmp     short loc_140072126
0x1400720ea  mov     rdx, r13; struct CJobBase *
0x1400720ed  mov     dword ptr [rbx+130Ch], 1
0x1400720f7  mov     rcx, rbx; this
0x1400720fa  call    ?StartChildJob@CJobBase@@IEAAHPEAV1@@Z; CJobBase::StartChildJob(CJobBase *)
0x1400720ff  mov     esi, eax
0x140072101  test    eax, eax
0x140072103  jz      short loc_140072151
0x140072105  lea     r13, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14007210c  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140072113  jz      loc_140071F9E
0x140072119  mov     r9d, 0D7h
0x14007211f  lea     r12, WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids
0x140072126  mov     rcx, cs:WPP_GLOBAL_Control
0x14007212d  mov     dl, 2
0x14007212f  mov     dword ptr [rsp+0A8h+var_70], eax
0x140072133  mov     eax, [rdi]
0x140072135  mov     [rsp+0A8h+var_78], eax
0x140072139  mov     rcx, [rcx+40h]
0x14007213d  mov     qword ptr [rsp+0A8h+var_80], rbx
0x140072142  mov     qword ptr [rsp+0A8h+var_88], r12
0x140072147  call    WPP_RECORDER_SF_qDD
0x14007214c  jmp     loc_140071FA5
0x140072151  lea     r12, WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids
0x140072158  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14007215f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140072166  jz      short loc_1400721A0
0x140072168  mov     rcx, cs:WPP_GLOBAL_Control
0x14007216f  cmp     byte ptr [rcx+29h], 5
0x140072173  jnb     short loc_14007217B
0x140072175  cmp     [rcx+48h], bp
0x140072179  jz      short loc_1400721A0
0x14007217b  mov     eax, [rdi]
0x14007217d  mov     r9d, 0D9h
0x140072183  mov     rcx, [rcx+40h]
0x140072187  mov     dl, 5
0x140072189  mov     dword ptr [rsp+0A8h+var_70], esi
0x14007218d  mov     [rsp+0A8h+var_78], eax
0x140072191  mov     qword ptr [rsp+0A8h+var_80], rbx
0x140072196  mov     qword ptr [rsp+0A8h+var_88], r12
0x14007219b  call    WPP_RECORDER_SF_qDD
0x1400721a0  add     rsp, 68h
0x1400721a4  pop     r15
0x1400721a6  pop     r14
0x1400721a8  pop     r13
0x1400721aa  pop     r12
0x1400721ac  pop     rdi
0x1400721ad  pop     rsi
0x1400721ae  pop     rbp
0x1400721af  pop     rbx
0x1400721b0  retn
```
