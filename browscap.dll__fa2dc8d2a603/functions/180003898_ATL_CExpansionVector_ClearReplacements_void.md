# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x180003898`
- end: `0x180003954`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `188`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002530`
- `0x180003960`

## callees

- `0x180003898`
- `0x18000701c`

## import_xrefs

- `msvcrt!free` at `0x1800038d2`
- `msvcrt!free` at `0x1800038ea`
- `msvcrt!free` at `0x180003901`
- `msvcrt!free` at `0x180003917`
- `msvcrt!free` at `0x1800038d2`
- `msvcrt!free` at `0x1800038ea`
- `msvcrt!free` at `0x180003901`
- `msvcrt!free` at `0x180003917`

## pseudocode

```c
__int64 __fastcall ATL::CExpansionVector::ClearReplacements(ATL::CExpansionVector *this, unsigned int a2)
{
  int v2; // eax
  int i; // edi
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  __int64 result; // rax

  v2 = *((_DWORD *)this + 4);
  if ( v2 > 0 )
  {
    for ( i = 0; i < v2; ++i )
    {
      if ( i < 0 || i >= v2 )
      {
        ATL::_AtlRaiseException(0xC000008C, a2);
        JUMPOUT(0x180003953LL);
      }
      v5 = *(void **)(*(_QWORD *)this + 8LL * i);
      if ( v5 )
        free(v5);
      if ( i >= *((_DWORD *)this + 4) )
      {
        ATL::_AtlRaiseException(0xC000008C, a2);
        __debugbreak();
      }
      v6 = *(void **)(*((_QWORD *)this + 1) + 8LL * i);
      if ( v6 )
        free(v6);
      v2 = *((_DWORD *)this + 4);
    }
  }
  if ( *(_QWORD *)this )
  {
    free(*(void **)this);
    *(_QWORD *)this = 0;
  }
  v7 = (void *)*((_QWORD *)this + 1);
  if ( v7 )
  {
    free(v7);
    *((_QWORD *)this + 1) = 0;
  }
  result = 0;
  *((_DWORD *)this + 4) = 0;
  return result;
}

```

## disassembly

```asm
0x180003898  mov     [rsp+arg_0], rbx
0x18000389d  mov     [rsp+arg_8], rsi
0x1800038a2  push    rdi
0x1800038a3  sub     rsp, 20h
0x1800038a7  mov     eax, [rcx+10h]
0x1800038aa  mov     rbx, rcx
0x1800038ad  test    eax, eax
0x1800038af  jle     short loc_1800038F9
0x1800038b1  xor     edi, edi
0x1800038b3  test    edi, edi
0x1800038b5  js      loc_180003949
0x1800038bb  cmp     edi, eax
0x1800038bd  jge     loc_180003949
0x1800038c3  mov     rax, [rbx]
0x1800038c6  movsxd  rsi, edi
0x1800038c9  mov     rcx, [rax+rsi*8]; Block
0x1800038cd  test    rcx, rcx
0x1800038d0  jz      short loc_1800038D8
0x1800038d2  call    cs:__imp_free
0x1800038d8  cmp     edi, [rbx+10h]
0x1800038db  jge     short loc_18000393E
0x1800038dd  mov     rax, [rbx+8]
0x1800038e1  mov     rcx, [rax+rsi*8]; Block
0x1800038e5  test    rcx, rcx
0x1800038e8  jz      short loc_1800038F0
0x1800038ea  call    cs:__imp_free
0x1800038f0  mov     eax, [rbx+10h]
0x1800038f3  inc     edi
0x1800038f5  cmp     edi, eax
0x1800038f7  jl      short loc_1800038B3
0x1800038f9  mov     rcx, [rbx]; Block
0x1800038fc  test    rcx, rcx
0x1800038ff  jz      short loc_18000390E
0x180003901  call    cs:__imp_free
0x180003907  mov     qword ptr [rbx], 0
0x18000390e  mov     rcx, [rbx+8]; Block
0x180003912  test    rcx, rcx
0x180003915  jz      short loc_180003925
0x180003917  call    cs:__imp_free
0x18000391d  mov     qword ptr [rbx+8], 0
0x180003925  mov     rsi, [rsp+28h+arg_8]
0x18000392a  xor     eax, eax
0x18000392c  mov     dword ptr [rbx+10h], 0
0x180003933  mov     rbx, [rsp+28h+arg_0]
0x180003938  add     rsp, 20h
0x18000393c  pop     rdi
0x18000393d  retn
0x18000393e  mov     ecx, 0C000008Ch; unsigned int
0x180003943  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x180003948  int     3; Trap to Debugger
0x180003949  mov     ecx, 0C000008Ch; unsigned int
0x18000394e  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
