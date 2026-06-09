# BfpGetInstanceTierNode

- ea: `0x14000f008`
- end: `0x14000f228`
- name: `BfpGetInstanceTierNode`
- size: `544`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140010384`
- `0x140010898`
- `0x140010d64`
- `0x14001d974`

## callees

- `0x140001348`
- `0x14000f008`
- `0x14001f71c`
- `0x14002001c`

## import_xrefs

- `FLTMGR!FltAcquireResourceExclusive` at `0x14000f0c1`
- `FLTMGR!FltAcquireResourceExclusive` at `0x14000f0c1`
- `FLTMGR!FltReleaseContext` at `0x14000f209`
- `FLTMGR!FltReleaseContext` at `0x14000f209`
- `FLTMGR!FltReleaseResource` at `0x14000f16a`
- `FLTMGR!FltReleaseResource` at `0x14000f1f5`
- `FLTMGR!FltReleaseResource` at `0x14000f16a`
- `FLTMGR!FltReleaseResource` at `0x14000f1f5`

## pseudocode

```c
__int64 __fastcall BfpGetInstanceTierNode(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        char a4,
        _QWORD *a5,
        _QWORD *a6,
        _QWORD *a7)
{
  int MappingContext; // eax
  int v9; // edx
  unsigned int v10; // r14d
  PFLT_CONTEXT v11; // rsi
  __int64 v12; // rdi
  int v13; // edx
  __int64 v14; // r8
  __int64 v15; // r9
  _QWORD *v16; // rbx
  int v17; // eax
  int v18; // r9d
  _QWORD *v19; // rax
  char v20; // dl
  char v22; // [rsp+30h] [rbp-30h]
  int v23; // [rsp+38h] [rbp-28h]
  PFLT_CONTEXT Context; // [rsp+40h] [rbp-20h] BYREF
  _QWORD *v25; // [rsp+48h] [rbp-18h] BYREF
  __int64 v26; // [rsp+50h] [rbp-10h] BYREF

  Context = 0;
  v26 = 0;
  v25 = 0;
  MappingContext = BfpGetMappingContext(0, a1, a2, a3, &Context, &v26);
  v10 = MappingContext;
  if ( MappingContext < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = 2;
      WPP_RECORDER_SF_sDd(
        WPP_GLOBAL_Control->DeviceExtension,
        v9,
        6,
        141,
        (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
        96,
        MappingContext);
    }
    v11 = Context;
    goto LABEL_26;
  }
  v12 = v26;
  FltAcquireResourceExclusive((PERESOURCE)(v26 + 16));
  v16 = *(_QWORD **)v12;
  v11 = Context;
  while ( v16 != (_QWORD *)v12 )
  {
    if ( *(_QWORD *)v16[2] == *(_QWORD *)Context )
      goto LABEL_16;
    v16 = (_QWORD *)*v16;
    v25 = 0;
  }
  if ( !a4 )
  {
    v10 = -1073741275;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v23 = -1073741275;
      v18 = 143;
      v22 = -122;
      goto LABEL_24;
    }
LABEL_25:
    FltReleaseResource((PERESOURCE)(v12 + 16));
    goto LABEL_26;
  }
  v17 = BfpCreateInstanceTierNode(Context, &v25, v14, v15);
  v10 = v17;
  if ( v17 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v23 = v17;
      v18 = 142;
      v22 = 121;
LABEL_24:
      LOBYTE(v13) = 2;
      WPP_RECORDER_SF_sDd(
        WPP_GLOBAL_Control->DeviceExtension,
        v13,
        6,
        v18,
        (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
        v22,
        v23);
      goto LABEL_25;
    }
    goto LABEL_25;
  }
  v19 = *(_QWORD **)(v12 + 8);
  if ( *v19 != v12 )
    __fastfail(3u);
  v16 = v25;
  *v25 = v12;
  v16[1] = v19;
  *v19 = v16;
  *(_QWORD *)(v12 + 8) = v16;
LABEL_16:
  v20 = 1;
  if ( a6 )
  {
    FltReleaseResource((PERESOURCE)(v12 + 16));
    v20 = 0;
    *a6 = v12;
    v12 = 0;
  }
  if ( a5 )
  {
    *a5 = v11;
    v11 = 0;
  }
  *a7 = v16;
  if ( v20 )
    goto LABEL_25;
LABEL_26:
  if ( v11 )
    FltReleaseContext(v11);
  return v10;
}

```

## disassembly

```asm
0x14000f008  push    rbp
0x14000f00a  push    rbx
0x14000f00b  push    rsi
0x14000f00c  push    rdi
0x14000f00d  push    r12
0x14000f00f  push    r14
0x14000f011  push    r15
0x14000f013  mov     rbp, rsp
0x14000f016  sub     rsp, 60h
0x14000f01a  mov     r15b, r9b
0x14000f01d  mov     [rbp+Context], 0
0x14000f025  lea     rax, [rbp+var_10]
0x14000f029  mov     [rbp+var_10], 0
0x14000f031  mov     [rsp+60h+var_38], rax
0x14000f036  mov     r9, r8
0x14000f039  mov     r8, rdx
0x14000f03c  mov     [rbp+var_18], 0
0x14000f044  lea     rax, [rbp+Context]
0x14000f048  mov     rdx, rcx
0x14000f04b  xor     ecx, ecx
0x14000f04d  mov     [rsp+60h+var_40], rax
0x14000f052  call    BfpGetMappingContext
0x14000f057  mov     r14d, eax
0x14000f05a  test    eax, eax
0x14000f05c  jns     short loc_14000F0B9
0x14000f05e  lea     rcx, WPP_RECORDER_INITIALIZED
0x14000f065  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14000f06c  jz      short loc_14000F0B0
0x14000f06e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f075  mov     r9d, 8Dh
0x14000f07b  mov     [rsp+60h+var_28], eax
0x14000f07f  mov     r8d, 6
0x14000f085  lea     rax, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x14000f08c  mov     dword ptr [rsp+60h+var_30], 1460h
0x14000f094  mov     [rsp+60h+var_38], rax
0x14000f099  mov     dl, 2
0x14000f09b  mov     rcx, [rcx+40h]
0x14000f09f  lea     rax, WPP_55845795197b3ed810b516bf1e89ed04_Traceguids
0x14000f0a6  mov     [rsp+60h+var_40], rax
0x14000f0ab  call    WPP_RECORDER_SF_sDd
0x14000f0b0  mov     rsi, [rbp+Context]
0x14000f0b4  jmp     loc_14000F201
0x14000f0b9  mov     rdi, [rbp+var_10]
0x14000f0bd  lea     rcx, [rdi+10h]; Resource
0x14000f0c1  call    cs:__imp_FltAcquireResourceExclusive
0x14000f0c8  nop     dword ptr [rax+rax+00h]
0x14000f0cd  mov     rbx, [rdi]
0x14000f0d0  mov     rsi, [rbp+Context]
0x14000f0d4  cmp     rbx, rdi
0x14000f0d7  jz      short loc_14000F0F2
0x14000f0d9  mov     rcx, [rbx+10h]
0x14000f0dd  mov     rax, [rsi]
0x14000f0e0  cmp     [rcx], rax
0x14000f0e3  jz      short loc_14000F15B
0x14000f0e5  mov     rbx, [rbx]
0x14000f0e8  mov     [rbp+var_18], 0
0x14000f0f0  jmp     short loc_14000F0D4
0x14000f0f2  test    r15b, r15b
0x14000f0f5  jz      loc_14000F198
0x14000f0fb  lea     rdx, [rbp+var_18]
0x14000f0ff  mov     rcx, rsi; Context
0x14000f102  call    BfpCreateInstanceTierNode
0x14000f107  mov     r14d, eax
0x14000f10a  test    eax, eax
0x14000f10c  jns     short loc_14000F139
0x14000f10e  lea     rcx, WPP_RECORDER_INITIALIZED
0x14000f115  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14000f11c  jz      loc_14000F1F1
0x14000f122  mov     [rsp+60h+var_28], eax
0x14000f126  mov     r9d, 8Eh
0x14000f12c  mov     dword ptr [rsp+60h+var_30], 1479h
0x14000f134  jmp     loc_14000F1C1
0x14000f139  mov     rax, [rdi+8]
0x14000f13d  cmp     [rax], rdi
0x14000f140  jz      short loc_14000F149
0x14000f142  mov     ecx, 3
0x14000f147  int     29h; Win8: RtlFailFast(ecx)
0x14000f149  mov     rbx, [rbp+var_18]
0x14000f14d  mov     [rbx], rdi
0x14000f150  mov     [rbx+8], rax
0x14000f154  mov     [rax], rbx
0x14000f157  mov     [rdi+8], rbx
0x14000f15b  mov     r15, [rbp+arg_28]
0x14000f15f  mov     dl, 1
0x14000f161  test    r15, r15
0x14000f164  jz      short loc_14000F17D
0x14000f166  lea     rcx, [rdi+10h]; Resource
0x14000f16a  call    cs:__imp_FltReleaseResource
0x14000f171  nop     dword ptr [rax+rax+00h]
0x14000f176  xor     dl, dl
0x14000f178  mov     [r15], rdi
0x14000f17b  xor     edi, edi
0x14000f17d  mov     rax, [rbp+arg_20]
0x14000f181  test    rax, rax
0x14000f184  jz      short loc_14000F18B
0x14000f186  mov     [rax], rsi
0x14000f189  xor     esi, esi
0x14000f18b  mov     rax, [rbp+arg_30]
0x14000f18f  mov     [rax], rbx
0x14000f192  test    dl, dl
0x14000f194  jnz     short loc_14000F1F1
0x14000f196  jmp     short loc_14000F201
0x14000f198  mov     r14d, 0C0000225h
0x14000f19e  lea     rcx, WPP_RECORDER_INITIALIZED
0x14000f1a5  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14000f1ac  jz      short loc_14000F1F1
0x14000f1ae  mov     [rsp+60h+var_28], r14d
0x14000f1b3  mov     r9d, 8Fh
0x14000f1b9  mov     dword ptr [rsp+60h+var_30], 1486h
0x14000f1c1  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f1c8  lea     rax, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x14000f1cf  mov     [rsp+60h+var_38], rax
0x14000f1d4  mov     r8d, 6
0x14000f1da  lea     rax, WPP_55845795197b3ed810b516bf1e89ed04_Traceguids
0x14000f1e1  mov     dl, 2
0x14000f1e3  mov     [rsp+60h+var_40], rax
0x14000f1e8  mov     rcx, [rcx+40h]
0x14000f1ec  call    WPP_RECORDER_SF_sDd
0x14000f1f1  lea     rcx, [rdi+10h]; Resource
0x14000f1f5  call    cs:__imp_FltReleaseResource
0x14000f1fc  nop     dword ptr [rax+rax+00h]
0x14000f201  test    rsi, rsi
0x14000f204  jz      short loc_14000F215
0x14000f206  mov     rcx, rsi; Context
0x14000f209  call    cs:__imp_FltReleaseContext
0x14000f210  nop     dword ptr [rax+rax+00h]
0x14000f215  mov     eax, r14d
0x14000f218  add     rsp, 60h
0x14000f21c  pop     r15
0x14000f21e  pop     r14
0x14000f220  pop     r12
0x14000f222  pop     rdi
0x14000f223  pop     rsi
0x14000f224  pop     rbx
0x14000f225  pop     rbp
0x14000f226  retn
```
