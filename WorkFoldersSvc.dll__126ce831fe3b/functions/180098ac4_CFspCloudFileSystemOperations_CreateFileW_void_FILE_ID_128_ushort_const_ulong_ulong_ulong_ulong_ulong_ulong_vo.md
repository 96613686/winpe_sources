# CFspCloudFileSystemOperations::CreateFileW(void *,_FILE_ID_128,ushort const *,ulong,ulong,ulong,ulong,ulong,ulong,void * *)

- ea: `0x180098ac4`
- end: `0x180098ee4`
- name: `?CreateFileW@CFspCloudFileSystemOperations@@SAJPEAXU_FILE_ID_128@@PEBGKKKKKKPEAPEAX@Z`
- size: `1056`
- prototype: `static int(void *, struct _FILE_ID_128 *__struct_ptr, const unsigned __int16 *, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, void **)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18008ce50`
- `0x18008edcc`

## callees

- `0x180007e10`
- `0x180008080`
- `0x180011314`
- `0x180098ac4`
- `0x18009adc8`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180098d8a`
- `ntdll!RtlInitUnicodeString` at `0x180098d8a`
- `ntdll!NtFsControlFile` at `0x180098d48`
- `ntdll!NtFsControlFile` at `0x180098e6a`
- `ntdll!NtFsControlFile` at `0x180098d48`
- `ntdll!NtFsControlFile` at `0x180098e6a`
- `ntdll!NtCreateFile` at `0x180098cc1`
- `ntdll!NtCreateFile` at `0x180098df6`
- `ntdll!NtCreateFile` at `0x180098cc1`
- `ntdll!NtCreateFile` at `0x180098df6`
- `ntdll!NtClose` at `0x180098ea3`
- `ntdll!NtClose` at `0x180098eba`
- `ntdll!NtClose` at `0x180098ea3`
- `ntdll!NtClose` at `0x180098eba`

## string_xrefs

- `0x180098b70`: `CFspCloudFileSystemOperations::CreateFileW`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CFspCloudFileSystemOperations::CreateFileW(
        void *a1,
        WCHAR *a2,
        const unsigned __int16 *a3,
        ACCESS_MASK a4,
        unsigned int a5,
        ULONG ShareAccess,
        ULONG CreateOptions,
        ULONG CreateDisposition,
        unsigned int a9,
        void **a10)
{
  void *v12; // rdx
  _DWORD *v13; // rax
  char v14; // cl
  __int16 v15; // ax
  int v16; // ebx
  unsigned int v17; // eax
  __int16 v18; // ax
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  int v23; // [rsp+60h] [rbp-91h] BYREF
  int v24; // [rsp+64h] [rbp-8Dh]
  char v25; // [rsp+68h] [rbp-89h]
  const char *v26; // [rsp+70h] [rbp-81h]
  __int64 v27; // [rsp+78h] [rbp-79h]
  struct _UNICODE_STRING InputBuffer; // [rsp+80h] [rbp-71h] BYREF
  __int64 v29; // [rsp+90h] [rbp-61h]
  ACCESS_MASK DesiredAccess; // [rsp+98h] [rbp-59h]
  void *FileHandle; // [rsp+A0h] [rbp-51h] BYREF
  HANDLE Handle; // [rsp+A8h] [rbp-49h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B0h] [rbp-41h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+E0h] [rbp-11h] BYREF

  DesiredAccess = a4;
  v12 = a1;
  *(_QWORD *)&InputBuffer.Length = a1;
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 16, WPP_e0db9af3e7d6384a3fbe331b6c49ab76_Traceguids);
    v13 = WPP_GLOBAL_Control;
    v12 = *(void **)&InputBuffer.Length;
    LOBYTE(a4) = DesiredAccess;
  }
  if ( (v13[17] & 0x100) == 0 || (v14 = 1, *((_BYTE *)v13 + 65) < 6u) )
    v14 = 0;
  v23 = 0;
  v24 = 364;
  v25 = v14;
  v26 = "CFspCloudFileSystemOperations::CreateFileW";
  v27 = 0;
  FileHandle = 0;
  Handle = 0;
  IoStatusBlock = 0;
  if ( a10 )
    *a10 = 0;
  v15 = 371;
  if ( !v12 || (LOWORD(v24) = 371, v23 = 0, v15 = 372, !a3) )
  {
    v16 = -2147024809;
    v23 = -2147024809;
    HIWORD(v24) = v15;
    goto LABEL_34;
  }
  v23 = 0;
  LOWORD(v24) = 372;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
  {
    WPP_SF_iiSDDDDDD(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      17,
      (unsigned int)WPP_e0db9af3e7d6384a3fbe331b6c49ab76_Traceguids,
      *((_QWORD *)a2 + 1),
      *(_QWORD *)a2,
      (__int64)a3,
      a4);
    v12 = *(void **)&InputBuffer.Length;
  }
  *(_QWORD *)&InputBuffer.Length = 1048592;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 2;
  InputBuffer.Buffer = a2;
  ObjectAttributes.RootDirectory = v12;
  ObjectAttributes.ObjectName = &InputBuffer;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v17 = NtCreateFile(&FileHandle, 0x100000u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 7u, 1u, 0x2021u, 0, 0);
  if ( v17 == -1073741811 )
    v17 = -1073741766;
  v16 = HRESULTFromNTSTATUS(v17);
  v23 = v16;
  v18 = 416;
  if ( v16 < 0 )
    goto LABEL_20;
  LOWORD(v24) = 416;
  if ( a9 )
  {
    InputBuffer = 0;
    v29 = 0;
    *(_DWORD *)&InputBuffer.Length = a9;
    v19 = NtFsControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x900FCu, &InputBuffer, 0x18u, 0, 0);
    v16 = HRESULTFromNTSTATUS(v19);
    v23 = v16;
    v18 = 434;
    if ( v16 < 0 )
      goto LABEL_20;
    LOWORD(v24) = 434;
  }
  InputBuffer = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  RtlInitUnicodeString(&InputBuffer, a3);
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = FileHandle;
  ObjectAttributes.Attributes = 2;
  ObjectAttributes.ObjectName = &InputBuffer;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v20 = NtCreateFile(
          &Handle,
          DesiredAccess,
          &ObjectAttributes,
          &IoStatusBlock,
          0,
          0x80u,
          ShareAccess,
          CreateDisposition,
          CreateOptions,
          0,
          0);
  v16 = HRESULTFromNTSTATUS(v20);
  v23 = v16;
  v18 = 460;
  if ( v16 >= 0 )
  {
    LOWORD(v24) = 460;
    if ( !a9 )
    {
LABEL_28:
      *a10 = Handle;
      goto LABEL_29;
    }
    InputBuffer = 0;
    v29 = 0;
    *(_DWORD *)&InputBuffer.Length = a9;
    v21 = NtFsControlFile(Handle, 0, 0, 0, &IoStatusBlock, 0x900FCu, &InputBuffer, 0x18u, 0, 0);
    v16 = HRESULTFromNTSTATUS(v21);
    v23 = v16;
    v18 = 478;
    if ( v16 >= 0 )
    {
      LOWORD(v24) = 478;
      goto LABEL_28;
    }
  }
LABEL_20:
  HIWORD(v24) = v18;
LABEL_29:
  if ( FileHandle )
  {
    NtClose(FileHandle);
    v16 = v23;
  }
  if ( v16 < 0 && Handle )
  {
    NtClose(Handle);
    v16 = v23;
  }
LABEL_34:
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v23);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x180098ac4  push    rbp
0x180098ac6  push    rbx
0x180098ac7  push    rsi
0x180098ac8  push    rdi
0x180098ac9  push    r12
0x180098acb  push    r13
0x180098acd  push    r14
0x180098acf  push    r15
0x180098ad1  lea     rbp, [rsp-7]
0x180098ad6  sub     rsp, 0F8h
0x180098add  mov     [rbp+3Fh+DesiredAccess], r9d
0x180098ae1  mov     r14, r8
0x180098ae4  mov     rbx, rdx
0x180098ae7  mov     rdx, rcx
0x180098aea  mov     qword ptr [rbp+3Fh+InputBuffer], rcx
0x180098aee  mov     rsi, [rbp+3Fh+arg_48]
0x180098af5  lea     r11, WPP_GLOBAL_Control
0x180098afc  mov     r10d, 100h
0x180098b02  mov     rax, cs:WPP_GLOBAL_Control
0x180098b09  cmp     rax, r11
0x180098b0c  jz      short loc_180098B4B
0x180098b0e  test    [rax+44h], r10d
0x180098b12  jz      short loc_180098B4B
0x180098b14  cmp     byte ptr [rax+41h], 6
0x180098b18  jb      short loc_180098B4B
0x180098b1a  mov     edx, 10h
0x180098b1f  lea     r8, WPP_e0db9af3e7d6384a3fbe331b6c49ab76_Traceguids
0x180098b26  mov     rcx, [rax+38h]
0x180098b2a  call    WPP_SF_
0x180098b2f  mov     rax, cs:WPP_GLOBAL_Control
0x180098b36  mov     rdx, qword ptr [rbp+3Fh+InputBuffer]
0x180098b3a  mov     r9d, [rbp+3Fh+DesiredAccess]
0x180098b3e  mov     r10d, 100h
0x180098b44  lea     r11, WPP_GLOBAL_Control
0x180098b4b  xor     r8d, r8d
0x180098b4e  test    [rax+44h], r10d
0x180098b52  jz      short loc_180098B5C
0x180098b54  cmp     byte ptr [rax+41h], 6
0x180098b58  mov     cl, 1
0x180098b5a  jnb     short loc_180098B5F
0x180098b5c  mov     cl, r8b
0x180098b5f  mov     [rsp+130h+var_D0], r8d
0x180098b64  mov     [rsp+130h+var_CC], 16Ch
0x180098b6c  mov     [rsp+130h+var_C8], cl
0x180098b70  lea     rax, aCfspcloudfiles_0; "CFspCloudFileSystemOperations::CreateFi"...
0x180098b77  mov     [rsp+130h+var_C0], rax
0x180098b7c  mov     [rbp+3Fh+var_B8], r8
0x180098b80  mov     [rbp+3Fh+FileHandle], r8
0x180098b84  mov     [rbp+3Fh+Handle], r8
0x180098b88  xorps   xmm0, xmm0
0x180098b8b  movups  xmmword ptr [rbp+3Fh+IoStatusBlock], xmm0
0x180098b8f  test    rsi, rsi
0x180098b92  jz      short loc_180098B97
0x180098b94  mov     [rsi], r8
0x180098b97  mov     eax, [rsp+130h+var_D0]
0x180098b9b  mov     [rsp+130h+var_D0], eax
0x180098b9f  mov     eax, 173h
0x180098ba4  test    rdx, rdx
0x180098ba7  jnz     short loc_180098BBC
0x180098ba9  mov     ebx, 80070057h
0x180098bae  mov     [rsp+130h+var_D0], ebx
0x180098bb2  mov     word ptr [rsp+130h+var_CC+2], ax
0x180098bb7  jmp     loc_180098EC4
0x180098bbc  mov     [rsp+130h+var_D0], r8d
0x180098bc1  mov     word ptr [rsp+130h+var_CC], ax
0x180098bc6  mov     [rsp+130h+var_D0], r8d
0x180098bcb  mov     eax, 174h
0x180098bd0  test    r14, r14
0x180098bd3  jz      short loc_180098BA9
0x180098bd5  mov     [rsp+130h+var_D0], r8d
0x180098bda  mov     word ptr [rsp+130h+var_CC], ax
0x180098bdf  mov     edi, [rbp+3Fh+arg_40]
0x180098be5  mov     r15d, [rbp+3Fh+arg_38]
0x180098bec  mov     r12d, [rbp+3Fh+arg_30]
0x180098bf0  mov     r13d, [rbp+3Fh+arg_28]
0x180098bf4  mov     rcx, cs:WPP_GLOBAL_Control
0x180098bfb  cmp     rcx, r11
0x180098bfe  jz      short loc_180098C51
0x180098c00  test    [rcx+44h], r10d
0x180098c04  jz      short loc_180098C51
0x180098c06  cmp     byte ptr [rcx+41h], 4
0x180098c0a  jb      short loc_180098C51
0x180098c0c  mov     edx, 11h
0x180098c11  mov     [rsp+130h+var_D8], edi
0x180098c15  mov     [rsp+130h+EaLength], r15d
0x180098c1a  mov     dword ptr [rsp+130h+EaBuffer], r12d
0x180098c1f  mov     [rsp+130h+CreateOptions], r13d
0x180098c24  mov     [rsp+130h+ShareAccess], r9d
0x180098c29  mov     qword ptr [rsp+130h+FileAttributes], r14
0x180098c2e  mov     rax, [rbx]
0x180098c31  mov     [rsp+130h+AllocationSize], rax
0x180098c36  mov     r9, [rbx+8]
0x180098c3a  lea     r8, WPP_e0db9af3e7d6384a3fbe331b6c49ab76_Traceguids
0x180098c41  mov     rcx, [rcx+38h]
0x180098c45  call    WPP_SF_iiSDDDDDD
0x180098c4a  mov     rdx, qword ptr [rbp+3Fh+InputBuffer]
0x180098c4e  xor     r8d, r8d
0x180098c51  mov     qword ptr [rbp+3Fh+InputBuffer], 100010h
0x180098c59  mov     qword ptr [rbp+3Fh+ObjectAttributes.Length], 30h ; '0'
0x180098c61  mov     qword ptr [rbp+3Fh+ObjectAttributes.Attributes], 2
0x180098c69  mov     qword ptr [rbp+3Fh+InputBuffer+8], rbx
0x180098c6d  mov     [rbp+3Fh+ObjectAttributes.RootDirectory], rdx
0x180098c71  lea     rax, [rbp+3Fh+InputBuffer]
0x180098c75  mov     [rbp+3Fh+ObjectAttributes.ObjectName], rax
0x180098c79  xorps   xmm0, xmm0
0x180098c7c  movdqu  xmmword ptr [rbp+3Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x180098c81  mov     [rsp+130h+EaLength], r8d; EaLength
0x180098c86  mov     [rsp+130h+EaBuffer], r8; EaBuffer
0x180098c8b  mov     [rsp+130h+CreateOptions], 2021h; CreateOptions
0x180098c93  mov     [rsp+130h+CreateDisposition], 1; CreateDisposition
0x180098c9b  mov     [rsp+130h+ShareAccess], 7; ShareAccess
0x180098ca3  mov     [rsp+130h+FileAttributes], 80h; FileAttributes
0x180098cab  mov     [rsp+130h+AllocationSize], r8; AllocationSize
0x180098cb0  lea     r9, [rbp+3Fh+IoStatusBlock]; IoStatusBlock
0x180098cb4  lea     r8, [rbp+3Fh+ObjectAttributes]; ObjectAttributes
0x180098cb8  mov     edx, 100000h; DesiredAccess
0x180098cbd  lea     rcx, [rbp+3Fh+FileHandle]; FileHandle
0x180098cc1  call    cs:__imp_NtCreateFile
0x180098cc7  mov     ecx, 0C000003Ah
0x180098ccc  cmp     eax, 0C000000Dh
0x180098cd1  cmovz   eax, ecx
0x180098cd4  mov     ecx, eax
0x180098cd6  call    HRESULTFromNTSTATUS
0x180098cdb  mov     ebx, eax
0x180098cdd  mov     [rsp+130h+var_D0], eax
0x180098ce1  mov     [rsp+130h+var_D0], eax
0x180098ce5  test    eax, eax
0x180098ce7  mov     eax, 1A0h
0x180098cec  jns     short loc_180098CF8
0x180098cee  mov     word ptr [rsp+130h+var_CC+2], ax
0x180098cf3  jmp     loc_180098E9A
0x180098cf8  mov     word ptr [rsp+130h+var_CC], ax
0x180098cfd  test    edi, edi
0x180098cff  jz      short loc_180098D6D
0x180098d01  xorps   xmm0, xmm0
0x180098d04  xor     eax, eax
0x180098d06  movups  [rbp+3Fh+InputBuffer], xmm0
0x180098d0a  mov     [rbp+3Fh+var_A0], rax
0x180098d0e  mov     dword ptr [rbp+3Fh+InputBuffer], edi
0x180098d11  mov     dword ptr [rsp+130h+EaBuffer], eax; OutputBufferLength
0x180098d15  mov     qword ptr [rsp+130h+CreateOptions], rax; OutputBuffer
0x180098d1a  mov     [rsp+130h+CreateDisposition], 18h; InputBufferLength
0x180098d22  lea     rax, [rbp+3Fh+InputBuffer]
0x180098d26  mov     qword ptr [rsp+130h+ShareAccess], rax; InputBuffer
0x180098d2b  mov     [rsp+130h+FileAttributes], 900FCh; FsControlCode
0x180098d33  lea     rax, [rbp+3Fh+IoStatusBlock]
0x180098d37  mov     [rsp+130h+AllocationSize], rax; IoStatusBlock
0x180098d3c  xor     r9d, r9d; ApcContext
0x180098d3f  xor     r8d, r8d; ApcRoutine
0x180098d42  xor     edx, edx; Event
0x180098d44  mov     rcx, [rbp+3Fh+FileHandle]; FileHandle
0x180098d48  call    cs:__imp_NtFsControlFile
0x180098d4e  mov     ecx, eax
0x180098d50  call    HRESULTFromNTSTATUS
0x180098d55  mov     ebx, eax
0x180098d57  mov     [rsp+130h+var_D0], eax
0x180098d5b  mov     [rsp+130h+var_D0], eax
0x180098d5f  test    eax, eax
0x180098d61  mov     eax, 1B2h
0x180098d66  js      short loc_180098CEE
0x180098d68  mov     word ptr [rsp+130h+var_CC], ax
0x180098d6d  xorps   xmm0, xmm0
0x180098d70  movups  [rbp+3Fh+InputBuffer], xmm0
0x180098d74  xorps   xmm1, xmm1
0x180098d77  movups  xmmword ptr [rbp+3Fh+ObjectAttributes.Length], xmm1
0x180098d7b  movups  xmmword ptr [rbp+3Fh+ObjectAttributes.ObjectName], xmm1
0x180098d7f  movups  xmmword ptr [rbp+3Fh+ObjectAttributes.SecurityDescriptor], xmm1
0x180098d83  mov     rdx, r14; SourceString
0x180098d86  lea     rcx, [rbp+3Fh+InputBuffer]; DestinationString
0x180098d8a  call    cs:__imp_RtlInitUnicodeString
0x180098d90  mov     [rbp+3Fh+ObjectAttributes.Length], 30h ; '0'
0x180098d97  mov     rax, [rbp+3Fh+FileHandle]
0x180098d9b  mov     [rbp+3Fh+ObjectAttributes.RootDirectory], rax
0x180098d9f  mov     [rbp+3Fh+ObjectAttributes.Attributes], 2
0x180098da6  lea     rax, [rbp+3Fh+InputBuffer]
0x180098daa  mov     [rbp+3Fh+ObjectAttributes.ObjectName], rax
0x180098dae  xorps   xmm0, xmm0
0x180098db1  movdqu  xmmword ptr [rbp+3Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x180098db6  mov     [rsp+130h+EaLength], 0; EaLength
0x180098dbe  mov     [rsp+130h+EaBuffer], 0; EaBuffer
0x180098dc7  mov     [rsp+130h+CreateOptions], r12d; CreateOptions
0x180098dcc  mov     [rsp+130h+CreateDisposition], r15d; CreateDisposition
0x180098dd1  mov     [rsp+130h+ShareAccess], r13d; ShareAccess
0x180098dd6  mov     [rsp+130h+FileAttributes], 80h; FileAttributes
0x180098dde  mov     [rsp+130h+AllocationSize], 0; AllocationSize
0x180098de7  lea     r9, [rbp+3Fh+IoStatusBlock]; IoStatusBlock
0x180098deb  lea     r8, [rbp+3Fh+ObjectAttributes]; ObjectAttributes
0x180098def  mov     edx, [rbp+3Fh+DesiredAccess]; DesiredAccess
0x180098df2  lea     rcx, [rbp+3Fh+Handle]; FileHandle
0x180098df6  call    cs:__imp_NtCreateFile
0x180098dfc  mov     ecx, eax
0x180098dfe  call    HRESULTFromNTSTATUS
0x180098e03  mov     ebx, eax
0x180098e05  mov     [rsp+130h+var_D0], eax
0x180098e09  mov     [rsp+130h+var_D0], eax
0x180098e0d  test    eax, eax
0x180098e0f  mov     eax, 1CCh
0x180098e14  js      loc_180098CEE
0x180098e1a  mov     word ptr [rsp+130h+var_CC], ax
0x180098e1f  test    edi, edi
0x180098e21  jz      short loc_180098E93
0x180098e23  xorps   xmm0, xmm0
0x180098e26  xor     eax, eax
0x180098e28  movups  [rbp+3Fh+InputBuffer], xmm0
0x180098e2c  mov     [rbp+3Fh+var_A0], rax
0x180098e30  mov     dword ptr [rbp+3Fh+InputBuffer], edi
0x180098e33  mov     dword ptr [rsp+130h+EaBuffer], eax; OutputBufferLength
0x180098e37  mov     qword ptr [rsp+130h+CreateOptions], rax; OutputBuffer
0x180098e3c  mov     [rsp+130h+CreateDisposition], 18h; InputBufferLength
0x180098e44  lea     rax, [rbp+3Fh+InputBuffer]
0x180098e48  mov     qword ptr [rsp+130h+ShareAccess], rax; InputBuffer
0x180098e4d  mov     [rsp+130h+FileAttributes], 900FCh; FsControlCode
0x180098e55  lea     rax, [rbp+3Fh+IoStatusBlock]
0x180098e59  mov     [rsp+130h+AllocationSize], rax; IoStatusBlock
0x180098e5e  xor     r9d, r9d; ApcContext
0x180098e61  xor     r8d, r8d; ApcRoutine
0x180098e64  xor     edx, edx; Event
0x180098e66  mov     rcx, [rbp+3Fh+Handle]; FileHandle
0x180098e6a  call    cs:__imp_NtFsControlFile
0x180098e70  mov     ecx, eax
0x180098e72  call    HRESULTFromNTSTATUS
0x180098e77  mov     ebx, eax
0x180098e79  mov     [rsp+130h+var_D0], eax
0x180098e7d  mov     [rsp+130h+var_D0], eax
0x180098e81  test    eax, eax
0x180098e83  mov     eax, 1DEh
0x180098e88  js      loc_180098CEE
0x180098e8e  mov     word ptr [rsp+130h+var_CC], ax
0x180098e93  mov     rax, [rbp+3Fh+Handle]
0x180098e97  mov     [rsi], rax
0x180098e9a  mov     rcx, [rbp+3Fh+FileHandle]; Handle
0x180098e9e  test    rcx, rcx
0x180098ea1  jz      short loc_180098EAD
0x180098ea3  call    cs:__imp_NtClose
0x180098ea9  mov     ebx, [rsp+130h+var_D0]
0x180098ead  test    ebx, ebx
0x180098eaf  jns     short loc_180098EC4
0x180098eb1  mov     rcx, [rbp+3Fh+Handle]; Handle
0x180098eb5  test    rcx, rcx
0x180098eb8  jz      short loc_180098EC4
0x180098eba  call    cs:__imp_NtClose
0x180098ec0  mov     ebx, [rsp+130h+var_D0]
0x180098ec4  lea     rcx, [rsp+130h+var_D0]; this
0x180098ec9  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x180098ece  mov     eax, ebx
0x180098ed0  add     rsp, 0F8h
0x180098ed7  pop     r15
0x180098ed9  pop     r14
0x180098edb  pop     r13
0x180098edd  pop     r12
0x180098edf  pop     rdi
0x180098ee0  pop     rsi
0x180098ee1  pop     rbx
0x180098ee2  pop     rbp
0x180098ee3  retn
```
