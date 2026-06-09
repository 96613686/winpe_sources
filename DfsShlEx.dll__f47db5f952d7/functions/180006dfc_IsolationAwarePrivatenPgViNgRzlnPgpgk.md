# IsolationAwarePrivatenPgViNgRzlnPgpgk

- ea: `0x180006dfc`
- end: `0x180006e82`
- name: `IsolationAwarePrivatenPgViNgRzlnPgpgk`
- size: `134`
- prototype: `__int64 __fastcall(ULONG_PTR *lpCookie)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x180006d3c`
- `0x180008120`
- `0x180008200`
- `0x180009c18`
- `0x180009ce0`
- `0x180009dd8`
- `0x180009eb4`
- `0x180009f9c`

## callees

- `0x180006dfc`
- `0x180006e88`

## import_xrefs

- `KERNEL32!ActivateActCtx` at `0x180006e42`
- `KERNEL32!ActivateActCtx` at `0x180006e42`
- `KERNEL32!OutputDebugStringA` at `0x180006e16`
- `KERNEL32!OutputDebugStringA` at `0x180006e16`
- `KERNEL32!GetLastError` at `0x180006e4c`
- `KERNEL32!GetLastError` at `0x180006e4c`

## pseudocode

```c
__int64 __fastcall IsolationAwarePrivatenPgViNgRzlnPgpgk(ULONG_PTR *lpCookie)
{
  int v1; // eax
  DWORD LastError; // eax
  DWORD v4; // edx
  __int64 result; // rax

  v1 = WinbaseIsolationAwarePrivateT_SpYRNahcpNYYRQ;
  if ( WinbaseIsolationAwarePrivateT_SpYRNahcpNYYRQ )
  {
    OutputDebugStringA("IsolationAware function called after IsolationAwareCleanup\n");
    v1 = WinbaseIsolationAwarePrivateT_SpYRNahcpNYYRQ;
  }
  if ( IsolationAwarePrivateT_SqbjaYRiRY
    || (v1 || (unsigned int)WinbaseIsolationAwarePrivatetRgzlnPgpgk())
    && ActivateActCtx(WinbaseIsolationAwarePrivateT_UnPgpgk, lpCookie) )
  {
    return 1;
  }
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError - 126 <= 1 || LastError == 120 || LastError == 1 || (result = 0, v4 == 50) )
  {
    IsolationAwarePrivateT_SqbjaYRiRY = 1;
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x180006dfc  push    rbx
0x180006dfe  sub     rsp, 20h
0x180006e02  mov     eax, cs:WinbaseIsolationAwarePrivateT_SpYRNahcpNYYRQ
0x180006e08  mov     rbx, rcx
0x180006e0b  test    eax, eax
0x180006e0d  jz      short loc_180006E22
0x180006e0f  lea     rcx, ?debugString@?4??IsolationAwarePrivatenPgViNgRzlnPgpgk@@9@4QBDB; "IsolationAware function called after Is"...
0x180006e16  call    cs:__imp_OutputDebugStringA
0x180006e1c  mov     eax, cs:WinbaseIsolationAwarePrivateT_SpYRNahcpNYYRQ
0x180006e22  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180006e29  jnz     short loc_180006E77
0x180006e2b  test    eax, eax
0x180006e2d  jnz     short loc_180006E38
0x180006e2f  call    WinbaseIsolationAwarePrivatetRgzlnPgpgk
0x180006e34  test    eax, eax
0x180006e36  jz      short loc_180006E4C
0x180006e38  mov     rcx, cs:WinbaseIsolationAwarePrivateT_UnPgpgk; hActCtx
0x180006e3f  mov     rdx, rbx; lpCookie
0x180006e42  call    cs:__imp_ActivateActCtx
0x180006e48  test    eax, eax
0x180006e4a  jnz     short loc_180006E77
0x180006e4c  call    cs:__imp_GetLastError
0x180006e52  mov     edx, eax
0x180006e54  lea     ecx, [rax-7Eh]
0x180006e57  cmp     ecx, 1
0x180006e5a  jbe     short loc_180006E6D
0x180006e5c  cmp     eax, 78h ; 'x'
0x180006e5f  jz      short loc_180006E6D
0x180006e61  cmp     eax, 1
0x180006e64  jz      short loc_180006E6D
0x180006e66  xor     eax, eax
0x180006e68  cmp     edx, 32h ; '2'
0x180006e6b  jnz     short loc_180006E7C
0x180006e6d  mov     cs:IsolationAwarePrivateT_SqbjaYRiRY, 1
0x180006e77  mov     eax, 1
0x180006e7c  add     rsp, 20h
0x180006e80  pop     rbx
0x180006e81  retn
```
