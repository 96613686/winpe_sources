# CLatchReader::CLatchReader(CReader *,CReader::ActiveState const *)

- ea: `0x180006700`
- end: `0x18000678e`
- name: `??0CLatchReader@@QEAA@PEAVCReader@@PEBUActiveState@1@@Z`
- size: `142`
- prototype: `CLatchReader *__fastcall(CLatchReader *this, struct CReader *, const struct CReader::ActiveState *)`
- caller_count: `15`
- callee_count: `5`
- tags: ``

## callers

- `0x180001950`
- `0x1800039e0`
- `0x180004c8c`
- `0x180005af0`
- `0x18000f2a0`
- `0x18000fcf0`
- `0x180018d4c`
- `0x18002c070`
- `0x18002d0c0`
- `0x18002d870`
- `0x18002dcc4`
- `0x18002f890`
- `0x18002fa94`
- `0x18002fcf0`
- `0x1800329ad`

## callees

- `0x180006700`
- `0x1800067a0`
- `0x180006ad0`
- `0x18000d190`
- `0x18000f800`

## pseudocode

```c
CLatchReader *__fastcall CLatchReader::CLatchReader(
        CLatchReader *this,
        struct CReader *a2,
        const struct CReader::ActiveState *a3)
{
  char v6; // di
  bool v10; // [rsp+60h] [rbp+18h] BYREF

  *((_DWORD *)this + 2) = 0;
  *((_BYTE *)this + 12) = a3 != 0;
  while ( 1 )
  {
    v10 = 0;
    *(_QWORD *)this = 0;
    v6 = *((_BYTE *)this + 12);
    CMutex::Grab((struct CReader *)((char *)a2 + 240));
    if ( v6 )
      CReader::TransactionTimeoutStart(a2);
    try
    {
      CReader::LatchReader(a2, a3, &v10);
      *(_QWORD *)this = a2;
    }
    catch ( ... )
    {
      CReader::ShareReader(a2, *((_BYTE *)this + 12));
      throw;
    }
    if ( v10 )
      break;
    ++*((_DWORD *)this + 2);
    CMutex::Share((struct CReader *)((char *)a2 + 328));
  }
  return this;
}

```

## disassembly

```asm
0x180006700  mov     [rsp+arg_8], rdx
0x180006705  mov     [rsp+arg_0], rcx
0x18000670a  push    rbx
0x18000670b  push    rsi
0x18000670c  push    rdi
0x18000670d  push    r14
0x18000670f  push    r15
0x180006711  sub     rsp, 20h
0x180006715  mov     r14, r8
0x180006718  mov     rsi, rdx
0x18000671b  mov     rbx, rcx
0x18000671e  xor     r15d, r15d
0x180006721  mov     [rcx+8], r15d
0x180006725  test    r8, r8
0x180006728  setnz   al
0x18000672b  mov     [rcx+0Ch], al
0x18000672e  mov     [rsp+48h+arg_10], 0
0x180006733  mov     [rbx], r15
0x180006736  movzx   edi, byte ptr [rbx+0Ch]
0x18000673a  lea     rcx, [rsi+0F0h]; this
0x180006741  call    ?Grab@CMutex@@QEAAXXZ; CMutex::Grab(void)
0x180006746  test    dil, dil
0x180006749  jz      short loc_180006754
0x18000674b  mov     rcx, rsi; this
0x18000674e  call    ?TransactionTimeoutStart@CReader@@IEAAXXZ; CReader::TransactionTimeoutStart(void)
0x180006753  nop
0x180006754  lea     r8, [rsp+48h+arg_10]; bool *
0x180006759  mov     rdx, r14; struct CReader::ActiveState *
0x18000675c  mov     rcx, rsi; this
0x18000675f  call    ?LatchReader@CReader@@QEAAXPEBUActiveState@1@PEA_N@Z; CReader::LatchReader(CReader::ActiveState const *,bool *)
0x180006764  mov     [rbx], rsi
0x180006767  cmp     [rsp+48h+arg_10], 0
0x18000676c  jz      short loc_18000677D
0x18000676e  mov     rax, rbx
0x180006771  add     rsp, 20h
0x180006775  pop     r15
0x180006777  pop     r14
0x180006779  pop     rdi
0x18000677a  pop     rsi
0x18000677b  pop     rbx
0x18000677c  retn
0x18000677d  inc     dword ptr [rbx+8]
0x180006780  lea     rcx, [rsi+148h]; this
0x180006787  call    ?Share@CMutex@@QEAAHXZ; CMutex::Share(void)
0x18000678c  jmp     short loc_18000672E
```
