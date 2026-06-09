# JobHelper::UpdateCurrentDP(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ulong,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x18001180c`
- end: `0x180011a3d`
- name: `?UpdateCurrentDP@JobHelper@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K0@Z`
- size: `561`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800100a4`

## callees

- `0x180002a50`
- `0x1800062ac`
- `0x18000702c`
- `0x1800098b0`
- `0x180009a14`
- `0x18000a2c0`
- `0x18000a3c0`
- `0x18000bae8`
- `0x18000f924`
- `0x18000fdf8`
- `0x18001180c`
- `0x18001f420`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800118b8`
- `KERNEL32!EnterCriticalSection` at `0x1800118b8`
- `KERNEL32!LeaveCriticalSection` at `0x1800119dd`
- `KERNEL32!LeaveCriticalSection` at `0x1800119dd`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall JobHelper::UpdateCurrentDP(__int64 a1, __int64 a2, int a3, __int64 a4)
{
  LSTATUS Key; // eax
  unsigned int v9; // edi
  struct _RTL_CRITICAL_SECTION *v10; // rbx
  __int64 v11; // rax
  int JobRegPath; // eax
  LPCWSTR v13; // rcx
  const unsigned __int16 *v14; // r9
  int v15; // edx
  const unsigned __int16 *v16; // rdx
  const BYTE *v17; // r9
  const unsigned __int16 *v18; // rdx
  __int64 v19; // rdx
  __int64 v20; // rdx
  __int64 v21; // rdx
  HKEY v23; // [rsp+30h] [rbp-49h] BYREF
  HKEY phkResult[2]; // [rsp+38h] [rbp-41h] BYREF
  _BYTE v25[32]; // [rsp+48h] [rbp-31h] BYREF
  __int64 v26; // [rsp+68h] [rbp-11h]
  __int64 v27; // [rsp+70h] [rbp-9h]
  unsigned __int16 *v28[3]; // [rsp+78h] [rbp-1h] BYREF
  unsigned __int64 v29; // [rsp+90h] [rbp+17h]

  v26 = a2;
  v27 = a4;
  std::wstring::wstring(v28, &dword_180022F6C);
  phkResult[0] = 0;
  v23 = 0;
  Key = CurrentUserRegKeyHelper::GetKey(phkResult, &v23);
  v9 = Key;
  if ( Key < 0 )
  {
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        113,
        &WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
        (unsigned int)Key);
    v10 = (struct _RTL_CRITICAL_SECTION *)(a1 + 128);
    goto LABEL_29;
  }
  v10 = (struct _RTL_CRITICAL_SECTION *)(a1 + 128);
  EnterCriticalSection(v10);
  v11 = std::wstring::wstring(v25, a2);
  JobRegPath = JobHelper::GetJobRegPath(v11, (__int64)v28);
  v9 = JobRegPath;
  if ( JobRegPath < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
      goto LABEL_29;
    if ( *(_QWORD *)(a2 + 24) < 8u )
      LODWORD(v14) = a2;
    else
      v14 = *(const unsigned __int16 **)a2;
    v15 = 114;
    goto LABEL_28;
  }
  v16 = (const unsigned __int16 *)v28;
  if ( v29 >= 8 )
    v16 = v28[0];
  JobRegPath = WriteRegDWORDValue(v23, v16, L"CurrentDPIndex", a3);
  v9 = JobRegPath;
  if ( JobRegPath < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
      goto LABEL_29;
    v15 = 115;
    v14 = L"CurrentDPIndex";
LABEL_28:
    WPP_SF_Sd(
      *((_QWORD *)v13 + 2),
      v15,
      (unsigned int)&WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
      (_DWORD)v14,
      JobRegPath);
    goto LABEL_29;
  }
  if ( *(_QWORD *)(a4 + 24) < 8u )
    v17 = (const BYTE *)a4;
  else
    v17 = *(const BYTE **)a4;
  v18 = (const unsigned __int16 *)v28;
  if ( v29 >= 8 )
    v18 = v28[0];
  JobRegPath = WriteRegSZValue(v23, v18, L"CurrentDPUrl", v17);
  v9 = JobRegPath;
  if ( JobRegPath < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    {
      v15 = 116;
      v14 = L"CurrentDPUrl";
      goto LABEL_28;
    }
  }
LABEL_29:
  LeaveCriticalSection(v10);
  CurrentUserRegKeyHelper::~CurrentUserRegKeyHelper((CurrentUserRegKeyHelper *)phkResult);
  LOBYTE(v19) = 1;
  std::wstring::_Tidy(v28, v19, 0);
  LOBYTE(v20) = 1;
  std::wstring::_Tidy(a2, v20, 0);
  LOBYTE(v21) = 1;
  std::wstring::_Tidy(a4, v21, 0);
  return v9;
}

```

## disassembly

```asm
0x18001180c  push    rbp
0x18001180e  push    rbx
0x18001180f  push    rsi
0x180011810  push    rdi
0x180011811  push    r14
0x180011813  push    r15
0x180011815  lea     rbp, [rsp-2Fh]
0x18001181a  sub     rsp, 0A8h
0x180011821  mov     rax, cs:__security_cookie
0x180011828  xor     rax, rsp
0x18001182b  mov     [rbp+57h+var_38], rax
0x18001182f  mov     r14, r9
0x180011832  mov     r15d, r8d
0x180011835  mov     rsi, rdx
0x180011838  mov     rbx, rcx
0x18001183b  mov     [rbp+57h+var_68], rdx
0x18001183f  mov     [rbp+57h+var_60], r9
0x180011843  lea     rdx, dword_180022F6C
0x18001184a  lea     rcx, [rbp+57h+var_58]
0x18001184e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180011853  nop
0x180011854  mov     [rbp+57h+phkResult], 0
0x18001185c  mov     [rbp+57h+var_A0], 0
0x180011864  lea     rdx, [rbp+57h+var_A0]; HKEY *
0x180011868  lea     rcx, [rbp+57h+phkResult]; phkResult
0x18001186c  call    ?GetKey@CurrentUserRegKeyHelper@@QEAAJAEAPEAUHKEY__@@@Z; CurrentUserRegKeyHelper::GetKey(HKEY__ * &)
0x180011871  mov     edi, eax
0x180011873  test    eax, eax
0x180011875  jns     short loc_1800118B1
0x180011877  lea     rdx, WPP_GLOBAL_Control
0x18001187e  mov     rcx, cs:WPP_GLOBAL_Control
0x180011885  cmp     rcx, rdx
0x180011888  jz      short loc_1800118A8
0x18001188a  test    byte ptr [rcx+1Ch], 4
0x18001188e  jz      short loc_1800118A8
0x180011890  mov     edx, 71h ; 'q'
0x180011895  mov     r9d, eax
0x180011898  lea     r8, WPP_9f155fbe94773387205a22e9edb85311_Traceguids
0x18001189f  mov     rcx, [rcx+10h]
0x1800118a3  call    WPP_SF_d
0x1800118a8  sub     rbx, 0FFFFFFFFFFFFFF80h
0x1800118ac  jmp     loc_1800119DA
0x1800118b1  sub     rbx, 0FFFFFFFFFFFFFF80h
0x1800118b5  mov     rcx, rbx; lpCriticalSection
0x1800118b8  call    cs:__imp_EnterCriticalSection
0x1800118bf  nop     dword ptr [rax+rax+00h]
0x1800118c4  mov     rdx, rsi
0x1800118c7  lea     rcx, [rbp+57h+var_88]
0x1800118cb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800118d0  lea     rdx, [rbp+57h+var_58]
0x1800118d4  mov     rcx, rax
0x1800118d7  call    ?GetJobRegPath@JobHelper@@CAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z; JobHelper::GetJobRegPath(std::wstring,std::wstring &)
0x1800118dc  mov     edi, eax
0x1800118de  test    eax, eax
0x1800118e0  jns     short loc_18001191C
0x1800118e2  lea     rdx, WPP_GLOBAL_Control
0x1800118e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800118f0  cmp     rcx, rdx
0x1800118f3  jz      loc_1800119DA
0x1800118f9  test    byte ptr [rcx+1Ch], 4
0x1800118fd  jz      loc_1800119DA
0x180011903  cmp     qword ptr [rsi+18h], 8
0x180011908  jb      short loc_18001190F
0x18001190a  mov     r9, [rsi]
0x18001190d  jmp     short loc_180011912
0x18001190f  mov     r9, rsi
0x180011912  mov     edx, 72h ; 'r'
0x180011917  jmp     loc_1800119C6
0x18001191c  lea     rdx, [rbp+57h+var_58]
0x180011920  cmp     [rbp+57h+var_40], 8
0x180011925  cmovnb  rdx, [rbp+57h+var_58]; unsigned __int16 *
0x18001192a  mov     r9d, r15d; unsigned int
0x18001192d  lea     r8, aCurrentdpindex; "CurrentDPIndex"
0x180011934  mov     rcx, [rbp+57h+var_A0]; HKEY
0x180011938  call    ?WriteRegDWORDValue@@YAJPEAUHKEY__@@PEBG1KPEAU_SECURITY_ATTRIBUTES@@@Z; WriteRegDWORDValue(HKEY__ *,ushort const *,ushort const *,ulong,_SECURITY_ATTRIBUTES *)
0x18001193d  mov     edi, eax
0x18001193f  test    eax, eax
0x180011941  jns     short loc_18001196E
0x180011943  lea     rdx, WPP_GLOBAL_Control
0x18001194a  mov     rcx, cs:WPP_GLOBAL_Control
0x180011951  cmp     rcx, rdx
0x180011954  jz      loc_1800119DA
0x18001195a  test    byte ptr [rcx+1Ch], 4
0x18001195e  jz      short loc_1800119DA
0x180011960  mov     edx, 73h ; 's'
0x180011965  lea     r9, aCurrentdpindex; "CurrentDPIndex"
0x18001196c  jmp     short loc_1800119C6
0x18001196e  cmp     qword ptr [r14+18h], 8
0x180011973  jb      short loc_18001197A
0x180011975  mov     r9, [r14]
0x180011978  jmp     short loc_18001197D
0x18001197a  mov     r9, r14; unsigned __int16 *
0x18001197d  lea     rdx, [rbp+57h+var_58]
0x180011981  cmp     [rbp+57h+var_40], 8
0x180011986  cmovnb  rdx, [rbp+57h+var_58]; unsigned __int16 *
0x18001198b  lea     r8, aCurrentdpurl; "CurrentDPUrl"
0x180011992  mov     rcx, [rbp+57h+var_A0]; HKEY
0x180011996  call    ?WriteRegSZValue@@YAJPEAUHKEY__@@PEBG11PEAU_SECURITY_ATTRIBUTES@@H@Z; WriteRegSZValue(HKEY__ *,ushort const *,ushort const *,ushort const *,_SECURITY_ATTRIBUTES *,int)
0x18001199b  mov     edi, eax
0x18001199d  test    eax, eax
0x18001199f  jns     short loc_1800119DA
0x1800119a1  lea     rdx, WPP_GLOBAL_Control
0x1800119a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800119af  cmp     rcx, rdx
0x1800119b2  jz      short loc_1800119DA
0x1800119b4  test    byte ptr [rcx+1Ch], 4
0x1800119b8  jz      short loc_1800119DA
0x1800119ba  mov     edx, 74h ; 't'
0x1800119bf  lea     r9, aCurrentdpurl; "CurrentDPUrl"
0x1800119c6  mov     [rsp+0D0h+var_B0], eax
0x1800119ca  lea     r8, WPP_9f155fbe94773387205a22e9edb85311_Traceguids
0x1800119d1  mov     rcx, [rcx+10h]
0x1800119d5  call    WPP_SF_Sd
0x1800119da  mov     rcx, rbx; lpCriticalSection
0x1800119dd  call    cs:__imp_LeaveCriticalSection
0x1800119e4  nop     dword ptr [rax+rax+00h]
0x1800119e9  nop
0x1800119ea  lea     rcx, [rbp+57h+phkResult]; this
0x1800119ee  call    ??1CurrentUserRegKeyHelper@@QEAA@XZ; CurrentUserRegKeyHelper::~CurrentUserRegKeyHelper(void)
0x1800119f3  nop
0x1800119f4  xor     r8d, r8d
0x1800119f7  mov     dl, 1
0x1800119f9  lea     rcx, [rbp+57h+var_58]
0x1800119fd  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180011a02  nop
0x180011a03  xor     r8d, r8d
0x180011a06  mov     dl, 1
0x180011a08  mov     rcx, rsi
0x180011a0b  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180011a10  nop
0x180011a11  xor     r8d, r8d
0x180011a14  mov     dl, 1
0x180011a16  mov     rcx, r14
0x180011a19  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180011a1e  mov     eax, edi
0x180011a20  mov     rcx, [rbp+57h+var_38]
0x180011a24  xor     rcx, rsp; StackCookie
0x180011a27  call    __security_check_cookie
0x180011a2c  add     rsp, 0A8h
0x180011a33  pop     r15
0x180011a35  pop     r14
0x180011a37  pop     rdi
0x180011a38  pop     rsi
0x180011a39  pop     rbx
0x180011a3a  pop     rbp
0x180011a3b  retn
```
