# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x1800066d0`
- end: `0x180006778`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `168`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000549c`
- `0x180006780`

## callees

- `0x180003914`
- `0x1800066d0`
- `0x18000a90c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180006725`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000673b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180006725`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000673b`

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
        JUMPOUT(0x180006777LL);
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
0x1800066d0  mov     [rsp+arg_0], rbx
0x1800066d5  mov     [rsp+arg_8], rsi
0x1800066da  push    rdi
0x1800066db  sub     rsp, 20h
0x1800066df  mov     eax, [rcx+10h]
0x1800066e2  mov     rbx, rcx
0x1800066e5  test    eax, eax
0x1800066e7  jle     short loc_18000671D
0x1800066e9  xor     edi, edi
0x1800066eb  test    edi, edi
0x1800066ed  js      short loc_180006762
0x1800066ef  cmp     edi, eax
0x1800066f1  jge     short loc_180006762
0x1800066f3  mov     rcx, [rbx]
0x1800066f6  movsxd  rsi, edi
0x1800066f9  mov     rcx, [rcx+rsi*8]; Block
0x1800066fd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006702  cmp     edi, [rbx+10h]
0x180006705  jge     short loc_18000676D
0x180006707  mov     rcx, [rbx+8]
0x18000670b  mov     rcx, [rcx+rsi*8]; Block
0x18000670f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006714  mov     eax, [rbx+10h]
0x180006717  inc     edi
0x180006719  cmp     edi, eax
0x18000671b  jl      short loc_1800066EB
0x18000671d  mov     rcx, [rbx]; Block
0x180006720  test    rcx, rcx
0x180006723  jz      short loc_180006732
0x180006725  call    cs:__imp_free
0x18000672b  mov     qword ptr [rbx], 0
0x180006732  mov     rcx, [rbx+8]; Block
0x180006736  test    rcx, rcx
0x180006739  jz      short loc_180006749
0x18000673b  call    cs:__imp_free
0x180006741  mov     qword ptr [rbx+8], 0
0x180006749  mov     rsi, [rsp+28h+arg_8]
0x18000674e  xor     eax, eax
0x180006750  mov     dword ptr [rbx+10h], 0
0x180006757  mov     rbx, [rsp+28h+arg_0]
0x18000675c  add     rsp, 20h
0x180006760  pop     rdi
0x180006761  retn
0x180006762  mov     ecx, 0C000008Ch; unsigned int
0x180006767  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x18000676c  int     3; Trap to Debugger
0x18000676d  mov     ecx, 0C000008Ch; unsigned int
0x180006772  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
