# CRegistrySearch::SearchAndBuildList(CHString,CHPtrArray &,CHString,CHString,int,HKEY__ *)

- ea: `0x140013510`
- end: `0x140013797`
- name: `?SearchAndBuildList@CRegistrySearch@@QEAAHVCHString@@AEAVCHPtrArray@@00HPEAUHKEY__@@@Z`
- size: `647`
- prototype: `__int64 __fastcall(__int64, WCHAR **, int *, unsigned __int16 **, unsigned __int16 **, int, HKEY)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x140013510`

## callees

- `0x14000fc80`
- `0x14000fe30`
- `0x14000ff40`
- `0x14000ffc0`
- `0x140010230`
- `0x140011be0`
- `0x140011cc0`
- `0x140011ee0`
- `0x140012c70`
- `0x140013180`
- `0x1400131d0`
- `0x140013510`
- `0x140014ad0`

## pseudocode

```c
__int64 __fastcall CRegistrySearch::SearchAndBuildList(
        __int64 a1,
        WCHAR **a2,
        int *a3,
        unsigned __int16 **a4,
        unsigned __int16 **a5,
        int a6,
        HKEY a7)
{
  unsigned int v9; // ebx
  const unsigned __int16 **v10; // rax
  const unsigned __int16 **v11; // rsi
  const wchar_t **v12; // rdi
  const unsigned __int16 **v13; // rbx
  CHString *v14; // rax
  CHString *v15; // rdi
  CHString *v16; // rbx
  CHString *v17; // rax
  unsigned __int16 *v19; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v20; // [rsp+48h] [rbp-B8h] BYREF
  int *v21; // [rsp+50h] [rbp-B0h]
  const unsigned __int16 *v22; // [rsp+58h] [rbp-A8h] BYREF
  const unsigned __int16 *v23; // [rsp+60h] [rbp-A0h] BYREF
  const unsigned __int16 *v24; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v25[8]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v26[8]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v27[8]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v28[8]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v29; // [rsp+90h] [rbp-70h]
  _BYTE v30[8]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v31[8]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v32[8]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE *v33; // [rsp+B0h] [rbp-50h]
  _BYTE *v34; // [rsp+B8h] [rbp-48h]
  _BYTE *v35; // [rsp+C0h] [rbp-40h]
  WCHAR **v36; // [rsp+C8h] [rbp-38h]
  unsigned __int16 **v37; // [rsp+D0h] [rbp-30h]
  unsigned __int16 **v38; // [rsp+D8h] [rbp-28h]
  _BYTE *v39; // [rsp+E0h] [rbp-20h]
  _BYTE v40[608]; // [rsp+F0h] [rbp-10h] BYREF

  v21 = a3;
  v29 = a1;
  v36 = a2;
  v37 = a4;
  v38 = a5;
  CRegistry::CRegistry((CRegistry *)v40);
  if ( CRegistry::Open((CRegistry *)v40, a7, *a2, 0x20019u) )
  {
    v9 = 0;
  }
  else
  {
    v19 = (unsigned __int16 *)afxPchNil;
    while ( !(unsigned int)CRegistry::GetCurrentSubKeyName((CRegistry *)v40, (struct CHString *)&v19) )
    {
      v20 = (unsigned __int16 *)afxPchNil;
      CHString::CHString((CHString *)&v22, L"\\");
      operator+((CHString *)&v24);
      v10 = (const unsigned __int16 **)operator+((CHString *)&v23);
      CHString::operator=((const unsigned __int16 **)&v20, v10);
      CHString::~CHString(&v23);
      CHString::~CHString(&v24);
      v39 = v25;
      v11 = (const unsigned __int16 **)CHString::CHString((CHString *)v25, a5);
      v33 = v26;
      v12 = (const wchar_t **)CHString::CHString((CHString *)v26, a4);
      v34 = v27;
      v13 = (const unsigned __int16 **)CHString::CHString((CHString *)v27, &v20);
      v14 = CHString::CHString((CHString *)v28, &v19);
      CRegistrySearch::CheckAndAddToList(v29, (CRegistry *)v40, v14, v13, v21, v12, v11, a6);
      CRegistry::NextSubKey((CRegistry *)v40);
      v35 = v30;
      v15 = CHString::CHString((CHString *)v30, a5);
      v34 = v31;
      v16 = CHString::CHString((CHString *)v31, a4);
      v17 = CHString::CHString((CHString *)v32, &v20);
      CRegistrySearch::SearchAndBuildList(v29, v17, v21, v16, v15, a6, -2147483646);
      CHString::~CHString(&v22);
      CHString::~CHString((const unsigned __int16 **)&v20);
    }
    CHString::~CHString((const unsigned __int16 **)&v19);
    v9 = 1;
  }
  CRegistry::~CRegistry((CRegistry *)v40);
  CHString::~CHString((const unsigned __int16 **)a2);
  CHString::~CHString((const unsigned __int16 **)a4);
  CHString::~CHString((const unsigned __int16 **)a5);
  return v9;
}

```

## disassembly

```asm
0x140013510  push    rbp
0x140013512  push    rbx
0x140013513  push    rsi
0x140013514  push    rdi
0x140013515  push    r12
0x140013517  push    r13
0x140013519  push    r14
0x14001351b  push    r15
0x14001351d  lea     rbp, [rsp-268h]
0x140013525  sub     rsp, 368h
0x14001352c  mov     rax, cs:__security_cookie
0x140013533  xor     rax, rsp
0x140013536  mov     [rbp+2A0h+var_50], rax
0x14001353d  mov     r15, r9
0x140013540  mov     [rsp+3A0h+var_350], r8
0x140013545  mov     r14, rdx
0x140013548  mov     [rbp+2A0h+var_310], rcx
0x14001354c  mov     [rbp+2A0h+var_2D8], rdx
0x140013550  mov     [rbp+2A0h+var_2D0], r9
0x140013554  mov     r12, [rbp+2A0h+arg_20]
0x14001355b  mov     [rbp+2A0h+var_2C8], r12
0x14001355f  mov     rbx, [rbp+2A0h+arg_30]
0x140013566  lea     rcx, [rbp+2A0h+var_2B0]; this
0x14001356a  call    ??0CRegistry@@QEAA@XZ; CRegistry::CRegistry(void)
0x14001356f  nop
0x140013570  mov     r9d, 20019h; unsigned int
0x140013576  mov     r8, [r14]; unsigned __int16 *
0x140013579  mov     rdx, rbx; HKEY
0x14001357c  lea     rcx, [rbp+2A0h+var_2B0]; this
0x140013580  call    ?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z; CRegistry::Open(HKEY__ *,ushort const *,ulong)
0x140013585  test    eax, eax
0x140013587  jz      short loc_140013590
0x140013589  xor     ebx, ebx
0x14001358b  jmp     loc_14001374E
0x140013590  mov     rax, cs:?afxPchNil@@3PEBGEB; ushort const * const afxPchNil
0x140013597  mov     [rsp+3A0h+var_360], rax
0x14001359c  lea     rdx, [rsp+3A0h+var_360]; struct CHString *
0x1400135a1  lea     rcx, [rbp+2A0h+var_2B0]; this
0x1400135a5  call    ?GetCurrentSubKeyName@CRegistry@@QEAAKAEAVCHString@@@Z; CRegistry::GetCurrentSubKeyName(CHString &)
0x1400135aa  test    eax, eax
0x1400135ac  jnz     loc_14001373F
0x1400135b2  mov     r13d, [rbp+2A0h+arg_28]
0x1400135b9  mov     rax, cs:?afxPchNil@@3PEBGEB; ushort const * const afxPchNil
0x1400135c0  mov     [rsp+3A0h+var_358], rax
0x1400135c5  lea     rdx, asc_14001A9B8; "\\"
0x1400135cc  lea     rcx, [rsp+3A0h+var_348]; this
0x1400135d1  call    ??0CHString@@QEAA@PEBG@Z; CHString::CHString(ushort const *)
0x1400135d6  nop
0x1400135d7  lea     r8, [rsp+3A0h+var_348]
0x1400135dc  mov     rdx, r14
0x1400135df  lea     rcx, [rsp+3A0h+var_338]; this
0x1400135e4  call    ??H@YA?AVCHString@@AEBV0@0@Z; operator+(CHString const &,CHString const &)
0x1400135e9  nop
0x1400135ea  lea     r8, [rsp+3A0h+var_360]
0x1400135ef  mov     rdx, rax
0x1400135f2  lea     rcx, [rsp+3A0h+var_340]; this
0x1400135f7  call    ??H@YA?AVCHString@@AEBV0@0@Z; operator+(CHString const &,CHString const &)
0x1400135fc  nop
0x1400135fd  mov     rdx, rax
0x140013600  lea     rcx, [rsp+3A0h+var_358]; this
0x140013605  call    ??4CHString@@QEAAAEBV0@AEBV0@@Z; CHString::operator=(CHString const &)
0x14001360a  nop
0x14001360b  lea     rcx, [rsp+3A0h+var_340]; this
0x140013610  call    ??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x140013615  nop
0x140013616  lea     rcx, [rsp+3A0h+var_338]; this
0x14001361b  call    ??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x140013620  lea     rax, [rsp+3A0h+var_330]
0x140013625  mov     [rbp+2A0h+var_2C0], rax
0x140013629  mov     rdx, r12; struct CHString *
0x14001362c  lea     rcx, [rsp+3A0h+var_330]; this
0x140013631  call    ??0CHString@@QEAA@AEBV0@@Z; CHString::CHString(CHString const &)
0x140013636  mov     rsi, rax
0x140013639  lea     rax, [rsp+3A0h+var_328]
0x14001363e  mov     [rbp+2A0h+var_2F0], rax
0x140013642  mov     rdx, r15; struct CHString *
0x140013645  lea     rcx, [rsp+3A0h+var_328]; this
0x14001364a  call    ??0CHString@@QEAA@AEBV0@@Z; CHString::CHString(CHString const &)
0x14001364f  mov     rdi, rax
0x140013652  lea     rax, [rbp+2A0h+var_320]
0x140013656  mov     [rbp+2A0h+var_2E8], rax
0x14001365a  lea     rdx, [rsp+3A0h+var_358]; struct CHString *
0x14001365f  lea     rcx, [rbp+2A0h+var_320]; this
0x140013663  call    ??0CHString@@QEAA@AEBV0@@Z; CHString::CHString(CHString const &)
0x140013668  mov     rbx, rax
0x14001366b  lea     rdx, [rsp+3A0h+var_360]; struct CHString *
0x140013670  lea     rcx, [rbp+2A0h+var_318]; this
0x140013674  call    ??0CHString@@QEAA@AEBV0@@Z; CHString::CHString(CHString const &)
0x140013679  nop
0x14001367a  mov     [rsp+3A0h+var_368], r13d
0x14001367f  mov     [rsp+3A0h+var_370], rsi
0x140013684  mov     [rsp+3A0h+var_378], rdi
0x140013689  mov     rcx, [rsp+3A0h+var_350]
0x14001368e  mov     [rsp+3A0h+var_380], rcx
0x140013693  mov     r9, rbx
0x140013696  mov     r8, rax
0x140013699  lea     rdx, [rbp+2A0h+var_2B0]
0x14001369d  mov     rcx, [rbp+2A0h+var_310]
0x1400136a1  call    ?CheckAndAddToList@CRegistrySearch@@AEAAXPEAVCRegistry@@VCHString@@1AEAVCHPtrArray@@11H@Z; CRegistrySearch::CheckAndAddToList(CRegistry *,CHString,CHString,CHPtrArray &,CHString,CHString,int)
0x1400136a6  lea     rcx, [rbp+2A0h+var_2B0]; this
0x1400136aa  call    ?NextSubKey@CRegistry@@QEAAKXZ; CRegistry::NextSubKey(void)
0x1400136af  lea     rax, [rbp+2A0h+var_308]
0x1400136b3  mov     [rbp+2A0h+var_2E0], rax
0x1400136b7  mov     rdx, r12; struct CHString *
0x1400136ba  lea     rcx, [rbp+2A0h+var_308]; this
0x1400136be  call    ??0CHString@@QEAA@AEBV0@@Z; CHString::CHString(CHString const &)
0x1400136c3  mov     rdi, rax
0x1400136c6  lea     rax, [rbp+2A0h+var_300]
0x1400136ca  mov     [rbp+2A0h+var_2E8], rax
0x1400136ce  mov     rdx, r15; struct CHString *
0x1400136d1  lea     rcx, [rbp+2A0h+var_300]; this
0x1400136d5  call    ??0CHString@@QEAA@AEBV0@@Z; CHString::CHString(CHString const &)
0x1400136da  mov     rbx, rax
0x1400136dd  lea     rdx, [rsp+3A0h+var_358]; struct CHString *
0x1400136e2  lea     rcx, [rbp+2A0h+var_2F8]; this
0x1400136e6  call    ??0CHString@@QEAA@AEBV0@@Z; CHString::CHString(CHString const &)
0x1400136eb  nop
0x1400136ec  mov     [rsp+3A0h+var_370], 0FFFFFFFF80000002h
0x1400136f5  mov     dword ptr [rsp+3A0h+var_378], r13d
0x1400136fa  mov     [rsp+3A0h+var_380], rdi
0x1400136ff  mov     r9, rbx
0x140013702  mov     r8, [rsp+3A0h+var_350]
0x140013707  mov     rdx, rax
0x14001370a  mov     rcx, [rbp+2A0h+var_310]
0x14001370e  call    ?SearchAndBuildList@CRegistrySearch@@QEAAHVCHString@@AEAVCHPtrArray@@00HPEAUHKEY__@@@Z; CRegistrySearch::SearchAndBuildList(CHString,CHPtrArray &,CHString,CHString,int,HKEY__ *)
0x140013713  nop
0x140013714  lea     rcx, [rsp+3A0h+var_348]; this
0x140013719  call    ??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x14001371e  nop
0x14001371f  lea     rcx, [rsp+3A0h+var_358]; this
0x140013724  call    ??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x140013729  lea     rdx, [rsp+3A0h+var_360]; struct CHString *
0x14001372e  lea     rcx, [rbp+2A0h+var_2B0]; this
0x140013732  call    ?GetCurrentSubKeyName@CRegistry@@QEAAKAEAVCHString@@@Z; CRegistry::GetCurrentSubKeyName(CHString &)
0x140013737  test    eax, eax
0x140013739  jz      loc_1400135B9
0x14001373f  lea     rcx, [rsp+3A0h+var_360]; this
0x140013744  call    ??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x140013749  mov     ebx, 1
0x14001374e  lea     rcx, [rbp+2A0h+var_2B0]; this
0x140013752  call    ??1CRegistry@@QEAA@XZ; CRegistry::~CRegistry(void)
0x140013757  nop
0x140013758  mov     rcx, r14; this
0x14001375b  call    ??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x140013760  nop
0x140013761  mov     rcx, r15; this
0x140013764  call    ??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x140013769  nop
0x14001376a  mov     rcx, r12; this
0x14001376d  call    ??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x140013772  mov     eax, ebx
0x140013774  mov     rcx, [rbp+2A0h+var_50]
0x14001377b  xor     rcx, rsp; StackCookie
0x14001377e  call    __security_check_cookie
0x140013783  add     rsp, 368h
0x14001378a  pop     r15
0x14001378c  pop     r14
0x14001378e  pop     r13
0x140013790  pop     r12
0x140013792  pop     rdi
0x140013793  pop     rsi
0x140013794  pop     rbx
0x140013795  pop     rbp
0x140013796  retn
```
