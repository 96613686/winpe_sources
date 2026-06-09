# pSetupOpenPredefinedKey

- ea: `0x180041418`
- end: `0x18004148f`
- name: `pSetupOpenPredefinedKey`
- size: `119`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180041318`

## callees

- `0x1800412c4`
- `0x1800413fc`
- `0x180041418`

## import_xrefs

- `ntdll!RtlFormatCurrentUserKeyPath` at `0x180041437`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x180041437`
- `ntdll!RtlFreeUnicodeString` at `0x180041472`
- `ntdll!RtlFreeUnicodeString` at `0x180041472`
- `ntdll!RtlNtStatusToDosError` at `0x180041443`
- `ntdll!RtlNtStatusToDosError` at `0x180041443`

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
0x180041418  push    rbx
0x18004141a  sub     rsp, 30h
0x18004141e  xorps   xmm0, xmm0
0x180041421  mov     rbx, rdx
0x180041424  movups  xmmword ptr [rsp+38h+KeyPath.Length], xmm0
0x180041429  cmp     rcx, 0FFFFFFFF80000001h
0x180041430  jnz     short loc_180041480
0x180041432  lea     rcx, [rsp+38h+KeyPath]; KeyPath
0x180041437  call    cs:__imp_RtlFormatCurrentUserKeyPath
0x18004143d  test    eax, eax
0x18004143f  jns     short loc_18004144B
0x180041441  mov     ecx, eax; Status
0x180041443  call    cs:__imp_RtlNtStatusToDosError
0x180041449  jmp     short loc_180041463
0x18004144b  mov     rax, [rsp+38h+KeyPath.Buffer]
0x180041450  mov     r9, rbx
0x180041453  mov     r8d, 2000000h
0x180041459  mov     rdx, rax
0x18004145c  xor     ecx, ecx
0x18004145e  call    pSetupOpenKeyEx
0x180041463  mov     ebx, eax
0x180041465  cmp     [rsp+38h+KeyPath.Buffer], 0
0x18004146b  jz      short loc_180041478
0x18004146d  lea     rcx, [rsp+38h+KeyPath]; UnicodeString
0x180041472  call    cs:__imp_RtlFreeUnicodeString
0x180041478  mov     eax, ebx
0x18004147a  add     rsp, 30h
0x18004147e  pop     rbx
0x18004147f  retn
0x180041480  call    pSetupGetPredefinedKeyPath
0x180041485  test    rax, rax
0x180041488  jnz     short loc_180041450
0x18004148a  lea     ebx, [rax+32h]
0x18004148d  jmp     short loc_180041465
```
