# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x1800085d4`
- end: `0x180008647`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `115`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180007acc`
- `0x180007b04`
- `0x180008650`

## callees

- `0x180006b80`
- `0x1800085d4`
- `0x1800089a8`
- `0x1800090b0`

## import_xrefs

- `KERNEL32!RaiseException` at `0x180008640`
- `KERNEL32!RaiseException` at `0x180008640`

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
        JUMPOUT(0x180008646LL);
      }
      operator delete[](*(void **)(*(_QWORD *)this + 8LL * i));
      ValueAt = (void **)ATL::CSimpleMap<unsigned short *,unsigned short *,ATL::CExpansionVectorEqualHelper>::GetValueAt(
                           this,
                           (unsigned int)i);
      operator delete[](*ValueAt);
      v1 = *((_DWORD *)this + 4);
    }
  }
  ATL::CSimpleMap<unsigned short *,unsigned short *,ATL::CExpansionVectorEqualHelper>::RemoveAll(this);
  return 0;
}

```

## disassembly

```asm
0x1800085d4  mov     [rsp+arg_0], rbx
0x1800085d9  push    rdi
0x1800085da  sub     rsp, 20h
0x1800085de  mov     eax, [rcx+10h]
0x1800085e1  mov     rdi, rcx
0x1800085e4  test    eax, eax
0x1800085e6  jle     short loc_18000861C
0x1800085e8  xor     ebx, ebx
0x1800085ea  test    ebx, ebx
0x1800085ec  js      short loc_180008631
0x1800085ee  cmp     ebx, eax
0x1800085f0  jge     short loc_180008631
0x1800085f2  mov     rcx, [rdi]
0x1800085f5  movsxd  rax, ebx
0x1800085f8  mov     rcx, [rcx+rax*8]; Block
0x1800085fc  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180008601  mov     edx, ebx
0x180008603  mov     rcx, rdi
0x180008606  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x18000860b  mov     rcx, [rax]; Block
0x18000860e  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180008613  mov     eax, [rdi+10h]
0x180008616  inc     ebx
0x180008618  cmp     ebx, eax
0x18000861a  jl      short loc_1800085EA
0x18000861c  mov     rcx, rdi
0x18000861f  call    ?RemoveAll@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::RemoveAll(void)
0x180008624  mov     rbx, [rsp+28h+arg_0]
0x180008629  xor     eax, eax
0x18000862b  add     rsp, 20h
0x18000862f  pop     rdi
0x180008630  retn
0x180008631  xor     r9d, r9d; lpArguments
0x180008634  xor     r8d, r8d; nNumberOfArguments
0x180008637  mov     ecx, 0C000008Ch; dwExceptionCode
0x18000863c  lea     edx, [r9+1]; dwExceptionFlags
0x180008640  call    cs:__imp_RaiseException
```
