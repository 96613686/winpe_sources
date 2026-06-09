# AipConvertToNtPath

- ea: `0x180004f4c`
- end: `0x1800051f5`
- name: `AipConvertToNtPath`
- size: `681`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800028d0`
- `0x18000423c`
- `0x180004de4`

## callees

- `0x180003fd4`
- `0x180004584`
- `0x180004f4c`
- `0x180009562`

## import_xrefs

- `ntdll!NtOpenFile` at `0x18000506c`
- `ntdll!NtOpenFile` at `0x18000506c`
- `ntdll!NtClose` at `0x1800050ac`
- `ntdll!NtClose` at `0x1800051b2`
- `ntdll!NtClose` at `0x1800050ac`
- `ntdll!NtClose` at `0x1800051b2`
- `ntdll!NtOpenSymbolicLinkObject` at `0x1800050ed`
- `ntdll!NtOpenSymbolicLinkObject` at `0x1800050ed`
- `ntdll!NtQuerySymbolicLinkObject` at `0x18000511b`
- `ntdll!NtQuerySymbolicLinkObject` at `0x18000517c`
- `ntdll!NtQuerySymbolicLinkObject` at `0x18000511b`
- `ntdll!NtQuerySymbolicLinkObject` at `0x18000517c`
- `ntdll!RtlFreeHeap` at `0x18000514e`
- `ntdll!RtlFreeHeap` at `0x1800051da`
- `ntdll!RtlFreeHeap` at `0x18000514e`
- `ntdll!RtlFreeHeap` at `0x1800051da`

## pseudocode

```c
__int64 __fastcall AipConvertToNtPath(struct _UNICODE_STRING *a1, struct _UNICODE_STRING *a2)
{
  WCHAR *v2; // rax
  bool v5; // cf
  NTSTATUS FullImagePath; // ebx
  PWSTR Buffer; // rcx
  USHORT v8; // cx
  USHORT v9; // ax
  struct _UNICODE_STRING LinkTarget; // [rsp+30h] [rbp-50h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  ULONG DataWritten; // [rsp+A0h] [rbp+20h] BYREF
  void *FileHandle; // [rsp+B0h] [rbp+30h] BYREF

  v2 = 0;
  *(_QWORD *)&LinkTarget.Length = 0;
  LinkTarget.Buffer = 0;
  FileHandle = 0;
  v5 = a1->Length < 4u;
  memset(&ObjectAttributes, 0, 44);
  DataWritten = 0;
  IoStatusBlock = 0;
  if ( v5 )
    return (unsigned int)-1073741811;
  Buffer = a1->Buffer;
  if ( Buffer[1] != 58 )
  {
    if ( *Buffer == 92 && Buffer[1] == 92 )
    {
      FullImagePath = 0;
      *a2 = *a1;
      return (unsigned int)FullImagePath;
    }
    LinkTarget = *a1;
    goto LABEL_13;
  }
  v8 = a1->Length + 8;
  if ( v8 < a1->Length )
  {
    FullImagePath = -1073741675;
    goto LABEL_31;
  }
  LinkTarget.Length = a1->Length + 8;
  LinkTarget.MaximumLength = v8;
  v2 = (WCHAR *)AiAlloc(v8);
  LinkTarget.Buffer = v2;
  if ( v2 )
  {
    *(_QWORD *)v2 = 0x5C003F003F005CLL;
    memcpy_0(LinkTarget.Buffer + 4, a1->Buffer, a1->Length);
LABEL_13:
    ObjectAttributes.ObjectName = &LinkTarget;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( NtOpenFile(&FileHandle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 7u, 0x21u) >= 0
      && (FullImagePath = AiGetFullImagePath(FileHandle, 0, 0), FullImagePath >= 0) )
    {
LABEL_29:
      v2 = LinkTarget.Buffer;
    }
    else
    {
      while ( 1 )
      {
        if ( FileHandle )
        {
          NtClose(FileHandle);
          FileHandle = 0;
        }
        ObjectAttributes.Length = 48;
        ObjectAttributes.ObjectName = &LinkTarget;
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.Attributes = 576;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        if ( NtOpenSymbolicLinkObject(&FileHandle, 1u, &ObjectAttributes) < 0 )
          break;
        if ( LinkTarget.Buffer == a1->Buffer )
        {
          LinkTarget.MaximumLength = 0;
          LinkTarget.Buffer = 0;
        }
        FullImagePath = NtQuerySymbolicLinkObject(FileHandle, &LinkTarget, &DataWritten);
        if ( FullImagePath == -1073741789 )
        {
          v9 = DataWritten;
          if ( DataWritten > 0xFFFF )
          {
            FullImagePath = -1073741823;
            goto LABEL_29;
          }
          if ( LinkTarget.Buffer )
          {
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, LinkTarget.Buffer);
            v9 = DataWritten;
          }
          LinkTarget.MaximumLength = v9;
          v2 = (WCHAR *)AiAlloc(v9);
          LinkTarget.Buffer = v2;
          if ( !v2 )
            goto LABEL_6;
          FullImagePath = NtQuerySymbolicLinkObject(FileHandle, &LinkTarget, &DataWritten);
        }
        if ( FullImagePath < 0 )
          goto LABEL_29;
      }
      FullImagePath = 0;
      v2 = 0;
      *a2 = LinkTarget;
      LinkTarget.Buffer = 0;
    }
    goto LABEL_31;
  }
LABEL_6:
  FullImagePath = -1073741801;
LABEL_31:
  if ( FileHandle )
  {
    NtClose(FileHandle);
    v2 = LinkTarget.Buffer;
  }
  if ( v2 && v2 != a1->Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, LinkTarget.Buffer);
  return (unsigned int)FullImagePath;
}

```

## disassembly

```asm
0x180004f4c  mov     [rsp-18h+arg_8], rbx
0x180004f51  push    rbp
0x180004f52  push    rsi
0x180004f53  push    rdi
0x180004f54  mov     rbp, rsp
0x180004f57  sub     rsp, 80h
0x180004f5e  xor     eax, eax
0x180004f60  xorps   xmm0, xmm0
0x180004f63  mov     rdi, rcx
0x180004f66  mov     qword ptr [rbp+LinkTarget.Length], rax
0x180004f6a  xor     ecx, ecx
0x180004f6c  mov     [rbp+LinkTarget.Buffer], rax
0x180004f70  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180004f74  mov     rsi, rdx
0x180004f77  mov     [rbp+FileHandle], rax
0x180004f7b  cmp     word ptr [rdi], 4
0x180004f7f  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180004f83  mov     [rbp+DataWritten], eax
0x180004f86  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x180004f8a  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x180004f8e  jnb     short loc_180004F9A
0x180004f90  mov     ebx, 0C000000Dh
0x180004f95  jmp     loc_1800051E0
0x180004f9a  mov     rcx, [rdi+8]
0x180004f9e  cmp     word ptr [rcx+2], 3Ah ; ':'
0x180004fa3  jnz     short loc_180005002
0x180004fa5  movzx   ecx, word ptr [rdi]
0x180004fa8  add     cx, 8
0x180004fac  cmp     cx, [rdi]
0x180004faf  jb      short loc_180004FF8
0x180004fb1  mov     [rbp+LinkTarget.Length], cx
0x180004fb5  mov     [rbp+LinkTarget.MaximumLength], cx
0x180004fb9  movzx   ecx, cx
0x180004fbc  call    AiAlloc
0x180004fc1  mov     [rbp+LinkTarget.Buffer], rax
0x180004fc5  test    rax, rax
0x180004fc8  jnz     short loc_180004FD4
0x180004fca  mov     ebx, 0C0000017h
0x180004fcf  jmp     loc_1800051A9
0x180004fd4  mov     rcx, 5C003F003F005Ch
0x180004fde  mov     [rax], rcx
0x180004fe1  mov     rcx, [rbp+LinkTarget.Buffer]
0x180004fe5  movzx   r8d, word ptr [rdi]; Size
0x180004fe9  add     rcx, 8; void *
0x180004fed  mov     rdx, [rdi+8]; Src
0x180004ff1  call    memcpy_0
0x180004ff6  jmp     short loc_180005025
0x180004ff8  mov     ebx, 0C0000095h
0x180004ffd  jmp     loc_1800051A9
0x180005002  cmp     word ptr [rcx], 5Ch ; '\'
0x180005006  jnz     short loc_18000501D
0x180005008  cmp     word ptr [rcx+2], 5Ch ; '\'
0x18000500d  jnz     short loc_18000501D
0x18000500f  movups  xmm0, xmmword ptr [rdi]
0x180005012  xor     ebx, ebx
0x180005014  movdqu  xmmword ptr [rdx], xmm0
0x180005018  jmp     loc_1800051E0
0x18000501d  movups  xmm0, xmmword ptr [rdi]
0x180005020  movdqu  xmmword ptr [rbp+LinkTarget.Length], xmm0
0x180005025  lea     rax, [rbp+LinkTarget]
0x180005029  mov     [rsp+80h+OpenOptions], 21h ; '!'; OpenOptions
0x180005031  xorps   xmm0, xmm0
0x180005034  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180005038  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x18000503c  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180005043  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180005047  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x18000504f  mov     edx, 100080h; DesiredAccess
0x180005054  mov     [rbp+ObjectAttributes.Attributes], 240h
0x18000505b  lea     rcx, [rbp+FileHandle]; FileHandle
0x18000505f  mov     [rsp+80h+ShareAccess], 7; ShareAccess
0x180005067  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18000506c  call    cs:__imp_NtOpenFile
0x180005072  test    eax, eax
0x180005074  js      short loc_1800050A3
0x180005076  mov     rcx, [rbp+FileHandle]; FileHandle
0x18000507a  xor     r9d, r9d
0x18000507d  mov     qword ptr [rsp+80h+OpenOptions], 0; __int64
0x180005086  mov     r8, rsi
0x180005089  xor     edx, edx
0x18000508b  mov     qword ptr [rsp+80h+ShareAccess], 0; __int64
0x180005094  call    AiGetFullImagePath
0x180005099  mov     ebx, eax
0x18000509b  test    eax, eax
0x18000509d  jns     loc_180005193
0x1800050a3  mov     rcx, [rbp+FileHandle]; Handle
0x1800050a7  test    rcx, rcx
0x1800050aa  jz      short loc_1800050BA
0x1800050ac  call    cs:__imp_NtClose
0x1800050b2  mov     [rbp+FileHandle], 0
0x1800050ba  lea     rax, [rbp+LinkTarget]
0x1800050be  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800050c5  xorps   xmm0, xmm0
0x1800050c8  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1800050cc  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800050d0  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1800050d8  mov     edx, 1; DesiredAccess
0x1800050dd  mov     [rbp+ObjectAttributes.Attributes], 240h
0x1800050e4  lea     rcx, [rbp+FileHandle]; SymbolicLinkHandle
0x1800050e8  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800050ed  call    cs:__imp_NtOpenSymbolicLinkObject
0x1800050f3  test    eax, eax
0x1800050f5  js      loc_180005199
0x1800050fb  mov     rax, [rdi+8]
0x1800050ff  cmp     [rbp+LinkTarget.Buffer], rax
0x180005103  jnz     short loc_18000510F
0x180005105  xor     eax, eax
0x180005107  mov     [rbp+LinkTarget.MaximumLength], ax
0x18000510b  mov     [rbp+LinkTarget.Buffer], rax
0x18000510f  mov     rcx, [rbp+FileHandle]; SymLinkObjHandle
0x180005113  lea     r8, [rbp+DataWritten]; DataWritten
0x180005117  lea     rdx, [rbp+LinkTarget]; LinkTarget
0x18000511b  call    cs:__imp_NtQuerySymbolicLinkObject
0x180005121  mov     ebx, eax
0x180005123  cmp     eax, 0C0000023h
0x180005128  jnz     short loc_180005184
0x18000512a  mov     eax, [rbp+DataWritten]
0x18000512d  cmp     eax, 0FFFFh
0x180005132  ja      short loc_18000518E
0x180005134  cmp     [rbp+LinkTarget.Buffer], 0
0x180005139  jz      short loc_180005157
0x18000513b  mov     rcx, gs:60h
0x180005144  xor     edx, edx; Flags
0x180005146  mov     r8, [rbp+LinkTarget.Buffer]; P
0x18000514a  mov     rcx, [rcx+30h]; HeapHandle
0x18000514e  call    cs:__imp_RtlFreeHeap
0x180005154  mov     eax, [rbp+DataWritten]
0x180005157  movzx   ecx, ax
0x18000515a  mov     [rbp+LinkTarget.MaximumLength], ax
0x18000515e  call    AiAlloc
0x180005163  mov     [rbp+LinkTarget.Buffer], rax
0x180005167  test    rax, rax
0x18000516a  jz      loc_180004FCA
0x180005170  mov     rcx, [rbp+FileHandle]; SymLinkObjHandle
0x180005174  lea     r8, [rbp+DataWritten]; DataWritten
0x180005178  lea     rdx, [rbp+LinkTarget]; LinkTarget
0x18000517c  call    cs:__imp_NtQuerySymbolicLinkObject
0x180005182  mov     ebx, eax
0x180005184  test    ebx, ebx
0x180005186  jns     loc_1800050A3
0x18000518c  jmp     short loc_180005193
0x18000518e  mov     ebx, 0C0000001h
0x180005193  mov     rax, [rbp+LinkTarget.Buffer]
0x180005197  jmp     short loc_1800051A9
0x180005199  movups  xmm0, xmmword ptr [rbp+LinkTarget.Length]
0x18000519d  xor     ebx, ebx
0x18000519f  xor     eax, eax
0x1800051a1  movdqu  xmmword ptr [rsi], xmm0
0x1800051a5  mov     [rbp+LinkTarget.Buffer], rax
0x1800051a9  mov     rcx, [rbp+FileHandle]; Handle
0x1800051ad  test    rcx, rcx
0x1800051b0  jz      short loc_1800051BC
0x1800051b2  call    cs:__imp_NtClose
0x1800051b8  mov     rax, [rbp+LinkTarget.Buffer]
0x1800051bc  test    rax, rax
0x1800051bf  jz      short loc_1800051E0
0x1800051c1  cmp     rax, [rdi+8]
0x1800051c5  jz      short loc_1800051E0
0x1800051c7  mov     rcx, gs:60h
0x1800051d0  xor     edx, edx; Flags
0x1800051d2  mov     r8, [rbp+LinkTarget.Buffer]; P
0x1800051d6  mov     rcx, [rcx+30h]; HeapHandle
0x1800051da  call    cs:__imp_RtlFreeHeap
0x1800051e0  mov     eax, ebx
0x1800051e2  mov     rbx, [rsp+80h+arg_8]
0x1800051ea  add     rsp, 80h
0x1800051f1  pop     rdi
0x1800051f2  pop     rsi
0x1800051f3  pop     rbp
0x1800051f4  retn
```
