# TpmApiRegistryGetValue(_UNICODE_STRING *,_UNICODE_STRING *,ulong,void *,ulong *)

- ea: `0x180076318`
- end: `0x180076494`
- name: `?TpmApiRegistryGetValue@@YAJPEAU_UNICODE_STRING@@0KPEAXPEAK@Z`
- size: `380`
- prototype: `int(struct _UNICODE_STRING *, struct _UNICODE_STRING *, unsigned int, void *, unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180076094`
- `0x1800761c8`

## callees

- `0x18002d500`
- `0x180074a1c`
- `0x180074a48`
- `0x180076318`

## import_xrefs

- `ntdll!NtClose` at `0x180076478`
- `ntdll!NtClose` at `0x180076478`
- `ntdll!ZwQueryValueKey` at `0x1800763ae`
- `ntdll!ZwQueryValueKey` at `0x180076413`
- `ntdll!ZwQueryValueKey` at `0x1800763ae`
- `ntdll!ZwQueryValueKey` at `0x180076413`
- `ntdll!ZwOpenKey` at `0x180076379`
- `ntdll!ZwOpenKey` at `0x180076379`

## pseudocode

```c
__int64 __fastcall TpmApiRegistryGetValue(
        struct _UNICODE_STRING *a1,
        struct _UNICODE_STRING *a2,
        int a3,
        void *a4,
        unsigned int *a5)
{
  NTSTATUS v8; // ebx
  _DWORD *v9; // rdi
  unsigned int v10; // eax
  PVOID KeyValueInformation; // [rsp+30h] [rbp-48h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-40h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-38h] BYREF
  ULONG ResultLength; // [rsp+B0h] [rbp+38h] BYREF

  ObjectAttributes.ObjectName = a1;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  ResultLength = 0;
  KeyHandle = 0;
  KeyValueInformation = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  ObjectAttributes.RootDirectory = 0;
  v8 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( v8 >= 0 )
  {
    v8 = ZwQueryValueKey(KeyHandle, a2, KeyValuePartialInformation, 0, 0, &ResultLength);
    if ( (int)(v8 + 0x80000000) < 0 || v8 == -1073741789 )
    {
      TpmApiCallbackAlloc(0, ResultLength, &KeyValueInformation);
      if ( KeyValueInformation )
      {
        v9 = KeyValueInformation;
        v8 = ZwQueryValueKey(
               KeyHandle,
               a2,
               KeyValuePartialInformation,
               KeyValueInformation,
               ResultLength,
               &ResultLength);
        if ( v8 >= 0 )
        {
          if ( v9[1] == a3 )
          {
            if ( a4 && (v10 = v9[2], *a5 >= v10) )
            {
              *a5 = v10;
              memcpy_0(a4, v9 + 3, v10);
              v8 = 0;
            }
            else
            {
              v8 = -1073741789;
              *a5 = v9[2];
            }
          }
          else
          {
            v8 = -1073741438;
          }
        }
      }
      else
      {
        v8 = -1073741801;
      }
    }
  }
  TpmApiCallbackFree(0, ResultLength, KeyValueInformation);
  if ( KeyHandle )
    NtClose(KeyHandle);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180076318  push    rbp
0x18007631a  push    rbx
0x18007631b  push    rsi
0x18007631c  push    rdi
0x18007631d  push    r14
0x18007631f  push    r15
0x180076321  mov     rbp, rsp
0x180076324  sub     rsp, 78h
0x180076328  mov     r14d, r8d
0x18007632b  mov     [rbp+ObjectAttributes.ObjectName], rcx
0x18007632f  mov     r15, rdx
0x180076332  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x18007633a  xorps   xmm0, xmm0
0x18007633d  mov     qword ptr [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180076345  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180076349  mov     [rbp+arg_0], 0
0x180076350  mov     edx, 20019h; DesiredAccess
0x180076355  mov     [rbp+KeyHandle], 0
0x18007635d  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x180076361  mov     [rbp+KeyValueInformation], 0
0x180076369  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18007636e  mov     rsi, r9
0x180076371  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x180076379  call    cs:__imp_ZwOpenKey
0x180076380  nop     dword ptr [rax+rax+00h]
0x180076385  mov     ebx, eax
0x180076387  test    eax, eax
0x180076389  js      loc_180076461
0x18007638f  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x180076393  lea     rax, [rbp+arg_0]
0x180076397  xor     r9d, r9d; KeyValueInformation
0x18007639a  mov     [rsp+78h+ResultLength], rax; ResultLength
0x18007639f  mov     rdx, r15; ValueName
0x1800763a2  mov     [rsp+78h+Length], 0; Length
0x1800763aa  lea     r8d, [r9+2]; KeyValueInformationClass
0x1800763ae  call    cs:__imp_ZwQueryValueKey
0x1800763b5  nop     dword ptr [rax+rax+00h]
0x1800763ba  mov     ecx, 80000000h
0x1800763bf  mov     ebx, eax
0x1800763c1  add     eax, ecx
0x1800763c3  test    ecx, eax
0x1800763c5  jnz     short loc_1800763D3
0x1800763c7  cmp     ebx, 0C0000023h
0x1800763cd  jnz     loc_180076461
0x1800763d3  mov     edx, [rbp+arg_0]
0x1800763d6  lea     r8, [rbp+KeyValueInformation]
0x1800763da  xor     ecx, ecx
0x1800763dc  call    TpmApiCallbackAlloc
0x1800763e1  cmp     [rbp+KeyValueInformation], 0
0x1800763e6  jnz     short loc_1800763EF
0x1800763e8  mov     ebx, 0C0000017h
0x1800763ed  jmp     short loc_180076461
0x1800763ef  mov     rdi, [rbp+KeyValueInformation]
0x1800763f3  lea     rax, [rbp+arg_0]
0x1800763f7  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1800763fb  mov     r9, rdi; KeyValueInformation
0x1800763fe  mov     [rsp+78h+ResultLength], rax; ResultLength
0x180076403  mov     r8d, 2; KeyValueInformationClass
0x180076409  mov     eax, [rbp+arg_0]
0x18007640c  mov     rdx, r15; ValueName
0x18007640f  mov     [rsp+78h+Length], eax; Length
0x180076413  call    cs:__imp_ZwQueryValueKey
0x18007641a  nop     dword ptr [rax+rax+00h]
0x18007641f  mov     ebx, eax
0x180076421  test    eax, eax
0x180076423  js      short loc_180076461
0x180076425  cmp     [rdi+4], r14d
0x180076429  jz      short loc_180076432
0x18007642b  mov     ebx, 0C0000182h
0x180076430  jmp     short loc_180076461
0x180076432  mov     rcx, [rbp+arg_20]
0x180076436  test    rsi, rsi
0x180076439  jz      short loc_180076457
0x18007643b  mov     eax, [rdi+8]
0x18007643e  cmp     [rcx], eax
0x180076440  jb      short loc_180076457
0x180076442  mov     [rcx], eax
0x180076444  lea     rdx, [rdi+0Ch]; Src
0x180076448  mov     rcx, rsi; void *
0x18007644b  mov     r8d, eax; Size
0x18007644e  call    memcpy_0
0x180076453  xor     ebx, ebx
0x180076455  jmp     short loc_180076461
0x180076457  mov     eax, [rdi+8]
0x18007645a  mov     ebx, 0C0000023h
0x18007645f  mov     [rcx], eax
0x180076461  mov     r8, [rbp+KeyValueInformation]
0x180076465  xor     ecx, ecx
0x180076467  mov     edx, [rbp+arg_0]
0x18007646a  call    TpmApiCallbackFree
0x18007646f  mov     rcx, [rbp+KeyHandle]; Handle
0x180076473  test    rcx, rcx
0x180076476  jz      short loc_180076484
0x180076478  call    cs:__imp_NtClose
0x18007647f  nop     dword ptr [rax+rax+00h]
0x180076484  mov     eax, ebx
0x180076486  add     rsp, 78h
0x18007648a  pop     r15
0x18007648c  pop     r14
0x18007648e  pop     rdi
0x18007648f  pop     rsi
0x180076490  pop     rbx
0x180076491  pop     rbp
0x180076492  retn
```
