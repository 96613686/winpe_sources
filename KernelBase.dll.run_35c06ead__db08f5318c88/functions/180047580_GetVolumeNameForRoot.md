# GetVolumeNameForRoot

- ea: `0x180047580`
- end: `0x180047c83`
- name: `GetVolumeNameForRoot`
- size: `1795`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180046310`
- `0x1800464e0`

## callees

- `0x180013ec0`
- `0x180047580`
- `0x18004873c`
- `0x180048f30`
- `0x18012eecc`
- `0x180188eb9`
- `0x180188f10`

## import_xrefs

- `ntdll!NtOpenFile` at `0x1800476a6`
- `ntdll!NtOpenFile` at `0x1800476a6`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800475de`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800475de`
- `ntdll!RtlSetLastWin32Error` at `0x180047b23`
- `ntdll!RtlSetLastWin32Error` at `0x180047b35`
- `ntdll!RtlSetLastWin32Error` at `0x180047b66`
- `ntdll!RtlSetLastWin32Error` at `0x180047b90`
- `ntdll!RtlSetLastWin32Error` at `0x180047ba2`
- `ntdll!RtlSetLastWin32Error` at `0x180047c38`
- `ntdll!RtlSetLastWin32Error` at `0x180047c4f`
- `ntdll!RtlSetLastWin32Error` at `0x180047b23`
- `ntdll!RtlSetLastWin32Error` at `0x180047b35`
- `ntdll!RtlSetLastWin32Error` at `0x180047b66`
- `ntdll!RtlSetLastWin32Error` at `0x180047b90`
- `ntdll!RtlSetLastWin32Error` at `0x180047ba2`
- `ntdll!RtlSetLastWin32Error` at `0x180047c38`
- `ntdll!RtlSetLastWin32Error` at `0x180047c4f`
- `ntdll!RtlNtStatusToDosError` at `0x180047b5e`
- `ntdll!RtlNtStatusToDosError` at `0x180047b5e`
- `ntdll!NtClose` at `0x1800476f2`
- `ntdll!NtClose` at `0x1800476f2`
- `ntdll!RtlFreeHeap` at `0x18004770c`
- `ntdll!RtlFreeHeap` at `0x1800477f3`
- `ntdll!RtlFreeHeap` at `0x1800478e2`
- `ntdll!RtlFreeHeap` at `0x180047a58`
- `ntdll!RtlFreeHeap` at `0x180047ac1`
- `ntdll!RtlFreeHeap` at `0x180047b56`
- `ntdll!RtlFreeHeap` at `0x180047b85`
- `ntdll!RtlFreeHeap` at `0x180047bba`
- `ntdll!RtlFreeHeap` at `0x180047be3`
- `ntdll!RtlFreeHeap` at `0x180047bfb`
- `ntdll!RtlFreeHeap` at `0x180047c2d`
- `ntdll!RtlFreeHeap` at `0x180047c73`
- `ntdll!RtlFreeHeap` at `0x18004770c`
- `ntdll!RtlFreeHeap` at `0x1800477f3`
- `ntdll!RtlFreeHeap` at `0x1800478e2`
- `ntdll!RtlFreeHeap` at `0x180047a58`
- `ntdll!RtlFreeHeap` at `0x180047ac1`
- `ntdll!RtlFreeHeap` at `0x180047b56`
- `ntdll!RtlFreeHeap` at `0x180047b85`
- `ntdll!RtlFreeHeap` at `0x180047bba`
- `ntdll!RtlFreeHeap` at `0x180047be3`
- `ntdll!RtlFreeHeap` at `0x180047bfb`
- `ntdll!RtlFreeHeap` at `0x180047c2d`
- `ntdll!RtlFreeHeap` at `0x180047c73`
- `ntdll!toupper` at `0x180047644`
- `ntdll!toupper` at `0x180047644`
- `ntdll!RtlAllocateHeap` at `0x180047744`
- `ntdll!RtlAllocateHeap` at `0x1800477a0`
- `ntdll!RtlAllocateHeap` at `0x180047812`
- `ntdll!RtlAllocateHeap` at `0x180047add`
- `ntdll!RtlAllocateHeap` at `0x180047744`
- `ntdll!RtlAllocateHeap` at `0x1800477a0`
- `ntdll!RtlAllocateHeap` at `0x180047812`
- `ntdll!RtlAllocateHeap` at `0x180047add`

## string_xrefs

- `0x180047852`: `\\.\MountPointManager`

## pseudocode

```c
__int64 __fastcall GetVolumeNameForRoot(const WCHAR *a1, __int64 a2, unsigned int a3)
{
  __int64 v3; // r15
  USHORT Length; // cx
  PWSTR Buffer; // rdx
  WCHAR *v7; // r8
  unsigned __int64 v8; // rax
  int v9; // ebx
  BOOL v10; // ebx
  WCHAR *Heap; // rax
  _WORD *v12; // rax
  _WORD *v13; // rdi
  void *v14; // rcx
  unsigned int v15; // eax
  DWORD *v16; // rbx
  void *FileInternal; // rax
  BOOL i; // eax
  BOOL v19; // esi
  DWORD j; // edx
  __int16 v21; // r8
  __int64 v22; // rax
  __int16 v23; // cx
  DWORD v25; // esi
  PVOID v26; // rax
  ULONG v27; // eax
  ULONG v28; // ecx
  struct _UNICODE_STRING NtPathName; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE FileHandle; // [rsp+50h] [rbp-B0h] BYREF
  DWORD BytesReturned; // [rsp+58h] [rbp-A8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD v33[4]; // [rsp+90h] [rbp-70h] BYREF
  __m128i si128; // [rsp+A0h] [rbp-60h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B0h] [rbp-50h] BYREF
  USHORT OutBuffer; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE Src[526]; // [rsp+C2h] [rbp-3Eh] BYREF

  v3 = a3;
  FileHandle = 0;
  NtPathName = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  if ( !RtlDosPathNameToNtPathName_U(a1, &NtPathName, 0, 0) )
  {
    RtlSetLastWin32Error(3u);
    return 0;
  }
  Length = NtPathName.Length;
  Buffer = NtPathName.Buffer;
  v7 = &NtPathName.Buffer[(unsigned __int64)NtPathName.Length >> 1];
  if ( *(v7 - 1) == 92 )
  {
    *(v7 - 1) = 0;
    Buffer = NtPathName.Buffer;
    Length = NtPathName.Length - 2;
    NtPathName.Length -= 2;
  }
  if ( Length >= 4u )
  {
    v8 = (unsigned __int64)Length >> 1;
    if ( Buffer[v8 - 1] == 58 )
      NtPathName.Buffer[((unsigned __int64)NtPathName.Length >> 1) - 2] = toupper(Buffer[v8 - 2]);
  }
  ObjectAttributes.ObjectName = &NtPathName;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v9 = NtOpenFile(&FileHandle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 3u, 0x10u);
  if ( v9 < 0 )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, NtPathName.Buffer);
    v27 = RtlNtStatusToDosError(v9);
    RtlSetLastWin32Error(v27);
    return 0;
  }
  v10 = DeviceIoControl(FileHandle, 0x4D0008u, 0, 0, &OutBuffer, 0x208u, &BytesReturned, 0);
  NtClose(FileHandle);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, NtPathName.Buffer);
  if ( !v10 )
    return 0;
  NtPathName.Length = OutBuffer;
  NtPathName.MaximumLength = OutBuffer + 2;
  Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, (unsigned __int16)(OutBuffer + 2));
  NtPathName.Buffer = Heap;
  if ( !Heap )
  {
    RtlSetLastWin32Error(8u);
    return 0;
  }
  memcpy_0(Heap, Src, OutBuffer);
  NtPathName.Buffer[(unsigned __int64)NtPathName.Length >> 1] = 0;
  v12 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, NtPathName.Length + 24LL);
  v13 = v12;
  if ( v12 )
  {
    v14 = v12 + 12;
    *(_OWORD *)v12 = 0;
    *((_QWORD *)v12 + 2) = 0;
    *((_DWORD *)v12 + 4) = 24;
    v15 = NtPathName.Length;
    v13[10] = NtPathName.Length;
    memcpy_0(v14, NtPathName.Buffer, v15);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, NtPathName.Buffer);
    v16 = (DWORD *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, 0x20u);
    if ( v16 )
    {
      v33[0] = 32;
      *(_QWORD *)&v33[1] = 128;
      v33[3] = 0;
      si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffff0000000000000000);
      FileInternal = (void *)CreateFileInternal(L"\\\\.\\MountPointManager", 0, 3u, 3, (__int64)v33, 1);
      if ( FileInternal == (void *)-1LL )
      {
        IsBrokeredCreateDirectoryWPresent();
        FileHandle = (HANDLE)-1LL;
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v16);
LABEL_52:
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v13);
        return 0;
      }
      else
      {
        FileHandle = FileInternal;
        for ( i = DeviceIoControl(FileInternal, 0x6D0008u, v13, NtPathName.Length + 24, v16, 0x20u, &BytesReturned, 0);
              ;
              i = DeviceIoControl(FileHandle, 0x6D0008u, v13, NtPathName.Length + 24, v26, v25, &BytesReturned, 0) )
        {
          v19 = i;
          if ( i || NtCurrentTeb()->LastErrorValue != 234 )
            break;
          v25 = *v16;
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v16);
          v26 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, v25);
          v16 = (DWORD *)v26;
          if ( !v26 )
          {
            CloseHandle(FileHandle);
            RtlSetLastWin32Error(8u);
            goto LABEL_52;
          }
        }
        CloseHandle(FileHandle);
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v13);
        if ( v19 )
        {
          for ( j = 0; j < v16[1]; ++j )
          {
            v21 = v16[6 * j + 3];
            v22 = v16[6 * j + 2];
            if ( (v21 == 96 || v21 == 98 && *(_WORD *)((char *)v16 + v22 + 96) == 92)
              && *(_WORD *)((char *)v16 + v22) == 92 )
            {
              v23 = *(_WORD *)((char *)v16 + v22 + 2);
              if ( (v23 == 63 || v23 == 92)
                && *(_WORD *)((char *)v16 + v22 + 4) == 63
                && *(_WORD *)((char *)v16 + v22 + 6) == 92
                && *(_WORD *)((char *)v16 + v22 + 8) == 86
                && *(_WORD *)((char *)v16 + v22 + 10) == 111
                && *(_WORD *)((char *)v16 + v22 + 12) == 108
                && *(_WORD *)((char *)v16 + v22 + 14) == 117
                && *(_WORD *)((char *)v16 + v22 + 16) == 109
                && *(_WORD *)((char *)v16 + v22 + 18) == 101
                && *(_WORD *)((char *)v16 + v22 + 20) == 123
                && *(_WORD *)((char *)v16 + v22 + 38) == 45
                && *(_WORD *)((char *)v16 + v22 + 48) == 45
                && *(_WORD *)((char *)v16 + v22 + 58) == 45
                && *(_WORD *)((char *)v16 + v22 + 68) == 45
                && *(_WORD *)((char *)v16 + v22 + 94) == 125
                && v21 == 96
                && v23 == 63 )
              {
                if ( (unsigned __int64)(2 * v3) >= 0x64 )
                {
                  *(_OWORD *)a2 = *(_OWORD *)((char *)v16 + v22);
                  *(_OWORD *)(a2 + 16) = *(_OWORD *)((char *)v16 + v22 + 16);
                  *(_OWORD *)(a2 + 32) = *(_OWORD *)((char *)v16 + v22 + 32);
                  *(_OWORD *)(a2 + 48) = *(_OWORD *)((char *)v16 + v22 + 48);
                  *(_OWORD *)(a2 + 64) = *(_OWORD *)((char *)v16 + v22 + 64);
                  *(_OWORD *)(a2 + 80) = *(_OWORD *)((char *)v16 + v22 + 80);
                  *(_WORD *)(a2 + 2) = 92;
                  *(_DWORD *)(a2 + 96) = 92;
                  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v16);
                  return 1;
                }
                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v16);
                v28 = 206;
                goto LABEL_49;
              }
            }
          }
        }
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v16);
        v28 = 87;
LABEL_49:
        RtlSetLastWin32Error(v28);
        return 0;
      }
    }
    else
    {
      RtlSetLastWin32Error(8u);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v13);
      return 0;
    }
  }
  else
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, NtPathName.Buffer);
    RtlSetLastWin32Error(8u);
    return 0;
  }
}

```

## disassembly

```asm
0x180047580  push    rbp
0x180047582  push    r12
0x180047584  push    r14
0x180047586  push    r15
0x180047588  lea     rbp, [rsp-1E8h]
0x180047590  sub     rsp, 2E8h
0x180047597  mov     rax, cs:__security_cookie
0x18004759e  xor     rax, rsp
0x1800475a1  mov     [rbp+200h+var_30], rax
0x1800475a8  xorps   xmm0, xmm0
0x1800475ab  mov     r15d, r8d
0x1800475ae  mov     r14, rdx
0x1800475b1  xor     r12d, r12d
0x1800475b4  movups  xmmword ptr [rsp+300h+ObjectAttributes.ObjectName], xmm0
0x1800475b9  xor     eax, eax
0x1800475bb  mov     [rsp+300h+FileHandle], r12
0x1800475c0  xor     r9d, r9d; DirectoryInfo
0x1800475c3  lea     rdx, [rsp+300h+NtPathName]; NtPathName
0x1800475c8  xor     r8d, r8d; NtFileNamePart
0x1800475cb  movups  xmmword ptr [rsp+300h+ObjectAttributes+1Ch], xmm0
0x1800475d0  movups  xmmword ptr [rsp+300h+NtPathName.Length], xmm0
0x1800475d5  movups  xmmword ptr [rsp+300h+ObjectAttributes.Length], xmm0
0x1800475da  movups  xmmword ptr [rbp+200h+IoStatusBlock], xmm0
0x1800475de  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x1800475e4  test    al, al
0x1800475e6  jz      loc_180047B30
0x1800475ec  movzx   ecx, [rsp+300h+NtPathName.Length]
0x1800475f1  mov     rdx, [rsp+300h+NtPathName.Buffer]
0x1800475f6  mov     eax, ecx
0x1800475f8  shr     rax, 1
0x1800475fb  cmp     word ptr [rdx+rax*2-2], 5Ch ; '\'
0x180047601  mov     [rsp+300h+arg_10], rbx
0x180047609  lea     r8, [rdx+rax*2]
0x18004760d  jnz     short loc_18004762B
0x18004760f  mov     [r8-2], r12w
0x180047614  mov     eax, 0FFFEh
0x180047619  movzx   ecx, [rsp+300h+NtPathName.Length]
0x18004761e  mov     rdx, [rsp+300h+NtPathName.Buffer]
0x180047623  add     cx, ax
0x180047626  mov     [rsp+300h+NtPathName.Length], cx
0x18004762b  cmp     cx, 4
0x18004762f  jb      short loc_18004765C
0x180047631  movzx   eax, cx
0x180047634  shr     rax, 1
0x180047637  cmp     word ptr [rdx+rax*2-2], 3Ah ; ':'
0x18004763d  jnz     short loc_18004765C
0x18004763f  movzx   ecx, word ptr [rdx+rax*2-4]; C
0x180047644  call    cs:__imp_toupper
0x18004764a  movzx   edx, [rsp+300h+NtPathName.Length]
0x18004764f  mov     rcx, [rsp+300h+NtPathName.Buffer]
0x180047654  shr     rdx, 1
0x180047657  mov     [rcx+rdx*2-4], ax
0x18004765c  lea     rax, [rsp+300h+NtPathName]
0x180047661  mov     [rsp+300h+OpenOptions], 10h; OpenOptions
0x180047669  xorps   xmm0, xmm0
0x18004766c  mov     [rsp+300h+ObjectAttributes.ObjectName], rax
0x180047671  lea     r9, [rbp+200h+IoStatusBlock]; IoStatusBlock
0x180047675  mov     [rsp+300h+ObjectAttributes.Length], 30h ; '0'
0x18004767d  lea     r8, [rsp+300h+ObjectAttributes]; ObjectAttributes
0x180047682  mov     [rsp+300h+ObjectAttributes.RootDirectory], r12
0x180047687  mov     edx, 100080h; DesiredAccess
0x18004768c  mov     [rsp+300h+ObjectAttributes.Attributes], 40h ; '@'
0x180047694  lea     rcx, [rsp+300h+FileHandle]; FileHandle
0x180047699  mov     [rsp+300h+ShareAccess], 3; ShareAccess
0x1800476a1  movdqu  xmmword ptr [rbp+200h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800476a6  call    cs:__imp_NtOpenFile
0x1800476ac  mov     ebx, eax
0x1800476ae  test    eax, eax
0x1800476b0  js      loc_180047B42
0x1800476b6  mov     rcx, [rsp+300h+FileHandle]; hDevice
0x1800476bb  lea     rax, [rsp+300h+BytesReturned]
0x1800476c0  mov     [rsp+300h+lpOverlapped], r12; lpOverlapped
0x1800476c5  xor     r9d, r9d; nInBufferSize
0x1800476c8  mov     [rsp+300h+lpBytesReturned], rax; lpBytesReturned
0x1800476cd  xor     r8d, r8d; lpInBuffer
0x1800476d0  lea     rax, [rbp+200h+OutBuffer]
0x1800476d4  mov     [rsp+300h+OpenOptions], 208h; nOutBufferSize
0x1800476dc  mov     edx, 4D0008h; dwIoControlCode
0x1800476e1  mov     qword ptr [rsp+300h+ShareAccess], rax; lpOutBuffer
0x1800476e6  call    DeviceIoControl
0x1800476eb  mov     rcx, [rsp+300h+FileHandle]; Handle
0x1800476f0  mov     ebx, eax
0x1800476f2  call    cs:__imp_NtClose
0x1800476f8  mov     rcx, gs:60h
0x180047701  xor     edx, edx; Flags
0x180047703  mov     r8, [rsp+300h+NtPathName.Buffer]; P
0x180047708  mov     rcx, [rcx+30h]; HeapHandle
0x18004770c  call    cs:__imp_RtlFreeHeap
0x180047712  test    ebx, ebx
0x180047714  jz      loc_180047B29
0x18004771a  movzx   eax, [rbp+200h+OutBuffer]
0x18004771e  mov     [rsp+300h+NtPathName.Length], ax
0x180047723  add     ax, 2
0x180047727  movzx   r8d, ax; Size
0x18004772b  mov     [rsp+300h+NtPathName.MaximumLength], r8w
0x180047731  mov     rcx, gs:60h
0x18004773a  mov     edx, cs:KernelBaseGlobalData; Flags
0x180047740  mov     rcx, [rcx+30h]; HeapHandle
0x180047744  call    cs:__imp_RtlAllocateHeap
0x18004774a  mov     [rsp+300h+NtPathName.Buffer], rax
0x18004774f  test    rax, rax
0x180047752  jz      loc_180047B1E
0x180047758  movzx   r8d, [rbp+200h+OutBuffer]; Size
0x18004775d  lea     rdx, [rbp+200h+Src]; Src
0x180047761  mov     rcx, rax; void *
0x180047764  mov     [rsp+300h+var_20], rdi
0x18004776c  call    memcpy_0
0x180047771  movzx   edx, [rsp+300h+NtPathName.Length]
0x180047776  mov     rax, [rsp+300h+NtPathName.Buffer]
0x18004777b  shr     rdx, 1
0x18004777e  mov     [rax+rdx*2], r12w
0x180047783  mov     rcx, gs:60h
0x18004778c  movzx   r8d, [rsp+300h+NtPathName.Length]
0x180047792  mov     edx, cs:KernelBaseGlobalData; Flags
0x180047798  add     r8, 18h; Size
0x18004779c  mov     rcx, [rcx+30h]; HeapHandle
0x1800477a0  call    cs:__imp_RtlAllocateHeap
0x1800477a6  mov     rdi, rax
0x1800477a9  test    rax, rax
0x1800477ac  jz      loc_180047C19
0x1800477b2  xor     eax, eax
0x1800477b4  lea     rcx, [rdi+18h]; void *
0x1800477b8  xorps   xmm0, xmm0
0x1800477bb  movups  xmmword ptr [rdi], xmm0
0x1800477be  mov     [rdi+10h], rax
0x1800477c2  mov     dword ptr [rdi+10h], 18h
0x1800477c9  movzx   eax, [rsp+300h+NtPathName.Length]
0x1800477ce  mov     [rdi+14h], ax
0x1800477d2  mov     r8d, eax; Size
0x1800477d5  mov     rdx, [rsp+300h+NtPathName.Buffer]; Src
0x1800477da  call    memcpy_0
0x1800477df  mov     rcx, gs:60h
0x1800477e8  xor     edx, edx; Flags
0x1800477ea  mov     r8, [rsp+300h+NtPathName.Buffer]; P
0x1800477ef  mov     rcx, [rcx+30h]; HeapHandle
0x1800477f3  call    cs:__imp_RtlFreeHeap
0x1800477f9  mov     rcx, gs:60h
0x180047802  mov     r8d, 20h ; ' '; Size
0x180047808  mov     edx, cs:KernelBaseGlobalData; Flags
0x18004780e  mov     rcx, [rcx+30h]; HeapHandle
0x180047812  call    cs:__imp_RtlAllocateHeap
0x180047818  mov     rbx, rax
0x18004781b  test    rax, rax
0x18004781e  jz      loc_180047B9D
0x180047824  movdqa  xmm0, cs:__xmm@ffffffffffffffff0000000000000000
0x18004782c  lea     rax, [rbp+200h+var_270]
0x180047830  mov     r9d, 3
0x180047836  mov     [rsp+300h+OpenOptions], 1; int
0x18004783e  mov     r8d, r9d
0x180047841  mov     [rsp+300h+arg_18], rsi
0x180047849  xor     edx, edx
0x18004784b  mov     dword ptr [rbp+200h+var_270], 20h ; ' '
0x180047852  lea     rcx, FileName; "\\\\.\\MountPointManager"
0x180047859  mov     qword ptr [rbp+200h+var_270+4], 80h
0x180047861  mov     [rbp+200h+var_264], r12d
0x180047865  movdqu  [rbp+200h+var_260], xmm0
0x18004786a  mov     qword ptr [rsp+300h+ShareAccess], rax; __int64
0x18004786f  call    CreateFileInternal
0x180047874  mov     rsi, rax
0x180047877  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004787b  jz      loc_180047BC7
0x180047881  mov     [rsp+300h+lpOverlapped], r12; lpOverlapped
0x180047886  mov     rcx, rsi; hDevice
0x180047889  mov     [rsp+300h+FileHandle], rax
0x18004788e  lea     rax, [rsp+300h+BytesReturned]
0x180047893  mov     [rsp+300h+lpBytesReturned], rax; lpBytesReturned
0x180047898  mov     [rsp+300h+OpenOptions], 20h ; ' '; nOutBufferSize
0x1800478a0  movzx   r9d, [rsp+300h+NtPathName.Length]
0x1800478a6  mov     r8, rdi; lpInBuffer
0x1800478a9  add     r9d, 18h; nInBufferSize
0x1800478ad  mov     qword ptr [rsp+300h+ShareAccess], rbx; lpOutBuffer
0x1800478b2  mov     edx, 6D0008h; dwIoControlCode
0x1800478b7  call    DeviceIoControl
0x1800478bc  mov     esi, eax
0x1800478be  test    eax, eax
0x1800478c0  jz      loc_180047A99
0x1800478c6  mov     rcx, [rsp+300h+FileHandle]; hObject
0x1800478cb  call    CloseHandle
0x1800478d0  mov     rcx, gs:60h
0x1800478d9  mov     r8, rdi; P
0x1800478dc  xor     edx, edx; Flags
0x1800478de  mov     rcx, [rcx+30h]; HeapHandle
0x1800478e2  call    cs:__imp_RtlFreeHeap
0x1800478e8  test    esi, esi
0x1800478ea  jz      loc_180047B73
0x1800478f0  mov     edx, r12d
0x1800478f3  cmp     edx, [rbx+4]
0x1800478f6  jnb     loc_180047B73
0x1800478fc  mov     eax, edx
0x1800478fe  lea     rcx, [rax+rax*2]
0x180047902  movzx   r8d, word ptr [rbx+rcx*8+0Ch]
0x180047908  mov     eax, [rbx+rcx*8+8]
0x18004790c  cmp     r8w, 60h ; '`'
0x180047911  jnz     loc_180047B0C
0x180047917  cmp     word ptr [rax+rbx], 5Ch ; '\'
0x18004791c  jnz     loc_180047B17
0x180047922  movzx   ecx, word ptr [rax+rbx+2]
0x180047927  cmp     cx, 3Fh ; '?'
0x18004792b  jnz     loc_180047C57
0x180047931  cmp     word ptr [rax+rbx+4], 3Fh ; '?'
0x180047937  jnz     loc_180047B17
0x18004793d  cmp     word ptr [rax+rbx+6], 5Ch ; '\'
0x180047943  jnz     loc_180047B17
0x180047949  cmp     word ptr [rax+rbx+8], 56h ; 'V'
0x18004794f  jnz     loc_180047B17
0x180047955  cmp     word ptr [rax+rbx+0Ah], 6Fh ; 'o'
0x18004795b  jnz     loc_180047B17
0x180047961  cmp     word ptr [rax+rbx+0Ch], 6Ch ; 'l'
0x180047967  jnz     loc_180047B17
0x18004796d  cmp     word ptr [rax+rbx+0Eh], 75h ; 'u'
0x180047973  jnz     loc_180047B17
0x180047979  cmp     word ptr [rax+rbx+10h], 6Dh ; 'm'
0x18004797f  jnz     loc_180047B17
0x180047985  cmp     word ptr [rax+rbx+12h], 65h ; 'e'
0x18004798b  jnz     loc_180047B17
0x180047991  cmp     word ptr [rax+rbx+14h], 7Bh ; '{'
0x180047997  jnz     loc_180047B17
0x18004799d  cmp     word ptr [rax+rbx+26h], 2Dh ; '-'
0x1800479a3  jnz     loc_180047B17
0x1800479a9  cmp     word ptr [rax+rbx+30h], 2Dh ; '-'
0x1800479af  jnz     loc_180047B17
0x1800479b5  cmp     word ptr [rax+rbx+3Ah], 2Dh ; '-'
0x1800479bb  jnz     loc_180047B17
0x1800479c1  cmp     word ptr [rax+rbx+44h], 2Dh ; '-'
0x1800479c7  jnz     loc_180047B17
0x1800479cd  cmp     word ptr [rax+rbx+5Eh], 7Dh ; '}'
0x1800479d3  jnz     loc_180047B17
0x1800479d9  cmp     r8w, 60h ; '`'
0x1800479de  jnz     loc_180047B17
0x1800479e4  cmp     cx, 3Fh ; '?'
0x1800479e8  jnz     loc_180047B17
0x1800479ee  mov     rcx, r15
0x1800479f1  xor     edx, edx; Flags
0x1800479f3  add     rcx, rcx
0x1800479f6  mov     r8, rbx; P
0x1800479f9  cmp     rcx, 64h ; 'd'
0x1800479fd  jb      loc_180047C66
0x180047a03  movups  xmm0, xmmword ptr [rax+rbx]
0x180047a07  mov     ecx, 5Ch ; '\'
0x180047a0c  movups  xmmword ptr [r14], xmm0
0x180047a10  movups  xmm1, xmmword ptr [rax+rbx+10h]
0x180047a15  movups  xmmword ptr [r14+10h], xmm1
0x180047a1a  movups  xmm0, xmmword ptr [rax+rbx+20h]
0x180047a1f  movups  xmmword ptr [r14+20h], xmm0
0x180047a24  movups  xmm1, xmmword ptr [rax+rbx+30h]
0x180047a29  movups  xmmword ptr [r14+30h], xmm1
0x180047a2e  movups  xmm0, xmmword ptr [rax+rbx+40h]
0x180047a33  movups  xmmword ptr [r14+40h], xmm0
0x180047a38  movups  xmm1, xmmword ptr [rax+rbx+50h]
0x180047a3d  movups  xmmword ptr [r14+50h], xmm1
0x180047a42  mov     [r14+2], cx
0x180047a47  mov     [r14+60h], ecx
0x180047a4b  mov     rcx, gs:60h
0x180047a54  mov     rcx, [rcx+30h]; HeapHandle
0x180047a58  call    cs:__imp_RtlFreeHeap
0x180047a5e  mov     eax, 1
0x180047a63  mov     rsi, [rsp+300h+arg_18]
0x180047a6b  mov     rdi, [rsp+300h+var_20]
0x180047a73  mov     rbx, [rsp+300h+arg_10]
0x180047a7b  mov     rcx, [rbp+200h+var_30]
0x180047a82  xor     rcx, rsp; StackCookie
0x180047a85  call    __security_check_cookie
0x180047a8a  add     rsp, 2E8h
0x180047a91  pop     r15
0x180047a93  pop     r14
0x180047a95  pop     r12
0x180047a97  pop     rbp
0x180047a98  retn
0x180047a99  mov     ecx, gs:68h
0x180047aa1  cmp     ecx, 0EAh
0x180047aa7  jnz     loc_1800478C6
0x180047aad  mov     rcx, gs:60h
0x180047ab6  mov     r8, rbx; P
0x180047ab9  mov     esi, [rbx]
0x180047abb  xor     edx, edx; Flags
0x180047abd  mov     rcx, [rcx+30h]; HeapHandle
0x180047ac1  call    cs:__imp_RtlFreeHeap
0x180047ac7  mov     rcx, gs:60h
0x180047ad0  mov     r8d, esi; Size
0x180047ad3  mov     edx, cs:KernelBaseGlobalData; Flags
0x180047ad9  mov     rcx, [rcx+30h]; HeapHandle
0x180047add  call    cs:__imp_RtlAllocateHeap
0x180047ae3  mov     rcx, [rsp+300h+FileHandle]; hObject
0x180047ae8  mov     rbx, rax
0x180047aeb  test    rax, rax
0x180047aee  jz      loc_180047C45
0x180047af4  mov     [rsp+300h+lpOverlapped], r12
0x180047af9  lea     rax, [rsp+300h+BytesReturned]
0x180047afe  mov     [rsp+300h+lpBytesReturned], rax
0x180047b03  mov     [rsp+300h+OpenOptions], esi
0x180047b07  jmp     loc_1800478A0
0x180047b0c  cmp     r8w, 62h ; 'b'
0x180047b11  jz      loc_180047C08
0x180047b17  inc     edx
0x180047b19  jmp     loc_1800478F3
0x180047b1e  mov     ecx, 8; LastError
0x180047b23  call    cs:__imp_RtlSetLastWin32Error
0x180047b29  xor     eax, eax
0x180047b2b  jmp     loc_180047A73
0x180047b30  mov     ecx, 3; LastError
  ... truncated ...
```
