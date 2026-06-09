# CBrowserBrokerInstance::OpenMigrationFile(migration_broker_file_id,int *)

- ea: `0x18000b280`
- end: `0x18000b3cf`
- name: `?OpenMigrationFile@CBrowserBrokerInstance@@UEAAJW4migration_broker_file_id@@PEAH@Z`
- size: `335`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x18000b280`
- `0x18000e428`
- `0x18001f064`
- `0x18001f16c`
- `0x18001f30c`
- `0x18001f40c`
- `0x18001f5b4`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b396`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b39f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b396`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b39f`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000b36c`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000b36c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b37d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b3a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b37d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b3a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000b346`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000b346`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000b2c5`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000b2c5`

## pseudocode

```c
__int64 __fastcall CBrowserBrokerInstance::OpenMigrationFile(__int64 a1, int a2, _DWORD *a3)
{
  int PIC; // ebx
  HANDLE v7; // r14
  int v8; // edi
  int v9; // edi
  int v10; // edi
  int v11; // eax
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  signed int v14; // eax
  HANDLE hSourceHandle; // [rsp+80h] [rbp+40h] BYREF
  HANDLE TargetHandle; // [rsp+88h] [rbp+48h] BYREF

  *a3 = 0;
  LODWORD(hSourceHandle) = 0;
  PIC = BrokerAuthenticateAttachedCallerGetPIC(1, (unsigned int *)&hSourceHandle);
  if ( PIC >= 0 )
  {
    v7 = OpenProcess(0x40u, 0, *(_DWORD *)(a1 + 32));
    if ( v7 )
    {
      if ( a2 )
      {
        v8 = a2 - 1;
        if ( v8 )
        {
          v9 = v8 - 1;
          if ( v9 )
          {
            v10 = v9 - 1;
            if ( v10 )
            {
              if ( v10 != 1 )
              {
LABEL_19:
                CloseHandle(v7);
                return (unsigned int)PIC;
              }
              hSourceHandle = 0;
              v11 = OpenQQBrowserBookmarksFile(&hSourceHandle);
            }
            else
            {
              hSourceHandle = 0;
              v11 = OpenQihoo360SEBookmarksFile(&hSourceHandle);
            }
          }
          else
          {
            hSourceHandle = 0;
            v11 = OpenFirefoxBookmarksFile(&hSourceHandle);
          }
        }
        else
        {
          hSourceHandle = 0;
          v11 = OpenChromeBookmarksFile(&hSourceHandle);
        }
      }
      else
      {
        hSourceHandle = 0;
        v11 = OpenFavIconsImagestore(&hSourceHandle);
      }
      PIC = v11;
      if ( v11 >= 0 )
      {
        TargetHandle = 0;
        CurrentProcess = GetCurrentProcess();
        if ( DuplicateHandle(CurrentProcess, hSourceHandle, v7, &TargetHandle, 0, 0, 2u) )
        {
          *a3 = (_DWORD)TargetHandle;
        }
        else
        {
          LastError = GetLastError();
          PIC = LastError;
          if ( LastError > 0 )
            PIC = (unsigned __int16)LastError | 0x80070000;
        }
        CloseHandle(hSourceHandle);
      }
      goto LABEL_19;
    }
    v14 = GetLastError();
    PIC = v14;
    if ( v14 > 0 )
      return (unsigned __int16)v14 | 0x80070000;
  }
  return (unsigned int)PIC;
}

```

## disassembly

```asm
0x18000b280  mov     [rsp-28h+arg_0], rbx
0x18000b285  push    rbp
0x18000b286  push    rsi
0x18000b287  push    rdi
0x18000b288  push    r14
0x18000b28a  push    r15
0x18000b28c  mov     rbp, rsp
0x18000b28f  sub     rsp, 40h
0x18000b293  xor     r15d, r15d
0x18000b296  mov     edi, edx
0x18000b298  mov     r14, rcx
0x18000b29b  mov     [r8], r15d
0x18000b29e  lea     rdx, [rbp+hSourceHandle]; unsigned int *
0x18000b2a2  mov     dword ptr [rbp+hSourceHandle], r15d
0x18000b2a6  mov     rsi, r8
0x18000b2a9  lea     ecx, [r15+1]; unsigned int
0x18000b2ad  call    ?BrokerAuthenticateAttachedCallerGetPIC@@YAJKPEAK@Z; BrokerAuthenticateAttachedCallerGetPIC(ulong,ulong *)
0x18000b2b2  mov     ebx, eax
0x18000b2b4  test    eax, eax
0x18000b2b6  js      loc_18000B3BC
0x18000b2bc  mov     r8d, [r14+20h]; dwProcessId
0x18000b2c0  xor     edx, edx; bInheritHandle
0x18000b2c2  lea     ecx, [rdx+40h]; dwDesiredAccess
0x18000b2c5  call    cs:__imp_OpenProcess
0x18000b2cb  mov     r14, rax
0x18000b2ce  test    rax, rax
0x18000b2d1  jz      loc_18000B3A7
0x18000b2d7  test    edi, edi
0x18000b2d9  jz      short loc_18000B32F
0x18000b2db  sub     edi, 1
0x18000b2de  jz      short loc_18000B320
0x18000b2e0  sub     edi, 1
0x18000b2e3  jz      short loc_18000B311
0x18000b2e5  sub     edi, 1
0x18000b2e8  jz      short loc_18000B302
0x18000b2ea  cmp     edi, 1
0x18000b2ed  jnz     loc_18000B39C
0x18000b2f3  lea     rcx, [rbp+hSourceHandle]; void **
0x18000b2f7  mov     [rbp+hSourceHandle], r15
0x18000b2fb  call    ?OpenQQBrowserBookmarksFile@@YAJPEAPEAX@Z; OpenQQBrowserBookmarksFile(void * *)
0x18000b300  jmp     short loc_18000B33C
0x18000b302  lea     rcx, [rbp+hSourceHandle]; void **
0x18000b306  mov     [rbp+hSourceHandle], r15
0x18000b30a  call    ?OpenQihoo360SEBookmarksFile@@YAJPEAPEAX@Z; OpenQihoo360SEBookmarksFile(void * *)
0x18000b30f  jmp     short loc_18000B33C
0x18000b311  lea     rcx, [rbp+hSourceHandle]; void **
0x18000b315  mov     [rbp+hSourceHandle], r15
0x18000b319  call    ?OpenFirefoxBookmarksFile@@YAJPEAPEAX@Z; OpenFirefoxBookmarksFile(void * *)
0x18000b31e  jmp     short loc_18000B33C
0x18000b320  lea     rcx, [rbp+hSourceHandle]; void **
0x18000b324  mov     [rbp+hSourceHandle], r15
0x18000b328  call    ?OpenChromeBookmarksFile@@YAJPEAPEAX@Z; OpenChromeBookmarksFile(void * *)
0x18000b32d  jmp     short loc_18000B33C
0x18000b32f  lea     rcx, [rbp+hSourceHandle]; void **
0x18000b333  mov     [rbp+hSourceHandle], r15
0x18000b337  call    ?OpenFavIconsImagestore@@YAJPEAPEAX@Z; OpenFavIconsImagestore(void * *)
0x18000b33c  mov     ebx, eax
0x18000b33e  test    eax, eax
0x18000b340  js      short loc_18000B39C
0x18000b342  mov     [rbp+TargetHandle], r15
0x18000b346  call    cs:__imp_GetCurrentProcess
0x18000b34c  mov     rdx, [rbp+hSourceHandle]; hSourceHandle
0x18000b350  lea     r9, [rbp+TargetHandle]; lpTargetHandle
0x18000b354  mov     [rsp+40h+dwOptions], 2; dwOptions
0x18000b35c  mov     rcx, rax; hSourceProcessHandle
0x18000b35f  mov     [rsp+40h+bInheritHandle], r15d; bInheritHandle
0x18000b364  mov     r8, r14; hTargetProcessHandle
0x18000b367  mov     [rsp+40h+dwDesiredAccess], r15d; dwDesiredAccess
0x18000b36c  call    cs:__imp_DuplicateHandle
0x18000b372  test    eax, eax
0x18000b374  jz      short loc_18000B37D
0x18000b376  mov     eax, dword ptr [rbp+TargetHandle]
0x18000b379  mov     [rsi], eax
0x18000b37b  jmp     short loc_18000B392
0x18000b37d  call    cs:__imp_GetLastError
0x18000b383  mov     ebx, eax
0x18000b385  test    eax, eax
0x18000b387  jle     short loc_18000B392
0x18000b389  movzx   ebx, ax
0x18000b38c  or      ebx, 80070000h
0x18000b392  mov     rcx, [rbp+hSourceHandle]; hObject
0x18000b396  call    cs:__imp_CloseHandle
0x18000b39c  mov     rcx, r14; hObject
0x18000b39f  call    cs:__imp_CloseHandle
0x18000b3a5  jmp     short loc_18000B3BC
0x18000b3a7  call    cs:__imp_GetLastError
0x18000b3ad  mov     ebx, eax
0x18000b3af  test    eax, eax
0x18000b3b1  jle     short loc_18000B3BC
0x18000b3b3  movzx   ebx, ax
0x18000b3b6  or      ebx, 80070000h
0x18000b3bc  mov     eax, ebx
0x18000b3be  mov     rbx, [rsp+40h+arg_0]
0x18000b3c3  add     rsp, 40h
0x18000b3c7  pop     r15
0x18000b3c9  pop     r14
0x18000b3cb  pop     rdi
0x18000b3cc  pop     rsi
0x18000b3cd  pop     rbp
0x18000b3ce  retn
```
