# EvtAdapterPreProcessOidRequest

- ea: `0x140005a30`
- end: `0x140005bea`
- name: `EvtAdapterPreProcessOidRequest`
- size: `442`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x140005a30`
- `0x140005d40`
- `0x14000c778`
- `0x1400cfae0`
- `0x1400cfd04`
- `0x1400d02ac`
- `0x1400d04a8`
- `0x1400dfd40`

## import_xrefs

- `NDIS!NdisConvertNtStatusToNdisStatus` at `0x140005bbe`
- `NDIS!NdisConvertNtStatusToNdisStatus` at `0x140005bbe`

## string_xrefs

- `0x140005ae1`: `PM_REMOVE_WOL_PATTERN`
- `0x140005ae8`: `Remove`

## pseudocode

```c
void __fastcall EvtAdapterPreProcessOidRequest(__int64 a1, __int64 a2, void *a3)
{
  __int64 v5; // rdi
  int v6; // eax
  int v7; // edx
  int v8; // eax
  unsigned int v9; // eax
  int v10; // edx
  int v11; // eax

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
          goto LABEL_17;
        case -50265843:
          WxAdapter::HandleProtocolOffloadAdditionOIDRequest((WxAdapter *)v5, (struct _NDIS_OID_REQUEST *)a2, a3);
          return;
        case -50265841:
          WxAdapter::HandleProtocolOffloadRemovalOIDRequest((WxAdapter *)v5, (struct _NDIS_OID_REQUEST *)a2, a3);
          return;
      }
    }
  }
  else
  {
    v8 = *(_DWORD *)(a2 + 32);
    if ( v8 == -50265847 || v8 == -50265842 )
      __int2c();
  }
  *(_DWORD *)(a2 + 8) = *(unsigned __int16 *)(v5 + 540);
  v9 = CAdapter::HandleOidRequest(*(CAdapter **)(v5 + 528), (struct _NDIS_OID_REQUEST *)a2, 0);
  if ( v9 == -1073741637 )
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
LABEL_17:
    ((void (__fastcall *)(PNET_DRIVER_GLOBALS, _QWORD, __int64, void *))qword_140110CA8)(
      NetDriverGlobals,
      *(_QWORD *)(v5 + 8),
      a2,
      a3);
    return;
  }
  if ( v9 != 259 )
  {
    v11 = NdisConvertNtStatusToNdisStatus(v9);
    WxNdisMOidRequestComplete(
      *(NDIS_HANDLE *)(v5 + 32),
      (struct _NDIS_OID_REQUEST *)a2,
      v11,
      (const struct CPort *)(v5 + 392));
  }
}

```

## disassembly

```asm
0x140005a30  push    rbx
0x140005a32  push    rbp
0x140005a33  push    rsi
0x140005a34  push    rdi
0x140005a35  sub     rsp, 48h
0x140005a39  mov     rax, cs:WdfFunctions_01031
0x140005a40  mov     rbx, rdx
0x140005a43  mov     rsi, r8
0x140005a46  mov     rdx, rcx
0x140005a49  mov     r8, cs:off_14010EB80
0x140005a50  mov     rcx, cs:WdfDriverGlobals
0x140005a57  mov     rax, [rax+650h]
0x140005a5e  call    _guard_dispatch_icall
0x140005a63  mov     rdi, rax
0x140005a66  mov     eax, [rbx+4]
0x140005a69  test    eax, eax
0x140005a6b  jz      loc_140005B21
0x140005a71  cmp     eax, 1
0x140005a74  jnz     loc_140005B34
0x140005a7a  mov     edx, [rbx+20h]
0x140005a7d  mov     r9d, 0FD01010Ah
0x140005a83  cmp     edx, r9d
0x140005a86  jz      short loc_140005ACA
0x140005a88  cmp     edx, 0FD01010Bh
0x140005a8e  jz      short loc_140005ACA
0x140005a90  cmp     edx, 0FD01010Dh
0x140005a96  jz      short loc_140005AB7
0x140005a98  cmp     edx, 0FD01010Fh
0x140005a9e  jnz     loc_140005B34
0x140005aa4  mov     r8, rsi; void *
0x140005aa7  mov     rdx, rbx; struct _NDIS_OID_REQUEST *
0x140005aaa  mov     rcx, rdi; this
0x140005aad  call    ?HandleProtocolOffloadRemovalOIDRequest@WxAdapter@@AEAAXPEAU_NDIS_OID_REQUEST@@PEAX@Z; WxAdapter::HandleProtocolOffloadRemovalOIDRequest(_NDIS_OID_REQUEST *,void *)
0x140005ab2  jmp     loc_140005BE0
0x140005ab7  mov     r8, rsi; void *
0x140005aba  mov     rdx, rbx; struct _NDIS_OID_REQUEST *
0x140005abd  mov     rcx, rdi; this
0x140005ac0  call    ?HandleProtocolOffloadAdditionOIDRequest@WxAdapter@@AEAAXPEAU_NDIS_OID_REQUEST@@PEAX@Z; WxAdapter::HandleProtocolOffloadAdditionOIDRequest(_NDIS_OID_REQUEST *,void *)
0x140005ac5  jmp     loc_140005BE0
0x140005aca  lea     rax, WPP_RECORDER_INITIALIZED
0x140005ad1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140005ad8  jz      loc_140005B96
0x140005ade  cmp     edx, r9d
0x140005ae1  lea     rax, aPmRemoveWolPat; "PM_REMOVE_WOL_PATTERN"
0x140005ae8  lea     r8, aRemove; "Remove"
0x140005aef  lea     rcx, aPmAddWolPatter; "PM_ADD_WOL_PATTERN"
0x140005af6  cmovnz  rcx, rax
0x140005afa  lea     rax, aAdd; "Add"
0x140005b01  mov     [rsp+68h+var_38], rcx
0x140005b06  cmovnz  rax, r8
0x140005b0a  mov     rcx, cs:WPP_GLOBAL_Control
0x140005b11  mov     [rsp+68h+var_40], rax
0x140005b16  mov     rcx, [rcx+40h]
0x140005b1a  call    WPP_RECORDER_SF_SS
0x140005b1f  jmp     short loc_140005B96
0x140005b21  mov     eax, [rbx+20h]
0x140005b24  cmp     eax, 0FD010109h
0x140005b29  jz      short loc_140005B32
0x140005b2b  cmp     eax, 0FD01010Eh
0x140005b30  jnz     short loc_140005B34
0x140005b32  int     2Ch; Windows NT - assertion failure
0x140005b34  movzx   eax, word ptr [rdi+21Ch]
0x140005b3b  xor     r8d, r8d; unsigned __int8
0x140005b3e  mov     [rbx+8], eax
0x140005b41  mov     rdx, rbx; struct _NDIS_OID_REQUEST *
0x140005b44  mov     rcx, [rdi+210h]; this
0x140005b4b  call    ?HandleOidRequest@CAdapter@@QEAAHPEAU_NDIS_OID_REQUEST@@E@Z; CAdapter::HandleOidRequest(_NDIS_OID_REQUEST *,uchar)
0x140005b50  cmp     eax, 0C00000BBh
0x140005b55  jnz     short loc_140005BB5
0x140005b57  lea     rax, WPP_RECORDER_INITIALIZED
0x140005b5e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140005b65  jz      short loc_140005B96
0x140005b67  mov     eax, [rbx+20h]
0x140005b6a  mov     r9d, 26h ; '&'
0x140005b70  mov     rcx, cs:WPP_GLOBAL_Control
0x140005b77  mov     dl, 2
0x140005b79  mov     dword ptr [rsp+68h+var_40], eax
0x140005b7d  lea     rax, WPP_3742f7b8aa593665a28f1ce7634f5781_Traceguids
0x140005b84  mov     [rsp+68h+var_48], rax
0x140005b89  lea     r8d, [r9-25h]
0x140005b8d  mov     rcx, [rcx+40h]
0x140005b91  call    WPP_RECORDER_SF_d
0x140005b96  mov     rax, cs:qword_140110CA8
0x140005b9d  mov     r9, rsi
0x140005ba0  mov     rdx, [rdi+8]
0x140005ba4  mov     r8, rbx
0x140005ba7  mov     rcx, cs:NetDriverGlobals
0x140005bae  call    _guard_dispatch_icall
0x140005bb3  jmp     short loc_140005BE0
0x140005bb5  cmp     eax, 103h
0x140005bba  jz      short loc_140005BE0
0x140005bbc  mov     ecx, eax
0x140005bbe  call    cs:__imp_NdisConvertNtStatusToNdisStatus
0x140005bc5  nop     dword ptr [rax+rax+00h]
0x140005bca  mov     rcx, [rdi+20h]; MiniportAdapterHandle
0x140005bce  lea     r9, [rdi+188h]; this
0x140005bd5  mov     r8d, eax; int
0x140005bd8  mov     rdx, rbx; struct _NDIS_OID_REQUEST *
0x140005bdb  call    ?WxNdisMOidRequestComplete@@YAXPEAXPEAU_NDIS_OID_REQUEST@@HPEBVCPort@@@Z; WxNdisMOidRequestComplete(void *,_NDIS_OID_REQUEST *,int,CPort const *)
0x140005be0  add     rsp, 48h
0x140005be4  pop     rdi
0x140005be5  pop     rsi
0x140005be6  pop     rbp
0x140005be7  pop     rbx
0x140005be8  retn
```
