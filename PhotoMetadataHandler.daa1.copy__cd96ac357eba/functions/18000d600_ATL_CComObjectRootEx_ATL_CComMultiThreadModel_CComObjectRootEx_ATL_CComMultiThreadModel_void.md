# ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>(void)

- ea: `0x18000d600`
- end: `0x18000d61d`
- name: `??1?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ`
- size: `29`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000d5b4`
- `0x180011094`
- `0x180017614`
- `0x18001d2a8`
- `0x180020768`
- `0x1800207cc`
- `0x180020890`
- `0x1800267c6`

## callees

- `0x18000d600`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d612`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d612`

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
0x18000d600  sub     rsp, 28h
0x18000d604  add     rcx, 8; lpCriticalSection
0x18000d608  cmp     byte ptr [rcx+28h], 0
0x18000d60c  jz      short loc_18000D618
0x18000d60e  mov     byte ptr [rcx+28h], 0
0x18000d612  call    cs:__imp_DeleteCriticalSection
0x18000d618  add     rsp, 28h
0x18000d61c  retn
```
