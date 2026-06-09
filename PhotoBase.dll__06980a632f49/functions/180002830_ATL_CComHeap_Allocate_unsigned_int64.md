# ATL::CComHeap::Allocate(unsigned __int64)

- ea: `0x180002830`
- end: `0x180002845`
- name: `?Allocate@CComHeap@ATL@@UEAAPEAX_K@Z`
- size: `21`
- prototype: `void *__fastcall(ATL::CComHeap *__hidden this, unsigned __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002830`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18000283e`

## pseudocode

```c
LPVOID __fastcall ATL::CComHeap::Allocate(ATL::CComHeap *this, unsigned __int64 a2)
{
  if ( a2 <= 0x7FFFFFFF )
    return CoTaskMemAlloc((unsigned int)a2);
  else
    return 0;
}

```

## disassembly

```asm
0x180002830  cmp     rdx, 7FFFFFFFh
0x180002837  jbe     short loc_18000283C
0x180002839  xor     eax, eax
0x18000283b  retn
0x18000283c  mov     ecx, edx
0x18000283e  jmp     cs:__imp_CoTaskMemAlloc
```
