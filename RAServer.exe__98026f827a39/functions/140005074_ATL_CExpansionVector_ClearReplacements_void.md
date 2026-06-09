# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x140005074`
- end: `0x1400050e9`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140003a00`
- `0x1400050f0`

## callees

- `0x140005074`
- `0x140006f0c`
- `0x14000a050`

## import_xrefs

- `KERNEL32!RaiseException` at `0x1400050e2`
- `KERNEL32!RaiseException` at `0x1400050e2`
- `msvcrt!??_V@YAXPEAX@Z` at `0x14000509c`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1400050af`
- `msvcrt!??_V@YAXPEAX@Z` at `0x14000509c`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1400050af`

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
        JUMPOUT(0x1400050E8LL);
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
0x140005074  mov     [rsp+arg_0], rbx
0x140005079  push    rdi
0x14000507a  sub     rsp, 20h
0x14000507e  mov     eax, [rcx+10h]
0x140005081  mov     rdi, rcx
0x140005084  test    eax, eax
0x140005086  jle     short loc_1400050BE
0x140005088  xor     ebx, ebx
0x14000508a  test    ebx, ebx
0x14000508c  js      short loc_1400050D3
0x14000508e  cmp     ebx, eax
0x140005090  jge     short loc_1400050D3
0x140005092  mov     rcx, [rdi]
0x140005095  movsxd  rax, ebx
0x140005098  mov     rcx, [rcx+rax*8]
0x14000509c  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1400050a2  mov     edx, ebx
0x1400050a4  mov     rcx, rdi
0x1400050a7  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x1400050ac  mov     rcx, [rax]
0x1400050af  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1400050b5  mov     eax, [rdi+10h]
0x1400050b8  inc     ebx
0x1400050ba  cmp     ebx, eax
0x1400050bc  jl      short loc_14000508A
0x1400050be  mov     rcx, rdi
0x1400050c1  call    ?RemoveAll@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::RemoveAll(void)
0x1400050c6  mov     rbx, [rsp+28h+arg_0]
0x1400050cb  xor     eax, eax
0x1400050cd  add     rsp, 20h
0x1400050d1  pop     rdi
0x1400050d2  retn
0x1400050d3  xor     r9d, r9d; lpArguments
0x1400050d6  xor     r8d, r8d; nNumberOfArguments
0x1400050d9  mov     ecx, 0C000008Ch; dwExceptionCode
0x1400050de  lea     edx, [r9+1]; dwExceptionFlags
0x1400050e2  call    cs:__imp_RaiseException
```
