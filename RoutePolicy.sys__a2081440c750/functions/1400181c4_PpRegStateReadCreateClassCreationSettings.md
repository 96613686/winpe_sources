# PpRegStateReadCreateClassCreationSettings

- ea: `0x1400181c4`
- end: `0x140018328`
- name: `PpRegStateReadCreateClassCreationSettings`
- size: `356`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x140017230`

## callees

- `0x140008c0c`
- `0x140017e48`
- `0x140017fdc`
- `0x1400181c4`
- `0x140018680`
- `0x140018880`
- `0x140018a64`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140018250`
- `ntoskrnl!ZwClose` at `0x140018309`
- `ntoskrnl!ZwClose` at `0x140018250`
- `ntoskrnl!ZwClose` at `0x140018309`

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
0x1400181c4  mov     [rsp-8+arg_0], rbx
0x1400181c9  mov     [rsp-8+arg_8], rdi
0x1400181ce  push    rbp
0x1400181cf  mov     rbp, rsp
0x1400181d2  sub     rsp, 40h
0x1400181d6  mov     rdi, r8
0x1400181d9  mov     qword ptr [r8], 0
0x1400181e0  mov     qword ptr [r8+8], 0
0x1400181e8  lea     rax, [rbp+Handle]
0x1400181ec  mov     qword ptr [r8+10h], 0
0x1400181f4  lea     r9, [rbp+arg_10]
0x1400181f8  mov     r8d, 1
0x1400181fe  mov     [rsp+40h+var_20], rax
0x140018203  mov     rbx, rdx
0x140018206  mov     [rbp+arg_10], 0
0x14001820d  mov     [rbp+Handle], 0
0x140018215  mov     qword ptr [rbp+DestinationString.Length], 0
0x14001821d  call    PiRegStateOpenClassKey
0x140018222  test    eax, eax
0x140018224  js      loc_140018317
0x14001822a  cmp     [rbp+arg_10], 2
0x14001822e  jnz     short loc_14001828A
0x140018230  mov     rcx, [rbp+Handle]
0x140018234  lea     r9, [rbp+DestinationString]
0x140018238  mov     r8d, 20019h
0x14001823e  lea     rdx, aProperties; "Properties"
0x140018245  call    CmRegUtilOpenExistingWstrKey
0x14001824a  mov     rcx, [rbp+Handle]; Handle
0x14001824e  mov     ebx, eax
0x140018250  call    cs:__imp_ZwClose
0x140018257  nop     dword ptr [rax+rax+00h]
0x14001825c  test    ebx, ebx
0x14001825e  js      short loc_140018277
0x140018260  mov     rcx, qword ptr [rbp+DestinationString.Length]; KeyHandle
0x140018264  mov     rdx, rdi
0x140018267  call    PiRegStateReadStackCreationSettingsFromKey
0x14001826c  mov     rcx, qword ptr [rbp+DestinationString.Length]
0x140018270  mov     ebx, eax
0x140018272  jmp     loc_140018309
0x140018277  cmp     ebx, 0C0000034h
0x14001827d  jnz     loc_140018315
0x140018283  xor     ebx, ebx
0x140018285  jmp     loc_140018315
0x14001828a  mov     r10, [rbx+30h]
0x14001828e  mov     rdi, [rbp+Handle]
0x140018292  add     r10, 18h
0x140018296  jnz     short loc_14001829F
0x140018298  mov     ebx, 0C000009Ah
0x14001829d  jmp     short loc_140018306
0x14001829f  xorps   xmm0, xmm0
0x1400182a2  lea     rdx, aClass; "Class"
0x1400182a9  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400182ad  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400182b1  call    WdmlibRtlInitUnicodeStringEx
0x1400182b6  mov     ebx, eax
0x1400182b8  test    eax, eax
0x1400182ba  js      short loc_140018306
0x1400182bc  mov     r8, r10
0x1400182bf  lea     rdx, [rbp+DestinationString]; ValueName
0x1400182c3  mov     rcx, rdi; KeyHandle
0x1400182c6  call    CmRegUtilUcValueSetUcString
0x1400182cb  mov     ebx, eax
0x1400182cd  test    eax, eax
0x1400182cf  js      short loc_140018306
0x1400182d1  lea     r8, [rbp+arg_10]
0x1400182d5  mov     [rbp+arg_10], 31h ; '1'
0x1400182dc  lea     rdx, aNodisplayclass; "NoDisplayClass"
0x1400182e3  mov     rcx, rdi
0x1400182e6  call    CmRegUtilWstrValueSetWstrString
0x1400182eb  mov     ebx, eax
0x1400182ed  test    eax, eax
0x1400182ef  js      short loc_140018306
0x1400182f1  lea     r8, [rbp+arg_10]
0x1400182f5  mov     rcx, rdi
0x1400182f8  lea     rdx, aNouseclass; "NoUseClass"
0x1400182ff  call    CmRegUtilWstrValueSetWstrString
0x140018304  mov     ebx, eax
0x140018306  mov     rcx, rdi; Handle
0x140018309  call    cs:__imp_ZwClose
0x140018310  nop     dword ptr [rax+rax+00h]
0x140018315  mov     eax, ebx
0x140018317  mov     rbx, [rsp+40h+arg_0]
0x14001831c  mov     rdi, [rsp+40h+arg_8]
0x140018321  add     rsp, 40h
0x140018325  pop     rbp
0x140018326  retn
```
