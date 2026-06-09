# CloudSettings::GetCloudSettingsSnapshot(void)

- ea: `0x1800ab28c`
- end: `0x1800ab40f`
- name: `?GetCloudSettingsSnapshot@CloudSettings@@QEAAAEBUWinHttpSettings@@XZ`
- size: `387`
- prototype: `const struct WinHttpSettings *__fastcall(CloudSettings *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800a9738`
- `0x1800a9934`
- `0x1800a9d30`
- `0x1800aa75c`
- `0x1800aae3c`

## callees

- `0x1800ab28c`
- `0x1800ab418`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ab2d1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ab2d1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ab3fc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ab3fc`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800ab2a6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800ab2a6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ab3ef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ab3ef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ab306`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ab306`

## string_xrefs

- `0x1800ab2f8`: `OSDATA\Cloud Settings Cache`
- `0x1800ab31c`: `WinHttp Reliability Configuration Flags`

## pseudocode

```c
const struct WinHttpSettings *__fastcall CloudSettings::GetCloudSettingsSnapshot(CloudSettings *this)
{
  ULONGLONG TickCount64; // rax
  const unsigned __int16 *v2; // rdx
  const unsigned __int16 *v3; // rdx
  const unsigned __int16 *v4; // rdx
  int v5; // eax
  const unsigned __int16 *v6; // rdx
  int v7; // eax
  bool v8; // cc
  __int64 v9; // rax
  CloudSettings *v11; // [rsp+40h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+18h] BYREF

  v11 = this;
  if ( byte_1800F2CA8 )
  {
    TickCount64 = GetTickCount64();
    if ( TickCount64 - qword_1800F2C88 > 0x927C0 )
    {
      qword_1800F2C88 = TickCount64;
      EnterCriticalSection(&CriticalSection);
      hKey = 0;
      LODWORD(v11) = 0;
      if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"OSDATA\\Cloud Settings Cache", 0, 1u, &hKey) )
      {
LABEL_27:
        LeaveCriticalSection(&CriticalSection);
        return (const struct WinHttpSettings *)&dword_1800F2C90;
      }
      if ( !(unsigned int)SHRegGetDWORD(hKey, v2, L"WinHttp Reliability Configuration Flags", (unsigned int *)&v11) )
        dword_1800F2C90 = (int)v11;
      if ( !(unsigned int)SHRegGetDWORD(hKey, v3, L"WinHttp Reliability Max Host Count", (unsigned int *)&v11) )
      {
        if ( (unsigned int)v11 <= 2 || (v5 = 1000, (unsigned int)v11 < 0x3E8) )
        {
          v5 = 2;
          if ( (unsigned int)v11 > 2 )
            v5 = (int)v11;
        }
        dword_1800F2C94 = v5;
      }
      if ( (unsigned int)SHRegGetDWORD(hKey, v4, L"WinHttp Reliability Max Status Count", (unsigned int *)&v11) )
      {
LABEL_20:
        if ( !(unsigned int)SHRegGetDWORD(
                              hKey,
                              v6,
                              L"WinHttp Reliability Upload Period in Seconds",
                              (unsigned int *)&v11) )
        {
          v9 = (unsigned int)(1000 * (_DWORD)v11);
          if ( (unsigned int)v9 <= 0x2710 )
          {
            v9 = 10000;
          }
          else if ( (unsigned int)v9 >= 0x112A880 )
          {
            v9 = 18000000;
          }
          qword_1800F2CA0 = v9;
        }
        RegCloseKey(hKey);
        goto LABEL_27;
      }
      v7 = 5;
      v8 = (unsigned int)v11 <= 5;
      if ( (unsigned int)v11 > 5 )
      {
        if ( (unsigned int)v11 >= 0x2710 )
        {
          v7 = 10000;
LABEL_19:
          dword_1800F2C98 = v7;
          goto LABEL_20;
        }
        v8 = (unsigned int)v11 <= 5;
      }
      if ( !v8 )
        v7 = (int)v11;
      goto LABEL_19;
    }
  }
  return (const struct WinHttpSettings *)&dword_1800F2C90;
}

```

## disassembly

```asm
0x1800ab28c  mov     [rsp-8+arg_0], rcx
0x1800ab291  push    rbp
0x1800ab292  mov     rbp, rsp
0x1800ab295  sub     rsp, 30h
0x1800ab299  cmp     cs:byte_1800F2CA8, 0
0x1800ab2a0  jz      loc_1800AB402
0x1800ab2a6  call    cs:__imp_GetTickCount64
0x1800ab2ac  mov     rcx, rax
0x1800ab2af  sub     rcx, cs:qword_1800F2C88
0x1800ab2b6  cmp     rcx, 927C0h
0x1800ab2bd  jbe     loc_1800AB402
0x1800ab2c3  lea     rcx, CriticalSection; lpCriticalSection
0x1800ab2ca  mov     cs:qword_1800F2C88, rax
0x1800ab2d1  call    cs:__imp_EnterCriticalSection
0x1800ab2d7  lea     rax, [rbp+hKey]
0x1800ab2db  mov     [rbp+hKey], 0
0x1800ab2e3  mov     r9d, 1; samDesired
0x1800ab2e9  mov     [rsp+30h+phkResult], rax; phkResult
0x1800ab2ee  xor     r8d, r8d; ulOptions
0x1800ab2f1  mov     dword ptr [rbp+arg_0], 0
0x1800ab2f8  lea     rdx, aOsdataCloudSet; "OSDATA\\Cloud Settings Cache"
0x1800ab2ff  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800ab306  call    cs:__imp_RegOpenKeyExW
0x1800ab30c  test    eax, eax
0x1800ab30e  jnz     loc_1800AB3F5
0x1800ab314  mov     rcx, [rbp+hKey]; HKEY
0x1800ab318  lea     r9, [rbp+arg_0]; unsigned int *
0x1800ab31c  lea     r8, aWinhttpReliabi_1; "WinHttp Reliability Configuration Flags"
0x1800ab323  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800ab328  test    eax, eax
0x1800ab32a  jnz     short loc_1800AB335
0x1800ab32c  mov     eax, dword ptr [rbp+arg_0]
0x1800ab32f  mov     cs:dword_1800F2C90, eax
0x1800ab335  mov     rcx, [rbp+hKey]; HKEY
0x1800ab339  lea     r9, [rbp+arg_0]; unsigned int *
0x1800ab33d  lea     r8, aWinhttpReliabi; "WinHttp Reliability Max Host Count"
0x1800ab344  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800ab349  test    eax, eax
0x1800ab34b  jnz     short loc_1800AB36E
0x1800ab34d  mov     ecx, dword ptr [rbp+arg_0]
0x1800ab350  cmp     ecx, 2
0x1800ab353  jbe     short loc_1800AB35E
0x1800ab355  mov     eax, 3E8h
0x1800ab35a  cmp     ecx, eax
0x1800ab35c  jnb     short loc_1800AB368
0x1800ab35e  mov     eax, 2
0x1800ab363  cmp     ecx, eax
0x1800ab365  cmova   eax, ecx
0x1800ab368  mov     cs:dword_1800F2C94, eax
0x1800ab36e  mov     rcx, [rbp+hKey]; HKEY
0x1800ab372  lea     r9, [rbp+arg_0]; unsigned int *
0x1800ab376  lea     r8, aWinhttpReliabi_2; "WinHttp Reliability Max Status Count"
0x1800ab37d  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800ab382  test    eax, eax
0x1800ab384  jnz     short loc_1800AB3AC
0x1800ab386  mov     ecx, dword ptr [rbp+arg_0]
0x1800ab389  mov     eax, 5
0x1800ab38e  cmp     ecx, eax
0x1800ab390  jbe     short loc_1800AB3A3
0x1800ab392  cmp     ecx, 2710h
0x1800ab398  jb      short loc_1800AB3A1
0x1800ab39a  mov     eax, 2710h
0x1800ab39f  jmp     short loc_1800AB3A6
0x1800ab3a1  cmp     ecx, eax
0x1800ab3a3  cmova   eax, ecx
0x1800ab3a6  mov     cs:dword_1800F2C98, eax
0x1800ab3ac  mov     rcx, [rbp+hKey]; HKEY
0x1800ab3b0  lea     r9, [rbp+arg_0]; unsigned int *
0x1800ab3b4  lea     r8, aWinhttpReliabi_0; "WinHttp Reliability Upload Period in Se"...
0x1800ab3bb  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800ab3c0  test    eax, eax
0x1800ab3c2  jnz     short loc_1800AB3EB
0x1800ab3c4  imul    eax, dword ptr [rbp+arg_0], 3E8h
0x1800ab3cb  cmp     eax, 2710h
0x1800ab3d0  jbe     short loc_1800AB3DF
0x1800ab3d2  mov     ecx, 112A880h
0x1800ab3d7  cmp     eax, ecx
0x1800ab3d9  jb      short loc_1800AB3E4
0x1800ab3db  mov     eax, ecx
0x1800ab3dd  jmp     short loc_1800AB3E4
0x1800ab3df  mov     eax, 2710h
0x1800ab3e4  mov     cs:qword_1800F2CA0, rax
0x1800ab3eb  mov     rcx, [rbp+hKey]; hKey
0x1800ab3ef  call    cs:__imp_RegCloseKey
0x1800ab3f5  lea     rcx, CriticalSection; lpCriticalSection
0x1800ab3fc  call    cs:__imp_LeaveCriticalSection
0x1800ab402  lea     rax, dword_1800F2C90
0x1800ab409  add     rsp, 30h
0x1800ab40d  pop     rbp
0x1800ab40e  retn
```
