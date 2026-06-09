# CChangeApplier::SaveConflictComplete(void)

- ea: `0x180045170`
- end: `0x180045257`
- name: `?SaveConflictComplete@CChangeApplier@@UEAAJXZ`
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
- `0x180045170`
- `0x180046160`

## string_xrefs

- `0x1800451a5`: `CChangeApplier::SaveConflictComplete`
- `0x180045229`: `CChangeApplier::SaveConflictComplete`

## pseudocode

```c
__int64 __fastcall CChangeApplier::SaveConflictComplete(CChangeApplier *this)
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
      44,
      &WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      "CChangeApplier::SaveConflictComplete");
  }
  v2 = (_CHANGE_APPLIER_WORK_ITEM *)SeAlloc(0x18u);
  v5 = (CChangeApplier *)((char *)this - 16);
  v6 = v2;
  if ( v2 )
  {
    *((_QWORD *)v2 + 1) = 0;
    *((_DWORD *)v2 + 4) = 0;
    *(_DWORD *)v2 = 4;
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
      45,
      (unsigned int)&WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      (unsigned int)"CChangeApplier::SaveConflictComplete",
      v8);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180045170  mov     [rsp+arg_0], rbx
0x180045175  mov     [rsp+arg_8], rsi
0x18004517a  push    rdi
0x18004517b  sub     rsp, 30h
0x18004517f  mov     rdi, rcx
0x180045182  mov     rcx, cs:WPP_GLOBAL_Control
0x180045189  lea     rsi, WPP_GLOBAL_Control
0x180045190  cmp     rcx, rsi
0x180045193  jz      short loc_1800451BD
0x180045195  test    byte ptr [rcx+1Ch], 8
0x180045199  jz      short loc_1800451BD
0x18004519b  cmp     byte ptr [rcx+19h], 5
0x18004519f  jb      short loc_1800451BD
0x1800451a1  mov     rcx, [rcx+10h]
0x1800451a5  lea     r9, aCchangeapplier_116; "CChangeApplier::SaveConflictComplete"
0x1800451ac  mov     edx, 2Ch ; ','
0x1800451b1  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x1800451b8  call    WPP_SF_s
0x1800451bd  mov     ecx, 18h; unsigned __int64
0x1800451c2  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x1800451c7  lea     rcx, [rdi-10h]; this
0x1800451cb  mov     rbx, rax
0x1800451ce  test    rax, rax
0x1800451d1  jz      short loc_180045200
0x1800451d3  mov     qword ptr [rax+8], 0
0x1800451db  mov     rdx, rax; struct _CHANGE_APPLIER_WORK_ITEM *
0x1800451de  mov     dword ptr [rax+10h], 0
0x1800451e5  mov     dword ptr [rax], 4
0x1800451eb  call    ?AddWorkItemToWorkQueue@CChangeApplier@@AEAAJPEAU_CHANGE_APPLIER_WORK_ITEM@@H@Z; CChangeApplier::AddWorkItemToWorkQueue(_CHANGE_APPLIER_WORK_ITEM *,int)
0x1800451f0  mov     edi, eax
0x1800451f2  test    eax, eax
0x1800451f4  jns     short loc_18004520D
0x1800451f6  mov     rcx, rbx; this
0x1800451f9  call    ??_G_CHANGE_APPLIER_WORK_ITEM@@QEAAPEAXI@Z; _CHANGE_APPLIER_WORK_ITEM::`scalar deleting destructor'(uint)
0x1800451fe  jmp     short loc_18004520D
0x180045200  mov     r8d, 8007000Eh; int
0x180045206  call    ?SetError@CChangeApplier@@AEAAJPEAUISyncCallback@@J@Z; CChangeApplier::SetError(ISyncCallback *,long)
0x18004520b  mov     edi, eax
0x18004520d  mov     rcx, cs:WPP_GLOBAL_Control
0x180045214  cmp     rcx, rsi
0x180045217  jz      short loc_180045245
0x180045219  test    byte ptr [rcx+1Ch], 8
0x18004521d  jz      short loc_180045245
0x18004521f  cmp     byte ptr [rcx+19h], 5
0x180045223  jb      short loc_180045245
0x180045225  mov     rcx, [rcx+10h]
0x180045229  lea     r9, aCchangeapplier_116; "CChangeApplier::SaveConflictComplete"
0x180045230  mov     edx, 2Dh ; '-'
0x180045235  mov     [rsp+38h+var_18], edi
0x180045239  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x180045240  call    WPP_SF_sD
0x180045245  mov     rbx, [rsp+38h+arg_0]
0x18004524a  mov     eax, edi
0x18004524c  mov     rsi, [rsp+38h+arg_8]
0x180045251  add     rsp, 30h
0x180045255  pop     rdi
0x180045256  retn
```
