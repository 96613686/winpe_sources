# ReadFontSetHeader

- ea: `0x180046b10`
- end: `0x180046c14`
- name: `ReadFontSetHeader`
- size: `260`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800484d4`

## callees

- `0x180046b10`
- `0x180046c1c`
- `0x180048b5c`
- `0x18004e048`
- `0x18004e324`

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
  *(_DWORD *)(a1 + 7844) = (unsigned __int8)XCF_Read1(a1);
  *(_DWORD *)(a1 + 7848) = (unsigned __int8)XCF_Read1(a1);
  *(_DWORD *)(a1 + 7856) = (unsigned __int8)XCF_Read1(a1);
  v2 = XCF_Read1(a1);
  v3 = *(_DWORD *)(a1 + 7844) == 1;
  *(_DWORD *)(a1 + 7852) = v2;
  if ( !v3 )
    XCF_FatalErrorHandler(a1, 9);
  if ( (unsigned int)v2 - 1 > 3 )
    XCF_FatalErrorHandler(a1, 10);
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
0x180046b10  mov     [rsp+arg_0], rbx
0x180046b15  push    rdi
0x180046b16  sub     rsp, 20h
0x180046b1a  xor     edx, edx
0x180046b1c  mov     rdi, rcx
0x180046b1f  lea     r8d, [rdx+4]
0x180046b23  call    XCF_ReadBlock
0x180046b28  mov     rcx, rdi
0x180046b2b  call    XCF_Read1
0x180046b30  movzx   eax, al
0x180046b33  mov     rcx, rdi
0x180046b36  mov     [rdi+1EA4h], eax
0x180046b3c  call    XCF_Read1
0x180046b41  movzx   eax, al
0x180046b44  mov     rcx, rdi
0x180046b47  mov     [rdi+1EA8h], eax
0x180046b4d  call    XCF_Read1
0x180046b52  movzx   eax, al
0x180046b55  mov     rcx, rdi
0x180046b58  mov     [rdi+1EB0h], eax
0x180046b5e  call    XCF_Read1
0x180046b63  cmp     dword ptr [rdi+1EA4h], 1
0x180046b6a  mov     rcx, rdi
0x180046b6d  movzx   eax, al
0x180046b70  mov     [rdi+1EACh], eax
0x180046b76  jnz     loc_180046C09
0x180046b7c  dec     eax
0x180046b7e  cmp     eax, 3
0x180046b81  ja      short loc_180046BFE
0x180046b83  mov     edx, [rdi+1EB0h]
0x180046b89  lea     r8, [rdi+1EB4h]
0x180046b90  call    ReadTableInfo
0x180046b95  lea     r8, [rdi+1EC4h]
0x180046b9c  mov     edx, eax
0x180046b9e  mov     rcx, rdi
0x180046ba1  call    ReadTableInfo
0x180046ba6  lea     r8, [rdi+1ED4h]
0x180046bad  mov     edx, eax
0x180046baf  mov     rcx, rdi
0x180046bb2  call    ReadTableInfo
0x180046bb7  lea     rbx, [rdi+1EF4h]
0x180046bbe  mov     edx, eax
0x180046bc0  mov     r8, rbx
0x180046bc3  mov     rcx, rdi
0x180046bc6  call    ReadTableInfo
0x180046bcb  cmp     dword ptr [rbx], 4D8h
0x180046bd1  jnb     short loc_180046BDA
0x180046bd3  mov     eax, 6Bh ; 'k'
0x180046bd8  jmp     short loc_180046BEC
0x180046bda  cmp     dword ptr [rbx], 846Ch
0x180046be0  mov     eax, 46Bh
0x180046be5  jb      short loc_180046BEC
0x180046be7  mov     eax, 8000h
0x180046bec  mov     rbx, [rsp+28h+arg_0]
0x180046bf1  mov     [rdi+1F04h], ax
0x180046bf8  add     rsp, 20h
0x180046bfc  pop     rdi
0x180046bfd  retn
0x180046bfe  mov     edx, 0Ah
0x180046c03  call    XCF_FatalErrorHandler
0x180046c09  mov     edx, 9
0x180046c0e  call    XCF_FatalErrorHandler
```
