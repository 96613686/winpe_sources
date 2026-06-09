# JobHelper::UpdateCurrentDP(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ulong,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x180011574`
- end: `0x180011806`
- name: `?UpdateCurrentDP@JobHelper@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0K0@Z`
- size: `658`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000fe4c`

## callees

- `0x180002a50`
- `0x1800062ac`
- `0x18000702c`
- `0x1800098b0`
- `0x180009a14`
- `0x18000a2c0`
- `0x18000a3c0`
- `0x18000a4f4`
- `0x18000bae8`
- `0x18000f7d4`
- `0x18000fdf8`
- `0x180011574`
- `0x18001f420`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18001162c`
- `KERNEL32!EnterCriticalSection` at `0x18001162c`
- `KERNEL32!LeaveCriticalSection` at `0x180011796`
- `KERNEL32!LeaveCriticalSection` at `0x180011796`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall JobHelper::UpdateCurrentDP(__int64 a1, _QWORD *a2, __int64 *a3, int a4, unsigned __int16 *a5)
{
  LSTATUS Key; // eax
  int JobDependencyRegPath; // ebx
  struct _RTL_CRITICAL_SECTION *v11; // rdi
  __int64 v12; // rbx
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // r9
  const unsigned __int16 *v16; // rdx
  int v17; // eax
  LPCWSTR v18; // rcx
  int v19; // edx
  const unsigned __int16 *v20; // r9
  const BYTE *v21; // r9
  const unsigned __int16 *v22; // rdx
  __int64 v23; // rdx
  __int64 v24; // rdx
  __int64 v25; // rdx
  __int64 v26; // rdx
  HKEY v28; // [rsp+30h] [rbp-81h] BYREF
  HKEY phkResult[3]; // [rsp+38h] [rbp-79h] BYREF
  _BYTE v30[32]; // [rsp+50h] [rbp-61h] BYREF
  _BYTE v31[32]; // [rsp+70h] [rbp-41h] BYREF
  _QWORD *v32; // [rsp+90h] [rbp-21h]
  __int64 *v33; // [rsp+98h] [rbp-19h]
  unsigned __int16 *v34; // [rsp+A0h] [rbp-11h]
  unsigned __int16 *v35[3]; // [rsp+A8h] [rbp-9h] BYREF
  unsigned __int64 v36; // [rsp+C0h] [rbp+Fh]

  v32 = a2;
  v33 = a3;
  v34 = a5;
  std::wstring::wstring(v35, &dword_180022F6C);
  phkResult[0] = 0;
  v28 = 0;
  Key = CurrentUserRegKeyHelper::GetKey(phkResult, &v28);
  JobDependencyRegPath = Key;
  if ( Key < 0 )
  {
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        117,
        &WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
        (unsigned int)Key);
    v11 = (struct _RTL_CRITICAL_SECTION *)(a1 + 128);
    goto LABEL_32;
  }
  v11 = (struct _RTL_CRITICAL_SECTION *)(a1 + 128);
  EnterCriticalSection(v11);
  phkResult[1] = (HKEY)v30;
  v12 = std::wstring::wstring(v30, a3);
  v13 = std::wstring::wstring(v31, a2);
  JobDependencyRegPath = JobHelper::GetJobDependencyRegPath(v13, v12, v35);
  if ( JobDependencyRegPath < 0 )
  {
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    {
      if ( (unsigned __int64)a3[3] < 8 )
        v14 = (__int64)a3;
      else
        v14 = *a3;
      if ( a2[3] < 8u )
        LODWORD(v15) = (_DWORD)a2;
      else
        v15 = *a2;
      WPP_SF_SSD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        118,
        (unsigned int)&WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
        v15,
        v14,
        JobDependencyRegPath);
    }
    goto LABEL_32;
  }
  v16 = (const unsigned __int16 *)v35;
  if ( v36 >= 8 )
    v16 = v35[0];
  v17 = WriteRegDWORDValue(v28, v16, L"CurrentDPIndex", a4);
  JobDependencyRegPath = v17;
  if ( v17 < 0 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
      goto LABEL_32;
    v19 = 119;
    v20 = L"CurrentDPIndex";
LABEL_31:
    WPP_SF_Sd(
      *((_QWORD *)v18 + 2),
      v19,
      (unsigned int)&WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
      (_DWORD)v20,
      v17);
    goto LABEL_32;
  }
  if ( *((_QWORD *)a5 + 3) < 8u )
    v21 = (const BYTE *)a5;
  else
    v21 = *(const BYTE **)a5;
  v22 = (const unsigned __int16 *)v35;
  if ( v36 >= 8 )
    v22 = v35[0];
  v17 = WriteRegSZValue(v28, v22, L"CurrentDPUrl", v21);
  JobDependencyRegPath = v17;
  if ( v17 < 0 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    {
      v19 = 120;
      v20 = L"CurrentDPUrl";
      goto LABEL_31;
    }
  }
LABEL_32:
  LeaveCriticalSection(v11);
  CurrentUserRegKeyHelper::~CurrentUserRegKeyHelper((CurrentUserRegKeyHelper *)phkResult);
  LOBYTE(v23) = 1;
  std::wstring::_Tidy(v35, v23, 0);
  LOBYTE(v24) = 1;
  std::wstring::_Tidy(a2, v24, 0);
  LOBYTE(v25) = 1;
  std::wstring::_Tidy(a3, v25, 0);
  LOBYTE(v26) = 1;
  std::wstring::_Tidy(a5, v26, 0);
  return (unsigned int)JobDependencyRegPath;
}

```

## disassembly

```asm
0x180011574  push    rbp
0x180011576  push    rbx
0x180011577  push    rsi
0x180011578  push    rdi
0x180011579  push    r12
0x18001157b  push    r14
0x18001157d  push    r15
0x18001157f  lea     rbp, [rsp-1Fh]
0x180011584  sub     rsp, 0D0h
0x18001158b  mov     rax, cs:__security_cookie
0x180011592  xor     rax, rsp
0x180011595  mov     [rbp+4Fh+var_38], rax
0x180011599  mov     r12d, r9d
0x18001159c  mov     rsi, r8
0x18001159f  mov     r14, rdx
0x1800115a2  mov     rdi, rcx
0x1800115a5  mov     [rbp+4Fh+var_70], rdx
0x1800115a9  mov     [rbp+4Fh+var_68], r8
0x1800115ad  mov     r15, [rbp+4Fh+arg_20]
0x1800115b1  mov     [rbp+4Fh+var_60], r15
0x1800115b5  lea     rdx, dword_180022F6C
0x1800115bc  lea     rcx, [rbp+4Fh+var_58]
0x1800115c0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800115c5  nop
0x1800115c6  mov     [rbp+4Fh+phkResult], 0
0x1800115ce  mov     [rsp+100h+var_D0], 0
0x1800115d7  lea     rdx, [rsp+100h+var_D0]; HKEY *
0x1800115dc  lea     rcx, [rbp+4Fh+phkResult]; phkResult
0x1800115e0  call    ?GetKey@CurrentUserRegKeyHelper@@QEAAJAEAPEAUHKEY__@@@Z; CurrentUserRegKeyHelper::GetKey(HKEY__ * &)
0x1800115e5  mov     ebx, eax
0x1800115e7  test    eax, eax
0x1800115e9  jns     short loc_180011625
0x1800115eb  lea     rdx, WPP_GLOBAL_Control
0x1800115f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800115f9  cmp     rcx, rdx
0x1800115fc  jz      short loc_18001161C
0x1800115fe  test    byte ptr [rcx+1Ch], 4
0x180011602  jz      short loc_18001161C
0x180011604  mov     edx, 75h ; 'u'
0x180011609  mov     r9d, eax
0x18001160c  lea     r8, WPP_9f155fbe94773387205a22e9edb85311_Traceguids
0x180011613  mov     rcx, [rcx+10h]
0x180011617  call    WPP_SF_d
0x18001161c  sub     rdi, 0FFFFFFFFFFFFFF80h
0x180011620  jmp     loc_180011793
0x180011625  sub     rdi, 0FFFFFFFFFFFFFF80h
0x180011629  mov     rcx, rdi; lpCriticalSection
0x18001162c  call    cs:__imp_EnterCriticalSection
0x180011633  nop     dword ptr [rax+rax+00h]
0x180011638  lea     rax, [rbp+4Fh+var_B0]
0x18001163c  mov     [rbp+4Fh+var_C0], rax
0x180011640  mov     rdx, rsi
0x180011643  lea     rcx, [rbp+4Fh+var_B0]
0x180011647  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001164c  mov     rbx, rax
0x18001164f  mov     rdx, r14
0x180011652  lea     rcx, [rbp+4Fh+var_90]
0x180011656  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001165b  nop
0x18001165c  lea     r8, [rbp+4Fh+var_58]
0x180011660  mov     rdx, rbx
0x180011663  mov     rcx, rax
0x180011666  call    ?GetJobDependencyRegPath@JobHelper@@CAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAV23@@Z; JobHelper::GetJobDependencyRegPath(std::wstring,std::wstring,std::wstring &)
0x18001166b  mov     ebx, eax
0x18001166d  test    eax, eax
0x18001166f  jns     short loc_1800116D3
0x180011671  lea     rdx, WPP_GLOBAL_Control
0x180011678  mov     rcx, cs:WPP_GLOBAL_Control
0x18001167f  cmp     rcx, rdx
0x180011682  jz      loc_180011793
0x180011688  test    byte ptr [rcx+1Ch], 4
0x18001168c  jz      loc_180011793
0x180011692  cmp     qword ptr [rsi+18h], 8
0x180011697  jb      short loc_18001169E
0x180011699  mov     rax, [rsi]
0x18001169c  jmp     short loc_1800116A1
0x18001169e  mov     rax, rsi
0x1800116a1  cmp     qword ptr [r14+18h], 8
0x1800116a6  jb      short loc_1800116AD
0x1800116a8  mov     r9, [r14]
0x1800116ab  jmp     short loc_1800116B0
0x1800116ad  mov     r9, r14
0x1800116b0  mov     edx, 76h ; 'v'
0x1800116b5  mov     [rsp+100h+var_D8], ebx
0x1800116b9  mov     [rsp+100h+var_E0], rax
0x1800116be  lea     r8, WPP_9f155fbe94773387205a22e9edb85311_Traceguids
0x1800116c5  mov     rcx, [rcx+10h]
0x1800116c9  call    WPP_SF_SSD
0x1800116ce  jmp     loc_180011793
0x1800116d3  lea     rdx, [rbp+4Fh+var_58]
0x1800116d7  cmp     [rbp+4Fh+var_40], 8
0x1800116dc  cmovnb  rdx, [rbp+4Fh+var_58]; unsigned __int16 *
0x1800116e1  mov     r9d, r12d; unsigned int
0x1800116e4  lea     r8, aCurrentdpindex; "CurrentDPIndex"
0x1800116eb  mov     rcx, [rsp+100h+var_D0]; HKEY
0x1800116f0  call    ?WriteRegDWORDValue@@YAJPEAUHKEY__@@PEBG1KPEAU_SECURITY_ATTRIBUTES@@@Z; WriteRegDWORDValue(HKEY__ *,ushort const *,ushort const *,ulong,_SECURITY_ATTRIBUTES *)
0x1800116f5  mov     ebx, eax
0x1800116f7  test    eax, eax
0x1800116f9  jns     short loc_180011726
0x1800116fb  lea     rdx, WPP_GLOBAL_Control
0x180011702  mov     rcx, cs:WPP_GLOBAL_Control
0x180011709  cmp     rcx, rdx
0x18001170c  jz      loc_180011793
0x180011712  test    byte ptr [rcx+1Ch], 4
0x180011716  jz      short loc_180011793
0x180011718  mov     edx, 77h ; 'w'
0x18001171d  lea     r9, aCurrentdpindex; "CurrentDPIndex"
0x180011724  jmp     short loc_18001177F
0x180011726  cmp     qword ptr [r15+18h], 8
0x18001172b  jb      short loc_180011732
0x18001172d  mov     r9, [r15]
0x180011730  jmp     short loc_180011735
0x180011732  mov     r9, r15; unsigned __int16 *
0x180011735  lea     rdx, [rbp+4Fh+var_58]
0x180011739  cmp     [rbp+4Fh+var_40], 8
0x18001173e  cmovnb  rdx, [rbp+4Fh+var_58]; unsigned __int16 *
0x180011743  lea     r8, aCurrentdpurl; "CurrentDPUrl"
0x18001174a  mov     rcx, [rsp+100h+var_D0]; HKEY
0x18001174f  call    ?WriteRegSZValue@@YAJPEAUHKEY__@@PEBG11PEAU_SECURITY_ATTRIBUTES@@H@Z; WriteRegSZValue(HKEY__ *,ushort const *,ushort const *,ushort const *,_SECURITY_ATTRIBUTES *,int)
0x180011754  mov     ebx, eax
0x180011756  test    eax, eax
0x180011758  jns     short loc_180011793
0x18001175a  lea     rdx, WPP_GLOBAL_Control
0x180011761  mov     rcx, cs:WPP_GLOBAL_Control
0x180011768  cmp     rcx, rdx
0x18001176b  jz      short loc_180011793
0x18001176d  test    byte ptr [rcx+1Ch], 4
0x180011771  jz      short loc_180011793
0x180011773  mov     edx, 78h ; 'x'
0x180011778  lea     r9, aCurrentdpurl; "CurrentDPUrl"
0x18001177f  mov     dword ptr [rsp+100h+var_E0], eax
0x180011783  lea     r8, WPP_9f155fbe94773387205a22e9edb85311_Traceguids
0x18001178a  mov     rcx, [rcx+10h]
0x18001178e  call    WPP_SF_Sd
0x180011793  mov     rcx, rdi; lpCriticalSection
0x180011796  call    cs:__imp_LeaveCriticalSection
0x18001179d  nop     dword ptr [rax+rax+00h]
0x1800117a2  nop
0x1800117a3  lea     rcx, [rbp+4Fh+phkResult]; this
0x1800117a7  call    ??1CurrentUserRegKeyHelper@@QEAA@XZ; CurrentUserRegKeyHelper::~CurrentUserRegKeyHelper(void)
0x1800117ac  nop
0x1800117ad  xor     r8d, r8d
0x1800117b0  mov     dl, 1
0x1800117b2  lea     rcx, [rbp+4Fh+var_58]
0x1800117b6  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800117bb  nop
0x1800117bc  xor     r8d, r8d
0x1800117bf  mov     dl, 1
0x1800117c1  mov     rcx, r14
0x1800117c4  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800117c9  nop
0x1800117ca  xor     r8d, r8d
0x1800117cd  mov     dl, 1
0x1800117cf  mov     rcx, rsi
0x1800117d2  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800117d7  nop
0x1800117d8  xor     r8d, r8d
0x1800117db  mov     dl, 1
0x1800117dd  mov     rcx, r15
0x1800117e0  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800117e5  mov     eax, ebx
0x1800117e7  mov     rcx, [rbp+4Fh+var_38]
0x1800117eb  xor     rcx, rsp; StackCookie
0x1800117ee  call    __security_check_cookie
0x1800117f3  add     rsp, 0D0h
0x1800117fa  pop     r15
0x1800117fc  pop     r14
0x1800117fe  pop     r12
0x180011800  pop     rdi
0x180011801  pop     rsi
0x180011802  pop     rbx
0x180011803  pop     rbp
0x180011804  retn
```
