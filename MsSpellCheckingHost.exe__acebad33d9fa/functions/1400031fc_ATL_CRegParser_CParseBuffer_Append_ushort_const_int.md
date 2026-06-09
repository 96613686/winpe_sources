# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x1400031fc`
- end: `0x1400032f0`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `244`
- prototype: `__int64 __fastcall(ATL::CRegParser::CParseBuffer *this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400048d0`

## callees

- `0x1400031fc`
- `0x140003b88`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140003290`
- `msvcrt!memcpy_s` at `0x140003290`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x140003253`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x140003253`

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
0x1400031fc  push    rbx
0x1400031fe  push    rbp
0x1400031ff  push    rsi
0x140003200  push    rdi
0x140003201  sub     rsp, 28h
0x140003205  mov     rdi, rcx
0x140003208  mov     esi, r8d
0x14000320b  lea     ecx, [r8+1]
0x14000320f  mov     rbp, rdx
0x140003212  add     ecx, [rdi]
0x140003214  cmp     ecx, [rdi]
0x140003216  jle     loc_1400032C4
0x14000321c  cmp     ecx, r8d
0x14000321f  jle     loc_1400032C4
0x140003225  mov     ebx, [rdi+4]
0x140003228  cmp     ecx, ebx
0x14000322a  jl      short loc_140003265
0x14000322c  cmp     ebx, 3FFFFFFFh
0x140003232  jg      loc_1400032C4
0x140003238  add     ebx, ebx
0x14000323a  cmp     ecx, ebx
0x14000323c  jge     short loc_14000322C
0x14000323e  mov     eax, ebx
0x140003240  mov     ecx, 0FFFFFFFFh
0x140003245  add     rax, rax
0x140003248  cmp     rax, rcx
0x14000324b  ja      short loc_1400032C4
0x14000324d  mov     rcx, [rdi+8]; pv
0x140003251  mov     edx, eax; cb
0x140003253  call    cs:__imp_CoTaskMemRealloc
0x140003259  test    rax, rax
0x14000325c  jz      short loc_1400032C4
0x14000325e  mov     [rdi+8], rax
0x140003262  mov     [rdi+4], ebx
0x140003265  cmp     dword ptr [rdi], 0
0x140003268  jl      short loc_1400032C4
0x14000326a  cmp     [rdi], ebx
0x14000326c  jge     short loc_1400032C4
0x14000326e  mov     ecx, ebx
0x140003270  sub     ecx, [rdi]
0x140003272  cmp     ecx, ebx
0x140003274  jg      short loc_1400032C4
0x140003276  movsxd  rdx, ecx
0x140003279  lea     eax, [rsi+rsi]
0x14000327c  movsxd  rcx, dword ptr [rdi]
0x14000327f  add     rdx, rdx; DestinationSize
0x140003282  movsxd  r9, eax; SourceSize
0x140003285  mov     r8, rbp; Source
0x140003288  mov     rax, [rdi+8]
0x14000328c  lea     rcx, [rax+rcx*2]; Destination
0x140003290  call    cs:__imp_memcpy_s
0x140003296  test    eax, eax
0x140003298  jz      short loc_1400032AE
0x14000329a  cmp     eax, 0Ch
0x14000329d  jz      short loc_1400032E5
0x14000329f  cmp     eax, 16h
0x1400032a2  jz      short loc_1400032DA
0x1400032a4  cmp     eax, 22h ; '"'
0x1400032a7  jz      short loc_1400032DA
0x1400032a9  cmp     eax, 50h ; 'P'
0x1400032ac  jnz     short loc_1400032CF
0x1400032ae  add     [rdi], esi
0x1400032b0  movsxd  rdx, dword ptr [rdi]
0x1400032b3  xor     eax, eax
0x1400032b5  mov     rcx, [rdi+8]
0x1400032b9  mov     [rcx+rdx*2], ax
0x1400032bd  mov     eax, 1
0x1400032c2  jmp     short loc_1400032C6
0x1400032c4  xor     eax, eax
0x1400032c6  add     rsp, 28h
0x1400032ca  pop     rdi
0x1400032cb  pop     rsi
0x1400032cc  pop     rbp
0x1400032cd  pop     rbx
0x1400032ce  retn
0x1400032cf  mov     ecx, 80004005h; int
0x1400032d4  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1400032da  mov     ecx, 80070057h; int
0x1400032df  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1400032e5  mov     ecx, 8007000Eh; int
0x1400032ea  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
