# PrshtIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY

- ea: `0x180008200`
- end: `0x1800082c2`
- name: `PrshtIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY`
- size: `194`
- prototype: `__int64 __fastcall(LPCSTR lpProcName)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008120`
- `0x180009ce0`

## callees

- `0x180006dfc`
- `0x1800081f0`
- `0x180008200`
- `0x180009c18`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180008269`
- `KERNEL32!GetProcAddress` at `0x180008269`
- `KERNEL32!SetLastError` at `0x1800082a9`
- `KERNEL32!SetLastError` at `0x1800082a9`
- `KERNEL32!DeactivateActCtx` at `0x18000829c`
- `KERNEL32!DeactivateActCtx` at `0x18000829c`
- `KERNEL32!GetLastError` at `0x180008289`
- `KERNEL32!GetLastError` at `0x180008289`

## pseudocode

```c
FARPROC __fastcall PrshtIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY(LPCSTR lpProcName)
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
    v4 = `PrshtIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY'::`2'::m;
    if ( `PrshtIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY'::`2'::m )
    {
LABEL_6:
      ProcAddress = GetProcAddress(v4, lpProcName);
      goto LABEL_7;
    }
    ProcAddress = 0;
    v4 = IsolationAwarePrivatezlybNQyVOeNelJ(L"Comctl32.dll");
    if ( v4 )
    {
      `PrshtIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY'::`2'::m = v4;
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
0x180008200  mov     rax, rsp
0x180008203  mov     [rax+8], rbx
0x180008207  mov     [rax+18h], rsi
0x18000820b  push    rdi
0x18000820c  sub     rsp, 30h
0x180008210  mov     rsi, rcx
0x180008213  xor     ebx, ebx
0x180008215  mov     [rax-10h], rbx
0x180008219  xor     edi, edi
0x18000821b  mov     [rax-18h], edi
0x18000821e  mov     [rax+10h], rbx
0x180008222  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, edi
0x180008228  jnz     short loc_18000823D
0x18000822a  lea     rcx, [rax+10h]; lpCookie
0x18000822e  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x180008233  mov     edi, eax
0x180008235  mov     [rsp+38h+var_18], eax
0x180008239  test    eax, eax
0x18000823b  jz      short loc_180008277
0x18000823d  mov     rax, cs:?m@?1??PrshtIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY@@9@4UIsolationAwarePrivate_zHGnoyr_zBqHyr_vAsB@@A; IsolationAwarePrivate_zHGnoyr_zBqHyr_vAsB `PrshtIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY'::`2'::m
0x180008244  test    rax, rax
0x180008247  jnz     short loc_180008263
0x180008249  xor     ebx, ebx
0x18000824b  mov     rcx, cs:lpLibFileName; lpLibFileName
0x180008252  call    IsolationAwarePrivatezlybNQyVOeNelJ
0x180008257  test    rax, rax
0x18000825a  jz      short loc_180008272
0x18000825c  mov     cs:?m@?1??PrshtIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY@@9@4UIsolationAwarePrivate_zHGnoyr_zBqHyr_vAsB@@A, rax; IsolationAwarePrivate_zHGnoyr_zBqHyr_vAsB `PrshtIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY'::`2'::m
0x180008263  mov     rdx, rsi; lpProcName
0x180008266  mov     rcx, rax; hModule
0x180008269  call    cs:__imp_GetProcAddress
0x18000826f  mov     rbx, rax
0x180008272  mov     [rsp+38h+var_10], rbx
0x180008277  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000827e  jnz     short loc_1800082AF
0x180008280  test    edi, edi
0x180008282  jz      short loc_1800082AF
0x180008284  test    rbx, rbx
0x180008287  jnz     short loc_180008293
0x180008289  call    cs:__imp_GetLastError
0x18000828f  mov     edi, eax
0x180008291  jmp     short loc_180008295
0x180008293  xor     edi, edi
0x180008295  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x18000829a  xor     ecx, ecx; dwFlags
0x18000829c  call    cs:__imp_DeactivateActCtx
0x1800082a2  test    rbx, rbx
0x1800082a5  jnz     short loc_1800082AF
0x1800082a7  mov     ecx, edi; dwErrCode
0x1800082a9  call    cs:__imp_SetLastError
0x1800082af  mov     rax, rbx
0x1800082b2  mov     rbx, [rsp+38h+arg_0]
0x1800082b7  mov     rsi, [rsp+38h+arg_10]
0x1800082bc  add     rsp, 30h
0x1800082c0  pop     rdi
0x1800082c1  retn
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
