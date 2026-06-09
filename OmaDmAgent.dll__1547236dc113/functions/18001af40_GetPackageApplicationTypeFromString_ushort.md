# GetPackageApplicationTypeFromString(ushort *)

- ea: `0x18001af40`
- end: `0x18001afab`
- name: `?GetPackageApplicationTypeFromString@@YA?AW4PackageApplicationType@@PEAG@Z`
- size: `107`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001ab3c`

## callees

- `0x18001af40`
- `0x18001f3f2`

## string_xrefs

- `0x18001af6c`: `WebLink`

## pseudocode

```c
__int64 __fastcall GetPackageApplicationTypeFromString(const wchar_t *a1)
{
  if ( !wcsncmp_0(a1, L"Application", 0xBu) )
    return 1;
  if ( !wcsncmp_0(a1, L"WebLink", 7u) )
    return 2;
  return wcsncmp_0(a1, L"Remote", 6u) == 0 ? 3 : 0;
}

```

## disassembly

```asm
0x18001af40  push    rbx
0x18001af42  sub     rsp, 20h
0x18001af46  mov     r8d, 0Bh; MaxCount
0x18001af4c  lea     rdx, aApplication; "Application"
0x18001af53  mov     rbx, rcx
0x18001af56  call    wcsncmp_0
0x18001af5b  test    eax, eax
0x18001af5d  jnz     short loc_18001AF66
0x18001af5f  mov     eax, 1
0x18001af64  jmp     short loc_18001AFA4
0x18001af66  mov     r8d, 7; MaxCount
0x18001af6c  lea     rdx, aWeblink; "WebLink"
0x18001af73  mov     rcx, rbx; String1
0x18001af76  call    wcsncmp_0
0x18001af7b  test    eax, eax
0x18001af7d  jnz     short loc_18001AF86
0x18001af7f  mov     eax, 2
0x18001af84  jmp     short loc_18001AFA4
0x18001af86  mov     r8d, 6; MaxCount
0x18001af8c  lea     rdx, aRemote; "Remote"
0x18001af93  mov     rcx, rbx; String1
0x18001af96  call    wcsncmp_0
0x18001af9b  neg     eax
0x18001af9d  sbb     eax, eax
0x18001af9f  not     eax
0x18001afa1  and     eax, 3
0x18001afa4  add     rsp, 20h
0x18001afa8  pop     rbx
0x18001afa9  retn
```
