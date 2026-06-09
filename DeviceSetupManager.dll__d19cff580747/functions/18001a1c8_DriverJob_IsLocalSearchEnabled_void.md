# DriverJob::_IsLocalSearchEnabled(void)

- ea: `0x18001a1c8`
- end: `0x18001a439`
- name: `?_IsLocalSearchEnabled@DriverJob@@AEAA_NXZ`
- size: `625`
- prototype: `bool __fastcall(DriverJob *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003493c`

## callees

- `0x18001a1c8`
- `0x18001a440`
- `0x18001a518`
- `0x18001af70`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001a25a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001a25a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001a228`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001a228`

## string_xrefs

- `0x18001a1f9`: `DevicePath`
- `0x18001a333`: `DevicePath`
- `0x18001a39c`: `DevicePath`

## pseudocode

```c
char __fastcall DriverJob::_IsLocalSearchEnabled(DriverJob *this)
{
  LSTATUS ValueW; // r9d
  _QWORD *v3; // rcx
  _QWORD *v4; // rax
  int v5; // edx
  WCHAR *v6; // r9
  _QWORD *v7; // rcx
  _QWORD *v8; // rax
  int v9; // edx
  _QWORD *v11; // rax
  int pdwType; // [rsp+20h] [rbp-268h]
  DWORD pcbData[4]; // [rsp+50h] [rbp-238h] BYREF
  WCHAR String1[264]; // [rsp+60h] [rbp-228h] BYREF

  pcbData[0] = 520;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows\\CurrentVersion",
             L"DevicePath",
             0x10000004u,
             0,
             String1,
             pcbData);
  if ( !ValueW )
  {
    if ( String1[0] && CompareStringOrdinal(String1, -1, L"%SystemRoot%\\inf", -1, 1) != 2 )
    {
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        return 1;
      }
      v4 = (_QWORD *)((char *)this + 40);
      if ( *((_QWORD *)this + 8) > 7u )
        v4 = (_QWORD *)*v4;
      v5 = 22;
      v6 = String1;
      goto LABEL_32;
    }
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      return 0;
    }
    v8 = (_QWORD *)((char *)this + 40);
    if ( *((_QWORD *)this + 8) > 7u )
      v8 = (_QWORD *)*v8;
    v9 = 21;
LABEL_23:
    WPP_SF_S_guid_LS(
      v7[2],
      v9,
      (_DWORD)this + 8,
      (unsigned int)L"DevicePath",
      (__int64)this + 8,
      *((_DWORD *)this + 7),
      (__int64)v8);
    return 0;
  }
  if ( ValueW == 2 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      return 0;
    }
    v8 = (_QWORD *)((char *)this + 40);
    if ( *((_QWORD *)this + 8) > 7u )
      v8 = (_QWORD *)*v8;
    v9 = 23;
    goto LABEL_23;
  }
  if ( ValueW != 234 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      v11 = (_QWORD *)((char *)this + 40);
      if ( *((_QWORD *)this + 8) > 7u )
        v11 = (_QWORD *)*v11;
      WPP_SF_SSD_guid_LS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        *((_DWORD *)this + 7),
        (_DWORD)this + 8,
        ValueW,
        pdwType,
        ValueW,
        (__int64)this + 8,
        *((_DWORD *)this + 7),
        (__int64)v11);
    }
    return 1;
  }
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v4 = (_QWORD *)((char *)this + 40);
    if ( *((_QWORD *)this + 8) > 7u )
      v4 = (_QWORD *)*v4;
    v5 = 24;
    v6 = (WCHAR *)L"DevicePath";
LABEL_32:
    WPP_SF_S_guid_LS(v3[2], v5, (_DWORD)this + 8, (_DWORD)v6, (__int64)this + 8, *((_DWORD *)this + 7), (__int64)v4);
  }
  return 1;
}

```

## disassembly

```asm
0x18001a1c8  mov     [rsp+arg_8], rbx
0x18001a1cd  push    rdi
0x18001a1ce  sub     rsp, 280h
0x18001a1d5  mov     rax, cs:__security_cookie
0x18001a1dc  xor     rax, rsp
0x18001a1df  mov     [rsp+288h+var_18], rax
0x18001a1e7  lea     rax, [rsp+288h+var_238]
0x18001a1ec  mov     [rsp+288h+var_238], 208h
0x18001a1f4  mov     [rsp+288h+pcbData], rax; pcbData
0x18001a1f9  lea     r8, aDevicepath; "DevicePath"
0x18001a200  lea     rax, [rsp+288h+String1]
0x18001a205  mov     rbx, rcx
0x18001a208  mov     [rsp+288h+pvData], rax; pvData
0x18001a20d  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18001a214  xor     edi, edi
0x18001a216  mov     r9d, 10000004h; dwFlags
0x18001a21c  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001a223  mov     [rsp+288h+pdwType], rdi; pdwType
0x18001a228  call    cs:__imp_RegGetValueW
0x18001a22e  mov     r9d, eax
0x18001a231  test    eax, eax
0x18001a233  jnz     loc_18001A2EB
0x18001a239  cmp     [rsp+288h+String1], di
0x18001a23e  jz      short loc_18001A2B0
0x18001a240  or      edx, 0FFFFFFFFh; cchCount1
0x18001a243  mov     dword ptr [rsp+288h+pdwType], 1; bIgnoreCase
0x18001a24b  mov     r9d, edx; cchCount2
0x18001a24e  lea     r8, aSystemrootInf; "%SystemRoot%\\inf"
0x18001a255  lea     rcx, [rsp+288h+String1]; lpString1
0x18001a25a  call    cs:__imp_CompareStringOrdinal
0x18001a260  cmp     eax, 2
0x18001a263  jz      short loc_18001A2B0
0x18001a265  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a26c  lea     rax, WPP_GLOBAL_Control
0x18001a273  cmp     rcx, rax
0x18001a276  jz      loc_18001A416
0x18001a27c  test    dword ptr [rcx+1Ch], 200h
0x18001a283  jz      loc_18001A416
0x18001a289  cmp     byte ptr [rcx+19h], 4
0x18001a28d  jb      loc_18001A416
0x18001a293  lea     rax, [rbx+28h]
0x18001a297  cmp     qword ptr [rax+18h], 7
0x18001a29c  jbe     short loc_18001A2A1
0x18001a29e  mov     rax, [rax]
0x18001a2a1  mov     edx, 16h
0x18001a2a6  lea     r9, [rsp+288h+String1]
0x18001a2ab  jmp     loc_18001A3A3
0x18001a2b0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a2b7  lea     rax, WPP_GLOBAL_Control
0x18001a2be  cmp     rcx, rax
0x18001a2c1  jz      loc_18001A34B
0x18001a2c7  test    dword ptr [rcx+1Ch], 200h
0x18001a2ce  jz      short loc_18001A34B
0x18001a2d0  cmp     byte ptr [rcx+19h], 4
0x18001a2d4  jb      short loc_18001A34B
0x18001a2d6  lea     rax, [rbx+28h]
0x18001a2da  cmp     qword ptr [rax+18h], 7
0x18001a2df  jbe     short loc_18001A2E4
0x18001a2e1  mov     rax, [rax]
0x18001a2e4  mov     edx, 15h
0x18001a2e9  jmp     short loc_18001A326
0x18001a2eb  cmp     r9d, 2
0x18001a2ef  jnz     short loc_18001A352
0x18001a2f1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a2f8  lea     rax, WPP_GLOBAL_Control
0x18001a2ff  cmp     rcx, rax
0x18001a302  jz      short loc_18001A34B
0x18001a304  test    dword ptr [rcx+1Ch], 200h
0x18001a30b  jz      short loc_18001A34B
0x18001a30d  cmp     byte ptr [rcx+19h], 4
0x18001a311  jb      short loc_18001A34B
0x18001a313  lea     rax, [rbx+28h]
0x18001a317  cmp     qword ptr [rax+18h], 7
0x18001a31c  jbe     short loc_18001A321
0x18001a31e  mov     rax, [rax]
0x18001a321  mov     edx, 17h
0x18001a326  mov     rcx, [rcx+10h]
0x18001a32a  lea     r8, [rbx+8]
0x18001a32e  mov     [rsp+288h+pcbData], rax
0x18001a333  lea     r9, aDevicepath; "DevicePath"
0x18001a33a  mov     eax, [rbx+1Ch]
0x18001a33d  mov     dword ptr [rsp+288h+pvData], eax
0x18001a341  mov     [rsp+288h+pdwType], r8
0x18001a346  call    WPP_SF_S_guid_LS
0x18001a34b  xor     al, al
0x18001a34d  jmp     loc_18001A418
0x18001a352  cmp     r9d, 0EAh
0x18001a359  jnz     short loc_18001A3C3
0x18001a35b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a362  lea     rax, WPP_GLOBAL_Control
0x18001a369  cmp     rcx, rax
0x18001a36c  jz      loc_18001A416
0x18001a372  test    dword ptr [rcx+1Ch], 200h
0x18001a379  jz      loc_18001A416
0x18001a37f  cmp     byte ptr [rcx+19h], 4
0x18001a383  jb      loc_18001A416
0x18001a389  lea     rax, [rbx+28h]
0x18001a38d  cmp     qword ptr [rax+18h], 7
0x18001a392  jbe     short loc_18001A397
0x18001a394  mov     rax, [rax]
0x18001a397  mov     edx, 18h
0x18001a39c  lea     r9, aDevicepath; "DevicePath"
0x18001a3a3  mov     rcx, [rcx+10h]
0x18001a3a7  lea     r8, [rbx+8]
0x18001a3ab  mov     [rsp+288h+pcbData], rax
0x18001a3b0  mov     eax, [rbx+1Ch]
0x18001a3b3  mov     dword ptr [rsp+288h+pvData], eax
0x18001a3b7  mov     [rsp+288h+pdwType], r8
0x18001a3bc  call    WPP_SF_S_guid_LS
0x18001a3c1  jmp     short loc_18001A416
0x18001a3c3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a3ca  lea     rax, WPP_GLOBAL_Control
0x18001a3d1  cmp     rcx, rax
0x18001a3d4  jz      short loc_18001A416
0x18001a3d6  test    dword ptr [rcx+1Ch], 200h
0x18001a3dd  jz      short loc_18001A416
0x18001a3df  cmp     byte ptr [rcx+19h], 3
0x18001a3e3  jb      short loc_18001A416
0x18001a3e5  lea     rax, [rbx+28h]
0x18001a3e9  cmp     qword ptr [rax+18h], 7
0x18001a3ee  jbe     short loc_18001A3F3
0x18001a3f0  mov     rax, [rax]
0x18001a3f3  mov     edx, [rbx+1Ch]
0x18001a3f6  lea     r8, [rbx+8]
0x18001a3fa  mov     rcx, [rcx+10h]
0x18001a3fe  mov     [rsp+288h+var_248], rax
0x18001a403  mov     [rsp+288h+var_250], edx
0x18001a407  mov     [rsp+288h+pcbData], r8
0x18001a40c  mov     dword ptr [rsp+288h+pvData], r9d
0x18001a411  call    WPP_SF_SSD_guid_LS
0x18001a416  mov     al, 1
0x18001a418  mov     rcx, [rsp+288h+var_18]
0x18001a420  xor     rcx, rsp; StackCookie
0x18001a423  call    __security_check_cookie
0x18001a428  mov     rbx, [rsp+288h+arg_8]
0x18001a430  add     rsp, 280h
0x18001a437  pop     rdi
0x18001a438  retn
```
