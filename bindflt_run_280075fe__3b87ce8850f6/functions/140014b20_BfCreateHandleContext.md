# BfCreateHandleContext

- ea: `0x140014b20`
- end: `0x140014cc5`
- name: `BfCreateHandleContext`
- size: `421`
- prototype: `__int64 __fastcall(int, int, int, int, PCUNICODE_STRING Source, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140014e9c`

## callees

- `0x140001348`
- `0x140002d54`
- `0x140004fc0`
- `0x140014b20`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140014bac`
- `ntoskrnl!KeInitializeEvent` at `0x140014bac`
- `FLTMGR!FltReleaseContext` at `0x140014cb4`
- `FLTMGR!FltReleaseContext` at `0x140014cb4`
- `FLTMGR!FltAllocateContext` at `0x140014b73`
- `FLTMGR!FltAllocateContext` at `0x140014b73`

## pseudocode

```c
__int64 __fastcall BfCreateHandleContext(
        int a1,
        int a2,
        int a3,
        int a4,
        PCUNICODE_STRING Source,
        __int64 a6,
        __int64 a7,
        _QWORD *a8)
{
  struct _FLT_FILTER *v12; // rcx
  NTSTATUS v13; // eax
  int v14; // edx
  unsigned int v15; // ebx
  int inited; // eax
  int v18; // r9d
  char v19; // [rsp+30h] [rbp-58h]
  __int64 v20; // [rsp+38h] [rbp-50h]
  PFLT_CONTEXT Context[9]; // [rsp+40h] [rbp-48h] BYREF

  Context[0] = 0;
  v12 = g_BindFltState;
  *a8 = 0;
  v13 = FltAllocateContext(v12, 0x10u, 0x98u, (POOL_TYPE)512, Context);
  v15 = v13;
  if ( v13 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_4;
    LODWORD(v20) = v13;
    v18 = 20;
    v19 = -46;
    goto LABEL_9;
  }
  memset(Context[0], 0, 0x98u);
  KeInitializeEvent((PRKEVENT)((char *)Context[0] + 128), SynchronizationEvent, 1u);
  inited = BfInitShadowFileHandleContext(a1, a2, a3, a4, Source, a6, a7, (__int64)Context);
  v15 = inited;
  if ( inited >= 0 )
  {
    *a8 = Context[0];
    Context[0] = 0;
    goto LABEL_4;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LODWORD(v20) = inited;
    v18 = 21;
    v19 = -28;
LABEL_9:
    LOBYTE(v14) = 2;
    WPP_RECORDER_SF_sDd(
      WPP_GLOBAL_Control->DeviceExtension,
      v14,
      7,
      v18,
      (__int64)WPP_ab4056511ca038337f1519c30a6fffbb_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\context.c",
      v19,
      v20);
  }
LABEL_4:
  if ( Context[0] )
    FltReleaseContext(Context[0]);
  return v15;
}

```

## disassembly

```asm
0x140014b20  push    rbx
0x140014b22  push    rbp
0x140014b23  push    rsi
0x140014b24  push    rdi
0x140014b25  push    r14
0x140014b27  push    r15
0x140014b29  sub     rsp, 58h
0x140014b2d  mov     rdi, [rsp+88h+arg_38]
0x140014b35  lea     rax, [rsp+88h+Context]
0x140014b3a  mov     rsi, r9
0x140014b3d  mov     [rsp+88h+Context], 0
0x140014b46  mov     rbp, r8
0x140014b49  mov     [rsp+88h+ReturnedContext], rax; ReturnedContext
0x140014b4e  mov     r14, rdx
0x140014b51  mov     r15, rcx
0x140014b54  mov     rcx, cs:g_BindFltState; Filter
0x140014b5b  mov     edx, 10h; ContextType
0x140014b60  mov     r9d, 200h; PoolType
0x140014b66  mov     qword ptr [rdi], 0
0x140014b6d  mov     r8d, 98h; ContextSize
0x140014b73  call    cs:__imp_FltAllocateContext
0x140014b7a  nop     dword ptr [rax+rax+00h]
0x140014b7f  mov     ebx, eax
0x140014b81  test    eax, eax
0x140014b83  js      loc_140014C33
0x140014b89  mov     rcx, [rsp+88h+Context]; void *
0x140014b8e  xor     edx, edx; Val
0x140014b90  mov     r8d, 98h; Size
0x140014b96  call    memset
0x140014b9b  mov     rcx, [rsp+88h+Context]
0x140014ba0  mov     r8b, 1; State
0x140014ba3  sub     rcx, 0FFFFFFFFFFFFFF80h; Event
0x140014ba7  mov     edx, 1; Type
0x140014bac  call    cs:__imp_KeInitializeEvent
0x140014bb3  nop     dword ptr [rax+rax+00h]
0x140014bb8  lea     rax, [rsp+88h+Context]
0x140014bbd  mov     r9, rsi; int
0x140014bc0  mov     [rsp+88h+var_50], rax; __int64
0x140014bc5  mov     r8, rbp; int
0x140014bc8  mov     rax, [rsp+88h+arg_30]
0x140014bd0  mov     rdx, r14; int
0x140014bd3  mov     [rsp+88h+var_58], rax; __int64
0x140014bd8  mov     rcx, r15; int
0x140014bdb  mov     rax, [rsp+88h+arg_28]
0x140014be3  mov     [rsp+88h+var_60], rax; __int64
0x140014be8  mov     rax, [rsp+88h+Source]
0x140014bf0  mov     [rsp+88h+ReturnedContext], rax; Source
0x140014bf5  call    BfInitShadowFileHandleContext
0x140014bfa  mov     ebx, eax
0x140014bfc  test    eax, eax
0x140014bfe  js      loc_140014C9E
0x140014c04  mov     rax, [rsp+88h+Context]
0x140014c09  mov     [rdi], rax
0x140014c0c  mov     [rsp+88h+Context], 0
0x140014c15  mov     rcx, [rsp+88h+Context]; Context
0x140014c1a  test    rcx, rcx
0x140014c1d  jnz     loc_140014CB4
0x140014c23  mov     eax, ebx
0x140014c25  add     rsp, 58h
0x140014c29  pop     r15
0x140014c2b  pop     r14
0x140014c2d  pop     rdi
0x140014c2e  pop     rsi
0x140014c2f  pop     rbp
0x140014c30  pop     rbx
0x140014c31  retn
0x140014c33  lea     rcx, WPP_RECORDER_INITIALIZED
0x140014c3a  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140014c41  jz      short loc_140014C15
0x140014c43  mov     dword ptr [rsp+88h+var_50], eax
0x140014c47  mov     r9d, 14h
0x140014c4d  mov     dword ptr [rsp+88h+var_58], 3D2h
0x140014c55  jmp     short loc_140014C69
0x140014c57  mov     dword ptr [rsp+88h+var_50], eax
0x140014c5b  mov     r9d, 15h
0x140014c61  mov     dword ptr [rsp+88h+var_58], 3E4h
0x140014c69  mov     rcx, cs:WPP_GLOBAL_Control
0x140014c70  lea     rax, aOnecoreBaseFsW; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140014c77  mov     [rsp+88h+var_60], rax
0x140014c7c  mov     r8d, 7
0x140014c82  lea     rax, WPP_ab4056511ca038337f1519c30a6fffbb_Traceguids
0x140014c89  mov     dl, 2
0x140014c8b  mov     [rsp+88h+ReturnedContext], rax
0x140014c90  mov     rcx, [rcx+40h]
0x140014c94  call    WPP_RECORDER_SF_sDd
0x140014c99  jmp     loc_140014C15
0x140014c9e  lea     rcx, WPP_RECORDER_INITIALIZED
0x140014ca5  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140014cac  jz      loc_140014C15
0x140014cb2  jmp     short loc_140014C57
0x140014cb4  call    cs:__imp_FltReleaseContext
0x140014cbb  nop     dword ptr [rax+rax+00h]
0x140014cc0  jmp     loc_140014C23
```
