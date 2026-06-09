# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::assign(char const *,unsigned __int64)

- ea: `0x180001650`
- end: `0x180001747`
- name: `?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z`
- size: `247`
- prototype: `__int64 __fastcall(void *, void *Src, size_t Size)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800018d0`
- `0x180001940`
- `0x1800019d0`

## callees

- `0x180001348`
- `0x1800014d0`
- `0x180001558`
- `0x180001650`
- `0x180002506`

## pseudocode

```c
size_t *__fastcall std::string::assign(size_t *a1, char *Src, size_t Size)
{
  size_t *v5; // rbx
  char *v6; // rax
  void *v8; // rcx
  _BYTE *v9; // rax
  size_t v10; // rax

  v5 = a1;
  if ( Src )
  {
    v6 = a1[3] < 0x10 ? (char *)a1 : (char *)*a1;
    if ( Src >= v6 )
    {
      if ( a1[3] >= 0x10 )
        a1 = (size_t *)*a1;
      if ( (char *)a1 + v5[2] > Src )
        return (size_t *)std::string::assign(v5);
    }
  }
  if ( Size == -1 )
    std::string::_Xlen(v5);
  if ( v5[3] >= Size )
  {
    if ( !Size )
    {
      if ( v5[3] < 0x10 )
        v9 = v5;
      else
        v9 = (_BYTE *)*v5;
      v5[2] = 0;
      *v9 = 0;
      return v5;
    }
    goto LABEL_13;
  }
  std::string::_Copy((const void **)v5, Size, v5[2]);
  if ( Size )
  {
LABEL_13:
    if ( v5[3] < 0x10 )
      v8 = v5;
    else
      v8 = (void *)*v5;
    memcpy_0(v8, Src, Size);
    if ( v5[3] < 0x10 )
      v10 = (size_t)v5;
    else
      v10 = *v5;
    v5[2] = Size;
    *(_BYTE *)(v10 + Size) = 0;
  }
  return v5;
}

```

## disassembly

```asm
0x180001650  mov     [rsp+arg_0], rbx
0x180001655  mov     [rsp+arg_8], rsi
0x18000165a  push    rdi
0x18000165b  sub     rsp, 20h
0x18000165f  mov     rdi, r8
0x180001662  mov     rsi, rdx
0x180001665  mov     rbx, rcx
0x180001668  test    rdx, rdx
0x18000166b  jz      short loc_1800016B9
0x18000166d  cmp     qword ptr [rcx+18h], 10h
0x180001672  jb      short loc_180001679
0x180001674  mov     rax, [rcx]
0x180001677  jmp     short loc_18000167C
0x180001679  mov     rax, rbx
0x18000167c  cmp     rsi, rax
0x18000167f  jb      short loc_1800016B9
0x180001681  cmp     qword ptr [rcx+18h], 10h
0x180001686  jb      short loc_18000168B
0x180001688  mov     rcx, [rcx]
0x18000168b  add     rcx, [rbx+10h]
0x18000168f  cmp     rcx, rsi
0x180001692  jbe     short loc_1800016B9
0x180001694  cmp     qword ptr [rbx+18h], 10h
0x180001699  jb      short loc_1800016A0
0x18000169b  mov     rax, [rbx]
0x18000169e  jmp     short loc_1800016A3
0x1800016a0  mov     rax, rbx
0x1800016a3  sub     rsi, rax
0x1800016a6  mov     r9, rdi
0x1800016a9  mov     r8, rsi
0x1800016ac  mov     rdx, rbx
0x1800016af  mov     rcx, rbx; void *
0x1800016b2  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::string::assign(std::string const &,unsigned __int64,unsigned __int64)
0x1800016b7  jmp     short loc_18000172E
0x1800016b9  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x1800016bd  ja      short loc_18000173E
0x1800016bf  cmp     [rbx+18h], rdi
0x1800016c3  jnb     short loc_1800016E5
0x1800016c5  mov     r8, [rbx+10h]
0x1800016c9  mov     rdx, rdi
0x1800016cc  mov     rcx, rbx; Src
0x1800016cf  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x1800016d4  test    rdi, rdi
0x1800016d7  jz      short loc_18000172B
0x1800016d9  cmp     qword ptr [rbx+18h], 10h
0x1800016de  jb      short loc_180001706
0x1800016e0  mov     rcx, [rbx]
0x1800016e3  jmp     short loc_180001709
0x1800016e5  test    rdi, rdi
0x1800016e8  jnz     short loc_1800016D9
0x1800016ea  cmp     qword ptr [rbx+18h], 10h
0x1800016ef  jb      short loc_1800016F6
0x1800016f1  mov     rax, [rbx]
0x1800016f4  jmp     short loc_1800016F9
0x1800016f6  mov     rax, rbx
0x1800016f9  mov     qword ptr [rbx+10h], 0
0x180001701  mov     byte ptr [rax], 0
0x180001704  jmp     short loc_18000172B
0x180001706  mov     rcx, rbx; void *
0x180001709  mov     r8, rdi; Size
0x18000170c  mov     rdx, rsi; Src
0x18000170f  call    memcpy_0
0x180001714  cmp     qword ptr [rbx+18h], 10h
0x180001719  jb      short loc_180001720
0x18000171b  mov     rax, [rbx]
0x18000171e  jmp     short loc_180001723
0x180001720  mov     rax, rbx
0x180001723  mov     [rbx+10h], rdi
0x180001727  mov     byte ptr [rax+rdi], 0
0x18000172b  mov     rax, rbx
0x18000172e  mov     rbx, [rsp+28h+arg_0]
0x180001733  mov     rsi, [rsp+28h+arg_8]
0x180001738  add     rsp, 20h
0x18000173c  pop     rdi
0x18000173d  retn
0x18000173e  mov     rcx, rbx
0x180001741  call    ?_Xlen@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ; std::string::_Xlen(void)
```
