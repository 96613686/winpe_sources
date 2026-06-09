# BampUserSettingsOpenUserKey

- ea: `0x140011b44`
- end: `0x140011c5f`
- name: `BampUserSettingsOpenUserKey`
- size: `283`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, __int16, void **)`
- caller_count: `4`
- callee_count: `1`
- tags: `reparse_path, registry_config`

## callers

- `0x14000ce18`
- `0x1400119a0`
- `0x140012c84`
- `0x140015608`

## callees

- `0x140011b44`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140011c4e`
- `ntoskrnl!ZwClose` at `0x140011c4e`
- `ntoskrnl!ZwOpenKey` at `0x140011ba4`
- `ntoskrnl!ZwOpenKey` at `0x140011ba4`
- `ntoskrnl!ZwCreateKey` at `0x140011bfc`
- `ntoskrnl!ZwCreateKey` at `0x140011bfc`
- `ntoskrnl!ZwSetValueKey` at `0x140011c3d`
- `ntoskrnl!ZwSetValueKey` at `0x140011c3d`

## pseudocode

```c
__int64 __fastcall BampUserSettingsOpenUserKey(struct _UNICODE_STRING *a1, __int16 a2, void **a3)
{
  NTSTATUS v4; // eax
  NTSTATUS v5; // ebx
  void *v6; // rcx
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  int Data; // [rsp+90h] [rbp+20h] BYREF
  ULONG Disposition; // [rsp+98h] [rbp+28h] BYREF
  void *KeyHandle; // [rsp+A8h] [rbp+38h] BYREF

  ObjectAttributes.ObjectName = a1;
  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  Data = 0;
  Disposition = 0;
  KeyHandle = 0;
  ObjectAttributes.RootDirectory = BampUserSettingsContext;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.Attributes = ~(a2 << 8) & 0x200 | 0x40;
  if ( (a2 & 1) != 0 )
  {
    v5 = ZwCreateKey(&KeyHandle, 0xF003Fu, &ObjectAttributes, 0, 0, 0, &Disposition);
    if ( v5 < 0 )
      goto LABEL_8;
    if ( Disposition != 1 )
      goto LABEL_4;
    Data = 1;
    v4 = ZwSetValueKey(KeyHandle, &BampUserSettingsVersionValueName, 0, 4u, &Data, 4u);
  }
  else
  {
    v4 = ZwOpenKey(&KeyHandle, 0xF003Fu, &ObjectAttributes);
  }
  v5 = v4;
  if ( v4 >= 0 )
  {
LABEL_4:
    v6 = 0;
    *a3 = KeyHandle;
    v5 = 0;
    KeyHandle = 0;
    goto LABEL_5;
  }
LABEL_8:
  v6 = KeyHandle;
LABEL_5:
  if ( v6 )
    ZwClose(v6);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140011b44  push    rbp
0x140011b46  push    rbx
0x140011b47  push    rdi
0x140011b48  mov     rbp, rsp
0x140011b4b  sub     rsp, 70h
0x140011b4f  xor     eax, eax
0x140011b51  mov     [rbp+ObjectAttributes.ObjectName], rcx
0x140011b55  mov     dword ptr [rbp+ObjectAttributes+1Ch], eax
0x140011b58  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x140011b5c  mov     [rbp+Data], eax
0x140011b5f  xorps   xmm0, xmm0
0x140011b62  mov     [rbp+arg_8], eax
0x140011b65  mov     rdi, r8
0x140011b68  mov     [rbp+KeyHandle], rax
0x140011b6c  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140011b70  mov     rax, qword ptr cs:BampUserSettingsContext
0x140011b77  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x140011b7b  mov     eax, edx
0x140011b7d  shl     eax, 8
0x140011b80  not     eax
0x140011b82  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x140011b8a  and     eax, 200h
0x140011b8f  or      eax, 40h
0x140011b92  test    dl, 1
0x140011b95  mov     [rbp+ObjectAttributes.Attributes], eax
0x140011b98  mov     edx, 0F003Fh; DesiredAccess
0x140011b9d  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140011ba2  jnz     short loc_140011BDF
0x140011ba4  call    cs:__imp_ZwOpenKey
0x140011bab  nop     dword ptr [rax+rax+00h]
0x140011bb0  mov     ebx, eax
0x140011bb2  test    eax, eax
0x140011bb4  js      short loc_140011BD9
0x140011bb6  mov     rax, [rbp+KeyHandle]
0x140011bba  xor     ecx, ecx; Handle
0x140011bbc  mov     [rdi], rax
0x140011bbf  xor     ebx, ebx
0x140011bc1  mov     [rbp+KeyHandle], rcx
0x140011bc5  test    rcx, rcx
0x140011bc8  jnz     loc_140011C4E
0x140011bce  mov     eax, ebx
0x140011bd0  add     rsp, 70h
0x140011bd4  pop     rdi
0x140011bd5  pop     rbx
0x140011bd6  pop     rbp
0x140011bd7  retn
0x140011bd9  mov     rcx, [rbp+KeyHandle]
0x140011bdd  jmp     short loc_140011BC5
0x140011bdf  lea     rax, [rbp+arg_8]
0x140011be3  xor     r9d, r9d; TitleIndex
0x140011be6  mov     [rsp+70h+Disposition], rax; Disposition
0x140011beb  mov     [rsp+70h+CreateOptions], 0; CreateOptions
0x140011bf3  mov     [rsp+70h+Class], 0; Class
0x140011bfc  call    cs:__imp_ZwCreateKey
0x140011c03  nop     dword ptr [rax+rax+00h]
0x140011c08  mov     ebx, eax
0x140011c0a  test    eax, eax
0x140011c0c  js      short loc_140011BD9
0x140011c0e  cmp     [rbp+arg_8], 1
0x140011c12  jnz     short loc_140011BB6
0x140011c14  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140011c18  lea     rax, [rbp+Data]
0x140011c1c  mov     r9d, 4; Type
0x140011c22  mov     [rbp+Data], 1
0x140011c29  mov     [rsp+70h+CreateOptions], r9d; DataSize
0x140011c2e  lea     rdx, BampUserSettingsVersionValueName; ValueName
0x140011c35  xor     r8d, r8d; TitleIndex
0x140011c38  mov     [rsp+70h+Class], rax; Data
0x140011c3d  call    cs:__imp_ZwSetValueKey
0x140011c44  nop     dword ptr [rax+rax+00h]
0x140011c49  jmp     loc_140011BB0
0x140011c4e  call    cs:__imp_ZwClose
0x140011c55  nop     dword ptr [rax+rax+00h]
0x140011c5a  jmp     loc_140011BCE
```
