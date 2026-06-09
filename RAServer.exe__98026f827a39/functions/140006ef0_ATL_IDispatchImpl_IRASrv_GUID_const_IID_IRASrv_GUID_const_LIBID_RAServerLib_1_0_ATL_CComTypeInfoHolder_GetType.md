# ATL::IDispatchImpl<IRASrv,&_GUID const IID_IRASrv,&_GUID const LIBID_RAServerLib,1,0,ATL::CComTypeInfoHolder>::GetTypeInfoCount(uint *)

- ea: `0x140006ef0`
- end: `0x140006f04`
- name: `?GetTypeInfoCount@?$IDispatchImpl@UIRASrv@@$1?IID_IRASrv@@3U_GUID@@B$1?LIBID_RAServerLib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJPEAI@Z`
- size: `20`
- prototype: `__int64 __fastcall(__int64, _DWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140006ef0`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IRASrv,&_GUID const IID_IRASrv,&_GUID const LIBID_RAServerLib,1,0,ATL::CComTypeInfoHolder>::GetTypeInfoCount(
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
0x140006ef0  test    rdx, rdx
0x140006ef3  jnz     short loc_140006EFB
0x140006ef5  mov     eax, 80004003h
0x140006efa  retn
0x140006efb  mov     dword ptr [rdx], 1
0x140006f01  xor     eax, eax
0x140006f03  retn
```
