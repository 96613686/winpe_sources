# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x180003580`
- end: `0x180003628`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `168`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180002318`
- `0x180003630`

## callees

- `0x18000117c`
- `0x180003580`
- `0x180004e44`

## import_xrefs

- `msvcrt!free` at `0x1800035d5`
- `msvcrt!free` at `0x1800035eb`
- `msvcrt!free` at `0x1800035d5`
- `msvcrt!free` at `0x1800035eb`

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
        JUMPOUT(0x180003627LL);
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
0x180003580  mov     [rsp+arg_0], rbx
0x180003585  mov     [rsp+arg_8], rsi
0x18000358a  push    rdi
0x18000358b  sub     rsp, 20h
0x18000358f  mov     eax, [rcx+10h]
0x180003592  mov     rbx, rcx
0x180003595  test    eax, eax
0x180003597  jle     short loc_1800035CD
0x180003599  xor     edi, edi
0x18000359b  test    edi, edi
0x18000359d  js      short loc_180003612
0x18000359f  cmp     edi, eax
0x1800035a1  jge     short loc_180003612
0x1800035a3  mov     rcx, [rbx]
0x1800035a6  movsxd  rsi, edi
0x1800035a9  mov     rcx, [rcx+rsi*8]; Block
0x1800035ad  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x1800035b2  cmp     edi, [rbx+10h]
0x1800035b5  jge     short loc_18000361D
0x1800035b7  mov     rcx, [rbx+8]
0x1800035bb  mov     rcx, [rcx+rsi*8]; Block
0x1800035bf  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x1800035c4  mov     eax, [rbx+10h]
0x1800035c7  inc     edi
0x1800035c9  cmp     edi, eax
0x1800035cb  jl      short loc_18000359B
0x1800035cd  mov     rcx, [rbx]; Block
0x1800035d0  test    rcx, rcx
0x1800035d3  jz      short loc_1800035E2
0x1800035d5  call    cs:__imp_free
0x1800035db  mov     qword ptr [rbx], 0
0x1800035e2  mov     rcx, [rbx+8]; Block
0x1800035e6  test    rcx, rcx
0x1800035e9  jz      short loc_1800035F9
0x1800035eb  call    cs:__imp_free
0x1800035f1  mov     qword ptr [rbx+8], 0
0x1800035f9  mov     rsi, [rsp+28h+arg_8]
0x1800035fe  xor     eax, eax
0x180003600  mov     dword ptr [rbx+10h], 0
0x180003607  mov     rbx, [rsp+28h+arg_0]
0x18000360c  add     rsp, 20h
0x180003610  pop     rdi
0x180003611  retn
0x180003612  mov     ecx, 0C000008Ch; unsigned int
0x180003617  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x18000361c  int     3; Trap to Debugger
0x18000361d  mov     ecx, 0C000008Ch; unsigned int
0x180003622  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
