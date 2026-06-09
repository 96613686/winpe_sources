# ReadTableInfo

- ea: `0x180048544`
- end: `0x180048601`
- name: `ReadTableInfo`
- size: `189`
- prototype: `__int64 __fastcall(__int64, __int64, _DWORD *)`
- caller_count: `4`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180048380`
- `0x180048438`
- `0x180048608`
- `0x18004a050`

## callees

- `0x180048544`
- `0x180049fe4`
- `0x18004a3cc`
- `0x18004f8e4`
- `0x18004fbc4`
- `0x18004fc04`

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
  v6 = XCF_Read2((_JBTYPE *)a1);
  v7 = v6;
  v8 = (unsigned int)(v4 + 2);
  *a3 = v6;
  if ( v6 )
  {
    XCF_ReadBlock(a1, v8, 1);
    v10 = XCF_Read1((_JBTYPE *)a1);
    a3[1] = v10;
    if ( (unsigned __int8)(v10 - 1) > 3u )
      XCF_FatalErrorHandler((_JBTYPE *)a1, 10);
    v11 = *a3;
    a3[2] = v4 + 3;
    a3[3] = v4 + v10 * (v11 + 1) + 2;
    XCF_LookUpTableEntry(a1, a3, v11 - 1);
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
0x180048544  mov     [rsp+arg_0], rbx
0x180048549  mov     [rsp+arg_8], rsi
0x18004854e  push    rdi
0x18004854f  sub     rsp, 20h
0x180048553  mov     rbx, r8
0x180048556  mov     esi, edx
0x180048558  mov     r8d, 2
0x18004855e  mov     rdi, rcx
0x180048561  call    XCF_ReadBlock
0x180048566  mov     rcx, rdi
0x180048569  call    XCF_Read2
0x18004856e  movzx   r9d, ax
0x180048572  lea     edx, [rsi+2]
0x180048575  mov     [rbx], r9d
0x180048578  test    r9d, r9d
0x18004857b  jnz     short loc_18004859C
0x18004857d  mov     qword ptr [rbx+4], 1
0x180048585  mov     eax, edx
0x180048587  mov     [rbx+0Ch], r9d
0x18004858b  mov     rbx, [rsp+28h+arg_0]
0x180048590  mov     rsi, [rsp+28h+arg_8]
0x180048595  add     rsp, 20h
0x180048599  pop     rdi
0x18004859a  retn
0x18004859c  mov     r8d, 1
0x1800485a2  mov     rcx, rdi
0x1800485a5  call    XCF_ReadBlock
0x1800485aa  mov     rcx, rdi
0x1800485ad  call    XCF_Read1
0x1800485b2  movzx   ecx, al
0x1800485b5  mov     [rbx+4], ecx
0x1800485b8  lea     eax, [rcx-1]
0x1800485bb  cmp     al, 3
0x1800485bd  ja      short loc_1800485F3
0x1800485bf  mov     r8d, [rbx]
0x1800485c2  lea     eax, [rsi+3]
0x1800485c5  mov     [rbx+8], eax
0x1800485c8  mov     rdx, rbx
0x1800485cb  lea     eax, [r8+1]
0x1800485cf  imul    eax, ecx
0x1800485d2  mov     rcx, rdi
0x1800485d5  add     eax, 2
0x1800485d8  add     eax, esi
0x1800485da  dec     r8d
0x1800485dd  mov     [rbx+0Ch], eax
0x1800485e0  call    XCF_LookUpTableEntry
0x1800485e5  mov     eax, [rdi+375Ch]
0x1800485eb  add     eax, [rdi+3758h]
0x1800485f1  jmp     short loc_18004858B
0x1800485f3  mov     edx, 0Ah
0x1800485f8  mov     rcx, rdi
0x1800485fb  call    XCF_FatalErrorHandler
```
