# CChangeApplier::SaveConflictCompleteHandler(void)

- ea: `0x180045260`
- end: `0x180045341`
- name: `?SaveConflictCompleteHandler@CChangeApplier@@AEAAJXZ`
- size: `225`
- prototype: `__int64 __fastcall(CChangeApplier *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180039f60`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x180035724`
- `0x180041f28`
- `0x180045260`
- `0x180046160`

## string_xrefs

- `0x180045295`: `CChangeApplier::SaveConflictCompleteHandler`
- `0x180045313`: `CChangeApplier::SaveConflictCompleteHandler`

## pseudocode

```c
__int64 __fastcall CChangeApplier::SaveConflictCompleteHandler(struct ISyncCallback **this)
{
  int v2; // ebx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      178,
      &WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      "CChangeApplier::SaveConflictCompleteHandler");
  }
  v2 = CChangeApplier::ChangeState((__int64)this, 14);
  if ( v2 >= 0 )
    v2 = CChangeApplier::ProcessItemData((CChangeApplier *)this);
  if ( v2 != -2147467260 )
  {
    if ( v2 >= 0 )
      goto LABEL_12;
LABEL_11:
    v2 = CChangeApplier::SetError((CChangeApplier *)this, this[50], v2);
    goto LABEL_12;
  }
  if ( !*((_DWORD *)this + 170) )
    goto LABEL_11;
  v2 = 0;
LABEL_12:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      179,
      (unsigned int)&WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      (unsigned int)"CChangeApplier::SaveConflictCompleteHandler",
      v2);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180045260  mov     [rsp+arg_0], rbx
0x180045265  mov     [rsp+arg_8], rsi
0x18004526a  push    rdi
0x18004526b  sub     rsp, 30h
0x18004526f  mov     rdi, rcx
0x180045272  mov     rcx, cs:WPP_GLOBAL_Control
0x180045279  lea     rsi, WPP_GLOBAL_Control
0x180045280  cmp     rcx, rsi
0x180045283  jz      short loc_1800452AD
0x180045285  test    byte ptr [rcx+1Ch], 8
0x180045289  jz      short loc_1800452AD
0x18004528b  cmp     byte ptr [rcx+19h], 5
0x18004528f  jb      short loc_1800452AD
0x180045291  mov     rcx, [rcx+10h]
0x180045295  lea     r9, aCchangeapplier_91; "CChangeApplier::SaveConflictCompleteHan"...
0x18004529c  mov     edx, 0B2h
0x1800452a1  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x1800452a8  call    WPP_SF_s
0x1800452ad  mov     edx, 0Eh
0x1800452b2  mov     rcx, rdi
0x1800452b5  call    ?ChangeState@CChangeApplier@@AEAAJW4ChangeApplierState@@@Z; CChangeApplier::ChangeState(ChangeApplierState)
0x1800452ba  mov     ebx, eax
0x1800452bc  test    eax, eax
0x1800452be  js      short loc_1800452CA
0x1800452c0  mov     rcx, rdi; this
0x1800452c3  call    ?ProcessItemData@CChangeApplier@@AEAAJXZ; CChangeApplier::ProcessItemData(void)
0x1800452c8  mov     ebx, eax
0x1800452ca  cmp     ebx, 80004004h
0x1800452d0  jnz     short loc_1800452DF
0x1800452d2  cmp     dword ptr [rdi+2A8h], 0
0x1800452d9  jz      short loc_1800452E3
0x1800452db  xor     ebx, ebx
0x1800452dd  jmp     short loc_1800452F7
0x1800452df  test    ebx, ebx
0x1800452e1  jns     short loc_1800452F7
0x1800452e3  mov     rdx, [rdi+190h]; struct ISyncCallback *
0x1800452ea  mov     r8d, ebx; int
0x1800452ed  mov     rcx, rdi; this
0x1800452f0  call    ?SetError@CChangeApplier@@AEAAJPEAUISyncCallback@@J@Z; CChangeApplier::SetError(ISyncCallback *,long)
0x1800452f5  mov     ebx, eax
0x1800452f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800452fe  cmp     rcx, rsi
0x180045301  jz      short loc_18004532F
0x180045303  test    byte ptr [rcx+1Ch], 8
0x180045307  jz      short loc_18004532F
0x180045309  cmp     byte ptr [rcx+19h], 5
0x18004530d  jb      short loc_18004532F
0x18004530f  mov     rcx, [rcx+10h]
0x180045313  lea     r9, aCchangeapplier_91; "CChangeApplier::SaveConflictCompleteHan"...
0x18004531a  mov     edx, 0B3h
0x18004531f  mov     [rsp+38h+var_18], ebx
0x180045323  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x18004532a  call    WPP_SF_sD
0x18004532f  mov     rsi, [rsp+38h+arg_8]
0x180045334  mov     eax, ebx
0x180045336  mov     rbx, [rsp+38h+arg_0]
0x18004533b  add     rsp, 30h
0x18004533f  pop     rdi
0x180045340  retn
```
