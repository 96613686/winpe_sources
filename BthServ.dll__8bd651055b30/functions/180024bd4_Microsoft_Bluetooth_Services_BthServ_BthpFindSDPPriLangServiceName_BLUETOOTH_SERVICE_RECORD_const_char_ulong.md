# Microsoft::Bluetooth::Services::BthServ::BthpFindSDPPriLangServiceName(_BLUETOOTH_SERVICE_RECORD const *,char *,ulong)

- ea: `0x180024bd4`
- end: `0x180024ca2`
- name: `?BthpFindSDPPriLangServiceName@BthServ@Services@Bluetooth@Microsoft@@YAKPEBU_BLUETOOTH_SERVICE_RECORD@@PEADK@Z`
- size: `206`
- prototype: `unsigned int(Microsoft::Bluetooth::Services::BthServ *__hidden this, const struct _BLUETOOTH_SERVICE_RECORD *, char *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180025e24`

## callees

- `0x180001790`
- `0x1800024ac`
- `0x180024bd4`
- `0x180029084`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024c77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024c77`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180024c6d`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180024c6d`

## pseudocode

```c
__int64 __fastcall Microsoft::Bluetooth::Services::BthServ::BthpFindSDPPriLangServiceName(
        Microsoft::Bluetooth::Services::BthServ *this,
        const struct _BLUETOOTH_SERVICE_RECORD *a2,
        char *a3)
{
  unsigned __int8 *v5; // rdx
  struct IMultiLanguage2 *v6; // rcx
  __int64 v7; // r8
  unsigned int String; // ebx
  int cchWideChar[4]; // [rsp+40h] [rbp-228h] BYREF
  WCHAR WideCharStr[256]; // [rsp+50h] [rbp-218h] BYREF

  memset_0(a2, 0, 0x100u);
  v5 = (unsigned __int8 *)*((unsigned int *)this + 4);
  v6 = (struct IMultiLanguage2 *)*((_QWORD *)this + 1);
  cchWideChar[0] = 256;
  String = Microsoft::Bluetooth::Services::BthServ::BluetoothSdpGetString(
             v6,
             v5,
             v7,
             0,
             (__int64)WideCharStr,
             (unsigned __int16 *)cchWideChar);
  if ( !String && !WideCharToMultiByte(0xFDE9u, 0x80u, WideCharStr, cchWideChar[0], (LPSTR)a2, 256, 0, 0) )
    return GetLastError();
  return String;
}

```

## disassembly

```asm
0x180024bd4  mov     [rsp+arg_10], rbx
0x180024bd9  push    rdi
0x180024bda  sub     rsp, 260h
0x180024be1  mov     rax, cs:__security_cookie
0x180024be8  xor     rax, rsp
0x180024beb  mov     [rsp+268h+var_18], rax
0x180024bf3  mov     rdi, rdx
0x180024bf6  mov     rbx, rcx
0x180024bf9  mov     rcx, rdi; void *
0x180024bfc  xor     edx, edx; Val
0x180024bfe  mov     r8d, 100h; Size
0x180024c04  call    memset_0
0x180024c09  mov     edx, [rbx+10h]; unsigned __int8 *
0x180024c0c  lea     rax, [rsp+268h+cchWideChar]
0x180024c11  mov     rcx, [rbx+8]; this
0x180024c15  xor     r9d, r9d; struct _SDP_STRING_TYPE_DATA *
0x180024c18  mov     qword ptr [rsp+268h+cbMultiByte], rax; unsigned __int16 *
0x180024c1d  lea     rax, [rsp+268h+WideCharStr]
0x180024c22  mov     [rsp+268h+lpMultiByteStr], rax; unsigned __int16
0x180024c27  mov     [rsp+268h+cchWideChar], 100h
0x180024c2f  call    ?BluetoothSdpGetString@BthServ@Services@Bluetooth@Microsoft@@YAKPEAEKPEAU_SDP_STRING_TYPE_DATA@@GPEAGPEAK@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothSdpGetString(uchar *,ulong,_SDP_STRING_TYPE_DATA *,ushort,ushort *,ulong *)
0x180024c34  mov     ebx, eax
0x180024c36  test    eax, eax
0x180024c38  jnz     short loc_180024C7F
0x180024c3a  mov     r9d, [rsp+268h+cchWideChar]; cchWideChar
0x180024c3f  lea     r8, [rsp+268h+WideCharStr]; lpWideCharStr
0x180024c44  mov     [rsp+268h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180024c4d  mov     edx, 80h; dwFlags
0x180024c52  mov     [rsp+268h+lpDefaultChar], 0; lpDefaultChar
0x180024c5b  mov     ecx, 0FDE9h; CodePage
0x180024c60  mov     [rsp+268h+cbMultiByte], 100h; cbMultiByte
0x180024c68  mov     [rsp+268h+lpMultiByteStr], rdi; lpMultiByteStr
0x180024c6d  call    cs:__imp_WideCharToMultiByte
0x180024c73  test    eax, eax
0x180024c75  jnz     short loc_180024C7F
0x180024c77  call    cs:__imp_GetLastError
0x180024c7d  mov     ebx, eax
0x180024c7f  mov     eax, ebx
0x180024c81  mov     rcx, [rsp+268h+var_18]
0x180024c89  xor     rcx, rsp; StackCookie
0x180024c8c  call    __security_check_cookie
0x180024c91  mov     rbx, [rsp+268h+arg_10]
0x180024c99  add     rsp, 260h
0x180024ca0  pop     rdi
0x180024ca1  retn
```
