# mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::comparei_str(unsigned __int64,unsigned __int64,ushort const *,unsigned __int64)

- ea: `0x18000ceb0`
- end: `0x18000cf54`
- name: `?comparei_str@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEBAH_K0PEBG0@Z`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001c46c`

## callees

- `0x18000ceb0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000cf04`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000cf04`

## pseudocode

```c
__int64 __fastcall mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::comparei_str(
        unsigned __int64 **a1,
        __int64 a2,
        unsigned __int64 a3,
        const WCHAR *lpString2,
        unsigned __int64 cchCount1)
{
  unsigned __int64 *v5; // rdx
  unsigned __int64 cchCount2; // rdi
  const WCHAR *v7; // r8
  int v8; // eax
  bool v9; // zf
  __int64 result; // rax

  v5 = *a1;
  cchCount2 = a3;
  if ( a3 > **a1 )
    cchCount2 = *v5;
  if ( cchCount2 )
  {
    if ( cchCount1 )
    {
      v7 = (const WCHAR *)v5[3];
      if ( cchCount2 >= cchCount1 )
        v8 = CompareStringW(0x400u, 0x1001u, v7, cchCount1, lpString2, cchCount1);
      else
        v8 = CompareStringW(0x400u, 0x1001u, v7, cchCount2, lpString2, cchCount2);
      v9 = v8 == 2;
      result = (unsigned int)(v8 - 2);
      if ( v9 )
      {
        if ( cchCount2 >= cchCount1 )
          return cchCount2 != cchCount1;
        else
          return 0xFFFFFFFFLL;
      }
    }
    else
    {
      return 1;
    }
  }
  else if ( cchCount1 )
  {
    return 0xFFFFFFFFLL;
  }
  else
  {
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000ceb0  push    rdi
0x18000ceb2  sub     rsp, 30h
0x18000ceb6  mov     rdx, [rcx]
0x18000ceb9  mov     rdi, r8
0x18000cebc  cmp     r8, [rdx]
0x18000cebf  cmova   rdi, [rdx]
0x18000cec3  test    rdi, rdi
0x18000cec6  jz      short loc_18000CF3C
0x18000cec8  mov     [rsp+38h+arg_0], rbx
0x18000cecd  mov     rbx, qword ptr [rsp+38h+cchCount1]
0x18000ced2  test    rbx, rbx
0x18000ced5  jz      short loc_18000CF35
0x18000ced7  mov     r8, [rdx+18h]; lpString1
0x18000cedb  mov     edx, 1001h; dwCmpFlags
0x18000cee0  mov     ecx, 400h; Locale
0x18000cee5  cmp     rdi, rbx
0x18000cee8  jnb     short loc_18000CEF8
0x18000ceea  mov     [rsp+38h+cchCount2], edi
0x18000ceee  mov     [rsp+38h+lpString2], r9
0x18000cef3  mov     r9d, edi
0x18000cef6  jmp     short loc_18000CF04
0x18000cef8  mov     [rsp+38h+cchCount2], ebx; cchCount2
0x18000cefc  mov     [rsp+38h+lpString2], r9; lpString2
0x18000cf01  mov     r9d, ebx; cchCount1
0x18000cf04  call    cs:__imp_CompareStringW
0x18000cf0b  nop     dword ptr [rax+rax+00h]
0x18000cf10  add     eax, 0FFFFFFFEh
0x18000cf13  jnz     short loc_18000CF1F
0x18000cf15  cmp     rdi, rbx
0x18000cf18  jnb     short loc_18000CF2B
0x18000cf1a  mov     eax, 0FFFFFFFFh
0x18000cf1f  mov     rbx, [rsp+38h+arg_0]
0x18000cf24  add     rsp, 30h
0x18000cf28  pop     rdi
0x18000cf29  retn
0x18000cf2b  xor     eax, eax
0x18000cf2d  cmp     rdi, rbx
0x18000cf30  setnz   al
0x18000cf33  jmp     short loc_18000CF1F
0x18000cf35  mov     eax, 1
0x18000cf3a  jmp     short loc_18000CF1F
0x18000cf3c  cmp     qword ptr [rsp+38h+cchCount1], 0
0x18000cf42  jz      short loc_18000CF4B
0x18000cf44  mov     eax, 0FFFFFFFFh
0x18000cf49  jmp     short loc_18000CF24
0x18000cf4b  xor     eax, eax
0x18000cf4d  add     rsp, 30h
0x18000cf51  pop     rdi
0x18000cf52  retn
```
