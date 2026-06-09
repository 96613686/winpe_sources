# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x180004ee0`
- end: `0x180004f88`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `168`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180003ca8`
- `0x180004f90`

## callees

- `0x180002494`
- `0x180004ee0`
- `0x180008fec`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180004f35`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180004f4b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180004f35`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180004f4b`

## pseudocode

```c
__int64 __fastcall ATL::CExpansionVector::ClearReplacements(ATL::CExpansionVector *this, unsigned int a2)
{
  int v2; // eax
  int i; // edi
  unsigned int v5; // edx
  void *v6; // rcx
  __int64 result; // rax

  v2 = *((_DWORD *)this + 4);
  if ( v2 > 0 )
  {
    for ( i = 0; i < v2; ++i )
    {
      if ( i < 0 || i >= v2 )
      {
        ATL::_AtlRaiseException(0xC000008C, a2);
        __debugbreak();
      }
      operator delete(*(void **)(*(_QWORD *)this + 8LL * i));
      if ( i >= *((_DWORD *)this + 4) )
      {
        ATL::_AtlRaiseException(0xC000008C, v5);
        JUMPOUT(0x180004F87LL);
      }
      operator delete(*(void **)(*((_QWORD *)this + 1) + 8LL * i));
      v2 = *((_DWORD *)this + 4);
    }
  }
  if ( *(_QWORD *)this )
  {
    free(*(void **)this);
    *(_QWORD *)this = 0;
  }
  v6 = (void *)*((_QWORD *)this + 1);
  if ( v6 )
  {
    free(v6);
    *((_QWORD *)this + 1) = 0;
  }
  result = 0;
  *((_DWORD *)this + 4) = 0;
  return result;
}

```

## disassembly

```asm
0x180004ee0  mov     [rsp+arg_0], rbx
0x180004ee5  mov     [rsp+arg_8], rsi
0x180004eea  push    rdi
0x180004eeb  sub     rsp, 20h
0x180004eef  mov     eax, [rcx+10h]
0x180004ef2  mov     rbx, rcx
0x180004ef5  test    eax, eax
0x180004ef7  jle     short loc_180004F2D
0x180004ef9  xor     edi, edi
0x180004efb  test    edi, edi
0x180004efd  js      short loc_180004F72
0x180004eff  cmp     edi, eax
0x180004f01  jge     short loc_180004F72
0x180004f03  mov     rcx, [rbx]
0x180004f06  movsxd  rsi, edi
0x180004f09  mov     rcx, [rcx+rsi*8]; Block
0x180004f0d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004f12  cmp     edi, [rbx+10h]
0x180004f15  jge     short loc_180004F7D
0x180004f17  mov     rcx, [rbx+8]
0x180004f1b  mov     rcx, [rcx+rsi*8]; Block
0x180004f1f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004f24  mov     eax, [rbx+10h]
0x180004f27  inc     edi
0x180004f29  cmp     edi, eax
0x180004f2b  jl      short loc_180004EFB
0x180004f2d  mov     rcx, [rbx]; Block
0x180004f30  test    rcx, rcx
0x180004f33  jz      short loc_180004F42
0x180004f35  call    cs:__imp_free
0x180004f3b  mov     qword ptr [rbx], 0
0x180004f42  mov     rcx, [rbx+8]; Block
0x180004f46  test    rcx, rcx
0x180004f49  jz      short loc_180004F59
0x180004f4b  call    cs:__imp_free
0x180004f51  mov     qword ptr [rbx+8], 0
0x180004f59  mov     rsi, [rsp+28h+arg_8]
0x180004f5e  xor     eax, eax
0x180004f60  mov     dword ptr [rbx+10h], 0
0x180004f67  mov     rbx, [rsp+28h+arg_0]
0x180004f6c  add     rsp, 20h
0x180004f70  pop     rdi
0x180004f71  retn
0x180004f72  mov     ecx, 0C000008Ch; unsigned int
0x180004f77  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x180004f7c  int     3; Trap to Debugger
0x180004f7d  mov     ecx, 0C000008Ch; unsigned int
0x180004f82  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
