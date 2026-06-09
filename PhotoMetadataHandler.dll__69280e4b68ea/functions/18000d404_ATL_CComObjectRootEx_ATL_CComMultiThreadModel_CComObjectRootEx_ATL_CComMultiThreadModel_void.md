# ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>(void)

- ea: `0x18000d404`
- end: `0x18000d428`
- name: `??1?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ`
- size: `36`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000d274`
- `0x18000d370`
- `0x180011848`
- `0x1800180d8`
- `0x18001e068`
- `0x1800217c8`
- `0x180021830`
- `0x1800218f0`
- `0x180027a76`

## callees

- `0x18000d404`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d416`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d416`

## pseudocode

```c
void __fastcall ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>(
        __int64 a1)
{
  __int64 v1; // rcx

  v1 = a1 + 8;
  if ( *(_BYTE *)(v1 + 40) )
  {
    *(_BYTE *)(v1 + 40) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)v1);
  }
}

```

## disassembly

```asm
0x18000d404  sub     rsp, 28h
0x18000d408  add     rcx, 8; lpCriticalSection
0x18000d40c  cmp     byte ptr [rcx+28h], 0
0x18000d410  jz      short loc_18000D422
0x18000d412  mov     byte ptr [rcx+28h], 0
0x18000d416  call    cs:__imp_DeleteCriticalSection
0x18000d41d  nop     dword ptr [rax+rax+00h]
0x18000d422  add     rsp, 28h
0x18000d426  retn
```
