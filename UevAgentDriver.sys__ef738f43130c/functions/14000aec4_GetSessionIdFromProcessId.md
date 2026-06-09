# GetSessionIdFromProcessId

- ea: `0x14000aec4`
- end: `0x14000b035`
- name: `GetSessionIdFromProcessId`
- size: `369`
- prototype: `__int64 __fastcall(void *, _DWORD *, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x14000b160`
- `0x14000b418`

## callees

- `0x140001118`
- `0x1400011b0`
- `0x140001298`
- `0x14000aec4`

## import_xrefs

- `ntoskrnl!ZwOpenProcess` at `0x14000af4c`
- `ntoskrnl!ZwOpenProcess` at `0x14000af4c`
- `ntoskrnl!ZwQueryInformationToken` at `0x14000afb6`
- `ntoskrnl!ZwQueryInformationToken` at `0x14000afb6`
- `ntoskrnl!ZwClose` at `0x14000aff5`
- `ntoskrnl!ZwClose` at `0x14000b00a`
- `ntoskrnl!ZwClose` at `0x14000aff5`
- `ntoskrnl!ZwClose` at `0x14000b00a`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x14000af7a`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x14000af7a`

## string_xrefs

- `0x14000aeee`: `UevFilter.GetSessionIdFromProcessId: Entry\n`
- `0x14000af5e`: `UevFilter.GetSessionIdFromProcessId: Failed to open process handle. Error = 0x%0X.\n`
- `0x14000af8c`: `UevFilter.GetSessionIdFromProcessId: Failed to open process token. Error = 0x%0X.\n`
- `0x14000afc8`: `UevFilter.GetSessionIdFromProcessId: Failed to get session ID. Error = 0x%0X.\n`
- `0x14000afdb`: `UevFilter.GetSessionIdFromProcessId: Session ID = %d.\n`
- `0x14000b019`: `UevFilter.GetSessionIdFromProcessId: Exit. Error = 0x%0X.\n`

## pseudocode

```c
__int64 __fastcall GetSessionIdFromProcessId(void *a1, _DWORD *a2, __int64 a3)
{
  NTSTATUS v5; // eax
  unsigned int v6; // ebx
  NTSTATUS v7; // eax
  NTSTATUS v8; // eax
  _CLIENT_ID ClientId; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  ULONG ReturnLength; // [rsp+90h] [rbp+20h] BYREF
  void *ProcessHandle; // [rsp+A0h] [rbp+30h] BYREF
  void *TokenHandle; // [rsp+A8h] [rbp+38h] BYREF

  ProcessHandle = 0;
  TokenHandle = 0;
  memset(&ObjectAttributes.Length + 1, 0, 20);
  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  DbgTrace(2, "UevFilter.GetSessionIdFromProcessId: Entry\n", a3);
  ObjectAttributes.Length = 48;
  ObjectAttributes.Attributes = 512;
  ClientId.UniqueProcess = a1;
  ClientId.UniqueThread = 0;
  v5 = ZwOpenProcess(&ProcessHandle, 0x80000000, &ObjectAttributes, &ClientId);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v7 = ZwOpenProcessTokenEx(ProcessHandle, 0x80000000, 0x200u, &TokenHandle);
    v6 = v7;
    if ( v7 >= 0 )
    {
      ReturnLength = 0;
      v8 = ZwQueryInformationToken(TokenHandle, TokenSessionId, a2, 4u, &ReturnLength);
      v6 = v8;
      if ( v8 >= 0 )
        DbgTraceFrmt(2u, "UevFilter.GetSessionIdFromProcessId: Session ID = %d.\n", *a2);
      else
        DbgTraceFrmtErr(
          "UevFilter.GetSessionIdFromProcessId: Failed to get session ID. Error = 0x%0X.\n",
          (unsigned int)v8);
    }
    else
    {
      DbgTraceFrmtErr(
        "UevFilter.GetSessionIdFromProcessId: Failed to open process token. Error = 0x%0X.\n",
        (unsigned int)v7);
    }
  }
  else
  {
    DbgTraceFrmtErr(
      "UevFilter.GetSessionIdFromProcessId: Failed to open process handle. Error = 0x%0X.\n",
      (unsigned int)v5);
  }
  if ( ProcessHandle )
    ZwClose(ProcessHandle);
  if ( TokenHandle )
    ZwClose(TokenHandle);
  DbgTraceFrmt(2u, "UevFilter.GetSessionIdFromProcessId: Exit. Error = 0x%0X.\n", v6);
  return v6;
}

```

## disassembly

```asm
0x14000aec4  push    rbp
0x14000aec6  push    rbx
0x14000aec7  push    rdi
0x14000aec8  mov     rbp, rsp
0x14000aecb  sub     rsp, 70h
0x14000aecf  xorps   xmm0, xmm0
0x14000aed2  mov     [rbp+ProcessHandle], 0
0x14000aeda  xor     eax, eax
0x14000aedc  mov     [rbp+TokenHandle], 0
0x14000aee4  mov     rdi, rdx
0x14000aee7  mov     rbx, rcx
0x14000aeea  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14000aeee  lea     rdx, aUevfilterGetse_3; "UevFilter.GetSessionIdFromProcessId: En"...
0x14000aef5  lea     ecx, [rax+2]
0x14000aef8  movups  xmmword ptr [rbp+ClientId.UniqueProcess], xmm0
0x14000aefc  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14000af00  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x14000af04  call    DbgTrace
0x14000af09  xorps   xmm0, xmm0
0x14000af0c  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14000af13  lea     r9, [rbp+ClientId]; ClientId
0x14000af17  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x14000af1f  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14000af23  mov     [rbp+ObjectAttributes.Attributes], 200h
0x14000af2a  mov     edx, 80000000h; DesiredAccess
0x14000af2f  mov     [rbp+ObjectAttributes.ObjectName], 0
0x14000af37  lea     rcx, [rbp+ProcessHandle]; ProcessHandle
0x14000af3b  mov     [rbp+ClientId.UniqueProcess], rbx
0x14000af3f  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14000af44  mov     [rbp+ClientId.UniqueThread], 0
0x14000af4c  call    cs:__imp_ZwOpenProcess
0x14000af53  nop     dword ptr [rax+rax+00h]
0x14000af58  mov     ebx, eax
0x14000af5a  test    eax, eax
0x14000af5c  jns     short loc_14000AF67
0x14000af5e  lea     rcx, aUevfilterGetse_0; "UevFilter.GetSessionIdFromProcessId: Fa"...
0x14000af65  jmp     short loc_14000AFCF
0x14000af67  mov     rcx, [rbp+ProcessHandle]; ProcessHandle
0x14000af6b  lea     r9, [rbp+TokenHandle]; TokenHandle
0x14000af6f  mov     edx, 80000000h; DesiredAccess
0x14000af74  mov     r8d, 200h; HandleAttributes
0x14000af7a  call    cs:__imp_ZwOpenProcessTokenEx
0x14000af81  nop     dword ptr [rax+rax+00h]
0x14000af86  mov     ebx, eax
0x14000af88  test    eax, eax
0x14000af8a  jns     short loc_14000AF95
0x14000af8c  lea     rcx, aUevfilterGetse_2; "UevFilter.GetSessionIdFromProcessId: Fa"...
0x14000af93  jmp     short loc_14000AFCF
0x14000af95  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x14000af99  lea     rax, [rbp+arg_0]
0x14000af9d  mov     r9d, 4; TokenInformationLength
0x14000afa3  mov     [rbp+arg_0], 0
0x14000afaa  mov     r8, rdi; TokenInformation
0x14000afad  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x14000afb2  lea     edx, [r9+8]; TokenInformationClass
0x14000afb6  call    cs:__imp_ZwQueryInformationToken
0x14000afbd  nop     dword ptr [rax+rax+00h]
0x14000afc2  mov     ebx, eax
0x14000afc4  test    eax, eax
0x14000afc6  jns     short loc_14000AFD8
0x14000afc8  lea     rcx, aUevfilterGetse_4; "UevFilter.GetSessionIdFromProcessId: Fa"...
0x14000afcf  mov     edx, eax
0x14000afd1  call    DbgTraceFrmtErr
0x14000afd6  jmp     short loc_14000AFEC
0x14000afd8  mov     r8d, [rdi]
0x14000afdb  lea     rdx, aUevfilterGetse_1; "UevFilter.GetSessionIdFromProcessId: Se"...
0x14000afe2  mov     ecx, 2
0x14000afe7  call    DbgTraceFrmt
0x14000afec  mov     rcx, [rbp+ProcessHandle]; Handle
0x14000aff0  test    rcx, rcx
0x14000aff3  jz      short loc_14000B001
0x14000aff5  call    cs:__imp_ZwClose
0x14000affc  nop     dword ptr [rax+rax+00h]
0x14000b001  mov     rcx, [rbp+TokenHandle]; Handle
0x14000b005  test    rcx, rcx
0x14000b008  jz      short loc_14000B016
0x14000b00a  call    cs:__imp_ZwClose
0x14000b011  nop     dword ptr [rax+rax+00h]
0x14000b016  mov     r8d, ebx
0x14000b019  lea     rdx, aUevfilterGetse; "UevFilter.GetSessionIdFromProcessId: Ex"...
0x14000b020  mov     ecx, 2
0x14000b025  call    DbgTraceFrmt
0x14000b02a  mov     eax, ebx
0x14000b02c  add     rsp, 70h
0x14000b030  pop     rdi
0x14000b031  pop     rbx
0x14000b032  pop     rbp
0x14000b033  retn
```
