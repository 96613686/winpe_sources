# JobHelper::UpdateContentLocation(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x180011160`
- end: `0x180011391`
- name: `?UpdateContentLocation@JobHelper@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00@Z`
- size: `561`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update`

## callers

- `0x180013e10`

## callees

- `0x180002a50`
- `0x1800062ac`
- `0x18000702c`
- `0x180009a14`
- `0x18000a2c0`
- `0x18000a3c0`
- `0x18000a4f4`
- `0x18000bae8`
- `0x18000f7d4`
- `0x18000fdf8`
- `0x180011160`
- `0x18001f420`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180011210`
- `KERNEL32!EnterCriticalSection` at `0x180011210`
- `KERNEL32!LeaveCriticalSection` at `0x180011323`
- `KERNEL32!LeaveCriticalSection` at `0x180011323`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall JobHelper::UpdateContentLocation(__int64 a1, _QWORD *a2, __int64 *a3, __int64 a4)
{
  LSTATUS Key; // eax
  int JobDependencyRegPath; // ebx
  struct _RTL_CRITICAL_SECTION *v10; // rdi
  __int64 v11; // rbx
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // r9
  const BYTE *v15; // r9
  const unsigned __int16 *v16; // rdx
  int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // rdx
  __int64 v20; // rdx
  __int64 v21; // rdx
  HKEY v23; // [rsp+30h] [rbp-79h] BYREF
  HKEY phkResult[3]; // [rsp+38h] [rbp-71h] BYREF
  _BYTE v25[32]; // [rsp+50h] [rbp-59h] BYREF
  _BYTE v26[32]; // [rsp+70h] [rbp-39h] BYREF
  _QWORD *v27; // [rsp+90h] [rbp-19h]
  __int64 *v28; // [rsp+98h] [rbp-11h]
  __int64 v29; // [rsp+A0h] [rbp-9h]
  unsigned __int16 *v30[4]; // [rsp+A8h] [rbp-1h] BYREF

  v27 = a2;
  v28 = a3;
  v29 = a4;
  std::wstring::wstring(v30, &dword_180022F6C);
  phkResult[0] = 0;
  v23 = 0;
  Key = CurrentUserRegKeyHelper::GetKey(phkResult, &v23);
  JobDependencyRegPath = Key;
  if ( Key >= 0 )
  {
    v10 = (struct _RTL_CRITICAL_SECTION *)(a1 + 128);
    EnterCriticalSection(v10);
    phkResult[1] = (HKEY)v25;
    v11 = std::wstring::wstring(v25, a3);
    v12 = std::wstring::wstring(v26, a2);
    JobDependencyRegPath = JobHelper::GetJobDependencyRegPath(v12, v11, v30);
    if ( JobDependencyRegPath >= 0 )
    {
      if ( *(_QWORD *)(a4 + 24) < 8u )
        v15 = (const BYTE *)a4;
      else
        v15 = *(const BYTE **)a4;
      v16 = (const unsigned __int16 *)v30;
      if ( v30[3] >= (unsigned __int16 *)8 )
        v16 = v30[0];
      v17 = WriteRegSZValue(v23, v16, L"ContentLocation", v15);
      JobDependencyRegPath = v17;
      if ( v17 < 0 && WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          106,
          (unsigned int)&WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
          (unsigned int)L"ContentLocation",
          v17);
    }
    else if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    {
      if ( (unsigned __int64)a3[3] < 8 )
        v13 = (__int64)a3;
      else
        v13 = *a3;
      if ( a2[3] < 8u )
        LODWORD(v14) = (_DWORD)a2;
      else
        v14 = *a2;
      WPP_SF_SSD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        105,
        (unsigned int)&WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
        v14,
        v13,
        JobDependencyRegPath);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        104,
        &WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
        (unsigned int)Key);
    v10 = (struct _RTL_CRITICAL_SECTION *)(a1 + 128);
  }
  LeaveCriticalSection(v10);
  CurrentUserRegKeyHelper::~CurrentUserRegKeyHelper((CurrentUserRegKeyHelper *)phkResult);
  LOBYTE(v18) = 1;
  std::wstring::_Tidy(v30, v18, 0);
  LOBYTE(v19) = 1;
  std::wstring::_Tidy(a2, v19, 0);
  LOBYTE(v20) = 1;
  std::wstring::_Tidy(a3, v20, 0);
  LOBYTE(v21) = 1;
  std::wstring::_Tidy(a4, v21, 0);
  return (unsigned int)JobDependencyRegPath;
}

```

## disassembly

```asm
0x180011160  push    rbp
0x180011162  push    rbx
0x180011163  push    rsi
0x180011164  push    rdi
0x180011165  push    r14
0x180011167  push    r15
0x180011169  lea     rbp, [rsp-2Fh]
0x18001116e  sub     rsp, 0D8h
0x180011175  mov     rax, cs:__security_cookie
0x18001117c  xor     rax, rsp
0x18001117f  mov     [rbp+57h+var_38], rax
0x180011183  mov     r15, r9
0x180011186  mov     rsi, r8
0x180011189  mov     r14, rdx
0x18001118c  mov     rdi, rcx
0x18001118f  mov     [rbp+57h+var_70], rdx
0x180011193  mov     [rbp+57h+var_68], r8
0x180011197  mov     [rbp+57h+var_60], r9
0x18001119b  lea     rdx, dword_180022F6C
0x1800111a2  lea     rcx, [rbp+57h+var_58]
0x1800111a6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800111ab  nop
0x1800111ac  mov     [rbp+57h+phkResult], 0
0x1800111b4  mov     [rbp+57h+var_D0], 0
0x1800111bc  lea     rdx, [rbp+57h+var_D0]; HKEY *
0x1800111c0  lea     rcx, [rbp+57h+phkResult]; phkResult
0x1800111c4  call    ?GetKey@CurrentUserRegKeyHelper@@QEAAJAEAPEAUHKEY__@@@Z; CurrentUserRegKeyHelper::GetKey(HKEY__ * &)
0x1800111c9  mov     ebx, eax
0x1800111cb  test    eax, eax
0x1800111cd  jns     short loc_180011209
0x1800111cf  lea     rdx, WPP_GLOBAL_Control
0x1800111d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800111dd  cmp     rcx, rdx
0x1800111e0  jz      short loc_180011200
0x1800111e2  test    byte ptr [rcx+1Ch], 4
0x1800111e6  jz      short loc_180011200
0x1800111e8  mov     edx, 68h ; 'h'
0x1800111ed  mov     r9d, eax
0x1800111f0  lea     r8, WPP_9f155fbe94773387205a22e9edb85311_Traceguids
0x1800111f7  mov     rcx, [rcx+10h]
0x1800111fb  call    WPP_SF_d
0x180011200  sub     rdi, 0FFFFFFFFFFFFFF80h
0x180011204  jmp     loc_180011320
0x180011209  sub     rdi, 0FFFFFFFFFFFFFF80h
0x18001120d  mov     rcx, rdi; lpCriticalSection
0x180011210  call    cs:__imp_EnterCriticalSection
0x180011217  nop     dword ptr [rax+rax+00h]
0x18001121c  lea     rax, [rbp+57h+var_B0]
0x180011220  mov     [rbp+57h+var_C0], rax
0x180011224  mov     rdx, rsi
0x180011227  lea     rcx, [rbp+57h+var_B0]
0x18001122b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180011230  mov     rbx, rax
0x180011233  mov     rdx, r14
0x180011236  lea     rcx, [rbp+57h+var_90]
0x18001123a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001123f  nop
0x180011240  lea     r8, [rbp+57h+var_58]
0x180011244  mov     rdx, rbx
0x180011247  mov     rcx, rax
0x18001124a  call    ?GetJobDependencyRegPath@JobHelper@@CAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAV23@@Z; JobHelper::GetJobDependencyRegPath(std::wstring,std::wstring,std::wstring &)
0x18001124f  mov     ebx, eax
0x180011251  test    eax, eax
0x180011253  jns     short loc_1800112B4
0x180011255  lea     rdx, WPP_GLOBAL_Control
0x18001125c  mov     rcx, cs:WPP_GLOBAL_Control
0x180011263  cmp     rcx, rdx
0x180011266  jz      loc_180011320
0x18001126c  test    byte ptr [rcx+1Ch], 4
0x180011270  jz      loc_180011320
0x180011276  cmp     qword ptr [rsi+18h], 8
0x18001127b  jb      short loc_180011282
0x18001127d  mov     rax, [rsi]
0x180011280  jmp     short loc_180011285
0x180011282  mov     rax, rsi
0x180011285  cmp     qword ptr [r14+18h], 8
0x18001128a  jb      short loc_180011291
0x18001128c  mov     r9, [r14]
0x18001128f  jmp     short loc_180011294
0x180011291  mov     r9, r14
0x180011294  mov     edx, 69h ; 'i'
0x180011299  mov     [rsp+100h+var_D8], ebx
0x18001129d  mov     [rsp+100h+var_E0], rax
0x1800112a2  lea     r8, WPP_9f155fbe94773387205a22e9edb85311_Traceguids
0x1800112a9  mov     rcx, [rcx+10h]
0x1800112ad  call    WPP_SF_SSD
0x1800112b2  jmp     short loc_180011320
0x1800112b4  cmp     qword ptr [r15+18h], 8
0x1800112b9  jb      short loc_1800112C0
0x1800112bb  mov     r9, [r15]
0x1800112be  jmp     short loc_1800112C3
0x1800112c0  mov     r9, r15; unsigned __int16 *
0x1800112c3  lea     rdx, [rbp+57h+var_58]
0x1800112c7  cmp     [rbp+57h+var_40], 8
0x1800112cc  cmovnb  rdx, [rbp+57h+var_58]; unsigned __int16 *
0x1800112d1  lea     r8, aContentlocatio; "ContentLocation"
0x1800112d8  mov     rcx, [rbp+57h+var_D0]; HKEY
0x1800112dc  call    ?WriteRegSZValue@@YAJPEAUHKEY__@@PEBG11PEAU_SECURITY_ATTRIBUTES@@H@Z; WriteRegSZValue(HKEY__ *,ushort const *,ushort const *,ushort const *,_SECURITY_ATTRIBUTES *,int)
0x1800112e1  mov     ebx, eax
0x1800112e3  test    eax, eax
0x1800112e5  jns     short loc_180011320
0x1800112e7  lea     rdx, WPP_GLOBAL_Control
0x1800112ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800112f5  cmp     rcx, rdx
0x1800112f8  jz      short loc_180011320
0x1800112fa  test    byte ptr [rcx+1Ch], 4
0x1800112fe  jz      short loc_180011320
0x180011300  mov     edx, 6Ah ; 'j'
0x180011305  mov     dword ptr [rsp+100h+var_E0], eax
0x180011309  lea     r9, aContentlocatio; "ContentLocation"
0x180011310  lea     r8, WPP_9f155fbe94773387205a22e9edb85311_Traceguids
0x180011317  mov     rcx, [rcx+10h]
0x18001131b  call    WPP_SF_Sd
0x180011320  mov     rcx, rdi; lpCriticalSection
0x180011323  call    cs:__imp_LeaveCriticalSection
0x18001132a  nop     dword ptr [rax+rax+00h]
0x18001132f  nop
0x180011330  lea     rcx, [rbp+57h+phkResult]; this
0x180011334  call    ??1CurrentUserRegKeyHelper@@QEAA@XZ; CurrentUserRegKeyHelper::~CurrentUserRegKeyHelper(void)
0x180011339  nop
0x18001133a  xor     r8d, r8d
0x18001133d  mov     dl, 1
0x18001133f  lea     rcx, [rbp+57h+var_58]
0x180011343  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180011348  nop
0x180011349  xor     r8d, r8d
0x18001134c  mov     dl, 1
0x18001134e  mov     rcx, r14
0x180011351  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180011356  nop
0x180011357  xor     r8d, r8d
0x18001135a  mov     dl, 1
0x18001135c  mov     rcx, rsi
0x18001135f  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180011364  nop
0x180011365  xor     r8d, r8d
0x180011368  mov     dl, 1
0x18001136a  mov     rcx, r15
0x18001136d  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180011372  mov     eax, ebx
0x180011374  mov     rcx, [rbp+57h+var_38]
0x180011378  xor     rcx, rsp; StackCookie
0x18001137b  call    __security_check_cookie
0x180011380  add     rsp, 0D8h
0x180011387  pop     r15
0x180011389  pop     r14
0x18001138b  pop     rdi
0x18001138c  pop     rsi
0x18001138d  pop     rbx
0x18001138e  pop     rbp
0x18001138f  retn
```
