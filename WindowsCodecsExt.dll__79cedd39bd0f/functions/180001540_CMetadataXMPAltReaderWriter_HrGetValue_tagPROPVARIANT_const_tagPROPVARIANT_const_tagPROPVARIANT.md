# CMetadataXMPAltReaderWriter::HrGetValue(tagPROPVARIANT const *,tagPROPVARIANT const *,tagPROPVARIANT *)

- ea: `0x180001540`
- end: `0x180001628`
- name: `?HrGetValue@CMetadataXMPAltReaderWriter@@UEAAJPEBUtagPROPVARIANT@@0PEAU2@@Z`
- size: `232`
- prototype: `int(CMetadataXMPAltReaderWriter *__hidden this, const struct tagPROPVARIANT *, const struct tagPROPVARIANT *, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180001540`
- `0x180001b50`
- `0x1800027e0`
- `0x1800171c4`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall CMetadataXMPAltReaderWriter::HrGetValue(
        CMetadataXMPAltReaderWriter *this,
        const struct tagPROPVARIANT *a2,
        const struct tagPROPVARIANT *a3,
        PROPVARIANT *a4)
{
  struct tagPROPVARIANT *v4; // rsi
  const struct tagPROPVARIANT *v5; // rbx
  CMetadataXMPAltReaderWriter *v6; // rdi
  int Value; // eax
  unsigned int v8; // ebx
  __int128 v10; // [rsp+30h] [rbp-38h] BYREF
  __int64 v11; // [rsp+40h] [rbp-28h]
  __int128 v12; // [rsp+48h] [rbp-20h] BYREF
  __int64 v13; // [rsp+58h] [rbp-10h]
  unsigned __int16 v14; // [rsp+80h] [rbp+18h] BYREF

  v14 = 0;
  v10 = 0;
  v11 = 0;
  v4 = (struct tagPROPVARIANT *)a4;
  v12 = 0;
  v13 = 0;
  v5 = a3;
  v6 = this;
  if ( a3->vt != 72 )
  {
    if ( CMetadataHandler::CoerceVariantToUShort(this, a3, &v14) >= 0 )
    {
      Value = (*(__int64 (__fastcall **)(CMetadataXMPAltReaderWriter *, _QWORD, _QWORD, _QWORD, struct tagPROPVARIANT *))(*(_QWORD *)v6 + 168LL))(
                v6,
                v14,
                0,
                0,
                v4);
      goto LABEL_3;
    }
    if ( !v5->vt )
    {
      LOWORD(v10) = 31;
      *((_QWORD *)&v10 + 1) = L"x-default";
    }
    a3 = (const struct tagPROPVARIANT *)&v10;
    a2 = (const struct tagPROPVARIANT *)&v12;
    a4 = (PROPVARIANT *)v4;
    this = v6;
    if ( v5->vt )
      a3 = v5;
  }
  Value = CMetadataRDFReaderWriter::HrGetValue(this, a2, a3, a4);
LABEL_3:
  v8 = Value;
  if ( Value < 0 && g_doStackCaptures )
    DoStackCapture(Value);
  return v8;
}

```

## disassembly

```asm
0x180001540  mov     r11, rsp
0x180001543  mov     [r11+8], rbx
0x180001547  mov     [r11+10h], rsi
0x18000154b  push    rdi
0x18000154c  sub     rsp, 60h
0x180001550  xor     eax, eax
0x180001552  xorps   xmm0, xmm0
0x180001555  xorps   xmm1, xmm1
0x180001558  mov     [r11+18h], ax
0x18000155d  movups  [rsp+68h+var_38], xmm0
0x180001562  mov     [r11-28h], rax
0x180001566  mov     rsi, r9
0x180001569  movups  [rsp+68h+var_20], xmm1
0x18000156e  mov     [r11-10h], rax
0x180001572  mov     rbx, r8
0x180001575  mov     eax, 48h ; 'H'
0x18000157a  mov     rdi, rcx
0x18000157d  cmp     ax, [r8]
0x180001581  jnz     short loc_1800015A9
0x180001583  call    ?HrGetValue@CMetadataRDFReaderWriter@@MEAAJPEBUtagPROPVARIANT@@0PEAU2@@Z; CMetadataRDFReaderWriter::HrGetValue(tagPROPVARIANT const *,tagPROPVARIANT const *,tagPROPVARIANT *)
0x180001588  mov     ebx, eax
0x18000158a  test    eax, eax
0x18000158c  jns     short loc_180001597
0x18000158e  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180001595  jnz     short loc_1800015E4
0x180001597  mov     rsi, [rsp+68h+arg_8]
0x18000159c  mov     eax, ebx
0x18000159e  mov     rbx, [rsp+68h+arg_0]
0x1800015a3  add     rsp, 60h
0x1800015a7  pop     rdi
0x1800015a8  retn
0x1800015a9  lea     r8, [rsp+68h+arg_10]; unsigned __int16 *
0x1800015b1  mov     rdx, rbx; struct tagPROPVARIANT *
0x1800015b4  call    ?CoerceVariantToUShort@CMetadataHandler@@IEAAJPEBUtagPROPVARIANT@@PEAG@Z; CMetadataHandler::CoerceVariantToUShort(tagPROPVARIANT const *,ushort *)
0x1800015b9  test    eax, eax
0x1800015bb  js      short loc_1800015ED
0x1800015bd  mov     rax, [rdi]
0x1800015c0  xor     r9d, r9d
0x1800015c3  movzx   edx, [rsp+68h+arg_10]
0x1800015cb  xor     r8d, r8d
0x1800015ce  mov     rcx, rdi
0x1800015d1  mov     [rsp+68h+var_48], rsi
0x1800015d6  mov     rax, [rax+0A8h]
0x1800015dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800015e2  jmp     short loc_180001588
0x1800015e4  mov     ecx, eax; int
0x1800015e6  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800015eb  jmp     short loc_180001597
0x1800015ed  xor     eax, eax
0x1800015ef  cmp     ax, [rbx]
0x1800015f2  jnz     short loc_18000160A
0x1800015f4  mov     eax, 1Fh
0x1800015f9  mov     word ptr [rsp+68h+var_38], ax
0x1800015fe  lea     rax, aXDefault; "x-default"
0x180001605  mov     qword ptr [rsp+68h+var_38+8], rax
0x18000160a  xor     eax, eax
0x18000160c  lea     r8, [rsp+68h+var_38]
0x180001611  cmp     ax, [rbx]
0x180001614  lea     rdx, [rsp+68h+var_20]
0x180001619  mov     r9, rsi
0x18000161c  mov     rcx, rdi
0x18000161f  cmovnz  r8, rbx
0x180001623  jmp     loc_180001583
```
