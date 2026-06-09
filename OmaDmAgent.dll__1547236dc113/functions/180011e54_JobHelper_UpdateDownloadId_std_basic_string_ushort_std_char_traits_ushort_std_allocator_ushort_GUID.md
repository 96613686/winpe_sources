# JobHelper::UpdateDownloadId(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,_GUID)

- ea: `0x180011e54`
- end: `0x180012049`
- name: `?UpdateDownloadId@JobHelper@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_GUID@@@Z`
- size: `501`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, installer_update`

## callers

- `0x180014680`

## callees

- `0x180002a50`
- `0x1800062ac`
- `0x18000702c`
- `0x180009a14`
- `0x18000a2c0`
- `0x18000a3c0`
- `0x18000bae8`
- `0x18000f924`
- `0x18000fdf8`
- `0x180011e54`
- `0x18001f420`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180011eff`
- `KERNEL32!EnterCriticalSection` at `0x180011eff`
- `KERNEL32!LeaveCriticalSection` at `0x180011fe2`
- `KERNEL32!LeaveCriticalSection` at `0x180011fe2`
- `RPCRT4!UuidToStringW` at `0x180011f67`
- `RPCRT4!UuidToStringW` at `0x180011f67`
- `RPCRT4!RpcStringFreeW` at `0x180011ff9`
- `RPCRT4!RpcStringFreeW` at `0x180011ff9`

## string_xrefs

- `0x180011f90`: `BITSId`
- `0x180011fc4`: `BITSId`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall JobHelper::UpdateDownloadId(__int64 a1, __int64 a2, const UUID *a3)
{
  LSTATUS Key; // eax
  unsigned int v7; // edi
  struct _RTL_CRITICAL_SECTION *v8; // rbx
  __int64 v9; // rax
  int JobRegPath; // eax
  LPCWSTR v11; // rcx
  const unsigned __int16 *v12; // r9
  int v13; // edx
  const unsigned __int16 *v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // rdx
  RPC_WSTR StringUuid; // [rsp+30h] [rbp-39h] BYREF
  HKEY v19; // [rsp+38h] [rbp-31h] BYREF
  HKEY phkResult[2]; // [rsp+40h] [rbp-29h] BYREF
  _BYTE v21[32]; // [rsp+50h] [rbp-19h] BYREF
  __int64 v22; // [rsp+70h] [rbp+7h]
  unsigned __int16 *v23[4]; // [rsp+78h] [rbp+Fh] BYREF

  v22 = a2;
  std::wstring::wstring(v23, &dword_180022F6C);
  StringUuid = 0;
  phkResult[0] = 0;
  v19 = 0;
  Key = CurrentUserRegKeyHelper::GetKey(phkResult, &v19);
  v7 = Key;
  if ( Key < 0 )
  {
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        107,
        &WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
        (unsigned int)Key);
    v8 = (struct _RTL_CRITICAL_SECTION *)(a1 + 128);
    goto LABEL_22;
  }
  v8 = (struct _RTL_CRITICAL_SECTION *)(a1 + 128);
  EnterCriticalSection(v8);
  v9 = std::wstring::wstring(v21, a2);
  JobRegPath = JobHelper::GetJobRegPath(v9, v23);
  v7 = JobRegPath;
  if ( JobRegPath < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
      goto LABEL_22;
    if ( *(_QWORD *)(a2 + 24) < 8u )
      LODWORD(v12) = a2;
    else
      v12 = *(const unsigned __int16 **)a2;
    v13 = 108;
LABEL_21:
    WPP_SF_Sd(
      *((_QWORD *)v11 + 2),
      v13,
      (unsigned int)&WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
      (_DWORD)v12,
      JobRegPath);
    goto LABEL_22;
  }
  if ( UuidToStringW(a3, &StringUuid) )
  {
    v7 = -2147467259;
    goto LABEL_22;
  }
  v14 = (const unsigned __int16 *)v23;
  if ( v23[3] >= (unsigned __int16 *)8 )
    v14 = v23[0];
  JobRegPath = WriteRegSZValue(v19, v14, L"BITSId", (const BYTE *)StringUuid);
  v7 = JobRegPath;
  if ( JobRegPath < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    {
      v13 = 109;
      v12 = L"BITSId";
      goto LABEL_21;
    }
  }
LABEL_22:
  LeaveCriticalSection(v8);
  if ( StringUuid )
    RpcStringFreeW(&StringUuid);
  CurrentUserRegKeyHelper::~CurrentUserRegKeyHelper((CurrentUserRegKeyHelper *)phkResult);
  LOBYTE(v15) = 1;
  std::wstring::_Tidy(v23, v15, 0);
  LOBYTE(v16) = 1;
  std::wstring::_Tidy(a2, v16, 0);
  return v7;
}

```

## disassembly

```asm
0x180011e54  push    rbp
0x180011e56  push    rbx
0x180011e57  push    rsi
0x180011e58  push    rdi
0x180011e59  push    r14
0x180011e5b  lea     rbp, [rsp-37h]
0x180011e60  sub     rsp, 0A0h
0x180011e67  mov     rax, cs:__security_cookie
0x180011e6e  xor     rax, rsp
0x180011e71  mov     [rbp+57h+var_28], rax
0x180011e75  mov     r14, r8
0x180011e78  mov     rsi, rdx
0x180011e7b  mov     rbx, rcx
0x180011e7e  mov     [rbp+57h+var_50], rdx
0x180011e82  lea     rdx, dword_180022F6C
0x180011e89  lea     rcx, [rbp+57h+var_48]
0x180011e8d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180011e92  nop
0x180011e93  mov     [rbp+57h+StringUuid], 0
0x180011e9b  mov     [rbp+57h+phkResult], 0
0x180011ea3  mov     [rbp+57h+var_88], 0
0x180011eab  lea     rdx, [rbp+57h+var_88]; HKEY *
0x180011eaf  lea     rcx, [rbp+57h+phkResult]; phkResult
0x180011eb3  call    ?GetKey@CurrentUserRegKeyHelper@@QEAAJAEAPEAUHKEY__@@@Z; CurrentUserRegKeyHelper::GetKey(HKEY__ * &)
0x180011eb8  mov     edi, eax
0x180011eba  test    eax, eax
0x180011ebc  jns     short loc_180011EF8
0x180011ebe  lea     rdx, WPP_GLOBAL_Control
0x180011ec5  mov     rcx, cs:WPP_GLOBAL_Control
0x180011ecc  cmp     rcx, rdx
0x180011ecf  jz      short loc_180011EEF
0x180011ed1  test    byte ptr [rcx+1Ch], 4
0x180011ed5  jz      short loc_180011EEF
0x180011ed7  mov     edx, 6Bh ; 'k'
0x180011edc  mov     r9d, eax
0x180011edf  lea     r8, WPP_9f155fbe94773387205a22e9edb85311_Traceguids
0x180011ee6  mov     rcx, [rcx+10h]
0x180011eea  call    WPP_SF_d
0x180011eef  sub     rbx, 0FFFFFFFFFFFFFF80h
0x180011ef3  jmp     loc_180011FDF
0x180011ef8  sub     rbx, 0FFFFFFFFFFFFFF80h
0x180011efc  mov     rcx, rbx; lpCriticalSection
0x180011eff  call    cs:__imp_EnterCriticalSection
0x180011f06  nop     dword ptr [rax+rax+00h]
0x180011f0b  mov     rdx, rsi
0x180011f0e  lea     rcx, [rbp+57h+var_70]
0x180011f12  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180011f17  lea     rdx, [rbp+57h+var_48]
0x180011f1b  mov     rcx, rax
0x180011f1e  call    ?GetJobRegPath@JobHelper@@CAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z; JobHelper::GetJobRegPath(std::wstring,std::wstring &)
0x180011f23  mov     edi, eax
0x180011f25  test    eax, eax
0x180011f27  jns     short loc_180011F60
0x180011f29  lea     rdx, WPP_GLOBAL_Control
0x180011f30  mov     rcx, cs:WPP_GLOBAL_Control
0x180011f37  cmp     rcx, rdx
0x180011f3a  jz      loc_180011FDF
0x180011f40  test    byte ptr [rcx+1Ch], 4
0x180011f44  jz      loc_180011FDF
0x180011f4a  cmp     qword ptr [rsi+18h], 8
0x180011f4f  jb      short loc_180011F56
0x180011f51  mov     r9, [rsi]
0x180011f54  jmp     short loc_180011F59
0x180011f56  mov     r9, rsi
0x180011f59  mov     edx, 6Ch ; 'l'
0x180011f5e  jmp     short loc_180011FCB
0x180011f60  lea     rdx, [rbp+57h+StringUuid]; StringUuid
0x180011f64  mov     rcx, r14; Uuid
0x180011f67  call    cs:__imp_UuidToStringW
0x180011f6e  nop     dword ptr [rax+rax+00h]
0x180011f73  test    eax, eax
0x180011f75  jz      short loc_180011F7E
0x180011f77  mov     edi, 80004005h
0x180011f7c  jmp     short loc_180011FDF
0x180011f7e  lea     rdx, [rbp+57h+var_48]
0x180011f82  cmp     [rbp+57h+var_30], 8
0x180011f87  cmovnb  rdx, [rbp+57h+var_48]; unsigned __int16 *
0x180011f8c  mov     r9, [rbp+57h+StringUuid]; unsigned __int16 *
0x180011f90  lea     r8, aBitsid; "BITSId"
0x180011f97  mov     rcx, [rbp+57h+var_88]; HKEY
0x180011f9b  call    ?WriteRegSZValue@@YAJPEAUHKEY__@@PEBG11PEAU_SECURITY_ATTRIBUTES@@H@Z; WriteRegSZValue(HKEY__ *,ushort const *,ushort const *,ushort const *,_SECURITY_ATTRIBUTES *,int)
0x180011fa0  mov     edi, eax
0x180011fa2  test    eax, eax
0x180011fa4  jns     short loc_180011FDF
0x180011fa6  lea     rdx, WPP_GLOBAL_Control
0x180011fad  mov     rcx, cs:WPP_GLOBAL_Control
0x180011fb4  cmp     rcx, rdx
0x180011fb7  jz      short loc_180011FDF
0x180011fb9  test    byte ptr [rcx+1Ch], 4
0x180011fbd  jz      short loc_180011FDF
0x180011fbf  mov     edx, 6Dh ; 'm'
0x180011fc4  lea     r9, aBitsid; "BITSId"
0x180011fcb  mov     [rsp+0C0h+var_A0], eax
0x180011fcf  lea     r8, WPP_9f155fbe94773387205a22e9edb85311_Traceguids
0x180011fd6  mov     rcx, [rcx+10h]
0x180011fda  call    WPP_SF_Sd
0x180011fdf  mov     rcx, rbx; lpCriticalSection
0x180011fe2  call    cs:__imp_LeaveCriticalSection
0x180011fe9  nop     dword ptr [rax+rax+00h]
0x180011fee  cmp     [rbp+57h+StringUuid], 0
0x180011ff3  jz      short loc_180012006
0x180011ff5  lea     rcx, [rbp+57h+StringUuid]; String
0x180011ff9  call    cs:__imp_RpcStringFreeW
0x180012000  nop     dword ptr [rax+rax+00h]
0x180012005  nop
0x180012006  lea     rcx, [rbp+57h+phkResult]; this
0x18001200a  call    ??1CurrentUserRegKeyHelper@@QEAA@XZ; CurrentUserRegKeyHelper::~CurrentUserRegKeyHelper(void)
0x18001200f  nop
0x180012010  xor     r8d, r8d
0x180012013  mov     dl, 1
0x180012015  lea     rcx, [rbp+57h+var_48]
0x180012019  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001201e  nop
0x18001201f  xor     r8d, r8d
0x180012022  mov     dl, 1
0x180012024  mov     rcx, rsi
0x180012027  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001202c  mov     eax, edi
0x18001202e  mov     rcx, [rbp+57h+var_28]
0x180012032  xor     rcx, rsp; StackCookie
0x180012035  call    __security_check_cookie
0x18001203a  add     rsp, 0A0h
0x180012041  pop     r14
0x180012043  pop     rdi
0x180012044  pop     rsi
0x180012045  pop     rbx
0x180012046  pop     rbp
0x180012047  retn
```
