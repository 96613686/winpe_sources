# UDRTrie::TagFor(uint,uint)

- ea: `0x18009edc0`
- end: `0x18009ee89`
- name: `?TagFor@UDRTrie@@UEBA?AV_variant_t@@II@Z`
- size: `201`
- prototype: `struct _variant_t __high(unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18009db54`
- `0x18009e294`
- `0x18009edc0`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18009ee14`
- `OLEAUT32!__imp_VariantInit` at `0x18009ee14`
- `OLEAUT32!__imp_VariantCopy` at `0x18009ee22`
- `OLEAUT32!__imp_VariantCopy` at `0x18009ee22`

## pseudocode

```c
VARIANTARG *__fastcall UDRTrie::TagFor(__int64 a1, VARIANTARG *a2, unsigned int a3, unsigned int a4)
{
  unsigned int v5; // edx
  const unsigned __int16 *v6; // rax
  HRESULT v7; // eax
  __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rcx
  VARIANTARG pvargSrc; // [rsp+28h] [rbp-20h] BYREF

  v5 = *(_DWORD *)(a1 + 616);
  if ( v5 )
  {
    v8 = **(_QWORD **)(a1 + 48);
    v9 = 32LL * a3;
    if ( (*(_BYTE *)(v9 + v8 + 26) & 2) == 0 )
      goto LABEL_12;
    if ( a4 >= v5 )
      goto LABEL_12;
    v10 = *(_QWORD *)(32LL * *(int *)(v9 + v8 + 8) + v8);
    if ( !v10 )
      goto LABEL_12;
    a2->lVal = *(_DWORD *)(v10 + 4LL * a4);
LABEL_13:
    a2->vt = 3;
    return a2;
  }
  if ( !a4 )
  {
    a2->lVal = 15;
    goto LABEL_13;
  }
  if ( a4 != 1 || (v6 = UDRTrie::ChangeTagFor((UDRTrie *)a1, a3)) == 0 )
  {
LABEL_12:
    a2->lVal = 0;
    goto LABEL_13;
  }
  *(_QWORD *)&pvargSrc.vt = 16402;
  *(_OWORD *)&pvargSrc.decVal.Lo32 = (unsigned __int64)v6;
  VariantInit(a2);
  v7 = VariantCopy(a2, &pvargSrc);
  if ( v7 < 0 )
    _com_issue_error(v7);
  return a2;
}

```

## disassembly

```asm
0x18009edc0  push    rbx
0x18009edc2  sub     rsp, 40h
0x18009edc6  mov     rbx, rdx
0x18009edc9  mov     edx, [rcx+268h]
0x18009edcf  test    edx, edx
0x18009edd1  jnz     short loc_18009EE3D
0x18009edd3  test    r9d, r9d
0x18009edd6  jz      short loc_18009EE34
0x18009edd8  cmp     r9d, 1
0x18009eddc  jnz     loc_18009EE74
0x18009ede2  mov     edx, r8d; unsigned __int64
0x18009ede5  call    ?ChangeTagFor@UDRTrie@@QEBAPEBG_K@Z; UDRTrie::ChangeTagFor(unsigned __int64)
0x18009edea  test    rax, rax
0x18009eded  jz      loc_18009EE74
0x18009edf3  xor     ecx, ecx
0x18009edf5  xorps   xmm0, xmm0
0x18009edf8  mov     qword ptr [rsp+48h+pvargSrc+10h], rcx
0x18009edfd  mov     ecx, 4012h
0x18009ee02  movups  xmmword ptr [rsp+48h+pvargSrc], xmm0
0x18009ee07  mov     word ptr [rsp+48h+pvargSrc], cx
0x18009ee0c  mov     rcx, rbx; pvarg
0x18009ee0f  mov     qword ptr [rsp+48h+pvargSrc+8], rax
0x18009ee14  call    cs:__imp_VariantInit
0x18009ee1a  lea     rdx, [rsp+48h+pvargSrc]; pvargSrc
0x18009ee1f  mov     rcx, rbx; pvargDest
0x18009ee22  call    cs:__imp_VariantCopy
0x18009ee28  test    eax, eax
0x18009ee2a  jns     short loc_18009EE80
0x18009ee2c  mov     ecx, eax; int
0x18009ee2e  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18009ee34  mov     dword ptr [rbx+8], 0Fh
0x18009ee3b  jmp     short loc_18009EE7B
0x18009ee3d  mov     rax, [rcx+30h]
0x18009ee41  mov     rcx, [rax]
0x18009ee44  mov     eax, r8d
0x18009ee47  shl     rax, 5
0x18009ee4b  test    byte ptr [rax+rcx+1Ah], 2
0x18009ee50  jz      short loc_18009EE74
0x18009ee52  cmp     r9d, edx
0x18009ee55  jnb     short loc_18009EE74
0x18009ee57  movsxd  rax, dword ptr [rax+rcx+8]
0x18009ee5c  shl     rax, 5
0x18009ee60  mov     rcx, [rax+rcx]
0x18009ee64  test    rcx, rcx
0x18009ee67  jz      short loc_18009EE74
0x18009ee69  mov     eax, r9d
0x18009ee6c  mov     ecx, [rcx+rax*4]
0x18009ee6f  mov     [rbx+8], ecx
0x18009ee72  jmp     short loc_18009EE7B
0x18009ee74  mov     dword ptr [rbx+8], 0
0x18009ee7b  mov     word ptr [rbx], 3
0x18009ee80  mov     rax, rbx
0x18009ee83  add     rsp, 40h
0x18009ee87  pop     rbx
0x18009ee88  retn
```
