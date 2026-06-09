# CChangeApplier::SaveConstraintConflictCompleteHandler(void)

- ea: `0x180045580`
- end: `0x180045661`
- name: `?SaveConstraintConflictCompleteHandler@CChangeApplier@@AEAAJXZ`
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
- `0x180045580`
- `0x180046160`

## string_xrefs

- `0x1800455b5`: `CChangeApplier::SaveConstraintConflictCompleteHandler`
- `0x180045633`: `CChangeApplier::SaveConstraintConflictCompleteHandler`

## pseudocode

```c
__int64 __fastcall CChangeApplier::SaveConstraintConflictCompleteHandler(struct ISyncCallback **this)
{
  int v2; // ebx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      182,
      &WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      "CChangeApplier::SaveConstraintConflictCompleteHandler");
  }
  v2 = CChangeApplier::ChangeState((__int64)this, 25);
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
      183,
      (unsigned int)&WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      (unsigned int)"CChangeApplier::SaveConstraintConflictCompleteHandler",
      v2);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180045580  mov     [rsp+arg_0], rbx
0x180045585  mov     [rsp+arg_8], rsi
0x18004558a  push    rdi
0x18004558b  sub     rsp, 30h
0x18004558f  mov     rdi, rcx
0x180045592  mov     rcx, cs:WPP_GLOBAL_Control
0x180045599  lea     rsi, WPP_GLOBAL_Control
0x1800455a0  cmp     rcx, rsi
0x1800455a3  jz      short loc_1800455CD
0x1800455a5  test    byte ptr [rcx+1Ch], 8
0x1800455a9  jz      short loc_1800455CD
0x1800455ab  cmp     byte ptr [rcx+19h], 5
0x1800455af  jb      short loc_1800455CD
0x1800455b1  mov     rcx, [rcx+10h]
0x1800455b5  lea     r9, aCchangeapplier_25; "CChangeApplier::SaveConstraintConflictC"...
0x1800455bc  mov     edx, 0B6h
0x1800455c1  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x1800455c8  call    WPP_SF_s
0x1800455cd  mov     edx, 19h
0x1800455d2  mov     rcx, rdi
0x1800455d5  call    ?ChangeState@CChangeApplier@@AEAAJW4ChangeApplierState@@@Z; CChangeApplier::ChangeState(ChangeApplierState)
0x1800455da  mov     ebx, eax
0x1800455dc  test    eax, eax
0x1800455de  js      short loc_1800455EA
0x1800455e0  mov     rcx, rdi; this
0x1800455e3  call    ?ProcessItemData@CChangeApplier@@AEAAJXZ; CChangeApplier::ProcessItemData(void)
0x1800455e8  mov     ebx, eax
0x1800455ea  cmp     ebx, 80004004h
0x1800455f0  jnz     short loc_1800455FF
0x1800455f2  cmp     dword ptr [rdi+2A8h], 0
0x1800455f9  jz      short loc_180045603
0x1800455fb  xor     ebx, ebx
0x1800455fd  jmp     short loc_180045617
0x1800455ff  test    ebx, ebx
0x180045601  jns     short loc_180045617
0x180045603  mov     rdx, [rdi+190h]; struct ISyncCallback *
0x18004560a  mov     r8d, ebx; int
0x18004560d  mov     rcx, rdi; this
0x180045610  call    ?SetError@CChangeApplier@@AEAAJPEAUISyncCallback@@J@Z; CChangeApplier::SetError(ISyncCallback *,long)
0x180045615  mov     ebx, eax
0x180045617  mov     rcx, cs:WPP_GLOBAL_Control
0x18004561e  cmp     rcx, rsi
0x180045621  jz      short loc_18004564F
0x180045623  test    byte ptr [rcx+1Ch], 8
0x180045627  jz      short loc_18004564F
0x180045629  cmp     byte ptr [rcx+19h], 5
0x18004562d  jb      short loc_18004564F
0x18004562f  mov     rcx, [rcx+10h]
0x180045633  lea     r9, aCchangeapplier_25; "CChangeApplier::SaveConstraintConflictC"...
0x18004563a  mov     edx, 0B7h
0x18004563f  mov     [rsp+38h+var_18], ebx
0x180045643  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x18004564a  call    WPP_SF_sD
0x18004564f  mov     rsi, [rsp+38h+arg_8]
0x180045654  mov     eax, ebx
0x180045656  mov     rbx, [rsp+38h+arg_0]
0x18004565b  add     rsp, 30h
0x18004565f  pop     rdi
0x180045660  retn
```
