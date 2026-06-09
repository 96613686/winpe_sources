# HidForceFeedbackBroker::InitializeIfNeeded(void)

- ea: `0x1800169fc`
- end: `0x180016c97`
- name: `?InitializeIfNeeded@HidForceFeedbackBroker@@AEAAJXZ`
- size: `667`
- prototype: `__int64 __fastcall(HidForceFeedbackBroker *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180018390`

## callees

- `0x180001304`
- `0x18000da08`
- `0x18000dad8`
- `0x1800169fc`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016a69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016a69`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180016a2b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180016a2b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180016c09`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180016c09`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180016a4b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180016a4b`

## string_xrefs

- `0x180016a9f`: `onecore\xbox\gameinput\feedback\hid\HidForceFeedbackBroker.cpp`
- `0x180016b49`: `onecore\xbox\gameinput\feedback\hid\HidForceFeedbackBroker.cpp`
- `0x180016a1e`: `dinput8.dll`

## pseudocode

```c
__int64 __fastcall HidForceFeedbackBroker::InitializeIfNeeded(HidForceFeedbackBroker *this)
{
  _QWORD *v1; // rsi
  __int64 v3; // rdx
  HMODULE Library; // rbx
  HMODULE v5; // rax
  DWORD LastError; // ebx
  int v7; // r8d
  int v8; // r9d
  int v10; // r8d
  int v11; // r9d
  int v12; // ecx
  char *v13; // rdx
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rdx
  HMODULE ModuleHandleW; // rax
  __int64 (*v18)(void); // [rsp+60h] [rbp+20h] BYREF
  int v19; // [rsp+68h] [rbp+28h] BYREF
  const char *v20; // [rsp+70h] [rbp+30h] BYREF

  v1 = (_QWORD *)((char *)this + 24);
  if ( !*((_QWORD *)this + 3) )
  {
    Library = LoadLibraryExW(L"dinput8.dll", 0, 0x800u);
    v5 = (HMODULE)*((_QWORD *)this + 2);
    if ( Library == v5 )
    {
      Library = (HMODULE)*((_QWORD *)this + 2);
    }
    else
    {
      if ( v5 )
        FreeLibrary(*((HMODULE *)this + 2));
      *((_QWORD *)this + 2) = Library;
    }
    if ( !Library )
    {
      LastError = GetLastError();
      if ( (unsigned int)dword_180069000 > 2 && (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
      {
        LODWORD(v18) = LastError;
        v20 = "onecore\\xbox\\gameinput\\feedback\\hid\\HidForceFeedbackBroker.cpp";
        v19 = 67;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          qword_180069018,
          (unsigned int)&dword_18005BD9C,
          v7,
          v8,
          (__int64)&v20,
          (__int64)&v19,
          (__int64)&v18);
      }
      if ( LastError )
      {
        if ( (int)LastError > 0 )
          return (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        return (DWORD)-2147418113;
      }
      return LastError;
    }
    v18 = 0;
    LastError = GetModuleProc<_DIDATAFORMAT const * (*)(void)>(Library, v3, &v18);
    if ( (LastError & 0x80000000) != 0 )
    {
      if ( (unsigned int)dword_180069000 <= 2 )
        return LastError;
      v12 = qword_180069010;
      if ( (qword_180069010 & 8) == 0 || (qword_180069018 & 8) != qword_180069018 )
        return LastError;
      v19 = 71;
      v13 = (char *)&unk_18005D5B0;
LABEL_22:
      v20 = "onecore\\xbox\\gameinput\\feedback\\hid\\HidForceFeedbackBroker.cpp";
      LODWORD(v18) = LastError;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v12,
        (_DWORD)v13,
        v10,
        v11,
        (__int64)&v20,
        (__int64)&v19,
        (__int64)&v18);
      return LastError;
    }
    v14 = v18();
    v15 = *((_QWORD *)this + 2);
    *((_QWORD *)this + 4) = v14;
    v18 = 0;
    LastError = GetModuleProc<long (*)(HINSTANCE__ *,unsigned long,_GUID const &,void * *,IUnknown *)>(v15, v16, &v18);
    if ( (LastError & 0x80000000) != 0 )
    {
      if ( (unsigned int)dword_180069000 <= 2 )
        return LastError;
      v12 = qword_180069010;
      if ( (qword_180069010 & 8) == 0 || (qword_180069018 & 8) != qword_180069018 )
        return LastError;
      v19 = 76;
      v13 = byte_18005D26B;
      goto LABEL_22;
    }
    if ( *v1 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v1 + 16LL))(*v1);
      *v1 = 0;
    }
    ModuleHandleW = GetModuleHandleW(0);
    LastError = ((__int64 (__fastcall *)(HMODULE, __int64, GUID *, _QWORD *, _QWORD))v18)(
                  ModuleHandleW,
                  2048,
                  &IID_IDirectInput8W,
                  v1,
                  0);
    if ( (LastError & 0x80000000) != 0 )
    {
      if ( (unsigned int)dword_180069000 <= 2 )
        return LastError;
      v12 = qword_180069010;
      if ( (qword_180069010 & 8) == 0 || (qword_180069018 & 8) != qword_180069018 )
        return LastError;
      v19 = 83;
      v13 = byte_18005B9ED;
      goto LABEL_22;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800169fc  mov     [rsp-18h+arg_18], rbx
0x180016a01  push    rbp
0x180016a02  push    rsi
0x180016a03  push    rdi
0x180016a04  mov     rbp, rsp
0x180016a07  sub     rsp, 40h
0x180016a0b  lea     rsi, [rcx+18h]
0x180016a0f  mov     rdi, rcx
0x180016a12  cmp     qword ptr [rsi], 0
0x180016a16  jnz     loc_180016C87
0x180016a1c  xor     edx, edx; hFile
0x180016a1e  lea     rcx, aDinput8Dll; "dinput8.dll"
0x180016a25  mov     r8d, 800h; dwFlags
0x180016a2b  call    cs:__imp_LoadLibraryExW
0x180016a32  nop     dword ptr [rax+rax+00h]
0x180016a37  mov     rbx, rax
0x180016a3a  mov     rax, [rdi+10h]
0x180016a3e  cmp     rbx, rax
0x180016a41  jz      short loc_180016A5D
0x180016a43  test    rax, rax
0x180016a46  jz      short loc_180016A57
0x180016a48  mov     rcx, rax; hLibModule
0x180016a4b  call    cs:__imp_FreeLibrary
0x180016a52  nop     dword ptr [rax+rax+00h]
0x180016a57  mov     [rdi+10h], rbx
0x180016a5b  jmp     short loc_180016A60
0x180016a5d  mov     rbx, rax
0x180016a60  test    rbx, rbx
0x180016a63  jnz     loc_180016AF8
0x180016a69  call    cs:__imp_GetLastError
0x180016a70  nop     dword ptr [rax+rax+00h]
0x180016a75  mov     ebx, eax
0x180016a77  mov     eax, cs:dword_180069000
0x180016a7d  cmp     eax, 2
0x180016a80  jbe     short loc_180016ADB
0x180016a82  mov     rcx, cs:qword_180069018
0x180016a89  mov     rax, cs:qword_180069010
0x180016a90  test    al, 8
0x180016a92  jz      short loc_180016ADB
0x180016a94  mov     rax, rcx
0x180016a97  and     eax, 8
0x180016a9a  cmp     rax, rcx
0x180016a9d  jnz     short loc_180016ADB
0x180016a9f  lea     rax, aOnecoreXboxGam_36; "onecore\\xbox\\gameinput\\feedback\\hid"...
0x180016aa6  mov     dword ptr [rbp+arg_0], ebx
0x180016aa9  mov     [rbp+arg_10], rax
0x180016aad  lea     rdx, dword_18005BD9C
0x180016ab4  lea     rax, [rbp+arg_0]
0x180016ab8  mov     [rbp+arg_8], 43h ; 'C'
0x180016abf  mov     [rsp+40h+var_10], rax
0x180016ac4  lea     rax, [rbp+arg_8]
0x180016ac8  mov     [rsp+40h+var_18], rax
0x180016acd  lea     rax, [rbp+arg_10]
0x180016ad1  mov     [rsp+40h+var_20], rax
0x180016ad6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180016adb  test    ebx, ebx
0x180016add  jnz     short loc_180016AE6
0x180016adf  mov     ebx, 8000FFFFh
0x180016ae4  jmp     short loc_180016AF1
0x180016ae6  jle     short loc_180016AF1
0x180016ae8  movzx   ebx, bx
0x180016aeb  or      ebx, 80070000h
0x180016af1  mov     eax, ebx
0x180016af3  jmp     loc_180016C89
0x180016af8  lea     r8, [rbp+arg_0]
0x180016afc  mov     [rbp+arg_0], 0
0x180016b04  mov     rcx, rbx
0x180016b07  call    ??$GetModuleProc@P6APEBU_DIDATAFORMAT@@XZ@@YAJPEAUHINSTANCE__@@PEBDPEAP6APEBU_DIDATAFORMAT@@XZ@Z; GetModuleProc<_DIDATAFORMAT const * (*)(void)>(HINSTANCE__ *,char const *,_DIDATAFORMAT const * (**)(void))
0x180016b0c  mov     ebx, eax
0x180016b0e  test    eax, eax
0x180016b10  jns     short loc_180016B7C
0x180016b12  mov     ecx, cs:dword_180069000
0x180016b18  cmp     ecx, 2
0x180016b1b  jbe     short loc_180016AF1
0x180016b1d  mov     rdx, cs:qword_180069018
0x180016b24  mov     rcx, cs:qword_180069010
0x180016b2b  test    cl, 8
0x180016b2e  jz      short loc_180016AF1
0x180016b30  mov     rax, rdx
0x180016b33  and     eax, 8
0x180016b36  cmp     rax, rdx
0x180016b39  jnz     short loc_180016AF1
0x180016b3b  mov     [rbp+arg_8], 47h ; 'G'
0x180016b42  lea     rdx, unk_18005D5B0
0x180016b49  lea     rax, aOnecoreXboxGam_36; "onecore\\xbox\\gameinput\\feedback\\hid"...
0x180016b50  mov     [rbp+arg_10], rax
0x180016b54  lea     rax, [rbp+arg_0]
0x180016b58  mov     [rsp+40h+var_10], rax
0x180016b5d  lea     rax, [rbp+arg_8]
0x180016b61  mov     [rsp+40h+var_18], rax
0x180016b66  lea     rax, [rbp+arg_10]
0x180016b6a  mov     [rsp+40h+var_20], rax
0x180016b6f  mov     dword ptr [rbp+arg_0], ebx
0x180016b72  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180016b77  jmp     loc_180016AF1
0x180016b7c  mov     rax, [rbp+arg_0]
0x180016b80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b85  mov     rcx, [rdi+10h]
0x180016b89  lea     r8, [rbp+arg_0]
0x180016b8d  mov     [rdi+20h], rax
0x180016b91  mov     [rbp+arg_0], 0
0x180016b99  call    ??$GetModuleProc@P6AJPEAUHINSTANCE__@@KAEBU_GUID@@PEAPEAXPEAUIUnknown@@@Z@@YAJPEAUHINSTANCE__@@PEBDPEAP6AJ0KAEBU_GUID@@PEAPEAXPEAUIUnknown@@@Z@Z; GetModuleProc<long (*)(HINSTANCE__ *,ulong,_GUID const &,void * *,IUnknown *)>(HINSTANCE__ *,char const *,long (**)(HINSTANCE__ *,ulong,_GUID const &,void * *,IUnknown *))
0x180016b9e  mov     ebx, eax
0x180016ba0  test    eax, eax
0x180016ba2  jns     short loc_180016BEC
0x180016ba4  mov     ecx, cs:dword_180069000
0x180016baa  cmp     ecx, 2
0x180016bad  jbe     loc_180016AF1
0x180016bb3  mov     rdx, cs:qword_180069018
0x180016bba  mov     rcx, cs:qword_180069010
0x180016bc1  test    cl, 8
0x180016bc4  jz      loc_180016AF1
0x180016bca  mov     rax, rdx
0x180016bcd  and     eax, 8
0x180016bd0  cmp     rax, rdx
0x180016bd3  jnz     loc_180016AF1
0x180016bd9  mov     [rbp+arg_8], 4Ch ; 'L'
0x180016be0  lea     rdx, byte_18005D26B
0x180016be7  jmp     loc_180016B49
0x180016bec  mov     rcx, [rsi]
0x180016bef  test    rcx, rcx
0x180016bf2  jz      short loc_180016C07
0x180016bf4  mov     rax, [rcx]
0x180016bf7  mov     rax, [rax+10h]
0x180016bfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c00  mov     qword ptr [rsi], 0
0x180016c07  xor     ecx, ecx; lpModuleName
0x180016c09  call    cs:__imp_GetModuleHandleW
0x180016c10  nop     dword ptr [rax+rax+00h]
0x180016c15  mov     r9, rsi
0x180016c18  mov     [rsp+40h+var_20], 0
0x180016c21  mov     rcx, rax
0x180016c24  lea     r8, IID_IDirectInput8W
0x180016c2b  mov     rax, [rbp+arg_0]
0x180016c2f  mov     edx, 800h
0x180016c34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c39  mov     ebx, eax
0x180016c3b  test    eax, eax
0x180016c3d  jns     short loc_180016C87
0x180016c3f  mov     ecx, cs:dword_180069000
0x180016c45  cmp     ecx, 2
0x180016c48  jbe     loc_180016AF1
0x180016c4e  mov     rdx, cs:qword_180069018
0x180016c55  mov     rcx, cs:qword_180069010
0x180016c5c  test    cl, 8
0x180016c5f  jz      loc_180016AF1
0x180016c65  mov     rax, rdx
0x180016c68  and     eax, 8
0x180016c6b  cmp     rax, rdx
0x180016c6e  jnz     loc_180016AF1
0x180016c74  mov     [rbp+arg_8], 53h ; 'S'
0x180016c7b  lea     rdx, byte_18005B9ED
0x180016c82  jmp     loc_180016B49
0x180016c87  xor     eax, eax
0x180016c89  mov     rbx, [rsp+40h+arg_18]
0x180016c8e  add     rsp, 40h
0x180016c92  pop     rdi
0x180016c93  pop     rsi
0x180016c94  pop     rbp
0x180016c95  retn
```
