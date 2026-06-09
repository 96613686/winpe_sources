# SystemSettings::DataModel::CPITRSnapshotRetention::GetValue(IInspectable * *)

- ea: `0x180101cc0`
- end: `0x180101ec3`
- name: `?GetValue@CPITRSnapshotRetention@DataModel@SystemSettings@@UEAAJPEAPEAUIInspectable@@@Z`
- size: `515`
- prototype: `int(SystemSettings::DataModel::CPITRSnapshotRetention *__hidden this, struct IInspectable **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000c840`
- `0x180019a20`
- `0x18001a64c`
- `0x1800201c4`
- `0x18004d1ac`
- `0x180101cc0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180101d23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180101dd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180101e76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180101e8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180101d23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180101dd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180101e76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180101e8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180101d6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180101e13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180101d6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180101e13`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::DataModel::CPITRSnapshotRetention::GetValue(
        SystemSettings::DataModel::CPITRSnapshotRetention *this,
        struct IInspectable **a2)
{
  signed int i; // r8d
  __int64 v5; // rbp
  HSTRING *v6; // r8
  int ResourceStringById; // eax
  unsigned int v8; // edi
  __int64 v9; // rdx
  unsigned int v10; // edi
  const unsigned __int16 *v11; // rax
  HSTRING *v12; // r8
  unsigned int v13; // edi
  const unsigned __int16 *StringRawBuffer; // rax
  HSTRING string[2]; // [rsp+20h] [rbp-248h] BYREF
  unsigned __int16 v17[264]; // [rsp+30h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  for ( i = 0; (unsigned int)i < 5; ++i )
  {
    v5 = i;
    if ( 60 * *((_DWORD *)qword_180306138 + i) == *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 11) + 24LL) + 244LL) )
    {
      WindowsDeleteString(0);
      string[0] = 0;
      ResourceStringById = SystemSettings::DataModel::GetResourceStringById(
                             (SystemSettings::DataModel *)L"SystemSettings_Misc_PointInTimeRestore_SnapshotRetention_HourlyValue",
                             string,
                             v12);
      v8 = ResourceStringById;
      if ( ResourceStringById < 0 )
      {
        v9 = 906;
        goto LABEL_17;
      }
      v13 = *((_DWORD *)qword_180306138 + v5);
      StringRawBuffer = WindowsGetStringRawBuffer(string[0], 0);
      ResourceStringById = StringCchPrintfW(v17, 0x104u, StringRawBuffer, v13);
      v8 = ResourceStringById;
      if ( ResourceStringById < 0 )
      {
        v9 = 910;
        goto LABEL_17;
      }
      ResourceStringById = SystemSettings::DataModel::PropValueHelper::CreateString(v17, a2);
      v8 = ResourceStringById;
      if ( ResourceStringById < 0 )
      {
        v9 = 913;
        goto LABEL_17;
      }
      goto LABEL_18;
    }
  }
  WindowsDeleteString(0);
  string[0] = 0;
  ResourceStringById = SystemSettings::DataModel::GetResourceStringById(
                         (SystemSettings::DataModel *)L"SystemSettings_Misc_PointInTimeRestore_SnapshotRetention_DisabledValue",
                         string,
                         v6);
  v8 = ResourceStringById;
  if ( ResourceStringById < 0 )
  {
    v9 = 922;
LABEL_17:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\restore\\pointintimerestore.cpp",
      (const char *)(unsigned int)ResourceStringById,
      (int)string[0]);
    WindowsDeleteString(string[0]);
    return v8;
  }
  v10 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 11) + 24LL) + 244LL);
  v11 = WindowsGetStringRawBuffer(string[0], 0);
  ResourceStringById = StringCchPrintfW(v17, 0x104u, v11, v10);
  v8 = ResourceStringById;
  if ( ResourceStringById < 0 )
  {
    v9 = 926;
    goto LABEL_17;
  }
  ResourceStringById = SystemSettings::DataModel::PropValueHelper::CreateString(v17, a2);
  v8 = ResourceStringById;
  if ( ResourceStringById < 0 )
  {
    v9 = 929;
    goto LABEL_17;
  }
LABEL_18:
  WindowsDeleteString(string[0]);
  return 0;
}

```

## disassembly

```asm
0x180101cc0  mov     [rsp+arg_10], rbp
0x180101cc5  mov     [rsp+arg_18], rsi
0x180101cca  push    rdi
0x180101ccb  push    r14
0x180101ccd  push    r15
0x180101ccf  sub     rsp, 250h
0x180101cd6  mov     rax, cs:__security_cookie
0x180101cdd  xor     rax, rsp
0x180101ce0  mov     [rsp+268h+var_28], rax
0x180101ce8  mov     rsi, rdx
0x180101ceb  mov     r14, rcx
0x180101cee  xor     r8d, r8d
0x180101cf1  mov     rax, [rcx+58h]
0x180101cf5  mov     rdx, [rax+18h]
0x180101cf9  mov     r9d, [rdx+0F4h]
0x180101d00  movsxd  rbp, r8d
0x180101d03  lea     r15, qword_180306138
0x180101d0a  imul    eax, [r15+rbp*4], 3Ch ; '<'
0x180101d0f  cmp     eax, r9d
0x180101d12  jz      loc_180101DD3
0x180101d18  inc     r8d
0x180101d1b  cmp     r8d, 5
0x180101d1f  jb      short loc_180101D00
0x180101d21  xor     ecx, ecx; string
0x180101d23  call    cs:__imp_WindowsDeleteString
0x180101d2a  nop     dword ptr [rax+rax+00h]
0x180101d2f  mov     [rsp+268h+string], 0; int
0x180101d38  lea     rdx, [rsp+268h+string]; HSTRING *
0x180101d3d  lea     rcx, aSystemsettings_1182; "SystemSettings_Misc_PointInTimeRestore_"...
0x180101d44  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x180101d49  mov     edi, eax
0x180101d4b  test    eax, eax
0x180101d4d  jns     short loc_180101D56
0x180101d4f  mov     edx, 39Ah
0x180101d54  jmp     short loc_180101DB1
0x180101d56  mov     rax, [r14+58h]
0x180101d5a  mov     rcx, [rax+18h]
0x180101d5e  mov     edi, [rcx+0F4h]
0x180101d64  xor     edx, edx; length
0x180101d66  mov     rcx, [rsp+268h+string]; string
0x180101d6b  call    cs:__imp_WindowsGetStringRawBuffer
0x180101d72  nop     dword ptr [rax+rax+00h]
0x180101d77  mov     r9d, edi
0x180101d7a  mov     r8, rax; unsigned __int16 *
0x180101d7d  mov     edx, 104h; unsigned __int64
0x180101d82  lea     rcx, [rsp+268h+var_238]; unsigned __int16 *
0x180101d87  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180101d8c  mov     edi, eax
0x180101d8e  test    eax, eax
0x180101d90  jns     short loc_180101D99
0x180101d92  mov     edx, 39Eh
0x180101d97  jmp     short loc_180101DB1
0x180101d99  mov     rdx, rsi; struct IInspectable **
0x180101d9c  lea     rcx, [rsp+268h+var_238]; unsigned __int16 *
0x180101da1  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x180101da6  mov     edi, eax
0x180101da8  test    eax, eax
0x180101daa  jns     short loc_180101DCE
0x180101dac  mov     edx, 3A1h; void *
0x180101db1  mov     r9d, eax; char *
0x180101db4  lea     r8, aShellSystemset_19; "shell\\systemsettingsthreshold\\handler"...
0x180101dbb  mov     rcx, [rsp+268h]; this
0x180101dc3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180101dc8  nop
0x180101dc9  jmp     loc_180101E71
0x180101dce  jmp     loc_180101E86
0x180101dd3  xor     ecx, ecx; string
0x180101dd5  call    cs:__imp_WindowsDeleteString
0x180101ddc  nop     dword ptr [rax+rax+00h]
0x180101de1  mov     [rsp+268h+string], 0; int
0x180101dea  lea     rdx, [rsp+268h+string]; HSTRING *
0x180101def  lea     rcx, aSystemsettings_1241; "SystemSettings_Misc_PointInTimeRestore_"...
0x180101df6  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x180101dfb  mov     edi, eax
0x180101dfd  test    eax, eax
0x180101dff  jns     short loc_180101E08
0x180101e01  mov     edx, 38Ah
0x180101e06  jmp     short loc_180101E59
0x180101e08  mov     edi, [r15+rbp*4]
0x180101e0c  xor     edx, edx; length
0x180101e0e  mov     rcx, [rsp+268h+string]; string
0x180101e13  call    cs:__imp_WindowsGetStringRawBuffer
0x180101e1a  nop     dword ptr [rax+rax+00h]
0x180101e1f  mov     r9d, edi
0x180101e22  mov     r8, rax; unsigned __int16 *
0x180101e25  mov     edx, 104h; unsigned __int64
0x180101e2a  lea     rcx, [rsp+268h+var_238]; unsigned __int16 *
0x180101e2f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180101e34  mov     edi, eax
0x180101e36  test    eax, eax
0x180101e38  jns     short loc_180101E41
0x180101e3a  mov     edx, 38Eh
0x180101e3f  jmp     short loc_180101E59
0x180101e41  mov     rdx, rsi; struct IInspectable **
0x180101e44  lea     rcx, [rsp+268h+var_238]; unsigned __int16 *
0x180101e49  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x180101e4e  mov     edi, eax
0x180101e50  test    eax, eax
0x180101e52  jns     short loc_180101E86
0x180101e54  mov     edx, 391h; void *
0x180101e59  mov     r9d, eax; char *
0x180101e5c  lea     r8, aShellSystemset_19; "shell\\systemsettingsthreshold\\handler"...
0x180101e63  mov     rcx, [rsp+268h]; this
0x180101e6b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180101e70  nop
0x180101e71  mov     rcx, [rsp+268h+string]; string
0x180101e76  call    cs:__imp_WindowsDeleteString
0x180101e7d  nop     dword ptr [rax+rax+00h]
0x180101e82  mov     eax, edi
0x180101e84  jmp     short loc_180101E99
0x180101e86  mov     rcx, [rsp+268h+string]; string
0x180101e8b  call    cs:__imp_WindowsDeleteString
0x180101e92  nop     dword ptr [rax+rax+00h]
0x180101e97  xor     eax, eax
0x180101e99  mov     rcx, [rsp+268h+var_28]
0x180101ea1  xor     rcx, rsp; StackCookie
0x180101ea4  call    __security_check_cookie
0x180101ea9  lea     r11, [rsp+268h+var_18]
0x180101eb1  mov     rbp, [r11+30h]
0x180101eb5  mov     rsi, [r11+38h]
0x180101eb9  mov     rsp, r11
0x180101ebc  pop     r15
0x180101ebe  pop     r14
0x180101ec0  pop     rdi
0x180101ec1  retn
```
