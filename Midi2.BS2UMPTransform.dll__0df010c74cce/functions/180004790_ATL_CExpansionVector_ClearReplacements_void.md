# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x180004790`
- end: `0x180004838`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `168`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180003554`
- `0x180004840`

## callees

- `0x180001e84`
- `0x180004790`
- `0x18000883c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800047e5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800047fb`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800047e5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800047fb`

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
        JUMPOUT(0x180004837LL);
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
0x180004790  mov     [rsp+arg_0], rbx
0x180004795  mov     [rsp+arg_8], rsi
0x18000479a  push    rdi
0x18000479b  sub     rsp, 20h
0x18000479f  mov     eax, [rcx+10h]
0x1800047a2  mov     rbx, rcx
0x1800047a5  test    eax, eax
0x1800047a7  jle     short loc_1800047DD
0x1800047a9  xor     edi, edi
0x1800047ab  test    edi, edi
0x1800047ad  js      short loc_180004822
0x1800047af  cmp     edi, eax
0x1800047b1  jge     short loc_180004822
0x1800047b3  mov     rcx, [rbx]
0x1800047b6  movsxd  rsi, edi
0x1800047b9  mov     rcx, [rcx+rsi*8]; Block
0x1800047bd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800047c2  cmp     edi, [rbx+10h]
0x1800047c5  jge     short loc_18000482D
0x1800047c7  mov     rcx, [rbx+8]
0x1800047cb  mov     rcx, [rcx+rsi*8]; Block
0x1800047cf  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800047d4  mov     eax, [rbx+10h]
0x1800047d7  inc     edi
0x1800047d9  cmp     edi, eax
0x1800047db  jl      short loc_1800047AB
0x1800047dd  mov     rcx, [rbx]; Block
0x1800047e0  test    rcx, rcx
0x1800047e3  jz      short loc_1800047F2
0x1800047e5  call    cs:__imp_free
0x1800047eb  mov     qword ptr [rbx], 0
0x1800047f2  mov     rcx, [rbx+8]; Block
0x1800047f6  test    rcx, rcx
0x1800047f9  jz      short loc_180004809
0x1800047fb  call    cs:__imp_free
0x180004801  mov     qword ptr [rbx+8], 0
0x180004809  mov     rsi, [rsp+28h+arg_8]
0x18000480e  xor     eax, eax
0x180004810  mov     dword ptr [rbx+10h], 0
0x180004817  mov     rbx, [rsp+28h+arg_0]
0x18000481c  add     rsp, 20h
0x180004820  pop     rdi
0x180004821  retn
0x180004822  mov     ecx, 0C000008Ch; unsigned int
0x180004827  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x18000482c  int     3; Trap to Debugger
0x18000482d  mov     ecx, 0C000008Ch; unsigned int
0x180004832  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
