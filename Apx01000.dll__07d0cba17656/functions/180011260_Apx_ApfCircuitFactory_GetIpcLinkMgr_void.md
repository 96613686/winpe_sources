# Apx::ApfCircuitFactory::GetIpcLinkMgr(void)

- ea: `0x180011260`
- end: `0x180011402`
- name: `?GetIpcLinkMgr@ApfCircuitFactory@Apx@@AEAAJXZ`
- size: `418`
- prototype: `__int64 __fastcall(Apx::ApfCircuitFactory *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180011408`

## callees

- `0x180002160`
- `0x18000a12c`
- `0x18000a1b4`
- `0x180011260`
- `0x180025888`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall Apx::ApfCircuitFactory::GetIpcLinkMgr(Apx::ApfCircuitFactory *this)
{
  _QWORD *v2; // rcx
  char v3; // bl
  Apx::ApfIpcIoLinkMgr *v4; // rbp
  Apx::ApfIpcIoLinkMgr *v5; // rax
  void (*v6)(void *, bool, bool); // r9
  Apx::ApfIpcIoLinkMgr *v7; // rax
  Apx::ApfIpcIoLinkMgr *v8; // rdi
  int v9; // ebx
  _QWORD *v10; // rcx

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_88d8f9f30453351596b6a72932727db3_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  v3 = *((_BYTE *)this + 16) & 1;
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 && *((_BYTE *)v2 + 25) >= 5u )
    WPP_SF_(v2[2], 10, &WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids);
  v4 = 0;
  v5 = (Apx::ApfIpcIoLinkMgr *)operator new(0x280u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v5 )
  {
    v7 = Apx::ApfIpcIoLinkMgr::ApfIpcIoLinkMgr(v5, (const struct _GUID *)((char *)this + 120), v3, v6, this);
    v8 = v7;
    if ( v7 )
    {
      v9 = (*(__int64 (__fastcall **)(Apx::ApfIpcIoLinkMgr *))(*(_QWORD *)v7 + 72LL))(v7);
      if ( v9 < 0 )
      {
        (**(void (__fastcall ***)(Apx::ApfIpcIoLinkMgr *, __int64))v8)(v8, 1);
      }
      else
      {
        v4 = v8;
        v9 = 0;
      }
      goto LABEL_18;
    }
  }
  v9 = -2147024882;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return (unsigned int)v9;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids);
LABEL_18:
    v10 = WPP_GLOBAL_Control;
  }
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 1) != 0 && *((_BYTE *)v10 + 25) >= 5u )
  {
    WPP_SF_(v10[2], 12, &WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids);
    v10 = WPP_GLOBAL_Control;
  }
  if ( v9 >= 0 )
  {
    *((_QWORD *)this + 17) = v4;
    v9 = 0;
    v10 = WPP_GLOBAL_Control;
  }
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 1) != 0 && *((_BYTE *)v10 + 25) >= 5u )
    WPP_SF_(v10[2], 25, &WPP_88d8f9f30453351596b6a72932727db3_Traceguids);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180011260  mov     [rsp+arg_8], rbx
0x180011265  mov     [rsp+arg_10], rbp
0x18001126a  push    rsi
0x18001126b  push    rdi
0x18001126c  push    r15
0x18001126e  sub     rsp, 30h
0x180011272  mov     rsi, rcx
0x180011275  mov     rcx, cs:WPP_GLOBAL_Control
0x18001127c  lea     r15, WPP_GLOBAL_Control
0x180011283  cmp     rcx, r15
0x180011286  jz      short loc_1800112B0
0x180011288  test    byte ptr [rcx+1Ch], 1
0x18001128c  jz      short loc_1800112B0
0x18001128e  cmp     byte ptr [rcx+19h], 5
0x180011292  jb      short loc_1800112B0
0x180011294  mov     rcx, [rcx+10h]
0x180011298  lea     r8, WPP_88d8f9f30453351596b6a72932727db3_Traceguids
0x18001129f  mov     edx, 18h
0x1800112a4  call    WPP_SF_
0x1800112a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800112b0  mov     bl, [rsi+10h]
0x1800112b3  and     bl, 1
0x1800112b6  cmp     rcx, r15
0x1800112b9  jz      short loc_1800112DC
0x1800112bb  test    byte ptr [rcx+1Ch], 1
0x1800112bf  jz      short loc_1800112DC
0x1800112c1  cmp     byte ptr [rcx+19h], 5
0x1800112c5  jb      short loc_1800112DC
0x1800112c7  mov     rcx, [rcx+10h]
0x1800112cb  lea     r8, WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids
0x1800112d2  mov     edx, 0Ah
0x1800112d7  call    WPP_SF_
0x1800112dc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800112e3  mov     ecx, 280h; unsigned __int64
0x1800112e8  xor     ebp, ebp
0x1800112ea  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800112ef  mov     [rsp+48h+arg_0], rax
0x1800112f4  test    rax, rax
0x1800112f7  jz      short loc_180011346
0x1800112f9  lea     rdx, [rsi+78h]; struct _GUID *
0x1800112fd  mov     [rsp+48h+var_28], rsi; void *
0x180011302  mov     r8b, bl; bool
0x180011305  mov     rcx, rax; this
0x180011308  call    ??0ApfIpcIoLinkMgr@Apx@@AEAA@PEBU_GUID@@_NP6AXPEAX11@Z2@Z; Apx::ApfIpcIoLinkMgr::ApfIpcIoLinkMgr(_GUID const *,bool,void (*)(void *,bool,bool),void *)
0x18001130d  mov     rdi, rax
0x180011310  test    rax, rax
0x180011313  jz      short loc_180011346
0x180011315  mov     rcx, [rax]
0x180011318  mov     rax, [rcx+48h]
0x18001131c  mov     rcx, rdi
0x18001131f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011324  mov     ebx, eax
0x180011326  test    eax, eax
0x180011328  js      short loc_180011331
0x18001132a  mov     rbp, rdi
0x18001132d  xor     ebx, ebx
0x18001132f  jmp     short loc_18001137F
0x180011331  mov     rax, [rdi]
0x180011334  mov     edx, 1
0x180011339  mov     rcx, rdi
0x18001133c  mov     rax, [rax]
0x18001133f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011344  jmp     short loc_18001137F
0x180011346  mov     ebx, 8007000Eh
0x18001134b  mov     rcx, cs:WPP_GLOBAL_Control
0x180011352  cmp     rcx, r15
0x180011355  jz      loc_1800113ED
0x18001135b  test    byte ptr [rcx+1Ch], 20h
0x18001135f  jz      short loc_180011386
0x180011361  cmp     byte ptr [rcx+19h], 2
0x180011365  jb      short loc_180011386
0x180011367  mov     rcx, [rcx+10h]
0x18001136b  lea     r8, WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids
0x180011372  mov     edx, 0Bh
0x180011377  mov     r9d, ebx
0x18001137a  call    WPP_SF_d
0x18001137f  mov     rcx, cs:WPP_GLOBAL_Control
0x180011386  cmp     rcx, r15
0x180011389  jz      short loc_1800113B3
0x18001138b  test    byte ptr [rcx+1Ch], 1
0x18001138f  jz      short loc_1800113B3
0x180011391  cmp     byte ptr [rcx+19h], 5
0x180011395  jb      short loc_1800113B3
0x180011397  mov     rcx, [rcx+10h]
0x18001139b  lea     r8, WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids
0x1800113a2  mov     edx, 0Ch
0x1800113a7  call    WPP_SF_
0x1800113ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800113b3  test    ebx, ebx
0x1800113b5  js      short loc_1800113C7
0x1800113b7  mov     [rsi+88h], rbp
0x1800113be  xor     ebx, ebx
0x1800113c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800113c7  cmp     rcx, r15
0x1800113ca  jz      short loc_1800113ED
0x1800113cc  test    byte ptr [rcx+1Ch], 1
0x1800113d0  jz      short loc_1800113ED
0x1800113d2  cmp     byte ptr [rcx+19h], 5
0x1800113d6  jb      short loc_1800113ED
0x1800113d8  mov     rcx, [rcx+10h]
0x1800113dc  lea     r8, WPP_88d8f9f30453351596b6a72932727db3_Traceguids
0x1800113e3  mov     edx, 19h
0x1800113e8  call    WPP_SF_
0x1800113ed  mov     rbp, [rsp+48h+arg_10]
0x1800113f2  mov     eax, ebx
0x1800113f4  mov     rbx, [rsp+48h+arg_8]
0x1800113f9  add     rsp, 30h
0x1800113fd  pop     r15
0x1800113ff  pop     rdi
0x180011400  pop     rsi
0x180011401  retn
```
