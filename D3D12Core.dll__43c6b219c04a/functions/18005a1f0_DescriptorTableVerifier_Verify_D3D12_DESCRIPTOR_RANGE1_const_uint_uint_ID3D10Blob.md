# DescriptorTableVerifier::Verify(D3D12_DESCRIPTOR_RANGE1 const *,uint,uint,ID3D10Blob * *)

- ea: `0x18005a1f0`
- end: `0x18005a43e`
- name: `?Verify@DescriptorTableVerifier@@QEAAJPEBUD3D12_DESCRIPTOR_RANGE1@@IIPEAPEAUID3D10Blob@@@Z`
- size: `590`
- prototype: `__int64 __fastcall(DescriptorTableVerifier *__hidden this, const struct D3D12_DESCRIPTOR_RANGE1 *, unsigned int, unsigned int, struct ID3D10Blob **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18003bbfc`

## callees

- `0x18003b478`
- `0x18005a1f0`
- `0x1801520ec`

## string_xrefs

- `0x18005a336`: `NumDescriptors cannot be 0 (descriptor table slot [%u], root parameter [%u]).\n`
- `0x18005a386`: `Samplers cannot be mixed with other resource types in a descriptor table (root parameter [%u]).\n`
- `0x18005a360`: `Unsupported RangeType value %u (descriptor table slot [%u], root parameter [%u]).\n`
- `0x18005a401`: `Overflow for descriptor range (descriptor table slot [%u], root parameter [%u])\n`
- `0x18005a3d5`: `Overflow for shader register range: BaseShaderRegister=%u, NumDescriptor=%u; (descriptor table slot [%u], root parameter [%u]).\n`
- `0x18005a3a8`: `Cannot append range with implicit lower bound after an unbounded range (descriptor table slot [%u], root parameter [%u]).\n`

## pseudocode

```c
__int64 __fastcall DescriptorTableVerifier::Verify(
        unsigned __int64 this,
        const struct D3D12_DESCRIPTOR_RANGE1 *a2,
        unsigned int a3,
        unsigned int a4,
        struct ID3D10Blob **a5)
{
  char v5; // si
  char v7; // dl
  int v8; // r10d
  __int64 v9; // r14
  __int64 v10; // rdi
  D3D12_DESCRIPTOR_RANGE_TYPE RangeType; // r8d
  unsigned __int64 v15; // rsi
  __int64 NumDescriptors; // r9
  __int64 BaseShaderRegister; // r8
  char v18; // [rsp+30h] [rbp-48h]
  _DWORD *v19; // [rsp+80h] [rbp+8h]
  char v20; // [rsp+90h] [rbp+18h]

  v19 = (_DWORD *)this;
  v5 = 0;
  v18 = 0;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  v20 = 0;
  v10 = 0;
  while ( (unsigned int)v10 < a3 )
  {
    RangeType = a2[v10].RangeType;
    this = (unsigned int)RangeType;
    if ( RangeType == D3D12_DESCRIPTOR_RANGE_TYPE_SRV
      || (this = (unsigned int)(RangeType - 1), RangeType == D3D12_DESCRIPTOR_RANGE_TYPE_UAV)
      || (this = (unsigned int)(RangeType - 2), RangeType == D3D12_DESCRIPTOR_RANGE_TYPE_CBV) )
    {
      v20 = 1;
    }
    else
    {
      if ( RangeType == D3D12_DESCRIPTOR_RANGE_TYPE_SAMPLER )
      {
        v5 = 1;
        v18 = 1;
      }
      else
      {
        v8 = ErrorRootSignature(
               a5,
               "Unsupported RangeType value %u (descriptor table slot [%u], root parameter [%u]).\n",
               RangeType,
               v10,
               a4);
        if ( v8 < 0 )
          return (unsigned int)v8;
        v7 = v20;
      }
      if ( !v7 )
        goto LABEL_11;
    }
    if ( v5 )
    {
      v8 = ErrorRootSignature(
             a5,
             "Samplers cannot be mixed with other resource types in a descriptor table (root parameter [%u]).\n",
             a4);
      if ( v8 < 0 )
        return (unsigned int)v8;
    }
LABEL_11:
    if ( !a2[v10].NumDescriptors )
    {
      v8 = ErrorRootSignature(
             a5,
             "NumDescriptors cannot be 0 (descriptor table slot [%u], root parameter [%u]).\n",
             v10,
             a4);
      if ( v8 < 0 )
        return (unsigned int)v8;
    }
    v15 = a2[v10].OffsetInDescriptorsFromTableStart == -1 ? v9 : a2[v10].OffsetInDescriptorsFromTableStart;
    if ( v15 > 0xFFFFFFFF )
    {
      v8 = ErrorRootSignature(
             a5,
             "Cannot append range with implicit lower bound after an unbounded range (descriptor table slot [%u], root pa"
             "rameter [%u]).\n",
             v10,
             a4);
      if ( v8 < 0 )
        return (unsigned int)v8;
    }
    NumDescriptors = a2[v10].NumDescriptors;
    if ( (_DWORD)NumDescriptors == -1 )
    {
      v9 = 0x100000000LL;
    }
    else
    {
      BaseShaderRegister = a2[v10].BaseShaderRegister;
      if ( (unsigned __int64)(BaseShaderRegister + NumDescriptors - 1) > 0xFFFFFFFF )
      {
        v8 = ErrorRootSignature(
               a5,
               "Overflow for shader register range: BaseShaderRegister=%u, NumDescriptor=%u; (descriptor table slot [%u],"
               " root parameter [%u]).\n",
               BaseShaderRegister,
               NumDescriptors,
               v10,
               a4);
        if ( v8 < 0 )
          return (unsigned int)v8;
      }
      this = v15 + a2[v10].NumDescriptors - 1LL;
      if ( this > 0xFFFFFFFF )
      {
        v8 = ErrorRootSignature(
               a5,
               "Overflow for descriptor range (descriptor table slot [%u], root parameter [%u])\n",
               v10,
               a4);
        if ( v8 < 0 )
          return (unsigned int)v8;
      }
      v9 = v15 + a2[v10].NumDescriptors;
    }
    v5 = v18;
    v10 = (unsigned int)(v10 + 1);
    v7 = v20;
  }
  if ( (unsigned int)(*v19 - 1) <= 1 )
    return (unsigned int)DescriptorTableVerifier::VerifyDescriptorTableSlotRangeOverlap(
                           (DescriptorTableVerifier *)this,
                           a2,
                           a3,
                           a4,
                           a5);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18005a1f0  mov     [rsp+arg_8], rbx
0x18005a1f5  mov     [rsp+arg_0], rcx
0x18005a1fa  push    rbp
0x18005a1fb  push    rsi
0x18005a1fc  push    rdi
0x18005a1fd  push    r12
0x18005a1ff  push    r13
0x18005a201  push    r14
0x18005a203  push    r15
0x18005a205  sub     rsp, 40h
0x18005a209  mov     r12, [rsp+78h+arg_20]
0x18005a211  xor     sil, sil
0x18005a214  mov     rbx, rdx
0x18005a217  mov     [rsp+78h+var_48], sil
0x18005a21c  xor     dl, dl
0x18005a21e  xor     r10d, r10d
0x18005a221  xor     r14d, r14d
0x18005a224  mov     [rsp+78h+arg_10], dl
0x18005a22b  xor     edi, edi
0x18005a22d  mov     r15d, r9d
0x18005a230  mov     r13d, r8d
0x18005a233  cmp     edi, r13d
0x18005a236  jb      short loc_18005A268
0x18005a238  mov     rax, [rsp+78h+arg_0]
0x18005a240  mov     eax, [rax]
0x18005a242  dec     eax
0x18005a244  cmp     eax, 1
0x18005a247  jbe     loc_18005A423
0x18005a24d  mov     rbx, [rsp+78h+arg_8]
0x18005a255  mov     eax, r10d
0x18005a258  add     rsp, 40h
0x18005a25c  pop     r15
0x18005a25e  pop     r14
0x18005a260  pop     r13
0x18005a262  pop     r12
0x18005a264  pop     rdi
0x18005a265  pop     rsi
0x18005a266  pop     rbp
0x18005a267  retn
0x18005a268  lea     rbp, [rdi+rdi*2]
0x18005a26c  mov     r8d, [rbx+rbp*8]
0x18005a270  mov     ecx, r8d
0x18005a273  test    r8d, r8d
0x18005a276  jz      short loc_18005A286
0x18005a278  sub     ecx, 1
0x18005a27b  jz      short loc_18005A286
0x18005a27d  sub     ecx, 1
0x18005a280  jnz     loc_18005A315
0x18005a286  mov     [rsp+78h+arg_10], 1
0x18005a28e  test    sil, sil
0x18005a291  jnz     loc_18005A383
0x18005a297  cmp     dword ptr [rbx+rbp*8+4], 0
0x18005a29c  jz      loc_18005A333
0x18005a2a2  mov     r11d, 0FFFFFFFFh
0x18005a2a8  cmp     [rbx+rbp*8+14h], r11d
0x18005a2ad  jz      short loc_18005A32E
0x18005a2af  mov     esi, [rbx+rbp*8+14h]
0x18005a2b3  cmp     rsi, r11
0x18005a2b6  ja      loc_18005A3A5
0x18005a2bc  mov     r9d, [rbx+rbp*8+4]
0x18005a2c1  cmp     r9d, r11d
0x18005a2c4  jz      short loc_18005A309
0x18005a2c6  mov     r8d, [rbx+rbp*8+8]
0x18005a2cb  lea     rcx, [r9-1]
0x18005a2cf  add     rcx, r8
0x18005a2d2  cmp     rcx, r11
0x18005a2d5  ja      loc_18005A3D0
0x18005a2db  mov     ecx, [rbx+rbp*8+4]
0x18005a2df  dec     rcx
0x18005a2e2  add     rcx, rsi
0x18005a2e5  cmp     rcx, r11
0x18005a2e8  ja      loc_18005A3FE
0x18005a2ee  mov     r14d, [rbx+rbp*8+4]
0x18005a2f3  add     r14, rsi
0x18005a2f6  mov     sil, [rsp+78h+var_48]
0x18005a2fb  inc     edi
0x18005a2fd  mov     dl, [rsp+78h+arg_10]
0x18005a304  jmp     loc_18005A233
0x18005a309  mov     r14, 100000000h
0x18005a313  jmp     short loc_18005A2F6
0x18005a315  cmp     ecx, 1
0x18005a318  jnz     short loc_18005A358
0x18005a31a  mov     sil, cl
0x18005a31d  mov     [rsp+78h+var_48], cl
0x18005a321  test    dl, dl
0x18005a323  jnz     loc_18005A28E
0x18005a329  jmp     loc_18005A297
0x18005a32e  mov     rsi, r14
0x18005a331  jmp     short loc_18005A2B3
0x18005a333  mov     r9d, r15d
0x18005a336  lea     rdx, aNumdescriptors; "NumDescriptors cannot be 0 (descriptor "...
0x18005a33d  mov     r8d, edi
0x18005a340  mov     rcx, r12
0x18005a343  call    ErrorRootSignature
0x18005a348  mov     r10d, eax
0x18005a34b  test    eax, eax
0x18005a34d  jns     loc_18005A2A2
0x18005a353  jmp     loc_18005A24D
0x18005a358  mov     r9d, edi
0x18005a35b  mov     dword ptr [rsp+78h+var_58], r15d
0x18005a360  lea     rdx, aUnsupportedRan; "Unsupported RangeType value %u (descrip"...
0x18005a367  mov     rcx, r12
0x18005a36a  call    ErrorRootSignature
0x18005a36f  mov     r10d, eax
0x18005a372  test    eax, eax
0x18005a374  js      loc_18005A24D
0x18005a37a  mov     dl, [rsp+78h+arg_10]
0x18005a381  jmp     short loc_18005A321
0x18005a383  mov     r8d, r15d
0x18005a386  lea     rdx, aSamplersCannot; "Samplers cannot be mixed with other res"...
0x18005a38d  mov     rcx, r12
0x18005a390  call    ErrorRootSignature
0x18005a395  mov     r10d, eax
0x18005a398  test    eax, eax
0x18005a39a  js      loc_18005A24D
0x18005a3a0  jmp     loc_18005A297
0x18005a3a5  mov     r9d, r15d
0x18005a3a8  lea     rdx, aCannotAppendRa; "Cannot append range with implicit lower"...
0x18005a3af  mov     r8d, edi
0x18005a3b2  mov     rcx, r12
0x18005a3b5  call    ErrorRootSignature
0x18005a3ba  mov     r10d, eax
0x18005a3bd  test    eax, eax
0x18005a3bf  js      loc_18005A24D
0x18005a3c5  mov     r11d, 0FFFFFFFFh
0x18005a3cb  jmp     loc_18005A2BC
0x18005a3d0  mov     [rsp+78h+var_50], r15d
0x18005a3d5  lea     rdx, aOverflowForSha; "Overflow for shader register range: Bas"...
0x18005a3dc  mov     rcx, r12
0x18005a3df  mov     dword ptr [rsp+78h+var_58], edi
0x18005a3e3  call    ErrorRootSignature
0x18005a3e8  mov     r10d, eax
0x18005a3eb  test    eax, eax
0x18005a3ed  js      loc_18005A24D
0x18005a3f3  mov     r11d, 0FFFFFFFFh
0x18005a3f9  jmp     loc_18005A2DB
0x18005a3fe  mov     r9d, r15d
0x18005a401  lea     rdx, aOverflowForDes; "Overflow for descriptor range (descript"...
0x18005a408  mov     r8d, edi
0x18005a40b  mov     rcx, r12
0x18005a40e  call    ErrorRootSignature
0x18005a413  mov     r10d, eax
0x18005a416  test    eax, eax
0x18005a418  js      loc_18005A24D
0x18005a41e  jmp     loc_18005A2EE
0x18005a423  mov     r9d, r15d; unsigned int
0x18005a426  mov     [rsp+78h+var_58], r12; struct ID3D10Blob **
0x18005a42b  mov     r8d, r13d; unsigned int
0x18005a42e  mov     rdx, rbx; struct D3D12_DESCRIPTOR_RANGE1 *
0x18005a431  call    ?VerifyDescriptorTableSlotRangeOverlap@DescriptorTableVerifier@@AEAAJPEBUD3D12_DESCRIPTOR_RANGE1@@IIPEAPEAUID3D10Blob@@@Z; DescriptorTableVerifier::VerifyDescriptorTableSlotRangeOverlap(D3D12_DESCRIPTOR_RANGE1 const *,uint,uint,ID3D10Blob * *)
0x18005a436  mov     r10d, eax
0x18005a439  jmp     loc_18005A24D
```
