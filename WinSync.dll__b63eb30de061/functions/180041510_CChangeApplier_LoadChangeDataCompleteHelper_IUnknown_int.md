# CChangeApplier::LoadChangeDataCompleteHelper(IUnknown *,int)

- ea: `0x180041510`
- end: `0x18004167a`
- name: `?LoadChangeDataCompleteHelper@CChangeApplier@@AEAAJPEAUIUnknown@@H@Z`
- size: `362`
- prototype: `__int64 __fastcall(CChangeApplier *__hidden this, struct IUnknown *, int)`
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180034f40`
- `0x180041120`
- `0x180041220`

## callees

- `0x18000a0f0`
- `0x18001a038`
- `0x18001ae20`
- `0x180031f2c`
- `0x180032bf8`
- `0x180041510`
- `0x180046160`
- `0x180094010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180041599`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180041599`

## string_xrefs

- `0x180041549`: `CChangeApplier::LoadChangeDataCompleteHelper`
- `0x18004164f`: `CChangeApplier::LoadChangeDataCompleteHelper`

## pseudocode

```c
__int64 __fastcall CChangeApplier::LoadChangeDataCompleteHelper(CChangeApplier *this, struct IUnknown *a2, int a3)
{
  int v6; // esi
  void *v7; // rcx
  struct _CHANGE_APPLIER_WORK_ITEM *v8; // rax
  int v9; // r8d
  struct _CHANGE_APPLIER_WORK_ITEM *v10; // rdi
  unsigned int v11; // edx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      115,
      &WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      "CChangeApplier::LoadChangeDataCompleteHelper");
  }
  if ( *((_DWORD *)this + 149) )
  {
    v6 = 0;
    if ( a2 && a3 )
      ((void (__fastcall *)(struct IUnknown *))a2->lpVtbl->AddRef)(a2);
    v7 = (void *)*((_QWORD *)this + 76);
    *((_QWORD *)this + 80) = a2;
    *((_DWORD *)this + 148) = 0;
    SetEvent(v7);
  }
  else
  {
    v8 = (struct _CHANGE_APPLIER_WORK_ITEM *)SeAlloc(0x18u);
    v10 = v8;
    if ( v8 )
    {
      *((_QWORD *)v8 + 1) = 0;
      *((_DWORD *)v8 + 4) = 0;
      *(_DWORD *)v8 = 2;
      if ( a2 && a3 )
        ((void (__fastcall *)(struct IUnknown *))a2->lpVtbl->AddRef)(a2);
      *((_QWORD *)v10 + 1) = a2;
      v6 = CChangeApplier::AddWorkItemToWorkQueue(this, v10, v9);
      if ( v6 < 0 )
        _CHANGE_APPLIER_WORK_ITEM::`scalar deleting destructor'(v10, v11);
    }
    else
    {
      v6 = CChangeApplier::SetError(this, *((struct ISyncCallback **)this + 50), -2147024882);
      if ( a2 && !a3 )
        ((void (__fastcall *)(struct IUnknown *))a2->lpVtbl->Release)(a2);
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      116,
      (unsigned int)&WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      (unsigned int)"CChangeApplier::LoadChangeDataCompleteHelper",
      v6);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180041510  push    rbx
0x180041512  push    rbp
0x180041513  push    rsi
0x180041514  push    rdi
0x180041515  push    r12
0x180041517  push    r14
0x180041519  sub     rsp, 38h
0x18004151d  mov     r14d, r8d
0x180041520  mov     rbx, rdx
0x180041523  mov     rbp, rcx
0x180041526  mov     rcx, cs:WPP_GLOBAL_Control
0x18004152d  lea     r12, WPP_GLOBAL_Control
0x180041534  cmp     rcx, r12
0x180041537  jz      short loc_180041561
0x180041539  test    byte ptr [rcx+1Ch], 8
0x18004153d  jz      short loc_180041561
0x18004153f  cmp     byte ptr [rcx+19h], 5
0x180041543  jb      short loc_180041561
0x180041545  mov     rcx, [rcx+10h]
0x180041549  lea     r9, aCchangeapplier_38; "CChangeApplier::LoadChangeDataCompleteH"...
0x180041550  mov     edx, 73h ; 's'
0x180041555  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x18004155c  call    WPP_SF_s
0x180041561  cmp     dword ptr [rbp+254h], 0
0x180041568  jz      short loc_1800415A4
0x18004156a  xor     esi, esi
0x18004156c  test    rbx, rbx
0x18004156f  jz      short loc_180041585
0x180041571  test    r14d, r14d
0x180041574  jz      short loc_180041585
0x180041576  mov     rax, [rbx]
0x180041579  mov     rcx, rbx
0x18004157c  mov     rax, [rax+8]
0x180041580  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041585  mov     rcx, [rbp+260h]; hEvent
0x18004158c  mov     [rbp+280h], rbx
0x180041593  mov     [rbp+250h], esi
0x180041599  call    cs:__imp_SetEvent
0x18004159f  jmp     loc_180041633
0x1800415a4  mov     ecx, 18h; unsigned __int64
0x1800415a9  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x1800415ae  mov     rdi, rax
0x1800415b1  test    rax, rax
0x1800415b4  jz      short loc_180041603
0x1800415b6  mov     qword ptr [rax+8], 0
0x1800415be  mov     dword ptr [rax+10h], 0
0x1800415c5  mov     dword ptr [rax], 2
0x1800415cb  test    rbx, rbx
0x1800415ce  jz      short loc_1800415E4
0x1800415d0  test    r14d, r14d
0x1800415d3  jz      short loc_1800415E4
0x1800415d5  mov     rax, [rbx]
0x1800415d8  mov     rcx, rbx
0x1800415db  mov     rax, [rax+8]
0x1800415df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800415e4  mov     rdx, rdi; struct _CHANGE_APPLIER_WORK_ITEM *
0x1800415e7  mov     [rdi+8], rbx
0x1800415eb  mov     rcx, rbp; this
0x1800415ee  call    ?AddWorkItemToWorkQueue@CChangeApplier@@AEAAJPEAU_CHANGE_APPLIER_WORK_ITEM@@H@Z; CChangeApplier::AddWorkItemToWorkQueue(_CHANGE_APPLIER_WORK_ITEM *,int)
0x1800415f3  mov     esi, eax
0x1800415f5  test    eax, eax
0x1800415f7  jns     short loc_180041633
0x1800415f9  mov     rcx, rdi; this
0x1800415fc  call    ??_G_CHANGE_APPLIER_WORK_ITEM@@QEAAPEAXI@Z; _CHANGE_APPLIER_WORK_ITEM::`scalar deleting destructor'(uint)
0x180041601  jmp     short loc_180041633
0x180041603  mov     rdx, [rbp+190h]; struct ISyncCallback *
0x18004160a  mov     r8d, 8007000Eh; int
0x180041610  mov     rcx, rbp; this
0x180041613  call    ?SetError@CChangeApplier@@AEAAJPEAUISyncCallback@@J@Z; CChangeApplier::SetError(ISyncCallback *,long)
0x180041618  mov     esi, eax
0x18004161a  test    rbx, rbx
0x18004161d  jz      short loc_180041633
0x18004161f  test    r14d, r14d
0x180041622  jnz     short loc_180041633
0x180041624  mov     rax, [rbx]
0x180041627  mov     rcx, rbx
0x18004162a  mov     rax, [rax+10h]
0x18004162e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041633  mov     rcx, cs:WPP_GLOBAL_Control
0x18004163a  cmp     rcx, r12
0x18004163d  jz      short loc_18004166B
0x18004163f  test    byte ptr [rcx+1Ch], 8
0x180041643  jz      short loc_18004166B
0x180041645  cmp     byte ptr [rcx+19h], 5
0x180041649  jb      short loc_18004166B
0x18004164b  mov     rcx, [rcx+10h]
0x18004164f  lea     r9, aCchangeapplier_38; "CChangeApplier::LoadChangeDataCompleteH"...
0x180041656  mov     edx, 74h ; 't'
0x18004165b  mov     [rsp+68h+var_48], esi
0x18004165f  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x180041666  call    WPP_SF_sD
0x18004166b  mov     eax, esi
0x18004166d  add     rsp, 38h
0x180041671  pop     r14
0x180041673  pop     r12
0x180041675  pop     rdi
0x180041676  pop     rsi
0x180041677  pop     rbp
0x180041678  pop     rbx
0x180041679  retn
```
