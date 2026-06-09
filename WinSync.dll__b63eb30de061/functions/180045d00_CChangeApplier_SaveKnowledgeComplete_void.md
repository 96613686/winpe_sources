# CChangeApplier::SaveKnowledgeComplete(void)

- ea: `0x180045d00`
- end: `0x180045de7`
- name: `?SaveKnowledgeComplete@CChangeApplier@@UEAAJXZ`
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
- `0x180045d00`
- `0x180046160`

## string_xrefs

- `0x180045d35`: `CChangeApplier::SaveKnowledgeComplete`
- `0x180045db9`: `CChangeApplier::SaveKnowledgeComplete`

## pseudocode

```c
__int64 __fastcall CChangeApplier::SaveKnowledgeComplete(CChangeApplier *this)
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
      38,
      &WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      "CChangeApplier::SaveKnowledgeComplete");
  }
  v2 = (_CHANGE_APPLIER_WORK_ITEM *)SeAlloc(0x18u);
  v5 = (CChangeApplier *)((char *)this - 16);
  v6 = v2;
  if ( v2 )
  {
    *((_QWORD *)v2 + 1) = 0;
    *((_DWORD *)v2 + 4) = 0;
    *(_DWORD *)v2 = 6;
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
      39,
      (unsigned int)&WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      (unsigned int)"CChangeApplier::SaveKnowledgeComplete",
      v8);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180045d00  mov     [rsp+arg_0], rbx
0x180045d05  mov     [rsp+arg_8], rsi
0x180045d0a  push    rdi
0x180045d0b  sub     rsp, 30h
0x180045d0f  mov     rdi, rcx
0x180045d12  mov     rcx, cs:WPP_GLOBAL_Control
0x180045d19  lea     rsi, WPP_GLOBAL_Control
0x180045d20  cmp     rcx, rsi
0x180045d23  jz      short loc_180045D4D
0x180045d25  test    byte ptr [rcx+1Ch], 8
0x180045d29  jz      short loc_180045D4D
0x180045d2b  cmp     byte ptr [rcx+19h], 5
0x180045d2f  jb      short loc_180045D4D
0x180045d31  mov     rcx, [rcx+10h]
0x180045d35  lea     r9, aCchangeapplier_18; "CChangeApplier::SaveKnowledgeComplete"
0x180045d3c  mov     edx, 26h ; '&'
0x180045d41  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x180045d48  call    WPP_SF_s
0x180045d4d  mov     ecx, 18h; unsigned __int64
0x180045d52  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x180045d57  lea     rcx, [rdi-10h]; this
0x180045d5b  mov     rbx, rax
0x180045d5e  test    rax, rax
0x180045d61  jz      short loc_180045D90
0x180045d63  mov     qword ptr [rax+8], 0
0x180045d6b  mov     rdx, rax; struct _CHANGE_APPLIER_WORK_ITEM *
0x180045d6e  mov     dword ptr [rax+10h], 0
0x180045d75  mov     dword ptr [rax], 6
0x180045d7b  call    ?AddWorkItemToWorkQueue@CChangeApplier@@AEAAJPEAU_CHANGE_APPLIER_WORK_ITEM@@H@Z; CChangeApplier::AddWorkItemToWorkQueue(_CHANGE_APPLIER_WORK_ITEM *,int)
0x180045d80  mov     edi, eax
0x180045d82  test    eax, eax
0x180045d84  jns     short loc_180045D9D
0x180045d86  mov     rcx, rbx; this
0x180045d89  call    ??_G_CHANGE_APPLIER_WORK_ITEM@@QEAAPEAXI@Z; _CHANGE_APPLIER_WORK_ITEM::`scalar deleting destructor'(uint)
0x180045d8e  jmp     short loc_180045D9D
0x180045d90  mov     r8d, 8007000Eh; int
0x180045d96  call    ?SetError@CChangeApplier@@AEAAJPEAUISyncCallback@@J@Z; CChangeApplier::SetError(ISyncCallback *,long)
0x180045d9b  mov     edi, eax
0x180045d9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180045da4  cmp     rcx, rsi
0x180045da7  jz      short loc_180045DD5
0x180045da9  test    byte ptr [rcx+1Ch], 8
0x180045dad  jz      short loc_180045DD5
0x180045daf  cmp     byte ptr [rcx+19h], 5
0x180045db3  jb      short loc_180045DD5
0x180045db5  mov     rcx, [rcx+10h]
0x180045db9  lea     r9, aCchangeapplier_18; "CChangeApplier::SaveKnowledgeComplete"
0x180045dc0  mov     edx, 27h ; '''
0x180045dc5  mov     [rsp+38h+var_18], edi
0x180045dc9  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x180045dd0  call    WPP_SF_sD
0x180045dd5  mov     rbx, [rsp+38h+arg_0]
0x180045dda  mov     eax, edi
0x180045ddc  mov     rsi, [rsp+38h+arg_8]
0x180045de1  add     rsp, 30h
0x180045de5  pop     rdi
0x180045de6  retn
```
