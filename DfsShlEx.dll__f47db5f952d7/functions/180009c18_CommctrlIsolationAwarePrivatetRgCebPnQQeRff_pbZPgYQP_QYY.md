# CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY

- ea: `0x180009c18`
- end: `0x180009cda`
- name: `CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY`
- size: `194`
- prototype: `__int64 __fastcall(LPCSTR lpProcName)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009dd8`
- `0x180009eb4`

## callees

- `0x180006dfc`
- `0x1800081f0`
- `0x180009c18`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180009c81`
- `KERNEL32!GetProcAddress` at `0x180009c81`
- `KERNEL32!SetLastError` at `0x180009cc1`
- `KERNEL32!SetLastError` at `0x18000b0d0`
- `KERNEL32!SetLastError` at `0x180009cc1`
- `KERNEL32!SetLastError` at `0x18000b0d0`
- `KERNEL32!DeactivateActCtx` at `0x180009cb4`
- `KERNEL32!DeactivateActCtx` at `0x18000b0c3`
- `KERNEL32!DeactivateActCtx` at `0x180009cb4`
- `KERNEL32!DeactivateActCtx` at `0x18000b0c3`
- `KERNEL32!GetLastError` at `0x180009ca1`
- `KERNEL32!GetLastError` at `0x18000b0b1`
- `KERNEL32!GetLastError` at `0x180009ca1`
- `KERNEL32!GetLastError` at `0x18000b0b1`

## pseudocode

```c
FARPROC __fastcall CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY(LPCSTR lpProcName)
{
  FARPROC ProcAddress; // rbx
  int v3; // edi
  HMODULE v4; // rax
  DWORD LastError; // edi
  ULONG_PTR ulCookie; // [rsp+48h] [rbp+10h] BYREF

  ProcAddress = 0;
  v3 = 0;
  ulCookie = 0;
  if ( IsolationAwarePrivateT_SqbjaYRiRY || (v3 = IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie)) != 0 )
  {
    v4 = `CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY'::`2'::m;
    if ( `CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY'::`2'::m )
    {
LABEL_6:
      ProcAddress = GetProcAddress(v4, lpProcName);
      goto LABEL_7;
    }
    ProcAddress = 0;
    v4 = IsolationAwarePrivatezlybNQyVOeNelJ(L"Comctl32.dll");
    if ( v4 )
    {
      `CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY'::`2'::m = v4;
      goto LABEL_6;
    }
  }
LABEL_7:
  if ( !IsolationAwarePrivateT_SqbjaYRiRY && v3 )
  {
    if ( ProcAddress )
      LastError = 0;
    else
      LastError = GetLastError();
    DeactivateActCtx(0, ulCookie);
    if ( !ProcAddress )
      SetLastError(LastError);
  }
  return ProcAddress;
}

```

## disassembly

```asm
0x180009c18  mov     rax, rsp
0x180009c1b  mov     [rax+8], rbx
0x180009c1f  mov     [rax+18h], rsi
0x180009c23  push    rdi
0x180009c24  sub     rsp, 30h
0x180009c28  mov     rsi, rcx
0x180009c2b  xor     ebx, ebx
0x180009c2d  mov     [rax-10h], rbx
0x180009c31  xor     edi, edi
0x180009c33  mov     [rax-18h], edi
0x180009c36  mov     [rax+10h], rbx
0x180009c3a  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, edi
0x180009c40  jnz     short loc_180009C55
0x180009c42  lea     rcx, [rax+10h]; lpCookie
0x180009c46  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x180009c4b  mov     edi, eax
0x180009c4d  mov     [rsp+38h+var_18], eax
0x180009c51  test    eax, eax
0x180009c53  jz      short loc_180009C8F
0x180009c55  mov     rax, cs:?m@?1??CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY@@9@4UIsolationAwarePrivate_zHGnoyr_zBqHyr_vAsB@@A; IsolationAwarePrivate_zHGnoyr_zBqHyr_vAsB `CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY'::`2'::m
0x180009c5c  test    rax, rax
0x180009c5f  jnz     short loc_180009C7B
0x180009c61  xor     ebx, ebx
0x180009c63  mov     rcx, cs:off_18000DCF0; lpLibFileName
0x180009c6a  call    IsolationAwarePrivatezlybNQyVOeNelJ
0x180009c6f  test    rax, rax
0x180009c72  jz      short loc_180009C8A
0x180009c74  mov     cs:?m@?1??CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY@@9@4UIsolationAwarePrivate_zHGnoyr_zBqHyr_vAsB@@A, rax; IsolationAwarePrivate_zHGnoyr_zBqHyr_vAsB `CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY'::`2'::m
0x180009c7b  mov     rdx, rsi; lpProcName
0x180009c7e  mov     rcx, rax; hModule
0x180009c81  call    cs:__imp_GetProcAddress
0x180009c87  mov     rbx, rax
0x180009c8a  mov     [rsp+38h+var_10], rbx
0x180009c8f  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180009c96  jnz     short loc_180009CC7
0x180009c98  test    edi, edi
0x180009c9a  jz      short loc_180009CC7
0x180009c9c  test    rbx, rbx
0x180009c9f  jnz     short loc_180009CAB
0x180009ca1  call    cs:__imp_GetLastError
0x180009ca7  mov     edi, eax
0x180009ca9  jmp     short loc_180009CAD
0x180009cab  xor     edi, edi
0x180009cad  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x180009cb2  xor     ecx, ecx; dwFlags
0x180009cb4  call    cs:__imp_DeactivateActCtx
0x180009cba  test    rbx, rbx
0x180009cbd  jnz     short loc_180009CC7
0x180009cbf  mov     ecx, edi; dwErrCode
0x180009cc1  call    cs:__imp_SetLastError
0x180009cc7  mov     rax, rbx
0x180009cca  mov     rbx, [rsp+38h+arg_0]
0x180009ccf  mov     rsi, [rsp+38h+arg_10]
0x180009cd4  add     rsp, 30h
0x180009cd8  pop     rdi
0x180009cd9  retn
0x18000b08e  push    rbx
0x18000b090  push    rbp
0x18000b091  push    rdi
0x18000b092  sub     rsp, 20h
0x18000b096  mov     rbp, rdx
0x18000b099  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000b0a0  jnz     short loc_18000B0D7
0x18000b0a2  cmp     dword ptr [rbp+20h], 0
0x18000b0a6  jz      short loc_18000B0D7
0x18000b0a8  mov     rbx, [rbp+28h]
0x18000b0ac  test    rbx, rbx
0x18000b0af  jnz     short loc_18000B0BB
0x18000b0b1  call    cs:__imp_GetLastError
0x18000b0b7  mov     edi, eax
0x18000b0b9  jmp     short loc_18000B0BD
0x18000b0bb  xor     edi, edi
0x18000b0bd  mov     rdx, [rbp+48h]; ulCookie
0x18000b0c1  xor     ecx, ecx; dwFlags
0x18000b0c3  call    cs:__imp_DeactivateActCtx
0x18000b0c9  test    rbx, rbx
0x18000b0cc  jnz     short loc_18000B0D7
0x18000b0ce  mov     ecx, edi; dwErrCode
0x18000b0d0  call    cs:__imp_SetLastError
0x18000b0d6  nop
0x18000b0d7  add     rsp, 20h
0x18000b0db  pop     rdi
0x18000b0dc  pop     rbp
0x18000b0dd  pop     rbx
0x18000b0de  retn
```
