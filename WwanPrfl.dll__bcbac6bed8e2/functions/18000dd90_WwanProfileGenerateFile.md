# WwanProfileGenerateFile

- ea: `0x18000dd90`
- end: `0x18000de8d`
- name: `WwanProfileGenerateFile`
- size: `253`
- prototype: `__int64 __fastcall(OLECHAR *, __int64, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001670`
- `0x180009b30`
- `0x18000d2c4`
- `0x18000dd90`
- `0x18000e050`
- `0x1800125a4`
- `0x180014010`

## string_xrefs

- `0x18000dde9`: `xmlns:MBNProfile='http://www.microsoft.com/networking/WWAN/profile/v1' xmlns:MBNProfileV2='http://www.microsoft.com/networking/WWAN/profile/v2' xmlns:MBNProfileV3='http://www.microsoft.com/networking/WWAN/profile/v3' xmlns:MBNProfileV4='http://www.microsoft.com/networking/WWAN/profile/v4' xmlns:MBNProfileV5='http://www.microsoft.com/networking/WWAN/profile/v5' xmlns:MBNProfileV6='http://www.microsoft.com/networking/WWAN/profile/v6' xmlns:MBNProfileV7='http://www.microsoft.com/networking/WWAN/pro`

## pseudocode

```c
__int64 __fastcall WwanProfileGenerateFile(OLECHAR *a1, __int64 a2, int a3)
{
  __int64 result; // rax
  unsigned int v5; // ebx
  struct IXMLDOMDocument2 *v6; // rbx
  unsigned int Profile; // edi
  struct IXMLDOMDocument2 *v8; // [rsp+20h] [rbp-248h] BYREF
  unsigned __int16 v9[264]; // [rsp+30h] [rbp-238h] BYREF

  v8 = 0;
  *((_DWORD *)a1 + 981) = a3;
  result = WwanProfileGetPath(a2, v9, 0x104u);
  if ( !(_DWORD)result )
  {
    v5 = XcCreateXmlDoc(
           (OLECHAR *)L"xmlns:MBNProfile='http://www.microsoft.com/networking/WWAN/profile/v1' xmlns:MBNProfileV2='http://"
                       "www.microsoft.com/networking/WWAN/profile/v2' xmlns:MBNProfileV3='http://www.microsoft.com/networ"
                       "king/WWAN/profile/v3' xmlns:MBNProfileV4='http://www.microsoft.com/networking/WWAN/profile/v4' xm"
                       "lns:MBNProfileV5='http://www.microsoft.com/networking/WWAN/profile/v5' xmlns:MBNProfileV6='http:/"
                       "/www.microsoft.com/networking/WWAN/profile/v6' xmlns:MBNProfileV7='http://www.microsoft.com/netwo"
                       "rking/WWAN/profile/v7' xmlns:MBNProfileV8='http://www.microsoft.com/networking/WWAN/profile/v8' x"
                       "mlns:MBNProfileV9='http://www.microsoft.com/networking/WWAN/profile/v9' ",
           0,
           &v8);
    if ( v5 )
    {
      if ( v8 )
        ((void (__fastcall *)(struct IXMLDOMDocument2 *))v8->lpVtbl->Release)(v8);
      return v5;
    }
    else
    {
      v6 = v8;
      Profile = generateProfile(v8, a1);
      if ( Profile )
      {
        if ( v6 )
          ((void (__fastcall *)(struct IXMLDOMDocument2 *))v6->lpVtbl->Release)(v6);
      }
      else
      {
        Profile = saveProfileXmlIndented(v6, v9);
        if ( v6 )
          ((void (__fastcall *)(struct IXMLDOMDocument2 *))v6->lpVtbl->Release)(v6);
      }
      return Profile;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000dd90  push    rbx
0x18000dd92  push    rsi
0x18000dd93  push    rdi
0x18000dd94  sub     rsp, 250h
0x18000dd9b  mov     rax, cs:__security_cookie
0x18000dda2  xor     rax, rsp
0x18000dda5  mov     [rsp+268h+var_28], rax
0x18000ddad  mov     esi, r9d
0x18000ddb0  mov     rax, rdx
0x18000ddb3  mov     rdi, rcx
0x18000ddb6  mov     [rsp+268h+var_248], 0
0x18000ddbf  mov     [rcx+0F54h], r8d
0x18000ddc6  mov     r8d, 104h
0x18000ddcc  lea     rdx, [rsp+268h+var_238]
0x18000ddd1  mov     rcx, rax
0x18000ddd4  call    WwanProfileGetPath
0x18000ddd9  test    eax, eax
0x18000dddb  jz      short loc_18000DDE2
0x18000dddd  jmp     loc_18000DE72
0x18000dde2  lea     r8, [rsp+268h+var_248]; struct IXMLDOMDocument2 **
0x18000dde7  xor     edx, edx; struct IXMLDOMSchemaCollection *
0x18000dde9  lea     rcx, aXmlnsMbnprofil; "xmlns:MBNProfile='http://www.microsoft."...
0x18000ddf0  call    ?XcCreateXmlDoc@@YAKPEBGPEAUIXMLDOMSchemaCollection@@PEAPEAUIXMLDOMDocument2@@@Z; XcCreateXmlDoc(ushort const *,IXMLDOMSchemaCollection *,IXMLDOMDocument2 * *)
0x18000ddf5  mov     ebx, eax
0x18000ddf7  test    eax, eax
0x18000ddf9  jz      short loc_18000DE16
0x18000ddfb  mov     rcx, [rsp+268h+var_248]
0x18000de00  test    rcx, rcx
0x18000de03  jz      short loc_18000DE12
0x18000de05  mov     rdx, [rcx]
0x18000de08  mov     rax, [rdx+10h]
0x18000de0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de11  nop
0x18000de12  mov     eax, ebx
0x18000de14  jmp     short loc_18000DE72
0x18000de16  mov     r9d, esi
0x18000de19  mov     r8d, 1
0x18000de1f  mov     rdx, rdi; OLECHAR *
0x18000de22  mov     rbx, [rsp+268h+var_248]
0x18000de27  mov     rcx, rbx; struct IXMLDOMDocument2 *
0x18000de2a  call    _generateProfile
0x18000de2f  mov     edi, eax
0x18000de31  test    eax, eax
0x18000de33  jz      short loc_18000DE4C
0x18000de35  test    rbx, rbx
0x18000de38  jz      short loc_18000DE4A
0x18000de3a  mov     rcx, [rbx]
0x18000de3d  mov     rax, [rcx+10h]
0x18000de41  mov     rcx, rbx
0x18000de44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de49  nop
0x18000de4a  jmp     short loc_18000DE70
0x18000de4c  lea     rdx, [rsp+268h+var_238]
0x18000de51  mov     rcx, rbx
0x18000de54  call    _saveProfileXmlIndented
0x18000de59  mov     edi, eax
0x18000de5b  test    rbx, rbx
0x18000de5e  jz      short loc_18000DE70
0x18000de60  mov     rcx, [rbx]
0x18000de63  mov     rax, [rcx+10h]
0x18000de67  mov     rcx, rbx
0x18000de6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de6f  nop
0x18000de70  mov     eax, edi
0x18000de72  mov     rcx, [rsp+268h+var_28]
0x18000de7a  xor     rcx, rsp; StackCookie
0x18000de7d  call    __security_check_cookie
0x18000de82  add     rsp, 250h
0x18000de89  pop     rdi
0x18000de8a  pop     rsi
0x18000de8b  pop     rbx
0x18000de8c  retn
```
