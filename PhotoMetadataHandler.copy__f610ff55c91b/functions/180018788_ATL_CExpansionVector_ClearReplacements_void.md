# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x180018788`
- end: `0x1800187fb`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `115`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180017674`
- `0x180018810`

## callees

- `0x180015c0c`
- `0x180018788`
- `0x180018b3c`
- `0x180019bd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800187f4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800187f4`

## pseudocode

```c
__int64 __fastcall ATL::CExpansionVector::ClearReplacements(ATL::CExpansionVector *this)
{
  int v1; // eax
  int i; // ebx
  HLOCAL *ValueAt; // rax

  v1 = *((_DWORD *)this + 4);
  if ( v1 > 0 )
  {
    for ( i = 0; i < v1; ++i )
    {
      if ( i < 0 || i >= v1 )
      {
        RaiseException(0xC000008C, 1u, 0, 0);
        JUMPOUT(0x1800187FALL);
      }
      operator delete(*(HLOCAL *)(*(_QWORD *)this + 8LL * i));
      ValueAt = (HLOCAL *)ATL::CSimpleMap<unsigned short *,unsigned short *,ATL::CExpansionVectorEqualHelper>::GetValueAt(
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
0x180018788  mov     [rsp+arg_0], rbx
0x18001878d  push    rdi
0x18001878e  sub     rsp, 20h
0x180018792  mov     eax, [rcx+10h]
0x180018795  mov     rdi, rcx
0x180018798  test    eax, eax
0x18001879a  jle     short loc_1800187D0
0x18001879c  xor     ebx, ebx
0x18001879e  test    ebx, ebx
0x1800187a0  js      short loc_1800187E5
0x1800187a2  cmp     ebx, eax
0x1800187a4  jge     short loc_1800187E5
0x1800187a6  mov     rcx, [rdi]
0x1800187a9  movsxd  rax, ebx
0x1800187ac  mov     rcx, [rcx+rax*8]; hMem
0x1800187b0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800187b5  mov     edx, ebx
0x1800187b7  mov     rcx, rdi
0x1800187ba  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x1800187bf  mov     rcx, [rax]; hMem
0x1800187c2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800187c7  mov     eax, [rdi+10h]
0x1800187ca  inc     ebx
0x1800187cc  cmp     ebx, eax
0x1800187ce  jl      short loc_18001879E
0x1800187d0  mov     rcx, rdi
0x1800187d3  call    ?RemoveAll@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::RemoveAll(void)
0x1800187d8  mov     rbx, [rsp+28h+arg_0]
0x1800187dd  xor     eax, eax
0x1800187df  add     rsp, 20h
0x1800187e3  pop     rdi
0x1800187e4  retn
0x1800187e5  xor     r9d, r9d; lpArguments
0x1800187e8  xor     r8d, r8d; nNumberOfArguments
0x1800187eb  mov     ecx, 0C000008Ch; dwExceptionCode
0x1800187f0  lea     edx, [r9+1]; dwExceptionFlags
0x1800187f4  call    cs:__imp_RaiseException
```
