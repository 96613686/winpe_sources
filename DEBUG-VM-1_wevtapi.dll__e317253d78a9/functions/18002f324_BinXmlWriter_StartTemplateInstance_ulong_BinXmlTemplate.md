# BinXmlWriter::StartTemplateInstance(ulong,BinXmlTemplate *)

- ea: `0x18002f324`
- end: `0x18002f3b9`
- name: `?StartTemplateInstance@BinXmlWriter@@QEAAPEAVBinXmlTmplInstWriter@@KPEAVBinXmlTemplate@@@Z`
- size: `149`
- prototype: `struct BinXmlTmplInstWriter *__fastcall(BinXmlWriter *__hidden this, unsigned int, struct BinXmlTemplate *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800243cc`
- `0x180026e30`

## callees

- `0x180003780`
- `0x180008b20`
- `0x18002f324`
- `0x18002f6fc`
- `0x18002f84c`

## pseudocode

```c
Write **__fastcall BinXmlWriter::StartTemplateInstance(Write **this, int a2, struct BinXmlTemplate *a3)
{
  Write *v6; // rcx
  Write *v7; // rcx
  WriteBuffer *v8; // rcx
  int v9; // r8d
  int v11; // [rsp+38h] [rbp+10h] BYREF

  BinXmlWriter::WriteHeaderTokenIfNecessary((BinXmlWriter *)this);
  if ( a3 )
  {
    v6 = *this;
    LOBYTE(v11) = 12;
    WriteBuffer::Write(v6, &v11, 1u);
    BinXmlWriter::WriteTemplateDefinition((BinXmlWriter *)this, a3);
  }
  v7 = this[3];
  v11 = a2;
  this[5] = 0;
  *((_DWORD *)this + 9) = a2;
  WriteBuffer::Write(v7, &v11, 4u);
  v8 = this[3];
  v9 = *((_DWORD *)this + 9);
  *((_DWORD *)this + 8) = *((_DWORD *)v8 + 4);
  WriteBuffer::SetCurrentIndex(v8, *((_DWORD *)v8 + 4) + 4 * v9);
  return this + 3;
}

```

## disassembly

```asm
0x18002f324  mov     [rsp+arg_0], rbx
0x18002f329  mov     [rsp+arg_10], rsi
0x18002f32e  push    rdi
0x18002f32f  sub     rsp, 20h
0x18002f333  mov     rdi, r8
0x18002f336  mov     esi, edx
0x18002f338  mov     rbx, rcx
0x18002f33b  call    ?WriteHeaderTokenIfNecessary@BinXmlWriter@@AEAAXXZ; BinXmlWriter::WriteHeaderTokenIfNecessary(void)
0x18002f340  test    rdi, rdi
0x18002f343  jz      short loc_18002F368
0x18002f345  mov     rcx, [rbx]; this
0x18002f348  lea     rdx, [rsp+28h+arg_8]; void *
0x18002f34d  mov     r8d, 1; unsigned int
0x18002f353  mov     byte ptr [rsp+28h+arg_8], 0Ch
0x18002f358  call    ?Write@WriteBuffer@@QEAAXQEBXK@Z; WriteBuffer::Write(void const * const,ulong)
0x18002f35d  mov     rdx, rdi; struct BinXmlTemplate *
0x18002f360  mov     rcx, rbx; this
0x18002f363  call    ?WriteTemplateDefinition@BinXmlWriter@@AEAAXAEAVBinXmlTemplate@@@Z; BinXmlWriter::WriteTemplateDefinition(BinXmlTemplate &)
0x18002f368  mov     rcx, [rbx+18h]; this
0x18002f36c  lea     rdx, [rsp+28h+arg_8]; void *
0x18002f371  mov     r8d, 4; unsigned int
0x18002f377  mov     [rsp+28h+arg_8], esi
0x18002f37b  mov     qword ptr [rbx+28h], 0
0x18002f383  mov     [rbx+24h], esi
0x18002f386  call    ?Write@WriteBuffer@@QEAAXQEBXK@Z; WriteBuffer::Write(void const * const,ulong)
0x18002f38b  mov     rcx, [rbx+18h]; this
0x18002f38f  mov     r8d, [rbx+24h]
0x18002f393  mov     edx, [rcx+10h]
0x18002f396  mov     [rbx+20h], edx
0x18002f399  mov     edx, [rcx+10h]
0x18002f39c  lea     edx, [rdx+r8*4]; unsigned int
0x18002f3a0  call    ?SetCurrentIndex@WriteBuffer@@QEAAXK@Z; WriteBuffer::SetCurrentIndex(ulong)
0x18002f3a5  mov     rsi, [rsp+28h+arg_10]
0x18002f3aa  lea     rax, [rbx+18h]
0x18002f3ae  mov     rbx, [rsp+28h+arg_0]
0x18002f3b3  add     rsp, 20h
0x18002f3b7  pop     rdi
0x18002f3b8  retn
```
