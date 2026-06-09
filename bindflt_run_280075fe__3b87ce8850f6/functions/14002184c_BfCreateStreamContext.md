# BfCreateStreamContext

- ea: `0x14002184c`
- end: `0x140021a60`
- name: `BfCreateStreamContext`
- size: `532`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1400157a0`
- `0x140018b60`

## callees

- `0x140001348`
- `0x140004fc0`
- `0x14002184c`

## import_xrefs

- `ntoskrnl!ExInitializeResourceLite` at `0x1400219af`
- `ntoskrnl!ExInitializeResourceLite` at `0x1400219af`
- `ntoskrnl!KeInitializeEvent` at `0x14002191a`
- `ntoskrnl!KeInitializeEvent` at `0x14002191a`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400218e5`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400218e5`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400219f8`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400219f8`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400218c6`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400218c6`
- `FLTMGR!FltAllocateContext` at `0x14002188e`
- `FLTMGR!FltAllocateContext` at `0x14002188e`

## pseudocode

```c
__int64 __fastcall BfCreateStreamContext(__int64 a1, char a2, void **a3)
{
  int v6; // edx
  NTSTATUS v7; // edi
  _QWORD *v8; // rbx
  struct _KEVENT *v9; // rax
  struct _KEVENT *v10; // rsi
  _OWORD *v11; // rax
  void *v13; // [rsp+78h] [rbp+20h] BYREF

  v13 = 0;
  v7 = FltAllocateContext(g_BindFltState, 8u, 0x78u, (POOL_TYPE)512, &v13);
  if ( v7 >= 0 )
  {
    v8 = 0;
    memset(v13, 0, 0x78u);
    if ( a2 )
    {
      v8 = ExAllocateFromPagedLookasideList(&stru_14000B280);
      if ( v8 )
      {
        v9 = (struct _KEVENT *)ExAllocateFromNPagedLookasideList(&stru_14000B300);
        v10 = v9;
        if ( v9 )
        {
          v9->Header.WaitListHead.Flink = 0;
          v9->Header.LockNV = 1;
          LODWORD(v9->Header.WaitListHead.Blink) = 0;
          KeInitializeEvent(v9 + 1, SynchronizationEvent, 0);
          v8[15] = v10;
          v8[16] = v13;
          v11 = *(_OWORD **)(a1 + 24);
          *(_OWORD *)v8 = *v11;
          *((_OWORD *)v8 + 1) = v11[1];
          *((_OWORD *)v8 + 2) = v11[2];
          LOBYTE(v11) = *((_BYTE *)v8 + 7);
          *((_BYTE *)v8 + 4) |= 0x40u;
          *((_BYTE *)v8 + 6) |= 2u;
          *(_DWORD *)v8 = 8938545;
          *((_BYTE *)v8 + 7) = (unsigned __int8)v11 & 0xF | 0x50;
          v8[8] = v8 + 7;
          v8[7] = v8 + 7;
          v8[6] = v10;
          v8[9] = 0;
          v8[10] = 0;
          v8[11] = 0;
          v8[12] = 0;
          *((_DWORD *)v8 + 26) = 0;
          v8[14] = 0;
          goto LABEL_6;
        }
        ExFreeToPagedLookasideList(&stru_14000B280, v8);
      }
      return (unsigned int)-1073741670;
    }
LABEL_6:
    ExInitializeResourceLite((PERESOURCE)((char *)v13 + 8));
    *(_QWORD *)v13 = 0;
    *((_QWORD *)v13 + 14) = v8;
    *a3 = v13;
    return (unsigned int)v7;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v6) = 2;
    WPP_RECORDER_SF_sDd(
      WPP_GLOBAL_Control->DeviceExtension,
      v6,
      5,
      19,
      (__int64)WPP_ab4056511ca038337f1519c30a6fffbb_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\context.c",
      120,
      v7);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14002184c  mov     r11, rsp
0x14002184f  mov     [r11+8], rbx
0x140021853  mov     [r11+10h], rbp
0x140021857  push    rsi
0x140021858  push    rdi
0x140021859  push    r14
0x14002185b  sub     rsp, 40h
0x14002185f  mov     sil, dl
0x140021862  mov     qword ptr [r11+20h], 0
0x14002186a  mov     edx, 8; ContextType
0x14002186f  lea     rax, [r11+20h]
0x140021873  mov     r14, r8
0x140021876  mov     [r11-38h], rax
0x14002187a  mov     rbp, rcx
0x14002187d  mov     r9d, 200h; PoolType
0x140021883  mov     rcx, cs:g_BindFltState; Filter
0x14002188a  lea     r8d, [rdx+70h]; ContextSize
0x14002188e  call    cs:__imp_FltAllocateContext
0x140021895  nop     dword ptr [rax+rax+00h]
0x14002189a  mov     edi, eax
0x14002189c  test    eax, eax
0x14002189e  js      loc_140021A0B
0x1400218a4  mov     rcx, [rsp+58h+arg_18]; void *
0x1400218a9  xor     ebx, ebx
0x1400218ab  xor     edx, edx; Val
0x1400218ad  lea     r8d, [rbx+78h]; Size
0x1400218b1  call    memset
0x1400218b6  test    sil, sil
0x1400218b9  jz      loc_1400219A6
0x1400218bf  lea     rcx, stru_14000B280; Lookaside
0x1400218c6  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1400218cd  nop     dword ptr [rax+rax+00h]
0x1400218d2  mov     rbx, rax
0x1400218d5  test    rax, rax
0x1400218d8  jz      loc_140021A04
0x1400218de  lea     rcx, stru_14000B300; Lookaside
0x1400218e5  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400218ec  nop     dword ptr [rax+rax+00h]
0x1400218f1  mov     rsi, rax
0x1400218f4  test    rax, rax
0x1400218f7  jz      loc_1400219EE
0x1400218fd  mov     edx, 1; Type
0x140021902  mov     qword ptr [rax+8], 0
0x14002190a  lea     rcx, [rax+18h]; Event
0x14002190e  mov     [rax], edx
0x140021910  xor     r8d, r8d; State
0x140021913  mov     dword ptr [rax+10h], 0
0x14002191a  call    cs:__imp_KeInitializeEvent
0x140021921  nop     dword ptr [rax+rax+00h]
0x140021926  mov     [rbx+78h], rsi
0x14002192a  mov     rcx, [rsp+58h+arg_18]
0x14002192f  mov     [rbx+80h], rcx
0x140021936  mov     rax, [rbp+18h]
0x14002193a  movups  xmm0, xmmword ptr [rax]
0x14002193d  movups  xmmword ptr [rbx], xmm0
0x140021940  movups  xmm1, xmmword ptr [rax+10h]
0x140021944  movups  xmmword ptr [rbx+10h], xmm1
0x140021948  movups  xmm0, xmmword ptr [rax+20h]
0x14002194c  movups  xmmword ptr [rbx+20h], xmm0
0x140021950  mov     al, [rbx+7]
0x140021953  or      byte ptr [rbx+4], 40h
0x140021957  and     al, 0Fh
0x140021959  or      byte ptr [rbx+6], 2
0x14002195d  or      al, 50h
0x14002195f  mov     dword ptr [rbx], 886431h
0x140021965  mov     [rbx+7], al
0x140021968  lea     rax, [rbx+38h]
0x14002196c  mov     [rax+8], rax
0x140021970  mov     [rax], rax
0x140021973  mov     [rbx+30h], rsi
0x140021977  mov     qword ptr [rbx+48h], 0
0x14002197f  mov     qword ptr [rbx+50h], 0
0x140021987  mov     qword ptr [rbx+58h], 0
0x14002198f  mov     qword ptr [rbx+60h], 0
0x140021997  mov     dword ptr [rbx+68h], 0
0x14002199e  mov     qword ptr [rbx+70h], 0
0x1400219a6  mov     rcx, [rsp+58h+arg_18]
0x1400219ab  add     rcx, 8; Resource
0x1400219af  call    cs:__imp_ExInitializeResourceLite
0x1400219b6  nop     dword ptr [rax+rax+00h]
0x1400219bb  mov     rax, [rsp+58h+arg_18]
0x1400219c0  mov     qword ptr [rax], 0
0x1400219c7  mov     rax, [rsp+58h+arg_18]
0x1400219cc  mov     [rax+70h], rbx
0x1400219d0  mov     rax, [rsp+58h+arg_18]
0x1400219d5  mov     [r14], rax
0x1400219d8  mov     rbx, [rsp+58h+arg_0]
0x1400219dd  mov     eax, edi
0x1400219df  mov     rbp, [rsp+58h+arg_8]
0x1400219e4  add     rsp, 40h
0x1400219e8  pop     r14
0x1400219ea  pop     rdi
0x1400219eb  pop     rsi
0x1400219ec  retn
0x1400219ee  mov     rdx, rbx; Entry
0x1400219f1  lea     rcx, stru_14000B280; Lookaside
0x1400219f8  call    cs:__imp_ExFreeToPagedLookasideList
0x1400219ff  nop     dword ptr [rax+rax+00h]
0x140021a04  mov     edi, 0C000009Ah
0x140021a09  jmp     short loc_1400219D8
0x140021a0b  lea     rax, WPP_RECORDER_INITIALIZED
0x140021a12  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140021a19  jz      short loc_1400219D8
0x140021a1b  mov     rcx, cs:WPP_GLOBAL_Control
0x140021a22  lea     rax, aOnecoreBaseFsW; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140021a29  mov     [rsp+58h+var_20], edi
0x140021a2d  mov     r9d, 13h
0x140021a33  mov     [rsp+58h+var_28], 278h
0x140021a3b  mov     dl, 2
0x140021a3d  mov     [rsp+58h+var_30], rax
0x140021a42  lea     rax, WPP_ab4056511ca038337f1519c30a6fffbb_Traceguids
0x140021a49  mov     rcx, [rcx+40h]
0x140021a4d  lea     r8d, [r9-0Eh]
0x140021a51  mov     [rsp+58h+var_38], rax
0x140021a56  call    WPP_RECORDER_SF_sDd
0x140021a5b  jmp     loc_1400219D8
```
