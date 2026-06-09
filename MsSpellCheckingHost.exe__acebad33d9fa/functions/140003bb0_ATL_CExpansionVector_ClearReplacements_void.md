# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x140003bb0`
- end: `0x140003c5a`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `170`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140002768`
- `0x140003c60`

## callees

- `0x140003bb0`
- `0x1400062fc`

## import_xrefs

- `msvcrt!free` at `0x140003c07`
- `msvcrt!free` at `0x140003c1d`
- `msvcrt!free` at `0x140003c07`
- `msvcrt!free` at `0x140003c1d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x140003bdd`
- `msvcrt!??_V@YAXPEAX@Z` at `0x140003bf0`
- `msvcrt!??_V@YAXPEAX@Z` at `0x140003bdd`
- `msvcrt!??_V@YAXPEAX@Z` at `0x140003bf0`

## pseudocode

```c
__int64 __fastcall ATL::CExpansionVector::ClearReplacements(ATL::CExpansionVector *this)
{
  int v1; // eax
  int i; // edi
  void *v4; // rcx
  __int64 result; // rax

  v1 = *((_DWORD *)this + 4);
  if ( v1 > 0 )
  {
    for ( i = 0; i < v1; ++i )
    {
      if ( i < 0 || i >= v1 )
      {
        ATL::_AtlRaiseException(0xC000008C);
        __debugbreak();
      }
      operator delete[](*(void **)(*(_QWORD *)this + 8LL * i));
      if ( i >= *((_DWORD *)this + 4) )
      {
        ATL::_AtlRaiseException(0xC000008C);
        JUMPOUT(0x140003C59LL);
      }
      operator delete[](*(void **)(*((_QWORD *)this + 1) + 8LL * i));
      v1 = *((_DWORD *)this + 4);
    }
  }
  if ( *(_QWORD *)this )
  {
    free(*(void **)this);
    *(_QWORD *)this = 0;
  }
  v4 = (void *)*((_QWORD *)this + 1);
  if ( v4 )
  {
    free(v4);
    *((_QWORD *)this + 1) = 0;
  }
  result = 0;
  *((_DWORD *)this + 4) = 0;
  return result;
}

```

## disassembly

```asm
0x140003bb0  mov     [rsp+arg_0], rbx
0x140003bb5  mov     [rsp+arg_8], rsi
0x140003bba  push    rdi
0x140003bbb  sub     rsp, 20h
0x140003bbf  mov     eax, [rcx+10h]
0x140003bc2  mov     rbx, rcx
0x140003bc5  test    eax, eax
0x140003bc7  jle     short loc_140003BFF
0x140003bc9  xor     edi, edi
0x140003bcb  test    edi, edi
0x140003bcd  js      short loc_140003C44
0x140003bcf  cmp     edi, eax
0x140003bd1  jge     short loc_140003C44
0x140003bd3  mov     rcx, [rbx]
0x140003bd6  movsxd  rsi, edi
0x140003bd9  mov     rcx, [rcx+rsi*8]
0x140003bdd  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x140003be3  cmp     edi, [rbx+10h]
0x140003be6  jge     short loc_140003C4F
0x140003be8  mov     rcx, [rbx+8]
0x140003bec  mov     rcx, [rcx+rsi*8]
0x140003bf0  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x140003bf6  mov     eax, [rbx+10h]
0x140003bf9  inc     edi
0x140003bfb  cmp     edi, eax
0x140003bfd  jl      short loc_140003BCB
0x140003bff  mov     rcx, [rbx]; Block
0x140003c02  test    rcx, rcx
0x140003c05  jz      short loc_140003C14
0x140003c07  call    cs:__imp_free
0x140003c0d  mov     qword ptr [rbx], 0
0x140003c14  mov     rcx, [rbx+8]; Block
0x140003c18  test    rcx, rcx
0x140003c1b  jz      short loc_140003C2B
0x140003c1d  call    cs:__imp_free
0x140003c23  mov     qword ptr [rbx+8], 0
0x140003c2b  mov     rsi, [rsp+28h+arg_8]
0x140003c30  xor     eax, eax
0x140003c32  mov     dword ptr [rbx+10h], 0
0x140003c39  mov     rbx, [rsp+28h+arg_0]
0x140003c3e  add     rsp, 20h
0x140003c42  pop     rdi
0x140003c43  retn
0x140003c44  mov     ecx, 0C000008Ch; unsigned int
0x140003c49  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x140003c4e  int     3; Trap to Debugger
0x140003c4f  mov     ecx, 0C000008Ch; unsigned int
0x140003c54  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
