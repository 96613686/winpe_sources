# AhcSdbQueryCreate

- ea: `0x14002ad30`
- end: `0x14002ade0`
- name: `AhcSdbQueryCreate`
- size: `176`
- prototype: `__int64 __fastcall(ULONGLONG **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14002a3dc`

## callees

- `0x14002ad30`
- `0x14002ade8`
- `0x14003e364`
- `0x14005498c`

## import_xrefs

- `ntoskrnl!EtwRegister` at `0x14002ad8a`
- `ntoskrnl!EtwRegister` at `0x14002ad8a`

## string_xrefs

- `0x14002ad65`: `AhcSdbQueryCreate`
- `0x14002adad`: `AhcSdbQueryCreate`

## pseudocode

```c
__int64 __fastcall AhcSdbQueryCreate(ULONGLONG **a1)
{
  ULONGLONG *v2; // rax
  ULONGLONG *v3; // rdi
  unsigned int v4; // ebx
  NTSTATUS v5; // eax

  v2 = (ULONGLONG *)AslAlloc(a1, 8, 1);
  v3 = v2;
  if ( v2 )
  {
    v5 = EtwRegister(&MS_Windows_AeCache_Provider, 0, 0, v2);
    v4 = v5;
    if ( v5 >= 0 )
    {
      *a1 = v3;
      return 0;
    }
    else
    {
      AslLogCallPrintf(1, "AhcSdbQueryCreate", 159, "Failed to register event provider [%x]", v5);
      AhcSdbQueryDelete(v3);
    }
  }
  else
  {
    AslLogCallPrintf(1, "AhcSdbQueryCreate", 144, "Out of memory");
    return (unsigned int)-1073741801;
  }
  return v4;
}

```

## disassembly

```asm
0x14002ad30  mov     [rsp+arg_0], rbx
0x14002ad35  mov     [rsp+arg_8], rsi
0x14002ad3a  push    rdi
0x14002ad3b  sub     rsp, 30h
0x14002ad3f  mov     edx, 8
0x14002ad44  mov     rsi, rcx
0x14002ad47  lea     r8d, [rdx-7]
0x14002ad4b  call    AslAlloc
0x14002ad50  mov     rdi, rax
0x14002ad53  test    rax, rax
0x14002ad56  jnz     short loc_14002AD7B
0x14002ad58  lea     r9, aOutOfMemory; "Out of memory"
0x14002ad5f  mov     r8d, 90h
0x14002ad65  lea     rdx, aAhcsdbquerycre; "AhcSdbQueryCreate"
0x14002ad6c  lea     ecx, [rax+1]
0x14002ad6f  call    AslLogCallPrintf
0x14002ad74  mov     ebx, 0C0000017h
0x14002ad79  jmp     short loc_14002ADCD
0x14002ad7b  mov     r9, rdi; RegHandle
0x14002ad7e  lea     rcx, MS_Windows_AeCache_Provider; ProviderId
0x14002ad85  xor     r8d, r8d; CallbackContext
0x14002ad88  xor     edx, edx; EnableCallback
0x14002ad8a  call    cs:__imp_EtwRegister
0x14002ad91  nop     dword ptr [rax+rax+00h]
0x14002ad96  mov     ebx, eax
0x14002ad98  test    eax, eax
0x14002ad9a  jns     short loc_14002ADC8
0x14002ad9c  lea     r9, aFailedToRegist; "Failed to register event provider [%x]"
0x14002ada3  mov     [rsp+38h+var_18], eax
0x14002ada7  mov     r8d, 9Fh
0x14002adad  lea     rdx, aAhcsdbquerycre; "AhcSdbQueryCreate"
0x14002adb4  mov     ecx, 1
0x14002adb9  call    AslLogCallPrintf
0x14002adbe  mov     rcx, rdi
0x14002adc1  call    AhcSdbQueryDelete
0x14002adc6  jmp     short loc_14002ADCD
0x14002adc8  mov     [rsi], rdi
0x14002adcb  xor     ebx, ebx
0x14002adcd  mov     rsi, [rsp+38h+arg_8]
0x14002add2  mov     eax, ebx
0x14002add4  mov     rbx, [rsp+38h+arg_0]
0x14002add9  add     rsp, 30h
0x14002addd  pop     rdi
0x14002adde  retn
```
