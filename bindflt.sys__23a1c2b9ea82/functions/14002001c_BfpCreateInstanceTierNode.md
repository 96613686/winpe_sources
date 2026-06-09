# BfpCreateInstanceTierNode

- ea: `0x14002001c`
- end: `0x140020177`
- name: `BfpCreateInstanceTierNode`
- size: `347`
- prototype: `__int64 __fastcall(PFLT_CONTEXT Context)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x14000f008`
- `0x14001efcc`

## callees

- `0x140001348`
- `0x140003304`
- `0x14001e8c0`
- `0x14002001c`
- `0x140020180`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140020166`
- `ntoskrnl!ExFreePoolWithTag` at `0x140020166`
- `ntoskrnl!ExAllocatePool2` at `0x140020048`
- `ntoskrnl!ExAllocatePool2` at `0x140020048`
- `FLTMGR!FltReferenceContext` at `0x140020063`
- `FLTMGR!FltReferenceContext` at `0x140020063`
- `FLTMGR!FltReleaseContext` at `0x140020152`
- `FLTMGR!FltReleaseContext` at `0x140020152`

## pseudocode

```c
__int64 __fastcall BfpCreateInstanceTierNode(PFLT_CONTEXT Context, _QWORD *a2, __int64 a3, __int64 a4)
{
  __int64 Pool2; // rax
  int v7; // edx
  _QWORD *v8; // rbx
  int v9; // edx
  int PathTree; // edi
  void *v12; // rcx
  void *v13; // rcx

  *a2 = 0;
  Pool2 = ExAllocatePool2(256, 40, 1886209602, a4);
  v8 = (_QWORD *)Pool2;
  if ( Pool2 )
  {
    *(_QWORD *)(Pool2 + 16) = Context;
    FltReferenceContext(Context);
    PathTree = BfpCreatePathTree(v8 + 3);
    if ( PathTree < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v9) = 2;
        WPP_RECORDER_SF_sDd(
          WPP_GLOBAL_Control->DeviceExtension,
          v9,
          8,
          11,
          (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
          127,
          PathTree);
      }
      v12 = (void *)v8[3];
      if ( v12 )
        BfpDeletePathTree(v12);
      v13 = (void *)v8[2];
      if ( v13 )
        FltReleaseContext(v13);
      ExFreePoolWithTag(v8, 0x706D4642u);
    }
    else
    {
      *a2 = v8;
      return 0;
    }
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v7) = 2;
      WPP_RECORDER_SF_sD(
        WPP_GLOBAL_Control->DeviceExtension,
        v7,
        8,
        10,
        (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
        109);
    }
    return (unsigned int)-1073741670;
  }
  return (unsigned int)PathTree;
}

```

## disassembly

```asm
0x14002001c  mov     [rsp+arg_0], rbx
0x140020021  mov     [rsp+arg_8], rsi
0x140020026  push    rdi
0x140020027  sub     rsp, 40h
0x14002002b  mov     rsi, rdx
0x14002002e  mov     qword ptr [rdx], 0
0x140020035  mov     rdi, rcx
0x140020038  mov     edx, 28h ; '('
0x14002003d  mov     ecx, 100h
0x140020042  mov     r8d, 706D4642h
0x140020048  call    cs:__imp_ExAllocatePool2
0x14002004f  nop     dword ptr [rax+rax+00h]
0x140020054  mov     rbx, rax
0x140020057  test    rax, rax
0x14002005a  jz      short loc_140020096
0x14002005c  mov     rcx, rdi; Context
0x14002005f  mov     [rax+10h], rdi
0x140020063  call    cs:__imp_FltReferenceContext
0x14002006a  nop     dword ptr [rax+rax+00h]
0x14002006f  lea     rcx, [rbx+18h]
0x140020073  call    BfpCreatePathTree
0x140020078  mov     edi, eax
0x14002007a  test    eax, eax
0x14002007c  js      short loc_1400200E9
0x14002007e  mov     [rsi], rbx
0x140020081  xor     edi, edi
0x140020083  mov     rbx, [rsp+48h+arg_0]
0x140020088  mov     eax, edi
0x14002008a  mov     rsi, [rsp+48h+arg_8]
0x14002008f  add     rsp, 40h
0x140020093  pop     rdi
0x140020094  retn
0x140020096  lea     rax, WPP_RECORDER_INITIALIZED
0x14002009d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400200a4  jz      short loc_1400200E2
0x1400200a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400200ad  lea     rax, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x1400200b4  mov     r9d, 0Ah
0x1400200ba  mov     [rsp+48h+var_18], 16Dh
0x1400200c2  mov     [rsp+48h+var_20], rax
0x1400200c7  mov     dl, 2
0x1400200c9  lea     rax, WPP_55845795197b3ed810b516bf1e89ed04_Traceguids
0x1400200d0  mov     rcx, [rcx+40h]
0x1400200d4  lea     r8d, [r9-2]
0x1400200d8  mov     [rsp+48h+var_28], rax
0x1400200dd  call    WPP_RECORDER_SF_sD
0x1400200e2  mov     edi, 0C000009Ah
0x1400200e7  jmp     short loc_140020083
0x1400200e9  lea     rax, WPP_RECORDER_INITIALIZED
0x1400200f0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400200f7  jz      short loc_140020139
0x1400200f9  mov     rcx, cs:WPP_GLOBAL_Control
0x140020100  lea     rax, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140020107  mov     [rsp+48h+var_10], edi
0x14002010b  mov     r9d, 0Bh
0x140020111  mov     [rsp+48h+var_18], 17Fh
0x140020119  mov     dl, 2
0x14002011b  mov     [rsp+48h+var_20], rax
0x140020120  lea     rax, WPP_55845795197b3ed810b516bf1e89ed04_Traceguids
0x140020127  mov     rcx, [rcx+40h]
0x14002012b  lea     r8d, [r9-3]
0x14002012f  mov     [rsp+48h+var_28], rax
0x140020134  call    WPP_RECORDER_SF_sDd
0x140020139  mov     rcx, [rbx+18h]; P
0x14002013d  test    rcx, rcx
0x140020140  jz      short loc_140020149
0x140020142  xor     edx, edx
0x140020144  call    BfpDeletePathTree
0x140020149  mov     rcx, [rbx+10h]; Context
0x14002014d  test    rcx, rcx
0x140020150  jz      short loc_14002015E
0x140020152  call    cs:__imp_FltReleaseContext
0x140020159  nop     dword ptr [rax+rax+00h]
0x14002015e  mov     edx, 706D4642h; Tag
0x140020163  mov     rcx, rbx; P
0x140020166  call    cs:__imp_ExFreePoolWithTag
0x14002016d  nop     dword ptr [rax+rax+00h]
0x140020172  jmp     loc_140020083
```
