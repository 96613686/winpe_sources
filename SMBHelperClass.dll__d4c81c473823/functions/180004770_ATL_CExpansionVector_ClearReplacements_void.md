# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x180004770`
- end: `0x18000481a`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `170`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180003744`
- `0x180004820`

## callees

- `0x180004770`
- `0x1800090c4`

## import_xrefs

- `msvcrt!free` at `0x1800047c7`
- `msvcrt!free` at `0x1800047dd`
- `msvcrt!free` at `0x1800047c7`
- `msvcrt!free` at `0x1800047dd`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000479d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800047b0`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000479d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800047b0`

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
        JUMPOUT(0x180004819LL);
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
0x180004770  mov     [rsp+arg_0], rbx
0x180004775  mov     [rsp+arg_8], rsi
0x18000477a  push    rdi
0x18000477b  sub     rsp, 20h
0x18000477f  mov     eax, [rcx+10h]
0x180004782  mov     rbx, rcx
0x180004785  test    eax, eax
0x180004787  jle     short loc_1800047BF
0x180004789  xor     edi, edi
0x18000478b  test    edi, edi
0x18000478d  js      short loc_180004804
0x18000478f  cmp     edi, eax
0x180004791  jge     short loc_180004804
0x180004793  mov     rcx, [rbx]
0x180004796  movsxd  rsi, edi
0x180004799  mov     rcx, [rcx+rsi*8]
0x18000479d  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800047a3  cmp     edi, [rbx+10h]
0x1800047a6  jge     short loc_18000480F
0x1800047a8  mov     rcx, [rbx+8]
0x1800047ac  mov     rcx, [rcx+rsi*8]
0x1800047b0  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800047b6  mov     eax, [rbx+10h]
0x1800047b9  inc     edi
0x1800047bb  cmp     edi, eax
0x1800047bd  jl      short loc_18000478B
0x1800047bf  mov     rcx, [rbx]; Block
0x1800047c2  test    rcx, rcx
0x1800047c5  jz      short loc_1800047D4
0x1800047c7  call    cs:__imp_free
0x1800047cd  mov     qword ptr [rbx], 0
0x1800047d4  mov     rcx, [rbx+8]; Block
0x1800047d8  test    rcx, rcx
0x1800047db  jz      short loc_1800047EB
0x1800047dd  call    cs:__imp_free
0x1800047e3  mov     qword ptr [rbx+8], 0
0x1800047eb  mov     rsi, [rsp+28h+arg_8]
0x1800047f0  xor     eax, eax
0x1800047f2  mov     dword ptr [rbx+10h], 0
0x1800047f9  mov     rbx, [rsp+28h+arg_0]
0x1800047fe  add     rsp, 20h
0x180004802  pop     rdi
0x180004803  retn
0x180004804  mov     ecx, 0C000008Ch; unsigned int
0x180004809  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x18000480e  int     3; Trap to Debugger
0x18000480f  mov     ecx, 0C000008Ch; unsigned int
0x180004814  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
