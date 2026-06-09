# SystemSettings::StorageSenseHandlers::CAppSizesList::_UpdateAppVisibility(SystemSettings::StorageSenseHandlers::CPackageSizeSetting *,HSTRING__ *,int)

- ea: `0x180049d8c`
- end: `0x180049e7d`
- name: `?_UpdateAppVisibility@CAppSizesList@StorageSenseHandlers@SystemSettings@@AEAA_NPEAVCPackageSizeSetting@23@PEAUHSTRING__@@H@Z`
- size: `241`
- prototype: `bool(SystemSettings::StorageSenseHandlers::CAppSizesList *__hidden this, struct SystemSettings::StorageSenseHandlers::CPackageSizeSetting *, HSTRING, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800476ec`
- `0x180047ee0`

## callees

- `0x18003ffd4`
- `0x180044d90`
- `0x180044f70`
- `0x180049d8c`
- `0x18004b9b0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049dd3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049e56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049e61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049dd3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049e56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049e61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180049df3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180049e05`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180049df3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180049e05`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x180049e11`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x180049e11`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool __fastcall SystemSettings::StorageSenseHandlers::CAppSizesList::_UpdateAppVisibility(
        SystemSettings::StorageSenseHandlers::CAppSizesList *this,
        SystemSettings::StorageSenseHandlers::CAppTileData **a2,
        HSTRING a3,
        int a4)
{
  HSTRING v6; // rbx
  bool v7; // dl
  const WCHAR *StringRawBuffer; // rdi
  const WCHAR *v9; // rax
  bool v10; // di
  HSTRING string; // [rsp+20h] [rbp-10h] BYREF
  HSTRING v13; // [rsp+50h] [rbp+20h] BYREF
  HSTRING v14; // [rsp+60h] [rbp+30h] BYREF

  v14 = a3;
  string = 0;
  v6 = 0;
  v13 = 0;
  Microsoft::WRL::Wrappers::HString::Set(&string, &v14);
  if ( string )
  {
    WindowsDeleteString(0);
    v13 = 0;
    if ( (int)SystemSettings::StorageSenseHandlers::CPackageSizeSetting::get_SearchCriteria(a2, &v13) < 0 )
    {
      v6 = v13;
    }
    else
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v6 = v13;
      v9 = WindowsGetStringRawBuffer(v13, 0);
      if ( !StrStrIW(v9, StringRawBuffer) )
      {
        v10 = 0;
        goto LABEL_8;
      }
    }
  }
  v10 = 1;
  if ( a4 >= 0 )
    v10 = ((1 << a4)
         & (unsigned int)SystemSettings::StorageSenseHandlers::CPackageSizeSetting::GetDriveBitmap(
                           (SystemSettings::StorageSenseHandlers::CPackageSizeSetting *)a2,
                           v7)) != 0;
LABEL_8:
  SystemSettings::StorageSenseHandlers::CPackageSizeSetting::SetIsAppVisible(
    (SystemSettings::StorageSenseHandlers::CPackageSizeSetting *)a2,
    v10);
  WindowsDeleteString(v6);
  WindowsDeleteString(string);
  return v10;
}

```

## disassembly

```asm
0x180049d8c  mov     rax, rsp
0x180049d8f  mov     [rax+10h], rbx
0x180049d93  mov     [rax+20h], rsi
0x180049d97  mov     [rax+18h], r8
0x180049d9b  mov     [rax+8], rcx
0x180049d9f  push    rbp
0x180049da0  push    rdi
0x180049da1  push    r14
0x180049da3  mov     rbp, rsp
0x180049da6  sub     rsp, 30h
0x180049daa  mov     r14d, r9d
0x180049dad  mov     rsi, rdx
0x180049db0  mov     [rbp+string], 0
0x180049db8  xor     ebx, ebx
0x180049dba  mov     [rbp+arg_0], rbx
0x180049dbe  lea     rdx, [rbp+arg_10]; HSTRING *
0x180049dc2  lea     rcx, [rbp+string]; newString
0x180049dc6  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x180049dcb  cmp     [rbp+string], rbx
0x180049dcf  jz      short loc_180049E25
0x180049dd1  xor     ecx, ecx; string
0x180049dd3  call    cs:__imp_WindowsDeleteString
0x180049dd9  mov     [rbp+arg_0], rbx
0x180049ddd  lea     rdx, [rbp+arg_0]; HSTRING *
0x180049de1  mov     rcx, rsi; this
0x180049de4  call    ?get_SearchCriteria@CPackageSizeSetting@StorageSenseHandlers@SystemSettings@@QEAAJPEAPEAUHSTRING__@@@Z; SystemSettings::StorageSenseHandlers::CPackageSizeSetting::get_SearchCriteria(HSTRING__ * *)
0x180049de9  test    eax, eax
0x180049deb  js      short loc_180049E21
0x180049ded  xor     edx, edx; length
0x180049def  mov     rcx, [rbp+string]; string
0x180049df3  call    cs:__imp_WindowsGetStringRawBuffer
0x180049df9  mov     rdi, rax
0x180049dfc  xor     edx, edx; length
0x180049dfe  mov     rbx, [rbp+arg_0]
0x180049e02  mov     rcx, rbx; string
0x180049e05  call    cs:__imp_WindowsGetStringRawBuffer
0x180049e0b  mov     rdx, rdi; pszSrch
0x180049e0e  mov     rcx, rax; pszFirst
0x180049e11  call    cs:__imp_StrStrIW
0x180049e17  test    rax, rax
0x180049e1a  jnz     short loc_180049E25
0x180049e1c  xor     dil, dil
0x180049e1f  jmp     short loc_180049E47
0x180049e21  mov     rbx, [rbp+arg_0]
0x180049e25  mov     edi, 1
0x180049e2a  test    r14d, r14d
0x180049e2d  js      short loc_180049E47
0x180049e2f  mov     rcx, rsi; this
0x180049e32  call    ?GetDriveBitmap@CPackageSizeSetting@StorageSenseHandlers@SystemSettings@@QEAAH_N@Z; SystemSettings::StorageSenseHandlers::CPackageSizeSetting::GetDriveBitmap(bool)
0x180049e37  mov     ecx, r14d
0x180049e3a  mov     edx, edi
0x180049e3c  shl     edx, cl
0x180049e3e  and     eax, edx
0x180049e40  neg     eax
0x180049e42  sbb     al, al
0x180049e44  and     dil, al
0x180049e47  mov     dl, dil; bool
0x180049e4a  mov     rcx, rsi; this
0x180049e4d  call    ?SetIsAppVisible@CPackageSizeSetting@StorageSenseHandlers@SystemSettings@@QEAAX_N@Z; SystemSettings::StorageSenseHandlers::CPackageSizeSetting::SetIsAppVisible(bool)
0x180049e52  nop
0x180049e53  mov     rcx, rbx; string
0x180049e56  call    cs:__imp_WindowsDeleteString
0x180049e5c  nop
0x180049e5d  mov     rcx, [rbp+string]; string
0x180049e61  call    cs:__imp_WindowsDeleteString
0x180049e67  mov     al, dil
0x180049e6a  mov     rbx, [rsp+30h+arg_8]
0x180049e6f  mov     rsi, [rsp+30h+arg_18]
0x180049e74  add     rsp, 30h
0x180049e78  pop     r14
0x180049e7a  pop     rdi
0x180049e7b  pop     rbp
0x180049e7c  retn
```
