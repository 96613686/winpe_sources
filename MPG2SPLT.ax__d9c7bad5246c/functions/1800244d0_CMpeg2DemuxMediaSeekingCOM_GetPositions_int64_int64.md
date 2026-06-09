# CMpeg2DemuxMediaSeekingCOM::GetPositions(__int64 *,__int64 *)

- ea: `0x1800244d0`
- end: `0x18002455d`
- name: `?GetPositions@CMpeg2DemuxMediaSeekingCOM@@UEAAJPEA_J0@Z`
- size: `141`
- prototype: `__int64 __fastcall(CMpeg2DemuxMediaSeekingCOM *__hidden this, __int64 *, __int64 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800244d0`
- `0x180034010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180024545`
- `KERNEL32!LeaveCriticalSection` at `0x180024545`
- `KERNEL32!EnterCriticalSection` at `0x180024505`
- `KERNEL32!EnterCriticalSection` at `0x180024505`

## pseudocode

```c
__int64 __fastcall CMpeg2DemuxMediaSeekingCOM::GetPositions(CMpeg2DemuxMediaSeekingCOM *this, __int64 *a2, __int64 *a3)
{
  __int64 v6; // rax
  int v7; // edi

  v6 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 6) + 40LL) + 336LL);
  if ( !v6 || !*(_DWORD *)(v6 + 176) )
    return 2147549183LL;
  v7 = 0;
  EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 5));
  if ( a2 )
    v7 = (*(__int64 (__fastcall **)(CMpeg2DemuxMediaSeekingCOM *, __int64 *))(*(_QWORD *)this + 96LL))(this, a2);
  if ( a3 )
  {
    if ( v7 >= 0 )
      v7 = (*(__int64 (__fastcall **)(CMpeg2DemuxMediaSeekingCOM *, __int64 *))(*(_QWORD *)this + 88LL))(this, a3);
  }
  LeaveCriticalSection(*((LPCRITICAL_SECTION *)this + 5));
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800244d0  push    rbx
0x1800244d2  push    rbp
0x1800244d3  push    rsi
0x1800244d4  push    rdi
0x1800244d5  sub     rsp, 28h
0x1800244d9  mov     rax, [rcx+30h]
0x1800244dd  mov     rsi, r8
0x1800244e0  mov     rbp, rdx
0x1800244e3  mov     rbx, rcx
0x1800244e6  mov     r9, [rax+28h]
0x1800244ea  mov     rax, [r9+150h]
0x1800244f1  test    rax, rax
0x1800244f4  jz      short loc_18002454F
0x1800244f6  cmp     dword ptr [rax+0B0h], 0
0x1800244fd  jz      short loc_18002454F
0x1800244ff  mov     rcx, [rcx+28h]; lpCriticalSection
0x180024503  xor     edi, edi
0x180024505  call    cs:__imp_EnterCriticalSection
0x18002450b  test    rbp, rbp
0x18002450e  jz      short loc_180024524
0x180024510  mov     rax, [rbx]
0x180024513  mov     rdx, rbp
0x180024516  mov     rcx, rbx
0x180024519  mov     rax, [rax+60h]
0x18002451d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024522  mov     edi, eax
0x180024524  test    rsi, rsi
0x180024527  jz      short loc_180024541
0x180024529  test    edi, edi
0x18002452b  js      short loc_180024541
0x18002452d  mov     rax, [rbx]
0x180024530  mov     rdx, rsi
0x180024533  mov     rcx, rbx
0x180024536  mov     rax, [rax+58h]
0x18002453a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002453f  mov     edi, eax
0x180024541  mov     rcx, [rbx+28h]; lpCriticalSection
0x180024545  call    cs:__imp_LeaveCriticalSection
0x18002454b  mov     eax, edi
0x18002454d  jmp     short loc_180024554
0x18002454f  mov     eax, 8000FFFFh
0x180024554  add     rsp, 28h
0x180024558  pop     rdi
0x180024559  pop     rsi
0x18002455a  pop     rbp
0x18002455b  pop     rbx
0x18002455c  retn
```
