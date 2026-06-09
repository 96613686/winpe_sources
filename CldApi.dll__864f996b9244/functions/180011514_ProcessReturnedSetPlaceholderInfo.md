# ProcessReturnedSetPlaceholderInfo

- ea: `0x180011514`
- end: `0x1800115f0`
- name: `ProcessReturnedSetPlaceholderInfo`
- size: `220`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000aa48`
- `0x18000d7b0`

## callees

- `0x180011514`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180011559`
- `ntdll!RtlNtStatusToDosError` at `0x180011559`

## pseudocode

```c
__int64 __fastcall ProcessReturnedSetPlaceholderInfo(__int64 a1, unsigned int a2, __int64 a3, unsigned int a4, int *a5)
{
  int v5; // esi
  __int64 v6; // r14
  unsigned int v7; // ebx
  unsigned __int64 v11; // r13
  NTSTATUS v12; // ecx
  signed int v13; // ecx
  signed int v14; // eax
  __int64 v15; // rdx

  v5 = 0;
  v6 = 0;
  v7 = 0;
  if ( a4 )
  {
    v11 = a2;
    do
    {
      if ( v6 + 80 > v11 )
        break;
      v12 = *(_DWORD *)(v6 + a1 + 64);
      if ( v12 == -1 )
      {
        v13 = -1;
      }
      else
      {
        v14 = RtlNtStatusToDosError(v12);
        v13 = v14;
        if ( v14 > 0 )
          v13 = (unsigned __int16)v14 | 0x80070000;
      }
      v15 = 88LL * v7;
      *(_DWORD *)(v15 + a3 + 72) = v13;
      if ( *(int *)(v6 + a1 + 64) >= 0 )
      {
        *(_OWORD *)(v15 + a3 + 8) = *(_OWORD *)(v6 + a1 + 16);
        *(_OWORD *)(v15 + a3 + 24) = *(_OWORD *)(v6 + a1 + 32);
        *(_QWORD *)(v15 + a3 + 40) = *(_QWORD *)(v6 + a1 + 48);
        *(_QWORD *)(v15 + a3 + 80) = *(_QWORD *)(v6 + a1 + 72);
      }
      if ( v13 < 0 && v5 >= 0 )
        v5 = v13;
      v6 = (unsigned int)(*(_DWORD *)(v6 + a1) + v6);
      ++v7;
    }
    while ( v7 < a4 );
  }
  if ( a5 && *a5 >= 0 )
    *a5 = v5;
  return v7;
}

```

## disassembly

```asm
0x180011514  push    rbx
0x180011516  push    rbp
0x180011517  push    rsi
0x180011518  push    rdi
0x180011519  push    r12
0x18001151b  push    r13
0x18001151d  push    r14
0x18001151f  push    r15
0x180011521  sub     rsp, 28h
0x180011525  xor     esi, esi
0x180011527  xor     r14d, r14d
0x18001152a  xor     ebx, ebx
0x18001152c  mov     r12d, r9d
0x18001152f  mov     r15, r8
0x180011532  mov     rbp, rcx
0x180011535  test    r9d, r9d
0x180011538  jz      loc_1800115C9
0x18001153e  mov     r13d, edx
0x180011541  lea     rax, [r14+50h]
0x180011545  cmp     rax, r13
0x180011548  ja      short loc_1800115C9
0x18001154a  mov     ecx, [r14+rbp+40h]; Status
0x18001154f  cmp     ecx, 0FFFFFFFFh
0x180011552  jnz     short loc_180011559
0x180011554  or      ecx, 0FFFFFFFFh
0x180011557  jmp     short loc_18001156E
0x180011559  call    cs:__imp_RtlNtStatusToDosError
0x18001155f  mov     ecx, eax
0x180011561  test    eax, eax
0x180011563  jle     short loc_18001156E
0x180011565  movzx   ecx, ax
0x180011568  or      ecx, 80070000h
0x18001156e  mov     eax, ebx
0x180011570  imul    rdx, rax, 58h ; 'X'
0x180011574  mov     [rdx+r15+48h], ecx
0x180011579  cmp     dword ptr [r14+rbp+40h], 0
0x18001157f  jl      short loc_1800115B1
0x180011581  movups  xmm0, xmmword ptr [r14+rbp+10h]
0x180011587  movups  xmmword ptr [rdx+r15+8], xmm0
0x18001158d  movups  xmm1, xmmword ptr [r14+rbp+20h]
0x180011593  movups  xmmword ptr [rdx+r15+18h], xmm1
0x180011599  movsd   xmm0, qword ptr [r14+rbp+30h]
0x1800115a0  movsd   qword ptr [rdx+r15+28h], xmm0
0x1800115a7  mov     rax, [r14+rbp+48h]
0x1800115ac  mov     [rdx+r15+50h], rax
0x1800115b1  test    ecx, ecx
0x1800115b3  jns     short loc_1800115BA
0x1800115b5  test    esi, esi
0x1800115b7  cmovns  esi, ecx
0x1800115ba  add     r14d, [r14+rbp]
0x1800115be  inc     ebx
0x1800115c0  cmp     ebx, r12d
0x1800115c3  jb      loc_180011541
0x1800115c9  mov     rcx, [rsp+68h+arg_20]
0x1800115d1  test    rcx, rcx
0x1800115d4  jz      short loc_1800115DD
0x1800115d6  cmp     dword ptr [rcx], 0
0x1800115d9  jl      short loc_1800115DD
0x1800115db  mov     [rcx], esi
0x1800115dd  mov     eax, ebx
0x1800115df  add     rsp, 28h
0x1800115e3  pop     r15
0x1800115e5  pop     r14
0x1800115e7  pop     r13
0x1800115e9  pop     r12
0x1800115eb  pop     rdi
0x1800115ec  pop     rsi
0x1800115ed  pop     rbp
0x1800115ee  pop     rbx
0x1800115ef  retn
```
