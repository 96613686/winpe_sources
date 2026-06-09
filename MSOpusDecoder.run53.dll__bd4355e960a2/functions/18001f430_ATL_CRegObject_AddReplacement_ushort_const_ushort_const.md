# ATL::CRegObject::AddReplacement(ushort const *,ushort const *)

- ea: `0x18001f430`
- end: `0x18001f496`
- name: `?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z`
- size: `102`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18001f0bc`
- `0x18001f430`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f450`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f450`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f474`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f474`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CRegObject::AddReplacement(
        ATL::CRegObject *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  int v6; // ebx

  if ( !a2 || !a3 )
    return 2147942487LL;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  v6 = ATL::CExpansionVector::Add((ATL::CRegObject *)((char *)this + 8), a2, a3);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  return v6 == 0 ? 0x8007000E : 0;
}

```

## disassembly

```asm
0x18001f430  push    rbx
0x18001f432  push    rbp
0x18001f433  push    rsi
0x18001f434  push    rdi
0x18001f435  sub     rsp, 28h
0x18001f439  mov     rbx, r8
0x18001f43c  mov     rsi, rdx
0x18001f43f  mov     rbp, rcx
0x18001f442  test    rdx, rdx
0x18001f445  jz      short loc_18001F488
0x18001f447  test    rbx, rbx
0x18001f44a  jz      short loc_18001F488
0x18001f44c  add     rcx, 20h ; ' '; lpCriticalSection
0x18001f450  call    cs:__imp_EnterCriticalSection
0x18001f456  mov     [rsp+48h+arg_8], 0
0x18001f45f  lea     rcx, [rbp+8]; this
0x18001f463  mov     r8, rbx; unsigned __int16 *
0x18001f466  mov     rdx, rsi; unsigned __int16 *
0x18001f469  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18001f46e  mov     ebx, eax
0x18001f470  lea     rcx, [rbp+20h]; lpCriticalSection
0x18001f474  call    cs:__imp_LeaveCriticalSection
0x18001f47a  nop
0x18001f47b  neg     ebx
0x18001f47d  sbb     eax, eax
0x18001f47f  not     eax
0x18001f481  and     eax, 8007000Eh
0x18001f486  jmp     short loc_18001F48D
0x18001f488  mov     eax, 80070057h
0x18001f48d  add     rsp, 28h
0x18001f491  pop     rdi
0x18001f492  pop     rsi
0x18001f493  pop     rbp
0x18001f494  pop     rbx
0x18001f495  retn
```
