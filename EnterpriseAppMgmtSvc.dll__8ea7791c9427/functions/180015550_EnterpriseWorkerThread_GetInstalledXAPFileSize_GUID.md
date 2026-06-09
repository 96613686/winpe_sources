# EnterpriseWorkerThread::GetInstalledXAPFileSize(_GUID)

- ea: `0x180015550`
- end: `0x18001562c`
- name: `?GetInstalledXAPFileSize@EnterpriseWorkerThread@@QEAAKU_GUID@@@Z`
- size: `220`
- prototype: `unsigned int __fastcall(EnterpriseWorkerThread *__hidden this, struct _GUID *__struct_ptr)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, installer_update`

## callers

- `0x1800165b8`

## callees

- `0x180015550`
- `0x18001b210`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18001560f`
- `OLEAUT32!__imp_SysFreeString` at `0x18001560f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800155f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800155f3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015606`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015606`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015576`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015576`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800155d4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800155d4`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800155e8`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800155e8`

## pseudocode

```c
__int64 __fastcall EnterpriseWorkerThread::GetInstalledXAPFileSize(EnterpriseWorkerThread *this, struct _GUID *a2)
{
  OLECHAR *v4; // rbx
  struct _RTL_CRITICAL_SECTION *v5; // rbp
  DWORD FileSize; // esi
  HANDLE FileW; // rax
  void *v8; // rdi
  __int128 v10; // [rsp+40h] [rbp-28h] BYREF
  LPCWSTR lpFileName; // [rsp+70h] [rbp+8h] BYREF

  v4 = 0;
  lpFileName = 0;
  v5 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 88);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  FileSize = 0;
  if ( *((_DWORD *)this + 32) )
  {
    v10 = (__int128)*a2;
    if ( (unsigned int)EnrollmentManager::RetrieveBSTR(1, &v10, 6, &lpFileName) )
    {
      v4 = (OLECHAR *)lpFileName;
    }
    else
    {
      v4 = (OLECHAR *)lpFileName;
      FileW = CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0x80u, 0);
      v8 = FileW;
      if ( FileW != (HANDLE)-1LL )
      {
        FileSize = GetFileSize(FileW, 0);
        CloseHandle(v8);
      }
    }
  }
  LeaveCriticalSection(v5);
  SysFreeString(v4);
  return FileSize >> 10;
}

```

## disassembly

```asm
0x180015550  mov     [rsp+arg_8], rbx
0x180015555  mov     [rsp+arg_10], rbp
0x18001555a  push    rsi
0x18001555b  push    rdi
0x18001555c  push    r14
0x18001555e  sub     rsp, 50h
0x180015562  mov     r14, rdx
0x180015565  mov     rdi, rcx
0x180015568  xor     ebx, ebx
0x18001556a  mov     [rsp+68h+lpFileName], rbx
0x18001556f  lea     rbp, [rcx+58h]
0x180015573  mov     rcx, rbp; lpCriticalSection
0x180015576  call    cs:__imp_EnterCriticalSection
0x18001557c  xor     esi, esi
0x18001557e  cmp     [rdi+80h], ebx
0x180015584  jz      short loc_180015600
0x180015586  movaps  xmm0, xmmword ptr [r14]
0x18001558a  movdqa  [rsp+68h+var_28], xmm0
0x180015590  lea     r8d, [rbx+6]
0x180015594  lea     r9, [rsp+68h+lpFileName]
0x180015599  lea     rdx, [rsp+68h+var_28]
0x18001559e  lea     ebx, [rsi+1]
0x1800155a1  mov     ecx, ebx
0x1800155a3  call    ?RetrieveBSTR@EnrollmentManager@@SAJW4TABLEID@@U_GUID@@GPEAPEAG@Z; EnrollmentManager::RetrieveBSTR(TABLEID,_GUID,ushort,ushort * *)
0x1800155a8  test    eax, eax
0x1800155aa  jnz     short loc_1800155FB
0x1800155ac  mov     [rsp+68h+hTemplateFile], rsi; hTemplateFile
0x1800155b1  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800155b9  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x1800155c1  xor     r9d, r9d; lpSecurityAttributes
0x1800155c4  mov     r8d, ebx; dwShareMode
0x1800155c7  mov     edx, 80000000h; dwDesiredAccess
0x1800155cc  mov     rbx, [rsp+68h+lpFileName]
0x1800155d1  mov     rcx, rbx; lpFileName
0x1800155d4  call    cs:__imp_CreateFileW
0x1800155da  mov     rdi, rax
0x1800155dd  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800155e1  jz      short loc_180015600
0x1800155e3  xor     edx, edx; lpFileSizeHigh
0x1800155e5  mov     rcx, rax; hFile
0x1800155e8  call    cs:__imp_GetFileSize
0x1800155ee  mov     esi, eax
0x1800155f0  mov     rcx, rdi; hObject
0x1800155f3  call    cs:__imp_CloseHandle
0x1800155f9  jmp     short loc_180015600
0x1800155fb  mov     rbx, [rsp+68h+lpFileName]
0x180015600  shr     esi, 0Ah
0x180015603  mov     rcx, rbp; lpCriticalSection
0x180015606  call    cs:__imp_LeaveCriticalSection
0x18001560c  mov     rcx, rbx; bstrString
0x18001560f  call    cs:__imp_SysFreeString
0x180015615  mov     eax, esi
0x180015617  lea     r11, [rsp+68h+var_18]
0x18001561c  mov     rbx, [r11+28h]
0x180015620  mov     rbp, [r11+30h]
0x180015624  mov     rsp, r11
0x180015627  pop     r14
0x180015629  pop     rdi
0x18001562a  pop     rsi
0x18001562b  retn
```
