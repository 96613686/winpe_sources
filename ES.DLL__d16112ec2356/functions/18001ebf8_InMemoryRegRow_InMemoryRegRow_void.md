# InMemoryRegRow::~InMemoryRegRow(void)

- ea: `0x18001ebf8`
- end: `0x18001ecdf`
- name: `??1InMemoryRegRow@@UEAA@XZ`
- size: `231`
- prototype: `void __fastcall(InMemoryRegRow *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001ebc0`

## callees

- `0x18001ebf8`
- `0x18001ee98`
- `0x18001efe8`
- `0x18001f158`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001ec34`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001ec34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ec70`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ec7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ec70`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ec7a`

## pseudocode

```c
void __fastcall InMemoryRegRow::~InMemoryRegRow(InMemoryRegRow *this)
{
  __int64 v2; // rcx
  __int64 i; // rsi
  __int64 v4; // rbx
  __int64 v5; // rax

  *(_QWORD *)this = &InMemoryRegRow::`vftable';
  v2 = *((_QWORD *)this + 7);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64, InMemoryRegRow *))(*(_QWORD *)v2 + 56LL))(v2, this);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 16LL))(*((_QWORD *)this + 7));
    *((_QWORD *)this + 7) = 0;
  }
  for ( i = 0; (unsigned int)i < *((_DWORD *)this + 16); *(_QWORD *)(v5 + 8 * v4 + 16) = 0 )
  {
    v4 = 3 * i;
    PropVariantClear((PROPVARIANT *)(*((_QWORD *)this + 9) + 24 * i));
    v5 = *((_QWORD *)this + 9);
    i = (unsigned int)(i + 1);
    *(_OWORD *)(v5 + 8 * v4) = 0;
  }
  InMemoryRegRow::ClearPropertyBag(this);
  (*(void (__fastcall **)(InMemoryRegRow *, _QWORD))(*(_QWORD *)this + 80LL))(this, 0);
  CoTaskMemFree(*((LPVOID *)this + 2));
  CoTaskMemFree(*((LPVOID *)this + 9));
  *((_QWORD *)this + 9) = 0;
  Map<unsigned short *,InMemoryRegRow::MapPropertyBag *,InMemoryRegRow::HashCaseInsentitiveWSTR,InMemoryRegRow::CNonFailFastingAllocator>::~Map<unsigned short *,InMemoryRegRow::MapPropertyBag *,InMemoryRegRow::HashCaseInsentitiveWSTR,InMemoryRegRow::CNonFailFastingAllocator>((char *)this + 80);
  *(_QWORD *)this = &RegRow::`vftable';
  UTSemReadWriteES::~UTSemReadWriteES((InMemoryRegRow *)((char *)this + 24));
}

```

## disassembly

```asm
0x18001ebf8  mov     [rsp+arg_0], rbx
0x18001ebfd  mov     [rsp+arg_8], rsi
0x18001ec02  push    rdi
0x18001ec03  sub     rsp, 20h
0x18001ec07  lea     rax, ??_7InMemoryRegRow@@6B@; const InMemoryRegRow::`vftable'
0x18001ec0e  mov     rdi, rcx
0x18001ec11  mov     [rcx], rax
0x18001ec14  mov     rcx, [rcx+38h]
0x18001ec18  test    rcx, rcx
0x18001ec1b  jnz     loc_18001ECB3
0x18001ec21  xor     esi, esi
0x18001ec23  cmp     [rdi+40h], esi
0x18001ec26  jbe     short loc_18001EC53
0x18001ec28  mov     rax, [rdi+48h]
0x18001ec2c  lea     rbx, [rsi+rsi*2]
0x18001ec30  lea     rcx, [rax+rbx*8]; pvar
0x18001ec34  call    cs:__imp_PropVariantClear
0x18001ec3a  mov     rax, [rdi+48h]
0x18001ec3e  xor     ecx, ecx
0x18001ec40  xorps   xmm0, xmm0
0x18001ec43  inc     esi
0x18001ec45  movups  xmmword ptr [rax+rbx*8], xmm0
0x18001ec49  mov     [rax+rbx*8+10h], rcx
0x18001ec4e  cmp     esi, [rdi+40h]
0x18001ec51  jb      short loc_18001EC28
0x18001ec53  mov     rcx, rdi; this
0x18001ec56  call    ?ClearPropertyBag@InMemoryRegRow@@AEAAXXZ; InMemoryRegRow::ClearPropertyBag(void)
0x18001ec5b  mov     rax, [rdi]
0x18001ec5e  xor     edx, edx
0x18001ec60  mov     rcx, rdi
0x18001ec63  mov     rax, [rax+50h]
0x18001ec67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec6c  mov     rcx, [rdi+10h]; pv
0x18001ec70  call    cs:__imp_CoTaskMemFree
0x18001ec76  mov     rcx, [rdi+48h]; pv
0x18001ec7a  call    cs:__imp_CoTaskMemFree
0x18001ec80  lea     rcx, [rdi+50h]
0x18001ec84  mov     qword ptr [rdi+48h], 0
0x18001ec8c  call    ??1?$Map@PEAGPEAUMapPropertyBag@InMemoryRegRow@@VHashCaseInsentitiveWSTR@2@VCNonFailFastingAllocator@2@@@QEAA@XZ; Map<ushort *,InMemoryRegRow::MapPropertyBag *,InMemoryRegRow::HashCaseInsentitiveWSTR,InMemoryRegRow::CNonFailFastingAllocator>::~Map<ushort *,InMemoryRegRow::MapPropertyBag *,InMemoryRegRow::HashCaseInsentitiveWSTR,InMemoryRegRow::CNonFailFastingAllocator>(void)
0x18001ec91  lea     rax, ??_7RegRow@@6B@; const RegRow::`vftable'
0x18001ec98  lea     rcx, [rdi+18h]; this
0x18001ec9c  mov     [rdi], rax
0x18001ec9f  mov     rbx, [rsp+28h+arg_0]
0x18001eca4  mov     rsi, [rsp+28h+arg_8]
0x18001eca9  add     rsp, 20h
0x18001ecad  pop     rdi
0x18001ecae  jmp     ??1UTSemReadWriteES@@QEAA@XZ; UTSemReadWriteES::~UTSemReadWriteES(void)
0x18001ecb3  mov     rax, [rcx]
0x18001ecb6  mov     rdx, rdi
0x18001ecb9  mov     rax, [rax+38h]
0x18001ecbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ecc2  mov     rcx, [rdi+38h]
0x18001ecc6  mov     rax, [rcx]
0x18001ecc9  mov     rax, [rax+10h]
0x18001eccd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ecd2  mov     qword ptr [rdi+38h], 0
0x18001ecda  jmp     loc_18001EC21
```
