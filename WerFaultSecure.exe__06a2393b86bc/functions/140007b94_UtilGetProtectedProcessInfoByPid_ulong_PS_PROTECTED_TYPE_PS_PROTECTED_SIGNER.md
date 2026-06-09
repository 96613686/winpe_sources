# UtilGetProtectedProcessInfoByPid(ulong,_PS_PROTECTED_TYPE *,_PS_PROTECTED_SIGNER *)

- ea: `0x140007b94`
- end: `0x140007c2c`
- name: `?UtilGetProtectedProcessInfoByPid@@YAJKPEAW4_PS_PROTECTED_TYPE@@PEAW4_PS_PROTECTED_SIGNER@@@Z`
- size: `152`
- prototype: `__int64 __fastcall(DWORD dwProcessId, enum _PS_PROTECTED_TYPE *, enum _PS_PROTECTED_SIGNER *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140006184`

## callees

- `0x140007a4c`
- `0x140007b94`
- `0x140007c80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007bc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007bc7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007c1b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007c1b`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140007baf`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140007baf`

## pseudocode

```c
__int64 __fastcall UtilGetProtectedProcessInfoByPid(
        DWORD dwProcessId,
        enum _PS_PROTECTED_TYPE *a2,
        enum _PS_PROTECTED_SIGNER *a3)
{
  HANDLE v6; // rax
  void *v7; // rdi
  signed int LastError; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  unsigned int ProtectedProcessInfo; // ebx

  v6 = OpenProcess(0x1000u, 0, dwProcessId);
  v7 = v6;
  if ( (unsigned __int64)v6 + 1 > 1 )
  {
    ProtectedProcessInfo = UtilGetProtectedProcessInfo(v6, a2, a3);
    CloseHandle(v7);
  }
  else
  {
    LastError = GetLastError();
    ProtectedProcessInfo = LastError;
    if ( LastError > 0 )
      ProtectedProcessInfo = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, v10, dwProcessId, ProtectedProcessInfo);
  }
  return ProtectedProcessInfo;
}

```

## disassembly

```asm
0x140007b94  push    rbx
0x140007b96  push    rbp
0x140007b97  push    rsi
0x140007b98  push    rdi
0x140007b99  sub     rsp, 38h
0x140007b9d  mov     rbx, r8
0x140007ba0  mov     rbp, rdx
0x140007ba3  mov     esi, ecx
0x140007ba5  mov     r8d, ecx; dwProcessId
0x140007ba8  xor     edx, edx; bInheritHandle
0x140007baa  mov     ecx, 1000h; dwDesiredAccess
0x140007baf  call    cs:__imp_OpenProcess
0x140007bb5  mov     rdi, rax
0x140007bb8  mov     [rsp+58h+arg_18], rax
0x140007bbd  lea     r9, [rax+1]
0x140007bc1  cmp     r9, 1
0x140007bc5  ja      short loc_140007C08
0x140007bc7  call    cs:__imp_GetLastError
0x140007bcd  mov     ebx, eax
0x140007bcf  test    eax, eax
0x140007bd1  jle     short loc_140007BDC
0x140007bd3  movzx   ebx, ax
0x140007bd6  or      ebx, 80070000h
0x140007bdc  lea     rax, WPP_GLOBAL_Control
0x140007be3  mov     rcx, cs:WPP_GLOBAL_Control
0x140007bea  cmp     rcx, rax
0x140007bed  jz      short loc_140007C06
0x140007bef  test    byte ptr [rcx+1Ch], 1
0x140007bf3  jz      short loc_140007C06
0x140007bf5  mov     [rsp+58h+var_38], ebx
0x140007bf9  mov     r9d, esi
0x140007bfc  mov     rcx, [rcx+10h]
0x140007c00  call    WPP_SF_Dd
0x140007c05  nop
0x140007c06  jmp     short loc_140007C21
0x140007c08  mov     r8, rbx; enum _PS_PROTECTED_SIGNER *
0x140007c0b  mov     rdx, rbp; enum _PS_PROTECTED_TYPE *
0x140007c0e  mov     rcx, rdi; void *
0x140007c11  call    ?UtilGetProtectedProcessInfo@@YAJPEAXPEAW4_PS_PROTECTED_TYPE@@PEAW4_PS_PROTECTED_SIGNER@@@Z; UtilGetProtectedProcessInfo(void *,_PS_PROTECTED_TYPE *,_PS_PROTECTED_SIGNER *)
0x140007c16  mov     ebx, eax
0x140007c18  mov     rcx, rdi; hObject
0x140007c1b  call    cs:__imp_CloseHandle
0x140007c21  mov     eax, ebx
0x140007c23  add     rsp, 38h
0x140007c27  pop     rdi
0x140007c28  pop     rsi
0x140007c29  pop     rbp
0x140007c2a  pop     rbx
0x140007c2b  retn
```
