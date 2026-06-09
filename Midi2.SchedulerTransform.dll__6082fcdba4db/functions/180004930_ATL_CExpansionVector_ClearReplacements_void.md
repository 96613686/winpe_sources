# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x180004930`
- end: `0x1800049d8`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `168`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800036f4`
- `0x1800049e0`

## callees

- `0x180002024`
- `0x180004930`
- `0x1800089ec`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180004985`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000499b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180004985`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000499b`

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
        JUMPOUT(0x1800049D7LL);
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
0x180004930  mov     [rsp+arg_0], rbx
0x180004935  mov     [rsp+arg_8], rsi
0x18000493a  push    rdi
0x18000493b  sub     rsp, 20h
0x18000493f  mov     eax, [rcx+10h]
0x180004942  mov     rbx, rcx
0x180004945  test    eax, eax
0x180004947  jle     short loc_18000497D
0x180004949  xor     edi, edi
0x18000494b  test    edi, edi
0x18000494d  js      short loc_1800049C2
0x18000494f  cmp     edi, eax
0x180004951  jge     short loc_1800049C2
0x180004953  mov     rcx, [rbx]
0x180004956  movsxd  rsi, edi
0x180004959  mov     rcx, [rcx+rsi*8]; Block
0x18000495d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004962  cmp     edi, [rbx+10h]
0x180004965  jge     short loc_1800049CD
0x180004967  mov     rcx, [rbx+8]
0x18000496b  mov     rcx, [rcx+rsi*8]; Block
0x18000496f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004974  mov     eax, [rbx+10h]
0x180004977  inc     edi
0x180004979  cmp     edi, eax
0x18000497b  jl      short loc_18000494B
0x18000497d  mov     rcx, [rbx]; Block
0x180004980  test    rcx, rcx
0x180004983  jz      short loc_180004992
0x180004985  call    cs:__imp_free
0x18000498b  mov     qword ptr [rbx], 0
0x180004992  mov     rcx, [rbx+8]; Block
0x180004996  test    rcx, rcx
0x180004999  jz      short loc_1800049A9
0x18000499b  call    cs:__imp_free
0x1800049a1  mov     qword ptr [rbx+8], 0
0x1800049a9  mov     rsi, [rsp+28h+arg_8]
0x1800049ae  xor     eax, eax
0x1800049b0  mov     dword ptr [rbx+10h], 0
0x1800049b7  mov     rbx, [rsp+28h+arg_0]
0x1800049bc  add     rsp, 20h
0x1800049c0  pop     rdi
0x1800049c1  retn
0x1800049c2  mov     ecx, 0C000008Ch; unsigned int
0x1800049c7  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x1800049cc  int     3; Trap to Debugger
0x1800049cd  mov     ecx, 0C000008Ch; unsigned int
0x1800049d2  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
