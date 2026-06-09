# HttpRemoveUrlFromUrlGroup

- ea: `0x1800011f0`
- end: `0x180001233`
- name: `HttpRemoveUrlFromUrlGroup`
- size: `67`
- prototype: `ULONG __stdcall(HTTP_URL_GROUP_ID UrlGroupId, PCWSTR pFullyQualifiedUrl, ULONG Flags)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001010`

## callees

- `0x1800011f0`
- `0x180001240`

## pseudocode

```c
ULONG __stdcall HttpRemoveUrlFromUrlGroup(HTTP_URL_GROUP_ID UrlGroupId, PCWSTR pFullyQualifiedUrl, ULONG Flags)
{
  if ( (Flags & 0xFFFFFFFE) != 0 || (Flags & 1) != 0 && pFullyQualifiedUrl )
    return 87;
  else
    return RemoveUrlFromUrlGroup(g_CommunicationChannel, 1u, UrlGroupId, pFullyQualifiedUrl, Flags);
}

```

## disassembly

```asm
0x1800011f0  sub     rsp, 38h
0x1800011f4  test    r8d, 0FFFFFFFEh
0x1800011fb  jnz     short loc_180001229
0x1800011fd  test    r8b, 1
0x180001201  jz      short loc_180001208
0x180001203  test    rdx, rdx
0x180001206  jnz     short loc_180001229
0x180001208  mov     [rsp+38h+var_18], r8d; int
0x18000120d  mov     r9, rdx
0x180001210  mov     r8, rcx
0x180001213  mov     edx, 1
0x180001218  mov     rcx, cs:g_CommunicationChannel; FileHandle
0x18000121f  call    RemoveUrlFromUrlGroup
0x180001224  add     rsp, 38h
0x180001228  retn
0x180001229  mov     eax, 57h ; 'W'
0x18000122e  add     rsp, 38h
0x180001232  retn
```
