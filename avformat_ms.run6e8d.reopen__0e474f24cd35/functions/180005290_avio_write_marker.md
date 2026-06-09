# avio_write_marker

- ea: `0x180005290`
- end: `0x18000532e`
- name: `avio_write_marker`
- size: `158`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800122a0`
- `0x180012670`
- `0x18001315c`

## callees

- `0x180003fb0`
- `0x180005290`

## pseudocode

```c
__int64 __fastcall avio_write_marker(__int64 a1, __int64 a2, unsigned int a3)
{
  int v3; // edi
  __int64 result; // rax

  v3 = a3;
  result = a3;
  if ( a3 == 5 )
  {
    result = *(int *)(a1 + 96);
    if ( *(_QWORD *)(a1 + 24) - *(_QWORD *)(a1 + 8) >= result )
      return avio_flush(a1);
    return result;
  }
  if ( !*(_QWORD *)(a1 + 160) )
    return result;
  if ( a3 == 2 )
  {
    if ( !*(_DWORD *)(a1 + 168) )
    {
LABEL_13:
      result = avio_flush(a1);
      *(_DWORD *)(a1 + 212) = v3;
      *(_QWORD *)(a1 + 216) = a2;
      return result;
    }
    v3 = 3;
  }
  else if ( a3 != 3 )
  {
    goto LABEL_11;
  }
  result = *(unsigned int *)(a1 + 212);
  if ( !(_DWORD)result )
    goto LABEL_13;
  if ( (_DWORD)result != 4 )
    return result;
LABEL_11:
  if ( (v3 & 0xFFFFFFFB) != 0 || v3 != *(_DWORD *)(a1 + 212) )
    goto LABEL_13;
  return result;
}

```

## disassembly

```asm
0x180005290  mov     [rsp+arg_0], rbx
0x180005295  mov     [rsp+arg_8], rsi
0x18000529a  push    rdi
0x18000529b  sub     rsp, 20h
0x18000529f  mov     edi, r8d
0x1800052a2  mov     rsi, rdx
0x1800052a5  mov     rbx, rcx
0x1800052a8  mov     eax, r8d
0x1800052ab  cmp     r8d, 5
0x1800052af  jnz     short loc_1800052C9
0x1800052b1  mov     rdx, [rcx+18h]
0x1800052b5  sub     rdx, [rcx+8]
0x1800052b9  movsxd  rax, dword ptr [rcx+60h]
0x1800052bd  cmp     rdx, rax
0x1800052c0  jl      short loc_18000531E
0x1800052c2  call    avio_flush
0x1800052c7  jmp     short loc_18000531E
0x1800052c9  cmp     qword ptr [rcx+0A0h], 0
0x1800052d1  jz      short loc_18000531E
0x1800052d3  cmp     r8d, 2
0x1800052d7  jnz     short loc_1800052E8
0x1800052d9  cmp     dword ptr [rcx+0A8h], 0
0x1800052e0  jz      short loc_18000530C
0x1800052e2  lea     edi, [r8+1]
0x1800052e6  jmp     short loc_1800052ED
0x1800052e8  cmp     eax, 3
0x1800052eb  jnz     short loc_1800052FC
0x1800052ed  mov     eax, [rcx+0D4h]
0x1800052f3  test    eax, eax
0x1800052f5  jz      short loc_18000530C
0x1800052f7  cmp     eax, 4
0x1800052fa  jnz     short loc_18000531E
0x1800052fc  test    edi, 0FFFFFFFBh
0x180005302  jnz     short loc_18000530C
0x180005304  cmp     edi, [rcx+0D4h]
0x18000530a  jz      short loc_18000531E
0x18000530c  call    avio_flush
0x180005311  mov     [rbx+0D4h], edi
0x180005317  mov     [rbx+0D8h], rsi
0x18000531e  mov     rbx, [rsp+28h+arg_0]
0x180005323  mov     rsi, [rsp+28h+arg_8]
0x180005328  add     rsp, 20h
0x18000532c  pop     rdi
0x18000532d  retn
```
