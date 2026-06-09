# AiRegReadBinaryValue

- ea: `0x140003198`
- end: `0x1400032b4`
- name: `AiRegReadBinaryValue`
- size: `284`
- prototype: `__int64 __fastcall(void *, struct _UNICODE_STRING *, __int64, _DWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140028f80`

## callees

- `0x140003198`
- `0x140006c40`
- `0x1400328b0`
- `0x140032a50`
- `0x1400331a0`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x14000321d`
- `ntoskrnl!ZwQueryValueKey` at `0x14000321d`
- `ntoskrnl!ZwClose` at `0x14000329b`
- `ntoskrnl!ZwClose` at `0x14000329b`

## pseudocode

```c
__int64 __fastcall AiRegReadBinaryValue(void *a1, struct _UNICODE_STRING *a2, __int64 a3, _DWORD *a4, _QWORD *a5)
{
  _DWORD *v6; // rdi
  NTSTATUS v7; // ebx
  ULONG Length; // ebx
  NTSTATUS v9; // eax
  void *v10; // rax
  void *v11; // rsi
  HANDLE KeyHandle; // [rsp+30h] [rbp-38h] BYREF
  ULONG ResultLength; // [rsp+80h] [rbp+18h] BYREF
  int v15; // [rsp+84h] [rbp+1Ch]

  v15 = HIDWORD(a3);
  KeyHandle = 0;
  ResultLength = 2064;
  v6 = 0;
  v7 = AiRegOpenKey(a1, a2, 0x20019u, &KeyHandle);
  if ( v7 >= 0 )
  {
    while ( 1 )
    {
      Length = ResultLength;
      AiFree(v6);
      v6 = (_DWORD *)AiAlloc(Length);
      if ( !v6 )
        break;
      v9 = ZwQueryValueKey(
             KeyHandle,
             (PUNICODE_STRING)&ValueName,
             KeyValuePartialInformation,
             v6,
             Length,
             &ResultLength);
      v7 = v9;
      if ( v9 != -2147483643 )
      {
        if ( v9 < 0 )
          goto LABEL_12;
        if ( v6[1] != 3 )
        {
          v7 = -1073741788;
          goto LABEL_12;
        }
        if ( !v6[2] )
        {
          v7 = -1073741275;
          goto LABEL_12;
        }
        v10 = (void *)AiAlloc((unsigned int)v6[2]);
        v11 = v10;
        if ( v10 )
        {
          memmove(v10, v6 + 3, (unsigned int)v6[2]);
          *a5 = v11;
          *a4 = v6[2];
          goto LABEL_12;
        }
        break;
      }
    }
    v7 = -1073741801;
  }
LABEL_12:
  AiFree(v6);
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140003198  mov     rax, rsp
0x14000319b  mov     [rax+18h], r8
0x14000319f  push    rbx
0x1400031a0  push    rsi
0x1400031a1  push    rdi
0x1400031a2  push    r14
0x1400031a4  sub     rsp, 48h
0x1400031a8  mov     r14, r9
0x1400031ab  mov     qword ptr [rax-38h], 0
0x1400031b3  lea     r9, [rax-38h]
0x1400031b7  mov     dword ptr [rax+18h], 810h
0x1400031be  mov     r8d, 20019h
0x1400031c4  xor     edi, edi
0x1400031c6  call    AiRegOpenKey
0x1400031cb  mov     ebx, eax
0x1400031cd  test    eax, eax
0x1400031cf  js      loc_140003289
0x1400031d5  mov     ebx, [rsp+68h+arg_10]
0x1400031dc  mov     rcx, rdi
0x1400031df  call    AiFree
0x1400031e4  mov     ecx, ebx
0x1400031e6  call    AiAlloc
0x1400031eb  mov     rdi, rax
0x1400031ee  test    rax, rax
0x1400031f1  jz      loc_140003284
0x1400031f7  mov     rcx, [rsp+68h+KeyHandle]; KeyHandle
0x1400031fc  lea     rax, [rsp+68h+arg_10]
0x140003204  mov     [rsp+68h+ResultLength], rax; ResultLength
0x140003209  lea     rdx, ValueName; ValueName
0x140003210  mov     r9, rdi; KeyValueInformation
0x140003213  mov     [rsp+68h+Length], ebx; Length
0x140003217  mov     r8d, 2; KeyValueInformationClass
0x14000321d  call    cs:__imp_ZwQueryValueKey
0x140003224  nop     dword ptr [rax+rax+00h]
0x140003229  mov     ebx, eax
0x14000322b  cmp     eax, 80000005h
0x140003230  jz      short loc_1400031D5
0x140003232  test    eax, eax
0x140003234  js      short loc_140003289
0x140003236  cmp     dword ptr [rdi+4], 3
0x14000323a  jz      short loc_140003243
0x14000323c  mov     ebx, 0C0000024h
0x140003241  jmp     short loc_140003289
0x140003243  mov     eax, [rdi+8]
0x140003246  test    eax, eax
0x140003248  jnz     short loc_140003251
0x14000324a  mov     ebx, 0C0000225h
0x14000324f  jmp     short loc_140003289
0x140003251  mov     rcx, rax
0x140003254  call    AiAlloc
0x140003259  mov     rsi, rax
0x14000325c  test    rax, rax
0x14000325f  jz      short loc_140003284
0x140003261  mov     r8d, [rdi+8]; Size
0x140003265  lea     rdx, [rdi+0Ch]; Src
0x140003269  mov     rcx, rax; void *
0x14000326c  call    memmove
0x140003271  mov     rax, [rsp+68h+arg_20]
0x140003279  mov     [rax], rsi
0x14000327c  mov     eax, [rdi+8]
0x14000327f  mov     [r14], eax
0x140003282  jmp     short loc_140003289
0x140003284  mov     ebx, 0C0000017h
0x140003289  mov     rcx, rdi
0x14000328c  call    AiFree
0x140003291  mov     rcx, [rsp+68h+KeyHandle]; Handle
0x140003296  test    rcx, rcx
0x140003299  jz      short loc_1400032A7
0x14000329b  call    cs:__imp_ZwClose
0x1400032a2  nop     dword ptr [rax+rax+00h]
0x1400032a7  mov     eax, ebx
0x1400032a9  add     rsp, 48h
0x1400032ad  pop     r14
0x1400032af  pop     rdi
0x1400032b0  pop     rsi
0x1400032b1  pop     rbx
0x1400032b2  retn
```
