# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x180004350`
- end: `0x1800043fa`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `170`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180002c18`
- `0x180004400`

## callees

- `0x180004350`
- `0x1800068ac`

## import_xrefs

- `msvcrt!free` at `0x1800043a7`
- `msvcrt!free` at `0x1800043bd`
- `msvcrt!free` at `0x1800043a7`
- `msvcrt!free` at `0x1800043bd`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000437d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180004390`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000437d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180004390`

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
        JUMPOUT(0x1800043F9LL);
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
0x180004350  mov     [rsp+arg_0], rbx
0x180004355  mov     [rsp+arg_8], rsi
0x18000435a  push    rdi
0x18000435b  sub     rsp, 20h
0x18000435f  mov     eax, [rcx+10h]
0x180004362  mov     rbx, rcx
0x180004365  test    eax, eax
0x180004367  jle     short loc_18000439F
0x180004369  xor     edi, edi
0x18000436b  test    edi, edi
0x18000436d  js      short loc_1800043E4
0x18000436f  cmp     edi, eax
0x180004371  jge     short loc_1800043E4
0x180004373  mov     rcx, [rbx]
0x180004376  movsxd  rsi, edi
0x180004379  mov     rcx, [rcx+rsi*8]
0x18000437d  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180004383  cmp     edi, [rbx+10h]
0x180004386  jge     short loc_1800043EF
0x180004388  mov     rcx, [rbx+8]
0x18000438c  mov     rcx, [rcx+rsi*8]
0x180004390  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180004396  mov     eax, [rbx+10h]
0x180004399  inc     edi
0x18000439b  cmp     edi, eax
0x18000439d  jl      short loc_18000436B
0x18000439f  mov     rcx, [rbx]; Block
0x1800043a2  test    rcx, rcx
0x1800043a5  jz      short loc_1800043B4
0x1800043a7  call    cs:__imp_free
0x1800043ad  mov     qword ptr [rbx], 0
0x1800043b4  mov     rcx, [rbx+8]; Block
0x1800043b8  test    rcx, rcx
0x1800043bb  jz      short loc_1800043CB
0x1800043bd  call    cs:__imp_free
0x1800043c3  mov     qword ptr [rbx+8], 0
0x1800043cb  mov     rsi, [rsp+28h+arg_8]
0x1800043d0  xor     eax, eax
0x1800043d2  mov     dword ptr [rbx+10h], 0
0x1800043d9  mov     rbx, [rsp+28h+arg_0]
0x1800043de  add     rsp, 20h
0x1800043e2  pop     rdi
0x1800043e3  retn
0x1800043e4  mov     ecx, 0C000008Ch; unsigned int
0x1800043e9  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x1800043ee  int     3; Trap to Debugger
0x1800043ef  mov     ecx, 0C000008Ch; unsigned int
0x1800043f4  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
