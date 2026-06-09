# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x180033854`
- end: `0x1800338c9`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000cb98`
- `0x180033810`
- `0x1800338d0`

## callees

- `0x180033854`
- `0x1800338f4`
- `0x18004316c`

## import_xrefs

- `KERNEL32!RaiseException` at `0x1800338c2`
- `KERNEL32!RaiseException` at `0x1800338c2`
- `PhotoBase!?Delete@BasePrivate@@YAXPEAX@Z` at `0x18003387c`
- `PhotoBase!?Delete@BasePrivate@@YAXPEAX@Z` at `0x18003388f`
- `PhotoBase!?Delete@BasePrivate@@YAXPEAX@Z` at `0x18003387c`
- `PhotoBase!?Delete@BasePrivate@@YAXPEAX@Z` at `0x18003388f`

## pseudocode

```c
__int64 __fastcall ATL::CExpansionVector::ClearReplacements(ATL::CExpansionVector *this, void *a2)
{
  int v2; // eax
  int i; // ebx
  BasePrivate **ValueAt; // rax
  void *v6; // rdx

  v2 = *((_DWORD *)this + 4);
  if ( v2 > 0 )
  {
    for ( i = 0; i < v2; ++i )
    {
      if ( i < 0 || i >= v2 )
      {
        RaiseException(0xC000008C, 1u, 0, 0);
        JUMPOUT(0x1800338C8LL);
      }
      BasePrivate::Delete(*(BasePrivate **)(*(_QWORD *)this + 8LL * i), a2);
      ValueAt = (BasePrivate **)ATL::CSimpleMap<unsigned short *,unsigned short *,ATL::CExpansionVectorEqualHelper>::GetValueAt(
                                  this,
                                  (unsigned int)i);
      BasePrivate::Delete(*ValueAt, v6);
      v2 = *((_DWORD *)this + 4);
    }
  }
  ATL::CSimpleMap<unsigned short *,unsigned short *,ATL::CExpansionVectorEqualHelper>::RemoveAll(this);
  return 0;
}

```

## disassembly

```asm
0x180033854  mov     [rsp+arg_0], rbx
0x180033859  push    rdi
0x18003385a  sub     rsp, 20h
0x18003385e  mov     eax, [rcx+10h]
0x180033861  mov     rdi, rcx
0x180033864  test    eax, eax
0x180033866  jle     short loc_18003389E
0x180033868  xor     ebx, ebx
0x18003386a  test    ebx, ebx
0x18003386c  js      short loc_1800338B3
0x18003386e  cmp     ebx, eax
0x180033870  jge     short loc_1800338B3
0x180033872  mov     rcx, [rdi]
0x180033875  movsxd  rax, ebx
0x180033878  mov     rcx, [rcx+rax*8]
0x18003387c  call    cs:__imp_?Delete@BasePrivate@@YAXPEAX@Z; BasePrivate::Delete(void *)
0x180033882  mov     edx, ebx
0x180033884  mov     rcx, rdi
0x180033887  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x18003388c  mov     rcx, [rax]
0x18003388f  call    cs:__imp_?Delete@BasePrivate@@YAXPEAX@Z; BasePrivate::Delete(void *)
0x180033895  mov     eax, [rdi+10h]
0x180033898  inc     ebx
0x18003389a  cmp     ebx, eax
0x18003389c  jl      short loc_18003386A
0x18003389e  mov     rcx, rdi
0x1800338a1  call    ?RemoveAll@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::RemoveAll(void)
0x1800338a6  mov     rbx, [rsp+28h+arg_0]
0x1800338ab  xor     eax, eax
0x1800338ad  add     rsp, 20h
0x1800338b1  pop     rdi
0x1800338b2  retn
0x1800338b3  xor     r9d, r9d; lpArguments
0x1800338b6  xor     r8d, r8d; nNumberOfArguments
0x1800338b9  mov     ecx, 0C000008Ch; dwExceptionCode
0x1800338be  lea     edx, [r9+1]; dwExceptionFlags
0x1800338c2  call    cs:__imp_RaiseException
```
