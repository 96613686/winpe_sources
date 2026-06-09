# XT1_WriteGlyphDictEntries

- ea: `0x18004dc54`
- end: `0x18004ddd9`
- name: `XT1_WriteGlyphDictEntries`
- size: `389`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180045e88`
- `0x18004cb44`

## callees

- `0x180001ee0`
- `0x180049e14`
- `0x18004b634`
- `0x18004dc54`
- `0x18004e048`
- `0x18005d010`

## string_xrefs

- `0x18004dcf8`: `GlyphDirectory\n`
- `0x18004dd16`: `ifelse}bind def/!{?{end}if end}bind def/:{string currentfile exch readstring\n`
- `0x18004dcbb`: `/GlyphDirectory %d dict def`

## pseudocode

```c
__int64 __fastcall XT1_WriteGlyphDictEntries(__int64 a1, unsigned int a2, unsigned int *a3, _DWORD *a4)
{
  unsigned int v8; // ebp
  __int64 v9; // r9
  unsigned int i; // esi
  __int64 v11; // rdx
  _BYTE v13[1024]; // [rsp+30h] [rbp-448h] BYREF

  if ( a4 )
    *a4 = 0;
  if ( a2 == -1 )
    v8 = *(_DWORD *)(a1 + 7908);
  else
    v8 = a2;
  if ( *(_WORD *)(a1 + 26088) == 1 )
  {
    v9 = v8;
    if ( a2 != -1 )
      v9 = v8 + 1;
    (*(void (__fastcall **)(_BYTE *, __int64, const char *, __int64))(a1 + 360))(
      v13,
      1024,
      "/GlyphDirectory %d dict def",
      v9);
    PutString(a1, v13);
    PutString(a1, "\r\n");
    PutString(a1, "GlyphDirectory\r\n");
    PutString(a1, "5 dict begin/$ exch def/? $ type/dicttype eq def/|{?{def}{$ 3 1 roll put}\r\n");
    PutString(a1, "ifelse}bind def/!{?{end}if end}bind def/:{string currentfile exch readstring\r\n");
    PutString(a1, "pop}executeonly def ?{$ begin}if\r\n");
    if ( a2 != -1 )
      WriteOneGlyphDictEntry(a1, 0, a4);
  }
  for ( i = 0; (int)i < (int)v8; ++i )
  {
    v11 = i;
    if ( a2 != -1 )
      v11 = *a3;
    if ( (int)v11 > *(_DWORD *)(a1 + 7908) )
      XCF_FatalErrorHandler(a1, 33);
    if ( (*(_BYTE *)(((__int64)(int)v11 >> 3) + *(_QWORD *)(a1 + 26096)) & (unsigned __int8)(1 << (v11 & 7))) == 0 )
      WriteOneGlyphDictEntry(a1, v11, a4);
    if ( a2 != -1 )
      ++a3;
  }
  return PutString(a1, "!\r\n");
}

```

## disassembly

```asm
0x18004dc54  push    rbx
0x18004dc56  push    rbp
0x18004dc57  push    rsi
0x18004dc58  push    rdi
0x18004dc59  push    r12
0x18004dc5b  push    r14
0x18004dc5d  push    r15
0x18004dc5f  sub     rsp, 440h
0x18004dc66  mov     rax, cs:__security_cookie
0x18004dc6d  xor     rax, rsp
0x18004dc70  mov     [rsp+478h+var_48], rax
0x18004dc78  mov     r14, r9
0x18004dc7b  mov     r15, r8
0x18004dc7e  mov     edi, edx
0x18004dc80  mov     rbx, rcx
0x18004dc83  test    r9, r9
0x18004dc86  jz      short loc_18004DC8F
0x18004dc88  mov     dword ptr [r9], 0
0x18004dc8f  cmp     edi, 0FFFFFFFFh
0x18004dc92  jnz     short loc_18004DC9C
0x18004dc94  mov     ebp, [rcx+1EE4h]
0x18004dc9a  jmp     short loc_18004DC9E
0x18004dc9c  mov     ebp, edi
0x18004dc9e  mov     r12d, 1
0x18004dca4  cmp     [rcx+65E8h], r12w
0x18004dcac  jnz     loc_18004DD46
0x18004dcb2  lea     eax, [rbp+1]
0x18004dcb5  mov     r9d, ebp
0x18004dcb8  cmp     edi, 0FFFFFFFFh
0x18004dcbb  lea     r8, aGlyphdirectory_0; "/GlyphDirectory %d dict def"
0x18004dcc2  mov     edx, 400h
0x18004dcc7  lea     rcx, [rsp+478h+var_448]
0x18004dccc  cmovnz  r9d, eax
0x18004dcd0  mov     rax, [rbx+168h]
0x18004dcd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dcdc  lea     rdx, [rsp+478h+var_448]
0x18004dce1  mov     rcx, rbx
0x18004dce4  call    PutString
0x18004dce9  lea     rdx, asc_180062FDC; "\r\n"
0x18004dcf0  mov     rcx, rbx
0x18004dcf3  call    PutString
0x18004dcf8  lea     rdx, aGlyphdirectory; "GlyphDirectory\r\n"
0x18004dcff  mov     rcx, rbx
0x18004dd02  call    PutString
0x18004dd07  lea     rdx, a5DictBeginExch; "5 dict begin/$ exch def/? $ type/dictty"...
0x18004dd0e  mov     rcx, rbx
0x18004dd11  call    PutString
0x18004dd16  lea     rdx, aIfelseBindDefE; "ifelse}bind def/!{?{end}if end}bind def"...
0x18004dd1d  mov     rcx, rbx
0x18004dd20  call    PutString
0x18004dd25  lea     rdx, aPopExecuteonly; "pop}executeonly def ?{$ begin}if\r\n"
0x18004dd2c  mov     rcx, rbx
0x18004dd2f  call    PutString
0x18004dd34  cmp     edi, 0FFFFFFFFh
0x18004dd37  jz      short loc_18004DD46
0x18004dd39  mov     r8, r14
0x18004dd3c  xor     edx, edx
0x18004dd3e  mov     rcx, rbx
0x18004dd41  call    WriteOneGlyphDictEntry
0x18004dd46  xor     esi, esi
0x18004dd48  test    ebp, ebp
0x18004dd4a  jle     short loc_18004DD9A
0x18004dd4c  mov     edx, esi
0x18004dd4e  cmp     edi, 0FFFFFFFFh
0x18004dd51  jz      short loc_18004DD56
0x18004dd53  mov     edx, [r15]
0x18004dd56  cmp     edx, [rbx+1EE4h]
0x18004dd5c  jg      short loc_18004DDCB
0x18004dd5e  mov     rax, [rbx+65F0h]
0x18004dd65  movsxd  rcx, edx
0x18004dd68  sar     rcx, 3
0x18004dd6c  mov     r8b, [rcx+rax]
0x18004dd70  mov     ecx, edx
0x18004dd72  and     ecx, 7
0x18004dd75  mov     eax, r12d
0x18004dd78  shl     eax, cl
0x18004dd7a  test    al, r8b
0x18004dd7d  jnz     short loc_18004DD8A
0x18004dd7f  mov     r8, r14
0x18004dd82  mov     rcx, rbx
0x18004dd85  call    WriteOneGlyphDictEntry
0x18004dd8a  cmp     edi, 0FFFFFFFFh
0x18004dd8d  jz      short loc_18004DD93
0x18004dd8f  add     r15, 4
0x18004dd93  add     esi, r12d
0x18004dd96  cmp     esi, ebp
0x18004dd98  jl      short loc_18004DD4C
0x18004dd9a  lea     rdx, asc_18006B4D8; "!\r\n"
0x18004dda1  mov     rcx, rbx
0x18004dda4  call    PutString
0x18004dda9  mov     rcx, [rsp+478h+var_48]
0x18004ddb1  xor     rcx, rsp; StackCookie
0x18004ddb4  call    __security_check_cookie
0x18004ddb9  add     rsp, 440h
0x18004ddc0  pop     r15
0x18004ddc2  pop     r14
0x18004ddc4  pop     r12
0x18004ddc6  pop     rdi
0x18004ddc7  pop     rsi
0x18004ddc8  pop     rbp
0x18004ddc9  pop     rbx
0x18004ddca  retn
0x18004ddcb  mov     edx, 21h ; '!'
0x18004ddd0  mov     rcx, rbx
0x18004ddd3  call    XCF_FatalErrorHandler
```
