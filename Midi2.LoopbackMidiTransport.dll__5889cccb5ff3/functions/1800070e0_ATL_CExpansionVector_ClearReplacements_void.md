# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x1800070e0`
- end: `0x180007188`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `168`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180005e6c`
- `0x180007190`

## callees

- `0x1800041a4`
- `0x1800070e0`
- `0x18000b1ac`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007135`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000714b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007135`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000714b`

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
        JUMPOUT(0x180007187LL);
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
0x1800070e0  mov     [rsp+arg_0], rbx
0x1800070e5  mov     [rsp+arg_8], rsi
0x1800070ea  push    rdi
0x1800070eb  sub     rsp, 20h
0x1800070ef  mov     eax, [rcx+10h]
0x1800070f2  mov     rbx, rcx
0x1800070f5  test    eax, eax
0x1800070f7  jle     short loc_18000712D
0x1800070f9  xor     edi, edi
0x1800070fb  test    edi, edi
0x1800070fd  js      short loc_180007172
0x1800070ff  cmp     edi, eax
0x180007101  jge     short loc_180007172
0x180007103  mov     rcx, [rbx]
0x180007106  movsxd  rsi, edi
0x180007109  mov     rcx, [rcx+rsi*8]; Block
0x18000710d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180007112  cmp     edi, [rbx+10h]
0x180007115  jge     short loc_18000717D
0x180007117  mov     rcx, [rbx+8]
0x18000711b  mov     rcx, [rcx+rsi*8]; Block
0x18000711f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180007124  mov     eax, [rbx+10h]
0x180007127  inc     edi
0x180007129  cmp     edi, eax
0x18000712b  jl      short loc_1800070FB
0x18000712d  mov     rcx, [rbx]; Block
0x180007130  test    rcx, rcx
0x180007133  jz      short loc_180007142
0x180007135  call    cs:__imp_free
0x18000713b  mov     qword ptr [rbx], 0
0x180007142  mov     rcx, [rbx+8]; Block
0x180007146  test    rcx, rcx
0x180007149  jz      short loc_180007159
0x18000714b  call    cs:__imp_free
0x180007151  mov     qword ptr [rbx+8], 0
0x180007159  mov     rsi, [rsp+28h+arg_8]
0x18000715e  xor     eax, eax
0x180007160  mov     dword ptr [rbx+10h], 0
0x180007167  mov     rbx, [rsp+28h+arg_0]
0x18000716c  add     rsp, 20h
0x180007170  pop     rdi
0x180007171  retn
0x180007172  mov     ecx, 0C000008Ch; unsigned int
0x180007177  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x18000717c  int     3; Trap to Debugger
0x18000717d  mov     ecx, 0C000008Ch; unsigned int
0x180007182  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
