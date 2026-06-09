# std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>::~vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>(void)

- ea: `0x1800027e4`
- end: `0x180002879`
- name: `??1?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ`
- size: `149`
- prototype: `void __fastcall(char **)`
- caller_count: `9`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180002c50`
- `0x180003210`
- `0x1800047f8`
- `0x18000bd57`
- `0x18000bd69`
- `0x18000bd7b`
- `0x18000be77`
- `0x18000be89`
- `0x18000be9b`

## callees

- `0x1800016f8`
- `0x180002778`
- `0x1800027e4`

## pseudocode

```c
void __fastcall std::vector<std::wstring>::~vector<std::wstring>(char **a1)
{
  char *v1; // rbx
  char *v3; // rsi
  char *v4; // rax
  char *v5; // rcx

  v1 = *a1;
  if ( *a1 )
  {
    v3 = a1[1];
    while ( v1 != v3 )
    {
      std::wstring::~wstring(v1);
      v1 += 32;
    }
    v4 = *a1;
    if ( ((a1[2] - *a1) & 0xFFFFFFFFFFFFFFE0uLL) < 0x1000 )
    {
      v5 = *a1;
    }
    else
    {
      v5 = (char *)*((_QWORD *)v4 - 1);
      if ( (unsigned __int64)(v4 - v5 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v5);
    *a1 = 0;
    a1[1] = 0;
    a1[2] = 0;
  }
}

```

## disassembly

```asm
0x1800027e4  mov     [rsp+arg_0], rbx
0x1800027e9  mov     [rsp+arg_8], rsi
0x1800027ee  push    rdi
0x1800027ef  sub     rsp, 20h
0x1800027f3  mov     rbx, [rcx]
0x1800027f6  mov     rdi, rcx
0x1800027f9  test    rbx, rbx
0x1800027fc  jz      short loc_180002869
0x1800027fe  mov     rsi, [rcx+8]
0x180002802  jmp     short loc_180002810
0x180002804  mov     rcx, rbx
0x180002807  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000280c  add     rbx, 20h ; ' '
0x180002810  cmp     rbx, rsi
0x180002813  jnz     short loc_180002804
0x180002815  mov     rax, [rdi]
0x180002818  mov     rdx, [rdi+10h]
0x18000281c  sub     rdx, rax
0x18000281f  and     rdx, 0FFFFFFFFFFFFFFE0h
0x180002823  cmp     rdx, 1000h
0x18000282a  jb      short loc_18000284A
0x18000282c  mov     rcx, [rax-8]
0x180002830  sub     rax, rcx
0x180002833  sub     rax, 8
0x180002837  cmp     rax, 1Fh
0x18000283b  ja      short loc_180002843
0x18000283d  add     rdx, 27h ; '''
0x180002841  jmp     short loc_18000284D
0x180002843  mov     ecx, 5
0x180002848  int     29h; Win8: RtlFailFast(ecx)
0x18000284a  mov     rcx, rax; Block
0x18000284d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180002852  mov     qword ptr [rdi], 0
0x180002859  mov     qword ptr [rdi+8], 0
0x180002861  mov     qword ptr [rdi+10h], 0
0x180002869  mov     rbx, [rsp+28h+arg_0]
0x18000286e  mov     rsi, [rsp+28h+arg_8]
0x180002873  add     rsp, 20h
0x180002877  pop     rdi
0x180002878  retn
```
