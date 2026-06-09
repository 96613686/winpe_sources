# ShaderParser::~ShaderParser(void)

- ea: `0x1800a0b48`
- end: `0x1800a0be5`
- name: `??1ShaderParser@@QEAA@XZ`
- size: `157`
- prototype: `void __fastcall(ShaderParser *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x1800a0afc`

## callees

- `0x18000bb58`
- `0x1800199cc`
- `0x180019dc8`
- `0x1800a0b48`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a0b58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a0b58`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ShaderParser::~ShaderParser(LPVOID *this)
{
  _BYTE *v2; // rcx

  CoTaskMemFree(this[39]);
  this[39] = 0;
  v2 = this[29];
  if ( v2 )
  {
    std::_Deallocate<16>(v2, 4 * (((_BYTE *)this[31] - v2) >> 2));
    this[29] = 0;
    this[30] = 0;
    this[31] = 0;
  }
  CSignatureParser::Cleanup((CSignatureParser *)(this + 22));
  CSignatureParser5::~CSignatureParser5((CSignatureParser5 *)(this + 3));
  CSignatureParser::Cleanup((CSignatureParser *)this);
}

```

## disassembly

```asm
0x1800a0b48  push    rbx
0x1800a0b4a  sub     rsp, 20h
0x1800a0b4e  mov     rbx, rcx
0x1800a0b51  mov     rcx, [rcx+138h]; pv
0x1800a0b58  call    cs:__imp_CoTaskMemFree
0x1800a0b5e  mov     qword ptr [rbx+138h], 0
0x1800a0b69  mov     rcx, [rbx+0E8h]
0x1800a0b70  test    rcx, rcx
0x1800a0b73  jz      short loc_1800A0BBF
0x1800a0b75  mov     rax, [rbx+0F8h]
0x1800a0b7c  sub     rax, rcx
0x1800a0b7f  sar     rax, 2
0x1800a0b83  mov     rdx, 0CCCCCCCCCCCCCCCDh
0x1800a0b8d  imul    rax, rdx
0x1800a0b91  lea     rdx, [rax+rax*4]
0x1800a0b95  shl     rdx, 2
0x1800a0b99  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800a0b9e  mov     qword ptr [rbx+0E8h], 0
0x1800a0ba9  mov     qword ptr [rbx+0F0h], 0
0x1800a0bb4  mov     qword ptr [rbx+0F8h], 0
0x1800a0bbf  lea     rcx, [rbx+0B0h]; this
0x1800a0bc6  call    ?Cleanup@CSignatureParser@@AEAAXXZ; CSignatureParser::Cleanup(void)
0x1800a0bcb  nop
0x1800a0bcc  lea     rcx, [rbx+18h]; this
0x1800a0bd0  call    ??1CSignatureParser5@@QEAA@XZ; CSignatureParser5::~CSignatureParser5(void)
0x1800a0bd5  nop
0x1800a0bd6  mov     rcx, rbx; this
0x1800a0bd9  call    ?Cleanup@CSignatureParser@@AEAAXXZ; CSignatureParser::Cleanup(void)
0x1800a0bde  nop
0x1800a0bdf  add     rsp, 20h
0x1800a0be3  pop     rbx
0x1800a0be4  retn
```
