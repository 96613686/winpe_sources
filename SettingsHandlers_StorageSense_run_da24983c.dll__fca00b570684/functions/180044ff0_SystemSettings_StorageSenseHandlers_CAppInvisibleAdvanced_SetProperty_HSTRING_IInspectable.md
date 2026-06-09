# SystemSettings::StorageSenseHandlers::CAppInvisibleAdvanced::SetProperty(HSTRING__ *,IInspectable *)

- ea: `0x180044ff0`
- end: `0x18004514f`
- name: `?SetProperty@CAppInvisibleAdvanced@StorageSenseHandlers@SystemSettings@@UEAAJPEAUHSTRING__@@PEAUIInspectable@@@Z`
- size: `351`
- prototype: `int(SystemSettings::StorageSenseHandlers::CAppInvisibleAdvanced *__hidden this, HSTRING, struct IInspectable *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000c964`
- `0x18000e6cc`
- `0x18001f688`
- `0x180044d90`
- `0x180044ff0`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045084`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800450c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004512f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045084`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800450c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004512f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800450da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800450f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800450da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800450f3`
- `api-ms-win-appmodel-runtime-l1-1-1!VerifyPackageFamilyName` at `0x1800450e3`
- `api-ms-win-appmodel-runtime-l1-1-1!VerifyPackageFamilyName` at `0x1800450e3`
- `api-ms-win-appmodel-runtime-l1-1-1!VerifyApplicationUserModelId` at `0x1800450fc`
- `api-ms-win-appmodel-runtime-l1-1-1!VerifyApplicationUserModelId` at `0x1800450fc`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SystemSettings::StorageSenseHandlers::CAppInvisibleAdvanced::SetProperty(
        SystemSettings::StorageSenseHandlers::CAppInvisibleAdvanced *this,
        SystemSettings::DataModel *a2,
        struct IInspectable *a3)
{
  HRESULT (__stdcall *QueryInterface)(IInspectable *, const IID *const, void **); // rbx
  int v6; // eax
  const unsigned __int16 *v7; // r8
  unsigned int v8; // ebx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, HSTRING *); // rbx
  int v11; // eax
  __int64 v12; // rdx
  const WCHAR *StringRawBuffer; // rax
  const WCHAR *v14; // rax
  HSTRING v16; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  HSTRING string; // [rsp+60h] [rbp+30h] BYREF
  __int64 v19; // [rsp+68h] [rbp+38h] BYREF

  v19 = 0;
  QueryInterface = a3->lpVtbl->QueryInterface;
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v19);
  v6 = ((__int64 (__fastcall *)(struct IInspectable *, GUID *, __int64 *))QueryInterface)(
         a3,
         &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62,
         &v19);
  v8 = v6;
  if ( v6 >= 0 )
  {
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18010B7C8, v7) )
    {
      string = 0;
      v9 = v19;
      v10 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v19 + 152LL);
      WindowsDeleteString(0);
      string = 0;
      v11 = v10(v9, &string);
      v8 = v11;
      if ( v11 < 0 )
      {
        v12 = 4281;
LABEL_6:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v12,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appsizeslist.cpp",
          (const char *)(unsigned int)v11,
          (int)v16);
        WindowsDeleteString(string);
        string = 0;
        goto LABEL_13;
      }
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      if ( !VerifyPackageFamilyName(StringRawBuffer)
        || (v14 = WindowsGetStringRawBuffer(string, 0), !VerifyApplicationUserModelId(v14)) )
      {
        v16 = string;
        v11 = Microsoft::WRL::Wrappers::HString::Set(&SystemSettings::StorageSenseHandlers::g_callerIdentity, &v16);
        v8 = v11;
        if ( v11 < 0 )
        {
          v12 = 4286;
          goto LABEL_6;
        }
      }
      WindowsDeleteString(string);
    }
    v8 = 0;
    goto LABEL_13;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x10B4,
    (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appsizeslist.cpp",
    (const char *)(unsigned int)v6,
    (int)v16);
LABEL_13:
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v19);
  return v8;
}

```

## disassembly

```asm
0x180044ff0  mov     [rsp-18h+arg_0], rbx
0x180044ff5  push    rbp
0x180044ff6  push    rsi
0x180044ff7  push    rdi
0x180044ff8  mov     rbp, rsp
0x180044ffb  sub     rsp, 30h
0x180044fff  mov     rdi, r8
0x180045002  mov     rsi, rdx
0x180045005  mov     [rbp+arg_18], 0
0x18004500d  mov     rax, [r8]
0x180045010  mov     rbx, [rax]
0x180045013  lea     rcx, [rbp+arg_18]
0x180045017  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x18004501c  lea     r8, [rbp+arg_18]
0x180045020  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x180045027  mov     rcx, rdi
0x18004502a  mov     rax, rbx
0x18004502d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045032  mov     ebx, eax
0x180045034  test    eax, eax
0x180045036  jns     short loc_180045055
0x180045038  mov     rcx, [rbp+18h]; this
0x18004503c  mov     r9d, eax; char *
0x18004503f  lea     r8, aOnecoreuapShel_29; "onecoreuap\\shell\\coresettinghandlers"...
0x180045046  mov     edx, 10B4h; void *
0x18004504b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045050  jmp     loc_180045137
0x180045055  lea     rdx, stru_18010B7C8; HSTRING
0x18004505c  mov     rcx, rsi; this
0x18004505f  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180045064  test    al, al
0x180045066  jz      loc_180045135
0x18004506c  mov     [rbp+string], 0
0x180045074  mov     rdi, [rbp+arg_18]
0x180045078  mov     rax, [rdi]
0x18004507b  mov     rbx, [rax+98h]
0x180045082  xor     ecx, ecx; string
0x180045084  call    cs:__imp_WindowsDeleteString
0x18004508a  mov     [rbp+string], 0
0x180045092  lea     rdx, [rbp+string]
0x180045096  mov     rcx, rdi
0x180045099  mov     rax, rbx
0x18004509c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800450a1  mov     ebx, eax
0x1800450a3  test    eax, eax
0x1800450a5  jns     short loc_1800450D4
0x1800450a7  mov     edx, 10B9h; void *
0x1800450ac  lea     r8, aOnecoreuapShel_29; "onecoreuap\\shell\\coresettinghandlers"...
0x1800450b3  mov     r9d, eax; char *
0x1800450b6  mov     rcx, [rbp+18h]; this
0x1800450ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800450bf  nop
0x1800450c0  mov     rcx, [rbp+string]; string
0x1800450c4  call    cs:__imp_WindowsDeleteString
0x1800450ca  mov     [rbp+string], 0
0x1800450d2  jmp     short loc_180045137
0x1800450d4  xor     edx, edx; length
0x1800450d6  mov     rcx, [rbp+string]; string
0x1800450da  call    cs:__imp_WindowsGetStringRawBuffer
0x1800450e0  mov     rcx, rax; packageFamilyName
0x1800450e3  call    cs:__imp_VerifyPackageFamilyName
0x1800450e9  test    eax, eax
0x1800450eb  jz      short loc_180045106
0x1800450ed  xor     edx, edx; length
0x1800450ef  mov     rcx, [rbp+string]; string
0x1800450f3  call    cs:__imp_WindowsGetStringRawBuffer
0x1800450f9  mov     rcx, rax; applicationUserModelId
0x1800450fc  call    cs:__imp_VerifyApplicationUserModelId
0x180045102  test    eax, eax
0x180045104  jnz     short loc_18004512B
0x180045106  mov     rax, [rbp+string]
0x18004510a  mov     [rbp+var_10], rax
0x18004510e  lea     rdx, [rbp+var_10]; HSTRING *
0x180045112  lea     rcx, ?g_callerIdentity@StorageSenseHandlers@SystemSettings@@3VHString@Wrappers@WRL@Microsoft@@A; newString
0x180045119  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x18004511e  mov     ebx, eax
0x180045120  test    eax, eax
0x180045122  jns     short loc_18004512B
0x180045124  mov     edx, 10BEh
0x180045129  jmp     short loc_1800450AC
0x18004512b  mov     rcx, [rbp+string]; string
0x18004512f  call    cs:__imp_WindowsDeleteString
0x180045135  xor     ebx, ebx
0x180045137  lea     rcx, [rbp+arg_18]
0x18004513b  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x180045140  mov     eax, ebx
0x180045142  mov     rbx, [rsp+30h+arg_0]
0x180045147  add     rsp, 30h
0x18004514b  pop     rdi
0x18004514c  pop     rsi
0x18004514d  pop     rbp
0x18004514e  retn
```
