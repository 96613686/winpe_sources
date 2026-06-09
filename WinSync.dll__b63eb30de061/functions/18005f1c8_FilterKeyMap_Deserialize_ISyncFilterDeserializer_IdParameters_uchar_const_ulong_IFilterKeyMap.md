# FilterKeyMap::Deserialize(ISyncFilterDeserializer *,IdParameters *,uchar const *,ulong,IFilterKeyMap * *)

- ea: `0x18005f1c8`
- end: `0x18005f431`
- name: `?Deserialize@FilterKeyMap@@SAJPEAUISyncFilterDeserializer@@PEAVIdParameters@@PEBEKPEAPEAUIFilterKeyMap@@@Z`
- size: `617`
- prototype: `__int64 __fastcall(struct ISyncFilterDeserializer *, struct IdParameters *, const unsigned __int8 *, unsigned int, struct IFilterKeyMap **)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18002cc70`
- `0x18004e754`

## callees

- `0x18000a0f0`
- `0x18001a038`
- `0x18001ae20`
- `0x18002ae24`
- `0x18005f1c8`
- `0x180094010`

## string_xrefs

- `0x18005f20e`: `FilterKeyMap::Deserialize`
- `0x18005f402`: `FilterKeyMap::Deserialize`

## pseudocode

```c
__int64 __fastcall FilterKeyMap::Deserialize(
        struct ISyncFilterDeserializer *a1,
        struct IdParameters *a2,
        const unsigned __int8 *a3,
        unsigned int a4,
        struct IFilterKeyMap **a5)
{
  __int64 v5; // rbx
  PVOID *v9; // r10
  __int64 v10; // rbp
  FilterKeyMap *v11; // rax
  struct IFilterKeyMap *v12; // r14
  unsigned int v13; // r12d
  unsigned int v14; // esi
  unsigned int v15; // edi
  int v16; // eax
  int v18; // [rsp+30h] [rbp-58h]
  _QWORD v19[10]; // [rsp+38h] [rbp-50h] BYREF

  v5 = a4;
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      20,
      WPP_ce263884cabe391074f7051e3bc29b0c_Traceguids,
      "FilterKeyMap::Deserialize");
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a1 && a2 && a3 && a5 )
  {
    if ( &a3[v5] < a3
      || (v18 = 6, (unsigned int)v5 < 6)
      || _byteswap_ushort(*(_WORD *)a3) < 5u
      || (v10 = a3[5] | ((a3[4] | ((a3[3] | (a3[2] << 8)) << 8)) << 8),
          (unsigned int)(v5 - 6) < (unsigned __int64)(4 * v10)) )
    {
      v14 = -2147217396;
    }
    else
    {
      v11 = (FilterKeyMap *)SeAlloc(0x28u);
      if ( v11 && (v12 = (struct IFilterKeyMap *)FilterKeyMap::FilterKeyMap(v11, a2)) != 0 )
      {
        v13 = 0;
        v14 = 0;
        while ( v13 < (unsigned int)v10 )
        {
          v19[0] = 0;
          v15 = a3[v18 + 3] | ((a3[v18 + 2] | ((a3[v18 + 1] | (a3[v18] << 8)) << 8)) << 8);
          v14 = ((__int64 (__fastcall *)(struct ISyncFilterDeserializer *, const unsigned __int8 *, _QWORD, _QWORD *))a1->lpVtbl->DeserializeSyncFilter)(
                  a1,
                  &a3[v18 + 4],
                  v15,
                  v19);
          v16 = v18 + 4 + v15;
          if ( v14 )
            v16 = v18 + 4;
          v18 = v16;
          if ( !v14 )
            v14 = ((__int64 (__fastcall *)(struct IFilterKeyMap *, _QWORD, _QWORD))v12->lpVtbl->AddFilter)(
                    v12,
                    v19[0],
                    0);
          if ( v19[0] )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v19[0] + 16LL))(v19[0]);
          ++v13;
          if ( v14 )
            goto LABEL_26;
        }
        *a5 = v12;
        ((void (__fastcall *)(struct IFilterKeyMap *))v12->lpVtbl->AddRef)(v12);
LABEL_26:
        ((void (__fastcall *)(struct IFilterKeyMap *))v12->lpVtbl->Release)(v12);
      }
      else
      {
        v14 = -2147024882;
      }
      v9 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  else
  {
    v14 = -2147467261;
  }
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 0x40) != 0 && *((_BYTE *)v9 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v9[2],
      21,
      (unsigned int)WPP_ce263884cabe391074f7051e3bc29b0c_Traceguids,
      (unsigned int)"FilterKeyMap::Deserialize",
      v14);
  return v14;
}

```

## disassembly

```asm
0x18005f1c8  mov     [rsp+arg_0], rcx
0x18005f1cd  push    rbx
0x18005f1ce  push    rbp
0x18005f1cf  push    rsi
0x18005f1d0  push    rdi
0x18005f1d1  push    r12
0x18005f1d3  push    r13
0x18005f1d5  push    r14
0x18005f1d7  push    r15
0x18005f1d9  sub     rsp, 48h
0x18005f1dd  mov     ebx, r9d
0x18005f1e0  mov     r15, r8
0x18005f1e3  mov     rdi, rdx
0x18005f1e6  mov     rsi, rcx
0x18005f1e9  mov     r10, cs:WPP_GLOBAL_Control
0x18005f1f0  lea     rax, WPP_GLOBAL_Control
0x18005f1f7  cmp     r10, rax
0x18005f1fa  jz      short loc_18005F22D
0x18005f1fc  test    byte ptr [r10+1Ch], 40h
0x18005f201  jz      short loc_18005F22D
0x18005f203  cmp     byte ptr [r10+19h], 5
0x18005f208  jb      short loc_18005F22D
0x18005f20a  mov     rcx, [r10+10h]
0x18005f20e  lea     r9, aFilterkeymapDe; "FilterKeyMap::Deserialize"
0x18005f215  mov     edx, 14h
0x18005f21a  lea     r8, WPP_ce263884cabe391074f7051e3bc29b0c_Traceguids
0x18005f221  call    WPP_SF_s
0x18005f226  mov     r10, cs:WPP_GLOBAL_Control
0x18005f22d  test    rsi, rsi
0x18005f230  jz      loc_18005F3DF
0x18005f236  test    rdi, rdi
0x18005f239  jz      loc_18005F3DF
0x18005f23f  test    r15, r15
0x18005f242  jz      loc_18005F3DF
0x18005f248  mov     r13, [rsp+88h+arg_20]
0x18005f250  test    r13, r13
0x18005f253  jz      loc_18005F3DF
0x18005f259  lea     rax, [r15+rbx]
0x18005f25d  cmp     rax, r15
0x18005f260  jb      loc_18005F3D8
0x18005f266  mov     eax, 6
0x18005f26b  mov     [rsp+88h+var_58], eax
0x18005f26f  cmp     ebx, eax
0x18005f271  jb      loc_18005F3D8
0x18005f277  movzx   ecx, byte ptr [r15]
0x18005f27b  movzx   eax, byte ptr [r15+1]
0x18005f280  shl     cx, 8
0x18005f284  or      cx, ax
0x18005f287  cmp     cx, 5
0x18005f28b  jb      loc_18005F3D8
0x18005f291  movzx   eax, byte ptr [r15+3]
0x18005f296  lea     ecx, [rbx-6]
0x18005f299  movzx   ebp, byte ptr [r15+2]
0x18005f29e  shl     ebp, 8
0x18005f2a1  or      ebp, eax
0x18005f2a3  movzx   eax, byte ptr [r15+4]
0x18005f2a8  shl     ebp, 8
0x18005f2ab  or      ebp, eax
0x18005f2ad  movzx   eax, byte ptr [r15+5]
0x18005f2b2  shl     ebp, 8
0x18005f2b5  or      ebp, eax
0x18005f2b7  mov     edx, ebp
0x18005f2b9  shl     rdx, 2
0x18005f2bd  cmp     rcx, rdx
0x18005f2c0  jb      loc_18005F3D8
0x18005f2c6  mov     ecx, 28h ; '('; unsigned __int64
0x18005f2cb  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x18005f2d0  test    rax, rax
0x18005f2d3  jz      loc_18005F3CA
0x18005f2d9  mov     rdx, rdi; struct IdParameters *
0x18005f2dc  mov     rcx, rax; this
0x18005f2df  call    ??0FilterKeyMap@@QEAA@PEAVIdParameters@@@Z; FilterKeyMap::FilterKeyMap(IdParameters *)
0x18005f2e4  mov     r14, rax
0x18005f2e7  test    rax, rax
0x18005f2ea  jz      loc_18005F3CA
0x18005f2f0  xor     r12d, r12d
0x18005f2f3  xor     esi, esi
0x18005f2f5  cmp     r12d, ebp
0x18005f2f8  jnb     loc_18005F3A1
0x18005f2fe  mov     ebx, [rsp+88h+var_58]
0x18005f302  lea     r9, [rsp+88h+var_50]
0x18005f307  mov     rcx, [rsp+88h+arg_0]
0x18005f30f  mov     [rsp+88h+var_50], 0
0x18005f318  movzx   eax, byte ptr [rbx+r15+1]
0x18005f31e  movzx   edi, byte ptr [rbx+r15]
0x18005f323  shl     edi, 8
0x18005f326  or      edi, eax
0x18005f328  movzx   eax, byte ptr [rbx+r15+2]
0x18005f32e  shl     edi, 8
0x18005f331  or      edi, eax
0x18005f333  movzx   eax, byte ptr [rbx+r15+3]
0x18005f339  shl     edi, 8
0x18005f33c  add     ebx, 4
0x18005f33f  or      edi, eax
0x18005f341  mov     edx, ebx
0x18005f343  mov     rax, [rcx]
0x18005f346  add     rdx, r15
0x18005f349  mov     r8d, edi
0x18005f34c  mov     rax, [rax+18h]
0x18005f350  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f355  mov     esi, eax
0x18005f357  lea     eax, [rbx+rdi]
0x18005f35a  test    esi, esi
0x18005f35c  cmovnz  eax, ebx
0x18005f35f  mov     [rsp+88h+var_58], eax
0x18005f363  jnz     short loc_18005F37E
0x18005f365  mov     rax, [r14]
0x18005f368  xor     r8d, r8d
0x18005f36b  mov     rdx, [rsp+88h+var_50]
0x18005f370  mov     rcx, r14
0x18005f373  mov     rax, [rax+20h]
0x18005f377  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f37c  mov     esi, eax
0x18005f37e  mov     rcx, [rsp+88h+var_50]
0x18005f383  test    rcx, rcx
0x18005f386  jz      short loc_18005F394
0x18005f388  mov     rax, [rcx]
0x18005f38b  mov     rax, [rax+10h]
0x18005f38f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f394  inc     r12d
0x18005f397  test    esi, esi
0x18005f399  jz      loc_18005F2F5
0x18005f39f  jmp     short loc_18005F3B4
0x18005f3a1  mov     [r13+0], r14
0x18005f3a5  mov     rcx, r14
0x18005f3a8  mov     rax, [r14]
0x18005f3ab  mov     rax, [rax+8]
0x18005f3af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f3b4  test    r14, r14
0x18005f3b7  jz      short loc_18005F3CF
0x18005f3b9  mov     rax, [r14]
0x18005f3bc  mov     rcx, r14
0x18005f3bf  mov     rax, [rax+10h]
0x18005f3c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f3c8  jmp     short loc_18005F3CF
0x18005f3ca  mov     esi, 8007000Eh
0x18005f3cf  mov     r10, cs:WPP_GLOBAL_Control
0x18005f3d6  jmp     short loc_18005F3E4
0x18005f3d8  mov     esi, 8004100Ch
0x18005f3dd  jmp     short loc_18005F3E4
0x18005f3df  mov     esi, 80004003h
0x18005f3e4  lea     rax, WPP_GLOBAL_Control
0x18005f3eb  cmp     r10, rax
0x18005f3ee  jz      short loc_18005F41E
0x18005f3f0  test    byte ptr [r10+1Ch], 40h
0x18005f3f5  jz      short loc_18005F41E
0x18005f3f7  cmp     byte ptr [r10+19h], 5
0x18005f3fc  jb      short loc_18005F41E
0x18005f3fe  mov     rcx, [r10+10h]
0x18005f402  lea     r9, aFilterkeymapDe; "FilterKeyMap::Deserialize"
0x18005f409  mov     edx, 15h
0x18005f40e  mov     [rsp+88h+var_68], esi
0x18005f412  lea     r8, WPP_ce263884cabe391074f7051e3bc29b0c_Traceguids
0x18005f419  call    WPP_SF_sD
0x18005f41e  mov     eax, esi
0x18005f420  add     rsp, 48h
0x18005f424  pop     r15
0x18005f426  pop     r14
0x18005f428  pop     r13
0x18005f42a  pop     r12
0x18005f42c  pop     rdi
0x18005f42d  pop     rsi
0x18005f42e  pop     rbp
0x18005f42f  pop     rbx
0x18005f430  retn
```
