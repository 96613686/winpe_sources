# NfcAsyncIo::DeviceIoControlInternal(NfcAsyncIoCallContext *,ulong,void const *,ulong,void *,ulong,UNNAMED_STRUCT_NfcAsyncIoCancelToken * *)

- ea: `0x180095c10`
- end: `0x180095cba`
- name: `?DeviceIoControlInternal@NfcAsyncIo@@AEAAJPEAVNfcAsyncIoCallContext@@KPEBXKPEAXKPEAPEAUUNNAMED_STRUCT_NfcAsyncIoCancelToken@@@Z`
- size: `170`
- prototype: `int(NfcAsyncIo *__hidden this, struct NfcAsyncIoCallContext *, unsigned int, const void *, unsigned int, void *, unsigned int, struct UNNAMED_STRUCT_NfcAsyncIoCancelToken **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180095cc0`

## callees

- `0x180014898`
- `0x180095c10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095c72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095c72`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180095c2a`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180095c2a`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180095c89`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180095c89`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180095c6a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180095c6a`

## pseudocode

```c
int __fastcall NfcAsyncIo::DeviceIoControlInternal(
        PTP_IO *this,
        struct NfcAsyncIoCallContext *a2,
        DWORD a3,
        void *a4,
        DWORD nInBufferSize,
        void *a6,
        DWORD nOutBufferSize)
{
  DWORD LastError; // eax
  DWORD v12; // edi
  unsigned int lpOutBuffer; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  StartThreadpoolIo(this[1]);
  LODWORD(a2) = DeviceIoControl(*this, a3, a4, nInBufferSize, a6, nOutBufferSize, 0, (LPOVERLAPPED)((char *)a2 + 8));
  LastError = GetLastError();
  v12 = LastError;
  if ( (_DWORD)a2 )
    return 0;
  if ( LastError == 997 )
    return 0;
  CancelThreadpoolIo(this[1]);
  if ( !v12 )
    return 0;
  else
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x92,
             (unsigned int)"onecoreuap\\ds\\nfc\\product\\utils\\nfcasyncio\\src\\nfcasyncio.cpp",
             (const char *)v12,
             lpOutBuffer);
}

```

## disassembly

```asm
0x180095c10  push    rbx
0x180095c12  push    rsi
0x180095c13  push    rdi
0x180095c14  push    r14
0x180095c16  sub     rsp, 48h
0x180095c1a  mov     r14, rcx
0x180095c1d  mov     rdi, r9
0x180095c20  mov     rcx, [rcx+8]; pio
0x180095c24  mov     esi, r8d
0x180095c27  mov     rbx, rdx
0x180095c2a  call    cs:__imp_StartThreadpoolIo
0x180095c30  mov     r9d, [rsp+68h+nInBufferSize]; nInBufferSize
0x180095c38  lea     rax, [rbx+8]
0x180095c3c  mov     rcx, [r14]; hDevice
0x180095c3f  mov     r8, rdi; lpInBuffer
0x180095c42  mov     [rsp+68h+lpOverlapped], rax; lpOverlapped
0x180095c47  mov     edx, esi; dwIoControlCode
0x180095c49  mov     eax, [rsp+68h+arg_30]
0x180095c50  mov     [rsp+68h+lpBytesReturned], 0; lpBytesReturned
0x180095c59  mov     [rsp+68h+nOutBufferSize], eax; nOutBufferSize
0x180095c5d  mov     rax, [rsp+68h+arg_28]
0x180095c65  mov     [rsp+68h+lpOutBuffer], rax; unsigned int
0x180095c6a  call    cs:__imp_DeviceIoControl
0x180095c70  mov     ebx, eax
0x180095c72  call    cs:__imp_GetLastError
0x180095c78  mov     edi, eax
0x180095c7a  test    ebx, ebx
0x180095c7c  jnz     short loc_180095CAE
0x180095c7e  cmp     eax, 3E5h
0x180095c83  jz      short loc_180095CAE
0x180095c85  mov     rcx, [r14+8]; pio
0x180095c89  call    cs:__imp_CancelThreadpoolIo
0x180095c8f  test    edi, edi
0x180095c91  jz      short loc_180095CAE
0x180095c93  mov     rcx, [rsp+68h]; this
0x180095c98  lea     r8, aOnecoreuapDsNf_24; "onecoreuap\\ds\\nfc\\product\\utils\\nf"...
0x180095c9f  mov     r9d, edi; char *
0x180095ca2  mov     edx, 92h; void *
0x180095ca7  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180095cac  jmp     short loc_180095CB0
0x180095cae  xor     eax, eax
0x180095cb0  add     rsp, 48h
0x180095cb4  pop     r14
0x180095cb6  pop     rdi
0x180095cb7  pop     rsi
0x180095cb8  pop     rbx
0x180095cb9  retn
```
