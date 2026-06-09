# UnbindNetworkInterfaceId

- ea: `0x18000f160`
- end: `0x18000f301`
- name: `UnbindNetworkInterfaceId`
- size: `417`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180006000`
- `0x180008cb0`
- `0x180008ff0`
- `0x180009850`
- `0x18000b6f4`
- `0x18000d978`
- `0x18000f160`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000f255`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000f255`

## pseudocode

```c
__int64 __fastcall UnbindNetworkInterfaceId(unsigned __int16 *a1, unsigned __int64 a2)
{
  unsigned int BindingRegistryPath; // ebx
  HKEY v4; // rdx
  unsigned __int16 *v5; // r9
  int v6; // eax
  LSTATUS v7; // eax
  signed int v8; // ecx
  unsigned int v10; // [rsp+20h] [rbp-268h]
  struct _SECURITY_ATTRIBUTES *v11; // [rsp+30h] [rbp-258h]
  unsigned int *v12; // [rsp+38h] [rbp-250h]
  HKEY hKey[4]; // [rsp+40h] [rbp-248h] BYREF
  unsigned __int16 v14[264]; // [rsp+60h] [rbp-228h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_3472e6cad6ce3ca55177cef16c8003e1_Traceguids);
  memset(hKey, 0, 24);
  if ( a1 )
  {
    BindingRegistryPath = GetBindingRegistryPath(a1, a2, v14);
    if ( (BindingRegistryPath & 0x80000000) == 0 )
    {
      v6 = ATL::CRegKey::Create((ATL::CRegKey *)hKey, v4, v14, v5, v10, 0x20006u, v11, v12);
      if ( v6 )
      {
        if ( v6 > 0 )
          BindingRegistryPath = (unsigned __int16)v6 | 0x80070000;
        else
          BindingRegistryPath = v6;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            11,
            WPP_3472e6cad6ce3ca55177cef16c8003e1_Traceguids,
            BindingRegistryPath);
      }
      else
      {
        v7 = RegDeleteValueW(hKey[0], L"NetworkAccountId");
        v8 = 0;
        if ( v7 != 2 )
          v8 = v7;
        if ( v8 )
        {
          BindingRegistryPath = v8 > 0 ? (unsigned __int16)v8 | 0x80070000 : v8;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              12,
              WPP_3472e6cad6ce3ca55177cef16c8003e1_Traceguids,
              BindingRegistryPath);
        }
      }
    }
    ATL::CRegKey::Close((ATL::CRegKey *)hKey);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        WPP_3472e6cad6ce3ca55177cef16c8003e1_Traceguids,
        BindingRegistryPath);
  }
  else
  {
    BindingRegistryPath = -2147024809;
  }
  ATL::CRegKey::Close((ATL::CRegKey *)hKey);
  return BindingRegistryPath;
}

```

## disassembly

```asm
0x18000f160  mov     [rsp+arg_8], rbx
0x18000f165  push    rsi
0x18000f166  sub     rsp, 280h
0x18000f16d  mov     rax, cs:__security_cookie
0x18000f174  xor     rax, rsp
0x18000f177  mov     [rsp+288h+var_18], rax
0x18000f17f  mov     rbx, rcx
0x18000f182  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f189  lea     rsi, WPP_GLOBAL_Control
0x18000f190  cmp     rcx, rsi
0x18000f193  jz      short loc_18000F1B0
0x18000f195  test    byte ptr [rcx+1Ch], 10h
0x18000f199  jz      short loc_18000F1B0
0x18000f19b  mov     rcx, [rcx+10h]
0x18000f19f  lea     r8, WPP_3472e6cad6ce3ca55177cef16c8003e1_Traceguids
0x18000f1a6  mov     edx, 0Ah
0x18000f1ab  call    WPP_SF_
0x18000f1b0  mov     [rsp+288h+hKey], 0
0x18000f1b9  mov     [rsp+288h+var_240], 0
0x18000f1c2  mov     [rsp+288h+var_238], 0
0x18000f1cb  test    rbx, rbx
0x18000f1ce  jnz     short loc_18000F1DA
0x18000f1d0  mov     ebx, 80070057h
0x18000f1d5  jmp     loc_18000F2D4
0x18000f1da  lea     r8, [rsp+288h+var_228]; unsigned __int16 *
0x18000f1df  mov     rcx, rbx; unsigned __int16 *
0x18000f1e2  call    ?GetBindingRegistryPath@@YAJPEBG_KPEAG@Z; GetBindingRegistryPath(ushort const *,unsigned __int64,ushort *)
0x18000f1e7  mov     ebx, eax
0x18000f1e9  test    eax, eax
0x18000f1eb  js      loc_18000F2A0
0x18000f1f1  lea     r8, [rsp+288h+var_228]; unsigned __int16 *
0x18000f1f6  mov     [rsp+288h+var_260], 20006h; unsigned int
0x18000f1fe  lea     rcx, [rsp+288h+hKey]; this
0x18000f203  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x18000f208  test    eax, eax
0x18000f20a  jz      short loc_18000F249
0x18000f20c  jg      short loc_18000F212
0x18000f20e  mov     ebx, eax
0x18000f210  jmp     short loc_18000F21B
0x18000f212  movzx   ebx, ax
0x18000f215  or      ebx, 80070000h
0x18000f21b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f222  cmp     rcx, rsi
0x18000f225  jz      short loc_18000F245
0x18000f227  test    byte ptr [rcx+1Ch], 2
0x18000f22b  jz      short loc_18000F245
0x18000f22d  mov     rcx, [rcx+10h]
0x18000f231  lea     r8, WPP_3472e6cad6ce3ca55177cef16c8003e1_Traceguids
0x18000f238  mov     edx, 0Bh
0x18000f23d  mov     r9d, ebx
0x18000f240  call    WPP_SF_d
0x18000f245  test    ebx, ebx
0x18000f247  js      short loc_18000F2A0
0x18000f249  mov     rcx, [rsp+288h+hKey]; hKey
0x18000f24e  lea     rdx, ValueName; "NetworkAccountId"
0x18000f255  call    cs:__imp_RegDeleteValueW
0x18000f25b  xor     ecx, ecx
0x18000f25d  cmp     eax, 2
0x18000f260  cmovnz  ecx, eax
0x18000f263  test    ecx, ecx
0x18000f265  jz      short loc_18000F2A0
0x18000f267  jg      short loc_18000F26D
0x18000f269  mov     ebx, ecx
0x18000f26b  jmp     short loc_18000F276
0x18000f26d  movzx   ebx, cx
0x18000f270  or      ebx, 80070000h
0x18000f276  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f27d  cmp     rcx, rsi
0x18000f280  jz      short loc_18000F2A0
0x18000f282  test    byte ptr [rcx+1Ch], 2
0x18000f286  jz      short loc_18000F2A0
0x18000f288  mov     rcx, [rcx+10h]
0x18000f28c  lea     r8, WPP_3472e6cad6ce3ca55177cef16c8003e1_Traceguids
0x18000f293  mov     edx, 0Ch
0x18000f298  mov     r9d, ebx
0x18000f29b  call    WPP_SF_d
0x18000f2a0  lea     rcx, [rsp+288h+hKey]; this
0x18000f2a5  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000f2aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f2b1  cmp     rcx, rsi
0x18000f2b4  jz      short loc_18000F2D4
0x18000f2b6  test    byte ptr [rcx+1Ch], 10h
0x18000f2ba  jz      short loc_18000F2D4
0x18000f2bc  mov     rcx, [rcx+10h]
0x18000f2c0  lea     r8, WPP_3472e6cad6ce3ca55177cef16c8003e1_Traceguids
0x18000f2c7  mov     edx, 0Dh
0x18000f2cc  mov     r9d, ebx
0x18000f2cf  call    WPP_SF_d
0x18000f2d4  lea     rcx, [rsp+288h+hKey]; this
0x18000f2d9  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000f2de  mov     eax, ebx
0x18000f2e0  mov     rcx, [rsp+288h+var_18]
0x18000f2e8  xor     rcx, rsp; StackCookie
0x18000f2eb  call    __security_check_cookie
0x18000f2f0  mov     rbx, [rsp+288h+arg_8]
0x18000f2f8  add     rsp, 280h
0x18000f2ff  pop     rsi
0x18000f300  retn
```
