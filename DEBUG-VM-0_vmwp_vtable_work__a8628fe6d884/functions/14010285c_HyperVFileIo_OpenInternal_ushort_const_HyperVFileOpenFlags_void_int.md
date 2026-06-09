# HyperVFileIo::OpenInternal(ushort const *,HyperVFileOpenFlags,void * *,int *)

- ea: `0x14010285c`
- end: `0x140102b5c`
- name: `?OpenInternal@HyperVFileIo@@CAJPEBGW4HyperVFileOpenFlags@@PEAPEAXPEAH@Z`
- size: `768`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400612b0`
- `0x1400fe210`
- `0x140102640`

## callees

- `0x140023e30`
- `0x1400261dc`
- `0x1400287a8`
- `0x14010285c`
- `0x140102eb4`
- `0x140132940`
- `0x140133bec`
- `0x140133c54`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x140102920`
- `ntdll!RtlNtStatusToDosError` at `0x140102b15`
- `ntdll!RtlNtStatusToDosError` at `0x140102920`
- `ntdll!RtlNtStatusToDosError` at `0x140102b15`
- `ntdll!NtCreateFile` at `0x1401029ff`
- `ntdll!NtCreateFile` at `0x140102a56`
- `ntdll!NtCreateFile` at `0x1401029ff`
- `ntdll!NtCreateFile` at `0x140102a56`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x14010290c`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x14010290c`

## pseudocode

```c
signed int __fastcall HyperVFileIo::OpenInternal(__int64 a1, __int16 a2, void **a3, int *a4)
{
  ULONG ShareAccess; // ebx
  int v8; // edi
  signed int result; // eax
  ULONG CreateDisposition; // r15d
  unsigned int v11; // r14d
  NTSTATUS v12; // eax
  int v13; // eax
  bool v14; // zf
  int IsDebugTraceEnabled; // ebx
  unsigned __int64 v16; // rdx
  unsigned __int8 v17; // cl
  bool IsEnabled; // al
  char v19; // di
  unsigned int v20; // ebx
  signed int v21; // eax
  void *FileHandle; // [rsp+68h] [rbp-98h] BYREF
  __int128 v24; // [rsp+70h] [rbp-90h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-80h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v27; // [rsp+C0h] [rbp-40h] BYREF
  int v28; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v29; // [rsp+CCh] [rbp-34h]
  _DWORD EaBuffer[2]; // [rsp+D8h] [rbp-28h] BYREF
  char v31[28]; // [rsp+E0h] [rbp-20h] BYREF
  int v32; // [rsp+FCh] [rbp-4h]

  *a3 = (void *)-1LL;
  FileHandle = (void *)-1LL;
  *a4 = 0;
  ShareAccess = (a2 & 8) != 0 ? 1 : 3;
  if ( (a2 & 0x40) != 0 )
  {
    if ( (a2 & 8) != 0 )
      return -2147024809;
    ShareAccess |= 4u;
  }
  v8 = 1;
  if ( (a2 & 0x20) != 0 && (a2 & 3) != 0 )
    return -2147024809;
  CreateDisposition = *((_DWORD *)qword_14030E418 + (a2 & 3));
  v11 = (a2 & 0x20) != 0 ? 0xFFFFFEFE : 0;
  v24 = 0;
  v12 = RtlDosPathNameToRelativeNtPathName_U_WithStatus(a1, &v24, 0, 0);
  if ( v12 >= 0 )
  {
    v27 = *((_QWORD *)&v24 + 1);
    ObjectAttributes.ObjectName = (PUNICODE_STRING)&v24;
    ObjectAttributes.SecurityQualityOfService = &v28;
    *(_QWORD *)&ObjectAttributes.Length = 48;
    *(_QWORD *)&ObjectAttributes.Attributes = 64;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.SecurityDescriptor = 0;
    v29 = 0;
    v28 = 12;
    IoStatusBlock = 0;
    if ( (a2 & 0x1000) == 0
      || (EaBuffer[0] = 0,
          v31[27] = 0,
          v32 = 0,
          strcpy(v31, "SmbDisableHandleDurability"),
          EaBuffer[1] = 6656,
          v13 = NtCreateFile(
                  &FileHandle,
                  v11 + 1048963,
                  &ObjectAttributes,
                  &IoStatusBlock,
                  0,
                  0x80u,
                  ShareAccess,
                  CreateDisposition,
                  0x840u,
                  EaBuffer,
                  0x28u),
          v13 == -1073741808)
      || v13 == -1073741745 )
    {
      v13 = NtCreateFile(
              &FileHandle,
              v11 + 1048963,
              &ObjectAttributes,
              &IoStatusBlock,
              0,
              0x80u,
              ShareAccess,
              CreateDisposition,
              0x840u,
              0,
              0);
    }
    if ( v13 < 0 )
    {
      v21 = RtlNtStatusToDosError(v13);
      v20 = v21;
      if ( v21 > 0 )
        v20 = (unsigned __int16)v21 | 0x80070000;
    }
    else
    {
      v14 = (IoStatusBlock.Information & 0xFFFFFFFFFFFFFFFCuLL) == 0;
      *a3 = FileHandle;
      if ( !v14 || IoStatusBlock.Information == 1 )
        v8 = 0;
      *a4 = v8;
      IsDebugTraceEnabled = HvsIsDebugTraceEnabled(0xC000u);
      IsEnabled = HyperVStorageTrace::IsEnabled(v17, v16);
      v19 = IsEnabled;
      if ( IsDebugTraceEnabled || IsEnabled )
      {
        if ( dword_1403C1950 > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 2064LL) )
        {
          Init_thread_header(&dword_1403C1950);
          if ( dword_1403C1950 == -1 )
          {
            byte_1403A6EDC = IsDebugTraceEnabled != 0;
            byte_1403A6EDD = v19;
            Init_thread_footer(&dword_1403C1950);
          }
        }
        HvsDebugTraceInternal(0xC000u, (const wchar_t *const *)&off_1403A6EC8, a1);
      }
      v20 = 0;
    }
    std::unique_ptr_unsigned_short__anonymous_namespace_::RtlHeapDeleter_unsigned_short___::_unique_ptr_unsigned_short__anonymous_namespace_::RtlHeapDeleter_unsigned_short___(&v27);
    return v20;
  }
  else
  {
    result = RtlNtStatusToDosError(v12);
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x14010285c  push    rbp
0x14010285e  push    rbx
0x14010285f  push    rsi
0x140102860  push    rdi
0x140102861  push    r12
0x140102863  push    r13
0x140102865  push    r14
0x140102867  push    r15
0x140102869  lea     rbp, [rsp-18h]
0x14010286e  sub     rsp, 118h
0x140102875  mov     rax, cs:__security_cookie
0x14010287c  xor     rax, rsp
0x14010287f  mov     [rbp+50h+var_50], rax
0x140102883  mov     r13, rcx
0x140102886  mov     [rsp+150h+var_F0], r9
0x14010288b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14010288f  mov     r12, r8
0x140102892  mov     [r8], rcx
0x140102895  mov     esi, edx
0x140102897  mov     [rsp+150h+FileHandle], rcx
0x14010289c  mov     ecx, edx
0x14010289e  and     ecx, 8
0x1401028a1  mov     dword ptr [r9], 0
0x1401028a8  mov     eax, ecx
0x1401028aa  neg     eax
0x1401028ac  sbb     ebx, ebx
0x1401028ae  and     ebx, 0FFFFFFFEh
0x1401028b1  add     ebx, 3
0x1401028b4  test    dl, 40h
0x1401028b7  jz      short loc_1401028C0
0x1401028b9  test    ecx, ecx
0x1401028bb  jnz     short loc_1401028D5
0x1401028bd  or      ebx, 4
0x1401028c0  mov     eax, esi
0x1401028c2  mov     ecx, esi
0x1401028c4  and     eax, 3
0x1401028c7  mov     edi, 1
0x1401028cc  and     ecx, 20h
0x1401028cf  jz      short loc_1401028DF
0x1401028d1  cmp     eax, edi
0x1401028d3  jb      short loc_1401028DF
0x1401028d5  mov     eax, 80070057h
0x1401028da  jmp     loc_140102B3B
0x1401028df  neg     ecx
0x1401028e1  lea     r15, qword_14030E418
0x1401028e8  mov     r15d, [r15+rax*4]
0x1401028ec  lea     rdx, [rsp+150h+var_E0]
0x1401028f1  sbb     r14d, r14d
0x1401028f4  xorps   xmm0, xmm0
0x1401028f7  xor     r9d, r9d
0x1401028fa  xor     r8d, r8d
0x1401028fd  mov     rcx, r13
0x140102900  and     r14d, 0FFFFFEFEh
0x140102907  movups  [rsp+150h+var_E0], xmm0
0x14010290c  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U_WithStatus
0x140102913  nop     dword ptr [rax+rax+00h]
0x140102918  xor     ecx, ecx
0x14010291a  test    eax, eax
0x14010291c  jns     short loc_140102941
0x14010291e  mov     ecx, eax; Status
0x140102920  call    cs:__imp_RtlNtStatusToDosError
0x140102927  nop     dword ptr [rax+rax+00h]
0x14010292c  test    eax, eax
0x14010292e  jle     loc_140102B3B
0x140102934  movzx   eax, ax
0x140102937  or      eax, 80070000h
0x14010293c  jmp     loc_140102B3B
0x140102941  mov     rax, qword ptr [rsp+150h+var_E0+8]
0x140102946  xorps   xmm0, xmm0
0x140102949  mov     [rbp+50h+var_90], rax
0x14010294d  lea     rax, [rsp+150h+var_E0]
0x140102952  mov     [rbp+50h+ObjectAttributes.ObjectName], rax
0x140102956  lea     rax, [rbp+50h+var_88]
0x14010295a  mov     [rbp+50h+ObjectAttributes.SecurityQualityOfService], rax
0x14010295e  mov     qword ptr [rbp+50h+ObjectAttributes.Length], 30h ; '0'
0x140102966  mov     qword ptr [rbp+50h+ObjectAttributes.Attributes], 40h ; '@'
0x14010296e  mov     [rbp+50h+ObjectAttributes.RootDirectory], rcx
0x140102972  mov     [rbp+50h+ObjectAttributes.SecurityDescriptor], rcx
0x140102976  mov     [rbp+50h+var_84], rcx
0x14010297a  mov     [rbp+50h+var_88], 0Ch
0x140102981  movups  xmmword ptr [rbp+50h+IoStatusBlock], xmm0
0x140102985  bt      esi, 0Ch
0x140102989  jnb     loc_140102A1B
0x14010298f  movups  xmm1, cs:xmmword_14030E428+0Ah
0x140102996  mov     [rsp+150h+EaLength], 28h ; '('; EaLength
0x14010299e  lea     r9, [rbp+50h+IoStatusBlock]; IoStatusBlock
0x1401029a2  movups  xmmword ptr [rbp+50h+var_74], xmm0
0x1401029a6  xor     eax, eax
0x1401029a8  mov     [rbp+50h+var_78], ecx
0x1401029ab  movups  xmmword ptr [rbp+50h+var_74+10h], xmm0
0x1401029af  mov     [rbp+50h+var_54], eax
0x1401029b2  lea     rax, [rbp+50h+var_78]
0x1401029b6  movups  xmm0, cs:xmmword_14030E428
0x1401029bd  mov     [rsp+150h+EaBuffer], rax; EaBuffer
0x1401029c2  lea     r8, [rbp+50h+ObjectAttributes]; ObjectAttributes
0x1401029c6  mov     [rsp+150h+CreateOptions], 840h; CreateOptions
0x1401029ce  lea     edx, [r14+100183h]; DesiredAccess
0x1401029d5  mov     [rsp+150h+CreateDisposition], r15d; CreateDisposition
0x1401029da  mov     [rsp+150h+ShareAccess], ebx; ShareAccess
0x1401029de  movups  xmmword ptr [rbp+50h+var_74+4], xmm0
0x1401029e2  mov     [rsp+150h+FileAttributes], 80h; FileAttributes
0x1401029ea  mov     [rsp+150h+AllocationSize], rcx; AllocationSize
0x1401029ef  lea     rcx, [rsp+150h+FileHandle]; FileHandle
0x1401029f4  mov     dword ptr [rbp+50h+var_74], 1A00h
0x1401029fb  movups  xmmword ptr [rbp+50h+var_74+0Eh], xmm1
0x1401029ff  call    cs:__imp_NtCreateFile
0x140102a06  nop     dword ptr [rax+rax+00h]
0x140102a0b  cmp     eax, 0C0000010h
0x140102a10  jz      short loc_140102A19
0x140102a12  cmp     eax, 0C000004Fh
0x140102a17  jnz     short loc_140102A62
0x140102a19  xor     ecx, ecx
0x140102a1b  mov     [rsp+150h+EaLength], ecx; EaLength
0x140102a1f  lea     r9, [rbp+50h+IoStatusBlock]; IoStatusBlock
0x140102a23  mov     [rsp+150h+EaBuffer], rcx; EaBuffer
0x140102a28  lea     r8, [rbp+50h+ObjectAttributes]; ObjectAttributes
0x140102a2c  mov     [rsp+150h+CreateOptions], 840h; CreateOptions
0x140102a34  lea     edx, [r14+100183h]; DesiredAccess
0x140102a3b  mov     [rsp+150h+CreateDisposition], r15d; CreateDisposition
0x140102a40  mov     [rsp+150h+ShareAccess], ebx; ShareAccess
0x140102a44  mov     [rsp+150h+FileAttributes], 80h; FileAttributes
0x140102a4c  mov     [rsp+150h+AllocationSize], rcx; AllocationSize
0x140102a51  lea     rcx, [rsp+150h+FileHandle]; FileHandle
0x140102a56  call    cs:__imp_NtCreateFile
0x140102a5d  nop     dword ptr [rax+rax+00h]
0x140102a62  test    eax, eax
0x140102a64  js      loc_140102B13
0x140102a6a  test    [rbp+50h+IoStatusBlock.Information], 0FFFFFFFFFFFFFFFCh
0x140102a72  mov     rax, [rsp+150h+FileHandle]
0x140102a77  mov     [r12], rax
0x140102a7b  jnz     short loc_140102A83
0x140102a7d  cmp     [rbp+50h+IoStatusBlock.Information], rdi
0x140102a81  jnz     short loc_140102A85
0x140102a83  xor     edi, edi
0x140102a85  mov     rax, [rsp+150h+var_F0]
0x140102a8a  mov     r14d, 0C000h
0x140102a90  mov     ecx, r14d; unsigned __int16
0x140102a93  mov     [rax], edi
0x140102a95  call    ?HvsIsDebugTraceEnabled@@YAHG@Z; HvsIsDebugTraceEnabled(ushort)
0x140102a9a  test    eax, eax
0x140102a9c  mov     ebx, eax
0x140102a9e  setnz   sil
0x140102aa2  call    ?IsEnabled@HyperVStorageTrace@@SA_NE_K@Z; HyperVStorageTrace::IsEnabled(uchar,unsigned __int64)
0x140102aa7  mov     dil, al
0x140102aaa  test    ebx, ebx
0x140102aac  jnz     short loc_140102AB2
0x140102aae  test    al, al
0x140102ab0  jz      short loc_140102B0F
0x140102ab2  mov     rcx, gs:58h
0x140102abb  mov     eax, 810h
0x140102ac0  mov     rdx, [rcx]
0x140102ac3  mov     ecx, [rax+rdx]
0x140102ac6  cmp     cs:dword_1403C1950, ecx
0x140102acc  jle     short loc_140102AFD
0x140102ace  lea     rcx, dword_1403C1950
0x140102ad5  call    _Init_thread_header
0x140102ada  cmp     cs:dword_1403C1950, 0FFFFFFFFh
0x140102ae1  jnz     short loc_140102AFD
0x140102ae3  lea     rcx, dword_1403C1950
0x140102aea  mov     cs:byte_1403A6EDC, sil
0x140102af1  mov     cs:byte_1403A6EDD, dil
0x140102af8  call    _Init_thread_footer
0x140102afd  mov     r8, r13
0x140102b00  lea     rdx, off_1403A6EC8; struct HvsDebugTraceParameters *
0x140102b07  mov     ecx, r14d; unsigned int
0x140102b0a  call    ?HvsDebugTraceInternal@@YAXIPEBUHvsDebugTraceParameters@@ZZ; HvsDebugTraceInternal(uint,HvsDebugTraceParameters const *,...)
0x140102b0f  xor     ebx, ebx
0x140102b11  jmp     short loc_140102B30
0x140102b13  mov     ecx, eax; Status
0x140102b15  call    cs:__imp_RtlNtStatusToDosError
0x140102b1c  nop     dword ptr [rax+rax+00h]
0x140102b21  mov     ebx, eax
0x140102b23  test    eax, eax
0x140102b25  jle     short loc_140102B30
0x140102b27  movzx   ebx, ax
0x140102b2a  or      ebx, 80070000h
0x140102b30  lea     rcx, [rbp+50h+var_90]
0x140102b34  call    std__unique_ptr_unsigned_short__anonymous_namespace___RtlHeapDeleter_unsigned_short______unique_ptr_unsigned_short__anonymous_namespace___RtlHeapDeleter_unsigned_short___
0x140102b39  mov     eax, ebx
0x140102b3b  mov     rcx, [rbp+50h+var_50]
0x140102b3f  xor     rcx, rsp; StackCookie
0x140102b42  call    __security_check_cookie
0x140102b47  add     rsp, 118h
0x140102b4e  pop     r15
0x140102b50  pop     r14
0x140102b52  pop     r13
0x140102b54  pop     r12
0x140102b56  pop     rdi
0x140102b57  pop     rsi
0x140102b58  pop     rbx
0x140102b59  pop     rbp
0x140102b5a  retn
```
