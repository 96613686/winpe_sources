# BinXmlReader::BinXmlReader(BinXmlReaderData *,ulong,AbstractPublishedEventRecord *,BinXmlStringTable *,BinXmlTemplateTable *)

- ea: `0x180003dc0`
- end: `0x180003ec5`
- name: `??0BinXmlReader@@QEAA@PEAUBinXmlReaderData@@KPEAVAbstractPublishedEventRecord@@PEAVBinXmlStringTable@@PEAVBinXmlTemplateTable@@@Z`
- size: `261`
- prototype: `BinXmlReader *__usercall@<rax>(BinXmlReader *__hidden this@<rcx>, struct BinXmlReaderData *@<rdx>, unsigned int@<r8d>, struct AbstractPublishedEventRecord *@<r9>, struct BinXmlStringTable *, struct BinXmlTemplateTable *)`
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180001568`
- `0x180007fb8`
- `0x180017864`
- `0x180026e30`
- `0x180027510`
- `0x1800303fc`

## callees

- `0x1800017cc`
- `0x180003ed0`
- `0x1800058f4`
- `0x18003c010`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
BinXmlReader *__fastcall BinXmlReader::BinXmlReader(
        BinXmlReader *this,
        struct BinXmlReaderData *a2,
        __int64 a3,
        struct AbstractPublishedEventRecord *a4,
        struct BinXmlStringTable *a5,
        struct BinXmlTemplateTable *a6)
{
  int v8; // ebx

  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = a2;
  *((_DWORD *)this + 8) = 1;
  *((_DWORD *)this + 9) = -1;
  utl::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>((_QWORD *)this + 5);
  utl::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>((_QWORD *)this + 8);
  *((_QWORD *)this + 11) = a5;
  *((_QWORD *)this + 12) = a6;
  *((_QWORD *)this + 13) = &unk_180040824;
  *((_DWORD *)this + 28) = 0;
  *((_BYTE *)this + 116) = 1;
  *((_QWORD *)this + 15) = &Buffer::`vftable';
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_BYTE *)this + 144) = 1;
  Buffer::SetSize((BinXmlReader *)((char *)this + 120), 0);
  *((_DWORD *)this + 35) = 0;
  *((_QWORD *)this + 19) = (char *)this + 120;
  *((_QWORD *)this + 20) = 0;
  *((_QWORD *)this + 21) = 0;
  v8 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 19) + 16LL))(*((_QWORD *)this + 19));
  *((_QWORD *)this + 20) = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 19) + 48LL))(*((_QWORD *)this + 19));
  *((_DWORD *)this + 43) = v8;
  *((_QWORD *)this + 22) = a4;
  *((_DWORD *)this + 46) = 0;
  *((_WORD *)this + 94) = 0;
  BinXmlReader::NextReaderData(this);
  return this;
}

```

## disassembly

```asm
0x180003dc0  mov     [rsp+arg_0], rcx
0x180003dc5  push    rbx
0x180003dc6  push    rbp
0x180003dc7  push    rsi
0x180003dc8  push    rdi
0x180003dc9  sub     rsp, 28h
0x180003dcd  mov     rdi, r9
0x180003dd0  mov     rsi, rcx
0x180003dd3  xor     ebp, ebp
0x180003dd5  mov     [rcx], rbp
0x180003dd8  mov     [rcx+8], rbp
0x180003ddc  mov     [rcx+10h], rbp
0x180003de0  mov     [rcx+18h], rdx
0x180003de4  mov     dword ptr [rcx+20h], 1
0x180003deb  mov     dword ptr [rcx+24h], 0FFFFFFFFh
0x180003df2  add     rcx, 28h ; '('
0x180003df6  call    ??0?$vector@UTmplInstInfo@BinXmlReader@@V?$allocator@UTmplInstInfo@BinXmlReader@@@utl@@@utl@@QEAA@XZ; utl::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>(void)
0x180003dfb  nop
0x180003dfc  lea     rcx, [rsi+40h]
0x180003e00  call    ??0?$vector@UTmplInstInfo@BinXmlReader@@V?$allocator@UTmplInstInfo@BinXmlReader@@@utl@@@utl@@QEAA@XZ; utl::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>(void)
0x180003e05  nop
0x180003e06  mov     rax, [rsp+48h+arg_20]
0x180003e0b  mov     [rsi+58h], rax
0x180003e0f  mov     rax, [rsp+48h+arg_28]
0x180003e14  mov     [rsi+60h], rax
0x180003e18  lea     rax, unk_180040824
0x180003e1f  mov     [rsi+68h], rax
0x180003e23  mov     [rsi+70h], ebp
0x180003e26  mov     byte ptr [rsi+74h], 1
0x180003e2a  lea     rbx, [rsi+78h]
0x180003e2e  lea     rax, ??_7Buffer@@6B@; const Buffer::`vftable'
0x180003e35  mov     [rbx], rax
0x180003e38  mov     [rbx+8], rbp
0x180003e3c  mov     [rbx+10h], rbp
0x180003e40  mov     byte ptr [rbx+18h], 1
0x180003e44  xor     edx, edx; unsigned int
0x180003e46  mov     rcx, rbx; this
0x180003e49  call    ?SetSize@Buffer@@QEAAXK@Z; Buffer::SetSize(ulong)
0x180003e4e  nop
0x180003e4f  mov     [rbx+14h], ebp
0x180003e52  mov     [rsi+98h], rbx
0x180003e59  mov     [rsi+0A0h], rbp
0x180003e60  mov     [rsi+0A8h], rbp
0x180003e67  mov     rcx, [rsi+98h]
0x180003e6e  mov     rax, [rcx]
0x180003e71  mov     rax, [rax+10h]
0x180003e75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e7a  mov     ebx, eax
0x180003e7c  mov     rcx, [rsi+98h]
0x180003e83  mov     rdx, [rcx]
0x180003e86  mov     rax, [rdx+30h]
0x180003e8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e8f  mov     [rsi+0A0h], rax
0x180003e96  mov     [rsi+0ACh], ebx
0x180003e9c  mov     [rsi+0B0h], rdi
0x180003ea3  mov     [rsi+0B8h], ebp
0x180003ea9  mov     [rsi+0BCh], bp
0x180003eb0  mov     rcx, rsi; this
0x180003eb3  call    ?NextReaderData@BinXmlReader@@AEAAXXZ; BinXmlReader::NextReaderData(void)
0x180003eb8  nop
0x180003eb9  mov     rax, rsi
0x180003ebc  add     rsp, 28h
0x180003ec0  pop     rdi
0x180003ec1  pop     rsi
0x180003ec2  pop     rbp
0x180003ec3  pop     rbx
0x180003ec4  retn
```
