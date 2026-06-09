# GetExitCode(void *,ulong *)

- ea: `0x140019b28`
- end: `0x140019c39`
- name: `?GetExitCode@@YAHPEAXPEAK@Z`
- size: `273`
- prototype: `__int64 __fastcall(HANDLE hProcess, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140017a48`

## callees

- `0x140001caf`
- `0x140019b28`
- `0x14001edc0`

## import_xrefs

- `KERNEL32!GetExitCodeThread` at `0x140019bd0`
- `KERNEL32!GetExitCodeThread` at `0x140019bd0`
- `KERNEL32!GetExitCodeProcess` at `0x140019bf9`
- `KERNEL32!GetExitCodeProcess` at `0x140019bf9`
- `KERNEL32!SetLastError` at `0x140019c0a`
- `KERNEL32!SetLastError` at `0x140019c0a`
- `ntdll!RtlEqualUnicodeString` at `0x140019bbe`
- `ntdll!RtlEqualUnicodeString` at `0x140019be7`
- `ntdll!RtlEqualUnicodeString` at `0x140019bbe`
- `ntdll!RtlEqualUnicodeString` at `0x140019be7`
- `ntdll!RtlNtStatusToDosError` at `0x140019b97`
- `ntdll!RtlNtStatusToDosError` at `0x140019b97`
- `ntdll!NtQueryObject` at `0x140019b89`
- `ntdll!NtQueryObject` at `0x140019b89`

## pseudocode

```c
__int64 __fastcall GetExitCode(HANDLE hProcess, unsigned int *a2)
{
  int Object; // eax
  unsigned int v5; // ebx
  DWORD v6; // ecx
  BOOL ExitCodeThread; // eax
  DWORD ExitCode; // [rsp+30h] [rbp-98h] BYREF
  ULONG ReturnLength[3]; // [rsp+34h] [rbp-94h] BYREF
  UNICODE_STRING ObjectInformation[7]; // [rsp+40h] [rbp-88h] BYREF

  memset_0(ObjectInformation, 0, 0x68u);
  ReturnLength[0] = 0;
  ExitCode = 0;
  Object = NtQueryObject(hProcess, ObjectTypeInformation, ObjectInformation, 0x68u, ReturnLength);
  if ( Object < 0 )
  {
    v5 = 0;
    v6 = RtlNtStatusToDosError(Object);
LABEL_12:
    SetLastError(v6);
    goto LABEL_13;
  }
  if ( ReturnLength[0] < 0x68 )
  {
    v6 = 1359;
LABEL_11:
    v5 = 0;
    goto LABEL_12;
  }
  if ( RtlEqualUnicodeString(ObjectInformation, &String2, 0) )
  {
    ExitCodeThread = GetExitCodeThread(hProcess, &ExitCode);
  }
  else
  {
    if ( !RtlEqualUnicodeString(ObjectInformation, &stru_140021070, 0) )
    {
      v6 = 87;
      goto LABEL_11;
    }
    ExitCodeThread = GetExitCodeProcess(hProcess, &ExitCode);
  }
  v5 = ExitCodeThread;
LABEL_13:
  *a2 = ExitCode;
  return v5;
}

```

## disassembly

```asm
0x140019b28  mov     [rsp+arg_10], rbx
0x140019b2d  push    rdi
0x140019b2e  sub     rsp, 0C0h
0x140019b35  mov     rax, cs:__security_cookie
0x140019b3c  xor     rax, rsp
0x140019b3f  mov     [rsp+0C8h+var_18], rax
0x140019b47  mov     rdi, rdx
0x140019b4a  mov     rbx, rcx
0x140019b4d  xor     edx, edx; Val
0x140019b4f  lea     rcx, [rsp+0C8h+ObjectInformation]; void *
0x140019b54  lea     r8d, [rdx+68h]; Size
0x140019b58  call    memset_0
0x140019b5d  mov     r9d, 68h ; 'h'; ObjectInformationLength
0x140019b63  mov     [rsp+0C8h+var_94], 0
0x140019b6b  lea     rax, [rsp+0C8h+var_94]
0x140019b70  mov     [rsp+0C8h+ExitCode], 0
0x140019b78  lea     r8, [rsp+0C8h+ObjectInformation]; ObjectInformation
0x140019b7d  mov     [rsp+0C8h+ReturnLength], rax; ReturnLength
0x140019b82  mov     rcx, rbx; Handle
0x140019b85  lea     edx, [r9-66h]; ObjectInformationClass
0x140019b89  call    cs:__imp_NtQueryObject
0x140019b8f  test    eax, eax
0x140019b91  jns     short loc_140019BA1
0x140019b93  xor     ebx, ebx
0x140019b95  mov     ecx, eax; Status
0x140019b97  call    cs:__imp_RtlNtStatusToDosError
0x140019b9d  mov     ecx, eax
0x140019b9f  jmp     short loc_140019C0A
0x140019ba1  cmp     [rsp+0C8h+var_94], 68h ; 'h'
0x140019ba6  jnb     short loc_140019BAF
0x140019ba8  mov     ecx, 54Fh
0x140019bad  jmp     short loc_140019C08
0x140019baf  xor     r8d, r8d; CaseInsensitive
0x140019bb2  lea     rdx, String2; String2
0x140019bb9  lea     rcx, [rsp+0C8h+ObjectInformation]; String1
0x140019bbe  call    cs:__imp_RtlEqualUnicodeString
0x140019bc4  test    al, al
0x140019bc6  jz      short loc_140019BD8
0x140019bc8  lea     rdx, [rsp+0C8h+ExitCode]; lpExitCode
0x140019bcd  mov     rcx, rbx; hThread
0x140019bd0  call    cs:__imp_GetExitCodeThread
0x140019bd6  jmp     short loc_140019BFF
0x140019bd8  xor     r8d, r8d; CaseInsensitive
0x140019bdb  lea     rdx, stru_140021070; String2
0x140019be2  lea     rcx, [rsp+0C8h+ObjectInformation]; String1
0x140019be7  call    cs:__imp_RtlEqualUnicodeString
0x140019bed  test    al, al
0x140019bef  jz      short loc_140019C03
0x140019bf1  lea     rdx, [rsp+0C8h+ExitCode]; lpExitCode
0x140019bf6  mov     rcx, rbx; hProcess
0x140019bf9  call    cs:__imp_GetExitCodeProcess
0x140019bff  mov     ebx, eax
0x140019c01  jmp     short loc_140019C10
0x140019c03  mov     ecx, 57h ; 'W'; dwErrCode
0x140019c08  xor     ebx, ebx
0x140019c0a  call    cs:__imp_SetLastError
0x140019c10  mov     eax, [rsp+0C8h+ExitCode]
0x140019c14  mov     [rdi], eax
0x140019c16  mov     eax, ebx
0x140019c18  mov     rcx, [rsp+0C8h+var_18]
0x140019c20  xor     rcx, rsp; StackCookie
0x140019c23  call    __security_check_cookie
0x140019c28  mov     rbx, [rsp+0C8h+arg_10]
0x140019c30  add     rsp, 0C0h
0x140019c37  pop     rdi
0x140019c38  retn
```
