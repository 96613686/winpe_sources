# Broker::BILayer::SignalEventConditional(_GUID const &,void const *,ulong,uchar,_GUID const *)

- ea: `0x180014398`
- end: `0x18001446d`
- name: `?SignalEventConditional@BILayer@Broker@@YAXAEBU_GUID@@PEBXKEPEBU3@@Z`
- size: `213`
- prototype: `void __fastcall(Broker::BILayer *__hidden this, const struct _GUID *, const void *, unsigned int, unsigned __int8, const struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180005724`

## callees

- `0x180009e94`
- `0x18000e4f0`
- `0x180014398`
- `0x1800165da`

## import_xrefs

- `api-ms-win-core-bicltapi-l1-1-6!BiSignalEvent` at `0x1800143c5`
- `api-ms-win-core-bicltapi-l1-1-6!BiSignalEvent` at `0x1800143c5`

## pseudocode

```c
void __fastcall Broker::BILayer::SignalEventConditional(
        Broker::BILayer *this,
        const struct _GUID *a2,
        const void *a3,
        char a4,
        __int64 a5)
{
  int v5; // edi
  int v7; // ebx
  _QWORD *v8; // rcx
  void **pExceptionObject; // [rsp+30h] [rbp-38h] BYREF
  __int128 v10; // [rsp+38h] [rbp-30h]
  int v11; // [rsp+48h] [rbp-20h]
  int v12; // [rsp+50h] [rbp-18h]
  char v13; // [rsp+88h] [rbp+20h] BYREF

  v13 = a4;
  v5 = (int)a3;
  v7 = BiSignalEvent(this, &v13, a5, a2, (_DWORD)a3);
  v8 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF__guid_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_6d22d7a2e1813c043b7d2163e38154fa_Traceguids, this, v5);
    v8 = WPP_GLOBAL_Control;
  }
  if ( v7 < 0 )
  {
    if ( (*((_BYTE *)v8 + 28) & 1) != 0 && *((_BYTE *)v8 + 25) >= 2u )
      WPP_SF_d(v8[2], 31, &WPP_6d22d7a2e1813c043b7d2163e38154fa_Traceguids, (unsigned int)v7);
    v11 = 6;
    v12 = v7;
    pExceptionObject = &Broker::BILayer::Failure::`vftable';
    v10 = 0;
    throw (Broker::BILayer::Failure *)&pExceptionObject;
  }
}

```

## disassembly

```asm
0x180014398  mov     rax, rsp
0x18001439b  mov     [rax+8], rbx
0x18001439f  mov     [rax+10h], rsi
0x1800143a3  mov     [rax+20h], r9b
0x1800143a7  push    rdi
0x1800143a8  sub     rsp, 60h
0x1800143ac  mov     edi, r8d
0x1800143af  mov     [rax-48h], r8d
0x1800143b3  mov     r8, [rsp+68h+arg_20]
0x1800143bb  mov     r9, rdx
0x1800143be  lea     rdx, [rax+20h]
0x1800143c2  mov     rsi, rcx
0x1800143c5  call    cs:__imp_BiSignalEvent
0x1800143cb  mov     ebx, eax
0x1800143cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800143d4  test    byte ptr [rcx+1Ch], 1
0x1800143d8  jz      short loc_180014403
0x1800143da  cmp     byte ptr [rcx+19h], 5
0x1800143de  jb      short loc_180014403
0x1800143e0  mov     rcx, [rcx+10h]
0x1800143e4  lea     r8, WPP_6d22d7a2e1813c043b7d2163e38154fa_Traceguids
0x1800143eb  mov     edx, 1Eh
0x1800143f0  mov     [rsp+68h+var_48], edi
0x1800143f4  mov     r9, rsi
0x1800143f7  call    WPP_SF__guid_d
0x1800143fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180014403  test    ebx, ebx
0x180014405  jns     short loc_18001445D
0x180014407  test    byte ptr [rcx+1Ch], 1
0x18001440b  jz      short loc_18001442B
0x18001440d  cmp     byte ptr [rcx+19h], 2
0x180014411  jb      short loc_18001442B
0x180014413  mov     rcx, [rcx+10h]
0x180014417  lea     r8, WPP_6d22d7a2e1813c043b7d2163e38154fa_Traceguids
0x18001441e  mov     edx, 1Fh
0x180014423  mov     r9d, ebx
0x180014426  call    WPP_SF_d
0x18001442b  xorps   xmm0, xmm0
0x18001442e  mov     [rsp+68h+var_20], 6
0x180014436  lea     rax, ??_7Failure@BILayer@Broker@@6B@; const Broker::BILayer::Failure::`vftable'
0x18001443d  mov     [rsp+68h+var_18], ebx
0x180014441  lea     rdx, _TI3?AUFailure@BILayer@Broker@@; pThrowInfo
0x180014448  mov     [rsp+68h+pExceptionObject], rax
0x18001444d  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180014452  movups  [rsp+68h+var_30], xmm0
0x180014457  call    _CxxThrowException_0
0x18001445d  mov     rbx, [rsp+68h+arg_0]
0x180014462  mov     rsi, [rsp+68h+arg_8]
0x180014467  add     rsp, 60h
0x18001446b  pop     rdi
0x18001446c  retn
```
