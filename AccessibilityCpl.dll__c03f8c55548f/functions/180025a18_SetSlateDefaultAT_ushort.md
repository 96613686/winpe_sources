# SetSlateDefaultAT(ushort *)

- ea: `0x180025a18`
- end: `0x180025beb`
- name: `?SetSlateDefaultAT@@YAJPEAG@Z`
- size: `467`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800177d0`

## callees

- `0x1800055c0`
- `0x1800057d4`
- `0x1800071c4`
- `0x180018260`
- `0x18002415c`
- `0x180024fd4`
- `0x180025068`
- `0x180025344`
- `0x180025a18`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025bb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025bb2`

## string_xrefs

- `0x180025a71`: `Control Panel\Accessibility\SlateLaunch\`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SetSlateDefaultAT(char *a1, __int64 a2, __int64 a3, unsigned __int16 *a4)
{
  LSTATUS v6; // edi
  int *v7; // rcx
  __int64 Next; // rax
  __int64 v9; // rsi
  const wchar_t *v10; // rax
  int v11; // r8d
  int v12; // edx
  char *v13; // rax
  int v14; // r8d
  int v15; // edx
  unsigned int v16; // ebx
  signed int LastError; // eax
  HKEY v18; // [rsp+30h] [rbp-D0h]
  HKEY v19[4]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v20[352]; // [rsp+60h] [rbp-A0h] BYREF
  int *v21; // [rsp+1E0h] [rbp+E0h] BYREF

  if ( a1 && !*(_WORD *)a1 )
    return 2147942487LL;
  memset(v19, 0, 24);
  if ( (unsigned int)ATL::CRegKey::Create(
                       (ATL::CRegKey *)v19,
                       HKEY_CURRENT_USER,
                       L"Control Panel\\Accessibility\\SlateLaunch\\",
                       a4,
                       0,
                       0x20006u,
                       v18,
                       0) )
    goto LABEL_25;
  if ( a1 )
  {
    v6 = 0;
    ATManager::ATManager((ATManager *)v20, 0);
    v7 = *(int **)ATManager::GetAccommodations((__int64)v20);
    v21 = v7;
    while ( v21 )
    {
      Next = ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::GetNext(
               v7,
               &v21);
      v9 = *(_QWORD *)Next;
      v7 = *(int **)(*(_QWORD *)Next + 40LL);
      if ( *(v7 - 4) > 0 )
      {
        v10 = L"SystemSetting";
        v7 = (int *)((char *)v7 - (unsigned __int64)L"SystemSetting");
        do
        {
          v11 = *(unsigned __int16 *)((char *)v7 + (_QWORD)v10);
          v12 = *v10 - v11;
          if ( v12 )
            break;
          ++v10;
        }
        while ( v11 );
        if ( v12 )
        {
          v13 = *(char **)(v9 + 8);
          v7 = (int *)(a1 - v13);
          do
          {
            v14 = *(unsigned __int16 *)((char *)v7 + (_QWORD)v13);
            v15 = *(unsigned __int16 *)v13 - v14;
            if ( v15 )
              break;
            v13 += 2;
          }
          while ( v14 );
          if ( !v15 )
          {
            v6 = ATL::CRegKey::SetDWORDValue(v19, L"LaunchAT", 1);
            if ( !v6 )
              v6 = ATL::CRegKey::SetStringValue(v19, L"ATapp", *(const BYTE **)v9);
            break;
          }
        }
      }
      if ( !v6 )
        v6 = 2;
    }
    ATManager::~ATManager((ATManager *)v20);
  }
  else
  {
    if ( ATL::CRegKey::SetDWORDValue(v19, L"LaunchAT", 0) )
      goto LABEL_25;
    v6 = ATL::CRegKey::SetStringValue(v19, L"ATapp", (const BYTE *)&Data);
  }
  v16 = 0;
  if ( v6 )
  {
LABEL_25:
    LastError = GetLastError();
    v16 = LastError;
    if ( LastError > 0 )
      v16 = (unsigned __int16)LastError | 0x80070000;
  }
  ATL::CRegKey::Close((ATL::CRegKey *)v19);
  return v16;
}

```

## disassembly

```asm
0x180025a18  mov     [rsp-8+arg_8], rbx
0x180025a1d  mov     [rsp-8+arg_10], rsi
0x180025a22  push    rbp
0x180025a23  push    rdi
0x180025a24  push    r14
0x180025a26  lea     rbp, [rsp-0C0h]
0x180025a2e  sub     rsp, 1C0h
0x180025a35  mov     rbx, rcx
0x180025a38  xor     r14d, r14d
0x180025a3b  test    rcx, rcx
0x180025a3e  jz      short loc_180025A50
0x180025a40  cmp     [rcx], r14w
0x180025a44  jnz     short loc_180025A50
0x180025a46  mov     eax, 80070057h
0x180025a4b  jmp     loc_180025BD3
0x180025a50  mov     [rsp+1D0h+var_190], r14
0x180025a55  mov     [rsp+1D0h+var_188], r14
0x180025a5a  mov     [rsp+1D0h+var_180], r14
0x180025a5f  mov     [rsp+1D0h+var_198], r14; unsigned int *
0x180025a64  mov     [rsp+1D0h+var_1A8], 20006h; REGSAM
0x180025a6c  mov     [rsp+1D0h+var_1B0], r14d; DWORD
0x180025a71  lea     r8, aControlPanelAc_0; "Control Panel\\Accessibility\\SlateLaun"...
0x180025a78  mov     rdx, 0FFFFFFFF80000001h; hKey
0x180025a7f  lea     rcx, [rsp+1D0h+var_190]; this
0x180025a84  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x180025a89  test    eax, eax
0x180025a8b  jnz     loc_180025BB2
0x180025a91  test    rbx, rbx
0x180025a94  jnz     short loc_180025AD1
0x180025a96  xor     r8d, r8d; unsigned int
0x180025a99  lea     rdx, aLaunchat; "LaunchAT"
0x180025aa0  lea     rcx, [rsp+1D0h+var_190]; this
0x180025aa5  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x180025aaa  test    eax, eax
0x180025aac  jnz     loc_180025BB2
0x180025ab2  lea     r8, Data; unsigned __int16 *
0x180025ab9  lea     rdx, aAtapp; "ATapp"
0x180025ac0  lea     rcx, [rsp+1D0h+var_190]; this
0x180025ac5  call    ?SetStringValue@CRegKey@ATL@@QEAAJPEBG0K@Z; ATL::CRegKey::SetStringValue(ushort const *,ushort const *,ulong)
0x180025aca  mov     edi, eax
0x180025acc  jmp     loc_180025BAB
0x180025ad1  mov     edi, r14d
0x180025ad4  xor     edx, edx; int
0x180025ad6  lea     rcx, [rsp+1D0h+var_170]; this
0x180025adb  call    ??0ATManager@@QEAA@H@Z; ATManager::ATManager(int)
0x180025ae0  nop
0x180025ae1  lea     rcx, [rsp+1D0h+var_170]
0x180025ae6  call    ?GetAccommodations@ATManager@@QEAAAEBV?$CAtlList@PEAVAccommodation@@V?$CElementTraits@PEAVAccommodation@@@ATL@@@ATL@@XZ; ATManager::GetAccommodations(void)
0x180025aeb  mov     rcx, [rax]
0x180025aee  mov     [rbp+0D0h+arg_0], rcx
0x180025af5  cmp     [rbp+0D0h+arg_0], r14
0x180025afc  jz      loc_180025BA1
0x180025b02  lea     rdx, [rbp+0D0h+arg_0]
0x180025b09  call    ?GetNext@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEBAAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@AEAPEAU__POSITION@@@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::GetNext(__POSITION * &)
0x180025b0e  mov     rsi, [rax]
0x180025b11  mov     rcx, [rsi+28h]
0x180025b15  cmp     [rcx-10h], r14d
0x180025b19  jle     short loc_180025B63
0x180025b1b  lea     rax, aSystemsetting_0; "SystemSetting"
0x180025b22  sub     rcx, rax
0x180025b25  movzx   edx, word ptr [rax]
0x180025b28  movzx   r8d, word ptr [rax+rcx]
0x180025b2d  sub     edx, r8d
0x180025b30  jnz     short loc_180025B3B
0x180025b32  add     rax, 2
0x180025b36  test    r8d, r8d
0x180025b39  jnz     short loc_180025B25
0x180025b3b  test    edx, edx
0x180025b3d  jz      short loc_180025B63
0x180025b3f  mov     rax, [rsi+8]
0x180025b43  mov     rcx, rbx
0x180025b46  sub     rcx, rax
0x180025b49  movzx   edx, word ptr [rax]
0x180025b4c  movzx   r8d, word ptr [rax+rcx]
0x180025b51  sub     edx, r8d
0x180025b54  jnz     short loc_180025B5F
0x180025b56  add     rax, 2
0x180025b5a  test    r8d, r8d
0x180025b5d  jnz     short loc_180025B49
0x180025b5f  test    edx, edx
0x180025b61  jz      short loc_180025B6E
0x180025b63  test    edi, edi
0x180025b65  jnz     short loc_180025AF5
0x180025b67  mov     edi, 2
0x180025b6c  jmp     short loc_180025AF5
0x180025b6e  mov     r8d, 1; unsigned int
0x180025b74  lea     rdx, aLaunchat; "LaunchAT"
0x180025b7b  lea     rcx, [rsp+1D0h+var_190]; this
0x180025b80  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x180025b85  mov     edi, eax
0x180025b87  test    eax, eax
0x180025b89  jnz     short loc_180025BA1
0x180025b8b  mov     r8, [rsi]; unsigned __int16 *
0x180025b8e  lea     rdx, aAtapp; "ATapp"
0x180025b95  lea     rcx, [rsp+1D0h+var_190]; this
0x180025b9a  call    ?SetStringValue@CRegKey@ATL@@QEAAJPEBG0K@Z; ATL::CRegKey::SetStringValue(ushort const *,ushort const *,ulong)
0x180025b9f  mov     edi, eax
0x180025ba1  lea     rcx, [rsp+1D0h+var_170]; this
0x180025ba6  call    ??1ATManager@@QEAA@XZ; ATManager::~ATManager(void)
0x180025bab  mov     ebx, r14d
0x180025bae  test    edi, edi
0x180025bb0  jz      short loc_180025BC7
0x180025bb2  call    cs:__imp_GetLastError
0x180025bb8  test    eax, eax
0x180025bba  mov     ebx, eax
0x180025bbc  jle     short loc_180025BC7
0x180025bbe  movzx   ebx, ax
0x180025bc1  or      ebx, 80070000h
0x180025bc7  lea     rcx, [rsp+1D0h+var_190]; this
0x180025bcc  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180025bd1  mov     eax, ebx
0x180025bd3  lea     r11, [rsp+1D0h+var_10]
0x180025bdb  mov     rbx, [r11+28h]
0x180025bdf  mov     rsi, [r11+30h]
0x180025be3  mov     rsp, r11
0x180025be6  pop     r14
0x180025be8  pop     rdi
0x180025be9  pop     rbp
0x180025bea  retn
```
