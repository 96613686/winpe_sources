# SystemSettings::DataModel::CKeyboardAccessSPIBoolSetting::DoSetValue(bool)

- ea: `0x1800756f0`
- end: `0x180075968`
- name: `?DoSetValue@CKeyboardAccessSPIBoolSetting@DataModel@SystemSettings@@MEAAJ_N@Z`
- size: `632`
- prototype: `__int64 __fastcall(SystemSettings::DataModel::CKeyboardAccessSPIBoolSetting *__hidden this, bool)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callees

- `0x180045080`
- `0x180074320`
- `0x180074378`
- `0x1800743d0`
- `0x1800756f0`
- `0x180075dcc`
- `0x1800881f0`

## import_xrefs

- `USER32!SystemParametersInfoW` at `0x180075762`
- `USER32!SystemParametersInfoW` at `0x1800757b4`
- `USER32!SystemParametersInfoW` at `0x180075806`
- `USER32!SystemParametersInfoW` at `0x180075872`
- `USER32!SystemParametersInfoW` at `0x1800758ca`
- `USER32!SystemParametersInfoW` at `0x18007591f`
- `USER32!SystemParametersInfoW` at `0x180075762`
- `USER32!SystemParametersInfoW` at `0x1800757b4`
- `USER32!SystemParametersInfoW` at `0x180075806`
- `USER32!SystemParametersInfoW` at `0x180075872`
- `USER32!SystemParametersInfoW` at `0x1800758ca`
- `USER32!SystemParametersInfoW` at `0x18007591f`

## string_xrefs

- `0x180075777`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\keyboardaid.cpp`
- `0x1800757c9`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\keyboardaid.cpp`
- `0x18007581f`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\keyboardaid.cpp`
- `0x180075887`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\keyboardaid.cpp`
- `0x1800758df`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\keyboardaid.cpp`
- `0x180075934`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\keyboardaid.cpp`

## pseudocode

```c
__int64 __fastcall SystemSettings::DataModel::CKeyboardAccessSPIBoolSetting::DoSetValue(
        SystemSettings::DataModel::CKeyboardAccessSPIBoolSetting *this,
        bool a2)
{
  int v4; // r9d
  _DWORD *KeyState_tagFILTERKEYS_50; // rax
  __int64 v6; // r8
  __int64 v7; // r9
  const char *v8; // r9
  __int64 KeyState_tagSTICKYKEYS_58; // rax
  __int64 v10; // r8
  __int64 v11; // r9
  const char *v12; // r9
  __int64 KeyState_tagTOGGLEKEYS_52; // rax
  __int64 v14; // r8
  __int64 v15; // r9
  const char *v16; // r9
  _DWORD *v17; // rax
  __int64 v18; // r8
  __int64 v19; // r9
  const char *v20; // r9
  __int64 v21; // rax
  __int64 v22; // r8
  __int64 v23; // r9
  const char *v24; // r9
  __int64 v25; // rax
  __int64 v26; // r8
  __int64 v27; // r9
  const char *v28; // r9
  const char *v29; // r9
  __int64 result; // rax
  int pvParam; // [rsp+20h] [rbp-48h] BYREF
  int FlagsFromBool; // [rsp+24h] [rbp-44h]
  __int128 v33; // [rsp+28h] [rbp-40h]
  _BYTE v34[32]; // [rsp+40h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  int v36; // [rsp+70h] [rbp+8h] BYREF
  int v37; // [rsp+74h] [rbp+Ch]

  try
  {
    v4 = *(_DWORD *)(*((_QWORD *)this + 11) + 64LL);
    if ( v4 )
    {
      if ( v4 == 1 )
      {
        KeyState_tagFILTERKEYS_50 = (_DWORD *)SystemSettings::DataModel::_anonymous_namespace_::GetKeyState_tagFILTERKEYS_50_(v34);
        LOBYTE(v6) = a2;
        FlagsFromBool = SystemSettings::DataModel::_anonymous_namespace_::GetFlagsFromBool(
                          (unsigned int)KeyState_tagFILTERKEYS_50[1],
                          8,
                          v6,
                          KeyState_tagFILTERKEYS_50,
                          *KeyState_tagFILTERKEYS_50);
        v33 = *(_OWORD *)(v7 + 8);
        if ( !SystemParametersInfoW(0x33u, 0x18u, &pvParam, 3u) )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0x5E,
            (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\keyboardaid.cpp",
            v8);
        KeyState_tagSTICKYKEYS_58 = SystemSettings::DataModel::_anonymous_namespace_::GetKeyState_tagSTICKYKEYS_58_(retaddr);
        v36 = KeyState_tagSTICKYKEYS_58;
        LOBYTE(v10) = a2;
        v37 = SystemSettings::DataModel::_anonymous_namespace_::GetFlagsFromBool(
                HIDWORD(KeyState_tagSTICKYKEYS_58),
                8,
                v10,
                v11,
                pvParam);
        if ( !SystemParametersInfoW(0x3Bu, 8u, &v36, 3u) )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0x5E,
            (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\keyboardaid.cpp",
            v12);
        KeyState_tagTOGGLEKEYS_52 = SystemSettings::DataModel::_anonymous_namespace_::GetKeyState_tagTOGGLEKEYS_52_(retaddr);
        v36 = KeyState_tagTOGGLEKEYS_52;
        LOBYTE(v14) = a2;
        v37 = SystemSettings::DataModel::_anonymous_namespace_::GetFlagsFromBool(
                HIDWORD(KeyState_tagTOGGLEKEYS_52),
                8,
                v14,
                v15,
                pvParam);
        if ( !SystemParametersInfoW(0x35u, 8u, &v36, 3u) )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0x5E,
            (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\keyboardaid.cpp",
            v16);
      }
    }
    else
    {
      v17 = (_DWORD *)SystemSettings::DataModel::_anonymous_namespace_::GetKeyState_tagFILTERKEYS_50_(v34);
      LOBYTE(v18) = a2;
      FlagsFromBool = SystemSettings::DataModel::_anonymous_namespace_::GetFlagsFromBool(
                        (unsigned int)v17[1],
                        16,
                        v18,
                        v17,
                        *v17);
      v33 = *(_OWORD *)(v19 + 8);
      if ( !SystemParametersInfoW(0x33u, 0x18u, &pvParam, 3u) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x5E,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\keyboardaid.cpp",
          v20);
      v21 = SystemSettings::DataModel::_anonymous_namespace_::GetKeyState_tagSTICKYKEYS_58_(retaddr);
      v36 = v21;
      LOBYTE(v22) = a2;
      v37 = SystemSettings::DataModel::_anonymous_namespace_::GetFlagsFromBool(HIDWORD(v21), 16, v22, v23, pvParam);
      if ( !SystemParametersInfoW(0x3Bu, 8u, &v36, 3u) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x5E,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\keyboardaid.cpp",
          v24);
      v25 = SystemSettings::DataModel::_anonymous_namespace_::GetKeyState_tagTOGGLEKEYS_52_(retaddr);
      v36 = v25;
      LOBYTE(v26) = a2;
      v37 = SystemSettings::DataModel::_anonymous_namespace_::GetFlagsFromBool(HIDWORD(v25), 16, v26, v27, pvParam);
      if ( !SystemParametersInfoW(0x35u, 8u, &v36, 3u) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x5E,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\keyboardaid.cpp",
          v28);
    }
    SystemSettings::DataModel::CInBoxATRegBoolSetting::DoSetValue(this, a2);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x530,
                           (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\keyboardaid.cpp",
                           v29);
  }
  return result;
}

```

## disassembly

```asm
0x1800756f0  mov     [rsp+arg_8], rbx
0x1800756f5  mov     [rsp+arg_10], rsi
0x1800756fa  push    rdi
0x1800756fb  sub     rsp, 60h
0x1800756ff  mov     bl, dl
0x180075701  mov     rsi, rcx
0x180075704  mov     r8, [rcx+58h]
0x180075708  mov     r9d, [r8+40h]
0x18007570c  test    r9d, r9d
0x18007570f  jz      loc_18007582E
0x180075715  cmp     r9d, 1
0x180075719  jnz     loc_180075943
0x18007571f  lea     rcx, [rsp+68h+var_28]; pvParam
0x180075724  call    SystemSettings__DataModel___anonymous_namespace___GetKeyState_tagFILTERKEYS_50_
0x180075729  mov     r9, rax
0x18007572c  mov     ecx, [rax]
0x18007572e  mov     [rsp+68h+pvParam], ecx
0x180075732  mov     r8b, bl
0x180075735  mov     edi, 8
0x18007573a  mov     edx, edi
0x18007573c  mov     ecx, [rax+4]
0x18007573f  call    SystemSettings__DataModel___anonymous_namespace___GetFlagsFromBool
0x180075744  mov     [rsp+68h+var_44], eax
0x180075748  movups  xmm0, xmmword ptr [r9+8]
0x18007574d  movdqu  [rsp+68h+var_40], xmm0
0x180075753  lea     r9d, [rdi-5]; fWinIni
0x180075757  lea     r8, [rsp+68h+pvParam]; pvParam
0x18007575c  lea     edx, [rdi+10h]; uiParam
0x18007575f  lea     ecx, [rdi+2Bh]; uiAction
0x180075762  call    cs:__imp_SystemParametersInfoW
0x180075769  nop     dword ptr [rax+rax+00h]
0x18007576e  mov     rcx, [rsp+68h]; this
0x180075773  test    eax, eax
0x180075775  jnz     short loc_180075786
0x180075777  lea     r8, aShellSystemset_105; "shell\\systemsettingsthreshold\\handler"...
0x18007577e  lea     edx, [rdi+56h]; void *
0x180075781  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180075786  call    SystemSettings__DataModel___anonymous_namespace___GetKeyState_tagSTICKYKEYS_58_
0x18007578b  mov     [rsp+68h+arg_0], eax
0x18007578f  shr     rax, 20h
0x180075793  mov     r8b, bl
0x180075796  mov     edx, edi
0x180075798  mov     ecx, eax
0x18007579a  call    SystemSettings__DataModel___anonymous_namespace___GetFlagsFromBool
0x18007579f  mov     [rsp+68h+arg_4], eax
0x1800757a3  mov     r9d, 3; fWinIni
0x1800757a9  lea     r8, [rsp+68h+arg_0]; pvParam
0x1800757ae  mov     edx, edi; uiParam
0x1800757b0  lea     ecx, [r9+38h]; uiAction
0x1800757b4  call    cs:__imp_SystemParametersInfoW
0x1800757bb  nop     dword ptr [rax+rax+00h]
0x1800757c0  mov     rcx, [rsp+68h]; this
0x1800757c5  test    eax, eax
0x1800757c7  jnz     short loc_1800757D8
0x1800757c9  lea     r8, aShellSystemset_105; "shell\\systemsettingsthreshold\\handler"...
0x1800757d0  lea     edx, [rax+5Eh]; void *
0x1800757d3  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800757d8  call    SystemSettings__DataModel___anonymous_namespace___GetKeyState_tagTOGGLEKEYS_52_
0x1800757dd  mov     [rsp+68h+arg_0], eax
0x1800757e1  shr     rax, 20h
0x1800757e5  mov     r8b, bl
0x1800757e8  mov     edx, edi
0x1800757ea  mov     ecx, eax
0x1800757ec  call    SystemSettings__DataModel___anonymous_namespace___GetFlagsFromBool
0x1800757f1  mov     [rsp+68h+arg_4], eax
0x1800757f5  mov     r9d, 3; fWinIni
0x1800757fb  lea     r8, [rsp+68h+arg_0]; pvParam
0x180075800  mov     edx, edi; uiParam
0x180075802  lea     ecx, [r9+32h]; uiAction
0x180075806  call    cs:__imp_SystemParametersInfoW
0x18007580d  nop     dword ptr [rax+rax+00h]
0x180075812  mov     rcx, [rsp+68h]; this
0x180075817  test    eax, eax
0x180075819  jnz     loc_180075943
0x18007581f  lea     r8, aShellSystemset_105; "shell\\systemsettingsthreshold\\handler"...
0x180075826  lea     edx, [rax+5Eh]; void *
0x180075829  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18007582e  lea     rcx, [rsp+68h+var_28]; pvParam
0x180075833  call    SystemSettings__DataModel___anonymous_namespace___GetKeyState_tagFILTERKEYS_50_
0x180075838  mov     r9, rax
0x18007583b  mov     ecx, [rax]
0x18007583d  mov     [rsp+68h+pvParam], ecx
0x180075841  mov     r8b, bl
0x180075844  mov     edx, 10h
0x180075849  mov     ecx, [rax+4]
0x18007584c  call    SystemSettings__DataModel___anonymous_namespace___GetFlagsFromBool
0x180075851  mov     [rsp+68h+var_44], eax
0x180075855  movups  xmm0, xmmword ptr [r9+8]
0x18007585a  movdqu  [rsp+68h+var_40], xmm0
0x180075860  mov     r9d, 3; fWinIni
0x180075866  lea     r8, [rsp+68h+pvParam]; pvParam
0x18007586b  lea     edx, [r9+15h]; uiParam
0x18007586f  lea     ecx, [rdx+1Bh]; uiAction
0x180075872  call    cs:__imp_SystemParametersInfoW
0x180075879  nop     dword ptr [rax+rax+00h]
0x18007587e  mov     rcx, [rsp+68h]; this
0x180075883  test    eax, eax
0x180075885  jnz     short loc_180075896
0x180075887  lea     r8, aShellSystemset_105; "shell\\systemsettingsthreshold\\handler"...
0x18007588e  lea     edx, [rax+5Eh]; void *
0x180075891  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180075896  call    SystemSettings__DataModel___anonymous_namespace___GetKeyState_tagSTICKYKEYS_58_
0x18007589b  mov     [rsp+68h+arg_0], eax
0x18007589f  shr     rax, 20h
0x1800758a3  mov     r8b, bl
0x1800758a6  mov     edx, 10h
0x1800758ab  mov     ecx, eax
0x1800758ad  call    SystemSettings__DataModel___anonymous_namespace___GetFlagsFromBool
0x1800758b2  mov     [rsp+68h+arg_4], eax
0x1800758b6  mov     r9d, 3; fWinIni
0x1800758bc  lea     r8, [rsp+68h+arg_0]; pvParam
0x1800758c1  lea     edi, [r9+5]
0x1800758c5  mov     edx, edi; uiParam
0x1800758c7  lea     ecx, [rdi+33h]; uiAction
0x1800758ca  call    cs:__imp_SystemParametersInfoW
0x1800758d1  nop     dword ptr [rax+rax+00h]
0x1800758d6  mov     rcx, [rsp+68h]; this
0x1800758db  test    eax, eax
0x1800758dd  jnz     short loc_1800758EE
0x1800758df  lea     r8, aShellSystemset_105; "shell\\systemsettingsthreshold\\handler"...
0x1800758e6  lea     edx, [rdi+56h]; void *
0x1800758e9  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800758ee  call    SystemSettings__DataModel___anonymous_namespace___GetKeyState_tagTOGGLEKEYS_52_
0x1800758f3  mov     [rsp+68h+arg_0], eax
0x1800758f7  shr     rax, 20h
0x1800758fb  mov     r8b, bl
0x1800758fe  mov     edx, 10h
0x180075903  mov     ecx, eax
0x180075905  call    SystemSettings__DataModel___anonymous_namespace___GetFlagsFromBool
0x18007590a  mov     [rsp+68h+arg_4], eax
0x18007590e  mov     r9d, 3; fWinIni
0x180075914  lea     r8, [rsp+68h+arg_0]; pvParam
0x180075919  mov     edx, edi; uiParam
0x18007591b  lea     ecx, [r9+32h]; uiAction
0x18007591f  call    cs:__imp_SystemParametersInfoW
0x180075926  nop     dword ptr [rax+rax+00h]
0x18007592b  mov     rcx, [rsp+68h]; this
0x180075930  test    eax, eax
0x180075932  jnz     short loc_180075943
0x180075934  lea     r8, aShellSystemset_105; "shell\\systemsettingsthreshold\\handler"...
0x18007593b  lea     edx, [rax+5Eh]; void *
0x18007593e  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180075943  mov     dl, bl; bool
0x180075945  mov     rcx, rsi; this
0x180075948  call    ?DoSetValue@CInBoxATRegBoolSetting@DataModel@SystemSettings@@MEAAJ_N@Z; SystemSettings::DataModel::CInBoxATRegBoolSetting::DoSetValue(bool)
0x18007594d  xor     eax, eax
0x18007594f  jmp     short loc_180075955
0x180075951  mov     eax, [rsp+68h+arg_0]
0x180075955  lea     r11, [rsp+68h+var_8]
0x18007595a  mov     rbx, [r11+18h]
0x18007595e  mov     rsi, [r11+20h]
0x180075962  mov     rsp, r11
0x180075965  pop     rdi
0x180075966  retn
```
