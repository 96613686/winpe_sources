# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)

- ea: `0x140004290`
- end: `0x14000433d`
- name: `??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z`
- size: `173`
- prototype: `__int64 __fastcall(char **, const void *, unsigned __int64)`
- caller_count: `18`
- callee_count: `4`
- tags: ``

## callers

- `0x1400020e0`
- `0x140002120`
- `0x140002160`
- `0x1400022d0`
- `0x140002310`
- `0x140002350`
- `0x140002390`
- `0x1400023d0`
- `0x140002410`
- `0x140002450`
- `0x140007f3c`
- `0x1400097e0`
- `0x14000a120`
- `0x14000f3ec`
- `0x14000f744`
- `0x14000fa3c`
- `0x140010a24`
- `0x140010c94`

## callees

- `0x140004218`
- `0x140004290`
- `0x14000740c`
- `0x14001202c`

## pseudocode

```c
__int64 __fastcall std::wstring::_Construct<1,unsigned short const *>(char **a1, const void *a2, unsigned __int64 a3)
{
  __int64 v3; // rax
  __int64 v7; // rbx
  __int64 result; // rax
  unsigned __int64 v9; // rcx
  char *v10; // rax
  __int64 v11; // rcx
  char *v12; // rdi
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
    v10 = (char *)std::wstring::_Allocate_for_capacity<0>(v9, &v14);
    v11 = v14;
    a1[2] = (char *)a3;
    v12 = v10;
    a1[3] = (char *)v11;
    v13 = 2 * a3;
    *a1 = v10;
    memcpy_0(v10, a2, v13);
    result = 0;
    *(_WORD *)&v12[v13] = 0;
  }
  else
  {
    a1[2] = (char *)a3;
    v7 = 2 * a3;
    a1[3] = (char *)7;
    memcpy_0(a1, a2, 2 * a3);
    result = 0;
    *(_WORD *)((char *)a1 + v7) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x140004290  push    rbx
0x140004292  push    rbp
0x140004293  push    rsi
0x140004294  push    rdi
0x140004295  sub     rsp, 28h
0x140004299  mov     rax, 7FFFFFFFFFFFFFFEh
0x1400042a3  mov     rbx, r8
0x1400042a6  mov     rbp, rdx
0x1400042a9  mov     rsi, rcx
0x1400042ac  cmp     r8, rax
0x1400042af  ja      loc_140004337
0x1400042b5  cmp     rbx, 7
0x1400042b9  ja      short loc_1400042DA
0x1400042bb  mov     [rcx+10h], rbx
0x1400042bf  add     rbx, rbx
0x1400042c2  mov     r8, rbx; Size
0x1400042c5  mov     qword ptr [rcx+18h], 7
0x1400042cd  call    memcpy_0
0x1400042d2  xor     eax, eax
0x1400042d4  mov     [rbx+rsi], ax
0x1400042d8  jmp     short loc_14000432E
0x1400042da  mov     rcx, rbx
0x1400042dd  or      rcx, 7
0x1400042e1  cmp     rcx, rax
0x1400042e4  ja      short loc_1400042F5
0x1400042e6  mov     edx, 0Ah
0x1400042eb  mov     rax, rcx
0x1400042ee  cmp     rcx, rdx
0x1400042f1  cmovb   rax, rdx
0x1400042f5  lea     rdx, [rsp+48h+arg_0]
0x1400042fa  mov     [rsp+48h+arg_0], rax
0x1400042ff  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CAPEAGAEAV?$allocator@G@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<ushort> &,unsigned __int64 &)
0x140004304  mov     rcx, [rsp+48h+arg_0]
0x140004309  mov     rdx, rbp; Src
0x14000430c  mov     [rsi+10h], rbx
0x140004310  mov     rdi, rax
0x140004313  mov     [rsi+18h], rcx
0x140004317  add     rbx, rbx
0x14000431a  mov     rcx, rax; void *
0x14000431d  mov     [rsi], rax
0x140004320  mov     r8, rbx; Size
0x140004323  call    memcpy_0
0x140004328  xor     eax, eax
0x14000432a  mov     [rbx+rdi], ax
0x14000432e  add     rsp, 28h
0x140004332  pop     rdi
0x140004333  pop     rsi
0x140004334  pop     rbp
0x140004335  pop     rbx
0x140004336  retn
0x140004337  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
