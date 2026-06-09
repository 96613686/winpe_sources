# CustomFilterInfo::Deserialize(ISyncFilterDeserializer *,IdParameters *,uchar const *,ulong,ISyncFilterInfo * *)

- ea: `0x18005e250`
- end: `0x18005e3c2`
- name: `?Deserialize@CustomFilterInfo@@SAJPEAUISyncFilterDeserializer@@PEAVIdParameters@@PEBEKPEAPEAUISyncFilterInfo@@@Z`
- size: `370`
- prototype: `__int64 __fastcall(struct ISyncFilterDeserializer *, struct IdParameters *, const unsigned __int8 *, unsigned int, struct ISyncFilterInfo **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18004b9fc`

## callees

- `0x18000a0f0`
- `0x18001a038`
- `0x18001ae20`
- `0x18005e078`
- `0x18005e250`
- `0x180094010`

## string_xrefs

- `0x18005e28c`: `CustomFilterInfo::Deserialize`
- `0x18005e397`: `CustomFilterInfo::Deserialize`

## pseudocode

```c
__int64 __fastcall CustomFilterInfo::Deserialize(
        struct ISyncFilterDeserializer *a1,
        struct IdParameters *a2,
        const unsigned __int8 *a3,
        unsigned int a4,
        struct ISyncFilterInfo **a5)
{
  __int64 v5; // rsi
  PVOID *v9; // rcx
  unsigned int v10; // edi
  CustomFilterInfo *v11; // rbx
  CustomFilterInfo *v12; // rax
  CustomFilterInfo *v13; // rax
  struct ISyncFilter *v15; // [rsp+70h] [rbp+8h] BYREF

  v5 = a4;
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      18,
      WPP_37465e2f2e533080cb8ec187738be578_Traceguids,
      "CustomFilterInfo::Deserialize");
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  v15 = 0;
  if ( a1 && (!(_DWORD)v5 || a3) )
  {
    if ( &a3[v5] >= a3 )
    {
      v11 = 0;
      v10 = ((__int64 (__fastcall *)(struct ISyncFilterDeserializer *, const unsigned __int8 *, _QWORD, struct ISyncFilter **))a1->lpVtbl->DeserializeSyncFilter)(
              a1,
              a3,
              (unsigned int)v5,
              &v15);
      if ( !v10 )
      {
        v12 = (CustomFilterInfo *)SeAlloc(0x30u);
        if ( v12 && (v13 = CustomFilterInfo::CustomFilterInfo(v12, a2, v15), (v11 = v13) != 0) )
          v10 = (**(__int64 (__fastcall ***)(CustomFilterInfo *, GUID *, struct ISyncFilterInfo **))v13)(
                  v13,
                  &IID_ISyncFilterInfo,
                  a5);
        else
          v10 = -2147024882;
      }
      if ( v15 )
        ((void (__fastcall *)(struct ISyncFilter *))v15->lpVtbl->Release)(v15);
      if ( v11 )
        (*(void (__fastcall **)(CustomFilterInfo *))(*(_QWORD *)v11 + 16LL))(v11);
      v9 = (PVOID *)WPP_GLOBAL_Control;
    }
    else
    {
      v10 = -2147217396;
    }
  }
  else
  {
    v10 = -2147467261;
  }
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 0x40) != 0 && *((_BYTE *)v9 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v9[2],
      19,
      (unsigned int)WPP_37465e2f2e533080cb8ec187738be578_Traceguids,
      (unsigned int)"CustomFilterInfo::Deserialize",
      v10);
  return v10;
}

```

## disassembly

```asm
0x18005e250  push    rbx
0x18005e252  push    rbp
0x18005e253  push    rsi
0x18005e254  push    rdi
0x18005e255  push    r14
0x18005e257  push    r15
0x18005e259  sub     rsp, 38h
0x18005e25d  mov     esi, r9d
0x18005e260  mov     rdi, r8
0x18005e263  mov     rbp, rdx
0x18005e266  mov     r14, rcx
0x18005e269  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e270  lea     r15, WPP_GLOBAL_Control
0x18005e277  cmp     rcx, r15
0x18005e27a  jz      short loc_18005E2AB
0x18005e27c  test    byte ptr [rcx+1Ch], 40h
0x18005e280  jz      short loc_18005E2AB
0x18005e282  cmp     byte ptr [rcx+19h], 5
0x18005e286  jb      short loc_18005E2AB
0x18005e288  mov     rcx, [rcx+10h]
0x18005e28c  lea     r9, aCustomfilterin_1; "CustomFilterInfo::Deserialize"
0x18005e293  mov     edx, 12h
0x18005e298  lea     r8, WPP_37465e2f2e533080cb8ec187738be578_Traceguids
0x18005e29f  call    WPP_SF_s
0x18005e2a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e2ab  mov     [rsp+68h+arg_0], 0
0x18005e2b4  test    r14, r14
0x18005e2b7  jz      loc_18005E37D
0x18005e2bd  test    esi, esi
0x18005e2bf  jz      short loc_18005E2CA
0x18005e2c1  test    rdi, rdi
0x18005e2c4  jz      loc_18005E37D
0x18005e2ca  lea     rax, [rdi+rsi]
0x18005e2ce  cmp     rax, rdi
0x18005e2d1  jnb     short loc_18005E2DD
0x18005e2d3  mov     edi, 8004100Ch
0x18005e2d8  jmp     loc_18005E382
0x18005e2dd  mov     rax, [r14]
0x18005e2e0  lea     r9, [rsp+68h+arg_0]
0x18005e2e5  mov     r8d, esi
0x18005e2e8  mov     rdx, rdi
0x18005e2eb  mov     rcx, r14
0x18005e2ee  xor     ebx, ebx
0x18005e2f0  mov     rax, [rax+18h]
0x18005e2f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e2f9  mov     edi, eax
0x18005e2fb  test    eax, eax
0x18005e2fd  jnz     short loc_18005E34A
0x18005e2ff  lea     ecx, [rbx+30h]; unsigned __int64
0x18005e302  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x18005e307  test    rax, rax
0x18005e30a  jz      short loc_18005E345
0x18005e30c  mov     r8, [rsp+68h+arg_0]; struct ISyncFilter *
0x18005e311  mov     rdx, rbp; struct IdParameters *
0x18005e314  mov     rcx, rax; this
0x18005e317  call    ??0CustomFilterInfo@@AEAA@PEAVIdParameters@@PEAUISyncFilter@@@Z; CustomFilterInfo::CustomFilterInfo(IdParameters *,ISyncFilter *)
0x18005e31c  mov     rbx, rax
0x18005e31f  test    rax, rax
0x18005e322  jz      short loc_18005E345
0x18005e324  mov     rax, [rax]
0x18005e327  lea     rdx, IID_ISyncFilterInfo
0x18005e32e  mov     r8, [rsp+68h+arg_20]
0x18005e336  mov     rcx, rbx
0x18005e339  mov     rax, [rax]
0x18005e33c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e341  mov     edi, eax
0x18005e343  jmp     short loc_18005E34A
0x18005e345  mov     edi, 8007000Eh
0x18005e34a  mov     rcx, [rsp+68h+arg_0]
0x18005e34f  test    rcx, rcx
0x18005e352  jz      short loc_18005E360
0x18005e354  mov     rax, [rcx]
0x18005e357  mov     rax, [rax+10h]
0x18005e35b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e360  test    rbx, rbx
0x18005e363  jz      short loc_18005E374
0x18005e365  mov     rax, [rbx]
0x18005e368  mov     rcx, rbx
0x18005e36b  mov     rax, [rax+10h]
0x18005e36f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e374  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e37b  jmp     short loc_18005E382
0x18005e37d  mov     edi, 80004003h
0x18005e382  cmp     rcx, r15
0x18005e385  jz      short loc_18005E3B3
0x18005e387  test    byte ptr [rcx+1Ch], 40h
0x18005e38b  jz      short loc_18005E3B3
0x18005e38d  cmp     byte ptr [rcx+19h], 5
0x18005e391  jb      short loc_18005E3B3
0x18005e393  mov     rcx, [rcx+10h]
0x18005e397  lea     r9, aCustomfilterin_1; "CustomFilterInfo::Deserialize"
0x18005e39e  mov     edx, 13h
0x18005e3a3  mov     [rsp+68h+var_48], edi
0x18005e3a7  lea     r8, WPP_37465e2f2e533080cb8ec187738be578_Traceguids
0x18005e3ae  call    WPP_SF_sD
0x18005e3b3  mov     eax, edi
0x18005e3b5  add     rsp, 38h
0x18005e3b9  pop     r15
0x18005e3bb  pop     r14
0x18005e3bd  pop     rdi
0x18005e3be  pop     rsi
0x18005e3bf  pop     rbp
0x18005e3c0  pop     rbx
0x18005e3c1  retn
```
