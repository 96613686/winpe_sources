# CKernelReport::SetReporting(int)

- ea: `0x14003b1ac`
- end: `0x14003b2b4`
- name: `?SetReporting@CKernelReport@@AEAAJH@Z`
- size: `264`
- prototype: `__int64 __fastcall(CKernelReport *this, int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140039614`

## callees

- `0x140034d9c`
- `0x14003b1ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x14003b1cc`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x14003b1cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b200`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b211`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b200`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b211`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003b1ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003b24c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003b29f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003b1ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003b24c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003b29f`

## string_xrefs

- `0x14003b259`: `CreateMutex failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CKernelReport::SetReporting(CKernelReport *this, int a2)
{
  HANDLE MutexW; // rax
  void *v4; // rcx
  signed int LastError; // eax
  signed int v6; // ebx
  void *v7; // rcx
  void *v8; // rcx
  wil::details *v10; // [rsp+20h] [rbp-18h]
  const char *v11; // [rsp+30h] [rbp-8h]
  wil::details::in1diag4 *retaddr; // [rsp+38h] [rbp+0h]

  if ( !a2 )
  {
    v8 = (void *)*((_QWORD *)this + 81);
    *((_QWORD *)this + 81) = 0;
    if ( (unsigned __int64)v8 + 1 > 1 )
      CloseHandle(v8);
    return 0;
  }
  MutexW = CreateMutexW(0, 0, L"Global\\WerKernelVerticalReporting");
  v4 = (void *)*((_QWORD *)this + 81);
  *((_QWORD *)this + 81) = MutexW;
  if ( (unsigned __int64)v4 + 1 > 1 )
    CloseHandle(v4);
  if ( *((_QWORD *)this + 81) != -1 && *((_QWORD *)this + 81) != 0 && GetLastError() != 183 )
    return 0;
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
  v7 = (void *)*((_QWORD *)this + 81);
  if ( v6 >= 0 )
    v6 = -2147467259;
  if ( (unsigned __int64)v7 + 1 <= 1 )
  {
    LODWORD(v10) = v6;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)0x1D0,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
      "CKernelReport::SetReporting",
      v10,
      (int)"CreateMutex failed",
      v11);
  }
  else
  {
    *((_QWORD *)this + 81) = 0;
    CloseHandle(v7);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14003b1ac  mov     [rsp+arg_0], rbx
0x14003b1b1  push    rdi; char *
0x14003b1b2  sub     rsp, 30h
0x14003b1b6  mov     rdi, rcx
0x14003b1b9  test    edx, edx
0x14003b1bb  jz      loc_14003B283
0x14003b1c1  lea     r8, aGlobalWerkerne_0; "Global\\WerKernelVerticalReporting"
0x14003b1c8  xor     edx, edx; bInitialOwner
0x14003b1ca  xor     ecx, ecx; lpMutexAttributes
0x14003b1cc  call    cs:__imp_CreateMutexW
0x14003b1d2  mov     rcx, [rdi+288h]; hObject
0x14003b1d9  mov     [rdi+288h], rax
0x14003b1e0  lea     rax, [rcx+1]
0x14003b1e4  cmp     rax, 1
0x14003b1e8  jbe     short loc_14003B1F0
0x14003b1ea  call    cs:__imp_CloseHandle
0x14003b1f0  mov     rax, [rdi+288h]
0x14003b1f7  inc     rax
0x14003b1fa  cmp     rax, 1
0x14003b1fe  jbe     short loc_14003B211
0x14003b200  call    cs:__imp_GetLastError
0x14003b206  cmp     eax, 0B7h
0x14003b20b  jnz     loc_14003B2A5
0x14003b211  call    cs:__imp_GetLastError
0x14003b217  mov     ebx, eax
0x14003b219  test    eax, eax
0x14003b21b  jle     short loc_14003B226
0x14003b21d  movzx   ebx, ax
0x14003b220  or      ebx, 80070000h
0x14003b226  mov     rcx, [rdi+288h]; hObject
0x14003b22d  test    ebx, ebx
0x14003b22f  mov     eax, 80004005h
0x14003b234  cmovns  ebx, eax
0x14003b237  lea     rax, [rcx+1]
0x14003b23b  cmp     rax, 1
0x14003b23f  jbe     short loc_14003B254
0x14003b241  mov     qword ptr [rdi+288h], 0
0x14003b24c  call    cs:__imp_CloseHandle
0x14003b252  jmp     short loc_14003B2A7
0x14003b254  mov     rcx, [rsp+38h]; this
0x14003b259  lea     rax, aCreatemutexFai; "CreateMutex failed"
0x14003b260  mov     qword ptr [rsp+38h+var_10], rax; int
0x14003b265  lea     r9, aCkernelreportS; "CKernelReport::SetReporting"
0x14003b26c  lea     r8, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x14003b273  mov     dword ptr [rsp+38h+var_18], ebx; wil::details *
0x14003b277  mov     edx, 1D0h; void *
0x14003b27c  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003b281  jmp     short loc_14003B2A7
0x14003b283  mov     rcx, [rcx+288h]; hObject
0x14003b28a  mov     qword ptr [rdi+288h], 0
0x14003b295  lea     rax, [rcx+1]
0x14003b299  cmp     rax, 1
0x14003b29d  jbe     short loc_14003B2A5
0x14003b29f  call    cs:__imp_CloseHandle
0x14003b2a5  xor     ebx, ebx
0x14003b2a7  mov     eax, ebx
0x14003b2a9  mov     rbx, [rsp+38h+arg_0]
0x14003b2ae  add     rsp, 30h
0x14003b2b2  pop     rdi
0x14003b2b3  retn
```
