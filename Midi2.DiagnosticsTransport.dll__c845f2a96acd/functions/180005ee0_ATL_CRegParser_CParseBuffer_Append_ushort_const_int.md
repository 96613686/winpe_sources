# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x180005ee0`
- end: `0x180005fd3`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `243`
- prototype: `int(ATL::CRegParser::CParseBuffer *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007aac`

## callees

- `0x180005ee0`
- `0x180006018`
- `0x18000a328`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180005f37`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180005f37`

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
0x180005ee0  push    rbx
0x180005ee2  push    rbp
0x180005ee3  push    rsi
0x180005ee4  push    rdi
0x180005ee5  sub     rsp, 28h
0x180005ee9  mov     rdi, rcx
0x180005eec  mov     esi, r8d
0x180005eef  lea     ecx, [r8+1]
0x180005ef3  mov     rbp, rdx
0x180005ef6  add     ecx, [rdi]
0x180005ef8  cmp     ecx, [rdi]
0x180005efa  jle     loc_180005FA7
0x180005f00  cmp     ecx, r8d
0x180005f03  jle     loc_180005FA7
0x180005f09  mov     ebx, [rdi+4]
0x180005f0c  cmp     ecx, ebx
0x180005f0e  jl      short loc_180005F49
0x180005f10  cmp     ebx, 3FFFFFFFh
0x180005f16  jg      loc_180005FA7
0x180005f1c  add     ebx, ebx
0x180005f1e  cmp     ecx, ebx
0x180005f20  jge     short loc_180005F10
0x180005f22  mov     eax, ebx
0x180005f24  mov     ecx, 0FFFFFFFFh
0x180005f29  add     rax, rax
0x180005f2c  cmp     rax, rcx
0x180005f2f  ja      short loc_180005FA7
0x180005f31  mov     rcx, [rdi+8]; pv
0x180005f35  mov     edx, eax; cb
0x180005f37  call    cs:__imp_CoTaskMemRealloc
0x180005f3d  test    rax, rax
0x180005f40  jz      short loc_180005FA7
0x180005f42  mov     [rdi+8], rax
0x180005f46  mov     [rdi+4], ebx
0x180005f49  cmp     dword ptr [rdi], 0
0x180005f4c  jl      short loc_180005FA7
0x180005f4e  cmp     [rdi], ebx
0x180005f50  jge     short loc_180005FA7
0x180005f52  mov     ecx, ebx
0x180005f54  sub     ecx, [rdi]
0x180005f56  cmp     ecx, ebx
0x180005f58  jg      short loc_180005FA7
0x180005f5a  movsxd  rdx, ecx
0x180005f5d  lea     eax, [rsi+rsi]
0x180005f60  movsxd  rcx, dword ptr [rdi]
0x180005f63  add     rdx, rdx; DestinationSize
0x180005f66  movsxd  r9, eax; SourceSize
0x180005f69  mov     r8, rbp; Source
0x180005f6c  mov     rax, [rdi+8]
0x180005f70  lea     rcx, [rax+rcx*2]; Destination
0x180005f74  call    memcpy_s
0x180005f79  test    eax, eax
0x180005f7b  jz      short loc_180005F91
0x180005f7d  cmp     eax, 0Ch
0x180005f80  jz      short loc_180005FC8
0x180005f82  cmp     eax, 16h
0x180005f85  jz      short loc_180005FBD
0x180005f87  cmp     eax, 22h ; '"'
0x180005f8a  jz      short loc_180005FBD
0x180005f8c  cmp     eax, 50h ; 'P'
0x180005f8f  jnz     short loc_180005FB2
0x180005f91  add     [rdi], esi
0x180005f93  movsxd  rdx, dword ptr [rdi]
0x180005f96  xor     eax, eax
0x180005f98  mov     rcx, [rdi+8]
0x180005f9c  mov     [rcx+rdx*2], ax
0x180005fa0  mov     eax, 1
0x180005fa5  jmp     short loc_180005FA9
0x180005fa7  xor     eax, eax
0x180005fa9  add     rsp, 28h
0x180005fad  pop     rdi
0x180005fae  pop     rsi
0x180005faf  pop     rbp
0x180005fb0  pop     rbx
0x180005fb1  retn
0x180005fb2  mov     ecx, 80004005h; int
0x180005fb7  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180005fbd  mov     ecx, 80070057h; int
0x180005fc2  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180005fc8  mov     ecx, 8007000Eh; int
0x180005fcd  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
