# StateWebServer::GetAllowRemoteConnectionFromReg(void)

- ea: `0x140002318`
- end: `0x1400023cf`
- name: `?GetAllowRemoteConnectionFromReg@StateWebServer@@AEAAJXZ`
- size: `183`
- prototype: `__int64 __fastcall(StateWebServer *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x14000210c`

## callees

- `0x140002318`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x140002394`
- `ADVAPI32!RegQueryValueExW` at `0x140002394`
- `ADVAPI32!RegOpenKeyExW` at `0x14000234c`
- `ADVAPI32!RegOpenKeyExW` at `0x14000234c`
- `ADVAPI32!RegCloseKey` at `0x1400023b2`
- `ADVAPI32!RegCloseKey` at `0x1400023b2`

## string_xrefs

- `0x140002335`: `SYSTEM\CurrentControlSet\Services\aspnet_state\Parameters`

## pseudocode

```c
__int64 __fastcall StateWebServer::GetAllowRemoteConnectionFromReg(StateWebServer *this)
{
  unsigned int v2; // ebx
  LSTATUS v3; // eax
  DWORD cbData; // [rsp+48h] [rbp+10h] BYREF
  int Data; // [rsp+50h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+20h] BYREF

  v2 = 0;
  hKey = 0;
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, StateWebServer::s_serviceKeyNameParameters, 0, 0x20019u, &hKey);
  if ( v3 || (cbData = 4, (v3 = RegQueryValueExW(hKey, L"AllowRemoteConnection", 0, 0, (LPBYTE)&Data, &cbData)) != 0) )
  {
    v2 = (unsigned __int16)v3 | 0x80070000;
    if ( v3 <= 0 )
      v2 = v3;
  }
  else
  {
    *((_BYTE *)this + 74) = Data != 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v2 )
  {
    *((_BYTE *)this + 74) = 0;
    return 0;
  }
  return v2;
}

```

## disassembly

```asm
0x140002318  mov     r11, rsp
0x14000231b  mov     [r11+8], rbx
0x14000231f  push    rdi
0x140002320  sub     rsp, 30h
0x140002324  mov     rdi, rcx
0x140002327  lea     rax, [r11+20h]
0x14000232b  xor     ebx, ebx
0x14000232d  mov     [r11-18h], rax
0x140002331  and     [r11+20h], rbx
0x140002335  lea     rdx, ?s_serviceKeyNameParameters@StateWebServer@@0PAGA; "SYSTEM\\CurrentControlSet\\Services\\as"...
0x14000233c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140002343  mov     r9d, 20019h; samDesired
0x140002349  xor     r8d, r8d; ulOptions
0x14000234c  call    cs:__imp_RegOpenKeyExW
0x140002352  test    eax, eax
0x140002354  jz      short loc_140002366
0x140002356  movzx   ebx, ax
0x140002359  or      ebx, 80070000h
0x14000235f  test    eax, eax
0x140002361  cmovle  ebx, eax
0x140002364  jmp     short loc_1400023A8
0x140002366  mov     rcx, [rsp+38h+hKey]; hKey
0x14000236b  lea     rax, [rsp+38h+cbData]
0x140002370  mov     [rsp+38h+lpcbData], rax; lpcbData
0x140002375  lea     rdx, ValueName; "AllowRemoteConnection"
0x14000237c  lea     rax, [rsp+38h+Data]
0x140002381  mov     [rsp+38h+cbData], 4
0x140002389  xor     r9d, r9d; lpType
0x14000238c  mov     [rsp+38h+lpData], rax; lpData
0x140002391  xor     r8d, r8d; lpReserved
0x140002394  call    cs:__imp_RegQueryValueExW
0x14000239a  test    eax, eax
0x14000239c  jnz     short loc_140002356
0x14000239e  cmp     [rsp+38h+Data], ebx
0x1400023a2  setnz   al
0x1400023a5  mov     [rdi+4Ah], al
0x1400023a8  mov     rcx, [rsp+38h+hKey]; hKey
0x1400023ad  test    rcx, rcx
0x1400023b0  jz      short loc_1400023B8
0x1400023b2  call    cs:__imp_RegCloseKey
0x1400023b8  test    ebx, ebx
0x1400023ba  jz      short loc_1400023C2
0x1400023bc  mov     byte ptr [rdi+4Ah], 0
0x1400023c0  xor     ebx, ebx
0x1400023c2  mov     eax, ebx
0x1400023c4  mov     rbx, [rsp+38h+arg_0]
0x1400023c9  add     rsp, 30h
0x1400023cd  pop     rdi
0x1400023ce  retn
```
