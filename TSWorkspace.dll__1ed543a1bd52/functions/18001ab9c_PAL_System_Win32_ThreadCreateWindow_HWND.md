# PAL_System_Win32_ThreadCreateWindow(HWND__ * *)

- ea: `0x18001ab9c`
- end: `0x18001ae5f`
- name: `?PAL_System_Win32_ThreadCreateWindow@@YAJPEAPEAUHWND__@@@Z`
- size: `707`
- prototype: `__int64 __fastcall(HWND *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18001c8b0`

## callees

- `0x180001180`
- `0x1800044bf`
- `0x18000b1d8`
- `0x18000ece0`
- `0x18001ab9c`
- `0x18001ae68`
- `0x18001b6d4`
- `0x18009a520`

## import_xrefs

- `USER32!CreateWindowExW` at `0x18001adb1`
- `USER32!CreateWindowExW` at `0x18001adb1`

## string_xrefs

- `0x18001ac02`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32int.cpp`
- `0x18001aca0`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32int.cpp`
- `0x18001ade2`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32int.cpp`
- `0x18001abe7`: `PAL_System_Win32_ThreadCreateWindow`
- `0x18001ac85`: `PAL_System_Win32_ThreadCreateWindow`
- `0x18001adc7`: `PAL_System_Win32_ThreadCreateWindow`
- `0x18001acb0`: `Failed to initialize thread window class`
- `0x18001adf6`: `Failed to create thread window`

## pseudocode

```c
__int64 __fastcall PAL_System_Win32_ThreadCreateWindow(HWND *a1, __int64 a2, int a3, int a4)
{
  int ModuleSpecificClassName; // ebx
  const unsigned __int16 *v6; // rcx
  unsigned int v7; // r8d
  int v8; // r9d
  unsigned int CurrentThreadActivityIdPrefix; // eax
  HWND Window; // rax
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  int v15; // [rsp+60h] [rbp-A0h] BYREF
  int v16; // [rsp+64h] [rbp-9Ch] BYREF
  const char *v17; // [rsp+68h] [rbp-98h] BYREF
  const char *v18; // [rsp+70h] [rbp-90h] BYREF
  const char *v19; // [rsp+78h] [rbp-88h] BYREF
  WCHAR ClassName[264]; // [rsp+80h] [rbp-80h] BYREF

  if ( a1 )
  {
    memset_0(ClassName, 0, 0x208u);
    ModuleSpecificClassName = PAL_System_Win32_ThreadRegisterWindowClass();
    if ( ModuleSpecificClassName >= 0 )
    {
      ModuleSpecificClassName = PAL_System_Win32_GetModuleSpecificClassName(v6, ClassName, v7);
      if ( ModuleSpecificClassName >= 0 )
      {
        Window = CreateWindowExW(0, ClassName, 0, 0, 0, 0, 0, 0, HWND_MESSAGE, 0, 0, 0);
        if ( Window )
        {
          *a1 = Window;
          return 0;
        }
        else if ( (unsigned int)dword_1800EB958 > 2 )
        {
          v16 = 463;
          v19 = "PAL_System_Win32_ThreadCreateWindow";
          v15 = -2147467259;
          v18 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32int.cpp";
          v17 = "Failed to create thread window";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v11,
            (unsigned int)&byte_1800CD2B7,
            v12,
            v13,
            (__int64)&v17,
            (__int64)&v15,
            (__int64)&v18,
            (__int64)&v16,
            (__int64)&v19);
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          (unsigned int)WPP_c585fe5194613b5687849eb156704f7c_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)"Failed to get module specific class name",
          ModuleSpecificClassName);
      }
    }
    else if ( (unsigned int)dword_1800EB958 > 2 )
    {
      v16 = 447;
      v19 = "PAL_System_Win32_ThreadCreateWindow";
      v15 = ModuleSpecificClassName;
      v18 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32int.cpp";
      v17 = "Failed to initialize thread window class";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        dword_1800EB958,
        (unsigned int)byte_1800CD341,
        v7,
        v8,
        (__int64)&v17,
        (__int64)&v15,
        (__int64)&v18,
        (__int64)&v16,
        (__int64)&v19);
    }
  }
  else
  {
    ModuleSpecificClassName = -2147024809;
    if ( (unsigned int)dword_1800EB958 > 2 )
    {
      v15 = 435;
      v17 = "PAL_System_Win32_ThreadCreateWindow";
      v16 = -2147024809;
      v18 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32int.cpp";
      v19 = "NULL paramater passed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        0,
        (unsigned int)word_1800CD3D2,
        a3,
        a4,
        (__int64)&v19,
        (__int64)&v16,
        (__int64)&v18,
        (__int64)&v15,
        (__int64)&v17);
    }
  }
  return (unsigned int)ModuleSpecificClassName;
}

```

## disassembly

```asm
0x18001ab9c  mov     [rsp-8+arg_8], rbx
0x18001aba1  mov     [rsp-8+arg_10], rdi
0x18001aba6  push    rbp
0x18001aba7  lea     rbp, [rsp-1A0h]
0x18001abaf  sub     rsp, 2A0h
0x18001abb6  mov     rax, cs:__security_cookie
0x18001abbd  xor     rax, rsp
0x18001abc0  mov     [rbp+1A0h+var_10], rax
0x18001abc7  mov     rdi, rcx
0x18001abca  test    rcx, rcx
0x18001abcd  jnz     loc_18001AC5A
0x18001abd3  mov     eax, cs:dword_1800EB958
0x18001abd9  mov     ebx, 80070057h
0x18001abde  cmp     eax, 2
0x18001abe1  jbe     loc_18001AE39
0x18001abe7  lea     rax, aPalSystemWin32_2; "PAL_System_Win32_ThreadCreateWindow"
0x18001abee  mov     [rsp+2A0h+var_240], 1B3h
0x18001abf6  mov     [rsp+2A0h+var_238], rax
0x18001abfb  lea     rdx, word_1800CD3D2
0x18001ac02  lea     rax, aOnecoreTermsrv_7; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18001ac09  mov     [rsp+2A0h+var_23C], ebx
0x18001ac0d  mov     [rsp+2A0h+var_230], rax
0x18001ac12  lea     rax, aNullParamaterP; "NULL paramater passed"
0x18001ac19  mov     [rsp+2A0h+var_228], rax
0x18001ac1e  lea     rax, [rsp+2A0h+var_238]
0x18001ac23  mov     [rsp+2A0h+hWndParent], rax
0x18001ac28  lea     rax, [rsp+2A0h+var_240]
0x18001ac2d  mov     qword ptr [rsp+2A0h+nHeight], rax
0x18001ac32  lea     rax, [rsp+2A0h+var_230]
0x18001ac37  mov     qword ptr [rsp+2A0h+nWidth], rax
0x18001ac3c  lea     rax, [rsp+2A0h+var_23C]
0x18001ac41  mov     qword ptr [rsp+2A0h+Y], rax
0x18001ac46  lea     rax, [rsp+2A0h+var_228]
0x18001ac4b  mov     qword ptr [rsp+2A0h+X], rax
0x18001ac50  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001ac55  jmp     loc_18001AE39
0x18001ac5a  xor     edx, edx; Val
0x18001ac5c  lea     rcx, [rbp+1A0h+ClassName]; void *
0x18001ac60  mov     r8d, 208h; Size
0x18001ac66  call    memset_0
0x18001ac6b  call    ?PAL_System_Win32_ThreadRegisterWindowClass@@YAJXZ; PAL_System_Win32_ThreadRegisterWindowClass(void)
0x18001ac70  mov     ebx, eax
0x18001ac72  test    eax, eax
0x18001ac74  jns     short loc_18001ACEE
0x18001ac76  mov     ecx, cs:dword_1800EB958
0x18001ac7c  cmp     ecx, 2
0x18001ac7f  jbe     loc_18001AE39
0x18001ac85  lea     rax, aPalSystemWin32_2; "PAL_System_Win32_ThreadCreateWindow"
0x18001ac8c  mov     [rsp+2A0h+var_23C], 1BFh
0x18001ac94  mov     [rsp+2A0h+var_228], rax
0x18001ac99  lea     rdx, byte_1800CD341
0x18001aca0  lea     rax, aOnecoreTermsrv_7; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18001aca7  mov     [rsp+2A0h+var_240], ebx
0x18001acab  mov     [rsp+2A0h+var_230], rax
0x18001acb0  lea     rax, aFailedToInitia_1; "Failed to initialize thread window clas"...
0x18001acb7  mov     [rsp+2A0h+var_238], rax
0x18001acbc  lea     rax, [rsp+2A0h+var_228]
0x18001acc1  mov     [rsp+2A0h+hWndParent], rax
0x18001acc6  lea     rax, [rsp+2A0h+var_23C]
0x18001accb  mov     qword ptr [rsp+2A0h+nHeight], rax
0x18001acd0  lea     rax, [rsp+2A0h+var_230]
0x18001acd5  mov     qword ptr [rsp+2A0h+nWidth], rax
0x18001acda  lea     rax, [rsp+2A0h+var_240]
0x18001acdf  mov     qword ptr [rsp+2A0h+Y], rax
0x18001ace4  lea     rax, [rsp+2A0h+var_238]
0x18001ace9  jmp     loc_18001AC4B
0x18001acee  lea     rdx, [rbp+1A0h+ClassName]; unsigned __int16 *
0x18001acf2  call    ?PAL_System_Win32_GetModuleSpecificClassName@@YAJPEBGPEAGK@Z; PAL_System_Win32_GetModuleSpecificClassName(ushort const *,ushort *,ulong)
0x18001acf7  mov     ebx, eax
0x18001acf9  test    eax, eax
0x18001acfb  jns     short loc_18001AD61
0x18001acfd  mov     rax, cs:WPP_GLOBAL_Control
0x18001ad04  lea     rcx, WPP_GLOBAL_Control
0x18001ad0b  cmp     rax, rcx
0x18001ad0e  jz      loc_18001AE39
0x18001ad14  test    byte ptr [rax+1Ch], 8
0x18001ad18  jz      loc_18001AE39
0x18001ad1e  cmp     byte ptr [rax+19h], 2
0x18001ad22  jb      loc_18001AE39
0x18001ad28  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18001ad2d  lea     rcx, aFailedToGetMod; "Failed to get module specific class nam"...
0x18001ad34  mov     [rsp+2A0h+Y], ebx
0x18001ad38  mov     qword ptr [rsp+2A0h+X], rcx
0x18001ad3d  lea     r8, WPP_c585fe5194613b5687849eb156704f7c_Traceguids
0x18001ad44  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ad4b  mov     edx, 11h
0x18001ad50  mov     r9d, eax
0x18001ad53  mov     rcx, [rcx+10h]
0x18001ad57  call    WPP_SF_DsD
0x18001ad5c  jmp     loc_18001AE39
0x18001ad61  mov     [rsp+2A0h+lpParam], 0; lpParam
0x18001ad6a  lea     rdx, [rbp+1A0h+ClassName]; lpClassName
0x18001ad6e  mov     [rsp+2A0h+hInstance], 0; hInstance
0x18001ad77  xor     r9d, r9d; dwStyle
0x18001ad7a  mov     [rsp+2A0h+hMenu], 0; hMenu
0x18001ad83  xor     r8d, r8d; lpWindowName
0x18001ad86  mov     [rsp+2A0h+hWndParent], 0FFFFFFFFFFFFFFFDh; hWndParent
0x18001ad8f  xor     ecx, ecx; dwExStyle
0x18001ad91  mov     [rsp+2A0h+nHeight], 0; nHeight
0x18001ad99  mov     [rsp+2A0h+nWidth], 0; nWidth
0x18001ada1  mov     [rsp+2A0h+Y], 0; Y
0x18001ada9  mov     [rsp+2A0h+X], 0; X
0x18001adb1  call    cs:__imp_CreateWindowExW
0x18001adb7  test    rax, rax
0x18001adba  jnz     short loc_18001AE34
0x18001adbc  mov     eax, cs:dword_1800EB958
0x18001adc2  cmp     eax, 2
0x18001adc5  jbe     short loc_18001AE39
0x18001adc7  lea     rax, aPalSystemWin32_2; "PAL_System_Win32_ThreadCreateWindow"
0x18001adce  mov     [rsp+2A0h+var_23C], 1CFh
0x18001add6  mov     [rsp+2A0h+var_228], rax
0x18001addb  lea     rdx, byte_1800CD2B7
0x18001ade2  lea     rax, aOnecoreTermsrv_7; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18001ade9  mov     [rsp+2A0h+var_240], 80004005h
0x18001adf1  mov     [rsp+2A0h+var_230], rax
0x18001adf6  lea     rax, aFailedToCreate_6; "Failed to create thread window"
0x18001adfd  mov     [rsp+2A0h+var_238], rax
0x18001ae02  lea     rax, [rsp+2A0h+var_228]
0x18001ae07  mov     [rsp+2A0h+hWndParent], rax
0x18001ae0c  lea     rax, [rsp+2A0h+var_23C]
0x18001ae11  mov     qword ptr [rsp+2A0h+nHeight], rax
0x18001ae16  lea     rax, [rsp+2A0h+var_230]
0x18001ae1b  mov     qword ptr [rsp+2A0h+nWidth], rax
0x18001ae20  lea     rax, [rsp+2A0h+var_240]
0x18001ae25  mov     qword ptr [rsp+2A0h+Y], rax
0x18001ae2a  lea     rax, [rsp+2A0h+var_238]
0x18001ae2f  jmp     loc_18001AC4B
0x18001ae34  mov     [rdi], rax
0x18001ae37  xor     ebx, ebx
0x18001ae39  mov     eax, ebx
0x18001ae3b  mov     rcx, [rbp+1A0h+var_10]
0x18001ae42  xor     rcx, rsp; StackCookie
0x18001ae45  call    __security_check_cookie
0x18001ae4a  lea     r11, [rsp+2A0h+var_s0]
0x18001ae52  mov     rbx, [r11+18h]
0x18001ae56  mov     rdi, [r11+20h]
0x18001ae5a  mov     rsp, r11
0x18001ae5d  pop     rbp
0x18001ae5e  retn
```
