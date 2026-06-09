# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x180018098`
- end: `0x18001816c`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `212`
- prototype: `__int64 __fastcall(ATL::CRegParser::CParseBuffer *this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180018d5c`

## callees

- `0x180010e60`
- `0x18001755c`
- `0x180018098`
- `0x18001a528`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180018102`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180018102`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::CParseBuffer::Append(
        ATL::CRegParser::CParseBuffer *this,
        const unsigned __int16 *a2,
        int a3)
{
  int v6; // ecx
  int v7; // ebx
  LPVOID v8; // rax
  int v9; // ecx
  errno_t v10; // eax
  SIZE_T cb; // [rsp+60h] [rbp+18h] BYREF

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
      LODWORD(cb) = 0;
      if ( (int)ATL::AtlMultiply<unsigned long>(&cb, (unsigned int)v7, 2) < 0 )
        return 0;
      v8 = CoTaskMemRealloc(*((LPVOID *)this + 1), (unsigned int)cb);
      if ( !v8 )
        return 0;
      *((_QWORD *)this + 1) = v8;
      *((_DWORD *)this + 1) = v7;
    }
    if ( *(int *)this >= 0 && *(_DWORD *)this < v7 )
    {
      v9 = v7 - *(_DWORD *)this;
      if ( v9 <= v7 )
      {
        v10 = memcpy_s((void *const)(*((_QWORD *)this + 1) + 2LL * *(int *)this), 2LL * v9, a2, 2 * a3);
        ATL::AtlCrtErrorCheck(v10);
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
0x180018098  push    rbx
0x18001809a  push    rbp
0x18001809b  push    rsi
0x18001809c  push    rdi
0x18001809d  sub     rsp, 28h
0x1800180a1  mov     rdi, rcx
0x1800180a4  mov     esi, r8d
0x1800180a7  lea     ecx, [r8+1]
0x1800180ab  mov     rbp, rdx
0x1800180ae  add     ecx, [rdi]
0x1800180b0  cmp     ecx, [rdi]
0x1800180b2  jle     loc_180018161
0x1800180b8  cmp     ecx, r8d
0x1800180bb  jle     loc_180018161
0x1800180c1  mov     ebx, [rdi+4]
0x1800180c4  cmp     ecx, ebx
0x1800180c6  jl      short loc_180018114
0x1800180c8  cmp     ecx, ebx
0x1800180ca  jl      short loc_1800180DC
0x1800180cc  cmp     ebx, 3FFFFFFFh
0x1800180d2  jg      loc_180018161
0x1800180d8  add     ebx, ebx
0x1800180da  jmp     short loc_1800180C8
0x1800180dc  mov     r8d, 2
0x1800180e2  mov     dword ptr [rsp+48h+cb], 0
0x1800180ea  mov     edx, ebx
0x1800180ec  lea     rcx, [rsp+48h+cb]
0x1800180f1  call    ??$AtlMultiply@K@ATL@@YAJPEAKKK@Z; ATL::AtlMultiply<ulong>(ulong *,ulong,ulong)
0x1800180f6  test    eax, eax
0x1800180f8  js      short loc_180018161
0x1800180fa  mov     edx, dword ptr [rsp+48h+cb]; cb
0x1800180fe  mov     rcx, [rdi+8]; pv
0x180018102  call    cs:__imp_CoTaskMemRealloc
0x180018108  test    rax, rax
0x18001810b  jz      short loc_180018161
0x18001810d  mov     [rdi+8], rax
0x180018111  mov     [rdi+4], ebx
0x180018114  cmp     dword ptr [rdi], 0
0x180018117  jl      short loc_180018161
0x180018119  cmp     [rdi], ebx
0x18001811b  jge     short loc_180018161
0x18001811d  mov     ecx, ebx
0x18001811f  sub     ecx, [rdi]
0x180018121  cmp     ecx, ebx
0x180018123  jg      short loc_180018161
0x180018125  movsxd  rdx, ecx
0x180018128  lea     eax, [rsi+rsi]
0x18001812b  movsxd  rcx, dword ptr [rdi]
0x18001812e  add     rdx, rdx; DestinationSize
0x180018131  movsxd  r9, eax; SourceSize
0x180018134  mov     r8, rbp; Source
0x180018137  mov     rax, [rdi+8]
0x18001813b  lea     rcx, [rax+rcx*2]; Destination
0x18001813f  call    memcpy_s
0x180018144  mov     ecx, eax; int
0x180018146  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18001814b  add     [rdi], esi
0x18001814d  movsxd  rdx, dword ptr [rdi]
0x180018150  xor     eax, eax
0x180018152  mov     rcx, [rdi+8]
0x180018156  mov     [rcx+rdx*2], ax
0x18001815a  mov     eax, 1
0x18001815f  jmp     short loc_180018163
0x180018161  xor     eax, eax
0x180018163  add     rsp, 28h
0x180018167  pop     rdi
0x180018168  pop     rsi
0x180018169  pop     rbp
0x18001816a  pop     rbx
0x18001816b  retn
```
