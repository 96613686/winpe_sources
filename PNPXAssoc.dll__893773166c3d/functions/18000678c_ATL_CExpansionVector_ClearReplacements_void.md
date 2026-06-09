# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x18000678c`
- end: `0x180006834`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `168`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180005368`
- `0x180006840`

## callees

- `0x1800019bc`
- `0x18000678c`
- `0x180008f7c`

## import_xrefs

- `msvcrt!free` at `0x1800067e1`
- `msvcrt!free` at `0x1800067f7`
- `msvcrt!free` at `0x1800067e1`
- `msvcrt!free` at `0x1800067f7`

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
        JUMPOUT(0x180006833LL);
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
0x18000678c  mov     [rsp+arg_0], rbx
0x180006791  mov     [rsp+arg_8], rsi
0x180006796  push    rdi
0x180006797  sub     rsp, 20h
0x18000679b  mov     eax, [rcx+10h]
0x18000679e  mov     rbx, rcx
0x1800067a1  test    eax, eax
0x1800067a3  jle     short loc_1800067D9
0x1800067a5  xor     edi, edi
0x1800067a7  test    edi, edi
0x1800067a9  js      short loc_18000681E
0x1800067ab  cmp     edi, eax
0x1800067ad  jge     short loc_18000681E
0x1800067af  mov     rcx, [rbx]
0x1800067b2  movsxd  rsi, edi
0x1800067b5  mov     rcx, [rcx+rsi*8]; Block
0x1800067b9  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x1800067be  cmp     edi, [rbx+10h]
0x1800067c1  jge     short loc_180006829
0x1800067c3  mov     rcx, [rbx+8]
0x1800067c7  mov     rcx, [rcx+rsi*8]; Block
0x1800067cb  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x1800067d0  mov     eax, [rbx+10h]
0x1800067d3  inc     edi
0x1800067d5  cmp     edi, eax
0x1800067d7  jl      short loc_1800067A7
0x1800067d9  mov     rcx, [rbx]; Block
0x1800067dc  test    rcx, rcx
0x1800067df  jz      short loc_1800067EE
0x1800067e1  call    cs:__imp_free
0x1800067e7  mov     qword ptr [rbx], 0
0x1800067ee  mov     rcx, [rbx+8]; Block
0x1800067f2  test    rcx, rcx
0x1800067f5  jz      short loc_180006805
0x1800067f7  call    cs:__imp_free
0x1800067fd  mov     qword ptr [rbx+8], 0
0x180006805  mov     rsi, [rsp+28h+arg_8]
0x18000680a  xor     eax, eax
0x18000680c  mov     dword ptr [rbx+10h], 0
0x180006813  mov     rbx, [rsp+28h+arg_0]
0x180006818  add     rsp, 20h
0x18000681c  pop     rdi
0x18000681d  retn
0x18000681e  mov     ecx, 0C000008Ch; unsigned int
0x180006823  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x180006828  int     3; Trap to Debugger
0x180006829  mov     ecx, 0C000008Ch; unsigned int
0x18000682e  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
