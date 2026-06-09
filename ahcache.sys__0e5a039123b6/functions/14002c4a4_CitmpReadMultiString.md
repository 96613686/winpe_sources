# CitmpReadMultiString

- ea: `0x14002c4a4`
- end: `0x14002c701`
- name: `CitmpReadMultiString`
- size: `605`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14002bb4c`

## callees

- `0x140007b40`
- `0x140007e40`
- `0x14002be24`
- `0x14002c4a4`
- `0x14003e364`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002c6c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002c6c7`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002c4e7`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002c4e7`
- `ntoskrnl!ZwClose` at `0x14002c6de`
- `ntoskrnl!ZwClose` at `0x14002c6de`
- `ntoskrnl!ZwQueryValueKey` at `0x14002c55d`
- `ntoskrnl!ZwQueryValueKey` at `0x14002c5f9`
- `ntoskrnl!ZwQueryValueKey` at `0x14002c55d`
- `ntoskrnl!ZwQueryValueKey` at `0x14002c5f9`
- `ntoskrnl!ExAllocatePool2` at `0x14002c5a1`
- `ntoskrnl!ExAllocatePool2` at `0x14002c666`
- `ntoskrnl!ExAllocatePool2` at `0x14002c5a1`
- `ntoskrnl!ExAllocatePool2` at `0x14002c666`

## string_xrefs

- `0x14002c4f6`: `\Registry\Machine\System\CurrentControlSet\Control\Session Manager\AppCompatCache`
- `0x14002c50c`: `Failed to open module key [%x]`
- `0x14002c519`: `CitmpReadMultiString`
- `0x14002c5c2`: `CitmpReadMultiString`
- `0x14002c61c`: `CitmpReadMultiString`
- `0x14002c687`: `CitmpReadMultiString`

## pseudocode

```c
__int64 __fastcall CitmpReadMultiString(_QWORD *a1, __int64 a2, __int64 a3)
{
  int v4; // eax
  unsigned int v5; // ebx
  const char *v6; // r9
  __int64 v7; // r8
  _DWORD *Pool2; // rdi
  NTSTATUS v9; // eax
  size_t v10; // r14
  void *v11; // rax
  void *v12; // rbx
  __int64 Length; // [rsp+20h] [rbp-20h]
  __int64 Lengtha; // [rsp+20h] [rbp-20h]
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-10h] BYREF
  HANDLE KeyHandle; // [rsp+68h] [rbp+28h] BYREF
  ULONG ResultLength; // [rsp+70h] [rbp+30h] BYREF
  int v19; // [rsp+74h] [rbp+34h]

  v19 = HIDWORD(a3);
  ResultLength = 0;
  KeyHandle = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"Citm");
  v4 = CitmpEnsureKey(
         &KeyHandle,
         L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Session Manager\\AppCompatCache",
         0);
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = "Failed to open module key [%x]";
    v7 = 817;
LABEL_3:
    LODWORD(Length) = v4;
    AslLogCallPrintf(1, "CitmpReadMultiString", v7, v6, Length);
    goto LABEL_19;
  }
  ResultLength = 0;
  v4 = ZwQueryValueKey(KeyHandle, &DestinationString, KeyValuePartialInformation, 0, 0, &ResultLength);
  v5 = v4;
  if ( v4 == -2147483643 || v4 == -1073741789 )
  {
    Pool2 = (_DWORD *)ExAllocatePool2(256, ResultLength, 1836345667);
    if ( Pool2 )
    {
      v9 = ZwQueryValueKey(
             KeyHandle,
             &DestinationString,
             KeyValuePartialInformation,
             Pool2,
             ResultLength,
             &ResultLength);
      v5 = v9;
      if ( v9 >= 0 )
      {
        if ( Pool2[1] == 7 )
        {
          v10 = (unsigned int)(Pool2[2] + 4);
          v11 = (void *)ExAllocatePool2(256, v10, 1836345667);
          v12 = v11;
          if ( v11 )
          {
            memset(v11, 0, v10);
            memmove(v12, Pool2 + 3, (unsigned int)Pool2[2]);
            *a1 = v12;
            v5 = 0;
          }
          else
          {
            v5 = -1073741801;
            AslLogCallPrintf(1, "CitmpReadMultiString", 873, "Out of memory");
          }
        }
        else
        {
          v5 = -1073741788;
          LODWORD(Lengtha) = -1073741788;
          AslLogCallPrintf(1, "CitmpReadMultiString", 861, "Invalid value type [%x]", Lengtha);
        }
      }
      else
      {
        LODWORD(Lengtha) = v9;
        AslLogCallPrintf(1, "CitmpReadMultiString", 854, "Failed to query key value [%x]", Lengtha);
      }
      ExFreePoolWithTag(Pool2, 0x6D746943u);
    }
    else
    {
      v5 = -1073741801;
      AslLogCallPrintf(1, "CitmpReadMultiString", 843, "Out of memory");
    }
    goto LABEL_19;
  }
  if ( v4 != -1073741772 )
  {
    v6 = "Failed to query key value [%x]";
    v7 = 830;
    goto LABEL_3;
  }
LABEL_19:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return v5;
}

```

## disassembly

```asm
0x14002c4a4  mov     rax, rsp
0x14002c4a7  mov     [rax+8], rbx
0x14002c4ab  mov     [rax+20h], rdi
0x14002c4af  mov     [rax+18h], r8
0x14002c4b3  mov     [rax+10h], rdx
0x14002c4b7  push    rbp
0x14002c4b8  push    r14
0x14002c4ba  push    r15
0x14002c4bc  mov     rbp, rsp
0x14002c4bf  sub     rsp, 40h
0x14002c4c3  mov     r15, rcx
0x14002c4c6  mov     [rbp+arg_10], 0
0x14002c4cd  xorps   xmm0, xmm0
0x14002c4d0  mov     [rbp+KeyHandle], 0
0x14002c4d8  lea     rcx, [rbp+DestinationString]; DestinationString
0x14002c4dc  lea     rdx, aCitm; "Citm"
0x14002c4e3  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14002c4e7  call    cs:__imp_RtlInitUnicodeString
0x14002c4ee  nop     dword ptr [rax+rax+00h]
0x14002c4f3  xor     r8d, r8d
0x14002c4f6  lea     rdx, aRegistryMachin_0; "\\Registry\\Machine\\System\\CurrentCon"...
0x14002c4fd  lea     rcx, [rbp+KeyHandle]
0x14002c501  call    CitmpEnsureKey
0x14002c506  mov     ebx, eax
0x14002c508  test    eax, eax
0x14002c50a  jns     short loc_14002C533
0x14002c50c  lea     r9, aFailedToOpenMo; "Failed to open module key [%x]"
0x14002c513  mov     r8d, 331h
0x14002c519  lea     rdx, aCitmpreadmulti; "CitmpReadMultiString"
0x14002c520  mov     dword ptr [rsp+40h+Length], eax
0x14002c524  mov     ecx, 1
0x14002c529  call    AslLogCallPrintf
0x14002c52e  jmp     loc_14002C6D3
0x14002c533  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x14002c537  lea     rax, [rbp+arg_10]
0x14002c53b  xor     r9d, r9d; KeyValueInformation
0x14002c53e  mov     [rsp+40h+ResultLength], rax; ResultLength
0x14002c543  lea     rdx, [rbp+DestinationString]; ValueName
0x14002c547  mov     [rbp+arg_10], 0
0x14002c54e  mov     dword ptr [rsp+40h+Length], 0; Length
0x14002c556  lea     r14d, [r9+2]
0x14002c55a  mov     r8d, r14d; KeyValueInformationClass
0x14002c55d  call    cs:__imp_ZwQueryValueKey
0x14002c564  nop     dword ptr [rax+rax+00h]
0x14002c569  mov     ebx, eax
0x14002c56b  cmp     eax, 80000005h
0x14002c570  jz      short loc_14002C593
0x14002c572  cmp     eax, 0C0000023h
0x14002c577  jz      short loc_14002C593
0x14002c579  cmp     eax, 0C0000034h
0x14002c57e  jz      loc_14002C6D3
0x14002c584  lea     r9, aFailedToQueryK_0; "Failed to query key value [%x]"
0x14002c58b  mov     r8d, 33Eh
0x14002c591  jmp     short loc_14002C519
0x14002c593  mov     edx, [rbp+arg_10]
0x14002c596  mov     ecx, 100h
0x14002c59b  mov     r8d, 6D746943h
0x14002c5a1  call    cs:__imp_ExAllocatePool2
0x14002c5a8  nop     dword ptr [rax+rax+00h]
0x14002c5ad  mov     rdi, rax
0x14002c5b0  test    rax, rax
0x14002c5b3  jnz     short loc_14002C5DB
0x14002c5b5  lea     r9, aOutOfMemory; "Out of memory"
0x14002c5bc  mov     r8d, 34Bh
0x14002c5c2  lea     rdx, aCitmpreadmulti; "CitmpReadMultiString"
0x14002c5c9  mov     ebx, 0C0000017h
0x14002c5ce  lea     ecx, [rax+1]
0x14002c5d1  call    AslLogCallPrintf
0x14002c5d6  jmp     loc_14002C6D3
0x14002c5db  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x14002c5df  lea     rax, [rbp+arg_10]
0x14002c5e3  mov     [rsp+40h+ResultLength], rax; ResultLength
0x14002c5e8  lea     rdx, [rbp+DestinationString]; ValueName
0x14002c5ec  mov     eax, [rbp+arg_10]
0x14002c5ef  mov     r9, rdi; KeyValueInformation
0x14002c5f2  mov     r8d, r14d; KeyValueInformationClass
0x14002c5f5  mov     dword ptr [rsp+40h+Length], eax; Length
0x14002c5f9  call    cs:__imp_ZwQueryValueKey
0x14002c600  nop     dword ptr [rax+rax+00h]
0x14002c605  mov     ebx, eax
0x14002c607  test    eax, eax
0x14002c609  jns     short loc_14002C632
0x14002c60b  mov     dword ptr [rsp+40h+Length], eax
0x14002c60f  lea     r9, aFailedToQueryK_0; "Failed to query key value [%x]"
0x14002c616  mov     r8d, 356h
0x14002c61c  lea     rdx, aCitmpreadmulti; "CitmpReadMultiString"
0x14002c623  mov     ecx, 1
0x14002c628  call    AslLogCallPrintf
0x14002c62d  jmp     loc_14002C6BF
0x14002c632  cmp     dword ptr [rdi+4], 7
0x14002c636  jz      short loc_14002C650
0x14002c638  mov     ebx, 0C0000024h
0x14002c63d  lea     r9, aInvalidValueTy_0; "Invalid value type [%x]"
0x14002c644  mov     dword ptr [rsp+40h+Length], ebx
0x14002c648  mov     r8d, 35Dh
0x14002c64e  jmp     short loc_14002C61C
0x14002c650  mov     eax, [rdi+8]
0x14002c653  mov     r8d, 6D746943h
0x14002c659  add     eax, 4
0x14002c65c  mov     ecx, 100h
0x14002c661  mov     edx, eax
0x14002c663  mov     r14d, eax
0x14002c666  call    cs:__imp_ExAllocatePool2
0x14002c66d  nop     dword ptr [rax+rax+00h]
0x14002c672  mov     rbx, rax
0x14002c675  test    rax, rax
0x14002c678  jnz     short loc_14002C69D
0x14002c67a  lea     r9, aOutOfMemory; "Out of memory"
0x14002c681  mov     r8d, 369h
0x14002c687  lea     rdx, aCitmpreadmulti; "CitmpReadMultiString"
0x14002c68e  mov     ebx, 0C0000017h
0x14002c693  lea     ecx, [rax+1]
0x14002c696  call    AslLogCallPrintf
0x14002c69b  jmp     short loc_14002C6BF
0x14002c69d  mov     r8, r14; Size
0x14002c6a0  xor     edx, edx; Val
0x14002c6a2  mov     rcx, rbx; void *
0x14002c6a5  call    memset
0x14002c6aa  mov     r8d, [rdi+8]; Size
0x14002c6ae  lea     rdx, [rdi+0Ch]; Src
0x14002c6b2  mov     rcx, rbx; void *
0x14002c6b5  call    memmove
0x14002c6ba  mov     [r15], rbx
0x14002c6bd  xor     ebx, ebx
0x14002c6bf  mov     edx, 6D746943h; Tag
0x14002c6c4  mov     rcx, rdi; P
0x14002c6c7  call    cs:__imp_ExFreePoolWithTag
0x14002c6ce  nop     dword ptr [rax+rax+00h]
0x14002c6d3  cmp     [rbp+KeyHandle], 0
0x14002c6d8  jz      short loc_14002C6EA
0x14002c6da  mov     rcx, [rbp+KeyHandle]; Handle
0x14002c6de  call    cs:__imp_ZwClose
0x14002c6e5  nop     dword ptr [rax+rax+00h]
0x14002c6ea  mov     rdi, [rsp+40h+arg_18]
0x14002c6ef  mov     eax, ebx
0x14002c6f1  mov     rbx, [rsp+40h+arg_0]
0x14002c6f6  add     rsp, 40h
0x14002c6fa  pop     r15
0x14002c6fc  pop     r14
0x14002c6fe  pop     rbp
0x14002c6ff  retn
```
