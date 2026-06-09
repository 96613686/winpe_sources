# CRdpIdAdapter::ProcessMonitorSurfaceUpdate(_RDPIDD_OPCODE_RAIL_MONITOR_SURFACE_UPDATE * const)

- ea: `0x18001a5c0`
- end: `0x18001a6b5`
- name: `?ProcessMonitorSurfaceUpdate@CRdpIdAdapter@@AEAAXQEAU_RDPIDD_OPCODE_RAIL_MONITOR_SURFACE_UPDATE@@@Z`
- size: `245`
- prototype: `void __fastcall(CRdpIdAdapter *__hidden this, struct _RDPIDD_OPCODE_RAIL_MONITOR_SURFACE_UPDATE *const)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x1800185bc`

## callees

- `0x18001072c`
- `0x180011584`
- `0x180013bb0`
- `0x18001534c`
- `0x18001a5c0`
- `0x180025c90`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CRdpIdAdapter::ProcessMonitorSurfaceUpdate(
        CRdpIdAdapter *this,
        struct _RDPIDD_OPCODE_RAIL_MONITOR_SURFACE_UPDATE *const a2,
        __int64 a3)
{
  struct _RDPIDD_OPCODE_RAIL_MONITOR_SURFACE_UPDATE *v3; // r10
  __int64 v4; // r9
  __int64 v5; // rax
  __int64 v6; // rdx
  _DWORD *v7; // rcx
  char *v8; // [rsp+28h] [rbp-40h]
  std::_Ref_count_base *v9[2]; // [rsp+40h] [rbp-28h] BYREF
  _QWORD v10[3]; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  __int64 v12; // [rsp+70h] [rbp+8h] BYREF

  v3 = a2;
  v4 = *((unsigned int *)a2 + 5);
  v5 = **((_QWORD **)this + 20);
  v12 = v5;
  while ( !*(_BYTE *)(v5 + 25) )
  {
    v6 = v5 + 48;
    v7 = *(_DWORD **)(v5 + 48);
    if ( v7[73] == *((_DWORD *)v3 + 3) && v7[74] == *((_DWORD *)v3 + 4) && v7[72] == (_DWORD)v4 )
    {
      std::shared_ptr<CRdpIdAdapter>::shared_ptr<CRdpIdAdapter>(v9, v6);
      goto LABEL_9;
    }
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>>,std::_Iterator_base0>::operator++(
      &v12,
      v6,
      a3,
      v4);
    v5 = v12;
  }
  *(_OWORD *)v9 = 0;
LABEL_9:
  if ( !v9[0] )
  {
    LODWORD(v8) = *((_DWORD *)v3 + 4);
    wil::details::in1diag3::Throw_NtStatusMsg(
      retaddr,
      (void *)0xB1C,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
      (const char *)0xC0000225LL,
      (int)"Monitor object is not found for Adapter %x.%x, TargetId %x",
      v8,
      *((_DWORD *)v3 + 3),
      *((_DWORD *)v3 + 5));
  }
  v10[0] = (char *)v3 + 32;
  v10[1] = (unsigned int)(*(_DWORD *)v3 - 32);
  CRdpIdMonitor::ProcessMonitorSurfaceUpdate((__int64)v9[0], *((_DWORD *)v3 + 6), *((_DWORD *)v3 + 7), v10);
  if ( v9[1] )
    std::_Ref_count_base::_Decref(v9[1]);
}

```

## disassembly

```asm
0x18001a5c0  sub     rsp, 68h
0x18001a5c4  mov     r10, rdx
0x18001a5c7  mov     r9d, [rdx+14h]
0x18001a5cb  mov     rax, [rcx+0A0h]
0x18001a5d2  mov     rax, [rax]
0x18001a5d5  mov     [rsp+68h+arg_0], rax
0x18001a5da  cmp     byte ptr [rax+19h], 0
0x18001a5de  jnz     short loc_18001A625
0x18001a5e0  lea     rdx, [rax+30h]
0x18001a5e4  mov     rcx, [rdx]
0x18001a5e7  mov     eax, [r10+0Ch]
0x18001a5eb  cmp     [rcx+124h], eax
0x18001a5f1  jnz     short loc_18001A608
0x18001a5f3  mov     eax, [r10+10h]
0x18001a5f7  cmp     [rcx+128h], eax
0x18001a5fd  jnz     short loc_18001A608
0x18001a5ff  cmp     [rcx+120h], r9d
0x18001a606  jz      short loc_18001A619
0x18001a608  lea     rcx, [rsp+68h+arg_0]
0x18001a60d  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>>,std::_Iterator_base0>::operator++(void)
0x18001a612  mov     rax, [rsp+68h+arg_0]
0x18001a617  jmp     short loc_18001A5DA
0x18001a619  lea     rcx, [rsp+68h+var_28]
0x18001a61e  call    ??0?$shared_ptr@VCRdpIdAdapter@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<CRdpIdAdapter>::shared_ptr<CRdpIdAdapter>(std::shared_ptr<CRdpIdAdapter> const &)
0x18001a623  jmp     short loc_18001A62E
0x18001a625  xorps   xmm0, xmm0
0x18001a628  movdqu  xmmword ptr [rsp+68h+var_28], xmm0
0x18001a62e  mov     rcx, [rsp+68h+var_28]
0x18001a633  test    rcx, rcx
0x18001a636  jz      short loc_18001A674
0x18001a638  lea     rax, [r10+20h]
0x18001a63c  mov     [rsp+68h+var_18], rax
0x18001a641  mov     eax, [r10]
0x18001a644  sub     eax, 20h ; ' '
0x18001a647  mov     [rsp+68h+var_10], rax
0x18001a64c  lea     r9, [rsp+68h+var_18]
0x18001a651  mov     r8d, [r10+1Ch]
0x18001a655  mov     edx, [r10+18h]
0x18001a659  call    ?ProcessMonitorSurfaceUpdate@CRdpIdMonitor@@QEAAXIIAEBV?$span@E$0?0@std@@@Z; CRdpIdMonitor::ProcessMonitorSurfaceUpdate(uint,uint,std::span<uchar,-1> const &)
0x18001a65e  nop
0x18001a65f  mov     rcx, [rsp+68h+var_28+8]; this
0x18001a664  test    rcx, rcx
0x18001a667  jz      short loc_18001A66E
0x18001a669  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001a66e  add     rsp, 68h
0x18001a672  retn
0x18001a674  mov     rcx, [rsp+68h]; this
0x18001a679  mov     eax, [r10+14h]
0x18001a67d  mov     [rsp+68h+var_30], eax
0x18001a681  mov     eax, [r10+0Ch]
0x18001a685  mov     [rsp+68h+var_38], eax
0x18001a689  mov     eax, [r10+10h]
0x18001a68d  mov     dword ptr [rsp+68h+var_40], eax; char *
0x18001a691  lea     rax, aMonitorObjectI; "Monitor object is not found for Adapter"...
0x18001a698  mov     qword ptr [rsp+68h+var_48], rax; int
0x18001a69d  mov     r9d, 0C0000225h; char *
0x18001a6a3  lea     r8, aOnecoreuapTerm_15; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18001a6aa  mov     edx, 0B1Ch; void *
0x18001a6af  call    ?Throw_NtStatusMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_NtStatusMsg(void *,uint,char const *,long,char const *,...)
```
