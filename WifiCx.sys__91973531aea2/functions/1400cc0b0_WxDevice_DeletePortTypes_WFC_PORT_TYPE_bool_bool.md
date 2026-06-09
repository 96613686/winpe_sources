# WxDevice::DeletePortTypes(_WFC_PORT_TYPE,bool,bool)

- ea: `0x1400cc0b0`
- end: `0x1400cc378`
- name: `?DeletePortTypes@WxDevice@@QEAAJW4_WFC_PORT_TYPE@@_N1@Z`
- size: `712`
- prototype: `int __high(enum _WFC_PORT_TYPE, bool, bool)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, loader_planting`

## callers

- `0x1400ccf40`
- `0x1400ce1f0`

## callees

- `0x14000c778`
- `0x14000d054`
- `0x14001eed0`
- `0x140024428`
- `0x1400249bc`
- `0x140024a20`
- `0x14002cb2c`
- `0x14002d3b4`
- `0x140061338`
- `0x1400cbf0c`
- `0x1400cc0b0`
- `0x1400dfd40`

## pseudocode

```c
__int64 __fastcall WxDevice::DeletePortTypes(WxDevice *a1, unsigned int a2, bool a3, char a4)
{
  unsigned int v6; // ebp
  int v8; // r8d
  CAdapter *v10; // r12
  int v11; // eax
  unsigned int v12; // esi
  int v13; // eax
  int v14; // edx
  __int64 v15; // r9
  int v16; // r9d
  unsigned int v17; // eax
  int v18; // edx
  int v19; // r8d
  unsigned int v20; // r15d
  unsigned int i; // esi
  struct NETADAPTER__ *v22; // r14
  WxDevice *v23; // rcx
  int v24; // eax
  int v25; // edx
  int v26; // r8d
  int v27; // ebp
  __int64 v28; // [rsp+28h] [rbp-70h]
  _QWORD v29[11]; // [rsp+40h] [rbp-58h] BYREF

  v6 = a2;
  if ( a3 || !WxDevice::IsPowerManagedQueuePurgedForSx(a1) )
  {
    v10 = (WxDevice *)((char *)a1 + 56);
    if ( a4 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(a2) = 4;
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          a2,
          1,
          47,
          (__int64)WPP_270fc2b2b10437060e298a6bcfb11c73_Traceguids);
      }
      v11 = CAdapter::HandleDevicePowerNotify(v10);
      v12 = v11;
      if ( v11 < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(a2) = 2;
          WPP_RECORDER_SF_d(
            WPP_GLOBAL_Control->DeviceExtension,
            a2,
            1,
            48,
            (__int64)WPP_270fc2b2b10437060e298a6bcfb11c73_Traceguids,
            v11);
        }
        return v12;
      }
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 4;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        1,
        49,
        (__int64)WPP_270fc2b2b10437060e298a6bcfb11c73_Traceguids,
        v6);
    }
    v29[0] = 0;
    v13 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD *))(WdfFunctions_01031 + 104))(
            WdfDriverGlobals,
            0,
            v29);
    v12 = v13;
    if ( v13 >= 0 )
    {
      LOBYTE(v15) = a3;
      v13 = CAdapter::PrepareNetAdaptersToStop(v10, v6, v29[0], v15);
      v12 = v13;
      if ( v13 >= 0 )
      {
        v17 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01031 + 112))(
                WdfDriverGlobals,
                v29[0]);
        v20 = v17;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v18) = 4;
          WPP_RECORDER_SF_Ld(
            WPP_GLOBAL_Control->DeviceExtension,
            v18,
            v19,
            52,
            (__int64)WPP_270fc2b2b10437060e298a6bcfb11c73_Traceguids,
            v17,
            v6);
        }
        for ( i = 0; ; ++i )
        {
          if ( i >= v20 )
          {
            v12 = 0;
            goto LABEL_33;
          }
          v22 = (struct NETADAPTER__ *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD))(WdfFunctions_01031 + 144))(
                                         WdfDriverGlobals,
                                         v29[0],
                                         i);
          v24 = WxDevice::DeleteInnerPort(v23, v10, v22, a3);
          v27 = v24;
          if ( v24 < 0 )
            break;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v25) = 4;
            WPP_RECORDER_SF_q(
              WPP_GLOBAL_Control->DeviceExtension,
              v25,
              v26,
              54,
              (__int64)WPP_270fc2b2b10437060e298a6bcfb11c73_Traceguids,
              (char)v22);
          }
        }
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v25) = 2;
          WPP_RECORDER_SF_qD(
            WPP_GLOBAL_Control->DeviceExtension,
            v25,
            v26,
            53,
            (__int64)WPP_270fc2b2b10437060e298a6bcfb11c73_Traceguids,
            (char)v22,
            v24);
        }
        v12 = v27;
        goto LABEL_33;
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v16 = 51;
        goto LABEL_20;
      }
    }
    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v16 = 50;
LABEL_20:
      LODWORD(v28) = v13;
      LOBYTE(v14) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v14,
        1,
        v16,
        (__int64)WPP_270fc2b2b10437060e298a6bcfb11c73_Traceguids,
        v28);
    }
LABEL_33:
    wil::details::unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(void *),&void WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(void *),&void WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>(v29);
    return v12;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a2) = 2;
    WPP_RECORDER_SF_Ld(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      v8,
      46,
      (__int64)WPP_270fc2b2b10437060e298a6bcfb11c73_Traceguids,
      v6,
      v6);
  }
  return 3221225488LL;
}

```

## disassembly

```asm
0x1400cc0b0  push    rbx
0x1400cc0b2  push    rbp
0x1400cc0b3  push    rsi
0x1400cc0b4  push    rdi
0x1400cc0b5  push    r12
0x1400cc0b7  push    r13
0x1400cc0b9  push    r14
0x1400cc0bb  push    r15
0x1400cc0bd  sub     rsp, 58h
0x1400cc0c1  mov     sil, r9b
0x1400cc0c4  mov     r13b, r8b
0x1400cc0c7  mov     ebp, edx
0x1400cc0c9  mov     rbx, rcx
0x1400cc0cc  test    r8b, r8b
0x1400cc0cf  jnz     short loc_1400CC120
0x1400cc0d1  call    ?IsPowerManagedQueuePurgedForSx@WxDevice@@QEAA_NXZ; WxDevice::IsPowerManagedQueuePurgedForSx(void)
0x1400cc0d6  test    al, al
0x1400cc0d8  jz      short loc_1400CC120
0x1400cc0da  lea     rbx, WPP_RECORDER_INITIALIZED
0x1400cc0e1  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1400cc0e8  jz      short loc_1400CC116
0x1400cc0ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cc0f1  lea     rdi, WPP_270fc2b2b10437060e298a6bcfb11c73_Traceguids
0x1400cc0f8  mov     [rsp+98h+var_68], ebp
0x1400cc0fc  mov     r9d, 2Eh ; '.'
0x1400cc102  mov     dword ptr [rsp+98h+var_70], ebp
0x1400cc106  mov     dl, 2
0x1400cc108  mov     [rsp+98h+var_78], rdi
0x1400cc10d  mov     rcx, [rcx+40h]
0x1400cc111  call    WPP_RECORDER_SF_Ld
0x1400cc116  mov     eax, 0C0000010h
0x1400cc11b  jmp     loc_1400CC366
0x1400cc120  lea     r12, [rbx+38h]
0x1400cc124  mov     r14d, 1
0x1400cc12a  lea     rbx, WPP_RECORDER_INITIALIZED
0x1400cc131  lea     rdi, WPP_270fc2b2b10437060e298a6bcfb11c73_Traceguids
0x1400cc138  test    sil, sil
0x1400cc13b  jz      short loc_1400CC1A8
0x1400cc13d  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1400cc144  jz      short loc_1400CC164
0x1400cc146  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cc14d  lea     r9d, [r14+2Eh]
0x1400cc151  mov     r8d, r14d
0x1400cc154  mov     [rsp+98h+var_78], rdi
0x1400cc159  mov     dl, 4
0x1400cc15b  mov     rcx, [rcx+40h]
0x1400cc15f  call    WPP_RECORDER_SF_
0x1400cc164  mov     rcx, r12; this
0x1400cc167  call    ?HandleDevicePowerNotify@CAdapter@@QEAAHXZ; CAdapter::HandleDevicePowerNotify(void)
0x1400cc16c  mov     esi, eax
0x1400cc16e  test    eax, eax
0x1400cc170  jns     short loc_1400CC1A8
0x1400cc172  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1400cc179  jz      loc_1400CC364
0x1400cc17f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cc186  mov     r9d, 30h ; '0'
0x1400cc18c  mov     dword ptr [rsp+98h+var_70], eax
0x1400cc190  mov     r8d, r14d
0x1400cc193  mov     dl, 2
0x1400cc195  mov     [rsp+98h+var_78], rdi
0x1400cc19a  mov     rcx, [rcx+40h]
0x1400cc19e  call    WPP_RECORDER_SF_d
0x1400cc1a3  jmp     loc_1400CC364
0x1400cc1a8  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1400cc1af  jz      short loc_1400CC1D5
0x1400cc1b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cc1b8  mov     r9d, 31h ; '1'
0x1400cc1be  mov     dword ptr [rsp+98h+var_70], ebp
0x1400cc1c2  mov     r8d, r14d
0x1400cc1c5  mov     dl, 4
0x1400cc1c7  mov     [rsp+98h+var_78], rdi
0x1400cc1cc  mov     rcx, [rcx+40h]
0x1400cc1d0  call    WPP_RECORDER_SF_d
0x1400cc1d5  mov     rax, cs:WdfFunctions_01031
0x1400cc1dc  lea     r8, [rsp+98h+var_58]
0x1400cc1e1  mov     rcx, cs:WdfDriverGlobals
0x1400cc1e8  xor     edx, edx
0x1400cc1ea  mov     [rsp+98h+var_58], 0
0x1400cc1f3  mov     rax, [rax+68h]
0x1400cc1f7  call    _guard_dispatch_icall
0x1400cc1fc  mov     esi, eax
0x1400cc1fe  test    eax, eax
0x1400cc200  jns     short loc_1400CC217
0x1400cc202  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1400cc209  jz      loc_1400CC35A
0x1400cc20f  mov     r9d, 32h ; '2'
0x1400cc215  jmp     short loc_1400CC242
0x1400cc217  mov     r8, [rsp+98h+var_58]
0x1400cc21c  mov     r9b, r13b
0x1400cc21f  mov     edx, ebp
0x1400cc221  mov     rcx, r12
0x1400cc224  call    ?PrepareNetAdaptersToStop@CAdapter@@QEAAJW4_WFC_PORT_TYPE@@PEAUWDFCOLLECTION__@@_N@Z; CAdapter::PrepareNetAdaptersToStop(_WFC_PORT_TYPE,WDFCOLLECTION__ *,bool)
0x1400cc229  mov     esi, eax
0x1400cc22b  test    eax, eax
0x1400cc22d  jns     short loc_1400CC265
0x1400cc22f  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1400cc236  jz      loc_1400CC35A
0x1400cc23c  mov     r9d, 33h ; '3'
0x1400cc242  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cc249  mov     r8d, r14d
0x1400cc24c  mov     dword ptr [rsp+98h+var_70], eax
0x1400cc250  mov     dl, 2
0x1400cc252  mov     [rsp+98h+var_78], rdi
0x1400cc257  mov     rcx, [rcx+40h]
0x1400cc25b  call    WPP_RECORDER_SF_d
0x1400cc260  jmp     loc_1400CC35A
0x1400cc265  mov     rax, cs:WdfFunctions_01031
0x1400cc26c  mov     rdx, [rsp+98h+var_58]
0x1400cc271  mov     rcx, cs:WdfDriverGlobals
0x1400cc278  mov     rax, [rax+70h]
0x1400cc27c  call    _guard_dispatch_icall
0x1400cc281  mov     r15d, eax
0x1400cc284  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1400cc28b  jz      short loc_1400CC2B2
0x1400cc28d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cc294  mov     r9d, 34h ; '4'
0x1400cc29a  mov     [rsp+98h+var_68], ebp
0x1400cc29e  mov     dl, 4
0x1400cc2a0  mov     dword ptr [rsp+98h+var_70], eax
0x1400cc2a4  mov     [rsp+98h+var_78], rdi
0x1400cc2a9  mov     rcx, [rcx+40h]
0x1400cc2ad  call    WPP_RECORDER_SF_Ld
0x1400cc2b2  xor     esi, esi
0x1400cc2b4  cmp     esi, r15d
0x1400cc2b7  jnb     loc_1400CC358
0x1400cc2bd  mov     rax, cs:WdfFunctions_01031
0x1400cc2c4  mov     r8d, esi
0x1400cc2c7  mov     rdx, [rsp+98h+var_58]
0x1400cc2cc  mov     rcx, cs:WdfDriverGlobals
0x1400cc2d3  mov     rax, [rax+90h]
0x1400cc2da  call    _guard_dispatch_icall
0x1400cc2df  mov     r9b, r13b; bool
0x1400cc2e2  mov     r8, rax; struct NETADAPTER__ *
0x1400cc2e5  mov     rdx, r12; struct CAdapter *
0x1400cc2e8  mov     r14, rax
0x1400cc2eb  call    ?DeleteInnerPort@WxDevice@@AEAAJQEAVCAdapter@@PEAUNETADAPTER__@@_N@Z; WxDevice::DeleteInnerPort(CAdapter * const,NETADAPTER__ *,bool)
0x1400cc2f0  mov     ebp, eax
0x1400cc2f2  test    eax, eax
0x1400cc2f4  js      short loc_1400CC325
0x1400cc2f6  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1400cc2fd  jz      short loc_1400CC321
0x1400cc2ff  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cc306  mov     r9d, 36h ; '6'
0x1400cc30c  mov     [rsp+98h+var_70], r14
0x1400cc311  mov     dl, 4
0x1400cc313  mov     [rsp+98h+var_78], rdi
0x1400cc318  mov     rcx, [rcx+40h]
0x1400cc31c  call    WPP_RECORDER_SF_q
0x1400cc321  inc     esi
0x1400cc323  jmp     short loc_1400CC2B4
0x1400cc325  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1400cc32c  jz      short loc_1400CC354
0x1400cc32e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cc335  mov     r9d, 35h ; '5'
0x1400cc33b  mov     [rsp+98h+var_68], ebp
0x1400cc33f  mov     dl, 2
0x1400cc341  mov     [rsp+98h+var_70], r14
0x1400cc346  mov     [rsp+98h+var_78], rdi
0x1400cc34b  mov     rcx, [rcx+40h]
0x1400cc34f  call    WPP_RECORDER_SF_qD
0x1400cc354  mov     esi, ebp
0x1400cc356  jmp     short loc_1400CC35A
0x1400cc358  xor     esi, esi
0x1400cc35a  lea     rcx, [rsp+98h+var_58]
0x1400cc35f  call    ??1?$unique_storage@U?$resource_policy@PEAUWDFSPINLOCK__@@P6AXPEAX@Z$1?WdfObjectDelete@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(void *),&WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(void *),&WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>(void)
0x1400cc364  mov     eax, esi
0x1400cc366  add     rsp, 58h
0x1400cc36a  pop     r15
0x1400cc36c  pop     r14
0x1400cc36e  pop     r13
0x1400cc370  pop     r12
0x1400cc372  pop     rdi
0x1400cc373  pop     rsi
0x1400cc374  pop     rbp
0x1400cc375  pop     rbx
0x1400cc376  retn
```
