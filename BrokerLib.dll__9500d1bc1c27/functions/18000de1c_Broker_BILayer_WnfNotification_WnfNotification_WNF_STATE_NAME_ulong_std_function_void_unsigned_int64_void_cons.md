# Broker::BILayer::WnfNotification::WnfNotification(_WNF_STATE_NAME,ulong,std::function<void (unsigned __int64,void const *)>)

- ea: `0x18000de1c`
- end: `0x18000dffa`
- name: `??0WnfNotification@BILayer@Broker@@QEAA@U_WNF_STATE_NAME@@KV?$function@$$A6AX_KPEBX@Z@std@@@Z`
- size: `478`
- prototype: ``
- caller_count: `10`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000dc30`
- `0x18000dcd4`
- `0x18000dd78`
- `0x18000e000`
- `0x18000e0a4`
- `0x18000e188`
- `0x18000e22c`
- `0x1800137e4`
- `0x180013888`
- `0x180014174`

## callees

- `0x180009e94`
- `0x18000de1c`
- `0x180015af0`
- `0x1800165da`
- `0x18001e010`

## import_xrefs

- `ntdll!NtQueryWnfStateData` at `0x18000dead`
- `ntdll!NtQueryWnfStateData` at `0x18000dead`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18000deee`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18000deee`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall Broker::BILayer::WnfNotification::WnfNotification(_QWORD *a1, __int64 a2, int a3, __int64 *a4)
{
  _QWORD *v7; // rbx
  __int64 (__fastcall ***v8)(_QWORD, _QWORD *); // rcx
  unsigned int v9; // ebx
  int v10; // eax
  int v11; // ebx
  __int64 *v12; // rcx
  __int64 v13; // rdx
  unsigned int v15; // [rsp+40h] [rbp-29h] BYREF
  int v16; // [rsp+44h] [rbp-25h] BYREF
  void **pExceptionObject; // [rsp+48h] [rbp-21h] BYREF
  __int128 v18; // [rsp+50h] [rbp-19h]
  int v19; // [rsp+60h] [rbp-9h]
  int v20; // [rsp+68h] [rbp-1h]
  _QWORD *v21; // [rsp+70h] [rbp+7h]
  __int64 *v22; // [rsp+78h] [rbp+Fh]
  _QWORD *v23; // [rsp+80h] [rbp+17h]
  __int64 v24; // [rsp+88h] [rbp+1Fh] BYREF

  v21 = a1;
  v24 = a2;
  v22 = a4;
  *a1 = a2;
  v7 = a1 + 2;
  v23 = a1 + 2;
  a1[9] = 0;
  v8 = (__int64 (__fastcall ***)(_QWORD, _QWORD *))a4[7];
  if ( v8 )
    v7[7] = (**v8)(v8, v7);
  v15 = 0;
  v16 = 0;
  v9 = NtQueryWnfStateData(&v24, 0, 0, &v15, 0, &v16);
  if ( (int)(v9 + 0x80000000) >= 0 && v9 != -1073741789 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_6d22d7a2e1813c043b7d2163e38154fa_Traceguids, v9);
    v18 = 0;
    v19 = 6;
    pExceptionObject = &Broker::BILayer::Failure::`vftable';
    v20 = v9;
    throw (Broker::BILayer::Failure *)&pExceptionObject;
  }
  v10 = RtlSubscribeWnfStateChangeNotification(
          a1 + 1,
          v24,
          v15,
          Broker::BILayer::WnfNotification::WnfCallback,
          a1,
          0,
          a3,
          0);
  v11 = v10;
  if ( v10 < 0 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        38,
        &WPP_6d22d7a2e1813c043b7d2163e38154fa_Traceguids,
        (unsigned int)v10);
    v18 = 0;
    v19 = 6;
    pExceptionObject = &Broker::BILayer::Failure::`vftable';
    v20 = v11;
    throw (Broker::BILayer::Failure *)&pExceptionObject;
  }
  v12 = (__int64 *)a4[7];
  if ( v12 )
  {
    v13 = *v12;
    LOBYTE(v13) = v12 != a4;
    (*(void (__fastcall **)(__int64 *, __int64))(*v12 + 32))(v12, v13);
    a4[7] = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x18000de1c  push    rbp
0x18000de1e  push    rbx
0x18000de1f  push    rsi
0x18000de20  push    rdi
0x18000de21  push    r14
0x18000de23  lea     rbp, [rsp-37h]
0x18000de28  sub     rsp, 0A0h
0x18000de2f  mov     rax, cs:__security_cookie
0x18000de36  xor     rax, rsp
0x18000de39  mov     [rbp+57h+var_30], rax
0x18000de3d  mov     rsi, r9
0x18000de40  mov     r14d, r8d
0x18000de43  mov     rdi, rcx
0x18000de46  mov     [rbp+57h+var_50], rcx
0x18000de4a  mov     [rbp+57h+var_38], rdx
0x18000de4e  mov     [rbp+57h+var_48], r9
0x18000de52  mov     [rcx], rdx
0x18000de55  lea     rbx, [rcx+10h]
0x18000de59  mov     [rbp+57h+var_40], rbx
0x18000de5d  mov     qword ptr [rbx+38h], 0
0x18000de65  mov     rcx, [r9+38h]
0x18000de69  test    rcx, rcx
0x18000de6c  jz      short loc_18000DE80
0x18000de6e  mov     rax, [rcx]
0x18000de71  mov     rdx, rbx
0x18000de74  mov     rax, [rax]
0x18000de77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de7c  mov     [rbx+38h], rax
0x18000de80  mov     [rbp+57h+var_80], 0
0x18000de87  mov     [rbp+57h+var_7C], 0
0x18000de8e  lea     rax, [rbp+57h+var_7C]
0x18000de92  mov     [rsp+0C0h+var_98], rax
0x18000de97  mov     [rsp+0C0h+var_A0], 0
0x18000dea0  lea     r9, [rbp+57h+var_80]
0x18000dea4  xor     r8d, r8d
0x18000dea7  xor     edx, edx
0x18000dea9  lea     rcx, [rbp+57h+var_38]
0x18000dead  call    cs:__imp_NtQueryWnfStateData
0x18000deb3  mov     ebx, eax
0x18000deb5  mov     ecx, 80000000h
0x18000deba  add     eax, ecx
0x18000debc  test    ecx, eax
0x18000debe  jz      short loc_18000DF3E
0x18000dec0  lea     rcx, [rdi+8]
0x18000dec4  mov     [rsp+0C0h+var_88], 0
0x18000decc  mov     [rsp+0C0h+var_90], r14d
0x18000ded1  mov     [rsp+0C0h+var_98], 0
0x18000deda  mov     [rsp+0C0h+var_A0], rdi
0x18000dedf  lea     r9, ?WnfCallback@WnfNotification@BILayer@Broker@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; Broker::BILayer::WnfNotification::WnfCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x18000dee6  mov     r8d, [rbp+57h+var_80]
0x18000deea  mov     rdx, [rbp+57h+var_38]
0x18000deee  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x18000def4  mov     ebx, eax
0x18000def6  test    eax, eax
0x18000def8  js      loc_18000DFA2
0x18000defe  mov     rcx, [rsi+38h]
0x18000df02  test    rcx, rcx
0x18000df05  jz      short loc_18000DF21
0x18000df07  mov     rdx, [rcx]
0x18000df0a  mov     rax, [rdx+20h]
0x18000df0e  cmp     rcx, rsi
0x18000df11  setnz   dl
0x18000df14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df19  mov     qword ptr [rsi+38h], 0
0x18000df21  mov     rax, rdi
0x18000df24  mov     rcx, [rbp+57h+var_30]
0x18000df28  xor     rcx, rsp; StackCookie
0x18000df2b  call    __security_check_cookie
0x18000df30  add     rsp, 0A0h
0x18000df37  pop     r14
0x18000df39  pop     rdi
0x18000df3a  pop     rsi
0x18000df3b  pop     rbx
0x18000df3c  pop     rbp
0x18000df3d  retn
0x18000df3e  cmp     ebx, 0C0000023h
0x18000df44  jz      loc_18000DEC0
0x18000df4a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000df51  test    byte ptr [rcx+1Ch], 1
0x18000df55  jz      short loc_18000DF75
0x18000df57  cmp     byte ptr [rcx+19h], 2
0x18000df5b  jb      short loc_18000DF75
0x18000df5d  mov     edx, 25h ; '%'
0x18000df62  mov     r9d, ebx
0x18000df65  lea     r8, WPP_6d22d7a2e1813c043b7d2163e38154fa_Traceguids
0x18000df6c  mov     rcx, [rcx+10h]
0x18000df70  call    WPP_SF_d
0x18000df75  xorps   xmm0, xmm0
0x18000df78  movups  [rbp+57h+var_70], xmm0
0x18000df7c  mov     [rbp+57h+var_60], 6
0x18000df83  lea     rax, ??_7Failure@BILayer@Broker@@6B@; const Broker::BILayer::Failure::`vftable'
0x18000df8a  mov     [rbp+57h+pExceptionObject], rax
0x18000df8e  mov     [rbp+57h+var_58], ebx
0x18000df91  lea     rdx, _TI3?AUFailure@BILayer@Broker@@; pThrowInfo
0x18000df98  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18000df9c  call    _CxxThrowException_0
0x18000dfa2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dfa9  test    byte ptr [rcx+1Ch], 1
0x18000dfad  jz      short loc_18000DFCD
0x18000dfaf  cmp     byte ptr [rcx+19h], 2
0x18000dfb3  jb      short loc_18000DFCD
0x18000dfb5  mov     edx, 26h ; '&'
0x18000dfba  mov     r9d, ebx
0x18000dfbd  lea     r8, WPP_6d22d7a2e1813c043b7d2163e38154fa_Traceguids
0x18000dfc4  mov     rcx, [rcx+10h]
0x18000dfc8  call    WPP_SF_d
0x18000dfcd  xorps   xmm0, xmm0
0x18000dfd0  movups  [rbp+57h+var_70], xmm0
0x18000dfd4  mov     [rbp+57h+var_60], 6
0x18000dfdb  lea     rax, ??_7Failure@BILayer@Broker@@6B@; const Broker::BILayer::Failure::`vftable'
0x18000dfe2  mov     [rbp+57h+pExceptionObject], rax
0x18000dfe6  mov     [rbp+57h+var_58], ebx
0x18000dfe9  lea     rdx, _TI3?AUFailure@BILayer@Broker@@; pThrowInfo
0x18000dff0  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18000dff4  call    _CxxThrowException_0
```
