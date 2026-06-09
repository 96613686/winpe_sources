# StartList::HandleFirstTime(ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CRegKey &)

- ea: `0x1800229ec`
- end: `0x180022e56`
- name: `?HandleFirstTime@StartList@@AEAAJAEBV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@3@AEAVCRegKey@3@@Z`
- size: `1130`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180023090`

## callees

- `0x180004310`
- `0x1800043d4`
- `0x180005340`
- `0x18000539c`
- `0x180005534`
- `0x1800055c0`
- `0x1800057d4`
- `0x1800071c4`
- `0x180014828`
- `0x180014b84`
- `0x180015780`
- `0x1800157dc`
- `0x18001855c`
- `0x18001bc60`
- `0x180020edc`
- `0x1800218bc`
- `0x1800229ec`
- `0x18002415c`
- `0x180024a44`
- `0x18002d1ee`
- `0x18002d220`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x180022d02`
- `KERNEL32!GetFileAttributesW` at `0x180022d5c`
- `KERNEL32!GetFileAttributesW` at `0x180022dac`
- `KERNEL32!GetFileAttributesW` at `0x180022d02`
- `KERNEL32!GetFileAttributesW` at `0x180022d5c`
- `KERNEL32!GetFileAttributesW` at `0x180022dac`
- `KERNEL32!DeleteFileW` at `0x180022d2e`
- `KERNEL32!DeleteFileW` at `0x180022d7e`
- `KERNEL32!DeleteFileW` at `0x180022dcf`
- `KERNEL32!DeleteFileW` at `0x180022d2e`
- `KERNEL32!DeleteFileW` at `0x180022d7e`
- `KERNEL32!DeleteFileW` at `0x180022dcf`

## string_xrefs

- `0x180022b1d`: `Configuration`
- `0x180022a3a`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall StartList::HandleFirstTime(__int64 a1, LPCWSTR *a2, _QWORD *a3, ATL::CRegKey *a4)
{
  unsigned int v7; // eax
  __int64 v8; // rcx
  int v9; // ebx
  const unsigned __int16 **Next; // rbx
  unsigned __int16 *v12; // rbx
  unsigned int v13; // r9d
  unsigned int v14; // eax
  signed int v15; // edi
  unsigned int v16; // eax
  ATL::CStringData *v17; // r12
  int *v18; // rdi
  __int64 v19; // rbx
  const WCHAR *v20; // rsi
  const WCHAR *v21; // rdi
  const WCHAR *v22; // rbx
  HKEY v23; // [rsp+30h] [rbp-D0h]
  LPCWSTR lpFileName; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v25; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR v26; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR v27; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v28[3]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v29; // [rsp+78h] [rbp-88h] BYREF
  __int64 v30; // [rsp+88h] [rbp-78h]
  __int128 v31; // [rsp+90h] [rbp-70h]
  int v32; // [rsp+A0h] [rbp-60h]
  unsigned __int16 v33[264]; // [rsp+B0h] [rbp-50h] BYREF

  v7 = ATL::CRegKey::Create(
         a4,
         HKEY_CURRENT_USER,
         StartList::_accessibilityKeyString,
         (unsigned __int16 *)a4,
         0,
         3u,
         v23,
         (unsigned int *)&lpFileName);
  v9 = v7;
  if ( !v7 )
  {
    v29 = 0;
    v30 = 0;
    v31 = 0;
    v32 = 10;
    lpFileName = *a2;
    while ( lpFileName )
    {
      Next = (const unsigned __int16 **)ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::GetNext(
                                          v8,
                                          &lpFileName);
      if ( *((_DWORD *)Accommodation::Open(*Next) + 20) != 1 )
        ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::AddTail(
          &v29,
          *Next);
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v25);
    StartList::BuildConfigString(&v25, &v29);
    v12 = v25;
    v14 = ATL::CRegKey::SetStringValue(a4, StartList::_configuration, v25, v13);
    v15 = v14;
    if ( v14 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids, v14);
      if ( v15 > 0 )
        v15 = (unsigned __int16)v15 | 0x80070000;
    }
    else
    {
      memset(v28, 0, sizeof(v28));
      v16 = ATL::CRegKey::Open(
              (ATL::CRegKey *)v28,
              HKEY_CURRENT_USER,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Shell Folders",
              0x20019u);
      v15 = v16;
      if ( !v16 )
      {
        memset_0(v33, 0, 0x208u);
        LODWORD(lpFileName) = 260;
        ATL::CRegKey::QueryStringValue((ATL::CRegKey *)v28, L"Startup", v33, (unsigned int *)&lpFileName);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          &lpFileName,
          v33);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          &v26,
          v33);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          &v27,
          v33);
        ATL::CSimpleStringT<unsigned short,0>::Append(&lpFileName, L"\\On-Screen Keyboard.lnk", 23);
        ATL::CSimpleStringT<unsigned short,0>::Append(&v26, L"\\Narrator.lnk", 13);
        ATL::CSimpleStringT<unsigned short,0>::Append(&v27, L"\\Magnifier.lnk", 14);
        v17 = (ATL::CStringData *)(v12 - 12);
        v18 = (int *)(*a3 - 24LL);
        if ( v12 - 12 != (unsigned __int16 *)v18 )
        {
          if ( v18[4] >= 0 && *(_QWORD *)v17 == *(_QWORD *)v18 )
          {
            v19 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v12 - 12);
            ATL::CStringData::Release((ATL::CStringData *)v18);
            *a3 = v19 + 24;
          }
          else
          {
            ATL::CSimpleStringT<unsigned short,0>::SetString(a3, v12, *((unsigned int *)v12 - 4));
          }
        }
        v20 = lpFileName;
        if ( GetFileAttributesW(lpFileName) != -1 )
        {
          ATL::CSimpleStringT<unsigned short,0>::Append(a3, L",osk", 4);
          DeleteFileW(v20);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44);
        }
        v21 = v26;
        if ( GetFileAttributesW(v26) != -1 )
        {
          ATL::CSimpleStringT<unsigned short,0>::Append(a3, L",Narrator", 9);
          DeleteFileW(v21);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45);
        }
        v22 = v27;
        if ( GetFileAttributesW(v27) != -1 )
        {
          ATL::CSimpleStringT<unsigned short,0>::Append(a3, L",magnifierpane", 14);
          DeleteFileW(v22);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46);
        }
        ATL::CStringData::Release((ATL::CStringData *)(v22 - 12));
        ATL::CStringData::Release((ATL::CStringData *)(v21 - 12));
        ATL::CStringData::Release((ATL::CStringData *)(v20 - 12));
        ATL::CRegKey::Close((ATL::CRegKey *)v28);
        ATL::CStringData::Release(v17);
        v15 = 0;
        goto LABEL_44;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids, v16);
      if ( v15 > 0 )
        v15 = (unsigned __int16)v15 | 0x80070000;
      ATL::CRegKey::Close((ATL::CRegKey *)v28);
    }
    ATL::CStringData::Release((ATL::CStringData *)(v12 - 12));
LABEL_44:
    ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::RemoveAll(&v29);
    return (unsigned int)v15;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids, v7);
  if ( v9 > 0 )
    return (unsigned __int16)v9 | 0x80070000;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800229ec  push    rbp
0x1800229ee  push    rbx
0x1800229ef  push    rsi
0x1800229f0  push    rdi
0x1800229f1  push    r12
0x1800229f3  push    r14
0x1800229f5  push    r15
0x1800229f7  lea     rbp, [rsp-1D0h]
0x1800229ff  sub     rsp, 2D0h
0x180022a06  mov     rax, cs:__security_cookie
0x180022a0d  xor     rax, rsp
0x180022a10  mov     [rbp+200h+var_40], rax
0x180022a17  mov     rdi, r9
0x180022a1a  mov     r15, r8
0x180022a1d  mov     rsi, rdx
0x180022a20  lea     rax, [rsp+300h+lpFileName]
0x180022a25  mov     [rsp+300h+var_2C8], rax; unsigned int *
0x180022a2a  mov     [rsp+300h+var_2D8], 3; REGSAM
0x180022a32  mov     [rsp+300h+var_2E0], 0; DWORD
0x180022a3a  lea     r8, ?_accessibilityKeyString@StartList@@0PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180022a41  mov     r14, 0FFFFFFFF80000001h
0x180022a48  mov     rdx, r14; hKey
0x180022a4b  mov     rcx, r9; this
0x180022a4e  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x180022a53  mov     ebx, eax
0x180022a55  test    eax, eax
0x180022a57  jz      short loc_180022A9E
0x180022a59  lea     r14, WPP_GLOBAL_Control
0x180022a60  mov     rcx, cs:WPP_GLOBAL_Control
0x180022a67  cmp     rcx, r14
0x180022a6a  jz      short loc_180022A8A
0x180022a6c  test    byte ptr [rcx+1Ch], 8
0x180022a70  jz      short loc_180022A8A
0x180022a72  mov     edx, 29h ; ')'
0x180022a77  mov     r9d, eax
0x180022a7a  lea     r8, WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids
0x180022a81  mov     rcx, [rcx+10h]
0x180022a85  call    WPP_SF_d
0x180022a8a  test    ebx, ebx
0x180022a8c  jle     short loc_180022A97
0x180022a8e  movzx   ebx, bx
0x180022a91  or      ebx, 80070000h
0x180022a97  mov     eax, ebx
0x180022a99  jmp     loc_180022E35
0x180022a9e  xorps   xmm0, xmm0
0x180022aa1  movdqu  [rsp+300h+var_288], xmm0
0x180022aa7  mov     [rbp+200h+var_278], 0
0x180022aaf  xorps   xmm1, xmm1
0x180022ab2  movdqu  [rbp+200h+var_270], xmm1
0x180022ab7  mov     [rbp+200h+var_260], 0Ah
0x180022abe  mov     rax, [rsi]
0x180022ac1  mov     [rsp+300h+lpFileName], rax
0x180022ac6  test    rax, rax
0x180022ac9  jz      short loc_180022AFB
0x180022acb  lea     rdx, [rsp+300h+lpFileName]
0x180022ad0  call    ?GetNext@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEBAAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@AEAPEAU__POSITION@@@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::GetNext(__POSITION * &)
0x180022ad5  mov     rbx, rax
0x180022ad8  mov     rcx, [rax]; unsigned __int16 *
0x180022adb  call    ?Open@Accommodation@@SAPEAV1@PEBG@Z; Accommodation::Open(ushort const *)
0x180022ae0  cmp     dword ptr [rax+50h], 1
0x180022ae4  jz      short loc_180022AF3
0x180022ae6  mov     rdx, [rbx]
0x180022ae9  lea     rcx, [rsp+300h+var_288]
0x180022aee  call    ?AddTail@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAPEAU__POSITION@@PEBG@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::AddTail(ushort const *)
0x180022af3  cmp     [rsp+300h+lpFileName], 0
0x180022af9  jnz     short loc_180022ACB
0x180022afb  lea     rcx, [rsp+300h+var_2B8]
0x180022b00  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180022b05  nop
0x180022b06  lea     rdx, [rsp+300h+var_288]
0x180022b0b  lea     rcx, [rsp+300h+var_2B8]
0x180022b10  call    ?BuildConfigString@StartList@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@3@@Z; StartList::BuildConfigString(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &)
0x180022b15  mov     rbx, [rsp+300h+var_2B8]
0x180022b1a  mov     r8, rbx; unsigned __int16 *
0x180022b1d  lea     rdx, ?_configuration@StartList@@0PAGA; "Configuration"
0x180022b24  mov     rcx, rdi; this
0x180022b27  call    ?SetStringValue@CRegKey@ATL@@QEAAJPEBG0K@Z; ATL::CRegKey::SetStringValue(ushort const *,ushort const *,ulong)
0x180022b2c  mov     edi, eax
0x180022b2e  test    eax, eax
0x180022b30  jz      short loc_180022B79
0x180022b32  lea     r14, WPP_GLOBAL_Control
0x180022b39  mov     rcx, cs:WPP_GLOBAL_Control
0x180022b40  cmp     rcx, r14
0x180022b43  jz      short loc_180022B63
0x180022b45  test    byte ptr [rcx+1Ch], 8
0x180022b49  jz      short loc_180022B63
0x180022b4b  mov     edx, 2Ah ; '*'
0x180022b50  mov     r9d, eax
0x180022b53  lea     r8, WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids
0x180022b5a  mov     rcx, [rcx+10h]
0x180022b5e  call    WPP_SF_d
0x180022b63  test    edi, edi
0x180022b65  jle     loc_180022BFD
0x180022b6b  movzx   edi, di
0x180022b6e  or      edi, 80070000h
0x180022b74  jmp     loc_180022BFD
0x180022b79  mov     [rsp+300h+var_2A0], 0
0x180022b82  mov     [rsp+300h+var_298], 0
0x180022b8b  mov     [rsp+300h+var_290], 0
0x180022b94  mov     r9d, 20019h; unsigned int
0x180022b9a  lea     r8, aSoftwareMicros_6; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180022ba1  mov     rdx, r14; hKey
0x180022ba4  lea     rcx, [rsp+300h+var_2A0]; this
0x180022ba9  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180022bae  mov     edi, eax
0x180022bb0  test    eax, eax
0x180022bb2  jz      short loc_180022C0B
0x180022bb4  lea     r14, WPP_GLOBAL_Control
0x180022bbb  mov     rcx, cs:WPP_GLOBAL_Control
0x180022bc2  cmp     rcx, r14
0x180022bc5  jz      short loc_180022BE5
0x180022bc7  test    byte ptr [rcx+1Ch], 8
0x180022bcb  jz      short loc_180022BE5
0x180022bcd  mov     edx, 2Bh ; '+'
0x180022bd2  mov     r9d, eax
0x180022bd5  lea     r8, WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids
0x180022bdc  mov     rcx, [rcx+10h]
0x180022be0  call    WPP_SF_d
0x180022be5  test    edi, edi
0x180022be7  jle     short loc_180022BF2
0x180022be9  movzx   edi, di
0x180022bec  or      edi, 80070000h
0x180022bf2  lea     rcx, [rsp+300h+var_2A0]; this
0x180022bf7  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180022bfc  nop
0x180022bfd  lea     rcx, [rbx-18h]; this
0x180022c01  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180022c06  jmp     loc_180022E29
0x180022c0b  xor     edx, edx; Val
0x180022c0d  mov     r8d, 208h; Size
0x180022c13  lea     rcx, [rbp+200h+var_250]; void *
0x180022c17  call    memset_0
0x180022c1c  mov     dword ptr [rsp+300h+lpFileName], 104h
0x180022c24  lea     r9, [rsp+300h+lpFileName]; unsigned int *
0x180022c29  lea     r8, [rbp+200h+var_250]; unsigned __int16 *
0x180022c2d  lea     rdx, aStartup; "Startup"
0x180022c34  lea     rcx, [rsp+300h+var_2A0]; this
0x180022c39  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x180022c3e  lea     rdx, [rbp+200h+var_250]
0x180022c42  lea     rcx, [rsp+300h+lpFileName]
0x180022c47  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180022c4c  nop
0x180022c4d  lea     rdx, [rbp+200h+var_250]
0x180022c51  lea     rcx, [rsp+300h+var_2B0]
0x180022c56  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180022c5b  nop
0x180022c5c  lea     rdx, [rbp+200h+var_250]
0x180022c60  lea     rcx, [rsp+300h+var_2A8]
0x180022c65  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180022c6a  nop
0x180022c6b  mov     r8d, 17h
0x180022c71  lea     rdx, aOnScreenKeyboa; "\\On-Screen Keyboard.lnk"
0x180022c78  lea     rcx, [rsp+300h+lpFileName]
0x180022c7d  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x180022c82  mov     r8d, 0Dh
0x180022c88  lea     rdx, aNarratorLnk; "\\Narrator.lnk"
0x180022c8f  lea     rcx, [rsp+300h+var_2B0]
0x180022c94  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x180022c99  mov     r8d, 0Eh
0x180022c9f  lea     rdx, aMagnifierLnk; "\\Magnifier.lnk"
0x180022ca6  lea     rcx, [rsp+300h+var_2A8]
0x180022cab  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x180022cb0  lea     r12, [rbx-18h]
0x180022cb4  mov     rdi, [r15]
0x180022cb7  add     rdi, 0FFFFFFFFFFFFFFE8h
0x180022cbb  cmp     r12, rdi
0x180022cbe  jz      short loc_180022CFA
0x180022cc0  cmp     dword ptr [rdi+10h], 0
0x180022cc4  jl      short loc_180022CEB
0x180022cc6  mov     rax, [rdi]
0x180022cc9  cmp     [r12], rax
0x180022ccd  jnz     short loc_180022CEB
0x180022ccf  mov     rcx, r12
0x180022cd2  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180022cd7  mov     rbx, rax
0x180022cda  mov     rcx, rdi; this
0x180022cdd  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180022ce2  lea     rax, [rbx+18h]
0x180022ce6  mov     [r15], rax
0x180022ce9  jmp     short loc_180022CFA
0x180022ceb  mov     r8d, [rbx-10h]
0x180022cef  mov     rdx, rbx
0x180022cf2  mov     rcx, r15
0x180022cf5  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180022cfa  mov     rsi, [rsp+300h+lpFileName]
0x180022cff  mov     rcx, rsi; lpFileName
0x180022d02  call    cs:__imp_GetFileAttributesW
0x180022d08  lea     r14, WPP_GLOBAL_Control
0x180022d0f  or      ebx, 0FFFFFFFFh
0x180022d12  cmp     eax, ebx
0x180022d14  jz      short loc_180022D54
0x180022d16  mov     r8d, 4
0x180022d1c  lea     rdx, aOsk_0; ",osk"
0x180022d23  mov     rcx, r15
0x180022d26  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x180022d2b  mov     rcx, rsi; lpFileName
0x180022d2e  call    cs:__imp_DeleteFileW
0x180022d34  mov     rcx, cs:WPP_GLOBAL_Control
0x180022d3b  cmp     rcx, r14
0x180022d3e  jz      short loc_180022D54
0x180022d40  test    byte ptr [rcx+1Ch], 10h
0x180022d44  jz      short loc_180022D54
0x180022d46  mov     edx, 2Ch ; ','
0x180022d4b  mov     rcx, [rcx+10h]
0x180022d4f  call    WPP_SF_
0x180022d54  mov     rdi, [rsp+300h+var_2B0]
0x180022d59  mov     rcx, rdi; lpFileName
0x180022d5c  call    cs:__imp_GetFileAttributesW
0x180022d62  cmp     eax, ebx
0x180022d64  jz      short loc_180022DA4
0x180022d66  mov     r8d, 9
0x180022d6c  lea     rdx, aNarrator_1; ",Narrator"
0x180022d73  mov     rcx, r15
0x180022d76  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x180022d7b  mov     rcx, rdi; lpFileName
0x180022d7e  call    cs:__imp_DeleteFileW
0x180022d84  mov     rcx, cs:WPP_GLOBAL_Control
0x180022d8b  cmp     rcx, r14
0x180022d8e  jz      short loc_180022DA4
0x180022d90  test    byte ptr [rcx+1Ch], 10h
0x180022d94  jz      short loc_180022DA4
0x180022d96  mov     edx, 2Dh ; '-'
0x180022d9b  mov     rcx, [rcx+10h]
0x180022d9f  call    WPP_SF_
0x180022da4  mov     rbx, [rsp+300h+var_2A8]
0x180022da9  mov     rcx, rbx; lpFileName
0x180022dac  call    cs:__imp_GetFileAttributesW
0x180022db2  cmp     eax, 0FFFFFFFFh
0x180022db5  jz      short loc_180022DF6
0x180022db7  mov     r8d, 0Eh
0x180022dbd  lea     rdx, aMagnifierpane_0; ",magnifierpane"
0x180022dc4  mov     rcx, r15
0x180022dc7  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x180022dcc  mov     rcx, rbx; lpFileName
0x180022dcf  call    cs:__imp_DeleteFileW
0x180022dd5  mov     rcx, cs:WPP_GLOBAL_Control
0x180022ddc  cmp     rcx, r14
0x180022ddf  jz      short loc_180022DF6
0x180022de1  test    byte ptr [rcx+1Ch], 10h
0x180022de5  jz      short loc_180022DF6
0x180022de7  mov     edx, 2Eh ; '.'
0x180022dec  mov     rcx, [rcx+10h]
0x180022df0  call    WPP_SF_
0x180022df5  nop
0x180022df6  lea     rcx, [rbx-18h]; this
0x180022dfa  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180022dff  nop
0x180022e00  lea     rcx, [rdi-18h]; this
0x180022e04  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180022e09  nop
0x180022e0a  lea     rcx, [rsi-18h]; this
0x180022e0e  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180022e13  nop
0x180022e14  lea     rcx, [rsp+300h+var_2A0]; this
0x180022e19  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180022e1e  nop
0x180022e1f  mov     rcx, r12; this
0x180022e22  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180022e27  xor     edi, edi
0x180022e29  lea     rcx, [rsp+300h+var_288]
0x180022e2e  call    ?RemoveAll@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAXXZ; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::RemoveAll(void)
0x180022e33  mov     eax, edi
0x180022e35  mov     rcx, [rbp+200h+var_40]
0x180022e3c  xor     rcx, rsp; StackCookie
0x180022e3f  call    __security_check_cookie
0x180022e44  add     rsp, 2D0h
0x180022e4b  pop     r15
0x180022e4d  pop     r14
0x180022e4f  pop     r12
0x180022e51  pop     rdi
0x180022e52  pop     rsi
0x180022e53  pop     rbx
0x180022e54  pop     rbp
0x180022e55  retn
```
