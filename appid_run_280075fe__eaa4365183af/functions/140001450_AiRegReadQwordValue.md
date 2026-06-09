# AiRegReadQwordValue

- ea: `0x140001450`
- end: `0x140001540`
- name: `AiRegReadQwordValue`
- size: `240`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140028f80`
- `0x140030ff0`
- `0x140033130`
- `0x140035460`
- `0x140035580`

## callees

- `0x140001450`
- `0x1400328b0`
- `0x140032a50`
- `0x1400331a0`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x1400014ea`
- `ntoskrnl!ZwQueryValueKey` at `0x1400014ea`
- `ntoskrnl!ZwClose` at `0x14000152f`
- `ntoskrnl!ZwClose` at `0x14000152f`

## pseudocode

```c
__int64 __fastcall AiRegReadQwordValue(void *a1, struct _UNICODE_STRING *a2, struct _UNICODE_STRING *a3, _QWORD *a4)
{
  __int64 v6; // rdi
  NTSTATUS v7; // ebx
  ULONG Length; // ebx
  NTSTATUS v10; // eax
  ULONG ResultLength; // [rsp+30h] [rbp-38h] BYREF
  HANDLE KeyHandle; // [rsp+38h] [rbp-30h] BYREF

  KeyHandle = 0;
  ResultLength = 48;
  v6 = 0;
  v7 = AiRegOpenKey(a1, a2, 0x20019u, &KeyHandle);
  if ( v7 >= 0 )
  {
    do
    {
      Length = ResultLength;
      AiFree(v6);
      v6 = AiAlloc(Length);
      if ( !v6 )
      {
        v7 = -1073741801;
        goto LABEL_2;
      }
      v10 = ZwQueryValueKey(KeyHandle, a3, KeyValuePartialInformation, (PVOID)v6, Length, &ResultLength);
      v7 = v10;
    }
    while ( v10 == -2147483643 );
    if ( v10 >= 0 )
    {
      if ( *(_DWORD *)(v6 + 4) == 11 && *(_DWORD *)(v6 + 8) == 8 )
        *a4 = *(_QWORD *)(v6 + 12);
      else
        v7 = -1073741788;
    }
  }
LABEL_2:
  AiFree(v6);
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140001450  push    rbx
0x140001452  push    rsi
0x140001453  push    rdi
0x140001454  push    r14
0x140001456  sub     rsp, 48h
0x14000145a  mov     r14, r9
0x14000145d  mov     [rsp+68h+KeyHandle], 0
0x140001466  mov     rsi, r8
0x140001469  mov     [rsp+68h+var_38], 30h ; '0'
0x140001471  lea     r9, [rsp+68h+KeyHandle]
0x140001476  mov     r8d, 20019h
0x14000147c  xor     edi, edi
0x14000147e  call    AiRegOpenKey
0x140001483  mov     ebx, eax
0x140001485  test    eax, eax
0x140001487  jns     short loc_1400014B0
0x140001489  mov     rcx, rdi
0x14000148c  call    AiFree
0x140001491  mov     rcx, [rsp+68h+KeyHandle]; Handle
0x140001496  test    rcx, rcx
0x140001499  jnz     loc_14000152F
0x14000149f  mov     eax, ebx
0x1400014a1  add     rsp, 48h
0x1400014a5  pop     r14
0x1400014a7  pop     rdi
0x1400014a8  pop     rsi
0x1400014a9  pop     rbx
0x1400014aa  retn
0x1400014b0  mov     ebx, [rsp+68h+var_38]
0x1400014b4  mov     rcx, rdi
0x1400014b7  call    AiFree
0x1400014bc  mov     ecx, ebx
0x1400014be  call    AiAlloc
0x1400014c3  mov     rdi, rax
0x1400014c6  test    rax, rax
0x1400014c9  jz      short loc_140001519
0x1400014cb  mov     rcx, [rsp+68h+KeyHandle]; KeyHandle
0x1400014d0  lea     rax, [rsp+68h+var_38]
0x1400014d5  mov     [rsp+68h+ResultLength], rax; ResultLength
0x1400014da  mov     r9, rdi; KeyValueInformation
0x1400014dd  mov     r8d, 2; KeyValueInformationClass
0x1400014e3  mov     [rsp+68h+Length], ebx; Length
0x1400014e7  mov     rdx, rsi; ValueName
0x1400014ea  call    cs:__imp_ZwQueryValueKey
0x1400014f1  nop     dword ptr [rax+rax+00h]
0x1400014f6  mov     ebx, eax
0x1400014f8  cmp     eax, 80000005h
0x1400014fd  jz      short loc_1400014B0
0x1400014ff  test    eax, eax
0x140001501  js      short loc_140001489
0x140001503  cmp     dword ptr [rdi+4], 0Bh
0x140001507  jnz     short loc_14000150F
0x140001509  cmp     dword ptr [rdi+8], 8
0x14000150d  jz      short loc_140001523
0x14000150f  mov     ebx, 0C0000024h
0x140001514  jmp     loc_140001489
0x140001519  mov     ebx, 0C0000017h
0x14000151e  jmp     loc_140001489
0x140001523  mov     rax, [rdi+0Ch]
0x140001527  mov     [r14], rax
0x14000152a  jmp     loc_140001489
0x14000152f  call    cs:__imp_ZwClose
0x140001536  nop     dword ptr [rax+rax+00h]
0x14000153b  jmp     loc_14000149F
```
