# CChangeApplier::SaveConstraintConflictComplete(void)

- ea: `0x180045490`
- end: `0x180045577`
- name: `?SaveConstraintConflictComplete@CChangeApplier@@UEAAJXZ`
- size: `231`
- prototype: `__int64 __fastcall(CChangeApplier *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x18000a0f0`
- `0x18001a038`
- `0x18001ae20`
- `0x180031f2c`
- `0x180032bf8`
- `0x180045490`
- `0x180046160`

## string_xrefs

- `0x1800454c5`: `CChangeApplier::SaveConstraintConflictComplete`
- `0x180045549`: `CChangeApplier::SaveConstraintConflictComplete`

## pseudocode

```c
__int64 __fastcall CChangeApplier::SaveConstraintConflictComplete(CChangeApplier *this)
{
  _CHANGE_APPLIER_WORK_ITEM *v2; // rax
  struct ISyncCallback *v3; // rdx
  int v4; // r8d
  CChangeApplier *v5; // rcx
  _CHANGE_APPLIER_WORK_ITEM *v6; // rbx
  unsigned int v7; // edx
  int v8; // edi

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      47,
      &WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      "CChangeApplier::SaveConstraintConflictComplete");
  }
  v2 = (_CHANGE_APPLIER_WORK_ITEM *)SeAlloc(0x18u);
  v5 = (CChangeApplier *)((char *)this - 16);
  v6 = v2;
  if ( v2 )
  {
    *((_QWORD *)v2 + 1) = 0;
    *((_DWORD *)v2 + 4) = 0;
    *(_DWORD *)v2 = 7;
    v8 = CChangeApplier::AddWorkItemToWorkQueue(v5, v2, v4);
    if ( v8 < 0 )
      _CHANGE_APPLIER_WORK_ITEM::`scalar deleting destructor'(v6, v7);
  }
  else
  {
    v8 = CChangeApplier::SetError(v5, v3, -2147024882);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      48,
      (unsigned int)&WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      (unsigned int)"CChangeApplier::SaveConstraintConflictComplete",
      v8);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180045490  mov     [rsp+arg_0], rbx
0x180045495  mov     [rsp+arg_8], rsi
0x18004549a  push    rdi
0x18004549b  sub     rsp, 30h
0x18004549f  mov     rdi, rcx
0x1800454a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800454a9  lea     rsi, WPP_GLOBAL_Control
0x1800454b0  cmp     rcx, rsi
0x1800454b3  jz      short loc_1800454DD
0x1800454b5  test    byte ptr [rcx+1Ch], 8
0x1800454b9  jz      short loc_1800454DD
0x1800454bb  cmp     byte ptr [rcx+19h], 5
0x1800454bf  jb      short loc_1800454DD
0x1800454c1  mov     rcx, [rcx+10h]
0x1800454c5  lea     r9, aCchangeapplier_41; "CChangeApplier::SaveConstraintConflictC"...
0x1800454cc  mov     edx, 2Fh ; '/'
0x1800454d1  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x1800454d8  call    WPP_SF_s
0x1800454dd  mov     ecx, 18h; unsigned __int64
0x1800454e2  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x1800454e7  lea     rcx, [rdi-10h]; this
0x1800454eb  mov     rbx, rax
0x1800454ee  test    rax, rax
0x1800454f1  jz      short loc_180045520
0x1800454f3  mov     qword ptr [rax+8], 0
0x1800454fb  mov     rdx, rax; struct _CHANGE_APPLIER_WORK_ITEM *
0x1800454fe  mov     dword ptr [rax+10h], 0
0x180045505  mov     dword ptr [rax], 7
0x18004550b  call    ?AddWorkItemToWorkQueue@CChangeApplier@@AEAAJPEAU_CHANGE_APPLIER_WORK_ITEM@@H@Z; CChangeApplier::AddWorkItemToWorkQueue(_CHANGE_APPLIER_WORK_ITEM *,int)
0x180045510  mov     edi, eax
0x180045512  test    eax, eax
0x180045514  jns     short loc_18004552D
0x180045516  mov     rcx, rbx; this
0x180045519  call    ??_G_CHANGE_APPLIER_WORK_ITEM@@QEAAPEAXI@Z; _CHANGE_APPLIER_WORK_ITEM::`scalar deleting destructor'(uint)
0x18004551e  jmp     short loc_18004552D
0x180045520  mov     r8d, 8007000Eh; int
0x180045526  call    ?SetError@CChangeApplier@@AEAAJPEAUISyncCallback@@J@Z; CChangeApplier::SetError(ISyncCallback *,long)
0x18004552b  mov     edi, eax
0x18004552d  mov     rcx, cs:WPP_GLOBAL_Control
0x180045534  cmp     rcx, rsi
0x180045537  jz      short loc_180045565
0x180045539  test    byte ptr [rcx+1Ch], 8
0x18004553d  jz      short loc_180045565
0x18004553f  cmp     byte ptr [rcx+19h], 5
0x180045543  jb      short loc_180045565
0x180045545  mov     rcx, [rcx+10h]
0x180045549  lea     r9, aCchangeapplier_41; "CChangeApplier::SaveConstraintConflictC"...
0x180045550  mov     edx, 30h ; '0'
0x180045555  mov     [rsp+38h+var_18], edi
0x180045559  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x180045560  call    WPP_SF_sD
0x180045565  mov     rbx, [rsp+38h+arg_0]
0x18004556a  mov     eax, edi
0x18004556c  mov     rsi, [rsp+38h+arg_8]
0x180045571  add     rsp, 30h
0x180045575  pop     rdi
0x180045576  retn
```
