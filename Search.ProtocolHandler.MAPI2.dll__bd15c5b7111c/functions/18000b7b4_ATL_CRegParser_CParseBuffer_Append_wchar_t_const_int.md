# ATL::CRegParser::CParseBuffer::Append(wchar_t const *,int)

- ea: `0x18000b7b4`
- end: `0x18000b888`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEB_WH@Z`
- size: `212`
- prototype: `__int64 __fastcall(ATL::CRegParser::CParseBuffer *this, const wchar_t *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000c8f8`

## callees

- `0x18000a484`
- `0x18000a9bc`
- `0x18000b7b4`
- `0x18000b9a4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000b81e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000b81e`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::CParseBuffer::Append(
        ATL::CRegParser::CParseBuffer *this,
        const wchar_t *a2,
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
0x18000b7b4  push    rbx
0x18000b7b6  push    rbp
0x18000b7b7  push    rsi
0x18000b7b8  push    rdi
0x18000b7b9  sub     rsp, 28h
0x18000b7bd  mov     rdi, rcx
0x18000b7c0  mov     esi, r8d
0x18000b7c3  lea     ecx, [r8+1]
0x18000b7c7  mov     rbp, rdx
0x18000b7ca  add     ecx, [rdi]
0x18000b7cc  cmp     ecx, [rdi]
0x18000b7ce  jle     loc_18000B87D
0x18000b7d4  cmp     ecx, r8d
0x18000b7d7  jle     loc_18000B87D
0x18000b7dd  mov     ebx, [rdi+4]
0x18000b7e0  cmp     ecx, ebx
0x18000b7e2  jl      short loc_18000B830
0x18000b7e4  cmp     ecx, ebx
0x18000b7e6  jl      short loc_18000B7F8
0x18000b7e8  cmp     ebx, 3FFFFFFFh
0x18000b7ee  jg      loc_18000B87D
0x18000b7f4  add     ebx, ebx
0x18000b7f6  jmp     short loc_18000B7E4
0x18000b7f8  mov     r8d, 2
0x18000b7fe  mov     dword ptr [rsp+48h+cb], 0
0x18000b806  mov     edx, ebx
0x18000b808  lea     rcx, [rsp+48h+cb]
0x18000b80d  call    ??$AtlMultiply@K@ATL@@YAJPEAKKK@Z; ATL::AtlMultiply<ulong>(ulong *,ulong,ulong)
0x18000b812  test    eax, eax
0x18000b814  js      short loc_18000B87D
0x18000b816  mov     edx, dword ptr [rsp+48h+cb]; cb
0x18000b81a  mov     rcx, [rdi+8]; pv
0x18000b81e  call    cs:__imp_CoTaskMemRealloc
0x18000b824  test    rax, rax
0x18000b827  jz      short loc_18000B87D
0x18000b829  mov     [rdi+8], rax
0x18000b82d  mov     [rdi+4], ebx
0x18000b830  cmp     dword ptr [rdi], 0
0x18000b833  jl      short loc_18000B87D
0x18000b835  cmp     [rdi], ebx
0x18000b837  jge     short loc_18000B87D
0x18000b839  mov     ecx, ebx
0x18000b83b  sub     ecx, [rdi]
0x18000b83d  cmp     ecx, ebx
0x18000b83f  jg      short loc_18000B87D
0x18000b841  movsxd  rdx, ecx
0x18000b844  lea     eax, [rsi+rsi]
0x18000b847  movsxd  rcx, dword ptr [rdi]
0x18000b84a  add     rdx, rdx; DestinationSize
0x18000b84d  movsxd  r9, eax; SourceSize
0x18000b850  mov     r8, rbp; Source
0x18000b853  mov     rax, [rdi+8]
0x18000b857  lea     rcx, [rax+rcx*2]; Destination
0x18000b85b  call    memcpy_s
0x18000b860  mov     ecx, eax; int
0x18000b862  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000b867  add     [rdi], esi
0x18000b869  movsxd  rdx, dword ptr [rdi]
0x18000b86c  xor     eax, eax
0x18000b86e  mov     rcx, [rdi+8]
0x18000b872  mov     [rcx+rdx*2], ax
0x18000b876  mov     eax, 1
0x18000b87b  jmp     short loc_18000B87F
0x18000b87d  xor     eax, eax
0x18000b87f  add     rsp, 28h
0x18000b883  pop     rdi
0x18000b884  pop     rsi
0x18000b885  pop     rbp
0x18000b886  pop     rbx
0x18000b887  retn
```
