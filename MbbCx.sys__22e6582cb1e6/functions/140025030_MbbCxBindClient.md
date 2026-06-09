# MbbCxBindClient

- ea: `0x140025030`
- end: `0x140025187`
- name: `MbbCxBindClient`
- size: `343`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140025030`
- `0x1400254b8`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x140025075`
- `ntoskrnl!DbgPrintEx` at `0x140025098`
- `ntoskrnl!DbgPrintEx` at `0x140025075`
- `ntoskrnl!DbgPrintEx` at `0x140025098`
- `ntoskrnl!ExAllocatePool2` at `0x140025119`
- `ntoskrnl!ExAllocatePool2` at `0x140025119`

## string_xrefs

- `0x140025069`: `\n\n************************* \n* MbbCx detected a function count mismatch. The driver \n* using this extension will not load until it is re-compiled \n* with the latest version of the extension's header and libs \n`

## pseudocode

```c
__int64 __fastcall MbbCxBindClient(__int64 a1, __int64 a2)
{
  __int64 v5; // rax
  _QWORD *Pool2; // rax
  int v7; // edx
  int v8; // r8d

  if ( (*(unsigned int *)(a1 + 20) | ((unsigned __int64)*(unsigned int *)(a1 + 16) << 16)) != 0x10000 )
    return 3221225659LL;
  if ( *(_DWORD *)(a1 + 40) == 15 )
  {
    v5 = *(_QWORD *)(a1 + 32);
    *(_OWORD *)v5 = *(_OWORD *)&off_14005DEA8;
    *(_OWORD *)(v5 + 16) = *(_OWORD *)off_14005DEB8;
    *(_OWORD *)(v5 + 32) = *(_OWORD *)&off_14005DEC8;
    *(_OWORD *)(v5 + 48) = *(_OWORD *)&off_14005DED8;
    *(_OWORD *)(v5 + 64) = *(_OWORD *)off_14005DEE8;
    *(_OWORD *)(v5 + 80) = *(_OWORD *)&off_14005DEF8;
    *(_OWORD *)(v5 + 96) = *(_OWORD *)&off_14005DF08;
    *(_QWORD *)(v5 + 112) = off_14005DF18;
    Pool2 = (_QWORD *)ExAllocatePool2(64, 16, 1683505741);
    if ( Pool2 )
    {
      *Pool2 = 2019708231;
      Pool2[1] = a2;
      **(_QWORD **)(a1 + 48) = (char *)Pool2 + 4;
      return 0;
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_s(WPP_GLOBAL_Control->DeviceExtension, v7, v8, 22);
      return 3221225626LL;
    }
  }
  else
  {
    DbgPrintEx(
      0x65u,
      0,
      "\n"
      "\n"
      "************************* \n"
      "* MbbCx detected a function count mismatch. The driver \n"
      "* using this extension will not load until it is re-compiled \n"
      "* with the latest version of the extension's header and libs \n");
    DbgPrintEx(
      0x65u,
      0,
      "* Actual function table count  : %u \n* Expected function table count: %u \n*************************** \n\n",
      *(_DWORD *)(a1 + 40),
      15);
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x140025030  mov     [rsp+arg_0], rbx
0x140025035  push    rdi
0x140025036  sub     rsp, 30h
0x14002503a  mov     r8d, [rcx+10h]
0x14002503e  mov     rdi, rdx
0x140025041  mov     eax, [rcx+14h]
0x140025044  mov     rbx, rcx
0x140025047  shl     r8, 10h
0x14002504b  or      r8, rax
0x14002504e  cmp     r8, 10000h
0x140025055  jz      short loc_140025061
0x140025057  mov     eax, 0C00000BBh
0x14002505c  jmp     loc_14002517B
0x140025061  cmp     dword ptr [rcx+28h], 0Fh
0x140025065  jz      short loc_1400250AE
0x140025067  xor     edx, edx; Level
0x140025069  lea     r8, Format; "\n\n************************* \n* MbbCx"...
0x140025070  lea     edi, [rdx+65h]
0x140025073  mov     ecx, edi; ComponentId
0x140025075  call    cs:__imp_DbgPrintEx
0x14002507c  nop     dword ptr [rax+rax+00h]
0x140025081  mov     r9d, [rbx+28h]
0x140025085  lea     r8, aActualFunction; "* Actual function table count  : %u \n*"...
0x14002508c  xor     edx, edx; Level
0x14002508e  mov     [rsp+38h+var_18], 0Fh
0x140025096  mov     ecx, edi; ComponentId
0x140025098  call    cs:__imp_DbgPrintEx
0x14002509f  nop     dword ptr [rax+rax+00h]
0x1400250a4  mov     eax, 0C000000Dh
0x1400250a9  jmp     loc_14002517B
0x1400250ae  mov     rax, [rcx+20h]
0x1400250b2  mov     edx, 10h
0x1400250b7  movups  xmm0, xmmword ptr cs:off_14005DEA8
0x1400250be  mov     r8d, 6458424Dh
0x1400250c4  movups  xmmword ptr [rax], xmm0
0x1400250c7  lea     ecx, [rdx+30h]
0x1400250ca  movups  xmm1, xmmword ptr cs:off_14005DEB8
0x1400250d1  movups  xmmword ptr [rax+10h], xmm1
0x1400250d5  movups  xmm0, xmmword ptr cs:off_14005DEC8
0x1400250dc  movups  xmmword ptr [rax+20h], xmm0
0x1400250e0  movups  xmm1, xmmword ptr cs:off_14005DED8
0x1400250e7  movups  xmmword ptr [rax+30h], xmm1
0x1400250eb  movups  xmm0, xmmword ptr cs:off_14005DEE8
0x1400250f2  movups  xmmword ptr [rax+40h], xmm0
0x1400250f6  movups  xmm1, xmmword ptr cs:off_14005DEF8
0x1400250fd  movups  xmmword ptr [rax+50h], xmm1
0x140025101  movups  xmm0, xmmword ptr cs:off_14005DF08
0x140025108  movups  xmmword ptr [rax+60h], xmm0
0x14002510c  movsd   xmm1, cs:off_14005DF18
0x140025114  movsd   qword ptr [rax+70h], xmm1
0x140025119  call    cs:__imp_ExAllocatePool2
0x140025120  nop     dword ptr [rax+rax+00h]
0x140025125  test    rax, rax
0x140025128  jnz     short loc_140025163
0x14002512a  lea     rax, WPP_RECORDER_INITIALIZED
0x140025131  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140025138  jz      short loc_14002515C
0x14002513a  mov     rcx, cs:WPP_GLOBAL_Control
0x140025141  lea     rax, aPrivateglobals; "privateGlobals"
0x140025148  mov     r9d, 16h
0x14002514e  mov     [rsp+38h+var_10], rax
0x140025153  mov     rcx, [rcx+40h]
0x140025157  call    WPP_RECORDER_SF_s
0x14002515c  mov     eax, 0C000009Ah
0x140025161  jmp     short loc_14002517B
0x140025163  mov     qword ptr [rax], 78624D47h
0x14002516a  lea     rcx, [rax+4]
0x14002516e  mov     [rax+8], rdi
0x140025172  mov     rax, [rbx+30h]
0x140025176  mov     [rax], rcx
0x140025179  xor     eax, eax
0x14002517b  mov     rbx, [rsp+38h+arg_0]
0x140025180  add     rsp, 30h
0x140025184  pop     rdi
0x140025185  retn
```
