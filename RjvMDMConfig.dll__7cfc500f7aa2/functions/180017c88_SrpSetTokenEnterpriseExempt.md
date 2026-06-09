# SrpSetTokenEnterpriseExempt

- ea: `0x180017c88`
- end: `0x180017cdd`
- name: `SrpSetTokenEnterpriseExempt`
- size: `85`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180014abc`
- `0x1800159cc`

## callees

- `0x180017b54`
- `0x180017bb0`
- `0x180017bcc`
- `0x180017c88`

## pseudocode

```c
__int64 __fastcall SrpSetTokenEnterpriseExempt(HANDLE TokenHandle, __int64 a2, __int64 a3)
{
  int v4; // edi
  int v5; // r8d
  int v6; // r9d
  __int64 v8; // [rsp+38h] [rbp+10h] BYREF

  v8 = 0;
  v4 = SrpCreateEnterpriseContext(TokenHandle, a2, a3, &v8);
  if ( v4 >= 0 )
    v4 = SrpSetEnterpriseContextToken(TokenHandle, v8, v5, v6);
  if ( v8 )
    SrpDeleteEnterpriseContext(v8);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180017c88  mov     [rsp+arg_0], rsi
0x180017c8d  push    rdi
0x180017c8e  sub     rsp, 20h
0x180017c92  lea     r9, [rsp+28h+arg_8]
0x180017c97  mov     [rsp+28h+arg_8], 0
0x180017ca0  mov     rsi, rcx
0x180017ca3  call    SrpCreateEnterpriseContext
0x180017ca8  mov     edi, eax
0x180017caa  test    eax, eax
0x180017cac  js      short loc_180017CBD
0x180017cae  mov     rdx, [rsp+28h+arg_8]
0x180017cb3  mov     rcx, rsi; TokenHandle
0x180017cb6  call    SrpSetEnterpriseContextToken
0x180017cbb  mov     edi, eax
0x180017cbd  cmp     [rsp+28h+arg_8], 0
0x180017cc3  jz      short loc_180017CCF
0x180017cc5  mov     rcx, [rsp+28h+arg_8]
0x180017cca  call    SrpDeleteEnterpriseContext
0x180017ccf  mov     rsi, [rsp+28h+arg_0]
0x180017cd4  mov     eax, edi
0x180017cd6  add     rsp, 20h
0x180017cda  pop     rdi
0x180017cdb  retn
```
