# CreatePrintConfigData(void *,PrintConfigData * *)

- ea: `0x180035a2c`
- end: `0x180035ad9`
- name: `?CreatePrintConfigData@@YAJPEAXPEAPEAVPrintConfigData@@@Z`
- size: `173`
- prototype: `__int64 __fastcall(void *, struct PrintConfigData **)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x180035170`
- `0x1800351e4`

## callees

- `0x1800024d8`
- `0x180035968`
- `0x180035a2c`
- `0x180035ae0`
- `0x18003791c`
- `0x180038118`

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
0x180035a2c  push    rbp
0x180035a2e  push    rbx
0x180035a2f  push    rsi
0x180035a30  push    rdi
0x180035a31  mov     rbp, rsp
0x180035a34  sub     rsp, 58h
0x180035a38  mov     rsi, rdx
0x180035a3b  mov     [rbp+var_18], 0
0x180035a3f  xorps   xmm0, xmm0
0x180035a42  lea     rdx, [rbp+Block]; struct _DRIVER_INFO_3W **
0x180035a46  xorps   xmm1, xmm1
0x180035a49  mov     rdi, rcx
0x180035a4c  movdqu  xmmword ptr [rbp+Block], xmm0
0x180035a51  movdqu  xmmword ptr [rbp+var_28], xmm1
0x180035a56  call    ?PopulatePrintConfigDataContext@PrintConfigDataContext@@SAJPEAXAEAV1@@Z; PrintConfigDataContext::PopulatePrintConfigDataContext(void *,PrintConfigDataContext &)
0x180035a5b  mov     byte ptr [rbp+arg_10], 1
0x180035a5f  mov     ebx, eax
0x180035a61  test    eax, eax
0x180035a63  js      short loc_180035AA9
0x180035a65  lea     r8, [rbp+arg_10]; bool *
0x180035a69  mov     rcx, rdi; void *
0x180035a6c  lea     rdx, [rbp+Block]; struct PrintConfigDataContext *
0x180035a70  call    ?UseLocalConfigData@@YAJPEAXAEAVPrintConfigDataContext@@PEA_N@Z; UseLocalConfigData(void *,PrintConfigDataContext &,bool *)
0x180035a75  mov     ebx, eax
0x180035a77  test    eax, eax
0x180035a79  js      short loc_180035AA9
0x180035a7b  cmp     byte ptr [rbp+arg_10], 0
0x180035a7f  lea     r8, [rbp+arg_10]; struct RemotePrintConfigData **
0x180035a83  mov     [rbp+arg_10], 0
0x180035a8b  lea     rdx, [rbp+Block]; struct PrintConfigDataContext *
0x180035a8f  mov     rcx, rdi; void *
0x180035a92  jz      short loc_180035A9B
0x180035a94  call    ?CreateLocalPrintConfigData@LocalPrintConfigData@@SAJPEAXAEAVPrintConfigDataContext@@PEAPEAV1@@Z; LocalPrintConfigData::CreateLocalPrintConfigData(void *,PrintConfigDataContext &,LocalPrintConfigData * *)
0x180035a99  jmp     short loc_180035AA0
0x180035a9b  call    ?CreateRemotePrintConfigData@RemotePrintConfigData@@SAJPEAXAEAVPrintConfigDataContext@@PEAPEAV1@@Z; RemotePrintConfigData::CreateRemotePrintConfigData(void *,PrintConfigDataContext &,RemotePrintConfigData * *)
0x180035aa0  mov     ebx, eax
0x180035aa2  mov     rax, [rbp+arg_10]
0x180035aa6  mov     [rsi], rax
0x180035aa9  mov     rcx, [rbp+Block]; Block
0x180035aad  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180035ab2  mov     rcx, [rbp+Block+8]; Block
0x180035ab6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180035abb  mov     rcx, [rbp+var_28]; Block
0x180035abf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180035ac4  mov     rcx, [rbp+var_28+8]; Block
0x180035ac8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180035acd  mov     eax, ebx
0x180035acf  add     rsp, 58h
0x180035ad3  pop     rdi
0x180035ad4  pop     rsi
0x180035ad5  pop     rbx
0x180035ad6  pop     rbp
0x180035ad7  retn
```
