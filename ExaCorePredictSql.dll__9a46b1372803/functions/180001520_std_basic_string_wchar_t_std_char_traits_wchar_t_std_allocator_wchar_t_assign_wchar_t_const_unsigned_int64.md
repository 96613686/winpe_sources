# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)

- ea: `0x180001520`
- end: `0x180001661`
- name: `?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@PEB_W_K@Z`
- size: `321`
- prototype: `__int64 __fastcall(void *, void *Src)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180001000`
- `0x1800011a0`
- `0x180002030`

## callees

- `0x180001520`
- `0x180001670`
- `0x1800017a0`
- `0x1800017c0`
- `0x180004acc`

## pseudocode

```c
unsigned __int64 *__fastcall std::wstring::assign(unsigned __int64 *a1, unsigned __int64 Src, unsigned __int64 a3)
{
  unsigned __int64 *v4; // rsi
  unsigned __int64 *v5; // rbx
  char *v6; // rax
  unsigned __int64 v7; // rax
  void *v9; // rcx
  bool v10; // cf
  unsigned __int64 v11; // rcx

  v4 = (unsigned __int64 *)Src;
  v5 = a1;
  if ( Src )
  {
    Src = a1[3];
    v6 = Src < 8 ? (char *)a1 : (char *)*a1;
    if ( v4 >= (unsigned __int64 *)v6 )
    {
      if ( Src >= 8 )
        a1 = (unsigned __int64 *)*a1;
      a1 = (unsigned __int64 *)((char *)a1 + 2 * v5[2]);
      if ( a1 > v4 )
      {
        if ( Src < 8 )
          v7 = (unsigned __int64)v5;
        else
          v7 = *v5;
        return std::wstring::assign(v5, v5, (__int64)((__int64)v4 - v7) >> 1, a3);
      }
    }
  }
  if ( a3 > 0x7FFFFFFFFFFFFFFELL )
    std::string::_Xlen(a1, Src);
  if ( v5[3] < a3 )
  {
    std::wstring::_Copy(v5, a3, v5[2]);
    if ( !a3 )
      return v5;
LABEL_16:
    if ( v5[3] < 8 )
      v9 = v5;
    else
      v9 = (void *)*v5;
    if ( a3 )
      memcpy_0(v9, v4, 2 * a3);
    v10 = v5[3] < 8;
    v5[2] = a3;
    if ( v10 )
      v11 = (unsigned __int64)v5;
    else
      v11 = *v5;
    *(_WORD *)(v11 + 2 * a3) = 0;
    return v5;
  }
  if ( a3 )
    goto LABEL_16;
  v10 = v5[3] < 8;
  v5[2] = 0;
  if ( v10 )
    *(_WORD *)v5 = 0;
  else
    *(_WORD *)*v5 = 0;
  return v5;
}

```

## disassembly

```asm
0x180001520  mov     [rsp+arg_0], rbx
0x180001525  mov     [rsp+arg_8], rsi
0x18000152a  push    rdi
0x18000152b  sub     rsp, 20h
0x18000152f  mov     rdi, r8
0x180001532  mov     rsi, rdx
0x180001535  mov     rbx, rcx
0x180001538  test    rdx, rdx
0x18000153b  jz      short loc_18000159E
0x18000153d  mov     rdx, [rcx+18h]
0x180001541  cmp     rdx, 8
0x180001545  jb      short loc_18000154C
0x180001547  mov     rax, [rcx]
0x18000154a  jmp     short loc_18000154F
0x18000154c  mov     rax, rbx
0x18000154f  cmp     rsi, rax
0x180001552  jb      short loc_18000159E
0x180001554  cmp     rdx, 8
0x180001558  jb      short loc_18000155D
0x18000155a  mov     rcx, [rcx]
0x18000155d  mov     rax, [rbx+10h]
0x180001561  lea     rcx, [rcx+rax*2]
0x180001565  cmp     rcx, rsi
0x180001568  jbe     short loc_18000159E
0x18000156a  cmp     rdx, 8
0x18000156e  jb      short loc_180001575
0x180001570  mov     rax, [rbx]
0x180001573  jmp     short loc_180001578
0x180001575  mov     rax, rbx
0x180001578  sub     rsi, rax
0x18000157b  mov     r9, rdi
0x18000157e  sar     rsi, 1
0x180001581  mov     rdx, rbx
0x180001584  mov     r8, rsi
0x180001587  mov     rcx, rbx; void *
0x18000158a  mov     rbx, [rsp+28h+arg_0]
0x18000158f  mov     rsi, [rsp+28h+arg_8]
0x180001594  add     rsp, 20h
0x180001598  pop     rdi
0x180001599  jmp     ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18000159e  mov     rax, 7FFFFFFFFFFFFFFEh
0x1800015a8  cmp     rdi, rax
0x1800015ab  ja      loc_18000165B
0x1800015b1  cmp     [rbx+18h], rdi
0x1800015b5  jnb     short loc_1800015D7
0x1800015b7  mov     r8, [rbx+10h]
0x1800015bb  mov     rdx, rdi
0x1800015be  mov     rcx, rbx; Src
0x1800015c1  call    ?_Copy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x1800015c6  test    rdi, rdi
0x1800015c9  jz      short loc_180001648
0x1800015cb  cmp     qword ptr [rbx+18h], 8
0x1800015d0  jb      short loc_18000161B
0x1800015d2  mov     rcx, [rbx]
0x1800015d5  jmp     short loc_18000161E
0x1800015d7  test    rdi, rdi
0x1800015da  jnz     short loc_1800015CB
0x1800015dc  xor     eax, eax
0x1800015de  cmp     qword ptr [rbx+18h], 8
0x1800015e3  mov     [rbx+10h], rax
0x1800015e7  jb      short loc_180001602
0x1800015e9  mov     rcx, [rbx]
0x1800015ec  mov     [rcx], ax
0x1800015ef  mov     rax, rbx
0x1800015f2  mov     rbx, [rsp+28h+arg_0]
0x1800015f7  mov     rsi, [rsp+28h+arg_8]
0x1800015fc  add     rsp, 20h
0x180001600  pop     rdi
0x180001601  retn
0x180001602  mov     [rbx], ax
0x180001605  mov     rcx, rbx
0x180001608  mov     rax, rbx
0x18000160b  mov     rbx, [rsp+28h+arg_0]
0x180001610  mov     rsi, [rsp+28h+arg_8]
0x180001615  add     rsp, 20h
0x180001619  pop     rdi
0x18000161a  retn
0x18000161b  mov     rcx, rbx; void *
0x18000161e  test    rdi, rdi
0x180001621  jz      short loc_18000162F
0x180001623  lea     r8, [rdi+rdi]; Size
0x180001627  mov     rdx, rsi; Src
0x18000162a  call    memcpy_0
0x18000162f  cmp     qword ptr [rbx+18h], 8
0x180001634  mov     [rbx+10h], rdi
0x180001638  jb      short loc_18000163F
0x18000163a  mov     rcx, [rbx]
0x18000163d  jmp     short loc_180001642
0x18000163f  mov     rcx, rbx
0x180001642  xor     eax, eax
0x180001644  mov     [rcx+rdi*2], ax
0x180001648  mov     rsi, [rsp+28h+arg_8]
0x18000164d  mov     rax, rbx
0x180001650  mov     rbx, [rsp+28h+arg_0]
0x180001655  add     rsp, 20h
0x180001659  pop     rdi
0x18000165a  retn
0x18000165b  call    ?_Xlen@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ; std::string::_Xlen(void)
```
