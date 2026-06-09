# Template_qq

- ea: `0x180013d24`
- end: `0x180013d92`
- name: `Template_qq`
- size: `110`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800150e8`

## callees

- `0x180026e30`

## import_xrefs

- `ADVAPI32!EventWrite` at `0x180013d7a`
- `ADVAPI32!EventWrite` at `0x180013d7a`

## pseudocode

```c
ULONG __fastcall Template_qq(__int64 a1, __int64 a2, int a3, int a4)
{
  struct _EVENT_DATA_DESCRIPTOR v5; // [rsp+20h] [rbp-38h] BYREF
  int *v6; // [rsp+30h] [rbp-28h]
  int v7; // [rsp+38h] [rbp-20h]
  int v8; // [rsp+3Ch] [rbp-1Ch]
  int v9; // [rsp+70h] [rbp+18h] BYREF
  int v10; // [rsp+78h] [rbp+20h] BYREF

  v10 = a4;
  v9 = a3;
  v5.Ptr = (ULONGLONG)&v9;
  v5.Reserved = 0;
  v5.Size = 4;
  v6 = &v10;
  v8 = 0;
  v7 = 4;
  return EventWrite(0, &TraceMerge_NGEN_CreatingPDB_Stop, 2u, &v5);
}

```

## disassembly

```asm
0x180013d24  mov     r11, rsp
0x180013d27  mov     [r11+20h], r9d
0x180013d2b  mov     [r11+18h], r8d
0x180013d2f  sub     rsp, 58h
0x180013d33  mov     rax, cs:__security_cookie
0x180013d3a  xor     rax, rsp
0x180013d3d  mov     [rsp+58h+var_10], rax
0x180013d42  mov     ecx, 4
0x180013d47  lea     rax, [r11+18h]
0x180013d4b  mov     [r11-38h], rax
0x180013d4f  lea     r9, [r11-38h]; UserData
0x180013d53  and     [rsp+58h+var_2C], 0
0x180013d58  lea     rax, [r11+20h]
0x180013d5c  mov     [rsp+58h+var_30], ecx
0x180013d60  lea     rdx, TraceMerge_NGEN_CreatingPDB_Stop; EventDescriptor
0x180013d67  mov     [r11-28h], rax
0x180013d6b  lea     r8d, [rcx-2]; UserDataCount
0x180013d6f  and     [rsp+58h+var_1C], 0
0x180013d74  mov     [rsp+58h+var_20], ecx
0x180013d78  xor     ecx, ecx; RegHandle
0x180013d7a  call    cs:__imp_EventWrite
0x180013d80  mov     rcx, [rsp+58h+var_10]
0x180013d85  xor     rcx, rsp; StackCookie
0x180013d88  call    __security_check_cookie
0x180013d8d  add     rsp, 58h
0x180013d91  retn
```
