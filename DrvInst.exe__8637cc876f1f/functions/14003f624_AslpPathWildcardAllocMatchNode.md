# AslpPathWildcardAllocMatchNode

- ea: `0x14003f624`
- end: `0x14003f8aa`
- name: `AslpPathWildcardAllocMatchNode`
- size: `646`
- prototype: `__int64 __fastcall(unsigned __int16 *, _WORD *, _WORD *, int, __int64, unsigned __int16)`
- caller_count: `2`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14003e294`
- `0x14003e7fc`

## callees

- `0x14003bf18`
- `0x14003f624`
- `0x14003f9a4`
- `0x14003fd84`
- `0x14003fda8`
- `0x14003fe48`
- `0x14003ff04`
- `0x14003ffb8`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x14003f71f`
- `ntdll!RtlAllocateHeap` at `0x14003f71f`
- `ntdll!ZwOpenFile` at `0x14003f85a`
- `ntdll!ZwOpenFile` at `0x14003f85a`

## string_xrefs

- `0x14003f877`: `AslpPathWildcardAllocMatchNode`
- `0x14003f749`: `RtlUnicodeStringCopy failed [%x]`
- `0x14003f866`: `Failed to open dir [%x]`

## pseudocode

```c
__int64 __fastcall AslpPathWildcardAllocMatchNode(
        unsigned __int16 *a1,
        _WORD *a2,
        _WORD *a3,
        int a4,
        __int64 a5,
        unsigned __int16 a6)
{
  int v8; // edi
  NTSTATUS v9; // eax
  const char *v10; // r9
  __int64 v11; // r8
  unsigned int v12; // ecx
  PVOID Heap; // rax
  __int16 v14; // bx
  ULONG ShareAccess[2]; // [rsp+20h] [rbp-60h]
  __int64 v17; // [rsp+30h] [rbp-50h] BYREF
  __int64 v18; // [rsp+38h] [rbp-48h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  __int64 v21; // [rsp+A0h] [rbp+20h] BYREF
  __int64 v22; // [rsp+B0h] [rbp+30h] BYREF

  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  *(_QWORD *)a1 = 0;
  *((_QWORD *)a1 + 1) = 0;
  *((_QWORD *)a1 + 3) = 0;
  while ( 1 )
  {
    *((_QWORD *)a1 + 2) = a3;
    if ( !*a3 )
      break;
    ++a3;
  }
  *((_QWORD *)a1 + 2) = a3 + 1;
  if ( !a3[1] )
  {
    v8 = a4 != 0 ? -1073741638 : -1073741197;
LABEL_27:
    AslpPathWildcardFreeMatchNode(a1);
    return (unsigned int)v8;
  }
  if ( !a4 )
  {
    v8 = -1073741565;
    goto LABEL_27;
  }
  LOWORD(v21) = *a2;
  v9 = RtlUShortAdd((unsigned __int16)v21, a6, &v21);
  v8 = v9;
  if ( v9 < 0 )
  {
    v10 = "RtlUShortAdd failed [%x]";
    v11 = 2886;
LABEL_26:
    ShareAccess[0] = v9;
    AslLogCallPrintf(1, "AslpPathWildcardAllocMatchNode", v11, v10, *(_QWORD *)ShareAccess);
    goto LABEL_27;
  }
  v9 = RtlUShortAdd((unsigned __int16)v21, 4, &v21);
  v8 = v9;
  if ( v9 < 0 )
  {
    v10 = "RtlUShortAdd failed [%x]";
    v11 = 2892;
    goto LABEL_26;
  }
  v12 = (unsigned __int16)v21;
  a1[1] = v21;
  *a1 = 0;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v12);
  *((_QWORD *)a1 + 1) = Heap;
  if ( !Heap )
  {
    v8 = -1073741801;
    goto LABEL_27;
  }
  v9 = RtlUnicodeStringCopy(a1, a2);
  v8 = v9;
  if ( v9 < 0 )
  {
    v10 = "RtlUnicodeStringCopy failed [%x]";
    v11 = 2907;
    goto LABEL_26;
  }
  if ( *(_WORD *)(*((_QWORD *)a1 + 1) + 2 * ((unsigned __int64)*a1 >> 1) - 2) != 92 )
  {
    v17 = 0;
    v21 = 0;
    v22 = 0;
    v8 = RtlUnicodeStringValidateDestWorker(a1, &v17, &v21, &v22);
    if ( v8 < 0
      || (v14 = v22,
          v18 = 0,
          v8 = RtlWideCharArrayCopyStringWorker(
                 (int)v17 + 2 * (int)v22,
                 (int)v21 - (int)v22,
                 (unsigned int)&v18,
                 (unsigned int)L"\\",
                 0x7FFF),
          *a1 = 2 * (v18 + v14),
          v8 < 0) )
    {
      ShareAccess[0] = v8;
      AslLogCallPrintf(
        1,
        "AslpPathWildcardAllocMatchNode",
        2923,
        "RtlUnicodeStringCatString failed [%x]",
        *(_QWORD *)ShareAccess);
      goto LABEL_27;
    }
  }
  if ( a5 )
  {
    if ( a6 )
    {
      v9 = RtlUnicodeStringCbCatStringN(a1, a5, a6);
      v8 = v9;
      if ( v9 < 0 )
      {
        v10 = "RtlUnicodeStringCbCatStringN failed [%x]";
        v11 = 2931;
        goto LABEL_26;
      }
    }
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)a1;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v9 = ZwOpenFile((PHANDLE)a1 + 3, 0x100001u, &ObjectAttributes, &IoStatusBlock, 1u, 0x21u);
  v8 = v9;
  if ( v9 < 0 )
  {
    v10 = "Failed to open dir [%x]";
    v11 = 2945;
    goto LABEL_26;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14003f624  mov     [rsp-18h+arg_8], rbx
0x14003f629  mov     [rsp-18h+arg_18], rsi
0x14003f62e  push    rbp
0x14003f62f  push    rdi
0x14003f630  push    r15
0x14003f632  mov     rbp, rsp
0x14003f635  sub     rsp, 80h
0x14003f63c  xorps   xmm0, xmm0
0x14003f63f  xor     eax, eax
0x14003f641  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14003f645  xor     r15d, r15d
0x14003f648  mov     rbx, rdx
0x14003f64b  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x14003f64f  mov     rsi, rcx
0x14003f652  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14003f656  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x14003f65a  mov     [rcx], r15
0x14003f65d  mov     [rcx+8], r15
0x14003f661  mov     [rcx+18h], r15
0x14003f665  jmp     short loc_14003F66B
0x14003f667  add     r8, 2
0x14003f66b  mov     [rcx+10h], r8
0x14003f66f  cmp     [r8], r15w
0x14003f673  jnz     short loc_14003F667
0x14003f675  lea     rax, [r8+2]
0x14003f679  mov     [rcx+10h], rax
0x14003f67d  cmp     [rax], r15w
0x14003f681  jnz     short loc_14003F699
0x14003f683  neg     r9d
0x14003f686  sbb     edi, edi
0x14003f688  and     edi, 0FFFFFE47h
0x14003f68e  add     edi, 0C0000273h
0x14003f694  jmp     loc_14003F888
0x14003f699  test    r9d, r9d
0x14003f69c  jnz     short loc_14003F6A8
0x14003f69e  mov     edi, 0C0000103h
0x14003f6a3  jmp     loc_14003F888
0x14003f6a8  movzx   ecx, word ptr [rdx]
0x14003f6ab  lea     r8, [rbp+arg_0]
0x14003f6af  movzx   edx, [rbp+arg_28]
0x14003f6b3  mov     word ptr [rbp+arg_0], cx
0x14003f6b7  call    RtlUShortAdd
0x14003f6bc  mov     edi, eax
0x14003f6be  test    eax, eax
0x14003f6c0  jns     short loc_14003F6D4
0x14003f6c2  lea     r9, aRtlushortaddFa; "RtlUShortAdd failed [%x]"
0x14003f6c9  mov     r8d, 0B46h
0x14003f6cf  jmp     loc_14003F873
0x14003f6d4  movzx   ecx, word ptr [rbp+arg_0]
0x14003f6d8  lea     r8, [rbp+arg_0]
0x14003f6dc  mov     edx, 4
0x14003f6e1  call    RtlUShortAdd
0x14003f6e6  mov     edi, eax
0x14003f6e8  test    eax, eax
0x14003f6ea  jns     short loc_14003F6FE
0x14003f6ec  lea     r9, aRtlushortaddFa; "RtlUShortAdd failed [%x]"
0x14003f6f3  mov     r8d, 0B4Ch
0x14003f6f9  jmp     loc_14003F873
0x14003f6fe  movzx   ecx, word ptr [rbp+arg_0]
0x14003f702  mov     edx, 8; Flags
0x14003f707  mov     [rsi+2], cx
0x14003f70b  mov     r8d, ecx; Size
0x14003f70e  mov     [rsi], r15w
0x14003f712  mov     rcx, gs:60h
0x14003f71b  mov     rcx, [rcx+30h]; HeapHandle
0x14003f71f  call    cs:__imp_RtlAllocateHeap
0x14003f725  mov     [rsi+8], rax
0x14003f729  test    rax, rax
0x14003f72c  jnz     short loc_14003F738
0x14003f72e  mov     edi, 0C0000017h
0x14003f733  jmp     loc_14003F888
0x14003f738  mov     rdx, rbx
0x14003f73b  mov     rcx, rsi
0x14003f73e  call    RtlUnicodeStringCopy
0x14003f743  mov     edi, eax
0x14003f745  test    eax, eax
0x14003f747  jns     short loc_14003F75B
0x14003f749  lea     r9, aRtlunicodestri_1; "RtlUnicodeStringCopy failed [%x]"
0x14003f750  mov     r8d, 0B5Bh
0x14003f756  jmp     loc_14003F873
0x14003f75b  movzx   ecx, word ptr [rsi]
0x14003f75e  mov     rax, [rsi+8]
0x14003f762  shr     rcx, 1
0x14003f765  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x14003f76b  jz      short loc_14003F7E9
0x14003f76d  lea     r9, [rbp+arg_10]
0x14003f771  mov     [rbp+var_50], r15
0x14003f775  lea     r8, [rbp+arg_0]
0x14003f779  mov     [rbp+arg_0], r15
0x14003f77d  lea     rdx, [rbp+var_50]
0x14003f781  mov     [rbp+arg_10], r15
0x14003f785  mov     rcx, rsi
0x14003f788  call    RtlUnicodeStringValidateDestWorker
0x14003f78d  mov     edi, eax
0x14003f78f  test    eax, eax
0x14003f791  js      short loc_14003F7D3
0x14003f793  mov     rbx, [rbp+arg_10]
0x14003f797  lea     r9, asc_140049D20; "\\"
0x14003f79e  mov     rax, [rbp+var_50]
0x14003f7a2  lea     r8, [rbp+var_48]
0x14003f7a6  mov     rdx, [rbp+arg_0]
0x14003f7aa  sub     rdx, rbx
0x14003f7ad  mov     [rbp+var_48], r15
0x14003f7b1  mov     qword ptr [rsp+80h+ShareAccess], 7FFFh
0x14003f7ba  lea     rcx, [rax+rbx*2]
0x14003f7be  call    RtlWideCharArrayCopyStringWorker
0x14003f7c3  add     bx, word ptr [rbp+var_48]
0x14003f7c7  mov     edi, eax
0x14003f7c9  add     bx, bx
0x14003f7cc  mov     [rsi], bx
0x14003f7cf  test    eax, eax
0x14003f7d1  jns     short loc_14003F7E9
0x14003f7d3  mov     [rsp+80h+ShareAccess], edi
0x14003f7d7  lea     r9, aRtlunicodestri_0; "RtlUnicodeStringCatString failed [%x]"
0x14003f7de  mov     r8d, 0B6Bh
0x14003f7e4  jmp     loc_14003F877
0x14003f7e9  mov     rdx, [rbp+arg_20]
0x14003f7ed  test    rdx, rdx
0x14003f7f0  jz      short loc_14003F81B
0x14003f7f2  cmp     [rbp+arg_28], r15w
0x14003f7f7  jbe     short loc_14003F81B
0x14003f7f9  movzx   r8d, [rbp+arg_28]
0x14003f7fe  mov     rcx, rsi
0x14003f801  call    RtlUnicodeStringCbCatStringN
0x14003f806  mov     edi, eax
0x14003f808  test    eax, eax
0x14003f80a  jns     short loc_14003F81B
0x14003f80c  lea     r9, aRtlunicodestri; "RtlUnicodeStringCbCatStringN failed [%x"...
0x14003f813  mov     r8d, 0B73h
0x14003f819  jmp     short loc_14003F873
0x14003f81b  xorps   xmm0, xmm0
0x14003f81e  mov     [rsp+80h+OpenOptions], 21h ; '!'; OpenOptions
0x14003f826  lea     rcx, [rsi+18h]; FileHandle
0x14003f82a  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14003f831  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x14003f835  mov     [rbp+ObjectAttributes.RootDirectory], r15
0x14003f839  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14003f83d  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x14003f844  mov     edx, 100001h; DesiredAccess
0x14003f849  mov     [rbp+ObjectAttributes.ObjectName], rsi
0x14003f84d  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14003f852  mov     [rsp+80h+ShareAccess], 1; ShareAccess
0x14003f85a  call    cs:__imp_ZwOpenFile
0x14003f860  mov     edi, eax
0x14003f862  test    eax, eax
0x14003f864  jns     short loc_14003F890
0x14003f866  lea     r9, aFailedToOpenDi; "Failed to open dir [%x]"
0x14003f86d  mov     r8d, 0B81h
0x14003f873  mov     [rsp+80h+ShareAccess], eax
0x14003f877  lea     rdx, aAslppathwildca_7; "AslpPathWildcardAllocMatchNode"
0x14003f87e  mov     ecx, 1
0x14003f883  call    AslLogCallPrintf
0x14003f888  mov     rcx, rsi
0x14003f88b  call    AslpPathWildcardFreeMatchNode
0x14003f890  lea     r11, [rsp+80h+var_s0]
0x14003f898  mov     eax, edi
0x14003f89a  mov     rbx, [r11+28h]
0x14003f89e  mov     rsi, [r11+38h]
0x14003f8a2  mov     rsp, r11
0x14003f8a5  pop     r15
0x14003f8a7  pop     rdi
0x14003f8a8  pop     rbp
0x14003f8a9  retn
```
