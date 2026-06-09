# Windows::UI::Input::Inking::PenAndInkSettings::GetHandwritingFontName(HSTRING__ * *)

- ea: `0x180088680`
- end: `0x1800887b7`
- name: `?GetHandwritingFontName@PenAndInkSettings@Inking@Input@UI@Windows@@AEAAJPEAPEAUHSTRING__@@@Z`
- size: `311`
- prototype: `__int64 __fastcall(Windows::UI::Input::Inking::PenAndInkSettings *__hidden this, HSTRING *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180089330`

## callees

- `0x1800062a0`
- `0x180006f00`
- `0x18001332c`
- `0x18001f73c`
- `0x18008760c`
- `0x180088680`
- `0x180089054`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180088780`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180088797`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180088780`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180088797`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::UI::Input::Inking::PenAndInkSettings::GetHandwritingFontName(
        Windows::UI::Input::Inking::PenAndInkSettings *this,
        HSTRING *a2)
{
  int v3; // eax
  int v4; // ebx
  unsigned __int64 v5; // r9
  __int64 v6; // rdx
  __int64 v7; // rcx
  unsigned __int64 v8; // rcx
  HSTRING v10; // rax
  unsigned __int16 *v11; // [rsp+20h] [rbp-59h]
  unsigned int v12; // [rsp+30h] [rbp-49h] BYREF
  HSTRING string; // [rsp+38h] [rbp-41h] BYREF
  int v14; // [rsp+40h] [rbp-39h]
  int v15; // [rsp+44h] [rbp-35h] BYREF
  unsigned __int16 v16[8]; // [rsp+48h] [rbp-31h] BYREF
  wchar_t v17; // [rsp+58h] [rbp-21h]
  unsigned __int16 v18[32]; // [rsp+60h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  *(_OWORD *)v16 = *(_OWORD *)L"Ink Free";
  v17 = aInkFree[8];
  string = 0;
  v3 = Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)&string, v16, 8u);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = (unsigned int)v3;
    v6 = 267;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\core\\penandinksettings.cpp",
      (const char *)v5,
      (int)v11);
    WindowsDeleteString(string);
    return (unsigned int)v4;
  }
  memset_0(v18, 0, sizeof(v18));
  v15 = 1;
  v14 = 64;
  v11 = v18;
  if ( (int)Windows::UI::Input::Inking::PenAndInkSettings::RegGetValueWithFallback<std::array<unsigned short const *,2>>(
              v7,
              L"LatinFontName",
              2,
              &v15) >= 0 )
  {
    v12 = 0;
    v8 = -1;
    do
      ++v8;
    while ( v18[v8] );
    v4 = ULongLongToUInt(v8, &v12);
    if ( v4 < 0
      || (v4 = Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)&string, v18, v12), v4 < 0) )
    {
      v5 = (unsigned int)v4;
      v6 = 281;
      goto LABEL_9;
    }
  }
  v10 = string;
  string = 0;
  *a2 = v10;
  WindowsDeleteString(0);
  return 0;
}

```

## disassembly

```asm
0x180088680  push    rbp
0x180088682  push    rbx
0x180088683  push    rsi
0x180088684  push    rdi
0x180088685  lea     rbp, [rsp-3Fh]
0x18008868a  sub     rsp, 0B8h
0x180088691  mov     rax, cs:__security_cookie
0x180088698  xor     rax, rsp
0x18008869b  mov     [rbp+57h+var_30], rax
0x18008869f  mov     rdi, rdx
0x1800886a2  movups  xmm0, xmmword ptr cs:aInkFree; "Ink Free"
0x1800886a9  movups  xmmword ptr [rbp+57h+var_88], xmm0
0x1800886ad  movzx   eax, word ptr cs:aInkFree+10h; ""
0x1800886b4  mov     [rbp+57h+var_78], ax
0x1800886b8  xor     esi, esi
0x1800886ba  mov     [rbp+57h+string], rsi
0x1800886be  lea     r8d, [rsi+8]; unsigned int
0x1800886c2  lea     rdx, [rbp+57h+var_88]; unsigned __int16 *
0x1800886c6  lea     rcx, [rbp+57h+string]; this
0x1800886ca  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x1800886cf  mov     ebx, eax
0x1800886d1  test    eax, eax
0x1800886d3  jns     short loc_1800886E2
0x1800886d5  mov     r9d, eax
0x1800886d8  mov     edx, 10Bh
0x1800886dd  jmp     loc_18008876B
0x1800886e2  mov     ebx, 40h ; '@'
0x1800886e7  mov     r8d, ebx; Size
0x1800886ea  xor     edx, edx; Val
0x1800886ec  lea     rcx, [rbp+57h+var_70]; void *
0x1800886f0  call    memset_0
0x1800886f5  mov     [rbp+57h+var_8C], 1
0x1800886fc  mov     [rbp+57h+var_90], ebx
0x1800886ff  lea     rax, [rbp+57h+var_90]
0x180088703  mov     [rsp+0D0h+var_A8], rax
0x180088708  lea     rax, [rbp+57h+var_70]
0x18008870c  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x180088711  lea     r9, [rbp+57h+var_8C]
0x180088715  lea     r8d, [rbx-3Eh]
0x180088719  lea     rdx, aLatinfontname; "LatinFontName"
0x180088720  call    ??$RegGetValueWithFallback@V?$array@PEBG$01@std@@@PenAndInkSettings@Inking@Input@UI@Windows@@CAJAEBV?$array@PEBG$01@std@@PEBGKPEAKPEAX2@Z; Windows::UI::Input::Inking::PenAndInkSettings::RegGetValueWithFallback<std::array<ushort const *,2>>(std::array<ushort const *,2> const &,ushort const *,ulong,ulong *,void *,ulong *)
0x180088725  test    eax, eax
0x180088727  js      short loc_18008878A
0x180088729  mov     [rbp+57h+var_A0], esi
0x18008872c  lea     rax, [rbp+57h+var_70]
0x180088730  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180088734  inc     rcx; unsigned __int64
0x180088737  cmp     [rax+rcx*2], si
0x18008873b  jnz     short loc_180088734
0x18008873d  lea     rdx, [rbp+57h+var_A0]; unsigned int *
0x180088741  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x180088746  mov     ebx, eax
0x180088748  test    eax, eax
0x18008874a  js      short loc_180088763
0x18008874c  mov     r8d, [rbp+57h+var_A0]; unsigned int
0x180088750  lea     rdx, [rbp+57h+var_70]; unsigned __int16 *
0x180088754  lea     rcx, [rbp+57h+string]; this
0x180088758  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x18008875d  mov     ebx, eax
0x18008875f  test    eax, eax
0x180088761  jns     short loc_18008878A
0x180088763  mov     r9d, ebx; char *
0x180088766  mov     edx, 119h; void *
0x18008876b  lea     r8, aOnecoreuapWind_29; "onecoreuap\\windows\\advcore\\winrt\\di"...
0x180088772  mov     rcx, [rbp+5Fh]; this
0x180088776  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008877b  nop
0x18008877c  mov     rcx, [rbp+57h+string]; string
0x180088780  call    cs:__imp_WindowsDeleteString
0x180088786  mov     eax, ebx
0x180088788  jmp     short loc_18008879F
0x18008878a  mov     rax, [rbp+57h+string]
0x18008878e  mov     [rbp+57h+string], rsi
0x180088792  mov     [rdi], rax
0x180088795  xor     ecx, ecx; string
0x180088797  call    cs:__imp_WindowsDeleteString
0x18008879d  xor     eax, eax
0x18008879f  mov     rcx, [rbp+57h+var_30]
0x1800887a3  xor     rcx, rsp; StackCookie
0x1800887a6  call    __security_check_cookie
0x1800887ab  add     rsp, 0B8h
0x1800887b2  pop     rdi
0x1800887b3  pop     rsi
0x1800887b4  pop     rbx
0x1800887b5  pop     rbp
0x1800887b6  retn
```
