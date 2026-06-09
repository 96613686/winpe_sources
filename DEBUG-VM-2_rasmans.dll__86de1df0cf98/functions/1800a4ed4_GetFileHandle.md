# GetFileHandle

- ea: `0x1800a4ed4`
- end: `0x1800a524e`
- name: `GetFileHandle`
- size: `890`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800a52cc`
- `0x1800a57a0`

## callees

- `0x180002294`
- `0x18000e564`
- `0x1800a442c`
- `0x1800a4ed4`
- `0x1800e7260`

## import_xrefs

- `msvcrt!wcschr` at `0x1800a50de`
- `msvcrt!wcschr` at `0x1800a50de`
- `ntdll!NtCreateFile` at `0x1800a50c9`
- `ntdll!NtCreateFile` at `0x1800a50c9`
- `ntdll!RtlFreeHeap` at `0x1800a51b1`
- `ntdll!RtlFreeHeap` at `0x1800a51d3`
- `ntdll!RtlFreeHeap` at `0x1800a51b1`
- `ntdll!RtlFreeHeap` at `0x1800a51d3`
- `ntdll!NtClose` at `0x1800a518a`
- `ntdll!NtClose` at `0x1800a518a`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800a5044`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800a5153`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800a5044`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800a5153`
- `ntdll!RtlInitUnicodeString` at `0x1800a5059`
- `ntdll!RtlInitUnicodeString` at `0x1800a5059`
- `RPCRT4!UuidCreate` at `0x1800a4f52`
- `RPCRT4!UuidCreate` at `0x1800a4f52`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a51ec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a5205`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a521e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a51ec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a5205`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a521e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a4f9c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a4fca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a510f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a51de`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a51f7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a5210`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a4f9c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a4fca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a510f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a51de`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a51f7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a5210`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a4fad`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a4fdb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a5120`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a4fad`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a4fdb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a5120`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800a50fb`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800a513c`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800a50fb`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800a513c`

## pseudocode

```c
__int64 __fastcall GetFileHandle(__int64 a1, void *a2)
{
  __int64 v3; // rdi
  wchar_t *v4; // r13
  WCHAR *v5; // r12
  __int64 v6; // r14
  __int64 v7; // r15
  HANDLE ProcessHeap; // rax
  WCHAR *v9; // rsi
  unsigned __int64 v10; // r14
  HANDLE v11; // rax
  DWORD v12; // r15d
  DWORD FinalPathNameByHandleW; // eax
  DWORD v14; // r14d
  SIZE_T v15; // rbx
  HANDLE v16; // rax
  WCHAR *v17; // rax
  HANDLE v18; // rax
  HANDLE v19; // rax
  HANDLE v20; // rax
  void *FileHandle; // [rsp+60h] [rbp-A0h] BYREF
  PVOID P; // [rsp+68h] [rbp-98h]
  PVOID Buffer; // [rsp+70h] [rbp-90h]
  __int64 v25; // [rsp+78h] [rbp-88h]
  unsigned __int64 v26; // [rsp+80h] [rbp-80h]
  void *v27; // [rsp+88h] [rbp-78h]
  struct _UNICODE_STRING NtPathName; // [rsp+90h] [rbp-70h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp-60h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+D0h] [rbp-30h] BYREF
  struct _UNICODE_STRING v31; // [rsp+E0h] [rbp-20h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+F0h] [rbp-10h] BYREF
  UUID Uuid; // [rsp+100h] [rbp+0h] BYREF
  _WORD v34[40]; // [rsp+110h] [rbp+10h] BYREF

  v25 = a1;
  v27 = a2;
  P = 0;
  Buffer = 0;
  v3 = -1;
  FileHandle = (void *)-1LL;
  v4 = 0;
  v5 = 0;
  NtPathName = 0;
  v31 = 0;
  DestinationString = 0;
  Uuid = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( UuidCreate(&Uuid) < 0 )
  {
    v9 = 0;
  }
  else
  {
    ConvertGuid2String(&Uuid, 39, v34);
    v6 = -1;
    do
      ++v6;
    while ( v34[v6] );
    v7 = -1;
    do
      ++v7;
    while ( *(_WORD *)(a1 + 2 * v7) );
    v26 = v6 + 1;
    ProcessHeap = GetProcessHeap();
    v9 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, 2 * (v6 + 1));
    if ( v9 )
    {
      v10 = v7 + v6 + 2;
      v11 = GetProcessHeap();
      v4 = (wchar_t *)HeapAlloc(v11, 8u, 2 * v10);
      if ( v4 )
      {
        if ( (int)StringCchPrintfW(v4, v10, L"%s\\%s", v25, v34) >= 0
          && (int)StringCchPrintfW(v9, v26, L"%s", v34) >= 0
          && RtlDosPathNameToNtPathName_U(v4, &NtPathName, 0, 0) )
        {
          RtlInitUnicodeString(&DestinationString, v9);
          P = NtPathName.Buffer;
          ObjectAttributes.RootDirectory = v27;
          ObjectAttributes.Attributes = 4160;
          ObjectAttributes.ObjectName = &DestinationString;
          ObjectAttributes.Length = 48;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          if ( NtCreateFile(&FileHandle, 0x10001u, &ObjectAttributes, &IoStatusBlock, 0, 0x82u, 0, 2u, 0x1040u, 0, 0) < 0 )
            goto LABEL_21;
          v12 = wcschr(v4, 0x3Au) == 0;
          FinalPathNameByHandleW = GetFinalPathNameByHandleW(FileHandle, 0, 0, v12);
          if ( FinalPathNameByHandleW )
          {
            v14 = FinalPathNameByHandleW + 1;
            v15 = 2LL * (FinalPathNameByHandleW + 1);
            v16 = GetProcessHeap();
            v17 = (WCHAR *)HeapAlloc(v16, 8u, v15);
            v5 = v17;
            if ( v17 )
            {
              if ( GetFinalPathNameByHandleW(FileHandle, v17, v14, v12) )
              {
                if ( RtlDosPathNameToNtPathName_U(v5, &v31, 0, 0) )
                {
                  Buffer = v31.Buffer;
                  if ( !wcsicmp_0(NtPathName.Buffer, v31.Buffer) )
                  {
                    v3 = (__int64)FileHandle;
                    goto LABEL_22;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  if ( FileHandle == (void *)-1LL )
    goto LABEL_22;
  NtClose(FileHandle);
LABEL_21:
  FileHandle = (void *)-1LL;
LABEL_22:
  if ( P )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  if ( Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
  if ( v4 )
  {
    v18 = GetProcessHeap();
    HeapFree(v18, 0, v4);
  }
  if ( v5 )
  {
    v19 = GetProcessHeap();
    HeapFree(v19, 0, v5);
  }
  if ( v9 )
  {
    v20 = GetProcessHeap();
    HeapFree(v20, 0, v9);
  }
  return v3;
}

```

## disassembly

```asm
0x1800a4ed4  mov     [rsp-8+arg_10], rbx
0x1800a4ed9  push    rbp
0x1800a4eda  push    rsi
0x1800a4edb  push    rdi
0x1800a4edc  push    r12
0x1800a4ede  push    r13
0x1800a4ee0  push    r14
0x1800a4ee2  push    r15
0x1800a4ee4  lea     rbp, [rsp-70h]
0x1800a4ee9  sub     rsp, 170h
0x1800a4ef0  mov     rax, cs:__security_cookie
0x1800a4ef7  xor     rax, rsp
0x1800a4efa  mov     [rbp+0A0h+var_40], rax
0x1800a4efe  xorps   xmm0, xmm0
0x1800a4f01  mov     [rsp+1A0h+var_128], rcx
0x1800a4f06  xor     r14d, r14d
0x1800a4f09  mov     [rbp+0A0h+var_118], rdx
0x1800a4f0d  xorps   xmm1, xmm1
0x1800a4f10  mov     [rsp+1A0h+P], r14
0x1800a4f15  mov     rbx, rcx
0x1800a4f18  mov     [rsp+1A0h+var_130], r14
0x1800a4f1d  movups  xmmword ptr [rbp+0A0h+ObjectAttributes.ObjectName], xmm0
0x1800a4f21  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800a4f25  lea     rcx, [rbp+0A0h+Uuid]; Uuid
0x1800a4f29  xor     eax, eax
0x1800a4f2b  mov     [rsp+1A0h+FileHandle], rdi
0x1800a4f30  movups  xmmword ptr [rbp+0A0h+ObjectAttributes+1Ch], xmm0
0x1800a4f34  mov     r13d, r14d
0x1800a4f37  mov     r12d, r14d
0x1800a4f3a  movups  xmmword ptr [rbp+0A0h+NtPathName.Length], xmm0
0x1800a4f3e  movups  xmmword ptr [rbp+0A0h+var_C0.Length], xmm1
0x1800a4f42  movups  xmmword ptr [rbp+0A0h+DestinationString.Length], xmm0
0x1800a4f46  movups  xmmword ptr [rbp+0A0h+Uuid.Data1], xmm1
0x1800a4f4a  movups  xmmword ptr [rbp+0A0h+IoStatusBlock], xmm0
0x1800a4f4e  movups  xmmword ptr [rbp+0A0h+ObjectAttributes.Length], xmm0
0x1800a4f52  call    cs:__imp_UuidCreate
0x1800a4f58  test    eax, eax
0x1800a4f5a  js      loc_1800A517D
0x1800a4f60  lea     r8, [rbp+0A0h+var_90]
0x1800a4f64  lea     edx, [rdi+28h]
0x1800a4f67  lea     rcx, [rbp+0A0h+Uuid]
0x1800a4f6b  call    ConvertGuid2String
0x1800a4f70  lea     rcx, [rbp+0A0h+var_90]
0x1800a4f74  xor     eax, eax
0x1800a4f76  mov     r14, rdi
0x1800a4f79  inc     r14
0x1800a4f7c  cmp     [rcx+r14*2], ax
0x1800a4f81  jnz     short loc_1800A4F79
0x1800a4f83  mov     r15, rdi
0x1800a4f86  inc     r15
0x1800a4f89  cmp     [rbx+r15*2], ax
0x1800a4f8e  jnz     short loc_1800A4F86
0x1800a4f90  lea     rax, [r14+1]
0x1800a4f94  mov     [rbp+0A0h+var_120], rax
0x1800a4f98  lea     rbx, [rax+rax]
0x1800a4f9c  call    cs:__imp_GetProcessHeap
0x1800a4fa2  mov     r8, rbx; dwBytes
0x1800a4fa5  mov     edx, 8; dwFlags
0x1800a4faa  mov     rcx, rax; hHeap
0x1800a4fad  call    cs:__imp_HeapAlloc
0x1800a4fb3  mov     rsi, rax
0x1800a4fb6  test    rax, rax
0x1800a4fb9  jz      loc_1800A5180
0x1800a4fbf  add     r14, 2
0x1800a4fc3  add     r14, r15
0x1800a4fc6  lea     rbx, [r14+r14]
0x1800a4fca  call    cs:__imp_GetProcessHeap
0x1800a4fd0  mov     r8, rbx; dwBytes
0x1800a4fd3  mov     edx, 8; dwFlags
0x1800a4fd8  mov     rcx, rax; hHeap
0x1800a4fdb  call    cs:__imp_HeapAlloc
0x1800a4fe1  mov     r13, rax
0x1800a4fe4  test    rax, rax
0x1800a4fe7  jz      loc_1800A5180
0x1800a4fed  mov     r9, [rsp+1A0h+var_128]
0x1800a4ff2  lea     rax, [rbp+0A0h+var_90]
0x1800a4ff6  lea     r8, aSS_2; "%s\\%s"
0x1800a4ffd  mov     [rsp+1A0h+AllocationSize], rax
0x1800a5002  mov     rdx, r14; unsigned __int64
0x1800a5005  mov     rcx, r13; unsigned __int16 *
0x1800a5008  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a500d  xor     r14d, r14d
0x1800a5010  test    eax, eax
0x1800a5012  js      loc_1800A5180
0x1800a5018  mov     rdx, [rbp+0A0h+var_120]; unsigned __int64
0x1800a501c  lea     r9, [rbp+0A0h+var_90]
0x1800a5020  lea     r8, aS; "%s"
0x1800a5027  mov     rcx, rsi; unsigned __int16 *
0x1800a502a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a502f  test    eax, eax
0x1800a5031  js      loc_1800A5180
0x1800a5037  xor     r9d, r9d; DirectoryInfo
0x1800a503a  lea     rdx, [rbp+0A0h+NtPathName]; NtPathName
0x1800a503e  xor     r8d, r8d; NtFileNamePart
0x1800a5041  mov     rcx, r13; DosPathName
0x1800a5044  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x1800a504a  test    al, al
0x1800a504c  jz      loc_1800A5180
0x1800a5052  mov     rdx, rsi; SourceString
0x1800a5055  lea     rcx, [rbp+0A0h+DestinationString]; DestinationString
0x1800a5059  call    cs:__imp_RtlInitUnicodeString
0x1800a505f  mov     rax, [rbp+0A0h+NtPathName.Buffer]
0x1800a5063  lea     r9, [rbp+0A0h+IoStatusBlock]; IoStatusBlock
0x1800a5067  mov     [rsp+1A0h+EaLength], r14d; EaLength
0x1800a506c  lea     r8, [rbp+0A0h+ObjectAttributes]; ObjectAttributes
0x1800a5070  mov     [rsp+1A0h+EaBuffer], r14; EaBuffer
0x1800a5075  mov     ecx, 1040h
0x1800a507a  mov     [rsp+1A0h+CreateOptions], ecx; CreateOptions
0x1800a507e  xorps   xmm0, xmm0
0x1800a5081  mov     [rsp+1A0h+P], rax
0x1800a5086  mov     edx, 10001h; DesiredAccess
0x1800a508b  mov     rax, [rbp+0A0h+var_118]
0x1800a508f  mov     [rsp+1A0h+CreateDisposition], 2; CreateDisposition
0x1800a5097  mov     [rbp+0A0h+ObjectAttributes.RootDirectory], rax
0x1800a509b  lea     rax, [rbp+0A0h+DestinationString]
0x1800a509f  mov     [rbp+0A0h+ObjectAttributes.Attributes], ecx
0x1800a50a2  lea     rcx, [rsp+1A0h+FileHandle]; FileHandle
0x1800a50a7  mov     [rsp+1A0h+ShareAccess], r14d; ShareAccess
0x1800a50ac  mov     [rsp+1A0h+FileAttributes], 82h; FileAttributes
0x1800a50b4  mov     [rbp+0A0h+ObjectAttributes.ObjectName], rax
0x1800a50b8  mov     [rbp+0A0h+ObjectAttributes.Length], 30h ; '0'
0x1800a50bf  movdqu  xmmword ptr [rbp+0A0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800a50c4  mov     [rsp+1A0h+AllocationSize], r14; AllocationSize
0x1800a50c9  call    cs:__imp_NtCreateFile
0x1800a50cf  test    eax, eax
0x1800a50d1  js      loc_1800A5190
0x1800a50d7  lea     edx, [r14+3Ah]; Ch
0x1800a50db  mov     rcx, r13; Str
0x1800a50de  call    cs:__imp_wcschr
0x1800a50e4  mov     rcx, [rsp+1A0h+FileHandle]; hFile
0x1800a50e9  mov     r15d, r14d
0x1800a50ec  test    rax, rax
0x1800a50ef  setz    r15b
0x1800a50f3  xor     r8d, r8d; cchFilePath
0x1800a50f6  mov     r9d, r15d; dwFlags
0x1800a50f9  xor     edx, edx; lpszFilePath
0x1800a50fb  call    cs:__imp_GetFinalPathNameByHandleW
0x1800a5101  test    eax, eax
0x1800a5103  jz      short loc_1800A5180
0x1800a5105  lea     r14d, [rax+1]
0x1800a5109  mov     ebx, r14d
0x1800a510c  add     rbx, rbx
0x1800a510f  call    cs:__imp_GetProcessHeap
0x1800a5115  mov     r8, rbx; dwBytes
0x1800a5118  mov     edx, 8; dwFlags
0x1800a511d  mov     rcx, rax; hHeap
0x1800a5120  call    cs:__imp_HeapAlloc
0x1800a5126  mov     r12, rax
0x1800a5129  test    rax, rax
0x1800a512c  jz      short loc_1800A5180
0x1800a512e  mov     rcx, [rsp+1A0h+FileHandle]; hFile
0x1800a5133  mov     r9d, r15d; dwFlags
0x1800a5136  mov     r8d, r14d; cchFilePath
0x1800a5139  mov     rdx, rax; lpszFilePath
0x1800a513c  call    cs:__imp_GetFinalPathNameByHandleW
0x1800a5142  test    eax, eax
0x1800a5144  jz      short loc_1800A5180
0x1800a5146  xor     r9d, r9d; DirectoryInfo
0x1800a5149  lea     rdx, [rbp+0A0h+var_C0]; NtPathName
0x1800a514d  xor     r8d, r8d; NtFileNamePart
0x1800a5150  mov     rcx, r12; DosPathName
0x1800a5153  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x1800a5159  test    al, al
0x1800a515b  jz      short loc_1800A5180
0x1800a515d  mov     rbx, [rbp+0A0h+var_C0.Buffer]
0x1800a5161  mov     rcx, [rbp+0A0h+NtPathName.Buffer]; String1
0x1800a5165  mov     rdx, rbx; String2
0x1800a5168  mov     [rsp+1A0h+var_130], rbx
0x1800a516d  call    _wcsicmp_0
0x1800a5172  test    eax, eax
0x1800a5174  jnz     short loc_1800A5180
0x1800a5176  mov     rdi, [rsp+1A0h+FileHandle]
0x1800a517b  jmp     short loc_1800A5195
0x1800a517d  mov     rsi, r14
0x1800a5180  mov     rcx, [rsp+1A0h+FileHandle]; Handle
0x1800a5185  cmp     rcx, rdi
0x1800a5188  jz      short loc_1800A5195
0x1800a518a  call    cs:__imp_NtClose
0x1800a5190  mov     [rsp+1A0h+FileHandle], rdi
0x1800a5195  mov     rax, [rsp+1A0h+P]
0x1800a519a  test    rax, rax
0x1800a519d  jz      short loc_1800A51B7
0x1800a519f  mov     rcx, gs:60h
0x1800a51a8  mov     r8, rax; P
0x1800a51ab  xor     edx, edx; Flags
0x1800a51ad  mov     rcx, [rcx+30h]; HeapHandle
0x1800a51b1  call    cs:__imp_RtlFreeHeap
0x1800a51b7  mov     rax, [rsp+1A0h+var_130]
0x1800a51bc  test    rax, rax
0x1800a51bf  jz      short loc_1800A51D9
0x1800a51c1  mov     rcx, gs:60h
0x1800a51ca  mov     r8, rax; P
0x1800a51cd  xor     edx, edx; Flags
0x1800a51cf  mov     rcx, [rcx+30h]; HeapHandle
0x1800a51d3  call    cs:__imp_RtlFreeHeap
0x1800a51d9  test    r13, r13
0x1800a51dc  jz      short loc_1800A51F2
0x1800a51de  call    cs:__imp_GetProcessHeap
0x1800a51e4  mov     r8, r13; lpMem
0x1800a51e7  xor     edx, edx; dwFlags
0x1800a51e9  mov     rcx, rax; hHeap
0x1800a51ec  call    cs:__imp_HeapFree
0x1800a51f2  test    r12, r12
0x1800a51f5  jz      short loc_1800A520B
0x1800a51f7  call    cs:__imp_GetProcessHeap
0x1800a51fd  mov     r8, r12; lpMem
0x1800a5200  xor     edx, edx; dwFlags
0x1800a5202  mov     rcx, rax; hHeap
0x1800a5205  call    cs:__imp_HeapFree
0x1800a520b  test    rsi, rsi
0x1800a520e  jz      short loc_1800A5224
0x1800a5210  call    cs:__imp_GetProcessHeap
0x1800a5216  mov     r8, rsi; lpMem
0x1800a5219  xor     edx, edx; dwFlags
0x1800a521b  mov     rcx, rax; hHeap
0x1800a521e  call    cs:__imp_HeapFree
0x1800a5224  mov     rax, rdi
0x1800a5227  mov     rcx, [rbp+0A0h+var_40]
0x1800a522b  xor     rcx, rsp; StackCookie
0x1800a522e  call    __security_check_cookie
0x1800a5233  mov     rbx, [rsp+1A0h+arg_10]
0x1800a523b  add     rsp, 170h
0x1800a5242  pop     r15
0x1800a5244  pop     r14
0x1800a5246  pop     r13
0x1800a5248  pop     r12
0x1800a524a  pop     rdi
0x1800a524b  pop     rsi
0x1800a524c  pop     rbp
0x1800a524d  retn
```
