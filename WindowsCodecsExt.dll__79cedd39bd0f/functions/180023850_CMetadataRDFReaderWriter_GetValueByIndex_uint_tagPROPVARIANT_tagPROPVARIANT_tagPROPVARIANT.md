# CMetadataRDFReaderWriter::GetValueByIndex(uint,tagPROPVARIANT *,tagPROPVARIANT *,tagPROPVARIANT *)

- ea: `0x180023850`
- end: `0x1800238f4`
- name: `?GetValueByIndex@CMetadataRDFReaderWriter@@UEAAJIPEAUtagPROPVARIANT@@00@Z`
- size: `164`
- prototype: `__int64 __fastcall(CMetadataRDFReaderWriter *__hidden this, unsigned int, struct tagPROPVARIANT *, struct tagPROPVARIANT *, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800058c0`
- `0x18000f1d0`
- `0x1800171c4`
- `0x180023850`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall CMetadataRDFReaderWriter::GetValueByIndex(
        CMetadataRDFReaderWriter *this,
        unsigned int a2,
        struct tagPROPVARIANT *a3,
        struct tagPROPVARIANT *a4,
        struct tagPROPVARIANT *a5)
{
  struct tagPROPVARIANT *v9; // rdi
  unsigned int v10; // ebx
  char *v12; // [rsp+50h] [rbp+8h] BYREF

  v12 = (char *)this + 40;
  CMTALock::Enter((CMetadataRDFReaderWriter *)((char *)this + 40));
  v9 = a5;
  if ( a4 && a4->vt || a5 && a5->vt || a3 && a3->vt )
  {
    if ( g_doStackCaptures )
      DoStackCapture(-2147024809);
  }
  v10 = (*(__int64 (__fastcall **)(CMetadataRDFReaderWriter *, _QWORD, struct tagPROPVARIANT *, struct tagPROPVARIANT *, struct tagPROPVARIANT *))(*(_QWORD *)this + 168LL))(
          this,
          a2,
          a3,
          a4,
          v9);
  CGuard<CMTALock>::~CGuard<CMTALock>(&v12);
  return v10;
}

```

## disassembly

```asm
0x180023850  mov     [rsp+arg_8], rbx
0x180023855  mov     [rsp+arg_10], rbp
0x18002385a  push    rsi
0x18002385b  push    rdi
0x18002385c  push    r14
0x18002385e  sub     rsp, 30h
0x180023862  mov     r14, rcx
0x180023865  mov     rsi, r9
0x180023868  add     rcx, 28h ; '('; this
0x18002386c  mov     rbx, r8
0x18002386f  mov     [rsp+48h+arg_0], rcx
0x180023874  mov     ebp, edx
0x180023876  call    ?Enter@CMTALock@@QEAAXXZ; CMTALock::Enter(void)
0x18002387b  mov     rdi, [rsp+48h+arg_20]
0x180023880  xor     eax, eax
0x180023882  test    rsi, rsi
0x180023885  jz      short loc_1800238DE
0x180023887  cmp     [rsi], ax
0x18002388a  jz      short loc_1800238DE
0x18002388c  cmp     cs:?g_doStackCaptures@@3HA, eax; int g_doStackCaptures
0x180023892  jz      short loc_18002389E
0x180023894  mov     ecx, 80070057h; int
0x180023899  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18002389e  mov     rax, [r14]
0x1800238a1  mov     r9, rsi
0x1800238a4  mov     r8, rbx
0x1800238a7  mov     [rsp+48h+var_28], rdi
0x1800238ac  mov     edx, ebp
0x1800238ae  mov     rcx, r14
0x1800238b1  mov     rax, [rax+0A8h]
0x1800238b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800238bd  lea     rcx, [rsp+48h+arg_0]
0x1800238c2  mov     ebx, eax
0x1800238c4  call    ??1?$CGuard@VCMTALock@@@@QEAA@XZ; CGuard<CMTALock>::~CGuard<CMTALock>(void)
0x1800238c9  mov     rbp, [rsp+48h+arg_10]
0x1800238ce  mov     eax, ebx
0x1800238d0  mov     rbx, [rsp+48h+arg_8]
0x1800238d5  add     rsp, 30h
0x1800238d9  pop     r14
0x1800238db  pop     rdi
0x1800238dc  pop     rsi
0x1800238dd  retn
0x1800238de  test    rdi, rdi
0x1800238e1  jz      short loc_1800238E8
0x1800238e3  cmp     [rdi], ax
0x1800238e6  jnz     short loc_18002388C
0x1800238e8  test    rbx, rbx
0x1800238eb  jz      short loc_18002389E
0x1800238ed  cmp     [rbx], ax
0x1800238f0  jz      short loc_18002389E
0x1800238f2  jmp     short loc_18002388C
```
