# EnterpriseWorkerThread::GetInstalledXAPFileSize(_GUID)

- ea: `0x180016254`
- end: `0x180016359`
- name: `?GetInstalledXAPFileSize@EnterpriseWorkerThread@@QEAAKU_GUID@@@Z`
- size: `261`
- prototype: `unsigned int __fastcall(EnterpriseWorkerThread *__hidden this, struct _GUID *__struct_ptr)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, installer_update`

## callers

- `0x18001735c`

## callees

- `0x180016254`
- `0x18001c550`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180016335`
- `OLEAUT32!__imp_SysFreeString` at `0x180016335`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001630d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001630d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016326`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016326`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001627a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001627a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800162e2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800162e2`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800162fc`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800162fc`

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
0x180016254  mov     [rsp+arg_8], rbx
0x180016259  mov     [rsp+arg_10], rbp
0x18001625e  push    rsi
0x18001625f  push    rdi
0x180016260  push    r14
0x180016262  sub     rsp, 50h
0x180016266  mov     r14, rdx
0x180016269  mov     rdi, rcx
0x18001626c  xor     ebx, ebx
0x18001626e  mov     [rsp+68h+lpFileName], rbx
0x180016273  lea     rbp, [rcx+58h]
0x180016277  mov     rcx, rbp; lpCriticalSection
0x18001627a  call    cs:__imp_EnterCriticalSection
0x180016281  nop     dword ptr [rax+rax+00h]
0x180016286  xor     esi, esi
0x180016288  cmp     [rdi+80h], ebx
0x18001628e  jz      loc_180016320
0x180016294  movaps  xmm0, xmmword ptr [r14]
0x180016298  movdqa  [rsp+68h+var_28], xmm0
0x18001629e  lea     r8d, [rbx+6]
0x1800162a2  lea     r9, [rsp+68h+lpFileName]
0x1800162a7  lea     rdx, [rsp+68h+var_28]
0x1800162ac  lea     ebx, [rsi+1]
0x1800162af  mov     ecx, ebx
0x1800162b1  call    ?RetrieveBSTR@EnrollmentManager@@SAJW4TABLEID@@U_GUID@@GPEAPEAG@Z; EnrollmentManager::RetrieveBSTR(TABLEID,_GUID,ushort,ushort * *)
0x1800162b6  test    eax, eax
0x1800162b8  jnz     short loc_18001631B
0x1800162ba  mov     [rsp+68h+hTemplateFile], rsi; hTemplateFile
0x1800162bf  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800162c7  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x1800162cf  xor     r9d, r9d; lpSecurityAttributes
0x1800162d2  mov     r8d, ebx; dwShareMode
0x1800162d5  mov     edx, 80000000h; dwDesiredAccess
0x1800162da  mov     rbx, [rsp+68h+lpFileName]
0x1800162df  mov     rcx, rbx; lpFileName
0x1800162e2  call    cs:__imp_CreateFileW
0x1800162e9  nop     dword ptr [rax+rax+00h]
0x1800162ee  mov     rdi, rax
0x1800162f1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800162f5  jz      short loc_180016320
0x1800162f7  xor     edx, edx; lpFileSizeHigh
0x1800162f9  mov     rcx, rax; hFile
0x1800162fc  call    cs:__imp_GetFileSize
0x180016303  nop     dword ptr [rax+rax+00h]
0x180016308  mov     esi, eax
0x18001630a  mov     rcx, rdi; hObject
0x18001630d  call    cs:__imp_CloseHandle
0x180016314  nop     dword ptr [rax+rax+00h]
0x180016319  jmp     short loc_180016320
0x18001631b  mov     rbx, [rsp+68h+lpFileName]
0x180016320  shr     esi, 0Ah
0x180016323  mov     rcx, rbp; lpCriticalSection
0x180016326  call    cs:__imp_LeaveCriticalSection
0x18001632d  nop     dword ptr [rax+rax+00h]
0x180016332  mov     rcx, rbx; bstrString
0x180016335  call    cs:__imp_SysFreeString
0x18001633c  nop     dword ptr [rax+rax+00h]
0x180016341  mov     eax, esi
0x180016343  lea     r11, [rsp+68h+var_18]
0x180016348  mov     rbx, [r11+28h]
0x18001634c  mov     rbp, [r11+30h]
0x180016350  mov     rsp, r11
0x180016353  pop     r14
0x180016355  pop     rdi
0x180016356  pop     rsi
0x180016357  retn
```
