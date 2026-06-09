# CUserAccountControlSettingsSource::s_SubclassWndProc(HWND__ *,uint,unsigned __int64,__int64,unsigned __int64,unsigned __int64)

- ea: `0x180003db0`
- end: `0x180003ef4`
- name: `?s_SubclassWndProc@CUserAccountControlSettingsSource@@CA_JPEAUHWND__@@I_K_J11@Z`
- size: `324`
- prototype: `__int64 (__fastcall *__fastcall(HWND, unsigned int, __int64, __int64, unsigned __int64, struct DirectUI::Element *))(HWND, _QWORD, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180003db0`
- `0x18000b2dc`
- `0x18000c010`

## import_xrefs

- `SHELL32!__imp_SetWindowRelaunchProperties` at `0x180003e6e`
- `SHELL32!__imp_SetWindowRelaunchProperties` at `0x180003e6e`
- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x180003e05`
- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x180003e05`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x180003e2b`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x180003e2b`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x180003e4d`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x180003e4d`
- `DUI70!?UpdateSheets@DUIXmlParser@DirectUI@@QEAAJPEAVElement@2@@Z` at `0x180003e42`
- `DUI70!?UpdateSheets@DUIXmlParser@DirectUI@@QEAAJPEAVElement@2@@Z` at `0x180003e42`

## pseudocode

```c
__int64 (__fastcall *__fastcall CUserAccountControlSettingsSource::s_SubclassWndProc(
        HWND a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        unsigned __int64 a5,
        struct DirectUI::Element *a6))(HWND, _QWORD, __int64, __int64)
{
  void (__fastcall *v10)(HWND, __int64 (__fastcall *)(HWND, unsigned int, unsigned __int64, __int64, unsigned __int64, unsigned __int64), _QWORD); // rax
  __int64 (__fastcall *result)(HWND, _QWORD, __int64, __int64); // rax
  struct DirectUI::DUIXmlParser *v12; // [rsp+30h] [rbp-38h] BYREF

  if ( a2 == 2 )
  {
    SetWindowRelaunchProperties(a1, 0, 0, 0, 0, 0);
    v10 = (void (__fastcall *)(HWND, __int64 (__fastcall *)(HWND, unsigned int, unsigned __int64, __int64, unsigned __int64, unsigned __int64), _QWORD))qword_180015268;
    if ( qword_180015268 == -1 )
    {
      GetProcFromComCtl32(&qword_180015268, 412);
      v10 = (void (__fastcall *)(HWND, __int64 (__fastcall *)(HWND, unsigned int, unsigned __int64, __int64, unsigned __int64, unsigned __int64), _QWORD))qword_180015268;
    }
    if ( v10 )
      v10(a1, CUserAccountControlSettingsSource::s_SubclassWndProc, 0);
  }
  else if ( a2 == 21 )
  {
    if ( a6 )
    {
      v12 = 0;
      if ( (int)DirectUI::DUIXmlParser::Create(&v12, 0, 0, 0, 0) >= 0 )
      {
        if ( (int)DirectUI::DUIXmlParser::SetXMLFromResource(v12, 0xCBu, g_hinst, (HINSTANCE)&_ImageBase) >= 0 )
          DirectUI::DUIXmlParser::UpdateSheets(v12, a6);
        DirectUI::DUIXmlParser::Destroy(v12);
      }
    }
  }
  result = (__int64 (__fastcall *)(HWND, _QWORD, __int64, __int64))qword_180015260;
  if ( qword_180015260 == -1 )
  {
    GetProcFromComCtl32(&qword_180015260, 413);
    result = (__int64 (__fastcall *)(HWND, _QWORD, __int64, __int64))qword_180015260;
  }
  if ( result )
    return (__int64 (__fastcall *)(HWND, _QWORD, __int64, __int64))result(a1, a2, a3, a4);
  return result;
}

```

## disassembly

```asm
0x180003db0  push    rbp
0x180003db2  push    rsi
0x180003db3  push    rdi
0x180003db4  push    r14
0x180003db6  sub     rsp, 48h
0x180003dba  mov     rbp, r9
0x180003dbd  mov     r14, r8
0x180003dc0  mov     edi, edx
0x180003dc2  mov     rsi, rcx
0x180003dc5  cmp     edx, 2
0x180003dc8  jz      loc_180003E55
0x180003dce  cmp     edx, 15h
0x180003dd1  jnz     loc_180003EB0
0x180003dd7  cmp     [rsp+68h+arg_28], 0
0x180003de0  jz      loc_180003EB0
0x180003de6  xor     r9d, r9d
0x180003de9  mov     [rsp+68h+var_38], 0
0x180003df2  xor     r8d, r8d
0x180003df5  mov     [rsp+68h+var_48], 0
0x180003dfe  xor     edx, edx
0x180003e00  lea     rcx, [rsp+68h+var_38]
0x180003e05  call    cs:__imp_?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z; DirectUI::DUIXmlParser::Create(DirectUI::DUIXmlParser * *,DirectUI::Value * (*)(ushort const *,void *),void *,void (*)(ushort const *,ushort const *,int,void *),void *)
0x180003e0b  test    eax, eax
0x180003e0d  js      loc_180003EB0
0x180003e13  mov     r8, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hinst
0x180003e1a  lea     r9, __ImageBase
0x180003e21  mov     rcx, [rsp+68h+var_38]
0x180003e26  mov     edx, 0CBh
0x180003e2b  call    cs:__imp_?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z; DirectUI::DUIXmlParser::SetXMLFromResource(uint,HINSTANCE__ *,HINSTANCE__ *)
0x180003e31  test    eax, eax
0x180003e33  js      short loc_180003E48
0x180003e35  mov     rdx, [rsp+68h+arg_28]
0x180003e3d  mov     rcx, [rsp+68h+var_38]
0x180003e42  call    cs:__imp_?UpdateSheets@DUIXmlParser@DirectUI@@QEAAJPEAVElement@2@@Z; DirectUI::DUIXmlParser::UpdateSheets(DirectUI::Element *)
0x180003e48  mov     rcx, [rsp+68h+var_38]
0x180003e4d  call    cs:__imp_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ; DirectUI::DUIXmlParser::Destroy(void)
0x180003e53  jmp     short loc_180003EB0
0x180003e55  mov     [rsp+68h+var_40], 0
0x180003e5d  xor     r9d, r9d
0x180003e60  xor     r8d, r8d
0x180003e63  mov     [rsp+68h+var_48], 0
0x180003e6c  xor     edx, edx
0x180003e6e  call    cs:__imp_SetWindowRelaunchProperties
0x180003e74  mov     rax, cs:qword_180015268
0x180003e7b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180003e7f  jnz     short loc_180003E99
0x180003e81  mov     edx, 19Ch
0x180003e86  lea     rcx, qword_180015268
0x180003e8d  call    _GetProcFromComCtl32
0x180003e92  mov     rax, cs:qword_180015268
0x180003e99  test    rax, rax
0x180003e9c  jz      short loc_180003EB0
0x180003e9e  xor     r8d, r8d
0x180003ea1  lea     rdx, ?s_SubclassWndProc@CUserAccountControlSettingsSource@@CA_JPEAUHWND__@@I_K_J11@Z; CUserAccountControlSettingsSource::s_SubclassWndProc(HWND__ *,uint,unsigned __int64,__int64,unsigned __int64,unsigned __int64)
0x180003ea8  mov     rcx, rsi
0x180003eab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003eb0  mov     rax, cs:qword_180015260
0x180003eb7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180003ebb  jnz     short loc_180003ED5
0x180003ebd  mov     edx, 19Dh
0x180003ec2  lea     rcx, qword_180015260
0x180003ec9  call    _GetProcFromComCtl32
0x180003ece  mov     rax, cs:qword_180015260
0x180003ed5  test    rax, rax
0x180003ed8  jz      short loc_180003EEA
0x180003eda  mov     r9, rbp
0x180003edd  mov     r8, r14
0x180003ee0  mov     edx, edi
0x180003ee2  mov     rcx, rsi
0x180003ee5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003eea  add     rsp, 48h
0x180003eee  pop     r14
0x180003ef0  pop     rdi
0x180003ef1  pop     rsi
0x180003ef2  pop     rbp
0x180003ef3  retn
```
