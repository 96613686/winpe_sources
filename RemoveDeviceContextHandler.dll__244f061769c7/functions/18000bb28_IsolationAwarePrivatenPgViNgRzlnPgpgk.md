# IsolationAwarePrivatenPgViNgRzlnPgpgk

- ea: `0x18000bb28`
- end: `0x18000bbae`
- name: `IsolationAwarePrivatenPgViNgRzlnPgpgk`
- size: `134`
- prototype: `__int64 __fastcall(ULONG_PTR *lpCookie)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b9a0`
- `0x18000ba68`
- `0x18000bbd0`
- `0x18000bcf4`

## callees

- `0x18000bb28`
- `0x18000bea8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bb78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bb78`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000bb42`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000bb42`
- `KERNEL32!ActivateActCtx` at `0x18000bb6e`
- `KERNEL32!ActivateActCtx` at `0x18000bb6e`

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
0x18000bb28  push    rbx
0x18000bb2a  sub     rsp, 20h
0x18000bb2e  mov     eax, cs:WinbaseIsolationAwarePrivateT_SpYRNahcpNYYRQ
0x18000bb34  mov     rbx, rcx
0x18000bb37  test    eax, eax
0x18000bb39  jz      short loc_18000BB4E
0x18000bb3b  lea     rcx, ?debugString@?4??IsolationAwarePrivatenPgViNgRzlnPgpgk@@9@4QBDB; "IsolationAware function called after Is"...
0x18000bb42  call    cs:__imp_OutputDebugStringA
0x18000bb48  mov     eax, cs:WinbaseIsolationAwarePrivateT_SpYRNahcpNYYRQ
0x18000bb4e  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000bb55  jnz     short loc_18000BBA3
0x18000bb57  test    eax, eax
0x18000bb59  jnz     short loc_18000BB64
0x18000bb5b  call    WinbaseIsolationAwarePrivatetRgzlnPgpgk
0x18000bb60  test    eax, eax
0x18000bb62  jz      short loc_18000BB78
0x18000bb64  mov     rcx, cs:WinbaseIsolationAwarePrivateT_UnPgpgk; hActCtx
0x18000bb6b  mov     rdx, rbx; lpCookie
0x18000bb6e  call    cs:__imp_ActivateActCtx
0x18000bb74  test    eax, eax
0x18000bb76  jnz     short loc_18000BBA3
0x18000bb78  call    cs:__imp_GetLastError
0x18000bb7e  mov     edx, eax
0x18000bb80  lea     ecx, [rax-7Eh]
0x18000bb83  cmp     ecx, 1
0x18000bb86  jbe     short loc_18000BB99
0x18000bb88  cmp     eax, 78h ; 'x'
0x18000bb8b  jz      short loc_18000BB99
0x18000bb8d  cmp     eax, 1
0x18000bb90  jz      short loc_18000BB99
0x18000bb92  xor     eax, eax
0x18000bb94  cmp     edx, 32h ; '2'
0x18000bb97  jnz     short loc_18000BBA8
0x18000bb99  mov     cs:IsolationAwarePrivateT_SqbjaYRiRY, 1
0x18000bba3  mov     eax, 1
0x18000bba8  add     rsp, 20h
0x18000bbac  pop     rbx
0x18000bbad  retn
```
