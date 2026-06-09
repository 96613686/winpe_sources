# CmRegUtilUcValueSetUcString

- ea: `0x14000e918`
- end: `0x14000ea4b`
- name: `CmRegUtilUcValueSetUcString`
- size: `307`
- prototype: `__int64 __fastcall(HANDLE KeyHandle, PUNICODE_STRING ValueName)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000e224`
- `0x14000eafc`

## callees

- `0x1400027c0`
- `0x140002ac0`
- `0x14000e918`

## import_xrefs

- `ntoskrnl!ZwSetValueKey` at `0x14000e976`
- `ntoskrnl!ZwSetValueKey` at `0x14000ea15`
- `ntoskrnl!ZwSetValueKey` at `0x14000e976`
- `ntoskrnl!ZwSetValueKey` at `0x14000ea15`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000e9a4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000e9a4`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000ea28`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000ea28`

## pseudocode

```c
__int64 __fastcall CmRegUtilUcValueSetUcString(HANDLE KeyHandle, PUNICODE_STRING ValueName, unsigned __int16 *a3)
{
  unsigned __int64 v3; // r9
  unsigned __int64 v4; // rax
  unsigned int v8; // ebx
  size_t v9; // rsi
  wchar_t *PoolWithTag; // rax
  const void *v11; // rdx
  struct _UNICODE_STRING Data; // [rsp+30h] [rbp-48h] BYREF

  v3 = *a3;
  v4 = a3[1] - v3;
  Data = 0;
  if ( v4 < 2 )
  {
    v9 = v3 + 2;
    Data.MaximumLength = v3 + 2;
    PoolWithTag = (wchar_t *)ExAllocatePoolWithTag(PagedPool, v3 + 2, 0x63557050u);
    Data.Buffer = PoolWithTag;
    if ( PoolWithTag )
    {
      memset(PoolWithTag, 0, v9);
      v11 = (const void *)*((_QWORD *)a3 + 1);
      Data.Length = *a3;
      memmove(Data.Buffer, v11, Data.Length);
      Data.Buffer[(unsigned __int64)Data.Length >> 1] = 0;
      v8 = ZwSetValueKey(KeyHandle, ValueName, 0, 1u, Data.Buffer, Data.Length + 2);
      RtlFreeUnicodeString(&Data);
    }
    else
    {
      return (unsigned int)-1073741670;
    }
  }
  else
  {
    *(_WORD *)(*((_QWORD *)a3 + 1) + 2 * (v3 >> 1)) = 0;
    return (unsigned int)ZwSetValueKey(KeyHandle, ValueName, 0, 1u, *((PVOID *)a3 + 1), *a3 + 2);
  }
  return v8;
}

```

## disassembly

```asm
0x14000e918  push    rbx
0x14000e91a  push    rbp
0x14000e91b  push    rsi
0x14000e91c  push    rdi
0x14000e91d  push    r14
0x14000e91f  push    r15
0x14000e921  sub     rsp, 48h
0x14000e925  movzx   r9d, word ptr [r8]
0x14000e929  mov     r15d, 2
0x14000e92f  movzx   eax, word ptr [r8+2]
0x14000e934  xorps   xmm0, xmm0
0x14000e937  sub     rax, r9
0x14000e93a  mov     rbx, r8
0x14000e93d  mov     rbp, rdx
0x14000e940  mov     r14, rcx
0x14000e943  movups  xmmword ptr [rsp+78h+var_48.Length], xmm0
0x14000e948  cmp     rax, r15
0x14000e94b  jb      short loc_14000E989
0x14000e94d  mov     rax, [r8+8]
0x14000e951  xor     edi, edi
0x14000e953  shr     r9, 1
0x14000e956  mov     [rax+r9*2], di
0x14000e95b  lea     r9d, [r15-1]; Type
0x14000e95f  movzx   eax, word ptr [r8]
0x14000e963  add     eax, r15d
0x14000e966  mov     [rsp+78h+DataSize], eax; DataSize
0x14000e96a  mov     rax, [r8+8]
0x14000e96e  xor     r8d, r8d; TitleIndex
0x14000e971  mov     [rsp+78h+Data], rax; Data
0x14000e976  call    cs:__imp_ZwSetValueKey
0x14000e97d  nop     dword ptr [rax+rax+00h]
0x14000e982  mov     ebx, eax
0x14000e984  jmp     loc_14000EA3B
0x14000e989  lea     rsi, [r9+2]
0x14000e98d  mov     r8d, 63557050h; Tag
0x14000e993  lea     eax, [r15+r9]
0x14000e997  mov     rdx, rsi; NumberOfBytes
0x14000e99a  mov     ecx, 1; PoolType
0x14000e99f  mov     [rsp+78h+var_48.MaximumLength], ax
0x14000e9a4  call    cs:__imp_ExAllocatePoolWithTag
0x14000e9ab  nop     dword ptr [rax+rax+00h]
0x14000e9b0  xor     edi, edi
0x14000e9b2  mov     [rsp+78h+var_48.Buffer], rax
0x14000e9b7  test    rax, rax
0x14000e9ba  jz      short loc_14000EA36
0x14000e9bc  mov     r8, rsi; Size
0x14000e9bf  xor     edx, edx; Val
0x14000e9c1  mov     rcx, rax; void *
0x14000e9c4  call    memset
0x14000e9c9  movzx   r8d, word ptr [rbx]; Size
0x14000e9cd  mov     rdx, [rbx+8]; Src
0x14000e9d1  mov     rcx, [rsp+78h+var_48.Buffer]; void *
0x14000e9d6  mov     [rsp+78h+var_48.Length], r8w
0x14000e9dc  call    memmove
0x14000e9e1  mov     rax, [rsp+78h+var_48.Buffer]
0x14000e9e6  lea     r9d, [rdi+1]; Type
0x14000e9ea  movzx   ecx, [rsp+78h+var_48.Length]
0x14000e9ef  xor     r8d, r8d; TitleIndex
0x14000e9f2  shr     rcx, 1
0x14000e9f5  mov     rdx, rbp; ValueName
0x14000e9f8  mov     [rax+rcx*2], di
0x14000e9fc  mov     rcx, r14; KeyHandle
0x14000e9ff  movzx   eax, [rsp+78h+var_48.Length]
0x14000ea04  add     eax, r15d
0x14000ea07  mov     [rsp+78h+DataSize], eax; DataSize
0x14000ea0b  mov     rax, [rsp+78h+var_48.Buffer]
0x14000ea10  mov     [rsp+78h+Data], rax; Data
0x14000ea15  call    cs:__imp_ZwSetValueKey
0x14000ea1c  nop     dword ptr [rax+rax+00h]
0x14000ea21  lea     rcx, [rsp+78h+var_48]; UnicodeString
0x14000ea26  mov     ebx, eax
0x14000ea28  call    cs:__imp_RtlFreeUnicodeString
0x14000ea2f  nop     dword ptr [rax+rax+00h]
0x14000ea34  jmp     short loc_14000EA3B
0x14000ea36  mov     ebx, 0C000009Ah
0x14000ea3b  mov     eax, ebx
0x14000ea3d  add     rsp, 48h
0x14000ea41  pop     r15
0x14000ea43  pop     r14
0x14000ea45  pop     rdi
0x14000ea46  pop     rsi
0x14000ea47  pop     rbp
0x14000ea48  pop     rbx
0x14000ea49  retn
```
