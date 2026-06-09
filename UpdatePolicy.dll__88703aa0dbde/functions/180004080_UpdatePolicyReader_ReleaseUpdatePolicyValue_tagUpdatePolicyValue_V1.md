# UpdatePolicyReader::ReleaseUpdatePolicyValue(tagUpdatePolicyValue_V1 * *)

- ea: `0x180004080`
- end: `0x18000411b`
- name: `?ReleaseUpdatePolicyValue@UpdatePolicyReader@@SAJPEAPEAUtagUpdatePolicyValue_V1@@@Z`
- size: `155`
- prototype: `static int(struct tagUpdatePolicyValue_V1 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x180003984`
- `0x180004080`
- `0x180005a1c`
- `0x180015430`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800040ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800040ad`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800040a4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800040a4`

## string_xrefs

- `0x18000409d`: `ReleaseUpdatePolicyValue`

## pseudocode

```c
__int64 __fastcall UpdatePolicyReader::ReleaseUpdatePolicyValue(struct tagUpdatePolicyValue_V1 **a1)
{
  int Dll; // eax
  FARPROC ProcAddress; // rdi
  signed int LastError; // eax
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  Dll = UndockedModuleForwarder::LoadDll((UndockedModuleForwarder *)a1);
  if ( Dll < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x31,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\inc\\UndockedModuleForwarder.h",
      (const char *)(unsigned int)Dll,
      v9);
  ProcAddress = GetProcAddress(hLibModule, "ReleaseUpdatePolicyValue");
  LastError = GetLastError();
  v7 = (unsigned __int16)LastError | 0x80070000;
  if ( LastError <= 0 )
    v7 = (unsigned int)LastError;
  if ( (int)v7 >= 0 )
    v7 = 2147549183LL;
  if ( !ProcAddress )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x37,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\inc\\UndockedModuleForwarder.h",
      (const char *)v7,
      v9);
  return ((__int64 (__fastcall *)(struct tagUpdatePolicyValue_V1 **, __int64, __int64, __int64))ProcAddress)(
           a1,
           v5,
           v6,
           v7);
}

```

## disassembly

```asm
0x180004080  mov     [rsp+arg_0], rbx
0x180004085  push    rdi; int
0x180004086  sub     rsp, 20h
0x18000408a  mov     rbx, rcx
0x18000408d  call    ?LoadDll@UndockedModuleForwarder@@AEAAJXZ; UndockedModuleForwarder::LoadDll(void)
0x180004092  test    eax, eax
0x180004094  js      short loc_180004101
0x180004096  mov     rcx, cs:hLibModule; hModule
0x18000409d  lea     rdx, aReleaseupdatep_0; "ReleaseUpdatePolicyValue"
0x1800040a4  call    cs:__imp_GetProcAddress
0x1800040aa  mov     rdi, rax
0x1800040ad  call    cs:__imp_GetLastError
0x1800040b3  movzx   r9d, ax
0x1800040b7  or      r9d, 80070000h
0x1800040be  test    eax, eax
0x1800040c0  cmovle  r9d, eax
0x1800040c4  mov     eax, 8000FFFFh
0x1800040c9  test    r9d, r9d
0x1800040cc  cmovns  r9d, eax; char *
0x1800040d0  test    rdi, rdi
0x1800040d3  jz      short loc_1800040EA
0x1800040d5  mov     rcx, rbx
0x1800040d8  mov     rax, rdi
0x1800040db  mov     rbx, [rsp+28h+arg_0]
0x1800040e0  add     rsp, 20h
0x1800040e4  pop     rdi
0x1800040e5  jmp     _guard_dispatch_icall
0x1800040ea  mov     rcx, [rsp+28h]; this
0x1800040ef  lea     r8, aCW1SSrcClientI_0; "C:\\__w\\1\\s\\src\\Client\\inc\\Undock"...
0x1800040f6  mov     edx, 37h ; '7'; void *
0x1800040fb  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180004101  mov     rcx, [rsp+28h]; this
0x180004106  lea     r8, aCW1SSrcClientI_0; "C:\\__w\\1\\s\\src\\Client\\inc\\Undock"...
0x18000410d  mov     r9d, eax; char *
0x180004110  mov     edx, 31h ; '1'; void *
0x180004115  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
