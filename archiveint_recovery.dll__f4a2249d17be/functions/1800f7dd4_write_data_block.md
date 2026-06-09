# write_data_block

- ea: `0x1800f7dd4`
- end: `0x1800f7fc6`
- name: `write_data_block`
- size: `498`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800f4af0`
- `0x1800f4b60`

## callees

- `0x180006c00`
- `0x1800149c0`
- `0x1800f7dd4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f7f6b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f7f80`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f7f6b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f7f80`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800f7f28`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800f7f28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f7f60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f7f60`

## string_xrefs

- `0x1800f7fa1`: `Attempt to write to an empty file`
- `0x1800f7f86`: `Write failed`

## pseudocode

```c
__int64 __fastcall write_data_block(__int64 a1, _BYTE *a2, __int64 a3)
{
  __int64 v3; // rdi
  __int64 v7; // rcx
  __int64 v8; // rbp
  int v9; // r14d
  __int64 v10; // r15
  __int64 v11; // rdx
  DWORD v12; // r8d
  _BYTE *i; // rcx
  __int64 v14; // rax
  __int64 v15; // rsi
  __int64 v16; // r9
  bool v17; // zf
  void *v18; // rcx
  __int64 v19; // rax
  DWORD LastError; // eax
  unsigned int *v21; // rax
  struct _OVERLAPPED Overlapped; // [rsp+30h] [rbp-58h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+A0h] [rbp+18h] BYREF

  NumberOfBytesWritten = 0;
  v3 = a3;
  memset(&Overlapped, 0, sizeof(Overlapped));
  if ( !a3 )
    return 0;
  v7 = *(_QWORD *)(a1 + 464);
  if ( !v7 || *(_QWORD *)(a1 + 432) == -1 )
  {
    archive_set_error(a1, 0, "Attempt to write to an empty file");
  }
  else
  {
    v8 = a3;
    v9 = *(_DWORD *)(a1 + 424) & 0x1000;
    if ( v7 >= 0 )
    {
      v11 = *(_QWORD *)(a1 + 440);
      if ( v11 + a3 > v7 )
      {
        v3 = v7 - v11;
        v8 = v7 - v11;
      }
    }
    while ( 1 )
    {
      if ( !v3 )
        return v8 - v3;
      if ( v9 )
      {
        for ( i = a2; i < &a2[v3]; ++i )
        {
          if ( *i )
            break;
        }
        v14 = i - a2;
        v15 = a2 - i;
        *(_QWORD *)(a1 + 440) += v14;
        v16 = *(_QWORD *)(a1 + 440);
        v17 = v15 + v3 == 0;
        v3 += v15;
        v12 = v3;
        if ( v17 )
          return v8 - v3;
        a2 = i;
        v10 = v9 != 0 ? 0x4000 : 0;
        if ( v3 + v16 > v10 + v16 - v16 % v10 )
          v12 = v10 - v16 % v10;
      }
      else
      {
        v12 = v3;
      }
      v18 = *(void **)(a1 + 432);
      Overlapped.Offset = *(_DWORD *)(a1 + 440);
      Overlapped.OffsetHigh = HIDWORD(*(_QWORD *)(a1 + 440));
      Overlapped.Internal = 0;
      Overlapped.InternalHigh = 0;
      Overlapped.hEvent = 0;
      if ( !WriteFile(v18, a2, v12, &NumberOfBytesWritten, &Overlapped) )
        break;
      v19 = NumberOfBytesWritten;
      *(_QWORD *)(a1 + 456) += NumberOfBytesWritten;
      a2 += v19;
      v3 -= v19;
      *(_QWORD *)(a1 + 440) += v19;
      *(_QWORD *)(a1 + 448) = *(_QWORD *)(a1 + 440);
    }
    LastError = GetLastError();
    if ( LastError == 5 )
      *(_DWORD *)_o__errno() = 9;
    else
      _la_dosmaperr(LastError);
    v21 = (unsigned int *)_o__errno();
    archive_set_error(a1, *v21, "Write failed");
  }
  return -20;
}

```

## disassembly

```asm
0x1800f7dd4  mov     rax, rsp
0x1800f7dd7  push    rbx
0x1800f7dd8  push    rbp
0x1800f7dd9  push    rsi
0x1800f7dda  push    rdi
0x1800f7ddb  push    r14
0x1800f7ddd  push    r15
0x1800f7ddf  sub     rsp, 58h
0x1800f7de3  mov     dword ptr [rax+18h], 0
0x1800f7dea  xorps   xmm0, xmm0
0x1800f7ded  mov     rdi, r8
0x1800f7df0  mov     rsi, rdx
0x1800f7df3  mov     rbx, rcx
0x1800f7df6  movups  xmmword ptr [rax-58h], xmm0
0x1800f7dfa  movups  xmmword ptr [rax-48h], xmm0
0x1800f7dfe  test    r8, r8
0x1800f7e01  jnz     short loc_1800F7E0A
0x1800f7e03  xor     eax, eax
0x1800f7e05  jmp     loc_1800F7FB9
0x1800f7e0a  mov     rcx, [rcx+1D0h]
0x1800f7e11  test    rcx, rcx
0x1800f7e14  jz      loc_1800F7FA1
0x1800f7e1a  cmp     qword ptr [rbx+1B0h], 0FFFFFFFFFFFFFFFFh
0x1800f7e22  jz      loc_1800F7FA1
0x1800f7e28  mov     r14d, [rbx+1A8h]
0x1800f7e2f  mov     rbp, r8
0x1800f7e32  and     r14d, 1000h
0x1800f7e39  mov     eax, r14d
0x1800f7e3c  neg     eax
0x1800f7e3e  sbb     r15, r15
0x1800f7e41  and     r15d, 4000h
0x1800f7e48  test    rcx, rcx
0x1800f7e4b  js      short loc_1800F7E66
0x1800f7e4d  mov     rdx, [rbx+1B8h]
0x1800f7e54  lea     rax, [rdx+r8]
0x1800f7e58  cmp     rax, rcx
0x1800f7e5b  jle     short loc_1800F7E66
0x1800f7e5d  mov     rdi, rcx
0x1800f7e60  sub     rdi, rdx
0x1800f7e63  mov     rbp, rdi
0x1800f7e66  test    rdi, rdi
0x1800f7e69  jz      loc_1800F7F99
0x1800f7e6f  test    r14d, r14d
0x1800f7e72  jnz     short loc_1800F7E79
0x1800f7e74  mov     r8, rdi
0x1800f7e77  jmp     short loc_1800F7ED8
0x1800f7e79  lea     rax, [rsi+rdi]
0x1800f7e7d  mov     rcx, rsi
0x1800f7e80  cmp     rsi, rax
0x1800f7e83  jnb     short loc_1800F7E92
0x1800f7e85  cmp     byte ptr [rcx], 0
0x1800f7e88  jnz     short loc_1800F7E92
0x1800f7e8a  inc     rcx
0x1800f7e8d  cmp     rcx, rax
0x1800f7e90  jb      short loc_1800F7E85
0x1800f7e92  mov     rax, rcx
0x1800f7e95  sub     rax, rsi
0x1800f7e98  sub     rsi, rcx
0x1800f7e9b  add     [rbx+1B8h], rax
0x1800f7ea2  mov     r9, [rbx+1B8h]
0x1800f7ea9  add     rdi, rsi
0x1800f7eac  mov     r8, rdi
0x1800f7eaf  jz      loc_1800F7F99
0x1800f7eb5  mov     rax, r9
0x1800f7eb8  mov     rsi, rcx
0x1800f7ebb  cqo
0x1800f7ebd  mov     rcx, r9
0x1800f7ec0  idiv    r15
0x1800f7ec3  lea     rax, [rdi+r9]
0x1800f7ec7  sub     rcx, rdx
0x1800f7eca  add     rcx, r15
0x1800f7ecd  cmp     rax, rcx
0x1800f7ed0  jle     short loc_1800F7ED8
0x1800f7ed2  sub     ecx, r9d
0x1800f7ed5  mov     r8d, ecx; nNumberOfBytesToWrite
0x1800f7ed8  mov     eax, [rbx+1B8h]
0x1800f7ede  lea     r9, [rsp+88h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800f7ee6  mov     rcx, [rbx+1B0h]; hFile
0x1800f7eed  mov     rdx, rsi; lpBuffer
0x1800f7ef0  mov     dword ptr [rsp+88h+Overlapped.10h], eax
0x1800f7ef4  mov     rax, [rbx+1B8h]
0x1800f7efb  sar     rax, 20h
0x1800f7eff  mov     dword ptr [rsp+88h+Overlapped.10h+4], eax
0x1800f7f03  lea     rax, [rsp+88h+Overlapped]
0x1800f7f08  mov     [rsp+88h+lpOverlapped], rax; lpOverlapped
0x1800f7f0d  mov     [rsp+88h+Overlapped.Internal], 0
0x1800f7f16  mov     [rsp+88h+Overlapped.InternalHigh], 0
0x1800f7f1f  mov     [rsp+88h+Overlapped.hEvent], 0
0x1800f7f28  call    cs:__imp_WriteFile
0x1800f7f2e  test    eax, eax
0x1800f7f30  jz      short loc_1800F7F60
0x1800f7f32  mov     eax, [rsp+88h+NumberOfBytesWritten]
0x1800f7f39  add     [rbx+1C8h], rax
0x1800f7f40  add     rsi, rax
0x1800f7f43  sub     rdi, rax
0x1800f7f46  add     [rbx+1B8h], rax
0x1800f7f4d  mov     rax, [rbx+1B8h]
0x1800f7f54  mov     [rbx+1C0h], rax
0x1800f7f5b  jmp     loc_1800F7E66
0x1800f7f60  call    cs:__imp_GetLastError
0x1800f7f66  cmp     eax, 5
0x1800f7f69  jnz     short loc_1800F7F79
0x1800f7f6b  call    cs:__imp__o__errno
0x1800f7f71  mov     dword ptr [rax], 9
0x1800f7f77  jmp     short loc_1800F7F80
0x1800f7f79  mov     ecx, eax
0x1800f7f7b  call    __la_dosmaperr
0x1800f7f80  call    cs:__imp__o__errno
0x1800f7f86  lea     r8, aWriteFailed; "Write failed"
0x1800f7f8d  mov     rcx, rbx
0x1800f7f90  mov     edx, [rax]
0x1800f7f92  call    archive_set_error
0x1800f7f97  jmp     short loc_1800F7FB2
0x1800f7f99  sub     rbp, rdi
0x1800f7f9c  mov     rax, rbp
0x1800f7f9f  jmp     short loc_1800F7FB9
0x1800f7fa1  lea     r8, aAttemptToWrite; "Attempt to write to an empty file"
0x1800f7fa8  xor     edx, edx
0x1800f7faa  mov     rcx, rbx
0x1800f7fad  call    archive_set_error
0x1800f7fb2  mov     rax, 0FFFFFFFFFFFFFFECh
0x1800f7fb9  add     rsp, 58h
0x1800f7fbd  pop     r15
0x1800f7fbf  pop     r14
0x1800f7fc1  pop     rdi
0x1800f7fc2  pop     rsi
0x1800f7fc3  pop     rbp
0x1800f7fc4  pop     rbx
0x1800f7fc5  retn
```
