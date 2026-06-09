# CPns_Read

- ea: `0x18007edc0`
- end: `0x18007ee68`
- name: `CPns_Read`
- size: `168`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180078d40`
- `0x18007f350`

## callees

- `0x1800363f0`
- `0x18007edc0`
- `0x18007f0d0`

## pseudocode

```c
int __fastcall CPns_Read(__int64 a1, int *a2, __int64 a3, unsigned __int8 a4, int a5, int a6)
{
  __int64 v8; // rdi
  int v9; // ebp
  int v10; // edx
  int v11; // edx
  unsigned __int64 v12; // rdx
  int result; // eax

  v8 = (unsigned int)(a5 + 16 * a6);
  v9 = a4;
  if ( *(_BYTE *)(a1 + 972) )
  {
    v10 = CBlock_DecodeHuffmanWord(a2, *(_QWORD *)(a3 + 8)) - 60;
  }
  else
  {
    if ( (unsigned int)*a2 < 9 )
      FillBitCache(a2, 9u);
    *a2 -= 9;
    v11 = ((unsigned int)a2[1] >> *a2) & 0x1FF;
    *(_BYTE *)(a1 + 972) = 1;
    v10 = v11 - 256;
    *(_DWORD *)(a1 + 968) = v9 - 90;
  }
  *(_DWORD *)(a1 + 968) += v10;
  v12 = (unsigned __int64)(unsigned int)v8 >> 3;
  *(_WORD *)(*(_QWORD *)a1 + 2 * v8) = *(_DWORD *)(a1 + 968);
  result = *(unsigned __int8 *)(v12 + a1 + 952) | (1 << ((a5 + 16 * a6) & 7));
  *(_BYTE *)(v12 + a1 + 952) = result;
  return result;
}

```

## disassembly

```asm
0x18007edc0  push    rbx
0x18007edc2  push    rbp
0x18007edc3  push    rsi
0x18007edc4  push    rdi
0x18007edc5  sub     rsp, 28h
0x18007edc9  mov     edi, [rsp+48h+arg_28]
0x18007edcd  mov     rbx, rdx
0x18007edd0  shl     edi, 4
0x18007edd3  mov     rsi, rcx
0x18007edd6  add     edi, [rsp+48h+arg_20]
0x18007edda  cmp     byte ptr [rcx+3CCh], 0
0x18007ede1  movzx   ebp, r9b
0x18007ede5  jz      short loc_18007EDF8
0x18007ede7  mov     rdx, [r8+8]
0x18007edeb  mov     rcx, rbx
0x18007edee  call    CBlock_DecodeHuffmanWord
0x18007edf3  lea     edx, [rax-3Ch]
0x18007edf6  jmp     short loc_18007EE30
0x18007edf8  cmp     dword ptr [rdx], 9
0x18007edfb  jnb     short loc_18007EE0A
0x18007edfd  mov     edx, 9
0x18007ee02  mov     rcx, rbx
0x18007ee05  call    FillBitCache
0x18007ee0a  add     dword ptr [rbx], 0FFFFFFF7h
0x18007ee0d  mov     edx, [rbx+4]
0x18007ee10  mov     ecx, [rbx]
0x18007ee12  shr     edx, cl
0x18007ee14  and     edx, 1FFh
0x18007ee1a  mov     byte ptr [rsi+3CCh], 1
0x18007ee21  sub     edx, 100h
0x18007ee27  sub     ebp, 5Ah ; 'Z'
0x18007ee2a  mov     [rsi+3C8h], ebp
0x18007ee30  add     [rsi+3C8h], edx
0x18007ee36  mov     rax, [rsi]
0x18007ee39  mov     ecx, [rsi+3C8h]
0x18007ee3f  mov     edx, edi
0x18007ee41  shr     rdx, 3
0x18007ee45  mov     [rax+rdi*2], cx
0x18007ee49  and     edi, 7
0x18007ee4c  movzx   eax, byte ptr [rdx+rsi+3B8h]
0x18007ee54  bts     eax, edi
0x18007ee57  mov     [rdx+rsi+3B8h], al
0x18007ee5e  add     rsp, 28h
0x18007ee62  pop     rdi
0x18007ee63  pop     rsi
0x18007ee64  pop     rbp
0x18007ee65  pop     rbx
0x18007ee66  retn
```
