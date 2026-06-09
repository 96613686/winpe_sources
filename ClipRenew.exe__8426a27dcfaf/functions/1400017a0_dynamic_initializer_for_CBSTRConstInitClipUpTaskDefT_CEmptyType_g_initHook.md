# _dynamic_initializer_for__CBSTRConstInitClipUpTaskDefT_CEmptyType_::g_initHook__

- ea: `0x1400017a0`
- end: `0x1400017f7`
- name: `_dynamic_initializer_for__CBSTRConstInitClipUpTaskDefT_CEmptyType_::g_initHook__`
- size: `87`
- prototype: `PVOID()`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## import_xrefs

- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1400017c7`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1400017db`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1400017c7`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1400017db`

## pseudocode

```c
PVOID dynamic_initializer_for__CBSTRConstInitClipUpTaskDefT_CEmptyType_::g_initHook__()
{
  PVOID result; // rax

  CBSTRConstInitClipUpTaskDefT<CEmptyType>::g_initHook = CGlobalList<CGlobalInitializer<1>>::g_pFirst;
  CGlobalList<CGlobalInitializer<1>>::g_pFirst = (__int64)&CBSTRConstInitClipUpTaskDefT<CEmptyType>::g_initHook;
  qword_140019DD0 = (__int64)EncodePointer(CBSTRConstInitClipUpTaskDefT<CEmptyType>::Init);
  result = EncodePointer(CBSTRConstInitClipUpTaskDefT<CEmptyType>::Done);
  qword_140019DD8 = (__int64)result;
  dword_140019DE0 = 0;
  return result;
}

```

## disassembly

```asm
0x1400017a0  sub     rsp, 28h
0x1400017a4  mov     rax, cs:?g_pFirst@?$CGlobalList@V?$CGlobalInitializer@$00@@@@2PEAV?$CGlobalInitializer@$00@@EA; CGlobalInitializer<1> * CGlobalList<CGlobalInitializer<1>>::g_pFirst
0x1400017ab  lea     rcx, ?Init@?$CBSTRConstInitClipUpTaskDefT@VCEmptyType@@@@CAJXZ; Ptr
0x1400017b2  mov     cs:?g_initHook@?$CBSTRConstInitClipUpTaskDefT@VCEmptyType@@@@0V?$CGlobalInitializer@$00@@A, rax; CGlobalInitializer<1> CBSTRConstInitClipUpTaskDefT<CEmptyType>::g_initHook
0x1400017b9  lea     rax, ?g_initHook@?$CBSTRConstInitClipUpTaskDefT@VCEmptyType@@@@0V?$CGlobalInitializer@$00@@A; CGlobalInitializer<1> CBSTRConstInitClipUpTaskDefT<CEmptyType>::g_initHook
0x1400017c0  mov     cs:?g_pFirst@?$CGlobalList@V?$CGlobalInitializer@$00@@@@2PEAV?$CGlobalInitializer@$00@@EA, rax; CGlobalInitializer<1> * CGlobalList<CGlobalInitializer<1>>::g_pFirst
0x1400017c7  call    cs:__imp_EncodePointer
0x1400017cd  lea     rcx, ?Done@?$CBSTRConstInitClipUpTaskDefT@VCEmptyType@@@@CAJXZ; Ptr
0x1400017d4  mov     cs:qword_140019DD0, rax
0x1400017db  call    cs:__imp_EncodePointer
0x1400017e1  mov     cs:qword_140019DD8, rax
0x1400017e8  mov     cs:dword_140019DE0, 0
0x1400017f2  add     rsp, 28h
0x1400017f6  retn
```
