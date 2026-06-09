# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x180006e1c`
- end: `0x180006ec4`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `168`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180005bd0`
- `0x180006ed0`

## callees

- `0x180001bec`
- `0x180006e1c`
- `0x18000b5c4`

## import_xrefs

- `msvcrt!free` at `0x180006e71`
- `msvcrt!free` at `0x180006e87`
- `msvcrt!free` at `0x180006e71`
- `msvcrt!free` at `0x180006e87`

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
      operator delete[](*(void **)(*(_QWORD *)this + 8LL * i));
      if ( i >= *((_DWORD *)this + 4) )
      {
        ATL::_AtlRaiseException(0xC000008C, v5);
        JUMPOUT(0x180006EC3LL);
      }
      operator delete[](*(void **)(*((_QWORD *)this + 1) + 8LL * i));
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
0x180006e1c  mov     [rsp+arg_0], rbx
0x180006e21  mov     [rsp+arg_8], rsi
0x180006e26  push    rdi
0x180006e27  sub     rsp, 20h
0x180006e2b  mov     eax, [rcx+10h]
0x180006e2e  mov     rbx, rcx
0x180006e31  test    eax, eax
0x180006e33  jle     short loc_180006E69
0x180006e35  xor     edi, edi
0x180006e37  test    edi, edi
0x180006e39  js      short loc_180006EAE
0x180006e3b  cmp     edi, eax
0x180006e3d  jge     short loc_180006EAE
0x180006e3f  mov     rcx, [rbx]
0x180006e42  movsxd  rsi, edi
0x180006e45  mov     rcx, [rcx+rsi*8]; Block
0x180006e49  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180006e4e  cmp     edi, [rbx+10h]
0x180006e51  jge     short loc_180006EB9
0x180006e53  mov     rcx, [rbx+8]
0x180006e57  mov     rcx, [rcx+rsi*8]; Block
0x180006e5b  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180006e60  mov     eax, [rbx+10h]
0x180006e63  inc     edi
0x180006e65  cmp     edi, eax
0x180006e67  jl      short loc_180006E37
0x180006e69  mov     rcx, [rbx]; Block
0x180006e6c  test    rcx, rcx
0x180006e6f  jz      short loc_180006E7E
0x180006e71  call    cs:__imp_free
0x180006e77  mov     qword ptr [rbx], 0
0x180006e7e  mov     rcx, [rbx+8]; Block
0x180006e82  test    rcx, rcx
0x180006e85  jz      short loc_180006E95
0x180006e87  call    cs:__imp_free
0x180006e8d  mov     qword ptr [rbx+8], 0
0x180006e95  mov     rsi, [rsp+28h+arg_8]
0x180006e9a  xor     eax, eax
0x180006e9c  mov     dword ptr [rbx+10h], 0
0x180006ea3  mov     rbx, [rsp+28h+arg_0]
0x180006ea8  add     rsp, 20h
0x180006eac  pop     rdi
0x180006ead  retn
0x180006eae  mov     ecx, 0C000008Ch; unsigned int
0x180006eb3  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x180006eb8  int     3; Trap to Debugger
0x180006eb9  mov     ecx, 0C000008Ch; unsigned int
0x180006ebe  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
