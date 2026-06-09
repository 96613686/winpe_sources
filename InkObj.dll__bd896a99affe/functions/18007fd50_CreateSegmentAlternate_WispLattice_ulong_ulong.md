# CreateSegmentAlternate(WispLattice *,ulong,ulong)

- ea: `0x18007fd50`
- end: `0x18007fdd5`
- name: `?CreateSegmentAlternate@@YAPEAUHRECOALT__@@PEAVWispLattice@@KK@Z`
- size: `133`
- prototype: `HRECOALT __fastcall(struct WispLattice *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800822a8`

## callees

- `0x18007fd50`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007fd66`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007fd89`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007fda6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007fd66`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007fd89`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007fda6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007fd9b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007fdb9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007fd9b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007fdb9`

## pseudocode

```c
_QWORD *__fastcall CreateSegmentAlternate(struct WispLattice *a1, int a2, int a3)
{
  _QWORD *v6; // rax
  _QWORD *v7; // rbx
  LPVOID v9; // rax
  LPVOID v10; // rax
  _DWORD *v11; // rcx

  v6 = CoTaskMemAlloc(0x28u);
  v7 = v6;
  if ( !v6 )
    return 0;
  *v6 = a1;
  *((_DWORD *)v6 + 2) = 1;
  v9 = CoTaskMemAlloc(4u);
  v7[2] = v9;
  if ( !v9 )
  {
LABEL_4:
    CoTaskMemFree(v7);
    return 0;
  }
  v10 = CoTaskMemAlloc(4u);
  v11 = (_DWORD *)v7[2];
  v7[3] = v10;
  if ( !v10 )
  {
    CoTaskMemFree(v11);
    goto LABEL_4;
  }
  *v11 = a2;
  *(_DWORD *)v7[3] = a3;
  return v7;
}

```

## disassembly

```asm
0x18007fd50  push    rbx
0x18007fd52  push    rbp
0x18007fd53  push    rsi
0x18007fd54  push    rdi
0x18007fd55  sub     rsp, 28h
0x18007fd59  mov     rbp, rcx
0x18007fd5c  mov     edi, r8d
0x18007fd5f  mov     ecx, 28h ; '('; cb
0x18007fd64  mov     esi, edx
0x18007fd66  call    cs:__imp_CoTaskMemAlloc
0x18007fd6c  mov     rbx, rax
0x18007fd6f  test    rax, rax
0x18007fd72  jnz     short loc_18007FD78
0x18007fd74  xor     eax, eax
0x18007fd76  jmp     short loc_18007FDCC
0x18007fd78  mov     [rax], rbp
0x18007fd7b  mov     ebp, 4
0x18007fd80  mov     ecx, ebp; cb
0x18007fd82  mov     dword ptr [rax+8], 1
0x18007fd89  call    cs:__imp_CoTaskMemAlloc
0x18007fd8f  mov     [rbx+10h], rax
0x18007fd93  test    rax, rax
0x18007fd96  jnz     short loc_18007FDA3
0x18007fd98  mov     rcx, rbx; pv
0x18007fd9b  call    cs:__imp_CoTaskMemFree
0x18007fda1  jmp     short loc_18007FD74
0x18007fda3  mov     rcx, rbp; cb
0x18007fda6  call    cs:__imp_CoTaskMemAlloc
0x18007fdac  mov     rcx, [rbx+10h]; pv
0x18007fdb0  mov     [rbx+18h], rax
0x18007fdb4  test    rax, rax
0x18007fdb7  jnz     short loc_18007FDC1
0x18007fdb9  call    cs:__imp_CoTaskMemFree
0x18007fdbf  jmp     short loc_18007FD98
0x18007fdc1  mov     [rcx], esi
0x18007fdc3  mov     rax, [rbx+18h]
0x18007fdc7  mov     [rax], edi
0x18007fdc9  mov     rax, rbx
0x18007fdcc  add     rsp, 28h
0x18007fdd0  pop     rdi
0x18007fdd1  pop     rsi
0x18007fdd2  pop     rbp
0x18007fdd3  pop     rbx
0x18007fdd4  retn
```
