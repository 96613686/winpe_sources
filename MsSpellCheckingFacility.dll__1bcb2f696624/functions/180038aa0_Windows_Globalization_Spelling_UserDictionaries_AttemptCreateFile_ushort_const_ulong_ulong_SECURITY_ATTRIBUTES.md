# Windows::Globalization::Spelling::UserDictionaries::AttemptCreateFile(ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,ulong)

- ea: `0x180038aa0`
- end: `0x180038b3a`
- name: `?AttemptCreateFile@UserDictionaries@Spelling@Globalization@Windows@@CAPEAXPEBGKKPEAU_SECURITY_ATTRIBUTES@@KKK@Z`
- size: `154`
- prototype: `void *__fastcall(LPCWSTR lpFileName, DWORD dwDesiredAccess, DWORD dwShareMode, LPSECURITY_ATTRIBUTES lpSecurityAttributes, DWORD, DWORD, unsigned int)`
- caller_count: `7`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180046be0`
- `0x180047770`
- `0x1800479dc`
- `0x180047b18`
- `0x18007e014`
- `0x180085a40`
- `0x180089b90`

## callees

- `0x180038aa0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038b04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038b04`
- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x180038b19`
- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x180038b19`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180038af8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180038af8`

## pseudocode

```c
__int64 __fastcall Windows::Globalization::Spelling::UserDictionaries::AttemptCreateFile(
        LPCWSTR lpFileName,
        DWORD dwDesiredAccess,
        DWORD dwShareMode,
        LPSECURITY_ATTRIBUTES lpSecurityAttributes,
        DWORD dwCreationDisposition,
        DWORD dwFlagsAndAttributes)
{
  DWORD v10; // edi
  unsigned int i; // ebx
  __int64 result; // rax

  v10 = 2;
  for ( i = 0; i < 5; ++i )
  {
    result = (__int64)CreateFileW(
                        lpFileName,
                        dwDesiredAccess,
                        dwShareMode,
                        lpSecurityAttributes,
                        dwCreationDisposition,
                        dwFlagsAndAttributes,
                        0);
    if ( result != -1 )
      return result;
    if ( GetLastError() - 2 <= 1 )
      break;
    SleepEx(v10, 1);
    v10 *= 2;
  }
  return -1;
}

```

## disassembly

```asm
0x180038aa0  push    rbx
0x180038aa2  push    rbp
0x180038aa3  push    rsi
0x180038aa4  push    rdi
0x180038aa5  push    r12
0x180038aa7  push    r13
0x180038aa9  push    r14
0x180038aab  push    r15
0x180038aad  sub     rsp, 48h
0x180038ab1  mov     r12d, [rsp+88h+arg_28]
0x180038ab9  mov     rsi, r9
0x180038abc  mov     r13d, [rsp+88h+arg_20]
0x180038ac4  mov     ebp, r8d
0x180038ac7  mov     r14d, edx
0x180038aca  mov     r15, rcx
0x180038acd  mov     edi, 2
0x180038ad2  xor     ebx, ebx
0x180038ad4  cmp     ebx, 5
0x180038ad7  jnb     short loc_180038B25
0x180038ad9  mov     [rsp+88h+hTemplateFile], 0; hTemplateFile
0x180038ae2  mov     r9, rsi; lpSecurityAttributes
0x180038ae5  mov     [rsp+88h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x180038aea  mov     r8d, ebp; dwShareMode
0x180038aed  mov     edx, r14d; dwDesiredAccess
0x180038af0  mov     [rsp+88h+dwCreationDisposition], r13d; dwCreationDisposition
0x180038af5  mov     rcx, r15; lpFileName
0x180038af8  call    cs:__imp_CreateFileW
0x180038afe  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180038b02  jnz     short loc_180038B29
0x180038b04  call    cs:__imp_GetLastError
0x180038b0a  add     eax, 0FFFFFFFEh
0x180038b0d  cmp     eax, 1
0x180038b10  jbe     short loc_180038B25
0x180038b12  mov     edx, 1; bAlertable
0x180038b17  mov     ecx, edi; dwMilliseconds
0x180038b19  call    cs:__imp_SleepEx
0x180038b1f  add     edi, edi
0x180038b21  inc     ebx
0x180038b23  jmp     short loc_180038AD4
0x180038b25  or      rax, 0FFFFFFFFFFFFFFFFh
0x180038b29  add     rsp, 48h
0x180038b2d  pop     r15
0x180038b2f  pop     r14
0x180038b31  pop     r13
0x180038b33  pop     r12
0x180038b35  pop     rdi
0x180038b36  pop     rsi
0x180038b37  pop     rbp
0x180038b38  pop     rbx
0x180038b39  retn
```
