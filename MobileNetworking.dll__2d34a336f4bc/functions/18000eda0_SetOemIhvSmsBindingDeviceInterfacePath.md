# SetOemIhvSmsBindingDeviceInterfacePath

- ea: `0x18000eda0`
- end: `0x18000efb9`
- name: `SetOemIhvSmsBindingDeviceInterfacePath`
- size: `537`
- prototype: `__int64 __fastcall(unsigned __int16 *, const BYTE *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x180006000`
- `0x180008cb0`
- `0x180008ff0`
- `0x180009020`
- `0x180009850`
- `0x18000b6f4`
- `0x18000d978`
- `0x18000eda0`
- `0x18000efc0`

## string_xrefs

- `0x18000eed1`: `SmsDeviceBindingDeviceInterfacePath`

## pseudocode

```c
__int64 __fastcall SetOemIhvSmsBindingDeviceInterfacePath(unsigned __int16 *a1, const BYTE *a2)
{
  PVOID *v4; // rcx
  HKEY v5; // rdx
  unsigned int BindingRegistryPath; // ebx
  unsigned __int16 *v7; // r9
  int v8; // eax
  PVOID *v9; // rcx
  LSTATUS v10; // eax
  unsigned int v12; // [rsp+20h] [rbp-278h]
  HKEY v13[4]; // [rsp+40h] [rbp-258h] BYREF
  unsigned __int16 v14[264]; // [rsp+60h] [rbp-238h] BYREF

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_e12f368a0cb238e419f0d89ee3ed1f0e_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  memset(v13, 0, 24);
  if ( a1 && *a1 && a2 && *(_WORD *)a2 )
  {
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x10) != 0 )
      WPP_SF_SS(
        (unsigned int)v4[2],
        20,
        (unsigned int)&WPP_e12f368a0cb238e419f0d89ee3ed1f0e_Traceguids,
        (_DWORD)a1,
        (__int64)a2);
    BindingRegistryPath = GetBindingRegistryPath(a1, (__int64)a2, v14);
    if ( (BindingRegistryPath & 0x80000000) == 0 )
    {
      v8 = ATL::CRegKey::Create(v13, v5, v14, v7, v12, 0x2001Fu);
      if ( v8 )
      {
        if ( v8 > 0 )
          BindingRegistryPath = (unsigned __int16)v8 | 0x80070000;
        else
          BindingRegistryPath = v8;
        v9 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            21,
            &WPP_e12f368a0cb238e419f0d89ee3ed1f0e_Traceguids,
            BindingRegistryPath);
          v9 = (PVOID *)WPP_GLOBAL_Control;
        }
        goto LABEL_28;
      }
      v10 = ATL::CRegKey::SetStringValue(v13, L"SmsDeviceBindingDeviceInterfacePath", a2);
      if ( !v10 )
      {
        v9 = (PVOID *)WPP_GLOBAL_Control;
LABEL_30:
        if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 0x10) != 0 )
          WPP_SF_d(v9[2], 23, &WPP_e12f368a0cb238e419f0d89ee3ed1f0e_Traceguids, BindingRegistryPath);
        ATL::CRegKey::Close(v13);
        return BindingRegistryPath;
      }
      if ( v10 > 0 )
        BindingRegistryPath = (unsigned __int16)v10 | 0x80070000;
      else
        BindingRegistryPath = v10;
      v9 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      {
LABEL_28:
        if ( BindingRegistryPath == -2147024894 )
          BindingRegistryPath = -2147023728;
        goto LABEL_30;
      }
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        &WPP_e12f368a0cb238e419f0d89ee3ed1f0e_Traceguids,
        BindingRegistryPath);
    }
    v9 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_28;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 )
    WPP_SF_(v4[2], 19, &WPP_e12f368a0cb238e419f0d89ee3ed1f0e_Traceguids);
  ATL::CRegKey::Close(v13);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18000eda0  mov     [rsp+arg_10], rbx
0x18000eda5  mov     [rsp+arg_18], rbp
0x18000edaa  push    rsi
0x18000edab  push    rdi
0x18000edac  push    r14
0x18000edae  sub     rsp, 280h
0x18000edb5  mov     rax, cs:__security_cookie
0x18000edbc  xor     rax, rsp
0x18000edbf  mov     [rsp+298h+var_28], rax
0x18000edc7  mov     rdi, rdx
0x18000edca  mov     rbx, rcx
0x18000edcd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000edd4  lea     rbp, WPP_GLOBAL_Control
0x18000eddb  lea     r14, WPP_e12f368a0cb238e419f0d89ee3ed1f0e_Traceguids
0x18000ede2  cmp     rcx, rbp
0x18000ede5  jz      short loc_18000EE05
0x18000ede7  test    byte ptr [rcx+1Ch], 10h
0x18000edeb  jz      short loc_18000EE05
0x18000eded  mov     rcx, [rcx+10h]
0x18000edf1  mov     edx, 12h
0x18000edf6  mov     r8, r14
0x18000edf9  call    WPP_SF_
0x18000edfe  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ee05  xor     esi, esi
0x18000ee07  mov     [rsp+298h+var_258], rsi
0x18000ee0c  mov     [rsp+298h+var_250], rsi
0x18000ee11  mov     [rsp+298h+var_248], rsi
0x18000ee16  test    rbx, rbx
0x18000ee19  jz      loc_18000EF66
0x18000ee1f  cmp     [rbx], si
0x18000ee22  jz      loc_18000EF66
0x18000ee28  test    rdi, rdi
0x18000ee2b  jz      loc_18000EF66
0x18000ee31  cmp     [rdi], si
0x18000ee34  jz      loc_18000EF66
0x18000ee3a  cmp     rcx, rbp
0x18000ee3d  jz      short loc_18000EE5C
0x18000ee3f  test    byte ptr [rcx+1Ch], 10h
0x18000ee43  jz      short loc_18000EE5C
0x18000ee45  mov     rcx, [rcx+10h]
0x18000ee49  lea     edx, [rsi+14h]
0x18000ee4c  mov     r9, rbx
0x18000ee4f  mov     qword ptr [rsp+298h+var_278], rdi; unsigned int
0x18000ee54  mov     r8, r14
0x18000ee57  call    WPP_SF_SS
0x18000ee5c  lea     r8, [rsp+298h+var_238]; unsigned __int16 *
0x18000ee61  mov     rcx, rbx; unsigned __int16 *
0x18000ee64  call    ?GetBindingRegistryPath@@YAJPEBG_KPEAG@Z; GetBindingRegistryPath(ushort const *,unsigned __int64,ushort *)
0x18000ee69  mov     ebx, eax
0x18000ee6b  test    eax, eax
0x18000ee6d  js      loc_18000EF1B
0x18000ee73  lea     r8, [rsp+298h+var_238]; unsigned __int16 *
0x18000ee78  mov     [rsp+298h+var_270], 2001Fh; unsigned int
0x18000ee80  lea     rcx, [rsp+298h+var_258]; this
0x18000ee85  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x18000ee8a  test    eax, eax
0x18000ee8c  jz      short loc_18000EECE
0x18000ee8e  jg      short loc_18000EE94
0x18000ee90  mov     ebx, eax
0x18000ee92  jmp     short loc_18000EE9D
0x18000ee94  movzx   ebx, ax
0x18000ee97  or      ebx, 80070000h
0x18000ee9d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eea4  cmp     rcx, rbp
0x18000eea7  jz      short loc_18000EECA
0x18000eea9  test    byte ptr [rcx+1Ch], 2
0x18000eead  jz      short loc_18000EECA
0x18000eeaf  mov     rcx, [rcx+10h]
0x18000eeb3  mov     edx, 15h
0x18000eeb8  mov     r9d, ebx
0x18000eebb  mov     r8, r14
0x18000eebe  call    WPP_SF_d
0x18000eec3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eeca  test    ebx, ebx
0x18000eecc  js      short loc_18000EF22
0x18000eece  mov     r8, rdi; unsigned __int16 *
0x18000eed1  lea     rdx, aSmsdevicebindi; "SmsDeviceBindingDeviceInterfacePath"
0x18000eed8  lea     rcx, [rsp+298h+var_258]; this
0x18000eedd  call    ?SetStringValue@CRegKey@ATL@@QEAAJPEBG0K@Z; ATL::CRegKey::SetStringValue(ushort const *,ushort const *,ulong)
0x18000eee2  test    eax, eax
0x18000eee4  jz      short loc_18000EF5D
0x18000eee6  jg      short loc_18000EEEC
0x18000eee8  mov     ebx, eax
0x18000eeea  jmp     short loc_18000EEF5
0x18000eeec  movzx   ebx, ax
0x18000eeef  or      ebx, 80070000h
0x18000eef5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eefc  cmp     rcx, rbp
0x18000eeff  jz      short loc_18000EF22
0x18000ef01  test    byte ptr [rcx+1Ch], 2
0x18000ef05  jz      short loc_18000EF22
0x18000ef07  mov     rcx, [rcx+10h]
0x18000ef0b  mov     edx, 16h
0x18000ef10  mov     r9d, ebx
0x18000ef13  mov     r8, r14
0x18000ef16  call    WPP_SF_d
0x18000ef1b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ef22  cmp     ebx, 80070002h
0x18000ef28  mov     eax, 80070490h
0x18000ef2d  cmovz   ebx, eax
0x18000ef30  cmp     rcx, rbp
0x18000ef33  jz      short loc_18000EF4F
0x18000ef35  test    byte ptr [rcx+1Ch], 10h
0x18000ef39  jz      short loc_18000EF4F
0x18000ef3b  mov     rcx, [rcx+10h]
0x18000ef3f  mov     edx, 17h
0x18000ef44  mov     r9d, ebx
0x18000ef47  mov     r8, r14
0x18000ef4a  call    WPP_SF_d
0x18000ef4f  lea     rcx, [rsp+298h+var_258]; this
0x18000ef54  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000ef59  mov     eax, ebx
0x18000ef5b  jmp     short loc_18000EF91
0x18000ef5d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ef64  jmp     short loc_18000EF30
0x18000ef66  cmp     rcx, rbp
0x18000ef69  jz      short loc_18000EF82
0x18000ef6b  test    byte ptr [rcx+1Ch], 2
0x18000ef6f  jz      short loc_18000EF82
0x18000ef71  mov     rcx, [rcx+10h]
0x18000ef75  mov     edx, 13h
0x18000ef7a  mov     r8, r14
0x18000ef7d  call    WPP_SF_
0x18000ef82  lea     rcx, [rsp+298h+var_258]; this
0x18000ef87  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000ef8c  mov     eax, 80070057h
0x18000ef91  mov     rcx, [rsp+298h+var_28]
0x18000ef99  xor     rcx, rsp; StackCookie
0x18000ef9c  call    __security_check_cookie
0x18000efa1  lea     r11, [rsp+298h+var_18]
0x18000efa9  mov     rbx, [r11+30h]
0x18000efad  mov     rbp, [r11+38h]
0x18000efb1  mov     rsp, r11
0x18000efb4  pop     r14
0x18000efb6  pop     rdi
0x18000efb7  pop     rsi
0x18000efb8  retn
```
