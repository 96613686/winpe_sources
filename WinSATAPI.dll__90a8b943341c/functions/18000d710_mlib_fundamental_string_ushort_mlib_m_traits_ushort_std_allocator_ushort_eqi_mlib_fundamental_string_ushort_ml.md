# mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::eqi(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18000d710`
- end: `0x18000d79e`
- name: `?eqi@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEBA_NAEBV12@@Z`
- size: `142`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002880`
- `0x18002bfac`

## callees

- `0x18000d710`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000d75c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000d75c`

## pseudocode

```c
bool __fastcall mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::eqi(
        unsigned __int64 **a1,
        unsigned __int64 **a2)
{
  unsigned __int64 v2; // rbx
  const WCHAR *lpString2; // rdx
  unsigned __int64 cchCount2; // rdi
  const WCHAR *v5; // r8
  int v6; // eax
  int v7; // eax

  v2 = **a2;
  lpString2 = (const WCHAR *)(*a2)[3];
  cchCount2 = **a1;
  if ( cchCount2 )
  {
    if ( v2 )
    {
      v5 = (const WCHAR *)(*a1)[3];
      if ( cchCount2 >= v2 )
        v6 = CompareStringW(0x400u, 0x1001u, v5, v2, lpString2, v2);
      else
        v6 = CompareStringW(0x400u, 0x1001u, v5, cchCount2, lpString2, cchCount2);
      v7 = v6 - 2;
      if ( !v7 )
      {
        if ( cchCount2 >= v2 )
          v7 = cchCount2 != v2;
        else
          v7 = -1;
      }
    }
    else
    {
      v7 = 1;
    }
  }
  else
  {
    v7 = -(v2 != 0);
  }
  return v7 == 0;
}

```

## disassembly

```asm
0x18000d710  mov     [rsp+arg_0], rbx
0x18000d715  push    rdi
0x18000d716  sub     rsp, 30h
0x18000d71a  mov     rax, [rdx]
0x18000d71d  mov     rbx, [rax]
0x18000d720  mov     rdx, [rax+18h]
0x18000d724  mov     rax, [rcx]
0x18000d727  mov     rdi, [rax]
0x18000d72a  test    rdi, rdi
0x18000d72d  jz      short loc_18000D788
0x18000d72f  test    rbx, rbx
0x18000d732  jz      short loc_18000D781
0x18000d734  mov     r8, [rax+18h]; lpString1
0x18000d738  mov     ecx, 400h; Locale
0x18000d73d  cmp     rdi, rbx
0x18000d740  jnb     short loc_18000D74B
0x18000d742  mov     [rsp+38h+cchCount2], edi
0x18000d746  mov     r9d, edi
0x18000d749  jmp     short loc_18000D752
0x18000d74b  mov     [rsp+38h+cchCount2], ebx; cchCount2
0x18000d74f  mov     r9d, ebx; cchCount1
0x18000d752  mov     [rsp+38h+lpString2], rdx; lpString2
0x18000d757  mov     edx, 1001h; dwCmpFlags
0x18000d75c  call    cs:__imp_CompareStringW
0x18000d763  nop     dword ptr [rax+rax+00h]
0x18000d768  add     eax, 0FFFFFFFEh
0x18000d76b  jnz     short loc_18000D78D
0x18000d76d  cmp     rdi, rbx
0x18000d770  jnb     short loc_18000D777
0x18000d772  or      eax, 0FFFFFFFFh
0x18000d775  jmp     short loc_18000D78D
0x18000d777  xor     eax, eax
0x18000d779  cmp     rdi, rbx
0x18000d77c  setnz   al
0x18000d77f  jmp     short loc_18000D78D
0x18000d781  mov     eax, 1
0x18000d786  jmp     short loc_18000D78D
0x18000d788  neg     rbx
0x18000d78b  sbb     eax, eax
0x18000d78d  mov     rbx, [rsp+38h+arg_0]
0x18000d792  test    eax, eax
0x18000d794  setz    al
0x18000d797  add     rsp, 30h
0x18000d79b  pop     rdi
0x18000d79c  retn
```
