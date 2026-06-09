# _write_internal

- ea: `0x140019aa8`
- end: `0x140019bc5`
- name: `_write_internal`
- size: `285`
- prototype: `__int64 __fastcall(unsigned int, __int64, unsigned int, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x140015aac`
- `0x140019a10`

## callees

- `0x140004614`
- `0x1400160ec`
- `0x1400161d4`
- `0x140019aa8`
- `0x140019bc8`

## pseudocode

```c
__int64 __fastcall write_internal(unsigned int a1, __int64 a2, unsigned int a3, __int64 a4)
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
  v8 = (a1 & 0x80000000) == 0 && a1 < dword_1400D6DC0;
  if ( !v8 || (v9 = (__int64)(int)a1 >> 6, (*(_BYTE *)(qword_1400D69C0[v9] + 72LL * (a1 & 0x3F) + 56) & 1) == 0) )
  {
    *(_BYTE *)(a4 + 56) = 1;
    *(_DWORD *)(a4 + 52) = 0;
    *(_BYTE *)(a4 + 48) = 1;
    *(_DWORD *)(a4 + 44) = 9;
    sub_140004614(0, 0, 0, 0, 0, (__crt_cached_ptd_host *)a4);
    return 0xFFFFFFFFLL;
  }
  sub_1400160EC(a1);
  v10 = -1;
  if ( (*(_BYTE *)(qword_1400D69C0[v9] + 72LL * (a1 & 0x3F) + 56) & 1) != 0 )
  {
    v10 = sub_140019BC8(a1, a2, a3, a4);
  }
  else
  {
    *(_BYTE *)(a4 + 48) = 1;
    *(_DWORD *)(a4 + 44) = 9;
    *(_BYTE *)(a4 + 56) = 1;
    *(_DWORD *)(a4 + 52) = 0;
  }
  sub_1400161D4(a1);
  return v10;
}

```

## disassembly

```asm
0x140019aa8  mov     [rsp+arg_10], rbx
0x140019aad  mov     [rsp+arg_8], rdx
0x140019ab2  mov     [rsp+arg_0], ecx
0x140019ab6  push    rsi
0x140019ab7  push    r12
0x140019ab9  push    r13
0x140019abb  push    r14
0x140019abd  push    r15
0x140019abf  sub     rsp, 30h
0x140019ac3  mov     rbx, r9
0x140019ac6  mov     r13d, r8d
0x140019ac9  movsxd  rsi, ecx
0x140019acc  cmp     esi, 0FFFFFFFEh
0x140019acf  jnz     short loc_140019AFE
0x140019ad1  mov     byte ptr [r9+38h], 1
0x140019ad6  and     dword ptr [r9+34h], 0
0x140019adb  mov     byte ptr [r9+30h], 1
0x140019ae0  mov     dword ptr [r9+2Ch], 9
0x140019ae8  or      eax, 0FFFFFFFFh
0x140019aeb  mov     rbx, [rsp+58h+arg_10]
0x140019af0  add     rsp, 30h
0x140019af4  pop     r15
0x140019af6  pop     r14
0x140019af8  pop     r13
0x140019afa  pop     r12
0x140019afc  pop     rsi
0x140019afd  retn
0x140019afe  test    ecx, ecx
0x140019b00  js      short loc_140019B11
0x140019b02  cmp     esi, cs:dword_1400D6DC0
0x140019b08  jnb     short loc_140019B11
0x140019b0a  mov     eax, 1
0x140019b0f  jmp     short loc_140019B13
0x140019b11  xor     eax, eax
0x140019b13  test    eax, eax
0x140019b15  jnz     short loc_140019B4A
0x140019b17  mov     byte ptr [r9+38h], 1
0x140019b1c  and     dword ptr [r9+34h], 0
0x140019b21  mov     byte ptr [r9+30h], 1
0x140019b26  mov     dword ptr [r9+2Ch], 9
0x140019b2e  mov     [rsp+58h+var_30], rbx; __crt_cached_ptd_host *
0x140019b33  and     [rsp+58h+var_38], 0
0x140019b39  xor     r9d, r9d; LineNo
0x140019b3c  xor     r8d, r8d; FileName
0x140019b3f  xor     edx, edx; FunctionName
0x140019b41  xor     ecx, ecx; Expression
0x140019b43  call    sub_140004614
0x140019b48  jmp     short loc_140019AE8
0x140019b4a  mov     rax, rsi
0x140019b4d  mov     r15, rsi
0x140019b50  sar     r15, 6
0x140019b54  lea     rcx, qword_1400D69C0
0x140019b5b  and     eax, 3Fh
0x140019b5e  lea     r12, [rax+rax*8]
0x140019b62  mov     rax, [rcx+r15*8]
0x140019b66  test    byte ptr [rax+r12*8+38h], 1
0x140019b6c  jz      short loc_140019B17
0x140019b6e  mov     ecx, esi
0x140019b70  call    sub_1400160EC
0x140019b75  or      r14d, 0FFFFFFFFh
0x140019b79  lea     rax, qword_1400D69C0
0x140019b80  mov     rax, [rax+r15*8]
0x140019b84  test    byte ptr [rax+r12*8+38h], 1
0x140019b8a  jnz     short loc_140019BA1
0x140019b8c  mov     byte ptr [rbx+30h], 1
0x140019b90  mov     dword ptr [rbx+2Ch], 9
0x140019b97  mov     byte ptr [rbx+38h], 1
0x140019b9b  and     dword ptr [rbx+34h], 0
0x140019b9f  jmp     short loc_140019BB6
0x140019ba1  mov     r9, rbx
0x140019ba4  mov     r8d, r13d
0x140019ba7  mov     rdx, [rsp+58h+arg_8]
0x140019bac  mov     ecx, esi
0x140019bae  call    sub_140019BC8
0x140019bb3  mov     r14d, eax
0x140019bb6  mov     ecx, esi
0x140019bb8  call    sub_1400161D4
0x140019bbd  mov     eax, r14d
0x140019bc0  jmp     loc_140019AEB
0x1400ae37f  push    rbp; Microsoft VisualC 64bit universal runtime
0x1400ae381  sub     rsp, 30h
0x1400ae385  mov     rbp, rdx
0x1400ae388  mov     ecx, [rbp+60h]
0x1400ae38b  add     rsp, 30h
0x1400ae38f  pop     rbp
0x1400ae390  jmp     sub_1400161D4
```
