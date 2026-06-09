# PCLmWriter::PDFDocumentWriter::_BuildIndex(std::vector<uint,std::allocator<uint>> *)

- ea: `0x1800163b0`
- end: `0x1800164e2`
- name: `?_BuildIndex@PDFDocumentWriter@PCLmWriter@@AEAAXPEAV?$vector@IV?$allocator@I@std@@@std@@@Z`
- size: `306`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180015de4`

## callees

- `0x1800139a4`
- `0x1800163b0`

## pseudocode

```c
__int64 **__fastcall PCLmWriter::PDFDocumentWriter::_BuildIndex(__int64 a1, __int64 a2)
{
  __int64 *v4; // rbx
  unsigned int v5; // esi
  unsigned int v6; // r8d
  unsigned int *v7; // rdx
  int *v8; // rdx
  int v9; // esi
  __int64 **v10; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  __int64 **result; // rax
  unsigned int *v14; // rdx
  int *v15; // rdx
  int v16; // esi
  unsigned int v17; // [rsp+50h] [rbp+8h] BYREF

  v4 = ***(__int64 ****)(a1 + 56);
  v5 = *((_DWORD *)v4 + 8);
  v6 = v5;
  v17 = v5;
  do
  {
    if ( *((_DWORD *)v4 + 8) - 1 <= v5 )
    {
      v5 = *((_DWORD *)v4 + 8);
    }
    else
    {
      v7 = *(unsigned int **)(a2 + 8);
      if ( v7 == *(unsigned int **)(a2 + 16) )
      {
        std::vector<unsigned int>::_Emplace_reallocate<unsigned int>(a2, v7, &v17);
        v6 = v17;
      }
      else
      {
        *v7 = v6;
        *(_QWORD *)(a2 + 8) += 4LL;
      }
      v8 = *(int **)(a2 + 8);
      v9 = v5 - v6 + 1;
      v17 = v9;
      if ( v8 == *(int **)(a2 + 16) )
      {
        std::vector<unsigned int>::_Emplace_reallocate<unsigned int>(a2, v8, &v17);
      }
      else
      {
        *v8 = v9;
        *(_QWORD *)(a2 + 8) += 4LL;
      }
      v5 = *((_DWORD *)v4 + 8);
      v6 = v5;
      v17 = v5;
    }
    v10 = (__int64 **)v4[2];
    if ( *((_BYTE *)v10 + 25) )
    {
      for ( i = (__int64 *)v4[1]; !*((_BYTE *)i + 25) && v4 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v4 = i;
      v4 = i;
    }
    else
    {
      v4 = (__int64 *)v4[2];
      for ( j = *v10; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v4 = j;
    }
    result = *(__int64 ***)(a1 + 56);
  }
  while ( v4 != *result );
  v14 = *(unsigned int **)(a2 + 8);
  if ( v14 == *(unsigned int **)(a2 + 16) )
  {
    result = (__int64 **)std::vector<unsigned int>::_Emplace_reallocate<unsigned int>(a2, v14, &v17);
    v6 = v17;
  }
  else
  {
    *v14 = v6;
    *(_QWORD *)(a2 + 8) += 4LL;
  }
  v15 = *(int **)(a2 + 8);
  v16 = v5 - v6 + 1;
  v17 = v16;
  if ( v15 == *(int **)(a2 + 16) )
    return (__int64 **)std::vector<unsigned int>::_Emplace_reallocate<unsigned int>(a2, v15, &v17);
  *v15 = v16;
  *(_QWORD *)(a2 + 8) += 4LL;
  return result;
}

```

## disassembly

```asm
0x1800163b0  push    rbx
0x1800163b2  push    rbp
0x1800163b3  push    rsi
0x1800163b4  push    rdi
0x1800163b5  sub     rsp, 28h
0x1800163b9  mov     rax, [rcx+38h]
0x1800163bd  mov     rdi, rdx
0x1800163c0  mov     rbp, rcx
0x1800163c3  mov     rbx, [rax]
0x1800163c6  mov     rbx, [rbx]
0x1800163c9  mov     esi, [rbx+20h]
0x1800163cc  mov     r8d, esi
0x1800163cf  mov     [rsp+48h+arg_0], esi
0x1800163d3  mov     ecx, [rbx+20h]
0x1800163d6  lea     eax, [rcx-1]
0x1800163d9  cmp     eax, esi
0x1800163db  jbe     short loc_180016438
0x1800163dd  mov     rdx, [rdi+8]
0x1800163e1  cmp     rdx, [rdi+10h]
0x1800163e5  jz      short loc_1800163F1
0x1800163e7  mov     [rdx], r8d
0x1800163ea  add     qword ptr [rdi+8], 4
0x1800163ef  jmp     short loc_180016403
0x1800163f1  lea     r8, [rsp+48h+arg_0]
0x1800163f6  mov     rcx, rdi
0x1800163f9  call    ??$_Emplace_reallocate@I@?$vector@IV?$allocator@I@std@@@std@@AEAAPEAIQEAI$$QEAI@Z; std::vector<uint>::_Emplace_reallocate<uint>(uint * const,uint &&)
0x1800163fe  mov     r8d, [rsp+48h+arg_0]
0x180016403  mov     rdx, [rdi+8]
0x180016407  sub     esi, r8d
0x18001640a  inc     esi
0x18001640c  mov     [rsp+48h+arg_0], esi
0x180016410  cmp     rdx, [rdi+10h]
0x180016414  jz      short loc_18001641F
0x180016416  mov     [rdx], esi
0x180016418  add     qword ptr [rdi+8], 4
0x18001641d  jmp     short loc_18001642C
0x18001641f  lea     r8, [rsp+48h+arg_0]
0x180016424  mov     rcx, rdi
0x180016427  call    ??$_Emplace_reallocate@I@?$vector@IV?$allocator@I@std@@@std@@AEAAPEAIQEAI$$QEAI@Z; std::vector<uint>::_Emplace_reallocate<uint>(uint * const,uint &&)
0x18001642c  mov     esi, [rbx+20h]
0x18001642f  mov     r8d, esi
0x180016432  mov     [rsp+48h+arg_0], esi
0x180016436  jmp     short loc_18001643A
0x180016438  mov     esi, ecx
0x18001643a  mov     rcx, [rbx+10h]
0x18001643e  cmp     byte ptr [rcx+19h], 0
0x180016442  jz      short loc_180016462
0x180016444  mov     rax, [rbx+8]
0x180016448  jmp     short loc_180016457
0x18001644a  cmp     rbx, [rax+10h]
0x18001644e  jnz     short loc_18001645D
0x180016450  mov     rbx, rax
0x180016453  mov     rax, [rax+8]
0x180016457  cmp     byte ptr [rax+19h], 0
0x18001645b  jz      short loc_18001644A
0x18001645d  mov     rbx, rax
0x180016460  jmp     short loc_18001647D
0x180016462  mov     rbx, rcx
0x180016465  mov     rcx, [rcx]
0x180016468  cmp     byte ptr [rcx+19h], 0
0x18001646c  jnz     short loc_18001647D
0x18001646e  mov     rax, [rcx]
0x180016471  mov     rbx, rcx
0x180016474  mov     rcx, rax
0x180016477  cmp     byte ptr [rax+19h], 0
0x18001647b  jz      short loc_18001646E
0x18001647d  mov     rax, [rbp+38h]
0x180016481  cmp     rbx, [rax]
0x180016484  jnz     loc_1800163D3
0x18001648a  mov     rdx, [rdi+8]
0x18001648e  cmp     rdx, [rdi+10h]
0x180016492  jz      short loc_18001649E
0x180016494  mov     [rdx], r8d
0x180016497  add     qword ptr [rdi+8], 4
0x18001649c  jmp     short loc_1800164B0
0x18001649e  lea     r8, [rsp+48h+arg_0]
0x1800164a3  mov     rcx, rdi
0x1800164a6  call    ??$_Emplace_reallocate@I@?$vector@IV?$allocator@I@std@@@std@@AEAAPEAIQEAI$$QEAI@Z; std::vector<uint>::_Emplace_reallocate<uint>(uint * const,uint &&)
0x1800164ab  mov     r8d, [rsp+48h+arg_0]
0x1800164b0  mov     rdx, [rdi+8]
0x1800164b4  sub     esi, r8d
0x1800164b7  inc     esi
0x1800164b9  mov     [rsp+48h+arg_0], esi
0x1800164bd  cmp     rdx, [rdi+10h]
0x1800164c1  jz      short loc_1800164CC
0x1800164c3  mov     [rdx], esi
0x1800164c5  add     qword ptr [rdi+8], 4
0x1800164ca  jmp     short loc_1800164D9
0x1800164cc  lea     r8, [rsp+48h+arg_0]
0x1800164d1  mov     rcx, rdi
0x1800164d4  call    ??$_Emplace_reallocate@I@?$vector@IV?$allocator@I@std@@@std@@AEAAPEAIQEAI$$QEAI@Z; std::vector<uint>::_Emplace_reallocate<uint>(uint * const,uint &&)
0x1800164d9  add     rsp, 28h
0x1800164dd  pop     rdi
0x1800164de  pop     rsi
0x1800164df  pop     rbp
0x1800164e0  pop     rbx
0x1800164e1  retn
```
