# FveRegistryGetValue

- ea: `0x18005db90`
- end: `0x18005dd0f`
- name: `FveRegistryGetValue`
- size: `383`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005d920`
- `0x18005da60`

## callees

- `0x180023af0`
- `0x180034d10`
- `0x18005c864`
- `0x18005db90`

## import_xrefs

- `ntdll!NtClose` at `0x18005dce7`
- `ntdll!NtClose` at `0x18005dce7`
- `ntdll!NtQueryValueKey` at `0x18005dc21`
- `ntdll!NtQueryValueKey` at `0x18005dc7e`
- `ntdll!NtQueryValueKey` at `0x18005dc21`
- `ntdll!NtQueryValueKey` at `0x18005dc7e`
- `ntdll!NtOpenKey` at `0x18005dbec`
- `ntdll!NtOpenKey` at `0x18005dbec`

## pseudocode

```c
__int64 __fastcall FveRegistryGetValue(
        struct _UNICODE_STRING *a1,
        struct _UNICODE_STRING *a2,
        int a3,
        void *a4,
        unsigned int *a5)
{
  NTSTATUS v8; // ebx
  ULONG v9; // esi
  int v10; // eax
  _DWORD *v11; // rdi
  unsigned int v12; // eax
  void *KeyHandle; // [rsp+30h] [rbp-40h] BYREF
  PVOID KeyValueInformation; // [rsp+38h] [rbp-38h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  ULONG ResultLength; // [rsp+A0h] [rbp+30h] BYREF

  ObjectAttributes.ObjectName = a1;
  ResultLength = 0;
  KeyHandle = 0;
  KeyValueInformation = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v8 = NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( v8 >= 0 )
  {
    v8 = NtQueryValueKey(KeyHandle, a2, KeyValuePartialInformation, 0, 0, &ResultLength);
    if ( (int)(v8 + 0x80000000) < 0 || v8 == -1073741789 )
    {
      v9 = 0;
      v10 = FveLibAllocWithTagZero(ResultLength);
      v11 = KeyValueInformation;
      v8 = v10;
      if ( v10 >= 0 )
      {
        v9 = ResultLength;
        v8 = NtQueryValueKey(
               KeyHandle,
               a2,
               KeyValuePartialInformation,
               KeyValueInformation,
               ResultLength,
               &ResultLength);
        if ( v8 >= 0 )
        {
          if ( v11[1] == a3 )
          {
            if ( a4 && (v12 = v11[2], *a5 >= v12) )
            {
              *a5 = v12;
              memcpy_0(a4, v11 + 3, v12);
              v8 = 0;
            }
            else
            {
              v8 = -1073741789;
              *a5 = v11[2];
            }
          }
          else
          {
            v8 = -1073741438;
          }
        }
      }
      if ( v11 )
        FveLibFreeWithTag(v11, v9, 0);
    }
  }
  if ( KeyHandle )
    NtClose(KeyHandle);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18005db90  mov     [rsp-28h+arg_8], rbx
0x18005db95  mov     [rsp-28h+arg_10], rsi
0x18005db9a  push    rbp
0x18005db9b  push    rdi
0x18005db9c  push    r12
0x18005db9e  push    r14
0x18005dba0  push    r15
0x18005dba2  mov     rbp, rsp
0x18005dba5  sub     rsp, 70h
0x18005dba9  xor     eax, eax
0x18005dbab  mov     [rbp+ObjectAttributes.ObjectName], rcx
0x18005dbaf  mov     r15d, r8d
0x18005dbb2  mov     [rbp+arg_0], eax
0x18005dbb5  mov     r12, rdx
0x18005dbb8  mov     [rbp+KeyHandle], rax
0x18005dbbc  xorps   xmm0, xmm0
0x18005dbbf  mov     [rbp+KeyValueInformation], rax
0x18005dbc3  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18005dbc7  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x18005dbcb  mov     edx, 20019h; DesiredAccess
0x18005dbd0  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x18005dbd8  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x18005dbdc  mov     qword ptr [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18005dbe4  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18005dbe9  mov     r14, r9
0x18005dbec  call    cs:__imp_NtOpenKey
0x18005dbf3  nop     dword ptr [rax+rax+00h]
0x18005dbf8  mov     ebx, eax
0x18005dbfa  test    eax, eax
0x18005dbfc  js      loc_18005DCDE
0x18005dc02  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18005dc06  lea     rax, [rbp+arg_0]
0x18005dc0a  xor     r9d, r9d; KeyValueInformation
0x18005dc0d  mov     [rsp+70h+ResultLength], rax; ResultLength
0x18005dc12  mov     rdx, r12; ValueName
0x18005dc15  mov     [rsp+70h+Length], 0; Length
0x18005dc1d  lea     r8d, [r9+2]; KeyValueInformationClass
0x18005dc21  call    cs:__imp_NtQueryValueKey
0x18005dc28  nop     dword ptr [rax+rax+00h]
0x18005dc2d  mov     ecx, 80000000h
0x18005dc32  mov     ebx, eax
0x18005dc34  add     eax, ecx
0x18005dc36  test    ecx, eax
0x18005dc38  jnz     short loc_18005DC46
0x18005dc3a  cmp     ebx, 0C0000023h
0x18005dc40  jnz     loc_18005DCDE
0x18005dc46  mov     ecx, [rbp+arg_0]; Size
0x18005dc49  lea     r8, [rbp+KeyValueInformation]
0x18005dc4d  xor     esi, esi
0x18005dc4f  call    FveLibAllocWithTagZero
0x18005dc54  mov     rdi, [rbp+KeyValueInformation]
0x18005dc58  mov     ebx, eax
0x18005dc5a  test    eax, eax
0x18005dc5c  js      short loc_18005DCCC
0x18005dc5e  mov     esi, [rbp+arg_0]
0x18005dc61  lea     rax, [rbp+arg_0]
0x18005dc65  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18005dc69  mov     r9, rdi; KeyValueInformation
0x18005dc6c  mov     [rsp+70h+ResultLength], rax; ResultLength
0x18005dc71  mov     r8d, 2; KeyValueInformationClass
0x18005dc77  mov     rdx, r12; ValueName
0x18005dc7a  mov     [rsp+70h+Length], esi; Length
0x18005dc7e  call    cs:__imp_NtQueryValueKey
0x18005dc85  nop     dword ptr [rax+rax+00h]
0x18005dc8a  mov     ebx, eax
0x18005dc8c  test    eax, eax
0x18005dc8e  js      short loc_18005DCCC
0x18005dc90  cmp     [rdi+4], r15d
0x18005dc94  jz      short loc_18005DC9D
0x18005dc96  mov     ebx, 0C0000182h
0x18005dc9b  jmp     short loc_18005DCCC
0x18005dc9d  mov     rcx, [rbp+arg_20]
0x18005dca1  test    r14, r14
0x18005dca4  jz      short loc_18005DCC2
0x18005dca6  mov     eax, [rdi+8]
0x18005dca9  cmp     [rcx], eax
0x18005dcab  jb      short loc_18005DCC2
0x18005dcad  mov     [rcx], eax
0x18005dcaf  lea     rdx, [rdi+0Ch]; Src
0x18005dcb3  mov     rcx, r14; void *
0x18005dcb6  mov     r8d, eax; Size
0x18005dcb9  call    memcpy_0
0x18005dcbe  xor     ebx, ebx
0x18005dcc0  jmp     short loc_18005DCCC
0x18005dcc2  mov     eax, [rdi+8]
0x18005dcc5  mov     ebx, 0C0000023h
0x18005dcca  mov     [rcx], eax
0x18005dccc  test    rdi, rdi
0x18005dccf  jz      short loc_18005DCDE
0x18005dcd1  mov     edx, esi
0x18005dcd3  xor     r8d, r8d
0x18005dcd6  mov     rcx, rdi
0x18005dcd9  call    FveLibFreeWithTag
0x18005dcde  mov     rcx, [rbp+KeyHandle]; Handle
0x18005dce2  test    rcx, rcx
0x18005dce5  jz      short loc_18005DCF3
0x18005dce7  call    cs:__imp_NtClose
0x18005dcee  nop     dword ptr [rax+rax+00h]
0x18005dcf3  lea     r11, [rsp+70h+var_s0]
0x18005dcf8  mov     eax, ebx
0x18005dcfa  mov     rbx, [r11+38h]
0x18005dcfe  mov     rsi, [r11+40h]
0x18005dd02  mov     rsp, r11
0x18005dd05  pop     r15
0x18005dd07  pop     r14
0x18005dd09  pop     r12
0x18005dd0b  pop     rdi
0x18005dd0c  pop     rbp
0x18005dd0d  retn
```
