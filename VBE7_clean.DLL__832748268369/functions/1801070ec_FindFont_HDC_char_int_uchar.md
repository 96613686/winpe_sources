# FindFont(HDC__ *,char *,int,uchar)

- ea: `0x1801070ec`
- end: `0x180107248`
- name: `?FindFont@@YAPEAUHFONT__@@PEAUHDC__@@PEADHE@Z`
- size: `348`
- prototype: `HFONT __fastcall(HDC, char *, int, unsigned __int8)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1801063cc`

## callees

- `0x1801070ec`
- `0x180379520`

## import_xrefs

- `MSVCR100!_mbsnicmp` at `0x18010720f`
- `MSVCR100!_mbsnicmp` at `0x18010720f`
- `MSVCR100!_mbsnbcpy_s` at `0x18010715f`
- `MSVCR100!_mbsnbcpy_s` at `0x18010715f`
- `GDI32!GetTextFaceA` at `0x1801071c1`
- `GDI32!GetTextFaceA` at `0x1801071c1`
- `GDI32!SelectObject` at `0x18010718a`
- `GDI32!SelectObject` at `0x1801071d0`
- `GDI32!SelectObject` at `0x18010718a`
- `GDI32!SelectObject` at `0x1801071d0`
- `GDI32!CreateFontIndirectA` at `0x18010716a`
- `GDI32!CreateFontIndirectA` at `0x18010716a`
- `GDI32!DeleteObject` at `0x1801071a2`
- `GDI32!DeleteObject` at `0x18010721e`
- `GDI32!DeleteObject` at `0x1801071a2`
- `GDI32!DeleteObject` at `0x18010721e`

## pseudocode

```c
HFONT __fastcall FindFont(HDC a1, char *a2, LONG a3, BYTE a4)
{
  HFONT h; // [rsp+20h] [rbp-80h]
  size_t MaxCount; // [rsp+28h] [rbp-78h]
  HGDIOBJ v7; // [rsp+30h] [rbp-70h]
  LOGFONTA lf; // [rsp+40h] [rbp-60h] BYREF

  memset(&lf, 0, sizeof(lf));
  lf.lfHeight = a3;
  lf.lfCharSet = a4;
  _mbsnbcpy_s((unsigned __int8 *)lf.lfFaceName, 0x20u, (const unsigned __int8 *)a2, 0x1Fu);
  h = CreateFontIndirectA(&lf);
  if ( h )
  {
    v7 = SelectObject(a1, h);
    if ( !v7 )
      goto LABEL_6;
    GetTextFaceA(a1, 32, lf.lfFaceName);
    SelectObject(a1, v7);
    MaxCount = -1;
    do
      ++MaxCount;
    while ( lf.lfFaceName[MaxCount] );
    if ( _mbsnicmp((const unsigned __int8 *)lf.lfFaceName, (const unsigned __int8 *)a2, MaxCount) )
    {
LABEL_6:
      DeleteObject(h);
      return 0;
    }
  }
  return h;
}

```

## disassembly

```asm
0x1801070ec  mov     [rsp-8+arg_18], r9b
0x1801070f1  mov     [rsp-8+arg_10], r8d
0x1801070f6  mov     [rsp-8+Src], rdx
0x1801070fb  mov     [rsp-8+hdc], rcx
0x180107100  push    rbp
0x180107101  mov     rbp, rsp
0x180107104  push    rdi
0x180107105  sub     rsp, 98h
0x18010710c  mov     rax, cs:__security_cookie
0x180107113  xor     rax, rsp
0x180107116  mov     [rbp+var_20], rax
0x18010711a  mov     [rsp+0A0h+h], 0
0x180107123  mov     [rsp+0A0h+var_70], 0
0x18010712c  lea     rax, [rsp+0A0h+lf]
0x180107131  mov     rdi, rax
0x180107134  xor     eax, eax
0x180107136  mov     ecx, 3Ch ; '<'
0x18010713b  rep stosb
0x18010713d  mov     eax, [rbp+arg_10]
0x180107140  mov     [rsp+0A0h+lf.lfHeight], eax
0x180107144  mov     al, [rbp+arg_18]
0x180107147  mov     [rsp+0A0h+lf.lfCharSet], al
0x18010714b  mov     r9d, 1Fh; MaxCount
0x180107151  mov     r8, [rbp+Src]; Src
0x180107155  mov     edx, 20h ; ' '; SizeInBytes
0x18010715a  lea     rcx, [rsp+0A0h+lf.lfFaceName]; Dst
0x18010715f  call    cs:__imp__mbsnbcpy_s
0x180107165  lea     rcx, [rsp+0A0h+lf]; lplf
0x18010716a  call    cs:__imp_CreateFontIndirectA
0x180107170  mov     [rsp+0A0h+h], rax
0x180107175  cmp     [rsp+0A0h+h], 0
0x18010717b  jz      loc_18010722D
0x180107181  mov     rdx, [rsp+0A0h+h]; h
0x180107186  mov     rcx, [rbp+hdc]; hdc
0x18010718a  call    cs:__imp_SelectObject
0x180107190  mov     [rsp+0A0h+var_70], rax
0x180107195  cmp     [rsp+0A0h+var_70], 0
0x18010719b  jnz     short loc_1801071B3
0x18010719d  mov     rcx, [rsp+0A0h+h]; ho
0x1801071a2  call    cs:__imp_DeleteObject
0x1801071a8  mov     [rsp+0A0h+h], 0
0x1801071b1  jmp     short loc_18010722D
0x1801071b3  lea     r8, [rsp+0A0h+lf.lfFaceName]; lpName
0x1801071b8  mov     edx, 20h ; ' '; c
0x1801071bd  mov     rcx, [rbp+hdc]; hdc
0x1801071c1  call    cs:__imp_GetTextFaceA
0x1801071c7  mov     rdx, [rsp+0A0h+var_70]; h
0x1801071cc  mov     rcx, [rbp+hdc]; hdc
0x1801071d0  call    cs:__imp_SelectObject
0x1801071d6  lea     rax, [rsp+0A0h+lf.lfFaceName]
0x1801071db  mov     [rsp+0A0h+var_68], rax
0x1801071e0  mov     [rsp+0A0h+MaxCount], 0FFFFFFFFFFFFFFFFh
0x1801071e9  inc     [rsp+0A0h+MaxCount]
0x1801071ee  mov     rax, [rsp+0A0h+var_68]
0x1801071f3  mov     rcx, [rsp+0A0h+MaxCount]
0x1801071f8  cmp     byte ptr [rax+rcx], 0
0x1801071fc  jnz     short loc_1801071E9
0x1801071fe  mov     rax, [rsp+0A0h+MaxCount]
0x180107203  mov     r8, rax; MaxCount
0x180107206  mov     rdx, [rbp+Src]; Str2
0x18010720a  lea     rcx, [rsp+0A0h+lf.lfFaceName]; Str1
0x18010720f  call    cs:__imp__mbsnicmp
0x180107215  test    eax, eax
0x180107217  jz      short loc_18010722D
0x180107219  mov     rcx, [rsp+0A0h+h]; ho
0x18010721e  call    cs:__imp_DeleteObject
0x180107224  mov     [rsp+0A0h+h], 0
0x18010722d  mov     rax, [rsp+0A0h+h]
0x180107232  mov     rcx, [rbp+var_20]
0x180107236  xor     rcx, rsp; StackCookie
0x180107239  call    __security_check_cookie
0x18010723e  add     rsp, 98h
0x180107245  pop     rdi
0x180107246  pop     rbp
0x180107247  retn
```
