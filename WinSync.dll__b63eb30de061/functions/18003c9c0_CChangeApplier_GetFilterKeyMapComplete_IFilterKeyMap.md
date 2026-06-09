# CChangeApplier::GetFilterKeyMapComplete(IFilterKeyMap *)

- ea: `0x18003c9c0`
- end: `0x18003cb2d`
- name: `?GetFilterKeyMapComplete@CChangeApplier@@UEAAJPEAUIFilterKeyMap@@@Z`
- size: `365`
- prototype: `__int64 __fastcall(CChangeApplier *this, struct ISyncCallback *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18000a0f0`
- `0x18001a038`
- `0x18001ae20`
- `0x180031f2c`
- `0x180032bf8`
- `0x18003c9c0`
- `0x180046160`
- `0x180094010`

## string_xrefs

- `0x18003c9fb`: `CChangeApplier::GetFilterKeyMapComplete`
- `0x18003cafc`: `CChangeApplier::GetFilterKeyMapComplete`

## pseudocode

```c
__int64 __fastcall CChangeApplier::GetFilterKeyMapComplete(CChangeApplier *this, struct ISyncCallback *a2)
{
  int v4; // ebx
  struct IFilterKeyMapVtbl *lpVtbl; // rax
  struct _CHANGE_APPLIER_WORK_ITEM *v6; // rax
  struct _CHANGE_APPLIER_WORK_ITEM *v7; // rdi
  int v8; // r8d
  int v10; // [rsp+58h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      49,
      &WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      "CChangeApplier::GetFilterKeyMapComplete");
  }
  if ( !a2 )
  {
    v4 = -2147467261;
LABEL_20:
    v4 = CChangeApplier::SetError((CChangeApplier *)((char *)this - 56), a2, v4);
    goto LABEL_21;
  }
  if ( *((_QWORD *)this + 17) )
  {
    lpVtbl = (struct IFilterKeyMapVtbl *)a2->lpVtbl;
    v10 = 0;
    v4 = ((__int64 (__fastcall *)(struct ISyncCallback *, int *))lpVtbl->GetCount)(a2, &v10);
    if ( v4 )
      goto LABEL_14;
    if ( !v10 )
    {
      v4 = -2147024809;
      goto LABEL_20;
    }
  }
  v6 = (struct _CHANGE_APPLIER_WORK_ITEM *)SeAlloc(0x18u);
  v7 = v6;
  if ( !v6 )
  {
    v4 = -2147024882;
    goto LABEL_20;
  }
  *((_QWORD *)v6 + 1) = 0;
  *((_DWORD *)v6 + 4) = 0;
  *((_QWORD *)this + 22) = a2;
  ((void (__fastcall *)(struct ISyncCallback *))a2->lpVtbl->AddRef)(a2);
  *(_DWORD *)v7 = 0;
  v4 = CChangeApplier::AddWorkItemToWorkQueue((CChangeApplier *)((char *)this - 56), v7, v8);
  if ( v4 < 0 )
    _CHANGE_APPLIER_WORK_ITEM::`scalar deleting destructor'(v7, (unsigned int)a2);
LABEL_14:
  if ( v4 == -2147467260 )
  {
    if ( !*((_DWORD *)this + 156) )
      goto LABEL_20;
    v4 = 0;
  }
  else if ( v4 < 0 )
  {
    goto LABEL_20;
  }
LABEL_21:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      50,
      (unsigned int)&WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      (unsigned int)"CChangeApplier::GetFilterKeyMapComplete",
      v4);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18003c9c0  mov     [rsp+arg_0], rbx
0x18003c9c5  mov     [rsp+arg_10], rbp
0x18003c9ca  push    rsi
0x18003c9cb  push    rdi
0x18003c9cc  push    r15
0x18003c9ce  sub     rsp, 30h
0x18003c9d2  mov     rsi, rdx
0x18003c9d5  mov     rbp, rcx
0x18003c9d8  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c9df  lea     r15, WPP_GLOBAL_Control
0x18003c9e6  cmp     rcx, r15
0x18003c9e9  jz      short loc_18003CA13
0x18003c9eb  test    byte ptr [rcx+1Ch], 8
0x18003c9ef  jz      short loc_18003CA13
0x18003c9f1  cmp     byte ptr [rcx+19h], 5
0x18003c9f5  jb      short loc_18003CA13
0x18003c9f7  mov     rcx, [rcx+10h]
0x18003c9fb  lea     r9, aCchangeapplier_39; "CChangeApplier::GetFilterKeyMapComplete"
0x18003ca02  mov     edx, 31h ; '1'
0x18003ca07  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x18003ca0e  call    WPP_SF_s
0x18003ca13  test    rsi, rsi
0x18003ca16  jnz     short loc_18003CA22
0x18003ca18  mov     ebx, 80004003h
0x18003ca1d  jmp     loc_18003CAD2
0x18003ca22  cmp     qword ptr [rbp+88h], 0
0x18003ca2a  jz      short loc_18003CA5B
0x18003ca2c  mov     rax, [rsi]
0x18003ca2f  lea     rdx, [rsp+48h+arg_8]
0x18003ca34  mov     rcx, rsi
0x18003ca37  mov     [rsp+48h+arg_8], 0
0x18003ca3f  mov     rax, [rax+18h]
0x18003ca43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ca48  mov     ebx, eax
0x18003ca4a  test    eax, eax
0x18003ca4c  jnz     short loc_18003CAB2
0x18003ca4e  cmp     [rsp+48h+arg_8], eax
0x18003ca52  jnz     short loc_18003CA5B
0x18003ca54  mov     ebx, 80070057h
0x18003ca59  jmp     short loc_18003CAD2
0x18003ca5b  mov     ecx, 18h; unsigned __int64
0x18003ca60  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x18003ca65  mov     rdi, rax
0x18003ca68  test    rax, rax
0x18003ca6b  jz      short loc_18003CACD
0x18003ca6d  mov     qword ptr [rax+8], 0
0x18003ca75  mov     rcx, rsi
0x18003ca78  mov     dword ptr [rax+10h], 0
0x18003ca7f  mov     [rbp+0B0h], rsi
0x18003ca86  mov     rdx, [rsi]
0x18003ca89  mov     rax, [rdx+8]
0x18003ca8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ca92  mov     rdx, rdi; struct _CHANGE_APPLIER_WORK_ITEM *
0x18003ca95  mov     dword ptr [rdi], 0
0x18003ca9b  lea     rcx, [rbp-38h]; this
0x18003ca9f  call    ?AddWorkItemToWorkQueue@CChangeApplier@@AEAAJPEAU_CHANGE_APPLIER_WORK_ITEM@@H@Z; CChangeApplier::AddWorkItemToWorkQueue(_CHANGE_APPLIER_WORK_ITEM *,int)
0x18003caa4  mov     ebx, eax
0x18003caa6  test    eax, eax
0x18003caa8  jns     short loc_18003CAB2
0x18003caaa  mov     rcx, rdi; this
0x18003caad  call    ??_G_CHANGE_APPLIER_WORK_ITEM@@QEAAPEAXI@Z; _CHANGE_APPLIER_WORK_ITEM::`scalar deleting destructor'(uint)
0x18003cab2  cmp     ebx, 80004004h
0x18003cab8  jnz     short loc_18003CAC7
0x18003caba  cmp     dword ptr [rbp+270h], 0
0x18003cac1  jz      short loc_18003CAD2
0x18003cac3  xor     ebx, ebx
0x18003cac5  jmp     short loc_18003CAE0
0x18003cac7  test    ebx, ebx
0x18003cac9  jns     short loc_18003CAE0
0x18003cacb  jmp     short loc_18003CAD2
0x18003cacd  mov     ebx, 8007000Eh
0x18003cad2  lea     rcx, [rbp-38h]; this
0x18003cad6  mov     r8d, ebx; int
0x18003cad9  call    ?SetError@CChangeApplier@@AEAAJPEAUISyncCallback@@J@Z; CChangeApplier::SetError(ISyncCallback *,long)
0x18003cade  mov     ebx, eax
0x18003cae0  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cae7  cmp     rcx, r15
0x18003caea  jz      short loc_18003CB18
0x18003caec  test    byte ptr [rcx+1Ch], 8
0x18003caf0  jz      short loc_18003CB18
0x18003caf2  cmp     byte ptr [rcx+19h], 5
0x18003caf6  jb      short loc_18003CB18
0x18003caf8  mov     rcx, [rcx+10h]
0x18003cafc  lea     r9, aCchangeapplier_39; "CChangeApplier::GetFilterKeyMapComplete"
0x18003cb03  mov     edx, 32h ; '2'
0x18003cb08  mov     [rsp+48h+var_28], ebx
0x18003cb0c  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x18003cb13  call    WPP_SF_sD
0x18003cb18  mov     rbp, [rsp+48h+arg_10]
0x18003cb1d  mov     eax, ebx
0x18003cb1f  mov     rbx, [rsp+48h+arg_0]
0x18003cb24  add     rsp, 30h
0x18003cb28  pop     r15
0x18003cb2a  pop     rdi
0x18003cb2b  pop     rsi
0x18003cb2c  retn
```
