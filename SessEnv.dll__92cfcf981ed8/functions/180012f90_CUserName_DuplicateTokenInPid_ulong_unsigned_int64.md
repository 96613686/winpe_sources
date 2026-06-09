# CUserName::DuplicateTokenInPid(ulong,unsigned __int64 *)

- ea: `0x180012f90`
- end: `0x1800130a2`
- name: `?DuplicateTokenInPid@CUserName@@UEAAJKPEA_K@Z`
- size: `274`
- prototype: `__int64 __fastcall(CUserName *this, DWORD, HANDLE *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180003f30`
- `0x180012f90`
- `0x1800130a8`
- `0x18003508c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012fff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012fff`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180013076`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180013076`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001304c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001304c`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18001303d`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18001303d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180012fe2`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180012fe2`

## string_xrefs

- `0x180012fbf`: `No token`

## pseudocode

```c
__int64 __fastcall CUserName::DuplicateTokenInPid(CUserName *this, DWORD a2, HANDLE *a3)
{
  bool v3; // zf
  unsigned int v6; // ebx
  HANDLE v7; // rax
  HANDLE v8; // rbx
  signed int LastError; // eax
  HANDLE v10; // rdi
  HANDLE CurrentProcess; // rax
  HANDLE hTargetProcessHandle; // [rsp+50h] [rbp+8h] BYREF
  HANDLE hSourceHandle; // [rsp+60h] [rbp+18h] BYREF

  v3 = (*((_BYTE *)this + 1600) & 1) == 0;
  hSourceHandle = 0;
  hTargetProcessHandle = 0;
  if ( v3 )
  {
    _DbgPrintMessage(8, "No token");
    v6 = -2147023888;
  }
  else
  {
    v7 = OpenProcess(0x40u, 0, a2);
    SmartHANDLE::operator=(&hTargetProcessHandle, v7);
    v8 = hTargetProcessHandle;
    if ( hTargetProcessHandle
      && DuplicateTokenEx(*((HANDLE *)this + 199), 0x2000000u, 0, SecurityImpersonation, TokenPrimary, &hSourceHandle)
      && (v10 = hSourceHandle,
          CurrentProcess = GetCurrentProcess(),
          DuplicateHandle(CurrentProcess, v10, v8, a3, 0, 0, 3u)) )
    {
      v6 = 0;
    }
    else
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
    }
  }
  SmartHANDLE::~SmartHANDLE((SmartHANDLE *)&hTargetProcessHandle);
  return v6;
}

```

## disassembly

```asm
0x180012f90  mov     rax, rsp
0x180012f93  mov     [rax+10h], rbx
0x180012f97  mov     [rax+20h], rsi
0x180012f9b  push    rdi
0x180012f9c  sub     rsp, 40h
0x180012fa0  test    byte ptr [rcx+640h], 1
0x180012fa7  mov     rsi, r8
0x180012faa  mov     rdi, rcx
0x180012fad  mov     qword ptr [rax+18h], 0
0x180012fb5  mov     qword ptr [rax+8], 0
0x180012fbd  jnz     short loc_180012FDA
0x180012fbf  lea     rdx, aNoToken; "No token"
0x180012fc6  mov     ecx, 8; int
0x180012fcb  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180012fd0  mov     ebx, 800703F0h
0x180012fd5  jmp     loc_180013086
0x180012fda  mov     r8d, edx; dwProcessId
0x180012fdd  xor     edx, edx; bInheritHandle
0x180012fdf  lea     ecx, [rdx+40h]; dwDesiredAccess
0x180012fe2  call    cs:__imp_OpenProcess
0x180012fe8  mov     rdx, rax
0x180012feb  lea     rcx, [rsp+48h+hTargetProcessHandle]
0x180012ff0  call    ??4SmartHANDLE@@QEAAXPEAX@Z; SmartHANDLE::operator=(void *)
0x180012ff5  mov     rbx, [rsp+48h+hTargetProcessHandle]
0x180012ffa  test    rbx, rbx
0x180012ffd  jnz     short loc_180013016
0x180012fff  call    cs:__imp_GetLastError
0x180013005  mov     ebx, eax
0x180013007  test    eax, eax
0x180013009  jle     short loc_180013086
0x18001300b  movzx   ebx, ax
0x18001300e  or      ebx, 80070000h
0x180013014  jmp     short loc_180013086
0x180013016  mov     rcx, [rdi+638h]; hExistingToken
0x18001301d  lea     rax, [rsp+48h+hSourceHandle]
0x180013022  mov     [rsp+48h+phNewToken], rax; phNewToken
0x180013027  mov     r9d, 2; ImpersonationLevel
0x18001302d  xor     r8d, r8d; lpTokenAttributes
0x180013030  mov     [rsp+48h+TokenType], 1; TokenType
0x180013038  mov     edx, 2000000h; dwDesiredAccess
0x18001303d  call    cs:__imp_DuplicateTokenEx
0x180013043  test    eax, eax
0x180013045  jz      short loc_180012FFF
0x180013047  mov     rdi, [rsp+48h+hSourceHandle]
0x18001304c  call    cs:__imp_GetCurrentProcess
0x180013052  mov     [rsp+48h+dwOptions], 3; dwOptions
0x18001305a  mov     r9, rsi; lpTargetHandle
0x18001305d  mov     rcx, rax; hSourceProcessHandle
0x180013060  mov     dword ptr [rsp+48h+phNewToken], 0; bInheritHandle
0x180013068  mov     r8, rbx; hTargetProcessHandle
0x18001306b  mov     [rsp+48h+TokenType], 0; dwDesiredAccess
0x180013073  mov     rdx, rdi; hSourceHandle
0x180013076  call    cs:__imp_DuplicateHandle
0x18001307c  test    eax, eax
0x18001307e  jz      loc_180012FFF
0x180013084  xor     ebx, ebx
0x180013086  lea     rcx, [rsp+48h+hTargetProcessHandle]; this
0x18001308b  call    ??1SmartHANDLE@@QEAA@XZ; SmartHANDLE::~SmartHANDLE(void)
0x180013090  mov     rsi, [rsp+48h+arg_18]
0x180013095  mov     eax, ebx
0x180013097  mov     rbx, [rsp+48h+arg_8]
0x18001309c  add     rsp, 40h
0x1800130a0  pop     rdi
0x1800130a1  retn
```
