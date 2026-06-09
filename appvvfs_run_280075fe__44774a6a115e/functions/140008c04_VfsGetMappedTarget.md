# VfsGetMappedTarget

- ea: `0x140008c04`
- end: `0x140008d47`
- name: `VfsGetMappedTarget`
- size: `323`
- prototype: `__int64 __usercall@<rax>(PVOID FltObject@<rcx>, __int64, __int64)`
- caller_count: `7`
- callee_count: `6`
- tags: ``

## callers

- `0x1400034a0`
- `0x140005b48`
- `0x140007124`
- `0x14000a22c`
- `0x14000aefc`
- `0x14000b4ec`
- `0x14000be3c`

## callees

- `0x140008aa8`
- `0x140008c04`
- `0x140008d50`
- `0x140008e7c`
- `0x140011520`
- `0x140012acc`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x140008ca6`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140008ca6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008d34`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008d34`
- `FLTMGR!FltObjectReference` at `0x140008cbe`
- `FLTMGR!FltObjectReference` at `0x140008cbe`

## pseudocode

```c
NTSTATUS __fastcall VfsGetMappedTarget(
        PVOID FltObject,
        const UNICODE_STRING *a2,
        char a3,
        __int64 a4,
        __int64 a5,
        _QWORD *a6)
{
  __int64 v8; // rcx
  NTSTATUS result; // eax
  void *v10; // r14
  NTSTATUS InstanceFromVolumeName; // eax
  int v12; // ebx
  PVOID v13; // r9
  const WCHAR *v14; // r8
  PVOID v15; // [rsp+38h] [rbp-50h]
  PVOID P[2]; // [rsp+40h] [rbp-48h] BYREF
  _OWORD v17[3]; // [rsp+50h] [rbp-38h] BYREF

  v15 = 0;
  *(_OWORD *)P = 0;
  *(_QWORD *)(a5 + 8) = 0;
  *(_DWORD *)a5 = 0;
  v8 = a4;
  if ( !a3 )
  {
    v17[0] = 0;
    result = VfsGetRelativeNameByMapping(a4, a2, 0, v17);
    if ( result < 0 )
      goto LABEL_5;
    a2 = (const UNICODE_STRING *)v17;
    v8 = a4;
  }
  result = VfsGenerateMappedName(v8, a2, (struct _UNICODE_STRING *)P);
LABEL_5:
  if ( result < 0 )
    return result;
  if ( !a6 )
  {
    *(_OWORD *)a5 = *(_OWORD *)P;
    return 0;
  }
  v10 = (void *)(a4 + 24);
  if ( RtlEqualUnicodeString((PCUNICODE_STRING)(a4 + 8), (PCUNICODE_STRING)(a4 + 24), 1u) )
  {
    v15 = FltObject;
    InstanceFromVolumeName = FltObjectReference(FltObject);
    v12 = InstanceFromVolumeName;
    if ( InstanceFromVolumeName < 0 )
    {
      v13 = FltObject;
      v14 = L"VfsGetMappedTarget() - Failed to reference instance: %p\n Status: 0x%08X";
LABEL_14:
      LogWrite(1, 0, v14, v13, InstanceFromVolumeName);
    }
  }
  else
  {
    InstanceFromVolumeName = VfsGetInstanceFromVolumeName((PCUNICODE_STRING)(a4 + 24));
    v12 = InstanceFromVolumeName;
    if ( InstanceFromVolumeName < 0 )
    {
      v13 = v10;
      v14 = L"VfsGetMappedTarget() - Failed to get instance for volume: %wZ\n Status: 0x%08X";
      goto LABEL_14;
    }
  }
  if ( v12 < 0 )
  {
    if ( P[1] )
      ExFreePoolWithTag(P[1], 0);
  }
  else
  {
    *(_OWORD *)a5 = *(_OWORD *)P;
    *a6 = v15;
  }
  return v12;
}

```

## disassembly

```asm
0x140008c04  push    rbx
0x140008c06  push    rsi
0x140008c07  push    rdi
0x140008c08  push    r14
0x140008c0a  push    r15
0x140008c0c  sub     rsp, 60h
0x140008c10  mov     rbx, r9
0x140008c13  mov     r15, rcx
0x140008c16  mov     [rsp+88h+var_50], 0
0x140008c1f  xorps   xmm0, xmm0
0x140008c22  movups  xmmword ptr [rsp+88h+P], xmm0
0x140008c27  mov     rsi, [rsp+88h+arg_20]
0x140008c2f  mov     qword ptr [rsi+8], 0
0x140008c37  xor     eax, eax
0x140008c39  mov     [rsi], eax
0x140008c3b  mov     rcx, rbx
0x140008c3e  test    r8b, r8b
0x140008c41  jnz     short loc_140008C61
0x140008c43  movups  [rsp+88h+var_38], xmm0
0x140008c48  lea     r9, [rsp+88h+var_38]
0x140008c4d  xor     r8d, r8d
0x140008c50  call    VfsGetRelativeNameByMapping
0x140008c55  test    eax, eax
0x140008c57  js      short loc_140008C6B
0x140008c59  lea     rdx, [rsp+88h+var_38]
0x140008c5e  mov     rcx, rbx
0x140008c61  lea     r8, [rsp+88h+P]
0x140008c66  call    VfsGenerateMappedName
0x140008c6b  mov     [rsp+88h+var_58], eax
0x140008c6f  test    eax, eax
0x140008c71  js      short loc_140008C8B
0x140008c73  mov     rdi, [rsp+88h+arg_28]
0x140008c7b  test    rdi, rdi
0x140008c7e  jnz     short loc_140008C98
0x140008c80  movups  xmm0, xmmword ptr [rsp+88h+P]
0x140008c85  movdqu  xmmword ptr [rsi], xmm0
0x140008c89  xor     eax, eax
0x140008c8b  add     rsp, 60h
0x140008c8f  pop     r15
0x140008c91  pop     r14
0x140008c93  pop     rdi
0x140008c94  pop     rsi
0x140008c95  pop     rbx
0x140008c96  retn
0x140008c98  lea     r14, [rbx+18h]
0x140008c9c  lea     rcx, [rbx+8]; String1
0x140008ca0  mov     r8b, 1; CaseInSensitive
0x140008ca3  mov     rdx, r14; String2
0x140008ca6  call    cs:__imp_RtlEqualUnicodeString
0x140008cad  nop     dword ptr [rax+rax+00h]
0x140008cb2  test    al, al
0x140008cb4  jz      short loc_140008CE0
0x140008cb6  mov     [rsp+88h+var_50], r15
0x140008cbb  mov     rcx, r15; FltObject
0x140008cbe  call    cs:__imp_FltObjectReference
0x140008cc5  nop     dword ptr [rax+rax+00h]
0x140008cca  mov     ebx, eax
0x140008ccc  mov     [rsp+88h+var_58], eax
0x140008cd0  test    eax, eax
0x140008cd2  jns     short loc_140008D0F
0x140008cd4  mov     r9, r15
0x140008cd7  lea     r8, aVfsgetmappedta_0; "VfsGetMappedTarget() - Failed to refere"...
0x140008cde  jmp     short loc_140008D01
0x140008ce0  lea     rdx, [rsp+88h+var_50]
0x140008ce5  mov     rcx, r14; String2
0x140008ce8  call    VfsGetInstanceFromVolumeName
0x140008ced  mov     ebx, eax
0x140008cef  mov     [rsp+88h+var_58], eax
0x140008cf3  test    eax, eax
0x140008cf5  jns     short loc_140008D0F
0x140008cf7  mov     r9, r14
0x140008cfa  lea     r8, aVfsgetmappedta; "VfsGetMappedTarget() - Failed to get in"...
0x140008d01  mov     [rsp+88h+var_68], eax
0x140008d05  xor     edx, edx
0x140008d07  lea     ecx, [rdx+1]
0x140008d0a  call    LogWrite
0x140008d0f  test    ebx, ebx
0x140008d11  js      short loc_140008D24
0x140008d13  movups  xmm0, xmmword ptr [rsp+88h+P]
0x140008d18  movdqu  xmmword ptr [rsi], xmm0
0x140008d1c  mov     rax, [rsp+88h+var_50]
0x140008d21  mov     [rdi], rax
0x140008d24  test    ebx, ebx
0x140008d26  jns     short loc_140008D40
0x140008d28  mov     rcx, [rsp+88h+P+8]; P
0x140008d2d  test    rcx, rcx
0x140008d30  jz      short loc_140008D40
0x140008d32  xor     edx, edx; Tag
0x140008d34  call    cs:__imp_ExFreePoolWithTag
0x140008d3b  nop     dword ptr [rax+rax+00h]
0x140008d40  mov     eax, ebx
0x140008d42  jmp     loc_140008C8B
0x140014d80  push    rbp
0x140014d82  sub     rsp, 30h
0x140014d86  mov     rbp, rdx
0x140014d89  cmp     dword ptr [rbp+30h], 0
0x140014d8d  jge     short loc_140014DA7
0x140014d8f  mov     rcx, [rbp+48h]; P
0x140014d93  test    rcx, rcx
0x140014d96  jz      short loc_140014DA7
0x140014d98  xor     edx, edx; Tag
0x140014d9a  call    cs:__imp_ExFreePoolWithTag
0x140014da1  nop     dword ptr [rax+rax+00h]
0x140014da6  nop
0x140014da7  add     rsp, 30h
0x140014dab  pop     rbp
0x140014dac  retn
```
