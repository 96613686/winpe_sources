# mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::compare_str(unsigned __int64,unsigned __int64,ushort const *,unsigned __int64)

- ea: `0x18000d660`
- end: `0x18000d709`
- name: `?compare_str@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEBAH_K0PEBG0@Z`
- size: `169`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002d378`

## callees

- `0x18000d660`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000d6b4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000d6b4`

## pseudocode

```c
__int64 __fastcall mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::compare_str(
        unsigned __int64 **a1,
        __int64 a2,
        unsigned __int64 a3,
        const WCHAR *lpString2,
        unsigned __int64 cchCount1)
{
  unsigned __int64 *v5; // rdx
  unsigned __int64 cchCount2; // rbx
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
        v8 = CompareStringW(0x400u, 0x1000u, v7, cchCount1, lpString2, cchCount1);
      else
        v8 = CompareStringW(0x400u, 0x1000u, v7, cchCount2, lpString2, cchCount2);
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
0x18000d660  push    rbx
0x18000d662  sub     rsp, 30h
0x18000d666  mov     rdx, [rcx]
0x18000d669  mov     rbx, r8
0x18000d66c  cmp     r8, [rdx]
0x18000d66f  cmova   rbx, [rdx]
0x18000d673  test    rbx, rbx
0x18000d676  jz      short loc_18000D6EC
0x18000d678  mov     [rsp+38h+arg_0], rdi
0x18000d67d  mov     rdi, qword ptr [rsp+38h+cchCount1]
0x18000d682  test    rdi, rdi
0x18000d685  jz      short loc_18000D6E5
0x18000d687  mov     r8, [rdx+18h]; lpString1
0x18000d68b  mov     edx, 1000h; dwCmpFlags
0x18000d690  mov     ecx, 400h; Locale
0x18000d695  cmp     rbx, rdi
0x18000d698  jnb     short loc_18000D6A8
0x18000d69a  mov     [rsp+38h+cchCount2], ebx
0x18000d69e  mov     [rsp+38h+lpString2], r9
0x18000d6a3  mov     r9d, ebx
0x18000d6a6  jmp     short loc_18000D6B4
0x18000d6a8  mov     [rsp+38h+cchCount2], edi; cchCount2
0x18000d6ac  mov     [rsp+38h+lpString2], r9; lpString2
0x18000d6b1  mov     r9d, edi; cchCount1
0x18000d6b4  call    cs:__imp_CompareStringW
0x18000d6bb  nop     dword ptr [rax+rax+00h]
0x18000d6c0  add     eax, 0FFFFFFFEh
0x18000d6c3  jnz     short loc_18000D6CF
0x18000d6c5  cmp     rbx, rdi
0x18000d6c8  jnb     short loc_18000D6DB
0x18000d6ca  mov     eax, 0FFFFFFFFh
0x18000d6cf  mov     rdi, [rsp+38h+arg_0]
0x18000d6d4  add     rsp, 30h
0x18000d6d8  pop     rbx
0x18000d6d9  retn
0x18000d6db  xor     eax, eax
0x18000d6dd  cmp     rbx, rdi
0x18000d6e0  setnz   al
0x18000d6e3  jmp     short loc_18000D6CF
0x18000d6e5  mov     eax, 1
0x18000d6ea  jmp     short loc_18000D6CF
0x18000d6ec  cmp     qword ptr [rsp+38h+cchCount1], 0
0x18000d6f2  jz      short loc_18000D700
0x18000d6f4  mov     eax, 0FFFFFFFFh
0x18000d6f9  add     rsp, 30h
0x18000d6fd  pop     rbx
0x18000d6fe  retn
0x18000d700  xor     eax, eax
0x18000d702  add     rsp, 30h
0x18000d706  pop     rbx
0x18000d707  retn
```
