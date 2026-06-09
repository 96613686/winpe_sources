# _anonymous_namespace_::GetDeviceRegistryProperty

- ea: `0x14006f04c`
- end: `0x14006f153`
- name: `_anonymous_namespace_::GetDeviceRegistryProperty`
- size: `263`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x14006ef04`

## callees

- `0x140004e68`
- `0x140005f30`
- `0x14000d850`
- `0x140068160`
- `0x14006f04c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14006f0cf`
- `KERNEL32!GetLastError` at `0x14006f0cf`
- `SETUPAPI!SetupDiGetDeviceRegistryPropertyW` at `0x14006f0c5`
- `SETUPAPI!SetupDiGetDeviceRegistryPropertyW` at `0x14006f0c5`

## string_xrefs

- `0x14006f108`: `pcshell\shell\systemsettings\adminflows\accessibility\narratoradminflowhandler.cpp`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::GetDeviceRegistryProperty(__int64 a1, HDEVINFO *a2, _OWORD *a3)
{
  __int128 v5; // xmm1
  signed int LastError; // eax
  unsigned __int64 v7; // r9
  BYTE *v8; // rdx
  int PropertyBuffer; // [rsp+20h] [rbp-868h]
  struct _SP_DEVINFO_DATA DeviceInfoData; // [rsp+50h] [rbp-838h] BYREF
  BYTE v12[2048]; // [rsp+70h] [rbp-818h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+888h] [rbp+0h]

  v5 = a3[1];
  *(_OWORD *)&DeviceInfoData.cbSize = *a3;
  *(_OWORD *)&DeviceInfoData.ClassGuid.Data4[4] = v5;
  memset_0(v12, 0, sizeof(v12));
  if ( SetupDiGetDeviceRegistryPropertyW(*a2, &DeviceInfoData, 1u, 0, v12, 0x800u, 0) )
  {
    v8 = v12;
  }
  else
  {
    LastError = GetLastError();
    v7 = (unsigned int)LastError;
    if ( (LastError & 0xE0000000) == 0xE0000000 )
    {
      v7 = (unsigned __int16)LastError | 0x800F0000;
    }
    else if ( LastError > 0 )
    {
      v7 = (unsigned __int16)LastError | 0x80070000;
    }
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x38,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\accessibility\\narratoradminflowhandler.cpp",
      (const char *)v7,
      PropertyBuffer);
    v8 = (BYTE *)&Data;
  }
  std::wstring::wstring(a1, (__int64)v8);
  return a1;
}

```

## disassembly

```asm
0x14006f04c  mov     [rsp+arg_18], rbx
0x14006f051  push    rdi
0x14006f052  sub     rsp, 880h
0x14006f059  mov     rax, cs:__security_cookie
0x14006f060  xor     rax, rsp
0x14006f063  mov     [rsp+888h+var_18], rax
0x14006f06b  movups  xmm0, xmmword ptr [r8]
0x14006f06f  mov     rbx, rdx
0x14006f072  mov     rdi, rcx
0x14006f075  movups  xmm1, xmmword ptr [r8+10h]
0x14006f07a  mov     [rsp+888h+var_840], rcx
0x14006f07f  xor     edx, edx; Val
0x14006f081  mov     r8d, 800h; Size
0x14006f087  lea     rcx, [rsp+888h+var_818]; void *
0x14006f08c  movups  xmmword ptr [rsp+888h+DeviceInfoData.cbSize], xmm0
0x14006f091  movups  xmmword ptr [rsp+888h+DeviceInfoData.ClassGuid.Data4+4], xmm1
0x14006f096  call    memset_0
0x14006f09b  mov     rcx, [rbx]; DeviceInfoSet
0x14006f09e  lea     rax, [rsp+888h+var_818]
0x14006f0a3  xor     r9d, r9d; PropertyRegDataType
0x14006f0a6  mov     [rsp+888h+RequiredSize], 0; RequiredSize
0x14006f0af  mov     [rsp+888h+PropertyBufferSize], 800h; PropertyBufferSize
0x14006f0b7  lea     rdx, [rsp+888h+DeviceInfoData]; DeviceInfoData
0x14006f0bc  mov     [rsp+888h+PropertyBuffer], rax; int
0x14006f0c1  lea     r8d, [r9+1]; Property
0x14006f0c5  call    cs:__imp_SetupDiGetDeviceRegistryPropertyW
0x14006f0cb  test    eax, eax
0x14006f0cd  jnz     short loc_14006F122
0x14006f0cf  call    cs:__imp_GetLastError
0x14006f0d5  mov     ecx, 0E0000000h
0x14006f0da  mov     r9d, eax
0x14006f0dd  and     eax, ecx
0x14006f0df  cmp     eax, ecx
0x14006f0e1  jnz     short loc_14006F0F0
0x14006f0e3  movzx   r9d, r9w
0x14006f0e7  or      r9d, 800F0000h
0x14006f0ee  jmp     short loc_14006F100
0x14006f0f0  test    r9d, r9d
0x14006f0f3  jle     short loc_14006F100
0x14006f0f5  movzx   r9d, r9w
0x14006f0f9  or      r9d, 80070000h; char *
0x14006f100  mov     rcx, [rsp+888h]; this
0x14006f108  lea     r8, aPcshellShellSy_31; "pcshell\\shell\\systemsettings\\adminfl"...
0x14006f10f  mov     edx, 38h ; '8'; void *
0x14006f114  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x14006f119  lea     rdx, Data
0x14006f120  jmp     short loc_14006F127
0x14006f122  lea     rdx, [rsp+888h+var_818]
0x14006f127  mov     rcx, rdi
0x14006f12a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x14006f12f  mov     rax, rdi
0x14006f132  mov     rcx, [rsp+888h+var_18]
0x14006f13a  xor     rcx, rsp; StackCookie
0x14006f13d  call    __security_check_cookie
0x14006f142  mov     rbx, [rsp+888h+arg_18]
0x14006f14a  add     rsp, 880h
0x14006f151  pop     rdi
0x14006f152  retn
```
