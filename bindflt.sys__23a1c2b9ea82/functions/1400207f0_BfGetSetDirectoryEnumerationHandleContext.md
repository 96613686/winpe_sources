# BfGetSetDirectoryEnumerationHandleContext

- ea: `0x1400207f0`
- end: `0x1400209fb`
- name: `BfGetSetDirectoryEnumerationHandleContext`
- size: `523`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140024e50`

## callees

- `0x140001348`
- `0x140004fc0`
- `0x1400207f0`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140020856`
- `ntoskrnl!KeWaitForSingleObject` at `0x140020856`
- `ntoskrnl!KeInitializeEvent` at `0x140020919`
- `ntoskrnl!KeInitializeEvent` at `0x140020919`
- `FLTMGR!FltGetStreamHandleContext` at `0x14002081f`
- `FLTMGR!FltGetStreamHandleContext` at `0x14002081f`
- `FLTMGR!FltSetStreamHandleContext` at `0x14002093a`
- `FLTMGR!FltSetStreamHandleContext` at `0x14002093a`
- `FLTMGR!FltAllocateContext` at `0x1400208e0`
- `FLTMGR!FltAllocateContext` at `0x1400208e0`

## pseudocode

```c
__int64 __fastcall BfGetSetDirectoryEnumerationHandleContext(__int64 a1, _BYTE *a2, _QWORD *a3)
{
  struct _FILE_OBJECT *v5; // rdx
  struct _FLT_INSTANCE *v7; // rcx
  NTSTATUS StreamHandleContext; // eax
  int v9; // edx
  unsigned int v10; // ebx
  _DWORD *v11; // rcx
  _QWORD *v12; // rax
  int v14; // r9d
  char v15; // [rsp+30h] [rbp-28h]
  unsigned int v16; // [rsp+38h] [rbp-20h]
  PFLT_CONTEXT Context; // [rsp+60h] [rbp+8h] BYREF

  v5 = *(struct _FILE_OBJECT **)(a1 + 32);
  v7 = *(struct _FLT_INSTANCE **)(a1 + 24);
  Context = 0;
  StreamHandleContext = FltGetStreamHandleContext(v7, v5, &Context);
  v10 = StreamHandleContext;
  if ( StreamHandleContext == -1073741275 )
  {
    v10 = FltAllocateContext(g_BindFltState, 0x10u, 0x98u, (POOL_TYPE)512, &Context);
    if ( (v10 & 0x80000000) != 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return v10;
      v16 = v10;
      v14 = 29;
      v15 = -68;
    }
    else
    {
      memset(Context, 0, 0x98u);
      KeInitializeEvent((PRKEVENT)((char *)Context + 128), SynchronizationEvent, 1u);
      v10 = FltSetStreamHandleContext(
              *(PFLT_INSTANCE *)(a1 + 24),
              *(PFILE_OBJECT *)(a1 + 32),
              FLT_SET_CONTEXT_REPLACE_IF_EXISTS,
              Context,
              0);
      if ( (v10 & 0x80000000) == 0 )
        goto LABEL_3;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return v10;
      v16 = v10;
      v14 = 30;
      v15 = -53;
    }
LABEL_13:
    LOBYTE(v9) = 2;
    WPP_RECORDER_SF_sDd(
      WPP_GLOBAL_Control->DeviceExtension,
      v9,
      7,
      v14,
      (__int64)WPP_e12ce5656ffd33908c95ca7de20f6d85_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\dirctrl.c",
      v15,
      v16);
    return v10;
  }
  if ( StreamHandleContext < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return v10;
    v16 = StreamHandleContext;
    v14 = 31;
    v15 = -47;
    goto LABEL_13;
  }
LABEL_3:
  KeWaitForSingleObject((char *)Context + 128, Executive, 0, 0, 0);
  v11 = Context;
  *a2 = 1;
  if ( (v11[20] & 2) == 0 )
  {
    v11[21] = 0;
    *((_QWORD *)Context + 11) = 0;
    v12 = (char *)Context + 96;
    *((_QWORD *)Context + 13) = (char *)Context + 96;
    *v12 = v12;
    *((_BYTE *)Context + 112) = 0;
    *((_DWORD *)Context + 20) |= 2u;
    v11 = Context;
  }
  *a3 = v11;
  return v10;
}

```

## disassembly

```asm
0x1400207f0  mov     [rsp+arg_8], rbx
0x1400207f5  mov     [rsp+arg_10], rbp
0x1400207fa  push    rsi
0x1400207fb  push    rdi
0x1400207fc  push    r14
0x1400207fe  sub     rsp, 40h
0x140020802  mov     r14, rdx
0x140020805  mov     rsi, r8
0x140020808  mov     rdx, [rcx+20h]; FileObject
0x14002080c  lea     r8, [rsp+58h+Context]; Context
0x140020811  mov     rdi, rcx
0x140020814  xor     ebp, ebp
0x140020816  mov     rcx, [rcx+18h]; Instance
0x14002081a  mov     [rsp+58h+Context], rbp
0x14002081f  call    cs:__imp_FltGetStreamHandleContext
0x140020826  nop     dword ptr [rax+rax+00h]
0x14002082b  mov     ebx, eax
0x14002082d  cmp     eax, 0C0000225h
0x140020832  jz      loc_1400208BE
0x140020838  test    eax, eax
0x14002083a  js      loc_1400209D3
0x140020840  mov     rcx, [rsp+58h+Context]
0x140020845  xor     r9d, r9d; Alertable
0x140020848  sub     rcx, 0FFFFFFFFFFFFFF80h; Object
0x14002084c  mov     [rsp+58h+Timeout], rbp; Timeout
0x140020851  xor     r8d, r8d; WaitMode
0x140020854  xor     edx, edx; WaitReason
0x140020856  call    cs:__imp_KeWaitForSingleObject
0x14002085d  nop     dword ptr [rax+rax+00h]
0x140020862  mov     rcx, [rsp+58h+Context]
0x140020867  mov     byte ptr [r14], 1
0x14002086b  mov     eax, [rcx+50h]
0x14002086e  test    al, 2
0x140020870  jnz     short loc_1400208A5
0x140020872  mov     [rcx+54h], ebp
0x140020875  mov     rax, [rsp+58h+Context]
0x14002087a  mov     [rax+58h], rbp
0x14002087e  mov     rax, [rsp+58h+Context]
0x140020883  add     rax, 60h ; '`'
0x140020887  mov     [rax+8], rax
0x14002088b  mov     [rax], rax
0x14002088e  mov     rax, [rsp+58h+Context]
0x140020893  mov     [rax+70h], bpl
0x140020897  mov     rax, [rsp+58h+Context]
0x14002089c  or      dword ptr [rax+50h], 2
0x1400208a0  mov     rcx, [rsp+58h+Context]
0x1400208a5  mov     [rsi], rcx
0x1400208a8  mov     eax, ebx
0x1400208aa  mov     rbx, [rsp+58h+arg_8]
0x1400208af  mov     rbp, [rsp+58h+arg_10]
0x1400208b4  add     rsp, 40h
0x1400208b8  pop     r14
0x1400208ba  pop     rdi
0x1400208bb  pop     rsi
0x1400208bc  retn
0x1400208be  mov     rcx, cs:g_BindFltState; Filter
0x1400208c5  lea     rax, [rsp+58h+Context]
0x1400208ca  mov     edx, 10h; ContextType
0x1400208cf  mov     [rsp+58h+Timeout], rax; ReturnedContext
0x1400208d4  mov     r9d, 200h; PoolType
0x1400208da  mov     r8d, 98h; ContextSize
0x1400208e0  call    cs:__imp_FltAllocateContext
0x1400208e7  nop     dword ptr [rax+rax+00h]
0x1400208ec  mov     ebx, eax
0x1400208ee  test    eax, eax
0x1400208f0  js      loc_140020978
0x1400208f6  mov     rcx, [rsp+58h+Context]; void *
0x1400208fb  xor     edx, edx; Val
0x1400208fd  mov     r8d, 98h; Size
0x140020903  call    memset
0x140020908  mov     rcx, [rsp+58h+Context]
0x14002090d  mov     r8b, 1; State
0x140020910  sub     rcx, 0FFFFFFFFFFFFFF80h; Event
0x140020914  mov     edx, 1; Type
0x140020919  call    cs:__imp_KeInitializeEvent
0x140020920  nop     dword ptr [rax+rax+00h]
0x140020925  mov     r9, [rsp+58h+Context]; NewContext
0x14002092a  xor     r8d, r8d; Operation
0x14002092d  mov     rdx, [rdi+20h]; FileObject
0x140020931  mov     rcx, [rdi+18h]; Instance
0x140020935  mov     [rsp+58h+Timeout], rbp; OldContext
0x14002093a  call    cs:__imp_FltSetStreamHandleContext
0x140020941  nop     dword ptr [rax+rax+00h]
0x140020946  mov     ebx, eax
0x140020948  test    eax, eax
0x14002094a  jns     loc_140020840
0x140020950  lea     rax, WPP_RECORDER_INITIALIZED
0x140020957  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002095e  jz      loc_1400208A8
0x140020964  mov     [rsp+58h+var_20], ebx
0x140020968  mov     r9d, 1Eh
0x14002096e  mov     dword ptr [rsp+58h+var_28], 7CBh
0x140020976  jmp     short loc_14002099E
0x140020978  lea     rax, WPP_RECORDER_INITIALIZED
0x14002097f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140020986  jz      loc_1400208A8
0x14002098c  mov     [rsp+58h+var_20], ebx
0x140020990  mov     r9d, 1Dh
0x140020996  mov     dword ptr [rsp+58h+var_28], 7BCh
0x14002099e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400209a5  lea     rax, aOnecoreBaseFsW_2; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x1400209ac  mov     [rsp+58h+var_30], rax
0x1400209b1  mov     r8d, 7
0x1400209b7  lea     rax, WPP_e12ce5656ffd33908c95ca7de20f6d85_Traceguids
0x1400209be  mov     dl, 2
0x1400209c0  mov     [rsp+58h+Timeout], rax
0x1400209c5  mov     rcx, [rcx+40h]
0x1400209c9  call    WPP_RECORDER_SF_sDd
0x1400209ce  jmp     loc_1400208A8
0x1400209d3  lea     rax, WPP_RECORDER_INITIALIZED
0x1400209da  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400209e1  jz      loc_1400208A8
0x1400209e7  mov     [rsp+58h+var_20], ebx
0x1400209eb  mov     r9d, 1Fh
0x1400209f1  mov     dword ptr [rsp+58h+var_28], 7D1h
0x1400209f9  jmp     short loc_14002099E
```
