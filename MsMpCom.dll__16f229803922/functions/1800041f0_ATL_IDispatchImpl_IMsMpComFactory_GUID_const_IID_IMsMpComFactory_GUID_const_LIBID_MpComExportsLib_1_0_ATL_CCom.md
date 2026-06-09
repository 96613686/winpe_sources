# ATL::IDispatchImpl<IMsMpComFactory,&_GUID const IID_IMsMpComFactory,&_GUID const LIBID_MpComExportsLib,1,0,ATL::CComTypeInfoHolder>::GetTypeInfoCount(uint *)

- ea: `0x1800041f0`
- end: `0x180004204`
- name: `?GetTypeInfoCount@?$IDispatchImpl@UIMsMpComFactory@@$1?IID_IMsMpComFactory@@3U_GUID@@B$1?LIBID_MpComExportsLib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJPEAI@Z`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800041f0`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IMsMpComFactory,&_GUID const IID_IMsMpComFactory,&_GUID const LIBID_MpComExportsLib,1,0,ATL::CComTypeInfoHolder>::GetTypeInfoCount(
        __int64 a1,
        _DWORD *a2)
{
  if ( !a2 )
    return 2147500035LL;
  *a2 = 1;
  return 0;
}

```

## disassembly

```asm
0x1800041f0  test    rdx, rdx
0x1800041f3  jnz     short loc_1800041FB
0x1800041f5  mov     eax, 80004003h
0x1800041fa  retn
0x1800041fb  mov     dword ptr [rdx], 1
0x180004201  xor     eax, eax
0x180004203  retn
```
