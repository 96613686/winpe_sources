# BaseRegReplaceKeyInternal

- ea: `0x180060ad4`
- end: `0x180060dba`
- name: `BaseRegReplaceKeyInternal`
- size: `742`
- prototype: `ULONG __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18004e5c0`
- `0x18004ee50`

## callees

- `0x180060ad4`
- `0x180064a10`

## import_xrefs

- `ntdll!NtClose` at `0x180060c2d`
- `ntdll!NtClose` at `0x180060dad`
- `ntdll!NtClose` at `0x180060c2d`
- `ntdll!NtClose` at `0x180060dad`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x180060c1f`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x180060cc2`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x180060c1f`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x180060cc2`
- `ntdll!RtlReleaseRelativeName` at `0x180060cd1`
- `ntdll!RtlReleaseRelativeName` at `0x180060d69`
- `ntdll!RtlReleaseRelativeName` at `0x180060d73`
- `ntdll!RtlReleaseRelativeName` at `0x180060cd1`
- `ntdll!RtlReleaseRelativeName` at `0x180060d69`
- `ntdll!RtlReleaseRelativeName` at `0x180060d73`
- `ntdll!NtReplaceKey` at `0x180060d5c`
- `ntdll!NtReplaceKey` at `0x180060d5c`
- `ntdll!RtlFreeHeap` at `0x180060ce9`
- `ntdll!RtlFreeHeap` at `0x180060d8b`
- `ntdll!RtlFreeHeap` at `0x180060da3`
- `ntdll!RtlFreeHeap` at `0x180060ce9`
- `ntdll!RtlFreeHeap` at `0x180060d8b`
- `ntdll!RtlFreeHeap` at `0x180060da3`
- `ntdll!RtlNtStatusToDosError` at `0x180060c06`
- `ntdll!RtlNtStatusToDosError` at `0x180060c06`

## pseudocode

```c
ULONG __fastcall BaseRegReplaceKeyInternal(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  int Key; // eax
  NTSTATUS v7; // ecx
  PWSTR Buffer; // rsi
  HANDLE ContainingDirectory; // rax
  const WCHAR *v11; // rcx
  PWSTR v12; // rdi
  HANDLE v13; // rax
  NTSTATUS v14; // ebx
  void *v15; // [rsp+20h] [rbp-E0h]
  struct _UNICODE_STRING NtName; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING v17; // [rsp+50h] [rbp-B0h] BYREF
  struct _RTL_RELATIVE_NAME_U RelativeName; // [rsp+60h] [rbp-A0h] BYREF
  struct _RTL_RELATIVE_NAME_U v19; // [rsp+80h] [rbp-80h] BYREF
  struct _OBJECT_ATTRIBUTES ReplacedObjectAttributes; // [rsp+A0h] [rbp-60h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+D0h] [rbp-30h] BYREF
  int v22[2]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v23; // [rsp+108h] [rbp+8h]
  __int64 v24; // [rsp+110h] [rbp+10h]
  int v25; // [rsp+118h] [rbp+18h]
  int v26; // [rsp+11Ch] [rbp+1Ch]
  __int128 v27; // [rsp+120h] [rbp+20h]
  HANDLE Handle; // [rsp+150h] [rbp+50h] BYREF

  Handle = 0;
  v22[1] = 0;
  v26 = 0;
  NtName = 0;
  v17 = 0;
  memset(&RelativeName, 0, sizeof(RelativeName));
  memset(&v19, 0, sizeof(v19));
  memset(&ObjectAttributes, 0, 44);
  memset(&ReplacedObjectAttributes, 0, 44);
  if ( !a1
    || !a3
    || !*(_QWORD *)(a3 + 8)
    || (*(_BYTE *)a3 & 1) != 0
    || !a4
    || !*(_QWORD *)(a4 + 8)
    || (*(_BYTE *)a4 & 1) != 0 )
  {
    return 87;
  }
  if ( a2 )
  {
    if ( (*(_BYTE *)a2 & 1) != 0 || *(_WORD *)a2 && !*(_QWORD *)(a2 + 8) )
      return 87;
    if ( *(_WORD *)a2 )
      *(_WORD *)a2 -= 2;
  }
  if ( *(_WORD *)a3 )
    *(_WORD *)a3 -= 2;
  if ( *(_WORD *)a4 )
    *(_WORD *)a4 -= 2;
  v23 = a1;
  v22[0] = 48;
  v25 = 64;
  v24 = a2;
  v27 = 0;
  Key = Wow64NtCreateKey((int)&Handle, a2, (int)v22, a4, v15, 4);
  if ( Key < 0 )
  {
    v7 = Key;
    return RtlNtStatusToDosError(v7);
  }
  if ( RtlDosPathNameToRelativeNtPathName_U(*(PCWSTR *)(a3 + 8), &NtName, 0, &RelativeName) )
  {
    Buffer = NtName.Buffer;
    if ( RelativeName.RelativeName.Length )
    {
      NtName = RelativeName.RelativeName;
      ContainingDirectory = RelativeName.ContainingDirectory;
    }
    else
    {
      ContainingDirectory = 0;
      RelativeName.ContainingDirectory = 0;
    }
    v11 = *(const WCHAR **)(a4 + 8);
    ObjectAttributes.RootDirectory = ContainingDirectory;
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &NtName;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( RtlDosPathNameToRelativeNtPathName_U(v11, &v17, 0, &v19) )
    {
      v12 = v17.Buffer;
      if ( v19.RelativeName.Length )
      {
        v17 = v19.RelativeName;
        v13 = v19.ContainingDirectory;
      }
      else
      {
        v13 = 0;
        v19.ContainingDirectory = 0;
      }
      ReplacedObjectAttributes.RootDirectory = v13;
      ReplacedObjectAttributes.Length = 48;
      ReplacedObjectAttributes.ObjectName = &v17;
      ReplacedObjectAttributes.Attributes = 64;
      *(_OWORD *)&ReplacedObjectAttributes.SecurityDescriptor = 0;
      v14 = NtReplaceKey(&ObjectAttributes, Handle, &ReplacedObjectAttributes);
      RtlReleaseRelativeName(&RelativeName);
      RtlReleaseRelativeName(&v19);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v12);
      NtClose(Handle);
      v7 = v14;
      return RtlNtStatusToDosError(v7);
    }
    RtlReleaseRelativeName(&RelativeName);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
  }
  NtClose(Handle);
  return 87;
}

```

## disassembly

```asm
0x180060ad4  mov     [rsp-8+arg_8], rbx
0x180060ad9  mov     [rsp-8+arg_10], rsi
0x180060ade  push    rbp
0x180060adf  push    rdi
0x180060ae0  push    r14
0x180060ae2  lea     rbp, [rsp-30h]
0x180060ae7  sub     rsp, 130h
0x180060aee  xorps   xmm0, xmm0
0x180060af1  xor     r14d, r14d
0x180060af4  xorps   xmm1, xmm1
0x180060af7  mov     [rbp+40h+Handle], r14
0x180060afb  xor     eax, eax
0x180060afd  mov     [rbp+40h+var_3C], r14d
0x180060b01  mov     [rbp+40h+var_24], r14d
0x180060b05  mov     rdi, r9
0x180060b08  mov     rbx, r8
0x180060b0b  movups  xmmword ptr [rbp+40h+ObjectAttributes.ObjectName], xmm0
0x180060b0f  movups  xmmword ptr [rbp+40h+ReplacedObjectAttributes.ObjectName], xmm0
0x180060b13  movups  xmmword ptr [rbp+40h+ObjectAttributes+1Ch], xmm0
0x180060b17  movups  xmmword ptr [rbp+40h+ReplacedObjectAttributes+1Ch], xmm0
0x180060b1b  movups  xmmword ptr [rsp+140h+NtName.Length], xmm0
0x180060b20  movups  xmmword ptr [rsp+140h+var_F0.Length], xmm1
0x180060b25  movups  xmmword ptr [rsp+140h+RelativeName.RelativeName.Length], xmm0
0x180060b2a  movups  xmmword ptr [rsp+140h+RelativeName.ContainingDirectory], xmm0
0x180060b2f  movups  xmmword ptr [rbp+40h+var_C0.RelativeName.Length], xmm1
0x180060b33  movups  xmmword ptr [rbp+40h+var_C0.ContainingDirectory], xmm1
0x180060b37  movups  xmmword ptr [rbp+40h+ObjectAttributes.Length], xmm0
0x180060b3b  movups  xmmword ptr [rbp+40h+ReplacedObjectAttributes.Length], xmm0
0x180060b3f  test    rcx, rcx
0x180060b42  jz      loc_180060C33
0x180060b48  test    rbx, rbx
0x180060b4b  jz      loc_180060C33
0x180060b51  cmp     [r8+8], r14
0x180060b55  jz      loc_180060C33
0x180060b5b  mov     al, 1
0x180060b5d  test    [r8], al
0x180060b60  jnz     loc_180060C33
0x180060b66  test    r9, r9
0x180060b69  jz      loc_180060C33
0x180060b6f  cmp     [r9+8], r14
0x180060b73  jz      loc_180060C33
0x180060b79  test    [r9], al
0x180060b7c  jnz     loc_180060C33
0x180060b82  test    rdx, rdx
0x180060b85  jz      short loc_180060BAE
0x180060b87  test    [rdx], al
0x180060b89  jnz     loc_180060C33
0x180060b8f  cmp     [rdx], r14w
0x180060b93  jz      short loc_180060B9F
0x180060b95  cmp     [rdx+8], r14
0x180060b99  jz      loc_180060C33
0x180060b9f  movzx   eax, word ptr [rdx]
0x180060ba2  test    ax, ax
0x180060ba5  jz      short loc_180060BAE
0x180060ba7  sub     ax, 2
0x180060bab  mov     [rdx], ax
0x180060bae  movzx   eax, word ptr [r8]
0x180060bb2  test    ax, ax
0x180060bb5  jz      short loc_180060BBF
0x180060bb7  sub     ax, 2
0x180060bbb  mov     [r8], ax
0x180060bbf  movzx   eax, word ptr [r9]
0x180060bc3  test    ax, ax
0x180060bc6  jz      short loc_180060BD0
0x180060bc8  sub     ax, 2
0x180060bcc  mov     [r9], ax
0x180060bd0  mov     [rbp+40h+var_38], rcx
0x180060bd4  lea     r8, [rbp+40h+var_40]; int
0x180060bd8  lea     rcx, [rbp+40h+Handle]; int
0x180060bdc  mov     [rbp+40h+var_40], 30h ; '0'
0x180060be3  mov     [rbp+40h+var_28], 40h ; '@'
0x180060bea  mov     [rbp+40h+var_30], rdx
0x180060bee  movdqu  [rbp+40h+var_20], xmm0
0x180060bf3  mov     [rsp+140h+var_118], 4; int
0x180060bfb  call    Wow64NtCreateKey
0x180060c00  test    eax, eax
0x180060c02  jns     short loc_180060C0E
0x180060c04  mov     ecx, eax; Status
0x180060c06  call    cs:__imp_RtlNtStatusToDosError
0x180060c0c  jmp     short loc_180060C38
0x180060c0e  mov     rcx, [rbx+8]; DosName
0x180060c12  lea     r9, [rsp+140h+RelativeName]; RelativeName
0x180060c17  xor     r8d, r8d; PartName
0x180060c1a  lea     rdx, [rsp+140h+NtName]; NtName
0x180060c1f  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U
0x180060c25  test    al, al
0x180060c27  jnz     short loc_180060C50
0x180060c29  mov     rcx, [rbp+40h+Handle]; Handle
0x180060c2d  call    cs:__imp_NtClose
0x180060c33  mov     eax, 57h ; 'W'
0x180060c38  lea     r11, [rsp+140h+var_10]
0x180060c40  mov     rbx, [r11+28h]
0x180060c44  mov     rsi, [r11+30h]
0x180060c48  mov     rsp, r11
0x180060c4b  pop     r14
0x180060c4d  pop     rdi
0x180060c4e  pop     rbp
0x180060c4f  retn
0x180060c50  movzx   eax, [rsp+140h+RelativeName.RelativeName.Length]
0x180060c55  mov     rsi, [rsp+140h+NtName.Buffer]
0x180060c5a  test    ax, ax
0x180060c5d  jz      short loc_180060C87
0x180060c5f  mov     [rsp+140h+NtName.Length], ax
0x180060c64  mov     eax, dword ptr [rsp+140h+RelativeName.RelativeName.MaximumLength]
0x180060c68  mov     dword ptr [rsp+140h+NtName.MaximumLength], eax
0x180060c6c  movzx   eax, word ptr [rsp+140h+RelativeName.RelativeName+6]
0x180060c71  mov     word ptr [rsp+140h+NtName+6], ax
0x180060c76  mov     rax, [rsp+140h+RelativeName.RelativeName.Buffer]
0x180060c7b  mov     [rsp+140h+NtName.Buffer], rax
0x180060c80  mov     rax, [rsp+140h+RelativeName.ContainingDirectory]
0x180060c85  jmp     short loc_180060C8F
0x180060c87  mov     rax, r14
0x180060c8a  mov     [rsp+140h+RelativeName.ContainingDirectory], rax
0x180060c8f  mov     rcx, [rdi+8]; DosName
0x180060c93  lea     r9, [rbp+40h+var_C0]; RelativeName
0x180060c97  mov     [rbp+40h+ObjectAttributes.RootDirectory], rax
0x180060c9b  lea     rdx, [rsp+140h+var_F0]; NtName
0x180060ca0  lea     rax, [rsp+140h+NtName]
0x180060ca5  mov     [rbp+40h+ObjectAttributes.Length], 30h ; '0'
0x180060cac  xorps   xmm0, xmm0
0x180060caf  mov     [rbp+40h+ObjectAttributes.ObjectName], rax
0x180060cb3  xor     r8d, r8d; PartName
0x180060cb6  mov     [rbp+40h+ObjectAttributes.Attributes], 40h ; '@'
0x180060cbd  movdqu  xmmword ptr [rbp+40h+ObjectAttributes.SecurityDescriptor], xmm0
0x180060cc2  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U
0x180060cc8  test    al, al
0x180060cca  jnz     short loc_180060CF4
0x180060ccc  lea     rcx, [rsp+140h+RelativeName]; RelativeName
0x180060cd1  call    cs:__imp_RtlReleaseRelativeName
0x180060cd7  mov     rcx, gs:60h
0x180060ce0  mov     r8, rsi; P
0x180060ce3  xor     edx, edx; Flags
0x180060ce5  mov     rcx, [rcx+30h]; HeapHandle
0x180060ce9  call    cs:__imp_RtlFreeHeap
0x180060cef  jmp     loc_180060C29
0x180060cf4  movzx   eax, [rbp+40h+var_C0.RelativeName.Length]
0x180060cf8  mov     rdi, [rsp+140h+var_F0.Buffer]
0x180060cfd  test    ax, ax
0x180060d00  jz      short loc_180060D26
0x180060d02  mov     [rsp+140h+var_F0.Length], ax
0x180060d07  mov     eax, dword ptr [rbp+40h+var_C0.RelativeName.MaximumLength]
0x180060d0a  mov     dword ptr [rsp+140h+var_F0.MaximumLength], eax
0x180060d0e  movzx   eax, word ptr [rbp+40h+var_C0.RelativeName+6]
0x180060d12  mov     word ptr [rsp+140h+var_F0+6], ax
0x180060d17  mov     rax, [rbp+40h+var_C0.RelativeName.Buffer]
0x180060d1b  mov     [rsp+140h+var_F0.Buffer], rax
0x180060d20  mov     rax, [rbp+40h+var_C0.ContainingDirectory]
0x180060d24  jmp     short loc_180060D2D
0x180060d26  mov     rax, r14
0x180060d29  mov     [rbp+40h+var_C0.ContainingDirectory], rax
0x180060d2d  mov     rdx, [rbp+40h+Handle]; Key
0x180060d31  lea     r8, [rbp+40h+ReplacedObjectAttributes]; ReplacedObjectAttributes
0x180060d35  mov     [rbp+40h+ReplacedObjectAttributes.RootDirectory], rax
0x180060d39  lea     rcx, [rbp+40h+ObjectAttributes]; ObjectAttributes
0x180060d3d  lea     rax, [rsp+140h+var_F0]
0x180060d42  mov     [rbp+40h+ReplacedObjectAttributes.Length], 30h ; '0'
0x180060d49  xorps   xmm0, xmm0
0x180060d4c  mov     [rbp+40h+ReplacedObjectAttributes.ObjectName], rax
0x180060d50  mov     [rbp+40h+ReplacedObjectAttributes.Attributes], 40h ; '@'
0x180060d57  movdqu  xmmword ptr [rbp+40h+ReplacedObjectAttributes.SecurityDescriptor], xmm0
0x180060d5c  call    cs:__imp_NtReplaceKey
0x180060d62  lea     rcx, [rsp+140h+RelativeName]; RelativeName
0x180060d67  mov     ebx, eax
0x180060d69  call    cs:__imp_RtlReleaseRelativeName
0x180060d6f  lea     rcx, [rbp+40h+var_C0]; RelativeName
0x180060d73  call    cs:__imp_RtlReleaseRelativeName
0x180060d79  mov     rcx, gs:60h
0x180060d82  mov     r8, rsi; P
0x180060d85  xor     edx, edx; Flags
0x180060d87  mov     rcx, [rcx+30h]; HeapHandle
0x180060d8b  call    cs:__imp_RtlFreeHeap
0x180060d91  mov     rcx, gs:60h
0x180060d9a  mov     r8, rdi; P
0x180060d9d  xor     edx, edx; Flags
0x180060d9f  mov     rcx, [rcx+30h]; HeapHandle
0x180060da3  call    cs:__imp_RtlFreeHeap
0x180060da9  mov     rcx, [rbp+40h+Handle]; Handle
0x180060dad  call    cs:__imp_NtClose
0x180060db3  mov     ecx, ebx
0x180060db5  jmp     loc_180060C06
```
