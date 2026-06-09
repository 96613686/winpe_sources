# BampUserSettingsReadEntry

- ea: `0x140011a98`
- end: `0x140011b3d`
- name: `BampUserSettingsReadEntry`
- size: `165`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1400119a0`
- `0x140012c84`
- `0x140015608`

## callees

- `0x1400026d0`
- `0x140011a98`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x140011ad5`
- `ntoskrnl!ZwQueryValueKey` at `0x140011ad5`

## pseudocode

```c
NTSTATUS __fastcall BampUserSettingsReadEntry(void *a1, struct _UNICODE_STRING *a2, __int64 a3)
{
  NTSTATUS result; // eax
  int v5; // edx
  int v6; // ecx
  ULONG ResultLength; // [rsp+30h] [rbp-48h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+38h] [rbp-40h] BYREF
  int v9; // [rsp+3Ch] [rbp-3Ch]
  int v10; // [rsp+40h] [rbp-38h]
  __int64 v11; // [rsp+44h] [rbp-34h]
  _DWORD v12[3]; // [rsp+4Ch] [rbp-2Ch]
  __int64 v13; // [rsp+58h] [rbp-20h]

  ResultLength = 0;
  result = ZwQueryValueKey(a1, a2, KeyValuePartialInformation, KeyValueInformation, 0x28u, &ResultLength);
  if ( result >= 0 )
  {
    if ( v10 == 24 && v9 == 3 && (v5 = v12[0], v12[0] < 3) && (v6 = v13, (unsigned int)v13 < 4) )
    {
      *(_QWORD *)a3 = v11;
      *(_QWORD *)(a3 + 12) = *(_QWORD *)&v12[1];
      result = 0;
      *(_DWORD *)(a3 + 8) = v5;
      *(_DWORD *)(a3 + 20) = v6;
    }
    else
    {
      return -1073739509;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140011a98  push    rbx
0x140011a9a  sub     rsp, 70h
0x140011a9e  mov     rax, cs:__security_cookie
0x140011aa5  xor     rax, rsp
0x140011aa8  mov     [rsp+78h+var_18], rax
0x140011aad  lea     rax, [rsp+78h+var_48]
0x140011ab2  mov     [rsp+78h+var_48], 0
0x140011aba  mov     rbx, r8
0x140011abd  mov     [rsp+78h+ResultLength], rax; ResultLength
0x140011ac2  lea     r9, [rsp+78h+KeyValueInformation]; KeyValueInformation
0x140011ac7  mov     [rsp+78h+Length], 28h ; '('; Length
0x140011acf  mov     r8d, 2; KeyValueInformationClass
0x140011ad5  call    cs:__imp_ZwQueryValueKey
0x140011adc  nop     dword ptr [rax+rax+00h]
0x140011ae1  test    eax, eax
0x140011ae3  jns     short loc_140011AF9
0x140011ae5  mov     rcx, [rsp+78h+var_18]
0x140011aea  xor     rcx, rsp; StackCookie
0x140011aed  call    __security_check_cookie
0x140011af2  add     rsp, 70h
0x140011af6  pop     rbx
0x140011af7  retn
0x140011af9  cmp     [rsp+78h+var_38], 18h
0x140011afe  jnz     short loc_140011B36
0x140011b00  cmp     [rsp+78h+var_3C], 3
0x140011b05  jnz     short loc_140011B36
0x140011b07  mov     rdx, qword ptr [rsp+78h+var_2C]
0x140011b0c  cmp     edx, 3
0x140011b0f  jge     short loc_140011B36
0x140011b11  mov     rcx, [rsp+78h+var_20]
0x140011b16  cmp     ecx, 4
0x140011b19  jnb     short loc_140011B36
0x140011b1b  mov     rax, [rsp+78h+var_34]
0x140011b20  mov     [rbx], rax
0x140011b23  mov     rax, qword ptr [rsp+78h+var_2C+4]
0x140011b28  mov     [rbx+0Ch], rax
0x140011b2c  xor     eax, eax
0x140011b2e  mov     [rbx+8], edx
0x140011b31  mov     [rbx+14h], ecx
0x140011b34  jmp     short loc_140011AE5
0x140011b36  mov     eax, 0C000090Bh
0x140011b3b  jmp     short loc_140011AE5
```
