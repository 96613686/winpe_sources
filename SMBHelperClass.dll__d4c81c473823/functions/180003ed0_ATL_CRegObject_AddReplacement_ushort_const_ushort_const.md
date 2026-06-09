# ATL::CRegObject::AddReplacement(ushort const *,ushort const *)

- ea: `0x180003ed0`
- end: `0x180003f36`
- name: `?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z`
- size: `102`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180003ba8`
- `0x180003ed0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180003f14`
- `KERNEL32!LeaveCriticalSection` at `0x180003f14`
- `KERNEL32!EnterCriticalSection` at `0x180003ef0`
- `KERNEL32!EnterCriticalSection` at `0x180003ef0`

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
0x180003ed0  push    rbx
0x180003ed2  push    rbp
0x180003ed3  push    rsi
0x180003ed4  push    rdi
0x180003ed5  sub     rsp, 28h
0x180003ed9  mov     rbx, r8
0x180003edc  mov     rsi, rdx
0x180003edf  mov     rbp, rcx
0x180003ee2  test    rdx, rdx
0x180003ee5  jz      short loc_180003F28
0x180003ee7  test    rbx, rbx
0x180003eea  jz      short loc_180003F28
0x180003eec  add     rcx, 20h ; ' '; lpCriticalSection
0x180003ef0  call    cs:__imp_EnterCriticalSection
0x180003ef6  mov     [rsp+48h+arg_8], 0
0x180003eff  lea     rcx, [rbp+8]; this
0x180003f03  mov     r8, rbx; unsigned __int16 *
0x180003f06  mov     rdx, rsi; unsigned __int16 *
0x180003f09  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180003f0e  mov     ebx, eax
0x180003f10  lea     rcx, [rbp+20h]; lpCriticalSection
0x180003f14  call    cs:__imp_LeaveCriticalSection
0x180003f1a  nop
0x180003f1b  neg     ebx
0x180003f1d  sbb     eax, eax
0x180003f1f  not     eax
0x180003f21  and     eax, 8007000Eh
0x180003f26  jmp     short loc_180003F2D
0x180003f28  mov     eax, 80070057h
0x180003f2d  add     rsp, 28h
0x180003f31  pop     rdi
0x180003f32  pop     rsi
0x180003f33  pop     rbp
0x180003f34  pop     rbx
0x180003f35  retn
```
