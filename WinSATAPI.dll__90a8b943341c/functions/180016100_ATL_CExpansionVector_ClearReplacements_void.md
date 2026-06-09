# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x180016100`
- end: `0x180016184`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `132`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180014524`
- `0x180016190`

## callees

- `0x180016100`
- `0x180017b2c`
- `0x180019990`
- `0x18001a3ac`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18001612c`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180016145`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001612c`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180016145`

## pseudocode

```c
__int64 __fastcall ATL::CExpansionVector::ClearReplacements(ATL::CExpansionVector *this, unsigned int a2)
{
  int v2; // eax
  int v3; // ebx
  __int64 v5; // rsi
  void **ValueAt; // rax

  v2 = *((_DWORD *)this + 4);
  v3 = 0;
  if ( v2 > 0 )
  {
    v5 = 0;
    do
    {
      if ( v3 < 0 || v3 >= v2 )
      {
        ATL::_AtlRaiseException(0xC000008C, a2);
        JUMPOUT(0x180016183LL);
      }
      operator delete[](*(void **)(v5 + *(_QWORD *)this));
      ValueAt = (void **)ATL::CSimpleMap<unsigned short *,unsigned short *,ATL::CExpansionVectorEqualHelper>::GetValueAt(
                           this,
                           (unsigned int)v3);
      operator delete[](*ValueAt);
      v2 = *((_DWORD *)this + 4);
      ++v3;
      v5 += 8;
    }
    while ( v3 < v2 );
  }
  ATL::CSimpleMap<unsigned short *,unsigned short *,ATL::CExpansionVectorEqualHelper>::RemoveAll(this);
  return 0;
}

```

## disassembly

```asm
0x180016100  mov     [rsp+arg_0], rbx
0x180016105  mov     [rsp+arg_8], rsi
0x18001610a  push    rdi
0x18001610b  sub     rsp, 20h
0x18001610f  mov     eax, [rcx+10h]
0x180016112  xor     ebx, ebx
0x180016114  mov     rdi, rcx
0x180016117  test    eax, eax
0x180016119  jle     short loc_18001615E
0x18001611b  xor     esi, esi
0x18001611d  test    ebx, ebx
0x18001611f  js      short loc_180016179
0x180016121  cmp     ebx, eax
0x180016123  jge     short loc_180016179
0x180016125  mov     rcx, [rdi]
0x180016128  mov     rcx, [rsi+rcx]
0x18001612c  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180016133  nop     dword ptr [rax+rax+00h]
0x180016138  mov     edx, ebx
0x18001613a  mov     rcx, rdi
0x18001613d  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x180016142  mov     rcx, [rax]
0x180016145  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001614c  nop     dword ptr [rax+rax+00h]
0x180016151  mov     eax, [rdi+10h]
0x180016154  inc     ebx
0x180016156  add     rsi, 8
0x18001615a  cmp     ebx, eax
0x18001615c  jl      short loc_18001611D
0x18001615e  mov     rcx, rdi
0x180016161  call    ?RemoveAll@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::RemoveAll(void)
0x180016166  mov     rbx, [rsp+28h+arg_0]
0x18001616b  xor     eax, eax
0x18001616d  mov     rsi, [rsp+28h+arg_8]
0x180016172  add     rsp, 20h
0x180016176  pop     rdi
0x180016177  retn
0x180016179  mov     ecx, 0C000008Ch; unsigned int
0x18001617e  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
