# BfspCreateNtldrObject

- ea: `0x140005ae8`
- end: `0x140005b92`
- name: `BfspCreateNtldrObject`
- size: `170`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x140007cdc`

## callees

- `0x140005ae8`
- `0x1400069e0`
- `0x140008844`
- `0x140008c74`
- `0x14000e628`
- `0x140014ec8`

## string_xrefs

- `0x140005b33`: `Failed to copy NTLDR object data. Status = [%x]`

## pseudocode

```c
__int64 __fastcall BfspCreateNtldrObject(__int64 a1, __int64 a2)
{
  unsigned int BcdCopyFlags; // eax
  int v5; // eax
  int v6; // ebx
  unsigned int v8; // [rsp+40h] [rbp+18h] BYREF
  int v9; // [rsp+44h] [rbp+1Ch]

  v8 = 1;
  v9 = 271581190;
  BcdCopyFlags = BfspGetBcdCopyFlags((unsigned int)dword_14003F8FC);
  v5 = BcdCopyObjects(a1, &v8, BcdCopyFlags, a2);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v6 = BfspSetObjectDeviceAndPath(a1, a2, &GUID_WINDOWS_LEGACY_NTLDR, &GUID_WINDOWS_LEGACY_NTLDR);
    if ( v6 >= 0 )
      return (unsigned int)BfspSetObjectStringElements(a1, a2, &GUID_WINDOWS_LEGACY_NTLDR, &GUID_WINDOWS_LEGACY_NTLDR);
  }
  else
  {
    BfspLogMessage(4, L"Failed to copy NTLDR object data. Status = [%x]", (unsigned int)v5);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140005ae8  mov     rax, rsp
0x140005aeb  mov     [rax+8], rbx
0x140005aef  mov     [rax+10h], rsi
0x140005af3  push    rdi
0x140005af4  sub     rsp, 20h
0x140005af8  mov     rsi, rcx
0x140005afb  mov     dword ptr [rax+18h], 1
0x140005b02  mov     ecx, cs:dword_14003F8FC
0x140005b08  mov     rdi, rdx
0x140005b0b  mov     dword ptr [rax+1Ch], 10300006h
0x140005b12  call    BfspGetBcdCopyFlags
0x140005b17  mov     r8d, eax
0x140005b1a  lea     rdx, [rsp+28h+arg_10]
0x140005b1f  mov     r9, rdi
0x140005b22  mov     rcx, rsi
0x140005b25  call    BcdCopyObjects
0x140005b2a  mov     ebx, eax
0x140005b2c  test    eax, eax
0x140005b2e  jns     short loc_140005B46
0x140005b30  mov     r8d, eax
0x140005b33  lea     rdx, aFailedToCopyNt; "Failed to copy NTLDR object data. Statu"...
0x140005b3a  mov     ecx, 4
0x140005b3f  call    BfspLogMessage
0x140005b44  jmp     short loc_140005B80
0x140005b46  lea     r9, GUID_WINDOWS_LEGACY_NTLDR
0x140005b4d  mov     rdx, rdi
0x140005b50  lea     r8, GUID_WINDOWS_LEGACY_NTLDR
0x140005b57  mov     rcx, rsi
0x140005b5a  call    BfspSetObjectDeviceAndPath
0x140005b5f  mov     ebx, eax
0x140005b61  test    eax, eax
0x140005b63  js      short loc_140005B80
0x140005b65  lea     r9, GUID_WINDOWS_LEGACY_NTLDR
0x140005b6c  mov     rdx, rdi
0x140005b6f  lea     r8, GUID_WINDOWS_LEGACY_NTLDR
0x140005b76  mov     rcx, rsi
0x140005b79  call    BfspSetObjectStringElements
0x140005b7e  mov     ebx, eax
0x140005b80  mov     rsi, [rsp+28h+arg_8]
0x140005b85  mov     eax, ebx
0x140005b87  mov     rbx, [rsp+28h+arg_0]
0x140005b8c  add     rsp, 20h
0x140005b90  pop     rdi
0x140005b91  retn
```
