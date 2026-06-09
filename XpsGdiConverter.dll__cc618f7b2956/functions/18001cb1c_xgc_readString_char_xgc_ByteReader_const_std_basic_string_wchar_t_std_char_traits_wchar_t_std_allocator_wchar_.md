# xgc::readString<char>(xgc::ByteReader const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,uint)

- ea: `0x18001cb1c`
- end: `0x18001cbe0`
- name: `??$readString@D@xgc@@YAXAEBUByteReader@0@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@Z`
- size: `196`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18001f444`
- `0x180020c14`

## callees

- `0x18000d524`
- `0x18001cb1c`
- `0x1800228f0`
- `0x180037278`
- `0x1800372e4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001cbb6`
- `KERNEL32!GetLastError` at `0x18001cbb6`

## pseudocode

```c
_WORD *__fastcall xgc::readString<char>(__int64 **a1, __int64 a2, int a3)
{
  unsigned __int64 v3; // rsi
  _WORD *result; // rax
  unsigned __int64 v7; // rdi
  _WORD *v8; // rbx
  __int64 *v9; // rcx
  const char *v10; // rdx
  __int64 v11; // r8
  xpsrdr *v12; // rcx
  signed int LastError; // eax
  int v14; // edx
  const char *v15; // r8
  int v16; // r9d
  _WORD *Destination; // [rsp+48h] [rbp+10h] BYREF

  v3 = *(_QWORD *)(a2 + 16);
  result = (_WORD *)std::wstring::begin(a2, &Destination);
  v7 = 0;
  if ( v3 )
  {
    v8 = Destination;
    do
    {
      v9 = *a1;
      v10 = (const char *)(unsigned int)(v7 + a3);
      LOBYTE(Destination) = 0;
      v11 = *v9;
      v12 = (xpsrdr *)(v9[1] - *v9);
      if ( v12 < (xpsrdr *)(v10 + 1) )
        xpsrdr::ThrowLogicException(v12, v10, v11);
      if ( memcpy_s(&Destination, 1u, &v10[v11], 1u) )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        if ( LastError >= 0 )
          LastError = -2147467259;
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)LastError, v14, v15, v16);
      }
      result = v8++;
      ++v7;
      *result = (char)Destination;
    }
    while ( v7 < v3 );
  }
  return result;
}

```

## disassembly

```asm
0x18001cb1c  mov     [rsp+arg_0], rbx
0x18001cb21  mov     [rsp+arg_10], rbp
0x18001cb26  push    rsi
0x18001cb27  push    rdi
0x18001cb28  push    r14
0x18001cb2a  sub     rsp, 20h
0x18001cb2e  mov     rsi, [rdx+10h]
0x18001cb32  mov     rax, rdx
0x18001cb35  mov     r14, rcx
0x18001cb38  lea     rdx, [rsp+38h+Destination]
0x18001cb3d  mov     rcx, rax
0x18001cb40  mov     ebp, r8d
0x18001cb43  call    ?begin@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$_String_const_iterator@V?$_String_val@U?$_Simple_types@_W@std@@@std@@@2@XZ; std::wstring::begin(void)
0x18001cb48  xor     edi, edi
0x18001cb4a  test    rsi, rsi
0x18001cb4d  jz      short loc_18001CBA3
0x18001cb4f  mov     rbx, [rsp+38h+Destination]
0x18001cb54  mov     rcx, [r14]
0x18001cb57  lea     eax, [rdi+rbp]
0x18001cb5a  mov     edx, eax; char *
0x18001cb5c  inc     rax
0x18001cb5f  mov     byte ptr [rsp+38h+Destination], 0
0x18001cb64  mov     r8, [rcx]; int
0x18001cb67  mov     rcx, [rcx+8]
0x18001cb6b  sub     rcx, r8; this
0x18001cb6e  cmp     rcx, rax
0x18001cb71  jb      short loc_18001CBDA
0x18001cb73  add     r8, rdx; Source
0x18001cb76  lea     rcx, [rsp+38h+Destination]; Destination
0x18001cb7b  mov     edx, 1; DestinationSize
0x18001cb80  mov     r9d, edx; SourceSize
0x18001cb83  call    memcpy_s
0x18001cb88  test    eax, eax
0x18001cb8a  jnz     short loc_18001CBB6
0x18001cb8c  movsx   ecx, byte ptr [rsp+38h+Destination]
0x18001cb91  mov     rax, rbx
0x18001cb94  add     rbx, 2
0x18001cb98  inc     rdi
0x18001cb9b  mov     [rax], cx
0x18001cb9e  cmp     rdi, rsi
0x18001cba1  jb      short loc_18001CB54
0x18001cba3  mov     rbx, [rsp+38h+arg_0]
0x18001cba8  mov     rbp, [rsp+38h+arg_10]
0x18001cbad  add     rsp, 20h
0x18001cbb1  pop     r14
0x18001cbb3  pop     rdi
0x18001cbb4  pop     rsi
0x18001cbb5  retn
0x18001cbb6  call    cs:__imp_GetLastError
0x18001cbbc  test    eax, eax
0x18001cbbe  jle     short loc_18001CBC8
0x18001cbc0  movzx   eax, ax
0x18001cbc3  or      eax, 80070000h
0x18001cbc8  mov     ecx, 80004005h
0x18001cbcd  test    eax, eax
0x18001cbcf  cmovns  eax, ecx
0x18001cbd2  mov     ecx, eax; this
0x18001cbd4  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18001cbda  call    ?ThrowLogicException@xpsrdr@@YAXPEBDH@Z; xpsrdr::ThrowLogicException(char const *,int)
```
