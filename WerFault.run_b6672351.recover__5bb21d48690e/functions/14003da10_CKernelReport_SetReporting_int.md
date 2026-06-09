# CKernelReport::SetReporting(int)

- ea: `0x14003da10`
- end: `0x14003db3d`
- name: `?SetReporting@CKernelReport@@AEAAJH@Z`
- size: `301`
- prototype: `int(CKernelReport *__hidden this, int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14003bbd4`

## callees

- `0x1400372dc`
- `0x14003da10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x14003da30`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x14003da30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003da70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003da87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003da70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003da87`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003da54`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003dac8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003db21`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003da54`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003dac8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003db21`

## string_xrefs

- `0x14003dadb`: `CreateMutex failed`

## pseudocode

```c
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
      (void *)0x1D1,
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
0x14003da10  mov     [rsp+arg_0], rbx
0x14003da15  push    rdi; char *
0x14003da16  sub     rsp, 30h
0x14003da1a  mov     rdi, rcx
0x14003da1d  test    edx, edx
0x14003da1f  jz      loc_14003DB05
0x14003da25  lea     r8, aGlobalWerkerne_0; "Global\\WerKernelVerticalReporting"
0x14003da2c  xor     edx, edx; bInitialOwner
0x14003da2e  xor     ecx, ecx; lpMutexAttributes
0x14003da30  call    cs:__imp_CreateMutexW
0x14003da37  nop     dword ptr [rax+rax+00h]
0x14003da3c  mov     rcx, [rdi+288h]; hObject
0x14003da43  mov     [rdi+288h], rax
0x14003da4a  lea     rax, [rcx+1]
0x14003da4e  cmp     rax, 1
0x14003da52  jbe     short loc_14003DA60
0x14003da54  call    cs:__imp_CloseHandle
0x14003da5b  nop     dword ptr [rax+rax+00h]
0x14003da60  mov     rax, [rdi+288h]
0x14003da67  inc     rax
0x14003da6a  cmp     rax, 1
0x14003da6e  jbe     short loc_14003DA87
0x14003da70  call    cs:__imp_GetLastError
0x14003da77  nop     dword ptr [rax+rax+00h]
0x14003da7c  cmp     eax, 0B7h
0x14003da81  jnz     loc_14003DB2D
0x14003da87  call    cs:__imp_GetLastError
0x14003da8e  nop     dword ptr [rax+rax+00h]
0x14003da93  mov     ebx, eax
0x14003da95  test    eax, eax
0x14003da97  jle     short loc_14003DAA2
0x14003da99  movzx   ebx, ax
0x14003da9c  or      ebx, 80070000h
0x14003daa2  mov     rcx, [rdi+288h]; hObject
0x14003daa9  test    ebx, ebx
0x14003daab  mov     eax, 80004005h
0x14003dab0  cmovns  ebx, eax
0x14003dab3  lea     rax, [rcx+1]
0x14003dab7  cmp     rax, 1
0x14003dabb  jbe     short loc_14003DAD6
0x14003dabd  mov     qword ptr [rdi+288h], 0
0x14003dac8  call    cs:__imp_CloseHandle
0x14003dacf  nop     dword ptr [rax+rax+00h]
0x14003dad4  jmp     short loc_14003DB2F
0x14003dad6  mov     rcx, [rsp+38h]; this
0x14003dadb  lea     rax, aCreatemutexFai; "CreateMutex failed"
0x14003dae2  mov     qword ptr [rsp+38h+var_10], rax; int
0x14003dae7  lea     r9, aCkernelreportS; "CKernelReport::SetReporting"
0x14003daee  lea     r8, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x14003daf5  mov     dword ptr [rsp+38h+var_18], ebx; wil::details *
0x14003daf9  mov     edx, 1D1h; void *
0x14003dafe  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003db03  jmp     short loc_14003DB2F
0x14003db05  mov     rcx, [rcx+288h]; hObject
0x14003db0c  mov     qword ptr [rdi+288h], 0
0x14003db17  lea     rax, [rcx+1]
0x14003db1b  cmp     rax, 1
0x14003db1f  jbe     short loc_14003DB2D
0x14003db21  call    cs:__imp_CloseHandle
0x14003db28  nop     dword ptr [rax+rax+00h]
0x14003db2d  xor     ebx, ebx
0x14003db2f  mov     eax, ebx
0x14003db31  mov     rbx, [rsp+38h+arg_0]
0x14003db36  add     rsp, 30h
0x14003db3a  pop     rdi
0x14003db3b  retn
```
