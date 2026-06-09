# HCI_DeleteAllSubkeys(void *)

- ea: `0x1401be354`
- end: `0x1401be4a1`
- name: `?HCI_DeleteAllSubkeys@@YAJPEAX@Z`
- size: `333`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1401be4a8`
- `0x1401e8f5c`

## callees

- `0x1401be354`
- `0x14020934c`

## import_xrefs

- `ntoskrnl!ZwEnumerateKey` at `0x1401be389`
- `ntoskrnl!ZwEnumerateKey` at `0x1401be3e8`
- `ntoskrnl!ZwEnumerateKey` at `0x1401be389`
- `ntoskrnl!ZwEnumerateKey` at `0x1401be3e8`
- `ntoskrnl!ZwDeleteKey` at `0x1401be443`
- `ntoskrnl!ZwDeleteKey` at `0x1401be443`
- `ntoskrnl!ZwClose` at `0x1401be455`
- `ntoskrnl!ZwClose` at `0x1401be455`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401be46d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401be46d`
- `ntoskrnl!ExAllocatePool2` at `0x1401be3b5`
- `ntoskrnl!ExAllocatePool2` at `0x1401be3b5`

## pseudocode

```c
__int64 __fastcall HCI_DeleteAllSubkeys(HANDLE KeyHandle)
{
  NTSTATUS v2; // eax
  NTSTATUS v3; // ebx
  unsigned __int16 *Pool2; // rdi
  __int64 result; // rax
  struct _UNICODE_STRING v6; // [rsp+30h] [rbp-10h] BYREF
  ULONG ResultLength; // [rsp+68h] [rbp+28h] BYREF
  HANDLE KeyHandlea; // [rsp+70h] [rbp+30h] BYREF

  while ( 1 )
  {
    ResultLength = 0;
    v2 = ZwEnumerateKey(KeyHandle, 0, KeyBasicInformation, 0, 0, &ResultLength);
    v3 = v2;
    if ( v2 == -1073741789 )
      break;
    Pool2 = 0;
    if ( v2 == -2147483643 )
      break;
LABEL_5:
    if ( v3 < 0 )
    {
      if ( !Pool2 )
        goto LABEL_13;
      goto LABEL_10;
    }
    if ( Pool2 )
    {
      v6.Length = Pool2[6];
      v6.MaximumLength = v6.Length;
      KeyHandlea = 0;
      v6.Buffer = Pool2 + 8;
      *(_DWORD *)(&v6.MaximumLength + 1) = 0;
      v3 = BthOpenKeyEx(KeyHandle, &v6, &KeyHandlea, 0);
      if ( v3 >= 0 )
      {
        v3 = ZwDeleteKey(KeyHandlea);
        ZwClose(KeyHandlea);
      }
LABEL_10:
      ExFreePoolWithTag(Pool2, 0);
      if ( v3 < 0 )
        goto LABEL_13;
    }
  }
  Pool2 = (unsigned __int16 *)ExAllocatePool2(256, ResultLength, 1346917442);
  if ( Pool2 )
  {
    v3 = ZwEnumerateKey(KeyHandle, 0, KeyBasicInformation, Pool2, ResultLength, &ResultLength);
    goto LABEL_5;
  }
  v3 = -1073741670;
LABEL_13:
  result = 0;
  if ( v3 != -2147483622 )
    return (unsigned int)v3;
  return result;
}

```

## disassembly

```asm
0x1401be354  mov     [rsp-18h+arg_0], rbx
0x1401be359  push    rbp
0x1401be35a  push    rsi
0x1401be35b  push    rdi
0x1401be35c  mov     rbp, rsp
0x1401be35f  sub     rsp, 40h
0x1401be363  mov     rsi, rcx
0x1401be366  lea     rax, [rbp+arg_8]
0x1401be36a  mov     [rbp+arg_8], 0
0x1401be371  mov     [rsp+40h+ResultLength], rax; ResultLength
0x1401be376  xor     r9d, r9d; KeyInformation
0x1401be379  xor     r8d, r8d; KeyInformationClass
0x1401be37c  mov     [rsp+40h+Length], 0; Length
0x1401be384  xor     edx, edx; Index
0x1401be386  mov     rcx, rsi; KeyHandle
0x1401be389  call    cs:__imp_ZwEnumerateKey
0x1401be390  nop     dword ptr [rax+rax+00h]
0x1401be395  mov     ebx, eax
0x1401be397  cmp     eax, 0C0000023h
0x1401be39c  jz      short loc_1401BE3A7
0x1401be39e  xor     edi, edi
0x1401be3a0  cmp     eax, 80000005h
0x1401be3a5  jnz     short loc_1401BE3F6
0x1401be3a7  mov     edx, [rbp+arg_8]
0x1401be3aa  mov     ecx, 100h
0x1401be3af  mov     r8d, 50485442h
0x1401be3b5  call    cs:__imp_ExAllocatePool2
0x1401be3bc  nop     dword ptr [rax+rax+00h]
0x1401be3c1  mov     rdi, rax
0x1401be3c4  test    rax, rax
0x1401be3c7  jz      loc_1401BE483
0x1401be3cd  mov     ecx, [rbp+arg_8]
0x1401be3d0  lea     rax, [rbp+arg_8]
0x1401be3d4  mov     [rsp+40h+ResultLength], rax; ResultLength
0x1401be3d9  mov     r9, rdi; KeyInformation
0x1401be3dc  mov     [rsp+40h+Length], ecx; Length
0x1401be3e0  xor     r8d, r8d; KeyInformationClass
0x1401be3e3  mov     rcx, rsi; KeyHandle
0x1401be3e6  xor     edx, edx; Index
0x1401be3e8  call    cs:__imp_ZwEnumerateKey
0x1401be3ef  nop     dword ptr [rax+rax+00h]
0x1401be3f4  mov     ebx, eax
0x1401be3f6  test    ebx, ebx
0x1401be3f8  js      short loc_1401BE463
0x1401be3fa  test    rdi, rdi
0x1401be3fd  jz      loc_1401BE366
0x1401be403  movzx   eax, word ptr [rdi+0Ch]
0x1401be407  lea     r8, [rbp+KeyHandle]
0x1401be40b  mov     [rbp+var_10], ax
0x1401be40f  lea     rdx, [rbp+var_10]
0x1401be413  mov     [rbp+var_E], ax
0x1401be417  xor     r9d, r9d
0x1401be41a  lea     rax, [rdi+10h]
0x1401be41e  mov     [rbp+KeyHandle], 0
0x1401be426  mov     rcx, rsi
0x1401be429  mov     [rbp+var_8], rax
0x1401be42d  mov     [rbp+var_C], 0
0x1401be434  call    BthOpenKeyEx
0x1401be439  mov     ebx, eax
0x1401be43b  test    eax, eax
0x1401be43d  js      short loc_1401BE468
0x1401be43f  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1401be443  call    cs:__imp_ZwDeleteKey
0x1401be44a  nop     dword ptr [rax+rax+00h]
0x1401be44f  mov     rcx, [rbp+KeyHandle]; Handle
0x1401be453  mov     ebx, eax
0x1401be455  call    cs:__imp_ZwClose
0x1401be45c  nop     dword ptr [rax+rax+00h]
0x1401be461  jmp     short loc_1401BE468
0x1401be463  test    rdi, rdi
0x1401be466  jz      short loc_1401BE488
0x1401be468  xor     edx, edx; Tag
0x1401be46a  mov     rcx, rdi; P
0x1401be46d  call    cs:__imp_ExFreePoolWithTag
0x1401be474  nop     dword ptr [rax+rax+00h]
0x1401be479  test    ebx, ebx
0x1401be47b  jns     loc_1401BE366
0x1401be481  jmp     short loc_1401BE488
0x1401be483  mov     ebx, 0C000009Ah
0x1401be488  xor     eax, eax
0x1401be48a  cmp     ebx, 8000001Ah
0x1401be490  cmovnz  eax, ebx
0x1401be493  mov     rbx, [rsp+40h+arg_0]
0x1401be498  add     rsp, 40h
0x1401be49c  pop     rdi
0x1401be49d  pop     rsi
0x1401be49e  pop     rbp
0x1401be49f  retn
```
