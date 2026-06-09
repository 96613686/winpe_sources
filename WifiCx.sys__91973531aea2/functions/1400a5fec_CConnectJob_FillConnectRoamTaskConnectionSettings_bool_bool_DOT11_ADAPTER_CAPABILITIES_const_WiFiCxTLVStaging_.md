# CConnectJob::FillConnectRoamTaskConnectionSettings(bool,bool,_DOT11_ADAPTER_CAPABILITIES const *,WiFiCxTLVStaging::_WDI_CONNECT_PARAMETERS_CONTAINER *)

- ea: `0x1400a5fec`
- end: `0x1400a6216`
- name: `?FillConnectRoamTaskConnectionSettings@CConnectJob@@AEAAH_N0PEBU_DOT11_ADAPTER_CAPABILITIES@@PEAU_WDI_CONNECT_PARAMETERS_CONTAINER@WiFiCxTLVStaging@@@Z`
- size: `554`
- prototype: `__int64 __usercall@<rax>(CConnectJob *__hidden this@<rcx>, bool@<dl>, bool@<r8b>, const struct _DOT11_ADAPTER_CAPABILITIES *@<r9>, struct _WDI_CONNECT_PARAMETERS_CONTAINER *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1400a6c04`

## callees

- `0x14000688c`
- `0x14000a34c`
- `0x140016d00`
- `0x14001e2c0`
- `0x14002ef48`
- `0x140071720`
- `0x140073410`
- `0x1400a5fec`
- `0x1400ab4e8`

## pseudocode

```c
__int64 __fastcall CConnectJob::FillConnectRoamTaskConnectionSettings(
        CConnectJob *this,
        char a2,
        char a3,
        const struct _DOT11_ADAPTER_CAPABILITIES *a4,
        struct _WDI_CONNECT_PARAMETERS_CONTAINER *a5)
{
  struct _WDI_CONNECT_PARAMETERS_CONTAINER *v6; // rdi
  struct CPort *PortFromPortId; // rax
  QoS::QoSManager *v11; // r9
  bool v12; // r11
  bool v13; // r8
  char IsDSCPToUPMappingAllowed; // al
  unsigned __int8 v15; // r8
  int v16; // edx
  char *v17; // r9
  char v18; // r11
  unsigned int v19; // esi
  CPropertyCache *PortPropertyCache; // rax
  CPropertyCache *v21; // rax
  int PropertyULong; // eax
  int v23; // edx
  int v24; // r8d
  __int64 v26; // [rsp+38h] [rbp-60h]
  unsigned int v27; // [rsp+A8h] [rbp+10h] BYREF

  v6 = a5;
  *((_BYTE *)a5 + 5) = *((_BYTE *)this + 1081);
  *((_BYTE *)v6 + 6) = *((_BYTE *)this + 1082);
  *((_BYTE *)v6 + 7) = *((_BYTE *)this + 1083);
  *((_BYTE *)v6 + 8) = *((_BYTE *)this + 1084);
  *((_BYTE *)v6 + 22) = *((_BYTE *)this + 1085);
  PortFromPortId = CAdapter::GetPortFromPortId(*((CAdapter **)this + 67), *((_WORD *)this + 26));
  v11 = (struct CPort *)((char *)PortFromPortId + 584);
  v12 = *((_BYTE *)PortFromPortId + 594) && *((_BYTE *)PortFromPortId + 616);
  *((_BYTE *)v6 + 23) = v12;
  v13 = *((_BYTE *)PortFromPortId + 593)
     && QoS::QoSManager::IsDSCPToUPMappingAllowed((struct CPort *)((char *)PortFromPortId + 584));
  *((_BYTE *)v6 + 24) = v13;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    IsDSCPToUPMappingAllowed = QoS::QoSManager::IsDSCPToUPMappingAllowed(v11);
    v16 = v15;
    LOBYTE(v16) = 4;
    WPP_RECORDER_SF_qDdddddd(
      WPP_GLOBAL_Control->DeviceExtension,
      v16,
      (unsigned __int8)v17[32],
      332,
      (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
      (char)this,
      *((_DWORD *)this + 4),
      v18,
      v17[10],
      v17[32],
      v15,
      v17[9],
      IsDSCPToUPMappingAllowed);
  }
  *((_BYTE *)v6 + 20) = *((_DWORD *)a4 + 105) == 1;
  if ( (*((_DWORD *)this + 158) & 0x10) != 0 )
    *((_DWORD *)v6 + 4) = 1;
  *((_BYTE *)v6 + 5) = a3;
  *((_BYTE *)v6 + 21) = *((_BYTE *)this + 1140);
  if ( a2 )
  {
    v19 = *((_DWORD *)this + 156);
    v27 = v19;
    PortPropertyCache = COidJobBase::GetPortPropertyCache((struct CPortPropertyCache **)this);
    if ( CPropertyCache::GetPropertyBooleanOrDefault(PortPropertyCache, 0x52u, 0) )
    {
      v21 = COidJobBase::GetPortPropertyCache((struct CPortPropertyCache **)this);
      PropertyULong = CPropertyCache::GetPropertyULong(v21, 0x54u, &v27);
      if ( PropertyULong || (v19 = v27, v27 == 0xFFFF) )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LODWORD(v26) = PropertyULong;
          LOBYTE(v23) = 2;
          WPP_RECORDER_SF_qDD(
            WPP_GLOBAL_Control->DeviceExtension,
            v23,
            v24,
            333,
            (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
            (char)this,
            *((_DWORD *)this + 4),
            v26);
        }
        v19 = *((_DWORD *)this + 156);
      }
    }
    *((_DWORD *)v6 + 3) = v19;
  }
  if ( (unsigned int)Feature_53299205__private_IsEnabledDeviceUsageNoInline() )
    *((_BYTE *)v6 + 25) = (*(_DWORD *)(*((_QWORD *)this + 67) + 4648LL) & 0x4000) != 0;
  return 0;
}

```

## disassembly

```asm
0x1400a5fec  mov     [rsp+arg_0], rbx
0x1400a5ff1  mov     [rsp+arg_10], rbp
0x1400a5ff6  push    rsi
0x1400a5ff7  push    rdi
0x1400a5ff8  push    r12
0x1400a5ffa  push    r13
0x1400a5ffc  push    r14
0x1400a5ffe  sub     rsp, 70h
0x1400a6002  mov     al, [rcx+439h]
0x1400a6008  mov     r14b, dl
0x1400a600b  mov     rdi, [rsp+98h+arg_20]
0x1400a6013  mov     rbx, rcx
0x1400a6016  mov     rsi, r9
0x1400a6019  mov     bpl, r8b
0x1400a601c  mov     [rdi+5], al
0x1400a601f  mov     al, [rcx+43Ah]
0x1400a6025  mov     [rdi+6], al
0x1400a6028  mov     al, [rcx+43Bh]
0x1400a602e  mov     [rdi+7], al
0x1400a6031  mov     al, [rcx+43Ch]
0x1400a6037  mov     [rdi+8], al
0x1400a603a  mov     al, [rcx+43Dh]
0x1400a6040  mov     [rdi+16h], al
0x1400a6043  movzx   edx, word ptr [rcx+34h]; unsigned __int16
0x1400a6047  mov     rcx, [rcx+218h]; this
0x1400a604e  call    ?GetPortFromPortId@CAdapter@@QEAAPEAVCPort@@G@Z; CAdapter::GetPortFromPortId(ushort)
0x1400a6053  lea     r9, [rax+248h]
0x1400a605a  cmp     byte ptr [r9+0Ah], 0
0x1400a605f  jz      short loc_1400A606D
0x1400a6061  cmp     byte ptr [r9+20h], 0
0x1400a6066  jz      short loc_1400A606D
0x1400a6068  mov     r11b, 1
0x1400a606b  jmp     short loc_1400A6070
0x1400a606d  xor     r11d, r11d
0x1400a6070  mov     [rdi+17h], r11b
0x1400a6074  cmp     byte ptr [r9+9], 0
0x1400a6079  jz      short loc_1400A608C
0x1400a607b  mov     rcx, r9; this
0x1400a607e  call    ?IsDSCPToUPMappingAllowed@QoSManager@QoS@@QEBA_NXZ; QoS::QoSManager::IsDSCPToUPMappingAllowed(void)
0x1400a6083  test    al, al
0x1400a6085  jz      short loc_1400A608C
0x1400a6087  mov     r8b, 1
0x1400a608a  jmp     short loc_1400A608F
0x1400a608c  xor     r8d, r8d
0x1400a608f  mov     [rdi+18h], r8b
0x1400a6093  lea     r12, WPP_RECORDER_INITIALIZED
0x1400a609a  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400a60a1  lea     r13, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400a60a8  jz      short loc_1400A6110
0x1400a60aa  mov     rcx, r9; this
0x1400a60ad  call    ?IsDSCPToUPMappingAllowed@QoSManager@QoS@@QEBA_NXZ; QoS::QoSManager::IsDSCPToUPMappingAllowed(void)
0x1400a60b2  movzx   r10d, byte ptr [r9+0Ah]
0x1400a60b7  movzx   ecx, al
0x1400a60ba  movzx   eax, byte ptr [r9+9]
0x1400a60bf  mov     [rsp+98h+var_38], ecx
0x1400a60c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a60ca  mov     [rsp+98h+var_40], eax
0x1400a60ce  mov     eax, [rbx+10h]
0x1400a60d1  movzx   edx, r8b
0x1400a60d5  movzx   r8d, byte ptr [r9+20h]
0x1400a60da  mov     r9d, 14Ch
0x1400a60e0  mov     rcx, [rcx+40h]
0x1400a60e4  mov     [rsp+98h+var_48], edx
0x1400a60e8  mov     dl, 4
0x1400a60ea  mov     [rsp+98h+var_50], r8d
0x1400a60ef  mov     [rsp+98h+var_58], r10d
0x1400a60f4  movzx   r11d, r11b
0x1400a60f8  mov     dword ptr [rsp+98h+var_60], r11d
0x1400a60fd  mov     [rsp+98h+var_68], eax
0x1400a6101  mov     [rsp+98h+var_70], rbx
0x1400a6106  mov     [rsp+98h+var_78], r13
0x1400a610b  call    WPP_RECORDER_SF_qDdddddd
0x1400a6110  cmp     dword ptr [rsi+1A4h], 1
0x1400a6117  setz    al
0x1400a611a  mov     [rdi+14h], al
0x1400a611d  mov     eax, [rbx+278h]
0x1400a6123  test    al, 10h
0x1400a6125  jz      short loc_1400A612E
0x1400a6127  mov     dword ptr [rdi+10h], 1
0x1400a612e  mov     [rdi+5], bpl
0x1400a6132  mov     al, [rbx+474h]
0x1400a6138  mov     [rdi+15h], al
0x1400a613b  test    r14b, r14b
0x1400a613e  jz      loc_1400A61DB
0x1400a6144  mov     esi, [rbx+270h]
0x1400a614a  mov     rcx, rbx; this
0x1400a614d  mov     [rsp+98h+arg_8], esi
0x1400a6154  call    ?GetPortPropertyCache@COidJobBase@@IEAAPEAVCPortPropertyCache@@XZ; COidJobBase::GetPortPropertyCache(void)
0x1400a6159  xor     r8d, r8d; unsigned __int8
0x1400a615c  mov     rcx, rax; this
0x1400a615f  lea     edx, [r8+52h]; unsigned int
0x1400a6163  call    ?GetPropertyBooleanOrDefault@CPropertyCache@@QEAAEKE@Z; CPropertyCache::GetPropertyBooleanOrDefault(ulong,uchar)
0x1400a6168  test    al, al
0x1400a616a  jz      short loc_1400A61D8
0x1400a616c  mov     rcx, rbx; this
0x1400a616f  call    ?GetPortPropertyCache@COidJobBase@@IEAAPEAVCPortPropertyCache@@XZ; COidJobBase::GetPortPropertyCache(void)
0x1400a6174  lea     r8, [rsp+98h+arg_8]; unsigned int *
0x1400a617c  mov     edx, 54h ; 'T'; unsigned int
0x1400a6181  mov     rcx, rax; this
0x1400a6184  call    ?GetPropertyULong@CPropertyCache@@QEAAHKPEAK@Z; CPropertyCache::GetPropertyULong(ulong,ulong *)
0x1400a6189  test    eax, eax
0x1400a618b  jnz     short loc_1400A619C
0x1400a618d  mov     esi, [rsp+98h+arg_8]
0x1400a6194  cmp     esi, 0FFFFh
0x1400a619a  jnz     short loc_1400A61D8
0x1400a619c  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400a61a3  jz      short loc_1400A61D2
0x1400a61a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a61ac  mov     r9d, 14Dh
0x1400a61b2  mov     dword ptr [rsp+98h+var_60], eax
0x1400a61b6  mov     dl, 2
0x1400a61b8  mov     eax, [rbx+10h]
0x1400a61bb  mov     [rsp+98h+var_68], eax
0x1400a61bf  mov     rcx, [rcx+40h]
0x1400a61c3  mov     [rsp+98h+var_70], rbx
0x1400a61c8  mov     [rsp+98h+var_78], r13
0x1400a61cd  call    WPP_RECORDER_SF_qDD
0x1400a61d2  mov     esi, [rbx+270h]
0x1400a61d8  mov     [rdi+0Ch], esi
0x1400a61db  call    Feature_53299205__private_IsEnabledDeviceUsageNoInline
0x1400a61e0  test    eax, eax
0x1400a61e2  jz      short loc_1400A61FA
0x1400a61e4  mov     rax, [rbx+218h]
0x1400a61eb  mov     ecx, [rax+1228h]
0x1400a61f1  shr     ecx, 0Eh
0x1400a61f4  and     cl, 1
0x1400a61f7  mov     [rdi+19h], cl
0x1400a61fa  lea     r11, [rsp+98h+var_28]
0x1400a61ff  xor     eax, eax
0x1400a6201  mov     rbx, [r11+30h]
0x1400a6205  mov     rbp, [r11+40h]
0x1400a6209  mov     rsp, r11
0x1400a620c  pop     r14
0x1400a620e  pop     r13
0x1400a6210  pop     r12
0x1400a6212  pop     rdi
0x1400a6213  pop     rsi
0x1400a6214  retn
```
