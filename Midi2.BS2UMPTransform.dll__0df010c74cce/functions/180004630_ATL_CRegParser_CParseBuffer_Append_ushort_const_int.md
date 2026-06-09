# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x180004630`
- end: `0x180004723`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `243`
- prototype: `int(ATL::CRegParser::CParseBuffer *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800061fc`

## callees

- `0x180004630`
- `0x180004768`
- `0x180008a78`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180004687`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180004687`

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
0x180004630  push    rbx
0x180004632  push    rbp
0x180004633  push    rsi
0x180004634  push    rdi
0x180004635  sub     rsp, 28h
0x180004639  mov     rdi, rcx
0x18000463c  mov     esi, r8d
0x18000463f  lea     ecx, [r8+1]
0x180004643  mov     rbp, rdx
0x180004646  add     ecx, [rdi]
0x180004648  cmp     ecx, [rdi]
0x18000464a  jle     loc_1800046F7
0x180004650  cmp     ecx, r8d
0x180004653  jle     loc_1800046F7
0x180004659  mov     ebx, [rdi+4]
0x18000465c  cmp     ecx, ebx
0x18000465e  jl      short loc_180004699
0x180004660  cmp     ebx, 3FFFFFFFh
0x180004666  jg      loc_1800046F7
0x18000466c  add     ebx, ebx
0x18000466e  cmp     ecx, ebx
0x180004670  jge     short loc_180004660
0x180004672  mov     eax, ebx
0x180004674  mov     ecx, 0FFFFFFFFh
0x180004679  add     rax, rax
0x18000467c  cmp     rax, rcx
0x18000467f  ja      short loc_1800046F7
0x180004681  mov     rcx, [rdi+8]; pv
0x180004685  mov     edx, eax; cb
0x180004687  call    cs:__imp_CoTaskMemRealloc
0x18000468d  test    rax, rax
0x180004690  jz      short loc_1800046F7
0x180004692  mov     [rdi+8], rax
0x180004696  mov     [rdi+4], ebx
0x180004699  cmp     dword ptr [rdi], 0
0x18000469c  jl      short loc_1800046F7
0x18000469e  cmp     [rdi], ebx
0x1800046a0  jge     short loc_1800046F7
0x1800046a2  mov     ecx, ebx
0x1800046a4  sub     ecx, [rdi]
0x1800046a6  cmp     ecx, ebx
0x1800046a8  jg      short loc_1800046F7
0x1800046aa  movsxd  rdx, ecx
0x1800046ad  lea     eax, [rsi+rsi]
0x1800046b0  movsxd  rcx, dword ptr [rdi]
0x1800046b3  add     rdx, rdx; DestinationSize
0x1800046b6  movsxd  r9, eax; SourceSize
0x1800046b9  mov     r8, rbp; Source
0x1800046bc  mov     rax, [rdi+8]
0x1800046c0  lea     rcx, [rax+rcx*2]; Destination
0x1800046c4  call    memcpy_s
0x1800046c9  test    eax, eax
0x1800046cb  jz      short loc_1800046E1
0x1800046cd  cmp     eax, 0Ch
0x1800046d0  jz      short loc_180004718
0x1800046d2  cmp     eax, 16h
0x1800046d5  jz      short loc_18000470D
0x1800046d7  cmp     eax, 22h ; '"'
0x1800046da  jz      short loc_18000470D
0x1800046dc  cmp     eax, 50h ; 'P'
0x1800046df  jnz     short loc_180004702
0x1800046e1  add     [rdi], esi
0x1800046e3  movsxd  rdx, dword ptr [rdi]
0x1800046e6  xor     eax, eax
0x1800046e8  mov     rcx, [rdi+8]
0x1800046ec  mov     [rcx+rdx*2], ax
0x1800046f0  mov     eax, 1
0x1800046f5  jmp     short loc_1800046F9
0x1800046f7  xor     eax, eax
0x1800046f9  add     rsp, 28h
0x1800046fd  pop     rdi
0x1800046fe  pop     rsi
0x1800046ff  pop     rbp
0x180004700  pop     rbx
0x180004701  retn
0x180004702  mov     ecx, 80004005h; int
0x180004707  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000470d  mov     ecx, 80070057h; int
0x180004712  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180004718  mov     ecx, 8007000Eh; int
0x18000471d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
