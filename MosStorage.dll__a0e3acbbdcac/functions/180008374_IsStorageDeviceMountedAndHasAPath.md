# IsStorageDeviceMountedAndHasAPath

- ea: `0x180008374`
- end: `0x1800083d4`
- name: `IsStorageDeviceMountedAndHasAPath`
- size: `96`
- prototype: `char __fastcall(__int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800079d8`
- `0x180007c90`
- `0x180007ef8`

## callees

- `0x180001c80`
- `0x180008374`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1800083ad`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1800083ad`

## pseudocode

```c
char __fastcall IsStorageDeviceMountedAndHasAPath(__int64 a1)
{
  const WCHAR *v1; // rcx
  bool v2; // zf
  char result; // al
  WCHAR szVolumePathName[264]; // [rsp+20h] [rbp-228h] BYREF

  if ( *(_DWORD *)(a1 + 528) )
    return 0;
  v1 = (const WCHAR *)(a1 + 4);
  if ( !*v1 )
    return 0;
  v2 = !GetVolumePathNameW(v1, szVolumePathName, 0x104u);
  result = 1;
  if ( v2 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x180008374  push    rbx
0x180008376  sub     rsp, 240h
0x18000837d  mov     rax, cs:__security_cookie
0x180008384  xor     rax, rsp
0x180008387  mov     [rsp+248h+var_18], rax
0x18000838f  xor     ebx, ebx
0x180008391  cmp     [rcx+210h], ebx
0x180008397  jnz     short loc_1800083B9
0x180008399  add     rcx, 4; lpszFileName
0x18000839d  cmp     [rcx], bx
0x1800083a0  jz      short loc_1800083B9
0x1800083a2  mov     r8d, 104h; cchBufferLength
0x1800083a8  lea     rdx, [rsp+248h+szVolumePathName]; lpszVolumePathName
0x1800083ad  call    cs:__imp_GetVolumePathNameW
0x1800083b3  test    eax, eax
0x1800083b5  mov     al, 1
0x1800083b7  jnz     short loc_1800083BB
0x1800083b9  mov     al, bl
0x1800083bb  mov     rcx, [rsp+248h+var_18]
0x1800083c3  xor     rcx, rsp; StackCookie
0x1800083c6  call    __security_check_cookie
0x1800083cb  add     rsp, 240h
0x1800083d2  pop     rbx
0x1800083d3  retn
```
