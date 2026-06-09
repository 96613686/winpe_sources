# WriteStemSnap

- ea: `0x18004c470`
- end: `0x18004c5f0`
- name: `WriteStemSnap`
- size: `384`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18004bb20`
- `0x18004cc6c`

## callees

- `0x180049890`
- `0x180049d80`
- `0x180049e14`
- `0x18004a1a8`
- `0x18004c470`

## pseudocode

```c
__int64 __fastcall WriteStemSnap(_DWORD *a1, int a2)
{
  unsigned int *v2; // r14
  __int64 result; // rax
  int v6; // r9d
  int v7; // r9d

  v2 = a1 + 444;
  WriteBlendArrayLine((_DWORD)a1, (unsigned int)"StdHW", (_DWORD)a1 + 1776, a1[443], a2, 1, 1);
  result = WriteBlendArrayLine((_DWORD)a1, (unsigned int)"StdVW", (int)a1 + 1844, a1[460], a2, 1, 1);
  if ( a1[1249] )
  {
    PutString(a1, "/StemSnapH [ ");
    PutBlendArray((_DWORD)a1, (_DWORD)a1 + 5000, a1[1249], a2, 1, 1);
    PutString(a1, "] ");
    v6 = a1[1249];
    if ( v6 <= 2 || a1[122] )
      result = PutString(a1, "def\r\n");
    else
      result = PutStemSnapBugFix((__int64)a1, *v2, (__int64)(a1 + 1250), v6);
  }
  if ( a1[1442] )
  {
    PutString(a1, "/StemSnapV [ ");
    PutBlendArray((_DWORD)a1, (_DWORD)a1 + 5772, a1[1442], a2, 1, 1);
    PutString(a1, "] ");
    v7 = a1[1442];
    if ( v7 <= 2 || a1[122] )
      return PutString(a1, "def\r\n");
    else
      return PutStemSnapBugFix((__int64)a1, a1[461], (__int64)(a1 + 1443), v7);
  }
  return result;
}

```

## disassembly

```asm
0x18004c470  push    rbx
0x18004c472  push    rsi
0x18004c473  push    rdi
0x18004c474  push    r14
0x18004c476  push    r15
0x18004c478  sub     rsp, 40h
0x18004c47c  mov     r9d, [rcx+6ECh]
0x18004c483  lea     r14, [rcx+6F0h]
0x18004c48a  mov     r15d, 1
0x18004c490  mov     esi, edx
0x18004c492  mov     [rsp+68h+var_38], r15d
0x18004c497  mov     r8, r14
0x18004c49a  mov     [rsp+68h+var_40], r15d
0x18004c49f  mov     rbx, rcx
0x18004c4a2  mov     [rsp+68h+var_48], edx
0x18004c4a6  lea     rdx, aStdhw; "StdHW"
0x18004c4ad  call    WriteBlendArrayLine
0x18004c4b2  mov     r9d, [rbx+730h]
0x18004c4b9  lea     r8, [rbx+734h]
0x18004c4c0  mov     [rsp+68h+var_38], r15d
0x18004c4c5  lea     rdx, aStdvw; "StdVW"
0x18004c4cc  mov     [rsp+68h+var_40], r15d
0x18004c4d1  mov     rcx, rbx
0x18004c4d4  mov     [rsp+68h+var_48], esi
0x18004c4d8  call    WriteBlendArrayLine
0x18004c4dd  cmp     dword ptr [rbx+1384h], 0
0x18004c4e4  jz      short loc_18004C55F
0x18004c4e6  lea     rdx, aStemsnaph; "/StemSnapH [ "
0x18004c4ed  mov     rcx, rbx
0x18004c4f0  call    PutString
0x18004c4f5  mov     r8d, [rbx+1384h]
0x18004c4fc  lea     rdi, [rbx+1388h]
0x18004c503  mov     rdx, rdi
0x18004c506  mov     [rsp+68h+var_40], r15d
0x18004c50b  mov     r9d, esi
0x18004c50e  mov     [rsp+68h+var_48], r15d
0x18004c513  mov     rcx, rbx
0x18004c516  call    PutBlendArray
0x18004c51b  lea     rdx, asc_1800630F0; "] "
0x18004c522  mov     rcx, rbx
0x18004c525  call    PutString
0x18004c52a  mov     r9d, [rbx+1384h]
0x18004c531  cmp     r9d, 2
0x18004c535  jle     short loc_18004C550
0x18004c537  cmp     dword ptr [rbx+1E8h], 0
0x18004c53e  jnz     short loc_18004C550
0x18004c540  mov     edx, [r14]
0x18004c543  mov     r8, rdi
0x18004c546  mov     rcx, rbx
0x18004c549  call    PutStemSnapBugFix
0x18004c54e  jmp     short loc_18004C55F
0x18004c550  lea     rdx, aDef_0; "def\r\n"
0x18004c557  mov     rcx, rbx
0x18004c55a  call    PutString
0x18004c55f  cmp     dword ptr [rbx+1688h], 0
0x18004c566  jz      short loc_18004C5E4
0x18004c568  lea     rdx, aStemsnapv; "/StemSnapV [ "
0x18004c56f  mov     rcx, rbx
0x18004c572  call    PutString
0x18004c577  mov     r8d, [rbx+1688h]
0x18004c57e  lea     rdi, [rbx+168Ch]
0x18004c585  mov     rdx, rdi
0x18004c588  mov     [rsp+68h+var_40], r15d
0x18004c58d  mov     r9d, esi
0x18004c590  mov     [rsp+68h+var_48], r15d
0x18004c595  mov     rcx, rbx
0x18004c598  call    PutBlendArray
0x18004c59d  lea     rdx, asc_1800630F0; "] "
0x18004c5a4  mov     rcx, rbx
0x18004c5a7  call    PutString
0x18004c5ac  mov     r9d, [rbx+1688h]
0x18004c5b3  cmp     r9d, 2
0x18004c5b7  jle     short loc_18004C5D5
0x18004c5b9  cmp     dword ptr [rbx+1E8h], 0
0x18004c5c0  jnz     short loc_18004C5D5
0x18004c5c2  mov     edx, [rbx+734h]
0x18004c5c8  mov     r8, rdi
0x18004c5cb  mov     rcx, rbx
0x18004c5ce  call    PutStemSnapBugFix
0x18004c5d3  jmp     short loc_18004C5E4
0x18004c5d5  lea     rdx, aDef_0; "def\r\n"
0x18004c5dc  mov     rcx, rbx
0x18004c5df  call    PutString
0x18004c5e4  add     rsp, 40h
0x18004c5e8  pop     r15
0x18004c5ea  pop     r14
0x18004c5ec  pop     rdi
0x18004c5ed  pop     rsi
0x18004c5ee  pop     rbx
0x18004c5ef  retn
```
