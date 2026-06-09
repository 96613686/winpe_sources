# ComputeFlushPeriod

- ea: `0x180019aac`
- end: `0x180019b39`
- name: `ComputeFlushPeriod`
- size: `141`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180010bcc`

## callees

- `0x18000ba60`

## pseudocode

```c
__int64 __fastcall ComputeFlushPeriod(unsigned __int64 a1, int a2)
{
  __int64 v2; // rax
  __int128 v4; // [rsp+20h] [rbp-18h] BYREF
  unsigned __int64 v5; // [rsp+40h] [rbp+8h] BYREF
  int v6; // [rsp+48h] [rbp+10h] BYREF

  v6 = a2;
  v2 = *(_QWORD *)(a1 + 328);
  v5 = a1 >> 4;
  v6 = 0;
  v4 = *(_OWORD *)(*(_QWORD *)(v2 + 8) - 16LL);
  RunningHash(&v6, &v4, 16);
  RunningHash(&v6, &v5, 8);
  return 32769 * ((9 * v6) ^ ((unsigned int)(9 * v6) >> 11)) % 0x927C0 + 600000;
}

```

## disassembly

```asm
0x180019aac  mov     [rsp+arg_8], edx
0x180019ab0  sub     rsp, 38h
0x180019ab4  mov     rax, [rcx+148h]
0x180019abb  mov     r8d, 10h
0x180019ac1  shr     rcx, 4
0x180019ac5  mov     [rsp+38h+arg_0], rcx
0x180019aca  lea     rcx, [rsp+38h+arg_8]
0x180019acf  mov     [rsp+38h+arg_8], 0
0x180019ad7  mov     rdx, [rax+8]
0x180019adb  movups  xmm0, xmmword ptr [rdx-10h]
0x180019adf  lea     rdx, [rsp+38h+var_18]
0x180019ae4  movdqu  [rsp+38h+var_18], xmm0
0x180019aea  call    RunningHash
0x180019aef  lea     rdx, [rsp+38h+arg_0]
0x180019af4  mov     r8d, 8
0x180019afa  lea     rcx, [rsp+38h+arg_8]
0x180019aff  call    RunningHash
0x180019b04  mov     ecx, [rsp+38h+arg_8]
0x180019b08  lea     eax, [rcx+rcx*8]
0x180019b0b  mov     ecx, eax
0x180019b0d  shr     ecx, 0Bh
0x180019b10  xor     ecx, eax
0x180019b12  mov     eax, 6FD91D85h
0x180019b17  imul    r8d, ecx, 8001h
0x180019b1e  mul     r8d
0x180019b21  shr     edx, 12h
0x180019b24  imul    ecx, edx, 927C0h
0x180019b2a  sub     r8d, ecx
0x180019b2d  lea     eax, [r8+927C0h]
0x180019b34  add     rsp, 38h
0x180019b38  retn
```
