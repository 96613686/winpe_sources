# JobHelper::UpdateContentLocation(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x180011398`
- end: `0x18001156d`
- name: `?UpdateContentLocation@JobHelper@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `469`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
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
- `0x18000bae8`
- `0x18000f924`
- `0x18000fdf8`
- `0x180011398`
- `0x18001f420`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18001143f`
- `KERNEL32!EnterCriticalSection` at `0x18001143f`
- `KERNEL32!LeaveCriticalSection` at `0x18001150f`
- `KERNEL32!LeaveCriticalSection` at `0x18001150f`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall JobHelper::UpdateContentLocation(__int64 a1, __int64 a2, __int64 a3)
{
  LSTATUS Key; // eax
  unsigned int v7; // esi
  struct _RTL_CRITICAL_SECTION *v8; // rbx
  __int64 v9; // rax
  int JobRegPath; // eax
  LPCWSTR v11; // rcx
  const unsigned __int16 *v12; // r9
  int v13; // edx
  const BYTE *v14; // r9
  const unsigned __int16 *v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // rdx
  HKEY v20; // [rsp+30h] [rbp-39h] BYREF
  HKEY phkResult[2]; // [rsp+38h] [rbp-31h] BYREF
  _BYTE v22[32]; // [rsp+48h] [rbp-21h] BYREF
  __int64 v23; // [rsp+68h] [rbp-1h]
  __int64 v24; // [rsp+70h] [rbp+7h]
  unsigned __int16 *v25[4]; // [rsp+78h] [rbp+Fh] BYREF

  v23 = a2;
  v24 = a3;
  std::wstring::wstring(v25, &dword_180022F6C);
  phkResult[0] = 0;
  v20 = 0;
  Key = CurrentUserRegKeyHelper::GetKey(phkResult, &v20);
  v7 = Key;
  if ( Key < 0 )
  {
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        101,
        &WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
        (unsigned int)Key);
    v8 = (struct _RTL_CRITICAL_SECTION *)(a1 + 128);
    goto LABEL_23;
  }
  v8 = (struct _RTL_CRITICAL_SECTION *)(a1 + 128);
  EnterCriticalSection(v8);
  v9 = std::wstring::wstring(v22, a2);
  JobRegPath = JobHelper::GetJobRegPath(v9, (__int64)v25);
  v7 = JobRegPath;
  if ( JobRegPath < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
      goto LABEL_23;
    if ( *(_QWORD *)(a2 + 24) < 8u )
      LODWORD(v12) = a2;
    else
      v12 = *(const unsigned __int16 **)a2;
    v13 = 102;
LABEL_22:
    WPP_SF_Sd(
      *((_QWORD *)v11 + 2),
      v13,
      (unsigned int)&WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
      (_DWORD)v12,
      JobRegPath);
    goto LABEL_23;
  }
  if ( *(_QWORD *)(a3 + 24) < 8u )
    v14 = (const BYTE *)a3;
  else
    v14 = *(const BYTE **)a3;
  v15 = (const unsigned __int16 *)v25;
  if ( v25[3] >= (unsigned __int16 *)8 )
    v15 = v25[0];
  JobRegPath = WriteRegSZValue(v20, v15, L"ContentLocation", v14);
  v7 = JobRegPath;
  if ( JobRegPath < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    {
      v13 = 103;
      v12 = L"ContentLocation";
      goto LABEL_22;
    }
  }
LABEL_23:
  LeaveCriticalSection(v8);
  CurrentUserRegKeyHelper::~CurrentUserRegKeyHelper((CurrentUserRegKeyHelper *)phkResult);
  LOBYTE(v16) = 1;
  std::wstring::_Tidy(v25, v16, 0);
  LOBYTE(v17) = 1;
  std::wstring::_Tidy(a2, v17, 0);
  LOBYTE(v18) = 1;
  std::wstring::_Tidy(a3, v18, 0);
  return v7;
}

```

## disassembly

```asm
0x180011398  push    rbp
0x18001139a  push    rbx
0x18001139b  push    rsi
0x18001139c  push    rdi
0x18001139d  push    r14
0x18001139f  lea     rbp, [rsp-37h]
0x1800113a4  sub     rsp, 0A0h
0x1800113ab  mov     rax, cs:__security_cookie
0x1800113b2  xor     rax, rsp
0x1800113b5  mov     [rbp+57h+var_28], rax
0x1800113b9  mov     r14, r8
0x1800113bc  mov     rdi, rdx
0x1800113bf  mov     rbx, rcx
0x1800113c2  mov     [rbp+57h+var_58], rdx
0x1800113c6  mov     [rbp+57h+var_50], r8
0x1800113ca  lea     rdx, dword_180022F6C
0x1800113d1  lea     rcx, [rbp+57h+var_48]
0x1800113d5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800113da  nop
0x1800113db  mov     [rbp+57h+phkResult], 0
0x1800113e3  mov     [rbp+57h+var_90], 0
0x1800113eb  lea     rdx, [rbp+57h+var_90]; HKEY *
0x1800113ef  lea     rcx, [rbp+57h+phkResult]; phkResult
0x1800113f3  call    ?GetKey@CurrentUserRegKeyHelper@@QEAAJAEAPEAUHKEY__@@@Z; CurrentUserRegKeyHelper::GetKey(HKEY__ * &)
0x1800113f8  mov     esi, eax
0x1800113fa  test    eax, eax
0x1800113fc  jns     short loc_180011438
0x1800113fe  lea     rdx, WPP_GLOBAL_Control
0x180011405  mov     rcx, cs:WPP_GLOBAL_Control
0x18001140c  cmp     rcx, rdx
0x18001140f  jz      short loc_18001142F
0x180011411  test    byte ptr [rcx+1Ch], 4
0x180011415  jz      short loc_18001142F
0x180011417  mov     edx, 65h ; 'e'
0x18001141c  mov     r9d, eax
0x18001141f  lea     r8, WPP_9f155fbe94773387205a22e9edb85311_Traceguids
0x180011426  mov     rcx, [rcx+10h]
0x18001142a  call    WPP_SF_d
0x18001142f  sub     rbx, 0FFFFFFFFFFFFFF80h
0x180011433  jmp     loc_18001150C
0x180011438  sub     rbx, 0FFFFFFFFFFFFFF80h
0x18001143c  mov     rcx, rbx; lpCriticalSection
0x18001143f  call    cs:__imp_EnterCriticalSection
0x180011446  nop     dword ptr [rax+rax+00h]
0x18001144b  mov     rdx, rdi
0x18001144e  lea     rcx, [rbp+57h+var_78]
0x180011452  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180011457  lea     rdx, [rbp+57h+var_48]
0x18001145b  mov     rcx, rax
0x18001145e  call    ?GetJobRegPath@JobHelper@@CAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z; JobHelper::GetJobRegPath(std::wstring,std::wstring &)
0x180011463  mov     esi, eax
0x180011465  test    eax, eax
0x180011467  jns     short loc_1800114A0
0x180011469  lea     rdx, WPP_GLOBAL_Control
0x180011470  mov     rcx, cs:WPP_GLOBAL_Control
0x180011477  cmp     rcx, rdx
0x18001147a  jz      loc_18001150C
0x180011480  test    byte ptr [rcx+1Ch], 4
0x180011484  jz      loc_18001150C
0x18001148a  cmp     qword ptr [rdi+18h], 8
0x18001148f  jb      short loc_180011496
0x180011491  mov     r9, [rdi]
0x180011494  jmp     short loc_180011499
0x180011496  mov     r9, rdi
0x180011499  mov     edx, 66h ; 'f'
0x18001149e  jmp     short loc_1800114F8
0x1800114a0  cmp     qword ptr [r14+18h], 8
0x1800114a5  jb      short loc_1800114AC
0x1800114a7  mov     r9, [r14]
0x1800114aa  jmp     short loc_1800114AF
0x1800114ac  mov     r9, r14; unsigned __int16 *
0x1800114af  lea     rdx, [rbp+57h+var_48]
0x1800114b3  cmp     [rbp+57h+var_30], 8
0x1800114b8  cmovnb  rdx, [rbp+57h+var_48]; unsigned __int16 *
0x1800114bd  lea     r8, aContentlocatio; "ContentLocation"
0x1800114c4  mov     rcx, [rbp+57h+var_90]; HKEY
0x1800114c8  call    ?WriteRegSZValue@@YAJPEAUHKEY__@@PEBG11PEAU_SECURITY_ATTRIBUTES@@H@Z; WriteRegSZValue(HKEY__ *,ushort const *,ushort const *,ushort const *,_SECURITY_ATTRIBUTES *,int)
0x1800114cd  mov     esi, eax
0x1800114cf  test    eax, eax
0x1800114d1  jns     short loc_18001150C
0x1800114d3  lea     rdx, WPP_GLOBAL_Control
0x1800114da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800114e1  cmp     rcx, rdx
0x1800114e4  jz      short loc_18001150C
0x1800114e6  test    byte ptr [rcx+1Ch], 4
0x1800114ea  jz      short loc_18001150C
0x1800114ec  mov     edx, 67h ; 'g'
0x1800114f1  lea     r9, aContentlocatio; "ContentLocation"
0x1800114f8  mov     [rsp+0C0h+var_A0], eax
0x1800114fc  lea     r8, WPP_9f155fbe94773387205a22e9edb85311_Traceguids
0x180011503  mov     rcx, [rcx+10h]
0x180011507  call    WPP_SF_Sd
0x18001150c  mov     rcx, rbx; lpCriticalSection
0x18001150f  call    cs:__imp_LeaveCriticalSection
0x180011516  nop     dword ptr [rax+rax+00h]
0x18001151b  nop
0x18001151c  lea     rcx, [rbp+57h+phkResult]; this
0x180011520  call    ??1CurrentUserRegKeyHelper@@QEAA@XZ; CurrentUserRegKeyHelper::~CurrentUserRegKeyHelper(void)
0x180011525  nop
0x180011526  xor     r8d, r8d
0x180011529  mov     dl, 1
0x18001152b  lea     rcx, [rbp+57h+var_48]
0x18001152f  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180011534  nop
0x180011535  xor     r8d, r8d
0x180011538  mov     dl, 1
0x18001153a  mov     rcx, rdi
0x18001153d  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180011542  nop
0x180011543  xor     r8d, r8d
0x180011546  mov     dl, 1
0x180011548  mov     rcx, r14
0x18001154b  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180011550  mov     eax, esi
0x180011552  mov     rcx, [rbp+57h+var_28]
0x180011556  xor     rcx, rsp; StackCookie
0x180011559  call    __security_check_cookie
0x18001155e  add     rsp, 0A0h
0x180011565  pop     r14
0x180011567  pop     rdi
0x180011568  pop     rsi
0x180011569  pop     rbx
0x18001156a  pop     rbp
0x18001156b  retn
```
