# CMetadataRDFIndexReaderWriter::HrSetValue(tagPROPVARIANT const *,tagPROPVARIANT const *,tagPROPVARIANT const *)

- ea: `0x180024ad0`
- end: `0x180024bbc`
- name: `?HrSetValue@CMetadataRDFIndexReaderWriter@@UEAAJPEBUtagPROPVARIANT@@00@Z`
- size: `236`
- prototype: `__int64 __fastcall(CMetadataRDFIndexReaderWriter *__hidden this, const struct tagPROPVARIANT *, const struct tagPROPVARIANT *, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180001630`
- `0x1800027e0`
- `0x1800171c4`
- `0x180024ad0`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall CMetadataRDFIndexReaderWriter::HrSetValue(
        CMetadataRDFIndexReaderWriter *this,
        const struct tagPROPVARIANT *a2,
        const struct tagPROPVARIANT *a3,
        struct tagPROPVARIANT *a4)
{
  CMetadataRDFIndexReaderWriter *v7; // rbx
  unsigned int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // rax
  int v11; // eax
  unsigned int v12; // ebx
  int v13; // ecx
  __int128 v15; // [rsp+30h] [rbp-38h] BYREF
  __int64 v16; // [rsp+40h] [rbp-28h]
  unsigned __int16 v17; // [rsp+80h] [rbp+18h] BYREF

  v7 = this;
  v17 = 0;
  v15 = 0;
  v16 = 0;
  if ( a3->vt )
  {
    if ( CMetadataHandler::CoerceVariantToUShort(this, a3, &v17) >= 0 )
    {
      v10 = *(_QWORD *)v7;
      this = v7;
      v9 = v17;
LABEL_4:
      v11 = (*(__int64 (__fastcall **)(CMetadataRDFIndexReaderWriter *, __int64, _QWORD, __int128 *, struct tagPROPVARIANT *))(v10 + 184))(
              this,
              v9,
              0,
              &v15,
              a4);
      v12 = v11;
      if ( v11 >= 0 || !g_doStackCaptures )
        return v12;
      v13 = v11;
      goto LABEL_15;
    }
    if ( a3->vt == 72 )
      return CMetadataRDFReaderWriter::HrSetValue(v7, a2, a3, a4);
    v12 = -2147024809;
  }
  else
  {
    v8 = *((_DWORD *)this + 43);
    if ( v8 <= 0xFFFF )
    {
      v9 = (unsigned __int16)v8;
      v10 = *(_QWORD *)this;
      goto LABEL_4;
    }
    v12 = -2147024362;
  }
  if ( g_doStackCaptures )
  {
    v13 = v12;
LABEL_15:
    DoStackCapture(v13);
  }
  return v12;
}

```

## disassembly

```asm
0x180024ad0  mov     r11, rsp
0x180024ad3  mov     [r11+8], rbx
0x180024ad7  mov     [r11+10h], rbp
0x180024adb  push    rsi
0x180024adc  push    rdi
0x180024add  push    r14
0x180024adf  sub     rsp, 50h
0x180024ae3  xor     eax, eax
0x180024ae5  xor     r14d, r14d
0x180024ae8  xorps   xmm0, xmm0
0x180024aeb  mov     rsi, r9
0x180024aee  mov     rdi, r8
0x180024af1  mov     rbp, rdx
0x180024af4  mov     rbx, rcx
0x180024af7  mov     [r11+18h], r14w
0x180024afc  movups  [rsp+68h+var_38], xmm0
0x180024b01  mov     [r11-28h], rax
0x180024b05  cmp     [r8], r14w
0x180024b09  jnz     short loc_180024B51
0x180024b0b  mov     eax, [rcx+0ACh]
0x180024b11  cmp     eax, 0FFFFh
0x180024b16  ja      short loc_180024B4A
0x180024b18  movzx   edx, ax
0x180024b1b  mov     rax, [rcx]
0x180024b1e  mov     rax, [rax+0B8h]
0x180024b25  lea     r9, [rsp+68h+var_38]
0x180024b2a  xor     r8d, r8d
0x180024b2d  mov     [rsp+68h+var_48], rsi
0x180024b32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024b37  mov     ebx, eax
0x180024b39  test    eax, eax
0x180024b3b  jns     short loc_180024BA7
0x180024b3d  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x180024b44  jz      short loc_180024BA7
0x180024b46  mov     ecx, eax; this
0x180024b48  jmp     short loc_180024BA2
0x180024b4a  mov     ebx, 80070216h
0x180024b4f  jmp     short loc_180024B97
0x180024b51  lea     r8, [rsp+68h+arg_10]; unsigned __int16 *
0x180024b59  mov     rdx, rdi; struct tagPROPVARIANT *
0x180024b5c  call    ?CoerceVariantToUShort@CMetadataHandler@@IEAAJPEBUtagPROPVARIANT@@PEAG@Z; CMetadataHandler::CoerceVariantToUShort(tagPROPVARIANT const *,ushort *)
0x180024b61  test    eax, eax
0x180024b63  js      short loc_180024B75
0x180024b65  mov     rax, [rbx]
0x180024b68  mov     rcx, rbx
0x180024b6b  movzx   edx, [rsp+68h+arg_10]
0x180024b73  jmp     short loc_180024B1E
0x180024b75  mov     eax, 48h ; 'H'
0x180024b7a  cmp     ax, [rdi]
0x180024b7d  jnz     short loc_180024B92
0x180024b7f  mov     r9, rsi; struct tagPROPVARIANT *
0x180024b82  mov     r8, rdi; struct tagPROPVARIANT *
0x180024b85  mov     rdx, rbp; struct tagPROPVARIANT *
0x180024b88  mov     rcx, rbx; this
0x180024b8b  call    ?HrSetValue@CMetadataRDFReaderWriter@@MEAAJPEBUtagPROPVARIANT@@00@Z; CMetadataRDFReaderWriter::HrSetValue(tagPROPVARIANT const *,tagPROPVARIANT const *,tagPROPVARIANT const *)
0x180024b90  jmp     short loc_180024BA9
0x180024b92  mov     ebx, 80070057h
0x180024b97  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x180024b9e  jz      short loc_180024BA7
0x180024ba0  mov     ecx, ebx; int
0x180024ba2  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180024ba7  mov     eax, ebx
0x180024ba9  mov     rbx, [rsp+68h+arg_0]
0x180024bae  mov     rbp, [rsp+68h+arg_8]
0x180024bb3  add     rsp, 50h
0x180024bb7  pop     r14
0x180024bb9  pop     rdi
0x180024bba  pop     rsi
0x180024bbb  retn
```
