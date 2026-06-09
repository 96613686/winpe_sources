# ValidateWriteOrReadSubresource(TDebugOutputFunctor &,D3D12_BOX &,ResourceValidationInfo const &,ResourceCopyValidationInfo &,DeviceValidationInfo const &,uint,D3D12_BOX const *,bool)

- ea: `0x18025958c`
- end: `0x18025991a`
- name: `?ValidateWriteOrReadSubresource@@YAJAEAUTDebugOutputFunctor@@AEAUD3D12_BOX@@AEBUResourceValidationInfo@@AEAUResourceCopyValidationInfo@@AEBUDeviceValidationInfo@@IPEBU2@_N@Z`
- size: `910`
- prototype: `__int64 __usercall@<rax>(struct TDebugOutputFunctor *@<rcx>, struct D3D12_BOX *@<rdx>, const struct ResourceValidationInfo *@<r8>, struct ResourceCopyValidationInfo *@<r9>, const struct DeviceValidationInfo *, unsigned int, const struct D3D12_BOX *, bool)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x180237810`
- `0x180259420`

## callees

- `0x18002ef50`
- `0x1800abc10`
- `0x180258570`
- `0x18025958c`
- `0x18025f86c`

## string_xrefs

- `0x1802595d1`: `WriteToSubresource`
- `0x180259630`: `WriteToSubresource`
- `0x1802595af`: `ReadFromSubresource`
- `0x1802595c0`: `%s can not be called on a resource created with the CreateReservedResource API. The CPU page mapping is not kept in-sync with the GPU tile mapping configuration.`
- `0x1802597ba`: `p%sBox was empty, but probably was not intended. The resulting behavior is well-defined to result in no copy. The left, top, and front coordinates must be less then the corresponding right, bottom, and back coordinates to avoid specifying an empty box. left is %u, right is %u, top is %u, bottom is %u, front is %u, and back is %u.`

## pseudocode

```c
__int64 __fastcall ValidateWriteOrReadSubresource(
        struct TDebugOutputFunctor *a1,
        struct D3D12_BOX *a2,
        const struct ResourceValidationInfo *a3,
        struct ResourceCopyValidationInfo *a4,
        const struct DeviceValidationInfo *a5,
        unsigned int a6,
        const struct D3D12_BOX *a7,
        bool a8)
{
  int v8; // eax
  const char *v13; // r8
  const char *v14; // r9
  const char *v17; // r8
  unsigned int v18; // ecx
  const char *v19; // r9
  _OWORD *TexSubresourceInfo; // rax
  unsigned int v21; // edx
  unsigned int left; // r13d
  __int64 v23; // r8
  __int64 v24; // rax
  unsigned int right; // r10d
  int v26; // edx
  unsigned int v27; // r8d
  unsigned int bottom; // ecx
  unsigned int top; // r11d
  unsigned int back; // r8d
  const char *v31; // r9
  const char *v32; // r9
  const char *Name; // rax
  int v34; // r10d
  const char *v35; // r9
  unsigned int v36; // eax
  unsigned int v37; // ecx
  unsigned int v38; // edx
  char *v39; // [rsp+20h] [rbp-A8h]
  _BYTE v40[104]; // [rsp+60h] [rbp-68h] BYREF
  int v41; // [rsp+E0h] [rbp+18h]
  unsigned int v42; // [rsp+108h] [rbp+40h]

  v8 = *((_DWORD *)a3 + 3);
  if ( (v8 & 0xF000000) == 0 )
  {
    v13 = "%s can not be called on a resource created with the CreateReservedResource API. The CPU page mapping is not ke"
          "pt in-sync with the GPU tile mapping configuration.";
LABEL_3:
    v14 = "WriteToSubresource";
    if ( !a8 )
      v14 = "ReadFromSubresource";
    TDebugOutputFunctor::operator()(a1, a8 ? 890 : 895, v13, v14);
    return 2147942487LL;
  }
  if ( (v8 & 0xF0000000) == 0x10000000 )
  {
    v13 = "%s can not be called on a resource associated with a heap that has the CPU page properties of D3D12_CPU_PAGE_P"
          "ROPERTY_NOT_AVAILABLE. Heaps of the type D3D12_HEAP_TYPE_DEFAULT should be assumed to have these properties.";
    goto LABEL_3;
  }
  if ( (*((_DWORD *)a3 + 2) & 0xF000000) == 0x1000000 )
  {
    v13 = "%s cannot be called for buffers.";
    goto LABEL_3;
  }
  v17 = "WriteToSubresource";
  if ( !a8 )
    v17 = "ReadFromSubresource";
  if ( (int)ValidateParameterizedSwizzleSupport(
              a1,
              a3,
              a5,
              (enum D3D12_MESSAGE_ID)(a8
                                    ? D3D12_MESSAGE_ID_WRITETOSUBRESOURCE_INVALIDRESOURCE
                                    : D3D12_MESSAGE_ID_READFROMSUBRESOURCE_INVALIDRESOURCE),
              v17) < 0 )
    return 2147942487LL;
  v18 = *((_DWORD *)a3 + 5) & 0xFFFFFF;
  if ( a6 >= v18 )
  {
    v19 = "Dst";
    if ( !a8 )
      v19 = "Src";
    TDebugOutputFunctor::operator()(
      a1,
      a8 ? 892 : 897,
      "%sSubresource is too large for the resource. The value is %u, when the resource only has %u subresources.",
      v19,
      a6,
      v18);
    return 2147942487LL;
  }
  TexSubresourceInfo = (_OWORD *)ResourceValidationInfo::GetTexSubresourceInfo(a3, v40);
  *(_OWORD *)a4 = *TexSubresourceInfo;
  *(_OWORD *)((char *)a4 + 12) = *(_OWORD *)((char *)TexSubresourceInfo + 12);
  if ( a7 )
  {
    v21 = *((_DWORD *)a4 + 3);
    left = a7->left;
    v23 = 0xFFFFFFFFLL;
    v24 = 0xFFFFFFFFLL;
    if ( v21 < 0xC0 )
      v24 = v21;
    v41 = *((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v24 + 6) & 0xF;
    right = a7->right;
    if ( v21 < 0xC0 )
      v23 = v21;
    v26 = (left | (unsigned __int64)a7->right)
        % (*((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v24 + 6) & 0xFu);
    v27 = (*((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v23 + 6) >> 4) & 0xF;
    v42 = v27;
    if ( v26 || (bottom = a7->bottom, top = a7->top, (v26 = (top | (unsigned __int64)bottom) % v27) != 0) )
    {
      Name = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName((enum DXGI_FORMAT)*((__int16 *)a3 + 9), v26);
      v35 = "Dst";
      if ( !a8 )
        v35 = "Src";
      TDebugOutputFunctor::operator()(
        a1,
        a8 ? 891 : 896,
        "The coordinates in p%sBox are not aligned properly for the resource format. When the format is %s, left & right "
        "must be a multiple of %u and top & bottom must be a multiple of %u. left is %u, right is %u, top is %u, and bottom is %u.",
        v35,
        Name,
        v41,
        v42,
        left,
        v34,
        a7->top,
        a7->bottom);
      return 2147942487LL;
    }
    if ( right > *(_DWORD *)a4 || bottom > *((_DWORD *)a4 + 1) || (back = a7->back, back > *((_DWORD *)a4 + 2)) )
    {
      v32 = "Dst";
      if ( !a8 )
        v32 = "Src";
      TDebugOutputFunctor::operator()(
        a1,
        a8 ? 891 : 896,
        "The box extends past, at least, one the edges of the subresource. p%sBox right is %u, bottom is %u, and back is "
        "%u. But, %sSubresource %u only has %u width, %u height, and %u depth.",
        v32,
        right,
        bottom,
        a7->back,
        v32,
        a6,
        *(_DWORD *)a4,
        *((_DWORD *)a4 + 1),
        *((_DWORD *)a4 + 2));
      return 2147942487LL;
    }
    if ( right <= left || bottom <= top || back <= a7->front )
    {
      v31 = "Dst";
      if ( !a8 )
        v31 = "Src";
      LODWORD(v39) = a7->left;
      TDebugOutputFunctor::operator()(
        a1,
        a8 ? 893 : 898,
        "p%sBox was empty, but probably was not intended. The resulting behavior is well-defined to result in no copy. Th"
        "e left, top, and front coordinates must be less then the corresponding right, bottom, and back coordinates to av"
        "oid specifying an empty box. left is %u, right is %u, top is %u, bottom is %u, front is %u, and back is %u.",
        v31,
        v39,
        a7->right,
        a7->top,
        a7->bottom,
        a7->front,
        a7->back);
    }
    *a2 = *a7;
  }
  else
  {
    v36 = *(_DWORD *)a4;
    v37 = *((_DWORD *)a4 + 1);
    v38 = *((_DWORD *)a4 + 2);
    *(_QWORD *)&a2->left = 0;
    a2->front = 0;
    a2->right = v36;
    a2->bottom = v37;
    a2->back = v38;
  }
  return 0;
}

```

## disassembly

```asm
0x18025958c  push    rbx
0x18025958e  push    rbp
0x18025958f  push    rsi
0x180259590  push    rdi
0x180259591  push    r12
0x180259593  push    r13
0x180259595  push    r14
0x180259597  push    r15
0x180259599  sub     rsp, 88h
0x1802595a0  mov     eax, [r8+0Ch]
0x1802595a4  mov     r14, rcx
0x1802595a7  mov     ecx, 0F000000h
0x1802595ac  mov     rdi, rdx
0x1802595af  lea     rdx, aReadfromsubres; "ReadFromSubresource"
0x1802595b6  mov     rbx, r9
0x1802595b9  mov     r15, r8
0x1802595bc  test    ecx, eax
0x1802595be  jnz     short loc_1802595FA
0x1802595c0  lea     r8, aSCanNotBeCalle; "%s can not be called on a resource crea"...
0x1802595c7  mov     rcx, r14
0x1802595ca  mov     al, [rsp+0C8h+arg_38]
0x1802595d1  lea     r9, aWritetosubreso; "WriteToSubresource"
0x1802595d8  test    al, al
0x1802595da  cmovz   r9, rdx
0x1802595de  neg     al
0x1802595e0  sbb     edx, edx
0x1802595e2  and     edx, 0FFFFFFFBh
0x1802595e5  add     edx, 37Fh
0x1802595eb  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1802595f0  mov     eax, 80070057h
0x1802595f5  jmp     loc_180259906
0x1802595fa  and     eax, 0F0000000h
0x1802595ff  cmp     eax, 10000000h
0x180259604  jnz     short loc_18025960F
0x180259606  lea     r8, aSCanNotBeCalle_0; "%s can not be called on a resource asso"...
0x18025960d  jmp     short loc_1802595C7
0x18025960f  mov     eax, [r8+8]
0x180259613  and     eax, ecx
0x180259615  mov     rcx, r14; struct TDebugOutputFunctor *
0x180259618  cmp     eax, 1000000h
0x18025961d  jnz     short loc_180259628
0x18025961f  lea     r8, aSCannotBeCalle; "%s cannot be called for buffers."
0x180259626  jmp     short loc_1802595CA
0x180259628  mov     bpl, [rsp+0C8h+arg_38]
0x180259630  lea     r8, aWritetosubreso; "WriteToSubresource"
0x180259637  test    bpl, bpl
0x18025963a  mov     al, bpl
0x18025963d  cmovz   r8, rdx
0x180259641  neg     al
0x180259643  mov     [rsp+0C8h+var_A8], r8; char *
0x180259648  mov     rdx, r15; struct ResourceValidationInfo *
0x18025964b  mov     r8, [rsp+0C8h+arg_20]; struct DeviceValidationInfo *
0x180259653  sbb     r9d, r9d
0x180259656  and     r9d, 0FFFFFFFBh
0x18025965a  add     r9d, 37Fh; enum D3D12_MESSAGE_ID
0x180259661  call    ?ValidateParameterizedSwizzleSupport@@YAJAEAUTDebugOutputFunctor@@AEBUResourceValidationInfo@@AEBUDeviceValidationInfo@@W4D3D12_MESSAGE_ID@@PEBD@Z; ValidateParameterizedSwizzleSupport(TDebugOutputFunctor &,ResourceValidationInfo const &,DeviceValidationInfo const &,D3D12_MESSAGE_ID,char const *)
0x180259666  test    eax, eax
0x180259668  js      short loc_1802595F0
0x18025966a  mov     ecx, [r15+14h]
0x18025966e  mov     r12d, [rsp+0C8h+arg_28]
0x180259676  and     ecx, 0FFFFFFh
0x18025967c  cmp     r12d, ecx
0x18025967f  jb      short loc_1802596C1
0x180259681  test    bpl, bpl
0x180259684  mov     [rsp+0C8h+var_A0], ecx
0x180259688  lea     rax, aSrc; "Src"
0x18025968f  mov     dword ptr [rsp+0C8h+var_A8], r12d
0x180259694  lea     r9, aDst; "Dst"
0x18025969b  mov     rcx, r14
0x18025969e  cmovz   r9, rax
0x1802596a2  lea     r8, aSsubresourceIs; "%sSubresource is too large for the reso"...
0x1802596a9  neg     bpl
0x1802596ac  sbb     edx, edx
0x1802596ae  and     edx, 0FFFFFFFBh
0x1802596b1  add     edx, 381h
0x1802596b7  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1802596bc  jmp     loc_1802595F0
0x1802596c1  mov     r8d, r12d
0x1802596c4  lea     rdx, [rsp+0C8h+var_68]
0x1802596c9  mov     rcx, r15
0x1802596cc  call    ?GetTexSubresourceInfo@ResourceValidationInfo@@QEBA?AUResourceCopyValidationInfo@@I@Z; ResourceValidationInfo::GetTexSubresourceInfo(uint)
0x1802596d1  mov     rsi, [rsp+0C8h+arg_30]
0x1802596d9  movups  xmm0, xmmword ptr [rax]
0x1802596dc  movups  xmmword ptr [rbx], xmm0
0x1802596df  movups  xmm1, xmmword ptr [rax+0Ch]
0x1802596e3  movups  xmmword ptr [rbx+0Ch], xmm1
0x1802596e7  test    rsi, rsi
0x1802596ea  jz      loc_1802598E5
0x1802596f0  mov     edx, [rbx+0Ch]
0x1802596f3  lea     r11, ?s_FormatDetail@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@0QBUFORMAT_DETAIL@1@B; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::FORMAT_DETAIL const near * const D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail
0x1802596fa  mov     r13d, [rsi]
0x1802596fd  or      r8d, 0FFFFFFFFh
0x180259701  mov     eax, r8d
0x180259704  mov     r10d, 0C0h
0x18025970a  cmp     edx, r10d
0x18025970d  cmovb   eax, edx
0x180259710  lea     rcx, [rax+rax*4]
0x180259714  mov     r9d, [r11+rcx*8+18h]
0x180259719  and     r9d, 0Fh
0x18025971d  cmp     edx, r10d
0x180259720  mov     [rsp+0C8h+arg_10], r9d
0x180259728  mov     r10d, [rsi+0Ch]
0x18025972c  mov     eax, r10d
0x18025972f  cmovb   r8d, edx
0x180259733  or      eax, r13d
0x180259736  xor     edx, edx; bool
0x180259738  div     r9d
0x18025973b  lea     rcx, [r8+r8*4]
0x18025973f  mov     r8d, [r11+rcx*8+18h]
0x180259744  shr     r8d, 4
0x180259748  and     r8d, 0Fh
0x18025974c  mov     dword ptr [rsp+0C8h+arg_38], r8d
0x180259754  test    edx, edx
0x180259756  jnz     loc_18025986E
0x18025975c  mov     ecx, [rsi+10h]
0x18025975f  xor     edx, edx
0x180259761  mov     r11d, [rsi+4]
0x180259765  mov     eax, ecx
0x180259767  or      eax, r11d
0x18025976a  div     r8d
0x18025976d  test    edx, edx
0x18025976f  jnz     loc_18025986E
0x180259775  mov     r15d, [rbx]
0x180259778  cmp     r10d, r15d
0x18025977b  ja      loc_18025980A
0x180259781  cmp     ecx, [rbx+4]
0x180259784  ja      loc_18025980A
0x18025978a  mov     r8d, [rsi+14h]
0x18025978e  cmp     r8d, [rbx+8]
0x180259792  ja      short loc_18025980A
0x180259794  cmp     r10d, r13d
0x180259797  jbe     short loc_1802597A4
0x180259799  cmp     ecx, r11d
0x18025979c  jbe     short loc_1802597A4
0x18025979e  cmp     r8d, [rsi+8]
0x1802597a2  ja      short loc_1802597F5
0x1802597a4  mov     [rsp+0C8h+var_80], r8d
0x1802597a9  lea     rax, aSrc; "Src"
0x1802597b0  test    bpl, bpl
0x1802597b3  lea     r9, aDst; "Dst"
0x1802597ba  lea     r8, aPSboxWasEmptyB; "p%sBox was empty, but probably was not "...
0x1802597c1  cmovz   r9, rax
0x1802597c5  mov     eax, [rsi+8]
0x1802597c8  mov     [rsp+0C8h+var_88], eax
0x1802597cc  neg     bpl
0x1802597cf  mov     dword ptr [rsp+0C8h+var_90], ecx
0x1802597d3  mov     rcx, r14
0x1802597d6  sbb     edx, edx
0x1802597d8  mov     [rsp+0C8h+var_98], r11d
0x1802597dd  and     edx, 0FFFFFFFBh
0x1802597e0  mov     [rsp+0C8h+var_A0], r10d
0x1802597e5  add     edx, 382h
0x1802597eb  mov     dword ptr [rsp+0C8h+var_A8], r13d
0x1802597f0  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1802597f5  movups  xmm0, xmmword ptr [rsi]
0x1802597f8  movups  xmmword ptr [rdi], xmm0
0x1802597fb  movsd   xmm1, qword ptr [rsi+10h]
0x180259800  movsd   qword ptr [rdi+10h], xmm1
0x180259805  jmp     loc_180259904
0x18025980a  test    bpl, bpl
0x18025980d  lea     rax, aSrc; "Src"
0x180259814  lea     r9, aDst; "Dst"
0x18025981b  cmovz   r9, rax
0x18025981f  lea     r8, aTheBoxExtendsP; "The box extends past, at least, one the"...
0x180259826  mov     eax, [rbx+8]
0x180259829  neg     bpl
0x18025982c  mov     [rsp+0C8h+var_70], eax
0x180259830  mov     eax, [rbx+4]
0x180259833  sbb     edx, edx
0x180259835  mov     [rsp+0C8h+var_78], eax
0x180259839  and     edx, 0FFFFFFFBh
0x18025983c  mov     eax, [rsi+14h]
0x18025983f  add     edx, 380h
0x180259845  mov     [rsp+0C8h+var_80], r15d
0x18025984a  mov     [rsp+0C8h+var_88], r12d
0x18025984f  mov     [rsp+0C8h+var_90], r9
0x180259854  mov     [rsp+0C8h+var_98], eax
0x180259858  mov     [rsp+0C8h+var_A0], ecx
0x18025985c  mov     rcx, r14
0x18025985f  mov     dword ptr [rsp+0C8h+var_A8], r10d
0x180259864  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180259869  jmp     loc_1802595F0
0x18025986e  movsx   ecx, word ptr [r15+12h]; enum DXGI_FORMAT
0x180259873  call    ?GetName@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@SAPEBDW4DXGI_FORMAT@@_N@Z; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(DXGI_FORMAT,bool)
0x180259878  mov     ecx, [rsi+10h]
0x18025987b  lea     r9, aDst; "Dst"
0x180259882  mov     [rsp+0C8h+var_78], ecx
0x180259886  mov     r8, rax
0x180259889  test    bpl, bpl
0x18025988c  lea     rax, aSrc; "Src"
0x180259893  mov     rcx, r14
0x180259896  cmovz   r9, rax
0x18025989a  mov     eax, [rsi+4]
0x18025989d  mov     [rsp+0C8h+var_80], eax
0x1802598a1  neg     bpl
0x1802598a4  mov     eax, dword ptr [rsp+0C8h+arg_38]
0x1802598ab  mov     [rsp+0C8h+var_88], r10d
0x1802598b0  sbb     edx, edx
0x1802598b2  mov     dword ptr [rsp+0C8h+var_90], r13d
0x1802598b7  and     edx, 0FFFFFFFBh
0x1802598ba  mov     [rsp+0C8h+var_98], eax
0x1802598be  add     edx, 380h
0x1802598c4  mov     eax, [rsp+0C8h+arg_10]
0x1802598cb  mov     [rsp+0C8h+var_A0], eax
0x1802598cf  mov     [rsp+0C8h+var_A8], r8
0x1802598d4  lea     r8, aTheCoordinates_0; "The coordinates in p%sBox are not align"...
0x1802598db  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1802598e0  jmp     loc_1802595F0
0x1802598e5  mov     eax, [rbx]
0x1802598e7  mov     ecx, [rbx+4]
0x1802598ea  mov     edx, [rbx+8]
0x1802598ed  mov     qword ptr [rdi], 0
0x1802598f4  mov     dword ptr [rdi+8], 0
0x1802598fb  mov     [rdi+0Ch], eax
0x1802598fe  mov     [rdi+10h], ecx
0x180259901  mov     [rdi+14h], edx
0x180259904  xor     eax, eax
0x180259906  add     rsp, 88h
0x18025990d  pop     r15
0x18025990f  pop     r14
0x180259911  pop     r13
0x180259913  pop     r12
0x180259915  pop     rdi
0x180259916  pop     rsi
0x180259917  pop     rbp
0x180259918  pop     rbx
0x180259919  retn
```
