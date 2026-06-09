# std::basic_stringbuf<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::~basic_stringbuf<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(void)

- ea: `0x14000f7d0`
- end: `0x14000f8ba`
- name: `??1?$basic_stringbuf@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UEAA@XZ`
- size: `234`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x14000fb74`
- `0x14000fc00`
- `0x14000fc3c`
- `0x14000fccc`

## callees

- `0x1400088f4`
- `0x14000f7d0`

## import_xrefs

- `msvcp_win!??1?$basic_streambuf@_WU?$char_traits@_W@std@@@std@@UEAA@XZ` at `0x14000f8b3`

## pseudocode

```c
__int64 __fastcall std::wstringbuf::~wstringbuf(__int64 a1)
{
  bool v1; // zf
  __int64 v3; // rdx
  __int64 v4; // rdx
  char **v5; // rax
  char *v6; // rcx
  unsigned __int64 v7; // rdx
  char *v8; // rax

  v1 = (*(_BYTE *)(a1 + 112) & 1) == 0;
  *(_QWORD *)a1 = &std::wstringbuf::`vftable';
  if ( !v1 )
  {
    v3 = **(_QWORD **)(a1 + 64);
    if ( v3 )
      v4 = v3 + 2LL * **(int **)(a1 + 88);
    else
      v4 = **(_QWORD **)(a1 + 56) + 2LL * **(int **)(a1 + 80);
    v5 = *(char ***)(a1 + 24);
    v6 = *v5;
    v7 = 2 * ((v4 - (__int64)*v5) >> 1);
    if ( v7 < 0x1000 )
    {
      v8 = *v5;
    }
    else
    {
      v8 = (char *)*((_QWORD *)v6 - 1);
      if ( (unsigned __int64)(v6 - v8 - 8) > 0x1F )
        __fastfail(5u);
      v7 += 39LL;
    }
    operator delete(v8, v7);
  }
  **(_QWORD **)(a1 + 24) = 0;
  **(_QWORD **)(a1 + 56) = 0;
  **(_DWORD **)(a1 + 80) = 0;
  **(_QWORD **)(a1 + 32) = 0;
  **(_QWORD **)(a1 + 64) = 0;
  **(_DWORD **)(a1 + 88) = 0;
  *(_DWORD *)(a1 + 112) &= ~1u;
  *(_QWORD *)(a1 + 104) = 0;
  return std::wstreambuf::~wstreambuf<wchar_t,std::char_traits<wchar_t>>(a1);
}

```

## disassembly

```asm
0x14000f7d0  mov     [rsp+arg_0], rbx
0x14000f7d5  push    rdi
0x14000f7d6  sub     rsp, 20h
0x14000f7da  test    byte ptr [rcx+70h], 1
0x14000f7de  lea     rax, ??_7?$basic_stringbuf@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@6B@; const std::wstringbuf::`vftable'
0x14000f7e5  mov     [rcx], rax
0x14000f7e8  mov     rbx, rcx
0x14000f7eb  jz      short loc_14000F85A
0x14000f7ed  mov     rax, [rcx+40h]
0x14000f7f1  mov     rdx, [rax]
0x14000f7f4  test    rdx, rdx
0x14000f7f7  jz      short loc_14000F806
0x14000f7f9  mov     rax, [rcx+58h]
0x14000f7fd  movsxd  rcx, dword ptr [rax]
0x14000f800  lea     rdx, [rdx+rcx*2]
0x14000f804  jmp     short loc_14000F818
0x14000f806  mov     rax, [rcx+50h]
0x14000f80a  movsxd  rdx, dword ptr [rax]
0x14000f80d  mov     rax, [rcx+38h]
0x14000f811  mov     rcx, [rax]
0x14000f814  lea     rdx, [rcx+rdx*2]
0x14000f818  mov     rax, [rbx+18h]
0x14000f81c  mov     rcx, [rax]
0x14000f81f  sub     rdx, rcx
0x14000f822  sar     rdx, 1
0x14000f825  add     rdx, rdx; unsigned __int64
0x14000f828  cmp     rdx, 1000h
0x14000f82f  jb      short loc_14000F84F
0x14000f831  mov     rax, [rcx-8]
0x14000f835  sub     rcx, rax
0x14000f838  sub     rcx, 8
0x14000f83c  cmp     rcx, 1Fh
0x14000f840  ja      short loc_14000F848
0x14000f842  add     rdx, 27h ; '''
0x14000f846  jmp     short loc_14000F852
0x14000f848  mov     ecx, 5
0x14000f84d  int     29h; Win8: RtlFailFast(ecx)
0x14000f84f  mov     rax, rcx
0x14000f852  mov     rcx, rax; void *
0x14000f855  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000f85a  mov     rax, [rbx+18h]
0x14000f85e  mov     rcx, rbx
0x14000f861  mov     qword ptr [rax], 0
0x14000f868  mov     rax, [rbx+38h]
0x14000f86c  mov     qword ptr [rax], 0
0x14000f873  mov     rax, [rbx+50h]
0x14000f877  mov     dword ptr [rax], 0
0x14000f87d  mov     rax, [rbx+20h]
0x14000f881  mov     qword ptr [rax], 0
0x14000f888  mov     rax, [rbx+40h]
0x14000f88c  mov     qword ptr [rax], 0
0x14000f893  mov     rax, [rbx+58h]
0x14000f897  mov     dword ptr [rax], 0
0x14000f89d  and     dword ptr [rbx+70h], 0FFFFFFFEh
0x14000f8a1  mov     qword ptr [rbx+68h], 0
0x14000f8a9  mov     rbx, [rsp+28h+arg_0]
0x14000f8ae  add     rsp, 20h
0x14000f8b2  pop     rdi
0x14000f8b3  jmp     cs:__imp_??1?$basic_streambuf@_WU?$char_traits@_W@std@@@std@@UEAA@XZ; std::wstreambuf::~wstreambuf<wchar_t,std::char_traits<wchar_t>>(void)
```
