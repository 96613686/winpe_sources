# GetRemotePath(ushort const *,ushort * *)

- ea: `0x1800071d0`
- end: `0x180007361`
- name: `?GetRemotePath@@YAJPEBGPEAPEAG@Z`
- size: `401`
- prototype: `__int64 __fastcall(PCWSTR SourceString, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180007368`

## callees

- `0x180002506`
- `0x1800071d0`
- `0x18000a9a6`
- `0x18000a9d0`

## import_xrefs

- `msvcrt!free` at `0x180007223`
- `msvcrt!free` at `0x180007223`
- `msvcrt!calloc` at `0x180007305`
- `msvcrt!calloc` at `0x180007305`
- `ntdll!NtClose` at `0x1800072dc`
- `ntdll!NtClose` at `0x1800072dc`
- `ntdll!RtlInitUnicodeString` at `0x180007239`
- `ntdll!RtlInitUnicodeString` at `0x180007239`
- `ntdll!NtQueryInformationFile` at `0x1800072cf`
- `ntdll!NtQueryInformationFile` at `0x1800072cf`
- `ntdll!NtOpenFile` at `0x180007294`
- `ntdll!NtOpenFile` at `0x180007294`

## pseudocode

```c
NTSTATUS __fastcall GetRemotePath(PCWSTR SourceString, unsigned __int16 **a2)
{
  NTSTATUS result; // eax
  NTSTATUS v5; // edi
  unsigned __int16 *v6; // rax
  void *FileHandle; // [rsp+30h] [rbp-D0h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-C8h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+48h] [rbp-B8h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int FileInformation; // [rsp+90h] [rbp-70h] BYREF
  _BYTE Src[540]; // [rsp+94h] [rbp-6Ch] BYREF

  if ( !SourceString || !*SourceString || !a2 )
    return -2147024809;
  if ( *a2 )
    free(*a2);
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  ObjectAttributes.RootDirectory = 0;
  FileHandle = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  IoStatusBlock = 0;
  result = NtOpenFile(&FileHandle, 0x100000u, &ObjectAttributes, &IoStatusBlock, 1u, 1u);
  if ( result >= 0 )
  {
    memset_0(&FileInformation, 0, 0x21Au);
    v5 = NtQueryInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 0x218u, FileNameInformation);
    NtClose(FileHandle);
    if ( v5 >= 0 )
    {
      if ( FileInformation >> 1 <= 0x104 )
      {
        v6 = (unsigned __int16 *)calloc((FileInformation >> 1) + 2, 2u);
        *a2 = v6;
        if ( v6 )
        {
          *v6 = 92;
          memcpy_0(*a2 + 1, Src, FileInformation);
          return 0;
        }
        else
        {
          return -2147024882;
        }
      }
      else
      {
        return -2147467259;
      }
    }
    else
    {
      return v5;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800071d0  mov     [rsp-8+arg_10], rbx
0x1800071d5  push    rbp
0x1800071d6  push    rsi
0x1800071d7  push    rdi
0x1800071d8  lea     rbp, [rsp-1C0h]
0x1800071e0  sub     rsp, 2C0h
0x1800071e7  mov     rax, cs:__security_cookie
0x1800071ee  xor     rax, rsp
0x1800071f1  mov     [rbp+1D0h+var_20], rax
0x1800071f8  xor     esi, esi
0x1800071fa  mov     rbx, rdx
0x1800071fd  mov     rdi, rcx
0x180007200  test    rcx, rcx
0x180007203  jz      loc_18000733A
0x180007209  cmp     [rcx], si
0x18000720c  jz      loc_18000733A
0x180007212  test    rdx, rdx
0x180007215  jz      loc_18000733A
0x18000721b  mov     rcx, [rdx]; Block
0x18000721e  test    rcx, rcx
0x180007221  jz      short loc_180007229
0x180007223  call    cs:__imp_free
0x180007229  xorps   xmm0, xmm0
0x18000722c  lea     rcx, [rsp+2D0h+DestinationString]; DestinationString
0x180007231  mov     rdx, rdi; SourceString
0x180007234  movups  xmmword ptr [rsp+2D0h+DestinationString.Length], xmm0
0x180007239  call    cs:__imp_RtlInitUnicodeString
0x18000723f  lea     rax, [rsp+2D0h+DestinationString]
0x180007244  mov     qword ptr [rsp+2D0h+ObjectAttributes.Length], 30h ; '0'
0x18000724d  xorps   xmm0, xmm0
0x180007250  mov     [rsp+2D0h+ObjectAttributes.ObjectName], rax
0x180007255  mov     eax, 1
0x18000725a  mov     qword ptr [rsp+2D0h+ObjectAttributes.Attributes], 40h ; '@'
0x180007263  mov     [rsp+2D0h+OpenOptions], eax; OpenOptions
0x180007267  lea     r9, [rsp+2D0h+IoStatusBlock]; IoStatusBlock
0x18000726c  lea     r8, [rsp+2D0h+ObjectAttributes]; ObjectAttributes
0x180007271  mov     [rsp+2D0h+ShareAccess], eax; ShareAccess
0x180007275  mov     edx, 100000h; DesiredAccess
0x18000727a  mov     [rsp+2D0h+ObjectAttributes.RootDirectory], rsi
0x18000727f  lea     rcx, [rsp+2D0h+FileHandle]; FileHandle
0x180007284  mov     [rsp+2D0h+FileHandle], rsi
0x180007289  movdqu  xmmword ptr [rsp+2D0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000728f  movups  xmmword ptr [rsp+2D0h+IoStatusBlock], xmm0
0x180007294  call    cs:__imp_NtOpenFile
0x18000729a  test    eax, eax
0x18000729c  js      loc_18000733F
0x1800072a2  xor     edx, edx; Val
0x1800072a4  lea     rcx, [rbp+1D0h+FileInformation]; void *
0x1800072a8  mov     r8d, 21Ah; Size
0x1800072ae  call    memset_0
0x1800072b3  mov     rcx, [rsp+2D0h+FileHandle]; FileHandle
0x1800072b8  lea     r8, [rbp+1D0h+FileInformation]; FileInformation
0x1800072bc  mov     r9d, 218h; Length
0x1800072c2  mov     [rsp+2D0h+ShareAccess], 9; FileInformationClass
0x1800072ca  lea     rdx, [rsp+2D0h+IoStatusBlock]; IoStatusBlock
0x1800072cf  call    cs:__imp_NtQueryInformationFile
0x1800072d5  mov     rcx, [rsp+2D0h+FileHandle]; Handle
0x1800072da  mov     edi, eax
0x1800072dc  call    cs:__imp_NtClose
0x1800072e2  test    edi, edi
0x1800072e4  jns     short loc_1800072EA
0x1800072e6  mov     eax, edi
0x1800072e8  jmp     short loc_18000733F
0x1800072ea  mov     eax, [rbp+1D0h+FileInformation]
0x1800072ed  shr     eax, 1
0x1800072ef  cmp     eax, 104h
0x1800072f4  jbe     short loc_1800072FD
0x1800072f6  mov     eax, 80004005h
0x1800072fb  jmp     short loc_18000733F
0x1800072fd  lea     ecx, [rax+2]; Count
0x180007300  mov     edx, 2; Size
0x180007305  call    cs:__imp_calloc
0x18000730b  mov     [rbx], rax
0x18000730e  test    rax, rax
0x180007311  jnz     short loc_18000731A
0x180007313  mov     eax, 8007000Eh
0x180007318  jmp     short loc_18000733F
0x18000731a  mov     ecx, 5Ch ; '\'
0x18000731f  lea     rdx, [rbp+1D0h+Src]; Src
0x180007323  mov     [rax], cx
0x180007326  mov     rcx, [rbx]
0x180007329  mov     r8d, [rbp+1D0h+FileInformation]; Size
0x18000732d  add     rcx, 2; void *
0x180007331  call    memcpy_0
0x180007336  xor     eax, eax
0x180007338  jmp     short loc_18000733F
0x18000733a  mov     eax, 80070057h
0x18000733f  mov     rcx, [rbp+1D0h+var_20]
0x180007346  xor     rcx, rsp; StackCookie
0x180007349  call    __security_check_cookie
0x18000734e  mov     rbx, [rsp+2D0h+arg_10]
0x180007356  add     rsp, 2C0h
0x18000735d  pop     rdi
0x18000735e  pop     rsi
0x18000735f  pop     rbp
0x180007360  retn
```
