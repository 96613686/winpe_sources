# CreateSetupOneSettingsEx(ushort const *,ushort const *,int,ISetupOneSettings * *)

- ea: `0x180041400`
- end: `0x18004158b`
- name: `?CreateSetupOneSettingsEx@@YAJPEBG0HPEAPEAUISetupOneSettings@@@Z`
- size: `395`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, __int64, struct ISetupOneSettings **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x18001eca0`

## callees

- `0x180001914`
- `0x180009e04`
- `0x1800408a0`
- `0x180041400`
- `0x180042554`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180041556`
- `msvcrt!??3@YAXPEAX@Z` at `0x180041567`
- `msvcrt!??3@YAXPEAX@Z` at `0x180041556`
- `msvcrt!??3@YAXPEAX@Z` at `0x180041567`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004145e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004145e`
- `WDSCORE!CurrentIP` at `0x180041466`
- `WDSCORE!CurrentIP` at `0x180041466`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800414d1`
- `WDSCORE!WdsSetupLogMessageW` at `0x180041539`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800414d1`
- `WDSCORE!WdsSetupLogMessageW` at `0x180041539`

## string_xrefs

- `0x180041490`: `CreateSetupOneSettingsEx`
- `0x1800414f8`: `CreateSetupOneSettingsEx`
- `0x18004147c`: `Onesettings: Cache warning detected and ignored`

## pseudocode

```c
__int64 __fastcall CreateSetupOneSettingsEx(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        __int64 a3,
        struct ISetupOneSettings **a4)
{
  CSetupOneSetting *v5; // rax
  CSetupOneSetting *v6; // r14
  int v7; // esi
  DWORD LastError; // edi
  __int64 v9; // rbx
  struct tagLOG_PARTIAL_MSG *v10; // rax
  struct tagLOG_PARTIAL_MSG *v11; // rax
  OneCore::Base::Telemetry::OneSettingsQuery *v12; // rbx

  if ( !a4 )
    return (unsigned int)-2147024809;
  v5 = (CSetupOneSetting *)operator new(0x10u);
  v6 = v5;
  if ( !v5 )
    return (unsigned int)-2147024882;
  *((_QWORD *)v5 + 1) = 0;
  *(_QWORD *)v5 = &CSetupOneSetting::`vftable';
  v7 = CSetupOneSetting::InitializeAndQuery(v5, L"WSD", L"PushButtonReset");
  if ( v7 >= 0 )
    goto LABEL_6;
  LastError = GetLastError();
  v9 = CurrentIP();
  if ( v7 == -2147221136 )
  {
    v10 = ConstructPartialMsgW(50331648, "Onesettings: Cache warning detected and ignored");
    WdsSetupLogMessageW(
      v10,
      0,
      L"D",
      0,
      172,
      L"base\\ntsetup\\lib\\onesettings\\src\\onesettings.cpp",
      L"CreateSetupOneSettingsEx",
      v9,
      LastError,
      0,
      0);
    v7 = 0;
LABEL_6:
    *a4 = v6;
    return (unsigned int)v7;
  }
  v11 = ConstructPartialMsgW(50331648, "Onesettings: Failed to initialize and query: 0x%x", v7);
  WdsSetupLogMessageW(
    v11,
    0,
    L"D",
    0,
    177,
    L"base\\ntsetup\\lib\\onesettings\\src\\onesettings.cpp",
    L"CreateSetupOneSettingsEx",
    v9,
    LastError,
    0,
    0);
  v12 = (OneCore::Base::Telemetry::OneSettingsQuery *)*((_QWORD *)v6 + 1);
  *(_QWORD *)v6 = &CSetupOneSetting::`vftable';
  if ( v12 )
  {
    OneCore::Base::Telemetry::OneSettingsQuery::~OneSettingsQuery(v12);
    operator delete(v12);
    *((_QWORD *)v6 + 1) = 0;
  }
  operator delete(v6);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180041400  push    rbx
0x180041402  push    rsi
0x180041403  push    rdi
0x180041404  push    r12
0x180041406  push    r14
0x180041408  push    r15
0x18004140a  sub     rsp, 68h
0x18004140e  mov     r15, r9
0x180041411  test    r9, r9
0x180041414  jz      loc_180041576
0x18004141a  mov     ecx, 10h; Size
0x18004141f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180041424  mov     r14, rax
0x180041427  test    rax, rax
0x18004142a  jz      loc_18004156F
0x180041430  lea     r12, ??_7CSetupOneSetting@@6B@; const CSetupOneSetting::`vftable'
0x180041437  mov     qword ptr [rax+8], 0
0x18004143f  lea     r8, aPushbuttonrese; "PushButtonReset"
0x180041446  mov     [rax], r12
0x180041449  lea     rdx, aWsd; "WSD"
0x180041450  mov     rcx, rax; this
0x180041453  call    ?InitializeAndQuery@CSetupOneSetting@@QEAAJPEBG0@Z; CSetupOneSetting::InitializeAndQuery(ushort const *,ushort const *)
0x180041458  mov     esi, eax
0x18004145a  test    eax, eax
0x18004145c  jns     short loc_1800414D9
0x18004145e  call    cs:__imp_GetLastError
0x180041464  mov     edi, eax
0x180041466  call    cs:__imp_CurrentIP
0x18004146c  mov     ecx, 3000000h; unsigned int
0x180041471  mov     rbx, rax
0x180041474  cmp     esi, 80040170h
0x18004147a  jnz     short loc_1800414E1
0x18004147c  lea     rdx, aOnesettingsCac; "Onesettings: Cache warning detected and"...
0x180041483  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180041488  mov     [rsp+98h+var_48], 0
0x180041490  lea     rcx, aCreatesetupone; "CreateSetupOneSettingsEx"
0x180041497  mov     [rsp+98h+var_50], 0
0x1800414a0  lea     r8, aD; "D"
0x1800414a7  mov     [rsp+98h+var_58], edi
0x1800414ab  xor     r9d, r9d
0x1800414ae  mov     [rsp+98h+var_60], rbx
0x1800414b3  xor     edx, edx
0x1800414b5  mov     [rsp+98h+var_68], rcx
0x1800414ba  lea     rcx, aBaseNtsetupLib; "base\\ntsetup\\lib\\onesettings\\src\\o"...
0x1800414c1  mov     [rsp+98h+var_70], rcx
0x1800414c6  mov     rcx, rax
0x1800414c9  mov     [rsp+98h+var_78], 0ACh
0x1800414d1  call    cs:__imp_WdsSetupLogMessageW
0x1800414d7  xor     esi, esi
0x1800414d9  mov     [r15], r14
0x1800414dc  jmp     loc_18004157B
0x1800414e1  mov     r8d, esi
0x1800414e4  lea     rdx, aOnesettingsFai_15; "Onesettings: Failed to initialize and q"...
0x1800414eb  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800414f0  mov     [rsp+98h+var_48], 0
0x1800414f8  lea     rcx, aCreatesetupone; "CreateSetupOneSettingsEx"
0x1800414ff  mov     [rsp+98h+var_50], 0
0x180041508  lea     r8, aD; "D"
0x18004150f  mov     [rsp+98h+var_58], edi
0x180041513  xor     r9d, r9d
0x180041516  mov     [rsp+98h+var_60], rbx
0x18004151b  xor     edx, edx
0x18004151d  mov     [rsp+98h+var_68], rcx
0x180041522  lea     rcx, aBaseNtsetupLib; "base\\ntsetup\\lib\\onesettings\\src\\o"...
0x180041529  mov     [rsp+98h+var_70], rcx
0x18004152e  mov     rcx, rax
0x180041531  mov     [rsp+98h+var_78], 0B1h
0x180041539  call    cs:__imp_WdsSetupLogMessageW
0x18004153f  mov     rbx, [r14+8]
0x180041543  mov     [r14], r12
0x180041546  test    rbx, rbx
0x180041549  jz      short loc_180041564
0x18004154b  mov     rcx, rbx; this
0x18004154e  call    ??1OneSettingsQuery@Telemetry@Base@OneCore@@QEAA@XZ; OneCore::Base::Telemetry::OneSettingsQuery::~OneSettingsQuery(void)
0x180041553  mov     rcx, rbx
0x180041556  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18004155c  mov     qword ptr [r14+8], 0
0x180041564  mov     rcx, r14
0x180041567  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18004156d  jmp     short loc_18004157B
0x18004156f  mov     esi, 8007000Eh
0x180041574  jmp     short loc_18004157B
0x180041576  mov     esi, 80070057h
0x18004157b  mov     eax, esi
0x18004157d  add     rsp, 68h
0x180041581  pop     r15
0x180041583  pop     r14
0x180041585  pop     r12
0x180041587  pop     rdi
0x180041588  pop     rsi
0x180041589  pop     rbx
0x18004158a  retn
```
