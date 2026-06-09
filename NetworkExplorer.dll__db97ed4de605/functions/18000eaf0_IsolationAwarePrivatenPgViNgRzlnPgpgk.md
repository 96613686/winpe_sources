# IsolationAwarePrivatenPgViNgRzlnPgpgk

- ea: `0x18000eaf0`
- end: `0x18000eb76`
- name: `IsolationAwarePrivatenPgViNgRzlnPgpgk`
- size: `134`
- prototype: `__int64 __fastcall(ULONG_PTR *lpCookie)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e604`
- `0x18000e6cc`
- `0x18000e790`
- `0x18000e87c`
- `0x18000e948`
- `0x18000ea20`

## callees

- `0x18000eaf0`
- `0x18000eb90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eb40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eb40`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000eb0a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000eb0a`
- `KERNEL32!ActivateActCtx` at `0x18000eb36`
- `KERNEL32!ActivateActCtx` at `0x18000eb36`

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
  if ( LastError == 120 || LastError == 1 || LastError - 126 <= 1 || (result = 0, v4 == 50) )
  {
    IsolationAwarePrivateT_SqbjaYRiRY = 1;
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x18000eaf0  push    rbx
0x18000eaf2  sub     rsp, 20h
0x18000eaf6  mov     eax, cs:WinbaseIsolationAwarePrivateT_SpYRNahcpNYYRQ
0x18000eafc  mov     rbx, rcx
0x18000eaff  test    eax, eax
0x18000eb01  jz      short loc_18000EB16
0x18000eb03  lea     rcx, ?debugString@?4??IsolationAwarePrivatenPgViNgRzlnPgpgk@@9@4QBDB; "IsolationAware function called after Is"...
0x18000eb0a  call    cs:__imp_OutputDebugStringA
0x18000eb10  mov     eax, cs:WinbaseIsolationAwarePrivateT_SpYRNahcpNYYRQ
0x18000eb16  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000eb1d  jnz     short loc_18000EB6B
0x18000eb1f  test    eax, eax
0x18000eb21  jnz     short loc_18000EB2C
0x18000eb23  call    WinbaseIsolationAwarePrivatetRgzlnPgpgk
0x18000eb28  test    eax, eax
0x18000eb2a  jz      short loc_18000EB40
0x18000eb2c  mov     rcx, cs:WinbaseIsolationAwarePrivateT_UnPgpgk; hActCtx
0x18000eb33  mov     rdx, rbx; lpCookie
0x18000eb36  call    cs:__imp_ActivateActCtx
0x18000eb3c  test    eax, eax
0x18000eb3e  jnz     short loc_18000EB6B
0x18000eb40  call    cs:__imp_GetLastError
0x18000eb46  mov     edx, eax
0x18000eb48  cmp     eax, 78h ; 'x'
0x18000eb4b  jz      short loc_18000EB61
0x18000eb4d  cmp     eax, 1
0x18000eb50  jz      short loc_18000EB61
0x18000eb52  lea     ecx, [rax-7Eh]
0x18000eb55  cmp     ecx, 1
0x18000eb58  jbe     short loc_18000EB61
0x18000eb5a  xor     eax, eax
0x18000eb5c  cmp     edx, 32h ; '2'
0x18000eb5f  jnz     short loc_18000EB70
0x18000eb61  mov     cs:IsolationAwarePrivateT_SqbjaYRiRY, 1
0x18000eb6b  mov     eax, 1
0x18000eb70  add     rsp, 20h
0x18000eb74  pop     rbx
0x18000eb75  retn
```
