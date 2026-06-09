# CreatePrintConfigData(void *,PrintConfigData * *)

- ea: `0x18003431c`
- end: `0x1800343c8`
- name: `?CreatePrintConfigData@@YAJPEAXPEAPEAVPrintConfigData@@@Z`
- size: `172`
- prototype: `__int64 __fastcall(void *, struct PrintConfigData **)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x180033a90`
- `0x180033b00`

## callees

- `0x180002498`
- `0x180034258`
- `0x18003431c`
- `0x1800343d0`
- `0x180036118`
- `0x1800368b8`

## pseudocode

```c
__int64 __fastcall CreatePrintConfigData(void *a1, struct PrintConfigData **a2)
{
  int v4; // eax
  int v5; // ebx
  bool v6; // zf
  int v7; // eax
  void *Block[2]; // [rsp+20h] [rbp-38h] BYREF
  void *v10[2]; // [rsp+30h] [rbp-28h]
  char v11; // [rsp+40h] [rbp-18h]
  struct RemotePrintConfigData *v12; // [rsp+90h] [rbp+38h] BYREF

  v11 = 0;
  *(_OWORD *)Block = 0;
  *(_OWORD *)v10 = 0;
  v4 = PrintConfigDataContext::PopulatePrintConfigDataContext(a1, (struct _DRIVER_INFO_3W **)Block);
  LOBYTE(v12) = 1;
  v5 = v4;
  if ( v4 >= 0 )
  {
    v5 = UseLocalConfigData(a1, (struct PrintConfigDataContext *)Block, (bool *)&v12);
    if ( v5 >= 0 )
    {
      v6 = (_BYTE)v12 == 0;
      v12 = 0;
      if ( v6 )
        v7 = RemotePrintConfigData::CreateRemotePrintConfigData(a1, (struct PrintConfigDataContext *)Block, &v12);
      else
        v7 = LocalPrintConfigData::CreateLocalPrintConfigData(a1, (struct PrintConfigDataContext *)Block, &v12);
      v5 = v7;
      *a2 = v12;
    }
  }
  operator delete(Block[0]);
  operator delete(Block[1]);
  operator delete(v10[0]);
  operator delete(v10[1]);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18003431c  push    rbp
0x18003431e  push    rbx
0x18003431f  push    rsi
0x180034320  push    rdi
0x180034321  mov     rbp, rsp
0x180034324  sub     rsp, 58h
0x180034328  mov     rsi, rdx
0x18003432b  mov     [rbp+var_18], 0
0x18003432f  xorps   xmm0, xmm0
0x180034332  lea     rdx, [rbp+Block]; struct _DRIVER_INFO_3W **
0x180034336  xorps   xmm1, xmm1
0x180034339  mov     rdi, rcx
0x18003433c  movdqu  xmmword ptr [rbp+Block], xmm0
0x180034341  movdqu  xmmword ptr [rbp+var_28], xmm1
0x180034346  call    ?PopulatePrintConfigDataContext@PrintConfigDataContext@@SAJPEAXAEAV1@@Z; PrintConfigDataContext::PopulatePrintConfigDataContext(void *,PrintConfigDataContext &)
0x18003434b  mov     byte ptr [rbp+arg_10], 1
0x18003434f  mov     ebx, eax
0x180034351  test    eax, eax
0x180034353  js      short loc_180034399
0x180034355  lea     r8, [rbp+arg_10]; bool *
0x180034359  mov     rcx, rdi; void *
0x18003435c  lea     rdx, [rbp+Block]; struct PrintConfigDataContext *
0x180034360  call    ?UseLocalConfigData@@YAJPEAXAEAVPrintConfigDataContext@@PEA_N@Z; UseLocalConfigData(void *,PrintConfigDataContext &,bool *)
0x180034365  mov     ebx, eax
0x180034367  test    eax, eax
0x180034369  js      short loc_180034399
0x18003436b  cmp     byte ptr [rbp+arg_10], 0
0x18003436f  lea     r8, [rbp+arg_10]; struct RemotePrintConfigData **
0x180034373  mov     [rbp+arg_10], 0
0x18003437b  lea     rdx, [rbp+Block]; struct PrintConfigDataContext *
0x18003437f  mov     rcx, rdi; void *
0x180034382  jz      short loc_18003438B
0x180034384  call    ?CreateLocalPrintConfigData@LocalPrintConfigData@@SAJPEAXAEAVPrintConfigDataContext@@PEAPEAV1@@Z; LocalPrintConfigData::CreateLocalPrintConfigData(void *,PrintConfigDataContext &,LocalPrintConfigData * *)
0x180034389  jmp     short loc_180034390
0x18003438b  call    ?CreateRemotePrintConfigData@RemotePrintConfigData@@SAJPEAXAEAVPrintConfigDataContext@@PEAPEAV1@@Z; RemotePrintConfigData::CreateRemotePrintConfigData(void *,PrintConfigDataContext &,RemotePrintConfigData * *)
0x180034390  mov     ebx, eax
0x180034392  mov     rax, [rbp+arg_10]
0x180034396  mov     [rsi], rax
0x180034399  mov     rcx, [rbp+Block]; Block
0x18003439d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800343a2  mov     rcx, [rbp+Block+8]; Block
0x1800343a6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800343ab  mov     rcx, [rbp+var_28]; Block
0x1800343af  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800343b4  mov     rcx, [rbp+var_28+8]; Block
0x1800343b8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800343bd  mov     eax, ebx
0x1800343bf  add     rsp, 58h
0x1800343c3  pop     rdi
0x1800343c4  pop     rsi
0x1800343c5  pop     rbx
0x1800343c6  pop     rbp
0x1800343c7  retn
```
