# NoAnimationNeeded

- ea: `0x1801fd5a0`
- end: `0x1801fd5ed`
- name: `NoAnimationNeeded`
- size: `77`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800d0ee4`

## callees

- `0x1801fd5a0`

## import_xrefs

- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x1801fd5d9`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x1801fd5d9`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1801fd5c2`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1801fd5c2`

## pseudocode

```c
char NoAnimationNeeded()
{
  char v0; // bl
  __int128 pvParam; // [rsp+20h] [rbp-18h] BYREF

  pvParam = 0;
  LODWORD(pvParam) = 16;
  v0 = 1;
  if ( (!SystemParametersInfoW(0x42u, 0x10u, &pvParam, 0) || (BYTE4(pvParam) & 1) == 0) && !GetSystemMetrics(4096) )
    return 0;
  return v0;
}

```

## disassembly

```asm
0x1801fd5a0  push    rbx
0x1801fd5a2  sub     rsp, 30h
0x1801fd5a6  mov     edx, 10h; uiParam
0x1801fd5ab  lea     r8, [rsp+38h+pvParam]; pvParam
0x1801fd5b0  xorps   xmm0, xmm0
0x1801fd5b3  xor     r9d, r9d; fWinIni
0x1801fd5b6  movups  [rsp+38h+pvParam], xmm0
0x1801fd5bb  mov     dword ptr [rsp+38h+pvParam], edx
0x1801fd5bf  lea     ecx, [rdx+32h]; uiAction
0x1801fd5c2  call    cs:__imp_SystemParametersInfoW
0x1801fd5c8  mov     bl, 1
0x1801fd5ca  test    eax, eax
0x1801fd5cc  jz      short loc_1801FD5D4
0x1801fd5ce  test    byte ptr [rsp+38h+pvParam+4], bl
0x1801fd5d2  jnz     short loc_1801FD5E5
0x1801fd5d4  mov     ecx, 1000h; nIndex
0x1801fd5d9  call    cs:__imp_GetSystemMetrics
0x1801fd5df  test    eax, eax
0x1801fd5e1  jnz     short loc_1801FD5E5
0x1801fd5e3  xor     bl, bl
0x1801fd5e5  mov     al, bl
0x1801fd5e7  add     rsp, 30h
0x1801fd5eb  pop     rbx
0x1801fd5ec  retn
```
