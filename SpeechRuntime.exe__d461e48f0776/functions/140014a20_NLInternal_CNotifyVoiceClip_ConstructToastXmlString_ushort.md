# NLInternal::CNotifyVoiceClip::ConstructToastXmlString(ushort * *)

- ea: `0x140014a20`
- end: `0x140014cc1`
- name: `?ConstructToastXmlString@CNotifyVoiceClip@NLInternal@@CAJPEAPEAG@Z`
- size: `673`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140017ad0`

## callees

- `0x140002d30`
- `0x140003848`
- `0x140004aa5`
- `0x14000e010`
- `0x14000e030`
- `0x140013cf8`
- `0x140014a20`
- `0x140015c48`
- `0x14002f370`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x140014bd9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x140014c14`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x140014c3c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x140014c5f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x140014bd9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x140014c14`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x140014c3c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x140014c5f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140014b9d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140014b9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014b26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014b26`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140014ae7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140014ae7`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x140014af8`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x140014af8`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x140014bb0`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x140014bb0`
- `api-ms-win-core-wow64-l1-1-0!Wow64DisableWow64FsRedirection` at `0x140014b17`
- `api-ms-win-core-wow64-l1-1-0!Wow64DisableWow64FsRedirection` at `0x140014b17`

## string_xrefs

- `0x140014ad2`: `<toast activationType="protocol" launch="ms-settings:privacy-speech">                                                   <visual>                                                       <binding template="ToastGeneric">                                                           <text>%1!ws!</text>                                                           <text>%2!ws!</text>                                                           <image placement="hero"/>                                            `
- `0x140014b92`: `Windows.Media.Speech.UXRes.dll`

## pseudocode

```c
__int64 __fastcall NLInternal::CNotifyVoiceClip::ConstructToastXmlString(unsigned __int16 **a1)
{
  HANDLE CurrentProcess; // rax
  char v3; // di
  signed int v4; // eax
  unsigned int LastError; // ebx
  unsigned __int64 v6; // r9
  __int64 v7; // rdx
  HMODULE Library; // rbx
  const char *v10; // r9
  __int64 v11; // rdx
  int v12; // eax
  WCHAR *v13; // [rsp+20h] [rbp-E0h]
  __int16 v14; // [rsp+30h] [rbp-D0h] BYREF
  PVOID OldValue; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Buffer; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v17[510]; // [rsp+42h] [rbp-BEh] BYREF
  WCHAR v18; // [rsp+240h] [rbp+140h] BYREF
  _BYTE v19[1022]; // [rsp+242h] [rbp+142h] BYREF
  WCHAR v20; // [rsp+640h] [rbp+540h] BYREF
  _BYTE v21[1022]; // [rsp+642h] [rbp+542h] BYREF
  WCHAR v22; // [rsp+A40h] [rbp+940h] BYREF
  _BYTE v23[2046]; // [rsp+A42h] [rbp+942h] BYREF
  _BYTE Source[2256]; // [rsp+1240h] [rbp+1140h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B38h] [rbp+1A38h]

  Buffer = 0;
  memset_0(v17, 0, sizeof(v17));
  v22 = 0;
  memset_0(v23, 0, sizeof(v23));
  v20 = 0;
  memset_0(v21, 0, sizeof(v21));
  v18 = 0;
  memset_0(v19, 0, sizeof(v19));
  memcpy_0(
    Source,
    L"<toast activationType=\"protocol\" launch=\"ms-settings:privacy-speech\">                                           "
     "        <visual>                                                       <binding template=\"ToastGeneric\">         "
     "                                                  <text>%1!ws!</text>                                              "
     "             <text>%2!ws!</text>                                                           <image placement=\"hero\""
     "/>                                                           <image placement=\"appLogoOverride\"/>                "
     "                                       </binding>                                                    </visual>     "
     "                                              <actions>                                                       <acti"
     "on content=\"%3!ws!\" activationtype=\"protocol\" arguments=\"ms-settings:privacy-speech\"/>                       "
     "                                <action content=\"%4!ws!\" activationtype=\"system\" arguments=\"dismiss\"/>       "
     "                                            </actions>                                               </toast>",
    0x8CAu);
  *a1 = 0;
  v14 = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !(unsigned int)IsWow64Process2(CurrentProcess, &v14, 0) )
    goto LABEL_4;
  OldValue = 0;
  if ( v14 )
  {
    v3 = 1;
    if ( !Wow64DisableWow64FsRedirection(&OldValue) )
    {
LABEL_4:
      OldValue = 0;
      goto LABEL_5;
    }
  }
  else
  {
    v3 = 0;
  }
  Library = LoadLibraryExW(L"Windows.Media.Speech.UXRes.dll", 0, 0x22u);
  if ( v3 )
    Wow64RevertWow64FsRedirection(OldValue);
  OldValue = Library;
  if ( Library )
  {
    if ( LoadStringW(Library, 0x400u, &Buffer, 256) )
    {
      if ( LoadStringW(Library, 0x401u, &v22, 1024) )
      {
        if ( LoadStringW(Library, 0x402u, &v20, 512) )
        {
          if ( LoadStringW(Library, 0x403u, &v18, 512) )
          {
            v13 = &v20;
            v12 = NLInternal::CNotifyVoiceClip::FormatToastMessage(Source, a1, &Buffer, &v22);
            LastError = v12;
            if ( v12 >= 0 )
            {
              LastError = 0;
              goto LABEL_10;
            }
            v6 = (unsigned int)v12;
            v7 = 197;
            goto LABEL_9;
          }
          v11 = 195;
        }
        else
        {
          v11 = 194;
        }
      }
      else
      {
        v11 = 193;
      }
    }
    else
    {
      v11 = 192;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v11,
                  (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechruntime\\toastnotifier\\sendtoastnotification.cpp",
                  v10);
    goto LABEL_10;
  }
LABEL_5:
  v4 = GetLastError();
  LastError = v4;
  if ( v4 > 0 )
    LastError = (unsigned __int16)v4 | 0x80070000;
  if ( (LastError & 0x80000000) != 0 )
  {
    v6 = LastError;
    v7 = 190;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechruntime\\toastnotifier\\sendtoastnotification.cpp",
      (const char *)v6,
      (int)v13);
  }
LABEL_10:
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&OldValue);
  return LastError;
}

```

## disassembly

```asm
0x140014a20  mov     [rsp-8+arg_8], rbx
0x140014a25  mov     [rsp-8+arg_10], rsi
0x140014a2a  push    rbp
0x140014a2b  push    rdi
0x140014a2c  push    r14
0x140014a2e  lea     rbp, [rsp-1A20h]
0x140014a36  mov     eax, 1B20h
0x140014a3b  call    _alloca_probe
0x140014a40  sub     rsp, rax
0x140014a43  mov     rax, cs:__security_cookie
0x140014a4a  xor     rax, rsp
0x140014a4d  mov     [rbp+1A30h+var_20], rax
0x140014a54  mov     rsi, rcx
0x140014a57  xor     r14d, r14d
0x140014a5a  lea     rcx, [rsp+1B30h+var_1AEE]; void *
0x140014a5f  mov     [rsp+1B30h+Buffer], r14w
0x140014a65  xor     edx, edx; Val
0x140014a67  mov     r8d, 1FEh; Size
0x140014a6d  call    memset_0
0x140014a72  xor     edx, edx; Val
0x140014a74  mov     [rbp+1A30h+var_10F0], r14w
0x140014a7c  mov     r8d, 7FEh; Size
0x140014a82  lea     rcx, [rbp+1A30h+var_10EE]; void *
0x140014a89  call    memset_0
0x140014a8e  mov     ebx, 3FEh
0x140014a93  mov     [rbp+1A30h+var_14F0], r14w
0x140014a9b  mov     r8d, ebx; Size
0x140014a9e  lea     rcx, [rbp+1A30h+var_14EE]; void *
0x140014aa5  xor     edx, edx; Val
0x140014aa7  call    memset_0
0x140014aac  mov     r8d, ebx; Size
0x140014aaf  mov     [rbp+1A30h+var_18F0], r14w
0x140014ab7  xor     edx, edx; Val
0x140014ab9  lea     rcx, [rbp+1A30h+var_18EE]; void *
0x140014ac0  call    memset_0
0x140014ac5  lea     rcx, [rbp+1A30h+Source]; void *
0x140014acc  mov     r8d, 8CAh; Size
0x140014ad2  lea     rdx, aToastActivatio; "<toast activationType=\"protocol\" laun"...
0x140014ad9  call    memcpy_0
0x140014ade  mov     [rsi], r14
0x140014ae1  mov     [rsp+1B30h+var_1B00], r14w
0x140014ae7  call    cs:__imp_GetCurrentProcess
0x140014aed  xor     r8d, r8d
0x140014af0  lea     rdx, [rsp+1B30h+var_1B00]
0x140014af5  mov     rcx, rax
0x140014af8  call    cs:__imp_IsWow64Process2
0x140014afe  test    eax, eax
0x140014b00  jz      short loc_140014B21
0x140014b02  mov     [rsp+1B30h+OldValue], r14
0x140014b07  cmp     [rsp+1B30h+var_1B00], r14w
0x140014b0d  jz      short loc_140014B8D
0x140014b0f  lea     rcx, [rsp+1B30h+OldValue]; OldValue
0x140014b14  mov     dil, 1
0x140014b17  call    cs:__imp_Wow64DisableWow64FsRedirection
0x140014b1d  test    eax, eax
0x140014b1f  jnz     short loc_140014B90
0x140014b21  mov     [rsp+1B30h+OldValue], r14
0x140014b26  call    cs:__imp_GetLastError
0x140014b2c  mov     ebx, eax
0x140014b2e  test    eax, eax
0x140014b30  jle     short loc_140014B3B
0x140014b32  movzx   ebx, ax
0x140014b35  or      ebx, 80070000h
0x140014b3b  test    ebx, ebx
0x140014b3d  jns     short loc_140014B5A
0x140014b3f  mov     r9d, ebx; char *
0x140014b42  mov     edx, 0BEh; void *
0x140014b47  mov     rcx, [rbp+1A38h]; this
0x140014b4e  lea     r8, aOnecoreuapEndu_102; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x140014b55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140014b5a  lea     rcx, [rsp+1B30h+OldValue]
0x140014b5f  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x140014b64  mov     eax, ebx
0x140014b66  mov     rcx, [rbp+1A30h+var_20]
0x140014b6d  xor     rcx, rsp; StackCookie
0x140014b70  call    __security_check_cookie
0x140014b75  lea     r11, [rsp+1B30h+var_10]
0x140014b7d  mov     rbx, [r11+28h]
0x140014b81  mov     rsi, [r11+30h]
0x140014b85  mov     rsp, r11
0x140014b88  pop     r14
0x140014b8a  pop     rdi
0x140014b8b  pop     rbp
0x140014b8c  retn
0x140014b8d  mov     dil, r14b
0x140014b90  xor     edx, edx; hFile
0x140014b92  lea     rcx, LibFileName; "Windows.Media.Speech.UXRes.dll"
0x140014b99  lea     r8d, [rdx+22h]; dwFlags
0x140014b9d  call    cs:__imp_LoadLibraryExW
0x140014ba3  mov     rbx, rax
0x140014ba6  test    dil, dil
0x140014ba9  jz      short loc_140014BB6
0x140014bab  mov     rcx, [rsp+1B30h+OldValue]; OlValue
0x140014bb0  call    cs:__imp_Wow64RevertWow64FsRedirection
0x140014bb6  mov     [rsp+1B30h+OldValue], rbx
0x140014bbb  test    rbx, rbx
0x140014bbe  jz      loc_140014B26
0x140014bc4  mov     edi, 400h
0x140014bc9  lea     r8, [rsp+1B30h+Buffer]; lpBuffer
0x140014bce  mov     edx, edi; uID
0x140014bd0  mov     r9d, 100h; cchBufferMax
0x140014bd6  mov     rcx, rbx; hInstance
0x140014bd9  call    cs:__imp_LoadStringW
0x140014bdf  test    eax, eax
0x140014be1  jnz     short loc_140014C02
0x140014be3  mov     edx, 0C0h; void *
0x140014be8  mov     rcx, [rbp+1A38h]; this
0x140014bef  lea     r8, aOnecoreuapEndu_102; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x140014bf6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140014bfb  mov     ebx, eax
0x140014bfd  jmp     loc_140014B5A
0x140014c02  mov     r9d, edi; cchBufferMax
0x140014c05  lea     r8, [rbp+1A30h+var_10F0]; lpBuffer
0x140014c0c  mov     edx, 401h; uID
0x140014c11  mov     rcx, rbx; hInstance
0x140014c14  call    cs:__imp_LoadStringW
0x140014c1a  test    eax, eax
0x140014c1c  jnz     short loc_140014C25
0x140014c1e  mov     edx, 0C1h
0x140014c23  jmp     short loc_140014BE8
0x140014c25  mov     edi, 200h
0x140014c2a  lea     r8, [rbp+1A30h+var_14F0]; lpBuffer
0x140014c31  mov     r9d, edi; cchBufferMax
0x140014c34  mov     edx, 402h; uID
0x140014c39  mov     rcx, rbx; hInstance
0x140014c3c  call    cs:__imp_LoadStringW
0x140014c42  test    eax, eax
0x140014c44  jnz     short loc_140014C4D
0x140014c46  mov     edx, 0C2h
0x140014c4b  jmp     short loc_140014BE8
0x140014c4d  mov     r9d, edi; cchBufferMax
0x140014c50  lea     r8, [rbp+1A30h+var_18F0]; lpBuffer
0x140014c57  mov     edx, 403h; uID
0x140014c5c  mov     rcx, rbx; hInstance
0x140014c5f  call    cs:__imp_LoadStringW
0x140014c65  test    eax, eax
0x140014c67  jnz     short loc_140014C73
0x140014c69  mov     edx, 0C3h
0x140014c6e  jmp     loc_140014BE8
0x140014c73  lea     rax, [rbp+1A30h+var_18F0]
0x140014c7a  mov     rdx, rsi; unsigned __int16 **
0x140014c7d  mov     [rsp+1B30h+var_1B08], rax
0x140014c82  lea     r9, [rbp+1A30h+var_10F0]
0x140014c89  lea     rax, [rbp+1A30h+var_14F0]
0x140014c90  lea     r8, [rsp+1B30h+Buffer]
0x140014c95  mov     [rsp+1B30h+var_1B10], rax
0x140014c9a  lea     rcx, [rbp+1A30h+Source]; lpSource
0x140014ca1  call    ?FormatToastMessage@CNotifyVoiceClip@NLInternal@@CAJPEBGPEAPEAGZZ; NLInternal::CNotifyVoiceClip::FormatToastMessage(ushort const *,ushort * *,...)
0x140014ca6  mov     ebx, eax
0x140014ca8  test    eax, eax
0x140014caa  jns     short loc_140014CB9
0x140014cac  mov     r9d, eax
0x140014caf  mov     edx, 0C5h
0x140014cb4  jmp     loc_140014B47
0x140014cb9  mov     ebx, r14d
0x140014cbc  jmp     loc_140014B5A
```
