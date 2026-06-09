# ReadFontSetHeader

- ea: `0x180048438`
- end: `0x18004853d`
- name: `ReadFontSetHeader`
- size: `261`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180049d44`

## callees

- `0x180048438`
- `0x180048544`
- `0x18004a3cc`
- `0x18004f8e4`
- `0x18004fbc4`

## pseudocode

```c
__int64 __fastcall ReadFontSetHeader(__int64 a1)
{
  unsigned __int8 v2; // al
  bool v3; // zf
  unsigned int TableInfo; // eax
  unsigned int v5; // eax
  unsigned int v6; // eax
  __int64 result; // rax

  XCF_ReadBlock(a1, 0, 4);
  *(_DWORD *)(a1 + 7844) = (unsigned __int8)XCF_Read1((_JBTYPE *)a1);
  *(_DWORD *)(a1 + 7848) = (unsigned __int8)XCF_Read1((_JBTYPE *)a1);
  *(_DWORD *)(a1 + 7856) = (unsigned __int8)XCF_Read1((_JBTYPE *)a1);
  v2 = XCF_Read1((_JBTYPE *)a1);
  v3 = *(_DWORD *)(a1 + 7844) == 1;
  *(_DWORD *)(a1 + 7852) = v2;
  if ( !v3 )
    XCF_FatalErrorHandler((_JBTYPE *)a1, 9);
  if ( (unsigned int)v2 - 1 > 3 )
    XCF_FatalErrorHandler((_JBTYPE *)a1, 10);
  TableInfo = ReadTableInfo(a1, *(unsigned int *)(a1 + 7856), (_DWORD *)(a1 + 7860));
  v5 = ReadTableInfo(a1, TableInfo, (_DWORD *)(a1 + 7876));
  v6 = ReadTableInfo(a1, v5, (_DWORD *)(a1 + 7892));
  ReadTableInfo(a1, v6, (_DWORD *)(a1 + 7924));
  if ( *(_DWORD *)(a1 + 7924) >= 0x4D8u )
  {
    result = 1131;
    if ( *(_DWORD *)(a1 + 7924) >= 0x846Cu )
      result = 0x8000;
  }
  else
  {
    result = 107;
  }
  *(_WORD *)(a1 + 7940) = result;
  return result;
}

```

## disassembly

```asm
0x180048438  mov     [rsp+arg_0], rbx
0x18004843d  push    rdi
0x18004843e  sub     rsp, 20h
0x180048442  xor     edx, edx
0x180048444  mov     rdi, rcx
0x180048447  lea     r8d, [rdx+4]
0x18004844b  call    XCF_ReadBlock
0x180048450  mov     rcx, rdi
0x180048453  call    XCF_Read1
0x180048458  movzx   eax, al
0x18004845b  mov     rcx, rdi
0x18004845e  mov     [rdi+1EA4h], eax
0x180048464  call    XCF_Read1
0x180048469  movzx   eax, al
0x18004846c  mov     rcx, rdi
0x18004846f  mov     [rdi+1EA8h], eax
0x180048475  call    XCF_Read1
0x18004847a  movzx   eax, al
0x18004847d  mov     rcx, rdi
0x180048480  mov     [rdi+1EB0h], eax
0x180048486  call    XCF_Read1
0x18004848b  cmp     dword ptr [rdi+1EA4h], 1
0x180048492  mov     rcx, rdi
0x180048495  movzx   eax, al
0x180048498  mov     [rdi+1EACh], eax
0x18004849e  jnz     loc_180048532
0x1800484a4  dec     eax
0x1800484a6  cmp     eax, 3
0x1800484a9  ja      short loc_180048527
0x1800484ab  mov     edx, [rdi+1EB0h]
0x1800484b1  lea     r8, [rdi+1EB4h]
0x1800484b8  call    ReadTableInfo
0x1800484bd  lea     r8, [rdi+1EC4h]
0x1800484c4  mov     edx, eax
0x1800484c6  mov     rcx, rdi
0x1800484c9  call    ReadTableInfo
0x1800484ce  lea     r8, [rdi+1ED4h]
0x1800484d5  mov     edx, eax
0x1800484d7  mov     rcx, rdi
0x1800484da  call    ReadTableInfo
0x1800484df  lea     rbx, [rdi+1EF4h]
0x1800484e6  mov     edx, eax
0x1800484e8  mov     r8, rbx
0x1800484eb  mov     rcx, rdi
0x1800484ee  call    ReadTableInfo
0x1800484f3  cmp     dword ptr [rbx], 4D8h
0x1800484f9  jnb     short loc_180048502
0x1800484fb  mov     eax, 6Bh ; 'k'
0x180048500  jmp     short loc_180048514
0x180048502  cmp     dword ptr [rbx], 846Ch
0x180048508  mov     eax, 46Bh
0x18004850d  jb      short loc_180048514
0x18004850f  mov     eax, 8000h
0x180048514  mov     rbx, [rsp+28h+arg_0]
0x180048519  mov     [rdi+1F04h], ax
0x180048520  add     rsp, 20h
0x180048524  pop     rdi
0x180048525  retn
0x180048527  mov     edx, 0Ah
0x18004852c  call    XCF_FatalErrorHandler
0x180048532  mov     edx, 9
0x180048537  call    XCF_FatalErrorHandler
```
