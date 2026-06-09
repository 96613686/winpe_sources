# BaseRegReplaceKeyInternal

- ea: `0x18006d4fc`
- end: `0x18006d82b`
- name: `BaseRegReplaceKeyInternal`
- size: `815`
- prototype: `ULONG __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180054960`
- `0x1800552d0`

## callees

- `0x18006d4fc`
- `0x1800719b8`

## import_xrefs

- `ntdll!NtClose` at `0x18006d661`
- `ntdll!NtClose` at `0x18006d818`
- `ntdll!NtClose` at `0x18006d661`
- `ntdll!NtClose` at `0x18006d818`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x18006d64d`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x18006d6fd`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x18006d64d`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x18006d6fd`
- `ntdll!RtlReleaseRelativeName` at `0x18006d712`
- `ntdll!RtlReleaseRelativeName` at `0x18006d7bc`
- `ntdll!RtlReleaseRelativeName` at `0x18006d7cc`
- `ntdll!RtlReleaseRelativeName` at `0x18006d712`
- `ntdll!RtlReleaseRelativeName` at `0x18006d7bc`
- `ntdll!RtlReleaseRelativeName` at `0x18006d7cc`
- `ntdll!NtReplaceKey` at `0x18006d7a9`
- `ntdll!NtReplaceKey` at `0x18006d7a9`
- `ntdll!RtlFreeHeap` at `0x18006d730`
- `ntdll!RtlFreeHeap` at `0x18006d7ea`
- `ntdll!RtlFreeHeap` at `0x18006d808`
- `ntdll!RtlFreeHeap` at `0x18006d730`
- `ntdll!RtlFreeHeap` at `0x18006d7ea`
- `ntdll!RtlFreeHeap` at `0x18006d808`
- `ntdll!RtlNtStatusToDosError` at `0x18006d62e`
- `ntdll!RtlNtStatusToDosError` at `0x18006d62e`

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
0x18006d4fc  mov     [rsp-8+arg_8], rbx
0x18006d501  mov     [rsp-8+arg_10], rsi
0x18006d506  push    rbp
0x18006d507  push    rdi
0x18006d508  push    r14
0x18006d50a  lea     rbp, [rsp-30h]
0x18006d50f  sub     rsp, 130h
0x18006d516  xorps   xmm0, xmm0
0x18006d519  xor     r14d, r14d
0x18006d51c  xorps   xmm1, xmm1
0x18006d51f  mov     [rbp+40h+Handle], r14
0x18006d523  xor     eax, eax
0x18006d525  mov     [rbp+40h+var_3C], r14d
0x18006d529  mov     [rbp+40h+var_24], r14d
0x18006d52d  mov     rdi, r9
0x18006d530  mov     rbx, r8
0x18006d533  movups  xmmword ptr [rbp+40h+ObjectAttributes.ObjectName], xmm0
0x18006d537  movups  xmmword ptr [rbp+40h+ReplacedObjectAttributes.ObjectName], xmm0
0x18006d53b  movups  xmmword ptr [rbp+40h+ObjectAttributes+1Ch], xmm0
0x18006d53f  movups  xmmword ptr [rbp+40h+ReplacedObjectAttributes+1Ch], xmm0
0x18006d543  movups  xmmword ptr [rsp+140h+NtName.Length], xmm0
0x18006d548  movups  xmmword ptr [rsp+140h+var_F0.Length], xmm1
0x18006d54d  movups  xmmword ptr [rsp+140h+RelativeName.RelativeName.Length], xmm0
0x18006d552  movups  xmmword ptr [rsp+140h+RelativeName.ContainingDirectory], xmm0
0x18006d557  movups  xmmword ptr [rbp+40h+var_C0.RelativeName.Length], xmm1
0x18006d55b  movups  xmmword ptr [rbp+40h+var_C0.ContainingDirectory], xmm1
0x18006d55f  movups  xmmword ptr [rbp+40h+ObjectAttributes.Length], xmm0
0x18006d563  movups  xmmword ptr [rbp+40h+ReplacedObjectAttributes.Length], xmm0
0x18006d567  test    rcx, rcx
0x18006d56a  jz      loc_18006D66D
0x18006d570  test    rbx, rbx
0x18006d573  jz      loc_18006D66D
0x18006d579  cmp     [r8+8], r14
0x18006d57d  jz      loc_18006D66D
0x18006d583  mov     al, 1
0x18006d585  test    [r8], al
0x18006d588  jnz     loc_18006D66D
0x18006d58e  test    r9, r9
0x18006d591  jz      loc_18006D66D
0x18006d597  cmp     [r9+8], r14
0x18006d59b  jz      loc_18006D66D
0x18006d5a1  test    [r9], al
0x18006d5a4  jnz     loc_18006D66D
0x18006d5aa  test    rdx, rdx
0x18006d5ad  jz      short loc_18006D5D6
0x18006d5af  test    [rdx], al
0x18006d5b1  jnz     loc_18006D66D
0x18006d5b7  cmp     [rdx], r14w
0x18006d5bb  jz      short loc_18006D5C7
0x18006d5bd  cmp     [rdx+8], r14
0x18006d5c1  jz      loc_18006D66D
0x18006d5c7  movzx   eax, word ptr [rdx]
0x18006d5ca  test    ax, ax
0x18006d5cd  jz      short loc_18006D5D6
0x18006d5cf  sub     ax, 2
0x18006d5d3  mov     [rdx], ax
0x18006d5d6  movzx   eax, word ptr [r8]
0x18006d5da  test    ax, ax
0x18006d5dd  jz      short loc_18006D5E7
0x18006d5df  sub     ax, 2
0x18006d5e3  mov     [r8], ax
0x18006d5e7  movzx   eax, word ptr [r9]
0x18006d5eb  test    ax, ax
0x18006d5ee  jz      short loc_18006D5F8
0x18006d5f0  sub     ax, 2
0x18006d5f4  mov     [r9], ax
0x18006d5f8  mov     [rbp+40h+var_38], rcx
0x18006d5fc  lea     r8, [rbp+40h+var_40]; int
0x18006d600  lea     rcx, [rbp+40h+Handle]; int
0x18006d604  mov     [rbp+40h+var_40], 30h ; '0'
0x18006d60b  mov     [rbp+40h+var_28], 40h ; '@'
0x18006d612  mov     [rbp+40h+var_30], rdx
0x18006d616  movdqu  [rbp+40h+var_20], xmm0
0x18006d61b  mov     [rsp+140h+var_118], 4; int
0x18006d623  call    Wow64NtCreateKey
0x18006d628  test    eax, eax
0x18006d62a  jns     short loc_18006D63C
0x18006d62c  mov     ecx, eax; Status
0x18006d62e  call    cs:__imp_RtlNtStatusToDosError
0x18006d635  nop     dword ptr [rax+rax+00h]
0x18006d63a  jmp     short loc_18006D672
0x18006d63c  mov     rcx, [rbx+8]; DosName
0x18006d640  lea     r9, [rsp+140h+RelativeName]; RelativeName
0x18006d645  xor     r8d, r8d; PartName
0x18006d648  lea     rdx, [rsp+140h+NtName]; NtName
0x18006d64d  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U
0x18006d654  nop     dword ptr [rax+rax+00h]
0x18006d659  test    al, al
0x18006d65b  jnz     short loc_18006D68B
0x18006d65d  mov     rcx, [rbp+40h+Handle]; Handle
0x18006d661  call    cs:__imp_NtClose
0x18006d668  nop     dword ptr [rax+rax+00h]
0x18006d66d  mov     eax, 57h ; 'W'
0x18006d672  lea     r11, [rsp+140h+var_10]
0x18006d67a  mov     rbx, [r11+28h]
0x18006d67e  mov     rsi, [r11+30h]
0x18006d682  mov     rsp, r11
0x18006d685  pop     r14
0x18006d687  pop     rdi
0x18006d688  pop     rbp
0x18006d689  retn
0x18006d68b  movzx   eax, [rsp+140h+RelativeName.RelativeName.Length]
0x18006d690  mov     rsi, [rsp+140h+NtName.Buffer]
0x18006d695  test    ax, ax
0x18006d698  jz      short loc_18006D6C2
0x18006d69a  mov     [rsp+140h+NtName.Length], ax
0x18006d69f  mov     eax, dword ptr [rsp+140h+RelativeName.RelativeName.MaximumLength]
0x18006d6a3  mov     dword ptr [rsp+140h+NtName.MaximumLength], eax
0x18006d6a7  movzx   eax, word ptr [rsp+140h+RelativeName.RelativeName+6]
0x18006d6ac  mov     word ptr [rsp+140h+NtName+6], ax
0x18006d6b1  mov     rax, [rsp+140h+RelativeName.RelativeName.Buffer]
0x18006d6b6  mov     [rsp+140h+NtName.Buffer], rax
0x18006d6bb  mov     rax, [rsp+140h+RelativeName.ContainingDirectory]
0x18006d6c0  jmp     short loc_18006D6CA
0x18006d6c2  mov     rax, r14
0x18006d6c5  mov     [rsp+140h+RelativeName.ContainingDirectory], rax
0x18006d6ca  mov     rcx, [rdi+8]; DosName
0x18006d6ce  lea     r9, [rbp+40h+var_C0]; RelativeName
0x18006d6d2  mov     [rbp+40h+ObjectAttributes.RootDirectory], rax
0x18006d6d6  lea     rdx, [rsp+140h+var_F0]; NtName
0x18006d6db  lea     rax, [rsp+140h+NtName]
0x18006d6e0  mov     [rbp+40h+ObjectAttributes.Length], 30h ; '0'
0x18006d6e7  xorps   xmm0, xmm0
0x18006d6ea  mov     [rbp+40h+ObjectAttributes.ObjectName], rax
0x18006d6ee  xor     r8d, r8d; PartName
0x18006d6f1  mov     [rbp+40h+ObjectAttributes.Attributes], 40h ; '@'
0x18006d6f8  movdqu  xmmword ptr [rbp+40h+ObjectAttributes.SecurityDescriptor], xmm0
0x18006d6fd  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U
0x18006d704  nop     dword ptr [rax+rax+00h]
0x18006d709  test    al, al
0x18006d70b  jnz     short loc_18006D741
0x18006d70d  lea     rcx, [rsp+140h+RelativeName]; RelativeName
0x18006d712  call    cs:__imp_RtlReleaseRelativeName
0x18006d719  nop     dword ptr [rax+rax+00h]
0x18006d71e  mov     rcx, gs:60h
0x18006d727  mov     r8, rsi; P
0x18006d72a  xor     edx, edx; Flags
0x18006d72c  mov     rcx, [rcx+30h]; HeapHandle
0x18006d730  call    cs:__imp_RtlFreeHeap
0x18006d737  nop     dword ptr [rax+rax+00h]
0x18006d73c  jmp     loc_18006D65D
0x18006d741  movzx   eax, [rbp+40h+var_C0.RelativeName.Length]
0x18006d745  mov     rdi, [rsp+140h+var_F0.Buffer]
0x18006d74a  test    ax, ax
0x18006d74d  jz      short loc_18006D773
0x18006d74f  mov     [rsp+140h+var_F0.Length], ax
0x18006d754  mov     eax, dword ptr [rbp+40h+var_C0.RelativeName.MaximumLength]
0x18006d757  mov     dword ptr [rsp+140h+var_F0.MaximumLength], eax
0x18006d75b  movzx   eax, word ptr [rbp+40h+var_C0.RelativeName+6]
0x18006d75f  mov     word ptr [rsp+140h+var_F0+6], ax
0x18006d764  mov     rax, [rbp+40h+var_C0.RelativeName.Buffer]
0x18006d768  mov     [rsp+140h+var_F0.Buffer], rax
0x18006d76d  mov     rax, [rbp+40h+var_C0.ContainingDirectory]
0x18006d771  jmp     short loc_18006D77A
0x18006d773  mov     rax, r14
0x18006d776  mov     [rbp+40h+var_C0.ContainingDirectory], rax
0x18006d77a  mov     rdx, [rbp+40h+Handle]; Key
0x18006d77e  lea     r8, [rbp+40h+ReplacedObjectAttributes]; ReplacedObjectAttributes
0x18006d782  mov     [rbp+40h+ReplacedObjectAttributes.RootDirectory], rax
0x18006d786  lea     rcx, [rbp+40h+ObjectAttributes]; ObjectAttributes
0x18006d78a  lea     rax, [rsp+140h+var_F0]
0x18006d78f  mov     [rbp+40h+ReplacedObjectAttributes.Length], 30h ; '0'
0x18006d796  xorps   xmm0, xmm0
0x18006d799  mov     [rbp+40h+ReplacedObjectAttributes.ObjectName], rax
0x18006d79d  mov     [rbp+40h+ReplacedObjectAttributes.Attributes], 40h ; '@'
0x18006d7a4  movdqu  xmmword ptr [rbp+40h+ReplacedObjectAttributes.SecurityDescriptor], xmm0
0x18006d7a9  call    cs:__imp_NtReplaceKey
0x18006d7b0  nop     dword ptr [rax+rax+00h]
0x18006d7b5  lea     rcx, [rsp+140h+RelativeName]; RelativeName
0x18006d7ba  mov     ebx, eax
0x18006d7bc  call    cs:__imp_RtlReleaseRelativeName
0x18006d7c3  nop     dword ptr [rax+rax+00h]
0x18006d7c8  lea     rcx, [rbp+40h+var_C0]; RelativeName
0x18006d7cc  call    cs:__imp_RtlReleaseRelativeName
0x18006d7d3  nop     dword ptr [rax+rax+00h]
0x18006d7d8  mov     rcx, gs:60h
0x18006d7e1  mov     r8, rsi; P
0x18006d7e4  xor     edx, edx; Flags
0x18006d7e6  mov     rcx, [rcx+30h]; HeapHandle
0x18006d7ea  call    cs:__imp_RtlFreeHeap
0x18006d7f1  nop     dword ptr [rax+rax+00h]
0x18006d7f6  mov     rcx, gs:60h
0x18006d7ff  mov     r8, rdi; P
0x18006d802  xor     edx, edx; Flags
0x18006d804  mov     rcx, [rcx+30h]; HeapHandle
0x18006d808  call    cs:__imp_RtlFreeHeap
0x18006d80f  nop     dword ptr [rax+rax+00h]
0x18006d814  mov     rcx, [rbp+40h+Handle]; Handle
0x18006d818  call    cs:__imp_NtClose
0x18006d81f  nop     dword ptr [rax+rax+00h]
0x18006d824  mov     ecx, ebx
0x18006d826  jmp     loc_18006D62E
```
