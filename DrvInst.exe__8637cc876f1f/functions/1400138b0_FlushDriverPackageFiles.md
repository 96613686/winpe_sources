# FlushDriverPackageFiles

- ea: `0x1400138b0`
- end: `0x140013a43`
- name: `FlushDriverPackageFiles`
- size: `403`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, LPCWSTR, LPCWSTR, LPCWSTR)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140013220`

## callees

- `0x14001379c`
- `0x1400138b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013926`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001396a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013991`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400139aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013926`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001396a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013991`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400139aa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140013a24`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140013a24`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1400138ec`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1400139c2`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1400138ec`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1400139c2`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400139fb`
- `DEVRTL!DevRtlWriteTextLog` at `0x140013a1c`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400139fb`
- `DEVRTL!DevRtlWriteTextLog` at `0x140013a1c`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x1400138d3`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x1400138d3`

## pseudocode

```c
_BOOL8 __fastcall FlushDriverPackageFiles(LPCWSTR lpFileName, LPCWSTR a2, LPCWSTR a3, LPCWSTR a4)
{
  DWORD LastError; // ebx
  __int64 ThreadLogToken; // rax
  __int64 v10; // rsi
  unsigned __int64 v11; // r15
  __int64 v12; // rax
  unsigned __int64 UnbiasedTime; // [rsp+88h] [rbp+10h] BYREF

  LastError = 0;
  ThreadLogToken = DevRtlGetThreadLogToken();
  UnbiasedTime = 0;
  v10 = ThreadLogToken;
  QueryUnbiasedInterruptTime(&UnbiasedTime);
  v11 = UnbiasedTime / 0x2710;
  if ( a4 )
  {
    while ( *a4 )
    {
      if ( !FlushDriverPackageFile(a4, 2u, v10) )
        LastError = GetLastError();
      v12 = -1;
      do
        ++v12;
      while ( a4[v12] );
      a4 += v12 + 1;
    }
  }
  if ( a3 && *a3 && !FlushDriverPackageFile(a3, 2u, v10) )
    LastError = GetLastError();
  if ( a2 && *a2 && !FlushDriverPackageFile(a2, 2u, v10) )
    LastError = GetLastError();
  if ( !FlushDriverPackageFile(lpFileName, 0, v10) )
    LastError = GetLastError();
  UnbiasedTime = 0;
  QueryUnbiasedInterruptTime(&UnbiasedTime);
  if ( LastError )
    DevRtlWriteTextLog(
      v10,
      1,
      2,
      "Unable to flush all driver package files to disk. Time = %u ms, Error = 0x%08X",
      UnbiasedTime / 0x2710 - v11,
      LastError);
  else
    DevRtlWriteTextLog(v10, 1, 4, "Flushed all driver package files to disk. Time = %u ms", UnbiasedTime / 0x2710 - v11);
  SetLastError(LastError);
  return LastError == 0;
}

```

## disassembly

```asm
0x1400138b0  push    rbx
0x1400138b2  push    rbp
0x1400138b3  push    rsi
0x1400138b4  push    rdi
0x1400138b5  push    r12
0x1400138b7  push    r13
0x1400138b9  push    r14
0x1400138bb  push    r15
0x1400138bd  sub     rsp, 38h
0x1400138c1  xor     r13d, r13d
0x1400138c4  mov     rdi, r9
0x1400138c7  mov     ebx, r13d
0x1400138ca  mov     rbp, r8
0x1400138cd  mov     r14, rdx
0x1400138d0  mov     r12, rcx
0x1400138d3  call    cs:__imp_DevRtlGetThreadLogToken
0x1400138d9  lea     rcx, [rsp+78h+UnbiasedTime]; UnbiasedTime
0x1400138e1  mov     [rsp+78h+UnbiasedTime], r13
0x1400138e9  mov     rsi, rax
0x1400138ec  call    cs:__imp_QueryUnbiasedInterruptTime
0x1400138f2  mov     rax, 346DC5D63886594Bh
0x1400138fc  mul     [rsp+78h+UnbiasedTime]
0x140013904  mov     r15, rdx
0x140013907  shr     r15, 0Bh
0x14001390b  test    rdi, rdi
0x14001390e  jz      short loc_14001394A
0x140013910  jmp     short loc_140013944
0x140013912  mov     r8, rsi
0x140013915  mov     edx, 2
0x14001391a  mov     rcx, rdi; lpFileName
0x14001391d  call    FlushDriverPackageFile
0x140013922  test    eax, eax
0x140013924  jnz     short loc_14001392E
0x140013926  call    cs:__imp_GetLastError
0x14001392c  mov     ebx, eax
0x14001392e  or      rax, 0FFFFFFFFFFFFFFFFh
0x140013932  inc     rax
0x140013935  cmp     [rdi+rax*2], r13w
0x14001393a  jnz     short loc_140013932
0x14001393c  lea     rdi, [rdi+rax*2]
0x140013940  add     rdi, 2
0x140013944  cmp     [rdi], r13w
0x140013948  jnz     short loc_140013912
0x14001394a  test    rbp, rbp
0x14001394d  jz      short loc_140013972
0x14001394f  cmp     [rbp+0], r13w
0x140013954  jz      short loc_140013972
0x140013956  mov     r8, rsi
0x140013959  mov     edx, 2
0x14001395e  mov     rcx, rbp; lpFileName
0x140013961  call    FlushDriverPackageFile
0x140013966  test    eax, eax
0x140013968  jnz     short loc_140013972
0x14001396a  call    cs:__imp_GetLastError
0x140013970  mov     ebx, eax
0x140013972  test    r14, r14
0x140013975  jz      short loc_140013999
0x140013977  cmp     [r14], r13w
0x14001397b  jz      short loc_140013999
0x14001397d  mov     r8, rsi
0x140013980  mov     edx, 2
0x140013985  mov     rcx, r14; lpFileName
0x140013988  call    FlushDriverPackageFile
0x14001398d  test    eax, eax
0x14001398f  jnz     short loc_140013999
0x140013991  call    cs:__imp_GetLastError
0x140013997  mov     ebx, eax
0x140013999  mov     r8, rsi
0x14001399c  xor     edx, edx
0x14001399e  mov     rcx, r12; lpFileName
0x1400139a1  call    FlushDriverPackageFile
0x1400139a6  test    eax, eax
0x1400139a8  jnz     short loc_1400139B2
0x1400139aa  call    cs:__imp_GetLastError
0x1400139b0  mov     ebx, eax
0x1400139b2  lea     rcx, [rsp+78h+UnbiasedTime]; UnbiasedTime
0x1400139ba  mov     [rsp+78h+UnbiasedTime], r13
0x1400139c2  call    cs:__imp_QueryUnbiasedInterruptTime
0x1400139c8  mov     rax, 346DC5D63886594Bh
0x1400139d2  mov     rcx, rsi
0x1400139d5  mul     [rsp+78h+UnbiasedTime]
0x1400139dd  shr     rdx, 0Bh
0x1400139e1  sub     rdx, r15
0x1400139e4  test    ebx, ebx
0x1400139e6  jnz     short loc_140013A03
0x1400139e8  mov     [rsp+78h+var_58], rdx
0x1400139ed  lea     r9, aFlushedAllDriv; "Flushed all driver package files to dis"...
0x1400139f4  lea     edx, [rbx+1]
0x1400139f7  lea     r8d, [rbx+4]
0x1400139fb  call    cs:__imp_DevRtlWriteTextLog
0x140013a01  jmp     short loc_140013A22
0x140013a03  mov     [rsp+78h+var_50], ebx
0x140013a07  lea     r9, aUnableToFlushA; "Unable to flush all driver package file"...
0x140013a0e  mov     [rsp+78h+var_58], rdx
0x140013a13  mov     edx, 1
0x140013a18  lea     r8d, [rdx+1]
0x140013a1c  call    cs:__imp_DevRtlWriteTextLog
0x140013a22  mov     ecx, ebx; dwErrCode
0x140013a24  call    cs:__imp_SetLastError
0x140013a2a  test    ebx, ebx
0x140013a2c  mov     eax, r13d
0x140013a2f  setz    al
0x140013a32  add     rsp, 38h
0x140013a36  pop     r15
0x140013a38  pop     r14
0x140013a3a  pop     r13
0x140013a3c  pop     r12
0x140013a3e  pop     rdi
0x140013a3f  pop     rsi
0x140013a40  pop     rbp
0x140013a41  pop     rbx
0x140013a42  retn
```
