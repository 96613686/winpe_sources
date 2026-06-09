# CMFTSimpleBase::GetInputCurrentType(ulong,IMFMediaType * *)

- ea: `0x1800029a0`
- end: `0x180002a70`
- name: `?GetInputCurrentType@CMFTSimpleBase@@UEAAJKPEAPEAUIMFMediaType@@@Z`
- size: `208`
- prototype: `int(CMFTSimpleBase *__hidden this, unsigned int, struct IMFMediaType **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800029a0`
- `0x18000b010`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x180002a08`
- `MFPlat!MFCreateMediaType` at `0x180002a08`

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
0x1800029a0  mov     [rsp+arg_0], rbx
0x1800029a5  mov     [rsp+arg_8], rsi
0x1800029aa  push    rdi
0x1800029ab  sub     rsp, 20h
0x1800029af  mov     rsi, r8
0x1800029b2  mov     ebx, edx
0x1800029b4  mov     rdi, rcx
0x1800029b7  mov     rax, [rcx]
0x1800029ba  mov     rax, [rax+0D0h]
0x1800029c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029c6  test    ebx, ebx
0x1800029c8  jz      short loc_1800029E4
0x1800029ca  mov     rax, [rdi]
0x1800029cd  mov     rcx, rdi
0x1800029d0  mov     rax, [rax+0D8h]
0x1800029d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029dc  nop
0x1800029dd  mov     eax, 0C00D36B3h
0x1800029e2  jmp     short loc_180002A60
0x1800029e4  cmp     qword ptr [rdi+28h], 0
0x1800029e9  jnz     short loc_180002A05
0x1800029eb  mov     rax, [rdi]
0x1800029ee  mov     rcx, rdi
0x1800029f1  mov     rax, [rax+0D8h]
0x1800029f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029fd  nop
0x1800029fe  mov     eax, 0C00D6D60h
0x180002a03  jmp     short loc_180002A60
0x180002a05  mov     rcx, rsi; ppMFType
0x180002a08  call    cs:__imp_MFCreateMediaType
0x180002a0e  mov     ebx, eax
0x180002a10  test    eax, eax
0x180002a12  js      short loc_180002A4B
0x180002a14  mov     rcx, [rdi+28h]
0x180002a18  mov     rax, [rcx]
0x180002a1b  mov     rdx, [rsi]
0x180002a1e  mov     rax, [rax+100h]
0x180002a25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a2a  mov     ebx, eax
0x180002a2c  test    eax, eax
0x180002a2e  jns     short loc_180002A4B
0x180002a30  mov     rcx, [rsi]
0x180002a33  test    rcx, rcx
0x180002a36  jz      short loc_180002A4B
0x180002a38  mov     rax, [rcx]
0x180002a3b  mov     rax, [rax+10h]
0x180002a3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a44  mov     qword ptr [rsi], 0
0x180002a4b  mov     rax, [rdi]
0x180002a4e  mov     rcx, rdi
0x180002a51  mov     rax, [rax+0D8h]
0x180002a58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a5d  nop
0x180002a5e  mov     eax, ebx
0x180002a60  mov     rbx, [rsp+28h+arg_0]
0x180002a65  mov     rsi, [rsp+28h+arg_8]
0x180002a6a  add     rsp, 20h
0x180002a6e  pop     rdi
0x180002a6f  retn
```
