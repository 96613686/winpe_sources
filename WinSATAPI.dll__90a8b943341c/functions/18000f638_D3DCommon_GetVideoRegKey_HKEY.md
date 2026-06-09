# D3DCommon::GetVideoRegKey(HKEY__ * *)

- ea: `0x18000f638`
- end: `0x18000f76c`
- name: `?GetVideoRegKey@D3DCommon@@YAJPEAPEAUHKEY__@@@Z`
- size: `308`
- prototype: `__int64 __fastcall(D3DCommon *__hidden this, HKEY *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c03c`

## callees

- `0x18000f638`
- `0x18000f774`
- `0x180013e69`
- `0x18002db6c`
- `0x18002fb50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f729`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f729`
- `USER32!EnumDisplayDevicesW` at `0x18000f6c7`
- `USER32!EnumDisplayDevicesW` at `0x18000f6c7`

## string_xrefs

- `0x18000f672`: `D3DCommon::GetVideoRegKey`

## pseudocode

```c
__int64 __fastcall D3DCommon::GetVideoRegKey(D3DCommon *this, HKEY *a2)
{
  DWORD v4; // edi
  int v5; // esi
  unsigned __int64 v6; // [rsp+38h] [rbp-D0h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-C8h] BYREF
  _DISPLAY_DEVICEW DisplayDevice; // [rsp+48h] [rbp-C0h] BYREF

  if ( this )
  {
    *(_QWORD *)this = 0;
    v4 = 0;
    v6 = 0;
    phkResult = 0;
    v5 = 0;
    memset_0(DisplayDevice.DeviceName, 0, 0x344u);
    DisplayDevice.cb = 840;
    while ( EnumDisplayDevicesW(0, v4, &DisplayDevice, 0) )
    {
      if ( (DisplayDevice.StateFlags & 4) != 0 )
      {
        v5 = StringCchLengthW(DisplayDevice.DeviceKey, 0x80u, &v6);
        if ( v5 >= 0
          && v6 >= 0x13
          && !RegOpenKeyExW(HKEY_LOCAL_MACHINE, &DisplayDevice.DeviceKey[18], 0, 3u, &phkResult) )
        {
          *(_QWORD *)this = phkResult;
        }
        return (unsigned int)v5;
      }
      ++v4;
    }
    return (unsigned int)v5;
  }
  else
  {
    D3DCommon::ERR((D3DCommon *)0x6A, (unsigned __int16)L"phKey", L"D3DCommon::GetVideoRegKey");
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18000f638  mov     rax, rsp
0x18000f63b  mov     [rax+10h], rbx
0x18000f63f  mov     [rax+18h], rsi
0x18000f643  mov     [rax+20h], rdi
0x18000f647  push    rbp
0x18000f648  lea     rbp, [rax-2A8h]
0x18000f64f  sub     rsp, 3A0h
0x18000f656  mov     rax, cs:__security_cookie
0x18000f65d  xor     rax, rsp
0x18000f660  mov     [rbp+2A0h+var_10], rax
0x18000f667  mov     rbx, rcx
0x18000f66a  test    rcx, rcx
0x18000f66d  jnz     short loc_18000F68F
0x18000f66f  lea     ecx, [rbx+6Ah]; this
0x18000f672  lea     r8, aD3dcommonGetvi; "D3DCommon::GetVideoRegKey"
0x18000f679  lea     rdx, aPhkey; "phKey"
0x18000f680  call    ?ERR@D3DCommon@@YAXGZZ; D3DCommon::ERR(ushort,...)
0x18000f685  mov     eax, 80070057h
0x18000f68a  jmp     loc_18000F743
0x18000f68f  and     qword ptr [rcx], 0
0x18000f693  xor     edi, edi
0x18000f695  and     [rsp+3A0h+var_370], rdi
0x18000f69a  lea     rcx, [rsp+3A0h+DisplayDevice.DeviceName]; void *
0x18000f69f  and     [rsp+3A0h+var_368], rdi
0x18000f6a4  xor     esi, esi
0x18000f6a6  xor     edx, edx; Val
0x18000f6a8  mov     r8d, 344h; Size
0x18000f6ae  call    memset_0
0x18000f6b3  mov     [rsp+3A0h+DisplayDevice.cb], 348h
0x18000f6bb  xor     r9d, r9d; dwFlags
0x18000f6be  lea     r8, [rsp+3A0h+DisplayDevice]; lpDisplayDevice
0x18000f6c3  mov     edx, edi; iDevNum
0x18000f6c5  xor     ecx, ecx; lpDevice
0x18000f6c7  call    cs:__imp_EnumDisplayDevicesW
0x18000f6ce  nop     dword ptr [rax+rax+00h]
0x18000f6d3  test    eax, eax
0x18000f6d5  jz      short loc_18000F741
0x18000f6d7  test    byte ptr [rbp+2A0h+DisplayDevice.StateFlags], 4
0x18000f6de  jnz     short loc_18000F6E4
0x18000f6e0  inc     edi
0x18000f6e2  jmp     short loc_18000F6BB
0x18000f6e4  lea     r8, [rsp+3A0h+var_370]; unsigned __int64 *
0x18000f6e9  mov     edx, 80h; unsigned __int64
0x18000f6ee  lea     rcx, [rbp+2A0h+DisplayDevice.DeviceKey]; unsigned __int16 *
0x18000f6f5  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000f6fa  mov     esi, eax
0x18000f6fc  test    eax, eax
0x18000f6fe  js      short loc_18000F741
0x18000f700  cmp     [rsp+3A0h+var_370], 13h
0x18000f706  jb      short loc_18000F741
0x18000f708  lea     rax, [rsp+3A0h+var_368]
0x18000f70d  mov     r9d, 3; samDesired
0x18000f713  xor     r8d, r8d; ulOptions
0x18000f716  mov     [rsp+3A0h+phkResult], rax; phkResult
0x18000f71b  lea     rdx, [rbp+2A0h+DisplayDevice.DeviceKey+24h]; lpSubKey
0x18000f722  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000f729  call    cs:__imp_RegOpenKeyExW
0x18000f730  nop     dword ptr [rax+rax+00h]
0x18000f735  test    eax, eax
0x18000f737  jnz     short loc_18000F741
0x18000f739  mov     rax, [rsp+3A0h+var_368]
0x18000f73e  mov     [rbx], rax
0x18000f741  mov     eax, esi
0x18000f743  mov     rcx, [rbp+2A0h+var_10]
0x18000f74a  xor     rcx, rsp; StackCookie
0x18000f74d  call    __security_check_cookie
0x18000f752  lea     r11, [rsp+3A0h+var_s0]
0x18000f75a  mov     rbx, [r11+18h]
0x18000f75e  mov     rsi, [r11+20h]
0x18000f762  mov     rdi, [r11+28h]
0x18000f766  mov     rsp, r11
0x18000f769  pop     rbp
0x18000f76a  retn
```
