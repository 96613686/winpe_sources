# VfsGetDeviceVolumeNameFromVolumeName

- ea: `0x140011438`
- end: `0x14001151a`
- name: `VfsGetDeviceVolumeNameFromVolumeName`
- size: `226`
- prototype: `__int64 __fastcall(PCUNICODE_STRING VolumeName)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000874c`

## callees

- `0x140011438`
- `0x14001171c`

## import_xrefs

- `ntoskrnl!RtlPrefixUnicodeString` at `0x14001146b`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14001146b`
- `ntoskrnl!ExAllocatePool2` at `0x14001148b`
- `ntoskrnl!ExAllocatePool2` at `0x14001148b`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400114b8`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400114b8`
- `FLTMGR!FltGetVolumeFromName` at `0x1400114d7`
- `FLTMGR!FltGetVolumeFromName` at `0x1400114d7`
- `FLTMGR!FltObjectDereference` at `0x1400114fb`
- `FLTMGR!FltObjectDereference` at `0x1400114fb`

## pseudocode

```c
NTSTATUS __fastcall VfsGetDeviceVolumeNameFromVolumeName(
        PCUNICODE_STRING VolumeName,
        __int64 a2,
        struct _UNICODE_STRING *a3)
{
  unsigned __int16 Length; // di
  __int64 Pool2; // rax
  int v7; // edi
  NTSTATUS result; // eax
  int v9; // ebx
  PFLT_VOLUME RetVolume; // [rsp+40h] [rbp+18h] BYREF

  a3->Buffer = 0;
  RetVolume = 0;
  if ( RtlPrefixUnicodeString(&String1, VolumeName, 1u) )
  {
    Length = VolumeName->Length;
    Pool2 = ExAllocatePool2(256, VolumeName->Length, 1851147862);
    a3->Buffer = (wchar_t *)Pool2;
    if ( !Pool2 )
      return -1073741670;
    a3->MaximumLength = Length;
    v7 = 0;
    a3->Length = 0;
    RtlCopyUnicodeString(a3, VolumeName);
    return v7;
  }
  else
  {
    result = FltGetVolumeFromName(VfsData, VolumeName, &RetVolume);
    if ( result >= 0 )
    {
      v9 = VfsGetVolumeName(RetVolume, a3);
      FltObjectDereference(RetVolume);
      return v9;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140011438  mov     [rsp+arg_0], rbx
0x14001143d  mov     [rsp+arg_8], rsi
0x140011442  push    rdi
0x140011443  sub     rsp, 20h
0x140011447  mov     rbx, r8
0x14001144a  mov     qword ptr [r8+8], 0
0x140011452  mov     rsi, rcx
0x140011455  mov     [rsp+28h+RetVolume], 0
0x14001145e  mov     rdx, rcx; String2
0x140011461  mov     r8b, 1; CaseInSensitive
0x140011464  lea     rcx, String1; String1
0x14001146b  call    cs:__imp_RtlPrefixUnicodeString
0x140011472  nop     dword ptr [rax+rax+00h]
0x140011477  test    al, al
0x140011479  jz      short loc_1400114C8
0x14001147b  movzx   edi, word ptr [rsi]
0x14001147e  mov     ecx, 100h
0x140011483  mov     edx, edi
0x140011485  mov     r8d, 6E564656h
0x14001148b  call    cs:__imp_ExAllocatePool2
0x140011492  nop     dword ptr [rax+rax+00h]
0x140011497  mov     [rbx+8], rax
0x14001149b  test    rax, rax
0x14001149e  jnz     short loc_1400114A7
0x1400114a0  mov     edi, 0C000009Ah
0x1400114a5  jmp     short loc_1400114C4
0x1400114a7  xor     eax, eax
0x1400114a9  mov     [rbx+2], di
0x1400114ad  xor     edi, edi
0x1400114af  mov     [rbx], ax
0x1400114b2  mov     rdx, rsi; SourceString
0x1400114b5  mov     rcx, rbx; DestinationString
0x1400114b8  call    cs:__imp_RtlCopyUnicodeString
0x1400114bf  nop     dword ptr [rax+rax+00h]
0x1400114c4  mov     eax, edi
0x1400114c6  jmp     short loc_140011509
0x1400114c8  mov     rcx, cs:VfsData; Filter
0x1400114cf  lea     r8, [rsp+28h+RetVolume]; RetVolume
0x1400114d4  mov     rdx, rsi; VolumeName
0x1400114d7  call    cs:__imp_FltGetVolumeFromName
0x1400114de  nop     dword ptr [rax+rax+00h]
0x1400114e3  test    eax, eax
0x1400114e5  js      short loc_140011509
0x1400114e7  mov     rcx, [rsp+28h+RetVolume]; Volume
0x1400114ec  mov     rdx, rbx; VolumeName
0x1400114ef  call    VfsGetVolumeName
0x1400114f4  mov     rcx, [rsp+28h+RetVolume]; FltObject
0x1400114f9  mov     ebx, eax
0x1400114fb  call    cs:__imp_FltObjectDereference
0x140011502  nop     dword ptr [rax+rax+00h]
0x140011507  mov     eax, ebx
0x140011509  mov     rbx, [rsp+28h+arg_0]
0x14001150e  mov     rsi, [rsp+28h+arg_8]
0x140011513  add     rsp, 20h
0x140011517  pop     rdi
0x140011518  retn
```
