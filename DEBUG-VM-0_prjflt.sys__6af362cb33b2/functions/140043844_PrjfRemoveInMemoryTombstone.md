# PrjfRemoveInMemoryTombstone

- ea: `0x140043844`
- end: `0x140043b1c`
- name: `PrjfRemoveInMemoryTombstone`
- size: `728`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance)`
- caller_count: `5`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140009d20`
- `0x14002c3f8`
- `0x14002c98c`
- `0x140040670`
- `0x140042eac`

## callees

- `0x140002b50`
- `0x14000d128`
- `0x14000d754`
- `0x14003c4b8`
- `0x140042b6c`
- `0x140043844`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140043a45`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043a6e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043a45`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043a6e`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1400439ba`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1400439ba`
- `ntoskrnl!ObfDereferenceObject` at `0x1400439fd`
- `ntoskrnl!ObfDereferenceObject` at `0x1400439fd`
- `FLTMGR!FltClose` at `0x1400439e4`
- `FLTMGR!FltClose` at `0x1400439e4`
- `FLTMGR!FltReleaseResource` at `0x1400439cd`
- `FLTMGR!FltReleaseResource` at `0x1400439cd`
- `FLTMGR!FltReleaseContext` at `0x140043a11`
- `FLTMGR!FltReleaseContext` at `0x140043a26`
- `FLTMGR!FltReleaseContext` at `0x140043a5a`
- `FLTMGR!FltReleaseContext` at `0x140043a11`
- `FLTMGR!FltReleaseContext` at `0x140043a26`
- `FLTMGR!FltReleaseContext` at `0x140043a5a`

## pseudocode

```c
__int64 __fastcall PrjfRemoveInMemoryTombstone(PFLT_INSTANCE Instance, __int64 a2, struct _FILE_OBJECT *a3)
{
  _WORD *v3; // r12
  struct _FILE_OBJECT *v4; // rbx
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v6; // r14
  char v7; // r13
  __int16 v8; // cx
  __int16 v9; // ax
  int v10; // edx
  int v11; // edi
  int v12; // r8d
  int v13; // edx
  int v14; // r8d
  void *Signature; // rcx
  struct _LIST_ENTRY *Flink; // rcx
  PRTL_DYNAMIC_HASH_TABLE_ENTRY Entry; // [rsp+68h] [rbp-1h] BYREF
  HANDLE FileHandle; // [rsp+70h] [rbp+7h] BYREF
  PFLT_CONTEXT Context; // [rsp+78h] [rbp+Fh]
  __m128i v21[4]; // [rsp+80h] [rbp+17h] BYREF
  char v22; // [rsp+E0h] [rbp+77h] BYREF
  PVOID Object; // [rsp+E8h] [rbp+7Fh] BYREF

  v3 = (_WORD *)(a2 + 88);
  FileHandle = 0;
  Object = 0;
  v4 = a3;
  Context = 0;
  v22 = 0;
  v6 = 0;
  Entry = 0;
  v21[0] = 0;
  if ( a3 )
  {
    v7 = 0;
  }
  else
  {
    v7 = 1;
    v21[0] = *(__m128i *)(a2 + 8);
    v8 = _mm_cvtsi128_si32(v21[0]) - *v3;
    v9 = v8 - 2;
    if ( v8 - 2 == *(_WORD *)(a2 + 24) )
      v9 = v8;
    v21[0].m128i_i16[0] = v9;
    v11 = PrjfOpenPlaceHolder(
            (_DWORD)Instance,
            (unsigned int)v21,
            0,
            (unsigned int)&FileHandle,
            (__int64)&Object,
            (__int64)&v22);
    if ( v11 < 0 )
    {
      if ( (BYTE2(xmmword_14001A3D0) & 8) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v10) = BYTE2(xmmword_14001A3D0) & 8;
        LOBYTE(v12) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDdZ(
          531,
          v10,
          v12,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          19,
          12,
          (__int64)WPP_3f08b24f959433411191d1ccab0ccd17_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\tombstone.c",
          57,
          v11,
          (__int64)v21);
      }
      v4 = (struct _FILE_OBJECT *)Object;
      goto LABEL_15;
    }
    v4 = (struct _FILE_OBJECT *)Object;
  }
  if ( !(unsigned __int8)PrjfGetContextFileObject(Instance, v4) )
  {
LABEL_14:
    v11 = 0;
    goto LABEL_15;
  }
  v11 = PrjfLookupInMemoryTombstoneEntry(0, v3, 1, 0, &Entry);
  if ( v11 >= 0 )
  {
    v6 = Entry;
    RtlRemoveEntryHashTable((PRTL_DYNAMIC_HASH_TABLE)0xF0, Entry, 0);
    FltReleaseResource((PERESOURCE)0x88);
    goto LABEL_14;
  }
  if ( v11 == -1073741275 )
    goto LABEL_14;
  if ( (BYTE2(xmmword_14001A3D0) & 8) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v13) = BYTE2(xmmword_14001A3D0) & 8;
    LOBYTE(v14) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sDL(
      531,
      v13,
      v14,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      2,
      19,
      13,
      (__int64)WPP_3f08b24f959433411191d1ccab0ccd17_Traceguids,
      (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\tombstone.c",
      90,
      v11);
  }
LABEL_15:
  if ( FileHandle )
    FltClose(FileHandle);
  if ( v7 && v4 )
    ObfDereferenceObject(v4);
  if ( Context )
    FltReleaseContext(Context);
  if ( v6 )
  {
    Signature = (void *)v6[1].Signature;
    if ( Signature )
      ExFreePoolWithTag(Signature, 0x6E664A50u);
    Flink = v6[2].Linkage.Flink;
    if ( Flink )
      FltReleaseContext(Flink);
    ExFreePoolWithTag(v6, 0x74684A50u);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140043844  mov     [rsp-8+arg_0], rbx
0x140043849  push    rbp
0x14004384a  push    rsi
0x14004384b  push    rdi
0x14004384c  push    r12
0x14004384e  push    r13
0x140043850  push    r14
0x140043852  push    r15
0x140043854  lea     rbp, [rsp-27h]
0x140043859  sub     rsp, 90h
0x140043860  xor     eax, eax
0x140043862  lea     r12, [rdx+58h]
0x140043866  mov     [rbp+57h+FileHandle], rax
0x14004386a  xorps   xmm0, xmm0
0x14004386d  mov     [rbp+57h+Object], rax
0x140043871  mov     rbx, r8
0x140043874  mov     [rbp+57h+var_60], rax
0x140043878  mov     r15, rcx
0x14004387b  mov     [rbp+57h+Context], rax
0x14004387f  mov     esi, eax
0x140043881  mov     [rbp+57h+arg_10], al
0x140043884  mov     r14d, eax
0x140043887  mov     [rbp+57h+Entry], rax
0x14004388b  movups  [rbp+57h+var_40], xmm0
0x14004388f  test    r8, r8
0x140043892  jz      short loc_14004389C
0x140043894  mov     r13b, al
0x140043897  jmp     loc_140043969
0x14004389c  movups  xmm0, xmmword ptr [rdx+8]
0x1400438a0  lea     r9, [rbp+57h+FileHandle]
0x1400438a4  mov     r13b, 1
0x1400438a7  movd    ecx, xmm0
0x1400438ab  movups  [rbp+57h+var_40], xmm0
0x1400438af  sub     cx, [r12]
0x1400438b4  lea     eax, [rcx-2]
0x1400438b7  cmp     ax, [rdx+18h]
0x1400438bb  lea     rdx, [rbp+57h+var_40]
0x1400438bf  cmovz   ax, cx
0x1400438c3  mov     rcx, r15
0x1400438c6  mov     word ptr [rbp+57h+var_40], ax
0x1400438ca  lea     rax, [rbp+57h+arg_10]
0x1400438ce  mov     [rsp+0C0h+var_98], rax
0x1400438d3  lea     rax, [rbp+57h+Object]
0x1400438d7  mov     [rsp+0C0h+var_A0], rax
0x1400438dc  call    PrjfOpenPlaceHolder
0x1400438e1  mov     edi, eax
0x1400438e3  test    eax, eax
0x1400438e5  jns     short loc_140043965
0x1400438e7  mov     dl, byte ptr cs:xmmword_14001A3D0+2
0x1400438ed  lea     rax, WPP_RECORDER_INITIALIZED
0x1400438f4  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400438fb  setnz   r8b
0x1400438ff  and     dl, 8
0x140043902  jnz     short loc_140043909
0x140043904  test    r8b, r8b
0x140043907  jz      short loc_14004395F
0x140043909  mov     r9, cs:WPP_GLOBAL_Control
0x140043910  lea     rax, [rbp+57h+var_40]
0x140043914  mov     [rsp+0C0h+var_68], rax
0x140043919  mov     ecx, 213h
0x14004391e  mov     [rsp+0C0h+var_70], edi
0x140043922  lea     rax, aOnecoreBaseFsG_6; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140043929  mov     [rsp+0C0h+var_78], 139h
0x140043931  mov     r9, [r9+40h]
0x140043935  mov     [rsp+0C0h+var_80], rax
0x14004393a  lea     rax, WPP_3f08b24f959433411191d1ccab0ccd17_Traceguids
0x140043941  mov     [rsp+0C0h+var_88], rax
0x140043946  mov     [rsp+0C0h+var_90], 0Ch
0x14004394d  mov     dword ptr [rsp+0C0h+var_98], 13h
0x140043955  mov     byte ptr [rsp+0C0h+var_A0], 2
0x14004395a  call    WPP_RECORDER_AND_TRACE_SF_sDdZ
0x14004395f  mov     rbx, [rbp+57h+Object]
0x140043963  jmp     short loc_1400439DB
0x140043965  mov     rbx, [rbp+57h+Object]
0x140043969  lea     r9, [rbp+57h+Context]
0x14004396d  mov     rdx, rbx; FileObject
0x140043970  lea     r8, [rbp+57h+var_60]
0x140043974  mov     rcx, r15; Instance
0x140043977  call    PrjfGetContextFileObject
0x14004397c  mov     rsi, [rbp+57h+var_60]
0x140043980  test    al, al
0x140043982  jz      short loc_1400439D9
0x140043984  xor     r9d, r9d
0x140043987  lea     rax, [rbp+57h+Entry]
0x14004398b  mov     rdx, r12
0x14004398e  mov     [rsp+0C0h+var_A0], rax
0x140043993  mov     rcx, rsi
0x140043996  lea     r8d, [r9+1]
0x14004399a  call    PrjfLookupInMemoryTombstoneEntry
0x14004399f  mov     edi, eax
0x1400439a1  test    eax, eax
0x1400439a3  js      loc_140043A98
0x1400439a9  mov     r14, [rbp+57h+Entry]
0x1400439ad  lea     rcx, [rsi+0F0h]; HashTable
0x1400439b4  mov     rdx, r14; Entry
0x1400439b7  xor     r8d, r8d; Context
0x1400439ba  call    cs:__imp_RtlRemoveEntryHashTable
0x1400439c1  nop     dword ptr [rax+rax+00h]
0x1400439c6  lea     rcx, [rsi+88h]; Resource
0x1400439cd  call    cs:__imp_FltReleaseResource
0x1400439d4  nop     dword ptr [rax+rax+00h]
0x1400439d9  xor     edi, edi
0x1400439db  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x1400439df  test    rcx, rcx
0x1400439e2  jz      short loc_1400439F0
0x1400439e4  call    cs:__imp_FltClose
0x1400439eb  nop     dword ptr [rax+rax+00h]
0x1400439f0  test    r13b, r13b
0x1400439f3  jz      short loc_140043A09
0x1400439f5  test    rbx, rbx
0x1400439f8  jz      short loc_140043A09
0x1400439fa  mov     rcx, rbx; Object
0x1400439fd  call    cs:__imp_ObfDereferenceObject
0x140043a04  nop     dword ptr [rax+rax+00h]
0x140043a09  test    rsi, rsi
0x140043a0c  jz      short loc_140043A1D
0x140043a0e  mov     rcx, rsi; Context
0x140043a11  call    cs:__imp_FltReleaseContext
0x140043a18  nop     dword ptr [rax+rax+00h]
0x140043a1d  mov     rcx, [rbp+57h+Context]; Context
0x140043a21  test    rcx, rcx
0x140043a24  jz      short loc_140043A32
0x140043a26  call    cs:__imp_FltReleaseContext
0x140043a2d  nop     dword ptr [rax+rax+00h]
0x140043a32  test    r14, r14
0x140043a35  jz      short loc_140043A7A
0x140043a37  mov     rcx, [r14+28h]; P
0x140043a3b  test    rcx, rcx
0x140043a3e  jz      short loc_140043A51
0x140043a40  mov     edx, 6E664A50h; Tag
0x140043a45  call    cs:__imp_ExFreePoolWithTag
0x140043a4c  nop     dword ptr [rax+rax+00h]
0x140043a51  mov     rcx, [r14+30h]; Context
0x140043a55  test    rcx, rcx
0x140043a58  jz      short loc_140043A66
0x140043a5a  call    cs:__imp_FltReleaseContext
0x140043a61  nop     dword ptr [rax+rax+00h]
0x140043a66  mov     edx, 74684A50h; Tag
0x140043a6b  mov     rcx, r14; P
0x140043a6e  call    cs:__imp_ExFreePoolWithTag
0x140043a75  nop     dword ptr [rax+rax+00h]
0x140043a7a  mov     rbx, [rsp+0C0h+arg_0]
0x140043a82  mov     eax, edi
0x140043a84  add     rsp, 90h
0x140043a8b  pop     r15
0x140043a8d  pop     r14
0x140043a8f  pop     r13
0x140043a91  pop     r12
0x140043a93  pop     rdi
0x140043a94  pop     rsi
0x140043a95  pop     rbp
0x140043a96  retn
0x140043a98  cmp     edi, 0C0000225h
0x140043a9e  jz      loc_1400439D9
0x140043aa4  mov     dl, byte ptr cs:xmmword_14001A3D0+2
0x140043aaa  lea     rax, WPP_RECORDER_INITIALIZED
0x140043ab1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140043ab8  setnz   r8b
0x140043abc  and     dl, 8
0x140043abf  jnz     short loc_140043ACA
0x140043ac1  test    r8b, r8b
0x140043ac4  jz      loc_1400439DB
0x140043aca  mov     r9, cs:WPP_GLOBAL_Control
0x140043ad1  lea     rax, aOnecoreBaseFsG_6; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140043ad8  mov     [rsp+0C0h+var_70], edi
0x140043adc  mov     ecx, 213h
0x140043ae1  mov     [rsp+0C0h+var_78], 15Ah
0x140043ae9  mov     [rsp+0C0h+var_80], rax
0x140043aee  lea     rax, WPP_3f08b24f959433411191d1ccab0ccd17_Traceguids
0x140043af5  mov     r9, [r9+40h]
0x140043af9  mov     [rsp+0C0h+var_88], rax
0x140043afe  mov     [rsp+0C0h+var_90], 0Dh
0x140043b05  mov     dword ptr [rsp+0C0h+var_98], 13h
0x140043b0d  mov     byte ptr [rsp+0C0h+var_A0], 2
0x140043b12  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140043b17  jmp     loc_1400439DB
```
