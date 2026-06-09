# CMFTSimpleBase::GetOutputCurrentType(ulong,IMFMediaType * *)

- ea: `0x18001c830`
- end: `0x18001c900`
- name: `?GetOutputCurrentType@CMFTSimpleBase@@UEAAJKPEAPEAUIMFMediaType@@@Z`
- size: `208`
- prototype: `int(CMFTSimpleBase *__hidden this, unsigned int, struct IMFMediaType **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18001c830`
- `0x180024010`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x18001c898`
- `MFPlat!MFCreateMediaType` at `0x18001c898`

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
0x18001c830  mov     [rsp+arg_0], rbx
0x18001c835  mov     [rsp+arg_8], rsi
0x18001c83a  push    rdi
0x18001c83b  sub     rsp, 20h
0x18001c83f  mov     rsi, r8
0x18001c842  mov     ebx, edx
0x18001c844  mov     rdi, rcx
0x18001c847  mov     rax, [rcx]
0x18001c84a  mov     rax, [rax+0D0h]
0x18001c851  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c856  test    ebx, ebx
0x18001c858  jz      short loc_18001C874
0x18001c85a  mov     rax, [rdi]
0x18001c85d  mov     rcx, rdi
0x18001c860  mov     rax, [rax+0D8h]
0x18001c867  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c86c  nop
0x18001c86d  mov     eax, 0C00D36B3h
0x18001c872  jmp     short loc_18001C8F0
0x18001c874  cmp     qword ptr [rdi+50h], 0
0x18001c879  jnz     short loc_18001C895
0x18001c87b  mov     rax, [rdi]
0x18001c87e  mov     rcx, rdi
0x18001c881  mov     rax, [rax+0D8h]
0x18001c888  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c88d  nop
0x18001c88e  mov     eax, 0C00D6D60h
0x18001c893  jmp     short loc_18001C8F0
0x18001c895  mov     rcx, rsi; ppMFType
0x18001c898  call    cs:__imp_MFCreateMediaType
0x18001c89e  mov     ebx, eax
0x18001c8a0  test    eax, eax
0x18001c8a2  js      short loc_18001C8DB
0x18001c8a4  mov     rcx, [rdi+50h]
0x18001c8a8  mov     rax, [rcx]
0x18001c8ab  mov     rdx, [rsi]
0x18001c8ae  mov     rax, [rax+100h]
0x18001c8b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c8ba  mov     ebx, eax
0x18001c8bc  test    eax, eax
0x18001c8be  jns     short loc_18001C8DB
0x18001c8c0  mov     rcx, [rsi]
0x18001c8c3  test    rcx, rcx
0x18001c8c6  jz      short loc_18001C8DB
0x18001c8c8  mov     rax, [rcx]
0x18001c8cb  mov     rax, [rax+10h]
0x18001c8cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c8d4  mov     qword ptr [rsi], 0
0x18001c8db  mov     rax, [rdi]
0x18001c8de  mov     rcx, rdi
0x18001c8e1  mov     rax, [rax+0D8h]
0x18001c8e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c8ed  nop
0x18001c8ee  mov     eax, ebx
0x18001c8f0  mov     rbx, [rsp+28h+arg_0]
0x18001c8f5  mov     rsi, [rsp+28h+arg_8]
0x18001c8fa  add     rsp, 20h
0x18001c8fe  pop     rdi
0x18001c8ff  retn
```
