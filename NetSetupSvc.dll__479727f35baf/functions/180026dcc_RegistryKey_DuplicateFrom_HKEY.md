# RegistryKey::DuplicateFrom(HKEY__ *)

- ea: `0x180026dcc`
- end: `0x180026ee5`
- name: `?DuplicateFrom@RegistryKey@@SA?AV1@PEAUHKEY__@@@Z`
- size: `281`
- prototype: `RegistryKey *__fastcall(RegistryKey *, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800207bc`

## callees

- `0x1800027c0`
- `0x1800032e4`
- `0x1800078f8`
- `0x180008854`
- `0x180026958`
- `0x180026dcc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026e49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026e49`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180026e07`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180026e10`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180026e07`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180026e10`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180026e3f`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180026e3f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
RegistryKey *__fastcall RegistryKey::DuplicateFrom(RegistryKey *a1, void *a2)
{
  HANDLE CurrentProcess; // rbx
  HANDLE v5; // rax
  signed int LastError; // ebx
  _BYTE pExceptionObject[208]; // [rsp+48h] [rbp-F0h] BYREF
  HANDLE TargetHandle; // [rsp+118h] [rbp-20h] BYREF

  TargetHandle = 0;
  CurrentProcess = GetCurrentProcess();
  v5 = GetCurrentProcess();
  if ( !DuplicateHandle(v5, a2, CurrentProcess, &TargetHandle, 0, 0, 2u) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_419802ccba213757c01acb0d7aa84d96_Traceguids,
        (unsigned int)LastError);
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    HResultException::HResultException((HResultException *)pExceptionObject, LastError);
    throw (HResultException *)pExceptionObject;
  }
  RegistryKey::RegistryKey(a1, (HKEY)TargetHandle);
  return a1;
}

```

## disassembly

```asm
0x180026dcc  mov     r11, rsp
0x180026dcf  mov     [r11+18h], rbx
0x180026dd3  mov     [r11+20h], rsi
0x180026dd7  push    rdi
0x180026dd8  sub     rsp, 130h
0x180026ddf  mov     rax, cs:__security_cookie
0x180026de6  xor     rax, rsp
0x180026de9  mov     [rsp+138h+var_18], rax
0x180026df1  mov     [rsp+138h+TargetHandle], rcx
0x180026df9  mov     rdi, rdx
0x180026dfc  mov     qword ptr [r11-20h], 0
0x180026e04  mov     rsi, rcx
0x180026e07  call    cs:__imp_GetCurrentProcess
0x180026e0d  mov     rbx, rax
0x180026e10  call    cs:__imp_GetCurrentProcess
0x180026e16  mov     [rsp+138h+dwOptions], 2; dwOptions
0x180026e1e  lea     r9, [rsp+138h+TargetHandle]; lpTargetHandle
0x180026e26  mov     rcx, rax; hSourceProcessHandle
0x180026e29  mov     [rsp+138h+bInheritHandle], 0; bInheritHandle
0x180026e31  mov     r8, rbx; hTargetProcessHandle
0x180026e34  mov     [rsp+138h+dwDesiredAccess], 0; dwDesiredAccess
0x180026e3c  mov     rdx, rdi; hSourceHandle
0x180026e3f  call    cs:__imp_DuplicateHandle
0x180026e45  test    eax, eax
0x180026e47  jnz     short loc_180026EAD
0x180026e49  call    cs:__imp_GetLastError
0x180026e4f  mov     ebx, eax
0x180026e51  mov     rcx, cs:WPP_GLOBAL_Control
0x180026e58  lea     rax, WPP_GLOBAL_Control
0x180026e5f  cmp     rcx, rax
0x180026e62  jz      short loc_180026E82
0x180026e64  cmp     byte ptr [rcx+19h], 2
0x180026e68  jb      short loc_180026E82
0x180026e6a  mov     rcx, [rcx+10h]
0x180026e6e  lea     r8, WPP_419802ccba213757c01acb0d7aa84d96_Traceguids
0x180026e75  mov     edx, 0Ah
0x180026e7a  mov     r9d, ebx
0x180026e7d  call    WPP_SF_d
0x180026e82  test    ebx, ebx
0x180026e84  jle     short loc_180026E8F
0x180026e86  movzx   ebx, bx
0x180026e89  or      ebx, 80070000h
0x180026e8f  mov     edx, ebx; int
0x180026e91  lea     rcx, [rsp+138h+pExceptionObject]; this
0x180026e96  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x180026e9b  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x180026ea2  lea     rcx, [rsp+138h+pExceptionObject]; pExceptionObject
0x180026ea7  call    _CxxThrowException_0
0x180026ead  mov     rdx, [rsp+138h+TargetHandle]; HKEY
0x180026eb5  mov     rcx, rsi; this
0x180026eb8  call    ??0RegistryKey@@QEAA@PEAUHKEY__@@@Z; RegistryKey::RegistryKey(HKEY__ *)
0x180026ebd  mov     rax, rsi
0x180026ec0  mov     rcx, [rsp+138h+var_18]
0x180026ec8  xor     rcx, rsp; StackCookie
0x180026ecb  call    __security_check_cookie
0x180026ed0  lea     r11, [rsp+138h+var_8]
0x180026ed8  mov     rbx, [r11+20h]
0x180026edc  mov     rsi, [r11+28h]
0x180026ee0  mov     rsp, r11
0x180026ee3  pop     rdi
0x180026ee4  retn
```
