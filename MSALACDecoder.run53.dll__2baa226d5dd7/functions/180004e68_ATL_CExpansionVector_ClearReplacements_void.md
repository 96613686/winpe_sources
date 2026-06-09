# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x180004e68`
- end: `0x180004f10`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `168`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000407c`
- `0x180004f20`

## callees

- `0x180001144`
- `0x180004e68`
- `0x18000725c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180004ebd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180004ed3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180004ebd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180004ed3`

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
        JUMPOUT(0x180004F0FLL);
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
0x180004e68  mov     [rsp+arg_0], rbx
0x180004e6d  mov     [rsp+arg_8], rsi
0x180004e72  push    rdi
0x180004e73  sub     rsp, 20h
0x180004e77  mov     eax, [rcx+10h]
0x180004e7a  mov     rbx, rcx
0x180004e7d  test    eax, eax
0x180004e7f  jle     short loc_180004EB5
0x180004e81  xor     edi, edi
0x180004e83  test    edi, edi
0x180004e85  js      short loc_180004EFA
0x180004e87  cmp     edi, eax
0x180004e89  jge     short loc_180004EFA
0x180004e8b  mov     rcx, [rbx]
0x180004e8e  movsxd  rsi, edi
0x180004e91  mov     rcx, [rcx+rsi*8]; Block
0x180004e95  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004e9a  cmp     edi, [rbx+10h]
0x180004e9d  jge     short loc_180004F05
0x180004e9f  mov     rcx, [rbx+8]
0x180004ea3  mov     rcx, [rcx+rsi*8]; Block
0x180004ea7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004eac  mov     eax, [rbx+10h]
0x180004eaf  inc     edi
0x180004eb1  cmp     edi, eax
0x180004eb3  jl      short loc_180004E83
0x180004eb5  mov     rcx, [rbx]; Block
0x180004eb8  test    rcx, rcx
0x180004ebb  jz      short loc_180004ECA
0x180004ebd  call    cs:__imp_free
0x180004ec3  mov     qword ptr [rbx], 0
0x180004eca  mov     rcx, [rbx+8]; Block
0x180004ece  test    rcx, rcx
0x180004ed1  jz      short loc_180004EE1
0x180004ed3  call    cs:__imp_free
0x180004ed9  mov     qword ptr [rbx+8], 0
0x180004ee1  mov     rsi, [rsp+28h+arg_8]
0x180004ee6  xor     eax, eax
0x180004ee8  mov     dword ptr [rbx+10h], 0
0x180004eef  mov     rbx, [rsp+28h+arg_0]
0x180004ef4  add     rsp, 20h
0x180004ef8  pop     rdi
0x180004ef9  retn
0x180004efa  mov     ecx, 0C000008Ch; unsigned int
0x180004eff  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x180004f04  int     3; Trap to Debugger
0x180004f05  mov     ecx, 0C000008Ch; unsigned int
0x180004f0a  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
