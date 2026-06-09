# NetpCreateSecurityObject

- ea: `0x180008bfc`
- end: `0x180008c87`
- name: `NetpCreateSecurityObject`
- size: `139`
- prototype: `__int64 __fastcall(int, int, int, int, PGENERIC_MAPPING, PSECURITY_DESCRIPTOR *NewDescriptor)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180008b04`
- `0x18002eb48`

## callees

- `0x180007604`
- `0x180007f60`
- `0x180008bfc`

## import_xrefs

- `ntdll!NtClose` at `0x180008c6f`
- `ntdll!NtClose` at `0x180008c6f`
- `ntdll!NtOpenProcessToken` at `0x180008c33`
- `ntdll!NtOpenProcessToken` at `0x180008c33`
- `ntdll!RtlNewSecurityObject` at `0x180008c62`
- `ntdll!RtlNewSecurityObject` at `0x180008c62`

## pseudocode

```c
__int64 __fastcall NetpCreateSecurityObject(
        __int64 a1,
        unsigned int a2,
        void *a3,
        void *a4,
        PGENERIC_MAPPING GenericMapping,
        PSECURITY_DESCRIPTOR *NewDescriptor)
{
  __int64 result; // rax
  NTSTATUS v7; // ebx
  PSECURITY_DESCRIPTOR CreatorDescriptor; // [rsp+30h] [rbp-18h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-10h] BYREF

  CreatorDescriptor = 0;
  TokenHandle = 0;
  result = NetpCreateSecurityDescriptor(a1, a2, a3, a4, (struct _ACL **)&CreatorDescriptor);
  if ( (int)result >= 0 )
  {
    v7 = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, &TokenHandle);
    if ( v7 >= 0 )
    {
      v7 = RtlNewSecurityObject(0, CreatorDescriptor, NewDescriptor, 0, TokenHandle, GenericMapping);
      NtClose(TokenHandle);
    }
    NetpMemoryFree(CreatorDescriptor);
    return (unsigned int)v7;
  }
  return result;
}

```

## disassembly

```asm
0x180008bfc  mov     r11, rsp
0x180008bff  push    rbx
0x180008c00  sub     rsp, 40h
0x180008c04  lea     rax, [r11-18h]
0x180008c08  mov     qword ptr [r11-18h], 0
0x180008c10  mov     [r11-28h], rax
0x180008c14  mov     qword ptr [r11-10h], 0
0x180008c1c  call    NetpCreateSecurityDescriptor
0x180008c21  test    eax, eax
0x180008c23  js      short loc_180008C81
0x180008c25  lea     r8, [rsp+48h+TokenHandle]; TokenHandle
0x180008c2a  mov     edx, 8; DesiredAccess
0x180008c2f  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180008c33  call    cs:__imp_NtOpenProcessToken
0x180008c39  mov     ebx, eax
0x180008c3b  test    eax, eax
0x180008c3d  js      short loc_180008C75
0x180008c3f  mov     rax, [rsp+48h+arg_20]
0x180008c44  xor     r9d, r9d; IsDirectoryObject
0x180008c47  mov     r8, [rsp+48h+NewDescriptor]; NewDescriptor
0x180008c4c  xor     ecx, ecx; ParentDescriptor
0x180008c4e  mov     rdx, [rsp+48h+CreatorDescriptor]; CreatorDescriptor
0x180008c53  mov     [rsp+48h+GenericMapping], rax; GenericMapping
0x180008c58  mov     rax, [rsp+48h+TokenHandle]
0x180008c5d  mov     [rsp+48h+Token], rax; Token
0x180008c62  call    cs:__imp_RtlNewSecurityObject
0x180008c68  mov     rcx, [rsp+48h+TokenHandle]; Handle
0x180008c6d  mov     ebx, eax
0x180008c6f  call    cs:__imp_NtClose
0x180008c75  mov     rcx, [rsp+48h+CreatorDescriptor]
0x180008c7a  call    NetpMemoryFree
0x180008c7f  mov     eax, ebx
0x180008c81  add     rsp, 40h
0x180008c85  pop     rbx
0x180008c86  retn
```
