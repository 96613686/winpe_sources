# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x180005a00`
- end: `0x180005aa8`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `168`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800047cc`
- `0x180005ab0`

## callees

- `0x180002e94`
- `0x180005a00`
- `0x180009aac`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005a55`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005a6b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005a55`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005a6b`

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
        JUMPOUT(0x180005AA7LL);
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
0x180005a00  mov     [rsp+arg_0], rbx
0x180005a05  mov     [rsp+arg_8], rsi
0x180005a0a  push    rdi
0x180005a0b  sub     rsp, 20h
0x180005a0f  mov     eax, [rcx+10h]
0x180005a12  mov     rbx, rcx
0x180005a15  test    eax, eax
0x180005a17  jle     short loc_180005A4D
0x180005a19  xor     edi, edi
0x180005a1b  test    edi, edi
0x180005a1d  js      short loc_180005A92
0x180005a1f  cmp     edi, eax
0x180005a21  jge     short loc_180005A92
0x180005a23  mov     rcx, [rbx]
0x180005a26  movsxd  rsi, edi
0x180005a29  mov     rcx, [rcx+rsi*8]; Block
0x180005a2d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180005a32  cmp     edi, [rbx+10h]
0x180005a35  jge     short loc_180005A9D
0x180005a37  mov     rcx, [rbx+8]
0x180005a3b  mov     rcx, [rcx+rsi*8]; Block
0x180005a3f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180005a44  mov     eax, [rbx+10h]
0x180005a47  inc     edi
0x180005a49  cmp     edi, eax
0x180005a4b  jl      short loc_180005A1B
0x180005a4d  mov     rcx, [rbx]; Block
0x180005a50  test    rcx, rcx
0x180005a53  jz      short loc_180005A62
0x180005a55  call    cs:__imp_free
0x180005a5b  mov     qword ptr [rbx], 0
0x180005a62  mov     rcx, [rbx+8]; Block
0x180005a66  test    rcx, rcx
0x180005a69  jz      short loc_180005A79
0x180005a6b  call    cs:__imp_free
0x180005a71  mov     qword ptr [rbx+8], 0
0x180005a79  mov     rsi, [rsp+28h+arg_8]
0x180005a7e  xor     eax, eax
0x180005a80  mov     dword ptr [rbx+10h], 0
0x180005a87  mov     rbx, [rsp+28h+arg_0]
0x180005a8c  add     rsp, 20h
0x180005a90  pop     rdi
0x180005a91  retn
0x180005a92  mov     ecx, 0C000008Ch; unsigned int
0x180005a97  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x180005a9c  int     3; Trap to Debugger
0x180005a9d  mov     ecx, 0C000008Ch; unsigned int
0x180005aa2  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
