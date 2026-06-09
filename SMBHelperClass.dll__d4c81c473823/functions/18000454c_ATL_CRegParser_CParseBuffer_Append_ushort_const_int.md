# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x18000454c`
- end: `0x180004640`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `244`
- prototype: `int(ATL::CRegParser::CParseBuffer *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006f6c`

## callees

- `0x18000454c`
- `0x180004684`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800045e0`
- `msvcrt!memcpy_s` at `0x1800045e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800045a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800045a3`

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
  int v10; // ecx
  errno_t v11; // eax

  v6 = *(_DWORD *)this + a3 + 1;
  if ( v6 <= *(_DWORD *)this || v6 <= a3 )
    return 0;
  v7 = *((_DWORD *)this + 1);
  if ( v6 >= v7 )
  {
    while ( v7 <= 0x3FFFFFFF )
    {
      v7 *= 2;
      if ( v6 < v7 )
      {
        v8 = 2LL * (unsigned int)v7;
        if ( v8 <= 0xFFFFFFFF )
        {
          v9 = CoTaskMemRealloc(*((LPVOID *)this + 1), (unsigned int)v8);
          if ( v9 )
          {
            *((_QWORD *)this + 1) = v9;
            *((_DWORD *)this + 1) = v7;
            goto LABEL_9;
          }
        }
        return 0;
      }
    }
    return 0;
  }
LABEL_9:
  if ( *(int *)this < 0 )
    return 0;
  if ( *(_DWORD *)this >= v7 )
    return 0;
  v10 = v7 - *(_DWORD *)this;
  if ( v10 > v7 )
    return 0;
  v11 = memcpy_s((void *const)(*((_QWORD *)this + 1) + 2LL * *(int *)this), 2LL * v10, a2, 2 * a3);
  if ( v11 )
  {
    if ( v11 == 12 )
      ATL::AtlThrowImpl(-2147024882);
    if ( v11 == 22 || v11 == 34 )
      ATL::AtlThrowImpl(-2147024809);
    if ( v11 != 80 )
      ATL::AtlThrowImpl(-2147467259);
  }
  *(_DWORD *)this += a3;
  *(_WORD *)(*((_QWORD *)this + 1) + 2LL * *(int *)this) = 0;
  return 1;
}

```

## disassembly

```asm
0x18000454c  push    rbx
0x18000454e  push    rbp
0x18000454f  push    rsi
0x180004550  push    rdi
0x180004551  sub     rsp, 28h
0x180004555  mov     rdi, rcx
0x180004558  mov     esi, r8d
0x18000455b  lea     ecx, [r8+1]
0x18000455f  mov     rbp, rdx
0x180004562  add     ecx, [rdi]
0x180004564  cmp     ecx, [rdi]
0x180004566  jle     loc_180004614
0x18000456c  cmp     ecx, r8d
0x18000456f  jle     loc_180004614
0x180004575  mov     ebx, [rdi+4]
0x180004578  cmp     ecx, ebx
0x18000457a  jl      short loc_1800045B5
0x18000457c  cmp     ebx, 3FFFFFFFh
0x180004582  jg      loc_180004614
0x180004588  add     ebx, ebx
0x18000458a  cmp     ecx, ebx
0x18000458c  jge     short loc_18000457C
0x18000458e  mov     eax, ebx
0x180004590  mov     ecx, 0FFFFFFFFh
0x180004595  add     rax, rax
0x180004598  cmp     rax, rcx
0x18000459b  ja      short loc_180004614
0x18000459d  mov     rcx, [rdi+8]; pv
0x1800045a1  mov     edx, eax; cb
0x1800045a3  call    cs:__imp_CoTaskMemRealloc
0x1800045a9  test    rax, rax
0x1800045ac  jz      short loc_180004614
0x1800045ae  mov     [rdi+8], rax
0x1800045b2  mov     [rdi+4], ebx
0x1800045b5  cmp     dword ptr [rdi], 0
0x1800045b8  jl      short loc_180004614
0x1800045ba  cmp     [rdi], ebx
0x1800045bc  jge     short loc_180004614
0x1800045be  mov     ecx, ebx
0x1800045c0  sub     ecx, [rdi]
0x1800045c2  cmp     ecx, ebx
0x1800045c4  jg      short loc_180004614
0x1800045c6  movsxd  rdx, ecx
0x1800045c9  lea     eax, [rsi+rsi]
0x1800045cc  movsxd  rcx, dword ptr [rdi]
0x1800045cf  add     rdx, rdx; DestinationSize
0x1800045d2  movsxd  r9, eax; SourceSize
0x1800045d5  mov     r8, rbp; Source
0x1800045d8  mov     rax, [rdi+8]
0x1800045dc  lea     rcx, [rax+rcx*2]; Destination
0x1800045e0  call    cs:__imp_memcpy_s
0x1800045e6  test    eax, eax
0x1800045e8  jz      short loc_1800045FE
0x1800045ea  cmp     eax, 0Ch
0x1800045ed  jz      short loc_180004635
0x1800045ef  cmp     eax, 16h
0x1800045f2  jz      short loc_18000462A
0x1800045f4  cmp     eax, 22h ; '"'
0x1800045f7  jz      short loc_18000462A
0x1800045f9  cmp     eax, 50h ; 'P'
0x1800045fc  jnz     short loc_18000461F
0x1800045fe  add     [rdi], esi
0x180004600  movsxd  rdx, dword ptr [rdi]
0x180004603  xor     eax, eax
0x180004605  mov     rcx, [rdi+8]
0x180004609  mov     [rcx+rdx*2], ax
0x18000460d  mov     eax, 1
0x180004612  jmp     short loc_180004616
0x180004614  xor     eax, eax
0x180004616  add     rsp, 28h
0x18000461a  pop     rdi
0x18000461b  pop     rsi
0x18000461c  pop     rbp
0x18000461d  pop     rbx
0x18000461e  retn
0x18000461f  mov     ecx, 80004005h; int
0x180004624  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000462a  mov     ecx, 80070057h; int
0x18000462f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180004635  mov     ecx, 8007000Eh; int
0x18000463a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
