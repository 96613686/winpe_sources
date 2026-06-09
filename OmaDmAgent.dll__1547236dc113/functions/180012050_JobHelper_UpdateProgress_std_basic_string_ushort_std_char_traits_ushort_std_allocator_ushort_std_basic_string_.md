# JobHelper::UpdateProgress(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,DependencyStatus,ulong,ulong,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x180012050`
- end: `0x180012331`
- name: `?UpdateProgress@JobHelper@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0W4DependencyStatus@@KK0@Z`
- size: `737`
- prototype: ``
- caller_count: `3`
- callee_count: `13`
- tags: `installer_update`

## callers

- `0x18000ccb4`
- `0x180013330`
- `0x180014680`

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
- `0x180012050`
- `0x18001f420`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18001210c`
- `KERNEL32!EnterCriticalSection` at `0x18001210c`
- `KERNEL32!LeaveCriticalSection` at `0x1800122be`
- `KERNEL32!LeaveCriticalSection` at `0x1800122be`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall JobHelper::UpdateProgress(
        __int64 a1,
        _QWORD *a2,
        __int64 *a3,
        int a4,
        __int64 a5,
        unsigned int a6,
        unsigned __int16 *a7)
{
  LSTATUS Key; // eax
  int JobDependencyRegPath; // ebx
  struct _RTL_CRITICAL_SECTION *v13; // rdi
  __int64 v14; // rbx
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // r9
  const unsigned __int16 *v18; // rsi
  int v19; // r9d
  HKEY v20; // r13
  int v21; // eax
  LPCWSTR v22; // rcx
  int v23; // edx
  const unsigned __int16 *v24; // r9
  const BYTE *v25; // r9
  __int64 v26; // rdx
  __int64 v27; // rdx
  __int64 v28; // rdx
  __int64 v29; // rdx
  HKEY v31; // [rsp+30h] [rbp-A1h] BYREF
  HKEY phkResult[3]; // [rsp+38h] [rbp-99h] BYREF
  _BYTE v33[32]; // [rsp+50h] [rbp-81h] BYREF
  _BYTE v34[32]; // [rsp+70h] [rbp-61h] BYREF
  _QWORD *v35; // [rsp+90h] [rbp-41h]
  __int64 *v36; // [rsp+98h] [rbp-39h]
  unsigned __int16 *v37; // [rsp+A0h] [rbp-31h]
  unsigned __int16 *v38[4]; // [rsp+A8h] [rbp-29h] BYREF

  v35 = a2;
  v36 = a3;
  v37 = a7;
  std::wstring::wstring(v38, &dword_180022F6C);
  phkResult[0] = 0;
  v31 = 0;
  Key = CurrentUserRegKeyHelper::GetKey(phkResult, &v31);
  JobDependencyRegPath = Key;
  if ( Key >= 0 )
  {
    v13 = (struct _RTL_CRITICAL_SECTION *)(a1 + 128);
    EnterCriticalSection(v13);
    phkResult[1] = (HKEY)v33;
    v14 = std::wstring::wstring(v33, a3);
    v15 = std::wstring::wstring(v34, a2);
    JobDependencyRegPath = JobHelper::GetJobDependencyRegPath(v15, v14, v38);
    if ( JobDependencyRegPath >= 0 )
    {
      v18 = (const unsigned __int16 *)v38;
      if ( v38[3] >= (unsigned __int16 *)8 )
        v18 = v38[0];
      v19 = a4;
      v20 = v31;
      v21 = WriteRegDWORDValue(v31, v18, L"Status", v19);
      JobDependencyRegPath = v21;
      if ( v21 >= 0 )
      {
        v21 = WriteRegDWORDValue(v20, v18, L"LastError", a6);
        JobDependencyRegPath = v21;
        if ( v21 >= 0 )
        {
          if ( *((_QWORD *)a7 + 3) < 8u )
            v25 = (const BYTE *)a7;
          else
            v25 = *(const BYTE **)a7;
          v21 = WriteRegSZValue(v20, v18, L"LastErrorDesc", v25);
          JobDependencyRegPath = v21;
          if ( v21 >= 0 )
            goto LABEL_34;
          v22 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
            goto LABEL_34;
          v23 = 100;
          v24 = L"LastErrorDesc";
        }
        else
        {
          v22 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
            goto LABEL_34;
          v23 = 99;
          v24 = L"LastError";
        }
      }
      else
      {
        v22 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
          goto LABEL_34;
        v23 = 98;
        v24 = L"Status";
      }
      WPP_SF_Sd(
        *((_QWORD *)v22 + 2),
        v23,
        (unsigned int)&WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
        (_DWORD)v24,
        v21);
      goto LABEL_34;
    }
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    {
      if ( (unsigned __int64)a3[3] < 8 )
        v16 = (__int64)a3;
      else
        v16 = *a3;
      if ( a2[3] < 8u )
        LODWORD(v17) = (_DWORD)a2;
      else
        v17 = *a2;
      WPP_SF_SSD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        97,
        (unsigned int)&WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
        v17,
        v16,
        JobDependencyRegPath);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        96,
        &WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
        (unsigned int)Key);
    v13 = (struct _RTL_CRITICAL_SECTION *)(a1 + 128);
  }
LABEL_34:
  LeaveCriticalSection(v13);
  CurrentUserRegKeyHelper::~CurrentUserRegKeyHelper((CurrentUserRegKeyHelper *)phkResult);
  LOBYTE(v26) = 1;
  std::wstring::_Tidy(v38, v26, 0);
  LOBYTE(v27) = 1;
  std::wstring::_Tidy(a2, v27, 0);
  LOBYTE(v28) = 1;
  std::wstring::_Tidy(a3, v28, 0);
  LOBYTE(v29) = 1;
  std::wstring::_Tidy(a7, v29, 0);
  return (unsigned int)JobDependencyRegPath;
}

```

## disassembly

```asm
0x180012050  push    rbp
0x180012052  push    rbx
0x180012053  push    rsi
0x180012054  push    rdi
0x180012055  push    r12
0x180012057  push    r13
0x180012059  push    r14
0x18001205b  push    r15
0x18001205d  lea     rbp, [rsp-7]
0x180012062  sub     rsp, 0D8h
0x180012069  mov     rax, cs:__security_cookie
0x180012070  xor     rax, rsp
0x180012073  mov     [rbp+3Fh+var_48], rax
0x180012077  mov     r13d, r9d
0x18001207a  mov     r14, r8
0x18001207d  mov     r15, rdx
0x180012080  mov     rdi, rcx
0x180012083  mov     [rbp+3Fh+var_80], rdx
0x180012087  mov     [rbp+3Fh+var_78], r8
0x18001208b  mov     r12, [rbp+3Fh+arg_30]
0x18001208f  mov     [rbp+3Fh+var_70], r12
0x180012093  lea     rdx, dword_180022F6C
0x18001209a  lea     rcx, [rbp+3Fh+var_68]
0x18001209e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800120a3  nop
0x1800120a4  mov     [rsp+110h+phkResult], 0
0x1800120ad  mov     [rsp+110h+var_E0], 0
0x1800120b6  lea     rdx, [rsp+110h+var_E0]; HKEY *
0x1800120bb  lea     rcx, [rsp+110h+phkResult]; phkResult
0x1800120c0  call    ?GetKey@CurrentUserRegKeyHelper@@QEAAJAEAPEAUHKEY__@@@Z; CurrentUserRegKeyHelper::GetKey(HKEY__ * &)
0x1800120c5  mov     ebx, eax
0x1800120c7  test    eax, eax
0x1800120c9  jns     short loc_180012105
0x1800120cb  lea     rdx, WPP_GLOBAL_Control
0x1800120d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800120d9  cmp     rcx, rdx
0x1800120dc  jz      short loc_1800120FC
0x1800120de  test    byte ptr [rcx+1Ch], 4
0x1800120e2  jz      short loc_1800120FC
0x1800120e4  mov     edx, 60h ; '`'
0x1800120e9  mov     r9d, eax
0x1800120ec  lea     r8, WPP_9f155fbe94773387205a22e9edb85311_Traceguids
0x1800120f3  mov     rcx, [rcx+10h]
0x1800120f7  call    WPP_SF_d
0x1800120fc  sub     rdi, 0FFFFFFFFFFFFFF80h
0x180012100  jmp     loc_1800122BB
0x180012105  sub     rdi, 0FFFFFFFFFFFFFF80h
0x180012109  mov     rcx, rdi; lpCriticalSection
0x18001210c  call    cs:__imp_EnterCriticalSection
0x180012113  nop     dword ptr [rax+rax+00h]
0x180012118  lea     rax, [rsp+110h+var_C0]
0x18001211d  mov     [rsp+110h+var_D0], rax
0x180012122  mov     rdx, r14
0x180012125  lea     rcx, [rsp+110h+var_C0]
0x18001212a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001212f  mov     rbx, rax
0x180012132  mov     rdx, r15
0x180012135  lea     rcx, [rbp+3Fh+var_A0]
0x180012139  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001213e  nop
0x18001213f  lea     r8, [rbp+3Fh+var_68]
0x180012143  mov     rdx, rbx
0x180012146  mov     rcx, rax
0x180012149  call    ?GetJobDependencyRegPath@JobHelper@@CAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAV23@@Z; JobHelper::GetJobDependencyRegPath(std::wstring,std::wstring,std::wstring &)
0x18001214e  mov     ebx, eax
0x180012150  test    eax, eax
0x180012152  jns     short loc_1800121B6
0x180012154  lea     rdx, WPP_GLOBAL_Control
0x18001215b  mov     rcx, cs:WPP_GLOBAL_Control
0x180012162  cmp     rcx, rdx
0x180012165  jz      loc_1800122BB
0x18001216b  test    byte ptr [rcx+1Ch], 4
0x18001216f  jz      loc_1800122BB
0x180012175  cmp     qword ptr [r14+18h], 8
0x18001217a  jb      short loc_180012181
0x18001217c  mov     rax, [r14]
0x18001217f  jmp     short loc_180012184
0x180012181  mov     rax, r14
0x180012184  cmp     qword ptr [r15+18h], 8
0x180012189  jb      short loc_180012190
0x18001218b  mov     r9, [r15]
0x18001218e  jmp     short loc_180012193
0x180012190  mov     r9, r15
0x180012193  mov     edx, 61h ; 'a'
0x180012198  mov     [rsp+110h+var_E8], ebx
0x18001219c  mov     [rsp+110h+var_F0], rax
0x1800121a1  lea     r8, WPP_9f155fbe94773387205a22e9edb85311_Traceguids
0x1800121a8  mov     rcx, [rcx+10h]
0x1800121ac  call    WPP_SF_SSD
0x1800121b1  jmp     loc_1800122BB
0x1800121b6  lea     rsi, [rbp+3Fh+var_68]
0x1800121ba  cmp     [rbp+3Fh+var_50], 8
0x1800121bf  cmovnb  rsi, [rbp+3Fh+var_68]
0x1800121c4  mov     r9d, r13d; unsigned int
0x1800121c7  lea     r8, aStatus; "Status"
0x1800121ce  mov     rdx, rsi; unsigned __int16 *
0x1800121d1  mov     r13, [rsp+110h+var_E0]
0x1800121d6  mov     rcx, r13; HKEY
0x1800121d9  call    ?WriteRegDWORDValue@@YAJPEAUHKEY__@@PEBG1KPEAU_SECURITY_ATTRIBUTES@@@Z; WriteRegDWORDValue(HKEY__ *,ushort const *,ushort const *,ulong,_SECURITY_ATTRIBUTES *)
0x1800121de  mov     ebx, eax
0x1800121e0  test    eax, eax
0x1800121e2  jns     short loc_180012216
0x1800121e4  lea     rdx, WPP_GLOBAL_Control
0x1800121eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800121f2  cmp     rcx, rdx
0x1800121f5  jz      loc_1800122BB
0x1800121fb  test    byte ptr [rcx+1Ch], 4
0x1800121ff  jz      loc_1800122BB
0x180012205  mov     edx, 62h ; 'b'
0x18001220a  lea     r9, aStatus; "Status"
0x180012211  jmp     loc_1800122A7
0x180012216  mov     r9d, [rbp+3Fh+arg_28]; unsigned int
0x18001221a  lea     r8, aLasterror; "LastError"
0x180012221  mov     rdx, rsi; unsigned __int16 *
0x180012224  mov     rcx, r13; HKEY
0x180012227  call    ?WriteRegDWORDValue@@YAJPEAUHKEY__@@PEBG1KPEAU_SECURITY_ATTRIBUTES@@@Z; WriteRegDWORDValue(HKEY__ *,ushort const *,ushort const *,ulong,_SECURITY_ATTRIBUTES *)
0x18001222c  mov     ebx, eax
0x18001222e  test    eax, eax
0x180012230  jns     short loc_180012259
0x180012232  lea     rdx, WPP_GLOBAL_Control
0x180012239  mov     rcx, cs:WPP_GLOBAL_Control
0x180012240  cmp     rcx, rdx
0x180012243  jz      short loc_1800122BB
0x180012245  test    byte ptr [rcx+1Ch], 4
0x180012249  jz      short loc_1800122BB
0x18001224b  mov     edx, 63h ; 'c'
0x180012250  lea     r9, aLasterror; "LastError"
0x180012257  jmp     short loc_1800122A7
0x180012259  cmp     qword ptr [r12+18h], 8
0x18001225f  jb      short loc_180012267
0x180012261  mov     r9, [r12]
0x180012265  jmp     short loc_18001226A
0x180012267  mov     r9, r12; unsigned __int16 *
0x18001226a  lea     r8, aLasterrordesc; "LastErrorDesc"
0x180012271  mov     rdx, rsi; unsigned __int16 *
0x180012274  mov     rcx, r13; HKEY
0x180012277  call    ?WriteRegSZValue@@YAJPEAUHKEY__@@PEBG11PEAU_SECURITY_ATTRIBUTES@@H@Z; WriteRegSZValue(HKEY__ *,ushort const *,ushort const *,ushort const *,_SECURITY_ATTRIBUTES *,int)
0x18001227c  mov     ebx, eax
0x18001227e  test    eax, eax
0x180012280  jns     short loc_1800122BB
0x180012282  lea     rdx, WPP_GLOBAL_Control
0x180012289  mov     rcx, cs:WPP_GLOBAL_Control
0x180012290  cmp     rcx, rdx
0x180012293  jz      short loc_1800122BB
0x180012295  test    byte ptr [rcx+1Ch], 4
0x180012299  jz      short loc_1800122BB
0x18001229b  mov     edx, 64h ; 'd'
0x1800122a0  lea     r9, aLasterrordesc; "LastErrorDesc"
0x1800122a7  mov     dword ptr [rsp+110h+var_F0], eax
0x1800122ab  lea     r8, WPP_9f155fbe94773387205a22e9edb85311_Traceguids
0x1800122b2  mov     rcx, [rcx+10h]
0x1800122b6  call    WPP_SF_Sd
0x1800122bb  mov     rcx, rdi; lpCriticalSection
0x1800122be  call    cs:__imp_LeaveCriticalSection
0x1800122c5  nop     dword ptr [rax+rax+00h]
0x1800122ca  nop
0x1800122cb  lea     rcx, [rsp+110h+phkResult]; this
0x1800122d0  call    ??1CurrentUserRegKeyHelper@@QEAA@XZ; CurrentUserRegKeyHelper::~CurrentUserRegKeyHelper(void)
0x1800122d5  nop
0x1800122d6  xor     r8d, r8d
0x1800122d9  mov     dl, 1
0x1800122db  lea     rcx, [rbp+3Fh+var_68]
0x1800122df  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800122e4  nop
0x1800122e5  xor     r8d, r8d
0x1800122e8  mov     dl, 1
0x1800122ea  mov     rcx, r15
0x1800122ed  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800122f2  nop
0x1800122f3  xor     r8d, r8d
0x1800122f6  mov     dl, 1
0x1800122f8  mov     rcx, r14
0x1800122fb  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180012300  nop
0x180012301  xor     r8d, r8d
0x180012304  mov     dl, 1
0x180012306  mov     rcx, r12
0x180012309  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001230e  mov     eax, ebx
0x180012310  mov     rcx, [rbp+3Fh+var_48]
0x180012314  xor     rcx, rsp; StackCookie
0x180012317  call    __security_check_cookie
0x18001231c  add     rsp, 0D8h
0x180012323  pop     r15
0x180012325  pop     r14
0x180012327  pop     r13
0x180012329  pop     r12
0x18001232b  pop     rdi
0x18001232c  pop     rsi
0x18001232d  pop     rbx
0x18001232e  pop     rbp
0x18001232f  retn
```
