# RmpLimitsCreateDump

- ea: `0x1800177d0`
- end: `0x1800178e6`
- name: `RmpLimitsCreateDump`
- size: `278`
- prototype: `char __fastcall(__int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800178f0`

## callees

- `0x18000cd30`
- `0x180011f00`
- `0x1800177d0`
- `0x18001ae8e`
- `0x18001aec0`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x180017825`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x180017825`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001781b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001781b`
- `ntdll!RtlReportException` at `0x18001785d`
- `ntdll!RtlReportException` at `0x18001785d`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001780e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001780e`

## pseudocode

```c
char __fastcall RmpLimitsCreateDump(__int64 a1)
{
  char result; // al
  __int64 v3; // rcx
  int v4; // r9d
  int v5; // [rsp+30h] [rbp-D0h] BYREF
  _DWORD v6[4]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v7; // [rsp+50h] [rbp-B0h]
  CONTEXT ContextRecord; // [rsp+E0h] [rbp-20h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v9; // [rsp+5B0h] [rbp+4B0h] BYREF
  int *v10; // [rsp+5D0h] [rbp+4D0h]
  __int64 v11; // [rsp+5D8h] [rbp+4D8h]

  memset_0(v6, 0, 0x98u);
  RtlAcquireSRWLockExclusive(a1);
  *(_DWORD *)(a1 + 36) |= 1u;
  RtlReleaseSRWLockExclusive(a1);
  RtlCaptureContext(&ContextRecord);
  memset_0(v6, 0, 0x98u);
  v6[0] = -1073741395;
  v6[1] = 0;
  v7 = 0;
  result = RtlReportException(v6, &ContextRecord, 14);
  if ( (unsigned int)dword_18002E000 > 4 )
  {
    result = tlgKeywordOn((__int64)&dword_18002E000, 5);
    if ( result )
    {
      v5 = v4;
      v10 = &v5;
      v11 = 4;
      return tlgWriteTransfer_EventWriteTransfer(v3, (unsigned __int8 *)byte_180026AF9, 0, 0, 3u, &v9);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800177d0  mov     [rsp-8+arg_8], rbx
0x1800177d5  push    rbp
0x1800177d6  lea     rbp, [rsp-4F0h]
0x1800177de  sub     rsp, 5F0h
0x1800177e5  mov     rax, cs:__security_cookie
0x1800177ec  xor     rax, rsp
0x1800177ef  mov     [rbp+4F0h+var_10], rax
0x1800177f6  mov     rbx, rcx
0x1800177f9  xor     edx, edx; Val
0x1800177fb  lea     rcx, [rsp+5F0h+var_5B0]; void *
0x180017800  mov     r8d, 98h; Size
0x180017806  call    memset_0
0x18001780b  mov     rcx, rbx
0x18001780e  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180017814  or      dword ptr [rbx+24h], 1
0x180017818  mov     rcx, rbx
0x18001781b  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180017821  lea     rcx, [rbp+4F0h+ContextRecord]; ContextRecord
0x180017825  call    cs:__imp_RtlCaptureContext
0x18001782b  xor     edx, edx; Val
0x18001782d  lea     rcx, [rsp+5F0h+var_5B0]; void *
0x180017832  mov     r8d, 98h; Size
0x180017838  call    memset_0
0x18001783d  xor     ebx, ebx
0x18001783f  mov     [rsp+5F0h+var_5B0], 0C00001ADh
0x180017847  lea     rdx, [rbp+4F0h+ContextRecord]
0x18001784b  mov     [rsp+5F0h+var_5AC], ebx
0x18001784f  lea     rcx, [rsp+5F0h+var_5B0]
0x180017854  mov     [rsp+5F0h+var_5A0], rbx
0x180017859  lea     r8d, [rbx+0Eh]
0x18001785d  call    cs:__imp_RtlReportException
0x180017863  mov     ecx, cs:dword_18002E000
0x180017869  mov     r9d, eax
0x18001786c  cmp     ecx, 4
0x18001786f  jbe     short loc_1800178C6
0x180017871  lea     edx, [rbx+5]
0x180017874  lea     rcx, dword_18002E000
0x18001787b  call    _tlgKeywordOn
0x180017880  test    al, al
0x180017882  jz      short loc_1800178C6
0x180017884  lea     rax, [rsp+5F0h+var_5C0]
0x180017889  mov     [rsp+5F0h+var_5C0], r9d
0x18001788e  mov     [rbp+4F0h+var_20], rax
0x180017895  lea     rdx, byte_180026AF9
0x18001789c  lea     rax, [rbp+4F0h+var_40]
0x1800178a3  mov     [rbp+4F0h+var_18], 4
0x1800178ae  mov     [rsp+5F0h+var_5C8], rax
0x1800178b3  xor     r9d, r9d
0x1800178b6  xor     r8d, r8d
0x1800178b9  mov     [rsp+5F0h+var_5D0], 3
0x1800178c1  call    _tlgWriteTransfer_EventWriteTransfer
0x1800178c6  mov     rcx, [rbp+4F0h+var_10]
0x1800178cd  xor     rcx, rsp; StackCookie
0x1800178d0  call    __security_check_cookie
0x1800178d5  mov     rbx, [rsp+5F0h+arg_8]
0x1800178dd  add     rsp, 5F0h
0x1800178e4  pop     rbp
0x1800178e5  retn
```
