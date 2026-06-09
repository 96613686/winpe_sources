# Microsoft::CoreUI::HvSockets::HvSocket::SendSynchronous(Microsoft::CoreUI::Support::Win32Event,void *,uint)

- ea: `0x18009aa9c`
- end: `0x18009ab60`
- name: `?SendSynchronous@HvSocket@HvSockets@CoreUI@Microsoft@@QEAAXUWin32Event@Support@34@PEAXI@Z`
- size: `196`
- prototype: `void __high(struct Microsoft::CoreUI::Support::Win32Event, void *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18009a960`

## callees

- `0x180007d80`
- `0x18008f584`
- `0x18009aa9c`
- `0x1800b50d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009aaf7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009aaf7`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18009aaed`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18009aaed`

## pseudocode

```c
void __fastcall Microsoft::CoreUI::HvSockets::HvSocket::SendSynchronous(void **a1, void *a2, char *a3, DWORD a4)
{
  void *v4; // rbp
  __int64 v9; // r8
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  struct _OVERLAPPED Overlapped; // [rsp+30h] [rbp-38h] BYREF
  unsigned int v15; // [rsp+88h] [rbp+20h] BYREF

  v4 = *a1;
  while ( a4 )
  {
    Overlapped.hEvent = a2;
    memset(&Overlapped, 0, 24);
    if ( !WriteFile(v4, a3, a4, 0, &Overlapped) && GetLastError() != 997 )
      Cn::FailFast::ForWin32();
    v15 = 0;
    LOBYTE(v9) = 1;
    if ( !(unsigned __int8)Microsoft::CoreUI::HvSockets::HvSocket::GetIoResult(a1, &Overlapped, v9, &v15) )
      CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,unsigned long,void *)>>::GetHashCode(
        v11,
        v10,
        v12,
        v13);
    a3 += v15;
    a4 -= v15;
  }
}

```

## disassembly

```asm
0x18009aa9c  mov     [rsp+arg_0], rbx
0x18009aaa1  mov     [rsp+arg_8], rbp
0x18009aaa6  push    rsi
0x18009aaa7  push    rdi
0x18009aaa8  push    r14
0x18009aaaa  sub     rsp, 50h
0x18009aaae  mov     rbp, [rcx]
0x18009aab1  mov     edi, r9d
0x18009aab4  mov     rsi, r8
0x18009aab7  mov     rbx, rdx
0x18009aaba  mov     r14, rcx
0x18009aabd  test    edi, edi
0x18009aabf  jz      loc_18009AB4D
0x18009aac5  xorps   xmm0, xmm0
0x18009aac8  lea     rax, [rsp+68h+Overlapped]
0x18009aacd  movups  xmmword ptr [rsp+68h+Overlapped.10h], xmm0
0x18009aad2  xor     r9d, r9d; lpNumberOfBytesWritten
0x18009aad5  mov     [rsp+68h+Overlapped.hEvent], rbx
0x18009aada  mov     r8d, edi; nNumberOfBytesToWrite
0x18009aadd  mov     [rsp+68h+lpOverlapped], rax; lpOverlapped
0x18009aae2  mov     rdx, rsi; lpBuffer
0x18009aae5  mov     rcx, rbp; hFile
0x18009aae8  movups  xmmword ptr [rsp+68h+Overlapped.Internal], xmm0
0x18009aaed  call    cs:__imp_WriteFile
0x18009aaf3  test    eax, eax
0x18009aaf5  jnz     short loc_18009AB04
0x18009aaf7  call    cs:__imp_GetLastError
0x18009aafd  cmp     eax, 3E5h
0x18009ab02  jnz     short loc_18009AB41
0x18009ab04  lea     r9, [rsp+68h+arg_18]
0x18009ab0c  mov     [rsp+68h+arg_18], 0
0x18009ab17  mov     r8b, 1
0x18009ab1a  lea     rdx, [rsp+68h+Overlapped]
0x18009ab1f  mov     rcx, r14
0x18009ab22  call    ?GetIoResult@HvSocket@HvSockets@CoreUI@Microsoft@@QEAA_NPEAX_NU?$Ref@I@CFlat@@@Z; Microsoft::CoreUI::HvSockets::HvSocket::GetIoResult(void *,bool,CFlat::Ref<uint>)
0x18009ab27  test    al, al
0x18009ab29  jz      short loc_18009AB47
0x18009ab2b  mov     eax, [rsp+68h+arg_18]
0x18009ab32  add     rsi, rax
0x18009ab35  sub     edi, [rsp+68h+arg_18]
0x18009ab3c  jmp     loc_18009AABD
0x18009ab41  call    ?ForWin32@FailFast@Cn@@SAXXZ; Cn::FailFast::ForWin32(void)
0x18009ab47  call    ?GetHashCode@?$Box$1@U?$FunctionPointerAndUserData$1@P6AJPEAXK0@Z@CFlat@@@CFlat@@UEAAHXZ; CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,ulong,void *)>>::GetHashCode(void)
0x18009ab4d  mov     rbx, [rsp+68h+arg_0]
0x18009ab52  mov     rbp, [rsp+68h+arg_8]
0x18009ab57  add     rsp, 50h
0x18009ab5b  pop     r14
0x18009ab5d  pop     rdi
0x18009ab5e  pop     rsi
0x18009ab5f  retn
```
