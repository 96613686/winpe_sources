# Microsoft::Bluetooth::Audio::Details::AudioLibControlClientImpl::LoadMicrosoftBluetoothAudio(void)

- ea: `0x1800285a0`
- end: `0x1800287d0`
- name: `?LoadMicrosoftBluetoothAudio@AudioLibControlClientImpl@Details@Audio@Bluetooth@Microsoft@@UEAAXXZ`
- size: `560`
- prototype: `void __fastcall(Microsoft::Bluetooth::Audio::Details::AudioLibControlClientImpl *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000e0c0`
- `0x180012554`
- `0x1800285a0`
- `0x1800288ac`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800286a6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800286a6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180028627`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180028627`

## string_xrefs

- `0x1800286c9`: `onecore\drivers\bluetooth\profiles\avrcp\avctp\service\lib\audiolibcontrolclient.cpp`
- `0x18002861a`: `Microsoft.Bluetooth.Audio.dll`

## pseudocode

```c
void __fastcall Microsoft::Bluetooth::Audio::Details::AudioLibControlClientImpl::LoadMicrosoftBluetoothAudio(
        Microsoft::Bluetooth::Audio::Details::AudioLibControlClientImpl *this)
{
  HMODULE *v1; // rbx
  _QWORD *v3; // rcx
  bool v4; // dl
  bool v5; // r8
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  int v8; // eax
  bool v9; // dl
  int v10; // [rsp+20h] [rbp-38h]
  __int16 v11; // [rsp+30h] [rbp-28h]
  char v12; // [rsp+40h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v1 = (HMODULE *)((char *)this + 8);
  if ( *((_QWORD *)this + 1) )
  {
    v3 = WPP_GLOBAL_Control;
    v4 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
    v5 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v12 = (char)this;
      v11 = 10;
LABEL_38:
      WPP_RECORDER_AND_TRACE_SF_q(
        v3[2],
        v4,
        v5,
        v3[5],
        2,
        1,
        v11,
        &WPP_ae2ad9942a4439d2a3f19bf635e3c4cd_Traceguids,
        v12);
    }
  }
  else
  {
    Library = LoadLibraryExW(L"Microsoft.Bluetooth.Audio.dll", 0, 0x800u);
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
      v1,
      Library);
    if ( *v1 )
    {
      ProcAddress = GetProcAddress(*v1, (LPCSTR)0x64);
      *((_QWORD *)this + 2) = ProcAddress;
      if ( ProcAddress )
      {
        v8 = ((__int64 (__fastcall *)(_QWORD))ProcAddress)(0);
        if ( v8 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x36,
            (unsigned int)"onecore\\drivers\\bluetooth\\profiles\\avrcp\\avctp\\service\\lib\\audiolibcontrolclient.cpp",
            (const char *)(unsigned int)v8,
            v10);
        v9 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
        if ( v9 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_AND_TRACE_SF_q(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v9,
            WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
            *((_QWORD *)WPP_GLOBAL_Control + 5),
            4,
            1,
            12,
            &WPP_ae2ad9942a4439d2a3f19bf635e3c4cd_Traceguids,
            (char)this);
      }
      else
      {
        wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
          v1,
          0);
        v3 = WPP_GLOBAL_Control;
        v4 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
        v5 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v12 = (char)this;
          v11 = 13;
          goto LABEL_38;
        }
      }
    }
    else
    {
      v3 = WPP_GLOBAL_Control;
      v4 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
      v5 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v12 = (char)this;
        v11 = 11;
        goto LABEL_38;
      }
    }
  }
}

```

## disassembly

```asm
0x1800285a0  mov     [rsp+arg_0], rbx
0x1800285a5  push    rdi
0x1800285a6  sub     rsp, 50h
0x1800285aa  lea     rbx, [rcx+8]
0x1800285ae  mov     rdi, rcx
0x1800285b1  cmp     qword ptr [rbx], 0
0x1800285b5  jz      short loc_180028618
0x1800285b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800285be  lea     rax, WPP_GLOBAL_Control
0x1800285c5  cmp     rcx, rax
0x1800285c8  jz      short loc_1800285DA
0x1800285ca  test    byte ptr [rcx+1Ch], 1
0x1800285ce  jz      short loc_1800285DA
0x1800285d0  cmp     byte ptr [rcx+19h], 2
0x1800285d4  jb      short loc_1800285DA
0x1800285d6  mov     dl, 1
0x1800285d8  jmp     short loc_1800285DC
0x1800285da  xor     dl, dl
0x1800285dc  lea     rax, WPP_RECORDER_INITIALIZED
0x1800285e3  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800285ea  setnz   r8b
0x1800285ee  test    dl, dl
0x1800285f0  jnz     short loc_1800285FB
0x1800285f2  test    r8b, r8b
0x1800285f5  jz      loc_1800287C5
0x1800285fb  mov     qword ptr [rsp+58h+var_18], rdi
0x180028600  lea     rax, WPP_ae2ad9942a4439d2a3f19bf635e3c4cd_Traceguids
0x180028607  mov     [rsp+58h+MessageGuid], rax
0x18002860c  mov     [rsp+58h+var_28], 0Ah
0x180028613  jmp     loc_1800287AB
0x180028618  xor     edx, edx; hFile
0x18002861a  lea     rcx, LibFileName; "Microsoft.Bluetooth.Audio.dll"
0x180028621  mov     r8d, 800h; dwFlags
0x180028627  call    cs:__imp_LoadLibraryExW
0x18002862d  mov     rdx, rax
0x180028630  mov     rcx, rbx
0x180028633  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x180028638  mov     rcx, [rbx]; hModule
0x18002863b  test    rcx, rcx
0x18002863e  jnz     short loc_1800286A1
0x180028640  mov     rcx, cs:WPP_GLOBAL_Control
0x180028647  lea     rax, WPP_GLOBAL_Control
0x18002864e  cmp     rcx, rax
0x180028651  jz      short loc_180028663
0x180028653  test    byte ptr [rcx+1Ch], 1
0x180028657  jz      short loc_180028663
0x180028659  cmp     byte ptr [rcx+19h], 2
0x18002865d  jb      short loc_180028663
0x18002865f  mov     dl, 1
0x180028661  jmp     short loc_180028665
0x180028663  xor     dl, dl
0x180028665  lea     rax, WPP_RECORDER_INITIALIZED
0x18002866c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180028673  setnz   r8b
0x180028677  test    dl, dl
0x180028679  jnz     short loc_180028684
0x18002867b  test    r8b, r8b
0x18002867e  jz      loc_1800287C5
0x180028684  mov     qword ptr [rsp+58h+var_18], rdi
0x180028689  lea     rax, WPP_ae2ad9942a4439d2a3f19bf635e3c4cd_Traceguids
0x180028690  mov     [rsp+58h+MessageGuid], rax
0x180028695  mov     [rsp+58h+var_28], 0Bh
0x18002869c  jmp     loc_1800287AB
0x1800286a1  mov     edx, 64h ; 'd'; lpProcName
0x1800286a6  call    cs:__imp_GetProcAddress
0x1800286ac  mov     [rdi+10h], rax
0x1800286b0  test    rax, rax
0x1800286b3  jz      loc_180028749
0x1800286b9  xor     ecx, ecx
0x1800286bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800286c0  test    eax, eax
0x1800286c2  jns     short loc_1800286DE
0x1800286c4  mov     rcx, [rsp+58h]; this
0x1800286c9  lea     r8, aOnecoreDrivers_26; "onecore\\drivers\\bluetooth\\profiles\\"...
0x1800286d0  mov     r9d, eax; char *
0x1800286d3  mov     edx, 36h ; '6'; void *
0x1800286d8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800286de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800286e5  lea     rax, WPP_GLOBAL_Control
0x1800286ec  cmp     rcx, rax
0x1800286ef  jz      short loc_180028701
0x1800286f1  test    byte ptr [rcx+1Ch], 1
0x1800286f5  jz      short loc_180028701
0x1800286f7  cmp     byte ptr [rcx+19h], 4
0x1800286fb  jb      short loc_180028701
0x1800286fd  mov     dl, 1
0x1800286ff  jmp     short loc_180028703
0x180028701  xor     dl, dl
0x180028703  lea     rax, WPP_RECORDER_INITIALIZED
0x18002870a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180028711  setnz   r8b
0x180028715  test    dl, dl
0x180028717  jnz     short loc_180028722
0x180028719  test    r8b, r8b
0x18002871c  jz      loc_1800287C5
0x180028722  mov     qword ptr [rsp+58h+var_18], rdi
0x180028727  lea     rax, WPP_ae2ad9942a4439d2a3f19bf635e3c4cd_Traceguids
0x18002872e  mov     [rsp+58h+MessageGuid], rax
0x180028733  mov     [rsp+58h+var_28], 0Ch
0x18002873a  mov     [rsp+58h+var_30], 1
0x180028742  mov     [rsp+58h+var_38], 4
0x180028747  jmp     short loc_1800287B8
0x180028749  xor     edx, edx
0x18002874b  mov     rcx, rbx
0x18002874e  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x180028753  mov     rcx, cs:WPP_GLOBAL_Control
0x18002875a  lea     rax, WPP_GLOBAL_Control
0x180028761  cmp     rcx, rax
0x180028764  jz      short loc_180028776
0x180028766  test    byte ptr [rcx+1Ch], 1
0x18002876a  jz      short loc_180028776
0x18002876c  cmp     byte ptr [rcx+19h], 2
0x180028770  jb      short loc_180028776
0x180028772  mov     dl, 1
0x180028774  jmp     short loc_180028778
0x180028776  xor     dl, dl; int
0x180028778  lea     rax, WPP_RECORDER_INITIALIZED
0x18002877f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180028786  setnz   r8b; int
0x18002878a  test    dl, dl
0x18002878c  jnz     short loc_180028793
0x18002878e  test    r8b, r8b
0x180028791  jz      short loc_1800287C5
0x180028793  mov     qword ptr [rsp+58h+var_18], rdi; char
0x180028798  lea     rax, WPP_ae2ad9942a4439d2a3f19bf635e3c4cd_Traceguids
0x18002879f  mov     [rsp+58h+MessageGuid], rax; MessageGuid
0x1800287a4  mov     [rsp+58h+var_28], 0Dh; __int16
0x1800287ab  mov     [rsp+58h+var_30], 1; int
0x1800287b3  mov     [rsp+58h+var_38], 2; char
0x1800287b8  mov     r9, [rcx+28h]; int
0x1800287bc  mov     rcx, [rcx+10h]; int
0x1800287c0  call    WPP_RECORDER_AND_TRACE_SF_q
0x1800287c5  mov     rbx, [rsp+58h+arg_0]
0x1800287ca  add     rsp, 50h
0x1800287ce  pop     rdi
0x1800287cf  retn
```
