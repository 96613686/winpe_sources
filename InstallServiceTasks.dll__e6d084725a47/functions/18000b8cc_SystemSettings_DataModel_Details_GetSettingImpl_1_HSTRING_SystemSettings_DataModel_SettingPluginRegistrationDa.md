# SystemSettings::DataModel::Details::GetSettingImpl<1>(HSTRING__ *,SystemSettings::DataModel::SettingPluginRegistrationData const (&)[1],SystemSettings::DataModel::ISettingItem * *)

- ea: `0x18000b8cc`
- end: `0x18000ba2c`
- name: `??$GetSettingImpl@$00@Details@DataModel@SystemSettings@@YAJPEAUHSTRING__@@AEAY00$$CBUSettingPluginRegistrationData@12@PEAPEAUISettingItem@12@@Z`
- size: `352`
- prototype: `__int64 __fastcall(HSTRING string, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180012090`

## callees

- `0x18000760c`
- `0x18000b8cc`
- `0x18000fc84`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000b8f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000b987`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000b9e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000b8f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000b987`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000b9e8`

## string_xrefs

- `0x18000b9a6`: `onecoreuap\internal\shell\inc\SettingsDBCommonThreshold.h`
- `0x18000ba0c`: `onecoreuap\internal\shell\inc\SettingsDBCommonThreshold.h`

## pseudocode

```c
__int64 __fastcall SystemSettings::DataModel::Details::GetSettingImpl<1>(HSTRING string, __int64 a2, _QWORD *a3)
{
  PCWSTR StringRawBuffer; // r10
  wchar_t **v6; // rdi
  wchar_t *v7; // r8
  _WORD *v8; // rcx
  wchar_t *v9; // rdx
  wchar_t *v10; // rdi
  __int64 (__fastcall *v11)(wchar_t *, __int64 *); // rbx
  int v12; // ebx
  const char *v13; // rax
  __int64 v14; // rax
  const char *v16; // rax
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  UINT32 v18; // [rsp+58h] [rbp+10h] BYREF
  int v19; // [rsp+5Ch] [rbp+14h]
  __int64 v20; // [rsp+60h] [rbp+18h] BYREF

  v19 = HIDWORD(a2);
  *a3 = 0;
  v18 = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(string, &v18);
  v6 = &off_180048508;
  while ( 1 )
  {
    v7 = v6[1];
    if ( (wchar_t *)v18 == v7 )
      break;
LABEL_6:
    v6 += 3;
    if ( v6 == &off_180048520 )
      goto LABEL_7;
  }
  v8 = &StringRawBuffer[v18];
  v9 = &(*v6)[(_QWORD)v7];
  while ( v8 != StringRawBuffer )
  {
    if ( *--v8 != *--v9 )
      goto LABEL_6;
  }
LABEL_7:
  if ( v6 == &off_180048520 )
  {
    v16 = (const char *)WindowsGetStringRawBuffer(string, 0);
    v12 = -2147024809;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xDC,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingsDBCommonThreshold.h",
      (const char *)0x80070057LL,
      (int)"%ls",
      v16);
  }
  else
  {
    v10 = v6[2];
    v20 = 0;
    v11 = *(__int64 (__fastcall **)(wchar_t *, __int64 *))(*((_QWORD *)v10 + 5) + 8LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
    v12 = v11(v10, &v20);
    if ( v12 >= 0 )
    {
      v14 = v20;
      v20 = 0;
      *a3 = v14;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
      return 0;
    }
    v13 = (const char *)WindowsGetStringRawBuffer(string, 0);
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xE1,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingsDBCommonThreshold.h",
      (const char *)(unsigned int)v12,
      (int)"%ls",
      v13);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000b8cc  mov     rax, rsp
0x18000b8cf  mov     [rax+8], rbx
0x18000b8d3  mov     [rax+10h], rdx
0x18000b8d7  push    rbp
0x18000b8d8  push    rsi
0x18000b8d9  push    rdi
0x18000b8da  sub     rsp, 30h
0x18000b8de  mov     rsi, r8
0x18000b8e1  mov     rbp, rcx
0x18000b8e4  mov     qword ptr [r8], 0
0x18000b8eb  mov     dword ptr [rax+10h], 0
0x18000b8f2  lea     rdx, [rax+10h]; length
0x18000b8f6  call    cs:__imp_WindowsGetStringRawBuffer
0x18000b8fc  mov     r10, rax
0x18000b8ff  lea     rdi, off_180048508; "SystemSettings_Apps_Offloading"
0x18000b906  mov     r9d, [rsp+48h+arg_8]
0x18000b90b  lea     r11, off_180048520; "SystemSettings_Apps_Offloading"
0x18000b912  mov     r8, [rdi+8]
0x18000b916  cmp     r9, r8
0x18000b919  jnz     short loc_18000B93B
0x18000b91b  lea     rcx, [r10+r9*2]
0x18000b91f  mov     rdx, [rdi]
0x18000b922  lea     rdx, [rdx+r8*2]
0x18000b926  cmp     rcx, r10
0x18000b929  jz      short loc_18000B944
0x18000b92b  add     rdx, 0FFFFFFFFFFFFFFFEh
0x18000b92f  add     rcx, 0FFFFFFFFFFFFFFFEh
0x18000b933  movzx   eax, word ptr [rdx]
0x18000b936  cmp     [rcx], ax
0x18000b939  jz      short loc_18000B926
0x18000b93b  add     rdi, 18h
0x18000b93f  cmp     rdi, r11
0x18000b942  jnz     short loc_18000B912
0x18000b944  cmp     rdi, r11
0x18000b947  jz      loc_18000B9E3
0x18000b94d  mov     rdi, [rdi+10h]
0x18000b951  mov     [rsp+48h+arg_10], 0
0x18000b95a  mov     rax, [rdi+28h]
0x18000b95e  mov     rbx, [rax+8]
0x18000b962  lea     rcx, [rsp+48h+arg_10]
0x18000b967  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000b96c  lea     rdx, [rsp+48h+arg_10]
0x18000b971  mov     rcx, rdi
0x18000b974  mov     rax, rbx
0x18000b977  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b97c  mov     ebx, eax
0x18000b97e  test    eax, eax
0x18000b980  jns     short loc_18000B9C4
0x18000b982  xor     edx, edx; length
0x18000b984  mov     rcx, rbp; string
0x18000b987  call    cs:__imp_WindowsGetStringRawBuffer
0x18000b98d  mov     rcx, [rsp+48h]; this
0x18000b992  mov     [rsp+48h+var_20], rax; char *
0x18000b997  lea     rdx, aLs; "%ls"
0x18000b99e  mov     qword ptr [rsp+48h+var_28], rdx; int
0x18000b9a3  mov     r9d, ebx; char *
0x18000b9a6  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x18000b9ad  mov     edx, 0E1h; void *
0x18000b9b2  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000b9b7  nop
0x18000b9b8  lea     rcx, [rsp+48h+arg_10]
0x18000b9bd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000b9c2  jmp     short loc_18000BA1D
0x18000b9c4  mov     rax, [rsp+48h+arg_10]
0x18000b9c9  mov     [rsp+48h+arg_10], 0
0x18000b9d2  mov     [rsi], rax
0x18000b9d5  lea     rcx, [rsp+48h+arg_10]
0x18000b9da  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000b9df  xor     eax, eax
0x18000b9e1  jmp     short loc_18000BA1F
0x18000b9e3  xor     edx, edx; length
0x18000b9e5  mov     rcx, rbp; string
0x18000b9e8  call    cs:__imp_WindowsGetStringRawBuffer
0x18000b9ee  mov     rcx, [rsp+48h]; this
0x18000b9f3  mov     [rsp+48h+var_20], rax; char *
0x18000b9f8  lea     rdx, aLs; "%ls"
0x18000b9ff  mov     qword ptr [rsp+48h+var_28], rdx; int
0x18000ba04  mov     ebx, 80070057h
0x18000ba09  mov     r9d, ebx; char *
0x18000ba0c  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x18000ba13  mov     edx, 0DCh; void *
0x18000ba18  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000ba1d  mov     eax, ebx
0x18000ba1f  mov     rbx, [rsp+48h+arg_0]
0x18000ba24  add     rsp, 30h
0x18000ba28  pop     rdi
0x18000ba29  pop     rsi
0x18000ba2a  pop     rbp
0x18000ba2b  retn
```
