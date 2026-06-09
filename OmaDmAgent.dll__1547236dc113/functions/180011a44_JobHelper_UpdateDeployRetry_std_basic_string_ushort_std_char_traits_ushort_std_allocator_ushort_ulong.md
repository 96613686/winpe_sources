# JobHelper::UpdateDeployRetry(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ulong)

- ea: `0x180011a44`
- end: `0x180011bf3`
- name: `?UpdateDeployRetry@JobHelper@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z`
- size: `431`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x18000d2cc`
- `0x18000dcb4`

## callees

- `0x180002a50`
- `0x1800062ac`
- `0x18000702c`
- `0x1800098b0`
- `0x18000a2c0`
- `0x18000a3c0`
- `0x18000bae8`
- `0x18000f924`
- `0x18000fdf8`
- `0x180011a44`
- `0x18001f420`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180011ae7`
- `KERNEL32!EnterCriticalSection` at `0x180011ae7`
- `KERNEL32!LeaveCriticalSection` at `0x180011ba3`
- `KERNEL32!LeaveCriticalSection` at `0x180011ba3`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall JobHelper::UpdateDeployRetry(__int64 a1, __int64 a2, int a3)
{
  LSTATUS Key; // eax
  unsigned int v7; // esi
  struct _RTL_CRITICAL_SECTION *v8; // rbx
  __int64 v9; // rax
  int JobRegPath; // eax
  LPCWSTR v11; // rcx
  const WCHAR *v12; // r9
  int v13; // edx
  const unsigned __int16 *v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // rdx
  HKEY v18; // [rsp+30h] [rbp-39h] BYREF
  HKEY phkResult[2]; // [rsp+38h] [rbp-31h] BYREF
  _BYTE v20[32]; // [rsp+48h] [rbp-21h] BYREF
  __int64 v21; // [rsp+68h] [rbp-1h]
  unsigned __int16 *v22[4]; // [rsp+70h] [rbp+7h] BYREF

  v21 = a2;
  std::wstring::wstring(v22, &dword_180022F6C);
  phkResult[0] = 0;
  v18 = 0;
  Key = CurrentUserRegKeyHelper::GetKey(phkResult, &v18);
  v7 = Key;
  if ( Key < 0 )
  {
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        121,
        &WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
        (unsigned int)Key);
    v8 = (struct _RTL_CRITICAL_SECTION *)(a1 + 128);
    goto LABEL_20;
  }
  v8 = (struct _RTL_CRITICAL_SECTION *)(a1 + 128);
  EnterCriticalSection(v8);
  v9 = std::wstring::wstring(v20, a2);
  JobRegPath = JobHelper::GetJobRegPath(v9, (__int64)v22);
  v7 = JobRegPath;
  if ( JobRegPath < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
      goto LABEL_20;
    if ( *(_QWORD *)(a2 + 24) < 8u )
      LODWORD(v12) = a2;
    else
      v12 = *(const WCHAR **)a2;
    v13 = 122;
LABEL_19:
    WPP_SF_Sd(
      *((_QWORD *)v11 + 2),
      v13,
      (unsigned int)&WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
      (_DWORD)v12,
      JobRegPath);
    goto LABEL_20;
  }
  v14 = (const unsigned __int16 *)v22;
  if ( v22[3] >= (unsigned __int16 *)8 )
    v14 = v22[0];
  JobRegPath = WriteRegDWORDValue(v18, v14, L"DeployRetryCount", a3);
  v7 = JobRegPath;
  if ( JobRegPath < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    {
      v13 = 123;
      v12 = L"DeployRetryCount";
      goto LABEL_19;
    }
  }
LABEL_20:
  LeaveCriticalSection(v8);
  CurrentUserRegKeyHelper::~CurrentUserRegKeyHelper((CurrentUserRegKeyHelper *)phkResult);
  LOBYTE(v15) = 1;
  std::wstring::_Tidy(v22, v15, 0);
  LOBYTE(v16) = 1;
  std::wstring::_Tidy(a2, v16, 0);
  return v7;
}

```

## disassembly

```asm
0x180011a44  push    rbp
0x180011a46  push    rbx
0x180011a47  push    rsi
0x180011a48  push    rdi
0x180011a49  push    r14
0x180011a4b  lea     rbp, [rsp-37h]
0x180011a50  sub     rsp, 0A0h
0x180011a57  mov     rax, cs:__security_cookie
0x180011a5e  xor     rax, rsp
0x180011a61  mov     [rbp+57h+var_30], rax
0x180011a65  mov     r14d, r8d
0x180011a68  mov     rdi, rdx
0x180011a6b  mov     rbx, rcx
0x180011a6e  mov     [rbp+57h+var_58], rdx
0x180011a72  lea     rdx, dword_180022F6C
0x180011a79  lea     rcx, [rbp+57h+var_50]
0x180011a7d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180011a82  nop
0x180011a83  mov     [rbp+57h+phkResult], 0
0x180011a8b  mov     [rbp+57h+var_90], 0
0x180011a93  lea     rdx, [rbp+57h+var_90]; HKEY *
0x180011a97  lea     rcx, [rbp+57h+phkResult]; phkResult
0x180011a9b  call    ?GetKey@CurrentUserRegKeyHelper@@QEAAJAEAPEAUHKEY__@@@Z; CurrentUserRegKeyHelper::GetKey(HKEY__ * &)
0x180011aa0  mov     esi, eax
0x180011aa2  test    eax, eax
0x180011aa4  jns     short loc_180011AE0
0x180011aa6  lea     rdx, WPP_GLOBAL_Control
0x180011aad  mov     rcx, cs:WPP_GLOBAL_Control
0x180011ab4  cmp     rcx, rdx
0x180011ab7  jz      short loc_180011AD7
0x180011ab9  test    byte ptr [rcx+1Ch], 4
0x180011abd  jz      short loc_180011AD7
0x180011abf  mov     edx, 79h ; 'y'
0x180011ac4  mov     r9d, eax
0x180011ac7  lea     r8, WPP_9f155fbe94773387205a22e9edb85311_Traceguids
0x180011ace  mov     rcx, [rcx+10h]
0x180011ad2  call    WPP_SF_d
0x180011ad7  sub     rbx, 0FFFFFFFFFFFFFF80h
0x180011adb  jmp     loc_180011BA0
0x180011ae0  sub     rbx, 0FFFFFFFFFFFFFF80h
0x180011ae4  mov     rcx, rbx; lpCriticalSection
0x180011ae7  call    cs:__imp_EnterCriticalSection
0x180011aee  nop     dword ptr [rax+rax+00h]
0x180011af3  mov     rdx, rdi
0x180011af6  lea     rcx, [rbp+57h+var_78]
0x180011afa  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180011aff  lea     rdx, [rbp+57h+var_50]
0x180011b03  mov     rcx, rax
0x180011b06  call    ?GetJobRegPath@JobHelper@@CAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z; JobHelper::GetJobRegPath(std::wstring,std::wstring &)
0x180011b0b  mov     esi, eax
0x180011b0d  test    eax, eax
0x180011b0f  jns     short loc_180011B40
0x180011b11  lea     rdx, WPP_GLOBAL_Control
0x180011b18  mov     rcx, cs:WPP_GLOBAL_Control
0x180011b1f  cmp     rcx, rdx
0x180011b22  jz      short loc_180011BA0
0x180011b24  test    byte ptr [rcx+1Ch], 4
0x180011b28  jz      short loc_180011BA0
0x180011b2a  cmp     qword ptr [rdi+18h], 8
0x180011b2f  jb      short loc_180011B36
0x180011b31  mov     r9, [rdi]
0x180011b34  jmp     short loc_180011B39
0x180011b36  mov     r9, rdi
0x180011b39  mov     edx, 7Ah ; 'z'
0x180011b3e  jmp     short loc_180011B8C
0x180011b40  lea     rdx, [rbp+57h+var_50]
0x180011b44  cmp     [rbp+57h+var_38], 8
0x180011b49  cmovnb  rdx, [rbp+57h+var_50]; unsigned __int16 *
0x180011b4e  mov     r9d, r14d; unsigned int
0x180011b51  lea     r8, aDeployretrycou; "DeployRetryCount"
0x180011b58  mov     rcx, [rbp+57h+var_90]; HKEY
0x180011b5c  call    ?WriteRegDWORDValue@@YAJPEAUHKEY__@@PEBG1KPEAU_SECURITY_ATTRIBUTES@@@Z; WriteRegDWORDValue(HKEY__ *,ushort const *,ushort const *,ulong,_SECURITY_ATTRIBUTES *)
0x180011b61  mov     esi, eax
0x180011b63  test    eax, eax
0x180011b65  jns     short loc_180011BA0
0x180011b67  lea     rdx, WPP_GLOBAL_Control
0x180011b6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180011b75  cmp     rcx, rdx
0x180011b78  jz      short loc_180011BA0
0x180011b7a  test    byte ptr [rcx+1Ch], 4
0x180011b7e  jz      short loc_180011BA0
0x180011b80  mov     edx, 7Bh ; '{'
0x180011b85  lea     r9, aDeployretrycou; "DeployRetryCount"
0x180011b8c  mov     [rsp+0C0h+var_A0], eax
0x180011b90  lea     r8, WPP_9f155fbe94773387205a22e9edb85311_Traceguids
0x180011b97  mov     rcx, [rcx+10h]
0x180011b9b  call    WPP_SF_Sd
0x180011ba0  mov     rcx, rbx; lpCriticalSection
0x180011ba3  call    cs:__imp_LeaveCriticalSection
0x180011baa  nop     dword ptr [rax+rax+00h]
0x180011baf  nop
0x180011bb0  lea     rcx, [rbp+57h+phkResult]; this
0x180011bb4  call    ??1CurrentUserRegKeyHelper@@QEAA@XZ; CurrentUserRegKeyHelper::~CurrentUserRegKeyHelper(void)
0x180011bb9  nop
0x180011bba  xor     r8d, r8d
0x180011bbd  mov     dl, 1
0x180011bbf  lea     rcx, [rbp+57h+var_50]
0x180011bc3  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180011bc8  nop
0x180011bc9  xor     r8d, r8d
0x180011bcc  mov     dl, 1
0x180011bce  mov     rcx, rdi
0x180011bd1  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180011bd6  mov     eax, esi
0x180011bd8  mov     rcx, [rbp+57h+var_30]
0x180011bdc  xor     rcx, rsp; StackCookie
0x180011bdf  call    __security_check_cookie
0x180011be4  add     rsp, 0A0h
0x180011beb  pop     r14
0x180011bed  pop     rdi
0x180011bee  pop     rsi
0x180011bef  pop     rbx
0x180011bf0  pop     rbp
0x180011bf1  retn
```
