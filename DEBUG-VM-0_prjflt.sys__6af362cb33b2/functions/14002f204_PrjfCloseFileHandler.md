# PrjfCloseFileHandler

- ea: `0x14002f204`
- end: `0x14002f48d`
- name: `PrjfCloseFileHandler`
- size: `649`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140031a00`

## callees

- `0x140003e6c`
- `0x14000ba20`
- `0x14000d008`
- `0x140021f8c`
- `0x14002f204`

## import_xrefs

- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x14002f37c`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x14002f37c`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x14002f3b3`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x14002f3b3`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x14002f39d`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x14002f39d`
- `ntoskrnl!IoGetCurrentProcess` at `0x14002f2c6`
- `ntoskrnl!IoGetCurrentProcess` at `0x14002f2c6`
- `FLTMGR!FltClose` at `0x14002f3d1`
- `FLTMGR!FltClose` at `0x14002f3d1`
- `FLTMGR!FltAcquireResourceExclusive` at `0x14002f361`
- `FLTMGR!FltAcquireResourceExclusive` at `0x14002f361`
- `FLTMGR!FltReleaseResource` at `0x14002f3c2`
- `FLTMGR!FltReleaseResource` at `0x14002f452`
- `FLTMGR!FltReleaseResource` at `0x14002f3c2`
- `FLTMGR!FltReleaseResource` at `0x14002f452`

## pseudocode

```c
__int64 __fastcall PrjfCloseFileHandler(__int64 a1, __int64 a2)
{
  __int64 UnionContextByVirtualizationInstanceInfo; // rax
  int v4; // edx
  int v5; // r8d
  __int64 v6; // rdi
  unsigned int v7; // ebp
  struct _KPROCESS *v8; // rbx
  int v9; // edx
  int v10; // r8d
  PVOID v11; // rax
  int v12; // edx
  int v13; // r8d
  _QWORD *v14; // rsi
  void *v15; // rbx
  _OWORD Buffer[2]; // [rsp+58h] [rbp-50h] BYREF

  memset(Buffer, 0, sizeof(Buffer));
  UnionContextByVirtualizationInstanceInfo = PrjfGetUnionContextByVirtualizationInstanceInfo(a2, a1);
  v6 = UnionContextByVirtualizationInstanceInfo;
  if ( UnionContextByVirtualizationInstanceInfo )
  {
    v8 = *(struct _KPROCESS **)(UnionContextByVirtualizationInstanceInfo + 32);
    if ( IoGetCurrentProcess() == v8 )
    {
      Buffer[0] = *(_OWORD *)(a2 + 80);
      FltAcquireResourceExclusive((PERESOURCE)(v6 + 96));
      v11 = RtlLookupElementGenericTableAvl((PRTL_AVL_TABLE)(v6 + 200), Buffer);
      v14 = v11;
      if ( v11 && *((_QWORD *)v11 + 3) )
      {
        v7 = 0;
        ObDereferenceObjectDeferDelete(*((PVOID *)v11 + 2));
        v15 = (void *)v14[3];
        RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)(v6 + 200), v14);
        FltReleaseResource((PERESOURCE)(v6 + 96));
        FltClose(v15);
      }
      else
      {
        v7 = -1073741816;
        if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v12) = BYTE1(xmmword_14001A3D0) & 0x40;
          LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_sD(
            526,
            v12,
            v13,
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            2,
            14,
            43,
            (__int64)WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
            (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
            139);
        }
        FltReleaseResource((PERESOURCE)(v6 + 96));
      }
    }
    else
    {
      v7 = -1073741790;
      if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v9) = BYTE1(xmmword_14001A3D0) & 0x40;
        LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sD(
          526,
          v9,
          v10,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          14,
          42,
          (__int64)WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
          116);
      }
    }
    PrjfReleaseUnionContext((char *)v6);
  }
  else
  {
    v7 = -1073741811;
    if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v4) = BYTE1(xmmword_14001A3D0) & 0x40;
      LOBYTE(v5) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sD(
        526,
        v4,
        v5,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        14,
        41,
        (__int64)WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
        104);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x14002f204  mov     [rsp+arg_10], rbx
0x14002f209  push    rbp
0x14002f20a  push    rsi
0x14002f20b  push    rdi
0x14002f20c  push    r14
0x14002f20e  push    r15
0x14002f210  sub     rsp, 80h
0x14002f217  mov     rax, cs:__security_cookie
0x14002f21e  xor     rax, rsp
0x14002f221  mov     [rsp+0A8h+var_30], rax
0x14002f226  mov     rsi, rdx
0x14002f229  xorps   xmm0, xmm0
0x14002f22c  mov     rdx, rcx
0x14002f22f  mov     rcx, rsi
0x14002f232  movups  [rsp+0A8h+Buffer], xmm0
0x14002f237  movups  [rsp+0A8h+var_40], xmm0
0x14002f23c  call    PrjfGetUnionContextByVirtualizationInstanceInfo
0x14002f241  mov     rdi, rax
0x14002f244  test    rax, rax
0x14002f247  jnz     short loc_14002F2C2
0x14002f249  mov     ebp, 0C000000Dh
0x14002f24e  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14002f254  lea     rax, WPP_RECORDER_INITIALIZED
0x14002f25b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002f262  setnz   r8b
0x14002f266  and     dl, 40h
0x14002f269  jnz     short loc_14002F274
0x14002f26b  test    r8b, r8b
0x14002f26e  jz      loc_14002F466
0x14002f274  mov     r9, cs:WPP_GLOBAL_Control
0x14002f27b  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002f282  mov     [rsp+0A8h+var_60], 468h
0x14002f28a  mov     ecx, 20Eh
0x14002f28f  mov     [rsp+0A8h+var_68], rax
0x14002f294  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x14002f29b  mov     [rsp+0A8h+var_70], rax
0x14002f2a0  mov     r9, [r9+40h]
0x14002f2a4  mov     [rsp+0A8h+var_78], 29h ; ')'
0x14002f2ab  mov     [rsp+0A8h+var_80], 0Eh
0x14002f2b3  mov     [rsp+0A8h+var_88], 2
0x14002f2b8  call    WPP_RECORDER_AND_TRACE_SF_sD
0x14002f2bd  jmp     loc_14002F466
0x14002f2c2  mov     rbx, [rax+20h]
0x14002f2c6  call    cs:__imp_IoGetCurrentProcess
0x14002f2cd  nop     dword ptr [rax+rax+00h]
0x14002f2d2  cmp     rax, rbx
0x14002f2d5  jz      short loc_14002F350
0x14002f2d7  mov     ebp, 0C0000022h
0x14002f2dc  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14002f2e2  lea     rax, WPP_RECORDER_INITIALIZED
0x14002f2e9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002f2f0  setnz   r8b
0x14002f2f4  and     dl, 40h
0x14002f2f7  jnz     short loc_14002F302
0x14002f2f9  test    r8b, r8b
0x14002f2fc  jz      loc_14002F45E
0x14002f302  mov     r9, cs:WPP_GLOBAL_Control
0x14002f309  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002f310  mov     [rsp+0A8h+var_60], 474h
0x14002f318  mov     ecx, 20Eh
0x14002f31d  mov     [rsp+0A8h+var_68], rax
0x14002f322  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x14002f329  mov     [rsp+0A8h+var_70], rax
0x14002f32e  mov     r9, [r9+40h]
0x14002f332  mov     [rsp+0A8h+var_78], 2Ah ; '*'
0x14002f339  mov     [rsp+0A8h+var_80], 0Eh
0x14002f341  mov     [rsp+0A8h+var_88], 2
0x14002f346  call    WPP_RECORDER_AND_TRACE_SF_sD
0x14002f34b  jmp     loc_14002F45E
0x14002f350  movups  xmm0, xmmword ptr [rsi+50h]
0x14002f354  lea     r14, [rdi+60h]
0x14002f358  mov     rcx, r14; Resource
0x14002f35b  movdqu  [rsp+0A8h+Buffer], xmm0
0x14002f361  call    cs:__imp_FltAcquireResourceExclusive
0x14002f368  nop     dword ptr [rax+rax+00h]
0x14002f36d  lea     r15, [rdi+0C8h]
0x14002f374  mov     rcx, r15; Table
0x14002f377  lea     rdx, [rsp+0A8h+Buffer]; Buffer
0x14002f37c  call    cs:__imp_RtlLookupElementGenericTableAvl
0x14002f383  nop     dword ptr [rax+rax+00h]
0x14002f388  mov     rsi, rax
0x14002f38b  test    rax, rax
0x14002f38e  jz      short loc_14002F3DF
0x14002f390  cmp     qword ptr [rax+18h], 0
0x14002f395  jz      short loc_14002F3DF
0x14002f397  mov     rcx, [rax+10h]; Object
0x14002f39b  xor     ebp, ebp
0x14002f39d  call    cs:__imp_ObDereferenceObjectDeferDelete
0x14002f3a4  nop     dword ptr [rax+rax+00h]
0x14002f3a9  mov     rbx, [rsi+18h]
0x14002f3ad  mov     rdx, rsi; Buffer
0x14002f3b0  mov     rcx, r15; Table
0x14002f3b3  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x14002f3ba  nop     dword ptr [rax+rax+00h]
0x14002f3bf  mov     rcx, r14; Resource
0x14002f3c2  call    cs:__imp_FltReleaseResource
0x14002f3c9  nop     dword ptr [rax+rax+00h]
0x14002f3ce  mov     rcx, rbx; FileHandle
0x14002f3d1  call    cs:__imp_FltClose
0x14002f3d8  nop     dword ptr [rax+rax+00h]
0x14002f3dd  jmp     short loc_14002F45E
0x14002f3df  mov     ebp, 0C0000008h
0x14002f3e4  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14002f3ea  lea     rax, WPP_RECORDER_INITIALIZED
0x14002f3f1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002f3f8  setnz   r8b
0x14002f3fc  and     dl, 40h
0x14002f3ff  jnz     short loc_14002F406
0x14002f401  test    r8b, r8b
0x14002f404  jz      short loc_14002F44F
0x14002f406  mov     r9, cs:WPP_GLOBAL_Control
0x14002f40d  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002f414  mov     [rsp+0A8h+var_60], 48Bh
0x14002f41c  mov     ecx, 20Eh
0x14002f421  mov     [rsp+0A8h+var_68], rax
0x14002f426  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x14002f42d  mov     [rsp+0A8h+var_70], rax
0x14002f432  mov     r9, [r9+40h]
0x14002f436  mov     [rsp+0A8h+var_78], 2Bh ; '+'
0x14002f43d  mov     [rsp+0A8h+var_80], 0Eh
0x14002f445  mov     [rsp+0A8h+var_88], 2
0x14002f44a  call    WPP_RECORDER_AND_TRACE_SF_sD
0x14002f44f  mov     rcx, r14; Resource
0x14002f452  call    cs:__imp_FltReleaseResource
0x14002f459  nop     dword ptr [rax+rax+00h]
0x14002f45e  mov     rcx, rdi; P
0x14002f461  call    PrjfReleaseUnionContext
0x14002f466  mov     eax, ebp
0x14002f468  mov     rcx, [rsp+0A8h+var_30]
0x14002f46d  xor     rcx, rsp; StackCookie
0x14002f470  call    __security_check_cookie
0x14002f475  mov     rbx, [rsp+0A8h+arg_10]
0x14002f47d  add     rsp, 80h
0x14002f484  pop     r15
0x14002f486  pop     r14
0x14002f488  pop     rdi
0x14002f489  pop     rsi
0x14002f48a  pop     rbp
0x14002f48b  retn
```
