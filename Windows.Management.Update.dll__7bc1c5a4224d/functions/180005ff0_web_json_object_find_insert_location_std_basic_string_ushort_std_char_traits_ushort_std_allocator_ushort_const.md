# web::json::object::find_insert_location(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180005ff0`
- end: `0x1800060f7`
- name: `?find_insert_location@object@json@web@@AEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@@std@@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@5@@Z`
- size: `263`
- prototype: `_QWORD *__fastcall(__int64 *, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800050b0`

## callees

- `0x1800036b0`
- `0x180005ff0`
- `0x180023098`

## pseudocode

```c
_QWORD *__fastcall web::json::object::find_insert_location(__int64 *a1, _QWORD *a2, __int64 a3)
{
  __int64 v4; // rbx
  __int64 v6; // rdi
  const wchar_t *v7; // rdx
  const wchar_t *v8; // rcx
  size_t v9; // r8
  unsigned __int64 v10; // rdi
  unsigned __int64 v11; // rdi

  v4 = *a1;
  v6 = a1[1];
  if ( *((_BYTE *)a1 + 24) )
  {
    for ( ; v4 != v6; v4 += 40 )
    {
      if ( *(_QWORD *)(a3 + 24) <= 7u )
        v7 = (const wchar_t *)a3;
      else
        v7 = *(const wchar_t **)a3;
      if ( *(_QWORD *)(v4 + 24) <= 7u )
        v8 = (const wchar_t *)v4;
      else
        v8 = *(const wchar_t **)v4;
      v9 = *(_QWORD *)(v4 + 16);
      if ( v9 == *(_QWORD *)(a3 + 16) && (!v9 || !wmemcmp(v8, v7, v9)) )
        break;
    }
  }
  else
  {
    v10 = (__int64)((unsigned __int128)((v6 - v4) * (__int128)0x6666666666666667LL) >> 64) >> 4;
    v11 = (v10 >> 63) + v10;
    while ( (__int64)v11 > 0 )
    {
      if ( (unsigned __int8)std::operator<<unsigned short>(v4 + 40 * (v11 >> 1), a3) )
      {
        v4 += 40 * (v11 >> 1) + 40;
        v11 += -1LL - (v11 >> 1);
      }
      else
      {
        v11 >>= 1;
      }
    }
  }
  *a2 = v4;
  return a2;
}

```

## disassembly

```asm
0x180005ff0  mov     [rsp+arg_10], rbx
0x180005ff5  push    rdi
0x180005ff6  push    r14
0x180005ff8  push    r15
0x180005ffa  sub     rsp, 20h
0x180005ffe  cmp     byte ptr [rcx+18h], 0
0x180006002  mov     r14, r8
0x180006005  mov     rbx, [rcx]
0x180006008  mov     r15, rdx
0x18000600b  mov     rdi, [rcx+8]
0x18000600f  jz      short loc_180006069
0x180006011  cmp     rbx, rdi
0x180006014  jz      loc_1800060E2
0x18000601a  nop     word ptr [rax+rax+00h]
0x180006020  cmp     qword ptr [r14+18h], 7
0x180006025  jbe     short loc_18000602C
0x180006027  mov     rdx, [r14]
0x18000602a  jmp     short loc_18000602F
0x18000602c  mov     rdx, r14; S2
0x18000602f  cmp     qword ptr [rbx+18h], 7
0x180006034  jbe     short loc_18000603B
0x180006036  mov     rcx, [rbx]
0x180006039  jmp     short loc_18000603E
0x18000603b  mov     rcx, rbx; S1
0x18000603e  mov     r8, [rbx+10h]; N
0x180006042  cmp     r8, [r14+10h]
0x180006046  jnz     short loc_18000605E
0x180006048  test    r8, r8
0x18000604b  jz      loc_1800060E2
0x180006051  call    wmemcmp
0x180006056  test    eax, eax
0x180006058  jz      loc_1800060E2
0x18000605e  add     rbx, 28h ; '('
0x180006062  cmp     rbx, rdi
0x180006065  jnz     short loc_180006020
0x180006067  jmp     short loc_1800060E2
0x180006069  sub     rdi, rbx
0x18000606c  mov     rax, 6666666666666667h
0x180006076  imul    rdi
0x180006079  mov     rdi, rdx
0x18000607c  sar     rdi, 4
0x180006080  mov     rax, rdi
0x180006083  shr     rax, 3Fh
0x180006087  add     rdi, rax
0x18000608a  test    rdi, rdi
0x18000608d  jle     short loc_1800060E2
0x18000608f  mov     [rsp+38h+arg_0], rbp
0x180006094  mov     [rsp+38h+arg_8], rsi
0x180006099  nop     dword ptr [rax+00000000h]
0x1800060a0  mov     rsi, rdi
0x1800060a3  mov     rdx, r14
0x1800060a6  shr     rsi, 1
0x1800060a9  lea     rax, [rsi+rsi*4]
0x1800060ad  lea     rbp, [rbx+rax*8]
0x1800060b1  mov     rcx, rbp
0x1800060b4  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x1800060b9  test    al, al
0x1800060bb  jz      short loc_1800060D0
0x1800060bd  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800060c4  lea     rbx, [rbp+28h]
0x1800060c8  sub     rax, rsi
0x1800060cb  add     rdi, rax
0x1800060ce  jmp     short loc_1800060D3
0x1800060d0  mov     rdi, rsi
0x1800060d3  test    rdi, rdi
0x1800060d6  jg      short loc_1800060A0
0x1800060d8  mov     rsi, [rsp+38h+arg_8]
0x1800060dd  mov     rbp, [rsp+38h+arg_0]
0x1800060e2  mov     [r15], rbx
0x1800060e5  mov     rax, r15
0x1800060e8  mov     rbx, [rsp+38h+arg_10]
0x1800060ed  add     rsp, 20h
0x1800060f1  pop     r15
0x1800060f3  pop     r14
0x1800060f5  pop     rdi
0x1800060f6  retn
```
