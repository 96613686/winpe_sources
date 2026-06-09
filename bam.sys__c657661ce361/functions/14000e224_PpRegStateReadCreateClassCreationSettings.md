# PpRegStateReadCreateClassCreationSettings

- ea: `0x14000e224`
- end: `0x14000e388`
- name: `PpRegStateReadCreateClassCreationSettings`
- size: `356`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x14000d2a0`

## callees

- `0x1400022c0`
- `0x14000dea8`
- `0x14000e03c`
- `0x14000e224`
- `0x14000e718`
- `0x14000e918`
- `0x14000eafc`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14000e2b0`
- `ntoskrnl!ZwClose` at `0x14000e369`
- `ntoskrnl!ZwClose` at `0x14000e2b0`
- `ntoskrnl!ZwClose` at `0x14000e369`

## pseudocode

```c
NTSTATUS __fastcall PpRegStateReadCreateClassCreationSettings(unsigned int *a1, __int64 a2, _QWORD *a3)
{
  NTSTATUS result; // eax
  NTSTATUS inited; // ebx
  NTSTATUS StackCreationSettingsFromKey; // eax
  void *v8; // rcx
  HANDLE v9; // rdi
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-10h] BYREF
  int v11; // [rsp+60h] [rbp+20h] BYREF
  HANDLE Handle; // [rsp+68h] [rbp+28h] BYREF

  *a3 = 0;
  a3[1] = 0;
  a3[2] = 0;
  v11 = 0;
  Handle = 0;
  *(_QWORD *)&DestinationString.Length = 0;
  result = PiRegStateOpenClassKey(a1, a2, 1, &v11, &Handle);
  if ( result >= 0 )
  {
    if ( v11 == 2 )
    {
      inited = CmRegUtilOpenExistingWstrKey((__int64)Handle, L"Properties", 131097, (void **)&DestinationString);
      ZwClose(Handle);
      if ( inited < 0 )
      {
        if ( inited == -1073741772 )
          return 0;
        return inited;
      }
      StackCreationSettingsFromKey = PiRegStateReadStackCreationSettingsFromKey(
                                       *(HANDLE *)&DestinationString.Length,
                                       (__int64)a3);
      v8 = *(void **)&DestinationString.Length;
      inited = StackCreationSettingsFromKey;
    }
    else
    {
      v9 = Handle;
      if ( *(_QWORD *)(a2 + 48) == -24 )
      {
        inited = -1073741670;
      }
      else
      {
        DestinationString = 0;
        inited = WdmlibRtlInitUnicodeStringEx(&DestinationString, L"Class");
        if ( inited >= 0 )
        {
          inited = CmRegUtilUcValueSetUcString(v9, &DestinationString);
          if ( inited >= 0 )
          {
            v11 = 49;
            inited = CmRegUtilWstrValueSetWstrString(v9, L"NoDisplayClass", &v11);
            if ( inited >= 0 )
              inited = CmRegUtilWstrValueSetWstrString(v9, L"NoUseClass", &v11);
          }
        }
      }
      v8 = v9;
    }
    ZwClose(v8);
    return inited;
  }
  return result;
}

```

## disassembly

```asm
0x14000e224  mov     [rsp-8+arg_0], rbx
0x14000e229  mov     [rsp-8+arg_8], rdi
0x14000e22e  push    rbp
0x14000e22f  mov     rbp, rsp
0x14000e232  sub     rsp, 40h
0x14000e236  mov     rdi, r8
0x14000e239  mov     qword ptr [r8], 0
0x14000e240  mov     qword ptr [r8+8], 0
0x14000e248  lea     rax, [rbp+Handle]
0x14000e24c  mov     qword ptr [r8+10h], 0
0x14000e254  lea     r9, [rbp+arg_10]
0x14000e258  mov     r8d, 1
0x14000e25e  mov     [rsp+40h+var_20], rax
0x14000e263  mov     rbx, rdx
0x14000e266  mov     [rbp+arg_10], 0
0x14000e26d  mov     [rbp+Handle], 0
0x14000e275  mov     qword ptr [rbp+DestinationString.Length], 0
0x14000e27d  call    PiRegStateOpenClassKey
0x14000e282  test    eax, eax
0x14000e284  js      loc_14000E377
0x14000e28a  cmp     [rbp+arg_10], 2
0x14000e28e  jnz     short loc_14000E2EA
0x14000e290  mov     rcx, [rbp+Handle]
0x14000e294  lea     r9, [rbp+DestinationString]
0x14000e298  mov     r8d, 20019h
0x14000e29e  lea     rdx, aProperties; "Properties"
0x14000e2a5  call    CmRegUtilOpenExistingWstrKey
0x14000e2aa  mov     rcx, [rbp+Handle]; Handle
0x14000e2ae  mov     ebx, eax
0x14000e2b0  call    cs:__imp_ZwClose
0x14000e2b7  nop     dword ptr [rax+rax+00h]
0x14000e2bc  test    ebx, ebx
0x14000e2be  js      short loc_14000E2D7
0x14000e2c0  mov     rcx, qword ptr [rbp+DestinationString.Length]; KeyHandle
0x14000e2c4  mov     rdx, rdi
0x14000e2c7  call    PiRegStateReadStackCreationSettingsFromKey
0x14000e2cc  mov     rcx, qword ptr [rbp+DestinationString.Length]
0x14000e2d0  mov     ebx, eax
0x14000e2d2  jmp     loc_14000E369
0x14000e2d7  cmp     ebx, 0C0000034h
0x14000e2dd  jnz     loc_14000E375
0x14000e2e3  xor     ebx, ebx
0x14000e2e5  jmp     loc_14000E375
0x14000e2ea  mov     r10, [rbx+30h]
0x14000e2ee  mov     rdi, [rbp+Handle]
0x14000e2f2  add     r10, 18h
0x14000e2f6  jnz     short loc_14000E2FF
0x14000e2f8  mov     ebx, 0C000009Ah
0x14000e2fd  jmp     short loc_14000E366
0x14000e2ff  xorps   xmm0, xmm0
0x14000e302  lea     rdx, aClass; "Class"
0x14000e309  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000e30d  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14000e311  call    WdmlibRtlInitUnicodeStringEx
0x14000e316  mov     ebx, eax
0x14000e318  test    eax, eax
0x14000e31a  js      short loc_14000E366
0x14000e31c  mov     r8, r10
0x14000e31f  lea     rdx, [rbp+DestinationString]; ValueName
0x14000e323  mov     rcx, rdi; KeyHandle
0x14000e326  call    CmRegUtilUcValueSetUcString
0x14000e32b  mov     ebx, eax
0x14000e32d  test    eax, eax
0x14000e32f  js      short loc_14000E366
0x14000e331  lea     r8, [rbp+arg_10]
0x14000e335  mov     [rbp+arg_10], 31h ; '1'
0x14000e33c  lea     rdx, aNodisplayclass; "NoDisplayClass"
0x14000e343  mov     rcx, rdi
0x14000e346  call    CmRegUtilWstrValueSetWstrString
0x14000e34b  mov     ebx, eax
0x14000e34d  test    eax, eax
0x14000e34f  js      short loc_14000E366
0x14000e351  lea     r8, [rbp+arg_10]
0x14000e355  mov     rcx, rdi
0x14000e358  lea     rdx, aNouseclass; "NoUseClass"
0x14000e35f  call    CmRegUtilWstrValueSetWstrString
0x14000e364  mov     ebx, eax
0x14000e366  mov     rcx, rdi; Handle
0x14000e369  call    cs:__imp_ZwClose
0x14000e370  nop     dword ptr [rax+rax+00h]
0x14000e375  mov     eax, ebx
0x14000e377  mov     rbx, [rsp+40h+arg_0]
0x14000e37c  mov     rdi, [rsp+40h+arg_8]
0x14000e381  add     rsp, 40h
0x14000e385  pop     rbp
0x14000e386  retn
```
