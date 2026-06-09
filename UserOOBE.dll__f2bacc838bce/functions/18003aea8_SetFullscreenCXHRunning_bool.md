# SetFullscreenCXHRunning(bool)

- ea: `0x18003aea8`
- end: `0x18003afb3`
- name: `?SetFullscreenCXHRunning@@YAJ_N@Z`
- size: `267`
- prototype: `__int64 __fastcall(bool)`
- caller_count: `7`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180037118`
- `0x180037270`
- `0x180038f8c`
- `0x180039740`
- `0x18003a030`
- `0x18003a9f8`
- `0x18003b6b0`

## callees

- `0x180015434`
- `0x18003aea8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003aefb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003af5f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003aefb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003af5f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003af95`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003afa0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003af95`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003afa0`

## pseudocode

```c
__int64 __fastcall SetFullscreenCXHRunning(unsigned __int8 a1)
{
  int v1; // edi
  LSTATUS v2; // eax
  signed int v3; // ebx
  LSTATUS v4; // eax
  HKEY phkResult; // [rsp+68h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  v1 = a1;
  hKey = 0;
  v2 = RegCreateKeyExW(
         HKEY_CURRENT_USER,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CloudExperienceHost",
         0,
         0,
         0,
         0x2001Fu,
         0,
         &hKey,
         0);
  v3 = v2;
  if ( v2 > 0 )
    v3 = (unsigned __int16)v2 | 0x80070000;
  if ( v3 >= 0 )
  {
    phkResult = 0;
    v4 = RegCreateKeyExW(hKey, L"Fullscreen", 0, 0, 1u, 0x2001Fu, 0, &phkResult, 0);
    v3 = v4;
    if ( v4 > 0 )
      v3 = (unsigned __int16)v4 | 0x80070000;
    if ( v3 >= 0 )
    {
      v3 = SHRegSetBOOL(phkResult, 0, L"FullscreenCXHRunning", v1);
      RegCloseKey(phkResult);
    }
    RegCloseKey(hKey);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18003aea8  mov     r11, rsp
0x18003aeab  mov     [r11+8], rbx
0x18003aeaf  push    rdi
0x18003aeb0  sub     rsp, 50h
0x18003aeb4  mov     qword ptr [r11-18h], 0
0x18003aebc  lea     rax, [r11+18h]
0x18003aec0  mov     [r11-20h], rax
0x18003aec4  lea     rdx, aSoftwareMicros_22; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18003aecb  mov     qword ptr [r11-28h], 0
0x18003aed3  xor     r9d, r9d; lpClass
0x18003aed6  movzx   edi, cl
0x18003aed9  xor     r8d, r8d; Reserved
0x18003aedc  mov     [rsp+58h+samDesired], 2001Fh; samDesired
0x18003aee4  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18003aeeb  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18003aef3  mov     qword ptr [r11+18h], 0
0x18003aefb  call    cs:__imp_RegCreateKeyExW
0x18003af01  mov     ebx, eax
0x18003af03  test    eax, eax
0x18003af05  jle     short loc_18003AF10
0x18003af07  movzx   ebx, ax
0x18003af0a  or      ebx, 80070000h
0x18003af10  test    ebx, ebx
0x18003af12  js      loc_18003AFA6
0x18003af18  mov     rcx, [rsp+58h+hKey]; hKey
0x18003af1d  lea     rax, [rsp+58h+arg_8]
0x18003af22  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x18003af2b  lea     rdx, aFullscreen; "Fullscreen"
0x18003af32  mov     [rsp+58h+phkResult], rax; phkResult
0x18003af37  xor     r9d, r9d; lpClass
0x18003af3a  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18003af43  xor     r8d, r8d; Reserved
0x18003af46  mov     [rsp+58h+samDesired], 2001Fh; samDesired
0x18003af4e  mov     [rsp+58h+dwOptions], 1; dwOptions
0x18003af56  mov     [rsp+58h+arg_8], 0
0x18003af5f  call    cs:__imp_RegCreateKeyExW
0x18003af65  mov     ebx, eax
0x18003af67  test    eax, eax
0x18003af69  jle     short loc_18003AF74
0x18003af6b  movzx   ebx, ax
0x18003af6e  or      ebx, 80070000h
0x18003af74  test    ebx, ebx
0x18003af76  js      short loc_18003AF9B
0x18003af78  mov     rcx, [rsp+58h+arg_8]; HKEY
0x18003af7d  lea     r8, aFullscreencxhr; "FullscreenCXHRunning"
0x18003af84  mov     r9d, edi; int
0x18003af87  xor     edx, edx; unsigned __int16 *
0x18003af89  call    ?SHRegSetBOOL@@YAJPEAUHKEY__@@PEBG1H@Z; SHRegSetBOOL(HKEY__ *,ushort const *,ushort const *,int)
0x18003af8e  mov     rcx, [rsp+58h+arg_8]; hKey
0x18003af93  mov     ebx, eax
0x18003af95  call    cs:__imp_RegCloseKey
0x18003af9b  mov     rcx, [rsp+58h+hKey]; hKey
0x18003afa0  call    cs:__imp_RegCloseKey
0x18003afa6  mov     eax, ebx
0x18003afa8  mov     rbx, [rsp+58h+arg_0]
0x18003afad  add     rsp, 50h
0x18003afb1  pop     rdi
0x18003afb2  retn
```
