# EdppCaptureProcess

- ea: `0x14002c1c0`
- end: `0x14002c2b2`
- name: `EdppCaptureProcess`
- size: `242`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14002cd1c`

## callees

- `0x14002c1c0`
- `0x14002c2b8`

## import_xrefs

- `ntoskrnl!ZwOpenFile` at `0x14002c245`
- `ntoskrnl!ZwOpenFile` at `0x14002c245`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14002c284`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14002c284`
- `ntoskrnl!IoFileObjectType` at `0x14002c257`
- `ntoskrnl!SeLocateProcessImageName` at `0x14002c1e8`
- `ntoskrnl!SeLocateProcessImageName` at `0x14002c1e8`

## pseudocode

```c
__int64 __fastcall EdppCaptureProcess(struct _KPROCESS *a1, __int64 a2)
{
  NTSTATUS ProcessImageName; // ebx
  void *v4; // rcx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+30h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-38h] BYREF
  PVOID Object; // [rsp+A8h] [rbp+30h] BYREF

  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  ProcessImageName = SeLocateProcessImageName(a1, (PUNICODE_STRING *)(a2 + 24));
  if ( ProcessImageName < 0 )
    goto LABEL_4;
  ObjectAttributes.ObjectName = *(PUNICODE_STRING *)(a2 + 24);
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  ObjectAttributes.Attributes = 576;
  ProcessImageName = ZwOpenFile((PHANDLE)(a2 + 32), 0x80100000, &ObjectAttributes, &IoStatusBlock, 5u, 0x60u);
  if ( ProcessImageName < 0
    || (v4 = *(void **)(a2 + 32),
        Object = 0,
        ProcessImageName = ObReferenceObjectByHandle(v4, 0, (POBJECT_TYPE)IoFileObjectType, 0, &Object, 0),
        *(_QWORD *)(a2 + 64) = Object,
        ProcessImageName < 0) )
  {
LABEL_4:
    EdppCleanupArgs((void *)a2);
  }
  return (unsigned int)ProcessImageName;
}

```

## disassembly

```asm
0x14002c1c0  push    rbp
0x14002c1c2  push    rbx
0x14002c1c3  push    rsi
0x14002c1c4  push    rdi
0x14002c1c5  mov     rbp, rsp
0x14002c1c8  sub     rsp, 78h
0x14002c1cc  xorps   xmm0, xmm0
0x14002c1cf  mov     rdi, rdx
0x14002c1d2  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14002c1d6  xor     eax, eax
0x14002c1d8  add     rdx, 18h; pImageFileName
0x14002c1dc  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x14002c1e0  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14002c1e4  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x14002c1e8  call    cs:__imp_SeLocateProcessImageName
0x14002c1ef  nop     dword ptr [rax+rax+00h]
0x14002c1f4  mov     ebx, eax
0x14002c1f6  test    eax, eax
0x14002c1f8  js      loc_14002C29E
0x14002c1fe  mov     rax, [rdi+18h]
0x14002c202  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x14002c206  xorps   xmm0, xmm0
0x14002c209  mov     [rsp+78h+OpenOptions], 60h ; '`'; OpenOptions
0x14002c211  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14002c215  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14002c219  mov     edx, 80100000h; DesiredAccess
0x14002c21e  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14002c225  lea     rcx, [rdi+20h]; FileHandle
0x14002c229  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x14002c231  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14002c236  mov     [rbp+ObjectAttributes.Attributes], 240h
0x14002c23d  mov     [rsp+78h+ShareAccess], 5; ShareAccess
0x14002c245  call    cs:__imp_ZwOpenFile
0x14002c24c  nop     dword ptr [rax+rax+00h]
0x14002c251  mov     ebx, eax
0x14002c253  test    eax, eax
0x14002c255  js      short loc_14002C29E
0x14002c257  mov     r8, cs:__imp_IoFileObjectType
0x14002c25e  lea     rax, [rbp+Object]
0x14002c262  mov     rcx, [rdi+20h]; Handle
0x14002c266  xor     r9d, r9d; AccessMode
0x14002c269  mov     qword ptr [rsp+78h+OpenOptions], 0; HandleInformation
0x14002c272  xor     edx, edx; DesiredAccess
0x14002c274  mov     [rbp+Object], 0
0x14002c27c  mov     r8, [r8]; ObjectType
0x14002c27f  mov     qword ptr [rsp+78h+ShareAccess], rax; Object
0x14002c284  call    cs:__imp_ObReferenceObjectByHandle
0x14002c28b  nop     dword ptr [rax+rax+00h]
0x14002c290  mov     ebx, eax
0x14002c292  mov     rax, [rbp+Object]
0x14002c296  mov     [rdi+40h], rax
0x14002c29a  test    ebx, ebx
0x14002c29c  jns     short loc_14002C2A6
0x14002c29e  mov     rcx, rdi; void *
0x14002c2a1  call    EdppCleanupArgs
0x14002c2a6  mov     eax, ebx
0x14002c2a8  add     rsp, 78h
0x14002c2ac  pop     rdi
0x14002c2ad  pop     rsi
0x14002c2ae  pop     rbx
0x14002c2af  pop     rbp
0x14002c2b0  retn
```
