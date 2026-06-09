# CMpeg2DemuxMediaSeekingCOM::GetAvailable(__int64 *,__int64 *)

- ea: `0x180024140`
- end: `0x1800241b8`
- name: `?GetAvailable@CMpeg2DemuxMediaSeekingCOM@@UEAAJPEA_J0@Z`
- size: `120`
- prototype: `__int64 __fastcall(CMpeg2DemuxMediaSeekingCOM *__hidden this, __int64 *, __int64 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180024140`
- `0x180034010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800241a0`
- `KERNEL32!LeaveCriticalSection` at `0x1800241a0`
- `KERNEL32!EnterCriticalSection` at `0x180024175`
- `KERNEL32!EnterCriticalSection` at `0x180024175`

## pseudocode

```c
__int64 __fastcall CMpeg2DemuxMediaSeekingCOM::GetAvailable(CMpeg2DemuxMediaSeekingCOM *this, __int64 *a2, __int64 *a3)
{
  __int64 v6; // rax
  unsigned int v7; // edi

  v6 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 6) + 40LL) + 336LL);
  if ( !v6 || !*(_DWORD *)(v6 + 176) )
    return 2147549183LL;
  v7 = 0;
  EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 5));
  if ( a2 )
    *a2 = 0;
  if ( a3 )
    v7 = (*(__int64 (__fastcall **)(CMpeg2DemuxMediaSeekingCOM *, __int64 *))(*(_QWORD *)this + 80LL))(this, a3);
  LeaveCriticalSection(*((LPCRITICAL_SECTION *)this + 5));
  return v7;
}

```

## disassembly

```asm
0x180024140  push    rbx
0x180024142  push    rbp
0x180024143  push    rsi
0x180024144  push    rdi
0x180024145  sub     rsp, 28h
0x180024149  mov     rax, [rcx+30h]
0x18002414d  mov     rbp, r8
0x180024150  mov     rsi, rdx
0x180024153  mov     rbx, rcx
0x180024156  mov     r9, [rax+28h]
0x18002415a  mov     rax, [r9+150h]
0x180024161  test    rax, rax
0x180024164  jz      short loc_1800241AA
0x180024166  cmp     dword ptr [rax+0B0h], 0
0x18002416d  jz      short loc_1800241AA
0x18002416f  mov     rcx, [rcx+28h]; lpCriticalSection
0x180024173  xor     edi, edi
0x180024175  call    cs:__imp_EnterCriticalSection
0x18002417b  test    rsi, rsi
0x18002417e  jz      short loc_180024183
0x180024180  mov     [rsi], rdi
0x180024183  test    rbp, rbp
0x180024186  jz      short loc_18002419C
0x180024188  mov     rax, [rbx]
0x18002418b  mov     rdx, rbp
0x18002418e  mov     rcx, rbx
0x180024191  mov     rax, [rax+50h]
0x180024195  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002419a  mov     edi, eax
0x18002419c  mov     rcx, [rbx+28h]; lpCriticalSection
0x1800241a0  call    cs:__imp_LeaveCriticalSection
0x1800241a6  mov     eax, edi
0x1800241a8  jmp     short loc_1800241AF
0x1800241aa  mov     eax, 8000FFFFh
0x1800241af  add     rsp, 28h
0x1800241b3  pop     rdi
0x1800241b4  pop     rsi
0x1800241b5  pop     rbp
0x1800241b6  pop     rbx
0x1800241b7  retn
```
