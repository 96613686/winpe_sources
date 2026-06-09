# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)

- ea: `0x14000ebb4`
- end: `0x14000ec61`
- name: `??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z`
- size: `173`
- prototype: `__int64 __fastcall(_QWORD *, const void *, unsigned __int64)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x140007f20`
- `0x140008280`
- `0x1400082c0`
- `0x14000fccc`
- `0x140011ea4`
- `0x140012104`

## callees

- `0x140009527`
- `0x14000d940`
- `0x14000eb3c`
- `0x14000ebb4`

## pseudocode

```c
__int64 __fastcall std::wstring::_Construct<1,wchar_t const *>(_QWORD *a1, const void *a2, unsigned __int64 a3)
{
  __int64 v3; // rax
  __int64 v7; // rbx
  __int64 result; // rax
  unsigned __int64 v9; // rcx
  _QWORD *v10; // rax
  __int64 v11; // rcx
  _QWORD *v12; // rdi
  size_t v13; // rbx
  __int64 v14; // [rsp+50h] [rbp+8h] BYREF

  v3 = 0x7FFFFFFFFFFFFFFELL;
  if ( a3 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlen_string();
  if ( a3 > 7 )
  {
    v9 = a3 | 7;
    if ( (a3 | 7) <= 0x7FFFFFFFFFFFFFFELL )
    {
      v3 = a3 | 7;
      if ( v9 < 0xA )
        v3 = 10;
    }
    v14 = v3;
    v10 = std::wstring::_Allocate_for_capacity<0>(v9, &v14);
    v11 = v14;
    a1[2] = a3;
    v12 = v10;
    a1[3] = v11;
    v13 = 2 * a3;
    *a1 = v10;
    memcpy_0(v10, a2, v13);
    result = 0;
    *(_WORD *)((char *)v12 + v13) = 0;
  }
  else
  {
    a1[2] = a3;
    v7 = 2 * a3;
    a1[3] = 7;
    memcpy_0(a1, a2, 2 * a3);
    result = 0;
    *(_WORD *)((char *)a1 + v7) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x14000ebb4  push    rbx
0x14000ebb6  push    rbp
0x14000ebb7  push    rsi
0x14000ebb8  push    rdi
0x14000ebb9  sub     rsp, 28h
0x14000ebbd  mov     rax, 7FFFFFFFFFFFFFFEh
0x14000ebc7  mov     rbx, r8
0x14000ebca  mov     rbp, rdx
0x14000ebcd  mov     rsi, rcx
0x14000ebd0  cmp     r8, rax
0x14000ebd3  ja      loc_14000EC5B
0x14000ebd9  cmp     rbx, 7
0x14000ebdd  ja      short loc_14000EBFE
0x14000ebdf  mov     [rcx+10h], rbx
0x14000ebe3  add     rbx, rbx
0x14000ebe6  mov     r8, rbx; Size
0x14000ebe9  mov     qword ptr [rcx+18h], 7
0x14000ebf1  call    memcpy_0
0x14000ebf6  xor     eax, eax
0x14000ebf8  mov     [rbx+rsi], ax
0x14000ebfc  jmp     short loc_14000EC52
0x14000ebfe  mov     rcx, rbx
0x14000ec01  or      rcx, 7
0x14000ec05  cmp     rcx, rax
0x14000ec08  ja      short loc_14000EC19
0x14000ec0a  mov     edx, 0Ah
0x14000ec0f  mov     rax, rcx
0x14000ec12  cmp     rcx, rdx
0x14000ec15  cmovb   rax, rdx
0x14000ec19  lea     rdx, [rsp+48h+arg_0]
0x14000ec1e  mov     [rsp+48h+arg_0], rax
0x14000ec23  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@CAPEA_WAEAV?$allocator@_W@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<wchar_t> &,unsigned __int64 &)
0x14000ec28  mov     rcx, [rsp+48h+arg_0]
0x14000ec2d  mov     rdx, rbp; Src
0x14000ec30  mov     [rsi+10h], rbx
0x14000ec34  mov     rdi, rax
0x14000ec37  mov     [rsi+18h], rcx
0x14000ec3b  add     rbx, rbx
0x14000ec3e  mov     rcx, rax; void *
0x14000ec41  mov     [rsi], rax
0x14000ec44  mov     r8, rbx; Size
0x14000ec47  call    memcpy_0
0x14000ec4c  xor     eax, eax
0x14000ec4e  mov     [rbx+rdi], ax
0x14000ec52  add     rsp, 28h
0x14000ec56  pop     rdi
0x14000ec57  pop     rsi
0x14000ec58  pop     rbp
0x14000ec59  pop     rbx
0x14000ec5a  retn
0x14000ec5b  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
