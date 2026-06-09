# CSetExcludedMacAddressListJob::SetData(void *,uint,uint *,uint *)

- ea: `0x140074120`
- end: `0x1400744d3`
- name: `?SetData@CSetExcludedMacAddressListJob@@UEAAHPEAXIPEAI1@Z`
- size: `947`
- prototype: `__int64 __usercall@<rax>(CSetExcludedMacAddressListJob *__hidden this@<rcx>, void *@<rdx>, unsigned int@<r8d>, unsigned int *@<r9>, unsigned int *)`
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400101c8`
- `0x140010298`
- `0x1400122e0`
- `0x1400147e8`
- `0x1400297a0`
- `0x14002aa28`
- `0x14002c5d8`
- `0x1400489f0`
- `0x140074120`
- `0x1400ac754`
- `0x1400b6414`
- `0x1400da680`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x140074366`
- `ntoskrnl!RtlCompareMemory` at `0x140074366`

## pseudocode

```c
__int64 __fastcall CSetExcludedMacAddressListJob::SetData(
        CSetExcludedMacAddressListJob *this,
        unsigned __int8 *a2,
        unsigned int a3,
        unsigned int *a4,
        unsigned int *a5)
{
  unsigned __int8 *v7; // rdi
  int v9; // edx
  int v10; // eax
  unsigned int v11; // ecx
  unsigned int v12; // ebx
  int v13; // edx
  int v14; // r8d
  struct CPortPropertyCache *PortPropertyCache; // rax
  int v16; // eax
  int v17; // r9d
  unsigned __int8 v18; // bp
  struct CPortPropertyCache *v19; // rax
  int v20; // eax
  struct CPort *PortFromNdisPortNumber; // r15
  __int64 v22; // rax
  const void *v23; // r14
  unsigned int m_ActivityId; // [rsp+30h] [rbp-88h]
  char v26; // [rsp+38h] [rbp-80h]

  v7 = a2;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      a3,
      109,
      (__int64)WPP_27877743ff0a3abe41d9950d4a9251de_Traceguids,
      (char)this,
      this->m_ActivityId);
  }
  v9 = *v7;
  if ( (_BYTE)v9 != 0x80 || !v7[1] || *((_WORD *)v7 + 1) < 0x14u )
  {
    v12 = -1073676267;
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      return v12;
    WPP_RECORDER_SF_qDDddddd(
      WPP_GLOBAL_Control->DeviceExtension,
      v9,
      20,
      110,
      (__int64)WPP_27877743ff0a3abe41d9950d4a9251de_Traceguids,
      (char)this,
      this->m_ActivityId,
      128,
      1,
      20,
      v9,
      v7[1],
      *((_WORD *)v7 + 1));
    goto LABEL_44;
  }
  v10 = *((_DWORD *)v7 + 1);
  if ( v10 && (v11 = 6 * (v10 + 2), *a5 = v11, a3 < v11) )
  {
    v12 = -2147483643;
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      return v12;
    LOBYTE(v9) = 2;
    WPP_RECORDER_SF_qDdd(
      WPP_GLOBAL_Control->DeviceExtension,
      v9,
      20,
      111,
      (__int64)WPP_27877743ff0a3abe41d9950d4a9251de_Traceguids,
      (char)this,
      this->m_ActivityId,
      v11,
      a3);
  }
  else
  {
    PortPropertyCache = COidJobBase::GetPortPropertyCache(this);
    v16 = CPropertyCache::SetPropertyList(
            PortPropertyCache,
            0x29u,
            6 * *((_DWORD *)v7 + 1),
            *((_DWORD *)v7 + 1),
            v7 + 12);
    v12 = v16;
    if ( v16 )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        return v12;
      v26 = v16;
      v17 = 112;
      m_ActivityId = this->m_ActivityId;
    }
    else
    {
      *a4 = *a5;
      if ( *((_DWORD *)v7 + 1) != 1
        || v7[12] != 0xFF
        || v7[13] != 0xFF
        || v7[14] != 0xFF
        || v7[15] != 0xFF
        || v7[16] != 0xFF
        || (v18 = 1, v7[17] != 0xFF) )
      {
        v18 = 0;
      }
      v19 = COidJobBase::GetPortPropertyCache(this);
      v20 = CPropertyCache::SetPropertyBoolean(v19, 0x2Au, v18);
      v12 = v20;
      if ( v20 )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
          return v12;
        v17 = 113;
      }
      else
      {
        if ( !*((_DWORD *)v7 + 1) )
        {
LABEL_40:
          v12 = 0;
          goto LABEL_44;
        }
        PortFromNdisPortNumber = CAdapter::GetPortFromNdisPortNumber(
                                   this->m_pAdapter,
                                   this->CSimpleSetOidJob::COidJobBase::CJobBase::m_NdisPortNumber);
        v22 = (__int64)PortFromNdisPortNumber->m_pPeerList->FindPeerByAssociationState(
                         PortFromNdisPortNumber->m_pPeerList,
                         dot11_assoc_state_auth_assoc);
        v12 = 0;
        if ( !v22 )
          goto LABEL_44;
        v23 = (const void *)(v22 + 1);
        while ( v12 < *((_DWORD *)v7 + 1) )
        {
          if ( RtlCompareMemory(v23, &v7[6 * v12 + 12], 6u) == 6 )
            goto LABEL_34;
          ++v12;
        }
        if ( !v18 )
          goto LABEL_40;
LABEL_34:
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v13) = 4;
          WPP_RECORDER_SF_qD_MAC_(
            WPP_GLOBAL_Control->DeviceExtension,
            v13,
            v14,
            114,
            (__int64)WPP_27877743ff0a3abe41d9950d4a9251de_Traceguids,
            (char)this,
            this->m_ActivityId,
            (__int64)v23);
        }
        v20 = CPort::TriggerDisconnectAndReconnect(
                PortFromNdisPortNumber,
                WDI_ASSOC_STATUS_DISASSOCIATED_BY_HOST,
                3u,
                WfcDisconnectTriggerExcludedMacAddressList);
        v12 = v20;
        if ( !v20 )
          goto LABEL_44;
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
          return v12;
        v17 = 115;
      }
      v26 = v20;
      m_ActivityId = this->m_ActivityId;
    }
    LOBYTE(v13) = 2;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v13,
      v14,
      v17,
      (__int64)WPP_27877743ff0a3abe41d9950d4a9251de_Traceguids,
      (char)this,
      m_ActivityId,
      v26);
  }
LABEL_44:
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v13) = 5;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v13,
      v14,
      116,
      (__int64)WPP_27877743ff0a3abe41d9950d4a9251de_Traceguids,
      (char)this,
      this->m_ActivityId,
      v12);
  }
  return v12;
}

```

## disassembly

```asm
0x140074120  push    rbx
0x140074122  push    rbp
0x140074123  push    rsi
0x140074124  push    rdi
0x140074125  push    r12
0x140074127  push    r13
0x140074129  push    r14
0x14007412b  push    r15
0x14007412d  sub     rsp, 78h
0x140074131  mov     r15, r9
0x140074134  mov     ebp, r8d
0x140074137  mov     rdi, rdx
0x14007413a  mov     rsi, rcx
0x14007413d  lea     r13, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140074144  xor     r12d, r12d
0x140074147  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14007414e  lea     r14, WPP_27877743ff0a3abe41d9950d4a9251de_Traceguids
0x140074155  jz      short loc_14007418D
0x140074157  mov     rcx, cs:WPP_GLOBAL_Control
0x14007415e  cmp     byte ptr [rcx+29h], 5
0x140074162  jnb     short loc_14007416B
0x140074164  cmp     [rcx+48h], r12w
0x140074169  jz      short loc_14007418D
0x14007416b  mov     eax, [rsi+10h]
0x14007416e  mov     r9d, 6Dh ; 'm'
0x140074174  mov     rcx, [rcx+40h]
0x140074178  mov     dl, 5
0x14007417a  mov     [rsp+0B8h+var_88], eax
0x14007417e  mov     [rsp+0B8h+var_90], rsi
0x140074183  mov     [rsp+0B8h+var_98], r14
0x140074188  call    WPP_RECORDER_SF_qD
0x14007418d  movzx   edx, byte ptr [rdi]
0x140074190  mov     r8d, 14h
0x140074196  cmp     dl, 80h
0x140074199  jnz     loc_14007441A
0x14007419f  cmp     byte ptr [rdi+1], 1
0x1400741a3  jb      loc_14007441A
0x1400741a9  cmp     [rdi+2], r8w
0x1400741ae  jb      loc_14007441A
0x1400741b4  mov     eax, [rdi+4]
0x1400741b7  mov     r14, [rsp+0B8h+arg_20]
0x1400741bf  test    eax, eax
0x1400741c1  jz      short loc_14007421F
0x1400741c3  add     eax, 2
0x1400741c6  lea     ecx, [rax+rax*2]
0x1400741c9  add     ecx, ecx
0x1400741cb  mov     [r14], ecx
0x1400741ce  cmp     ebp, ecx
0x1400741d0  jnb     short loc_14007421F
0x1400741d2  mov     ebx, 80000005h
0x1400741d7  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x1400741de  jz      loc_1400744BF
0x1400741e4  mov     eax, [rsi+10h]
0x1400741e7  lea     r14, WPP_27877743ff0a3abe41d9950d4a9251de_Traceguids
0x1400741ee  mov     [rsp+0B8h+var_78], ebp
0x1400741f2  lea     r9d, [r8+5Bh]
0x1400741f6  mov     dword ptr [rsp+0B8h+var_80], ecx
0x1400741fa  mov     dl, 2
0x1400741fc  mov     rcx, cs:WPP_GLOBAL_Control
0x140074203  mov     [rsp+0B8h+var_88], eax
0x140074207  mov     [rsp+0B8h+var_90], rsi
0x14007420c  mov     [rsp+0B8h+var_98], r14
0x140074211  mov     rcx, [rcx+40h]
0x140074215  call    WPP_RECORDER_SF_qDdd
0x14007421a  jmp     loc_14007447C
0x14007421f  mov     rcx, rsi; this
0x140074222  call    ?GetPortPropertyCache@COidJobBase@@IEAAPEAVCPortPropertyCache@@XZ; COidJobBase::GetPortPropertyCache(void)
0x140074227  mov     rcx, rax; this
0x14007422a  lea     rbp, [rdi+0Ch]
0x14007422e  mov     eax, [rdi+4]
0x140074231  mov     edx, 29h ; ')'; unsigned int
0x140074236  movzx   r9d, ax; unsigned __int16
0x14007423a  mov     [rsp+0B8h+var_98], rbp; unsigned __int8 *
0x14007423f  lea     r8d, [rax+rax*2]
0x140074243  add     r8d, r8d; unsigned int
0x140074246  call    ?SetPropertyList@CPropertyCache@@QEAAHKKGPEAE@Z; CPropertyCache::SetPropertyList(ulong,ulong,ushort,uchar *)
0x14007424b  mov     ebx, eax
0x14007424d  test    eax, eax
0x14007424f  jz      short loc_140074297
0x140074251  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140074258  jz      loc_1400744BF
0x14007425e  mov     ecx, [rsi+10h]
0x140074261  lea     r14, WPP_27877743ff0a3abe41d9950d4a9251de_Traceguids
0x140074268  mov     dword ptr [rsp+0B8h+var_80], eax
0x14007426c  mov     r9d, 70h ; 'p'
0x140074272  mov     [rsp+0B8h+var_88], ecx
0x140074276  mov     rcx, cs:WPP_GLOBAL_Control
0x14007427d  mov     dl, 2
0x14007427f  mov     [rsp+0B8h+var_90], rsi
0x140074284  mov     [rsp+0B8h+var_98], r14
0x140074289  mov     rcx, [rcx+40h]
0x14007428d  call    WPP_RECORDER_SF_qDD
0x140074292  jmp     loc_14007447C
0x140074297  mov     eax, [r14]
0x14007429a  mov     [r15], eax
0x14007429d  cmp     dword ptr [rdi+4], 1
0x1400742a1  jnz     short loc_1400742C6
0x1400742a3  mov     al, 0FFh
0x1400742a5  cmp     [rbp+0], al
0x1400742a8  jnz     short loc_1400742C6
0x1400742aa  cmp     [rdi+0Dh], al
0x1400742ad  jnz     short loc_1400742C6
0x1400742af  cmp     [rdi+0Eh], al
0x1400742b2  jnz     short loc_1400742C6
0x1400742b4  cmp     [rdi+0Fh], al
0x1400742b7  jnz     short loc_1400742C6
0x1400742b9  cmp     [rdi+10h], al
0x1400742bc  jnz     short loc_1400742C6
0x1400742be  mov     bpl, 1
0x1400742c1  cmp     [rdi+11h], al
0x1400742c4  jz      short loc_1400742C9
0x1400742c6  mov     bpl, r12b
0x1400742c9  mov     rcx, rsi; this
0x1400742cc  call    ?GetPortPropertyCache@COidJobBase@@IEAAPEAVCPortPropertyCache@@XZ; COidJobBase::GetPortPropertyCache(void)
0x1400742d1  mov     rcx, rax; this
0x1400742d4  mov     r8b, bpl; unsigned __int8
0x1400742d7  mov     edx, 2Ah ; '*'; unsigned int
0x1400742dc  call    ?SetPropertyBoolean@CPropertyCache@@QEAAHKE@Z; CPropertyCache::SetPropertyBoolean(ulong,uchar)
0x1400742e1  mov     ebx, eax
0x1400742e3  test    eax, eax
0x1400742e5  jz      short loc_140074306
0x1400742e7  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x1400742ee  lea     r14, WPP_27877743ff0a3abe41d9950d4a9251de_Traceguids
0x1400742f5  jz      loc_1400744BF
0x1400742fb  mov     r9d, 71h ; 'q'
0x140074301  jmp     loc_1400743FE
0x140074306  cmp     [rdi+4], r12d
0x14007430a  jz      loc_14007440E
0x140074310  mov     rcx, [rsi+200h]; this
0x140074317  mov     edx, [rsi+38h]; unsigned int
0x14007431a  call    ?GetPortFromNdisPortNumber@CAdapter@@QEAAPEAVCPort@@K@Z; CAdapter::GetPortFromNdisPortNumber(ulong)
0x14007431f  mov     r15, rax
0x140074322  mov     rcx, [rax+398h]
0x140074329  mov     rdx, [rcx]
0x14007432c  mov     rax, [rdx+18h]
0x140074330  mov     edx, 3
0x140074335  call    _guard_dispatch_icall
0x14007433a  mov     ebx, r12d
0x14007433d  test    rax, rax
0x140074340  jz      loc_140074411
0x140074346  lea     r14, [rax+1]
0x14007434a  cmp     ebx, [rdi+4]
0x14007434d  jnb     short loc_14007437C
0x14007434f  mov     eax, ebx
0x140074351  mov     r8d, 6; Length
0x140074357  add     rax, 2
0x14007435b  mov     rcx, r14; Source1
0x14007435e  lea     rax, [rax+rax*2]
0x140074362  lea     rdx, [rdi+rax*2]; Source2
0x140074366  call    cs:__imp_RtlCompareMemory
0x14007436d  nop     dword ptr [rax+rax+00h]
0x140074372  cmp     rax, 6
0x140074376  jz      short loc_140074385
0x140074378  inc     ebx
0x14007437a  jmp     short loc_14007434A
0x14007437c  test    bpl, bpl
0x14007437f  jz      loc_14007440E
0x140074385  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14007438c  jz      short loc_1400743C5
0x14007438e  mov     rcx, cs:WPP_GLOBAL_Control
0x140074395  mov     r9d, 72h ; 'r'
0x14007439b  mov     eax, [rsi+10h]
0x14007439e  mov     dl, 4
0x1400743a0  mov     [rsp+0B8h+var_80], r14
0x1400743a5  lea     r14, WPP_27877743ff0a3abe41d9950d4a9251de_Traceguids
0x1400743ac  mov     [rsp+0B8h+var_88], eax
0x1400743b0  mov     rcx, [rcx+40h]
0x1400743b4  mov     [rsp+0B8h+var_90], rsi
0x1400743b9  mov     [rsp+0B8h+var_98], r14
0x1400743be  call    WPP_RECORDER_SF_qD_MAC_
0x1400743c3  jmp     short loc_1400743CC
0x1400743c5  lea     r14, WPP_27877743ff0a3abe41d9950d4a9251de_Traceguids
0x1400743cc  mov     edx, 7; enum _WDI_ASSOC_STATUS
0x1400743d1  mov     rcx, r15; this
0x1400743d4  lea     r8d, [rdx-4]; unsigned __int16
0x1400743d8  lea     r9d, [rdx-2]; enum _WFC_DISCONNECT_TRIGGER
0x1400743dc  call    ?TriggerDisconnectAndReconnect@CPort@@QEAAHW4_WDI_ASSOC_STATUS@@GW4_WFC_DISCONNECT_TRIGGER@@@Z; CPort::TriggerDisconnectAndReconnect(_WDI_ASSOC_STATUS,ushort,_WFC_DISCONNECT_TRIGGER)
0x1400743e1  mov     ebx, eax
0x1400743e3  test    eax, eax
0x1400743e5  jz      loc_14007447C
0x1400743eb  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x1400743f2  jz      loc_1400744BF
0x1400743f8  mov     r9d, 73h ; 's'
0x1400743fe  mov     dword ptr [rsp+0B8h+var_80], eax
0x140074402  mov     eax, [rsi+10h]
0x140074405  mov     [rsp+0B8h+var_88], eax
0x140074409  jmp     loc_140074276
0x14007440e  mov     ebx, r12d
0x140074411  lea     r14, WPP_27877743ff0a3abe41d9950d4a9251de_Traceguids
0x140074418  jmp     short loc_14007447C
0x14007441a  mov     ebx, 0C0010015h
0x14007441f  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140074426  jz      loc_1400744BF
0x14007442c  movzx   eax, word ptr [rdi+2]
0x140074430  mov     r9d, 6Eh ; 'n'
0x140074436  movzx   ecx, byte ptr [rdi+1]
0x14007443a  mov     [rsp+0B8h+var_58], eax
0x14007443e  mov     eax, [rsi+10h]
0x140074441  mov     [rsp+0B8h+var_60], ecx
0x140074445  mov     rcx, cs:WPP_GLOBAL_Control
0x14007444c  mov     [rsp+0B8h+var_68], edx
0x140074450  mov     [rsp+0B8h+var_70], r8d
0x140074455  mov     [rsp+0B8h+var_78], 1
0x14007445d  mov     rcx, [rcx+40h]
0x140074461  mov     dword ptr [rsp+0B8h+var_80], 80h
0x140074469  mov     [rsp+0B8h+var_88], eax
0x14007446d  mov     [rsp+0B8h+var_90], rsi
0x140074472  mov     [rsp+0B8h+var_98], r14
0x140074477  call    WPP_RECORDER_SF_qDDddddd
0x14007447c  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140074483  jz      short loc_1400744BF
0x140074485  mov     rcx, cs:WPP_GLOBAL_Control
0x14007448c  cmp     byte ptr [rcx+29h], 5
0x140074490  jnb     short loc_140074499
0x140074492  cmp     [rcx+48h], r12w
0x140074497  jz      short loc_1400744BF
0x140074499  mov     eax, [rsi+10h]
0x14007449c  mov     r9d, 74h ; 't'
0x1400744a2  mov     rcx, [rcx+40h]
0x1400744a6  mov     dl, 5
0x1400744a8  mov     dword ptr [rsp+0B8h+var_80], ebx
0x1400744ac  mov     [rsp+0B8h+var_88], eax
0x1400744b0  mov     [rsp+0B8h+var_90], rsi
0x1400744b5  mov     [rsp+0B8h+var_98], r14
0x1400744ba  call    WPP_RECORDER_SF_qDD
0x1400744bf  mov     eax, ebx
0x1400744c1  add     rsp, 78h
0x1400744c5  pop     r15
0x1400744c7  pop     r14
0x1400744c9  pop     r13
0x1400744cb  pop     r12
0x1400744cd  pop     rdi
0x1400744ce  pop     rsi
0x1400744cf  pop     rbp
0x1400744d0  pop     rbx
0x1400744d1  retn
```
