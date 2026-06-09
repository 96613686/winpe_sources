# _write_internal

- ea: `0x14000bea8`
- end: `0x14000bfc5`
- name: `_write_internal`
- size: `285`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14000a0d0`

## callees

- `0x14000648c`
- `0x140008468`
- `0x140008490`
- `0x14000bea8`
- `0x14000bfc8`

## pseudocode

```c
__int64 __fastcall write_internal(int a1, _BYTE *a2, unsigned int a3, __int64 a4)
{
  BOOL v8; // eax
  __int64 v9; // r15
  unsigned int v10; // r14d

  if ( a1 == -2 )
  {
    *(_BYTE *)(a4 + 56) = 1;
    *(_DWORD *)(a4 + 52) = 0;
    *(_BYTE *)(a4 + 48) = 1;
    *(_DWORD *)(a4 + 44) = 9;
    return 0xFFFFFFFFLL;
  }
  v8 = a1 >= 0 && a1 < (unsigned int)dword_14001AB50;
  if ( !v8 || (v9 = (__int64)a1 >> 6, (*(_BYTE *)(qword_14001A750[v9] + 72LL * (a1 & 0x3F) + 56) & 1) == 0) )
  {
    *(_BYTE *)(a4 + 56) = 1;
    *(_DWORD *)(a4 + 52) = 0;
    *(_BYTE *)(a4 + 48) = 1;
    *(_DWORD *)(a4 + 44) = 9;
    sub_14000648C(0, 0, 0, 0, 0, (__crt_cached_ptd_host *)a4);
    return 0xFFFFFFFFLL;
  }
  sub_140008468((unsigned int)a1);
  v10 = -1;
  if ( (*(_BYTE *)(qword_14001A750[v9] + 72LL * (a1 & 0x3F) + 56) & 1) != 0 )
  {
    v10 = sub_14000BFC8(a1, a2, a3, a4);
  }
  else
  {
    *(_BYTE *)(a4 + 48) = 1;
    *(_DWORD *)(a4 + 44) = 9;
    *(_BYTE *)(a4 + 56) = 1;
    *(_DWORD *)(a4 + 52) = 0;
  }
  sub_140008490((unsigned int)a1);
  return v10;
}

```

## disassembly

```asm
0x14000bea8  mov     [rsp+arg_10], rbx
0x14000bead  mov     [rsp+arg_8], rdx
0x14000beb2  mov     [rsp+arg_0], ecx
0x14000beb6  push    rsi
0x14000beb7  push    r12
0x14000beb9  push    r13
0x14000bebb  push    r14
0x14000bebd  push    r15
0x14000bebf  sub     rsp, 30h
0x14000bec3  mov     rbx, r9
0x14000bec6  mov     r13d, r8d
0x14000bec9  movsxd  rsi, ecx
0x14000becc  cmp     esi, 0FFFFFFFEh
0x14000becf  jnz     short loc_14000BEFE
0x14000bed1  mov     byte ptr [r9+38h], 1
0x14000bed6  and     dword ptr [r9+34h], 0
0x14000bedb  mov     byte ptr [r9+30h], 1
0x14000bee0  mov     dword ptr [r9+2Ch], 9
0x14000bee8  or      eax, 0FFFFFFFFh
0x14000beeb  mov     rbx, [rsp+58h+arg_10]
0x14000bef0  add     rsp, 30h
0x14000bef4  pop     r15
0x14000bef6  pop     r14
0x14000bef8  pop     r13
0x14000befa  pop     r12
0x14000befc  pop     rsi
0x14000befd  retn
0x14000befe  test    ecx, ecx
0x14000bf00  js      short loc_14000BF11
0x14000bf02  cmp     esi, cs:dword_14001AB50
0x14000bf08  jnb     short loc_14000BF11
0x14000bf0a  mov     eax, 1
0x14000bf0f  jmp     short loc_14000BF13
0x14000bf11  xor     eax, eax
0x14000bf13  test    eax, eax
0x14000bf15  jnz     short loc_14000BF4A
0x14000bf17  mov     byte ptr [r9+38h], 1
0x14000bf1c  and     dword ptr [r9+34h], 0
0x14000bf21  mov     byte ptr [r9+30h], 1
0x14000bf26  mov     dword ptr [r9+2Ch], 9
0x14000bf2e  mov     [rsp+58h+var_30], rbx; __crt_cached_ptd_host *
0x14000bf33  and     [rsp+58h+var_38], 0
0x14000bf39  xor     r9d, r9d; LineNo
0x14000bf3c  xor     r8d, r8d; FileName
0x14000bf3f  xor     edx, edx; FunctionName
0x14000bf41  xor     ecx, ecx; Expression
0x14000bf43  call    sub_14000648C
0x14000bf48  jmp     short loc_14000BEE8
0x14000bf4a  mov     rax, rsi
0x14000bf4d  mov     r15, rsi
0x14000bf50  sar     r15, 6
0x14000bf54  lea     rcx, qword_14001A750
0x14000bf5b  and     eax, 3Fh
0x14000bf5e  lea     r12, [rax+rax*8]
0x14000bf62  mov     rax, [rcx+r15*8]
0x14000bf66  test    byte ptr [rax+r12*8+38h], 1
0x14000bf6c  jz      short loc_14000BF17
0x14000bf6e  mov     ecx, esi
0x14000bf70  call    sub_140008468
0x14000bf75  or      r14d, 0FFFFFFFFh
0x14000bf79  lea     rax, qword_14001A750
0x14000bf80  mov     rax, [rax+r15*8]
0x14000bf84  test    byte ptr [rax+r12*8+38h], 1
0x14000bf8a  jnz     short loc_14000BFA1
0x14000bf8c  mov     byte ptr [rbx+30h], 1
0x14000bf90  mov     dword ptr [rbx+2Ch], 9
0x14000bf97  mov     byte ptr [rbx+38h], 1
0x14000bf9b  and     dword ptr [rbx+34h], 0
0x14000bf9f  jmp     short loc_14000BFB6
0x14000bfa1  mov     r9, rbx
0x14000bfa4  mov     r8d, r13d
0x14000bfa7  mov     rdx, [rsp+58h+arg_8]
0x14000bfac  mov     ecx, esi
0x14000bfae  call    sub_14000BFC8
0x14000bfb3  mov     r14d, eax
0x14000bfb6  mov     ecx, esi
0x14000bfb8  call    sub_140008490
0x14000bfbd  mov     eax, r14d
0x14000bfc0  jmp     loc_14000BEEB
0x14000e01f  push    rbp; Microsoft VisualC 64bit universal runtime
0x14000e021  sub     rsp, 30h
0x14000e025  mov     rbp, rdx
0x14000e028  mov     ecx, [rbp+60h]
0x14000e02b  add     rsp, 30h
0x14000e02f  pop     rbp
0x14000e030  jmp     sub_140008490
```
