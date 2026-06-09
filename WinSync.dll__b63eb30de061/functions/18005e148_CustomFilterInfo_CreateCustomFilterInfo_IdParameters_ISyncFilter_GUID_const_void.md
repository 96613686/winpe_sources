# CustomFilterInfo::CreateCustomFilterInfo(IdParameters *,ISyncFilter *,_GUID const &,void * *)

- ea: `0x18005e148`
- end: `0x18005e24a`
- name: `?CreateCustomFilterInfo@CustomFilterInfo@@SAJPEAVIdParameters@@PEAUISyncFilter@@AEBU_GUID@@PEAPEAX@Z`
- size: `258`
- prototype: `__int64 __fastcall(struct IdParameters *, struct ISyncFilter *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18002b4b0`

## callees

- `0x18000a0f0`
- `0x18001a038`
- `0x18001ae20`
- `0x18005e078`
- `0x18005e148`
- `0x180094010`

## string_xrefs

- `0x18005e17d`: `CustomFilterInfo::CreateCustomFilterInfo`
- `0x18005e223`: `CustomFilterInfo::CreateCustomFilterInfo`

## pseudocode

```c
__int64 __fastcall CustomFilterInfo::CreateCustomFilterInfo(
        struct IdParameters *a1,
        struct ISyncFilter *a2,
        const struct _GUID *a3,
        void **a4)
{
  PVOID *v7; // rcx
  CustomFilterInfo *v8; // rax
  CustomFilterInfo *v9; // rax
  CustomFilterInfo *v10; // rdi
  unsigned int v11; // ebx

  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_37465e2f2e533080cb8ec187738be578_Traceguids,
      "CustomFilterInfo::CreateCustomFilterInfo");
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a1 && a2 && a4 )
  {
    v8 = (CustomFilterInfo *)SeAlloc(0x30u);
    if ( v8 && (v9 = CustomFilterInfo::CustomFilterInfo(v8, a1, a2), (v10 = v9) != 0) )
    {
      v11 = (**(__int64 (__fastcall ***)(CustomFilterInfo *, GUID *, void **))v9)(
              v9,
              &GUID_1d335dff_6f88_4e4d_91a8_a3f351cfd473,
              a4);
      (*(void (__fastcall **)(CustomFilterInfo *))(*(_QWORD *)v10 + 16LL))(v10);
    }
    else
    {
      v11 = -2147024882;
    }
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    v11 = -2147467261;
  }
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x40) != 0 && *((_BYTE *)v7 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v7[2],
      11,
      (unsigned int)WPP_37465e2f2e533080cb8ec187738be578_Traceguids,
      (unsigned int)"CustomFilterInfo::CreateCustomFilterInfo",
      v11);
  return v11;
}

```

## disassembly

```asm
0x18005e148  push    rbx
0x18005e14a  push    rbp
0x18005e14b  push    rsi
0x18005e14c  push    rdi
0x18005e14d  sub     rsp, 38h
0x18005e151  mov     rsi, r9
0x18005e154  mov     rbx, rdx
0x18005e157  mov     rdi, rcx
0x18005e15a  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e161  lea     rbp, WPP_GLOBAL_Control
0x18005e168  cmp     rcx, rbp
0x18005e16b  jz      short loc_18005E19C
0x18005e16d  test    byte ptr [rcx+1Ch], 40h
0x18005e171  jz      short loc_18005E19C
0x18005e173  cmp     byte ptr [rcx+19h], 5
0x18005e177  jb      short loc_18005E19C
0x18005e179  mov     rcx, [rcx+10h]
0x18005e17d  lea     r9, aCustomfilterin; "CustomFilterInfo::CreateCustomFilterInf"...
0x18005e184  mov     edx, 0Ah
0x18005e189  lea     r8, WPP_37465e2f2e533080cb8ec187738be578_Traceguids
0x18005e190  call    WPP_SF_s
0x18005e195  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e19c  test    rdi, rdi
0x18005e19f  jz      short loc_18005E209
0x18005e1a1  test    rbx, rbx
0x18005e1a4  jz      short loc_18005E209
0x18005e1a6  test    rsi, rsi
0x18005e1a9  jz      short loc_18005E209
0x18005e1ab  mov     ecx, 30h ; '0'; unsigned __int64
0x18005e1b0  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x18005e1b5  test    rax, rax
0x18005e1b8  jz      short loc_18005E1FB
0x18005e1ba  mov     r8, rbx; struct ISyncFilter *
0x18005e1bd  mov     rdx, rdi; struct IdParameters *
0x18005e1c0  mov     rcx, rax; this
0x18005e1c3  call    ??0CustomFilterInfo@@AEAA@PEAVIdParameters@@PEAUISyncFilter@@@Z; CustomFilterInfo::CustomFilterInfo(IdParameters *,ISyncFilter *)
0x18005e1c8  mov     rdi, rax
0x18005e1cb  test    rax, rax
0x18005e1ce  jz      short loc_18005E1FB
0x18005e1d0  mov     rcx, [rax]
0x18005e1d3  lea     rdx, _GUID_1d335dff_6f88_4e4d_91a8_a3f351cfd473
0x18005e1da  mov     r8, rsi
0x18005e1dd  mov     rax, [rcx]
0x18005e1e0  mov     rcx, rdi
0x18005e1e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e1e8  mov     rcx, [rdi]
0x18005e1eb  mov     ebx, eax
0x18005e1ed  mov     rax, [rcx+10h]
0x18005e1f1  mov     rcx, rdi
0x18005e1f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e1f9  jmp     short loc_18005E200
0x18005e1fb  mov     ebx, 8007000Eh
0x18005e200  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e207  jmp     short loc_18005E20E
0x18005e209  mov     ebx, 80004003h
0x18005e20e  cmp     rcx, rbp
0x18005e211  jz      short loc_18005E23F
0x18005e213  test    byte ptr [rcx+1Ch], 40h
0x18005e217  jz      short loc_18005E23F
0x18005e219  cmp     byte ptr [rcx+19h], 5
0x18005e21d  jb      short loc_18005E23F
0x18005e21f  mov     rcx, [rcx+10h]
0x18005e223  lea     r9, aCustomfilterin; "CustomFilterInfo::CreateCustomFilterInf"...
0x18005e22a  mov     edx, 0Bh
0x18005e22f  mov     [rsp+58h+var_38], ebx
0x18005e233  lea     r8, WPP_37465e2f2e533080cb8ec187738be578_Traceguids
0x18005e23a  call    WPP_SF_sD
0x18005e23f  mov     eax, ebx
0x18005e241  add     rsp, 38h
0x18005e245  pop     rdi
0x18005e246  pop     rsi
0x18005e247  pop     rbp
0x18005e248  pop     rbx
0x18005e249  retn
```
