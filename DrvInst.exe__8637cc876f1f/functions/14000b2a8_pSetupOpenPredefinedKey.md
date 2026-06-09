# pSetupOpenPredefinedKey

- ea: `0x14000b2a8`
- end: `0x14000b31f`
- name: `pSetupOpenPredefinedKey`
- size: `119`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x14000b030`
- `0x14000b1a8`

## callees

- `0x14000b154`
- `0x14000b28c`
- `0x14000b2a8`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x14000b302`
- `ntdll!RtlFreeUnicodeString` at `0x14000b302`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x14000b2c7`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x14000b2c7`
- `ntdll!RtlNtStatusToDosError` at `0x14000b2d3`
- `ntdll!RtlNtStatusToDosError` at `0x14000b2d3`

## pseudocode

```c
__int64 __fastcall pSetupOpenPredefinedKey(__int64 a1, __int64 a2)
{
  int v3; // eax
  ULONG v4; // eax
  PWSTR Buffer; // rax
  unsigned int v6; // ebx
  struct _UNICODE_STRING KeyPath; // [rsp+20h] [rbp-18h] BYREF

  KeyPath = 0;
  if ( a1 == -2147483647 )
  {
    v3 = RtlFormatCurrentUserKeyPath(&KeyPath);
    if ( v3 < 0 )
    {
      v4 = RtlNtStatusToDosError(v3);
LABEL_6:
      v6 = v4;
      goto LABEL_7;
    }
    Buffer = KeyPath.Buffer;
LABEL_5:
    v4 = pSetupOpenKeyEx(0, Buffer, 0x2000000, a2);
    goto LABEL_6;
  }
  Buffer = (PWSTR)pSetupGetPredefinedKeyPath(a1);
  if ( Buffer )
    goto LABEL_5;
  v6 = 50;
LABEL_7:
  if ( KeyPath.Buffer )
    RtlFreeUnicodeString(&KeyPath);
  return v6;
}

```

## disassembly

```asm
0x14000b2a8  push    rbx
0x14000b2aa  sub     rsp, 30h
0x14000b2ae  xorps   xmm0, xmm0
0x14000b2b1  mov     rbx, rdx
0x14000b2b4  movups  xmmword ptr [rsp+38h+KeyPath.Length], xmm0
0x14000b2b9  cmp     rcx, 0FFFFFFFF80000001h
0x14000b2c0  jnz     short loc_14000B310
0x14000b2c2  lea     rcx, [rsp+38h+KeyPath]; KeyPath
0x14000b2c7  call    cs:__imp_RtlFormatCurrentUserKeyPath
0x14000b2cd  test    eax, eax
0x14000b2cf  jns     short loc_14000B2DB
0x14000b2d1  mov     ecx, eax; Status
0x14000b2d3  call    cs:__imp_RtlNtStatusToDosError
0x14000b2d9  jmp     short loc_14000B2F3
0x14000b2db  mov     rax, [rsp+38h+KeyPath.Buffer]
0x14000b2e0  mov     r9, rbx
0x14000b2e3  mov     r8d, 2000000h
0x14000b2e9  mov     rdx, rax
0x14000b2ec  xor     ecx, ecx
0x14000b2ee  call    pSetupOpenKeyEx
0x14000b2f3  mov     ebx, eax
0x14000b2f5  cmp     [rsp+38h+KeyPath.Buffer], 0
0x14000b2fb  jz      short loc_14000B308
0x14000b2fd  lea     rcx, [rsp+38h+KeyPath]; UnicodeString
0x14000b302  call    cs:__imp_RtlFreeUnicodeString
0x14000b308  mov     eax, ebx
0x14000b30a  add     rsp, 30h
0x14000b30e  pop     rbx
0x14000b30f  retn
0x14000b310  call    pSetupGetPredefinedKeyPath
0x14000b315  test    rax, rax
0x14000b318  jnz     short loc_14000B2E0
0x14000b31a  lea     ebx, [rax+32h]
0x14000b31d  jmp     short loc_14000B2F5
```
