# ATL::CComHeap::Reallocate(void *,unsigned __int64)

- ea: `0x180002a00`
- end: `0x180002a1c`
- name: `?Reallocate@CComHeap@ATL@@UEAAPEAXPEAX_K@Z`
- size: `28`
- prototype: `void *__fastcall(ATL::CComHeap *__hidden this, void *, unsigned __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002a00`

## import_xrefs

- `ole32!CoTaskMemRealloc` at `0x180002a15`

## pseudocode

```c
LPVOID __fastcall ATL::CComHeap::Reallocate(ATL::CComHeap *this, void *a2, unsigned __int64 a3)
{
  if ( a3 <= 0x7FFFFFFF )
    return CoTaskMemRealloc(a2, (unsigned int)a3);
  else
    return 0;
}

```

## disassembly

```asm
0x180002a00  mov     rax, rdx
0x180002a03  cmp     r8, 7FFFFFFFh
0x180002a0a  jbe     short loc_180002A0F
0x180002a0c  xor     eax, eax
0x180002a0e  retn
0x180002a0f  mov     edx, r8d
0x180002a12  mov     rcx, rax
0x180002a15  jmp     cs:__imp_CoTaskMemRealloc
```
