# SxQueryDeviceTypeVirtualDiskSub(ushort const *,DF_DEVICE_TYPE *)

- ea: `0x1801aaac8`
- end: `0x1801aacc4`
- name: `?SxQueryDeviceTypeVirtualDiskSub@@YAJPEBGPEAW4DF_DEVICE_TYPE@@@Z`
- size: `508`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, enum DF_DEVICE_TYPE *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1801a9c4c`
- `0x1801aa5bc`

## callees

- `0x1801a9974`
- `0x1801aaac8`
- `0x1801ab4d0`
- `0x1801ab5c8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801aac80`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801aac80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801aab97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801aac6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801aab97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801aac6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801aab9f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801aab9f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801aab61`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801aab61`
- `VirtDisk!GetStorageDependencyInformation` at `0x1801aabd7`
- `VirtDisk!GetStorageDependencyInformation` at `0x1801aabd7`

## pseudocode

```c
__int64 __fastcall SxQueryDeviceTypeVirtualDiskSub(LPCWSTR lpFileName, enum DF_DEVICE_TYPE *a2)
{
  __int16 v4; // ax
  HANDLE FileW; // r14
  struct _STORAGE_DEPENDENCY_INFO *v6; // rdi
  ULONG v7; // ebx
  DWORD StorageDependencyInformation; // eax
  unsigned int v9; // ebx
  int v10; // r9d
  int v11; // r8d
  ULONG v12; // edx
  __int64 v13; // rcx
  int LastFailureAsHRESULT; // [rsp+40h] [rbp-19h] BYREF
  __int16 v16; // [rsp+44h] [rbp-15h]
  __int16 v17; // [rsp+46h] [rbp-13h]
  ULONG SizeUsed; // [rsp+C0h] [rbp+67h] BYREF

  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&LastFailureAsHRESULT,
    "SxQueryDeviceTypeVirtualDiskSub",
    0xB0u,
    1u);
  SizeUsed = 0;
  v4 = 188;
  if ( lpFileName && (v16 = 188, v4 = 189, a2) )
  {
    v16 = 189;
    LastFailureAsHRESULT = 0;
    *(_DWORD *)a2 = 8;
    FileW = CreateFileW(lpFileName, 0xC0000000, 3u, 0, 3u, 0, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT();
      v17 = 203;
      v9 = LastFailureAsHRESULT;
    }
    else
    {
      v6 = 0;
      LastFailureAsHRESULT = 0;
      v16 = 203;
      v7 = 100;
LABEL_5:
      StorageDependencyInformation = 122;
      while ( StorageDependencyInformation == 122 )
      {
        if ( v6 )
          CoTaskMemFree(v6);
        v6 = (struct _STORAGE_DEPENDENCY_INFO *)CoTaskMemAlloc(v7);
        if ( !v6 )
        {
          v9 = -2147024882;
          v17 = 222;
          LastFailureAsHRESULT = -2147024882;
          goto LABEL_29;
        }
        v16 = 222;
        LastFailureAsHRESULT = 0;
        *(_QWORD *)&v6->Version = 1;
        StorageDependencyInformation = GetStorageDependencyInformation(
                                         FileW,
                                         GET_STORAGE_DEPENDENCY_FLAG_DISK_HANDLE|GET_STORAGE_DEPENDENCY_FLAG_HOST_VOLUMES,
                                         v7,
                                         v6,
                                         &SizeUsed);
        if ( StorageDependencyInformation == 234 )
        {
          if ( SizeUsed > 0x48 )
          {
            v7 = 28 * v6->NumberEntries + 72;
            goto LABEL_5;
          }
        }
        else
        {
          if ( StorageDependencyInformation != 122 )
            break;
          v7 *= 2;
        }
      }
      if ( !StorageDependencyInformation )
      {
        v10 = 0;
        v11 = 0;
        v12 = 0;
        if ( v6->NumberEntries )
        {
          do
          {
            v13 = v12;
            if ( (v6->Version1Entries[v13].DependencyTypeFlags & 0x100) != 0 )
            {
              v10 = 1;
            }
            else if ( (v6->Version1Entries[v13].DependencyTypeFlags & 2) == 0 )
            {
              v11 = 1;
            }
            ++v12;
          }
          while ( v12 < v6->NumberEntries );
          if ( v10 )
          {
            *(_DWORD *)a2 = 9;
          }
          else if ( v11 )
          {
            *(_DWORD *)a2 = 10;
          }
        }
      }
      v9 = 0;
      LastFailureAsHRESULT = 0;
      v16 = 278;
      if ( v6 )
      {
        CoTaskMemFree(v6);
        v9 = LastFailureAsHRESULT;
      }
LABEL_29:
      if ( FileW )
        CloseHandle(FileW);
    }
  }
  else
  {
    v9 = -2147024809;
    v17 = v4;
    LastFailureAsHRESULT = -2147024809;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return v9;
}

```

## disassembly

```asm
0x1801aaac8  push    rbp
0x1801aaaca  push    rbx
0x1801aaacb  push    rsi
0x1801aaacc  push    rdi
0x1801aaacd  push    r13
0x1801aaacf  push    r14
0x1801aaad1  lea     rbp, [rsp-2Fh]
0x1801aaad6  sub     rsp, 88h
0x1801aaadd  mov     rsi, rdx
0x1801aaae0  mov     rbx, rcx
0x1801aaae3  mov     r13d, 1
0x1801aaae9  lea     rdx, aSxquerydevicet_0; "SxQueryDeviceTypeVirtualDiskSub"
0x1801aaaf0  mov     r9d, r13d; unsigned __int16
0x1801aaaf3  lea     rcx, [rbp+57h+var_70]; this
0x1801aaaf7  mov     r8d, 0B0h; unsigned __int16
0x1801aaafd  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1801aab02  mov     [rbp+57h+SizeUsed], 0
0x1801aab09  mov     eax, 0BCh
0x1801aab0e  test    rbx, rbx
0x1801aab11  jz      loc_1801AAC9D
0x1801aab17  mov     [rbp+57h+var_6C], ax
0x1801aab1b  mov     eax, 0BDh
0x1801aab20  test    rsi, rsi
0x1801aab23  jz      loc_1801AAC9D
0x1801aab29  mov     [rbp+57h+var_6C], ax
0x1801aab2d  xor     r9d, r9d; lpSecurityAttributes
0x1801aab30  lea     eax, [r13+2]
0x1801aab34  mov     [rsp+0B0h+hTemplateFile], 0; hTemplateFile
0x1801aab3d  mov     r8d, eax; dwShareMode
0x1801aab40  mov     [rsp+0B0h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1801aab48  mov     edx, 0C0000000h; dwDesiredAccess
0x1801aab4d  mov     [rbp+57h+var_70], 0
0x1801aab54  mov     rcx, rbx; lpFileName
0x1801aab57  mov     dword ptr [rsi], 8
0x1801aab5d  mov     [rsp+0B0h+dwCreationDisposition], eax; dwCreationDisposition
0x1801aab61  call    cs:__imp_CreateFileW
0x1801aab67  mov     r14, rax
0x1801aab6a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801aab6e  jz      loc_1801AAC88
0x1801aab74  xor     edi, edi
0x1801aab76  mov     ecx, 0CBh
0x1801aab7b  mov     [rbp+57h+var_70], edi
0x1801aab7e  mov     [rbp+57h+var_6C], cx
0x1801aab82  lea     ebx, [rdi+64h]
0x1801aab85  mov     eax, 7Ah ; 'z'
0x1801aab8a  cmp     eax, 7Ah ; 'z'
0x1801aab8d  jnz     short loc_1801AAC0A
0x1801aab8f  test    rdi, rdi
0x1801aab92  jz      short loc_1801AAB9D
0x1801aab94  mov     rcx, rdi; pv
0x1801aab97  call    cs:__imp_CoTaskMemFree
0x1801aab9d  mov     ecx, ebx; cb
0x1801aab9f  call    cs:__imp_CoTaskMemAlloc
0x1801aaba5  mov     rdi, rax
0x1801aaba8  test    rax, rax
0x1801aabab  mov     eax, 0DEh
0x1801aabb0  jz      short loc_1801AABFC
0x1801aabb2  mov     [rbp+57h+var_6C], ax
0x1801aabb6  mov     r9, rdi; StorageDependencyInfo
0x1801aabb9  lea     rax, [rbp+57h+SizeUsed]
0x1801aabbd  mov     [rbp+57h+var_70], 0
0x1801aabc4  mov     r8d, ebx; StorageDependencyInfoSize
0x1801aabc7  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax; SizeUsed
0x1801aabcc  mov     edx, 3; Flags
0x1801aabd1  mov     [rdi], r13
0x1801aabd4  mov     rcx, r14; ObjectHandle
0x1801aabd7  call    cs:__imp_GetStorageDependencyInformation
0x1801aabdd  cmp     eax, 0EAh
0x1801aabe2  jnz     short loc_1801AABF3
0x1801aabe4  cmp     [rbp+57h+SizeUsed], 48h ; 'H'
0x1801aabe8  jbe     short loc_1801AAB8A
0x1801aabea  imul    ebx, [rdi+4], 1Ch
0x1801aabee  add     ebx, 48h ; 'H'
0x1801aabf1  jmp     short loc_1801AAB85
0x1801aabf3  cmp     eax, 7Ah ; 'z'
0x1801aabf6  jnz     short loc_1801AAC0A
0x1801aabf8  add     ebx, ebx
0x1801aabfa  jmp     short loc_1801AAB8A
0x1801aabfc  mov     ebx, 8007000Eh
0x1801aac01  mov     [rbp+57h+var_6A], ax
0x1801aac05  mov     [rbp+57h+var_70], ebx
0x1801aac08  jmp     short loc_1801AAC78
0x1801aac0a  test    eax, eax
0x1801aac0c  jnz     short loc_1801AAC59
0x1801aac0e  xor     r9d, r9d
0x1801aac11  xor     r8d, r8d
0x1801aac14  xor     edx, edx
0x1801aac16  cmp     [rdi+4], edx
0x1801aac19  jbe     short loc_1801AAC59
0x1801aac1b  mov     eax, edx
0x1801aac1d  imul    rcx, rax, 1Ch
0x1801aac21  test    dword ptr [rcx+rdi+8], 100h
0x1801aac29  jz      short loc_1801AAC30
0x1801aac2b  mov     r9d, r13d
0x1801aac2e  jmp     short loc_1801AAC39
0x1801aac30  test    byte ptr [rcx+rdi+8], 2
0x1801aac35  cmovz   r8d, r13d
0x1801aac39  add     edx, r13d
0x1801aac3c  cmp     edx, [rdi+4]
0x1801aac3f  jb      short loc_1801AAC1B
0x1801aac41  test    r9d, r9d
0x1801aac44  jz      short loc_1801AAC4E
0x1801aac46  mov     dword ptr [rsi], 9
0x1801aac4c  jmp     short loc_1801AAC59
0x1801aac4e  test    r8d, r8d
0x1801aac51  jz      short loc_1801AAC59
0x1801aac53  mov     dword ptr [rsi], 0Ah
0x1801aac59  xor     ebx, ebx
0x1801aac5b  mov     eax, 116h
0x1801aac60  mov     [rbp+57h+var_70], ebx
0x1801aac63  mov     [rbp+57h+var_6C], ax
0x1801aac67  test    rdi, rdi
0x1801aac6a  jz      short loc_1801AAC78
0x1801aac6c  mov     rcx, rdi; pv
0x1801aac6f  call    cs:__imp_CoTaskMemFree
0x1801aac75  mov     ebx, [rbp+57h+var_70]
0x1801aac78  test    r14, r14
0x1801aac7b  jz      short loc_1801AACA9
0x1801aac7d  mov     rcx, r14; hObject
0x1801aac80  call    cs:__imp_CloseHandle
0x1801aac86  jmp     short loc_1801AACA9
0x1801aac88  call    GetLastFailureAsHRESULT
0x1801aac8d  mov     ecx, 0CBh
0x1801aac92  mov     [rbp+57h+var_70], eax
0x1801aac95  mov     [rbp+57h+var_6A], cx
0x1801aac99  mov     ebx, eax
0x1801aac9b  jmp     short loc_1801AACA9
0x1801aac9d  mov     ebx, 80070057h
0x1801aaca2  mov     [rbp+57h+var_6A], ax
0x1801aaca6  mov     [rbp+57h+var_70], ebx
0x1801aaca9  lea     rcx, [rbp+57h+var_70]; this
0x1801aacad  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1801aacb2  mov     eax, ebx
0x1801aacb4  add     rsp, 88h
0x1801aacbb  pop     r14
0x1801aacbd  pop     r13
0x1801aacbf  pop     rdi
0x1801aacc0  pop     rsi
0x1801aacc1  pop     rbx
0x1801aacc2  pop     rbp
0x1801aacc3  retn
```
