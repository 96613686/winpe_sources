# ATL::CRegObject::AddReplacement(ushort const *,ushort const *)

- ea: `0x180003630`
- end: `0x180003696`
- name: `?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z`
- size: `102`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800032f8`
- `0x180003630`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003674`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003674`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003650`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003650`

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
0x180003630  push    rbx
0x180003632  push    rbp
0x180003633  push    rsi
0x180003634  push    rdi
0x180003635  sub     rsp, 28h
0x180003639  mov     rbx, r8
0x18000363c  mov     rsi, rdx
0x18000363f  mov     rbp, rcx
0x180003642  test    rdx, rdx
0x180003645  jz      short loc_180003688
0x180003647  test    rbx, rbx
0x18000364a  jz      short loc_180003688
0x18000364c  add     rcx, 20h ; ' '; lpCriticalSection
0x180003650  call    cs:__imp_EnterCriticalSection
0x180003656  mov     [rsp+48h+arg_8], 0
0x18000365f  lea     rcx, [rbp+8]; this
0x180003663  mov     r8, rbx; unsigned __int16 *
0x180003666  mov     rdx, rsi; unsigned __int16 *
0x180003669  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18000366e  mov     ebx, eax
0x180003670  lea     rcx, [rbp+20h]; lpCriticalSection
0x180003674  call    cs:__imp_LeaveCriticalSection
0x18000367a  nop
0x18000367b  neg     ebx
0x18000367d  sbb     eax, eax
0x18000367f  not     eax
0x180003681  and     eax, 8007000Eh
0x180003686  jmp     short loc_18000368D
0x180003688  mov     eax, 80070057h
0x18000368d  add     rsp, 28h
0x180003691  pop     rdi
0x180003692  pop     rsi
0x180003693  pop     rbp
0x180003694  pop     rbx
0x180003695  retn
```
