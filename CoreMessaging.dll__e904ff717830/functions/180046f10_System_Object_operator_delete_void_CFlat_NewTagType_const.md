# System::Object::operator delete(void *,CFlat::NewTagType const &)

- ea: `0x180046f10`
- end: `0x180046f49`
- name: `??3Object@System@@SAXPEAXAEBUNewTagType@CFlat@@@Z`
- size: `57`
- prototype: `void __fastcall(void *lpMem, const struct CFlat::NewTagType *)`
- caller_count: `103`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180002240`
- `0x180030f40`
- `0x1800311d0`
- `0x180031200`
- `0x180031aa0`
- `0x180031b30`
- `0x180031b70`
- `0x180031bf0`
- `0x180031c50`
- `0x180031c80`
- `0x180031ef0`
- `0x180032090`
- `0x1800326a0`
- `0x180032dd0`
- `0x180033220`
- `0x1800332d0`
- `0x180033330`
- `0x180033360`
- `0x180033480`
- `0x1800334c0`
- `0x180033870`
- `0x1800338d0`
- `0x180033d10`
- `0x180034ce0`
- `0x1800353f0`
- `0x180035430`
- `0x18003af60`
- `0x18003b310`
- `0x180046480`
- `0x180046d30`
- `0x180046d60`
- `0x180046d90`
- `0x180046dc0`
- `0x180046df0`
- `0x180046e40`
- `0x180046ec0`
- `0x180046ee0`
- `0x18004bec0`
- `0x18004dc60`
- `0x18004e020`
- `0x18004e1c0`
- `0x18004e450`
- `0x18004f490`
- `0x18004f930`
- `0x18005f500`
- `0x180065eb0`
- `0x1800662e0`
- `0x180066310`
- `0x180066340`
- `0x1800663a0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180046f35`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180046f35`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180046f23`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180046f23`

## pseudocode

```c
void __fastcall System::Object::operator delete(void *lpMem, const struct CFlat::NewTagType *a2)
{
  HANDLE *Value; // rdi

  Value = (HANDLE *)TlsGetValue(Cn::Context::s_tlsStorage);
  HeapFree(Value[7], 0, lpMem);
  --*((_DWORD *)Value + 16);
}

```

## disassembly

```asm
0x180046f10  mov     [rsp+arg_0], rbx
0x180046f15  push    rdi
0x180046f16  sub     rsp, 20h
0x180046f1a  mov     rbx, rcx
0x180046f1d  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x180046f23  call    cs:__imp_TlsGetValue
0x180046f29  mov     r8, rbx; lpMem
0x180046f2c  xor     edx, edx; dwFlags
0x180046f2e  mov     rdi, rax
0x180046f31  mov     rcx, [rax+38h]; hHeap
0x180046f35  call    cs:__imp_HeapFree
0x180046f3b  dec     dword ptr [rdi+40h]
0x180046f3e  mov     rbx, [rsp+28h+arg_0]
0x180046f43  add     rsp, 20h
0x180046f47  pop     rdi
0x180046f48  retn
```
