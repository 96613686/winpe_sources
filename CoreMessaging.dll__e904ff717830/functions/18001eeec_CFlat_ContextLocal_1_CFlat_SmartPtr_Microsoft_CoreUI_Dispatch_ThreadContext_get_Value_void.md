# CFlat::ContextLocal$1<CFlat::SmartPtr<Microsoft::CoreUI::Dispatch::ThreadContext>>::get_Value(void)

- ea: `0x18001eeec`
- end: `0x18001ef09`
- name: `?get_Value@?$ContextLocal$1@V?$SmartPtr@VThreadContext@Dispatch@CoreUI@Microsoft@@@CFlat@@@CFlat@@QEAAPEAVThreadContext@Dispatch@CoreUI@Microsoft@@XZ`
- size: `29`
- prototype: ``
- caller_count: `22`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001dca0`
- `0x18001e760`
- `0x18001ee6c`
- `0x180021edc`
- `0x180023288`
- `0x180026104`
- `0x180029310`
- `0x18002a6cc`
- `0x18002bec8`
- `0x180030084`
- `0x18003b490`
- `0x18004c6d0`
- `0x18004cce0`
- `0x18005bc90`
- `0x1800644b4`
- `0x180071c8c`
- `0x1800893ec`
- `0x18008b870`
- `0x18008c0dc`
- `0x18008c2c4`
- `0x1800921b8`
- `0x1800a2710`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001eef6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001eef6`

## pseudocode

```c
__int64 CFlat::ContextLocal$1<CFlat::SmartPtr<Microsoft::CoreUI::Dispatch::ThreadContext>>::get_Value()
{
  return *(_QWORD *)(*((_QWORD *)TlsGetValue(Cn::Context::s_tlsStorage) + 6) + 56LL);
}

```

## disassembly

```asm
0x18001eeec  sub     rsp, 28h
0x18001eef0  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18001eef6  call    cs:__imp_TlsGetValue
0x18001eefc  mov     rax, [rax+30h]
0x18001ef00  mov     rax, [rax+38h]
0x18001ef04  add     rsp, 28h
0x18001ef08  retn
```
