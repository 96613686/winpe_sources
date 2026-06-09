# CEnumBSSListJob::CompleteBSSListEnum(int)

- ea: `0x140011f9c`
- end: `0x1400123b3`
- name: `?CompleteBSSListEnum@CEnumBSSListJob@@AEAAXH@Z`
- size: `1047`
- prototype: `void __fastcall(CEnumBSSListJob *__hidden this, int)`
- caller_count: `2`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140011dc0`
- `0x140091f00`

## callees

- `0x14000d054`
- `0x140011f9c`
- `0x140012f80`
- `0x140017260`
- `0x140018270`
- `0x14001a630`
- `0x14001af20`
- `0x14001e2c0`
- `0x14001eed0`
- `0x1400290c4`
- `0x14002ed50`
- `0x14002ef48`
- `0x1400959d0`
- `0x1400dfd40`

## pseudocode

```c
void __fastcall CEnumBSSListJob::CompleteBSSListEnum(CEnumBSSListJob *this, unsigned int Dot11WfdDeviceEntryList)
{
  int v4; // edx
  __int64 v5; // r8
  int v6; // r9d
  int v7; // r9d
  struct DOT11_BYTE_ARRAY *v8; // rbp
  int v9; // eax
  struct CPort *PortFromPortId; // rsi
  unsigned __int64 CurrentTime; // rax
  unsigned __int64 v12; // rdi
  CPropertyCache *v13; // rax
  unsigned __int64 v14; // rdx
  __int64 v15; // rax
  PDEVICE_OBJECT v16; // rcx
  int v17; // r9d
  unsigned __int64 v18; // r10
  __int64 v19; // rax
  struct _LIST_ENTRY *v20; // r9
  struct _LIST_ENTRY *v21; // r8
  _QWORD *CppObjectFromListEntry; // rax
  struct _LIST_ENTRY **v23; // r8
  unsigned __int64 v24; // rcx
  char v25; // al
  int v26; // edx
  int v27; // r8d
  __int64 v28; // [rsp+38h] [rbp-30h]
  unsigned int v29; // [rsp+80h] [rbp+18h] BYREF
  unsigned __int8 *v30; // [rsp+88h] [rbp+20h] BYREF

  if ( (unsigned int)Feature_Bugfix_59713127__private_IsEnabledDeviceUsageNoInline() )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
      && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      LOBYTE(v4) = 5;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        v4,
        v5,
        112,
        (__int64)WPP_1fe3c85c899130460b7e9228c55753b1_Traceguids,
        (char)this,
        *((_DWORD *)this + 4));
    }
    if ( Dot11WfdDeviceEntryList )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v7 = 113;
LABEL_21:
        LOBYTE(v4) = 2;
        WPP_RECORDER_SF_qDD(
          WPP_GLOBAL_Control->DeviceExtension,
          v4,
          v5,
          v7,
          (__int64)WPP_1fe3c85c899130460b7e9228c55753b1_Traceguids,
          (char)this,
          *((_DWORD *)this + 4),
          Dot11WfdDeviceEntryList);
        goto LABEL_58;
      }
      goto LABEL_58;
    }
    if ( *((_DWORD *)this + 147) < 0x10u )
    {
      Dot11WfdDeviceEntryList = -2147483643;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v4) = 2;
        WPP_RECORDER_SF_qD(
          WPP_GLOBAL_Control->DeviceExtension,
          v4,
          v5,
          114,
          (__int64)WPP_1fe3c85c899130460b7e9228c55753b1_Traceguids,
          (char)this,
          *((_DWORD *)this + 4));
      }
      **((_DWORD **)this + 74) = 0;
      **((_DWORD **)this + 75) = 16;
      goto LABEL_58;
    }
  }
  v8 = (struct DOT11_BYTE_ARRAY *)*((_QWORD *)this + 72);
  if ( (unsigned int)Feature_Bugfix_59713127__private_IsEnabledDeviceUsageNoInline() )
    goto LABEL_22;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v4) = 5;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      v4,
      v5,
      115,
      (__int64)WPP_1fe3c85c899130460b7e9228c55753b1_Traceguids,
      (char)this,
      *((_DWORD *)this + 4));
  }
  if ( !Dot11WfdDeviceEntryList )
  {
LABEL_22:
    **((_DWORD **)this + 74) = 12;
    v9 = *((_DWORD *)this + 15);
    if ( v9 != 40 )
    {
      if ( v9 != 139 )
      {
        Dot11WfdDeviceEntryList = -1073741637;
        goto LABEL_58;
      }
      Dot11WfdDeviceEntryList = CBSSListManager::GetDot11WfdDeviceEntryList(
                                  *((CBSSListManager **)this + 77),
                                  v8,
                                  *((_DWORD *)this + 147));
LABEL_52:
      if ( !Dot11WfdDeviceEntryList || Dot11WfdDeviceEntryList == -2147483643 )
      {
        **((_DWORD **)this + 74) = v8->uNumOfBytes + 12;
        **((_DWORD **)this + 75) = v8->uTotalNumOfBytes + 12;
        goto LABEL_58;
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v7 = 119;
        goto LABEL_21;
      }
      goto LABEL_58;
    }
    PortFromPortId = CAdapter::GetPortFromPortId(*((CAdapter **)this + 67), *((_WORD *)this + 26));
    CurrentTime = CSystem::get_CurrentTime();
    v12 = CurrentTime - 1200000000;
    if ( CurrentTime < 0x47868C00 )
      v12 = CurrentTime;
    if ( !*((_DWORD *)PortFromPortId + 97) )
    {
      v13 = (CPropertyCache *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)this + 67) + 8LL) + 8LL))(*((_QWORD *)this + 67) + 8LL);
      if ( (unsigned int)CPropertyCache::GetPropertyULongOrDefault(v13, 0x35u, 0) )
      {
        v15 = *((_QWORD *)this + 77);
        v30 = 0;
        v29 = 0;
        if ( *(_BYTE *)(v15 + 45) && *(_DWORD *)(v15 + 56) == 1 )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_49;
          v16 = WPP_GLOBAL_Control;
          if ( BYTE1(WPP_GLOBAL_Control->Timer) < 5u && !LOWORD(WPP_GLOBAL_Control->DeviceType) )
            goto LABEL_49;
          v17 = 117;
          LOBYTE(v14) = 5;
        }
        else
        {
          if ( (unsigned int)CPropertyCache::GetPropertyBuffer(
                               (struct CPort *)((char *)PortFromPortId + 480),
                               0x49u,
                               &v29,
                               &v30) )
            goto LABEL_49;
          if ( v29 != 8 )
            goto LABEL_49;
          v18 = *(_QWORD *)v30;
          if ( *(_QWORD *)v30 >= v12 )
            goto LABEL_49;
          v19 = *((_QWORD *)this + 77);
          if ( *(_BYTE *)(v19 + 45) )
            goto LABEL_49;
          if ( *(_BYTE *)(v19 + 44) )
          {
            v20 = (struct _LIST_ENTRY *)(v19 + 344);
            v21 = *(struct _LIST_ENTRY **)(v19 + 344);
            while ( v21 != v20 )
            {
              CppObjectFromListEntry = GetCppObjectFromListEntry(v21);
              v21 = *v23;
              v14 = CppObjectFromListEntry[84];
              v24 = CppObjectFromListEntry[79];
              if ( v24 <= v14 )
                v24 = CppObjectFromListEntry[84];
              if ( v24 >= v12 )
              {
                v25 = 0;
                goto LABEL_45;
              }
            }
            v25 = 1;
LABEL_45:
            if ( !v25 )
              goto LABEL_49;
          }
          v12 = v18;
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_49;
          v16 = WPP_GLOBAL_Control;
          v17 = 118;
          LOBYTE(v14) = 4;
        }
        WPP_RECORDER_SF_(v16->DeviceExtension, v14, 1, v17, (__int64)WPP_1fe3c85c899130460b7e9228c55753b1_Traceguids);
      }
    }
LABEL_49:
    Dot11WfdDeviceEntryList = CBSSListManager::GetDot11BSSEntryList(
                                *((CBSSListManager **)this + 77),
                                v12,
                                v8,
                                *((_DWORD *)this + 147));
    **((_DWORD **)this + 76) = 3;
    goto LABEL_52;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v7 = 116;
    goto LABEL_21;
  }
LABEL_58:
  CJobBase::CompleteJob(this, Dot11WfdDeviceEntryList, v5, v6);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v26) = 5;
    LODWORD(v28) = Dot11WfdDeviceEntryList;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v26,
      v27,
      120,
      (__int64)WPP_1fe3c85c899130460b7e9228c55753b1_Traceguids,
      (char)this,
      *((_DWORD *)this + 4),
      v28);
  }
}

```

## disassembly

```asm
0x140011f9c  mov     [rsp+arg_0], rbx
0x140011fa1  mov     [rsp+arg_8], rbp
0x140011fa6  push    rsi
0x140011fa7  push    rdi
0x140011fa8  push    r13
0x140011faa  push    r14
0x140011fac  push    r15
0x140011fae  sub     rsp, 40h
0x140011fb2  mov     edi, edx
0x140011fb4  mov     rbx, rcx
0x140011fb7  call    Feature_Bugfix_59713127__private_IsEnabledDeviceUsageNoInline
0x140011fbc  xor     r14d, r14d
0x140011fbf  lea     r15, WPP_RECORDER_INITIALIZED
0x140011fc6  lea     r13, WPP_1fe3c85c899130460b7e9228c55753b1_Traceguids
0x140011fcd  test    eax, eax
0x140011fcf  jz      loc_14001208C
0x140011fd5  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140011fdc  jz      short loc_140012014
0x140011fde  mov     rcx, cs:WPP_GLOBAL_Control
0x140011fe5  cmp     byte ptr [rcx+29h], 5
0x140011fe9  jnb     short loc_140011FF2
0x140011feb  cmp     [rcx+48h], r14w
0x140011ff0  jz      short loc_140012014
0x140011ff2  mov     eax, [rbx+10h]
0x140011ff5  mov     r9d, 70h ; 'p'
0x140011ffb  mov     rcx, [rcx+40h]
0x140011fff  mov     dl, 5
0x140012001  mov     [rsp+68h+var_38], eax
0x140012005  mov     [rsp+68h+var_40], rbx
0x14001200a  mov     [rsp+68h+var_48], r13
0x14001200f  call    WPP_RECORDER_SF_qD
0x140012014  test    edi, edi
0x140012016  jz      short loc_140012030
0x140012018  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14001201f  jz      loc_14001234E
0x140012025  mov     r9d, 71h ; 'q'
0x14001202b  jmp     loc_1400120F6
0x140012030  cmp     dword ptr [rbx+24Ch], 10h
0x140012037  jnb     short loc_14001208C
0x140012039  mov     edi, 80000005h
0x14001203e  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140012045  jz      short loc_140012070
0x140012047  mov     rcx, cs:WPP_GLOBAL_Control
0x14001204e  mov     r9d, 72h ; 'r'
0x140012054  mov     eax, [rbx+10h]
0x140012057  mov     dl, 2
0x140012059  mov     [rsp+68h+var_38], eax
0x14001205d  mov     [rsp+68h+var_40], rbx
0x140012062  mov     rcx, [rcx+40h]
0x140012066  mov     [rsp+68h+var_48], r13
0x14001206b  call    WPP_RECORDER_SF_qD
0x140012070  mov     rax, [rbx+250h]
0x140012077  mov     [rax], r14d
0x14001207a  mov     rax, [rbx+258h]
0x140012081  mov     dword ptr [rax], 10h
0x140012087  jmp     loc_14001234E
0x14001208c  mov     rbp, [rbx+240h]
0x140012093  call    Feature_Bugfix_59713127__private_IsEnabledDeviceUsageNoInline
0x140012098  test    eax, eax
0x14001209a  jnz     loc_140012122
0x1400120a0  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400120a7  jz      short loc_1400120DF
0x1400120a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400120b0  cmp     byte ptr [rcx+29h], 5
0x1400120b4  jnb     short loc_1400120BD
0x1400120b6  cmp     [rcx+48h], r14w
0x1400120bb  jz      short loc_1400120DF
0x1400120bd  mov     eax, [rbx+10h]
0x1400120c0  mov     r9d, 73h ; 's'
0x1400120c6  mov     rcx, [rcx+40h]
0x1400120ca  mov     dl, 5
0x1400120cc  mov     [rsp+68h+var_38], eax
0x1400120d0  mov     [rsp+68h+var_40], rbx
0x1400120d5  mov     [rsp+68h+var_48], r13
0x1400120da  call    WPP_RECORDER_SF_qD
0x1400120df  test    edi, edi
0x1400120e1  jz      short loc_140012122
0x1400120e3  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400120ea  jz      loc_14001234E
0x1400120f0  mov     r9d, 74h ; 't'
0x1400120f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400120fd  mov     dl, 2
0x1400120ff  mov     eax, [rbx+10h]
0x140012102  mov     dword ptr [rsp+68h+var_30], edi
0x140012106  mov     [rsp+68h+var_38], eax
0x14001210a  mov     rcx, [rcx+40h]
0x14001210e  mov     [rsp+68h+var_40], rbx
0x140012113  mov     [rsp+68h+var_48], r13
0x140012118  call    WPP_RECORDER_SF_qDD
0x14001211d  jmp     loc_14001234E
0x140012122  mov     rax, [rbx+250h]
0x140012129  mov     dword ptr [rax], 0Ch
0x14001212f  mov     eax, [rbx+3Ch]
0x140012132  cmp     eax, 28h ; '('
0x140012135  jnz     loc_1400122EA
0x14001213b  movzx   edx, word ptr [rbx+34h]; unsigned __int16
0x14001213f  mov     rcx, [rbx+218h]; this
0x140012146  call    ?GetPortFromPortId@CAdapter@@QEAAPEAVCPort@@G@Z; CAdapter::GetPortFromPortId(ushort)
0x14001214b  mov     rsi, rax
0x14001214e  call    ?get_CurrentTime@CSystem@@SA_KXZ; CSystem::get_CurrentTime(void)
0x140012153  cmp     rax, 47868C00h
0x140012159  lea     rdi, [rax-47868C00h]
0x140012160  cmovb   rdi, rax
0x140012164  cmp     [rsi+184h], r14d
0x14001216b  jnz     loc_1400122C0
0x140012171  mov     rcx, [rbx+218h]
0x140012178  add     rcx, 8
0x14001217c  mov     rdx, [rcx]
0x14001217f  mov     rax, [rdx+8]
0x140012183  call    _guard_dispatch_icall
0x140012188  xor     r8d, r8d; unsigned int
0x14001218b  mov     rcx, rax; this
0x14001218e  lea     edx, [r8+35h]; unsigned int
0x140012192  call    ?GetPropertyULongOrDefault@CPropertyCache@@QEAAKKK@Z; CPropertyCache::GetPropertyULongOrDefault(ulong,ulong)
0x140012197  test    eax, eax
0x140012199  jz      loc_1400122C0
0x14001219f  mov     rax, [rbx+268h]
0x1400121a6  mov     [rsp+68h+arg_18], r14
0x1400121ae  mov     [rsp+68h+arg_10], r14d
0x1400121b6  cmp     [rax+2Dh], r14b
0x1400121ba  jz      short loc_1400121F4
0x1400121bc  cmp     dword ptr [rax+38h], 1
0x1400121c0  jnz     short loc_1400121F4
0x1400121c2  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400121c9  jz      loc_1400122C0
0x1400121cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400121d6  cmp     byte ptr [rcx+29h], 5
0x1400121da  jnb     short loc_1400121E7
0x1400121dc  cmp     [rcx+48h], r14w
0x1400121e1  jz      loc_1400122C0
0x1400121e7  mov     r9d, 75h ; 'u'
0x1400121ed  mov     dl, 5
0x1400121ef  jmp     loc_1400122AC
0x1400121f4  lea     rcx, [rsi+1E0h]; this
0x1400121fb  mov     edx, 49h ; 'I'; unsigned int
0x140012200  lea     r9, [rsp+68h+arg_18]; unsigned __int8 **
0x140012208  lea     r8, [rsp+68h+arg_10]; unsigned int *
0x140012210  call    ?GetPropertyBuffer@CPropertyCache@@QEAAHKPEAKPEAPEAE@Z; CPropertyCache::GetPropertyBuffer(ulong,ulong *,uchar * *)
0x140012215  test    eax, eax
0x140012217  jnz     loc_1400122C0
0x14001221d  cmp     [rsp+68h+arg_10], 8
0x140012225  jnz     loc_1400122C0
0x14001222b  mov     rax, [rsp+68h+arg_18]
0x140012233  mov     r10, [rax]
0x140012236  cmp     r10, rdi
0x140012239  jnb     loc_1400122C0
0x14001223f  mov     rax, [rbx+268h]
0x140012246  cmp     [rax+2Dh], r14b
0x14001224a  jnz     short loc_1400122C0
0x14001224c  cmp     [rax+2Ch], r14b
0x140012250  jz      short loc_140012291
0x140012252  lea     r9, [rax+158h]
0x140012259  mov     r8, [r9]
0x14001225c  cmp     r8, r9
0x14001225f  jz      short loc_14001228B
0x140012261  mov     rcx, r8; struct _LIST_ENTRY *
0x140012264  call    ?GetCppObjectFromListEntry@@YAPEAXPEAU_LIST_ENTRY@@@Z; GetCppObjectFromListEntry(_LIST_ENTRY *)
0x140012269  mov     r8, [r8]
0x14001226c  mov     rdx, [rax+2A0h]
0x140012273  mov     rcx, [rax+278h]
0x14001227a  cmp     rcx, rdx
0x14001227d  cmovbe  rcx, rdx
0x140012281  cmp     rcx, rdi
0x140012284  jb      short loc_14001225C
0x140012286  mov     al, r14b
0x140012289  jmp     short loc_14001228D
0x14001228b  mov     al, 1
0x14001228d  test    al, al
0x14001228f  jz      short loc_1400122C0
0x140012291  mov     rdi, r10
0x140012294  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14001229b  jz      short loc_1400122C0
0x14001229d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400122a4  mov     r9d, 76h ; 'v'
0x1400122aa  mov     dl, 4
0x1400122ac  mov     rcx, [rcx+40h]
0x1400122b0  mov     r8d, 1
0x1400122b6  mov     [rsp+68h+var_48], r13
0x1400122bb  call    WPP_RECORDER_SF_
0x1400122c0  mov     r9d, [rbx+24Ch]; unsigned int
0x1400122c7  mov     r8, rbp; struct DOT11_BYTE_ARRAY *
0x1400122ca  mov     rcx, [rbx+268h]; this
0x1400122d1  mov     rdx, rdi; unsigned __int64
0x1400122d4  call    ?GetDot11BSSEntryList@CBSSListManager@@QEAAH_KPEAUDOT11_BYTE_ARRAY@@K@Z; CBSSListManager::GetDot11BSSEntryList(unsigned __int64,DOT11_BYTE_ARRAY *,ulong)
0x1400122d9  mov     edi, eax
0x1400122db  mov     rax, [rbx+260h]
0x1400122e2  mov     dword ptr [rax], 3
0x1400122e8  jmp     short loc_140012309
0x1400122ea  cmp     eax, 8Bh
0x1400122ef  jnz     short loc_140012349
0x1400122f1  mov     r8d, [rbx+24Ch]; unsigned int
0x1400122f8  mov     rdx, rbp; struct DOT11_BYTE_ARRAY *
0x1400122fb  mov     rcx, [rbx+268h]; this
0x140012302  call    ?GetDot11WfdDeviceEntryList@CBSSListManager@@QEAAHPEAUDOT11_BYTE_ARRAY@@K@Z; CBSSListManager::GetDot11WfdDeviceEntryList(DOT11_BYTE_ARRAY *,ulong)
0x140012307  mov     edi, eax
0x140012309  test    edi, edi
0x14001230b  jz      short loc_140012329
0x14001230d  cmp     edi, 80000005h
0x140012313  jz      short loc_140012329
0x140012315  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14001231c  jz      short loc_14001234E
0x14001231e  mov     r9d, 77h ; 'w'
0x140012324  jmp     loc_1400120F6
0x140012329  mov     rax, [rbx+250h]
0x140012330  mov     ecx, [rbp+4]
0x140012333  add     ecx, 0Ch
0x140012336  mov     [rax], ecx
0x140012338  mov     ecx, [rbp+8]
0x14001233b  mov     rax, [rbx+258h]
0x140012342  add     ecx, 0Ch
0x140012345  mov     [rax], ecx
0x140012347  jmp     short loc_14001234E
0x140012349  mov     edi, 0C00000BBh
0x14001234e  mov     edx, edi; int
0x140012350  mov     rcx, rbx; this
0x140012353  call    ?CompleteJob@CJobBase@@IEAAHH@Z; CJobBase::CompleteJob(int)
0x140012358  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14001235f  jz      short loc_14001239B
0x140012361  mov     rcx, cs:WPP_GLOBAL_Control
0x140012368  cmp     byte ptr [rcx+29h], 5
0x14001236c  jnb     short loc_140012375
0x14001236e  cmp     [rcx+48h], r14w
0x140012373  jz      short loc_14001239B
0x140012375  mov     eax, [rbx+10h]
0x140012378  mov     r9d, 78h ; 'x'
0x14001237e  mov     rcx, [rcx+40h]
0x140012382  mov     dl, 5
0x140012384  mov     dword ptr [rsp+68h+var_30], edi
0x140012388  mov     [rsp+68h+var_38], eax
0x14001238c  mov     [rsp+68h+var_40], rbx
0x140012391  mov     [rsp+68h+var_48], r13
0x140012396  call    WPP_RECORDER_SF_qDD
0x14001239b  mov     rbx, [rsp+68h+arg_0]
0x1400123a0  mov     rbp, [rsp+68h+arg_8]
0x1400123a5  add     rsp, 40h
0x1400123a9  pop     r15
0x1400123ab  pop     r14
0x1400123ad  pop     r13
0x1400123af  pop     rdi
0x1400123b0  pop     rsi
0x1400123b1  retn
```
