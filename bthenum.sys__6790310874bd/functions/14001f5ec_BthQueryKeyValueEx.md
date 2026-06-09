# BthQueryKeyValueEx

- ea: `0x14001f5ec`
- end: `0x14001f6db`
- name: `BthQueryKeyValueEx`
- size: `239`
- prototype: `__int64 __usercall@<rax>(HANDLE KeyHandle@<rcx>, PUNICODE_STRING ValueName@<rdx>, void *@<r8>, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140006e5c`
- `0x1400072a8`
- `0x140019058`
- `0x14001d960`

## callees

- `0x140007e40`
- `0x14001f5ec`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001f6ab`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f6ab`
- `ntoskrnl!ZwQueryValueKey` at `0x14001f666`
- `ntoskrnl!ZwQueryValueKey` at `0x14001f666`
- `ntoskrnl!ExAllocatePool2` at `0x14001f631`
- `ntoskrnl!ExAllocatePool2` at `0x14001f631`

## pseudocode

```c
__int64 __fastcall BthQueryKeyValueEx(
        HANDLE KeyHandle,
        PUNICODE_STRING ValueName,
        void *a3,
        unsigned int a4,
        _DWORD *a5)
{
  unsigned int v6; // eax
  unsigned int *Pool2; // rbx
  NTSTATUS v11; // edi
  unsigned int v12; // eax
  ULONG Length; // [rsp+68h] [rbp+20h] BYREF

  v6 = ValueName->MaximumLength + 24;
  if ( v6 + a4 < v6 )
  {
    return (unsigned int)-1073741675;
  }
  else
  {
    Length = v6 + a4;
    Pool2 = (unsigned int *)ExAllocatePool2(256, v6 + a4, 1818784834);
    if ( Pool2 )
    {
      v11 = ZwQueryValueKey(KeyHandle, ValueName, KeyValueFullInformation, Pool2, Length, &Length);
      if ( v11 >= 0 )
      {
        v12 = Pool2[3];
        if ( a4 < v12 )
          v11 = -1073741789;
        else
          memmove(a3, (char *)Pool2 + Pool2[2], v12);
      }
      if ( a5 )
        *a5 = Pool2[3];
      ExFreePoolWithTag(Pool2, 0);
    }
    else
    {
      return (unsigned int)-1073741670;
    }
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14001f5ec  mov     [rsp+arg_0], rbx
0x14001f5f1  mov     [rsp+arg_8], rbp
0x14001f5f6  push    rsi
0x14001f5f7  push    rdi
0x14001f5f8  push    r14
0x14001f5fa  sub     rsp, 30h
0x14001f5fe  movzx   eax, word ptr [rdx+2]
0x14001f602  mov     esi, r9d
0x14001f605  add     eax, 18h
0x14001f608  mov     rbp, r8
0x14001f60b  mov     rdi, rdx
0x14001f60e  mov     r14, rcx
0x14001f611  lea     r10d, [rax+r9]
0x14001f615  cmp     r10d, eax
0x14001f618  jb      loc_14001F6C0
0x14001f61e  mov     edx, r10d
0x14001f621  mov     ecx, 100h
0x14001f626  mov     r8d, 6C687442h
0x14001f62c  mov     [rsp+48h+arg_18], r10d
0x14001f631  call    cs:__imp_ExAllocatePool2
0x14001f638  nop     dword ptr [rax+rax+00h]
0x14001f63d  mov     rbx, rax
0x14001f640  test    rax, rax
0x14001f643  jz      short loc_14001F6B9
0x14001f645  mov     ecx, [rsp+48h+arg_18]
0x14001f649  lea     rax, [rsp+48h+arg_18]
0x14001f64e  mov     [rsp+48h+ResultLength], rax; ResultLength
0x14001f653  mov     r9, rbx; KeyValueInformation
0x14001f656  mov     [rsp+48h+Length], ecx; Length
0x14001f65a  mov     r8d, 1; KeyValueInformationClass
0x14001f660  mov     rcx, r14; KeyHandle
0x14001f663  mov     rdx, rdi; ValueName
0x14001f666  call    cs:__imp_ZwQueryValueKey
0x14001f66d  nop     dword ptr [rax+rax+00h]
0x14001f672  mov     edi, eax
0x14001f674  test    eax, eax
0x14001f676  js      short loc_14001F697
0x14001f678  mov     eax, [rbx+0Ch]
0x14001f67b  cmp     esi, eax
0x14001f67d  jb      short loc_14001F692
0x14001f67f  mov     edx, [rbx+8]
0x14001f682  mov     r8d, eax; Size
0x14001f685  add     rdx, rbx; Src
0x14001f688  mov     rcx, rbp; void *
0x14001f68b  call    memmove
0x14001f690  jmp     short loc_14001F697
0x14001f692  mov     edi, 0C0000023h
0x14001f697  mov     rcx, [rsp+48h+arg_20]
0x14001f69c  test    rcx, rcx
0x14001f69f  jz      short loc_14001F6A6
0x14001f6a1  mov     eax, [rbx+0Ch]
0x14001f6a4  mov     [rcx], eax
0x14001f6a6  xor     edx, edx; Tag
0x14001f6a8  mov     rcx, rbx; P
0x14001f6ab  call    cs:__imp_ExFreePoolWithTag
0x14001f6b2  nop     dword ptr [rax+rax+00h]
0x14001f6b7  jmp     short loc_14001F6C5
0x14001f6b9  mov     edi, 0C000009Ah
0x14001f6be  jmp     short loc_14001F6C5
0x14001f6c0  mov     edi, 0C0000095h
0x14001f6c5  mov     rbx, [rsp+48h+arg_0]
0x14001f6ca  mov     eax, edi
0x14001f6cc  mov     rbp, [rsp+48h+arg_8]
0x14001f6d1  add     rsp, 30h
0x14001f6d5  pop     r14
0x14001f6d7  pop     rdi
0x14001f6d8  pop     rsi
0x14001f6d9  retn
```
