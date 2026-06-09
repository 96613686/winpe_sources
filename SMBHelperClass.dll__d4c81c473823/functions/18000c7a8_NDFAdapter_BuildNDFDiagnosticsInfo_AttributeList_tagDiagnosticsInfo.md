# NDFAdapter::BuildNDFDiagnosticsInfo(AttributeList *,tagDiagnosticsInfo * *)

- ea: `0x18000c7a8`
- end: `0x18000c84b`
- name: `?BuildNDFDiagnosticsInfo@NDFAdapter@@SAXPEAVAttributeList@@PEAPEAUtagDiagnosticsInfo@@@Z`
- size: `163`
- prototype: `void __fastcall(struct AttributeList *this, struct tagDiagnosticsInfo **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800054f0`

## callees

- `0x18000c7a8`
- `0x18000d750`
- `0x18000dd04`
- `0x18000eddc`

## string_xrefs

- `0x18000c7d6`: `ImpersonationRequired`

## pseudocode

```c
void __fastcall NDFAdapter::BuildNDFDiagnosticsInfo(struct AttributeList *this, struct tagDiagnosticsInfo **a2)
{
  struct tagDiagnosticsInfo *TestMemory; // rbx
  int v5; // [rsp+20h] [rbp-28h] BYREF
  int v6; // [rsp+24h] [rbp-24h] BYREF
  _BYTE v7[32]; // [rsp+28h] [rbp-20h] BYREF

  TestMemory = (struct tagDiagnosticsInfo *)AllocateTestMemory(8u);
  *TestMemory = 0;
  if ( (unsigned int)AttributeList::attributeExists(this, L"ImpersonationRequired") )
    TestMemory->flags |= 0x80000000;
  if ( (unsigned int)AttributeList::attributeExists(this, L"Traceless") )
    TestMemory->flags |= 0x40000000u;
  if ( (unsigned int)AttributeList::attributeExists(this, L"Cost") )
  {
    try
    {
      TestMemory->cost = *(_DWORD *)(AttributeList::getAttribute(this, v7, L"DiagnosisCost", 2) + 8);
    }
    catch ( TestException v6 )
    {
      FreeTestMemory(TestMemory);
      v5 = v6;
      throw (TestException *)&v5;
    }
  }
  *a2 = TestMemory;
}

```

## disassembly

```asm
0x18000c7a8  mov     [rsp+arg_0], rbx
0x18000c7ad  mov     [rsp+arg_8], rsi
0x18000c7b2  push    rdi
0x18000c7b3  sub     rsp, 40h
0x18000c7b7  mov     rsi, rdx
0x18000c7ba  mov     rdi, rcx
0x18000c7bd  mov     ecx, 8; unsigned __int64
0x18000c7c2  call    ?AllocateTestMemory@@YAPEAX_K@Z; AllocateTestMemory(unsigned __int64)
0x18000c7c7  mov     rbx, rax
0x18000c7ca  mov     [rsp+48h+arg_10], rax
0x18000c7cf  mov     qword ptr [rax], 0
0x18000c7d6  lea     rdx, aImpersonationr; "ImpersonationRequired"
0x18000c7dd  mov     rcx, rdi; this
0x18000c7e0  call    ?attributeExists@AttributeList@@QEAAHPEAG@Z; AttributeList::attributeExists(ushort *)
0x18000c7e5  test    eax, eax
0x18000c7e7  jz      short loc_18000C7EE
0x18000c7e9  bts     dword ptr [rbx+4], 1Fh
0x18000c7ee  lea     rdx, aTraceless; "Traceless"
0x18000c7f5  mov     rcx, rdi; this
0x18000c7f8  call    ?attributeExists@AttributeList@@QEAAHPEAG@Z; AttributeList::attributeExists(ushort *)
0x18000c7fd  test    eax, eax
0x18000c7ff  jz      short loc_18000C806
0x18000c801  bts     dword ptr [rbx+4], 1Eh
0x18000c806  lea     rdx, aCost; "Cost"
0x18000c80d  mov     rcx, rdi; this
0x18000c810  call    ?attributeExists@AttributeList@@QEAAHPEAG@Z; AttributeList::attributeExists(ushort *)
0x18000c815  test    eax, eax
0x18000c817  jz      short loc_18000C838
0x18000c819  mov     r9d, 2
0x18000c81f  lea     r8, aDiagnosiscost; "DiagnosisCost"
0x18000c826  lea     rdx, [rsp+48h+var_20]
0x18000c82b  mov     rcx, rdi
0x18000c82e  call    ?getAttribute@AttributeList@@QEAA?AUAttribute@@PEAGW4AttributeType@@@Z; AttributeList::getAttribute(ushort *,AttributeType)
0x18000c833  mov     eax, [rax+8]
0x18000c836  mov     [rbx], eax
0x18000c838  mov     [rsi], rbx
0x18000c83b  mov     rbx, [rsp+48h+arg_0]
0x18000c840  mov     rsi, [rsp+48h+arg_8]
0x18000c845  add     rsp, 40h
0x18000c849  pop     rdi
0x18000c84a  retn
```
