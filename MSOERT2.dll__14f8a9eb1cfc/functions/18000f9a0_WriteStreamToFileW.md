# WriteStreamToFileW

- ea: `0x18000f9a0`
- end: `0x18000fa41`
- name: `WriteStreamToFileW`
- size: `161`
- prototype: `__int64 __fastcall(IStream *pstm)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000f8e0`

## callees

- `0x18000ed40`
- `0x18000f6b0`
- `0x18000f9a0`
- `0x180014010`

## import_xrefs

- `SHLWAPI!__imp_IStream_Reset` at `0x18000f9f0`
- `SHLWAPI!__imp_IStream_Reset` at `0x18000fa13`
- `SHLWAPI!__imp_IStream_Reset` at `0x18000f9f0`
- `SHLWAPI!__imp_IStream_Reset` at `0x18000fa13`

## pseudocode

```c
__int64 __fastcall WriteStreamToFileW(IStream *pstm, const unsigned __int16 *a2, unsigned int a3, unsigned int a4)
{
  int v5; // eax
  struct IStream *v6; // rdi
  int v7; // ebx
  struct IStream *v9; // [rsp+30h] [rbp-18h] BYREF

  v9 = 0;
  v5 = OpenFileStreamWithFlagsW(a2, a3, a4, 0x80u, &v9);
  v6 = v9;
  v7 = v5;
  if ( v5 >= 0 )
  {
    v7 = IStream_Reset(pstm);
    if ( v7 >= 0 )
    {
      v7 = HrCopyStream((__int64)pstm, (__int64)v6, 0);
      if ( v7 >= 0 )
        v7 = IStream_Reset(pstm);
    }
  }
  if ( v6 )
    ((void (__fastcall *)(struct IStream *))v6->lpVtbl->Release)(v6);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000f9a0  mov     [rsp+arg_0], rbx
0x18000f9a5  mov     [rsp+arg_8], rsi
0x18000f9aa  push    rdi
0x18000f9ab  sub     rsp, 40h
0x18000f9af  mov     rsi, rcx
0x18000f9b2  mov     [rsp+48h+var_18], 0
0x18000f9bb  mov     eax, r9d
0x18000f9be  lea     rcx, [rsp+48h+var_18]
0x18000f9c3  mov     r10d, r8d
0x18000f9c6  mov     [rsp+48h+var_28], rcx
0x18000f9cb  mov     r11, rdx
0x18000f9ce  mov     r9d, 80h
0x18000f9d4  mov     rcx, r11
0x18000f9d7  mov     r8d, eax
0x18000f9da  mov     edx, r10d
0x18000f9dd  call    OpenFileStreamWithFlagsW
0x18000f9e2  mov     rdi, [rsp+48h+var_18]
0x18000f9e7  mov     ebx, eax
0x18000f9e9  test    eax, eax
0x18000f9eb  js      short loc_18000FA1B
0x18000f9ed  mov     rcx, rsi; pstm
0x18000f9f0  call    cs:__imp_IStream_Reset
0x18000f9f6  mov     ebx, eax
0x18000f9f8  test    eax, eax
0x18000f9fa  js      short loc_18000FA1B
0x18000f9fc  xor     r8d, r8d
0x18000f9ff  mov     rdx, rdi
0x18000fa02  mov     rcx, rsi
0x18000fa05  call    HrCopyStream
0x18000fa0a  mov     ebx, eax
0x18000fa0c  test    eax, eax
0x18000fa0e  js      short loc_18000FA1B
0x18000fa10  mov     rcx, rsi; pstm
0x18000fa13  call    cs:__imp_IStream_Reset
0x18000fa19  mov     ebx, eax
0x18000fa1b  test    rdi, rdi
0x18000fa1e  jz      short loc_18000FA2F
0x18000fa20  mov     rax, [rdi]
0x18000fa23  mov     rcx, rdi
0x18000fa26  mov     rax, [rax+10h]
0x18000fa2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa2f  mov     rsi, [rsp+48h+arg_8]
0x18000fa34  mov     eax, ebx
0x18000fa36  mov     rbx, [rsp+48h+arg_0]
0x18000fa3b  add     rsp, 40h
0x18000fa3f  pop     rdi
0x18000fa40  retn
```
