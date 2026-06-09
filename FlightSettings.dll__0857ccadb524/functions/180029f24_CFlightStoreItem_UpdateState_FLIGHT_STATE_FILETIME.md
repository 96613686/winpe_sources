# CFlightStoreItem::UpdateState(FLIGHT_STATE,_FILETIME *)

- ea: `0x180029f24`
- end: `0x18002a060`
- name: `?UpdateState@CFlightStoreItem@@QEAAJW4FLIGHT_STATE@@PEAU_FILETIME@@@Z`
- size: `316`
- prototype: `int __high(enum FLIGHT_STATE, struct _FILETIME *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180020914`
- `0x1800299c4`

## callees

- `0x18000cc8c`
- `0x18002998c`
- `0x180029f24`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180029f73`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180029fd7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002a024`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180029f73`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180029fd7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002a024`

## string_xrefs

- `0x180029f3a`: `InstallationTS`
- `0x180029f64`: `InstallationTS`
- `0x180029f96`: `onecore\base\flighting\flightsettings\broker\libs\clientapi\flightstoreitem.cpp`

## pseudocode

```c
__int64 __fastcall CFlightStoreItem::UpdateState(__int64 a1, int a2, const BYTE *a3)
{
  LSTATUS v5; // eax
  signed int v6; // ebx
  __int64 v7; // rdx
  LSTATUS v9; // eax
  HKEY v10; // rcx
  LSTATUS v11; // eax
  int lpData; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int Data; // [rsp+48h] [rbp+10h] BYREF

  Data = a2;
  if ( !SHRegValueExists(*(HKEY *)(a1 + 24), L"InstallationTS", 0) )
  {
    v5 = RegSetValueExW(*(HKEY *)(a1 + 24), L"InstallationTS", 0, 3u, a3, 8u);
    v6 = v5;
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
    if ( v6 < 0 )
    {
      v7 = 272;
LABEL_6:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v7,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\clientapi\\flightstoreitem.cpp",
        (const char *)(unsigned int)v6,
        lpData);
      return (unsigned int)v6;
    }
    *(_QWORD *)(a1 + 136) = *(_QWORD *)a3;
  }
  v9 = RegSetValueExW(*(HKEY *)(a1 + 24), L"LastChangeTS", 0, 3u, a3, 8u);
  v6 = v9;
  if ( v9 > 0 )
    v6 = (unsigned __int16)v9 | 0x80070000;
  if ( v6 < 0 )
  {
    v7 = 279;
    goto LABEL_6;
  }
  v10 = *(HKEY *)(a1 + 24);
  *(_QWORD *)(a1 + 144) = *(_QWORD *)a3;
  v11 = RegSetValueExW(v10, L"CurrentState", 0, 4u, (const BYTE *)&Data, 4u);
  v6 = v11;
  if ( v11 > 0 )
    v6 = (unsigned __int16)v11 | 0x80070000;
  if ( v6 < 0 )
  {
    v7 = 286;
    goto LABEL_6;
  }
  *(_DWORD *)(a1 + 72) = Data;
  return 0;
}

```

## disassembly

```asm
0x180029f24  mov     [rsp+arg_0], rbx
0x180029f29  mov     [rsp+arg_10], rsi
0x180029f2e  mov     [rsp+Data], edx
0x180029f32  push    rdi
0x180029f33  sub     rsp, 30h
0x180029f37  mov     rsi, r8
0x180029f3a  lea     rdx, aInstallationts; "InstallationTS"
0x180029f41  mov     rdi, rcx
0x180029f44  xor     r8d, r8d; unsigned int *
0x180029f47  mov     rcx, [rcx+18h]; HKEY
0x180029f4b  call    ?SHRegValueExists@@YAHPEAUHKEY__@@PEBGPEAK@Z; SHRegValueExists(HKEY__ *,ushort const *,ulong *)
0x180029f50  test    eax, eax
0x180029f52  jnz     short loc_180029FB6
0x180029f54  mov     rcx, [rdi+18h]; hKey
0x180029f58  lea     r9d, [rax+3]; dwType
0x180029f5c  mov     [rsp+38h+cbData], 8; cbData
0x180029f64  lea     rdx, aInstallationts; "InstallationTS"
0x180029f6b  xor     r8d, r8d; Reserved
0x180029f6e  mov     [rsp+38h+lpData], rsi; int
0x180029f73  call    cs:__imp_RegSetValueExW
0x180029f79  mov     ebx, eax
0x180029f7b  test    eax, eax
0x180029f7d  jle     short loc_180029F88
0x180029f7f  movzx   ebx, ax
0x180029f82  or      ebx, 80070000h
0x180029f88  test    ebx, ebx
0x180029f8a  jns     short loc_180029FAC
0x180029f8c  mov     edx, 110h; void *
0x180029f91  mov     rcx, [rsp+38h]; this
0x180029f96  lea     r8, aOnecoreBaseFli_13; "onecore\\base\\flighting\\flightsetting"...
0x180029f9d  mov     r9d, ebx; char *
0x180029fa0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029fa5  mov     eax, ebx
0x180029fa7  jmp     loc_18002A050
0x180029fac  mov     rax, [rsi]
0x180029faf  mov     [rdi+88h], rax
0x180029fb6  mov     rcx, [rdi+18h]; hKey
0x180029fba  lea     rdx, aLastchangets; "LastChangeTS"
0x180029fc1  mov     [rsp+38h+cbData], 8; cbData
0x180029fc9  mov     r9d, 3; dwType
0x180029fcf  xor     r8d, r8d; Reserved
0x180029fd2  mov     [rsp+38h+lpData], rsi; lpData
0x180029fd7  call    cs:__imp_RegSetValueExW
0x180029fdd  mov     ebx, eax
0x180029fdf  test    eax, eax
0x180029fe1  jle     short loc_180029FEC
0x180029fe3  movzx   ebx, ax
0x180029fe6  or      ebx, 80070000h
0x180029fec  test    ebx, ebx
0x180029fee  jns     short loc_180029FF7
0x180029ff0  mov     edx, 117h
0x180029ff5  jmp     short loc_180029F91
0x180029ff7  mov     rax, [rsi]
0x180029ffa  lea     rdx, aCurrentstate; "CurrentState"
0x18002a001  mov     rcx, [rdi+18h]; hKey
0x18002a005  mov     r9d, 4; dwType
0x18002a00b  mov     [rdi+90h], rax
0x18002a012  xor     r8d, r8d; Reserved
0x18002a015  lea     rax, [rsp+38h+Data]
0x18002a01a  mov     [rsp+38h+cbData], r9d; cbData
0x18002a01f  mov     [rsp+38h+lpData], rax; lpData
0x18002a024  call    cs:__imp_RegSetValueExW
0x18002a02a  mov     ebx, eax
0x18002a02c  test    eax, eax
0x18002a02e  jle     short loc_18002A039
0x18002a030  movzx   ebx, ax
0x18002a033  or      ebx, 80070000h
0x18002a039  test    ebx, ebx
0x18002a03b  jns     short loc_18002A047
0x18002a03d  mov     edx, 11Eh
0x18002a042  jmp     loc_180029F91
0x18002a047  mov     eax, [rsp+38h+Data]
0x18002a04b  mov     [rdi+48h], eax
0x18002a04e  xor     eax, eax
0x18002a050  mov     rbx, [rsp+38h+arg_0]
0x18002a055  mov     rsi, [rsp+38h+arg_10]
0x18002a05a  add     rsp, 30h
0x18002a05e  pop     rdi
0x18002a05f  retn
```
