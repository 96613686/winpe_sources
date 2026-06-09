# Broker::BILayer::DeleteEvent(_GUID const &)

- ea: `0x180011594`
- end: `0x180011644`
- name: `?DeleteEvent@BILayer@Broker@@YAXAEBU_GUID@@@Z`
- size: `176`
- prototype: `void __fastcall(Broker::BILayer *__hidden this, const struct _GUID *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180008c70`
- `0x18000a100`

## callees

- `0x180003800`
- `0x18000a0b0`
- `0x180011594`
- `0x180013978`

## import_xrefs

- `api-ms-win-core-bicltapi-l1-1-6!BiDeleteEvent` at `0x1800115a1`
- `api-ms-win-core-bicltapi-l1-1-6!BiDeleteEvent` at `0x1800115a1`

## pseudocode

```c
void __fastcall Broker::BILayer::DeleteEvent(Broker::BILayer *this, const struct _GUID *a2)
{
  int v3; // eax
  int v4; // ebx
  _QWORD *v5; // rcx
  void **pExceptionObject; // [rsp+30h] [rbp-38h] BYREF
  __int128 v7; // [rsp+38h] [rbp-30h]
  int v8; // [rsp+48h] [rbp-20h]
  int v9; // [rsp+50h] [rbp-18h]

  v3 = BiDeleteEvent(this, a2);
  v4 = v3;
  v5 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF__guid_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_6d22d7a2e1813c043b7d2163e38154fa_Traceguids, this, v3);
    v5 = WPP_GLOBAL_Control;
  }
  if ( v4 < 0 )
  {
    if ( (*((_BYTE *)v5 + 28) & 1) != 0 && *((_BYTE *)v5 + 25) >= 2u )
      WPP_SF_d(v5[2], 13, WPP_6d22d7a2e1813c043b7d2163e38154fa_Traceguids, (unsigned int)v4);
    v8 = 6;
    v9 = v4;
    pExceptionObject = &Broker::BILayer::Failure::`vftable';
    v7 = 0;
    throw (Broker::BILayer::Failure *)&pExceptionObject;
  }
}

```

## disassembly

```asm
0x180011594  mov     [rsp+arg_0], rbx
0x180011599  push    rdi
0x18001159a  sub     rsp, 60h
0x18001159e  mov     rdi, rcx
0x1800115a1  call    cs:__imp_BiDeleteEvent
0x1800115a7  mov     ebx, eax
0x1800115a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800115b0  test    byte ptr [rcx+1Ch], 1
0x1800115b4  jz      short loc_1800115DF
0x1800115b6  cmp     byte ptr [rcx+19h], 5
0x1800115ba  jb      short loc_1800115DF
0x1800115bc  mov     rcx, [rcx+10h]
0x1800115c0  lea     r8, WPP_6d22d7a2e1813c043b7d2163e38154fa_Traceguids
0x1800115c7  mov     edx, 0Ch
0x1800115cc  mov     [rsp+68h+var_48], eax
0x1800115d0  mov     r9, rdi
0x1800115d3  call    WPP_SF__guid_d
0x1800115d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800115df  test    ebx, ebx
0x1800115e1  jns     short loc_180011639
0x1800115e3  test    byte ptr [rcx+1Ch], 1
0x1800115e7  jz      short loc_180011607
0x1800115e9  cmp     byte ptr [rcx+19h], 2
0x1800115ed  jb      short loc_180011607
0x1800115ef  mov     rcx, [rcx+10h]
0x1800115f3  lea     r8, WPP_6d22d7a2e1813c043b7d2163e38154fa_Traceguids
0x1800115fa  mov     edx, 0Dh
0x1800115ff  mov     r9d, ebx
0x180011602  call    WPP_SF_d
0x180011607  xorps   xmm0, xmm0
0x18001160a  mov     [rsp+68h+var_20], 6
0x180011612  lea     rax, ??_7Failure@BILayer@Broker@@6B@; const Broker::BILayer::Failure::`vftable'
0x180011619  mov     [rsp+68h+var_18], ebx
0x18001161d  lea     rdx, _TI3?AUFailure@BILayer@Broker@@; pThrowInfo
0x180011624  mov     [rsp+68h+pExceptionObject], rax
0x180011629  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18001162e  movups  [rsp+68h+var_30], xmm0
0x180011633  call    _CxxThrowException_0
0x180011639  mov     rbx, [rsp+68h+arg_0]
0x18001163e  add     rsp, 60h
0x180011642  pop     rdi
0x180011643  retn
```
