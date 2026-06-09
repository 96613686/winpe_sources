# CmRegUtilUcValueSetUcString

- ea: `0x140018880`
- end: `0x1400189b3`
- name: `CmRegUtilUcValueSetUcString`
- size: `307`
- prototype: `__int64 __fastcall(HANDLE KeyHandle, PUNICODE_STRING ValueName)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1400181c4`
- `0x140018a64`

## callees

- `0x14000a780`
- `0x14000aa80`
- `0x140018880`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x140018990`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140018990`
- `ntoskrnl!ZwSetValueKey` at `0x1400188de`
- `ntoskrnl!ZwSetValueKey` at `0x14001897d`
- `ntoskrnl!ZwSetValueKey` at `0x1400188de`
- `ntoskrnl!ZwSetValueKey` at `0x14001897d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14001890c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14001890c`

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
0x140018880  push    rbx
0x140018882  push    rbp
0x140018883  push    rsi
0x140018884  push    rdi
0x140018885  push    r14
0x140018887  push    r15
0x140018889  sub     rsp, 48h
0x14001888d  movzx   r9d, word ptr [r8]
0x140018891  mov     r15d, 2
0x140018897  movzx   eax, word ptr [r8+2]
0x14001889c  xorps   xmm0, xmm0
0x14001889f  sub     rax, r9
0x1400188a2  mov     rbx, r8
0x1400188a5  mov     rbp, rdx
0x1400188a8  mov     r14, rcx
0x1400188ab  movups  xmmword ptr [rsp+78h+var_48.Length], xmm0
0x1400188b0  cmp     rax, r15
0x1400188b3  jb      short loc_1400188F1
0x1400188b5  mov     rax, [r8+8]
0x1400188b9  xor     edi, edi
0x1400188bb  shr     r9, 1
0x1400188be  mov     [rax+r9*2], di
0x1400188c3  lea     r9d, [r15-1]; Type
0x1400188c7  movzx   eax, word ptr [r8]
0x1400188cb  add     eax, r15d
0x1400188ce  mov     [rsp+78h+DataSize], eax; DataSize
0x1400188d2  mov     rax, [r8+8]
0x1400188d6  xor     r8d, r8d; TitleIndex
0x1400188d9  mov     [rsp+78h+Data], rax; Data
0x1400188de  call    cs:__imp_ZwSetValueKey
0x1400188e5  nop     dword ptr [rax+rax+00h]
0x1400188ea  mov     ebx, eax
0x1400188ec  jmp     loc_1400189A3
0x1400188f1  lea     rsi, [r9+2]
0x1400188f5  mov     r8d, 63557050h; Tag
0x1400188fb  lea     eax, [r15+r9]
0x1400188ff  mov     rdx, rsi; NumberOfBytes
0x140018902  mov     ecx, 1; PoolType
0x140018907  mov     [rsp+78h+var_48.MaximumLength], ax
0x14001890c  call    cs:__imp_ExAllocatePoolWithTag
0x140018913  nop     dword ptr [rax+rax+00h]
0x140018918  xor     edi, edi
0x14001891a  mov     [rsp+78h+var_48.Buffer], rax
0x14001891f  test    rax, rax
0x140018922  jz      short loc_14001899E
0x140018924  mov     r8, rsi; Size
0x140018927  xor     edx, edx; Val
0x140018929  mov     rcx, rax; void *
0x14001892c  call    memset
0x140018931  movzx   r8d, word ptr [rbx]; Size
0x140018935  mov     rdx, [rbx+8]; Src
0x140018939  mov     rcx, [rsp+78h+var_48.Buffer]; void *
0x14001893e  mov     [rsp+78h+var_48.Length], r8w
0x140018944  call    memmove
0x140018949  mov     rax, [rsp+78h+var_48.Buffer]
0x14001894e  lea     r9d, [rdi+1]; Type
0x140018952  movzx   ecx, [rsp+78h+var_48.Length]
0x140018957  xor     r8d, r8d; TitleIndex
0x14001895a  shr     rcx, 1
0x14001895d  mov     rdx, rbp; ValueName
0x140018960  mov     [rax+rcx*2], di
0x140018964  mov     rcx, r14; KeyHandle
0x140018967  movzx   eax, [rsp+78h+var_48.Length]
0x14001896c  add     eax, r15d
0x14001896f  mov     [rsp+78h+DataSize], eax; DataSize
0x140018973  mov     rax, [rsp+78h+var_48.Buffer]
0x140018978  mov     [rsp+78h+Data], rax; Data
0x14001897d  call    cs:__imp_ZwSetValueKey
0x140018984  nop     dword ptr [rax+rax+00h]
0x140018989  lea     rcx, [rsp+78h+var_48]; UnicodeString
0x14001898e  mov     ebx, eax
0x140018990  call    cs:__imp_RtlFreeUnicodeString
0x140018997  nop     dword ptr [rax+rax+00h]
0x14001899c  jmp     short loc_1400189A3
0x14001899e  mov     ebx, 0C000009Ah
0x1400189a3  mov     eax, ebx
0x1400189a5  add     rsp, 48h
0x1400189a9  pop     r15
0x1400189ab  pop     r14
0x1400189ad  pop     rdi
0x1400189ae  pop     rsi
0x1400189af  pop     rbp
0x1400189b0  pop     rbx
0x1400189b1  retn
```
