# IsWizardOnlyAccount(ushort const *)

- ea: `0x14000eca4`
- end: `0x14000ed95`
- name: `?IsWizardOnlyAccount@@YA_NPEBG@Z`
- size: `241`
- prototype: `bool __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000ed9c`

## callees

- `0x14000eca4`
- `0x14000f90c`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14000ed42`
- `ADVAPI32!RegOpenKeyExW` at `0x14000ed42`
- `ADVAPI32!RegCloseKey` at `0x14000ed73`
- `ADVAPI32!RegCloseKey` at `0x14000ed73`

## pseudocode

```c
char __fastcall IsWizardOnlyAccount(const unsigned __int16 *a1)
{
  LSTATUS v2; // eax
  bool v3; // sf
  int v5; // [rsp+48h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+20h] BYREF

  v5 = 0;
  SHRegGetBOOL(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE", L"LaunchUserOOBE", &v5);
  if ( v5 )
    return 1;
  v5 = 0;
  SHRegGetBOOL(
    HKEY_LOCAL_MACHINE,
    L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Authentication\\CFL\\ExperienceManagerData",
    L"LaunchCflScenario",
    &v5);
  if ( v5 )
    return 1;
  v5 = 0;
  if ( !a1 )
    return 0;
  hKey = 0;
  v2 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\CandidateAccountManager",
         0,
         0x20019u,
         &hKey);
  v3 = v2 < 0;
  if ( v2 > 0 )
    v3 = 1;
  if ( !v3 && (SHRegGetBOOL(hKey, a1, L"CxhOnlyUse", &v5), RegCloseKey(hKey), v5) )
    return 1;
  else
    return 0;
}

```

## disassembly

```asm
0x14000eca4  mov     [rsp-8+arg_0], rbx
0x14000eca9  mov     [rsp-8+arg_18], rsi
0x14000ecae  push    rbp
0x14000ecaf  mov     rbp, rsp
0x14000ecb2  sub     rsp, 30h
0x14000ecb6  mov     rbx, rcx
0x14000ecb9  mov     [rbp+arg_8], 0
0x14000ecc0  mov     rsi, 0FFFFFFFF80000002h
0x14000ecc7  lea     r9, [rbp+arg_8]; int *
0x14000eccb  mov     rcx, rsi; HKEY
0x14000ecce  lea     r8, aLaunchuseroobe; "LaunchUserOOBE"
0x14000ecd5  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x14000ecdc  call    ?SHRegGetBOOL@@YAJPEAUHKEY__@@PEBG1PEAH@Z; SHRegGetBOOL(HKEY__ *,ushort const *,ushort const *,int *)
0x14000ece1  cmp     [rbp+arg_8], 0
0x14000ece5  jnz     loc_14000ED83
0x14000eceb  lea     r9, [rbp+arg_8]; int *
0x14000ecef  mov     [rbp+arg_8], 0
0x14000ecf6  lea     r8, aLaunchcflscena; "LaunchCflScenario"
0x14000ecfd  mov     rcx, rsi; HKEY
0x14000ed00  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x14000ed07  call    ?SHRegGetBOOL@@YAJPEAUHKEY__@@PEBG1PEAH@Z; SHRegGetBOOL(HKEY__ *,ushort const *,ushort const *,int *)
0x14000ed0c  cmp     [rbp+arg_8], 0
0x14000ed10  jnz     short loc_14000ED83
0x14000ed12  mov     [rbp+arg_8], 0
0x14000ed19  test    rbx, rbx
0x14000ed1c  jz      short loc_14000ED7F
0x14000ed1e  lea     rax, [rbp+hKey]
0x14000ed22  mov     [rbp+hKey], 0
0x14000ed2a  mov     r9d, 20019h; samDesired
0x14000ed30  mov     [rsp+30h+phkResult], rax; phkResult
0x14000ed35  xor     r8d, r8d; ulOptions
0x14000ed38  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x14000ed3f  mov     rcx, rsi; hKey
0x14000ed42  call    cs:__imp_RegOpenKeyExW
0x14000ed48  test    eax, eax
0x14000ed4a  jle     short loc_14000ED56
0x14000ed4c  movzx   eax, ax
0x14000ed4f  or      eax, 80070000h
0x14000ed54  test    eax, eax
0x14000ed56  js      short loc_14000ED7F
0x14000ed58  mov     rcx, [rbp+hKey]; HKEY
0x14000ed5c  lea     r9, [rbp+arg_8]; int *
0x14000ed60  lea     r8, aCxhonlyuse; "CxhOnlyUse"
0x14000ed67  mov     rdx, rbx; unsigned __int16 *
0x14000ed6a  call    ?SHRegGetBOOL@@YAJPEAUHKEY__@@PEBG1PEAH@Z; SHRegGetBOOL(HKEY__ *,ushort const *,ushort const *,int *)
0x14000ed6f  mov     rcx, [rbp+hKey]; hKey
0x14000ed73  call    cs:__imp_RegCloseKey
0x14000ed79  cmp     [rbp+arg_8], 0
0x14000ed7d  jnz     short loc_14000ED83
0x14000ed7f  xor     al, al
0x14000ed81  jmp     short loc_14000ED85
0x14000ed83  mov     al, 1
0x14000ed85  mov     rbx, [rsp+30h+arg_0]
0x14000ed8a  mov     rsi, [rsp+30h+arg_18]
0x14000ed8f  add     rsp, 30h
0x14000ed93  pop     rbp
0x14000ed94  retn
```
