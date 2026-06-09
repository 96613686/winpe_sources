# StructuredQuery1::MnemonicsCollection::~MnemonicsCollection(void)

- ea: `0x180056974`
- end: `0x1800569cd`
- name: `??1MnemonicsCollection@StructuredQuery1@@AEAA@XZ`
- size: `89`
- prototype: `void __fastcall(StructuredQuery1::MnemonicsCollection *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180056930`

## callees

- `0x180056974`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800569a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800569b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800569a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800569b5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall StructuredQuery1::MnemonicsCollection::~MnemonicsCollection(
        StructuredQuery1::MnemonicsCollection *this)
{
  bool v1; // zf
  unsigned __int64 i; // rdi

  v1 = *((_QWORD *)this + 1) == 0;
  *(_QWORD *)this = &StructuredQuery1::MnemonicsCollection::`vftable';
  if ( !v1 )
  {
    for ( i = 0; i < *((_QWORD *)this + 2); ++i )
      CoTaskMemFree(*(LPVOID *)(*((_QWORD *)this + 1) + 8 * i));
    CoTaskMemFree(*((LPVOID *)this + 1));
  }
  _InterlockedDecrement(&dword_1800B134C);
}

```

## disassembly

```asm
0x180056974  mov     [rsp+arg_0], rbx
0x180056979  push    rdi
0x18005697a  sub     rsp, 20h
0x18005697e  cmp     qword ptr [rcx+8], 0
0x180056983  lea     rax, ??_7MnemonicsCollection@StructuredQuery1@@6B@; const StructuredQuery1::MnemonicsCollection::`vftable'
0x18005698a  mov     [rcx], rax
0x18005698d  mov     rbx, rcx
0x180056990  jz      short loc_1800569BB
0x180056992  xor     edi, edi
0x180056994  cmp     [rcx+10h], rdi
0x180056998  jbe     short loc_1800569B1
0x18005699a  mov     rcx, [rbx+8]
0x18005699e  mov     rcx, [rcx+rdi*8]; pv
0x1800569a2  call    cs:__imp_CoTaskMemFree
0x1800569a8  inc     rdi
0x1800569ab  cmp     rdi, [rbx+10h]
0x1800569af  jb      short loc_18005699A
0x1800569b1  mov     rcx, [rbx+8]; pv
0x1800569b5  call    cs:__imp_CoTaskMemFree
0x1800569bb  lock dec cs:dword_1800B134C
0x1800569c2  mov     rbx, [rsp+28h+arg_0]
0x1800569c7  add     rsp, 20h
0x1800569cb  pop     rdi
0x1800569cc  retn
```
