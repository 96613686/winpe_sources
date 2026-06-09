# XT1_WriteGlyphDictEntries

- ea: `0x18004f4e4`
- end: `0x18004f66a`
- name: `XT1_WriteGlyphDictEntries`
- size: `390`
- prototype: `__int64 __fastcall(__int64, signed int, signed int *, _DWORD *)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800477ac`
- `0x18004e3d4`

## callees

- `0x180001f20`
- `0x18004b690`
- `0x18004cebc`
- `0x18004f4e4`
- `0x18004f8e4`
- `0x18005f010`

## string_xrefs

- `0x18004f588`: `GlyphDirectory\n`
- `0x18004f5a6`: `ifelse}bind def/!{?{end}if end}bind def/:{string currentfile exch readstring\n`
- `0x18004f54b`: `/GlyphDirectory %d dict def`

## pseudocode

```c
__int64 __fastcall XT1_WriteGlyphDictEntries(__int64 a1, signed int a2, signed int *a3, _DWORD *a4)
{
  signed int v8; // ebp
  __int64 v9; // r9
  signed int i; // esi
  signed int v11; // edx
  _BYTE v13[1024]; // [rsp+30h] [rbp-448h] BYREF

  if ( a4 )
    *a4 = 0;
  if ( a2 == -1 )
    v8 = *(_DWORD *)(a1 + 7908);
  else
    v8 = a2;
  if ( *(_WORD *)(a1 + 26088) == 1 )
  {
    v9 = (unsigned int)v8;
    if ( a2 != -1 )
      v9 = (unsigned int)(v8 + 1);
    (*(void (__fastcall **)(_BYTE *, __int64, const char *, __int64))(a1 + 360))(
      v13,
      1024,
      "/GlyphDirectory %d dict def",
      v9);
    PutString(a1, (__int64)v13);
    PutString(a1, (__int64)"\r\n");
    PutString(a1, (__int64)"GlyphDirectory\r\n");
    PutString(a1, (__int64)"5 dict begin/$ exch def/? $ type/dicttype eq def/|{?{def}{$ 3 1 roll put}\r\n");
    PutString(a1, (__int64)"ifelse}bind def/!{?{end}if end}bind def/:{string currentfile exch readstring\r\n");
    PutString(a1, (__int64)"pop}executeonly def ?{$ begin}if\r\n");
    if ( a2 != -1 )
      WriteOneGlyphDictEntry(a1, 0, a4);
  }
  for ( i = 0; i < v8; ++i )
  {
    v11 = i;
    if ( a2 != -1 )
      v11 = *a3;
    if ( v11 > *(_DWORD *)(a1 + 7908) )
      XCF_FatalErrorHandler((_JBTYPE *)a1, 33);
    if ( (*(_BYTE *)(((__int64)v11 >> 3) + *(_QWORD *)(a1 + 26096)) & (unsigned __int8)(1 << (v11 & 7))) == 0 )
      WriteOneGlyphDictEntry(a1, v11, a4);
    if ( a2 != -1 )
      ++a3;
  }
  return PutString(a1, (__int64)"!\r\n");
}

```

## disassembly

```asm
0x18004f4e4  push    rbx
0x18004f4e6  push    rbp
0x18004f4e7  push    rsi
0x18004f4e8  push    rdi
0x18004f4e9  push    r12
0x18004f4eb  push    r14
0x18004f4ed  push    r15
0x18004f4ef  sub     rsp, 440h
0x18004f4f6  mov     rax, cs:__security_cookie
0x18004f4fd  xor     rax, rsp
0x18004f500  mov     [rsp+478h+var_48], rax
0x18004f508  mov     r14, r9
0x18004f50b  mov     r15, r8
0x18004f50e  mov     edi, edx
0x18004f510  mov     rbx, rcx
0x18004f513  test    r9, r9
0x18004f516  jz      short loc_18004F51F
0x18004f518  mov     dword ptr [r9], 0
0x18004f51f  cmp     edi, 0FFFFFFFFh
0x18004f522  jnz     short loc_18004F52C
0x18004f524  mov     ebp, [rcx+1EE4h]
0x18004f52a  jmp     short loc_18004F52E
0x18004f52c  mov     ebp, edi
0x18004f52e  mov     r12d, 1
0x18004f534  cmp     [rcx+65E8h], r12w
0x18004f53c  jnz     loc_18004F5D6
0x18004f542  lea     eax, [rbp+1]
0x18004f545  mov     r9d, ebp
0x18004f548  cmp     edi, 0FFFFFFFFh
0x18004f54b  lea     r8, aGlyphdirectory_0; "/GlyphDirectory %d dict def"
0x18004f552  mov     edx, 400h
0x18004f557  lea     rcx, [rsp+478h+var_448]
0x18004f55c  cmovnz  r9d, eax
0x18004f560  mov     rax, [rbx+168h]
0x18004f567  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f56c  lea     rdx, [rsp+478h+var_448]
0x18004f571  mov     rcx, rbx
0x18004f574  call    PutString
0x18004f579  lea     rdx, asc_180064FCC; "\r\n"
0x18004f580  mov     rcx, rbx
0x18004f583  call    PutString
0x18004f588  lea     rdx, aGlyphdirectory; "GlyphDirectory\r\n"
0x18004f58f  mov     rcx, rbx
0x18004f592  call    PutString
0x18004f597  lea     rdx, a5DictBeginExch; "5 dict begin/$ exch def/? $ type/dictty"...
0x18004f59e  mov     rcx, rbx
0x18004f5a1  call    PutString
0x18004f5a6  lea     rdx, aIfelseBindDefE; "ifelse}bind def/!{?{end}if end}bind def"...
0x18004f5ad  mov     rcx, rbx
0x18004f5b0  call    PutString
0x18004f5b5  lea     rdx, aPopExecuteonly; "pop}executeonly def ?{$ begin}if\r\n"
0x18004f5bc  mov     rcx, rbx
0x18004f5bf  call    PutString
0x18004f5c4  cmp     edi, 0FFFFFFFFh
0x18004f5c7  jz      short loc_18004F5D6
0x18004f5c9  mov     r8, r14
0x18004f5cc  xor     edx, edx
0x18004f5ce  mov     rcx, rbx
0x18004f5d1  call    WriteOneGlyphDictEntry
0x18004f5d6  xor     esi, esi
0x18004f5d8  test    ebp, ebp
0x18004f5da  jle     short loc_18004F62A
0x18004f5dc  mov     edx, esi
0x18004f5de  cmp     edi, 0FFFFFFFFh
0x18004f5e1  jz      short loc_18004F5E6
0x18004f5e3  mov     edx, [r15]
0x18004f5e6  cmp     edx, [rbx+1EE4h]
0x18004f5ec  jg      short loc_18004F65C
0x18004f5ee  mov     rax, [rbx+65F0h]
0x18004f5f5  movsxd  rcx, edx
0x18004f5f8  sar     rcx, 3
0x18004f5fc  mov     r8b, [rcx+rax]
0x18004f600  mov     ecx, edx
0x18004f602  and     ecx, 7
0x18004f605  mov     eax, r12d
0x18004f608  shl     eax, cl
0x18004f60a  test    al, r8b
0x18004f60d  jnz     short loc_18004F61A
0x18004f60f  mov     r8, r14
0x18004f612  mov     rcx, rbx
0x18004f615  call    WriteOneGlyphDictEntry
0x18004f61a  cmp     edi, 0FFFFFFFFh
0x18004f61d  jz      short loc_18004F623
0x18004f61f  add     r15, 4
0x18004f623  add     esi, r12d
0x18004f626  cmp     esi, ebp
0x18004f628  jl      short loc_18004F5DC
0x18004f62a  lea     rdx, asc_18006D498; "!\r\n"
0x18004f631  mov     rcx, rbx
0x18004f634  call    PutString
0x18004f639  mov     rcx, [rsp+478h+var_48]
0x18004f641  xor     rcx, rsp; StackCookie
0x18004f644  call    __security_check_cookie
0x18004f649  add     rsp, 440h
0x18004f650  pop     r15
0x18004f652  pop     r14
0x18004f654  pop     r12
0x18004f656  pop     rdi
0x18004f657  pop     rsi
0x18004f658  pop     rbp
0x18004f659  pop     rbx
0x18004f65a  retn
0x18004f65c  mov     edx, 21h ; '!'
0x18004f661  mov     rcx, rbx
0x18004f664  call    XCF_FatalErrorHandler
```
