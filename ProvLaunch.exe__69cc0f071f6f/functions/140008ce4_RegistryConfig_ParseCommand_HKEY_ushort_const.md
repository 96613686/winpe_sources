# RegistryConfig::ParseCommand(HKEY__ *,ushort const *)

- ea: `0x140008ce4`
- end: `0x140008f4c`
- name: `?ParseCommand@RegistryConfig@@AEAA?AUCommand@@PEAUHKEY__@@PEBG@Z`
- size: `616`
- prototype: `_WORD *__fastcall(__int64, _WORD *, HKEY, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x140007e3c`

## callees

- `0x140001008`
- `0x1400083a8`
- `0x1400089dc`
- `0x140008a2c`
- `0x140008ce4`
- `0x14000972c`
- `0x14000a370`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140008d68`
- `msvcrt!??3@YAXPEAX@Z` at `0x140008d98`
- `msvcrt!??3@YAXPEAX@Z` at `0x140008f02`
- `msvcrt!??3@YAXPEAX@Z` at `0x140008f25`
- `msvcrt!??3@YAXPEAX@Z` at `0x140008d68`
- `msvcrt!??3@YAXPEAX@Z` at `0x140008d98`
- `msvcrt!??3@YAXPEAX@Z` at `0x140008f02`
- `msvcrt!??3@YAXPEAX@Z` at `0x140008f25`

## string_xrefs

- `0x140008d41`: `CommandLine`
- `0x140008d6e`: `WorkingDirectory`
- `0x140008e5e`: `ContinueInstall`

## pseudocode

```c
_WORD *__fastcall RegistryConfig::ParseCommand(__int64 a1, _WORD *a2, HKEY a3, void *a4)
{
  void *StringValue; // rax
  __int64 v8; // rcx
  void *v9; // rax
  void **v10; // rdi
  void **v11; // rbx
  RegistryConfig *v12; // rcx
  RegistryConfig *v13; // rcx
  RegistryConfig *v14; // rcx
  RegistryConfig *v15; // rcx
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  void **v19; // rax
  void **v20; // rax
  unsigned int v22; // [rsp+40h] [rbp-79h] BYREF
  void **v23; // [rsp+48h] [rbp-71h] BYREF
  void *v24; // [rsp+50h] [rbp-69h] BYREF
  void **v25; // [rsp+68h] [rbp-51h] BYREF
  void *v26[2]; // [rsp+70h] [rbp-49h] BYREF
  __int64 v27; // [rsp+80h] [rbp-39h]
  unsigned __int64 v28; // [rsp+88h] [rbp-31h]
  void *Src[3]; // [rsp+90h] [rbp-29h] BYREF
  unsigned __int64 v30; // [rsp+A8h] [rbp-11h]
  void *v31[3]; // [rsp+B0h] [rbp-9h] BYREF
  unsigned __int64 v32; // [rsp+C8h] [rbp+Fh]

  v24 = a2;
  v30 = 7;
  Src[2] = 0;
  LOWORD(Src[0]) = 0;
  v28 = 7;
  v27 = 0;
  LOWORD(v26[0]) = 0;
  v23 = 0;
  v22 = 0;
  StringValue = (void *)RegistryConfig::GetStringValue(a1, v31, a3, L"CommandLine");
  std::wstring::operator=(Src, StringValue);
  if ( v32 >= 8 )
    operator delete(v31[0]);
  v9 = (void *)RegistryConfig::GetStringValue(v8, v31, a3, L"WorkingDirectory");
  std::wstring::operator=(v26, v9);
  if ( v32 >= 8 )
    operator delete(v31[0]);
  v10 = v26;
  if ( v28 >= 8 )
    v10 = (void **)v26[0];
  v11 = Src;
  if ( v30 >= 8 )
    v11 = (void **)Src[0];
  *((_QWORD *)a2 + 3) = 7;
  *((_QWORD *)a2 + 2) = 0;
  *a2 = 0;
  std::wstring::assign(a2, a4);
  *((_QWORD *)a2 + 7) = 7;
  *((_QWORD *)a2 + 6) = 0;
  a2[16] = 0;
  std::wstring::assign(a2 + 16, v11);
  *((_QWORD *)a2 + 11) = 7;
  *((_QWORD *)a2 + 10) = 0;
  a2[32] = 0;
  std::wstring::assign(a2 + 32, v10);
  *((_DWORD *)a2 + 24) = 0;
  *((_DWORD *)a2 + 25) = 1;
  if ( !RegistryConfig::GetNumericalValue(v12, a3, L"ReturnCodeSuccess", &v22) )
    *((_DWORD *)a2 + 26) = v22;
  if ( !RegistryConfig::GetNumericalValue(v13, a3, L"ReturnCodeRestart", &v22) )
    *((_DWORD *)a2 + 27) = v22;
  if ( !RegistryConfig::GetNumericalValue(v14, a3, L"ContinueInstall", &v22) )
    *((_DWORD *)a2 + 25) = v22 == 1;
  if ( !RegistryConfig::GetNumericalValue(v15, a3, L"RestartRequired", &v22) )
    *((_DWORD *)a2 + 24) = v22 == 1;
  if ( (unsigned int)dword_140010000 > 4 )
  {
    v19 = v26;
    if ( v28 >= 8 )
      v19 = (void **)v26[0];
    v25 = v19;
    v20 = Src;
    if ( v30 >= 8 )
      v20 = (void **)Src[0];
    v23 = v20;
    v24 = a4;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      v16,
      (unsigned int)&byte_14000D68F,
      v17,
      v18,
      (__int64)&v24,
      (__int64)&v23,
      (__int64)&v25);
  }
  if ( v28 >= 8 )
    operator delete(v26[0]);
  v28 = 7;
  v27 = 0;
  LOWORD(v26[0]) = 0;
  if ( v30 >= 8 )
    operator delete(Src[0]);
  return a2;
}

```

## disassembly

```asm
0x140008ce4  push    rbp
0x140008ce6  push    rbx
0x140008ce7  push    rsi
0x140008ce8  push    rdi
0x140008ce9  push    r13
0x140008ceb  push    r14
0x140008ced  push    r15
0x140008cef  lea     rbp, [rsp-27h]
0x140008cf4  sub     rsp, 0E0h
0x140008cfb  mov     rax, cs:__security_cookie
0x140008d02  xor     rax, rsp
0x140008d05  mov     [rbp+57h+var_40], rax
0x140008d09  mov     r15, r9
0x140008d0c  mov     r14, r8
0x140008d0f  mov     rsi, rdx
0x140008d12  mov     [rbp+57h+var_C0], rdx
0x140008d16  mov     r13d, 7
0x140008d1c  mov     [rbp+57h+var_68], r13
0x140008d20  mov     [rbp+57h+var_70], 0
0x140008d28  xor     eax, eax
0x140008d2a  mov     word ptr [rbp+57h+Src], ax
0x140008d2e  mov     [rbp+57h+var_88], r13
0x140008d32  mov     [rbp+57h+var_90], rax
0x140008d36  mov     word ptr [rbp+57h+var_A0], ax
0x140008d3a  mov     [rbp+57h+var_C8], rax
0x140008d3e  mov     [rbp+57h+var_D0], eax
0x140008d41  lea     r9, aCommandline; "CommandLine"
0x140008d48  lea     rdx, [rbp+57h+var_60]
0x140008d4c  call    ?GetStringValue@RegistryConfig@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHKEY__@@PEBG@Z; RegistryConfig::GetStringValue(HKEY__ *,ushort const *)
0x140008d51  mov     rdx, rax; Src
0x140008d54  lea     rcx, [rbp+57h+Src]; void *
0x140008d58  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x140008d5d  cmp     [rbp+57h+var_48], 8
0x140008d62  jb      short loc_140008D6E
0x140008d64  mov     rcx, [rbp+57h+var_60]
0x140008d68  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140008d6e  lea     r9, aWorkingdirecto; "WorkingDirectory"
0x140008d75  mov     r8, r14
0x140008d78  lea     rdx, [rbp+57h+var_60]
0x140008d7c  call    ?GetStringValue@RegistryConfig@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHKEY__@@PEBG@Z; RegistryConfig::GetStringValue(HKEY__ *,ushort const *)
0x140008d81  mov     rdx, rax; Src
0x140008d84  lea     rcx, [rbp+57h+var_A0]; void *
0x140008d88  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x140008d8d  cmp     [rbp+57h+var_48], 8
0x140008d92  jb      short loc_140008D9E
0x140008d94  mov     rcx, [rbp+57h+var_60]
0x140008d98  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140008d9e  lea     rdi, [rbp+57h+var_A0]
0x140008da2  cmp     [rbp+57h+var_88], 8
0x140008da7  cmovnb  rdi, [rbp+57h+var_A0]
0x140008dac  lea     rbx, [rbp+57h+Src]
0x140008db0  cmp     [rbp+57h+var_68], 8
0x140008db5  cmovnb  rbx, [rbp+57h+Src]
0x140008dba  mov     [rsi+18h], r13
0x140008dbe  mov     qword ptr [rsi+10h], 0
0x140008dc6  xor     eax, eax
0x140008dc8  mov     [rsi], ax
0x140008dcb  mov     rdx, r15; Src
0x140008dce  mov     rcx, rsi; void *
0x140008dd1  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x140008dd6  nop
0x140008dd7  lea     rcx, [rsi+20h]; void *
0x140008ddb  mov     [rcx+18h], r13
0x140008ddf  mov     qword ptr [rcx+10h], 0
0x140008de7  xor     eax, eax
0x140008de9  mov     [rcx], ax
0x140008dec  mov     rdx, rbx; Src
0x140008def  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x140008df4  nop
0x140008df5  lea     rcx, [rsi+40h]; void *
0x140008df9  mov     [rcx+18h], r13
0x140008dfd  mov     qword ptr [rcx+10h], 0
0x140008e05  xor     eax, eax
0x140008e07  mov     [rcx], ax
0x140008e0a  mov     rdx, rdi; Src
0x140008e0d  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x140008e12  mov     dword ptr [rsi+60h], 0
0x140008e19  mov     dword ptr [rsi+64h], 1
0x140008e20  lea     r9, [rbp+57h+var_D0]; unsigned int *
0x140008e24  lea     r8, aReturncodesucc; "ReturnCodeSuccess"
0x140008e2b  mov     rdx, r14; HKEY
0x140008e2e  call    ?GetNumericalValue@RegistryConfig@@AEAAJPEAUHKEY__@@PEBGPEAK@Z; RegistryConfig::GetNumericalValue(HKEY__ *,ushort const *,ulong *)
0x140008e33  test    eax, eax
0x140008e35  jnz     short loc_140008E3D
0x140008e37  mov     eax, [rbp+57h+var_D0]
0x140008e3a  mov     [rsi+68h], eax
0x140008e3d  lea     r9, [rbp+57h+var_D0]; unsigned int *
0x140008e41  lea     r8, aReturncoderest; "ReturnCodeRestart"
0x140008e48  mov     rdx, r14; HKEY
0x140008e4b  call    ?GetNumericalValue@RegistryConfig@@AEAAJPEAUHKEY__@@PEBGPEAK@Z; RegistryConfig::GetNumericalValue(HKEY__ *,ushort const *,ulong *)
0x140008e50  test    eax, eax
0x140008e52  jnz     short loc_140008E5A
0x140008e54  mov     eax, [rbp+57h+var_D0]
0x140008e57  mov     [rsi+6Ch], eax
0x140008e5a  lea     r9, [rbp+57h+var_D0]; unsigned int *
0x140008e5e  lea     r8, aContinueinstal; "ContinueInstall"
0x140008e65  mov     rdx, r14; HKEY
0x140008e68  call    ?GetNumericalValue@RegistryConfig@@AEAAJPEAUHKEY__@@PEBGPEAK@Z; RegistryConfig::GetNumericalValue(HKEY__ *,ushort const *,ulong *)
0x140008e6d  test    eax, eax
0x140008e6f  jnz     short loc_140008E7B
0x140008e71  cmp     [rbp+57h+var_D0], 1
0x140008e75  setz    al
0x140008e78  mov     [rsi+64h], eax
0x140008e7b  lea     r9, [rbp+57h+var_D0]; unsigned int *
0x140008e7f  lea     r8, aRestartrequire; "RestartRequired"
0x140008e86  mov     rdx, r14; HKEY
0x140008e89  call    ?GetNumericalValue@RegistryConfig@@AEAAJPEAUHKEY__@@PEBGPEAK@Z; RegistryConfig::GetNumericalValue(HKEY__ *,ushort const *,ulong *)
0x140008e8e  test    eax, eax
0x140008e90  jnz     short loc_140008E9C
0x140008e92  cmp     [rbp+57h+var_D0], 1
0x140008e96  setz    al
0x140008e99  mov     [rsi+60h], eax
0x140008e9c  mov     eax, cs:dword_140010000
0x140008ea2  cmp     eax, 4
0x140008ea5  jbe     short loc_140008EF7
0x140008ea7  lea     rax, [rbp+57h+var_A0]
0x140008eab  cmp     [rbp+57h+var_88], 8
0x140008eb0  cmovnb  rax, [rbp+57h+var_A0]
0x140008eb5  mov     [rbp+57h+var_A8], rax
0x140008eb9  lea     rax, [rbp+57h+Src]
0x140008ebd  cmp     [rbp+57h+var_68], 8
0x140008ec2  cmovnb  rax, [rbp+57h+Src]
0x140008ec7  mov     [rbp+57h+var_C8], rax
0x140008ecb  mov     [rbp+57h+var_C0], r15
0x140008ecf  lea     rax, [rbp+57h+var_A8]
0x140008ed3  mov     [rsp+110h+var_E0], rax
0x140008ed8  lea     rax, [rbp+57h+var_C8]
0x140008edc  mov     [rsp+110h+var_E8], rax
0x140008ee1  lea     rax, [rbp+57h+var_C0]
0x140008ee5  mov     [rsp+110h+var_F0], rax
0x140008eea  lea     rdx, byte_14000D68F
0x140008ef1  call    ??$Write@U?$_tlgWrapSz@G@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x140008ef6  nop
0x140008ef7  cmp     [rbp+57h+var_88], 8
0x140008efc  jb      short loc_140008F08
0x140008efe  mov     rcx, [rbp+57h+var_A0]
0x140008f02  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140008f08  mov     [rbp+57h+var_88], r13
0x140008f0c  mov     [rbp+57h+var_90], 0
0x140008f14  xor     ecx, ecx
0x140008f16  mov     word ptr [rbp+57h+var_A0], cx
0x140008f1a  cmp     [rbp+57h+var_68], 8
0x140008f1f  jb      short loc_140008F2B
0x140008f21  mov     rcx, [rbp+57h+Src]
0x140008f25  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140008f2b  mov     rax, rsi
0x140008f2e  mov     rcx, [rbp+57h+var_40]
0x140008f32  xor     rcx, rsp; StackCookie
0x140008f35  call    __security_check_cookie
0x140008f3a  add     rsp, 0E0h
0x140008f41  pop     r15
0x140008f43  pop     r14
0x140008f45  pop     r13
0x140008f47  pop     rdi
0x140008f48  pop     rsi
0x140008f49  pop     rbx
0x140008f4a  pop     rbp
0x140008f4b  retn
```
