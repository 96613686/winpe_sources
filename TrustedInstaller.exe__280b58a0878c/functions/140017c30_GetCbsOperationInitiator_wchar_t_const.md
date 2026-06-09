# GetCbsOperationInitiator(wchar_t const *)

- ea: `0x140017c30`
- end: `0x140017cf1`
- name: `?GetCbsOperationInitiator@@YA?AW4CbsOperationInitiator@@PEB_W@Z`
- size: `193`
- prototype: `__int64 __fastcall(const wchar_t *)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140013414`

## callees

- `0x140017c30`
- `0x14002a940`

## string_xrefs

- `0x140017c47`: `TrustedInstaller FOD`
- `0x140017c5b`: `TrustedInstaller FOD Enumerate`
- `0x140017c81`: `TrustedInstaller ACR`
- `0x140017c9b`: `TrustedInstaller MCR`
- `0x140017ccf`: `AutomaticUpdates`

## pseudocode

```c
__int64 __fastcall GetCbsOperationInitiator(const wchar_t *a1)
{
  __int64 result; // rax

  result = 5;
  if ( a1 )
  {
    if ( !wcscmp_0(a1, L"TrustedInstaller FOD")
      || !wcscmp_0(a1, L"TrustedInstaller FOD Enumerate")
      || !wcscmp_0(a1, L"LCU Reservicing") )
    {
      return 0;
    }
    else if ( !wcscmp_0(a1, L"TrustedInstaller ACR") )
    {
      return 1;
    }
    else if ( !wcscmp_0(a1, L"TrustedInstaller MCR") )
    {
      return 2;
    }
    else if ( !wcscmp_0(a1, L"wusa") )
    {
      return 3;
    }
    else
    {
      return (unsigned int)(wcscmp_0(a1, L"AutomaticUpdates") != 0) + 4;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140017c30  push    rbx
0x140017c32  sub     rsp, 20h
0x140017c36  mov     rbx, rcx
0x140017c39  mov     eax, 5
0x140017c3e  test    rcx, rcx
0x140017c41  jz      loc_140017CEB
0x140017c47  lea     rdx, aTrustedinstall; "TrustedInstaller FOD"
0x140017c4e  call    wcscmp_0
0x140017c53  test    eax, eax
0x140017c55  jz      loc_140017CE9
0x140017c5b  lea     rdx, aTrustedinstall_1; "TrustedInstaller FOD Enumerate"
0x140017c62  mov     rcx, rbx; String1
0x140017c65  call    wcscmp_0
0x140017c6a  test    eax, eax
0x140017c6c  jz      short loc_140017CE9
0x140017c6e  lea     rdx, aLcuReservicing; "LCU Reservicing"
0x140017c75  mov     rcx, rbx; String1
0x140017c78  call    wcscmp_0
0x140017c7d  test    eax, eax
0x140017c7f  jz      short loc_140017CE9
0x140017c81  lea     rdx, aTrustedinstall_4; "TrustedInstaller ACR"
0x140017c88  mov     rcx, rbx; String1
0x140017c8b  call    wcscmp_0
0x140017c90  test    eax, eax
0x140017c92  jnz     short loc_140017C9B
0x140017c94  mov     eax, 1
0x140017c99  jmp     short loc_140017CEB
0x140017c9b  lea     rdx, aTrustedinstall_0; "TrustedInstaller MCR"
0x140017ca2  mov     rcx, rbx; String1
0x140017ca5  call    wcscmp_0
0x140017caa  test    eax, eax
0x140017cac  jnz     short loc_140017CB5
0x140017cae  mov     eax, 2
0x140017cb3  jmp     short loc_140017CEB
0x140017cb5  lea     rdx, aWusa; "wusa"
0x140017cbc  mov     rcx, rbx; String1
0x140017cbf  call    wcscmp_0
0x140017cc4  test    eax, eax
0x140017cc6  jnz     short loc_140017CCF
0x140017cc8  mov     eax, 3
0x140017ccd  jmp     short loc_140017CEB
0x140017ccf  lea     rdx, aAutomaticupdat; "AutomaticUpdates"
0x140017cd6  mov     rcx, rbx; String1
0x140017cd9  call    wcscmp_0
0x140017cde  neg     eax
0x140017ce0  sbb     eax, eax
0x140017ce2  neg     eax
0x140017ce4  add     eax, 4
0x140017ce7  jmp     short loc_140017CEB
0x140017ce9  xor     eax, eax
0x140017ceb  add     rsp, 20h
0x140017cef  pop     rbx
0x140017cf0  retn
```
