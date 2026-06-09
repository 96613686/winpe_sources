# CMapiSupport::GetRegKeyForCurrentUser(wchar_t const *,int,ATL::CRegKey *)

- ea: `0x180031bdc`
- end: `0x180031c46`
- name: `?GetRegKeyForCurrentUser@CMapiSupport@@SAJPEB_WHPEAVCRegKey@ATL@@@Z`
- size: `106`
- prototype: `static int(const wchar_t *, int, struct ATL::CRegKey *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180031f3c`

## callees

- `0x18000bfb0`
- `0x18000e6e0`
- `0x18000ee48`
- `0x180011884`
- `0x180031bdc`

## string_xrefs

- `0x180031bf9`: `Software\Microsoft\Windows Search\Gather\Windows\SystemIndex\Protocols\Mapi`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMapiSupport::GetRegKeyForCurrentUser(const wchar_t *a1, __int64 a2, struct ATL::CRegKey *a3)
{
  LPCWSTR v4; // rbx
  wchar_t *v5; // r9
  int v6; // eax
  unsigned int v7; // edi
  unsigned int v9; // [rsp+20h] [rbp-28h]
  LPCWSTR lpSubKey; // [rsp+50h] [rbp+8h] BYREF

  lpSubKey = a1;
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>((__int64)&lpSubKey);
  ATL::CSimpleStringT<wchar_t,0>::Append(
    &lpSubKey,
    L"Software\\Microsoft\\Windows Search\\Gather\\Windows\\SystemIndex\\Protocols\\Mapi");
  v4 = lpSubKey;
  v6 = ATL::CRegKey::Create(a3, HKEY_CURRENT_USER_LOCAL_SETTINGS, lpSubKey, v5, v9);
  v7 = v6;
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x80070000;
  ATL::CStringData::Release((ATL::CStringData *)(v4 - 12));
  return v7;
}

```

## disassembly

```asm
0x180031bdc  mov     [rsp+arg_8], rbx
0x180031be1  mov     [rsp+lpSubKey], rcx
0x180031be6  push    rdi
0x180031be7  sub     rsp, 40h
0x180031beb  mov     rdi, r8
0x180031bee  lea     rcx, [rsp+48h+lpSubKey]
0x180031bf3  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x180031bf8  nop
0x180031bf9  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows Search\\Ga"...
0x180031c00  lea     rcx, [rsp+48h+lpSubKey]
0x180031c05  call    ?Append@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_W@Z; ATL::CSimpleStringT<wchar_t,0>::Append(wchar_t const *)
0x180031c0a  mov     rbx, [rsp+48h+lpSubKey]
0x180031c0f  mov     r8, rbx; lpSubKey
0x180031c12  mov     rdx, 0FFFFFFFF80000007h; hKey
0x180031c19  mov     rcx, rdi; this
0x180031c1c  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WPEA_WKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,wchar_t const *,wchar_t *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x180031c21  mov     edi, eax
0x180031c23  test    eax, eax
0x180031c25  jle     short loc_180031C30
0x180031c27  movzx   edi, ax
0x180031c2a  or      edi, 80070000h
0x180031c30  lea     rcx, [rbx-18h]; this
0x180031c34  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180031c39  mov     eax, edi
0x180031c3b  mov     rbx, [rsp+48h+arg_8]
0x180031c40  add     rsp, 40h
0x180031c44  pop     rdi
0x180031c45  retn
```
