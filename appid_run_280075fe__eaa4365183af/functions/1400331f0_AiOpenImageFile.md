# AiOpenImageFile

- ea: `0x1400331f0`
- end: `0x1400333a7`
- name: `AiOpenImageFile`
- size: `439`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14002b5e0`
- `0x1400373b0`

## callees

- `0x140001ee0`
- `0x1400331f0`

## import_xrefs

- `ntoskrnl!ZwOpenFile` at `0x1400332b9`
- `ntoskrnl!ZwOpenFile` at `0x1400332b9`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400332fa`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400332fa`
- `ntoskrnl!IoFileObjectType` at `0x140033214`
- `ntoskrnl!IoFileObjectType` at `0x1400332cf`
- `ntoskrnl!ObfDereferenceObject` at `0x140033373`
- `ntoskrnl!ObfDereferenceObject` at `0x140033373`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140033259`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140033259`
- `ntoskrnl!ZwClose` at `0x14003335f`
- `ntoskrnl!ZwClose` at `0x14003335f`

## pseudocode

```c
__int64 __fastcall AiOpenImageFile(struct _UNICODE_STRING *a1, _QWORD *a2, void **Handle)
{
  PVOID v6; // rdi
  NTSTATUS v7; // ebx
  NTSTATUS v8; // eax
  PVOID Object; // [rsp+40h] [rbp-88h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+48h] [rbp-80h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-70h] BYREF
  void *FileHandle; // [rsp+E8h] [rbp+20h] BYREF

  FileHandle = 0;
  v6 = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  v7 = ObOpenObjectByPointer(a2, 0x200u, 0, 0x80100000, (POBJECT_TYPE)IoFileObjectType, 0, Handle);
  if ( v7 < 0 )
  {
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.ObjectName = a1;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v7 = ZwOpenFile(&FileHandle, 0x80100000, &ObjectAttributes, &IoStatusBlock, 5u, 0x60u);
    if ( v7 >= 0 )
    {
      Object = 0;
      v8 = ObReferenceObjectByHandle(FileHandle, 0, (POBJECT_TYPE)IoFileObjectType, 0, &Object, 0);
      v6 = Object;
      v7 = v8;
      if ( v8 >= 0 )
      {
        if ( a2[3] == *((_QWORD *)Object + 3) )
        {
          *Handle = FileHandle;
          FileHandle = 0;
          goto LABEL_11;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_eb456f0194b1375dfc92b638f91e9c3b_Traceguids, a1);
        v7 = -1073741275;
      }
    }
  }
  if ( FileHandle )
    ZwClose(FileHandle);
LABEL_11:
  if ( v6 )
    ObfDereferenceObject(v6);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400331f0  push    rbx
0x1400331f2  push    rbp
0x1400331f3  push    rsi
0x1400331f4  push    rdi
0x1400331f5  push    r14
0x1400331f7  push    r15
0x1400331f9  sub     rsp, 98h
0x140033200  xorps   xmm0, xmm0
0x140033203  mov     [rsp+0C8h+Handle], r8; Handle
0x140033208  xor     eax, eax
0x14003320a  mov     r14, rcx
0x14003320d  mov     [rsp+0C8h+AccessMode], al; AccessMode
0x140033211  mov     rbp, rdx
0x140033214  mov     rax, cs:__imp_IoFileObjectType
0x14003321b  mov     rsi, r8
0x14003321e  xor     r15d, r15d
0x140033221  mov     r9d, 80100000h; DesiredAccess
0x140033227  movups  xmmword ptr [rsp+0C8h+ObjectAttributes.ObjectName], xmm0
0x14003322c  xor     r8d, r8d; PassedAccessState
0x14003322f  mov     [rsp+0C8h+FileHandle], r15
0x140033237  mov     rcx, [rax]
0x14003323a  mov     edx, 200h; HandleAttributes
0x14003323f  mov     [rsp+0C8h+ObjectType], rcx; ObjectType
0x140033244  mov     edi, r15d
0x140033247  mov     rcx, rbp; Object
0x14003324a  movups  xmmword ptr [rsp+0C8h+ObjectAttributes.Length], xmm0
0x14003324f  movups  xmmword ptr [rsp+0C8h+ObjectAttributes+1Ch], xmm0
0x140033254  movups  xmmword ptr [rsp+0C8h+IoStatusBlock], xmm0
0x140033259  call    cs:__imp_ObOpenObjectByPointer
0x140033260  nop     dword ptr [rax+rax+00h]
0x140033265  mov     ebx, eax
0x140033267  test    eax, eax
0x140033269  jns     loc_140033352
0x14003326f  xorps   xmm0, xmm0
0x140033272  mov     dword ptr [rsp+0C8h+AccessMode], 60h ; '`'; OpenOptions
0x14003327a  lea     r9, [rsp+0C8h+IoStatusBlock]; IoStatusBlock
0x14003327f  mov     [rsp+0C8h+ObjectAttributes.Length], 30h ; '0'
0x140033287  lea     r8, [rsp+0C8h+ObjectAttributes]; ObjectAttributes
0x14003328c  mov     [rsp+0C8h+ObjectAttributes.RootDirectory], r15
0x140033291  mov     edx, 80100000h; DesiredAccess
0x140033296  mov     [rsp+0C8h+ObjectAttributes.Attributes], 240h
0x14003329e  lea     rcx, [rsp+0C8h+FileHandle]; FileHandle
0x1400332a6  mov     [rsp+0C8h+ObjectAttributes.ObjectName], r14
0x1400332ab  movdqu  xmmword ptr [rsp+0C8h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400332b1  mov     dword ptr [rsp+0C8h+ObjectType], 5; ShareAccess
0x1400332b9  call    cs:__imp_ZwOpenFile
0x1400332c0  nop     dword ptr [rax+rax+00h]
0x1400332c5  mov     ebx, eax
0x1400332c7  test    eax, eax
0x1400332c9  js      loc_140033352
0x1400332cf  mov     r8, cs:__imp_IoFileObjectType
0x1400332d6  lea     rax, [rsp+0C8h+Object]
0x1400332db  mov     rcx, [rsp+0C8h+FileHandle]; Handle
0x1400332e3  xor     r9d, r9d; AccessMode
0x1400332e6  mov     qword ptr [rsp+0C8h+AccessMode], r15; HandleInformation
0x1400332eb  xor     edx, edx; DesiredAccess
0x1400332ed  mov     [rsp+0C8h+Object], r15
0x1400332f2  mov     r8, [r8]; ObjectType
0x1400332f5  mov     [rsp+0C8h+ObjectType], rax; Object
0x1400332fa  call    cs:__imp_ObReferenceObjectByHandle
0x140033301  nop     dword ptr [rax+rax+00h]
0x140033306  mov     rdi, [rsp+0C8h+Object]
0x14003330b  mov     ebx, eax
0x14003330d  test    eax, eax
0x14003330f  js      short loc_140033352
0x140033311  mov     rax, [rdi+18h]
0x140033315  cmp     [rbp+18h], rax
0x140033319  jz      short loc_140033392
0x14003331b  mov     rcx, cs:WPP_GLOBAL_Control
0x140033322  lea     rax, WPP_GLOBAL_Control
0x140033329  cmp     rcx, rax
0x14003332c  jz      short loc_14003334D
0x14003332e  mov     eax, [rcx+2Ch]
0x140033331  test    al, 4
0x140033333  jz      short loc_14003334D
0x140033335  mov     rcx, [rcx+18h]
0x140033339  lea     r8, WPP_eb456f0194b1375dfc92b638f91e9c3b_Traceguids
0x140033340  mov     edx, 0Ah
0x140033345  mov     r9, r14
0x140033348  call    WPP_SF_Z
0x14003334d  mov     ebx, 0C0000225h
0x140033352  mov     rcx, [rsp+0C8h+FileHandle]; Handle
0x14003335a  test    rcx, rcx
0x14003335d  jz      short loc_14003336B
0x14003335f  call    cs:__imp_ZwClose
0x140033366  nop     dword ptr [rax+rax+00h]
0x14003336b  test    rdi, rdi
0x14003336e  jz      short loc_14003337F
0x140033370  mov     rcx, rdi; Object
0x140033373  call    cs:__imp_ObfDereferenceObject
0x14003337a  nop     dword ptr [rax+rax+00h]
0x14003337f  mov     eax, ebx
0x140033381  add     rsp, 98h
0x140033388  pop     r15
0x14003338a  pop     r14
0x14003338c  pop     rdi
0x14003338d  pop     rsi
0x14003338e  pop     rbp
0x14003338f  pop     rbx
0x140033390  retn
0x140033392  mov     rax, [rsp+0C8h+FileHandle]
0x14003339a  mov     [rsi], rax
0x14003339d  mov     [rsp+0C8h+FileHandle], r15
0x1400333a5  jmp     short loc_14003336B
```
