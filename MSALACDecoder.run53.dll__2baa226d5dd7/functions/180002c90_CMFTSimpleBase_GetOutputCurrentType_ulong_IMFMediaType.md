# CMFTSimpleBase::GetOutputCurrentType(ulong,IMFMediaType * *)

- ea: `0x180002c90`
- end: `0x180002d60`
- name: `?GetOutputCurrentType@CMFTSimpleBase@@UEAAJKPEAPEAUIMFMediaType@@@Z`
- size: `208`
- prototype: `int(CMFTSimpleBase *__hidden this, unsigned int, struct IMFMediaType **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002c90`
- `0x18000b010`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x180002cf8`
- `MFPlat!MFCreateMediaType` at `0x180002cf8`

## pseudocode

```c
__int64 __fastcall CMFTSimpleBase::GetOutputCurrentType(CMFTSimpleBase *this, int a2, struct IMFMediaType **a3)
{
  HRESULT v7; // ebx

  (*(void (__fastcall **)(CMFTSimpleBase *))(*(_QWORD *)this + 208LL))(this);
  if ( a2 )
  {
    (*(void (__fastcall **)(CMFTSimpleBase *))(*(_QWORD *)this + 216LL))(this);
    return 3222091443LL;
  }
  else if ( *((_QWORD *)this + 10) )
  {
    v7 = MFCreateMediaType(a3);
    if ( v7 >= 0 )
    {
      v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 10) + 256LL))(*((_QWORD *)this + 10), *a3);
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
0x180002c90  mov     [rsp+arg_0], rbx
0x180002c95  mov     [rsp+arg_8], rsi
0x180002c9a  push    rdi
0x180002c9b  sub     rsp, 20h
0x180002c9f  mov     rsi, r8
0x180002ca2  mov     ebx, edx
0x180002ca4  mov     rdi, rcx
0x180002ca7  mov     rax, [rcx]
0x180002caa  mov     rax, [rax+0D0h]
0x180002cb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cb6  test    ebx, ebx
0x180002cb8  jz      short loc_180002CD4
0x180002cba  mov     rax, [rdi]
0x180002cbd  mov     rcx, rdi
0x180002cc0  mov     rax, [rax+0D8h]
0x180002cc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ccc  nop
0x180002ccd  mov     eax, 0C00D36B3h
0x180002cd2  jmp     short loc_180002D50
0x180002cd4  cmp     qword ptr [rdi+50h], 0
0x180002cd9  jnz     short loc_180002CF5
0x180002cdb  mov     rax, [rdi]
0x180002cde  mov     rcx, rdi
0x180002ce1  mov     rax, [rax+0D8h]
0x180002ce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ced  nop
0x180002cee  mov     eax, 0C00D6D60h
0x180002cf3  jmp     short loc_180002D50
0x180002cf5  mov     rcx, rsi; ppMFType
0x180002cf8  call    cs:__imp_MFCreateMediaType
0x180002cfe  mov     ebx, eax
0x180002d00  test    eax, eax
0x180002d02  js      short loc_180002D3B
0x180002d04  mov     rcx, [rdi+50h]
0x180002d08  mov     rax, [rcx]
0x180002d0b  mov     rdx, [rsi]
0x180002d0e  mov     rax, [rax+100h]
0x180002d15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d1a  mov     ebx, eax
0x180002d1c  test    eax, eax
0x180002d1e  jns     short loc_180002D3B
0x180002d20  mov     rcx, [rsi]
0x180002d23  test    rcx, rcx
0x180002d26  jz      short loc_180002D3B
0x180002d28  mov     rax, [rcx]
0x180002d2b  mov     rax, [rax+10h]
0x180002d2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d34  mov     qword ptr [rsi], 0
0x180002d3b  mov     rax, [rdi]
0x180002d3e  mov     rcx, rdi
0x180002d41  mov     rax, [rax+0D8h]
0x180002d48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d4d  nop
0x180002d4e  mov     eax, ebx
0x180002d50  mov     rbx, [rsp+28h+arg_0]
0x180002d55  mov     rsi, [rsp+28h+arg_8]
0x180002d5a  add     rsp, 20h
0x180002d5e  pop     rdi
0x180002d5f  retn
```
