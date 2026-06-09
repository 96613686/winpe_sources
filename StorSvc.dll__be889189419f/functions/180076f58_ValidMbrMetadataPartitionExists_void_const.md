# ValidMbrMetadataPartitionExists(void * const)

- ea: `0x180076f58`
- end: `0x18007717d`
- name: `?ValidMbrMetadataPartitionExists@@YA_NQEAX@Z`
- size: `549`
- prototype: `bool __fastcall(HANDLE hDevice)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180075240`

## callees

- `0x18000d030`
- `0x180073034`
- `0x18007318c`
- `0x18007342c`
- `0x180074cd4`
- `0x180074d94`
- `0x180076f58`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077032`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007707a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800770db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077032`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007707a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800770db`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800770d1`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800770d1`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180077070`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180077070`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180077024`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180077024`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18007714e`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18007714e`

## string_xrefs

- `0x180077099`: `SetFilePointerEx`
- `0x1800770f6`: `ReadFile`

## pseudocode

```c
bool __fastcall ValidMbrMetadataPartitionExists(HANDLE hDevice, __int64 a2, unsigned int *a3)
{
  unsigned int *v3; // rdi
  bool v5; // si
  unsigned int *v6; // r8
  unsigned __int64 BytesPerSector; // r15
  __int64 i; // rdx
  LARGE_INTEGER v9; // rbx
  __int64 v10; // r14
  SIZE_T v11; // r15
  __int64 v12; // rcx
  char LastError; // al
  int v14; // edx
  int v15; // ecx
  const wchar_t *v16; // r9
  struct _DISK_GEOMETRY_EX *v18; // [rsp+30h] [rbp-48h] BYREF
  struct _DISK_GEOMETRY_EX *v19; // [rsp+38h] [rbp-40h] BYREF
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-38h] BYREF

  v3 = 0;
  v19 = 0;
  v18 = 0;
  v5 = 0;
  if ( (int)GetDiskGeometry(hDevice, &v19, a3) >= 0 )
  {
    BytesPerSector = v19->Geometry.BytesPerSector;
    if ( (int)GetDiskLayoutInternal(hDevice, (struct _DRIVE_LAYOUT_INFORMATION_EX **)&v18, v6) >= 0 )
    {
      for ( i = 0; ; i = (unsigned int)(i + 1) )
      {
        if ( (unsigned int)i >= v18->Geometry.Cylinders.HighPart )
          goto LABEL_21;
        if ( *((_BYTE *)&v18[2].Geometry.Cylinders.LowPart + 144 * i) == 112 )
          break;
      }
      v9 = *(LARGE_INTEGER *)(&v18[1].Geometry.SectorsPerTrack + 36 * i);
      if ( v9.QuadPart )
      {
        v10 = *(&v18[1].DiskSize.QuadPart + 18 * i);
        if ( v10 )
        {
          v11 = (unsigned int)BytesPerSector
              * (unsigned int)(((unsigned __int64)(unsigned int)(BytesPerSector - 1) + 12) / BytesPerSector);
          v3 = (unsigned int *)VirtualAlloc(0, v11, 0x3000u, 4u);
          if ( !v3 )
          {
            GetLastError();
            if ( (Microsoft_WindowsPhone_StorageHelperEnableBits & 1) != 0 )
              McTemplateU0zz_EventWriteTransfer(
                v12,
                AllocationFailure,
                L"ValidMbrMetadataPartitionExists",
                L"MBR_META_HEADER");
            goto LABEL_21;
          }
          if ( !SetFilePointerEx(hDevice, v9, 0, 0) )
          {
            LastError = GetLastError();
            if ( (Microsoft_WindowsPhone_StorageHelperEnableBits & 4) == 0 )
              goto LABEL_21;
            v16 = L"SetFilePointerEx";
            goto LABEL_15;
          }
          NumberOfBytesRead = 0;
          if ( !ReadFile(hDevice, v3, v11, &NumberOfBytesRead, 0) )
          {
            LastError = GetLastError();
            if ( (Microsoft_WindowsPhone_StorageHelperEnableBits & 4) == 0 )
              goto LABEL_21;
            v16 = L"ReadFile";
LABEL_15:
            McTemplateU0zzq_EventWriteTransfer(
              v15,
              v14,
              (unsigned int)L"ValidMbrMetadataPartitionExists",
              (_DWORD)v16,
              LastError);
            goto LABEL_21;
          }
          if ( *v3 == 524289 )
            v5 = (v10 - 12) / 0x60uLL >= v3[2];
        }
      }
    }
  }
LABEL_21:
  SafeFreeDiskGeometry(&v18);
  SafeFreeDiskGeometry(&v19);
  if ( v3 )
    VirtualFree(v3, 0, 0x8000u);
  return v5;
}

```

## disassembly

```asm
0x180076f58  mov     r11, rsp
0x180076f5b  mov     [r11+10h], rbx
0x180076f5f  mov     [r11+18h], rbp
0x180076f63  push    rsi
0x180076f64  push    rdi
0x180076f65  push    r13
0x180076f67  push    r14
0x180076f69  push    r15
0x180076f6b  sub     rsp, 50h
0x180076f6f  mov     rax, cs:__security_cookie
0x180076f76  xor     rax, rsp
0x180076f79  mov     [rsp+78h+var_30], rax
0x180076f7e  xor     edi, edi
0x180076f80  lea     rdx, [r11-40h]; struct _DISK_GEOMETRY_EX **
0x180076f84  mov     [r11-40h], rdi
0x180076f88  mov     rbp, rcx
0x180076f8b  mov     [r11-48h], rdi
0x180076f8f  xor     sil, sil
0x180076f92  call    ?GetDiskGeometry@@YAJQEAXPEAPEAU_DISK_GEOMETRY_EX@@PEAK@Z; GetDiskGeometry(void * const,_DISK_GEOMETRY_EX * *,ulong *)
0x180076f97  test    eax, eax
0x180076f99  js      loc_18007712A
0x180076f9f  mov     rax, [rsp+78h+var_40]
0x180076fa4  lea     rdx, [rsp+78h+var_48]; struct _DRIVE_LAYOUT_INFORMATION_EX **
0x180076fa9  mov     rcx, rbp; hDevice
0x180076fac  mov     r15d, [rax+14h]
0x180076fb0  call    ?GetDiskLayoutInternal@@YAJQEAXPEAPEAU_DRIVE_LAYOUT_INFORMATION_EX@@PEAK@Z; GetDiskLayoutInternal(void * const,_DRIVE_LAYOUT_INFORMATION_EX * *,ulong *)
0x180076fb5  test    eax, eax
0x180076fb7  js      loc_18007712A
0x180076fbd  mov     r8, [rsp+78h+var_48]
0x180076fc2  lea     r13d, [rdi+1]
0x180076fc6  xor     edx, edx
0x180076fc8  cmp     edx, [r8+4]
0x180076fcc  jnb     loc_18007712A
0x180076fd2  lea     rcx, [rdx+rdx*8]
0x180076fd6  add     rcx, rcx
0x180076fd9  cmp     byte ptr [r8+rcx*8+50h], 70h ; 'p'
0x180076fdf  jz      short loc_180076FE6
0x180076fe1  add     edx, r13d
0x180076fe4  jmp     short loc_180076FC8
0x180076fe6  mov     rbx, [r8+rcx*8+38h]
0x180076feb  test    rbx, rbx
0x180076fee  jz      loc_18007712A
0x180076ff4  mov     r14, [r8+rcx*8+40h]
0x180076ff9  test    r14, r14
0x180076ffc  jz      loc_18007712A
0x180077002  xor     edx, edx
0x180077004  lea     eax, [r15-1]
0x180077008  add     rax, 0Ch
0x18007700c  xor     ecx, ecx; lpAddress
0x18007700e  div     r15
0x180077011  lea     r9d, [rcx+4]; flProtect
0x180077015  mov     r8d, 3000h; flAllocationType
0x18007701b  imul    eax, r15d
0x18007701f  mov     edx, eax; dwSize
0x180077021  mov     r15d, eax
0x180077024  call    cs:__imp_VirtualAlloc
0x18007702a  mov     rdi, rax
0x18007702d  test    rax, rax
0x180077030  jnz     short loc_180077064
0x180077032  call    cs:__imp_GetLastError
0x180077038  test    cs:Microsoft_WindowsPhone_StorageHelperEnableBits, r13b
0x18007703f  jz      loc_18007712A
0x180077045  lea     r9, aMbrMetaHeader; "MBR_META_HEADER"
0x18007704c  lea     r8, aValidmbrmetada; "ValidMbrMetadataPartitionExists"
0x180077053  lea     rdx, AllocationFailure
0x18007705a  call    McTemplateU0zz_EventWriteTransfer
0x18007705f  jmp     loc_18007712A
0x180077064  xor     r9d, r9d; dwMoveMethod
0x180077067  xor     r8d, r8d; lpNewFilePointer
0x18007706a  mov     rdx, rbx; liDistanceToMove
0x18007706d  mov     rcx, rbp; hFile
0x180077070  call    cs:__imp_SetFilePointerEx
0x180077076  test    eax, eax
0x180077078  jnz     short loc_1800770B2
0x18007707a  call    cs:__imp_GetLastError
0x180077080  test    eax, eax
0x180077082  jle     short loc_18007708C
0x180077084  movzx   eax, ax
0x180077087  or      eax, 80070000h
0x18007708c  test    cs:Microsoft_WindowsPhone_StorageHelperEnableBits, 4
0x180077093  jz      loc_18007712A
0x180077099  lea     r9, aSetfilepointer; "SetFilePointerEx"
0x1800770a0  lea     r8, aValidmbrmetada; "ValidMbrMetadataPartitionExists"
0x1800770a7  mov     dword ptr [rsp+78h+lpOverlapped], eax
0x1800770ab  call    McTemplateU0zzq_EventWriteTransfer
0x1800770b0  jmp     short loc_18007712A
0x1800770b2  lea     r9, [rsp+78h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800770b7  mov     [rsp+78h+NumberOfBytesRead], 0
0x1800770bf  mov     r8d, r15d; nNumberOfBytesToRead
0x1800770c2  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x1800770cb  mov     rdx, rdi; lpBuffer
0x1800770ce  mov     rcx, rbp; hFile
0x1800770d1  call    cs:__imp_ReadFile
0x1800770d7  test    eax, eax
0x1800770d9  jnz     short loc_1800770FF
0x1800770db  call    cs:__imp_GetLastError
0x1800770e1  test    eax, eax
0x1800770e3  jle     short loc_1800770ED
0x1800770e5  movzx   eax, ax
0x1800770e8  or      eax, 80070000h
0x1800770ed  test    cs:Microsoft_WindowsPhone_StorageHelperEnableBits, 4
0x1800770f4  jz      short loc_18007712A
0x1800770f6  lea     r9, aReadfile; "ReadFile"
0x1800770fd  jmp     short loc_1800770A0
0x1800770ff  cmp     dword ptr [rdi], 80001h
0x180077105  jnz     short loc_18007712A
0x180077107  lea     rcx, [r14-0Ch]
0x18007710b  movzx   esi, sil
0x18007710f  mov     rax, 0AAAAAAAAAAAAAAABh
0x180077119  mul     rcx
0x18007711c  mov     eax, [rdi+8]
0x18007711f  shr     rdx, 6
0x180077123  cmp     rdx, rax
0x180077126  cmovnb  esi, r13d
0x18007712a  lea     rcx, [rsp+78h+var_48]; struct _DISK_GEOMETRY_EX **
0x18007712f  call    ?SafeFreeDiskGeometry@@YAXPEAPEAU_DISK_GEOMETRY_EX@@@Z; SafeFreeDiskGeometry(_DISK_GEOMETRY_EX * *)
0x180077134  lea     rcx, [rsp+78h+var_40]; struct _DISK_GEOMETRY_EX **
0x180077139  call    ?SafeFreeDiskGeometry@@YAXPEAPEAU_DISK_GEOMETRY_EX@@@Z; SafeFreeDiskGeometry(_DISK_GEOMETRY_EX * *)
0x18007713e  test    rdi, rdi
0x180077141  jz      short loc_180077154
0x180077143  xor     edx, edx; dwSize
0x180077145  mov     r8d, 8000h; dwFreeType
0x18007714b  mov     rcx, rdi; lpAddress
0x18007714e  call    cs:__imp_VirtualFree
0x180077154  mov     al, sil
0x180077157  mov     rcx, [rsp+78h+var_30]
0x18007715c  xor     rcx, rsp; StackCookie
0x18007715f  call    __security_check_cookie
0x180077164  lea     r11, [rsp+78h+var_28]
0x180077169  mov     rbx, [r11+38h]
0x18007716d  mov     rbp, [r11+40h]
0x180077171  mov     rsp, r11
0x180077174  pop     r15
0x180077176  pop     r14
0x180077178  pop     r13
0x18007717a  pop     rdi
0x18007717b  pop     rsi
0x18007717c  retn
```
