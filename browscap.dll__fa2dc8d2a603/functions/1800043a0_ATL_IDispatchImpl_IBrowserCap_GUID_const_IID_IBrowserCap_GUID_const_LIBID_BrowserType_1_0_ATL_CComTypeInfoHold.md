# ATL::IDispatchImpl<IBrowserCap,&_GUID const IID_IBrowserCap,&_GUID const LIBID_BrowserType,1,0,ATL::CComTypeInfoHolder>::GetTypeInfoCount(uint *)

- ea: `0x1800043a0`
- end: `0x1800043b4`
- name: `?GetTypeInfoCount@?$IDispatchImpl@UIBrowserCap@@$1?IID_IBrowserCap@@3U_GUID@@B$1?LIBID_BrowserType@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJPEAI@Z`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800043a0`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IBrowserCap,&_GUID const IID_IBrowserCap,&_GUID const LIBID_BrowserType,1,0,ATL::CComTypeInfoHolder>::GetTypeInfoCount(
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
0x1800043a0  test    rdx, rdx
0x1800043a3  jnz     short loc_1800043AB
0x1800043a5  mov     eax, 80004003h
0x1800043aa  retn
0x1800043ab  mov     dword ptr [rdx], 1
0x1800043b1  xor     eax, eax
0x1800043b3  retn
```
