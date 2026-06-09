# CMpeg2DemuxMediaSeekingCOM::CheckCapabilities(ulong *)

- ea: `0x1800240b0`
- end: `0x180024136`
- name: `?CheckCapabilities@CMpeg2DemuxMediaSeekingCOM@@UEAAJPEAK@Z`
- size: `134`
- prototype: `__int64 __fastcall(CMpeg2DemuxMediaSeekingCOM *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800240b0`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall CMpeg2DemuxMediaSeekingCOM::CheckCapabilities(CMpeg2DemuxMediaSeekingCOM *this, unsigned int *a2)
{
  __int64 v4; // rax
  int v5; // ecx
  unsigned int v6; // eax
  int v7; // [rsp+38h] [rbp+10h] BYREF

  v7 = 0;
  if ( !a2 )
    return 2147500035LL;
  v4 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 6) + 40LL) + 336LL);
  if ( !v4 || !*(_DWORD *)(v4 + 176) )
    return 2147549183LL;
  v5 = (*(__int64 (__fastcall **)(CMpeg2DemuxMediaSeekingCOM *, int *))(*(_QWORD *)this + 24LL))(this, &v7);
  if ( v5 < 0 )
  {
    *a2 = 0;
  }
  else
  {
    v6 = *a2 & v7;
    if ( v6 )
      v5 = v6 != *a2;
    else
      v5 = -2147467259;
    *a2 = v6;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800240b0  push    rbx
0x1800240b2  sub     rsp, 20h
0x1800240b6  mov     [rsp+28h+arg_8], 0
0x1800240be  mov     rbx, rdx
0x1800240c1  mov     r8, rcx
0x1800240c4  test    rdx, rdx
0x1800240c7  jnz     short loc_1800240D0
0x1800240c9  mov     eax, 80004003h
0x1800240ce  jmp     short loc_180024130
0x1800240d0  mov     rax, [rcx+30h]
0x1800240d4  mov     rcx, [rax+28h]
0x1800240d8  mov     rax, [rcx+150h]
0x1800240df  test    rax, rax
0x1800240e2  jz      short loc_18002412B
0x1800240e4  cmp     dword ptr [rax+0B0h], 0
0x1800240eb  jz      short loc_18002412B
0x1800240ed  mov     rax, [r8]
0x1800240f0  lea     rdx, [rsp+28h+arg_8]
0x1800240f5  mov     rcx, r8
0x1800240f8  mov     rax, [rax+18h]
0x1800240fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024101  mov     ecx, eax
0x180024103  test    eax, eax
0x180024105  js      short loc_180024121
0x180024107  mov     eax, [rsp+28h+arg_8]
0x18002410b  and     eax, [rbx]
0x18002410d  jz      short loc_180024118
0x18002410f  xor     ecx, ecx
0x180024111  cmp     eax, [rbx]
0x180024113  setnz   cl
0x180024116  jmp     short loc_18002411D
0x180024118  mov     ecx, 80004005h
0x18002411d  mov     [rbx], eax
0x18002411f  jmp     short loc_180024127
0x180024121  mov     dword ptr [rbx], 0
0x180024127  mov     eax, ecx
0x180024129  jmp     short loc_180024130
0x18002412b  mov     eax, 8000FFFFh
0x180024130  add     rsp, 20h
0x180024134  pop     rbx
0x180024135  retn
```
