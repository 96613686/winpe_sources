# CBrowserCap::AddProperty(char *,char const *,int)

- ea: `0x1800076e8`
- end: `0x180007960`
- name: `?AddProperty@CBrowserCap@@QEAAXPEADPEBDH@Z`
- size: `632`
- prototype: `void __fastcall(CBrowserCap *this, char *, const char *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180007a70`
- `0x180008fa8`

## callees

- `0x180002498`
- `0x1800037f4`
- `0x180007570`
- `0x1800076e8`
- `0x18000888c`
- `0x180009ab4`
- `0x18000b640`
- `0x18000b700`

## import_xrefs

- `msvcrt!_strnicmp` at `0x18000781f`
- `msvcrt!_strnicmp` at `0x18000785e`
- `msvcrt!_strnicmp` at `0x18000781f`
- `msvcrt!_strnicmp` at `0x18000785e`
- `msvcrt!atol` at `0x180007781`
- `msvcrt!atol` at `0x180007781`
- `msvcrt!_strlwr` at `0x180007727`
- `msvcrt!_strlwr` at `0x180007727`
- `KERNEL32!MultiByteToWideChar` at `0x1800078ed`
- `KERNEL32!MultiByteToWideChar` at `0x1800078ed`
- `OLEAUT32!__imp_SysAllocString` at `0x180007915`
- `OLEAUT32!__imp_SysAllocString` at `0x180007915`
- `OLEAUT32!__imp_VariantInit` at `0x18000771d`
- `OLEAUT32!__imp_VariantInit` at `0x18000771d`
- `OLEAUT32!__imp_VariantClear` at `0x180007798`
- `OLEAUT32!__imp_VariantClear` at `0x1800077f0`
- `OLEAUT32!__imp_VariantClear` at `0x180007836`
- `OLEAUT32!__imp_VariantClear` at `0x180007875`
- `OLEAUT32!__imp_VariantClear` at `0x180007903`
- `OLEAUT32!__imp_VariantClear` at `0x180007798`
- `OLEAUT32!__imp_VariantClear` at `0x1800077f0`
- `OLEAUT32!__imp_VariantClear` at `0x180007836`
- `OLEAUT32!__imp_VariantClear` at `0x180007875`
- `OLEAUT32!__imp_VariantClear` at `0x180007903`
- `OLEAUT32!__imp_VariantCopy` at `0x1800077d2`
- `OLEAUT32!__imp_VariantCopy` at `0x1800077d2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CBrowserCap::AddProperty(CBrowserCap *this, char *a2, const char *a3, int a4)
{
  char v8; // si
  bool v9; // r8
  __int64 v10; // rbx
  bool v11; // bl
  LONG v12; // edi
  bool v13; // r8
  VARIANTARG *v14; // rbx
  HRESULT v15; // eax
  __int64 v16; // rax
  int cchWideChar; // edx
  unsigned __int64 v18; // rax
  __int64 v19; // rcx
  unsigned __int64 v20; // rcx
  void *v21; // rsp
  void *v22; // rsp
  const OLECHAR *v23; // rbx
  __int64 v24; // [rsp+0h] [rbp-30h] BYREF
  VARIANTARG pvarg; // [rsp+30h] [rbp+0h] BYREF
  int v26; // [rsp+48h] [rbp+18h]
  _BYTE v27[16]; // [rsp+50h] [rbp+20h] BYREF

  v8 = 0;
  v26 = 0;
  VariantInit(&pvarg);
  _strlwr(a2);
  v11 = 0;
  if ( !a4 )
  {
    String::String((String *)v27, a2, v9);
    v8 = 1;
    v26 = 1;
    v10 = *((_QWORD *)this + 12);
    if ( TStringMap<ATL::CComVariant>::find((char *)this + 80, v27) != v10 )
      v11 = 1;
  }
  if ( (v8 & 1) != 0 )
    TRefPtr<CMonitorNotify>::~TRefPtr<CMonitorNotify>(v27);
  if ( !v11 )
  {
    if ( *a3 == 35 )
    {
      v12 = atol(a3 + 1);
      if ( pvarg.vt != 3 )
      {
        VariantClear(&pvarg);
        pvarg.vt = 3;
      }
      pvarg.lVal = v12;
    }
    else if ( !_strnicmp(a3, "TRUE", 5u) )
    {
      if ( pvarg.vt != 11 )
      {
        VariantClear(&pvarg);
        pvarg.vt = 11;
      }
      pvarg.iVal = -1;
    }
    else if ( !_strnicmp(a3, "FALSE", 6u) )
    {
      if ( pvarg.vt != 11 )
      {
        VariantClear(&pvarg);
        pvarg.vt = 11;
      }
      pvarg.iVal = 0;
    }
    else
    {
      v16 = -1;
      do
        ++v16;
      while ( a3[v16] );
      cchWideChar = v16 + 1;
      if ( (int)v16 + 1 > 0x3FFFFFFF )
        goto LABEL_31;
      v18 = 2LL * cchWideChar;
      v19 = v18 + 15;
      if ( v18 + 15 < v18 )
        v19 = 0xFFFFFFFFFFFFFF0LL;
      v20 = v19 & 0xFFFFFFFFFFFFFFF0uLL;
      v21 = alloca(v20);
      v22 = alloca(v20);
      if ( &v24 == (__int64 *)-48LL )
      {
LABEL_31:
        v23 = 0;
      }
      else
      {
        pvarg.vt = 0;
        v23 = (const OLECHAR *)((unsigned __int64)&pvarg
                              & -(__int64)(MultiByteToWideChar(3u, 0, a3, -1, &pvarg.vt, cchWideChar) != 0));
      }
      VariantClear(&pvarg);
      pvarg.vt = 8;
      pvarg.llVal = (LONGLONG)SysAllocString(v23);
      if ( !pvarg.llVal && v23 )
      {
        pvarg.vt = 10;
        pvarg.lVal = -2147024882;
        ATL::AtlThrowImpl(-2147024882);
      }
    }
    String::String((String *)v27, a2, v13);
    v14 = (VARIANTARG *)TStringMap<ATL::CComVariant>::operator[]((char *)this + 80, v27);
    if ( v14 != &pvarg )
    {
      v15 = VariantCopy(v14, &pvarg);
      if ( v15 < 0 )
      {
        v14->vt = 10;
        v14->lVal = v15;
        ATL::AtlThrowImpl(v15);
      }
    }
    TRefPtr<CMonitorNotify>::~TRefPtr<CMonitorNotify>(v27);
  }
  VariantClear(&pvarg);
}

```

## disassembly

```asm
0x1800076e8  push    rbp
0x1800076ea  push    rbx
0x1800076eb  push    rsi
0x1800076ec  push    rdi
0x1800076ed  push    r14
0x1800076ef  push    r15
0x1800076f1  sub     rsp, 78h
0x1800076f5  lea     rbp, [rsp+30h]
0x1800076fa  mov     rax, cs:__security_cookie
0x180007701  xor     rax, rbp
0x180007704  mov     [rbp+70h+var_40], rax
0x180007708  mov     ebx, r9d
0x18000770b  mov     rdi, r8
0x18000770e  mov     r14, rdx
0x180007711  mov     r15, rcx
0x180007714  xor     esi, esi
0x180007716  mov     [rbp+70h+var_58], esi
0x180007719  lea     rcx, [rbp+70h+pvarg]; pvarg
0x18000771d  call    cs:__imp_VariantInit
0x180007723  nop
0x180007724  mov     rcx, r14; String
0x180007727  call    cs:__imp__strlwr
0x18000772d  test    ebx, ebx
0x18000772f  jnz     short loc_18000775F
0x180007731  mov     rdx, r14; char *
0x180007734  lea     rcx, [rbp+70h+var_50]; this
0x180007738  call    ??0String@@QEAA@PEBD_N@Z; String::String(char const *,bool)
0x18000773d  nop
0x18000773e  lea     esi, [rbx+1]
0x180007741  mov     [rbp+70h+var_58], esi
0x180007744  mov     rbx, [r15+60h]
0x180007748  lea     rcx, [r15+50h]
0x18000774c  lea     rdx, [rbp+70h+var_50]
0x180007750  call    ?find@?$TStringMap@VCComVariant@ATL@@@@QEAAPEAU?$pair@VString@@VCComVariant@ATL@@@std@@AEBVString@@@Z; TStringMap<ATL::CComVariant>::find(String const &)
0x180007755  cmp     rax, rbx
0x180007758  jz      short loc_18000775F
0x18000775a  mov     bl, sil
0x18000775d  jmp     short loc_180007761
0x18000775f  xor     bl, bl
0x180007761  test    sil, 1
0x180007765  jz      short loc_180007770
0x180007767  lea     rcx, [rbp+70h+var_50]
0x18000776b  call    ??1?$TRefPtr@VCMonitorNotify@@@@QEAA@XZ; TRefPtr<CMonitorNotify>::~TRefPtr<CMonitorNotify>(void)
0x180007770  test    bl, bl
0x180007772  jnz     short loc_1800077EC
0x180007774  cmp     byte ptr [rdi], 23h ; '#'
0x180007777  jnz     loc_18000780F
0x18000777d  lea     rcx, [rdi+1]; String
0x180007781  call    cs:__imp_atol
0x180007787  mov     edi, eax
0x180007789  mov     ebx, 3
0x18000778e  cmp     word ptr [rbp+70h+pvarg], bx
0x180007792  jz      short loc_1800077A2
0x180007794  lea     rcx, [rbp+70h+pvarg]; pvarg
0x180007798  call    cs:__imp_VariantClear
0x18000779e  mov     word ptr [rbp+70h+pvarg], bx
0x1800077a2  mov     dword ptr [rbp+70h+pvarg+8], edi
0x1800077a5  mov     rdx, r14; char *
0x1800077a8  lea     rcx, [rbp+70h+var_50]; this
0x1800077ac  call    ??0String@@QEAA@PEBD_N@Z; String::String(char const *,bool)
0x1800077b1  nop
0x1800077b2  lea     rcx, [r15+50h]
0x1800077b6  lea     rdx, [rbp+70h+var_50]
0x1800077ba  call    ??A?$TStringMap@VCComVariant@ATL@@@@QEAAAEAVCComVariant@ATL@@AEBVString@@@Z; TStringMap<ATL::CComVariant>::operator[](String const &)
0x1800077bf  mov     rbx, rax
0x1800077c2  lea     rax, [rbp+70h+pvarg]
0x1800077c6  cmp     rbx, rax
0x1800077c9  jz      short loc_1800077E2
0x1800077cb  lea     rdx, [rbp+70h+pvarg]; pvargSrc
0x1800077cf  mov     rcx, rbx; pvargDest
0x1800077d2  call    cs:__imp_VariantCopy
0x1800077d8  mov     ecx, eax; int
0x1800077da  test    eax, eax
0x1800077dc  js      loc_18000793B
0x1800077e2  lea     rcx, [rbp+70h+var_50]
0x1800077e6  call    ??1?$TRefPtr@VCMonitorNotify@@@@QEAA@XZ; TRefPtr<CMonitorNotify>::~TRefPtr<CMonitorNotify>(void)
0x1800077eb  nop
0x1800077ec  lea     rcx, [rbp+70h+pvarg]; pvarg
0x1800077f0  call    cs:__imp_VariantClear
0x1800077f6  mov     rcx, [rbp+70h+var_40]
0x1800077fa  xor     rcx, rbp; StackCookie
0x1800077fd  call    __security_check_cookie
0x180007802  lea     rsp, [rbp+48h]
0x180007806  pop     r15
0x180007808  pop     r14
0x18000780a  pop     rdi
0x18000780b  pop     rsi
0x18000780c  pop     rbx
0x18000780d  pop     rbp
0x18000780e  retn
0x18000780f  mov     r8d, 5; MaxCount
0x180007815  lea     rdx, aTrue; "TRUE"
0x18000781c  mov     rcx, rdi; String1
0x18000781f  call    cs:__imp__strnicmp
0x180007825  test    eax, eax
0x180007827  jnz     short loc_18000784E
0x180007829  lea     ebx, [rax+0Bh]
0x18000782c  cmp     word ptr [rbp+70h+pvarg], bx
0x180007830  jz      short loc_180007840
0x180007832  lea     rcx, [rbp+70h+pvarg]; pvarg
0x180007836  call    cs:__imp_VariantClear
0x18000783c  mov     word ptr [rbp+70h+pvarg], bx
0x180007840  or      r9, 0FFFFFFFFFFFFFFFFh
0x180007844  mov     word ptr [rbp+70h+pvarg+8], r9w
0x180007849  jmp     loc_1800077A5
0x18000784e  mov     r8d, 6; MaxCount
0x180007854  lea     rdx, aFalse; "FALSE"
0x18000785b  mov     rcx, rdi; String1
0x18000785e  call    cs:__imp__strnicmp
0x180007864  test    eax, eax
0x180007866  jnz     short loc_18000788A
0x180007868  lea     ebx, [rax+0Bh]
0x18000786b  cmp     word ptr [rbp+70h+pvarg], bx
0x18000786f  jz      short loc_18000787F
0x180007871  lea     rcx, [rbp+70h+pvarg]; pvarg
0x180007875  call    cs:__imp_VariantClear
0x18000787b  mov     word ptr [rbp+70h+pvarg], bx
0x18000787f  xor     eax, eax
0x180007881  mov     word ptr [rbp+70h+pvarg+8], ax
0x180007885  jmp     loc_1800077A5
0x18000788a  or      r9, 0FFFFFFFFFFFFFFFFh
0x18000788e  mov     rax, r9
0x180007891  inc     rax
0x180007894  cmp     byte ptr [rdi+rax], 0
0x180007898  jnz     short loc_180007891
0x18000789a  lea     edx, [rax+1]
0x18000789d  cmp     edx, 3FFFFFFFh
0x1800078a3  jg      short loc_1800078FD
0x1800078a5  movsxd  rax, edx
0x1800078a8  add     rax, rax
0x1800078ab  lea     rcx, [rax+0Fh]
0x1800078af  cmp     rcx, rax
0x1800078b2  ja      short loc_1800078BE
0x1800078b4  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800078be  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800078c2  mov     rax, rcx
0x1800078c5  call    _alloca_probe
0x1800078ca  sub     rsp, rcx
0x1800078cd  lea     rsi, [rsp+0A0h+pvarg]
0x1800078d2  test    rsi, rsi
0x1800078d5  jz      short loc_1800078FD
0x1800078d7  xor     eax, eax
0x1800078d9  mov     [rsi], ax
0x1800078dc  mov     [rsp+0A0h+cchWideChar], edx; cchWideChar
0x1800078e0  mov     [rsp+0A0h+lpWideCharStr], rsi; lpWideCharStr
0x1800078e5  mov     r8, rdi; lpMultiByteStr
0x1800078e8  xor     edx, edx; dwFlags
0x1800078ea  lea     ecx, [rax+3]; CodePage
0x1800078ed  call    cs:__imp_MultiByteToWideChar
0x1800078f3  neg     eax
0x1800078f5  sbb     rbx, rbx
0x1800078f8  and     rbx, rsi
0x1800078fb  jmp     short loc_1800078FF
0x1800078fd  xor     ebx, ebx
0x1800078ff  lea     rcx, [rbp+70h+pvarg]; pvarg
0x180007903  call    cs:__imp_VariantClear
0x180007909  mov     eax, 8
0x18000790e  mov     word ptr [rbp+70h+pvarg], ax
0x180007912  mov     rcx, rbx; psz
0x180007915  call    cs:__imp_SysAllocString
0x18000791b  mov     dword ptr [rbp+70h+pvarg+8], eax
0x18000791e  mov     rcx, rax
0x180007921  sar     rcx, 20h
0x180007925  mov     dword ptr [rbp+70h+pvarg+0Ch], ecx
0x180007928  test    rax, rax
0x18000792b  jnz     loc_1800077A5
0x180007931  test    rbx, rbx
0x180007934  jnz     short loc_180007949
0x180007936  jmp     loc_1800077A5
0x18000793b  mov     word ptr [rbx], 0Ah
0x180007940  mov     [rbx+8], ecx
0x180007943  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180007949  mov     eax, 0Ah
0x18000794e  mov     word ptr [rbp+70h+pvarg], ax
0x180007952  mov     ecx, 8007000Eh; int
0x180007957  mov     dword ptr [rbp+70h+pvarg+8], ecx
0x18000795a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
