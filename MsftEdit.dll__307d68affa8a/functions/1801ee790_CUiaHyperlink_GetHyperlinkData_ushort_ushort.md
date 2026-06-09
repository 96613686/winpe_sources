# CUiaHyperlink::GetHyperlinkData(ushort * *,ushort * *)

- ea: `0x1801ee790`
- end: `0x1801ee8ce`
- name: `?GetHyperlinkData@CUiaHyperlink@@QEAAJPEAPEAG0@Z`
- size: `318`
- prototype: `int(CUiaHyperlink *__hidden this, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1801eebd0`
- `0x1801eecac`
- `0x1801eef90`

## callees

- `0x180021928`
- `0x180021b88`
- `0x180109178`
- `0x1801ee578`
- `0x1801ee790`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1801ee822`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1801ee822`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801ee80d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801ee80d`

## string_xrefs

- `0x1801ee800`: `HYPERLINK "`

## pseudocode

```c
__int64 __fastcall CUiaHyperlink::GetHyperlinkData(CUiaHyperlink *this, unsigned __int16 **a2, unsigned __int16 **a3)
{
  signed int LinkText; // ebx
  LPCWCH v6; // rbp
  const unsigned __int16 *v7; // r14
  wchar_t *v8; // rax
  wchar_t *v9; // rbp
  const unsigned __int16 *i; // rcx
  unsigned __int16 *v11; // rax
  unsigned __int16 *v12; // rcx
  LPCWCH lpString2; // [rsp+58h] [rbp+10h] BYREF

  if ( a2 )
    *a2 = 0;
  if ( a3 )
    *a3 = 0;
  lpString2 = 0;
  LinkText = CUiaHyperlink::GetLinkText(this, (unsigned __int16 **)&lpString2);
  if ( LinkText >= 0 )
  {
    LinkText = 0;
    v6 = lpString2 + 1;
    if ( *lpString2 != 0xFDDF )
      v6 = lpString2;
    if ( CompareStringOrdinal(L"HYPERLINK \"", -1, v6, 11, 1) == 2 )
    {
      v7 = v6 + 11;
      v8 = wcschr(v6 + 11, 0x22u);
      v9 = v8;
      if ( v8 )
      {
        for ( i = v8 + 1; *i == 32; ++i )
          ;
        if ( a2 )
          LinkText = HrSysAllocString(i, a2);
        if ( a3 )
        {
          v11 = CW32System::SysAllocStringLen(v7, v9 - v7);
          *a3 = v11;
          LinkText = v11 == 0 ? 0x8007000E : 0;
        }
      }
      else
      {
        LinkText = -2147467259;
      }
    }
    else
    {
      if ( a2 )
        LinkText = HrSysAllocString(v6, a2);
      if ( a3 )
        LinkText = HrSysAllocString(v6, a3);
    }
  }
  v12 = (unsigned __int16 *)lpString2;
  if ( lpString2 )
  {
    lpString2 = 0;
    CW32System::SysFreeString(v12);
  }
  return (unsigned int)LinkText;
}

```

## disassembly

```asm
0x1801ee790  mov     [rsp+arg_0], rbx
0x1801ee795  mov     [rsp+arg_10], rbp
0x1801ee79a  push    rsi
0x1801ee79b  push    rdi
0x1801ee79c  push    r14
0x1801ee79e  sub     rsp, 30h
0x1801ee7a2  mov     rdi, r8
0x1801ee7a5  mov     rsi, rdx
0x1801ee7a8  test    rdx, rdx
0x1801ee7ab  jz      short loc_1801EE7B4
0x1801ee7ad  mov     qword ptr [rdx], 0
0x1801ee7b4  test    rdi, rdi
0x1801ee7b7  jz      short loc_1801EE7C0
0x1801ee7b9  mov     qword ptr [r8], 0
0x1801ee7c0  lea     rdx, [rsp+48h+lpString2]; unsigned __int16 **
0x1801ee7c5  mov     [rsp+48h+lpString2], 0
0x1801ee7ce  call    ?GetLinkText@CUiaHyperlink@@QEAAJPEAPEAG@Z; CUiaHyperlink::GetLinkText(ushort * *)
0x1801ee7d3  mov     ebx, eax
0x1801ee7d5  test    eax, eax
0x1801ee7d7  js      loc_1801EE8A1
0x1801ee7dd  mov     rax, [rsp+48h+lpString2]
0x1801ee7e2  xor     ebx, ebx
0x1801ee7e4  mov     ecx, 0FDDFh
0x1801ee7e9  mov     [rsp+48h+bIgnoreCase], 1; bIgnoreCase
0x1801ee7f1  cmp     [rax], cx
0x1801ee7f4  lea     rbp, [rax+2]
0x1801ee7f8  lea     r9d, [rbx+0Bh]; cchCount2
0x1801ee7fc  cmovnz  rbp, rax
0x1801ee800  lea     rcx, ?cszLinkPrefix@@3QBGB; "HYPERLINK \""
0x1801ee807  mov     r8, rbp; lpString2
0x1801ee80a  or      edx, 0FFFFFFFFh; cchCount1
0x1801ee80d  call    cs:__imp_CompareStringOrdinal
0x1801ee813  cmp     eax, 2
0x1801ee816  jnz     short loc_1801EE87D
0x1801ee818  lea     r14, [rbp+16h]
0x1801ee81c  mov     rcx, r14; Str
0x1801ee81f  lea     edx, [rbx+22h]; Ch
0x1801ee822  call    cs:__imp_wcschr
0x1801ee828  mov     rbp, rax
0x1801ee82b  test    rax, rax
0x1801ee82e  jz      short loc_1801EE876
0x1801ee830  lea     rcx, [rax+2]
0x1801ee834  jmp     short loc_1801EE83A
0x1801ee836  add     rcx, 2; unsigned __int16 *
0x1801ee83a  cmp     word ptr [rcx], 20h ; ' '
0x1801ee83e  jz      short loc_1801EE836
0x1801ee840  test    rsi, rsi
0x1801ee843  jz      short loc_1801EE84F
0x1801ee845  mov     rdx, rsi; unsigned __int16 **
0x1801ee848  call    ?HrSysAllocString@@YAJPEBGPEAPEAG@Z; HrSysAllocString(ushort const *,ushort * *)
0x1801ee84d  mov     ebx, eax
0x1801ee84f  test    rdi, rdi
0x1801ee852  jz      short loc_1801EE8A1
0x1801ee854  sub     rbp, r14
0x1801ee857  mov     rcx, r14; unsigned __int16 *
0x1801ee85a  sar     rbp, 1
0x1801ee85d  mov     edx, ebp; unsigned int
0x1801ee85f  call    ?SysAllocStringLen@CW32System@@SAPEAGPEBGI@Z; CW32System::SysAllocStringLen(ushort const *,uint)
0x1801ee864  mov     [rdi], rax
0x1801ee867  neg     rax
0x1801ee86a  sbb     ebx, ebx
0x1801ee86c  not     ebx
0x1801ee86e  and     ebx, 8007000Eh
0x1801ee874  jmp     short loc_1801EE8A1
0x1801ee876  mov     ebx, 80004005h
0x1801ee87b  jmp     short loc_1801EE8A1
0x1801ee87d  test    rsi, rsi
0x1801ee880  jz      short loc_1801EE88F
0x1801ee882  mov     rdx, rsi; unsigned __int16 **
0x1801ee885  mov     rcx, rbp; unsigned __int16 *
0x1801ee888  call    ?HrSysAllocString@@YAJPEBGPEAPEAG@Z; HrSysAllocString(ushort const *,ushort * *)
0x1801ee88d  mov     ebx, eax
0x1801ee88f  test    rdi, rdi
0x1801ee892  jz      short loc_1801EE8A1
0x1801ee894  mov     rdx, rdi; unsigned __int16 **
0x1801ee897  mov     rcx, rbp; unsigned __int16 *
0x1801ee89a  call    ?HrSysAllocString@@YAJPEBGPEAPEAG@Z; HrSysAllocString(ushort const *,ushort * *)
0x1801ee89f  mov     ebx, eax
0x1801ee8a1  mov     rcx, [rsp+48h+lpString2]; unsigned __int16 *
0x1801ee8a6  test    rcx, rcx
0x1801ee8a9  jz      short loc_1801EE8B9
0x1801ee8ab  mov     [rsp+48h+lpString2], 0
0x1801ee8b4  call    ?SysFreeString@CW32System@@SAXPEAG@Z; CW32System::SysFreeString(ushort *)
0x1801ee8b9  mov     rbp, [rsp+48h+arg_10]
0x1801ee8be  mov     eax, ebx
0x1801ee8c0  mov     rbx, [rsp+48h+arg_0]
0x1801ee8c5  add     rsp, 30h
0x1801ee8c9  pop     r14
0x1801ee8cb  pop     rdi
0x1801ee8cc  pop     rsi
0x1801ee8cd  retn
```
