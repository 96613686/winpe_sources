# DIRECTORY_BROWSING_CUSTOM_MAPPER::SetAboProperties(PROPERTY_MAPPING *,INativeConfigurationElement *,ABO_NODE *)

- ea: `0x18001ecc0`
- end: `0x18001eecd`
- name: `?SetAboProperties@DIRECTORY_BROWSING_CUSTOM_MAPPER@@UEAAJPEAVPROPERTY_MAPPING@@PEAVINativeConfigurationElement@@PEAVABO_NODE@@@Z`
- size: `525`
- prototype: `int(DIRECTORY_BROWSING_CUSTOM_MAPPER *__hidden this, struct PROPERTY_MAPPING *, struct INativeConfigurationElement *, struct ABO_NODE *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180003426`
- `0x180009818`
- `0x18000a838`
- `0x18001ecc0`
- `0x18002c010`

## import_xrefs

- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18001ed10`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18001ed10`

## string_xrefs

- `0x18001ed19`: `system.webServer/directoryBrowse`
- `0x18001ed5b`: `system.webServer/directoryBrowse`

## pseudocode

```c
__int64 __fastcall DIRECTORY_BROWSING_CUSTOM_MAPPER::SetAboProperties(
        DIRECTORY_BROWSING_CUSTOM_MAPPER *this,
        struct PROPERTY_MAPPING *a2,
        struct INativeConfigurationElement *a3,
        struct ABO_NODE *a4)
{
  struct INativeConfigurationElement *v4; // rcx
  struct INativeConfigurationElement *v6; // r8
  const wchar_t *Str; // rax
  int v10; // eax
  int v11; // r9d
  int MergedConfigElement; // ebx
  int v14; // [rsp+30h] [rbp-40h] BYREF
  struct INativeConfigurationElement *v15; // [rsp+38h] [rbp-38h] BYREF
  struct INativeConfigurationElement *v16; // [rsp+40h] [rbp-30h] BYREF
  struct _METADATA_RECORD v17; // [rsp+48h] [rbp-28h] BYREF
  int v18; // [rsp+98h] [rbp+28h] BYREF

  v4 = 0;
  v6 = 0;
  v15 = 0;
  v16 = 0;
  v18 = 0;
  v14 = 0;
  if ( a2 && a3 && a4 )
  {
    Str = STRU::QueryStr((struct PROPERTY_MAPPING *)((char *)a2 + 32));
    v10 = wcscmp_0(Str, L"system.webServer/directoryBrowse");
    v11 = *((_DWORD *)a2 + 43) & 1;
    if ( v10 )
    {
      MergedConfigElement = ABO_NODE::GetMergedConfigElement(a4, L"system.webServer/directoryBrowse", &v15, v11);
      if ( MergedConfigElement >= 0 )
      {
        v16 = a3;
        goto LABEL_9;
      }
    }
    else
    {
      MergedConfigElement = ABO_NODE::GetMergedConfigElement(a4, L"system.webServer/defaultDocument", &v16, v11);
      if ( MergedConfigElement >= 0 )
      {
        v15 = a3;
LABEL_9:
        (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)a3 + 8LL))(a3);
        MergedConfigElement = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v15 + 48LL))(
                                v15,
                                L"showFlags",
                                &v18,
                                0,
                                0);
        if ( MergedConfigElement >= 0 )
        {
          MergedConfigElement = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v15 + 72LL))(
                                  v15,
                                  L"enabled",
                                  &v14,
                                  0,
                                  0);
          if ( MergedConfigElement >= 0 )
          {
            if ( v14 )
              v18 |= 0x80000000;
            MergedConfigElement = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v16 + 72LL))(
                                    v16,
                                    L"enabled",
                                    &v14,
                                    0,
                                    0);
            if ( MergedConfigElement >= 0 )
            {
              if ( v14 )
                v18 |= 0x40000000u;
              v17.dwMDIdentifier = *((_DWORD *)a2 + 36);
              v17.dwMDUserType = *((_DWORD *)a2 + 37);
              v17.dwMDDataType = *((_DWORD *)a2 + 38);
              v17.dwMDAttributes = *((_DWORD *)a2 + 39);
              v17.pbMDData = (unsigned __int8 *)&v18;
              *(_QWORD *)&v17.dwMDDataLen = 4;
              *(_QWORD *)&v17.dwMDDataTag = 0;
              MergedConfigElement = ABO_NODE::SetDataByMapping(a4, &v17, a2);
            }
          }
        }
      }
    }
    v4 = v15;
    v6 = v16;
    goto LABEL_19;
  }
  MergedConfigElement = -2147024809;
LABEL_19:
  if ( v6 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v6 + 16LL))(v6);
    v4 = v15;
    v16 = 0;
  }
  if ( v4 )
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v4 + 16LL))(v4);
  return (unsigned int)MergedConfigElement;
}

```

## disassembly

```asm
0x18001ecc0  mov     [rsp-18h+arg_0], rbx
0x18001ecc5  mov     [rsp-18h+arg_10], rsi
0x18001ecca  push    rbp
0x18001eccb  push    rdi
0x18001eccc  push    r14
0x18001ecce  mov     rbp, rsp
0x18001ecd1  sub     rsp, 70h
0x18001ecd5  xor     ecx, ecx
0x18001ecd7  mov     rdi, r8
0x18001ecda  xor     r8d, r8d
0x18001ecdd  mov     [rbp+var_38], rcx
0x18001ece1  mov     [rbp+var_30], r8
0x18001ece5  mov     r14, r9
0x18001ece8  mov     [rbp+arg_8], ecx
0x18001eceb  mov     rsi, rdx
0x18001ecee  mov     [rbp+var_40], ecx
0x18001ecf1  test    rdx, rdx
0x18001ecf4  jz      loc_18001EE80
0x18001ecfa  test    rdi, rdi
0x18001ecfd  jz      loc_18001EE80
0x18001ed03  test    r9, r9
0x18001ed06  jz      loc_18001EE80
0x18001ed0c  lea     rcx, [rdx+20h]
0x18001ed10  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x18001ed16  mov     rcx, rax; String1
0x18001ed19  lea     rdx, aSystemWebserve_5; "system.webServer/directoryBrowse"
0x18001ed20  call    wcscmp_0
0x18001ed25  mov     r9d, [rsi+0ACh]
0x18001ed2c  mov     rcx, r14; this
0x18001ed2f  and     r9d, 1; int
0x18001ed33  test    eax, eax
0x18001ed35  jnz     short loc_18001ED57
0x18001ed37  lea     r8, [rbp+var_30]; struct INativeConfigurationElement **
0x18001ed3b  lea     rdx, aSystemWebserve_4; "system.webServer/defaultDocument"
0x18001ed42  call    ?GetMergedConfigElement@ABO_NODE@@QEAAJPEBGPEAPEAVINativeConfigurationElement@@H@Z; ABO_NODE::GetMergedConfigElement(ushort const *,INativeConfigurationElement * *,int)
0x18001ed47  mov     ebx, eax
0x18001ed49  test    eax, eax
0x18001ed4b  js      loc_18001EE76
0x18001ed51  mov     [rbp+var_38], rdi
0x18001ed55  jmp     short loc_18001ED75
0x18001ed57  lea     r8, [rbp+var_38]; struct INativeConfigurationElement **
0x18001ed5b  lea     rdx, aSystemWebserve_5; "system.webServer/directoryBrowse"
0x18001ed62  call    ?GetMergedConfigElement@ABO_NODE@@QEAAJPEBGPEAPEAVINativeConfigurationElement@@H@Z; ABO_NODE::GetMergedConfigElement(ushort const *,INativeConfigurationElement * *,int)
0x18001ed67  mov     ebx, eax
0x18001ed69  test    eax, eax
0x18001ed6b  js      loc_18001EE76
0x18001ed71  mov     [rbp+var_30], rdi
0x18001ed75  mov     rax, [rdi]
0x18001ed78  mov     rcx, rdi
0x18001ed7b  mov     rax, [rax+8]
0x18001ed7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed84  mov     rcx, [rbp+var_38]
0x18001ed88  lea     r8, [rbp+arg_8]
0x18001ed8c  xor     r9d, r9d
0x18001ed8f  mov     [rsp+70h+var_50], 0
0x18001ed98  lea     rdx, aShowflags; "showFlags"
0x18001ed9f  mov     rax, [rcx]
0x18001eda2  mov     rax, [rax+30h]
0x18001eda6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001edab  mov     ebx, eax
0x18001edad  test    eax, eax
0x18001edaf  js      loc_18001EE76
0x18001edb5  mov     rcx, [rbp+var_38]
0x18001edb9  lea     r8, [rbp+var_40]
0x18001edbd  xor     r9d, r9d
0x18001edc0  mov     [rsp+70h+var_50], 0
0x18001edc9  lea     rdx, aEnabled; "enabled"
0x18001edd0  mov     rax, [rcx]
0x18001edd3  mov     rax, [rax+48h]
0x18001edd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eddc  mov     ebx, eax
0x18001edde  test    eax, eax
0x18001ede0  js      loc_18001EE76
0x18001ede6  cmp     [rbp+var_40], 0
0x18001edea  jz      short loc_18001EDF1
0x18001edec  bts     [rbp+arg_8], 1Fh
0x18001edf1  mov     rcx, [rbp+var_30]
0x18001edf5  lea     r8, [rbp+var_40]
0x18001edf9  xor     r9d, r9d
0x18001edfc  mov     [rsp+70h+var_50], 0
0x18001ee05  lea     rdx, aEnabled; "enabled"
0x18001ee0c  mov     rax, [rcx]
0x18001ee0f  mov     rax, [rax+48h]
0x18001ee13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee18  mov     ebx, eax
0x18001ee1a  test    eax, eax
0x18001ee1c  js      short loc_18001EE76
0x18001ee1e  cmp     [rbp+var_40], 0
0x18001ee22  jz      short loc_18001EE29
0x18001ee24  bts     [rbp+arg_8], 1Eh
0x18001ee29  mov     eax, [rsi+90h]
0x18001ee2f  lea     rdx, [rbp+var_28]; struct _METADATA_RECORD *
0x18001ee33  mov     [rbp+var_28.dwMDIdentifier], eax
0x18001ee36  mov     r8, rsi; struct PROPERTY_MAPPING *
0x18001ee39  mov     eax, [rsi+94h]
0x18001ee3f  mov     rcx, r14; this
0x18001ee42  mov     [rbp+var_28.dwMDUserType], eax
0x18001ee45  mov     eax, [rsi+98h]
0x18001ee4b  mov     [rbp+var_28.dwMDDataType], eax
0x18001ee4e  mov     eax, [rsi+9Ch]
0x18001ee54  mov     [rbp+var_28.dwMDAttributes], eax
0x18001ee57  lea     rax, [rbp+arg_8]
0x18001ee5b  mov     [rbp+var_28.pbMDData], rax
0x18001ee5f  mov     qword ptr [rbp+var_28.dwMDDataLen], 4
0x18001ee67  mov     qword ptr [rbp+var_28.dwMDDataTag], 0
0x18001ee6f  call    ?SetDataByMapping@ABO_NODE@@QEAAJPEAU_METADATA_RECORD@@PEAVPROPERTY_MAPPING@@@Z; ABO_NODE::SetDataByMapping(_METADATA_RECORD *,PROPERTY_MAPPING *)
0x18001ee74  mov     ebx, eax
0x18001ee76  mov     rcx, [rbp+var_38]
0x18001ee7a  mov     r8, [rbp+var_30]
0x18001ee7e  jmp     short loc_18001EE85
0x18001ee80  mov     ebx, 80070057h
0x18001ee85  test    r8, r8
0x18001ee88  jz      short loc_18001EEA5
0x18001ee8a  mov     rax, [r8]
0x18001ee8d  mov     rcx, r8
0x18001ee90  mov     rax, [rax+10h]
0x18001ee94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee99  mov     rcx, [rbp+var_38]
0x18001ee9d  mov     [rbp+var_30], 0
0x18001eea5  test    rcx, rcx
0x18001eea8  jz      short loc_18001EEB6
0x18001eeaa  mov     rax, [rcx]
0x18001eead  mov     rax, [rax+10h]
0x18001eeb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eeb6  lea     r11, [rsp+70h+var_s0]
0x18001eebb  mov     eax, ebx
0x18001eebd  mov     rbx, [r11+20h]
0x18001eec1  mov     rsi, [r11+30h]
0x18001eec5  mov     rsp, r11
0x18001eec8  pop     r14
0x18001eeca  pop     rdi
0x18001eecb  pop     rbp
0x18001eecc  retn
```
