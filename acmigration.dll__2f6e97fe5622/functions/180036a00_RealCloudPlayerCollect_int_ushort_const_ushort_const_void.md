# RealCloudPlayerCollect(int *,ushort const *,ushort const *,void *)

- ea: `0x180036a00`
- end: `0x180036ad0`
- name: `?RealCloudPlayerCollect@@YAJPEAHPEBG1PEAX@Z`
- size: `208`
- prototype: `__int64 __fastcall(int *, const unsigned __int16 *, const unsigned __int16 *, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, installer_update`

## callees

- `0x180036a00`
- `0x1800543c0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180036a2b`
- `KERNEL32!GetLastError` at `0x180036a70`
- `KERNEL32!GetLastError` at `0x180036a2b`
- `KERNEL32!GetLastError` at `0x180036a70`
- `ADVAPI32!OpenSCManagerW` at `0x180036a1d`
- `ADVAPI32!OpenSCManagerW` at `0x180036a1d`
- `ADVAPI32!OpenServiceW` at `0x180036a65`
- `ADVAPI32!OpenServiceW` at `0x180036a65`
- `ADVAPI32!CloseServiceHandle` at `0x180036aa7`
- `ADVAPI32!CloseServiceHandle` at `0x180036ab0`
- `ADVAPI32!CloseServiceHandle` at `0x180036aa7`
- `ADVAPI32!CloseServiceHandle` at `0x180036ab0`

## string_xrefs

- `0x180036a31`: `Failed to open service control manager [%d]`
- `0x180036a5b`: `RealPlayerUpdateSvc`
- `0x180036a76`: `Failed to open real cloud player update service [%d]`

## pseudocode

```c
__int64 __fastcall RealCloudPlayerCollect(int *a1, const unsigned __int16 *a2, const unsigned __int16 *a3, void *a4)
{
  SC_HANDLE v5; // rax
  SC_HANDLE v6; // rdi
  signed int LastError; // ebx
  SC_HANDLE v8; // rax

  *a1 = 1;
  v5 = OpenSCManagerW(0, 0, 0xF003Fu);
  v6 = v5;
  if ( v5 )
  {
    v8 = OpenServiceW(v5, L"RealPlayerUpdateSvc", 2u);
    if ( v8 )
    {
      *a1 = 0;
      LastError = 0;
      CloseServiceHandle(v8);
    }
    else
    {
      LastError = GetLastError();
      AslLogCallPrintf(
        1,
        "RealCloudPlayerCollect",
        172,
        "Failed to open real cloud player update service [%d]",
        LastError);
    }
    CloseServiceHandle(v6);
  }
  else
  {
    LastError = GetLastError();
    AslLogCallPrintf(1, "RealCloudPlayerCollect", 160, "Failed to open service control manager [%d]", LastError);
  }
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180036a00  mov     [rsp+arg_0], rbx
0x180036a05  push    rdi
0x180036a06  sub     rsp, 30h
0x180036a0a  mov     rbx, rcx
0x180036a0d  mov     dword ptr [rcx], 1
0x180036a13  xor     ecx, ecx; lpMachineName
0x180036a15  xor     edx, edx; lpDatabaseName
0x180036a17  mov     r8d, 0F003Fh; dwDesiredAccess
0x180036a1d  call    cs:__imp_OpenSCManagerW
0x180036a23  mov     rdi, rax
0x180036a26  test    rax, rax
0x180036a29  jnz     short loc_180036A55
0x180036a2b  call    cs:__imp_GetLastError
0x180036a31  lea     r9, aFailedToOpenSe_0; "Failed to open service control manager "...
0x180036a38  mov     r8d, 0A0h
0x180036a3e  lea     rdx, aRealcloudplaye; "RealCloudPlayerCollect"
0x180036a45  mov     [rsp+38h+var_18], eax
0x180036a49  lea     ecx, [rdi+1]
0x180036a4c  mov     ebx, eax
0x180036a4e  call    AslLogCallPrintf
0x180036a53  jmp     short loc_180036AB6
0x180036a55  mov     r8d, 2; dwDesiredAccess
0x180036a5b  lea     rdx, ServiceName; "RealPlayerUpdateSvc"
0x180036a62  mov     rcx, rdi; hSCManager
0x180036a65  call    cs:__imp_OpenServiceW
0x180036a6b  test    rax, rax
0x180036a6e  jnz     short loc_180036A9C
0x180036a70  call    cs:__imp_GetLastError
0x180036a76  lea     r9, aFailedToOpenRe_0; "Failed to open real cloud player update"...
0x180036a7d  mov     r8d, 0ACh
0x180036a83  lea     rdx, aRealcloudplaye; "RealCloudPlayerCollect"
0x180036a8a  mov     [rsp+38h+var_18], eax
0x180036a8e  mov     ecx, 1
0x180036a93  mov     ebx, eax
0x180036a95  call    AslLogCallPrintf
0x180036a9a  jmp     short loc_180036AAD
0x180036a9c  mov     dword ptr [rbx], 0
0x180036aa2  xor     ebx, ebx
0x180036aa4  mov     rcx, rax; hSCObject
0x180036aa7  call    cs:__imp_CloseServiceHandle
0x180036aad  mov     rcx, rdi; hSCObject
0x180036ab0  call    cs:__imp_CloseServiceHandle
0x180036ab6  test    ebx, ebx
0x180036ab8  jle     short loc_180036AC3
0x180036aba  movzx   ebx, bx
0x180036abd  or      ebx, 80070000h
0x180036ac3  mov     eax, ebx
0x180036ac5  mov     rbx, [rsp+38h+arg_0]
0x180036aca  add     rsp, 30h
0x180036ace  pop     rdi
0x180036acf  retn
```
