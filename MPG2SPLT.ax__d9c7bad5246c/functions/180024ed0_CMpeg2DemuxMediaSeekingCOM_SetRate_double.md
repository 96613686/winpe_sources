# CMpeg2DemuxMediaSeekingCOM::SetRate(double)

- ea: `0x180024ed0`
- end: `0x180024f52`
- name: `?SetRate@CMpeg2DemuxMediaSeekingCOM@@UEAAJN@Z`
- size: `130`
- prototype: `__int64 __fastcall(CMpeg2DemuxMediaSeekingCOM *__hidden this, double)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180024ed0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180024f38`
- `KERNEL32!LeaveCriticalSection` at `0x180024f38`
- `KERNEL32!EnterCriticalSection` at `0x180024f12`
- `KERNEL32!EnterCriticalSection` at `0x180024f12`

## pseudocode

```c
__int64 __fastcall CMpeg2DemuxMediaSeekingCOM::SetRate(CMpeg2DemuxMediaSeekingCOM *this, double a2)
{
  __int64 v3; // rax
  __int64 v5; // rdx

  v3 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 6) + 40LL) + 336LL);
  if ( !v3 || !*(_DWORD *)(v3 + 176) )
    return 2147549183LL;
  if ( a2 <= 0.0 )
    return 2147942487LL;
  EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 5));
  v5 = *((_QWORD *)this + 6);
  *(double *)(*(_QWORD *)(*(_QWORD *)(v5 + 40) + 280LL) + 480LL) = a2;
  *(double *)(v5 + 48) = a2;
  LeaveCriticalSection(*((LPCRITICAL_SECTION *)this + 5));
  return 0;
}

```

## disassembly

```asm
0x180024ed0  push    rbx
0x180024ed2  sub     rsp, 30h
0x180024ed6  mov     rax, [rcx+30h]
0x180024eda  mov     rbx, rcx
0x180024edd  movaps  [rsp+38h+var_18], xmm6
0x180024ee2  movaps  xmm6, xmm1
0x180024ee5  mov     rdx, [rax+28h]
0x180024ee9  mov     rax, [rdx+150h]
0x180024ef0  test    rax, rax
0x180024ef3  jz      short loc_180024F42
0x180024ef5  cmp     dword ptr [rax+0B0h], 0
0x180024efc  jz      short loc_180024F42
0x180024efe  xorps   xmm0, xmm0
0x180024f01  comisd  xmm0, xmm1
0x180024f05  jb      short loc_180024F0E
0x180024f07  mov     eax, 80070057h
0x180024f0c  jmp     short loc_180024F47
0x180024f0e  mov     rcx, [rcx+28h]; lpCriticalSection
0x180024f12  call    cs:__imp_EnterCriticalSection
0x180024f18  mov     rdx, [rbx+30h]
0x180024f1c  mov     rax, [rdx+28h]
0x180024f20  mov     rcx, [rax+118h]
0x180024f27  movsd   qword ptr [rcx+1E0h], xmm6
0x180024f2f  movsd   qword ptr [rdx+30h], xmm6
0x180024f34  mov     rcx, [rbx+28h]; lpCriticalSection
0x180024f38  call    cs:__imp_LeaveCriticalSection
0x180024f3e  xor     eax, eax
0x180024f40  jmp     short loc_180024F47
0x180024f42  mov     eax, 8000FFFFh
0x180024f47  movaps  xmm6, [rsp+38h+var_18]
0x180024f4c  add     rsp, 30h
0x180024f50  pop     rbx
0x180024f51  retn
```
