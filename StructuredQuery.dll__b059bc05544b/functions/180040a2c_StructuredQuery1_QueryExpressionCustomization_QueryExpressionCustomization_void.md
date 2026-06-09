# StructuredQuery1::QueryExpressionCustomization::~QueryExpressionCustomization(void)

- ea: `0x180040a2c`
- end: `0x180040ac7`
- name: `??1QueryExpressionCustomization@StructuredQuery1@@AEAA@XZ`
- size: `155`
- prototype: `void __fastcall(StructuredQuery1::QueryExpressionCustomization *this, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x180040990`

## callees

- `0x18001b2b4`
- `0x180040a2c`
- `0x180040de4`
- `0x180040e10`
- `0x180040e60`
- `0x18005db14`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040a72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040a83`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040a72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040a83`

## pseudocode

```c
void __fastcall StructuredQuery1::QueryExpressionCustomization::~QueryExpressionCustomization(
        StructuredQuery1::QueryExpressionCustomization *this,
        unsigned int a2)
{
  StructuredQuery1::PseudoPropertyList *v3; // rcx
  StructuredQuery1::DefaultPropertyList *v4; // rcx
  StructuredQuery1::TypeHandlerList *v5; // rcx
  __int64 i; // rdi

  *(_QWORD *)this = &StructuredQuery1::QueryExpressionCustomization::`vftable';
  v3 = (StructuredQuery1::PseudoPropertyList *)*((_QWORD *)this + 1);
  if ( v3 )
    StructuredQuery1::PseudoPropertyList::`scalar deleting destructor'(v3, a2);
  v4 = (StructuredQuery1::DefaultPropertyList *)*((_QWORD *)this + 2);
  if ( v4 )
    StructuredQuery1::DefaultPropertyList::`scalar deleting destructor'(v4, a2);
  v5 = (StructuredQuery1::TypeHandlerList *)*((_QWORD *)this + 3);
  if ( v5 )
    StructuredQuery1::TypeHandlerList::`scalar deleting destructor'(v5, a2);
  for ( i = 0; (unsigned int)i < *((_DWORD *)this + 11); i = (unsigned int)(i + 1) )
    CoTaskMemFree(*(LPVOID *)(*((_QWORD *)this + 4) + 40 * i + 24));
  CoTaskMemFree(*((LPVOID *)this + 4));
  IUnknown_SafeReleaseAndNullPtr<GrowableBuffer<tagHITRANGE>>((_QWORD *)this + 6);
  operator delete(*((void **)this + 7), (const struct std::nothrow_t *)0xAC);
  _InterlockedDecrement(&dword_1800B134C);
}

```

## disassembly

```asm
0x180040a2c  mov     [rsp+arg_0], rbx
0x180040a31  push    rdi
0x180040a32  sub     rsp, 20h
0x180040a36  mov     rbx, rcx
0x180040a39  lea     rax, ??_7QueryExpressionCustomization@StructuredQuery1@@6B@; const StructuredQuery1::QueryExpressionCustomization::`vftable'
0x180040a40  mov     [rcx], rax
0x180040a43  mov     rcx, [rcx+8]; this
0x180040a47  test    rcx, rcx
0x180040a4a  jnz     short loc_180040AC0
0x180040a4c  mov     rcx, [rbx+10h]; this
0x180040a50  test    rcx, rcx
0x180040a53  jnz     short loc_180040AB2
0x180040a55  mov     rcx, [rbx+18h]; this
0x180040a59  test    rcx, rcx
0x180040a5c  jnz     short loc_180040AB9
0x180040a5e  xor     edi, edi
0x180040a60  cmp     [rbx+2Ch], edi
0x180040a63  jbe     short loc_180040A7F
0x180040a65  lea     rdx, [rdi+rdi*4]
0x180040a69  mov     rcx, [rbx+20h]
0x180040a6d  mov     rcx, [rcx+rdx*8+18h]; pv
0x180040a72  call    cs:__imp_CoTaskMemFree
0x180040a78  inc     edi
0x180040a7a  cmp     edi, [rbx+2Ch]
0x180040a7d  jb      short loc_180040A65
0x180040a7f  mov     rcx, [rbx+20h]; pv
0x180040a83  call    cs:__imp_CoTaskMemFree
0x180040a89  lea     rcx, [rbx+30h]
0x180040a8d  call    ??$IUnknown_SafeReleaseAndNullPtr@V?$GrowableBuffer@UtagHITRANGE@@@@@@YAXAEAPEAV?$GrowableBuffer@UtagHITRANGE@@@@@Z; IUnknown_SafeReleaseAndNullPtr<GrowableBuffer<tagHITRANGE>>(GrowableBuffer<tagHITRANGE> * &)
0x180040a92  mov     edx, 0ACh; struct std::nothrow_t *
0x180040a97  mov     rcx, [rbx+38h]; void *
0x180040a9b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180040aa0  lock dec cs:dword_1800B134C
0x180040aa7  mov     rbx, [rsp+28h+arg_0]
0x180040aac  add     rsp, 20h
0x180040ab0  pop     rdi
0x180040ab1  retn
0x180040ab2  call    ??_GDefaultPropertyList@StructuredQuery1@@QEAAPEAXI@Z; StructuredQuery1::DefaultPropertyList::`scalar deleting destructor'(uint)
0x180040ab7  jmp     short loc_180040A55
0x180040ab9  call    ??_GTypeHandlerList@StructuredQuery1@@QEAAPEAXI@Z; StructuredQuery1::TypeHandlerList::`scalar deleting destructor'(uint)
0x180040abe  jmp     short loc_180040A5E
0x180040ac0  call    ??_GPseudoPropertyList@StructuredQuery1@@QEAAPEAXI@Z; StructuredQuery1::PseudoPropertyList::`scalar deleting destructor'(uint)
0x180040ac5  jmp     short loc_180040A4C
```
