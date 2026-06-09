# ReadTableInfo

- ea: `0x180046c1c`
- end: `0x180046cd8`
- name: `ReadTableInfo`
- size: `188`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180046a58`
- `0x180046b10`
- `0x180046ce0`
- `0x1800487e0`

## callees

- `0x180046c1c`
- `0x180048774`
- `0x180048b5c`
- `0x18004e048`
- `0x18004e324`
- `0x18004e360`

## pseudocode

```c
__int64 __fastcall ReadTableInfo(__int64 a1, __int64 a2, _DWORD *a3)
{
  int v4; // esi
  unsigned __int16 v6; // ax
  int v7; // r9d
  __int64 v8; // rdx
  __int64 result; // rax
  unsigned __int8 v10; // al
  int v11; // r8d

  v4 = a2;
  XCF_ReadBlock(a1, a2, 2);
  v6 = XCF_Read2(a1);
  v7 = v6;
  v8 = (unsigned int)(v4 + 2);
  *a3 = v6;
  if ( v6 )
  {
    XCF_ReadBlock(a1, v8, 1);
    v10 = XCF_Read1(a1);
    a3[1] = v10;
    if ( (unsigned __int8)(v10 - 1) > 3u )
      XCF_FatalErrorHandler(a1, 10);
    v11 = *a3;
    a3[2] = v4 + 3;
    a3[3] = v4 + v10 * (v11 + 1) + 2;
    XCF_LookUpTableEntry(a1, a3, (unsigned int)(v11 - 1));
    return (unsigned int)(*(_DWORD *)(a1 + 14168) + *(_DWORD *)(a1 + 14172));
  }
  else
  {
    *(_QWORD *)(a3 + 1) = 1;
    result = (unsigned int)v8;
    a3[3] = v7;
  }
  return result;
}

```

## disassembly

```asm
0x180046c1c  mov     [rsp+arg_0], rbx
0x180046c21  mov     [rsp+arg_8], rsi
0x180046c26  push    rdi
0x180046c27  sub     rsp, 20h
0x180046c2b  mov     rbx, r8
0x180046c2e  mov     esi, edx
0x180046c30  mov     r8d, 2
0x180046c36  mov     rdi, rcx
0x180046c39  call    XCF_ReadBlock
0x180046c3e  mov     rcx, rdi
0x180046c41  call    XCF_Read2
0x180046c46  movzx   r9d, ax
0x180046c4a  lea     edx, [rsi+2]
0x180046c4d  mov     [rbx], r9d
0x180046c50  test    r9d, r9d
0x180046c53  jnz     short loc_180046C73
0x180046c55  mov     qword ptr [rbx+4], 1
0x180046c5d  mov     eax, edx
0x180046c5f  mov     [rbx+0Ch], r9d
0x180046c63  mov     rbx, [rsp+28h+arg_0]
0x180046c68  mov     rsi, [rsp+28h+arg_8]
0x180046c6d  add     rsp, 20h
0x180046c71  pop     rdi
0x180046c72  retn
0x180046c73  mov     r8d, 1
0x180046c79  mov     rcx, rdi
0x180046c7c  call    XCF_ReadBlock
0x180046c81  mov     rcx, rdi
0x180046c84  call    XCF_Read1
0x180046c89  movzx   ecx, al
0x180046c8c  mov     [rbx+4], ecx
0x180046c8f  lea     eax, [rcx-1]
0x180046c92  cmp     al, 3
0x180046c94  ja      short loc_180046CCA
0x180046c96  mov     r8d, [rbx]
0x180046c99  lea     eax, [rsi+3]
0x180046c9c  mov     [rbx+8], eax
0x180046c9f  mov     rdx, rbx
0x180046ca2  lea     eax, [r8+1]
0x180046ca6  imul    eax, ecx
0x180046ca9  mov     rcx, rdi
0x180046cac  add     eax, 2
0x180046caf  add     eax, esi
0x180046cb1  dec     r8d
0x180046cb4  mov     [rbx+0Ch], eax
0x180046cb7  call    XCF_LookUpTableEntry
0x180046cbc  mov     eax, [rdi+375Ch]
0x180046cc2  add     eax, [rdi+3758h]
0x180046cc8  jmp     short loc_180046C63
0x180046cca  mov     edx, 0Ah
0x180046ccf  mov     rcx, rdi
0x180046cd2  call    XCF_FatalErrorHandler
```
