# mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::findi_str(ushort const *,unsigned __int64,unsigned __int64)

- ea: `0x14002070c`
- end: `0x14002081a`
- name: `?findi_str@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEBA_KPEBG_K1@Z`
- size: `270`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140020664`
- `0x1400335dc`

## callees

- `0x14002070c`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x1400207c5`
- `KERNEL32!CompareStringW` at `0x1400207c5`
- `USER32!CharLowerW` at `0x14002077a`
- `USER32!CharLowerW` at `0x140020785`
- `USER32!CharLowerW` at `0x14002077a`
- `USER32!CharLowerW` at `0x140020785`

## pseudocode

```c
__int64 __fastcall mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::findi_str(
        unsigned __int64 **a1,
        const WCHAR *a2,
        __int64 a3,
        unsigned __int64 a4)
{
  int cchCount2; // r14d
  unsigned __int64 v7; // rbp
  const WCHAR *v8; // r13
  __int64 v9; // rbp
  WCHAR v10; // ax
  __int64 v11; // r15
  const WCHAR *v12; // rsi
  unsigned int v13; // ebx
  WCHAR *v14; // rdi
  __int64 v15; // rcx
  const WCHAR *lpString2; // [rsp+78h] [rbp+10h]
  WCHAR v17; // [rsp+80h] [rbp+18h]

  lpString2 = a2;
  cchCount2 = a4;
  if ( !a4 )
    return 0;
  v7 = **a1;
  if ( a4 <= v7 )
  {
    v8 = (const WCHAR *)(*a1)[3];
    v9 = v7 - a4 + 1;
LABEL_5:
    v10 = *a2;
    v11 = v9;
    v17 = *a2;
    v12 = v8;
    while ( v11 )
    {
      if ( *v12 == v10 || (v13 = *v12, v14 = CharLowerW((LPWSTR)v10), CharLowerW((LPWSTR)v13) == v14) )
      {
        if ( !v12 )
          return -1;
        if ( CompareStringW(0x400u, 0x1001u, v12, cchCount2, lpString2, cchCount2) != 2 )
        {
          a2 = lpString2;
          v15 = (char *)v12 - (char *)v8;
          v8 = v12 + 1;
          v9 += -1 - (v15 >> 1);
          goto LABEL_5;
        }
        return (__int64)((__int64)v12 - (*a1)[3]) >> 1;
      }
      v10 = v17;
      ++v12;
      --v11;
    }
  }
  return -1;
}

```

## disassembly

```asm
0x14002070c  mov     [rsp+arg_0], rbx
0x140020711  mov     [rsp+arg_10], r8
0x140020716  mov     [rsp+arg_8], rdx
0x14002071b  push    rbp
0x14002071c  push    rsi
0x14002071d  push    rdi
0x14002071e  push    r12
0x140020720  push    r13
0x140020722  push    r14
0x140020724  push    r15
0x140020726  sub     rsp, 30h
0x14002072a  mov     r14, r9
0x14002072d  mov     r12, rcx
0x140020730  test    r9, r9
0x140020733  jnz     short loc_14002073C
0x140020735  xor     eax, eax
0x140020737  jmp     loc_140020805
0x14002073c  mov     rax, [rcx]
0x14002073f  mov     rbp, [rax]
0x140020742  cmp     r14, rbp
0x140020745  ja      loc_140020801
0x14002074b  mov     r13, [rax+18h]
0x14002074f  sub     rbp, r14
0x140020752  inc     rbp
0x140020755  movzx   eax, word ptr [rdx]
0x140020758  mov     r15, rbp
0x14002075b  mov     word ptr [rsp+68h+arg_10], ax
0x140020763  mov     rsi, r13
0x140020766  test    r15, r15
0x140020769  jz      loc_140020801
0x14002076f  cmp     [rsi], ax
0x140020772  jz      short loc_1400207A1
0x140020774  movzx   ebx, word ptr [rsi]
0x140020777  movzx   ecx, ax; lpsz
0x14002077a  call    cs:__imp_CharLowerW
0x140020780  mov     ecx, ebx; lpsz
0x140020782  mov     rdi, rax
0x140020785  call    cs:__imp_CharLowerW
0x14002078b  cmp     rax, rdi
0x14002078e  jz      short loc_1400207A1
0x140020790  movzx   eax, word ptr [rsp+68h+arg_10]
0x140020798  add     rsi, 2
0x14002079c  dec     r15
0x14002079f  jmp     short loc_140020766
0x1400207a1  test    rsi, rsi
0x1400207a4  jz      short loc_140020801
0x1400207a6  mov     rax, [rsp+68h+arg_8]
0x1400207ab  mov     r9d, r14d; cchCount1
0x1400207ae  mov     [rsp+68h+cchCount2], r14d; cchCount2
0x1400207b3  mov     r8, rsi; lpString1
0x1400207b6  mov     edx, 1001h; dwCmpFlags
0x1400207bb  mov     [rsp+68h+lpString2], rax; lpString2
0x1400207c0  mov     ecx, 400h; Locale
0x1400207c5  call    cs:__imp_CompareStringW
0x1400207cb  cmp     eax, 2
0x1400207ce  jz      short loc_1400207F1
0x1400207d0  mov     rdx, [rsp+68h+arg_8]
0x1400207d5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400207d9  mov     rcx, rsi
0x1400207dc  sub     rcx, r13
0x1400207df  lea     r13, [rsi+2]
0x1400207e3  sar     rcx, 1
0x1400207e6  sub     rax, rcx
0x1400207e9  add     rbp, rax
0x1400207ec  jmp     loc_140020755
0x1400207f1  mov     rax, [r12]
0x1400207f5  sub     rsi, [rax+18h]
0x1400207f9  sar     rsi, 1
0x1400207fc  mov     rax, rsi
0x1400207ff  jmp     short loc_140020805
0x140020801  or      rax, 0FFFFFFFFFFFFFFFFh
0x140020805  mov     rbx, [rsp+68h+arg_0]
0x14002080a  add     rsp, 30h
0x14002080e  pop     r15
0x140020810  pop     r14
0x140020812  pop     r13
0x140020814  pop     r12
0x140020816  pop     rdi
0x140020817  pop     rsi
0x140020818  pop     rbp
0x140020819  retn
```
