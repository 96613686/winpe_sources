# StateWebServer::GetSocketTimeoutValueFromReg(void)

- ea: `0x1400023d0`
- end: `0x140002489`
- name: `?GetSocketTimeoutValueFromReg@StateWebServer@@AEAAJXZ`
- size: `185`
- prototype: `__int64 __fastcall(StateWebServer *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x1400027ec`

## callees

- `0x1400023d0`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x14000244e`
- `ADVAPI32!RegQueryValueExW` at `0x14000244e`
- `ADVAPI32!RegOpenKeyExW` at `0x140002403`
- `ADVAPI32!RegOpenKeyExW` at `0x140002403`
- `ADVAPI32!RegCloseKey` at `0x140002472`
- `ADVAPI32!RegCloseKey` at `0x140002472`

## string_xrefs

- `0x1400023ec`: `SYSTEM\CurrentControlSet\Services\aspnet_state\Parameters`

## pseudocode

```c
__int64 __fastcall StateWebServer::GetSocketTimeoutValueFromReg(StateWebServer *this)
{
  unsigned int v2; // ebx
  LSTATUS v3; // eax
  int v4; // eax
  int Data; // [rsp+58h] [rbp+10h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+20h] BYREF

  v2 = 0;
  hKey = 0;
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, StateWebServer::s_serviceKeyNameParameters, 0, 0x20019u, &hKey);
  if ( v3 || (cbData = 4, (v3 = RegQueryValueExW(hKey, L"SocketTimeout", 0, 0, (LPBYTE)&Data, &cbData)) != 0) )
  {
    v2 = (unsigned __int16)v3 | 0x80070000;
    if ( v3 <= 0 )
      v2 = v3;
  }
  else
  {
    v4 = Data;
    if ( Data <= 0 )
      v4 = 15;
    Data = v4;
    *((_DWORD *)this + 8) = v4;
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v2 )
    *((_DWORD *)this + 8) = 15;
  return v2;
}

```

## disassembly

```asm
0x1400023d0  push    rbx
0x1400023d2  push    rsi
0x1400023d3  push    rdi
0x1400023d4  sub     rsp, 30h
0x1400023d8  mov     rdi, rcx
0x1400023db  lea     rax, [rsp+48h+hKey]
0x1400023e0  xor     ebx, ebx
0x1400023e2  mov     [rsp+48h+phkResult], rax; phkResult
0x1400023e7  and     [rsp+48h+hKey], rbx
0x1400023ec  lea     rdx, ?s_serviceKeyNameParameters@StateWebServer@@0PAGA; "SYSTEM\\CurrentControlSet\\Services\\as"...
0x1400023f3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400023fa  mov     r9d, 20019h; samDesired
0x140002400  xor     r8d, r8d; ulOptions
0x140002403  call    cs:__imp_RegOpenKeyExW
0x140002409  lea     esi, [rbx+0Fh]
0x14000240c  test    eax, eax
0x14000240e  jz      short loc_140002420
0x140002410  movzx   ebx, ax
0x140002413  or      ebx, 80070000h
0x140002419  test    eax, eax
0x14000241b  cmovle  ebx, eax
0x14000241e  jmp     short loc_140002468
0x140002420  mov     rcx, [rsp+48h+hKey]; hKey
0x140002425  lea     rax, [rsp+48h+cbData]
0x14000242a  mov     [rsp+48h+lpcbData], rax; lpcbData
0x14000242f  lea     rdx, aSockettimeout; "SocketTimeout"
0x140002436  lea     rax, [rsp+48h+Data]
0x14000243b  mov     [rsp+48h+cbData], 4
0x140002443  xor     r9d, r9d; lpType
0x140002446  mov     [rsp+48h+phkResult], rax; lpData
0x14000244b  xor     r8d, r8d; lpReserved
0x14000244e  call    cs:__imp_RegQueryValueExW
0x140002454  test    eax, eax
0x140002456  jnz     short loc_140002410
0x140002458  mov     eax, [rsp+48h+Data]
0x14000245c  test    eax, eax
0x14000245e  cmovle  eax, esi
0x140002461  mov     [rsp+48h+Data], eax
0x140002465  mov     [rdi+20h], eax
0x140002468  mov     rcx, [rsp+48h+hKey]; hKey
0x14000246d  test    rcx, rcx
0x140002470  jz      short loc_140002478
0x140002472  call    cs:__imp_RegCloseKey
0x140002478  test    ebx, ebx
0x14000247a  jz      short loc_14000247F
0x14000247c  mov     [rdi+20h], esi
0x14000247f  mov     eax, ebx
0x140002481  add     rsp, 30h
0x140002485  pop     rdi
0x140002486  pop     rsi
0x140002487  pop     rbx
0x140002488  retn
```
