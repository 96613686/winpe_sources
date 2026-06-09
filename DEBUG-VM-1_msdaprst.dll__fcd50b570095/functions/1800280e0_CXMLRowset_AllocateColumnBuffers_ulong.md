# CXMLRowset::AllocateColumnBuffers(ulong)

- ea: `0x1800280e0`
- end: `0x18002823f`
- name: `?AllocateColumnBuffers@CXMLRowset@@UEAAJK@Z`
- size: `351`
- prototype: `__int64 __fastcall(CXMLRowset *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x180001d94`
- `0x18001a6c8`
- `0x18001ffa0`
- `0x1800280e0`
- `0x180028fb0`
- `0x18002e02a`

## pseudocode

```c
__int64 __fastcall CXMLRowset::AllocateColumnBuffers(void **this, unsigned int a2)
{
  __int64 v2; // rsi
  int ColumnBuffers; // ebx
  unsigned __int64 v5; // rbx
  unsigned int v6; // edx
  void **v7; // r9
  unsigned int v8; // eax
  unsigned int v9; // esi
  __int64 v10; // rcx
  unsigned __int128 v11; // rax
  unsigned __int8 *v12; // rax
  bool v13; // zf
  unsigned int v14; // eax

  v2 = a2;
  ColumnBuffers = CRowset::AllocateColumnBuffers((CRowset *)this, a2);
  if ( ColumnBuffers >= 0 )
  {
    if ( (_DWORD)v2 == -1 )
    {
      ColumnBuffers = -2147024882;
      if ( (bidGblFlags & 2) != 0 && off_180048DD8[0] )
        bidTraceW(off_180048210[0], 246784, off_180048DD8[0], 2147942414LL, 241);
    }
    else
    {
      v5 = (unsigned int)(v2 + 1);
      v6 = 0;
      if ( (unsigned int)v5 < 4 )
        goto LABEL_24;
      v7 = (void **)this[20];
      if ( v7 <= this + 20 && (void **)((char *)v7 + 4 * v2) >= this + 20 )
        goto LABEL_24;
      v8 = v5 & 0xFFFFFFFC;
      do
      {
        v6 += 4;
        v9 = v6;
      }
      while ( v6 < v8 );
      memset_0(this[20], -1, 16 * ((unsigned __int64)v8 >> 2));
      v6 = v9;
      if ( v9 < (unsigned int)v5 )
      {
LABEL_24:
        do
        {
          v10 = v6++;
          *((_DWORD *)this[20] + v10) = -1;
        }
        while ( v6 < (unsigned int)v5 );
      }
      v11 = v5 * (unsigned __int128)8uLL;
      if ( !is_mul_ok(v5, 8u) )
        LODWORD(v11) = -1;
      v12 = MMMAlloc(v11, DWORD2(v11));
      this[68] = v12;
      if ( v12 )
        memset_0(v12, 0, 8 * v5);
      ColumnBuffers = CCollectionList::Reserve((CCollectionList *)(this + 69), 5u);
      if ( ColumnBuffers >= 0 )
      {
        v13 = this[68] == 0;
        *((_WORD *)this + 153) = *((_WORD *)this + 152);
        v14 = ColumnBuffers;
        if ( v13 )
          return (unsigned int)-2147024882;
        return v14;
      }
    }
  }
  return (unsigned int)ColumnBuffers;
}

```

## disassembly

```asm
0x1800280e0  mov     [rsp+arg_0], rbx
0x1800280e5  mov     [rsp+arg_8], rsi
0x1800280ea  push    rdi
0x1800280eb  sub     rsp, 30h
0x1800280ef  mov     esi, edx
0x1800280f1  mov     rdi, rcx
0x1800280f4  call    ?AllocateColumnBuffers@CRowset@@UEAAJK@Z; CRowset::AllocateColumnBuffers(ulong)
0x1800280f9  mov     ebx, eax
0x1800280fb  test    eax, eax
0x1800280fd  js      loc_18002822D
0x180028103  cmp     esi, 0FFFFFFFEh
0x180028106  jbe     short loc_180028152
0x180028108  test    byte ptr cs:_bidGblFlags, 2
0x18002810f  mov     ebx, 8007000Eh
0x180028114  jz      loc_18002822D
0x18002811a  mov     rax, cs:off_180048DD8; "<CXMLRowset::AllocateColumnBuffers|ADO|"...
0x180028121  test    rax, rax
0x180028124  jz      loc_18002822D
0x18002812a  mov     r8, cs:off_180048DD8; "<CXMLRowset::AllocateColumnBuffers|ADO|"...
0x180028131  mov     r9d, ebx
0x180028134  mov     rcx, cs:off_180048210; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18002813b  mov     edx, 3C400h
0x180028140  mov     [rsp+38h+var_18], 0F1h
0x180028148  call    _bidTraceW
0x18002814d  jmp     loc_18002822D
0x180028152  lea     ebx, [rsi+1]
0x180028155  test    ebx, ebx
0x180028157  jz      short loc_1800281BC
0x180028159  xor     edx, edx
0x18002815b  cmp     ebx, 4
0x18002815e  jb      short loc_1800281A6
0x180028160  lea     r8, [rdi+0A0h]
0x180028167  mov     r9, [r8]
0x18002816a  cmp     r9, r8
0x18002816d  ja      short loc_180028178
0x18002816f  lea     rcx, [r9+rsi*4]
0x180028173  cmp     rcx, r8
0x180028176  jnb     short loc_1800281A6
0x180028178  mov     eax, ebx
0x18002817a  and     eax, 0FFFFFFFCh
0x18002817d  add     edx, 4
0x180028180  mov     esi, edx
0x180028182  cmp     edx, eax
0x180028184  jb      short loc_18002817D
0x180028186  mov     r8d, eax
0x180028189  or      edx, 0FFFFFFFFh; Val
0x18002818c  shr     r8, 2
0x180028190  mov     rcx, r9; void *
0x180028193  shl     r8, 4
0x180028197  and     r8, 0FFFFFFFFFFFFFFFCh; Size
0x18002819b  call    memset_0
0x1800281a0  mov     edx, esi
0x1800281a2  cmp     esi, ebx
0x1800281a4  jnb     short loc_1800281BC
0x1800281a6  mov     rax, [rdi+0A0h]
0x1800281ad  mov     ecx, edx
0x1800281af  inc     edx; unsigned int
0x1800281b1  mov     dword ptr [rax+rcx*4], 0FFFFFFFFh
0x1800281b8  cmp     edx, ebx
0x1800281ba  jb      short loc_1800281A6
0x1800281bc  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800281c3  mov     eax, 8
0x1800281c8  mul     rbx
0x1800281cb  cmovb   rax, rcx
0x1800281cf  mov     ecx, eax; unsigned int
0x1800281d1  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x1800281d6  mov     [rdi+220h], rax
0x1800281dd  test    rax, rax
0x1800281e0  jz      short loc_1800281F4
0x1800281e2  lea     r8, ds:0[rbx*8]; Size
0x1800281ea  xor     edx, edx; Val
0x1800281ec  mov     rcx, rax; void *
0x1800281ef  call    memset_0
0x1800281f4  lea     rcx, [rdi+228h]; this
0x1800281fb  mov     edx, 5; unsigned int
0x180028200  call    ?Reserve@CCollectionList@@QEAAJK@Z; CCollectionList::Reserve(ulong)
0x180028205  mov     ebx, eax
0x180028207  test    eax, eax
0x180028209  js      short loc_18002822D
0x18002820b  movzx   eax, word ptr [rdi+130h]
0x180028212  cmp     qword ptr [rdi+220h], 0
0x18002821a  mov     [rdi+132h], ax
0x180028221  mov     eax, ebx
0x180028223  mov     ebx, 8007000Eh
0x180028228  cmovz   eax, ebx
0x18002822b  mov     ebx, eax
0x18002822d  mov     rsi, [rsp+38h+arg_8]
0x180028232  mov     eax, ebx
0x180028234  mov     rbx, [rsp+38h+arg_0]
0x180028239  add     rsp, 30h
0x18002823d  pop     rdi
0x18002823e  retn
```
