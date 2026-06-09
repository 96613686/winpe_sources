# CBdeCfgConsole::NotifyConfigurationStateChange(_BDECFG_STATE,__int64)

- ea: `0x140002a00`
- end: `0x140002b81`
- name: `?NotifyConfigurationStateChange@CBdeCfgConsole@@UEAAXW4_BDECFG_STATE@@_J@Z`
- size: `385`
- prototype: `void __fastcall(__int64, int, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callees

- `0x140001008`
- `0x1400016f3`
- `0x140002480`
- `0x140002a00`
- `0x1400032b0`
- `0x14000343c`
- `0x140003f84`
- `0x140004460`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x140002b5e`
- `KERNEL32!LeaveCriticalSection` at `0x140002b5e`
- `KERNEL32!EnterCriticalSection` at `0x140002a65`
- `KERNEL32!EnterCriticalSection` at `0x140002a65`
- `KERNEL32!SetThreadPreferredUILanguages` at `0x140002a55`
- `KERNEL32!SetThreadPreferredUILanguages` at `0x140002a55`
- `KERNEL32!SetEvent` at `0x140002b55`
- `KERNEL32!SetEvent` at `0x140002b55`
- `BDEHDCFGLIB!BdeCfgLoadResourceString` at `0x140002a91`
- `BDEHDCFGLIB!BdeCfgLoadResourceString` at `0x140002a91`

## pseudocode

```c
void __fastcall CBdeCfgConsole::NotifyConfigurationStateChange(__int64 a1, int a2, int a3)
{
  unsigned __int64 *v6; // r9
  int v7; // edx
  void *Block; // [rsp+30h] [rbp-258h] BYREF
  void *v9; // [rsp+38h] [rbp-250h] BYREF
  unsigned __int16 v10[264]; // [rsp+40h] [rbp-248h] BYREF

  Block = 0;
  v9 = 0;
  memset_0(v10, 0, 0x208u);
  SetThreadPreferredUILanguages(0x100u, 0, 0);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 1456));
  v7 = *(_DWORD *)(a1 + 1496);
  if ( v7 != -1 )
  {
    if ( (int)CBdeCfgConsole::GetStepDescription((CBdeCfgConsole *)a1, v7, &Block, v6) >= 0
      && (int)BdeCfgLoadResourceString(0x1C2u, (unsigned __int16 **)&v9) >= 0
      && (int)StringCchPrintfW(v10, 0x104u, L"%s - %s.", Block, v9) >= 0 )
    {
      CBdeCfgConsole::PrintProgressLine((CBdeCfgConsole *)a1, v10);
    }
    operator delete(Block);
    operator delete(v9);
    CBdeCfgConsole::PrintConsoleMessage((CBdeCfgConsole *)a1, L"\r\n\r\n");
  }
  if ( !a2 )
    CBdeCfgConsole::PrintConsoleMessage((CBdeCfgConsole *)a1, L"\r\n\r\n");
  *(_DWORD *)(a1 + 1500) = 0;
  if ( a2 == 1 )
  {
    if ( (int)CBdeCfgConsole::GetStepDescription((CBdeCfgConsole *)a1, a3, &Block, v6) >= 0 )
    {
      CBdeCfgConsole::PrintProgressLine((CBdeCfgConsole *)a1, (const unsigned __int16 *)Block);
      operator delete(Block);
    }
    *(_DWORD *)(a1 + 1496) = a3;
  }
  else if ( a2 == 2 )
  {
    SetEvent(*(HANDLE *)(a1 + 1440));
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 1456));
}

```

## disassembly

```asm
0x140002a00  push    rbx
0x140002a02  push    rsi
0x140002a03  push    rdi
0x140002a04  push    r14
0x140002a06  sub     rsp, 268h
0x140002a0d  mov     rax, cs:__security_cookie
0x140002a14  xor     rax, rsp
0x140002a17  mov     [rsp+288h+var_38], rax
0x140002a1f  mov     rsi, r8
0x140002a22  mov     edi, edx
0x140002a24  mov     rbx, rcx
0x140002a27  mov     [rsp+288h+Block], 0
0x140002a30  mov     [rsp+288h+var_250], 0
0x140002a39  xor     edx, edx; Val
0x140002a3b  mov     r8d, 208h; Size
0x140002a41  lea     rcx, [rsp+288h+var_248]; void *
0x140002a46  call    memset_0
0x140002a4b  xor     r8d, r8d; pulNumLanguages
0x140002a4e  xor     edx, edx; pwszLanguagesBuffer
0x140002a50  mov     ecx, 100h; dwFlags
0x140002a55  call    cs:__imp_SetThreadPreferredUILanguages
0x140002a5b  lea     r14, [rbx+5B0h]
0x140002a62  mov     rcx, r14; lpCriticalSection
0x140002a65  call    cs:__imp_EnterCriticalSection
0x140002a6b  mov     edx, [rbx+5D8h]
0x140002a71  cmp     edx, 0FFFFFFFFh
0x140002a74  jz      short loc_140002AF5
0x140002a76  lea     r8, [rsp+288h+Block]
0x140002a7b  mov     rcx, rbx
0x140002a7e  call    ?GetStepDescription@CBdeCfgConsole@@AEAAJW4_BDECFG_STEP_ID@@PEAPEAG@Z; CBdeCfgConsole::GetStepDescription(_BDECFG_STEP_ID,ushort * *)
0x140002a83  test    eax, eax
0x140002a85  js      short loc_140002AD2
0x140002a87  lea     rdx, [rsp+288h+var_250]
0x140002a8c  mov     ecx, 1C2h
0x140002a91  call    cs:__imp_?BdeCfgLoadResourceString@@YAJIPEAPEAG@Z; BdeCfgLoadResourceString(uint,ushort * *)
0x140002a97  test    eax, eax
0x140002a99  js      short loc_140002AD2
0x140002a9b  mov     rax, [rsp+288h+var_250]
0x140002aa0  mov     [rsp+288h+var_268], rax
0x140002aa5  mov     r9, [rsp+288h+Block]
0x140002aaa  lea     r8, aSS; "%s - %s."
0x140002ab1  mov     edx, 104h; unsigned __int64
0x140002ab6  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x140002abb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140002ac0  test    eax, eax
0x140002ac2  js      short loc_140002AD2
0x140002ac4  lea     rdx, [rsp+288h+var_248]; unsigned __int16 *
0x140002ac9  mov     rcx, rbx; this
0x140002acc  call    ?PrintProgressLine@CBdeCfgConsole@@AEAAXPEBG@Z; CBdeCfgConsole::PrintProgressLine(ushort const *)
0x140002ad1  nop
0x140002ad2  mov     rcx, [rsp+288h+Block]; Block
0x140002ad7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140002adc  mov     rcx, [rsp+288h+var_250]; Block
0x140002ae1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140002ae6  lea     rdx, asc_1400067C8; "\r\n\r\n"
0x140002aed  mov     rcx, rbx; this
0x140002af0  call    ?PrintConsoleMessage@CBdeCfgConsole@@AEAAJPEBGZZ; CBdeCfgConsole::PrintConsoleMessage(ushort const *,...)
0x140002af5  test    edi, edi
0x140002af7  jnz     short loc_140002B08
0x140002af9  lea     rdx, asc_1400067C8; "\r\n\r\n"
0x140002b00  mov     rcx, rbx; this
0x140002b03  call    ?PrintConsoleMessage@CBdeCfgConsole@@AEAAJPEBGZZ; CBdeCfgConsole::PrintConsoleMessage(ushort const *,...)
0x140002b08  mov     dword ptr [rbx+5DCh], 0
0x140002b12  cmp     edi, 1
0x140002b15  jnz     short loc_140002B49
0x140002b17  lea     r8, [rsp+288h+Block]
0x140002b1c  mov     edx, esi
0x140002b1e  mov     rcx, rbx
0x140002b21  call    ?GetStepDescription@CBdeCfgConsole@@AEAAJW4_BDECFG_STEP_ID@@PEAPEAG@Z; CBdeCfgConsole::GetStepDescription(_BDECFG_STEP_ID,ushort * *)
0x140002b26  test    eax, eax
0x140002b28  js      short loc_140002B41
0x140002b2a  mov     rdx, [rsp+288h+Block]; unsigned __int16 *
0x140002b2f  mov     rcx, rbx; this
0x140002b32  call    ?PrintProgressLine@CBdeCfgConsole@@AEAAXPEBG@Z; CBdeCfgConsole::PrintProgressLine(ushort const *)
0x140002b37  mov     rcx, [rsp+288h+Block]; Block
0x140002b3c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140002b41  mov     [rbx+5D8h], esi
0x140002b47  jmp     short loc_140002B5B
0x140002b49  cmp     edi, 2
0x140002b4c  jnz     short loc_140002B5B
0x140002b4e  mov     rcx, [rbx+5A0h]; hEvent
0x140002b55  call    cs:__imp_SetEvent
0x140002b5b  mov     rcx, r14; lpCriticalSection
0x140002b5e  call    cs:__imp_LeaveCriticalSection
0x140002b64  mov     rcx, [rsp+288h+var_38]
0x140002b6c  xor     rcx, rsp; StackCookie
0x140002b6f  call    __security_check_cookie
0x140002b74  add     rsp, 268h
0x140002b7b  pop     r14
0x140002b7d  pop     rdi
0x140002b7e  pop     rsi
0x140002b7f  pop     rbx
0x140002b80  retn
0x14000469e  push    rbp
0x1400046a0  sub     rsp, 30h
0x1400046a4  mov     rbp, rdx
0x1400046a7  mov     rcx, [rbp+30h]; Block
0x1400046ab  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400046b0  mov     rcx, [rbp+38h]; Block
0x1400046b4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400046b9  nop
0x1400046ba  add     rsp, 30h
0x1400046be  pop     rbp
0x1400046bf  retn
```
