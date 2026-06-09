# EnvironmentDefaultImpl::get_IsFullscreenCXHRunning(uchar *)

- ea: `0x180019040`
- end: `0x1800190d5`
- name: `?get_IsFullscreenCXHRunning@EnvironmentDefaultImpl@@UEAAJPEAE@Z`
- size: `149`
- prototype: `__int64 __fastcall(EnvironmentDefaultImpl *__hidden this, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180019040`
- `0x180022658`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001907b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001907b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800190b8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800190b8`

## pseudocode

```c
__int64 __fastcall EnvironmentDefaultImpl::get_IsFullscreenCXHRunning(
        EnvironmentDefaultImpl *this,
        unsigned __int8 *a2)
{
  LSTATUS v3; // eax
  unsigned int v4; // r9d
  bool v5; // sf
  unsigned __int8 v6; // al
  int v8; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  v8 = 0;
  hKey = 0;
  v3 = RegOpenKeyExW(
         HKEY_CURRENT_USER,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CloudExperienceHost",
         0,
         0x20019u,
         &hKey);
  v5 = v3 < 0;
  if ( v3 > 0 )
    v5 = 1;
  v6 = 0;
  if ( !v5 )
  {
    SHRegGetBOOLWithREGSAM(hKey, L"Fullscreen", L"FullscreenCXHRunning", v4, &v8);
    RegCloseKey(hKey);
    if ( v8 )
      v6 = 1;
  }
  *a2 = v6;
  return 0;
}

```

## disassembly

```asm
0x180019040  push    rbx
0x180019042  sub     rsp, 30h
0x180019046  mov     rbx, rdx
0x180019049  mov     [rsp+38h+arg_8], 0
0x180019051  lea     rax, [rsp+38h+hKey]
0x180019056  mov     [rsp+38h+hKey], 0
0x18001905f  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180019066  mov     [rsp+38h+phkResult], rax; phkResult
0x18001906b  mov     r9d, 20019h; samDesired
0x180019071  xor     r8d, r8d; ulOptions
0x180019074  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18001907b  call    cs:__imp_RegOpenKeyExW
0x180019081  test    eax, eax
0x180019083  jle     short loc_18001908F
0x180019085  movzx   eax, ax
0x180019088  or      eax, 80070000h
0x18001908d  test    eax, eax
0x18001908f  js      short loc_1800190C9
0x180019091  mov     rcx, [rsp+38h+hKey]; HKEY
0x180019096  lea     rax, [rsp+38h+arg_8]
0x18001909b  lea     r8, aFullscreencxhr; "FullscreenCXHRunning"
0x1800190a2  mov     [rsp+38h+phkResult], rax; int *
0x1800190a7  lea     rdx, aFullscreen; "Fullscreen"
0x1800190ae  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x1800190b3  mov     rcx, [rsp+38h+hKey]; hKey
0x1800190b8  call    cs:__imp_RegCloseKey
0x1800190be  cmp     [rsp+38h+arg_8], 0
0x1800190c3  jz      short loc_1800190C9
0x1800190c5  mov     al, 1
0x1800190c7  jmp     short loc_1800190CB
0x1800190c9  xor     al, al
0x1800190cb  mov     [rbx], al
0x1800190cd  xor     eax, eax
0x1800190cf  add     rsp, 30h
0x1800190d3  pop     rbx
0x1800190d4  retn
```
