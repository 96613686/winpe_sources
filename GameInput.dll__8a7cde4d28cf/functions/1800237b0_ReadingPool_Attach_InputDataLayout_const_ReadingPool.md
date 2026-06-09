# ReadingPool::Attach(InputDataLayout const *,ReadingPool * *)

- ea: `0x1800237b0`
- end: `0x180023885`
- name: `?Attach@ReadingPool@@SAJPEBVInputDataLayout@@PEAPEAV1@@Z`
- size: `213`
- prototype: `__int64 __fastcall(const struct InputDataLayout *, struct ReadingPool **)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180005200`

## callees

- `0x180001304`
- `0x1800234b4`
- `0x1800237b0`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1800237d3`
- `ntdll!RtlAllocateHeap` at `0x1800237d3`

## string_xrefs

- `0x180023835`: `onecore\xbox\gameinput\memory\ReadingPool.cpp`

## pseudocode

```c
__int64 __fastcall ReadingPool::Attach(const struct InputDataLayout *a1, struct ReadingPool **a2)
{
  ReadingPool *Heap; // rax
  int v5; // r8d
  int v6; // r9d
  struct ReadingPool *v7; // rax
  int v9; // [rsp+50h] [rbp+8h] BYREF
  int v10; // [rsp+58h] [rbp+10h] BYREF
  const char *v11; // [rsp+60h] [rbp+18h] BYREF

  Heap = (ReadingPool *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x48u);
  if ( Heap )
  {
    v7 = ReadingPool::ReadingPool(Heap, a1, a1, 0);
    *a2 = v7;
    if ( v7 )
      return 0;
  }
  else
  {
    *a2 = 0;
  }
  if ( (unsigned int)dword_180069000 > 2 && (qword_180069010 & 0x20) != 0 && (qword_180069018 & 0x20) == qword_180069018 )
  {
    v9 = -2147024882;
    v11 = "onecore\\xbox\\gameinput\\memory\\ReadingPool.cpp";
    v10 = 210;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (unsigned int)&v11,
      (unsigned int)byte_18005E93B,
      v5,
      v6,
      (__int64)&v11,
      (__int64)&v10,
      (__int64)&v9);
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x1800237b0  mov     [rsp+arg_18], rbx
0x1800237b5  push    rdi
0x1800237b6  sub     rsp, 40h
0x1800237ba  mov     rdi, rcx
0x1800237bd  mov     rbx, rdx
0x1800237c0  mov     rcx, gs:60h
0x1800237c9  xor     edx, edx; Flags
0x1800237cb  mov     rcx, [rcx+30h]; HeapHandle
0x1800237cf  lea     r8d, [rdx+48h]; Size
0x1800237d3  call    cs:__imp_RtlAllocateHeap
0x1800237da  nop     dword ptr [rax+rax+00h]
0x1800237df  test    rax, rax
0x1800237e2  jz      short loc_180023801
0x1800237e4  xor     r9d, r9d; struct ReadingPoolElementId *
0x1800237e7  mov     r8, rdi; struct InputDataLayout *
0x1800237ea  mov     rdx, rdi; void *
0x1800237ed  mov     rcx, rax; this
0x1800237f0  call    ??0ReadingPool@@AEAA@PEAXPEBVInputDataLayout@@PEAVReadingPoolElementId@@@Z; ReadingPool::ReadingPool(void *,InputDataLayout const *,ReadingPoolElementId *)
0x1800237f5  mov     [rbx], rax
0x1800237f8  test    rax, rax
0x1800237fb  jz      short loc_180023808
0x1800237fd  xor     eax, eax
0x1800237ff  jmp     short loc_180023879
0x180023801  mov     qword ptr [rbx], 0
0x180023808  mov     eax, cs:dword_180069000
0x18002380e  mov     ebx, 8007000Eh
0x180023813  cmp     eax, 2
0x180023816  jbe     short loc_180023877
0x180023818  mov     rcx, cs:qword_180069018
0x18002381f  mov     rax, cs:qword_180069010
0x180023826  test    al, 20h
0x180023828  jz      short loc_180023877
0x18002382a  mov     rax, rcx
0x18002382d  and     eax, 20h
0x180023830  cmp     rax, rcx
0x180023833  jnz     short loc_180023877
0x180023835  lea     rcx, aOnecoreXboxGam_41; "onecore\\xbox\\gameinput\\memory\\Readi"...
0x18002383c  mov     [rsp+48h+arg_0], ebx
0x180023840  mov     [rsp+48h+arg_10], rcx
0x180023845  lea     rdx, byte_18005E93B
0x18002384c  lea     rcx, [rsp+48h+arg_0]
0x180023851  mov     [rsp+48h+arg_8], 0D2h
0x180023859  mov     [rsp+48h+var_18], rcx
0x18002385e  lea     rcx, [rsp+48h+arg_8]
0x180023863  mov     [rsp+48h+var_20], rcx
0x180023868  lea     rcx, [rsp+48h+arg_10]
0x18002386d  mov     [rsp+48h+var_28], rcx
0x180023872  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180023877  mov     eax, ebx
0x180023879  mov     rbx, [rsp+48h+arg_18]
0x18002387e  add     rsp, 40h
0x180023882  pop     rdi
0x180023883  retn
```
