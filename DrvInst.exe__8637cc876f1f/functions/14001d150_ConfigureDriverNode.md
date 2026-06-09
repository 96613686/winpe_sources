# ConfigureDriverNode

- ea: `0x14001d150`
- end: `0x14001d2bb`
- name: `ConfigureDriverNode`
- size: `363`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001d2c4`

## callees

- `0x1400070bc`
- `0x140009794`
- `0x140018dc0`
- `0x14001d150`
- `0x140045eea`
- `0x140045f30`

## import_xrefs

- `DEVRTL!DevRtlWriteTextLog` at `0x14001d23c`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001d23c`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x14001d186`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x14001d186`
- `drvstore!DriverStoreConfigureW` at `0x14001d1fc`
- `drvstore!DriverStoreConfigureW` at `0x14001d1fc`

## string_xrefs

- `0x14001d212`: `Reboot required to complete device configuration.`

## pseudocode

```c
__int64 __fastcall ConfigureDriverNode(__int64 a1, __int64 a2, __int16 a3, __int64 a4, int a5, _DWORD *a6)
{
  __int64 ThreadLogToken; // rbp
  unsigned int v10; // ebx
  unsigned int v11; // eax
  HRESULT v12; // eax
  unsigned int v13; // ecx
  unsigned __int16 v15[208]; // [rsp+30h] [rbp-1D8h] BYREF

  ThreadLogToken = DevRtlGetThreadLogToken();
  memset_0(v15, 0, 0x192u);
  if ( (int)StringCchCopyW(v15, 0xC8u, (size_t *)(a2 + 1576)) < 0 )
    return 13;
  DrvInstActionCallback(0, 0);
  v11 = DriverStoreConfigureW(a1, a2 + 536, (a3 & 0x400 | 0x80000u) >> 2, v15, 0);
  v10 = v11;
  if ( v11 == 3010 )
  {
    *(_DWORD *)(a2 + 3976) |= 1u;
    DevRtlWriteTextLog(ThreadLogToken, 1, 4, "Reboot required to complete device configuration.");
  }
  else
  {
    if ( v11 != 3011 )
    {
      if ( v11 )
        return v10;
      goto LABEL_9;
    }
    *(_DWORD *)(a2 + 3976) |= 4u;
    DevRtlWriteTextLog(ThreadLogToken, 1, 4, "Restart required for any devices using this driver.");
  }
  v10 = 0;
LABEL_9:
  if ( a6 )
    *a6 = *(_DWORD *)(a2 + 3976);
  v12 = StringCchPrintfW((STRSAFE_LPWSTR)(a2 + 2496), 0x2D0u, L"%ws:%ws,%ws", a2 + 16, a2 + 1576, a2 + 1976);
  v13 = v10;
  if ( v12 < 0 )
    return 13;
  return v13;
}

```

## disassembly

```asm
0x14001d150  mov     [rsp+arg_10], rbx
0x14001d155  push    rbp
0x14001d156  push    rsi
0x14001d157  push    rdi
0x14001d158  push    r14
0x14001d15a  push    r15
0x14001d15c  sub     rsp, 1E0h
0x14001d163  mov     rax, cs:__security_cookie
0x14001d16a  xor     rax, rsp
0x14001d16d  mov     [rsp+208h+var_38], rax
0x14001d175  mov     rsi, [rsp+208h+arg_28]
0x14001d17d  mov     ebx, r8d
0x14001d180  mov     rdi, rdx
0x14001d183  mov     r14, rcx
0x14001d186  call    cs:__imp_DevRtlGetThreadLogToken
0x14001d18c  xor     edx, edx; Val
0x14001d18e  lea     rcx, [rsp+208h+var_1D8]; void *
0x14001d193  mov     r8d, 192h; Size
0x14001d199  mov     rbp, rax
0x14001d19c  call    memset_0
0x14001d1a1  lea     r15, [rdi+628h]
0x14001d1a8  mov     edx, 0C8h; unsigned __int64
0x14001d1ad  mov     r8, r15; unsigned __int16 *
0x14001d1b0  lea     rcx, [rsp+208h+var_1D8]; unsigned __int16 *
0x14001d1b5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14001d1ba  test    eax, eax
0x14001d1bc  jns     short loc_14001D1C8
0x14001d1be  mov     ebx, 0Dh
0x14001d1c3  jmp     loc_14001D292
0x14001d1c8  xor     r8d, r8d
0x14001d1cb  xor     edx, edx
0x14001d1cd  xor     ecx, ecx
0x14001d1cf  call    DrvInstActionCallback
0x14001d1d4  and     ebx, 400h
0x14001d1da  mov     [rsp+208h+var_1E8], 0
0x14001d1e3  bts     ebx, 13h
0x14001d1e7  lea     rdx, [rdi+218h]
0x14001d1ee  shr     ebx, 2
0x14001d1f1  lea     r9, [rsp+208h+var_1D8]
0x14001d1f6  mov     r8d, ebx
0x14001d1f9  mov     rcx, r14
0x14001d1fc  call    cs:__imp_DriverStoreConfigureW
0x14001d202  mov     ebx, eax
0x14001d204  cmp     eax, 0BC2h
0x14001d209  jnz     short loc_14001D21B
0x14001d20b  or      dword ptr [rdi+0F88h], 1
0x14001d212  lea     r9, aRebootRequired_1; "Reboot required to complete device conf"...
0x14001d219  jmp     short loc_14001D230
0x14001d21b  cmp     eax, 0BC3h
0x14001d220  jnz     short loc_14001D246
0x14001d222  or      dword ptr [rdi+0F88h], 4
0x14001d229  lea     r9, aRestartRequire; "Restart required for any devices using "...
0x14001d230  mov     edx, 1
0x14001d235  mov     rcx, rbp
0x14001d238  lea     r8d, [rdx+3]
0x14001d23c  call    cs:__imp_DevRtlWriteTextLog
0x14001d242  xor     ebx, ebx
0x14001d244  jmp     short loc_14001D24A
0x14001d246  test    eax, eax
0x14001d248  jnz     short loc_14001D292
0x14001d24a  test    rsi, rsi
0x14001d24d  jz      short loc_14001D257
0x14001d24f  mov     eax, [rdi+0F88h]
0x14001d255  mov     [rsi], eax
0x14001d257  lea     rax, [rdi+7B8h]
0x14001d25e  mov     edx, 2D0h; cchDest
0x14001d263  mov     [rsp+208h+var_1E0], rax
0x14001d268  lea     r9, [rdi+10h]
0x14001d26c  lea     rcx, [rdi+9C0h]; pszDest
0x14001d273  mov     [rsp+208h+var_1E8], r15
0x14001d278  lea     r8, aWsWsWs; "%ws:%ws,%ws"
0x14001d27f  call    StringCchPrintfW
0x14001d284  mov     ecx, ebx
0x14001d286  test    eax, eax
0x14001d288  mov     ebx, 0Dh
0x14001d28d  cmovs   ecx, ebx
0x14001d290  mov     ebx, ecx
0x14001d292  mov     eax, ebx
0x14001d294  mov     rcx, [rsp+208h+var_38]
0x14001d29c  xor     rcx, rsp; StackCookie
0x14001d29f  call    __security_check_cookie
0x14001d2a4  mov     rbx, [rsp+208h+arg_10]
0x14001d2ac  add     rsp, 1E0h
0x14001d2b3  pop     r15
0x14001d2b5  pop     r14
0x14001d2b7  pop     rdi
0x14001d2b8  pop     rsi
0x14001d2b9  pop     rbp
0x14001d2ba  retn
```
