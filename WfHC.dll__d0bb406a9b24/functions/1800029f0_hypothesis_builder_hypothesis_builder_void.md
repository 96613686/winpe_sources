# _hypothesis_builder::~_hypothesis_builder(void)

- ea: `0x1800029f0`
- end: `0x180002a72`
- name: `??1_hypothesis_builder@@QEAA@XZ`
- size: `130`
- prototype: `void __fastcall(LPVOID *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800029f0`
- `0x180003b60`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002a05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002a14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002a34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002a3e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002a55`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002a05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002a14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002a34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002a3e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002a55`

## pseudocode

```c
void __fastcall _hypothesis_builder::~_hypothesis_builder(LPVOID *this)
{
  void *v2; // rcx
  LPVOID *v3; // rcx

  CoTaskMemFree(*this);
  v2 = this[1];
  *this = 0;
  CoTaskMemFree(v2);
  this[1] = 0;
  _attributes_array_t::FreeElements((_attributes_array_t *)(this + 2));
  v3 = (LPVOID *)this[4];
  if ( v3 )
    CoTaskMemFree(v3[3]);
  CoTaskMemFree(this[4]);
  this[4] = 0;
  _attributes_array_t::FreeElements((_attributes_array_t *)(this + 2));
  CoTaskMemFree(this[3]);
  this[3] = 0;
  *((_DWORD *)this + 4) = 0;
}

```

## disassembly

```asm
0x1800029f0  mov     [rsp+arg_0], rbx
0x1800029f5  mov     [rsp+arg_8], rsi
0x1800029fa  push    rdi
0x1800029fb  sub     rsp, 20h
0x1800029ff  mov     rbx, rcx
0x180002a02  mov     rcx, [rcx]; pv
0x180002a05  call    cs:__imp_CoTaskMemFree
0x180002a0b  mov     rcx, [rbx+8]; pv
0x180002a0f  xor     esi, esi
0x180002a11  mov     [rbx], rsi
0x180002a14  call    cs:__imp_CoTaskMemFree
0x180002a1a  lea     rcx, [rbx+10h]; this
0x180002a1e  mov     [rbx+8], rsi
0x180002a22  call    ?FreeElements@_attributes_array_t@@QEAAXXZ; _attributes_array_t::FreeElements(void)
0x180002a27  mov     rcx, [rbx+20h]
0x180002a2b  test    rcx, rcx
0x180002a2e  jz      short loc_180002A3A
0x180002a30  mov     rcx, [rcx+18h]; pv
0x180002a34  call    cs:__imp_CoTaskMemFree
0x180002a3a  mov     rcx, [rbx+20h]; pv
0x180002a3e  call    cs:__imp_CoTaskMemFree
0x180002a44  lea     rcx, [rbx+10h]; this
0x180002a48  mov     [rbx+20h], rsi
0x180002a4c  call    ?FreeElements@_attributes_array_t@@QEAAXXZ; _attributes_array_t::FreeElements(void)
0x180002a51  mov     rcx, [rbx+18h]; pv
0x180002a55  call    cs:__imp_CoTaskMemFree
0x180002a5b  mov     [rbx+18h], rsi
0x180002a5f  mov     [rbx+10h], esi
0x180002a62  mov     rbx, [rsp+28h+arg_0]
0x180002a67  mov     rsi, [rsp+28h+arg_8]
0x180002a6c  add     rsp, 20h
0x180002a70  pop     rdi
0x180002a71  retn
```
