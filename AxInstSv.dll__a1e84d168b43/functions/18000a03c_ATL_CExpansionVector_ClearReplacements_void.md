# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x18000a03c`
- end: `0x18000a0af`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `115`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800088b4`
- `0x18000a0c0`

## callees

- `0x180001744`
- `0x18000a03c`
- `0x18000ba74`
- `0x18000ef8c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000a0a8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000a0a8`

## pseudocode

```c
__int64 __fastcall ATL::CExpansionVector::ClearReplacements(ATL::CExpansionVector *this)
{
  int v1; // eax
  int i; // ebx
  void **ValueAt; // rax

  v1 = *((_DWORD *)this + 4);
  if ( v1 > 0 )
  {
    for ( i = 0; i < v1; ++i )
    {
      if ( i < 0 || i >= v1 )
      {
        RaiseException(0xC000008C, 1u, 0, 0);
        JUMPOUT(0x18000A0AELL);
      }
      operator delete(*(void **)(*(_QWORD *)this + 8LL * i));
      ValueAt = (void **)ATL::CSimpleMap<unsigned short *,unsigned short *,ATL::CExpansionVectorEqualHelper>::GetValueAt(
                           this,
                           (unsigned int)i);
      operator delete(*ValueAt);
      v1 = *((_DWORD *)this + 4);
    }
  }
  ATL::CSimpleMap<unsigned short *,unsigned short *,ATL::CExpansionVectorEqualHelper>::RemoveAll(this);
  return 0;
}

```

## disassembly

```asm
0x18000a03c  mov     [rsp+arg_0], rbx
0x18000a041  push    rdi
0x18000a042  sub     rsp, 20h
0x18000a046  mov     eax, [rcx+10h]
0x18000a049  mov     rdi, rcx
0x18000a04c  test    eax, eax
0x18000a04e  jle     short loc_18000A084
0x18000a050  xor     ebx, ebx
0x18000a052  test    ebx, ebx
0x18000a054  js      short loc_18000A099
0x18000a056  cmp     ebx, eax
0x18000a058  jge     short loc_18000A099
0x18000a05a  mov     rcx, [rdi]
0x18000a05d  movsxd  rax, ebx
0x18000a060  mov     rcx, [rcx+rax*8]; Block
0x18000a064  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000a069  mov     edx, ebx
0x18000a06b  mov     rcx, rdi
0x18000a06e  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x18000a073  mov     rcx, [rax]; Block
0x18000a076  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000a07b  mov     eax, [rdi+10h]
0x18000a07e  inc     ebx
0x18000a080  cmp     ebx, eax
0x18000a082  jl      short loc_18000A052
0x18000a084  mov     rcx, rdi
0x18000a087  call    ?RemoveAll@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::RemoveAll(void)
0x18000a08c  mov     rbx, [rsp+28h+arg_0]
0x18000a091  xor     eax, eax
0x18000a093  add     rsp, 20h
0x18000a097  pop     rdi
0x18000a098  retn
0x18000a099  xor     r9d, r9d; lpArguments
0x18000a09c  xor     r8d, r8d; nNumberOfArguments
0x18000a09f  mov     ecx, 0C000008Ch; dwExceptionCode
0x18000a0a4  lea     edx, [r9+1]; dwExceptionFlags
0x18000a0a8  call    cs:__imp_RaiseException
```
