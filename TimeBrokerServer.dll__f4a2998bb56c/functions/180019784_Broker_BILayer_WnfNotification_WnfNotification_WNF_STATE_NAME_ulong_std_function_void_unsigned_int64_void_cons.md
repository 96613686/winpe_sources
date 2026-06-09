# Broker::BILayer::WnfNotification::WnfNotification(_WNF_STATE_NAME,ulong,std::function<void (unsigned __int64,void const *)>)

- ea: `0x180019784`
- end: `0x18001995a`
- name: `??0WnfNotification@BILayer@Broker@@QEAA@U_WNF_STATE_NAME@@KV?$function@$$A6AX_KPEBX@Z@std@@@Z`
- size: `470`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, int, __int64 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180012638`
- `0x180012924`

## callees

- `0x180003800`
- `0x180012dd0`
- `0x180013978`
- `0x180019784`
- `0x18001c010`

## import_xrefs

- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800198b6`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800198b6`
- `ntdll!NtQueryWnfStateData` at `0x180019815`
- `ntdll!NtQueryWnfStateData` at `0x180019815`

## pseudocode

```c
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
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_6d22d7a2e1813c043b7d2163e38154fa_Traceguids, v9);
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
        WPP_6d22d7a2e1813c043b7d2163e38154fa_Traceguids,
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
0x180019784  push    rbp
0x180019786  push    rbx
0x180019787  push    rsi
0x180019788  push    rdi
0x180019789  push    r14
0x18001978b  lea     rbp, [rsp-37h]
0x180019790  sub     rsp, 0A0h
0x180019797  mov     rax, cs:__security_cookie
0x18001979e  xor     rax, rsp
0x1800197a1  mov     [rbp+57h+var_30], rax
0x1800197a5  mov     rsi, r9
0x1800197a8  mov     r14d, r8d
0x1800197ab  mov     rdi, rcx
0x1800197ae  mov     [rbp+57h+var_50], rcx
0x1800197b2  mov     [rbp+57h+var_38], rdx
0x1800197b6  mov     [rbp+57h+var_48], r9
0x1800197ba  mov     [rcx], rdx
0x1800197bd  lea     rbx, [rcx+10h]
0x1800197c1  mov     [rbp+57h+var_40], rbx
0x1800197c5  mov     qword ptr [rbx+38h], 0
0x1800197cd  mov     rcx, [r9+38h]
0x1800197d1  test    rcx, rcx
0x1800197d4  jz      short loc_1800197E8
0x1800197d6  mov     rax, [rcx]
0x1800197d9  mov     rdx, rbx
0x1800197dc  mov     rax, [rax]
0x1800197df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800197e4  mov     [rbx+38h], rax
0x1800197e8  mov     [rbp+57h+var_80], 0
0x1800197ef  mov     [rbp+57h+var_7C], 0
0x1800197f6  lea     rax, [rbp+57h+var_7C]
0x1800197fa  mov     [rsp+0C0h+var_98], rax
0x1800197ff  mov     [rsp+0C0h+var_A0], 0
0x180019808  lea     r9, [rbp+57h+var_80]
0x18001980c  xor     r8d, r8d
0x18001980f  xor     edx, edx
0x180019811  lea     rcx, [rbp+57h+var_38]
0x180019815  call    cs:__imp_NtQueryWnfStateData
0x18001981b  mov     ebx, eax
0x18001981d  mov     ecx, 80000000h
0x180019822  add     eax, ecx
0x180019824  test    ecx, eax
0x180019826  jnz     short loc_180019888
0x180019828  cmp     ebx, 0C0000023h
0x18001982e  jz      short loc_180019888
0x180019830  mov     rcx, cs:WPP_GLOBAL_Control
0x180019837  test    byte ptr [rcx+1Ch], 1
0x18001983b  jz      short loc_18001985B
0x18001983d  cmp     byte ptr [rcx+19h], 2
0x180019841  jb      short loc_18001985B
0x180019843  mov     edx, 25h ; '%'
0x180019848  mov     r9d, ebx
0x18001984b  lea     r8, WPP_6d22d7a2e1813c043b7d2163e38154fa_Traceguids
0x180019852  mov     rcx, [rcx+10h]
0x180019856  call    WPP_SF_d
0x18001985b  xorps   xmm0, xmm0
0x18001985e  movups  [rbp+57h+var_70], xmm0
0x180019862  mov     [rbp+57h+var_60], 6
0x180019869  lea     rax, ??_7Failure@BILayer@Broker@@6B@; const Broker::BILayer::Failure::`vftable'
0x180019870  mov     [rbp+57h+pExceptionObject], rax
0x180019874  mov     [rbp+57h+var_58], ebx
0x180019877  lea     rdx, _TI3?AUFailure@BILayer@Broker@@; pThrowInfo
0x18001987e  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180019882  call    _CxxThrowException_0
0x180019888  lea     rcx, [rdi+8]
0x18001988c  mov     [rsp+0C0h+var_88], 0
0x180019894  mov     [rsp+0C0h+var_90], r14d
0x180019899  mov     [rsp+0C0h+var_98], 0
0x1800198a2  mov     [rsp+0C0h+var_A0], rdi
0x1800198a7  lea     r9, ?WnfCallback@WnfNotification@BILayer@Broker@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; Broker::BILayer::WnfNotification::WnfCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x1800198ae  mov     r8d, [rbp+57h+var_80]
0x1800198b2  mov     rdx, [rbp+57h+var_38]
0x1800198b6  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x1800198bc  mov     ebx, eax
0x1800198be  test    eax, eax
0x1800198c0  jns     short loc_18001991A
0x1800198c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800198c9  test    byte ptr [rcx+1Ch], 1
0x1800198cd  jz      short loc_1800198ED
0x1800198cf  cmp     byte ptr [rcx+19h], 2
0x1800198d3  jb      short loc_1800198ED
0x1800198d5  mov     edx, 26h ; '&'
0x1800198da  mov     r9d, eax
0x1800198dd  lea     r8, WPP_6d22d7a2e1813c043b7d2163e38154fa_Traceguids
0x1800198e4  mov     rcx, [rcx+10h]
0x1800198e8  call    WPP_SF_d
0x1800198ed  xorps   xmm0, xmm0
0x1800198f0  movups  [rbp+57h+var_70], xmm0
0x1800198f4  mov     [rbp+57h+var_60], 6
0x1800198fb  lea     rax, ??_7Failure@BILayer@Broker@@6B@; const Broker::BILayer::Failure::`vftable'
0x180019902  mov     [rbp+57h+pExceptionObject], rax
0x180019906  mov     [rbp+57h+var_58], ebx
0x180019909  lea     rdx, _TI3?AUFailure@BILayer@Broker@@; pThrowInfo
0x180019910  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180019914  call    _CxxThrowException_0
0x18001991a  mov     rcx, [rsi+38h]
0x18001991e  test    rcx, rcx
0x180019921  jz      short loc_18001993D
0x180019923  mov     rdx, [rcx]
0x180019926  mov     rax, [rdx+20h]
0x18001992a  cmp     rcx, rsi
0x18001992d  setnz   dl
0x180019930  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019935  mov     qword ptr [rsi+38h], 0
0x18001993d  mov     rax, rdi
0x180019940  mov     rcx, [rbp+57h+var_30]
0x180019944  xor     rcx, rsp; StackCookie
0x180019947  call    __security_check_cookie
0x18001994c  add     rsp, 0A0h
0x180019953  pop     r14
0x180019955  pop     rdi
0x180019956  pop     rsi
0x180019957  pop     rbx
0x180019958  pop     rbp
0x180019959  retn
```
