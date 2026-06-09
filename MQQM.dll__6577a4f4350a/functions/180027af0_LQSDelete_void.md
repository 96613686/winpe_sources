# LQSDelete(void *)

- ea: `0x180027af0`
- end: `0x180027b80`
- name: `?LQSDelete@@YAJPEAX@Z`
- size: `144`
- prototype: `__int64 __fastcall(LPCWSTR *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180050e90`

## callees

- `0x180009924`
- `0x180027af0`
- `0x18002c61c`
- `0x18002c6c8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180027b1f`
- `KERNEL32!GetLastError` at `0x180027b1f`
- `KERNEL32!LeaveCriticalSection` at `0x180027b41`
- `KERNEL32!LeaveCriticalSection` at `0x180027b6c`
- `KERNEL32!LeaveCriticalSection` at `0x180027b41`
- `KERNEL32!LeaveCriticalSection` at `0x180027b6c`
- `KERNEL32!DeleteFileW` at `0x180027b15`
- `KERNEL32!DeleteFileW` at `0x180027b15`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LQSDelete(LPCWSTR *a1)
{
  DWORD LastError; // eax

  CCriticalSection::Lock((CCriticalSection *)&stru_18013A368);
  if ( DeleteFileW(*a1) )
  {
    LastError = GetLastError();
    if ( LastError )
      LogMsgNTStatus(LastError, (wchar_t *)L"lqs", 0x172u);
    LeaveCriticalSection(&stru_18013A368);
    return 3222143080LL;
  }
  else
  {
    LogMsgHR(-1072824319, (wchar_t *)L"lqs", 0x17Cu);
    LeaveCriticalSection(&stru_18013A368);
    return 3222142977LL;
  }
}

```

## disassembly

```asm
0x180027af0  mov     [rsp+arg_8], rbx
0x180027af5  push    rdi
0x180027af6  sub     rsp, 20h
0x180027afa  mov     rbx, rcx
0x180027afd  lea     rdi, stru_18013A368
0x180027b04  mov     [rsp+28h+arg_0], rdi
0x180027b09  mov     rcx, rdi; this
0x180027b0c  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x180027b11  nop
0x180027b12  mov     rcx, [rbx]; lpFileName
0x180027b15  call    cs:__imp_DeleteFileW
0x180027b1b  test    eax, eax
0x180027b1d  jz      short loc_180027B4F
0x180027b1f  call    cs:__imp_GetLastError
0x180027b25  test    eax, eax
0x180027b27  jz      short loc_180027B3E
0x180027b29  mov     r8d, 172h; unsigned __int16
0x180027b2f  lea     rdx, aLqs_0; "lqs"
0x180027b36  mov     ecx, eax; int
0x180027b38  call    ?LogMsgNTStatus@@YAXJPEA_WG@Z; LogMsgNTStatus(long,wchar_t *,ushort)
0x180027b3d  nop
0x180027b3e  mov     rcx, rdi; lpCriticalSection
0x180027b41  call    cs:__imp_LeaveCriticalSection
0x180027b47  nop
0x180027b48  mov     eax, 0C00E0068h
0x180027b4d  jmp     short loc_180027B75
0x180027b4f  mov     r8d, 17Ch; unsigned __int16
0x180027b55  lea     rdx, aLqs_0; "lqs"
0x180027b5c  mov     ebx, 0C00E0001h
0x180027b61  mov     ecx, ebx; int
0x180027b63  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180027b68  nop
0x180027b69  mov     rcx, rdi; lpCriticalSection
0x180027b6c  call    cs:__imp_LeaveCriticalSection
0x180027b72  nop
0x180027b73  mov     eax, ebx
0x180027b75  mov     rbx, [rsp+28h+arg_8]
0x180027b7a  add     rsp, 20h
0x180027b7e  pop     rdi
0x180027b7f  retn
```
