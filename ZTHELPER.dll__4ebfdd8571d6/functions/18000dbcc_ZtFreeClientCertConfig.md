# ZtFreeClientCertConfig

- ea: `0x18000dbcc`
- end: `0x18000dc1a`
- name: `ZtFreeClientCertConfig`
- size: `78`
- prototype: `void __fastcall(LPVOID *lpMem)`
- caller_count: `8`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180003e00`
- `0x1800049b0`
- `0x180008e40`
- `0x1800092d0`
- `0x180009420`
- `0x180011f68`
- `0x1800121b0`
- `0x180012284`

## callees

- `0x18000c6bc`
- `0x18000dbcc`
- `0x1800125d4`

## pseudocode

```c
void __fastcall ZtFreeClientCertConfig(LPVOID *lpMem)
{
  void *v2; // rcx

  if ( lpMem )
  {
    Dns_Free(lpMem[2]);
    v2 = lpMem[4];
    lpMem[2] = 0;
    *((_DWORD *)lpMem + 6) = 0;
    DnsFreeZtClientCertEkuListW(v2);
    lpMem[4] = 0;
    *((_DWORD *)lpMem + 10) = 0;
    Dns_Free(lpMem);
  }
}

```

## disassembly

```asm
0x18000dbcc  test    rcx, rcx
0x18000dbcf  jz      short locret_18000DC19
0x18000dbd1  push    rbx
0x18000dbd2  sub     rsp, 20h
0x18000dbd6  mov     rbx, rcx
0x18000dbd9  mov     rcx, [rcx+10h]; lpMem
0x18000dbdd  call    Dns_Free
0x18000dbe2  mov     edx, [rbx+28h]
0x18000dbe5  mov     rcx, [rbx+20h]; lpMem
0x18000dbe9  mov     qword ptr [rbx+10h], 0
0x18000dbf1  mov     dword ptr [rbx+18h], 0
0x18000dbf8  call    DnsFreeZtClientCertEkuListW
0x18000dbfd  mov     rcx, rbx; lpMem
0x18000dc00  mov     qword ptr [rbx+20h], 0
0x18000dc08  mov     dword ptr [rbx+28h], 0
0x18000dc0f  call    Dns_Free
0x18000dc14  add     rsp, 20h
0x18000dc18  pop     rbx
0x18000dc19  retn
```
