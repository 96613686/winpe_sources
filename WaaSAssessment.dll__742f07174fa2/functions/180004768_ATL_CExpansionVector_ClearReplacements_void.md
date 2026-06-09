# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x180004768`
- end: `0x180004812`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `170`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180003190`
- `0x180004820`

## callees

- `0x180004768`
- `0x1800069fc`

## import_xrefs

- `msvcrt!free` at `0x1800047bf`
- `msvcrt!free` at `0x1800047d5`
- `msvcrt!free` at `0x1800047bf`
- `msvcrt!free` at `0x1800047d5`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180004795`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800047a8`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180004795`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800047a8`

## pseudocode

```c
__int64 __fastcall ATL::CExpansionVector::ClearReplacements(ATL::CExpansionVector *this, int a2, unsigned int a3)
{
  int v3; // eax
  int i; // edi
  int v6; // edx
  unsigned int v7; // r8d
  void *v8; // rcx
  __int64 result; // rax

  v3 = *((_DWORD *)this + 4);
  if ( v3 > 0 )
  {
    for ( i = 0; i < v3; ++i )
    {
      if ( i < 0 || i >= v3 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0xC000008CLL, a2, a3);
        __debugbreak();
      }
      operator delete[](*(void **)(*(_QWORD *)this + 8LL * i));
      if ( i >= *((_DWORD *)this + 4) )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0xC000008CLL, v6, v7);
        JUMPOUT(0x180004811LL);
      }
      operator delete[](*(void **)(*((_QWORD *)this + 1) + 8LL * i));
      v3 = *((_DWORD *)this + 4);
    }
  }
  if ( *(_QWORD *)this )
  {
    free(*(void **)this);
    *(_QWORD *)this = 0;
  }
  v8 = (void *)*((_QWORD *)this + 1);
  if ( v8 )
  {
    free(v8);
    *((_QWORD *)this + 1) = 0;
  }
  result = 0;
  *((_DWORD *)this + 4) = 0;
  return result;
}

```

## disassembly

```asm
0x180004768  mov     [rsp+arg_0], rbx
0x18000476d  mov     [rsp+arg_8], rsi
0x180004772  push    rdi
0x180004773  sub     rsp, 20h
0x180004777  mov     eax, [rcx+10h]
0x18000477a  mov     rbx, rcx
0x18000477d  test    eax, eax
0x18000477f  jle     short loc_1800047B7
0x180004781  xor     edi, edi
0x180004783  test    edi, edi
0x180004785  js      short loc_1800047FC
0x180004787  cmp     edi, eax
0x180004789  jge     short loc_1800047FC
0x18000478b  mov     rcx, [rbx]
0x18000478e  movsxd  rsi, edi
0x180004791  mov     rcx, [rcx+rsi*8]
0x180004795  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000479b  cmp     edi, [rbx+10h]
0x18000479e  jge     short loc_180004807
0x1800047a0  mov     rcx, [rbx+8]
0x1800047a4  mov     rcx, [rcx+rsi*8]
0x1800047a8  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800047ae  mov     eax, [rbx+10h]
0x1800047b1  inc     edi
0x1800047b3  cmp     edi, eax
0x1800047b5  jl      short loc_180004783
0x1800047b7  mov     rcx, [rbx]; Block
0x1800047ba  test    rcx, rcx
0x1800047bd  jz      short loc_1800047CC
0x1800047bf  call    cs:__imp_free
0x1800047c5  mov     qword ptr [rbx], 0
0x1800047cc  mov     rcx, [rbx+8]; Block
0x1800047d0  test    rcx, rcx
0x1800047d3  jz      short loc_1800047E3
0x1800047d5  call    cs:__imp_free
0x1800047db  mov     qword ptr [rbx+8], 0
0x1800047e3  mov     rsi, [rsp+28h+arg_8]
0x1800047e8  xor     eax, eax
0x1800047ea  mov     dword ptr [rbx+10h], 0
0x1800047f1  mov     rbx, [rsp+28h+arg_0]
0x1800047f6  add     rsp, 20h
0x1800047fa  pop     rdi
0x1800047fb  retn
0x1800047fc  mov     ecx, 0C000008Ch; this
0x180004801  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180004806  int     3; Trap to Debugger
0x180004807  mov     ecx, 0C000008Ch; this
0x18000480c  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
