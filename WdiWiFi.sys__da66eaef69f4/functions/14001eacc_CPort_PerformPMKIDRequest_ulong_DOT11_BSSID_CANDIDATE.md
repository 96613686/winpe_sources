# CPort::PerformPMKIDRequest(ulong,DOT11_BSSID_CANDIDATE *)

- ea: `0x14001eacc`
- end: `0x14001ede9`
- name: `?PerformPMKIDRequest@CPort@@QEAAKKPEAUDOT11_BSSID_CANDIDATE@@@Z`
- size: `797`
- prototype: `unsigned int(CPort *__hidden this, unsigned int, struct DOT11_BSSID_CANDIDATE *)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x14001f3cc`
- `0x1400886f0`

## callees

- `0x14000da4c`
- `0x1400100f8`
- `0x140017388`
- `0x14001eacc`
- `0x140023ae0`
- `0x1400297a0`
- `0x14002aa28`
- `0x140034e04`
- `0x140034ec4`
- `0x140060af4`
- `0x1400b3000`
- `0x1400da740`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001eb79`
- `ntoskrnl!ExAllocatePool2` at `0x14001eb79`

## pseudocode

```c
__int64 __fastcall CPort::PerformPMKIDRequest(CPort *this, unsigned int a2, struct DOT11_BSSID_CANDIDATE *a3)
{
  unsigned int v4; // esi
  _WFC_PORT_DOT11_STATE m_Dot11State; // edx
  unsigned int v7; // edi
  unsigned int v8; // r15d
  struct DOT11_PMKID_CANDIDATE_LIST_PARAMETERS *Pool2; // rax
  int v10; // edx
  int v11; // r8d
  struct DOT11_PMKID_CANDIDATE_LIST_PARAMETERS *v12; // r14
  CPort *v13; // rcx
  int v14; // r12d
  int PropertyULongOrDefault; // edi
  char v16; // al
  int v17; // edx
  int v18; // r8d
  unsigned __int64 v19; // r13
  unsigned int v20; // edi
  char v21; // al
  int v22; // edx
  int v23; // r8d
  int v24; // edx
  unsigned int v26[2]; // [rsp+28h] [rbp-80h]

  v4 = a2;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      396,
      (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids);
  }
  m_Dot11State = this->m_Dot11State;
  if ( m_Dot11State == WfcPortDot11StateInit || !v4 )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
      && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      LOBYTE(m_Dot11State) = 5;
      WPP_RECORDER_SF_qDdd(
        WPP_GLOBAL_Control->DeviceExtension,
        m_Dot11State,
        (unsigned int)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
        397,
        (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
        (char)this,
        this->m_WfcPortId,
        this->m_Dot11State,
        v4);
    }
    return 0;
  }
  v7 = 40;
  if ( v4 <= 0x28 )
    v7 = v4;
  v8 = 16 * v7 + 12;
  Pool2 = (struct DOT11_PMKID_CANDIDATE_LIST_PARAMETERS *)ExAllocatePool2(64, v8, 1198089303);
  v12 = Pool2;
  if ( !Pool2 )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = 2;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        v10,
        v11,
        398,
        (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
        (char)this,
        this->m_WfcPortId);
    }
    return 0;
  }
  memset(Pool2, 0, 16 * v7 + 12);
  v12->Header = (_NDIS_OBJECT_HEADER)786816;
  v14 = CPort::BuildNwfPmkidParamList(v13, v4, a3, v7, v12);
  PropertyULongOrDefault = CPropertyCache::GetPropertyULongOrDefault(&this->m_PortPropertyCache, 0x2Cu, 0);
  v16 = CPropertyCache::GetPropertyULongOrDefault(&this->m_PortPropertyCache, 0x2Du, 0);
  v19 = MEMORY[0xFFFFF78000000014];
  if ( MEMORY[0xFFFFF78000000014] < this->m_LastPMKIDRequest + 600000000 )
  {
    v20 = PropertyULongOrDefault + 1;
  }
  else
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v17) = 4;
      WPP_RECORDER_SF_qDdd(
        WPP_GLOBAL_Control->DeviceExtension,
        v17,
        v18,
        399,
        (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
        (char)this,
        this->m_WfcPortId,
        PropertyULongOrDefault,
        v16);
    }
    v20 = 1;
    CPropertyCache::SetPropertyULong(&this->m_PortPropertyCache, 0x2Du, 0);
  }
  this->m_LastPMKIDRequest = v19;
  CPropertyCache::SetPropertyULong(&this->m_PortPropertyCache, 0x2Cu, v20);
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v21 = CPropertyCache::GetPropertyULongOrDefault(&this->m_PortPropertyCache, 0x2Du, 0);
    WPP_RECORDER_SF_qDDddd(
      WPP_GLOBAL_Control->DeviceExtension,
      v22,
      v23,
      400,
      (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
      (char)this,
      this->m_WfcPortId,
      v14,
      v4,
      v20,
      v21);
  }
  CAdapter::IndicateStatus(this->m_pAdapter, this->m_NdisPortNumber, v14, 0, v12, v8);
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    v26[0] = 0;
    LOBYTE(v24) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v24,
      1,
      401,
      (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
      *(_QWORD *)v26);
  }
  operator delete(v12);
  return v20;
}

```

## disassembly

```asm
0x14001eacc  push    rbx
0x14001eace  push    rbp
0x14001eacf  push    rsi
0x14001ead0  push    rdi
0x14001ead1  push    r12
0x14001ead3  push    r13
0x14001ead5  push    r14
0x14001ead7  push    r15
0x14001ead9  sub     rsp, 68h
0x14001eadd  mov     r12, r8
0x14001eae0  mov     esi, edx
0x14001eae2  mov     rbx, rcx
0x14001eae5  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001eaec  xor     r13d, r13d
0x14001eaef  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001eaf6  lea     r8, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x14001eafd  jz      short loc_14001EB3D
0x14001eaff  mov     rcx, cs:WPP_GLOBAL_Control
0x14001eb06  cmp     byte ptr [rcx+29h], 5
0x14001eb0a  jnb     short loc_14001EB13
0x14001eb0c  cmp     [rcx+48h], r13w
0x14001eb11  jz      short loc_14001EB3D
0x14001eb13  mov     rcx, [rcx+40h]
0x14001eb17  mov     r9d, 18Ch
0x14001eb1d  mov     [rsp+0A8h+var_88], r8
0x14001eb22  mov     dl, 5
0x14001eb24  mov     r8d, 1
0x14001eb2a  call    WPP_RECORDER_SF_
0x14001eb2f  lea     rax, WPP_RECORDER_INITIALIZED
0x14001eb36  lea     r8, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x14001eb3d  mov     edx, [rbx+32Ch]
0x14001eb43  test    edx, edx
0x14001eb45  jz      loc_14001ED8D
0x14001eb4b  test    esi, esi
0x14001eb4d  jz      loc_14001ED8D
0x14001eb53  mov     edi, 28h ; '('
0x14001eb58  mov     r8d, 47696457h
0x14001eb5e  cmp     esi, edi
0x14001eb60  mov     ecx, 40h ; '@'
0x14001eb65  cmovbe  edi, esi
0x14001eb68  mov     r15d, edi
0x14001eb6b  shl     r15d, 4
0x14001eb6f  add     r15d, 0Ch
0x14001eb73  mov     edx, r15d
0x14001eb76  mov     ebp, r15d
0x14001eb79  call    cs:__imp_ExAllocatePool2
0x14001eb80  nop     dword ptr [rax+rax+00h]
0x14001eb85  mov     r14, rax
0x14001eb88  test    rax, rax
0x14001eb8b  jnz     short loc_14001EBD7
0x14001eb8d  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001eb94  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14001eb9b  jz      loc_14001EDD5
0x14001eba1  movzx   eax, word ptr [rbx+64h]
0x14001eba5  mov     r9d, 18Eh
0x14001ebab  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ebb2  mov     dl, 2
0x14001ebb4  mov     [rsp+0A8h+var_78], eax
0x14001ebb8  lea     rax, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x14001ebbf  mov     qword ptr [rsp+0A8h+var_80], rbx
0x14001ebc4  mov     [rsp+0A8h+var_88], rax
0x14001ebc9  mov     rcx, [rcx+40h]
0x14001ebcd  call    WPP_RECORDER_SF_qD
0x14001ebd2  jmp     loc_14001EDD5
0x14001ebd7  mov     r8, rbp; Size
0x14001ebda  xor     edx, edx; Val
0x14001ebdc  mov     rcx, r14; void *
0x14001ebdf  call    memset
0x14001ebe4  mov     r9d, edi; unsigned int
0x14001ebe7  mov     dword ptr [r14], 0C0180h
0x14001ebee  mov     r8, r12; struct DOT11_BSSID_CANDIDATE *
0x14001ebf1  mov     [rsp+0A8h+var_88], r14; struct DOT11_PMKID_CANDIDATE_LIST_PARAMETERS *
0x14001ebf6  mov     edx, esi; unsigned int
0x14001ebf8  call    ?BuildNwfPmkidParamList@CPort@@QEAAHKPEAUDOT11_BSSID_CANDIDATE@@KPEAUDOT11_PMKID_CANDIDATE_LIST_PARAMETERS@@@Z; CPort::BuildNwfPmkidParamList(ulong,DOT11_BSSID_CANDIDATE *,ulong,DOT11_PMKID_CANDIDATE_LIST_PARAMETERS *)
0x14001ebfd  xor     r8d, r8d; unsigned int
0x14001ec00  lea     rbp, [rbx+3A8h]
0x14001ec07  mov     rcx, rbp; this
0x14001ec0a  mov     r12d, eax
0x14001ec0d  lea     edx, [r8+2Ch]; unsigned int
0x14001ec11  call    ?GetPropertyULongOrDefault@CPropertyCache@@QEAAKKK@Z; CPropertyCache::GetPropertyULongOrDefault(ulong,ulong)
0x14001ec16  xor     r8d, r8d; unsigned int
0x14001ec19  mov     rcx, rbp; this
0x14001ec1c  mov     edi, eax
0x14001ec1e  lea     edx, [r8+2Dh]; unsigned int
0x14001ec22  call    ?GetPropertyULongOrDefault@CPropertyCache@@QEAAKKK@Z; CPropertyCache::GetPropertyULongOrDefault(ulong,ulong)
0x14001ec27  mov     r13, 0FFFFF78000000014h
0x14001ec31  mov     r13, [r13+0]
0x14001ec35  mov     rcx, [rbx+3F8h]
0x14001ec3c  add     rcx, 23C34600h
0x14001ec43  cmp     r13, rcx
0x14001ec46  jb      short loc_14001ECA6
0x14001ec48  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001ec4f  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14001ec56  jz      short loc_14001EC91
0x14001ec58  movzx   ecx, word ptr [rbx+64h]
0x14001ec5c  mov     r9d, 18Fh
0x14001ec62  mov     [rsp+0A8h+var_68], eax
0x14001ec66  mov     dl, 4
0x14001ec68  mov     [rsp+0A8h+var_70], edi
0x14001ec6c  lea     rax, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x14001ec73  mov     [rsp+0A8h+var_78], ecx
0x14001ec77  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ec7e  mov     qword ptr [rsp+0A8h+var_80], rbx
0x14001ec83  mov     [rsp+0A8h+var_88], rax
0x14001ec88  mov     rcx, [rcx+40h]
0x14001ec8c  call    WPP_RECORDER_SF_qDdd
0x14001ec91  mov     edi, 1
0x14001ec96  xor     r8d, r8d; unsigned int
0x14001ec99  mov     rcx, rbp; this
0x14001ec9c  lea     edx, [rdi+2Ch]; unsigned int
0x14001ec9f  call    ?SetPropertyULong@CPropertyCache@@QEAAHKK@Z; CPropertyCache::SetPropertyULong(ulong,ulong)
0x14001eca4  jmp     short loc_14001ECA8
0x14001eca6  inc     edi
0x14001eca8  mov     r8d, edi; unsigned int
0x14001ecab  mov     [rbx+3F8h], r13
0x14001ecb2  mov     edx, 2Ch ; ','; unsigned int
0x14001ecb7  mov     rcx, rbp; this
0x14001ecba  call    ?SetPropertyULong@CPropertyCache@@QEAAHKK@Z; CPropertyCache::SetPropertyULong(ulong,ulong)
0x14001ecbf  lea     r13, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001ecc6  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14001eccd  jz      short loc_14001ED20
0x14001eccf  xor     r8d, r8d; unsigned int
0x14001ecd2  mov     rcx, rbp; this
0x14001ecd5  lea     edx, [r8+2Dh]; unsigned int
0x14001ecd9  call    ?GetPropertyULongOrDefault@CPropertyCache@@QEAAKKK@Z; CPropertyCache::GetPropertyULongOrDefault(ulong,ulong)
0x14001ecde  movzx   ecx, word ptr [rbx+64h]
0x14001ece2  mov     r9d, 190h
0x14001ece8  mov     [rsp+0A8h+var_58], eax
0x14001ecec  mov     [rsp+0A8h+var_60], edi
0x14001ecf0  mov     [rsp+0A8h+var_68], esi
0x14001ecf4  lea     rsi, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x14001ecfb  mov     [rsp+0A8h+var_70], r12d
0x14001ed00  mov     [rsp+0A8h+var_78], ecx
0x14001ed04  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ed0b  mov     qword ptr [rsp+0A8h+var_80], rbx
0x14001ed10  mov     [rsp+0A8h+var_88], rsi
0x14001ed15  mov     rcx, [rcx+40h]
0x14001ed19  call    WPP_RECORDER_SF_qDDddd
0x14001ed1e  jmp     short loc_14001ED27
0x14001ed20  lea     rsi, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x14001ed27  mov     edx, [rbx+60h]; unsigned int
0x14001ed2a  xor     r9d, r9d; void *
0x14001ed2d  mov     rcx, [rbx+58h]; this
0x14001ed31  mov     r8d, r12d; int
0x14001ed34  mov     [rsp+0A8h+var_80], r15d; unsigned int
0x14001ed39  mov     [rsp+0A8h+var_88], r14; void *
0x14001ed3e  call    ?IndicateStatus@CAdapter@@QEAAXKHPEAX0K@Z; CAdapter::IndicateStatus(ulong,int,void *,void *,ulong)
0x14001ed43  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14001ed4a  jz      short loc_14001ED81
0x14001ed4c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ed53  xor     eax, eax
0x14001ed55  cmp     byte ptr [rcx+29h], 5
0x14001ed59  jnb     short loc_14001ED61
0x14001ed5b  cmp     [rcx+48h], ax
0x14001ed5f  jz      short loc_14001ED81
0x14001ed61  mov     rcx, [rcx+40h]
0x14001ed65  mov     r9d, 191h
0x14001ed6b  mov     [rsp+0A8h+var_80], eax
0x14001ed6f  mov     r8d, 1
0x14001ed75  mov     dl, 5
0x14001ed77  mov     [rsp+0A8h+var_88], rsi
0x14001ed7c  call    WPP_RECORDER_SF_D
0x14001ed81  mov     rcx, r14; void *
0x14001ed84  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14001ed89  mov     eax, edi
0x14001ed8b  jmp     short loc_14001EDD7
0x14001ed8d  cmp     cs:WPP_RECORDER_INITIALIZED, rax; __annotation("TMF:",
0x14001ed94  jz      short loc_14001EDD5
0x14001ed96  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ed9d  cmp     byte ptr [rcx+29h], 5
0x14001eda1  jnb     short loc_14001EDAA
0x14001eda3  cmp     [rcx+48h], r13w
0x14001eda8  jz      short loc_14001EDD5
0x14001edaa  movzx   eax, word ptr [rbx+64h]
0x14001edae  mov     r9d, 18Dh
0x14001edb4  mov     rcx, [rcx+40h]
0x14001edb8  mov     [rsp+0A8h+var_68], esi
0x14001edbc  mov     [rsp+0A8h+var_70], edx
0x14001edc0  mov     dl, 5
0x14001edc2  mov     [rsp+0A8h+var_78], eax
0x14001edc6  mov     qword ptr [rsp+0A8h+var_80], rbx
0x14001edcb  mov     [rsp+0A8h+var_88], r8
0x14001edd0  call    WPP_RECORDER_SF_qDdd
0x14001edd5  xor     eax, eax
0x14001edd7  add     rsp, 68h
0x14001eddb  pop     r15
0x14001eddd  pop     r14
0x14001eddf  pop     r13
0x14001ede1  pop     r12
0x14001ede3  pop     rdi
0x14001ede4  pop     rsi
0x14001ede5  pop     rbp
0x14001ede6  pop     rbx
0x14001ede7  retn
```
