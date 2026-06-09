# CallMsiAdvertiseScriptThread(MSI_ADVERTISE_SCRIPT_PARAM *)

- ea: `0x180005c40`
- end: `0x180005ce3`
- name: `?CallMsiAdvertiseScriptThread@@YAKPEAUMSI_ADVERTISE_SCRIPT_PARAM@@@Z`
- size: `163`
- prototype: `__int64 __fastcall(_DWORD *Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180005c40`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005c8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005c8a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005cce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005cce`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180005cad`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180005cad`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180005c80`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180005c80`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180005c6e`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180005c6e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180005cb3`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180005cb3`

## pseudocode

```c
__int64 __fastcall CallMsiAdvertiseScriptThread(_DWORD *Parameter)
{
  __int64 v2; // rbx
  unsigned int v3; // ebp
  __int64 v4; // r14
  unsigned int v5; // r15d
  char *v6; // rdi
  HRESULT v7; // eax
  DWORD LastError; // ebx

  v2 = *(_QWORD *)Parameter;
  v3 = Parameter[2];
  v4 = *((_QWORD *)Parameter + 2);
  v5 = Parameter[6];
  v6 = (char *)*((_QWORD *)Parameter + 4);
  v7 = CoInitializeEx(0, 2u);
  if ( v7 < 0 )
  {
    LastError = (unsigned __int16)v7;
  }
  else if ( !v6 || ImpersonateLoggedOnUser(v6) )
  {
    LastError = ((__int64 (__fastcall *)(__int64, _QWORD, __int64, _QWORD))gpfnMsiAdvertiseScript)(v2, v3, v4, v5);
    RevertToSelf();
    CoUninitialize();
  }
  else
  {
    LastError = GetLastError();
  }
  Parameter[10] = LastError;
  if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v6);
  return LastError;
}

```

## disassembly

```asm
0x180005c40  push    rbx
0x180005c42  push    rbp
0x180005c43  push    rsi
0x180005c44  push    rdi
0x180005c45  push    r14
0x180005c47  push    r15
0x180005c49  sub     rsp, 38h
0x180005c4d  mov     rsi, rcx
0x180005c50  mov     rbx, [rcx]
0x180005c53  mov     ebp, [rcx+8]
0x180005c56  mov     r14, [rcx+10h]
0x180005c5a  mov     r15d, [rcx+18h]
0x180005c5e  mov     rdi, [rcx+20h]
0x180005c62  mov     [rsp+68h+arg_0], rdi
0x180005c67  mov     edx, 2; dwCoInit
0x180005c6c  xor     ecx, ecx; pvReserved
0x180005c6e  call    cs:__imp_CoInitializeEx
0x180005c74  test    eax, eax
0x180005c76  js      short loc_180005CBB
0x180005c78  test    rdi, rdi
0x180005c7b  jz      short loc_180005C94
0x180005c7d  mov     rcx, rdi; hToken
0x180005c80  call    cs:__imp_ImpersonateLoggedOnUser
0x180005c86  test    eax, eax
0x180005c88  jnz     short loc_180005C94
0x180005c8a  call    cs:__imp_GetLastError
0x180005c90  mov     ebx, eax
0x180005c92  jmp     short loc_180005CBE
0x180005c94  mov     r9d, r15d
0x180005c97  mov     r8, r14
0x180005c9a  mov     edx, ebp
0x180005c9c  mov     rcx, rbx
0x180005c9f  mov     rax, cs:?gpfnMsiAdvertiseScript@@3P6AIPEBGKPEAPEAUHKEY__@@H@ZEA; uint (*gpfnMsiAdvertiseScript)(ushort const *,ulong,HKEY__ * *,int)
0x180005ca6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cab  mov     ebx, eax
0x180005cad  call    cs:__imp_RevertToSelf
0x180005cb3  call    cs:__imp_CoUninitialize
0x180005cb9  jmp     short loc_180005CBE
0x180005cbb  movzx   ebx, ax
0x180005cbe  mov     [rsi+28h], ebx
0x180005cc1  lea     rax, [rdi-1]
0x180005cc5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180005cc9  ja      short loc_180005CD4
0x180005ccb  mov     rcx, rdi; hObject
0x180005cce  call    cs:__imp_CloseHandle
0x180005cd4  mov     eax, ebx
0x180005cd6  add     rsp, 38h
0x180005cda  pop     r15
0x180005cdc  pop     r14
0x180005cde  pop     rdi
0x180005cdf  pop     rsi
0x180005ce0  pop     rbp
0x180005ce1  pop     rbx
0x180005ce2  retn
```
