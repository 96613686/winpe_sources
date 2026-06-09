# HtmlDocForParsingSite::QueryInterface(_GUID const &,void * *)

- ea: `0x180009ae0`
- end: `0x180009bdd`
- name: `?QueryInterface@HtmlDocForParsingSite@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `253`
- prototype: `__int64 __fastcall(HtmlDocForParsingSite *this, const struct _GUID *, HtmlDocForParsingSite **)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180009bf0`
- `0x180009c00`
- `0x180009c10`
- `0x180009c20`

## callees

- `0x180009ae0`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall HtmlDocForParsingSite::QueryInterface(
        HtmlDocForParsingSite *this,
        const struct _GUID *a2,
        HtmlDocForParsingSite **a3)
{
  HtmlDocForParsingSite *v5; // rax
  unsigned __int64 v6; // rcx

  if ( !a3 )
    return 2147942487LL;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IUnknown.Data4
    || *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_00000118_0000_0000_c000_000000000046.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_00000118_0000_0000_c000_000000000046.Data4 )
  {
    v5 = this;
LABEL_21:
    *a3 = v5;
    (*(void (__fastcall **)(HtmlDocForParsingSite *))(*(_QWORD *)this + 8LL))(this);
    return 0;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_6d5140c1_7436_11ce_8034_00aa006009fa.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_6d5140c1_7436_11ce_8034_00aa006009fa.Data4 )
  {
    v6 = (unsigned __int64)this + 8;
LABEL_20:
    v5 = (HtmlDocForParsingSite *)(v6 & -(__int64)(this != 0));
    goto LABEL_21;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_c4d244b0_d43e_11cf_893b_00aa00bdce1a.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_c4d244b0_d43e_11cf_893b_00aa00bdce1a.Data4 )
  {
    v6 = (unsigned __int64)this + 16;
    goto LABEL_20;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_caeb5d28_ae4c_11d1_ba40_00c04fb92d79.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_caeb5d28_ae4c_11d1_ba40_00c04fb92d79.Data4 )
  {
    v6 = (unsigned __int64)this + 24;
    goto LABEL_20;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_00000003_0000_0000_c000_000000000046.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_00000003_0000_0000_c000_000000000046.Data4 )
  {
    v6 = (unsigned __int64)this + 32;
    goto LABEL_20;
  }
  *a3 = 0;
  return 2147500034LL;
}

```

## disassembly

```asm
0x180009ae0  sub     rsp, 28h
0x180009ae4  mov     r9, rcx
0x180009ae7  test    r8, r8
0x180009aea  jnz     short loc_180009AF6
0x180009aec  mov     eax, 80070057h
0x180009af1  jmp     loc_180009BD8
0x180009af6  mov     rax, [rdx]
0x180009af9  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x180009b00  jnz     short loc_180009B0F
0x180009b02  mov     rax, [rdx+8]
0x180009b06  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x180009b0d  jz      short loc_180009B28
0x180009b0f  mov     rax, [rdx]
0x180009b12  cmp     rax, qword ptr cs:_GUID_00000118_0000_0000_c000_000000000046.Data1
0x180009b19  jnz     short loc_180009B30
0x180009b1b  mov     rax, [rdx+8]
0x180009b1f  cmp     rax, qword ptr cs:_GUID_00000118_0000_0000_c000_000000000046.Data4
0x180009b26  jnz     short loc_180009B30
0x180009b28  mov     rax, r9
0x180009b2b  jmp     loc_180009BB6
0x180009b30  mov     rax, [rdx]
0x180009b33  cmp     rax, qword ptr cs:_GUID_6d5140c1_7436_11ce_8034_00aa006009fa.Data1
0x180009b3a  jnz     short loc_180009B4F
0x180009b3c  mov     rax, [rdx+8]
0x180009b40  cmp     rax, qword ptr cs:_GUID_6d5140c1_7436_11ce_8034_00aa006009fa.Data4
0x180009b47  jnz     short loc_180009B4F
0x180009b49  add     rcx, 8
0x180009b4d  jmp     short loc_180009BAA
0x180009b4f  mov     rax, [rdx]
0x180009b52  cmp     rax, qword ptr cs:_GUID_c4d244b0_d43e_11cf_893b_00aa00bdce1a.Data1
0x180009b59  jnz     short loc_180009B6E
0x180009b5b  mov     rax, [rdx+8]
0x180009b5f  cmp     rax, qword ptr cs:_GUID_c4d244b0_d43e_11cf_893b_00aa00bdce1a.Data4
0x180009b66  jnz     short loc_180009B6E
0x180009b68  add     rcx, 10h
0x180009b6c  jmp     short loc_180009BAA
0x180009b6e  mov     rax, [rdx]
0x180009b71  cmp     rax, qword ptr cs:_GUID_caeb5d28_ae4c_11d1_ba40_00c04fb92d79.Data1
0x180009b78  jnz     short loc_180009B8D
0x180009b7a  mov     rax, [rdx+8]
0x180009b7e  cmp     rax, qword ptr cs:_GUID_caeb5d28_ae4c_11d1_ba40_00c04fb92d79.Data4
0x180009b85  jnz     short loc_180009B8D
0x180009b87  add     rcx, 18h
0x180009b8b  jmp     short loc_180009BAA
0x180009b8d  mov     rax, [rdx]
0x180009b90  cmp     rax, qword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data1
0x180009b97  jnz     short loc_180009BCC
0x180009b99  mov     rax, [rdx+8]
0x180009b9d  cmp     rax, qword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4
0x180009ba4  jnz     short loc_180009BCC
0x180009ba6  add     rcx, 20h ; ' '
0x180009baa  mov     rax, r9
0x180009bad  neg     rax
0x180009bb0  sbb     rax, rax
0x180009bb3  and     rax, rcx
0x180009bb6  mov     [r8], rax
0x180009bb9  mov     rcx, r9
0x180009bbc  mov     rax, [r9]
0x180009bbf  mov     rax, [rax+8]
0x180009bc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bc8  xor     eax, eax
0x180009bca  jmp     short loc_180009BD8
0x180009bcc  mov     qword ptr [r8], 0
0x180009bd3  mov     eax, 80004002h
0x180009bd8  add     rsp, 28h
0x180009bdc  retn
```
