# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x180006040`
- end: `0x1800060e8`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `168`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180004e08`
- `0x1800060f0`

## callees

- `0x1800033f4`
- `0x180006040`
- `0x18000a0ec`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180006095`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800060ab`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180006095`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800060ab`

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
        JUMPOUT(0x1800060E7LL);
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
0x180006040  mov     [rsp+arg_0], rbx
0x180006045  mov     [rsp+arg_8], rsi
0x18000604a  push    rdi
0x18000604b  sub     rsp, 20h
0x18000604f  mov     eax, [rcx+10h]
0x180006052  mov     rbx, rcx
0x180006055  test    eax, eax
0x180006057  jle     short loc_18000608D
0x180006059  xor     edi, edi
0x18000605b  test    edi, edi
0x18000605d  js      short loc_1800060D2
0x18000605f  cmp     edi, eax
0x180006061  jge     short loc_1800060D2
0x180006063  mov     rcx, [rbx]
0x180006066  movsxd  rsi, edi
0x180006069  mov     rcx, [rcx+rsi*8]; Block
0x18000606d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006072  cmp     edi, [rbx+10h]
0x180006075  jge     short loc_1800060DD
0x180006077  mov     rcx, [rbx+8]
0x18000607b  mov     rcx, [rcx+rsi*8]; Block
0x18000607f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006084  mov     eax, [rbx+10h]
0x180006087  inc     edi
0x180006089  cmp     edi, eax
0x18000608b  jl      short loc_18000605B
0x18000608d  mov     rcx, [rbx]; Block
0x180006090  test    rcx, rcx
0x180006093  jz      short loc_1800060A2
0x180006095  call    cs:__imp_free
0x18000609b  mov     qword ptr [rbx], 0
0x1800060a2  mov     rcx, [rbx+8]; Block
0x1800060a6  test    rcx, rcx
0x1800060a9  jz      short loc_1800060B9
0x1800060ab  call    cs:__imp_free
0x1800060b1  mov     qword ptr [rbx+8], 0
0x1800060b9  mov     rsi, [rsp+28h+arg_8]
0x1800060be  xor     eax, eax
0x1800060c0  mov     dword ptr [rbx+10h], 0
0x1800060c7  mov     rbx, [rsp+28h+arg_0]
0x1800060cc  add     rsp, 20h
0x1800060d0  pop     rdi
0x1800060d1  retn
0x1800060d2  mov     ecx, 0C000008Ch; unsigned int
0x1800060d7  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x1800060dc  int     3; Trap to Debugger
0x1800060dd  mov     ecx, 0C000008Ch; unsigned int
0x1800060e2  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
