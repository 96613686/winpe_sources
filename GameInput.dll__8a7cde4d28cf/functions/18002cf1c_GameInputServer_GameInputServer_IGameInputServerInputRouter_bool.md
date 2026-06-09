# GameInputServer::GameInputServer(IGameInputServerInputRouter *,bool)

- ea: `0x18002cf1c`
- end: `0x18002d1bf`
- name: `??0GameInputServer@@AEAA@PEAUIGameInputServerInputRouter@@_N@Z`
- size: `675`
- prototype: `GameInputServer *__fastcall(GameInputServer *__hidden this, struct IGameInputServerInputRouter *, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18003adb0`

## callees

- `0x180001540`
- `0x18002cf1c`
- `0x180045090`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002d031`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002d07e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002d031`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002d07e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002d057`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002d0a0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002d057`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002d0a0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002d0bf`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002d0e0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002d0bf`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002d0e0`

## string_xrefs

- `0x18002d04d`: `CoreUIOpenExisting`
- `0x18002d15a`: `GameInputServer: Created`

## pseudocode

```c
GameInputServer *__fastcall GameInputServer::GameInputServer(
        GameInputServer *this,
        int (__fastcall ***a2)(struct IGameInputServerInputRouter *, GUID *, const char **),
        char a3)
{
  bool v3; // zf
  int v4; // r9d
  int (__fastcall **v6)(struct IGameInputServerInputRouter *, GUID *, const char **); // rax
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  HMODULE v9; // rax
  FARPROC v10; // rax
  const char *v12; // [rsp+50h] [rbp+8h] BYREF
  const char *v13; // [rsp+58h] [rbp+10h] BYREF
  int v14; // [rsp+60h] [rbp+18h] BYREF

  LOBYTE(v14) = a3;
  *((_QWORD *)this + 3) = a2;
  v3 = byte_180069913 == 0;
  *(_QWORD *)this = &GameInputServer::`vftable';
  v4 = (int)a2;
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_DWORD *)this + 18) = 0;
  *((_QWORD *)this + 8) = (char *)this + 56;
  *((_QWORD *)this + 7) = (char *)this + 56;
  *((_DWORD *)this + 24) = 0;
  *((_QWORD *)this + 11) = (char *)this + 80;
  *((_QWORD *)this + 10) = (char *)this + 80;
  *((_DWORD *)this + 30) = 0;
  *((_QWORD *)this + 14) = (char *)this + 104;
  *((_QWORD *)this + 13) = (char *)this + 104;
  *((_DWORD *)this + 42) = 0;
  *((_QWORD *)this + 20) = (char *)this + 152;
  *((_QWORD *)this + 19) = (char *)this + 152;
  *((_DWORD *)this + 32) = 0;
  *((_BYTE *)this + 132) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 22) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_QWORD *)this + 24) = 0;
  *((_QWORD *)this + 25) = 0;
  *((_QWORD *)this + 26) = 0;
  *((_QWORD *)this + 27) = 0;
  if ( !v3 && a2 )
  {
    v6 = *a2;
    v12 = 0;
    if ( (*v6)((struct IGameInputServerInputRouter *)a2, &GUID_f1738582_1e0c_4ff8_82e3_41fef5d9df1a, &v12) < 0 )
    {
      Library = LoadLibraryExW(L"coremessaging", 0, 0x800u);
      *((_QWORD *)this + 25) = Library;
      if ( Library )
      {
        ProcAddress = GetProcAddress(Library, "CoreUIOpenExisting");
        *((_QWORD *)this + 23) = ProcAddress;
        if ( ProcAddress )
        {
          v9 = LoadLibraryExW(L"win32u", 0, 0x800u);
          *((_QWORD *)this + 26) = v9;
          if ( v9 )
          {
            v10 = GetProcAddress(v9, "NtMITSetKeyboardInputRoutingPolicy");
            *((_QWORD *)this + 24) = v10;
            if ( v10 )
              goto LABEL_12;
            FreeLibrary(*((HMODULE *)this + 26));
            *((_QWORD *)this + 26) = 0;
          }
          *((_QWORD *)this + 23) = 0;
        }
        FreeLibrary(*((HMODULE *)this + 25));
        *((_QWORD *)this + 25) = 0;
      }
    }
    else
    {
      (*(void (__fastcall **)(const char *))(*(_QWORD *)v12 + 16LL))(v12);
    }
  }
LABEL_12:
  *((_QWORD *)this + 29) = 0;
  *((_QWORD *)this + 30) = 0;
  *((_QWORD *)this + 31) = 0;
  *((_BYTE *)this + 256) = 0;
  *((_QWORD *)this + 33) = 0;
  *((_BYTE *)this + 272) = 0;
  *((_QWORD *)this + 35) = 0;
  *((_DWORD *)this + 72) = 0;
  if ( (unsigned int)dword_180069000 > 4
    && (qword_180069010 & 0x400) != 0
    && (qword_180069018 & 0x400) == qword_180069018 )
  {
    v14 = 76;
    v12 = "GameInputServer: Created";
    v13 = "onecore\\xbox\\gameinput\\server\\gameinputserver.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      qword_180069018,
      (unsigned int)byte_18005F37B,
      a3,
      v4,
      (__int64)&v13,
      (__int64)&v14,
      (__int64)&v12);
  }
  ControllerWatcher::Create((struct ControllerWatcher **)&qword_180069878);
  return this;
}

```

## disassembly

```asm
0x18002cf1c  mov     r11, rsp
0x18002cf1f  mov     [r11+20h], rbx
0x18002cf23  mov     [r11+18h], r8b
0x18002cf27  push    rdi
0x18002cf28  sub     rsp, 40h
0x18002cf2c  xor     edi, edi
0x18002cf2e  mov     [rcx+18h], rdx
0x18002cf32  cmp     cs:byte_180069913, dil
0x18002cf39  lea     rax, ??_7GameInputServer@@6B@; const GameInputServer::`vftable'
0x18002cf40  mov     [rcx], rax
0x18002cf43  mov     r9, rdx
0x18002cf46  mov     [rcx+8], edi
0x18002cf49  lea     rax, [rcx+38h]
0x18002cf4d  mov     [rcx+20h], rdi
0x18002cf51  mov     rbx, rcx
0x18002cf54  mov     [rcx+28h], rdi
0x18002cf58  mov     [rcx+30h], rdi
0x18002cf5c  mov     [rcx+10h], rdi
0x18002cf60  mov     [rax+10h], edi
0x18002cf63  mov     [rax+8], rax
0x18002cf67  mov     [rax], rax
0x18002cf6a  lea     rax, [rcx+50h]
0x18002cf6e  mov     [rax+10h], edi
0x18002cf71  mov     [rax+8], rax
0x18002cf75  mov     [rax], rax
0x18002cf78  lea     rax, [rcx+68h]
0x18002cf7c  mov     [rax+10h], edi
0x18002cf7f  mov     [rax+8], rax
0x18002cf83  mov     [rax], rax
0x18002cf86  lea     rax, [rcx+98h]
0x18002cf8d  mov     [rax+10h], edi
0x18002cf90  mov     [rax+8], rax
0x18002cf94  mov     [rax], rax
0x18002cf97  mov     [rcx+80h], edi
0x18002cf9d  mov     [rcx+84h], dil
0x18002cfa4  mov     [rcx+88h], rdi
0x18002cfab  mov     [rcx+90h], rdi
0x18002cfb2  mov     [rcx+0B0h], rdi
0x18002cfb9  mov     [rcx+0B8h], rdi
0x18002cfc0  mov     [rcx+0C0h], rdi
0x18002cfc7  mov     [rcx+0C8h], rdi
0x18002cfce  mov     [rcx+0D0h], rdi
0x18002cfd5  mov     [rcx+0D8h], rdi
0x18002cfdc  jz      loc_18002D0F3
0x18002cfe2  test    rdx, rdx
0x18002cfe5  jz      loc_18002D0F3
0x18002cfeb  mov     rax, [rdx]
0x18002cfee  lea     r8, [r11+8]
0x18002cff2  lea     rdx, _GUID_f1738582_1e0c_4ff8_82e3_41fef5d9df1a
0x18002cff9  mov     [r11+8], rdi
0x18002cffd  mov     rcx, r9
0x18002d000  mov     rax, [rax]
0x18002d003  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d008  test    eax, eax
0x18002d00a  js      short loc_18002D022
0x18002d00c  mov     rcx, [rsp+48h+arg_0]
0x18002d011  mov     rax, [rcx]
0x18002d014  mov     rax, [rax+10h]
0x18002d018  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d01d  jmp     loc_18002D0F3
0x18002d022  xor     edx, edx; hFile
0x18002d024  lea     rcx, aCoremessaging; "coremessaging"
0x18002d02b  mov     r8d, 800h; dwFlags
0x18002d031  call    cs:__imp_LoadLibraryExW
0x18002d038  nop     dword ptr [rax+rax+00h]
0x18002d03d  mov     [rbx+0C8h], rax
0x18002d044  test    rax, rax
0x18002d047  jz      loc_18002D0F3
0x18002d04d  lea     rdx, aCoreuiopenexis; "CoreUIOpenExisting"
0x18002d054  mov     rcx, rax; hModule
0x18002d057  call    cs:__imp_GetProcAddress
0x18002d05e  nop     dword ptr [rax+rax+00h]
0x18002d063  mov     [rbx+0B8h], rax
0x18002d06a  test    rax, rax
0x18002d06d  jz      short loc_18002D0D9
0x18002d06f  xor     edx, edx; hFile
0x18002d071  lea     rcx, aWin32u; "win32u"
0x18002d078  mov     r8d, 800h; dwFlags
0x18002d07e  call    cs:__imp_LoadLibraryExW
0x18002d085  nop     dword ptr [rax+rax+00h]
0x18002d08a  mov     [rbx+0D0h], rax
0x18002d091  test    rax, rax
0x18002d094  jz      short loc_18002D0D2
0x18002d096  lea     rdx, aNtmitsetkeyboa; "NtMITSetKeyboardInputRoutingPolicy"
0x18002d09d  mov     rcx, rax; hModule
0x18002d0a0  call    cs:__imp_GetProcAddress
0x18002d0a7  nop     dword ptr [rax+rax+00h]
0x18002d0ac  mov     [rbx+0C0h], rax
0x18002d0b3  test    rax, rax
0x18002d0b6  jnz     short loc_18002D0F3
0x18002d0b8  mov     rcx, [rbx+0D0h]; hLibModule
0x18002d0bf  call    cs:__imp_FreeLibrary
0x18002d0c6  nop     dword ptr [rax+rax+00h]
0x18002d0cb  mov     [rbx+0D0h], rdi
0x18002d0d2  mov     [rbx+0B8h], rdi
0x18002d0d9  mov     rcx, [rbx+0C8h]; hLibModule
0x18002d0e0  call    cs:__imp_FreeLibrary
0x18002d0e7  nop     dword ptr [rax+rax+00h]
0x18002d0ec  mov     [rbx+0C8h], rdi
0x18002d0f3  mov     [rbx+0E8h], rdi
0x18002d0fa  xor     eax, eax
0x18002d0fc  mov     [rbx+0F0h], rax
0x18002d103  mov     [rbx+0F8h], rax
0x18002d10a  mov     [rbx+100h], dil
0x18002d111  mov     [rbx+108h], rdi
0x18002d118  mov     [rbx+110h], dil
0x18002d11f  mov     [rbx+118h], rdi
0x18002d126  mov     [rbx+120h], edi
0x18002d12c  mov     eax, cs:dword_180069000
0x18002d132  cmp     eax, 4
0x18002d135  jbe     short loc_18002D1A4
0x18002d137  mov     rcx, cs:qword_180069018
0x18002d13e  mov     edx, 400h
0x18002d143  mov     rax, cs:qword_180069010
0x18002d14a  test    rdx, rax
0x18002d14d  jz      short loc_18002D1A4
0x18002d14f  mov     rax, rcx
0x18002d152  and     rax, rdx
0x18002d155  cmp     rax, rcx
0x18002d158  jnz     short loc_18002D1A4
0x18002d15a  lea     rax, aGameinputserve_4; "GameInputServer: Created"
0x18002d161  mov     [rsp+48h+arg_10], 4Ch ; 'L'
0x18002d169  mov     [rsp+48h+arg_0], rax
0x18002d16e  lea     rdx, byte_18005F37B
0x18002d175  lea     rax, aOnecoreXboxGam_0; "onecore\\xbox\\gameinput\\server\\gamei"...
0x18002d17c  mov     [rsp+48h+arg_8], rax
0x18002d181  lea     rax, [rsp+48h+arg_0]
0x18002d186  mov     [rsp+48h+var_18], rax
0x18002d18b  lea     rax, [rsp+48h+arg_10]
0x18002d190  mov     [rsp+48h+var_20], rax
0x18002d195  lea     rax, [rsp+48h+arg_8]
0x18002d19a  mov     [rsp+48h+var_28], rax
0x18002d19f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18002d1a4  lea     rcx, qword_180069878; struct ControllerWatcher **
0x18002d1ab  call    ?Create@ControllerWatcher@@SAJPEAPEAV1@@Z; ControllerWatcher::Create(ControllerWatcher * *)
0x18002d1b0  mov     rax, rbx
0x18002d1b3  mov     rbx, [rsp+48h+arg_18]
0x18002d1b8  add     rsp, 40h
0x18002d1bc  pop     rdi
0x18002d1bd  retn
```
