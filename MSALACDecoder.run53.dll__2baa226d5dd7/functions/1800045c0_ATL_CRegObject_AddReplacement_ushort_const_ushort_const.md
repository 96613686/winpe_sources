# ATL::CRegObject::AddReplacement(ushort const *,ushort const *)

- ea: `0x1800045c0`
- end: `0x180004626`
- name: `?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z`
- size: `102`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000428c`
- `0x1800045c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004604`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004604`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800045e0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800045e0`

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
0x1800045c0  push    rbx
0x1800045c2  push    rbp
0x1800045c3  push    rsi
0x1800045c4  push    rdi
0x1800045c5  sub     rsp, 28h
0x1800045c9  mov     rbx, r8
0x1800045cc  mov     rsi, rdx
0x1800045cf  mov     rbp, rcx
0x1800045d2  test    rdx, rdx
0x1800045d5  jz      short loc_180004618
0x1800045d7  test    rbx, rbx
0x1800045da  jz      short loc_180004618
0x1800045dc  add     rcx, 20h ; ' '; lpCriticalSection
0x1800045e0  call    cs:__imp_EnterCriticalSection
0x1800045e6  mov     [rsp+48h+arg_8], 0
0x1800045ef  lea     rcx, [rbp+8]; this
0x1800045f3  mov     r8, rbx; unsigned __int16 *
0x1800045f6  mov     rdx, rsi; unsigned __int16 *
0x1800045f9  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x1800045fe  mov     ebx, eax
0x180004600  lea     rcx, [rbp+20h]; lpCriticalSection
0x180004604  call    cs:__imp_LeaveCriticalSection
0x18000460a  nop
0x18000460b  neg     ebx
0x18000460d  sbb     eax, eax
0x18000460f  not     eax
0x180004611  and     eax, 8007000Eh
0x180004616  jmp     short loc_18000461D
0x180004618  mov     eax, 80070057h
0x18000461d  add     rsp, 28h
0x180004621  pop     rdi
0x180004622  pop     rsi
0x180004623  pop     rbp
0x180004624  pop     rbx
0x180004625  retn
```
