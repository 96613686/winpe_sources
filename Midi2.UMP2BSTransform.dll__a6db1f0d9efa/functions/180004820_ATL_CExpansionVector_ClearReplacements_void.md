# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x180004820`
- end: `0x1800048c8`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `168`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800035e4`
- `0x1800048d0`

## callees

- `0x180001f14`
- `0x180004820`
- `0x1800088cc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180004875`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000488b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180004875`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000488b`

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
        JUMPOUT(0x1800048C7LL);
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
0x180004820  mov     [rsp+arg_0], rbx
0x180004825  mov     [rsp+arg_8], rsi
0x18000482a  push    rdi
0x18000482b  sub     rsp, 20h
0x18000482f  mov     eax, [rcx+10h]
0x180004832  mov     rbx, rcx
0x180004835  test    eax, eax
0x180004837  jle     short loc_18000486D
0x180004839  xor     edi, edi
0x18000483b  test    edi, edi
0x18000483d  js      short loc_1800048B2
0x18000483f  cmp     edi, eax
0x180004841  jge     short loc_1800048B2
0x180004843  mov     rcx, [rbx]
0x180004846  movsxd  rsi, edi
0x180004849  mov     rcx, [rcx+rsi*8]; Block
0x18000484d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004852  cmp     edi, [rbx+10h]
0x180004855  jge     short loc_1800048BD
0x180004857  mov     rcx, [rbx+8]
0x18000485b  mov     rcx, [rcx+rsi*8]; Block
0x18000485f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004864  mov     eax, [rbx+10h]
0x180004867  inc     edi
0x180004869  cmp     edi, eax
0x18000486b  jl      short loc_18000483B
0x18000486d  mov     rcx, [rbx]; Block
0x180004870  test    rcx, rcx
0x180004873  jz      short loc_180004882
0x180004875  call    cs:__imp_free
0x18000487b  mov     qword ptr [rbx], 0
0x180004882  mov     rcx, [rbx+8]; Block
0x180004886  test    rcx, rcx
0x180004889  jz      short loc_180004899
0x18000488b  call    cs:__imp_free
0x180004891  mov     qword ptr [rbx+8], 0
0x180004899  mov     rsi, [rsp+28h+arg_8]
0x18000489e  xor     eax, eax
0x1800048a0  mov     dword ptr [rbx+10h], 0
0x1800048a7  mov     rbx, [rsp+28h+arg_0]
0x1800048ac  add     rsp, 20h
0x1800048b0  pop     rdi
0x1800048b1  retn
0x1800048b2  mov     ecx, 0C000008Ch; unsigned int
0x1800048b7  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x1800048bc  int     3; Trap to Debugger
0x1800048bd  mov     ecx, 0C000008Ch; unsigned int
0x1800048c2  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
