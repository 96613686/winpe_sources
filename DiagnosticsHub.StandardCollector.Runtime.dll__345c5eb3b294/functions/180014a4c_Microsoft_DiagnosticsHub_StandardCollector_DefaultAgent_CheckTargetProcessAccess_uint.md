# Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent::CheckTargetProcessAccess(uint)

- ea: `0x180014a4c`
- end: `0x180014b60`
- name: `?CheckTargetProcessAccess@DefaultAgent@StandardCollector@DiagnosticsHub@Microsoft@@AEAAJI@Z`
- size: `276`
- prototype: `int(Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180013908`

## callees

- `0x180014a4c`
- `0x180049b50`
- `0x18004b640`

## import_xrefs

- `KERNEL32!OpenProcess` at `0x180014aae`
- `KERNEL32!OpenProcess` at `0x180014aae`
- `KERNEL32!CloseHandle` at `0x180014b23`
- `KERNEL32!CloseHandle` at `0x180014b23`
- `KERNEL32!GetLastError` at `0x180014abc`
- `KERNEL32!GetLastError` at `0x180014abc`
- `ole32!CoGetCallContext` at `0x180014a80`
- `ole32!CoGetCallContext` at `0x180014a80`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent::CheckTargetProcessAccess(
        Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent *this,
        DWORD a2)
{
  signed int v3; // edi
  HANDLE v4; // rbx
  signed int LastError; // esi
  void *v6; // rcx
  void *v8; // [rsp+28h] [rbp-20h] BYREF

  v8 = 0;
  if ( !CoGetCallContext(&IID_IServerSecurity, &v8) )
  {
    v3 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v8 + 32LL))(v8);
    if ( v3 < 0 )
      goto LABEL_15;
  }
  v4 = OpenProcess(0x38u, 0, a2);
  LastError = GetLastError();
  v6 = v8;
  if ( !v8 )
    goto LABEL_8;
  if ( (*(unsigned int (__fastcall **)(void *))(*(_QWORD *)v8 + 48LL))(v8) != 1
    || (v3 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v8 + 40LL))(v8), v3 >= 0) )
  {
    v6 = v8;
LABEL_8:
    if ( v4 )
    {
      v3 = 0;
    }
    else
    {
      v3 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v3 = LastError;
    }
    goto LABEL_13;
  }
  v6 = v8;
LABEL_13:
  if ( !v4 )
    goto LABEL_16;
  CloseHandle(v4);
LABEL_15:
  v6 = v8;
LABEL_16:
  if ( v6 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v6 + 16LL))(v6);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180014a4c  mov     r11, rsp
0x180014a4f  mov     [r11+8], rbx
0x180014a53  mov     [r11+18h], rsi
0x180014a57  push    rdi
0x180014a58  sub     rsp, 40h
0x180014a5c  mov     rax, cs:__security_cookie
0x180014a63  xor     rax, rsp
0x180014a66  mov     [rsp+48h+var_18], rax
0x180014a6b  mov     ebx, edx
0x180014a6d  mov     qword ptr [r11-20h], 0
0x180014a75  lea     rdx, [r11-20h]; ppInterface
0x180014a79  lea     rcx, IID_IServerSecurity; riid
0x180014a80  call    cs:__imp_CoGetCallContext
0x180014a86  test    eax, eax
0x180014a88  jnz     short loc_180014AA6
0x180014a8a  mov     rcx, [rsp+48h+var_20]
0x180014a8f  mov     rax, [rcx]
0x180014a92  mov     rax, [rax+20h]
0x180014a96  call    cs:__guard_dispatch_icall_fptr
0x180014a9c  mov     edi, eax
0x180014a9e  test    eax, eax
0x180014aa0  js      loc_180014B29
0x180014aa6  mov     r8d, ebx; dwProcessId
0x180014aa9  xor     edx, edx; bInheritHandle
0x180014aab  lea     ecx, [rdx+38h]; dwDesiredAccess
0x180014aae  call    cs:__imp_OpenProcess
0x180014ab4  mov     rbx, rax
0x180014ab7  mov     [rsp+48h+var_28], rax
0x180014abc  call    cs:__imp_GetLastError
0x180014ac2  mov     esi, eax
0x180014ac4  mov     rcx, [rsp+48h+var_20]
0x180014ac9  test    rcx, rcx
0x180014acc  jz      short loc_180014B04
0x180014ace  mov     rdx, [rcx]
0x180014ad1  mov     rax, [rdx+30h]
0x180014ad5  call    cs:__guard_dispatch_icall_fptr
0x180014adb  cmp     eax, 1
0x180014ade  jnz     short loc_180014AFF
0x180014ae0  mov     rcx, [rsp+48h+var_20]
0x180014ae5  mov     rax, [rcx]
0x180014ae8  mov     rax, [rax+28h]
0x180014aec  call    cs:__guard_dispatch_icall_fptr
0x180014af2  mov     edi, eax
0x180014af4  test    eax, eax
0x180014af6  jns     short loc_180014AFF
0x180014af8  mov     rcx, [rsp+48h+var_20]
0x180014afd  jmp     short loc_180014B1B
0x180014aff  mov     rcx, [rsp+48h+var_20]
0x180014b04  test    rbx, rbx
0x180014b07  jnz     short loc_180014B19
0x180014b09  movzx   edi, si
0x180014b0c  or      edi, 80070000h
0x180014b12  test    esi, esi
0x180014b14  cmovle  edi, esi
0x180014b17  jmp     short loc_180014B1B
0x180014b19  xor     edi, edi
0x180014b1b  test    rbx, rbx
0x180014b1e  jz      short loc_180014B2E
0x180014b20  mov     rcx, rbx; hObject
0x180014b23  call    cs:__imp_CloseHandle
0x180014b29  mov     rcx, [rsp+48h+var_20]
0x180014b2e  test    rcx, rcx
0x180014b31  jz      short loc_180014B41
0x180014b33  mov     rdx, [rcx]
0x180014b36  mov     rax, [rdx+10h]
0x180014b3a  call    cs:__guard_dispatch_icall_fptr
0x180014b40  nop
0x180014b41  mov     eax, edi
0x180014b43  mov     rcx, [rsp+48h+var_18]
0x180014b48  xor     rcx, rsp; StackCookie
0x180014b4b  call    __security_check_cookie
0x180014b50  mov     rbx, [rsp+48h+arg_0]
0x180014b55  mov     rsi, [rsp+48h+arg_10]
0x180014b5a  add     rsp, 40h
0x180014b5e  pop     rdi
0x180014b5f  retn
```
