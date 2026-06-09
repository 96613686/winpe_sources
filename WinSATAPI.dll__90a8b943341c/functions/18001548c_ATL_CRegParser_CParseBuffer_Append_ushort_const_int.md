# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x18001548c`
- end: `0x180015581`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `245`
- prototype: `int(ATL::CRegParser::CParseBuffer *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180018330`

## callees

- `0x18001548c`
- `0x180015728`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18001553b`
- `msvcrt!memcpy_s` at `0x18001553b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800154f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800154f8`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::CParseBuffer::Append(
        ATL::CRegParser::CParseBuffer *this,
        const unsigned __int16 *a2,
        int a3)
{
  int v6; // ecx
  int v7; // ebx
  unsigned __int64 v8; // rax
  LPVOID v9; // rax
  int v10; // edx
  errno_t v11; // eax

  v6 = *(_DWORD *)this + a3 + 1;
  if ( v6 > *(_DWORD *)this && v6 > a3 )
  {
    v7 = *((_DWORD *)this + 1);
    if ( v6 >= v7 )
    {
      while ( v6 >= v7 )
      {
        if ( v7 > 0x3FFFFFFF )
          return 0;
        v7 *= 2;
      }
      v8 = 2LL * (unsigned int)v7;
      if ( v8 > 0xFFFFFFFF )
        return 0;
      v9 = CoTaskMemRealloc(*((LPVOID *)this + 1), (unsigned int)v8);
      if ( !v9 )
        return 0;
      *((_QWORD *)this + 1) = v9;
      *((_DWORD *)this + 1) = v7;
    }
    if ( *(int *)this >= 0 && *(_DWORD *)this < v7 )
    {
      v10 = v7 - *(_DWORD *)this;
      if ( v10 <= v7 )
      {
        v11 = memcpy_s((void *const)(*((_QWORD *)this + 1) + 2LL * *(int *)this), 2LL * v10, a2, 2 * a3);
        ATL::AtlCrtErrorCheck(v11);
        *(_DWORD *)this += a3;
        *(_WORD *)(*((_QWORD *)this + 1) + 2LL * *(int *)this) = 0;
        return 1;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001548c  mov     rax, rsp
0x18001548f  mov     [rax+8], rbx
0x180015493  mov     [rax+10h], rbp
0x180015497  mov     [rax+18h], rsi
0x18001549b  mov     [rax+20h], rdi
0x18001549f  push    r14
0x1800154a1  sub     rsp, 20h
0x1800154a5  mov     rdi, rcx
0x1800154a8  mov     esi, r8d
0x1800154ab  lea     ecx, [r8+1]
0x1800154af  mov     rbp, rdx
0x1800154b2  add     ecx, [rdi]
0x1800154b4  cmp     ecx, [rdi]
0x1800154b6  jle     loc_180015563
0x1800154bc  cmp     ecx, r8d
0x1800154bf  jle     loc_180015563
0x1800154c5  mov     ebx, [rdi+4]
0x1800154c8  xor     r14d, r14d
0x1800154cb  cmp     ecx, ebx
0x1800154cd  jl      short loc_180015510
0x1800154cf  cmp     ecx, ebx
0x1800154d1  jl      short loc_1800154E3
0x1800154d3  cmp     ebx, 3FFFFFFFh
0x1800154d9  jg      loc_180015563
0x1800154df  add     ebx, ebx
0x1800154e1  jmp     short loc_1800154CF
0x1800154e3  mov     eax, ebx
0x1800154e5  mov     ecx, 0FFFFFFFFh
0x1800154ea  add     rax, rax
0x1800154ed  cmp     rax, rcx
0x1800154f0  ja      short loc_180015563
0x1800154f2  mov     rcx, [rdi+8]; pv
0x1800154f6  mov     edx, eax; cb
0x1800154f8  call    cs:__imp_CoTaskMemRealloc
0x1800154ff  nop     dword ptr [rax+rax+00h]
0x180015504  test    rax, rax
0x180015507  jz      short loc_180015563
0x180015509  mov     [rdi+8], rax
0x18001550d  mov     [rdi+4], ebx
0x180015510  cmp     [rdi], r14d
0x180015513  jl      short loc_180015563
0x180015515  cmp     [rdi], ebx
0x180015517  jge     short loc_180015563
0x180015519  mov     edx, ebx
0x18001551b  sub     edx, [rdi]
0x18001551d  cmp     edx, ebx
0x18001551f  jg      short loc_180015563
0x180015521  mov     rax, [rdi+8]
0x180015525  mov     r8, rbp; Source
0x180015528  movsxd  rcx, dword ptr [rdi]
0x18001552b  movsxd  rdx, edx
0x18001552e  add     rdx, rdx; DestinationSize
0x180015531  lea     rcx, [rax+rcx*2]; Destination
0x180015535  lea     eax, [rsi+rsi]
0x180015538  movsxd  r9, eax; SourceSize
0x18001553b  call    cs:__imp_memcpy_s
0x180015542  nop     dword ptr [rax+rax+00h]
0x180015547  mov     ecx, eax; int
0x180015549  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18001554e  add     [rdi], esi
0x180015550  mov     rax, [rdi+8]
0x180015554  movsxd  rcx, dword ptr [rdi]
0x180015557  mov     [rax+rcx*2], r14w
0x18001555c  mov     eax, 1
0x180015561  jmp     short loc_180015565
0x180015563  xor     eax, eax
0x180015565  mov     rbx, [rsp+28h+arg_0]
0x18001556a  mov     rbp, [rsp+28h+arg_8]
0x18001556f  mov     rsi, [rsp+28h+arg_10]
0x180015574  mov     rdi, [rsp+28h+arg_18]
0x180015579  add     rsp, 20h
0x18001557d  pop     r14
0x18001557f  retn
```
