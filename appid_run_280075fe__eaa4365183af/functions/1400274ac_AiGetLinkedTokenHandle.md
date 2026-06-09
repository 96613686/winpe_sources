# AiGetLinkedTokenHandle

- ea: `0x1400274ac`
- end: `0x1400274fc`
- name: `AiGetLinkedTokenHandle`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140035250`

## callees

- `0x1400274ac`

## import_xrefs

- `ntoskrnl!ZwQueryInformationToken` at `0x1400274dd`
- `ntoskrnl!ZwQueryInformationToken` at `0x1400274dd`

## pseudocode

```c
NTSTATUS __fastcall AiGetLinkedTokenHandle(void *a1, _QWORD *a2)
{
  NTSTATUS result; // eax
  ULONG v4; // [rsp+50h] [rbp+18h] BYREF
  __int64 v5; // [rsp+58h] [rbp+20h] BYREF

  v4 = 0;
  v5 = 0;
  result = ZwQueryInformationToken(a1, TokenLinkedToken, &v5, 8u, &v4);
  if ( result >= 0 )
    *a2 = v5;
  return result;
}

```

## disassembly

```asm
0x1400274ac  mov     r11, rsp
0x1400274af  push    rbx
0x1400274b0  sub     rsp, 30h
0x1400274b4  mov     r9d, 8; TokenInformationLength
0x1400274ba  mov     [rsp+38h+arg_10], 0
0x1400274c2  mov     rbx, rdx
0x1400274c5  mov     qword ptr [r11+20h], 0
0x1400274cd  lea     rax, [r11+18h]
0x1400274d1  lea     r8, [r11+20h]; TokenInformation
0x1400274d5  mov     [r11-18h], rax
0x1400274d9  lea     edx, [r9+0Bh]; TokenInformationClass
0x1400274dd  call    cs:__imp_ZwQueryInformationToken
0x1400274e4  nop     dword ptr [rax+rax+00h]
0x1400274e9  test    eax, eax
0x1400274eb  js      short loc_1400274F5
0x1400274ed  mov     rcx, [rsp+38h+arg_18]
0x1400274f2  mov     [rbx], rcx
0x1400274f5  add     rsp, 30h
0x1400274f9  pop     rbx
0x1400274fa  retn
```
