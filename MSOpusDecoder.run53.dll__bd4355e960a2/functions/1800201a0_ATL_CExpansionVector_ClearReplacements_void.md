# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x1800201a0`
- end: `0x180020248`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `168`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18001ee9c`
- `0x180020250`

## callees

- `0x180001434`
- `0x1800201a0`
- `0x18002262c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800201f5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002020b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800201f5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002020b`

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
        JUMPOUT(0x180020247LL);
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
0x1800201a0  mov     [rsp+arg_0], rbx
0x1800201a5  mov     [rsp+arg_8], rsi
0x1800201aa  push    rdi
0x1800201ab  sub     rsp, 20h
0x1800201af  mov     eax, [rcx+10h]
0x1800201b2  mov     rbx, rcx
0x1800201b5  test    eax, eax
0x1800201b7  jle     short loc_1800201ED
0x1800201b9  xor     edi, edi
0x1800201bb  test    edi, edi
0x1800201bd  js      short loc_180020232
0x1800201bf  cmp     edi, eax
0x1800201c1  jge     short loc_180020232
0x1800201c3  mov     rcx, [rbx]
0x1800201c6  movsxd  rsi, edi
0x1800201c9  mov     rcx, [rcx+rsi*8]; Block
0x1800201cd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800201d2  cmp     edi, [rbx+10h]
0x1800201d5  jge     short loc_18002023D
0x1800201d7  mov     rcx, [rbx+8]
0x1800201db  mov     rcx, [rcx+rsi*8]; Block
0x1800201df  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800201e4  mov     eax, [rbx+10h]
0x1800201e7  inc     edi
0x1800201e9  cmp     edi, eax
0x1800201eb  jl      short loc_1800201BB
0x1800201ed  mov     rcx, [rbx]; Block
0x1800201f0  test    rcx, rcx
0x1800201f3  jz      short loc_180020202
0x1800201f5  call    cs:__imp_free
0x1800201fb  mov     qword ptr [rbx], 0
0x180020202  mov     rcx, [rbx+8]; Block
0x180020206  test    rcx, rcx
0x180020209  jz      short loc_180020219
0x18002020b  call    cs:__imp_free
0x180020211  mov     qword ptr [rbx+8], 0
0x180020219  mov     rsi, [rsp+28h+arg_8]
0x18002021e  xor     eax, eax
0x180020220  mov     dword ptr [rbx+10h], 0
0x180020227  mov     rbx, [rsp+28h+arg_0]
0x18002022c  add     rsp, 20h
0x180020230  pop     rdi
0x180020231  retn
0x180020232  mov     ecx, 0C000008Ch; unsigned int
0x180020237  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x18002023c  int     3; Trap to Debugger
0x18002023d  mov     ecx, 0C000008Ch; unsigned int
0x180020242  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
