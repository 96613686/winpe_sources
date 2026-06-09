# ListBasedFilterInfo::Deserialize(ulong,IdParameters *,uchar const *,ulong,ISyncFilterInfo * *)

- ea: `0x18004afb8`
- end: `0x18004b298`
- name: `?Deserialize@ListBasedFilterInfo@@SAJKPEAVIdParameters@@PEBEKPEAPEAUISyncFilterInfo@@@Z`
- size: `736`
- prototype: `__int64 __fastcall(unsigned int, struct IdParameters *, const unsigned __int8 *, unsigned int, struct ISyncFilterInfo **)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x18004b9fc`

## callees

- `0x18000a0f0`
- `0x18001a038`
- `0x18001ae20`
- `0x18001fc38`
- `0x1800206d4`
- `0x18002addc`
- `0x18002af0c`
- `0x18004aeec`
- `0x18004afb8`
- `0x18004b2a0`
- `0x180094010`

## string_xrefs

- `0x18004affa`: `ListBasedFilterInfo::Deserialize`
- `0x18004b269`: `ListBasedFilterInfo::Deserialize`

## pseudocode

```c
__int64 __fastcall ListBasedFilterInfo::Deserialize(
        unsigned int a1,
        struct IdParameters *a2,
        const unsigned __int8 *a3,
        unsigned int a4,
        struct ISyncFilterInfo **a5)
{
  __int64 v5; // rdi
  PVOID *v9; // r10
  const unsigned __int8 *v10; // rbp
  unsigned int v11; // r14d
  const unsigned __int8 *v12; // r8
  __int16 v13; // cx
  unsigned __int8 *v14; // rdx
  unsigned __int8 *v15; // rcx
  int v16; // esi
  int v17; // eax
  int v18; // esi
  int v19; // edx
  unsigned int v20; // esi
  int v21; // eax
  _QWORD *v22; // rdi
  _QWORD *v23; // rax
  int v24; // ebx
  FilterInfo *v25; // rax
  FilterInfo *v26; // rsi
  struct ISyncFilterInfo **v27; // r8
  _QWORD *v28; // rcx
  __int64 i; // rsi
  unsigned __int8 *v31; // [rsp+30h] [rbp-58h] BYREF
  _ID_PARAMETER_PAIR v32; // [rsp+A0h] [rbp+18h] BYREF

  v5 = a4;
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      20,
      WPP_8c3e8ceaadcc3625839d548a135dd323_Traceguids,
      "ListBasedFilterInfo::Deserialize");
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  v10 = &a3[v5];
  if ( &a3[v5] < a3 )
    goto LABEL_38;
  v11 = 0;
  v32 = 0;
  if ( a3 >= v10 )
    goto LABEL_38;
  v12 = a3 + 1;
  if ( a3 + 1 > v10 )
    goto LABEL_38;
  if ( a3 + 2 < a3 )
    goto LABEL_38;
  if ( a3 + 3 > v10 )
    goto LABEL_38;
  if ( a3 + 3 <= v12 )
    goto LABEL_38;
  v13 = a3[2];
  v32.fIsVariable = *a3;
  v32.cbIdSize = (*v12 << 8) | v13;
  if ( !(unsigned int)IdParameterPair::IsValidParameterPair(&v32) )
    goto LABEL_38;
  v15 = v14 + 4;
  if ( v14 + 4 < v14 || v15 > v10 )
    goto LABEL_38;
  v16 = (*v14 << 8) | v14[1];
  v31 = v14 + 4;
  v17 = v14[3];
  v18 = (v14[2] | (v16 << 8)) << 8;
  v19 = 3;
  v20 = v17 | v18;
  v21 = 3;
  if ( !*((_DWORD *)a2 + 8) )
    v21 = *((unsigned __int16 *)a2 + 18);
  if ( &v15[v20 * v21] < v15 )
    goto LABEL_38;
  if ( !*((_DWORD *)a2 + 8) )
    v19 = *((unsigned __int16 *)a2 + 18);
  if ( &v15[v20 * v19] <= v10 )
  {
    v22 = 0;
    if ( !v20 )
      goto LABEL_23;
    v23 = SeAlloc(0x18u);
    v22 = v23;
    if ( v23 )
    {
      *v23 = 0;
      v23[2] = 0;
      *((_DWORD *)v23 + 2) = v20;
LABEL_23:
      while ( v11 < v20 )
      {
        v32 = 0;
        v24 = IdParameterPair::DeserializeId(
                (struct IdParameters *)((char *)a2 + 32),
                (unsigned __int16 **)&v31,
                v10,
                (unsigned __int8 **)&v32);
        if ( v24 < 0 )
          goto LABEL_34;
        v24 = Vector<unsigned char *,0>::Add(v22, &v32);
        if ( v24 < 0 )
        {
          IdParameters::FreeId(*(unsigned __int8 **)&v32);
          goto LABEL_34;
        }
        ++v11;
      }
      v25 = (FilterInfo *)SeAlloc(0x30u);
      v26 = v25;
      if ( v25 )
      {
        FilterInfo::FilterInfo(v25, a2, a1);
        v27 = a5;
        *v28 = &ListBasedFilterInfo::`vftable'{for `FilterInfo'};
        v28[4] = &ListBasedFilterInfo::`vftable'{for `IChangeUnitListFilterInfo'};
        v28[5] = v22;
        v24 = ((__int64 (__fastcall *)(_QWORD *, GUID *, struct ISyncFilterInfo **))ListBasedFilterInfo::`vftable'{for `FilterInfo'})(
                v28,
                &IID_ISyncFilterInfo,
                v27);
        (*(void (__fastcall **)(FilterInfo *))(*(_QWORD *)v26 + 16LL))(v26);
        if ( v24 >= 0 )
          goto LABEL_28;
        v22 = 0;
      }
      else
      {
        v24 = -2147024882;
      }
LABEL_34:
      if ( v22 )
      {
        for ( i = 0; (unsigned int)i < *(_DWORD *)v22; i = (unsigned int)(i + 1) )
          IdParameters::FreeId(*(unsigned __int8 **)(v22[2] + 8 * i));
        Vector<unsigned char *,0>::`scalar deleting destructor'(v22);
      }
    }
    else
    {
      v24 = -2147024882;
    }
LABEL_28:
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
LABEL_38:
    v24 = -2147217396;
  }
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 0x40) != 0 && *((_BYTE *)v9 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v9[2],
      21,
      (unsigned int)WPP_8c3e8ceaadcc3625839d548a135dd323_Traceguids,
      (unsigned int)"ListBasedFilterInfo::Deserialize",
      v24);
  return (unsigned int)v24;
}

```

## disassembly

```asm
0x18004afb8  push    rbx
0x18004afba  push    rbp
0x18004afbb  push    rsi
0x18004afbc  push    rdi
0x18004afbd  push    r12
0x18004afbf  push    r13
0x18004afc1  push    r14
0x18004afc3  push    r15
0x18004afc5  sub     rsp, 48h
0x18004afc9  mov     edi, r9d
0x18004afcc  mov     rbx, r8
0x18004afcf  mov     r13, rdx
0x18004afd2  mov     r12d, ecx
0x18004afd5  mov     r10, cs:WPP_GLOBAL_Control
0x18004afdc  lea     rax, WPP_GLOBAL_Control
0x18004afe3  cmp     r10, rax
0x18004afe6  jz      short loc_18004B019
0x18004afe8  test    byte ptr [r10+1Ch], 40h
0x18004afed  jz      short loc_18004B019
0x18004afef  cmp     byte ptr [r10+19h], 5
0x18004aff4  jb      short loc_18004B019
0x18004aff6  mov     rcx, [r10+10h]
0x18004affa  lea     r9, aListbasedfilte_1; "ListBasedFilterInfo::Deserialize"
0x18004b001  mov     edx, 14h
0x18004b006  lea     r8, WPP_8c3e8ceaadcc3625839d548a135dd323_Traceguids
0x18004b00d  call    WPP_SF_s
0x18004b012  mov     r10, cs:WPP_GLOBAL_Control
0x18004b019  lea     rbp, [rbx+rdi]
0x18004b01d  cmp     rbp, rbx
0x18004b020  jb      loc_18004B246
0x18004b026  xor     r14d, r14d
0x18004b029  mov     qword ptr [rsp+88h+arg_10.fIsVariable], r14
0x18004b031  cmp     rbx, rbp
0x18004b034  jnb     loc_18004B246
0x18004b03a  lea     r8, [rbx+1]
0x18004b03e  cmp     r8, rbp
0x18004b041  ja      loc_18004B246
0x18004b047  lea     rax, [rbx+2]
0x18004b04b  cmp     rax, rbx
0x18004b04e  jbe     loc_18004B246
0x18004b054  lea     rdx, [r8+2]
0x18004b058  cmp     rdx, rbp
0x18004b05b  ja      loc_18004B246
0x18004b061  cmp     rdx, r8
0x18004b064  jbe     loc_18004B246
0x18004b06a  movzx   eax, byte ptr [rbx]
0x18004b06d  movzx   ecx, byte ptr [r8+1]
0x18004b072  mov     [rsp+88h+arg_10.fIsVariable], eax
0x18004b079  movzx   eax, byte ptr [r8]
0x18004b07d  shl     ax, 8
0x18004b081  or      cx, ax
0x18004b084  mov     [rsp+88h+arg_10.cbIdSize], cx
0x18004b08c  lea     rcx, [rsp+88h+arg_10]; struct _ID_PARAMETER_PAIR *
0x18004b094  call    ?IsValidParameterPair@IdParameterPair@@SAHPEBU_ID_PARAMETER_PAIR@@@Z; IdParameterPair::IsValidParameterPair(_ID_PARAMETER_PAIR const *)
0x18004b099  test    eax, eax
0x18004b09b  jz      loc_18004B246
0x18004b0a1  lea     rcx, [rdx+4]
0x18004b0a5  cmp     rcx, rdx
0x18004b0a8  jb      loc_18004B246
0x18004b0ae  cmp     rcx, rbp
0x18004b0b1  ja      loc_18004B246
0x18004b0b7  movzx   eax, byte ptr [rdx]
0x18004b0ba  lea     r15, [r13+20h]
0x18004b0be  movzx   esi, byte ptr [rdx+1]
0x18004b0c2  shl     eax, 8
0x18004b0c5  or      esi, eax
0x18004b0c7  mov     [rsp+88h+var_58], rcx
0x18004b0cc  movzx   eax, byte ptr [rdx+2]
0x18004b0d0  shl     esi, 8
0x18004b0d3  or      esi, eax
0x18004b0d5  movzx   eax, byte ptr [rdx+3]
0x18004b0d9  shl     esi, 8
0x18004b0dc  lea     edx, [r14+3]
0x18004b0e0  or      esi, eax
0x18004b0e2  mov     eax, edx
0x18004b0e4  cmp     [r15], r14d
0x18004b0e7  jnz     short loc_18004B0EE
0x18004b0e9  movzx   eax, word ptr [r15+4]
0x18004b0ee  imul    eax, esi
0x18004b0f1  add     rax, rcx
0x18004b0f4  cmp     rax, rcx
0x18004b0f7  jb      loc_18004B246
0x18004b0fd  cmp     [r15], r14d
0x18004b100  jnz     short loc_18004B107
0x18004b102  movzx   edx, word ptr [r13+24h]
0x18004b107  imul    edx, esi
0x18004b10a  mov     eax, edx
0x18004b10c  add     rax, rcx
0x18004b10f  cmp     rax, rbp
0x18004b112  ja      loc_18004B246
0x18004b118  mov     rdi, r14
0x18004b11b  test    esi, esi
0x18004b11d  jz      short loc_18004B13B
0x18004b11f  mov     ecx, 18h; unsigned __int64
0x18004b124  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x18004b129  mov     rdi, rax
0x18004b12c  test    rax, rax
0x18004b12f  jz      short loc_18004B189
0x18004b131  mov     [rax], r14
0x18004b134  mov     [rax+10h], r14
0x18004b138  mov     [rax+8], esi
0x18004b13b  cmp     r14d, esi
0x18004b13e  jnb     short loc_18004B1A9
0x18004b140  lea     r9, [rsp+88h+arg_10]; unsigned __int8 **
0x18004b148  mov     qword ptr [rsp+88h+arg_10.fIsVariable], 0
0x18004b154  mov     r8, rbp; unsigned __int8 *
0x18004b157  lea     rdx, [rsp+88h+var_58]; unsigned __int8 **
0x18004b15c  mov     rcx, r15; this
0x18004b15f  call    ?DeserializeId@IdParameterPair@@QEAAJPEAPEBEPEBEPEAPEAEH@Z; IdParameterPair::DeserializeId(uchar const * *,uchar const *,uchar * *,int)
0x18004b164  mov     ebx, eax
0x18004b166  test    eax, eax
0x18004b168  js      loc_18004B217
0x18004b16e  lea     rdx, [rsp+88h+arg_10]
0x18004b176  mov     rcx, rdi
0x18004b179  call    ?Add@?$Vector@PEAE$0A@@@QEAAJAEBQEAE@Z; Vector<uchar *,0>::Add(uchar * const &)
0x18004b17e  mov     ebx, eax
0x18004b180  test    eax, eax
0x18004b182  js      short loc_18004B19A
0x18004b184  inc     r14d
0x18004b187  jmp     short loc_18004B13B
0x18004b189  mov     ebx, 8007000Eh
0x18004b18e  mov     r10, cs:WPP_GLOBAL_Control
0x18004b195  jmp     loc_18004B24B
0x18004b19a  mov     rcx, qword ptr [rsp+88h+arg_10.fIsVariable]; unsigned __int8 *
0x18004b1a2  call    ?FreeId@IdParameters@@SAXPEAE@Z; IdParameters::FreeId(uchar *)
0x18004b1a7  jmp     short loc_18004B217
0x18004b1a9  mov     ecx, 30h ; '0'; unsigned __int64
0x18004b1ae  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x18004b1b3  mov     rsi, rax
0x18004b1b6  test    rax, rax
0x18004b1b9  jz      short loc_18004B212
0x18004b1bb  mov     r8d, r12d; unsigned int
0x18004b1be  mov     rdx, r13; struct IdParameters *
0x18004b1c1  mov     rcx, rax; this
0x18004b1c4  call    ??0FilterInfo@@IEAA@PEAVIdParameters@@K@Z; FilterInfo::FilterInfo(IdParameters *,ulong)
0x18004b1c9  mov     r8, [rsp+88h+arg_20]
0x18004b1d1  lea     r9, ??_7ListBasedFilterInfo@@6BFilterInfo@@@; const ListBasedFilterInfo::`vftable'{for `FilterInfo'}
0x18004b1d8  lea     rax, ??_7ListBasedFilterInfo@@6BIChangeUnitListFilterInfo@@@; const ListBasedFilterInfo::`vftable'{for `IChangeUnitListFilterInfo'}
0x18004b1df  mov     [rcx], r9
0x18004b1e2  mov     [rcx+20h], rax
0x18004b1e6  lea     rdx, IID_ISyncFilterInfo
0x18004b1ed  mov     rax, [r9]
0x18004b1f0  mov     [rcx+28h], rdi
0x18004b1f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b1f9  mov     ebx, eax
0x18004b1fb  mov     rcx, rsi
0x18004b1fe  mov     rax, [rsi]
0x18004b201  mov     rax, [rax+10h]
0x18004b205  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b20a  test    ebx, ebx
0x18004b20c  jns     short loc_18004B18E
0x18004b20e  xor     edi, edi
0x18004b210  jmp     short loc_18004B217
0x18004b212  mov     ebx, 8007000Eh
0x18004b217  test    rdi, rdi
0x18004b21a  jz      loc_18004B18E
0x18004b220  xor     esi, esi
0x18004b222  cmp     [rdi], esi
0x18004b224  jbe     short loc_18004B239
0x18004b226  mov     rcx, [rdi+10h]
0x18004b22a  mov     rcx, [rcx+rsi*8]; unsigned __int8 *
0x18004b22e  call    ?FreeId@IdParameters@@SAXPEAE@Z; IdParameters::FreeId(uchar *)
0x18004b233  inc     esi
0x18004b235  cmp     esi, [rdi]
0x18004b237  jb      short loc_18004B226
0x18004b239  mov     rcx, rdi; void *
0x18004b23c  call    ??_G?$Vector@PEAE$0A@@@QEAAPEAXI@Z; Vector<uchar *,0>::`scalar deleting destructor'(uint)
0x18004b241  jmp     loc_18004B18E
0x18004b246  mov     ebx, 8004100Ch
0x18004b24b  lea     rax, WPP_GLOBAL_Control
0x18004b252  cmp     r10, rax
0x18004b255  jz      short loc_18004B285
0x18004b257  test    byte ptr [r10+1Ch], 40h
0x18004b25c  jz      short loc_18004B285
0x18004b25e  cmp     byte ptr [r10+19h], 5
0x18004b263  jb      short loc_18004B285
0x18004b265  mov     rcx, [r10+10h]
0x18004b269  lea     r9, aListbasedfilte_1; "ListBasedFilterInfo::Deserialize"
0x18004b270  mov     edx, 15h
0x18004b275  mov     [rsp+88h+var_68], ebx
0x18004b279  lea     r8, WPP_8c3e8ceaadcc3625839d548a135dd323_Traceguids
0x18004b280  call    WPP_SF_sD
0x18004b285  mov     eax, ebx
0x18004b287  add     rsp, 48h
0x18004b28b  pop     r15
0x18004b28d  pop     r14
0x18004b28f  pop     r13
0x18004b291  pop     r12
0x18004b293  pop     rdi
0x18004b294  pop     rsi
0x18004b295  pop     rbp
0x18004b296  pop     rbx
0x18004b297  retn
```
