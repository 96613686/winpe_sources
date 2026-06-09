# SystemSettings::DataModel::CPITRSnapshotCadence::GetValue(IInspectable * *)

- ea: `0x180101a40`
- end: `0x180101c8e`
- name: `?GetValue@CPITRSnapshotCadence@DataModel@SystemSettings@@UEAAJPEAPEAUIInspectable@@@Z`
- size: `590`
- prototype: `int(SystemSettings::DataModel::CPITRSnapshotCadence *__hidden this, struct IInspectable **)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000c840`
- `0x180019a20`
- `0x18001a64c`
- `0x1800201c4`
- `0x18004d1ac`
- `0x18004d218`
- `0x180101a40`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180101ab2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180101b63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180101b9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180101c3d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180101ab2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180101b63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180101b9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180101c3d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180101afd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180101bdc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180101afd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180101bdc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::DataModel::CPITRSnapshotCadence::GetValue(
        SystemSettings::DataModel::CPITRSnapshotCadence *this,
        struct IInspectable **a2)
{
  __int64 v4; // r8
  int v5; // edx
  __int64 v6; // rbp
  HSTRING *v7; // r8
  int ResourceStringById; // eax
  unsigned int v9; // edi
  HSTRING v10; // rbx
  __int64 v11; // rdx
  unsigned int v12; // edi
  const unsigned __int16 *StringRawBuffer; // rax
  HSTRING *v15; // r8
  unsigned int v16; // edi
  const unsigned __int16 *v17; // rax
  int ResourceStringValue; // eax
  unsigned int v19; // ebx
  HSTRING string[2]; // [rsp+20h] [rbp-258h] BYREF
  unsigned __int16 v21[264]; // [rsp+30h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  *a2 = 0;
  v4 = *(_QWORD *)(*((_QWORD *)this + 11) + 24LL);
  if ( *(_BYTE *)(v4 + 232) )
  {
    v5 = 0;
    while ( 1 )
    {
      v6 = v5;
      if ( 60 * *((_DWORD *)qword_180306120 + v5) == *(_DWORD *)(v4 + 236) )
        break;
      if ( (unsigned int)++v5 >= 5 )
      {
        WindowsDeleteString(0);
        string[0] = 0;
        ResourceStringById = SystemSettings::DataModel::GetResourceStringById(
                               (SystemSettings::DataModel *)L"SystemSettings_Misc_PointInTimeRestore_SnapshotCadence_CustomValue",
                               string,
                               v7);
        v9 = ResourceStringById;
        v10 = string[0];
        if ( ResourceStringById < 0 )
        {
          v11 = 644;
          goto LABEL_19;
        }
        v12 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 11) + 24LL) + 236LL);
        StringRawBuffer = WindowsGetStringRawBuffer(string[0], 0);
        ResourceStringById = StringCchPrintfW(v21, 0x104u, StringRawBuffer, v12);
        v9 = ResourceStringById;
        if ( ResourceStringById < 0 )
        {
          v11 = 648;
          goto LABEL_19;
        }
        ResourceStringById = SystemSettings::DataModel::PropValueHelper::CreateString(v21, a2);
        v9 = ResourceStringById;
        if ( ResourceStringById < 0 )
        {
          v11 = 651;
          goto LABEL_19;
        }
LABEL_11:
        WindowsDeleteString(v10);
        return 0;
      }
    }
    WindowsDeleteString(0);
    string[0] = 0;
    ResourceStringById = SystemSettings::DataModel::GetResourceStringById(
                           (SystemSettings::DataModel *)L"SystemSettings_Misc_PointInTimeRestore_SnapshotCadence_HourlyValue",
                           string,
                           v15);
    v9 = ResourceStringById;
    v10 = string[0];
    if ( ResourceStringById >= 0 )
    {
      v16 = *((_DWORD *)qword_180306120 + v6);
      v17 = WindowsGetStringRawBuffer(string[0], 0);
      ResourceStringById = StringCchPrintfW(v21, 0x104u, v17, v16);
      v9 = ResourceStringById;
      if ( ResourceStringById >= 0 )
      {
        ResourceStringById = SystemSettings::DataModel::PropValueHelper::CreateString(v21, a2);
        v9 = ResourceStringById;
        if ( ResourceStringById >= 0 )
          goto LABEL_11;
        v11 = 634;
      }
      else
      {
        v11 = 631;
      }
    }
    else
    {
      v11 = 627;
    }
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\restore\\pointintimerestore.cpp",
      (const char *)(unsigned int)ResourceStringById,
      (int)string[0]);
    WindowsDeleteString(v10);
    return v9;
  }
  else
  {
    ResourceStringValue = SystemSettings::DataModel::GetResourceStringValue(
                            (SystemSettings::DataModel *)L"SystemSettings_Misc_PointInTimeRestore_SnapshotCadence_DisabledValue",
                            a2,
                            (struct IInspectable **)v4);
    v19 = ResourceStringValue;
    if ( ResourceStringValue >= 0 )
    {
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x291,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\restore\\pointintimerestore.cpp",
        (const char *)(unsigned int)ResourceStringValue,
        (int)string[0]);
      return v19;
    }
  }
}

```

## disassembly

```asm
0x180101a40  mov     [rsp+arg_10], rbx
0x180101a45  push    rbp
0x180101a46  push    rsi
0x180101a47  push    rdi
0x180101a48  push    r12
0x180101a4a  push    r14
0x180101a4c  sub     rsp, 250h
0x180101a53  mov     rax, cs:__security_cookie
0x180101a5a  xor     rax, rsp
0x180101a5d  mov     [rsp+278h+var_38], rax
0x180101a65  mov     rsi, rdx
0x180101a68  mov     r14, rcx
0x180101a6b  mov     qword ptr [rdx], 0
0x180101a72  mov     rax, [rcx+58h]
0x180101a76  mov     r8, [rax+18h]; struct IInspectable **
0x180101a7a  cmp     byte ptr [r8+0E8h], 0
0x180101a82  jz      loc_180101C55
0x180101a88  xor     edx, edx
0x180101a8a  mov     r9d, [r8+0ECh]
0x180101a91  movsxd  rbp, edx
0x180101a94  lea     r12, qword_180306120
0x180101a9b  imul    eax, [r12+rbp*4], 3Ch ; '<'
0x180101aa0  cmp     eax, r9d
0x180101aa3  jz      loc_180101B99
0x180101aa9  inc     edx
0x180101aab  cmp     edx, 5
0x180101aae  jb      short loc_180101A91
0x180101ab0  xor     ecx, ecx; string
0x180101ab2  call    cs:__imp_WindowsDeleteString
0x180101ab9  nop     dword ptr [rax+rax+00h]
0x180101abe  mov     [rsp+278h+string], 0; int
0x180101ac7  lea     rdx, [rsp+278h+string]; HSTRING *
0x180101acc  lea     rcx, aSystemsettings_733; "SystemSettings_Misc_PointInTimeRestore_"...
0x180101ad3  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x180101ad8  mov     edi, eax
0x180101ada  mov     rbx, [rsp+278h+string]
0x180101adf  test    eax, eax
0x180101ae1  jns     short loc_180101AEA
0x180101ae3  mov     edx, 284h
0x180101ae8  jmp     short loc_180101B43
0x180101aea  mov     rax, [r14+58h]
0x180101aee  mov     rcx, [rax+18h]
0x180101af2  mov     edi, [rcx+0ECh]
0x180101af8  xor     edx, edx; length
0x180101afa  mov     rcx, rbx; string
0x180101afd  call    cs:__imp_WindowsGetStringRawBuffer
0x180101b04  nop     dword ptr [rax+rax+00h]
0x180101b09  mov     r9d, edi
0x180101b0c  mov     r8, rax; unsigned __int16 *
0x180101b0f  mov     edx, 104h; unsigned __int64
0x180101b14  lea     rcx, [rsp+278h+var_248]; unsigned __int16 *
0x180101b19  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180101b1e  mov     edi, eax
0x180101b20  test    eax, eax
0x180101b22  jns     short loc_180101B2B
0x180101b24  mov     edx, 288h
0x180101b29  jmp     short loc_180101B43
0x180101b2b  mov     rdx, rsi; struct IInspectable **
0x180101b2e  lea     rcx, [rsp+278h+var_248]; unsigned __int16 *
0x180101b33  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x180101b38  mov     edi, eax
0x180101b3a  test    eax, eax
0x180101b3c  jns     short loc_180101B60
0x180101b3e  mov     edx, 28Bh; void *
0x180101b43  mov     r9d, eax; char *
0x180101b46  lea     r8, aShellSystemset_19; "shell\\systemsettingsthreshold\\handler"...
0x180101b4d  mov     rcx, [rsp+278h]; this
0x180101b55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180101b5a  nop
0x180101b5b  jmp     loc_180101C3A
0x180101b60  mov     rcx, rbx; string
0x180101b63  call    cs:__imp_WindowsDeleteString
0x180101b6a  nop     dword ptr [rax+rax+00h]
0x180101b6f  xor     eax, eax
0x180101b71  mov     rcx, [rsp+278h+var_38]
0x180101b79  xor     rcx, rsp; StackCookie
0x180101b7c  call    __security_check_cookie
0x180101b81  mov     rbx, [rsp+278h+arg_10]
0x180101b89  add     rsp, 250h
0x180101b90  pop     r14
0x180101b92  pop     r12
0x180101b94  pop     rdi
0x180101b95  pop     rsi
0x180101b96  pop     rbp
0x180101b97  retn
0x180101b99  xor     ecx, ecx; string
0x180101b9b  call    cs:__imp_WindowsDeleteString
0x180101ba2  nop     dword ptr [rax+rax+00h]
0x180101ba7  mov     [rsp+278h+string], 0; int
0x180101bb0  lea     rdx, [rsp+278h+string]; HSTRING *
0x180101bb5  lea     rcx, aSystemsettings_1072; "SystemSettings_Misc_PointInTimeRestore_"...
0x180101bbc  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x180101bc1  mov     edi, eax
0x180101bc3  mov     rbx, [rsp+278h+string]
0x180101bc8  test    eax, eax
0x180101bca  jns     short loc_180101BD3
0x180101bcc  mov     edx, 273h
0x180101bd1  jmp     short loc_180101C22
0x180101bd3  mov     edi, [r12+rbp*4]
0x180101bd7  xor     edx, edx; length
0x180101bd9  mov     rcx, rbx; string
0x180101bdc  call    cs:__imp_WindowsGetStringRawBuffer
0x180101be3  nop     dword ptr [rax+rax+00h]
0x180101be8  mov     r9d, edi
0x180101beb  mov     r8, rax; unsigned __int16 *
0x180101bee  mov     edx, 104h; unsigned __int64
0x180101bf3  lea     rcx, [rsp+278h+var_248]; unsigned __int16 *
0x180101bf8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180101bfd  mov     edi, eax
0x180101bff  test    eax, eax
0x180101c01  jns     short loc_180101C0A
0x180101c03  mov     edx, 277h
0x180101c08  jmp     short loc_180101C22
0x180101c0a  mov     rdx, rsi; struct IInspectable **
0x180101c0d  lea     rcx, [rsp+278h+var_248]; unsigned __int16 *
0x180101c12  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x180101c17  mov     edi, eax
0x180101c19  test    eax, eax
0x180101c1b  jns     short loc_180101C50
0x180101c1d  mov     edx, 27Ah; void *
0x180101c22  mov     r9d, eax; char *
0x180101c25  lea     r8, aShellSystemset_19; "shell\\systemsettingsthreshold\\handler"...
0x180101c2c  mov     rcx, [rsp+278h]; this
0x180101c34  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180101c39  nop
0x180101c3a  mov     rcx, rbx; string
0x180101c3d  call    cs:__imp_WindowsDeleteString
0x180101c44  nop     dword ptr [rax+rax+00h]
0x180101c49  mov     eax, edi
0x180101c4b  jmp     loc_180101B71
0x180101c50  jmp     loc_180101B60
0x180101c55  lea     rcx, aSystemsettings_322; "SystemSettings_Misc_PointInTimeRestore_"...
0x180101c5c  call    ?GetResourceStringValue@DataModel@SystemSettings@@YAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::GetResourceStringValue(ushort const *,IInspectable * *)
0x180101c61  mov     ebx, eax
0x180101c63  test    eax, eax
0x180101c65  jns     loc_180101B6F
0x180101c6b  mov     rcx, [rsp+278h]; this
0x180101c73  mov     r9d, eax; char *
0x180101c76  lea     r8, aShellSystemset_19; "shell\\systemsettingsthreshold\\handler"...
0x180101c7d  mov     edx, 291h; void *
0x180101c82  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180101c87  mov     eax, ebx
0x180101c89  jmp     loc_180101B71
```
