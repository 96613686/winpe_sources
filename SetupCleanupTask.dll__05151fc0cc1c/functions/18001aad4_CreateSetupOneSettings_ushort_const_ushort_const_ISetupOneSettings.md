# CreateSetupOneSettings(ushort const *,ushort const *,ISetupOneSettings * *)

- ea: `0x18001aad4`
- end: `0x18001abf5`
- name: `?CreateSetupOneSettings@@YAJPEBG0PEAPEAUISetupOneSettings@@@Z`
- size: `289`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, struct ISetupOneSettings **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x18000ae40`

## callees

- `0x180001784`
- `0x18000638c`
- `0x18001941c`
- `0x18001aad4`
- `0x18001cc9c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001abbe`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001abcf`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001abbe`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001abcf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ab33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ab33`
- `WDSCORE!CurrentIP` at `0x18001ab3b`
- `WDSCORE!CurrentIP` at `0x18001ab3b`
- `WDSCORE!WdsSetupLogMessageW` at `0x18001aba1`
- `WDSCORE!WdsSetupLogMessageW` at `0x18001aba1`

## string_xrefs

- `0x18001ab60`: `CreateSetupOneSettings`

## pseudocode

```c
__int64 __fastcall CreateSetupOneSettings(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        struct ISetupOneSettings **a3)
{
  CSetupOneSetting *v4; // rax
  CSetupOneSetting *v5; // rsi
  int v6; // ebp
  DWORD LastError; // edi
  __int64 v8; // rbx
  struct tagLOG_PARTIAL_MSG *v9; // rax
  OneCore::Base::Telemetry::OneSettingsQuery *v10; // rbx

  if ( a3 )
  {
    v4 = (CSetupOneSetting *)operator new(0x10u);
    v5 = v4;
    if ( v4 )
    {
      *((_QWORD *)v4 + 1) = 0;
      *(_QWORD *)v4 = &CSetupOneSetting::`vftable';
      v6 = CSetupOneSetting::InitializeAndQuery(v4, L"WSD", L"SetupPlatform");
      if ( v6 >= 0 )
      {
        *a3 = v5;
      }
      else
      {
        LastError = GetLastError();
        v8 = CurrentIP();
        v9 = ConstructPartialMsgW(50331648, "Onesettings: Failed to initialize and query: 0x%x", v6);
        WdsSetupLogMessageW(
          v9,
          0,
          L"D",
          0,
          125,
          L"base\\ntsetup\\lib\\onesettings\\src\\onesettings.cpp",
          L"CreateSetupOneSettings",
          v8,
          LastError,
          0,
          0);
        v10 = (OneCore::Base::Telemetry::OneSettingsQuery *)*((_QWORD *)v5 + 1);
        *(_QWORD *)v5 = &CSetupOneSetting::`vftable';
        if ( v10 )
        {
          OneCore::Base::Telemetry::OneSettingsQuery::~OneSettingsQuery(v10);
          operator delete(v10);
          *((_QWORD *)v5 + 1) = 0;
        }
        operator delete(v5);
      }
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001aad4  push    rbx
0x18001aad6  push    rbp
0x18001aad7  push    rsi
0x18001aad8  push    rdi
0x18001aad9  push    r15
0x18001aadb  sub     rsp, 60h
0x18001aadf  mov     rbx, r8
0x18001aae2  test    r8, r8
0x18001aae5  jz      loc_18001ABE3
0x18001aaeb  mov     ecx, 10h; Size
0x18001aaf0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001aaf5  mov     rsi, rax
0x18001aaf8  test    rax, rax
0x18001aafb  jz      loc_18001ABDC
0x18001ab01  lea     r15, ??_7CSetupOneSetting@@6B@; const CSetupOneSetting::`vftable'
0x18001ab08  mov     qword ptr [rax+8], 0
0x18001ab10  lea     r8, aSetupplatform; "SetupPlatform"
0x18001ab17  mov     [rax], r15
0x18001ab1a  lea     rdx, aWsd; "WSD"
0x18001ab21  mov     rcx, rax; this
0x18001ab24  call    ?InitializeAndQuery@CSetupOneSetting@@QEAAJPEBG0@Z; CSetupOneSetting::InitializeAndQuery(ushort const *,ushort const *)
0x18001ab29  mov     ebp, eax
0x18001ab2b  test    eax, eax
0x18001ab2d  jns     loc_18001ABD7
0x18001ab33  call    cs:__imp_GetLastError
0x18001ab39  mov     edi, eax
0x18001ab3b  call    cs:__imp_CurrentIP
0x18001ab41  mov     r8d, ebp
0x18001ab44  lea     rdx, aOnesettingsFai_15; "Onesettings: Failed to initialize and q"...
0x18001ab4b  mov     ecx, 3000000h; unsigned int
0x18001ab50  mov     rbx, rax
0x18001ab53  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18001ab58  mov     [rsp+88h+var_38], 0
0x18001ab60  lea     rcx, aCreatesetupone; "CreateSetupOneSettings"
0x18001ab67  mov     [rsp+88h+var_40], 0
0x18001ab70  lea     r8, aD_0; "D"
0x18001ab77  mov     [rsp+88h+var_48], edi
0x18001ab7b  xor     r9d, r9d
0x18001ab7e  mov     [rsp+88h+var_50], rbx
0x18001ab83  xor     edx, edx
0x18001ab85  mov     [rsp+88h+var_58], rcx
0x18001ab8a  lea     rcx, aBaseNtsetupLib; "base\\ntsetup\\lib\\onesettings\\src\\o"...
0x18001ab91  mov     [rsp+88h+var_60], rcx
0x18001ab96  mov     rcx, rax
0x18001ab99  mov     [rsp+88h+var_68], 7Dh ; '}'
0x18001aba1  call    cs:__imp_WdsSetupLogMessageW
0x18001aba7  mov     rbx, [rsi+8]
0x18001abab  mov     [rsi], r15
0x18001abae  test    rbx, rbx
0x18001abb1  jz      short loc_18001ABCC
0x18001abb3  mov     rcx, rbx; this
0x18001abb6  call    ??1OneSettingsQuery@Telemetry@Base@OneCore@@QEAA@XZ; OneCore::Base::Telemetry::OneSettingsQuery::~OneSettingsQuery(void)
0x18001abbb  mov     rcx, rbx
0x18001abbe  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001abc4  mov     qword ptr [rsi+8], 0
0x18001abcc  mov     rcx, rsi
0x18001abcf  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001abd5  jmp     short loc_18001ABE8
0x18001abd7  mov     [rbx], rsi
0x18001abda  jmp     short loc_18001ABE8
0x18001abdc  mov     ebp, 8007000Eh
0x18001abe1  jmp     short loc_18001ABE8
0x18001abe3  mov     ebp, 80070057h
0x18001abe8  mov     eax, ebp
0x18001abea  add     rsp, 60h
0x18001abee  pop     r15
0x18001abf0  pop     rdi
0x18001abf1  pop     rsi
0x18001abf2  pop     rbp
0x18001abf3  pop     rbx
0x18001abf4  retn
```
