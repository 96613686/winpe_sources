# CMetadataRDFIndexReaderWriter::HrRemoveValue(tagPROPVARIANT const *,tagPROPVARIANT const *)

- ea: `0x180024a30`
- end: `0x180024ac9`
- name: `?HrRemoveValue@CMetadataRDFIndexReaderWriter@@UEAAJPEBUtagPROPVARIANT@@0@Z`
- size: `153`
- prototype: `__int64 __fastcall(CMetadataRDFIndexReaderWriter *__hidden this, const struct tagPROPVARIANT *, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x1800027e0`
- `0x1800171c4`
- `0x18001e950`
- `0x180024a30`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall CMetadataRDFIndexReaderWriter::HrRemoveValue(
        CMetadataRDFIndexReaderWriter *this,
        const struct tagPROPVARIANT *a2,
        const struct tagPROPVARIANT *a3)
{
  CMetadataRDFIndexReaderWriter *v5; // rdi
  __int64 v6; // rax
  __int64 v7; // rdx
  int v8; // eax
  unsigned int v9; // ebx
  int v10; // ecx
  unsigned __int16 v12; // [rsp+60h] [rbp+18h] BYREF

  v5 = this;
  v12 = 0;
  if ( !a3->vt )
  {
    v6 = *(_QWORD *)this;
    v7 = 0;
    goto LABEL_3;
  }
  if ( CMetadataHandler::CoerceVariantToUShort(this, a3, &v12) >= 0 )
  {
    v6 = *(_QWORD *)v5;
    this = v5;
    v7 = v12;
LABEL_3:
    v8 = (*(__int64 (__fastcall **)(CMetadataRDFIndexReaderWriter *, __int64))(v6 + 200))(this, v7);
    v9 = v8;
    if ( v8 >= 0 || !g_doStackCaptures )
      return v9;
    v10 = v8;
    goto LABEL_12;
  }
  if ( a3->vt == 72 )
    return CMetadataRDFReaderWriter::HrRemoveValue(v5, a2, a3);
  v9 = -2147024809;
  if ( g_doStackCaptures )
  {
    v10 = -2147024809;
LABEL_12:
    DoStackCapture(v10);
  }
  return v9;
}

```

## disassembly

```asm
0x180024a30  push    rbx
0x180024a32  push    rbp
0x180024a33  push    rsi
0x180024a34  push    rdi
0x180024a35  sub     rsp, 28h
0x180024a39  xor     ebp, ebp
0x180024a3b  mov     rbx, r8
0x180024a3e  mov     rsi, rdx
0x180024a41  mov     rdi, rcx
0x180024a44  mov     [rsp+48h+arg_10], bp
0x180024a49  cmp     [r8], bp
0x180024a4d  jnz     short loc_180024A72
0x180024a4f  mov     rax, [rcx]
0x180024a52  xor     edx, edx
0x180024a54  mov     rax, [rax+0C8h]
0x180024a5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024a60  mov     ebx, eax
0x180024a62  test    eax, eax
0x180024a64  jns     short loc_180024ABE
0x180024a66  cmp     cs:?g_doStackCaptures@@3HA, ebp; int g_doStackCaptures
0x180024a6c  jz      short loc_180024ABE
0x180024a6e  mov     ecx, eax; this
0x180024a70  jmp     short loc_180024AB9
0x180024a72  lea     r8, [rsp+48h+arg_10]; unsigned __int16 *
0x180024a77  mov     rdx, rbx; struct tagPROPVARIANT *
0x180024a7a  call    ?CoerceVariantToUShort@CMetadataHandler@@IEAAJPEBUtagPROPVARIANT@@PEAG@Z; CMetadataHandler::CoerceVariantToUShort(tagPROPVARIANT const *,ushort *)
0x180024a7f  test    eax, eax
0x180024a81  js      short loc_180024A90
0x180024a83  mov     rax, [rdi]
0x180024a86  mov     rcx, rdi
0x180024a89  movzx   edx, [rsp+48h+arg_10]
0x180024a8e  jmp     short loc_180024A54
0x180024a90  mov     eax, 48h ; 'H'
0x180024a95  cmp     ax, [rbx]
0x180024a98  jnz     short loc_180024AAA
0x180024a9a  mov     r8, rbx; struct tagPROPVARIANT *
0x180024a9d  mov     rdx, rsi; struct tagPROPVARIANT *
0x180024aa0  mov     rcx, rdi; this
0x180024aa3  call    ?HrRemoveValue@CMetadataRDFReaderWriter@@MEAAJPEBUtagPROPVARIANT@@0@Z; CMetadataRDFReaderWriter::HrRemoveValue(tagPROPVARIANT const *,tagPROPVARIANT const *)
0x180024aa8  jmp     short loc_180024AC0
0x180024aaa  cmp     cs:?g_doStackCaptures@@3HA, ebp; int g_doStackCaptures
0x180024ab0  mov     ebx, 80070057h
0x180024ab5  jz      short loc_180024ABE
0x180024ab7  mov     ecx, ebx; int
0x180024ab9  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180024abe  mov     eax, ebx
0x180024ac0  add     rsp, 28h
0x180024ac4  pop     rdi
0x180024ac5  pop     rsi
0x180024ac6  pop     rbp
0x180024ac7  pop     rbx
0x180024ac8  retn
```
