# CConnectJob::CheckAndRequestPMKIDUpdate(ulong,CBSSEntry * *)

- ea: `0x14001f3cc`
- end: `0x14001f749`
- name: `?CheckAndRequestPMKIDUpdate@CConnectJob@@AEAA_NKPEAPEAVCBSSEntry@@@Z`
- size: `893`
- prototype: `bool __fastcall(CConnectJob *__hidden this, unsigned int, struct CBSSEntry **)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update`

## callers

- `0x140013160`
- `0x140014828`

## callees

- `0x140010b20`
- `0x1400122e0`
- `0x140013000`
- `0x1400147e8`
- `0x14001eacc`
- `0x14001f3cc`
- `0x140021280`
- `0x140023ae0`
- `0x1400297a0`
- `0x14002aa28`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001f4c8`
- `ntoskrnl!ExAllocatePool2` at `0x14001f4c8`

## pseudocode

```c
bool __fastcall CConnectJob::CheckAndRequestPMKIDUpdate(CConnectJob *this, unsigned int a2, struct CBSSEntry **a3)
{
  unsigned __int64 v3; // rsi
  struct DOT11_BSSID_CANDIDATE *Pool2; // rbx
  struct CPort *PortFromPortId; // rbp
  int v8; // r8d
  __int64 *v9; // rdx
  struct CPortPropertyCache *PortPropertyCache; // rax
  __int64 v11; // rax
  unsigned int v12; // r10d
  __int64 v13; // r9
  struct CBSSEntry *v14; // rdx
  __int64 v15; // r8
  struct CBSSEntry *v16; // rax
  bool v17; // di
  PDEVICE_OBJECT v19; // rcx
  int v20; // r9d
  __int64 v21; // [rsp+38h] [rbp-40h]
  unsigned __int8 v22; // [rsp+80h] [rbp+8h] BYREF

  v3 = a2;
  Pool2 = 0;
  PortFromPortId = CAdapter::GetPortFromPortId(this->m_pAdapter, this->m_PortId);
  v9 = WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v9) = 5;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v9,
      v8,
      255,
      (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
      (char)this,
      this->m_ActivityId);
    v9 = WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids;
  }
  if ( (this->m_RoamConfigFlags & 1) != 0 )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      goto LABEL_18;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v9) = 5;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)v9,
        v8,
        256,
        (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
        (char)this,
        this->m_ActivityId);
    }
    goto LABEL_15;
  }
  v22 = 0;
  CPropertyCache::GetPropertyUchar(&PortFromPortId->m_PortPropertyCache, 0x14u, &v22);
  if ( v22 )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      goto LABEL_18;
    v19 = WPP_GLOBAL_Control;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) < 5u && !LOWORD(WPP_GLOBAL_Control->DeviceType) )
      goto LABEL_15;
    v20 = 257;
    goto LABEL_40;
  }
  if ( !(_DWORD)v3 || this->m_IsP2PConnect )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      goto LABEL_18;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v9) = 5;
      WPP_RECORDER_SF_qDdd(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)v9,
        v8,
        258,
        (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
        (char)this,
        this->m_ActivityId,
        v3,
        this->m_IsP2PConnect);
    }
    goto LABEL_15;
  }
  PortPropertyCache = COidJobBase::GetPortPropertyCache(this);
  if ( !CPropertyCache::GetPropertyBooleanOrDefault(PortPropertyCache, 0x2Fu, 0) )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      goto LABEL_18;
    v19 = WPP_GLOBAL_Control;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) < 5u && !LOWORD(WPP_GLOBAL_Control->DeviceType) )
      goto LABEL_15;
    v20 = 259;
    goto LABEL_40;
  }
  v11 = 12 * v3;
  if ( !is_mul_ok(v3, 0xCu) )
    v11 = -1;
  Pool2 = (struct DOT11_BSSID_CANDIDATE *)ExAllocatePool2(64, v11, 1198089303);
  if ( Pool2 )
  {
    v12 = 0;
    v13 = 0;
    do
    {
      v14 = a3[v13];
      v15 = v13;
      ++v12;
      *(_DWORD *)Pool2[v15].BSSID = *(_DWORD *)v14->m_BssID;
      *(_WORD *)&Pool2[v15].BSSID[4] = *(_WORD *)&v14->m_BssID[4];
      v16 = a3[v13++];
      Pool2[v15].uFlags = v16->m_ConnectionCapabilityFlags;
    }
    while ( v12 < (unsigned int)v3 );
    this->m_PMKIDRequestCounter = CPort::PerformPMKIDRequest(PortFromPortId, v3, Pool2);
    goto LABEL_15;
  }
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
    goto LABEL_18;
  v19 = WPP_GLOBAL_Control;
  if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    v20 = 260;
LABEL_40:
    LOBYTE(v9) = 5;
    WPP_RECORDER_SF_qD(
      v19->DeviceExtension,
      (_DWORD)v9,
      v8,
      v20,
      (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
      (char)this,
      this->m_ActivityId);
  }
LABEL_15:
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v9) = 5;
    LODWORD(v21) = 0;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v9,
      v8,
      261,
      (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
      (char)this,
      this->m_ActivityId,
      v21);
  }
LABEL_18:
  v17 = this->m_PMKIDRequestCounter != 0;
  if ( Pool2 )
    operator delete(Pool2);
  return v17;
}

```

## disassembly

```asm
0x14001f3cc  mov     [rsp+arg_8], rbx
0x14001f3d1  mov     [rsp+arg_10], rbp
0x14001f3d6  push    rsi
0x14001f3d7  push    rdi
0x14001f3d8  push    r13
0x14001f3da  push    r14
0x14001f3dc  push    r15
0x14001f3de  sub     rsp, 50h
0x14001f3e2  xor     r15d, r15d
0x14001f3e5  mov     esi, edx
0x14001f3e7  movzx   edx, word ptr [rcx+34h]; unsigned __int16
0x14001f3eb  mov     rdi, rcx
0x14001f3ee  mov     rcx, [rcx+200h]; this
0x14001f3f5  mov     r14, r8
0x14001f3f8  mov     ebx, r15d
0x14001f3fb  call    ?GetPortFromPortId@CAdapter@@QEAAPEAVCPort@@G@Z; CAdapter::GetPortFromPortId(ushort)
0x14001f400  mov     rbp, rax
0x14001f403  lea     r13, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001f40a  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14001f411  lea     rdx, WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids
0x14001f418  jz      short loc_14001F436
0x14001f41a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f421  cmp     byte ptr [rcx+29h], 5
0x14001f425  jnb     loc_14001F6C6
0x14001f42b  cmp     [rcx+48h], r15w
0x14001f430  jnz     loc_14001F6C6
0x14001f436  mov     eax, [rdi+260h]
0x14001f43c  test    al, 1
0x14001f43e  jnz     loc_14001F597
0x14001f444  lea     rcx, [rbp+3A8h]; this
0x14001f44b  mov     [rsp+78h+arg_0], r15b
0x14001f453  lea     r8, [rsp+78h+arg_0]; unsigned __int8 *
0x14001f45b  mov     edx, 14h; unsigned int
0x14001f460  call    ?GetPropertyUchar@CPropertyCache@@QEAAHKPEAE@Z; CPropertyCache::GetPropertyUchar(ulong,uchar *)
0x14001f465  cmp     [rsp+78h+arg_0], r15b
0x14001f46d  jnz     loc_14001F66D
0x14001f473  test    esi, esi
0x14001f475  jz      loc_14001F60B
0x14001f47b  cmp     [rdi+13C8h], r15b
0x14001f482  jnz     loc_14001F60B
0x14001f488  mov     rcx, rdi; this
0x14001f48b  call    ?GetPortPropertyCache@COidJobBase@@IEAAPEAVCPortPropertyCache@@XZ; COidJobBase::GetPortPropertyCache(void)
0x14001f490  xor     r8d, r8d; unsigned __int8
0x14001f493  mov     rcx, rax; this
0x14001f496  lea     edx, [r8+2Fh]; unsigned int
0x14001f49a  call    ?GetPropertyBooleanOrDefault@CPropertyCache@@QEAAEKE@Z; CPropertyCache::GetPropertyBooleanOrDefault(ulong,uchar)
0x14001f49f  test    al, al
0x14001f4a1  jz      loc_14001F5DB
0x14001f4a7  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14001f4ae  mov     eax, 0Ch
0x14001f4b3  mul     rsi
0x14001f4b6  mov     r8d, 47696457h
0x14001f4bc  cmovb   rax, rcx
0x14001f4c0  mov     ecx, 40h ; '@'
0x14001f4c5  mov     rdx, rax
0x14001f4c8  call    cs:__imp_ExAllocatePool2
0x14001f4cf  nop     dword ptr [rax+rax+00h]
0x14001f4d4  mov     rbx, rax
0x14001f4d7  test    rax, rax
0x14001f4da  jz      loc_14001F722
0x14001f4e0  mov     r10d, r15d
0x14001f4e3  test    esi, esi
0x14001f4e5  jz      short loc_14001F523
0x14001f4e7  mov     r9, r15
0x14001f4ea  mov     rdx, [r14+r9*8]
0x14001f4ee  lea     r8, [r9+r9*2]
0x14001f4f2  inc     r10d
0x14001f4f5  mov     eax, [rdx+1BCh]
0x14001f4fb  mov     [rbx+r8*4], eax
0x14001f4ff  movzx   eax, word ptr [rdx+1C0h]
0x14001f506  mov     [rbx+r8*4+4], ax
0x14001f50c  mov     rax, [r14+r9*8]
0x14001f510  inc     r9
0x14001f513  mov     edx, [rax+2D8h]
0x14001f519  mov     [rbx+r8*4+8], edx
0x14001f51e  cmp     r10d, esi
0x14001f521  jb      short loc_14001F4EA
0x14001f523  mov     r8, rbx; struct DOT11_BSSID_CANDIDATE *
0x14001f526  mov     edx, esi; unsigned int
0x14001f528  mov     rcx, rbp; this
0x14001f52b  call    ?PerformPMKIDRequest@CPort@@QEAAKKPEAUDOT11_BSSID_CANDIDATE@@@Z; CPort::PerformPMKIDRequest(ulong,DOT11_BSSID_CANDIDATE *)
0x14001f530  mov     [rdi+1DACh], eax
0x14001f536  lea     rsi, WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids
0x14001f53d  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14001f544  jz      short loc_14001F562
0x14001f546  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f54d  cmp     byte ptr [rcx+29h], 5
0x14001f551  jnb     loc_14001F69A
0x14001f557  cmp     [rcx+48h], r15w
0x14001f55c  jnz     loc_14001F69A
0x14001f562  cmp     [rdi+1DACh], r15d
0x14001f569  setnz   dil
0x14001f56d  test    rbx, rbx
0x14001f570  jz      short loc_14001F57A
0x14001f572  mov     rcx, rbx; void *
0x14001f575  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14001f57a  lea     r11, [rsp+78h+var_28]
0x14001f57f  mov     al, dil
0x14001f582  mov     rbx, [r11+38h]
0x14001f586  mov     rbp, [r11+40h]
0x14001f58a  mov     rsp, r11
0x14001f58d  pop     r15
0x14001f58f  pop     r14
0x14001f591  pop     r13
0x14001f593  pop     rdi
0x14001f594  pop     rsi
0x14001f595  retn
0x14001f597  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14001f59e  jz      short loc_14001F562
0x14001f5a0  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f5a7  cmp     byte ptr [rcx+29h], 5
0x14001f5ab  jnb     short loc_14001F5B4
0x14001f5ad  cmp     [rcx+48h], r15w
0x14001f5b2  jz      short loc_14001F536
0x14001f5b4  mov     eax, [rdi+10h]
0x14001f5b7  mov     r9d, 100h
0x14001f5bd  mov     rcx, [rcx+40h]
0x14001f5c1  mov     [rsp+78h+var_48], eax
0x14001f5c5  mov     [rsp+78h+var_50], rdi
0x14001f5ca  mov     [rsp+78h+var_58], rdx
0x14001f5cf  mov     dl, 5
0x14001f5d1  call    WPP_RECORDER_SF_qD
0x14001f5d6  jmp     loc_14001F536
0x14001f5db  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14001f5e2  jz      loc_14001F562
0x14001f5e8  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f5ef  cmp     byte ptr [rcx+29h], 5
0x14001f5f3  jnb     short loc_14001F600
0x14001f5f5  cmp     [rcx+48h], r15w
0x14001f5fa  jz      loc_14001F536
0x14001f600  mov     r9d, 103h
0x14001f606  jmp     loc_14001F6FA
0x14001f60b  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14001f612  jz      loc_14001F562
0x14001f618  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f61f  cmp     byte ptr [rcx+29h], 5
0x14001f623  jnb     short loc_14001F630
0x14001f625  cmp     [rcx+48h], r15w
0x14001f62a  jz      loc_14001F536
0x14001f630  movzx   eax, byte ptr [rdi+13C8h]
0x14001f637  mov     r9d, 102h
0x14001f63d  mov     rcx, [rcx+40h]
0x14001f641  mov     dl, 5
0x14001f643  mov     [rsp+78h+var_38], eax
0x14001f647  mov     eax, [rdi+10h]
0x14001f64a  mov     dword ptr [rsp+78h+var_40], esi
0x14001f64e  lea     rsi, WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids
0x14001f655  mov     [rsp+78h+var_48], eax
0x14001f659  mov     [rsp+78h+var_50], rdi
0x14001f65e  mov     [rsp+78h+var_58], rsi
0x14001f663  call    WPP_RECORDER_SF_qDdd
0x14001f668  jmp     loc_14001F53D
0x14001f66d  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14001f674  jz      loc_14001F562
0x14001f67a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f681  cmp     byte ptr [rcx+29h], 5
0x14001f685  jnb     short loc_14001F692
0x14001f687  cmp     [rcx+48h], r15w
0x14001f68c  jz      loc_14001F536
0x14001f692  mov     r9d, 101h
0x14001f698  jmp     short loc_14001F6FA
0x14001f69a  mov     eax, [rdi+10h]
0x14001f69d  mov     r9d, 105h
0x14001f6a3  mov     rcx, [rcx+40h]
0x14001f6a7  mov     dl, 5
0x14001f6a9  mov     dword ptr [rsp+78h+var_40], r15d
0x14001f6ae  mov     [rsp+78h+var_48], eax
0x14001f6b2  mov     [rsp+78h+var_50], rdi
0x14001f6b7  mov     [rsp+78h+var_58], rsi
0x14001f6bc  call    WPP_RECORDER_SF_qDD
0x14001f6c1  jmp     loc_14001F562
0x14001f6c6  mov     eax, [rdi+10h]
0x14001f6c9  mov     r9d, 0FFh
0x14001f6cf  mov     rcx, [rcx+40h]
0x14001f6d3  mov     [rsp+78h+var_48], eax
0x14001f6d7  mov     [rsp+78h+var_50], rdi
0x14001f6dc  mov     [rsp+78h+var_58], rdx
0x14001f6e1  mov     dl, 5
0x14001f6e3  call    WPP_RECORDER_SF_qD
0x14001f6e8  lea     rdx, WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids
0x14001f6ef  jmp     loc_14001F436
0x14001f6f4  mov     r9d, 104h
0x14001f6fa  mov     eax, [rdi+10h]
0x14001f6fd  lea     rsi, WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids
0x14001f704  mov     rcx, [rcx+40h]
0x14001f708  mov     dl, 5
0x14001f70a  mov     [rsp+78h+var_48], eax
0x14001f70e  mov     [rsp+78h+var_50], rdi
0x14001f713  mov     [rsp+78h+var_58], rsi
0x14001f718  call    WPP_RECORDER_SF_qD
0x14001f71d  jmp     loc_14001F53D
0x14001f722  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14001f729  jz      loc_14001F562
0x14001f72f  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f736  cmp     byte ptr [rcx+29h], 5
0x14001f73a  jnb     short loc_14001F6F4
0x14001f73c  cmp     [rcx+48h], r15w
0x14001f741  jz      loc_14001F536
0x14001f747  jmp     short loc_14001F6F4
```
