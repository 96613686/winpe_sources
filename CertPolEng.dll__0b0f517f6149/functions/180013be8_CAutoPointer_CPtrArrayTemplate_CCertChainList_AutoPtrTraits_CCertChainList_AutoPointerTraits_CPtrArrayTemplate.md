# CAutoPointer<CPtrArrayTemplate<CCertChainList,AutoPtrTraits<CCertChainList>>,AutoPointerTraits<CPtrArrayTemplate<CCertChainList,AutoPtrTraits<CCertChainList>>>>::~CAutoPointer<CPtrArrayTemplate<CCertChainList,AutoPtrTraits<CCertChainList>>,AutoPointerTraits<CPtrArrayTemplate<CCertChainList,AutoPtrTraits<CCertChainList>>>>(void)

- ea: `0x180013be8`
- end: `0x180013c20`
- name: `??1?$CAutoPointer@V?$CPtrArrayTemplate@VCCertChainList@@U?$AutoPtrTraits@VCCertChainList@@@@@@U?$AutoPointerTraits@V?$CPtrArrayTemplate@VCCertChainList@@U?$AutoPtrTraits@VCCertChainList@@@@@@@@@@QEAA@XZ`
- size: `56`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18001aa74`

## callees

- `0x180013be8`
- `0x180013c28`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180013c08`
- `msvcrt!??3@YAXPEAX@Z` at `0x180013c08`

## pseudocode

```c
void __fastcall CAutoPointer<CPtrArrayTemplate<CCertChainList,AutoPtrTraits<CCertChainList>>,AutoPointerTraits<CPtrArrayTemplate<CCertChainList,AutoPtrTraits<CCertChainList>>>>::~CAutoPointer<CPtrArrayTemplate<CCertChainList,AutoPtrTraits<CCertChainList>>,AutoPointerTraits<CPtrArrayTemplate<CCertChainList,AutoPtrTraits<CCertChainList>>>>(
        _QWORD *a1)
{
  void *v1; // rbx

  v1 = (void *)*a1;
  if ( *a1 )
  {
    CPtrArrayTemplate<CCertChainList,AutoPtrTraits<CCertChainList>>::~CPtrArrayTemplate<CCertChainList,AutoPtrTraits<CCertChainList>>(*a1);
    operator delete(v1);
    *a1 = 0;
  }
}

```

## disassembly

```asm
0x180013be8  mov     [rsp+arg_0], rbx
0x180013bed  push    rdi
0x180013bee  sub     rsp, 20h
0x180013bf2  mov     rbx, [rcx]
0x180013bf5  mov     rdi, rcx
0x180013bf8  test    rbx, rbx
0x180013bfb  jz      short loc_180013C15
0x180013bfd  mov     rcx, rbx
0x180013c00  call    ??1?$CPtrArrayTemplate@VCCertChainList@@U?$AutoPtrTraits@VCCertChainList@@@@@@QEAA@XZ; CPtrArrayTemplate<CCertChainList,AutoPtrTraits<CCertChainList>>::~CPtrArrayTemplate<CCertChainList,AutoPtrTraits<CCertChainList>>(void)
0x180013c05  mov     rcx, rbx
0x180013c08  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180013c0e  mov     qword ptr [rdi], 0
0x180013c15  mov     rbx, [rsp+28h+arg_0]
0x180013c1a  add     rsp, 20h
0x180013c1e  pop     rdi
0x180013c1f  retn
```
