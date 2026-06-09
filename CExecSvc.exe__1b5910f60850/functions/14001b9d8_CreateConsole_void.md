# CreateConsole(void)

- ea: `0x14001b9d8`
- end: `0x14001bac7`
- name: `?CreateConsole@@YA?AUConsoleDriverHandles@@XZ`
- size: `239`
- prototype: `void **__fastcall(void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140016cc0`

## callees

- `0x140014f3c`
- `0x14001b9d8`
- `0x14001f36c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001ba3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001ba3e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001ba51`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001ba51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001ba49`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001ba49`

## string_xrefs

- `0x14001ba9b`: `onecore\vm\compute\service\cexec\lib\consoletostream.cpp`
- `0x14001bab5`: `onecore\vm\compute\service\cexec\lib\consoletostream.cpp`

## pseudocode

```c
void **__fastcall CreateConsole(void **a1)
{
  void **v2; // rsi
  int Handle; // eax
  void *v4; // rbp
  DWORD LastError; // ebx
  int v6; // eax
  int v8; // [rsp+20h] [rbp-58h]
  int v9; // [rsp+20h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v2 = a1 + 1;
  a1[1] = (void *)-1LL;
  *a1 = (void *)-1LL;
  Handle = CspCreateHandle(a1, 1, 0);
  if ( Handle < 0 )
    wil::details::in1diag3::Throw_NtStatus(
      retaddr,
      (void *)0x81,
      (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\consoletostream.cpp",
      (const char *)(unsigned int)Handle,
      v8);
  v4 = *v2;
  if ( (char *)*v2 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    LastError = GetLastError();
    CloseHandle(v4);
    SetLastError(LastError);
  }
  *v2 = (void *)-1LL;
  v6 = CspCreateHandle(v2, 0, 0x20u);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_NtStatus(
      retaddr,
      (void *)0x86,
      (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\consoletostream.cpp",
      (const char *)(unsigned int)v6,
      v9);
  return a1;
}

```

## disassembly

```asm
0x14001b9d8  mov     rax, rsp
0x14001b9db  mov     [rax+8], rcx
0x14001b9df  push    rbx
0x14001b9e0  push    rbp
0x14001b9e1  push    rsi
0x14001b9e2  push    rdi
0x14001b9e3  push    r12
0x14001b9e5  push    r14
0x14001b9e7  sub     rsp, 48h
0x14001b9eb  mov     rdi, rcx
0x14001b9ee  mov     dword ptr [rax-48h], 0
0x14001b9f5  or      r12, 0FFFFFFFFFFFFFFFFh
0x14001b9f9  lea     rsi, [rcx+8]
0x14001b9fd  mov     [rsi], r12
0x14001ba00  mov     dword ptr [rax-48h], 1
0x14001ba07  mov     [rcx], r12
0x14001ba0a  mov     dword ptr [rax-50h], 0
0x14001ba11  mov     byte ptr [rax-58h], 1
0x14001ba15  xor     r9d, r9d
0x14001ba18  mov     r8d, 10000000h
0x14001ba1e  lea     rdx, aDeviceCondrvSe; "\\Device\\ConDrv\\Server"
0x14001ba25  call    CspCreateHandle
0x14001ba2a  test    eax, eax
0x14001ba2c  js      short loc_14001BAAD
0x14001ba2e  mov     r14, [rdi]
0x14001ba31  mov     rbp, [rsi]
0x14001ba34  lea     rax, [rbp-1]
0x14001ba38  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001ba3c  ja      short loc_14001BA57
0x14001ba3e  call    cs:__imp_GetLastError
0x14001ba44  mov     ebx, eax
0x14001ba46  mov     rcx, rbp; hObject
0x14001ba49  call    cs:__imp_CloseHandle
0x14001ba4f  mov     ecx, ebx; dwErrCode
0x14001ba51  call    cs:__imp_SetLastError
0x14001ba57  mov     [rsi], r12
0x14001ba5a  mov     [rsp+78h+var_50], 20h ; ' '; ULONG
0x14001ba62  mov     [rsp+78h+var_58], 0; int
0x14001ba67  mov     r9, r14
0x14001ba6a  mov     r8d, 0C0100000h
0x14001ba70  lea     rdx, aReference; "\\Reference"
0x14001ba77  mov     rcx, rsi; FileHandle
0x14001ba7a  call    CspCreateHandle
0x14001ba7f  test    eax, eax
0x14001ba81  js      short loc_14001BA93
0x14001ba83  mov     rax, rdi
0x14001ba86  add     rsp, 48h
0x14001ba8a  pop     r14
0x14001ba8c  pop     r12
0x14001ba8e  pop     rdi
0x14001ba8f  pop     rsi
0x14001ba90  pop     rbp
0x14001ba91  pop     rbx
0x14001ba92  retn
0x14001ba93  mov     rcx, [rsp+78h]; this
0x14001ba98  mov     r9d, eax; char *
0x14001ba9b  lea     r8, aOnecoreVmCompu_4; "onecore\\vm\\compute\\service\\cexec\\l"...
0x14001baa2  mov     edx, 86h; void *
0x14001baa7  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x14001baad  mov     rcx, [rsp+78h]; this
0x14001bab2  mov     r9d, eax; char *
0x14001bab5  lea     r8, aOnecoreVmCompu_4; "onecore\\vm\\compute\\service\\cexec\\l"...
0x14001babc  mov     edx, 81h; void *
0x14001bac1  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
```
