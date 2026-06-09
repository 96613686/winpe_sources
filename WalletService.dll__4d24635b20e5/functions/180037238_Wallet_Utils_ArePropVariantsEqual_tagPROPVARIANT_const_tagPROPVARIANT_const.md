# Wallet::Utils::ArePropVariantsEqual(tagPROPVARIANT const &,tagPROPVARIANT const &)

- ea: `0x180037238`
- end: `0x180037308`
- name: `?ArePropVariantsEqual@Utils@Wallet@@YAHAEBUtagPROPVARIANT@@0@Z`
- size: `208`
- prototype: `__int64 __fastcall(Wallet::Utils *__hidden this, const struct tagPROPVARIANT *, const struct tagPROPVARIANT *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800222bc`
- `0x180027870`

## callees

- `0x180037238`
- `0x18004302e`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800372a3`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800372a3`

## pseudocode

```c
__int64 __fastcall Wallet::Utils::ArePropVariantsEqual(
        Wallet::Utils *this,
        const struct tagPROPVARIANT *a2,
        const struct tagPROPVARIANT *a3)
{
  int v3; // eax
  unsigned int v4; // r8d
  unsigned int v5; // eax
  LONG v6; // eax
  bool v7; // zf
  unsigned __int16 *v8; // rax
  LONGLONG v9; // r8
  int v10; // ecx
  int v11; // edx

  v3 = *(unsigned __int16 *)this;
  v4 = 0;
  if ( (_WORD)v3 != a2->vt )
    return v4;
  switch ( v3 )
  {
    case 5:
      if ( *((double *)this + 1) != a2->dblVal )
        return v4;
      return 1;
    case 8:
      v8 = (unsigned __int16 *)*((_QWORD *)this + 1);
      v9 = a2->hVal.QuadPart - (_QWORD)v8;
      do
      {
        v10 = *(unsigned __int16 *)((char *)v8 + v9);
        v11 = *v8 - v10;
        if ( v11 )
          break;
        ++v8;
      }
      while ( v10 );
      v4 = 0;
      v7 = v11 == 0;
      goto LABEL_18;
    case 21:
      v7 = *((_QWORD *)this + 1) == a2->hVal.QuadPart;
      goto LABEL_18;
    case 22:
      v7 = *((_DWORD *)this + 2) == a2->lVal;
      goto LABEL_18;
    case 64:
      v6 = CompareFileTime((const FILETIME *)this + 1, &a2->filetime);
      v4 = 0;
      v7 = v6 == 0;
LABEL_18:
      LOBYTE(v4) = v7;
      return v4;
    case 65:
      v5 = *((_DWORD *)this + 2);
      return v5 == a2->lVal && !memcmp_0(*((const void **)this + 2), a2->bstrblobVal.pData, v5);
  }
  return v4;
}

```

## disassembly

```asm
0x180037238  sub     rsp, 28h
0x18003723c  movzx   eax, word ptr [rcx]
0x18003723f  xor     r8d, r8d
0x180037242  cmp     ax, [rdx]
0x180037245  jnz     loc_180037300
0x18003724b  mov     r9d, eax
0x18003724e  sub     r9d, 5
0x180037252  jz      loc_1800372EC
0x180037258  sub     r9d, 3
0x18003725c  jz      short loc_1800372C2
0x18003725e  sub     r9d, 0Dh
0x180037262  jz      short loc_1800372B8
0x180037264  sub     r9d, 1
0x180037268  jz      short loc_1800372B0
0x18003726a  sub     r9d, 2Ah ; '*'
0x18003726e  jz      short loc_18003729B
0x180037270  cmp     r9d, 1
0x180037274  jnz     loc_180037300
0x18003727a  mov     eax, [rcx+8]
0x18003727d  cmp     eax, [rdx+8]
0x180037280  jnz     short loc_180037296
0x180037282  mov     rdx, [rdx+10h]; Buf2
0x180037286  mov     r8d, eax; Size
0x180037289  mov     rcx, [rcx+10h]; Buf1
0x18003728d  call    memcmp_0
0x180037292  test    eax, eax
0x180037294  jz      short loc_1800372FA
0x180037296  xor     r8d, r8d
0x180037299  jmp     short loc_180037300
0x18003729b  add     rdx, 8; lpFileTime2
0x18003729f  add     rcx, 8; lpFileTime1
0x1800372a3  call    cs:__imp_CompareFileTime
0x1800372a9  xor     r8d, r8d
0x1800372ac  test    eax, eax
0x1800372ae  jmp     short loc_1800372E6
0x1800372b0  mov     eax, [rdx+8]
0x1800372b3  cmp     [rcx+8], eax
0x1800372b6  jmp     short loc_1800372E6
0x1800372b8  mov     rax, [rdx+8]
0x1800372bc  cmp     [rcx+8], rax
0x1800372c0  jmp     short loc_1800372E6
0x1800372c2  mov     rax, [rcx+8]
0x1800372c6  mov     r8, [rdx+8]
0x1800372ca  sub     r8, rax
0x1800372cd  movzx   edx, word ptr [rax]
0x1800372d0  movzx   ecx, word ptr [rax+r8]
0x1800372d5  sub     edx, ecx
0x1800372d7  jnz     short loc_1800372E1
0x1800372d9  add     rax, 2
0x1800372dd  test    ecx, ecx
0x1800372df  jnz     short loc_1800372CD
0x1800372e1  xor     r8d, r8d
0x1800372e4  test    edx, edx
0x1800372e6  setz    r8b
0x1800372ea  jmp     short loc_180037300
0x1800372ec  movsd   xmm0, qword ptr [rcx+8]
0x1800372f1  ucomisd xmm0, qword ptr [rdx+8]
0x1800372f6  jp      short loc_180037300
0x1800372f8  jnz     short loc_180037300
0x1800372fa  mov     r8d, 1
0x180037300  mov     eax, r8d
0x180037303  add     rsp, 28h
0x180037307  retn
```
