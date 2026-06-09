# JobHelper::UpdateProgress(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,JobStatus,ulong,ulong,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x180012338`
- end: `0x180012679`
- name: `?UpdateProgress@JobHelper@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4JobStatus@@KK0@Z`
- size: `833`
- prototype: ``
- caller_count: `13`
- callee_count: `13`
- tags: `installer_update`

## callers

- `0x18000ccb4`
- `0x18000d2cc`
- `0x18000dcb4`
- `0x1800102b8`
- `0x180010700`
- `0x180010eac`
- `0x180013330`
- `0x180014680`
- `0x180017b58`
- `0x18001cb10`
- `0x18001d000`
- `0x18001d910`
- `0x18001da10`

## callees

- `0x180002a50`
- `0x1800062ac`
- `0x18000702c`
- `0x1800098b0`
- `0x180009a14`
- `0x18000a2c0`
- `0x18000a3c0`
- `0x18000a6a4`
- `0x18000bae8`
- `0x18000f924`
- `0x18000fdf8`
- `0x180012338`
- `0x18001f420`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18001246e`
- `KERNEL32!EnterCriticalSection` at `0x18001246e`
- `KERNEL32!LeaveCriticalSection` at `0x1800125d2`
- `KERNEL32!LeaveCriticalSection` at `0x1800125d2`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall JobHelper::UpdateProgress(
        __int64 a1,
        _QWORD *a2,
        int a3,
        int a4,
        unsigned int a5,
        unsigned __int16 *a6)
{
  int v7; // r14d
  __int64 v10; // rax
  int JobRegPath; // eax
  int v12; // ebx
  __int64 v13; // r9
  const unsigned __int16 *v14; // rsi
  LSTATUS Key; // eax
  int v16; // r9d
  HKEY v17; // r14
  int v18; // eax
  LPCWSTR v19; // rcx
  int v20; // edx
  const unsigned __int16 *v21; // r9
  const BYTE *v22; // r9
  __int64 v23; // r9
  __int64 v24; // rdx
  __int64 v25; // rdx
  __int64 v26; // rdx
  char v28; // [rsp+30h] [rbp-79h]
  HKEY v29; // [rsp+38h] [rbp-71h] BYREF
  HKEY phkResult[2]; // [rsp+40h] [rbp-69h] BYREF
  char v31[32]; // [rsp+50h] [rbp-59h] BYREF
  _QWORD *v32; // [rsp+70h] [rbp-39h]
  unsigned __int16 *v33; // [rsp+78h] [rbp-31h]
  unsigned __int16 *v34[4]; // [rsp+80h] [rbp-29h] BYREF

  v7 = a3;
  v28 = a3;
  v32 = a2;
  v33 = a6;
  std::wstring::wstring(v34, &dword_180022F6C);
  phkResult[0] = 0;
  v29 = 0;
  v10 = std::wstring::wstring(v31, a2);
  JobRegPath = JobHelper::GetJobRegPath(v10, v34);
  v12 = JobRegPath;
  if ( JobRegPath < 0 )
  {
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    {
      if ( a2[3] < 8u )
        LODWORD(v13) = (_DWORD)a2;
      else
        v13 = *a2;
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        89,
        (unsigned int)&WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
        v13,
        JobRegPath);
    }
    goto LABEL_35;
  }
  v14 = (const unsigned __int16 *)v34;
  if ( v34[3] >= (unsigned __int16 *)8 )
    v14 = v34[0];
  Key = CurrentUserRegKeyHelper::GetKey(phkResult, &v29);
  v12 = Key;
  if ( Key >= 0 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 128));
    v16 = v7;
    v17 = v29;
    v18 = WriteRegDWORDValue(v29, v14, L"Status", v16);
    v12 = v18;
    if ( v18 >= 0 )
    {
      v18 = WriteRegDWORDValue(v17, v14, L"Progress", a4);
      v12 = v18;
      if ( v18 >= 0 )
      {
        v18 = WriteRegDWORDValue(v17, v14, L"LastError", a5);
        v12 = v18;
        if ( v18 >= 0 )
        {
          if ( *((_QWORD *)a6 + 3) < 8u )
            v22 = (const BYTE *)a6;
          else
            v22 = *(const BYTE **)a6;
          v18 = WriteRegSZValue(v17, v14, L"LastErrorDesc", v22);
          v12 = v18;
          if ( v18 >= 0 )
            goto LABEL_34;
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
            goto LABEL_34;
          v20 = 94;
          v21 = L"LastErrorDesc";
        }
        else
        {
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
            goto LABEL_34;
          v20 = 93;
          v21 = L"LastError";
        }
      }
      else
      {
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
          goto LABEL_34;
        v20 = 92;
        v21 = L"Progress";
      }
    }
    else
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
        goto LABEL_34;
      v20 = 91;
      v21 = L"Status";
    }
    WPP_SF_Sd(
      *((_QWORD *)v19 + 2),
      v20,
      (unsigned int)&WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
      (_DWORD)v21,
      v18);
LABEL_34:
    LOBYTE(v7) = v28;
    goto LABEL_35;
  }
  if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      90,
      &WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
      (unsigned int)Key);
LABEL_35:
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 128));
  if ( v12 < 0 && WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
  {
    if ( a2[3] < 8u )
      LODWORD(v23) = (_DWORD)a2;
    else
      v23 = *a2;
    WPP_SF_SdD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      95,
      (unsigned int)&WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
      v23,
      v7,
      v12);
  }
  CurrentUserRegKeyHelper::~CurrentUserRegKeyHelper((CurrentUserRegKeyHelper *)phkResult);
  LOBYTE(v24) = 1;
  std::wstring::_Tidy(v34, v24, 0);
  LOBYTE(v25) = 1;
  std::wstring::_Tidy(a2, v25, 0);
  LOBYTE(v26) = 1;
  std::wstring::_Tidy(a6, v26, 0);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180012338  push    rbp
0x18001233a  push    rbx
0x18001233b  push    rsi
0x18001233c  push    rdi
0x18001233d  push    r12
0x18001233f  push    r13
0x180012341  push    r14
0x180012343  push    r15
0x180012345  lea     rbp, [rsp-0Fh]
0x18001234a  sub     rsp, 0B8h
0x180012351  mov     rax, cs:__security_cookie
0x180012358  xor     rax, rsp
0x18001235b  mov     [rbp+47h+var_50], rax
0x18001235f  mov     r12d, r9d
0x180012362  mov     r14d, r8d
0x180012365  mov     dword ptr [rbp+47h+var_C0], r8d
0x180012369  mov     rdi, rdx
0x18001236c  mov     r13, rcx
0x18001236f  mov     [rbp+47h+var_80], rdx
0x180012373  mov     r15, [rbp+47h+arg_28]
0x180012377  mov     [rbp+47h+var_78], r15
0x18001237b  lea     rdx, dword_180022F6C
0x180012382  lea     rcx, [rbp+47h+var_70]
0x180012386  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18001238b  nop
0x18001238c  mov     [rbp+47h+phkResult], 0
0x180012394  mov     [rbp+47h+var_B8], 0
0x18001239c  mov     rdx, rdi
0x18001239f  lea     rcx, [rbp+47h+var_A0]
0x1800123a3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800123a8  lea     rdx, [rbp+47h+var_70]
0x1800123ac  mov     rcx, rax
0x1800123af  call    ?GetJobRegPath@JobHelper@@CAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z; JobHelper::GetJobRegPath(std::wstring,std::wstring &)
0x1800123b4  mov     ebx, eax
0x1800123b6  lea     rsi, WPP_GLOBAL_Control
0x1800123bd  test    eax, eax
0x1800123bf  jns     short loc_180012408
0x1800123c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800123c8  cmp     rcx, rsi
0x1800123cb  jz      loc_1800125CB
0x1800123d1  test    byte ptr [rcx+1Ch], 4
0x1800123d5  jz      loc_1800125CB
0x1800123db  cmp     qword ptr [rdi+18h], 8
0x1800123e0  jb      short loc_1800123E7
0x1800123e2  mov     r9, [rdi]
0x1800123e5  jmp     short loc_1800123EA
0x1800123e7  mov     r9, rdi
0x1800123ea  mov     edx, 59h ; 'Y'
0x1800123ef  mov     [rsp+0F0h+var_D0], eax
0x1800123f3  lea     r8, WPP_9f155fbe94773387205a22e9edb85311_Traceguids
0x1800123fa  mov     rcx, [rcx+10h]
0x1800123fe  call    WPP_SF_Sd
0x180012403  jmp     loc_1800125CB
0x180012408  lea     rsi, [rbp+47h+var_70]
0x18001240c  cmp     [rbp+47h+var_58], 8
0x180012411  cmovnb  rsi, [rbp+47h+var_70]
0x180012416  lea     rdx, [rbp+47h+var_B8]; HKEY *
0x18001241a  lea     rcx, [rbp+47h+phkResult]; phkResult
0x18001241e  call    ?GetKey@CurrentUserRegKeyHelper@@QEAAJAEAPEAUHKEY__@@@Z; CurrentUserRegKeyHelper::GetKey(HKEY__ * &)
0x180012423  mov     ebx, eax
0x180012425  test    eax, eax
0x180012427  jns     short loc_180012467
0x180012429  mov     rcx, cs:WPP_GLOBAL_Control
0x180012430  lea     rsi, WPP_GLOBAL_Control
0x180012437  cmp     rcx, rsi
0x18001243a  jz      loc_1800125CB
0x180012440  test    byte ptr [rcx+1Ch], 4
0x180012444  jz      loc_1800125CB
0x18001244a  mov     edx, 5Ah ; 'Z'
0x18001244f  mov     r9d, eax
0x180012452  lea     r8, WPP_9f155fbe94773387205a22e9edb85311_Traceguids
0x180012459  mov     rcx, [rcx+10h]
0x18001245d  call    WPP_SF_d
0x180012462  jmp     loc_1800125CB
0x180012467  lea     rcx, [r13+80h]; lpCriticalSection
0x18001246e  call    cs:__imp_EnterCriticalSection
0x180012475  nop     dword ptr [rax+rax+00h]
0x18001247a  mov     r9d, r14d; unsigned int
0x18001247d  lea     r8, aStatus; "Status"
0x180012484  mov     rdx, rsi; unsigned __int16 *
0x180012487  mov     r14, [rbp+47h+var_B8]
0x18001248b  mov     rcx, r14; HKEY
0x18001248e  call    ?WriteRegDWORDValue@@YAJPEAUHKEY__@@PEBG1KPEAU_SECURITY_ATTRIBUTES@@@Z; WriteRegDWORDValue(HKEY__ *,ushort const *,ushort const *,ulong,_SECURITY_ATTRIBUTES *)
0x180012493  mov     ebx, eax
0x180012495  test    eax, eax
0x180012497  jns     short loc_1800124DF
0x180012499  mov     rcx, cs:WPP_GLOBAL_Control
0x1800124a0  lea     rsi, WPP_GLOBAL_Control
0x1800124a7  cmp     rcx, rsi
0x1800124aa  jz      loc_1800125C7
0x1800124b0  test    byte ptr [rcx+1Ch], 4
0x1800124b4  jz      loc_1800125C7
0x1800124ba  mov     edx, 5Bh ; '['
0x1800124bf  lea     r9, aStatus; "Status"
0x1800124c6  mov     [rsp+0F0h+var_D0], eax
0x1800124ca  lea     r8, WPP_9f155fbe94773387205a22e9edb85311_Traceguids
0x1800124d1  mov     rcx, [rcx+10h]
0x1800124d5  call    WPP_SF_Sd
0x1800124da  jmp     loc_1800125C7
0x1800124df  mov     r9d, r12d; unsigned int
0x1800124e2  lea     r8, aProgress; "Progress"
0x1800124e9  mov     rdx, rsi; unsigned __int16 *
0x1800124ec  mov     rcx, r14; HKEY
0x1800124ef  call    ?WriteRegDWORDValue@@YAJPEAUHKEY__@@PEBG1KPEAU_SECURITY_ATTRIBUTES@@@Z; WriteRegDWORDValue(HKEY__ *,ushort const *,ushort const *,ulong,_SECURITY_ATTRIBUTES *)
0x1800124f4  mov     ebx, eax
0x1800124f6  test    eax, eax
0x1800124f8  jns     short loc_180012529
0x1800124fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180012501  lea     rsi, WPP_GLOBAL_Control
0x180012508  cmp     rcx, rsi
0x18001250b  jz      loc_1800125C7
0x180012511  test    byte ptr [rcx+1Ch], 4
0x180012515  jz      loc_1800125C7
0x18001251b  mov     edx, 5Ch ; '\'
0x180012520  lea     r9, aProgress; "Progress"
0x180012527  jmp     short loc_1800124C6
0x180012529  mov     r9d, [rbp+47h+arg_20]; unsigned int
0x18001252d  lea     r8, aLasterror; "LastError"
0x180012534  mov     rdx, rsi; unsigned __int16 *
0x180012537  mov     rcx, r14; HKEY
0x18001253a  call    ?WriteRegDWORDValue@@YAJPEAUHKEY__@@PEBG1KPEAU_SECURITY_ATTRIBUTES@@@Z; WriteRegDWORDValue(HKEY__ *,ushort const *,ushort const *,ulong,_SECURITY_ATTRIBUTES *)
0x18001253f  mov     ebx, eax
0x180012541  test    eax, eax
0x180012543  jns     short loc_18001256F
0x180012545  mov     rcx, cs:WPP_GLOBAL_Control
0x18001254c  lea     rsi, WPP_GLOBAL_Control
0x180012553  cmp     rcx, rsi
0x180012556  jz      short loc_1800125C7
0x180012558  test    byte ptr [rcx+1Ch], 4
0x18001255c  jz      short loc_1800125C7
0x18001255e  mov     edx, 5Dh ; ']'
0x180012563  lea     r9, aLasterror; "LastError"
0x18001256a  jmp     loc_1800124C6
0x18001256f  cmp     qword ptr [r15+18h], 8
0x180012574  jb      short loc_18001257B
0x180012576  mov     r9, [r15]
0x180012579  jmp     short loc_18001257E
0x18001257b  mov     r9, r15; unsigned __int16 *
0x18001257e  lea     r8, aLasterrordesc; "LastErrorDesc"
0x180012585  mov     rdx, rsi; unsigned __int16 *
0x180012588  mov     rcx, r14; HKEY
0x18001258b  call    ?WriteRegSZValue@@YAJPEAUHKEY__@@PEBG11PEAU_SECURITY_ATTRIBUTES@@H@Z; WriteRegSZValue(HKEY__ *,ushort const *,ushort const *,ushort const *,_SECURITY_ATTRIBUTES *,int)
0x180012590  mov     ebx, eax
0x180012592  test    eax, eax
0x180012594  jns     short loc_1800125C0
0x180012596  mov     rcx, cs:WPP_GLOBAL_Control
0x18001259d  lea     rsi, WPP_GLOBAL_Control
0x1800125a4  cmp     rcx, rsi
0x1800125a7  jz      short loc_1800125C7
0x1800125a9  test    byte ptr [rcx+1Ch], 4
0x1800125ad  jz      short loc_1800125C7
0x1800125af  mov     edx, 5Eh ; '^'
0x1800125b4  lea     r9, aLasterrordesc; "LastErrorDesc"
0x1800125bb  jmp     loc_1800124C6
0x1800125c0  lea     rsi, WPP_GLOBAL_Control
0x1800125c7  mov     r14d, dword ptr [rbp+47h+var_C0]
0x1800125cb  lea     rcx, [r13+80h]; lpCriticalSection
0x1800125d2  call    cs:__imp_LeaveCriticalSection
0x1800125d9  nop     dword ptr [rax+rax+00h]
0x1800125de  test    ebx, ebx
0x1800125e0  jns     short loc_180012622
0x1800125e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800125e9  cmp     rcx, rsi
0x1800125ec  jz      short loc_180012622
0x1800125ee  test    byte ptr [rcx+1Ch], 4
0x1800125f2  jz      short loc_180012622
0x1800125f4  cmp     qword ptr [rdi+18h], 8
0x1800125f9  jb      short loc_180012600
0x1800125fb  mov     r9, [rdi]
0x1800125fe  jmp     short loc_180012603
0x180012600  mov     r9, rdi
0x180012603  mov     edx, 5Fh ; '_'
0x180012608  mov     [rsp+0F0h+var_C8], ebx
0x18001260c  mov     [rsp+0F0h+var_D0], r14d
0x180012611  lea     r8, WPP_9f155fbe94773387205a22e9edb85311_Traceguids
0x180012618  mov     rcx, [rcx+10h]
0x18001261c  call    WPP_SF_SdD
0x180012621  nop
0x180012622  lea     rcx, [rbp+47h+phkResult]; this
0x180012626  call    ??1CurrentUserRegKeyHelper@@QEAA@XZ; CurrentUserRegKeyHelper::~CurrentUserRegKeyHelper(void)
0x18001262b  nop
0x18001262c  xor     r8d, r8d
0x18001262f  mov     dl, 1
0x180012631  lea     rcx, [rbp+47h+var_70]
0x180012635  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001263a  nop
0x18001263b  xor     r8d, r8d
0x18001263e  mov     dl, 1
0x180012640  mov     rcx, rdi
0x180012643  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180012648  nop
0x180012649  xor     r8d, r8d
0x18001264c  mov     dl, 1
0x18001264e  mov     rcx, r15
0x180012651  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180012656  mov     eax, ebx
0x180012658  mov     rcx, [rbp+47h+var_50]
0x18001265c  xor     rcx, rsp; StackCookie
0x18001265f  call    __security_check_cookie
0x180012664  add     rsp, 0B8h
0x18001266b  pop     r15
0x18001266d  pop     r14
0x18001266f  pop     r13
0x180012671  pop     r12
0x180012673  pop     rdi
0x180012674  pop     rsi
0x180012675  pop     rbx
0x180012676  pop     rbp
0x180012677  retn
```
