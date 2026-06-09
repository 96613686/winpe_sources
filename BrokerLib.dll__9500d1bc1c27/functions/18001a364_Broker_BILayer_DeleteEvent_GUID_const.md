# Broker::BILayer::DeleteEvent(_GUID const &)

- ea: `0x18001a364`
- end: `0x18001a414`
- name: `?DeleteEvent@BILayer@Broker@@YAXAEBU_GUID@@@Z`
- size: `176`
- prototype: `void __fastcall(Broker::BILayer *__hidden this, const struct _GUID *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180018358`
- `0x1800187b8`

## callees

- `0x180009e94`
- `0x18000e4f0`
- `0x1800165da`
- `0x18001a364`

## import_xrefs

- `api-ms-win-core-bicltapi-l1-1-6!BiDeleteEvent` at `0x18001a371`
- `api-ms-win-core-bicltapi-l1-1-6!BiDeleteEvent` at `0x18001a371`

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
    WPP_SF__guid_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_6d22d7a2e1813c043b7d2163e38154fa_Traceguids, this, v3);
    v5 = WPP_GLOBAL_Control;
  }
  if ( v4 < 0 )
  {
    if ( (*((_BYTE *)v5 + 28) & 1) != 0 && *((_BYTE *)v5 + 25) >= 2u )
      WPP_SF_d(v5[2], 13, &WPP_6d22d7a2e1813c043b7d2163e38154fa_Traceguids, (unsigned int)v4);
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
0x18001a364  mov     [rsp+arg_0], rbx
0x18001a369  push    rdi
0x18001a36a  sub     rsp, 60h
0x18001a36e  mov     rdi, rcx
0x18001a371  call    cs:__imp_BiDeleteEvent
0x18001a377  mov     ebx, eax
0x18001a379  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a380  test    byte ptr [rcx+1Ch], 1
0x18001a384  jz      short loc_18001A3AF
0x18001a386  cmp     byte ptr [rcx+19h], 5
0x18001a38a  jb      short loc_18001A3AF
0x18001a38c  mov     rcx, [rcx+10h]
0x18001a390  lea     r8, WPP_6d22d7a2e1813c043b7d2163e38154fa_Traceguids
0x18001a397  mov     edx, 0Ch
0x18001a39c  mov     [rsp+68h+var_48], eax
0x18001a3a0  mov     r9, rdi
0x18001a3a3  call    WPP_SF__guid_d
0x18001a3a8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a3af  test    ebx, ebx
0x18001a3b1  jns     short loc_18001A409
0x18001a3b3  test    byte ptr [rcx+1Ch], 1
0x18001a3b7  jz      short loc_18001A3D7
0x18001a3b9  cmp     byte ptr [rcx+19h], 2
0x18001a3bd  jb      short loc_18001A3D7
0x18001a3bf  mov     rcx, [rcx+10h]
0x18001a3c3  lea     r8, WPP_6d22d7a2e1813c043b7d2163e38154fa_Traceguids
0x18001a3ca  mov     edx, 0Dh
0x18001a3cf  mov     r9d, ebx
0x18001a3d2  call    WPP_SF_d
0x18001a3d7  xorps   xmm0, xmm0
0x18001a3da  mov     [rsp+68h+var_20], 6
0x18001a3e2  lea     rax, ??_7Failure@BILayer@Broker@@6B@; const Broker::BILayer::Failure::`vftable'
0x18001a3e9  mov     [rsp+68h+var_18], ebx
0x18001a3ed  lea     rdx, _TI3?AUFailure@BILayer@Broker@@; pThrowInfo
0x18001a3f4  mov     [rsp+68h+pExceptionObject], rax
0x18001a3f9  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18001a3fe  movups  [rsp+68h+var_30], xmm0
0x18001a403  call    _CxxThrowException_0
0x18001a409  mov     rbx, [rsp+68h+arg_0]
0x18001a40e  add     rsp, 60h
0x18001a412  pop     rdi
0x18001a413  retn
```
