# SettingsCopier::CopyATSettings(ATL::CRegKey &,ATL::CRegKey &)

- ea: `0x1800288dc`
- end: `0x180028b5d`
- name: `?CopyATSettings@SettingsCopier@@AEAAJAEAVCRegKey@ATL@@0@Z`
- size: `641`
- prototype: `int(SettingsCopier *__hidden this, struct ATL::CRegKey *, struct ATL::CRegKey *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180029144`

## callees

- `0x1800055c0`
- `0x1800071c4`
- `0x180015c40`
- `0x18001bc60`
- `0x180025344`
- `0x1800288dc`
- `0x180028b64`
- `0x180028e60`
- `0x180029200`
- `0x180029434`
- `0x1800295f4`
- `0x18002d220`

## import_xrefs

- `msvcrt!free` at `0x180028a7f`
- `msvcrt!free` at `0x180028b12`
- `msvcrt!free` at `0x180028a7f`
- `msvcrt!free` at `0x180028b12`

## string_xrefs

- `0x180028928`: `enduser\ezap\easeofaccess\atmanager\settingscopier.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SettingsCopier::CopyATSettings(SettingsCopier *this, HKEY *a2, HKEY *a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v9; // rcx
  __int64 Next; // rax
  LPCWSTR *v11; // rsi
  DWORD v12; // edi
  signed int RegKeyValue; // eax
  unsigned int v14; // ebx
  BYTE *v15; // rcx
  BYTE *v16; // rbx
  LSTATUS v17; // eax
  BYTE *v18; // rcx
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // r9
  DWORD lpData; // [rsp+20h] [rbp-E0h]
  DWORD dwType[2]; // [rsp+40h] [rbp-C0h] BYREF
  BYTE *v24; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v25; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v26[3]; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v27[4]; // [rsp+70h] [rbp-90h] BYREF
  wchar_t String1[264]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+1E8h]

  v6 = SettingsCopier::DeleteATSettings(a3);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1FC,
      (unsigned int)"enduser\\ezap\\easeofaccess\\atmanager\\settingscopier.cpp",
      (const char *)(unsigned int)v6,
      lpData);
    return v7;
  }
  v9 = *(_QWORD *)ATManager::GetAccommodations(*(_QWORD *)this);
  v25 = v9;
  if ( !v9 )
    return 0;
  do
  {
    Next = ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::GetNext(
             v9,
             &v25);
    v11 = *(LPCWSTR **)Next;
    if ( !*(_DWORD *)(*(_QWORD *)Next + 68LL) )
      continue;
    memset(v27, 0, 24);
    memset(v26, 0, sizeof(v26));
    v12 = 0;
    while ( 1 )
    {
      dwType[1] = 0;
      dwType[0] = 0;
      v24 = 0;
      RegKeyValue = SettingsCopier::GetRegKeyValue(*a2, *v11, v12, String1, lpData, &dwType[1], (void **)&v24, dwType);
      v14 = RegKeyValue;
      if ( RegKeyValue == 1 )
      {
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          goto LABEL_29;
        v20 = 10;
        v21 = 1;
        goto LABEL_28;
      }
      if ( RegKeyValue < 0 )
      {
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
          goto LABEL_29;
        v20 = 11;
        v21 = (unsigned int)RegKeyValue;
LABEL_28:
        WPP_SF_d(v19[2], v20, WPP_fe5ab529b727364d0549539a0e90a98d_Traceguids, v21);
LABEL_29:
        v18 = v24;
        goto LABEL_30;
      }
      if ( !(unsigned int)CATUtils::IsInteractiveUser() && (unsigned __int8)IsBlockedCopyValue(String1) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_fe5ab529b727364d0549539a0e90a98d_Traceguids, v14);
        v15 = v24;
        goto LABEL_16;
      }
      v16 = v24;
      v17 = SettingsCopier::SetRegKeyValue(*a3, *v11, String1, dwType[1], v24, dwType[0]);
      if ( v17 < 0 )
        break;
      v15 = v16;
LABEL_16:
      free(v15);
      if ( ++v12 > 0x64 )
        goto LABEL_31;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        WPP_fe5ab529b727364d0549539a0e90a98d_Traceguids,
        (unsigned int)v17);
    v18 = v16;
LABEL_30:
    free(v18);
LABEL_31:
    ATL::CRegKey::Close((ATL::CRegKey *)v26);
    ATL::CRegKey::Close((ATL::CRegKey *)v27);
  }
  while ( v25 );
  return 0;
}

```

## disassembly

```asm
0x1800288dc  push    rbp
0x1800288de  push    rbx
0x1800288df  push    rsi
0x1800288e0  push    rdi
0x1800288e1  push    r13
0x1800288e3  push    r14
0x1800288e5  push    r15
0x1800288e7  lea     rbp, [rsp-1B0h]
0x1800288ef  sub     rsp, 2B0h
0x1800288f6  mov     rax, cs:__security_cookie
0x1800288fd  xor     rax, rsp
0x180028900  mov     [rbp+1E0h+var_40], rax
0x180028907  mov     r14, r8
0x18002890a  mov     r15, rdx
0x18002890d  mov     rdi, rcx
0x180028910  mov     rcx, r8; struct ATL::CRegKey *
0x180028913  call    ?DeleteATSettings@SettingsCopier@@CAJAEAVCRegKey@ATL@@@Z; SettingsCopier::DeleteATSettings(ATL::CRegKey &)
0x180028918  mov     ebx, eax
0x18002891a  test    eax, eax
0x18002891c  jns     short loc_180028940
0x18002891e  mov     rcx, [rbp+1E8h]; this
0x180028925  mov     r9d, eax; char *
0x180028928  lea     r8, aEnduserEzapEas; "enduser\\ezap\\easeofaccess\\atmanager"...
0x18002892f  mov     edx, 1FCh; void *
0x180028934  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028939  mov     eax, ebx
0x18002893b  jmp     loc_180028B3C
0x180028940  mov     rcx, [rdi]
0x180028943  call    ?GetAccommodations@ATManager@@QEAAAEBV?$CAtlList@PEAVAccommodation@@V?$CElementTraits@PEAVAccommodation@@@ATL@@@ATL@@XZ; ATManager::GetAccommodations(void)
0x180028948  mov     rcx, [rax]
0x18002894b  mov     [rsp+2E0h+var_290], rcx
0x180028950  test    rcx, rcx
0x180028953  jz      loc_180028B3A
0x180028959  lea     r13, WPP_GLOBAL_Control
0x180028960  lea     rdx, [rsp+2E0h+var_290]
0x180028965  call    ?GetNext@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEBAAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@AEAPEAU__POSITION@@@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::GetNext(__POSITION * &)
0x18002896a  mov     rsi, [rax]
0x18002896d  cmp     dword ptr [rsi+44h], 0
0x180028971  jz      loc_180028B2E
0x180028977  mov     [rsp+2E0h+var_270], 0
0x180028980  mov     [rsp+2E0h+var_268], 0
0x180028989  mov     [rbp+1E0h+var_260], 0
0x180028991  mov     [rsp+2E0h+var_288], 0
0x18002899a  mov     [rsp+2E0h+var_280], 0
0x1800289a3  mov     [rsp+2E0h+var_278], 0
0x1800289ac  xor     edi, edi
0x1800289ae  mov     [rsp+2E0h+dwType+4], 0
0x1800289b6  mov     [rsp+2E0h+dwType], 0
0x1800289be  mov     [rsp+2E0h+var_298], 0
0x1800289c7  lea     rax, [rsp+2E0h+dwType]
0x1800289cc  mov     [rsp+2E0h+var_2A8], rax; __int64
0x1800289d1  lea     rax, [rsp+2E0h+var_298]
0x1800289d6  mov     [rsp+2E0h+var_2B0], rax; __int64
0x1800289db  lea     rax, [rsp+2E0h+dwType+4]
0x1800289e0  mov     qword ptr [rsp+2E0h+var_2B8], rax; __int64
0x1800289e5  lea     r9, [rbp+1E0h+String1]
0x1800289e9  mov     r8d, edi
0x1800289ec  mov     rdx, [rsi]; lpSubKey
0x1800289ef  mov     rcx, [r15]; hKey
0x1800289f2  call    ?GetRegKeyValue@SettingsCopier@@CAJPEAUHKEY__@@PEBGKPEAGKPEAKAEAV?$CHeapPtr@EVCCRTAllocator@ATL@@@ATL@@3@Z; SettingsCopier::GetRegKeyValue(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong *,ATL::CHeapPtr<uchar,ATL::CCRTAllocator> &,ulong *)
0x1800289f7  mov     ebx, eax
0x1800289f9  cmp     eax, 1
0x1800289fc  jz      loc_180028AE1
0x180028a02  test    eax, eax
0x180028a04  js      loc_180028AC5
0x180028a0a  call    ?IsInteractiveUser@CATUtils@@SAHXZ; CATUtils::IsInteractiveUser(void)
0x180028a0f  test    eax, eax
0x180028a11  jnz     short loc_180028A52
0x180028a13  lea     rcx, [rbp+1E0h+String1]; String1
0x180028a17  call    IsBlockedCopyValue
0x180028a1c  test    al, al
0x180028a1e  jz      short loc_180028A52
0x180028a20  mov     rcx, cs:WPP_GLOBAL_Control
0x180028a27  cmp     rcx, r13
0x180028a2a  jz      short loc_180028A4B
0x180028a2c  test    byte ptr [rcx+1Ch], 10h
0x180028a30  jz      short loc_180028A4B
0x180028a32  mov     edx, 0Ch
0x180028a37  mov     r9d, ebx
0x180028a3a  lea     r8, WPP_fe5ab529b727364d0549539a0e90a98d_Traceguids
0x180028a41  mov     rcx, [rcx+10h]
0x180028a45  call    WPP_SF_d
0x180028a4a  nop
0x180028a4b  mov     rcx, [rsp+2E0h+var_298]
0x180028a50  jmp     short loc_180028A7F
0x180028a52  mov     eax, [rsp+2E0h+dwType]
0x180028a56  mov     [rsp+2E0h+var_2B8], eax; DWORD
0x180028a5a  mov     rbx, [rsp+2E0h+var_298]
0x180028a5f  mov     [rsp+2E0h+lpData], rbx; lpData
0x180028a64  mov     r9d, [rsp+2E0h+dwType+4]; dwType
0x180028a69  lea     r8, [rbp+1E0h+String1]; lpValueName
0x180028a6d  mov     rdx, [rsi]; lpSubKey
0x180028a70  mov     rcx, [r14]; hKey
0x180028a73  call    ?SetRegKeyValue@SettingsCopier@@CAJPEAUHKEY__@@PEBG1KPEBEK@Z; SettingsCopier::SetRegKeyValue(HKEY__ *,ushort const *,ushort const *,ulong,uchar const *,ulong)
0x180028a78  test    eax, eax
0x180028a7a  js      short loc_180028A95
0x180028a7c  mov     rcx, rbx; Block
0x180028a7f  call    cs:__imp_free
0x180028a85  inc     edi
0x180028a87  cmp     edi, 64h ; 'd'
0x180028a8a  jbe     loc_1800289AE
0x180028a90  jmp     loc_180028B19
0x180028a95  mov     rcx, cs:WPP_GLOBAL_Control
0x180028a9c  cmp     rcx, r13
0x180028a9f  jz      short loc_180028AC0
0x180028aa1  test    byte ptr [rcx+1Ch], 8
0x180028aa5  jz      short loc_180028AC0
0x180028aa7  mov     edx, 0Dh
0x180028aac  mov     r9d, eax
0x180028aaf  lea     r8, WPP_fe5ab529b727364d0549539a0e90a98d_Traceguids
0x180028ab6  mov     rcx, [rcx+10h]
0x180028aba  call    WPP_SF_d
0x180028abf  nop
0x180028ac0  mov     rcx, rbx
0x180028ac3  jmp     short loc_180028B12
0x180028ac5  mov     rcx, cs:WPP_GLOBAL_Control
0x180028acc  cmp     rcx, r13
0x180028acf  jz      short loc_180028B0D
0x180028ad1  test    byte ptr [rcx+1Ch], 8
0x180028ad5  jz      short loc_180028B0D
0x180028ad7  mov     edx, 0Bh
0x180028adc  mov     r9d, ebx
0x180028adf  jmp     short loc_180028AFC
0x180028ae1  mov     rcx, cs:WPP_GLOBAL_Control
0x180028ae8  cmp     rcx, r13
0x180028aeb  jz      short loc_180028B0D
0x180028aed  test    byte ptr [rcx+1Ch], 10h
0x180028af1  jz      short loc_180028B0D
0x180028af3  mov     edx, 0Ah
0x180028af8  lea     r9d, [rdx-9]
0x180028afc  lea     r8, WPP_fe5ab529b727364d0549539a0e90a98d_Traceguids
0x180028b03  mov     rcx, [rcx+10h]
0x180028b07  call    WPP_SF_d
0x180028b0c  nop
0x180028b0d  mov     rcx, [rsp+2E0h+var_298]; Block
0x180028b12  call    cs:__imp_free
0x180028b18  nop
0x180028b19  lea     rcx, [rsp+2E0h+var_288]; this
0x180028b1e  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180028b23  nop
0x180028b24  lea     rcx, [rsp+2E0h+var_270]; this
0x180028b29  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180028b2e  cmp     [rsp+2E0h+var_290], 0
0x180028b34  jnz     loc_180028960
0x180028b3a  xor     eax, eax
0x180028b3c  mov     rcx, [rbp+1E0h+var_40]
0x180028b43  xor     rcx, rsp; StackCookie
0x180028b46  call    __security_check_cookie
0x180028b4b  add     rsp, 2B0h
0x180028b52  pop     r15
0x180028b54  pop     r14
0x180028b56  pop     r13
0x180028b58  pop     rdi
0x180028b59  pop     rsi
0x180028b5a  pop     rbx
0x180028b5b  pop     rbp
0x180028b5c  retn
```
