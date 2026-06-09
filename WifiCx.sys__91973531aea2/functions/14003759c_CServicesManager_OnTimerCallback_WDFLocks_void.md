# CServicesManager::OnTimerCallback_WDFLocks(void *)

- ea: `0x14003759c`
- end: `0x14003792a`
- name: `?OnTimerCallback_WDFLocks@CServicesManager@@AEAAXPEAX@Z`
- size: `910`
- prototype: `void __fastcall(CServicesManager *__hidden this, void *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x140037190`

## callees

- `0x14000c778`
- `0x14000d054`
- `0x14002007c`
- `0x14002293c`
- `0x140024a20`
- `0x14002ed50`
- `0x140036284`
- `0x14003759c`
- `0x14003895c`
- `0x1400940c0`
- `0x1400dfd00`

## pseudocode

```c
void __fastcall CServicesManager::OnTimerCallback_WDFLocks(CServicesManager *this, CServicesManager *a2)
{
  CServicesManager *v2; // rdi
  char v4; // si
  int v5; // edx
  int v6; // eax
  PDEVICE_OBJECT v7; // rcx
  int v8; // r9d
  unsigned __int64 CurrentTime; // rax
  int v10; // r8d
  PDEVICE_OBJECT v11; // rcx
  int v12; // r9d
  int v13; // edx
  __int64 v14; // [rsp+28h] [rbp-70h]
  _BYTE v15[8]; // [rsp+40h] [rbp-58h] BYREF
  __int128 v16; // [rsp+48h] [rbp-50h] BYREF
  __int64 v17; // [rsp+58h] [rbp-40h]

  v2 = a2;
  v17 = 0;
  v4 = 0;
  v16 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      214,
      (__int64)WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids);
  }
  wil::details::unique_wdf_spin_lock_storage::acquire((char *)this + 144, v15);
  if ( (CServicesManager *)((char *)this + 128) == v2 )
  {
    *((_BYTE *)this + 132) = 0;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
      && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      LOBYTE(v5) = 5;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v5,
        1,
        215,
        (__int64)WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids);
    }
    goto LABEL_23;
  }
  if ( (CServicesManager *)((char *)this + 124) != v2 )
    goto LABEL_47;
  v6 = *((_DWORD *)this + 26);
  *((_BYTE *)this + 133) = 0;
  if ( v6 )
  {
    if ( *((_BYTE *)this + 53) )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_23;
      v7 = WPP_GLOBAL_Control;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) < 5u && !LOWORD(WPP_GLOBAL_Control->DeviceType) )
        goto LABEL_23;
      v8 = 216;
LABEL_22:
      LOBYTE(v5) = 5;
      WPP_RECORDER_SF_d(v7->DeviceExtension, v5, 1, v8, (__int64)WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids, v6);
LABEL_23:
      v16 = *((_OWORD *)this + 6);
      v17 = *((_QWORD *)this + 14);
      *((_BYTE *)this + 54) = 1;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
        && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
      {
        LOBYTE(v5) = 5;
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v5,
          1,
          222,
          (__int64)WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids);
      }
      CAdapter::IndicateStatus(*((CAdapter **)this + 1), *((_DWORD *)this + 6), 1073938470, 0, &v16, 0x18u);
      goto LABEL_47;
    }
    CurrentTime = CSystem::get_CurrentTime();
    if ( CServicesManager::CheckForExpiredDevicesAndServices(this, CurrentTime) )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_23;
      v7 = WPP_GLOBAL_Control;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) < 5u && !LOWORD(WPP_GLOBAL_Control->DeviceType) )
        goto LABEL_23;
      v6 = *((_DWORD *)this + 26);
      v8 = 217;
      goto LABEL_22;
    }
    v5 = *((_DWORD *)this + 28);
    if ( !*((_QWORD *)this + 14) )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_47;
      v11 = WPP_GLOBAL_Control;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) < 5u && !LOWORD(WPP_GLOBAL_Control->DeviceType) )
        goto LABEL_47;
      v12 = 219;
      goto LABEL_46;
    }
    v4 = 1;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
      && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      LOBYTE(v5) = 5;
      WPP_RECORDER_SF_Ld(
        WPP_GLOBAL_Control->DeviceExtension,
        v5,
        v10,
        218,
        (__int64)WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids,
        *((_DWORD *)this + 28),
        *((_DWORD *)this + 29));
    }
  }
  else
  {
    if ( !*((_DWORD *)this + 24) )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_47;
      v11 = WPP_GLOBAL_Control;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) < 5u && !LOWORD(WPP_GLOBAL_Control->DeviceType) )
        goto LABEL_47;
      v12 = 221;
LABEL_46:
      LOBYTE(v5) = 5;
      WPP_RECORDER_SF_(v11->DeviceExtension, v5, 1, v12, (__int64)WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids);
      goto LABEL_47;
    }
    v4 = 1;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
      && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      LOBYTE(v5) = 5;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v5,
        1,
        220,
        (__int64)WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids,
        *((_DWORD *)this + 24));
    }
  }
LABEL_47:
  wil::details::unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(WDFSPINLOCK__ *),&void WdfSpinLockRelease(WDFSPINLOCK__ *),wistd::integral_constant<unsigned __int64,2>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(WDFSPINLOCK__ *),&void WdfSpinLockRelease(WDFSPINLOCK__ *),wistd::integral_constant<unsigned __int64,2>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>(v15);
  if ( v4 )
    CServicesManager::StartDeviceExpiryNotificationTimer(this);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LODWORD(v14) = 0;
    LOBYTE(v13) = 5;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v13,
      1,
      223,
      (__int64)WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids,
      v14);
  }
}

```

## disassembly

```asm
0x14003759c  mov     [rsp+arg_8], rbx
0x1400375a1  mov     [rsp+arg_10], rbp
0x1400375a6  push    rsi
0x1400375a7  push    rdi
0x1400375a8  push    r12
0x1400375aa  push    r13
0x1400375ac  push    r15
0x1400375ae  sub     rsp, 70h
0x1400375b2  mov     rax, cs:__security_cookie
0x1400375b9  xor     rax, rsp
0x1400375bc  mov     [rsp+98h+var_38], rax
0x1400375c1  xor     ebp, ebp
0x1400375c3  xorps   xmm0, xmm0
0x1400375c6  xor     eax, eax
0x1400375c8  mov     rdi, rdx
0x1400375cb  mov     [rsp+98h+var_40], rax
0x1400375d0  mov     rbx, rcx
0x1400375d3  mov     sil, bpl
0x1400375d6  movups  [rsp+98h+var_50], xmm0
0x1400375db  lea     r15, WPP_RECORDER_INITIALIZED
0x1400375e2  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400375e9  lea     r13, WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids
0x1400375f0  lea     r12d, [rbp+1]
0x1400375f4  jz      short loc_140037622
0x1400375f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400375fd  cmp     byte ptr [rcx+29h], 5
0x140037601  jnb     short loc_140037609
0x140037603  cmp     [rcx+48h], bp
0x140037607  jz      short loc_140037622
0x140037609  mov     rcx, [rcx+40h]
0x14003760d  mov     r9d, 0D6h
0x140037613  mov     r8d, r12d
0x140037616  mov     [rsp+98h+var_78], r13
0x14003761b  mov     dl, 5
0x14003761d  call    WPP_RECORDER_SF_
0x140037622  lea     rcx, [rbx+90h]
0x140037629  lea     rdx, [rsp+98h+var_58]
0x14003762e  call    ?acquire@unique_wdf_spin_lock_storage@details@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUWDFSPINLOCK__@@P6AXPEAU1@@Z$1?WdfSpinLockRelease@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@XZ; wil::details::unique_wdf_spin_lock_storage::acquire(void)
0x140037633  lea     rax, [rbx+80h]
0x14003763a  cmp     rax, rdi
0x14003763d  jnz     short loc_140037688
0x14003763f  mov     [rbx+84h], bpl
0x140037646  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14003764d  jz      loc_140037725
0x140037653  mov     rcx, cs:WPP_GLOBAL_Control
0x14003765a  cmp     byte ptr [rcx+29h], 5
0x14003765e  jnb     short loc_14003766A
0x140037660  cmp     [rcx+48h], bp
0x140037664  jz      loc_140037725
0x14003766a  mov     rcx, [rcx+40h]
0x14003766e  mov     r9d, 0D7h
0x140037674  mov     r8d, r12d
0x140037677  mov     [rsp+98h+var_78], r13
0x14003767c  mov     dl, 5
0x14003767e  call    WPP_RECORDER_SF_
0x140037683  jmp     loc_140037725
0x140037688  lea     rax, [rbx+7Ch]
0x14003768c  cmp     rax, rdi
0x14003768f  jnz     loc_1400378B3
0x140037695  mov     eax, [rbx+68h]
0x140037698  mov     [rbx+85h], bpl
0x14003769f  test    eax, eax
0x1400376a1  jz      loc_140037839
0x1400376a7  cmp     [rbx+35h], bpl
0x1400376ab  jz      short loc_1400376D1
0x1400376ad  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400376b4  jz      short loc_140037725
0x1400376b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400376bd  cmp     byte ptr [rcx+29h], 5
0x1400376c1  jnb     short loc_1400376C9
0x1400376c3  cmp     [rcx+48h], bp
0x1400376c7  jz      short loc_140037725
0x1400376c9  mov     r9d, 0D8h
0x1400376cf  jmp     short loc_14003770E
0x1400376d1  call    ?get_CurrentTime@CSystem@@SA_KXZ; CSystem::get_CurrentTime(void)
0x1400376d6  mov     rdx, rax; unsigned __int64
0x1400376d9  mov     rcx, rbx; this
0x1400376dc  call    ?CheckForExpiredDevicesAndServices@CServicesManager@@QEAAK_K@Z; CServicesManager::CheckForExpiredDevicesAndServices(unsigned __int64)
0x1400376e1  test    eax, eax
0x1400376e3  jz      loc_1400377B4
0x1400376e9  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400376f0  jz      short loc_140037725
0x1400376f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400376f9  cmp     byte ptr [rcx+29h], 5
0x1400376fd  jnb     short loc_140037705
0x1400376ff  cmp     [rcx+48h], bp
0x140037703  jz      short loc_140037725
0x140037705  mov     eax, [rbx+68h]
0x140037708  mov     r9d, 0D9h
0x14003770e  mov     rcx, [rcx+40h]
0x140037712  mov     r8d, r12d
0x140037715  mov     dword ptr [rsp+98h+var_70], eax
0x140037719  mov     dl, 5
0x14003771b  mov     [rsp+98h+var_78], r13
0x140037720  call    WPP_RECORDER_SF_d
0x140037725  mov     eax, [rbx+60h]
0x140037728  mov     dword ptr [rsp+98h+var_50], eax
0x14003772c  mov     eax, [rbx+64h]
0x14003772f  mov     dword ptr [rsp+98h+var_50+4], eax
0x140037733  mov     eax, [rbx+68h]
0x140037736  mov     dword ptr [rsp+98h+var_50+8], eax
0x14003773a  mov     eax, [rbx+6Ch]
0x14003773d  mov     dword ptr [rsp+98h+var_50+0Ch], eax
0x140037741  mov     eax, [rbx+70h]
0x140037744  mov     dword ptr [rsp+98h+var_40], eax
0x140037748  mov     eax, [rbx+74h]
0x14003774b  mov     dword ptr [rsp+98h+var_40+4], eax
0x14003774f  mov     [rbx+36h], r12b
0x140037753  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14003775a  jz      short loc_140037788
0x14003775c  mov     rcx, cs:WPP_GLOBAL_Control
0x140037763  cmp     byte ptr [rcx+29h], 5
0x140037767  jnb     short loc_14003776F
0x140037769  cmp     [rcx+48h], bp
0x14003776d  jz      short loc_140037788
0x14003776f  mov     rcx, [rcx+40h]
0x140037773  mov     r9d, 0DEh
0x140037779  mov     r8d, r12d
0x14003777c  mov     [rsp+98h+var_78], r13
0x140037781  mov     dl, 5
0x140037783  call    WPP_RECORDER_SF_
0x140037788  mov     edx, [rbx+18h]; unsigned int
0x14003778b  lea     rax, [rsp+98h+var_50]
0x140037790  mov     rcx, [rbx+8]; this
0x140037794  xor     r9d, r9d; void *
0x140037797  mov     dword ptr [rsp+98h+var_70], 18h; unsigned int
0x14003779f  mov     r8d, 40030026h; int
0x1400377a5  mov     [rsp+98h+var_78], rax; void *
0x1400377aa  call    ?IndicateStatus@CAdapter@@QEAAXKHPEAX0K@Z; CAdapter::IndicateStatus(ulong,int,void *,void *,ulong)
0x1400377af  jmp     loc_1400378B3
0x1400377b4  mov     edx, [rbx+70h]
0x1400377b7  test    edx, edx
0x1400377b9  jnz     short loc_1400377EF
0x1400377bb  cmp     [rbx+74h], ebp
0x1400377be  jnz     short loc_1400377EF
0x1400377c0  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400377c7  jz      loc_1400378B3
0x1400377cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400377d4  cmp     byte ptr [rcx+29h], 5
0x1400377d8  jnb     short loc_1400377E4
0x1400377da  cmp     [rcx+48h], bp
0x1400377de  jz      loc_1400378B3
0x1400377e4  mov     r9d, 0DBh
0x1400377ea  jmp     loc_1400378A0
0x1400377ef  mov     sil, r12b
0x1400377f2  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400377f9  jz      loc_1400378B3
0x1400377ff  mov     rcx, cs:WPP_GLOBAL_Control
0x140037806  cmp     byte ptr [rcx+29h], 5
0x14003780a  jnb     short loc_140037816
0x14003780c  cmp     [rcx+48h], bp
0x140037810  jz      loc_1400378B3
0x140037816  mov     eax, [rbx+74h]
0x140037819  mov     r9d, 0DAh
0x14003781f  mov     rcx, [rcx+40h]
0x140037823  mov     [rsp+98h+var_68], eax
0x140037827  mov     dword ptr [rsp+98h+var_70], edx
0x14003782b  mov     dl, 5
0x14003782d  mov     [rsp+98h+var_78], r13
0x140037832  call    WPP_RECORDER_SF_Ld
0x140037837  jmp     short loc_1400378B3
0x140037839  mov     eax, [rbx+60h]
0x14003783c  test    eax, eax
0x14003783e  jz      short loc_14003787E
0x140037840  mov     sil, r12b
0x140037843  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14003784a  jz      short loc_1400378B3
0x14003784c  mov     rcx, cs:WPP_GLOBAL_Control
0x140037853  cmp     byte ptr [rcx+29h], 5
0x140037857  jnb     short loc_14003785F
0x140037859  cmp     [rcx+48h], bp
0x14003785d  jz      short loc_1400378B3
0x14003785f  mov     rcx, [rcx+40h]
0x140037863  mov     r9d, 0DCh
0x140037869  mov     dword ptr [rsp+98h+var_70], eax
0x14003786d  mov     r8d, r12d
0x140037870  mov     dl, 5
0x140037872  mov     [rsp+98h+var_78], r13
0x140037877  call    WPP_RECORDER_SF_d
0x14003787c  jmp     short loc_1400378B3
0x14003787e  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140037885  jz      short loc_1400378B3
0x140037887  mov     rcx, cs:WPP_GLOBAL_Control
0x14003788e  cmp     byte ptr [rcx+29h], 5
0x140037892  jnb     short loc_14003789A
0x140037894  cmp     [rcx+48h], bp
0x140037898  jz      short loc_1400378B3
0x14003789a  mov     r9d, 0DDh
0x1400378a0  mov     rcx, [rcx+40h]
0x1400378a4  mov     r8d, r12d
0x1400378a7  mov     dl, 5
0x1400378a9  mov     [rsp+98h+var_78], r13
0x1400378ae  call    WPP_RECORDER_SF_
0x1400378b3  lea     rcx, [rsp+98h+var_58]
0x1400378b8  call    ??1?$unique_storage@U?$resource_policy@PEAUWDFSPINLOCK__@@P6AXPEAU1@@Z$1?WdfSpinLockRelease@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(WDFSPINLOCK__ *),&WdfSpinLockRelease(WDFSPINLOCK__ *),wistd::integral_constant<unsigned __int64,2>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(WDFSPINLOCK__ *),&WdfSpinLockRelease(WDFSPINLOCK__ *),wistd::integral_constant<unsigned __int64,2>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>(void)
0x1400378bd  test    sil, sil
0x1400378c0  jz      short loc_1400378CA
0x1400378c2  mov     rcx, rbx; this
0x1400378c5  call    ?StartDeviceExpiryNotificationTimer@CServicesManager@@QEAAXXZ; CServicesManager::StartDeviceExpiryNotificationTimer(void)
0x1400378ca  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400378d1  jz      short loc_140037903
0x1400378d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400378da  cmp     byte ptr [rcx+29h], 5
0x1400378de  jnb     short loc_1400378E6
0x1400378e0  cmp     [rcx+48h], bp
0x1400378e4  jz      short loc_140037903
0x1400378e6  mov     rcx, [rcx+40h]
0x1400378ea  mov     r9d, 0DFh
0x1400378f0  mov     dword ptr [rsp+98h+var_70], ebp
0x1400378f4  mov     r8d, r12d
0x1400378f7  mov     dl, 5
0x1400378f9  mov     [rsp+98h+var_78], r13
0x1400378fe  call    WPP_RECORDER_SF_d
0x140037903  mov     rcx, [rsp+98h+var_38]
0x140037908  xor     rcx, rsp; StackCookie
0x14003790b  call    __security_check_cookie
0x140037910  lea     r11, [rsp+98h+var_28]
0x140037915  mov     rbx, [r11+38h]
0x140037919  mov     rbp, [r11+40h]
0x14003791d  mov     rsp, r11
0x140037920  pop     r15
0x140037922  pop     r13
0x140037924  pop     r12
0x140037926  pop     rdi
0x140037927  pop     rsi
0x140037928  retn
```
