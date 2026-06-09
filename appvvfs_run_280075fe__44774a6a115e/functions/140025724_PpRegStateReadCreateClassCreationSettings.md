# PpRegStateReadCreateClassCreationSettings

- ea: `0x140025724`
- end: `0x140025888`
- name: `PpRegStateReadCreateClassCreationSettings`
- size: `356`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x140024790`

## callees

- `0x1400138e0`
- `0x1400253a8`
- `0x14002553c`
- `0x140025724`
- `0x140025be0`
- `0x140025de0`
- `0x140025fc4`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1400257b0`
- `ntoskrnl!ZwClose` at `0x140025869`
- `ntoskrnl!ZwClose` at `0x1400257b0`
- `ntoskrnl!ZwClose` at `0x140025869`

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
0x140025724  mov     [rsp-8+arg_0], rbx
0x140025729  mov     [rsp-8+arg_8], rdi
0x14002572e  push    rbp
0x14002572f  mov     rbp, rsp
0x140025732  sub     rsp, 40h
0x140025736  mov     rdi, r8
0x140025739  mov     qword ptr [r8], 0
0x140025740  mov     qword ptr [r8+8], 0
0x140025748  lea     rax, [rbp+Handle]
0x14002574c  mov     qword ptr [r8+10h], 0
0x140025754  lea     r9, [rbp+arg_10]
0x140025758  mov     r8d, 1
0x14002575e  mov     [rsp+40h+var_20], rax
0x140025763  mov     rbx, rdx
0x140025766  mov     [rbp+arg_10], 0
0x14002576d  mov     [rbp+Handle], 0
0x140025775  mov     qword ptr [rbp+DestinationString.Length], 0
0x14002577d  call    PiRegStateOpenClassKey
0x140025782  test    eax, eax
0x140025784  js      loc_140025877
0x14002578a  cmp     [rbp+arg_10], 2
0x14002578e  jnz     short loc_1400257EA
0x140025790  mov     rcx, [rbp+Handle]
0x140025794  lea     r9, [rbp+DestinationString]
0x140025798  mov     r8d, 20019h
0x14002579e  lea     rdx, aProperties; "Properties"
0x1400257a5  call    CmRegUtilOpenExistingWstrKey
0x1400257aa  mov     rcx, [rbp+Handle]; Handle
0x1400257ae  mov     ebx, eax
0x1400257b0  call    cs:__imp_ZwClose
0x1400257b7  nop     dword ptr [rax+rax+00h]
0x1400257bc  test    ebx, ebx
0x1400257be  js      short loc_1400257D7
0x1400257c0  mov     rcx, qword ptr [rbp+DestinationString.Length]; KeyHandle
0x1400257c4  mov     rdx, rdi
0x1400257c7  call    PiRegStateReadStackCreationSettingsFromKey
0x1400257cc  mov     rcx, qword ptr [rbp+DestinationString.Length]
0x1400257d0  mov     ebx, eax
0x1400257d2  jmp     loc_140025869
0x1400257d7  cmp     ebx, 0C0000034h
0x1400257dd  jnz     loc_140025875
0x1400257e3  xor     ebx, ebx
0x1400257e5  jmp     loc_140025875
0x1400257ea  mov     r10, [rbx+30h]
0x1400257ee  mov     rdi, [rbp+Handle]
0x1400257f2  add     r10, 18h
0x1400257f6  jnz     short loc_1400257FF
0x1400257f8  mov     ebx, 0C000009Ah
0x1400257fd  jmp     short loc_140025866
0x1400257ff  xorps   xmm0, xmm0
0x140025802  lea     rdx, aClass; "Class"
0x140025809  lea     rcx, [rbp+DestinationString]; DestinationString
0x14002580d  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140025811  call    WdmlibRtlInitUnicodeStringEx
0x140025816  mov     ebx, eax
0x140025818  test    eax, eax
0x14002581a  js      short loc_140025866
0x14002581c  mov     r8, r10
0x14002581f  lea     rdx, [rbp+DestinationString]; ValueName
0x140025823  mov     rcx, rdi; KeyHandle
0x140025826  call    CmRegUtilUcValueSetUcString
0x14002582b  mov     ebx, eax
0x14002582d  test    eax, eax
0x14002582f  js      short loc_140025866
0x140025831  lea     r8, [rbp+arg_10]
0x140025835  mov     [rbp+arg_10], 31h ; '1'
0x14002583c  lea     rdx, aNodisplayclass; "NoDisplayClass"
0x140025843  mov     rcx, rdi
0x140025846  call    CmRegUtilWstrValueSetWstrString
0x14002584b  mov     ebx, eax
0x14002584d  test    eax, eax
0x14002584f  js      short loc_140025866
0x140025851  lea     r8, [rbp+arg_10]
0x140025855  mov     rcx, rdi
0x140025858  lea     rdx, aNouseclass; "NoUseClass"
0x14002585f  call    CmRegUtilWstrValueSetWstrString
0x140025864  mov     ebx, eax
0x140025866  mov     rcx, rdi; Handle
0x140025869  call    cs:__imp_ZwClose
0x140025870  nop     dword ptr [rax+rax+00h]
0x140025875  mov     eax, ebx
0x140025877  mov     rbx, [rsp+40h+arg_0]
0x14002587c  mov     rdi, [rsp+40h+arg_8]
0x140025881  add     rsp, 40h
0x140025885  pop     rbp
0x140025886  retn
```
