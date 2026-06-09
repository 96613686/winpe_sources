# GetSkuUpdateManagementGroup

- ea: `0x180003dd0`
- end: `0x180003e5c`
- name: `GetSkuUpdateManagementGroup`
- size: `140`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callees

- `0x180003984`
- `0x180003dd0`
- `0x180005a1c`
- `0x180015430`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003df6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003df6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003ded`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003ded`

## string_xrefs

- `0x180003de6`: `GetSkuUpdateManagementGroup`

## pseudocode

```c
__int64 __fastcall GetSkuUpdateManagementGroup(UndockedModuleForwarder *a1)
{
  int Dll; // eax
  FARPROC ProcAddress; // rbx
  signed int LastError; // eax
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  Dll = UndockedModuleForwarder::LoadDll(a1);
  if ( Dll < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x31,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\inc\\UndockedModuleForwarder.h",
      (const char *)(unsigned int)Dll,
      v9);
  ProcAddress = GetProcAddress(hLibModule, "GetSkuUpdateManagementGroup");
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
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))ProcAddress)(v5, v4, v6, v7);
}

```

## disassembly

```asm
0x180003dd0  push    rbx; int
0x180003dd2  sub     rsp, 20h
0x180003dd6  call    ?LoadDll@UndockedModuleForwarder@@AEAAJXZ; UndockedModuleForwarder::LoadDll(void)
0x180003ddb  test    eax, eax
0x180003ddd  js      short loc_180003E42
0x180003ddf  mov     rcx, cs:hLibModule; hModule
0x180003de6  lea     rdx, aGetskuupdatema_0; "GetSkuUpdateManagementGroup"
0x180003ded  call    cs:__imp_GetProcAddress
0x180003df3  mov     rbx, rax
0x180003df6  call    cs:__imp_GetLastError
0x180003dfc  movzx   r9d, ax
0x180003e00  or      r9d, 80070000h
0x180003e07  test    eax, eax
0x180003e09  cmovle  r9d, eax
0x180003e0d  mov     eax, 8000FFFFh
0x180003e12  test    r9d, r9d
0x180003e15  cmovns  r9d, eax; char *
0x180003e19  test    rbx, rbx
0x180003e1c  jz      short loc_180003E2B
0x180003e1e  mov     rax, rbx
0x180003e21  add     rsp, 20h
0x180003e25  pop     rbx
0x180003e26  jmp     _guard_dispatch_icall
0x180003e2b  mov     rcx, [rsp+28h]; this
0x180003e30  lea     r8, aCW1SSrcClientI_0; "C:\\__w\\1\\s\\src\\Client\\inc\\Undock"...
0x180003e37  mov     edx, 37h ; '7'; void *
0x180003e3c  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180003e42  mov     rcx, [rsp+28h]; this
0x180003e47  lea     r8, aCW1SSrcClientI_0; "C:\\__w\\1\\s\\src\\Client\\inc\\Undock"...
0x180003e4e  mov     r9d, eax; char *
0x180003e51  mov     edx, 31h ; '1'; void *
0x180003e56  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
