# OOBEUserAutologon::SetAutologon(ushort const *,uchar const *,ulong,int,int)

- ea: `0x18001f030`
- end: `0x18001f162`
- name: `?SetAutologon@OOBEUserAutologon@@UEAAJPEBGPEBEKHH@Z`
- size: `306`
- prototype: `int(OOBEUserAutologon *__hidden this, const unsigned __int16 *, const unsigned __int8 *, unsigned int, int, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180007134`
- `0x180015434`
- `0x180018c98`
- `0x18001b61c`
- `0x18001ee68`
- `0x18001f030`
- `0x18001f168`
- `0x18002d5fc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18001f063`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18001f063`

## string_xrefs

- `0x18001f071`: `shell\oobe\user\dll\oobeuserautologon.cpp`
- `0x18001f0bb`: `shell\oobe\user\dll\oobeuserautologon.cpp`

## pseudocode

```c
__int64 __fastcall OOBEUserAutologon::SetAutologon(
        OOBEUserAutologon *this,
        const unsigned __int16 *a2,
        const unsigned __int8 *a3,
        int a4,
        int a5,
        int a6)
{
  unsigned int v9; // ebx
  int v10; // eax
  __int64 v11; // rdx
  int v13; // [rsp+20h] [rbp-20h]
  HKEY phkResult[2]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]

  phkResult[0] = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    phkResult,
    0);
  if ( RegOpenCurrentUser(0xF003Fu, phkResult) )
  {
    v9 = -2147024891;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C,
      (unsigned int)"shell\\oobe\\user\\dll\\oobeuserautologon.cpp",
      (const char *)0x80070005LL,
      v13);
  }
  else
  {
    v10 = SHRegSetString(
            phkResult[0],
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\UserOOBE",
            L"AutologonSigninName",
            a2);
    v9 = v10;
    if ( v10 >= 0 )
    {
      v10 = SHRegSetBOOL(
              phkResult[0],
              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\UserOOBE",
              L"AutologonIsConnected",
              a5);
      v9 = v10;
      if ( v10 >= 0 )
      {
        v13 = a4;
        v10 = SHRegSetBinaryData(
                phkResult[0],
                L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\UserOOBE",
                L"AutologonAuthenticationBuffer",
                a3);
        v9 = v10;
        if ( v10 >= 0 )
        {
          v10 = SHRegSetBOOL(
                  phkResult[0],
                  L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\UserOOBE",
                  L"AutologonPreserveOobeAutologonCredentials",
                  a6);
          v9 = v10;
          if ( v10 >= 0 )
          {
            v9 = 0;
            goto LABEL_13;
          }
          v11 = 36;
        }
        else
        {
          v11 = 35;
        }
      }
      else
      {
        v11 = 34;
      }
    }
    else
    {
      v11 = 33;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"shell\\oobe\\user\\dll\\oobeuserautologon.cpp",
      (const char *)(unsigned int)v10,
      v13);
    ClearCachedAutologonSettings(L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\UserOOBE", phkResult[0]);
  }
LABEL_13:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(phkResult);
  return v9;
}

```

## disassembly

```asm
0x18001f030  push    rbp
0x18001f032  push    rbx
0x18001f033  push    rsi
0x18001f034  push    rdi
0x18001f035  push    r14
0x18001f037  mov     rbp, rsp
0x18001f03a  sub     rsp, 40h
0x18001f03e  mov     rbx, rdx
0x18001f041  mov     [rbp+phkResult], 0
0x18001f049  xor     edx, edx
0x18001f04b  lea     rcx, [rbp+phkResult]
0x18001f04f  mov     edi, r9d
0x18001f052  mov     rsi, r8
0x18001f055  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18001f05a  lea     rdx, [rbp+phkResult]; phkResult
0x18001f05e  mov     ecx, 0F003Fh; samDesired
0x18001f063  call    cs:__imp_RegOpenCurrentUser
0x18001f069  test    eax, eax
0x18001f06b  jz      short loc_18001F08F
0x18001f06d  mov     rcx, [rbp+28h]; this
0x18001f071  lea     r8, aShellOobeUserD_4; "shell\\oobe\\user\\dll\\oobeuserautolog"...
0x18001f078  mov     ebx, 80070005h
0x18001f07d  mov     edx, 1Ch; void *
0x18001f082  mov     r9d, ebx; char *
0x18001f085  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f08a  jmp     loc_18001F14C
0x18001f08f  mov     rcx, [rbp+phkResult]; HKEY
0x18001f093  lea     r14, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001f09a  mov     rdx, r14; unsigned __int16 *
0x18001f09d  lea     r8, aAutologonsigni; "AutologonSigninName"
0x18001f0a4  mov     r9, rbx; unsigned __int16 *
0x18001f0a7  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18001f0ac  mov     ebx, eax
0x18001f0ae  test    eax, eax
0x18001f0b0  jns     short loc_18001F0D8
0x18001f0b2  mov     edx, 21h ; '!'; void *
0x18001f0b7  mov     rcx, [rbp+28h]; this
0x18001f0bb  lea     r8, aShellOobeUserD_4; "shell\\oobe\\user\\dll\\oobeuserautolog"...
0x18001f0c2  mov     r9d, eax; char *
0x18001f0c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f0ca  mov     rdx, [rbp+phkResult]; HKEY
0x18001f0ce  mov     rcx, r14; pszSubKey
0x18001f0d1  call    ?ClearCachedAutologonSettings@@YAXPEBGPEAUHKEY__@@@Z; ClearCachedAutologonSettings(ushort const *,HKEY__ *)
0x18001f0d6  jmp     short loc_18001F14C
0x18001f0d8  mov     r9d, [rbp+arg_20]; int
0x18001f0dc  lea     r8, aAutologoniscon; "AutologonIsConnected"
0x18001f0e3  mov     rcx, [rbp+phkResult]; HKEY
0x18001f0e7  mov     rdx, r14; unsigned __int16 *
0x18001f0ea  call    ?SHRegSetBOOL@@YAJPEAUHKEY__@@PEBG1H@Z; SHRegSetBOOL(HKEY__ *,ushort const *,ushort const *,int)
0x18001f0ef  mov     ebx, eax
0x18001f0f1  test    eax, eax
0x18001f0f3  jns     short loc_18001F0FC
0x18001f0f5  mov     edx, 22h ; '"'
0x18001f0fa  jmp     short loc_18001F0B7
0x18001f0fc  mov     rcx, [rbp+phkResult]
0x18001f100  lea     r8, aAutologonauthe; "AutologonAuthenticationBuffer"
0x18001f107  mov     r9, rsi
0x18001f10a  mov     [rsp+40h+var_20], edi
0x18001f10e  mov     rdx, r14
0x18001f111  call    SHRegSetBinaryData
0x18001f116  mov     ebx, eax
0x18001f118  test    eax, eax
0x18001f11a  jns     short loc_18001F123
0x18001f11c  mov     edx, 23h ; '#'
0x18001f121  jmp     short loc_18001F0B7
0x18001f123  mov     r9d, [rbp+arg_28]; int
0x18001f127  lea     r8, aAutologonprese; "AutologonPreserveOobeAutologonCredentia"...
0x18001f12e  mov     rcx, [rbp+phkResult]; HKEY
0x18001f132  mov     rdx, r14; unsigned __int16 *
0x18001f135  call    ?SHRegSetBOOL@@YAJPEAUHKEY__@@PEBG1H@Z; SHRegSetBOOL(HKEY__ *,ushort const *,ushort const *,int)
0x18001f13a  mov     ebx, eax
0x18001f13c  test    eax, eax
0x18001f13e  jns     short loc_18001F14A
0x18001f140  mov     edx, 24h ; '$'
0x18001f145  jmp     loc_18001F0B7
0x18001f14a  xor     ebx, ebx
0x18001f14c  lea     rcx, [rbp+phkResult]
0x18001f150  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001f155  mov     eax, ebx
0x18001f157  add     rsp, 40h
0x18001f15b  pop     r14
0x18001f15d  pop     rdi
0x18001f15e  pop     rsi
0x18001f15f  pop     rbx
0x18001f160  pop     rbp
0x18001f161  retn
```
