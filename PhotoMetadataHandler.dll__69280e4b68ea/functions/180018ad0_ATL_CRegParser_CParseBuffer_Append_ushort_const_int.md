# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x180018ad0`
- end: `0x180018bab`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `219`
- prototype: `int(ATL::CRegParser::CParseBuffer *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180019890`

## callees

- `0x180011698`
- `0x180018014`
- `0x180018ad0`
- `0x18001b1ac`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180018b3a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180018b3a`

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
0x180018ad0  push    rbx
0x180018ad2  push    rbp
0x180018ad3  push    rsi
0x180018ad4  push    rdi
0x180018ad5  sub     rsp, 28h
0x180018ad9  mov     rdi, rcx
0x180018adc  mov     esi, r8d
0x180018adf  lea     ecx, [r8+1]
0x180018ae3  mov     rbp, rdx
0x180018ae6  add     ecx, [rdi]
0x180018ae8  cmp     ecx, [rdi]
0x180018aea  jle     loc_180018B9F
0x180018af0  cmp     ecx, r8d
0x180018af3  jle     loc_180018B9F
0x180018af9  mov     ebx, [rdi+4]
0x180018afc  cmp     ecx, ebx
0x180018afe  jl      short loc_180018B52
0x180018b00  cmp     ecx, ebx
0x180018b02  jl      short loc_180018B14
0x180018b04  cmp     ebx, 3FFFFFFFh
0x180018b0a  jg      loc_180018B9F
0x180018b10  add     ebx, ebx
0x180018b12  jmp     short loc_180018B00
0x180018b14  mov     r8d, 2
0x180018b1a  mov     dword ptr [rsp+48h+cb], 0
0x180018b22  mov     edx, ebx
0x180018b24  lea     rcx, [rsp+48h+cb]
0x180018b29  call    ??$AtlMultiply@K@ATL@@YAJPEAKKK@Z; ATL::AtlMultiply<ulong>(ulong *,ulong,ulong)
0x180018b2e  test    eax, eax
0x180018b30  js      short loc_180018B9F
0x180018b32  mov     edx, dword ptr [rsp+48h+cb]; cb
0x180018b36  mov     rcx, [rdi+8]; pv
0x180018b3a  call    cs:__imp_CoTaskMemRealloc
0x180018b41  nop     dword ptr [rax+rax+00h]
0x180018b46  test    rax, rax
0x180018b49  jz      short loc_180018B9F
0x180018b4b  mov     [rdi+8], rax
0x180018b4f  mov     [rdi+4], ebx
0x180018b52  cmp     dword ptr [rdi], 0
0x180018b55  jl      short loc_180018B9F
0x180018b57  cmp     [rdi], ebx
0x180018b59  jge     short loc_180018B9F
0x180018b5b  mov     ecx, ebx
0x180018b5d  sub     ecx, [rdi]
0x180018b5f  cmp     ecx, ebx
0x180018b61  jg      short loc_180018B9F
0x180018b63  movsxd  rdx, ecx
0x180018b66  lea     eax, [rsi+rsi]
0x180018b69  movsxd  rcx, dword ptr [rdi]
0x180018b6c  add     rdx, rdx; DestinationSize
0x180018b6f  movsxd  r9, eax; SourceSize
0x180018b72  mov     r8, rbp; Source
0x180018b75  mov     rax, [rdi+8]
0x180018b79  lea     rcx, [rax+rcx*2]; Destination
0x180018b7d  call    memcpy_s
0x180018b82  mov     ecx, eax; int
0x180018b84  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180018b89  add     [rdi], esi
0x180018b8b  movsxd  rdx, dword ptr [rdi]
0x180018b8e  xor     eax, eax
0x180018b90  mov     rcx, [rdi+8]
0x180018b94  mov     [rcx+rdx*2], ax
0x180018b98  mov     eax, 1
0x180018b9d  jmp     short loc_180018BA1
0x180018b9f  xor     eax, eax
0x180018ba1  add     rsp, 28h
0x180018ba5  pop     rdi
0x180018ba6  pop     rsi
0x180018ba7  pop     rbp
0x180018ba8  pop     rbx
0x180018ba9  retn
```
