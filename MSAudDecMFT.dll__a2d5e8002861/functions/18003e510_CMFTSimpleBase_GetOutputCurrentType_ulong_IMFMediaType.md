# CMFTSimpleBase::GetOutputCurrentType(ulong,IMFMediaType * *)

- ea: `0x18003e510`
- end: `0x18003e5ef`
- name: `?GetOutputCurrentType@CMFTSimpleBase@@UEAAJKPEAPEAUIMFMediaType@@@Z`
- size: `223`
- prototype: `int(CMFTSimpleBase *__hidden this, unsigned int, struct IMFMediaType **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18003e510`
- `0x1800960c0`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x18003e545`
- `MFPlat!MFCreateMediaType` at `0x18003e545`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMFTSimpleBase::GetOutputCurrentType(CMFTSimpleBase *this, int a2, struct IMFMediaType **a3)
{
  HRESULT v6; // ebx

  (*(void (__fastcall **)(CMFTSimpleBase *))(*(_QWORD *)this + 208LL))(this);
  if ( a2 )
  {
    (*(void (__fastcall **)(CMFTSimpleBase *))(*(_QWORD *)this + 216LL))(this);
    return 3222091443LL;
  }
  else if ( *((_QWORD *)this + 10) )
  {
    v6 = MFCreateMediaType(a3);
    if ( v6 >= 0 )
    {
      v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 10) + 256LL))(*((_QWORD *)this + 10), *a3);
      if ( v6 < 0 )
      {
        if ( *a3 )
        {
          ((void (__fastcall *)(_QWORD))(*a3)->lpVtbl->Release)(*a3);
          *a3 = 0;
        }
      }
    }
    (*(void (__fastcall **)(CMFTSimpleBase *))(*(_QWORD *)this + 216LL))(this);
    return (unsigned int)v6;
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
0x18003e510  mov     [rsp+arg_0], rbx
0x18003e515  mov     [rsp+arg_8], rsi
0x18003e51a  push    rdi
0x18003e51b  sub     rsp, 20h
0x18003e51f  mov     rsi, r8
0x18003e522  mov     ebx, edx
0x18003e524  mov     rdi, rcx
0x18003e527  mov     rax, [rcx]
0x18003e52a  mov     rax, [rax+0D0h]
0x18003e531  call    cs:__guard_dispatch_icall_fptr
0x18003e537  test    ebx, ebx
0x18003e539  jnz     short loc_18003E5B6
0x18003e53b  cmp     qword ptr [rdi+50h], 0
0x18003e540  jz      short loc_18003E59B
0x18003e542  mov     rcx, rsi; ppMFType
0x18003e545  call    cs:__imp_MFCreateMediaType
0x18003e54c  nop     dword ptr [rax+rax+00h]
0x18003e551  mov     ebx, eax
0x18003e553  test    eax, eax
0x18003e555  js      short loc_18003E574
0x18003e557  mov     rcx, [rdi+50h]
0x18003e55b  mov     rax, [rcx]
0x18003e55e  mov     rdx, [rsi]
0x18003e561  mov     rax, [rax+100h]
0x18003e568  call    cs:__guard_dispatch_icall_fptr
0x18003e56e  mov     ebx, eax
0x18003e570  test    eax, eax
0x18003e572  js      short loc_18003E5D1
0x18003e574  mov     rax, [rdi]
0x18003e577  mov     rcx, rdi
0x18003e57a  mov     rax, [rax+0D8h]
0x18003e581  call    cs:__guard_dispatch_icall_fptr
0x18003e587  nop
0x18003e588  mov     eax, ebx
0x18003e58a  mov     rbx, [rsp+28h+arg_0]
0x18003e58f  mov     rsi, [rsp+28h+arg_8]
0x18003e594  add     rsp, 20h
0x18003e598  pop     rdi
0x18003e599  retn
0x18003e59b  mov     rax, [rdi]
0x18003e59e  mov     rcx, rdi
0x18003e5a1  mov     rax, [rax+0D8h]
0x18003e5a8  call    cs:__guard_dispatch_icall_fptr
0x18003e5ae  nop
0x18003e5af  mov     eax, 0C00D6D60h
0x18003e5b4  jmp     short loc_18003E58A
0x18003e5b6  mov     rax, [rdi]
0x18003e5b9  mov     rcx, rdi
0x18003e5bc  mov     rax, [rax+0D8h]
0x18003e5c3  call    cs:__guard_dispatch_icall_fptr
0x18003e5c9  nop
0x18003e5ca  mov     eax, 0C00D36B3h
0x18003e5cf  jmp     short loc_18003E58A
0x18003e5d1  mov     rcx, [rsi]
0x18003e5d4  test    rcx, rcx
0x18003e5d7  jz      short loc_18003E574
0x18003e5d9  mov     rax, [rcx]
0x18003e5dc  mov     rax, [rax+10h]
0x18003e5e0  call    cs:__guard_dispatch_icall_fptr
0x18003e5e6  mov     qword ptr [rsi], 0
0x18003e5ed  jmp     short loc_18003E574
```
