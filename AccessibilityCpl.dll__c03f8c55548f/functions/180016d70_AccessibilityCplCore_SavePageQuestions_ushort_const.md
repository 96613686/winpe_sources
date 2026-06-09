# AccessibilityCplCore::SavePageQuestions(ushort const *)

- ea: `0x180016d70`
- end: `0x180016edd`
- name: `?SavePageQuestions@AccessibilityCplCore@@AEAAJPEBG@Z`
- size: `365`
- prototype: `int(AccessibilityCplCore *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800134a0`

## callees

- `0x1800055c0`
- `0x180014828`
- `0x180016d70`
- `0x180018260`
- `0x180018294`
- `0x18001a6c0`
- `0x18002d220`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016dd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016e96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016dd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016e96`
- `DUI70!StrToID` at `0x180016e4b`
- `DUI70!StrToID` at `0x180016e4b`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180016e57`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180016e57`

## string_xrefs

- `0x180016dc5`: `Software\Microsoft\Ease of Access`

## pseudocode

```c
__int64 __fastcall AccessibilityCplCore::SavePageQuestions(AccessibilityCplCore *this, const unsigned __int16 *a2)
{
  signed int LastError; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdi
  DirectUI::Element *v7; // rbx
  unsigned __int16 v8; // ax
  struct DirectUI::Element *Descendent; // rax
  AccessibilityCplCore *v10; // rcx
  signed int v11; // eax
  __int64 v13; // [rsp+20h] [rbp-60h] BYREF
  unsigned int v14[2]; // [rsp+28h] [rbp-58h]
  __int64 v15; // [rsp+30h] [rbp-50h]
  __int64 v16; // [rsp+38h] [rbp-48h]
  HKEY v17[3]; // [rsp+40h] [rbp-40h] BYREF
  unsigned __int16 v18[12]; // [rsp+58h] [rbp-28h] BYREF

  memset(v17, 0, sizeof(v17));
  if ( (unsigned int)ATL::CRegKey::Open(
                       (ATL::CRegKey *)v17,
                       HKEY_CURRENT_USER,
                       L"Software\\Microsoft\\Ease of Access",
                       0x2001Fu) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    LODWORD(v13) = 0;
    v6 = 0;
    v14[0] = 1;
    v14[1] = 2;
    v15 = 0x800000004LL;
    v16 = 0x2000000010LL;
    while ( (unsigned int)v6 < 6 )
    {
      StringCchPrintfW(v18, 0xAu, L"q%d", (unsigned int)v6, v13, *(_QWORD *)v14, v15, v16);
      v7 = (DirectUI::Element *)*((_QWORD *)this + 12);
      v8 = StrToID(v18);
      Descendent = DirectUI::Element::FindDescendent(v7, v8);
      if ( !Descendent )
      {
        if ( !(_DWORD)v6 )
        {
          v5 = -2147467259;
          goto LABEL_15;
        }
        break;
      }
      AccessibilityCplCore::SetFlagBasedOnSelection(v10, Descendent, (unsigned int *)&v13, v14[v6]);
      v6 = (unsigned int)(v6 + 1);
    }
    if ( ATL::CRegKey::SetDWORDValue(v17, a2, v13) )
    {
      v11 = GetLastError();
      if ( v11 > 0 )
        v11 = (unsigned __int16)v11 | 0x80070000;
      v5 = v11;
    }
    else
    {
      v5 = 0;
    }
  }
LABEL_15:
  ATL::CRegKey::Close((ATL::CRegKey *)v17);
  return v5;
}

```

## disassembly

```asm
0x180016d70  mov     [rsp-18h+arg_10], rbx
0x180016d75  mov     [rsp-18h+arg_18], rsi
0x180016d7a  push    rbp
0x180016d7b  push    rdi
0x180016d7c  push    r14
0x180016d7e  mov     rbp, rsp
0x180016d81  sub     rsp, 80h
0x180016d88  mov     rax, cs:__security_cookie
0x180016d8f  xor     rax, rsp
0x180016d92  mov     [rbp+var_10], rax
0x180016d96  mov     rsi, rdx
0x180016d99  mov     [rbp+var_40], 0
0x180016da1  mov     r14, rcx
0x180016da4  mov     [rbp+var_38], 0
0x180016dac  mov     rdx, 0FFFFFFFF80000001h; hKey
0x180016db3  mov     [rbp+var_30], 0
0x180016dbb  lea     rcx, [rbp+var_40]; this
0x180016dbf  mov     r9d, 2001Fh; unsigned int
0x180016dc5  lea     r8, aSoftwareMicros_0; "Software\\Microsoft\\Ease of Access"
0x180016dcc  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180016dd1  test    eax, eax
0x180016dd3  jz      short loc_180016DF3
0x180016dd5  call    cs:__imp_GetLastError
0x180016ddb  mov     ebx, eax
0x180016ddd  test    eax, eax
0x180016ddf  jle     loc_180016EAE
0x180016de5  movzx   ebx, ax
0x180016de8  or      ebx, 80070000h
0x180016dee  jmp     loc_180016EAE
0x180016df3  mov     dword ptr [rbp+var_60], 0
0x180016dfa  xor     edi, edi
0x180016dfc  mov     [rbp+var_58], 1
0x180016e03  mov     [rbp+var_54], 2
0x180016e0a  mov     [rbp+var_50], 4
0x180016e11  mov     [rbp+var_4C], 8
0x180016e18  mov     [rbp+var_48], 10h
0x180016e1f  mov     [rbp+var_44], 20h ; ' '
0x180016e26  cmp     edi, 6
0x180016e29  jnb     short loc_180016E82
0x180016e2b  mov     r9d, edi
0x180016e2e  lea     r8, aQD; "q%d"
0x180016e35  mov     edx, 0Ah; unsigned __int64
0x180016e3a  lea     rcx, [rbp+var_28]; unsigned __int16 *
0x180016e3e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180016e43  mov     rbx, [r14+60h]
0x180016e47  lea     rcx, [rbp+var_28]
0x180016e4b  call    cs:__imp_StrToID
0x180016e51  movzx   edx, ax
0x180016e54  mov     rcx, rbx
0x180016e57  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180016e5d  test    rax, rax
0x180016e60  jz      short loc_180016E77
0x180016e62  mov     r9d, [rbp+rdi*4+var_58]; unsigned int
0x180016e67  lea     r8, [rbp+var_60]; unsigned int *
0x180016e6b  mov     rdx, rax; struct DirectUI::Element *
0x180016e6e  call    ?SetFlagBasedOnSelection@AccessibilityCplCore@@AEAAXPEAVElement@DirectUI@@PEAKK@Z; AccessibilityCplCore::SetFlagBasedOnSelection(DirectUI::Element *,ulong *,ulong)
0x180016e73  inc     edi
0x180016e75  jmp     short loc_180016E26
0x180016e77  test    edi, edi
0x180016e79  jnz     short loc_180016E82
0x180016e7b  mov     ebx, 80004005h
0x180016e80  jmp     short loc_180016EAE
0x180016e82  mov     r8d, dword ptr [rbp+var_60]; unsigned int
0x180016e86  lea     rcx, [rbp+var_40]; this
0x180016e8a  mov     rdx, rsi; unsigned __int16 *
0x180016e8d  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x180016e92  test    eax, eax
0x180016e94  jz      short loc_180016EAC
0x180016e96  call    cs:__imp_GetLastError
0x180016e9c  test    eax, eax
0x180016e9e  jle     short loc_180016EA8
0x180016ea0  movzx   eax, ax
0x180016ea3  or      eax, 80070000h
0x180016ea8  mov     ebx, eax
0x180016eaa  jmp     short loc_180016EAE
0x180016eac  xor     ebx, ebx
0x180016eae  lea     rcx, [rbp+var_40]; this
0x180016eb2  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180016eb7  mov     eax, ebx
0x180016eb9  mov     rcx, [rbp+var_10]
0x180016ebd  xor     rcx, rsp; StackCookie
0x180016ec0  call    __security_check_cookie
0x180016ec5  lea     r11, [rsp+80h+var_s0]
0x180016ecd  mov     rbx, [r11+30h]
0x180016ed1  mov     rsi, [r11+38h]
0x180016ed5  mov     rsp, r11
0x180016ed8  pop     r14
0x180016eda  pop     rdi
0x180016edb  pop     rbp
0x180016edc  retn
```
