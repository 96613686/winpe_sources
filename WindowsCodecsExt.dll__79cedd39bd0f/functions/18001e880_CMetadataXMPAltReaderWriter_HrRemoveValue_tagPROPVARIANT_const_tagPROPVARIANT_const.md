# CMetadataXMPAltReaderWriter::HrRemoveValue(tagPROPVARIANT const *,tagPROPVARIANT const *)

- ea: `0x18001e880`
- end: `0x18001e941`
- name: `?HrRemoveValue@CMetadataXMPAltReaderWriter@@UEAAJPEBUtagPROPVARIANT@@0@Z`
- size: `193`
- prototype: `__int64 __fastcall(CMetadataXMPAltReaderWriter *__hidden this, const struct tagPROPVARIANT *, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x1800027e0`
- `0x1800171c4`
- `0x18001e880`
- `0x18001e950`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall CMetadataXMPAltReaderWriter::HrRemoveValue(
        CMetadataXMPAltReaderWriter *this,
        const struct tagPROPVARIANT *a2,
        const struct tagPROPVARIANT *a3)
{
  const struct tagPROPVARIANT *v3; // rbx
  CMetadataXMPAltReaderWriter *v4; // rdi
  int v5; // eax
  bool v6; // zf
  unsigned int v7; // ebx
  __int128 v9; // [rsp+20h] [rbp-38h] BYREF
  __int64 v10; // [rsp+30h] [rbp-28h]
  tagPROPVARIANT v11; // [rsp+38h] [rbp-20h] BYREF
  unsigned __int16 v12; // [rsp+70h] [rbp+18h] BYREF

  v12 = 0;
  v3 = a3;
  v9 = 0;
  v10 = 0;
  v4 = this;
  memset(&v11, 0, sizeof(v11));
  if ( a3->vt == 72 )
  {
LABEL_9:
    v5 = CMetadataRDFReaderWriter::HrRemoveValue(this, a2, a3);
    goto LABEL_10;
  }
  if ( CMetadataHandler::CoerceVariantToUShort(this, a3, &v12) < 0 )
  {
    v6 = v3->vt == 0;
    if ( !v3->vt )
    {
      LOWORD(v9) = 31;
      *((_QWORD *)&v9 + 1) = L"x-default";
    }
    a3 = (const struct tagPROPVARIANT *)&v9;
    this = v4;
    if ( !v6 )
      a3 = v3;
    a2 = &v11;
    goto LABEL_9;
  }
  v5 = (*(__int64 (__fastcall **)(CMetadataXMPAltReaderWriter *, _QWORD))(*(_QWORD *)v4 + 200LL))(v4, v12);
LABEL_10:
  v7 = v5;
  if ( v5 < 0 && g_doStackCaptures )
    DoStackCapture(v5);
  return v7;
}

```

## disassembly

```asm
0x18001e880  mov     r11, rsp
0x18001e883  mov     [r11+8], rbx
0x18001e887  mov     [r11+10h], rsi
0x18001e88b  push    rdi
0x18001e88c  sub     rsp, 50h
0x18001e890  xor     eax, eax
0x18001e892  xor     esi, esi
0x18001e894  xorps   xmm0, xmm0
0x18001e897  mov     [rsp+58h+arg_10], si
0x18001e89c  xorps   xmm1, xmm1
0x18001e89f  mov     rbx, r8
0x18001e8a2  movups  [rsp+58h+var_38], xmm0
0x18001e8a7  mov     [r11-28h], rax
0x18001e8ab  mov     rdi, rcx
0x18001e8ae  movups  xmmword ptr [rsp+58h+var_20], xmm1
0x18001e8b3  mov     [r11-10h], rax
0x18001e8b7  lea     eax, [rsi+48h]
0x18001e8ba  cmp     ax, [r8]
0x18001e8be  jz      short loc_18001E915
0x18001e8c0  lea     r8, [r11+18h]; unsigned __int16 *
0x18001e8c4  mov     rdx, rbx; struct tagPROPVARIANT *
0x18001e8c7  call    ?CoerceVariantToUShort@CMetadataHandler@@IEAAJPEBUtagPROPVARIANT@@PEAG@Z; CMetadataHandler::CoerceVariantToUShort(tagPROPVARIANT const *,ushort *)
0x18001e8cc  test    eax, eax
0x18001e8ce  js      short loc_18001E8E9
0x18001e8d0  mov     rax, [rdi]
0x18001e8d3  mov     rcx, rdi
0x18001e8d6  movzx   edx, [rsp+58h+arg_10]
0x18001e8db  mov     rax, [rax+0C8h]
0x18001e8e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e8e7  jmp     short loc_18001E91A
0x18001e8e9  cmp     [rbx], si
0x18001e8ec  jnz     short loc_18001E904
0x18001e8ee  mov     eax, 1Fh
0x18001e8f3  mov     word ptr [rsp+58h+var_38], ax
0x18001e8f8  lea     rax, aXDefault; "x-default"
0x18001e8ff  mov     qword ptr [rsp+58h+var_38+8], rax
0x18001e904  lea     r8, [rsp+58h+var_38]
0x18001e909  mov     rcx, rdi; this
0x18001e90c  cmovnz  r8, rbx; struct tagPROPVARIANT *
0x18001e910  lea     rdx, [rsp+58h+var_20]; struct tagPROPVARIANT *
0x18001e915  call    ?HrRemoveValue@CMetadataRDFReaderWriter@@MEAAJPEBUtagPROPVARIANT@@0@Z; CMetadataRDFReaderWriter::HrRemoveValue(tagPROPVARIANT const *,tagPROPVARIANT const *)
0x18001e91a  mov     ebx, eax
0x18001e91c  test    eax, eax
0x18001e91e  jns     short loc_18001E92F
0x18001e920  cmp     cs:?g_doStackCaptures@@3HA, esi; int g_doStackCaptures
0x18001e926  jz      short loc_18001E92F
0x18001e928  mov     ecx, eax; int
0x18001e92a  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18001e92f  mov     rsi, [rsp+58h+arg_8]
0x18001e934  mov     eax, ebx
0x18001e936  mov     rbx, [rsp+58h+arg_0]
0x18001e93b  add     rsp, 50h
0x18001e93f  pop     rdi
0x18001e940  retn
```
