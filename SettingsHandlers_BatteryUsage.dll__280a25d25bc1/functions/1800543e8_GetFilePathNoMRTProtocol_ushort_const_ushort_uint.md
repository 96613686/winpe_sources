# GetFilePathNoMRTProtocol(ushort const *,ushort *,uint)

- ea: `0x1800543e8`
- end: `0x1800544b2`
- name: `?GetFilePathNoMRTProtocol@@YAJPEBGPEAGI@Z`
- size: `202`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180052848`

## callees

- `0x18000a8b8`
- `0x1800543e8`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180054469`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180054469`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_FixSlashesAndColonW` at `0x18005448c`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_FixSlashesAndColonW` at `0x18005448c`

## pseudocode

```c
__int64 __fastcall GetFilePathNoMRTProtocol(const unsigned __int16 *a1, unsigned __int16 *a2)
{
  const unsigned __int16 *v4; // rax
  __int64 v5; // r8
  signed int v6; // ebx
  int v7; // edx

  if ( a1 )
  {
    v4 = a1;
    v5 = 260;
    do
    {
      if ( !*v4 )
        break;
      ++v4;
      --v5;
    }
    while ( v5 );
    v6 = v5 == 0 ? 0x80070057 : 0;
    if ( v5 )
    {
      v7 = 11;
      if ( (int)(v5 != 0 ? 260 - v5 : 0) < 11 )
        v7 = v5 != 0 ? 260 - v5 : 0;
      if ( CompareStringOrdinal(a1, v7, L"ms-appx:///", 11, 1) == 2 )
      {
        v6 = StringCchCopyW(a2, 0x104u, a1 + 11);
        if ( v6 >= 0 )
          FixSlashesAndColonW(a2);
      }
      else
      {
        return (unsigned int)StringCchCopyW(a2, 0x104u, a1);
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800543e8  push    rbx
0x1800543ea  push    rbp
0x1800543eb  push    rsi
0x1800543ec  push    rdi
0x1800543ed  push    r14
0x1800543ef  sub     rsp, 30h
0x1800543f3  xor     ebp, ebp
0x1800543f5  mov     rsi, rdx
0x1800543f8  mov     rdi, rcx
0x1800543fb  test    rcx, rcx
0x1800543fe  jz      loc_1800544A0
0x180054404  mov     r14d, 104h
0x18005440a  mov     rax, rcx
0x18005440d  mov     r8d, r14d
0x180054410  cmp     [rax], bp
0x180054413  jz      short loc_18005441F
0x180054415  add     rax, 2
0x180054419  sub     r8, 1
0x18005441d  jnz     short loc_180054410
0x18005441f  mov     rax, r8
0x180054422  mov     rcx, r14
0x180054425  neg     rax
0x180054428  mov     rax, r8
0x18005442b  sbb     ebx, ebx
0x18005442d  sub     rcx, r8
0x180054430  not     ebx
0x180054432  and     ebx, 80070057h
0x180054438  neg     rax
0x18005443b  sbb     r9, r9
0x18005443e  and     r9, rcx
0x180054441  test    r8, r8
0x180054444  jz      short loc_1800544A5
0x180054446  mov     eax, 0Bh
0x18005444b  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x180054453  cmp     r9d, eax
0x180054456  lea     r8, pwzBaseUrl; "ms-appx:///"
0x18005445d  mov     edx, eax
0x18005445f  mov     rcx, rdi; lpString1
0x180054462  cmovl   edx, r9d; cchCount1
0x180054466  mov     r9d, eax; cchCount2
0x180054469  call    cs:__imp_CompareStringOrdinal
0x18005446f  mov     rdx, r14; unsigned __int64
0x180054472  mov     rcx, rsi; unsigned __int16 *
0x180054475  cmp     eax, 2
0x180054478  jnz     short loc_180054494
0x18005447a  lea     r8, [rdi+16h]; unsigned __int16 *
0x18005447e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180054483  mov     ebx, eax
0x180054485  test    eax, eax
0x180054487  js      short loc_1800544A5
0x180054489  mov     rcx, rsi
0x18005448c  call    cs:__imp_FixSlashesAndColonW
0x180054492  jmp     short loc_1800544A5
0x180054494  mov     r8, rdi; unsigned __int16 *
0x180054497  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18005449c  mov     ebx, eax
0x18005449e  jmp     short loc_1800544A5
0x1800544a0  mov     ebx, 80070057h
0x1800544a5  mov     eax, ebx
0x1800544a7  add     rsp, 30h
0x1800544ab  pop     r14
0x1800544ad  pop     rdi
0x1800544ae  pop     rsi
0x1800544af  pop     rbp
0x1800544b0  pop     rbx
0x1800544b1  retn
```
