# AiLicReadIntegerValue

- ea: `0x140008f14`
- end: `0x140008f6d`
- name: `AiLicReadIntegerValue`
- size: `89`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14000775c`

## callees

- `0x140008f14`

## import_xrefs

- `ntdll!NtQueryLicenseValue` at `0x140008f4b`
- `ntdll!NtQueryLicenseValue` at `0x140008f4b`

## pseudocode

```c
__int64 __fastcall AiLicReadIntegerValue(__int64 a1, __int64 a2)
{
  __int64 result; // rax
  int v3; // [rsp+40h] [rbp+8h] BYREF
  int v4; // [rsp+44h] [rbp+Ch]
  int v5; // [rsp+50h] [rbp+18h] BYREF

  v4 = HIDWORD(a1);
  v3 = 0;
  v5 = 4;
  result = NtQueryLicenseValue(&qword_140017540, &v3, a2, 4, &v5);
  if ( (int)result >= 0 && (v3 != 4 || v5 != 4) )
    return 3221225473LL;
  return result;
}

```

## disassembly

```asm
0x140008f14  mov     rax, rsp
0x140008f17  mov     [rax+8], rcx
0x140008f1b  sub     rsp, 38h
0x140008f1f  mov     dword ptr [rax+8], 0
0x140008f26  mov     r8, rdx
0x140008f29  mov     dword ptr [rax+18h], 4
0x140008f30  lea     rax, [rax+18h]
0x140008f34  mov     r9d, 4
0x140008f3a  mov     [rsp+38h+var_18], rax
0x140008f3f  lea     rdx, [rsp+38h+arg_0]
0x140008f44  lea     rcx, qword_140017540
0x140008f4b  call    cs:__imp_NtQueryLicenseValue
0x140008f51  test    eax, eax
0x140008f53  js      short loc_140008F68
0x140008f55  cmp     [rsp+38h+arg_0], 4
0x140008f5a  jnz     short loc_140008F63
0x140008f5c  cmp     [rsp+38h+arg_10], 4
0x140008f61  jz      short loc_140008F68
0x140008f63  mov     eax, 0C0000001h
0x140008f68  add     rsp, 38h
0x140008f6c  retn
```
