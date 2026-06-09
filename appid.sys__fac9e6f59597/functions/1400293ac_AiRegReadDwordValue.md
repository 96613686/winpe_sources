# AiRegReadDwordValue

- ea: `0x1400293ac`
- end: `0x140029485`
- name: `AiRegReadDwordValue`
- size: `217`
- prototype: `__int64 __fastcall(__int64, struct _UNICODE_STRING *, struct _UNICODE_STRING *, _DWORD *)`
- caller_count: `10`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14001fef0`
- `0x1400230a8`
- `0x140023e00`
- `0x140023ee8`
- `0x1400253ac`
- `0x14002bb30`
- `0x14002d1bc`
- `0x14002d390`
- `0x1400380c4`
- `0x140038c60`

## callees

- `0x1400293ac`
- `0x1400328b0`
- `0x140032a50`
- `0x1400331a0`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x140029423`
- `ntoskrnl!ZwQueryValueKey` at `0x140029423`
- `ntoskrnl!ZwClose` at `0x14002946d`
- `ntoskrnl!ZwClose` at `0x14002946d`

## pseudocode

```c
__int64 __fastcall AiRegReadDwordValue(__int64 a1, struct _UNICODE_STRING *a2, struct _UNICODE_STRING *a3, _DWORD *a4)
{
  _DWORD *v6; // rbx
  NTSTATUS v7; // edi
  ULONG Length; // edi
  NTSTATUS v9; // eax
  HANDLE KeyHandle; // [rsp+30h] [rbp-38h] BYREF
  ULONG ResultLength; // [rsp+70h] [rbp+8h] BYREF
  int v13; // [rsp+74h] [rbp+Ch]

  v13 = HIDWORD(a1);
  KeyHandle = 0;
  ResultLength = 48;
  v6 = 0;
  v7 = AiRegOpenKey(0, a2, 0x20019u, &KeyHandle);
  if ( v7 >= 0 )
  {
    do
    {
      Length = ResultLength;
      AiFree(v6);
      v6 = (_DWORD *)AiAlloc(Length);
      if ( !v6 )
      {
        v7 = -1073741801;
        goto LABEL_10;
      }
      v9 = ZwQueryValueKey(KeyHandle, a3, KeyValuePartialInformation, v6, Length, &ResultLength);
      v7 = v9;
    }
    while ( v9 == -2147483643 );
    if ( v9 >= 0 )
    {
      if ( v6[1] == 4 && v6[2] == 4 )
        *a4 = v6[3];
      else
        v7 = -1073741788;
    }
  }
LABEL_10:
  AiFree(v6);
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400293ac  mov     rax, rsp
0x1400293af  mov     [rax+8], rcx
0x1400293b3  push    rbx
0x1400293b4  push    rbp
0x1400293b5  push    rsi
0x1400293b6  push    rdi
0x1400293b7  sub     rsp, 48h
0x1400293bb  mov     rsi, r9
0x1400293be  mov     qword ptr [rax-38h], 0
0x1400293c6  mov     rbp, r8
0x1400293c9  mov     dword ptr [rax+8], 30h ; '0'
0x1400293d0  lea     r9, [rax-38h]
0x1400293d4  mov     r8d, 20019h
0x1400293da  xor     ecx, ecx
0x1400293dc  xor     ebx, ebx
0x1400293de  call    AiRegOpenKey
0x1400293e3  mov     edi, eax
0x1400293e5  test    eax, eax
0x1400293e7  js      short loc_14002945B
0x1400293e9  mov     edi, [rsp+68h+arg_0]
0x1400293ed  mov     rcx, rbx
0x1400293f0  call    AiFree
0x1400293f5  mov     ecx, edi
0x1400293f7  call    AiAlloc
0x1400293fc  mov     rbx, rax
0x1400293ff  test    rax, rax
0x140029402  jz      short loc_140029456
0x140029404  mov     rcx, [rsp+68h+KeyHandle]; KeyHandle
0x140029409  lea     rax, [rsp+68h+arg_0]
0x14002940e  mov     [rsp+68h+ResultLength], rax; ResultLength
0x140029413  mov     r9, rbx; KeyValueInformation
0x140029416  mov     r8d, 2; KeyValueInformationClass
0x14002941c  mov     [rsp+68h+Length], edi; Length
0x140029420  mov     rdx, rbp; ValueName
0x140029423  call    cs:__imp_ZwQueryValueKey
0x14002942a  nop     dword ptr [rax+rax+00h]
0x14002942f  mov     edi, eax
0x140029431  cmp     eax, 80000005h
0x140029436  jz      short loc_1400293E9
0x140029438  test    eax, eax
0x14002943a  js      short loc_14002945B
0x14002943c  cmp     dword ptr [rbx+4], 4
0x140029440  jnz     short loc_14002944F
0x140029442  cmp     dword ptr [rbx+8], 4
0x140029446  jnz     short loc_14002944F
0x140029448  mov     eax, [rbx+0Ch]
0x14002944b  mov     [rsi], eax
0x14002944d  jmp     short loc_14002945B
0x14002944f  mov     edi, 0C0000024h
0x140029454  jmp     short loc_14002945B
0x140029456  mov     edi, 0C0000017h
0x14002945b  mov     rcx, rbx
0x14002945e  call    AiFree
0x140029463  mov     rcx, [rsp+68h+KeyHandle]; Handle
0x140029468  test    rcx, rcx
0x14002946b  jz      short loc_140029479
0x14002946d  call    cs:__imp_ZwClose
0x140029474  nop     dword ptr [rax+rax+00h]
0x140029479  mov     eax, edi
0x14002947b  add     rsp, 48h
0x14002947f  pop     rdi
0x140029480  pop     rsi
0x140029481  pop     rbp
0x140029482  pop     rbx
0x140029483  retn
```
