# CMFTSimpleBase::GetInputCurrentType(ulong,IMFMediaType * *)

- ea: `0x18001c540`
- end: `0x18001c610`
- name: `?GetInputCurrentType@CMFTSimpleBase@@UEAAJKPEAPEAUIMFMediaType@@@Z`
- size: `208`
- prototype: `int(CMFTSimpleBase *__hidden this, unsigned int, struct IMFMediaType **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18001c540`
- `0x180024010`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x18001c5a8`
- `MFPlat!MFCreateMediaType` at `0x18001c5a8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMFTSimpleBase::GetInputCurrentType(CMFTSimpleBase *this, int a2, struct IMFMediaType **a3)
{
  HRESULT v7; // ebx

  (*(void (__fastcall **)(CMFTSimpleBase *))(*(_QWORD *)this + 208LL))(this);
  if ( a2 )
  {
    (*(void (__fastcall **)(CMFTSimpleBase *))(*(_QWORD *)this + 216LL))(this);
    return 3222091443LL;
  }
  else if ( *((_QWORD *)this + 5) )
  {
    v7 = MFCreateMediaType(a3);
    if ( v7 >= 0 )
    {
      v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 5) + 256LL))(*((_QWORD *)this + 5), *a3);
      if ( v7 < 0 )
      {
        if ( *a3 )
        {
          ((void (__fastcall *)(_QWORD))(*a3)->lpVtbl->Release)(*a3);
          *a3 = 0;
        }
      }
    }
    (*(void (__fastcall **)(CMFTSimpleBase *))(*(_QWORD *)this + 216LL))(this);
    return (unsigned int)v7;
  }
  else
  {
    (*(void (__fastcall **)(CMFTSimpleBase *))(*(_QWORD *)this + 216LL))(this);
    return 3222105440LL;
  }
}

```

## disassembly

```asm
0x18001c540  mov     [rsp+arg_0], rbx
0x18001c545  mov     [rsp+arg_8], rsi
0x18001c54a  push    rdi
0x18001c54b  sub     rsp, 20h
0x18001c54f  mov     rsi, r8
0x18001c552  mov     ebx, edx
0x18001c554  mov     rdi, rcx
0x18001c557  mov     rax, [rcx]
0x18001c55a  mov     rax, [rax+0D0h]
0x18001c561  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c566  test    ebx, ebx
0x18001c568  jz      short loc_18001C584
0x18001c56a  mov     rax, [rdi]
0x18001c56d  mov     rcx, rdi
0x18001c570  mov     rax, [rax+0D8h]
0x18001c577  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c57c  nop
0x18001c57d  mov     eax, 0C00D36B3h
0x18001c582  jmp     short loc_18001C600
0x18001c584  cmp     qword ptr [rdi+28h], 0
0x18001c589  jnz     short loc_18001C5A5
0x18001c58b  mov     rax, [rdi]
0x18001c58e  mov     rcx, rdi
0x18001c591  mov     rax, [rax+0D8h]
0x18001c598  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c59d  nop
0x18001c59e  mov     eax, 0C00D6D60h
0x18001c5a3  jmp     short loc_18001C600
0x18001c5a5  mov     rcx, rsi; ppMFType
0x18001c5a8  call    cs:__imp_MFCreateMediaType
0x18001c5ae  mov     ebx, eax
0x18001c5b0  test    eax, eax
0x18001c5b2  js      short loc_18001C5EB
0x18001c5b4  mov     rcx, [rdi+28h]
0x18001c5b8  mov     rax, [rcx]
0x18001c5bb  mov     rdx, [rsi]
0x18001c5be  mov     rax, [rax+100h]
0x18001c5c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c5ca  mov     ebx, eax
0x18001c5cc  test    eax, eax
0x18001c5ce  jns     short loc_18001C5EB
0x18001c5d0  mov     rcx, [rsi]
0x18001c5d3  test    rcx, rcx
0x18001c5d6  jz      short loc_18001C5EB
0x18001c5d8  mov     rax, [rcx]
0x18001c5db  mov     rax, [rax+10h]
0x18001c5df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c5e4  mov     qword ptr [rsi], 0
0x18001c5eb  mov     rax, [rdi]
0x18001c5ee  mov     rcx, rdi
0x18001c5f1  mov     rax, [rax+0D8h]
0x18001c5f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c5fd  nop
0x18001c5fe  mov     eax, ebx
0x18001c600  mov     rbx, [rsp+28h+arg_0]
0x18001c605  mov     rsi, [rsp+28h+arg_8]
0x18001c60a  add     rsp, 20h
0x18001c60e  pop     rdi
0x18001c60f  retn
```
