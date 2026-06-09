# AipConvertToNtPath

- ea: `0x1400365f0`
- end: `0x140036930`
- name: `AipConvertToNtPath`
- size: `832`
- prototype: `NTSTATUS __fastcall(struct _UNICODE_STRING *, struct _UNICODE_STRING *)`
- caller_count: `3`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140027ebc`
- `0x1400281b4`
- `0x140037ac0`

## callees

- `0x140002e98`
- `0x140006c40`
- `0x14002ff50`
- `0x140032a50`
- `0x1400365f0`

## import_xrefs

- `ntoskrnl!ZwOpenFile` at `0x140036737`
- `ntoskrnl!ZwOpenFile` at `0x140036737`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14003676c`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14003676c`
- `ntoskrnl!IoFileObjectType` at `0x140036747`
- `ntoskrnl!ObfDereferenceObject` at `0x1400368c2`
- `ntoskrnl!ObfDereferenceObject` at `0x1400368c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036856`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036901`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036856`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036901`
- `ntoskrnl!ZwOpenSymbolicLinkObject` at `0x1400367f9`
- `ntoskrnl!ZwOpenSymbolicLinkObject` at `0x1400367f9`
- `ntoskrnl!ZwQuerySymbolicLinkObject` at `0x14003682c`
- `ntoskrnl!ZwQuerySymbolicLinkObject` at `0x140036886`
- `ntoskrnl!ZwQuerySymbolicLinkObject` at `0x14003682c`
- `ntoskrnl!ZwQuerySymbolicLinkObject` at `0x140036886`
- `ntoskrnl!ZwClose` at `0x1400367ba`
- `ntoskrnl!ZwClose` at `0x1400368df`
- `ntoskrnl!ZwClose` at `0x1400367ba`
- `ntoskrnl!ZwClose` at `0x1400368df`

## pseudocode

```c
NTSTATUS __fastcall AipConvertToNtPath(struct _UNICODE_STRING *a1, struct _UNICODE_STRING *a2)
{
  USHORT Length; // cx
  NTSTATUS result; // eax
  PWSTR Buffer; // rdx
  WCHAR v7; // ax
  int FullImagePath; // esi
  struct _FILE_OBJECT *v9; // r14
  NTSTATUS v10; // eax
  USHORT v11; // ax
  struct _UNICODE_STRING v12; // xmm0
  struct _UNICODE_STRING LinkTarget; // [rsp+40h] [rbp-19h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp+7h] BYREF
  struct _FILE_OBJECT *pusResult; // [rsp+C0h] [rbp+67h] BYREF
  ULONG ReturnedLength; // [rsp+D0h] [rbp+77h] BYREF
  void *FileHandle; // [rsp+D8h] [rbp+7Fh] BYREF

  *(_QWORD *)&LinkTarget.Length = 0;
  Length = a1->Length;
  LinkTarget.Buffer = 0;
  FileHandle = 0;
  ReturnedLength = 0;
  LOWORD(pusResult) = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  if ( Length < 4u )
    return -1073741811;
  Buffer = a1->Buffer;
  v7 = Buffer[1];
  if ( v7 != 58 )
  {
    if ( *Buffer == 92 && v7 == 92 )
    {
      result = 0;
      *a2 = *a1;
      return result;
    }
    LinkTarget = *a1;
    goto LABEL_12;
  }
  result = RtlUShortAdd(Length, 8u, (USHORT *)&pusResult);
  if ( result < 0 )
    return result;
  LinkTarget.Length = (unsigned __int16)pusResult;
  LinkTarget.MaximumLength = (unsigned __int16)pusResult;
  LinkTarget.Buffer = (PWSTR)AiAlloc((unsigned __int16)pusResult);
  if ( LinkTarget.Buffer )
  {
    *(_QWORD *)LinkTarget.Buffer = *(_QWORD *)L"\\??\\";
    memmove(LinkTarget.Buffer + 4, a1->Buffer, a1->Length);
LABEL_12:
    ObjectAttributes.ObjectName = &LinkTarget;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v9 = 0;
    if ( ZwOpenFile(&FileHandle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 7u, 0x21u) < 0
      || (pusResult = 0,
          v10 = ObReferenceObjectByHandle(FileHandle, 0, (POBJECT_TYPE)IoFileObjectType, 0, (PVOID *)&pusResult, 0),
          v9 = pusResult,
          FullImagePath = v10,
          v10 >= 0)
      && (FullImagePath = AiGetFullImagePath(FileHandle, pusResult, 0, a2, 0, 0, 0), FullImagePath < 0) )
    {
      while ( 1 )
      {
        if ( FileHandle )
        {
          ZwClose(FileHandle);
          FileHandle = 0;
        }
        ObjectAttributes.Length = 48;
        ObjectAttributes.ObjectName = &LinkTarget;
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.Attributes = 576;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        if ( ZwOpenSymbolicLinkObject(&FileHandle, 1u, &ObjectAttributes) < 0 )
          break;
        if ( LinkTarget.Buffer == a1->Buffer )
        {
          LinkTarget.MaximumLength = 0;
          LinkTarget.Buffer = 0;
        }
        FullImagePath = ZwQuerySymbolicLinkObject(FileHandle, &LinkTarget, &ReturnedLength);
        if ( FullImagePath == -1073741789 )
        {
          v11 = ReturnedLength;
          if ( ReturnedLength > 0xFFFF )
          {
            FullImagePath = -1073741823;
            goto LABEL_31;
          }
          if ( LinkTarget.Buffer )
          {
            ExFreePoolWithTag(LinkTarget.Buffer, 0);
            v11 = ReturnedLength;
          }
          LinkTarget.MaximumLength = v11;
          LinkTarget.Buffer = (PWSTR)AiAlloc(v11);
          if ( !LinkTarget.Buffer )
          {
            FullImagePath = -1073741801;
            goto LABEL_31;
          }
          FullImagePath = ZwQuerySymbolicLinkObject(FileHandle, &LinkTarget, &ReturnedLength);
        }
        if ( FullImagePath < 0 )
          goto LABEL_31;
      }
      v12 = LinkTarget;
      FullImagePath = 0;
      LinkTarget.Buffer = 0;
      *a2 = v12;
    }
LABEL_31:
    if ( v9 )
      ObfDereferenceObject(v9);
    goto LABEL_33;
  }
  FullImagePath = -1073741801;
LABEL_33:
  if ( FileHandle )
    ZwClose(FileHandle);
  if ( LinkTarget.Buffer )
  {
    if ( LinkTarget.Buffer != a1->Buffer )
      ExFreePoolWithTag(LinkTarget.Buffer, 0);
  }
  return FullImagePath;
}

```

## disassembly

```asm
0x1400365f0  push    rbp
0x1400365f2  push    rbx
0x1400365f3  push    rdi
0x1400365f4  push    r15
0x1400365f6  lea     rbp, [rsp-3Fh]
0x1400365fb  sub     rsp, 98h
0x140036602  xor     r15d, r15d
0x140036605  xorps   xmm0, xmm0
0x140036608  mov     rbx, rcx
0x14003660b  mov     qword ptr [rbp+57h+LinkTarget.Length], r15
0x14003660f  movzx   ecx, word ptr [rcx]; usAugend
0x140036612  xor     eax, eax
0x140036614  mov     [rbp+57h+LinkTarget.Buffer], r15
0x140036618  mov     rdi, rdx
0x14003661b  mov     [rbp+57h+FileHandle], r15
0x14003661f  mov     [rbp+57h+ReturnedLength], r15d
0x140036623  mov     word ptr [rbp+57h+pusResult], r15w
0x140036628  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14003662c  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140036630  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x140036634  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x140036638  cmp     cx, 4
0x14003663c  jnb     short loc_140036651
0x14003663e  mov     eax, 0C000000Dh
0x140036643  add     rsp, 98h
0x14003664a  pop     r15
0x14003664c  pop     rdi
0x14003664d  pop     rbx
0x14003664e  pop     rbp
0x14003664f  retn
0x140036651  mov     rdx, [rbx+8]
0x140036655  mov     [rsp+0B0h+arg_8], rsi
0x14003665d  movzx   eax, word ptr [rdx+2]
0x140036661  cmp     ax, 3Ah ; ':'
0x140036665  jnz     short loc_1400366C8
0x140036667  mov     edx, 8; usAddend
0x14003666c  lea     r8, [rbp+57h+pusResult]; pusResult
0x140036670  call    RtlUShortAdd
0x140036675  test    eax, eax
0x140036677  js      loc_14003690F
0x14003667d  movzx   eax, word ptr [rbp+57h+pusResult]
0x140036681  mov     ecx, eax
0x140036683  mov     [rbp+57h+LinkTarget.Length], ax
0x140036687  mov     [rbp+57h+LinkTarget.MaximumLength], ax
0x14003668b  call    AiAlloc
0x140036690  mov     [rbp+57h+LinkTarget.Buffer], rax
0x140036694  test    rax, rax
0x140036697  jnz     short loc_1400366A3
0x140036699  mov     esi, 0C0000017h
0x14003669e  jmp     loc_1400368D6
0x1400366a3  mov     rcx, [rbp+57h+LinkTarget.Buffer]
0x1400366a7  mov     rax, qword ptr cs:asc_14000A548; "\\??\\"
0x1400366ae  mov     [rcx], rax
0x1400366b1  mov     rcx, [rbp+57h+LinkTarget.Buffer]
0x1400366b5  movzx   r8d, word ptr [rbx]; Size
0x1400366b9  add     rcx, 8; void *
0x1400366bd  mov     rdx, [rbx+8]; Src
0x1400366c1  call    memmove
0x1400366c6  jmp     short loc_1400366E9
0x1400366c8  cmp     word ptr [rdx], 5Ch ; '\'
0x1400366cc  jnz     short loc_1400366E2
0x1400366ce  cmp     ax, 5Ch ; '\'
0x1400366d2  jnz     short loc_1400366E2
0x1400366d4  movups  xmm0, xmmword ptr [rbx]
0x1400366d7  mov     eax, r15d
0x1400366da  movups  xmmword ptr [rdi], xmm0
0x1400366dd  jmp     loc_14003690F
0x1400366e2  movups  xmm0, xmmword ptr [rbx]
0x1400366e5  movups  xmmword ptr [rbp+57h+LinkTarget.Length], xmm0
0x1400366e9  lea     rax, [rbp+57h+LinkTarget]
0x1400366ed  mov     [rsp+0B0h+var_20], r14
0x1400366f5  xorps   xmm0, xmm0
0x1400366f8  mov     [rsp+0B0h+OpenOptions], 21h ; '!'; OpenOptions
0x140036700  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140036704  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140036708  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14003670c  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140036713  mov     edx, 100080h; DesiredAccess
0x140036718  mov     [rbp+57h+ObjectAttributes.RootDirectory], r15
0x14003671c  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x140036720  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140036727  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14003672c  mov     r14, r15
0x14003672f  mov     [rsp+0B0h+ShareAccess], 7; ShareAccess
0x140036737  call    cs:__imp_ZwOpenFile
0x14003673e  nop     dword ptr [rax+rax+00h]
0x140036743  test    eax, eax
0x140036745  js      short loc_1400367B1
0x140036747  mov     r8, cs:__imp_IoFileObjectType
0x14003674e  lea     rax, [rbp+57h+pusResult]
0x140036752  mov     rcx, [rbp+57h+FileHandle]; Handle
0x140036756  xor     r9d, r9d; AccessMode
0x140036759  mov     qword ptr [rsp+0B0h+OpenOptions], r15; HandleInformation
0x14003675e  xor     edx, edx; DesiredAccess
0x140036760  mov     [rbp+57h+pusResult], r15
0x140036764  mov     r8, [r8]; ObjectType
0x140036767  mov     qword ptr [rsp+0B0h+ShareAccess], rax; Object
0x14003676c  call    cs:__imp_ObReferenceObjectByHandle
0x140036773  nop     dword ptr [rax+rax+00h]
0x140036778  mov     r14, [rbp+57h+pusResult]
0x14003677c  mov     esi, eax
0x14003677e  test    eax, eax
0x140036780  js      loc_1400368BA
0x140036786  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x14003678a  mov     r9, rdi
0x14003678d  mov     [rsp+0B0h+var_80], r15; __int64
0x140036792  xor     r8d, r8d
0x140036795  mov     qword ptr [rsp+0B0h+OpenOptions], r15; __int64
0x14003679a  mov     rdx, r14; FileObject
0x14003679d  mov     qword ptr [rsp+0B0h+ShareAccess], r15; DestinationString
0x1400367a2  call    AiGetFullImagePath
0x1400367a7  mov     esi, eax
0x1400367a9  test    eax, eax
0x1400367ab  jns     loc_1400368BA
0x1400367b1  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1400367b5  test    rcx, rcx
0x1400367b8  jz      short loc_1400367CA
0x1400367ba  call    cs:__imp_ZwClose
0x1400367c1  nop     dword ptr [rax+rax+00h]
0x1400367c6  mov     [rbp+57h+FileHandle], r15
0x1400367ca  lea     rax, [rbp+57h+LinkTarget]
0x1400367ce  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400367d5  xorps   xmm0, xmm0
0x1400367d8  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400367dc  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400367e0  mov     [rbp+57h+ObjectAttributes.RootDirectory], r15
0x1400367e4  mov     edx, 1; DesiredAccess
0x1400367e9  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x1400367f0  lea     rcx, [rbp+57h+FileHandle]; LinkHandle
0x1400367f4  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400367f9  call    cs:__imp_ZwOpenSymbolicLinkObject
0x140036800  nop     dword ptr [rax+rax+00h]
0x140036805  test    eax, eax
0x140036807  js      loc_1400368AC
0x14003680d  mov     rax, [rbx+8]
0x140036811  cmp     [rbp+57h+LinkTarget.Buffer], rax
0x140036815  jnz     short loc_140036820
0x140036817  mov     [rbp+57h+LinkTarget.MaximumLength], r15w
0x14003681c  mov     [rbp+57h+LinkTarget.Buffer], r15
0x140036820  mov     rcx, [rbp+57h+FileHandle]; LinkHandle
0x140036824  lea     r8, [rbp+57h+ReturnedLength]; ReturnedLength
0x140036828  lea     rdx, [rbp+57h+LinkTarget]; LinkTarget
0x14003682c  call    cs:__imp_ZwQuerySymbolicLinkObject
0x140036833  nop     dword ptr [rax+rax+00h]
0x140036838  mov     esi, eax
0x14003683a  cmp     eax, 0C0000023h
0x14003683f  jnz     short loc_140036894
0x140036841  mov     eax, [rbp+57h+ReturnedLength]
0x140036844  cmp     eax, 0FFFFh
0x140036849  ja      short loc_1400368A5
0x14003684b  mov     rcx, [rbp+57h+LinkTarget.Buffer]; P
0x14003684f  test    rcx, rcx
0x140036852  jz      short loc_140036865
0x140036854  xor     edx, edx; Tag
0x140036856  call    cs:__imp_ExFreePoolWithTag
0x14003685d  nop     dword ptr [rax+rax+00h]
0x140036862  mov     eax, [rbp+57h+ReturnedLength]
0x140036865  movzx   ecx, ax
0x140036868  mov     [rbp+57h+LinkTarget.MaximumLength], ax
0x14003686c  call    AiAlloc
0x140036871  mov     [rbp+57h+LinkTarget.Buffer], rax
0x140036875  test    rax, rax
0x140036878  jz      short loc_14003689E
0x14003687a  mov     rcx, [rbp+57h+FileHandle]; LinkHandle
0x14003687e  lea     r8, [rbp+57h+ReturnedLength]; ReturnedLength
0x140036882  lea     rdx, [rbp+57h+LinkTarget]; LinkTarget
0x140036886  call    cs:__imp_ZwQuerySymbolicLinkObject
0x14003688d  nop     dword ptr [rax+rax+00h]
0x140036892  mov     esi, eax
0x140036894  test    esi, esi
0x140036896  jns     loc_1400367B1
0x14003689c  jmp     short loc_1400368BA
0x14003689e  mov     esi, 0C0000017h
0x1400368a3  jmp     short loc_1400368BA
0x1400368a5  mov     esi, 0C0000001h
0x1400368aa  jmp     short loc_1400368BA
0x1400368ac  movups  xmm0, xmmword ptr [rbp+57h+LinkTarget.Length]
0x1400368b0  mov     esi, r15d
0x1400368b3  mov     [rbp+57h+LinkTarget.Buffer], r15
0x1400368b7  movups  xmmword ptr [rdi], xmm0
0x1400368ba  test    r14, r14
0x1400368bd  jz      short loc_1400368CE
0x1400368bf  mov     rcx, r14; Object
0x1400368c2  call    cs:__imp_ObfDereferenceObject
0x1400368c9  nop     dword ptr [rax+rax+00h]
0x1400368ce  mov     r14, [rsp+0B0h+var_20]
0x1400368d6  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1400368da  test    rcx, rcx
0x1400368dd  jz      short loc_1400368EB
0x1400368df  call    cs:__imp_ZwClose
0x1400368e6  nop     dword ptr [rax+rax+00h]
0x1400368eb  mov     rcx, [rbp+57h+LinkTarget.Buffer]; P
0x1400368ef  test    rcx, rcx
0x1400368f2  jz      short loc_14003690D
0x1400368f4  cmp     rcx, [rbx+8]
0x1400368f8  jz      short loc_14003690D
0x1400368fa  test    rcx, rcx
0x1400368fd  jz      short loc_14003690D
0x1400368ff  xor     edx, edx; Tag
0x140036901  call    cs:__imp_ExFreePoolWithTag
0x140036908  nop     dword ptr [rax+rax+00h]
0x14003690d  mov     eax, esi
0x14003690f  mov     rsi, [rsp+0B0h+arg_8]
0x140036917  add     rsp, 98h
0x14003691e  pop     r15
0x140036920  pop     rdi
0x140036921  pop     rbx
0x140036922  pop     rbp
0x140036923  retn
```
