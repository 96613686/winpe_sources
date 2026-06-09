# GetFileNameFromPath

- ea: `0x14000b76c`
- end: `0x14000b84d`
- name: `GetFileNameFromPath`
- size: `225`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14000aca0`

## callees

- `0x140001118`
- `0x140001168`
- `0x1400011b0`
- `0x14000b76c`

## string_xrefs

- `0x14000b786`: `UevFilter.GetFileNameFromPath: Entry\n`
- `0x14000b7ef`: `UevFilter.GetFileNameFromPath: Invalid file name.\n`
- `0x14000b818`: `UevFilter.GetFileNameFromPath: Invalid parameter specified\n`
- `0x14000b82c`: `UevFilter.GetProcessNameFromPath: Exit, retStatus = 0x%X\n`

## pseudocode

```c
__int64 __fastcall GetFileNameFromPath(unsigned __int16 *a1, __int64 a2, __int64 a3)
{
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int16 v10; // r8
  unsigned int v11; // ebx

  DbgTrace(2, "UevFilter.GetFileNameFromPath: Entry\n", a3);
  if ( !a1 || !a2 || (v6 = *a1, !(_WORD)v6) )
  {
    DbgTraceErr("UevFilter.GetFileNameFromPath: Invalid parameter specified\n", v5, v6);
    v11 = -1073741811;
    goto LABEL_15;
  }
  v7 = ((unsigned int)v6 >> 1) - 1;
  if ( (int)(((unsigned int)v6 >> 1) - 1) < 0 )
    goto LABEL_12;
  v8 = *((_QWORD *)a1 + 1);
  do
  {
    if ( *(_WORD *)(v8 + 2 * v7) == 92 )
      break;
    v7 = (unsigned int)(v7 - 1);
  }
  while ( (int)v7 >= 0 );
  if ( (int)v7 < 0 )
  {
LABEL_12:
    *(_WORD *)(a2 + 2) = v6;
    *(_WORD *)a2 = v6;
    *(_QWORD *)(a2 + 8) = *((_QWORD *)a1 + 1);
    goto LABEL_13;
  }
  if ( (unsigned __int16)v6 > 2u )
  {
    v9 = 2LL * ((int)v7 + 1);
    v10 = v6 - v9;
    *(_WORD *)(a2 + 2) = v10;
    *(_WORD *)a2 = v10;
    *(_QWORD *)(a2 + 8) = *((_QWORD *)a1 + 1) + v9;
LABEL_13:
    v11 = 0;
    goto LABEL_15;
  }
  v11 = -1073741823;
  DbgTraceErr("UevFilter.GetFileNameFromPath: Invalid file name.\n", v8, v6);
LABEL_15:
  DbgTraceFrmt(2u, "UevFilter.GetProcessNameFromPath: Exit, retStatus = 0x%X\n", v11);
  return v11;
}

```

## disassembly

```asm
0x14000b76c  mov     [rsp+arg_0], rbx
0x14000b771  mov     [rsp+arg_8], rsi
0x14000b776  push    rdi
0x14000b777  sub     rsp, 20h
0x14000b77b  mov     rbx, rdx
0x14000b77e  mov     rdi, rcx
0x14000b781  mov     esi, 2
0x14000b786  lea     rdx, aUevfilterGetfi_0; "UevFilter.GetFileNameFromPath: Entry\n"
0x14000b78d  mov     ecx, esi
0x14000b78f  call    DbgTrace
0x14000b794  xor     r9d, r9d
0x14000b797  test    rdi, rdi
0x14000b79a  jz      short loc_14000B818
0x14000b79c  test    rbx, rbx
0x14000b79f  jz      short loc_14000B818
0x14000b7a1  movzx   r8d, word ptr [rdi]
0x14000b7a5  test    r8w, r8w
0x14000b7a9  jz      short loc_14000B818
0x14000b7ab  mov     ecx, r8d
0x14000b7ae  shr     ecx, 1
0x14000b7b0  sub     ecx, 1
0x14000b7b3  js      short loc_14000B802
0x14000b7b5  mov     rdx, [rdi+8]
0x14000b7b9  cmp     word ptr [rdx+rcx*2], 5Ch ; '\'
0x14000b7be  jz      short loc_14000B7C5
0x14000b7c0  sub     ecx, 1
0x14000b7c3  jns     short loc_14000B7B9
0x14000b7c5  test    ecx, ecx
0x14000b7c7  js      short loc_14000B802
0x14000b7c9  cmp     r8w, si
0x14000b7cd  jbe     short loc_14000B7EF
0x14000b7cf  lea     eax, [rcx+1]
0x14000b7d2  movsxd  rcx, eax
0x14000b7d5  add     rcx, rcx
0x14000b7d8  sub     r8w, cx
0x14000b7dc  mov     [rbx+2], r8w
0x14000b7e1  mov     [rbx], r8w
0x14000b7e5  add     rcx, [rdi+8]
0x14000b7e9  mov     [rbx+8], rcx
0x14000b7ed  jmp     short loc_14000B813
0x14000b7ef  lea     rcx, aUevfilterGetfi; "UevFilter.GetFileNameFromPath: Invalid "...
0x14000b7f6  mov     ebx, 0C0000001h
0x14000b7fb  call    DbgTraceErr
0x14000b800  jmp     short loc_14000B829
0x14000b802  mov     [rbx+2], r8w
0x14000b807  mov     [rbx], r8w
0x14000b80b  mov     rax, [rdi+8]
0x14000b80f  mov     [rbx+8], rax
0x14000b813  mov     ebx, r9d
0x14000b816  jmp     short loc_14000B829
0x14000b818  lea     rcx, aUevfilterGetfi_1; "UevFilter.GetFileNameFromPath: Invalid "...
0x14000b81f  call    DbgTraceErr
0x14000b824  mov     ebx, 0C000000Dh
0x14000b829  mov     r8d, ebx
0x14000b82c  lea     rdx, aUevfilterGetpr; "UevFilter.GetProcessNameFromPath: Exit,"...
0x14000b833  mov     ecx, esi
0x14000b835  call    DbgTraceFrmt
0x14000b83a  mov     rsi, [rsp+28h+arg_8]
0x14000b83f  mov     eax, ebx
0x14000b841  mov     rbx, [rsp+28h+arg_0]
0x14000b846  add     rsp, 20h
0x14000b84a  pop     rdi
0x14000b84b  retn
```
