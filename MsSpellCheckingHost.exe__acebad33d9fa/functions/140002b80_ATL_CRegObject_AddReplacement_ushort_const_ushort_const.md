# ATL::CRegObject::AddReplacement(ushort const *,ushort const *)

- ea: `0x140002b80`
- end: `0x140002be6`
- name: `?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z`
- size: `102`
- prototype: `__int64 __fastcall(ATL::CRegObject *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1400028c0`
- `0x140002b80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140002bc4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140002bc4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140002ba0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140002ba0`

## pseudocode

```c
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
0x140002b80  push    rbx
0x140002b82  push    rbp
0x140002b83  push    rsi
0x140002b84  push    rdi
0x140002b85  sub     rsp, 28h
0x140002b89  mov     rbx, r8
0x140002b8c  mov     rsi, rdx
0x140002b8f  mov     rbp, rcx
0x140002b92  test    rdx, rdx
0x140002b95  jz      short loc_140002BD8
0x140002b97  test    rbx, rbx
0x140002b9a  jz      short loc_140002BD8
0x140002b9c  add     rcx, 20h ; ' '; lpCriticalSection
0x140002ba0  call    cs:__imp_EnterCriticalSection
0x140002ba6  mov     [rsp+48h+arg_8], 0
0x140002baf  lea     rcx, [rbp+8]; this
0x140002bb3  mov     r8, rbx; unsigned __int16 *
0x140002bb6  mov     rdx, rsi; unsigned __int16 *
0x140002bb9  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x140002bbe  mov     ebx, eax
0x140002bc0  lea     rcx, [rbp+20h]; lpCriticalSection
0x140002bc4  call    cs:__imp_LeaveCriticalSection
0x140002bca  nop
0x140002bcb  neg     ebx
0x140002bcd  sbb     eax, eax
0x140002bcf  not     eax
0x140002bd1  and     eax, 8007000Eh
0x140002bd6  jmp     short loc_140002BDD
0x140002bd8  mov     eax, 80070057h
0x140002bdd  add     rsp, 28h
0x140002be1  pop     rdi
0x140002be2  pop     rsi
0x140002be3  pop     rbp
0x140002be4  pop     rbx
0x140002be5  retn
```
