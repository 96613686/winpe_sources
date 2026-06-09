# EvtAdapterPreProcessDirectOidRequest

- ea: `0x140029d60`
- end: `0x140029f15`
- name: `EvtAdapterPreProcessDirectOidRequest`
- size: `437`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x140005d40`
- `0x14000c778`
- `0x140029d60`
- `0x1400cfae0`
- `0x1400cfd04`
- `0x1400d04a8`
- `0x1400dfd40`

## string_xrefs

- `0x140029e15`: `PM_REMOVE_WOL_PATTERN`
- `0x140029e1c`: `Remove`

## pseudocode

```c
__int64 __fastcall EvtAdapterPreProcessDirectOidRequest(__int64 a1, __int64 a2, void *a3)
{
  __int64 v5; // rdi
  int v6; // eax
  int v7; // edx
  __int64 result; // rax
  int v9; // eax
  int v10; // edx

  v5 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01031 + 1616))(
         WdfDriverGlobals,
         a1,
         off_14010EB80);
  v6 = *(_DWORD *)(a2 + 4);
  if ( v6 )
  {
    if ( v6 == 1 )
    {
      v7 = *(_DWORD *)(a2 + 32);
      switch ( v7 )
      {
        case -50265846:
        case -50265845:
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_SS(WPP_GLOBAL_Control->DeviceExtension, v7, (unsigned int)L"Remove", -50265846);
          ((void (__fastcall *)(PNET_DRIVER_GLOBALS, _QWORD, __int64, void *))qword_140110CA8)(
            NetDriverGlobals,
            *(_QWORD *)(v5 + 8),
            a2,
            a3);
          return 259;
        case -50265843:
          WxAdapter::HandleProtocolOffloadAdditionOIDRequest((WxAdapter *)v5, (struct _NDIS_OID_REQUEST *)a2, a3);
          return 259;
        case -50265841:
          WxAdapter::HandleProtocolOffloadRemovalOIDRequest((WxAdapter *)v5, (struct _NDIS_OID_REQUEST *)a2, a3);
          return 259;
      }
    }
  }
  else
  {
    v9 = *(_DWORD *)(a2 + 32);
    if ( v9 == -50265847 || v9 == -50265842 )
      __int2c();
  }
  *(_DWORD *)(a2 + 8) = *(unsigned __int16 *)(v5 + 540);
  result = CAdapter::HandleOidRequest(*(CAdapter **)(v5 + 528), (struct _NDIS_OID_REQUEST *)a2, 1u);
  if ( (_DWORD)result == -1073741637 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v10,
        1,
        38,
        (__int64)WPP_3742f7b8aa593665a28f1ce7634f5781_Traceguids,
        *(_DWORD *)(a2 + 32));
    }
    return ((__int64 (__fastcall *)(PNET_DRIVER_GLOBALS, _QWORD, __int64, void *))qword_140110E68)(
             NetDriverGlobals,
             *(_QWORD *)(v5 + 8),
             a2,
             a3);
  }
  return result;
}

```

## disassembly

```asm
0x140029d60  mov     [rsp+arg_0], rbx
0x140029d65  mov     [rsp+arg_8], rsi
0x140029d6a  push    rdi
0x140029d6b  sub     rsp, 40h
0x140029d6f  mov     rax, cs:WdfFunctions_01031
0x140029d76  mov     rbx, rdx
0x140029d79  mov     rsi, r8
0x140029d7c  mov     rdx, rcx
0x140029d7f  mov     r8, cs:off_14010EB80
0x140029d86  mov     rcx, cs:WdfDriverGlobals
0x140029d8d  mov     rax, [rax+650h]
0x140029d94  call    _guard_dispatch_icall
0x140029d99  mov     rdi, rax
0x140029d9c  mov     eax, [rbx+4]
0x140029d9f  test    eax, eax
0x140029da1  jz      loc_140029E72
0x140029da7  cmp     eax, 1
0x140029daa  jnz     loc_140029E85
0x140029db0  mov     edx, [rbx+20h]
0x140029db3  mov     r9d, 0FD01010Ah
0x140029db9  cmp     edx, r9d
0x140029dbc  jz      short loc_140029E02
0x140029dbe  cmp     edx, 0FD01010Bh
0x140029dc4  jz      short loc_140029E02
0x140029dc6  cmp     edx, 0FD01010Dh
0x140029dcc  jz      short loc_140029DEA
0x140029dce  cmp     edx, 0FD01010Fh
0x140029dd4  jnz     loc_140029E85
0x140029dda  mov     r8, rsi; void *
0x140029ddd  mov     rdx, rbx; struct _NDIS_OID_REQUEST *
0x140029de0  mov     rcx, rdi; this
0x140029de3  call    ?HandleProtocolOffloadRemovalOIDRequest@WxAdapter@@AEAAXPEAU_NDIS_OID_REQUEST@@PEAX@Z; WxAdapter::HandleProtocolOffloadRemovalOIDRequest(_NDIS_OID_REQUEST *,void *)
0x140029de8  jmp     short loc_140029DF8
0x140029dea  mov     r8, rsi; void *
0x140029ded  mov     rdx, rbx; struct _NDIS_OID_REQUEST *
0x140029df0  mov     rcx, rdi; this
0x140029df3  call    ?HandleProtocolOffloadAdditionOIDRequest@WxAdapter@@AEAAXPEAU_NDIS_OID_REQUEST@@PEAX@Z; WxAdapter::HandleProtocolOffloadAdditionOIDRequest(_NDIS_OID_REQUEST *,void *)
0x140029df8  mov     eax, 103h
0x140029dfd  jmp     loc_140029F04
0x140029e02  lea     rax, WPP_RECORDER_INITIALIZED
0x140029e09  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140029e10  jz      short loc_140029E53
0x140029e12  cmp     edx, r9d
0x140029e15  lea     rax, aPmRemoveWolPat; "PM_REMOVE_WOL_PATTERN"
0x140029e1c  lea     r8, aRemove; "Remove"
0x140029e23  lea     rcx, aPmAddWolPatter; "PM_ADD_WOL_PATTERN"
0x140029e2a  cmovnz  rcx, rax
0x140029e2e  lea     rax, aAdd; "Add"
0x140029e35  mov     [rsp+48h+var_18], rcx
0x140029e3a  cmovnz  rax, r8
0x140029e3e  mov     rcx, cs:WPP_GLOBAL_Control
0x140029e45  mov     [rsp+48h+var_20], rax
0x140029e4a  mov     rcx, [rcx+40h]
0x140029e4e  call    WPP_RECORDER_SF_SS
0x140029e53  mov     rax, cs:qword_140110CA8
0x140029e5a  mov     r9, rsi
0x140029e5d  mov     rdx, [rdi+8]
0x140029e61  mov     r8, rbx
0x140029e64  mov     rcx, cs:NetDriverGlobals
0x140029e6b  call    _guard_dispatch_icall
0x140029e70  jmp     short loc_140029DF8
0x140029e72  mov     eax, [rbx+20h]
0x140029e75  cmp     eax, 0FD010109h
0x140029e7a  jz      short loc_140029E83
0x140029e7c  cmp     eax, 0FD01010Eh
0x140029e81  jnz     short loc_140029E85
0x140029e83  int     2Ch; Windows NT - assertion failure
0x140029e85  movzx   eax, word ptr [rdi+21Ch]
0x140029e8c  mov     r8b, 1; unsigned __int8
0x140029e8f  mov     [rbx+8], eax
0x140029e92  mov     rdx, rbx; struct _NDIS_OID_REQUEST *
0x140029e95  mov     rcx, [rdi+210h]; this
0x140029e9c  call    ?HandleOidRequest@CAdapter@@QEAAHPEAU_NDIS_OID_REQUEST@@E@Z; CAdapter::HandleOidRequest(_NDIS_OID_REQUEST *,uchar)
0x140029ea1  cmp     eax, 0C00000BBh
0x140029ea6  jnz     short loc_140029F04
0x140029ea8  lea     rax, WPP_RECORDER_INITIALIZED
0x140029eaf  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140029eb6  jz      short loc_140029EE7
0x140029eb8  mov     eax, [rbx+20h]
0x140029ebb  mov     r9d, 26h ; '&'
0x140029ec1  mov     rcx, cs:WPP_GLOBAL_Control
0x140029ec8  mov     dl, 2
0x140029eca  mov     dword ptr [rsp+48h+var_20], eax
0x140029ece  lea     rax, WPP_3742f7b8aa593665a28f1ce7634f5781_Traceguids
0x140029ed5  mov     [rsp+48h+var_28], rax
0x140029eda  lea     r8d, [r9-25h]
0x140029ede  mov     rcx, [rcx+40h]
0x140029ee2  call    WPP_RECORDER_SF_d
0x140029ee7  mov     rax, cs:qword_140110E68
0x140029eee  mov     r9, rsi
0x140029ef1  mov     rdx, [rdi+8]
0x140029ef5  mov     r8, rbx
0x140029ef8  mov     rcx, cs:NetDriverGlobals
0x140029eff  call    _guard_dispatch_icall
0x140029f04  mov     rbx, [rsp+48h+arg_0]
0x140029f09  mov     rsi, [rsp+48h+arg_8]
0x140029f0e  add     rsp, 40h
0x140029f12  pop     rdi
0x140029f13  retn
```
