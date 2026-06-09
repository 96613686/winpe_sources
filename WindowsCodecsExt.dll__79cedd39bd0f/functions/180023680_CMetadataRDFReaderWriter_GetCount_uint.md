# CMetadataRDFReaderWriter::GetCount(uint *)

- ea: `0x180023680`
- end: `0x1800236e4`
- name: `?GetCount@CMetadataRDFReaderWriter@@UEAAJPEAI@Z`
- size: `100`
- prototype: `__int64 __fastcall(CMetadataRDFReaderWriter *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180022a60`

## callees

- `0x1800058c0`
- `0x18000f1d0`
- `0x1800171c4`
- `0x180023680`

## pseudocode

```c
__int64 __fastcall CMetadataRDFReaderWriter::GetCount(CMetadataRDFReaderWriter *this, unsigned int *a2)
{
  unsigned int v4; // ebx
  char *v6; // [rsp+30h] [rbp+8h] BYREF

  v6 = (char *)this + 40;
  CMTALock::Enter((CMetadataRDFReaderWriter *)((char *)this + 40));
  if ( a2 )
  {
    v4 = 0;
    *a2 = *((_DWORD *)this + 43);
  }
  else
  {
    v4 = -2147024809;
    if ( g_doStackCaptures )
      DoStackCapture(-2147024809);
  }
  CGuard<CMTALock>::~CGuard<CMTALock>(&v6);
  return v4;
}

```

## disassembly

```asm
0x180023680  mov     [rsp+arg_8], rbx
0x180023685  mov     [rsp+arg_10], rsi
0x18002368a  push    rdi
0x18002368b  sub     rsp, 20h
0x18002368f  mov     rsi, rcx
0x180023692  mov     rdi, rdx
0x180023695  add     rcx, 28h ; '('; this
0x180023699  mov     [rsp+28h+arg_0], rcx
0x18002369e  call    ?Enter@CMTALock@@QEAAXXZ; CMTALock::Enter(void)
0x1800236a3  test    rdi, rdi
0x1800236a6  jnz     short loc_1800236BE
0x1800236a8  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x1800236ae  mov     ebx, 80070057h
0x1800236b3  jz      short loc_1800236C8
0x1800236b5  mov     ecx, ebx; int
0x1800236b7  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800236bc  jmp     short loc_1800236C8
0x1800236be  mov     ecx, [rsi+0ACh]
0x1800236c4  xor     ebx, ebx
0x1800236c6  mov     [rdi], ecx
0x1800236c8  lea     rcx, [rsp+28h+arg_0]
0x1800236cd  call    ??1?$CGuard@VCMTALock@@@@QEAA@XZ; CGuard<CMTALock>::~CGuard<CMTALock>(void)
0x1800236d2  mov     rsi, [rsp+28h+arg_10]
0x1800236d7  mov     eax, ebx
0x1800236d9  mov     rbx, [rsp+28h+arg_8]
0x1800236de  add     rsp, 20h
0x1800236e2  pop     rdi
0x1800236e3  retn
```
