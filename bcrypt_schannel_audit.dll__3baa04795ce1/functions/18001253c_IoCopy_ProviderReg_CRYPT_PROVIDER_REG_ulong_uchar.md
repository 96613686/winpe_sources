# IoCopy_ProviderReg(_CRYPT_PROVIDER_REG *,ulong *,uchar *)

- ea: `0x18001253c`
- end: `0x180012674`
- name: `?IoCopy_ProviderReg@@YAKPEAU_CRYPT_PROVIDER_REG@@PEAKPEAE@Z`
- size: `312`
- prototype: `unsigned int __fastcall(struct _CRYPT_PROVIDER_REG *, unsigned int *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180001c04`

## callees

- `0x18001253c`
- `0x180019dac`
- `0x18001a008`

## pseudocode

```c
unsigned int __fastcall IoCopy_ProviderReg(struct _CRYPT_PROVIDER_REG *a1, unsigned int *a2, unsigned __int8 *a3)
{
  unsigned __int16 **rgpszAliases; // rcx
  unsigned __int8 *v7; // r15
  unsigned int result; // eax
  unsigned int v9; // r14d
  unsigned __int8 *v10; // rcx
  __int64 v11; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v12; // [rsp+70h] [rbp+30h] BYREF
  unsigned int v13; // [rsp+78h] [rbp+38h] BYREF
  __int64 v14; // [rsp+88h] [rbp+48h] BYREF

  v12 = 0;
  v13 = 0;
  v14 = 0;
  v11 = 0;
  if ( a2 )
    *a2 = 0;
  if ( !a1 )
    return 87;
  rgpszAliases = a1->rgpszAliases;
  if ( rgpszAliases )
  {
    if ( a1->cAliases )
    {
      v7 = (unsigned __int8 *)((unsigned __int64)(a3 + 32) & -(__int64)(a3 != 0));
      result = IoCopy_SzStringArray(rgpszAliases, a1->cAliases, &v12, v7);
      if ( result )
        return result;
      v9 = v12 + 32;
      goto LABEL_10;
    }
    return 87;
  }
  if ( a1->cAliases )
    return 87;
  v9 = 32;
  v7 = 0;
LABEL_10:
  if ( a3 )
    v10 = &a3[v9];
  else
    v10 = 0;
  result = IoCopy_ImageRegs(
             a1->pUM,
             a1->pKM,
             (unsigned __int8 **)((unsigned __int64)&v14 & -(__int64)(a3 != 0)),
             (unsigned __int8 **)((unsigned __int64)&v11 & -(__int64)(a3 != 0)),
             &v13,
             v10);
  if ( !result )
  {
    if ( a3 )
    {
      *((_QWORD *)a3 + 1) = v7;
      *(_DWORD *)a3 = a1->cAliases;
      *((_QWORD *)a3 + 2) = v14;
      *((_QWORD *)a3 + 3) = v11;
    }
    if ( a2 )
      *a2 = v9 + v13;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001253c  mov     [rsp-28h+arg_10], rbx
0x180012541  push    rbp
0x180012542  push    rsi
0x180012543  push    rdi
0x180012544  push    r14
0x180012546  push    r15
0x180012548  mov     rbp, rsp
0x18001254b  sub     rsp, 40h
0x18001254f  mov     [rbp+arg_0], 0
0x180012556  mov     rbx, r8
0x180012559  mov     [rbp+arg_8], 0
0x180012560  mov     rsi, rdx
0x180012563  mov     [rbp+arg_18], 0
0x18001256b  mov     rdi, rcx
0x18001256e  mov     [rbp+var_10], 0
0x180012576  test    rdx, rdx
0x180012579  jz      short loc_180012581
0x18001257b  mov     dword ptr [rdx], 0
0x180012581  test    rdi, rdi
0x180012584  jz      loc_18001265A
0x18001258a  mov     rcx, [rcx+8]; unsigned __int16 **
0x18001258e  test    rcx, rcx
0x180012591  jz      short loc_1800125CC
0x180012593  cmp     dword ptr [rdi], 0
0x180012596  jz      loc_18001265A
0x18001259c  mov     edx, [rdi]; unsigned int
0x18001259e  add     r8, 20h ; ' '
0x1800125a2  mov     rax, rbx
0x1800125a5  neg     rax
0x1800125a8  sbb     r15, r15
0x1800125ab  and     r15, r8
0x1800125ae  lea     r8, [rbp+arg_0]; unsigned int *
0x1800125b2  mov     r9, r15; unsigned __int8 *
0x1800125b5  call    ?IoCopy_SzStringArray@@YAKPEAPEAGKPEAKPEAE@Z; IoCopy_SzStringArray(ushort * *,ulong,ulong *,uchar *)
0x1800125ba  test    eax, eax
0x1800125bc  jnz     loc_18001265F
0x1800125c2  mov     r14d, [rbp+arg_0]
0x1800125c6  add     r14d, 20h ; ' '
0x1800125ca  jmp     short loc_1800125DE
0x1800125cc  cmp     dword ptr [rdi], 0
0x1800125cf  jnz     loc_18001265A
0x1800125d5  mov     r14d, 20h ; ' '
0x1800125db  xor     r15d, r15d
0x1800125de  test    rbx, rbx
0x1800125e1  jz      short loc_1800125EB
0x1800125e3  mov     ecx, r14d
0x1800125e6  add     rcx, rbx
0x1800125e9  jmp     short loc_1800125ED
0x1800125eb  xor     ecx, ecx
0x1800125ed  mov     rdx, [rdi+18h]; struct _CRYPT_IMAGE_REG *
0x1800125f1  mov     rax, rbx
0x1800125f4  neg     rax
0x1800125f7  mov     [rsp+40h+var_18], rcx; unsigned __int8 *
0x1800125fc  mov     rcx, [rdi+10h]; struct _CRYPT_IMAGE_REG *
0x180012600  lea     rax, [rbp+var_10]
0x180012604  sbb     r9, r9
0x180012607  and     r9, rax; unsigned __int8 **
0x18001260a  mov     rax, rbx
0x18001260d  neg     rax
0x180012610  lea     rax, [rbp+arg_18]
0x180012614  sbb     r8, r8
0x180012617  and     r8, rax; unsigned __int8 **
0x18001261a  lea     rax, [rbp+arg_8]
0x18001261e  mov     [rsp+40h+var_20], rax; unsigned int *
0x180012623  call    ?IoCopy_ImageRegs@@YAKPEAU_CRYPT_IMAGE_REG@@0PEAPEAE1PEAKPEAE@Z; IoCopy_ImageRegs(_CRYPT_IMAGE_REG *,_CRYPT_IMAGE_REG *,uchar * *,uchar * *,ulong *,uchar *)
0x180012628  test    eax, eax
0x18001262a  jnz     short loc_18001265F
0x18001262c  test    rbx, rbx
0x18001262f  jz      short loc_180012649
0x180012631  mov     [rbx+8], r15
0x180012635  mov     eax, [rdi]
0x180012637  mov     [rbx], eax
0x180012639  mov     rax, [rbp+arg_18]
0x18001263d  mov     [rbx+10h], rax
0x180012641  mov     rax, [rbp+var_10]
0x180012645  mov     [rbx+18h], rax
0x180012649  test    rsi, rsi
0x18001264c  jz      short loc_180012656
0x18001264e  mov     ecx, [rbp+arg_8]
0x180012651  add     ecx, r14d
0x180012654  mov     [rsi], ecx
0x180012656  xor     eax, eax
0x180012658  jmp     short loc_18001265F
0x18001265a  mov     eax, 57h ; 'W'
0x18001265f  mov     rbx, [rsp+40h+arg_10]
0x180012667  add     rsp, 40h
0x18001266b  pop     r15
0x18001266d  pop     r14
0x18001266f  pop     rdi
0x180012670  pop     rsi
0x180012671  pop     rbp
0x180012672  retn
```
