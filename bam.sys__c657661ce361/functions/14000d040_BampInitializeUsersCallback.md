# BampInitializeUsersCallback

- ea: `0x14000d040`
- end: `0x14000d18f`
- name: `BampInitializeUsersCallback`
- size: `335`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x140001430`
- `0x1400026d0`
- `0x14000d040`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x14000d092`
- `ntoskrnl!ZwQueryValueKey` at `0x14000d092`
- `ntoskrnl!ZwDeleteKey` at `0x14000d0cd`
- `ntoskrnl!ZwDeleteKey` at `0x14000d0cd`

## pseudocode

```c
NTSTATUS __fastcall BampInitializeUsersCallback(HANDLE KeyHandle, unsigned __int16 *a2)
{
  unsigned int v3; // esi
  NTSTATUS v5; // ebx
  char v6; // di
  NTSTATUS result; // eax
  char v8; // [rsp+30h] [rbp-79h] BYREF
  ULONG ResultLength; // [rsp+34h] [rbp-75h] BYREF
  NTSTATUS v10; // [rsp+38h] [rbp-71h] BYREF
  unsigned int v11; // [rsp+3Ch] [rbp-6Dh] BYREF
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+40h] [rbp-69h] BYREF
  _DWORD *v13; // [rsp+60h] [rbp-49h]
  __int64 v14; // [rsp+68h] [rbp-41h]
  __int64 v15; // [rsp+70h] [rbp-39h]
  _DWORD v16[2]; // [rsp+78h] [rbp-31h] BYREF
  char *v17; // [rsp+80h] [rbp-29h]
  __int64 v18; // [rsp+88h] [rbp-21h]
  NTSTATUS *v19; // [rsp+90h] [rbp-19h]
  __int64 v20; // [rsp+98h] [rbp-11h]
  unsigned int *v21; // [rsp+A0h] [rbp-9h]
  __int64 v22; // [rsp+A8h] [rbp-1h]
  char KeyValueInformation[4]; // [rsp+B0h] [rbp+7h] BYREF
  int v24; // [rsp+B4h] [rbp+Bh]
  int v25; // [rsp+B8h] [rbp+Fh]
  unsigned int v26; // [rsp+BCh] [rbp+13h]

  ResultLength = 0;
  v3 = 0;
  v5 = ZwQueryValueKey(
         KeyHandle,
         &BampUserSettingsVersionValueName,
         KeyValuePartialInformation,
         KeyValueInformation,
         0x14u,
         &ResultLength);
  if ( v5 >= 0 )
  {
    if ( v24 == 4 && v25 == 4 )
    {
      v3 = v26;
      v6 = 0;
      if ( v26 <= 1 )
        goto LABEL_8;
      v5 = -1073741637;
    }
    else
    {
      v5 = -1073739509;
    }
  }
  v6 = 1;
  ZwDeleteKey(KeyHandle);
LABEL_8:
  result = dword_140007010;
  if ( (unsigned int)dword_140007010 > 5 )
  {
    v14 = 2;
    v13 = v16;
    v15 = *((_QWORD *)a2 + 1);
    v16[0] = *a2;
    v17 = &v8;
    v19 = &v10;
    v21 = &v11;
    v16[1] = 0;
    v8 = v6;
    v18 = 1;
    v10 = v5;
    v20 = 4;
    v11 = v3;
    v22 = 4;
    return tlgWriteTransfer_EtwWriteTransfer(
             (__int64)&dword_140007010,
             (unsigned __int8 *)&dword_140005944,
             0,
             0,
             7u,
             &v12);
  }
  return result;
}

```

## disassembly

```asm
0x14000d040  push    rbp
0x14000d042  push    rbx
0x14000d043  push    rsi
0x14000d044  push    rdi
0x14000d045  push    r14
0x14000d047  push    r15
0x14000d049  lea     rbp, [rsp-2Fh]
0x14000d04e  sub     rsp, 0D8h
0x14000d055  mov     rax, cs:__security_cookie
0x14000d05c  xor     rax, rsp
0x14000d05f  mov     [rbp+57h+var_38], rax
0x14000d063  lea     rax, [rbp+57h+var_CC]
0x14000d067  mov     [rbp+57h+var_CC], 0
0x14000d06e  mov     r15, rdx
0x14000d071  mov     [rsp+100h+ResultLength], rax; ResultLength
0x14000d076  xor     esi, esi
0x14000d078  mov     [rsp+100h+Length], 14h; Length
0x14000d080  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x14000d084  mov     r14, rcx
0x14000d087  lea     rdx, BampUserSettingsVersionValueName; ValueName
0x14000d08e  lea     r8d, [rsi+2]; KeyValueInformationClass
0x14000d092  call    cs:__imp_ZwQueryValueKey
0x14000d099  nop     dword ptr [rax+rax+00h]
0x14000d09e  mov     ebx, eax
0x14000d0a0  test    eax, eax
0x14000d0a2  js      short loc_14000D0C7
0x14000d0a4  cmp     [rbp+57h+var_4C], 4
0x14000d0a8  jz      short loc_14000D0B1
0x14000d0aa  mov     ebx, 0C000090Bh
0x14000d0af  jmp     short loc_14000D0C7
0x14000d0b1  cmp     [rbp+57h+var_48], 4
0x14000d0b5  jnz     short loc_14000D0AA
0x14000d0b7  mov     esi, [rbp+57h+var_44]
0x14000d0ba  xor     dil, dil
0x14000d0bd  cmp     esi, 1
0x14000d0c0  jbe     short loc_14000D0D9
0x14000d0c2  mov     ebx, 0C00000BBh
0x14000d0c7  mov     dil, 1
0x14000d0ca  mov     rcx, r14; KeyHandle
0x14000d0cd  call    cs:__imp_ZwDeleteKey
0x14000d0d4  nop     dword ptr [rax+rax+00h]
0x14000d0d9  mov     eax, cs:dword_140007010
0x14000d0df  cmp     eax, 5
0x14000d0e2  jbe     loc_14000D172
0x14000d0e8  lea     rax, [rbp+57h+var_88]
0x14000d0ec  mov     [rbp+57h+var_98], 2
0x14000d0f4  mov     [rbp+57h+var_A0], rax
0x14000d0f8  lea     rdx, dword_140005944
0x14000d0ff  mov     rax, [r15+8]
0x14000d103  lea     rcx, dword_140007010
0x14000d10a  mov     [rbp+57h+var_90], rax
0x14000d10e  xor     r9d, r9d
0x14000d111  movzx   eax, word ptr [r15]
0x14000d115  xor     r8d, r8d
0x14000d118  mov     [rbp+57h+var_88], eax
0x14000d11b  lea     rax, [rbp+57h+var_D0]
0x14000d11f  mov     [rbp+57h+var_80], rax
0x14000d123  lea     rax, [rbp+57h+var_C8]
0x14000d127  mov     [rbp+57h+var_70], rax
0x14000d12b  lea     rax, [rbp+57h+var_C4]
0x14000d12f  mov     [rbp+57h+var_60], rax
0x14000d133  lea     rax, [rbp+57h+var_C0]
0x14000d137  mov     [rsp+100h+ResultLength], rax
0x14000d13c  mov     [rsp+100h+Length], 7
0x14000d144  mov     [rbp+57h+var_84], 0
0x14000d14b  mov     [rbp+57h+var_D0], dil
0x14000d14f  mov     [rbp+57h+var_78], 1
0x14000d157  mov     [rbp+57h+var_C8], ebx
0x14000d15a  mov     [rbp+57h+var_68], 4
0x14000d162  mov     [rbp+57h+var_C4], esi
0x14000d165  mov     [rbp+57h+var_58], 4
0x14000d16d  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000d172  mov     rcx, [rbp+57h+var_38]
0x14000d176  xor     rcx, rsp; StackCookie
0x14000d179  call    __security_check_cookie
0x14000d17e  add     rsp, 0D8h
0x14000d185  pop     r15
0x14000d187  pop     r14
0x14000d189  pop     rdi
0x14000d18a  pop     rsi
0x14000d18b  pop     rbx
0x14000d18c  pop     rbp
0x14000d18d  retn
```
