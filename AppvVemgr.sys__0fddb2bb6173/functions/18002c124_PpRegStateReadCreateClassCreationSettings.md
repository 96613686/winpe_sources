# PpRegStateReadCreateClassCreationSettings

- ea: `0x18002c124`
- end: `0x18002c288`
- name: `PpRegStateReadCreateClassCreationSettings`
- size: `356`
- prototype: `NTSTATUS __fastcall(unsigned int *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18002b190`

## callees

- `0x18001b8ac`
- `0x18002bda8`
- `0x18002bf3c`
- `0x18002c124`
- `0x18002c5e0`
- `0x18002c7e0`
- `0x18002c9c4`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x18002c1b0`
- `ntoskrnl!ZwClose` at `0x18002c269`
- `ntoskrnl!ZwClose` at `0x18002c1b0`
- `ntoskrnl!ZwClose` at `0x18002c269`

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
  ULONG v11; // [rsp+60h] [rbp+20h] BYREF
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
0x18002c124  mov     [rsp-8+arg_0], rbx
0x18002c129  mov     [rsp-8+arg_8], rdi
0x18002c12e  push    rbp
0x18002c12f  mov     rbp, rsp
0x18002c132  sub     rsp, 40h
0x18002c136  mov     rdi, r8
0x18002c139  mov     qword ptr [r8], 0
0x18002c140  mov     qword ptr [r8+8], 0
0x18002c148  lea     rax, [rbp+Handle]
0x18002c14c  mov     qword ptr [r8+10h], 0
0x18002c154  lea     r9, [rbp+arg_10]
0x18002c158  mov     r8d, 1
0x18002c15e  mov     [rsp+40h+var_20], rax
0x18002c163  mov     rbx, rdx
0x18002c166  mov     [rbp+arg_10], 0
0x18002c16d  mov     [rbp+Handle], 0
0x18002c175  mov     qword ptr [rbp+DestinationString.Length], 0
0x18002c17d  call    PiRegStateOpenClassKey
0x18002c182  test    eax, eax
0x18002c184  js      loc_18002C277
0x18002c18a  cmp     [rbp+arg_10], 2
0x18002c18e  jnz     short loc_18002C1EA
0x18002c190  mov     rcx, [rbp+Handle]
0x18002c194  lea     r9, [rbp+DestinationString]
0x18002c198  mov     r8d, 20019h
0x18002c19e  lea     rdx, aProperties; "Properties"
0x18002c1a5  call    CmRegUtilOpenExistingWstrKey
0x18002c1aa  mov     rcx, [rbp+Handle]; Handle
0x18002c1ae  mov     ebx, eax
0x18002c1b0  call    cs:__imp_ZwClose
0x18002c1b7  nop     dword ptr [rax+rax+00h]
0x18002c1bc  test    ebx, ebx
0x18002c1be  js      short loc_18002C1D7
0x18002c1c0  mov     rcx, qword ptr [rbp+DestinationString.Length]; KeyHandle
0x18002c1c4  mov     rdx, rdi
0x18002c1c7  call    PiRegStateReadStackCreationSettingsFromKey
0x18002c1cc  mov     rcx, qword ptr [rbp+DestinationString.Length]
0x18002c1d0  mov     ebx, eax
0x18002c1d2  jmp     loc_18002C269
0x18002c1d7  cmp     ebx, 0C0000034h
0x18002c1dd  jnz     loc_18002C275
0x18002c1e3  xor     ebx, ebx
0x18002c1e5  jmp     loc_18002C275
0x18002c1ea  mov     r10, [rbx+30h]
0x18002c1ee  mov     rdi, [rbp+Handle]
0x18002c1f2  add     r10, 18h
0x18002c1f6  jnz     short loc_18002C1FF
0x18002c1f8  mov     ebx, 0C000009Ah
0x18002c1fd  jmp     short loc_18002C266
0x18002c1ff  xorps   xmm0, xmm0
0x18002c202  lea     rdx, aClass; "Class"
0x18002c209  lea     rcx, [rbp+DestinationString]; DestinationString
0x18002c20d  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18002c211  call    WdmlibRtlInitUnicodeStringEx
0x18002c216  mov     ebx, eax
0x18002c218  test    eax, eax
0x18002c21a  js      short loc_18002C266
0x18002c21c  mov     r8, r10
0x18002c21f  lea     rdx, [rbp+DestinationString]; ValueName
0x18002c223  mov     rcx, rdi; KeyHandle
0x18002c226  call    CmRegUtilUcValueSetUcString
0x18002c22b  mov     ebx, eax
0x18002c22d  test    eax, eax
0x18002c22f  js      short loc_18002C266
0x18002c231  lea     r8, [rbp+arg_10]
0x18002c235  mov     [rbp+arg_10], 31h ; '1'
0x18002c23c  lea     rdx, aNodisplayclass; "NoDisplayClass"
0x18002c243  mov     rcx, rdi
0x18002c246  call    CmRegUtilWstrValueSetWstrString
0x18002c24b  mov     ebx, eax
0x18002c24d  test    eax, eax
0x18002c24f  js      short loc_18002C266
0x18002c251  lea     r8, [rbp+arg_10]
0x18002c255  mov     rcx, rdi
0x18002c258  lea     rdx, aNouseclass; "NoUseClass"
0x18002c25f  call    CmRegUtilWstrValueSetWstrString
0x18002c264  mov     ebx, eax
0x18002c266  mov     rcx, rdi; Handle
0x18002c269  call    cs:__imp_ZwClose
0x18002c270  nop     dword ptr [rax+rax+00h]
0x18002c275  mov     eax, ebx
0x18002c277  mov     rbx, [rsp+40h+arg_0]
0x18002c27c  mov     rdi, [rsp+40h+arg_8]
0x18002c281  add     rsp, 40h
0x18002c285  pop     rbp
0x18002c286  retn
```
