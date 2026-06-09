# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x1800047d0`
- end: `0x1800048c3`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `243`
- prototype: `int(ATL::CRegParser::CParseBuffer *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000639c`

## callees

- `0x1800047d0`
- `0x180004908`
- `0x180008c28`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180004827`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180004827`

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
0x1800047d0  push    rbx
0x1800047d2  push    rbp
0x1800047d3  push    rsi
0x1800047d4  push    rdi
0x1800047d5  sub     rsp, 28h
0x1800047d9  mov     rdi, rcx
0x1800047dc  mov     esi, r8d
0x1800047df  lea     ecx, [r8+1]
0x1800047e3  mov     rbp, rdx
0x1800047e6  add     ecx, [rdi]
0x1800047e8  cmp     ecx, [rdi]
0x1800047ea  jle     loc_180004897
0x1800047f0  cmp     ecx, r8d
0x1800047f3  jle     loc_180004897
0x1800047f9  mov     ebx, [rdi+4]
0x1800047fc  cmp     ecx, ebx
0x1800047fe  jl      short loc_180004839
0x180004800  cmp     ebx, 3FFFFFFFh
0x180004806  jg      loc_180004897
0x18000480c  add     ebx, ebx
0x18000480e  cmp     ecx, ebx
0x180004810  jge     short loc_180004800
0x180004812  mov     eax, ebx
0x180004814  mov     ecx, 0FFFFFFFFh
0x180004819  add     rax, rax
0x18000481c  cmp     rax, rcx
0x18000481f  ja      short loc_180004897
0x180004821  mov     rcx, [rdi+8]; pv
0x180004825  mov     edx, eax; cb
0x180004827  call    cs:__imp_CoTaskMemRealloc
0x18000482d  test    rax, rax
0x180004830  jz      short loc_180004897
0x180004832  mov     [rdi+8], rax
0x180004836  mov     [rdi+4], ebx
0x180004839  cmp     dword ptr [rdi], 0
0x18000483c  jl      short loc_180004897
0x18000483e  cmp     [rdi], ebx
0x180004840  jge     short loc_180004897
0x180004842  mov     ecx, ebx
0x180004844  sub     ecx, [rdi]
0x180004846  cmp     ecx, ebx
0x180004848  jg      short loc_180004897
0x18000484a  movsxd  rdx, ecx
0x18000484d  lea     eax, [rsi+rsi]
0x180004850  movsxd  rcx, dword ptr [rdi]
0x180004853  add     rdx, rdx; DestinationSize
0x180004856  movsxd  r9, eax; SourceSize
0x180004859  mov     r8, rbp; Source
0x18000485c  mov     rax, [rdi+8]
0x180004860  lea     rcx, [rax+rcx*2]; Destination
0x180004864  call    memcpy_s
0x180004869  test    eax, eax
0x18000486b  jz      short loc_180004881
0x18000486d  cmp     eax, 0Ch
0x180004870  jz      short loc_1800048B8
0x180004872  cmp     eax, 16h
0x180004875  jz      short loc_1800048AD
0x180004877  cmp     eax, 22h ; '"'
0x18000487a  jz      short loc_1800048AD
0x18000487c  cmp     eax, 50h ; 'P'
0x18000487f  jnz     short loc_1800048A2
0x180004881  add     [rdi], esi
0x180004883  movsxd  rdx, dword ptr [rdi]
0x180004886  xor     eax, eax
0x180004888  mov     rcx, [rdi+8]
0x18000488c  mov     [rcx+rdx*2], ax
0x180004890  mov     eax, 1
0x180004895  jmp     short loc_180004899
0x180004897  xor     eax, eax
0x180004899  add     rsp, 28h
0x18000489d  pop     rdi
0x18000489e  pop     rsi
0x18000489f  pop     rbp
0x1800048a0  pop     rbx
0x1800048a1  retn
0x1800048a2  mov     ecx, 80004005h; int
0x1800048a7  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800048ad  mov     ecx, 80070057h; int
0x1800048b2  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800048b8  mov     ecx, 8007000Eh; int
0x1800048bd  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
