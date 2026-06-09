# Broker::BILayer::SignalEventEx(_GUID const &,void const *,ulong,_BI_ACTIVATION_STATUS *,_GUID const *,_GUID const *)

- ea: `0x1800142ac`
- end: `0x18001438f`
- name: `?SignalEventEx@BILayer@Broker@@YAXAEBU_GUID@@PEBXKPEAW4_BI_ACTIVATION_STATUS@@PEBU3@3@Z`
- size: `227`
- prototype: `void __fastcall(Broker::BILayer *__hidden this, const struct _GUID *, const void *, unsigned int, enum _BI_ACTIVATION_STATUS *, const struct _GUID *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180005724`

## callees

- `0x180009e94`
- `0x18000e4f0`
- `0x1800142ac`
- `0x1800165da`

## import_xrefs

- `api-ms-win-core-bicltapi-l1-1-6!BiSignalTriggerEventEx` at `0x1800142e7`
- `api-ms-win-core-bicltapi-l1-1-6!BiSignalTriggerEventEx` at `0x1800142e7`

## pseudocode

```c
void __fastcall Broker::BILayer::SignalEventEx(
        Broker::BILayer *this,
        const struct _GUID *a2,
        const void *a3,
        __int64 a4,
        enum _BI_ACTIVATION_STATUS *a5,
        const struct _GUID *a6)
{
  int v6; // edi
  int v8; // ebx
  _QWORD *v9; // rcx
  void **pExceptionObject; // [rsp+30h] [rbp-38h] BYREF
  __int128 v11; // [rsp+38h] [rbp-30h]
  int v12; // [rsp+48h] [rbp-20h]
  int v13; // [rsp+50h] [rbp-18h]

  v6 = (int)a3;
  v8 = BiSignalTriggerEventEx(a4, this, a5, a2, (_DWORD)a3, a6);
  v9 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF__guid_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_6d22d7a2e1813c043b7d2163e38154fa_Traceguids, this, v6);
    v9 = WPP_GLOBAL_Control;
  }
  if ( v8 < 0 )
  {
    if ( (*((_BYTE *)v9 + 28) & 1) != 0 && *((_BYTE *)v9 + 25) >= 2u )
      WPP_SF_d(v9[2], 21, &WPP_6d22d7a2e1813c043b7d2163e38154fa_Traceguids, (unsigned int)v8);
    v12 = 6;
    v13 = v8;
    pExceptionObject = &Broker::BILayer::Failure::`vftable';
    v11 = 0;
    throw (Broker::BILayer::Failure *)&pExceptionObject;
  }
}

```

## disassembly

```asm
0x1800142ac  mov     [rsp+arg_0], rbx
0x1800142b1  mov     [rsp+arg_8], rsi
0x1800142b6  push    rdi
0x1800142b7  sub     rsp, 60h
0x1800142bb  mov     rax, [rsp+68h+arg_28]
0x1800142c3  mov     r10, r9
0x1800142c6  mov     [rsp+68h+var_40], rax
0x1800142cb  mov     r9, rdx
0x1800142ce  mov     [rsp+68h+var_48], r8d
0x1800142d3  mov     edi, r8d
0x1800142d6  mov     r8, [rsp+68h+arg_20]
0x1800142de  mov     rsi, rcx
0x1800142e1  mov     rdx, rcx
0x1800142e4  mov     rcx, r10
0x1800142e7  call    cs:__imp_BiSignalTriggerEventEx
0x1800142ed  mov     ebx, eax
0x1800142ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800142f6  test    byte ptr [rcx+1Ch], 1
0x1800142fa  jz      short loc_180014325
0x1800142fc  cmp     byte ptr [rcx+19h], 5
0x180014300  jb      short loc_180014325
0x180014302  mov     rcx, [rcx+10h]
0x180014306  lea     r8, WPP_6d22d7a2e1813c043b7d2163e38154fa_Traceguids
0x18001430d  mov     edx, 14h
0x180014312  mov     [rsp+68h+var_48], edi
0x180014316  mov     r9, rsi
0x180014319  call    WPP_SF__guid_d
0x18001431e  mov     rcx, cs:WPP_GLOBAL_Control
0x180014325  test    ebx, ebx
0x180014327  jns     short loc_18001437F
0x180014329  test    byte ptr [rcx+1Ch], 1
0x18001432d  jz      short loc_18001434D
0x18001432f  cmp     byte ptr [rcx+19h], 2
0x180014333  jb      short loc_18001434D
0x180014335  mov     rcx, [rcx+10h]
0x180014339  lea     r8, WPP_6d22d7a2e1813c043b7d2163e38154fa_Traceguids
0x180014340  mov     edx, 15h
0x180014345  mov     r9d, ebx
0x180014348  call    WPP_SF_d
0x18001434d  xorps   xmm0, xmm0
0x180014350  mov     [rsp+68h+var_20], 6
0x180014358  lea     rax, ??_7Failure@BILayer@Broker@@6B@; const Broker::BILayer::Failure::`vftable'
0x18001435f  mov     [rsp+68h+var_18], ebx
0x180014363  lea     rdx, _TI3?AUFailure@BILayer@Broker@@; pThrowInfo
0x18001436a  mov     [rsp+68h+pExceptionObject], rax
0x18001436f  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180014374  movups  [rsp+68h+var_30], xmm0
0x180014379  call    _CxxThrowException_0
0x18001437f  mov     rbx, [rsp+68h+arg_0]
0x180014384  mov     rsi, [rsp+68h+arg_8]
0x180014389  add     rsp, 60h
0x18001438d  pop     rdi
0x18001438e  retn
```
