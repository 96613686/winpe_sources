# ATL::IDispatchImpl<IDsmControl,&_GUID const IID_IDsmControl,&_GUID const LIBID_DsmApiLib,1,0,ATL::CComTypeInfoHolder>::GetTypeInfoCount(uint *)

- ea: `0x18000a870`
- end: `0x18000a884`
- name: `?GetTypeInfoCount@?$IDispatchImpl@UIDsmControl@@$1?IID_IDsmControl@@3U_GUID@@B$1?LIBID_DsmApiLib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJPEAI@Z`
- size: `20`
- prototype: `__int64 __fastcall(__int64, _DWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000a870`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IDsmControl,&_GUID const IID_IDsmControl,&_GUID const LIBID_DsmApiLib,1,0,ATL::CComTypeInfoHolder>::GetTypeInfoCount(
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
0x18000a870  test    rdx, rdx
0x18000a873  jnz     short loc_18000A87B
0x18000a875  mov     eax, 80004003h
0x18000a87a  retn
0x18000a87b  mov     dword ptr [rdx], 1
0x18000a881  xor     eax, eax
0x18000a883  retn
```
