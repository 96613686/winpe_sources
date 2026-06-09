# GPSLatLongPropertyHelper::GetDecimalFromProperties(Windows::Foundation::Collections::IMapView<HSTRING__ *,IInspectable *> *,double *)

- ea: `0x1800464b4`
- end: `0x180046635`
- name: `?GetDecimalFromProperties@GPSLatLongPropertyHelper@@QEBAJPEAU?$IMapView@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEAN@Z`
- size: `385`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180047268`

## callees

- `0x180020c48`
- `0x180021f14`
- `0x180026920`
- `0x180046424`
- `0x1800464b4`
- `0x180046c18`
- `0x180047574`
- `0x18004a1bc`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004655c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046613`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004655c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046613`

## string_xrefs

- `0x180046514`: `avcore\mf\photography\components\geotag\lib\geotag.cpp`
- `0x1800465cb`: `avcore\mf\photography\components\geotag\lib\geotag.cpp`

## pseudocode

```c
__int64 __fastcall GPSLatLongPropertyHelper::GetDecimalFromProperties(__int64 a1, __int64 a2, double *a3)
{
  __int64 v6; // rax
  int LatLongUInt32ArrayFromMap; // ebx
  __int64 v8; // rdx
  __int64 v9; // rax
  __int64 v10; // rax
  int HSTRINGFromMap; // eax
  __int64 v12; // rdx
  bool v13; // zf
  HSTRING string; // [rsp+20h] [rbp-60h] BYREF
  double v16; // [rsp+28h] [rbp-58h] BYREF
  double v17; // [rsp+30h] [rbp-50h] BYREF
  __int128 v18; // [rsp+38h] [rbp-48h] BYREF
  __int64 v19; // [rsp+48h] [rbp-38h]
  _BYTE v20[32]; // [rsp+50h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  v19 = 0;
  v18 = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v20, a1);
  LatLongUInt32ArrayFromMap = GPSLatLongPropertyHelper::GetLatLongUInt32ArrayFromMap(a2, *(_QWORD *)(v6 + 24), &v18);
  if ( LatLongUInt32ArrayFromMap >= 0 )
  {
    v9 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v20, a1 + 8);
    LatLongUInt32ArrayFromMap = GPSLatLongPropertyHelper::GetLatLongUInt32ArrayFromMap(
                                  a2,
                                  *(_QWORD *)(v9 + 24),
                                  (char *)&v18 + 12);
    if ( LatLongUInt32ArrayFromMap < 0 )
    {
      v8 = 143;
      goto LABEL_3;
    }
    WindowsDeleteString(0);
    string = 0;
    v10 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v20, a1 + 16);
    HSTRINGFromMap = GetHSTRINGFromMap(a2, *(_QWORD *)(v10 + 24), &string);
    LatLongUInt32ArrayFromMap = HSTRINGFromMap;
    if ( HSTRINGFromMap >= 0 )
    {
      v13 = *(_QWORD *)(a1 + 16) == (_QWORD)L"System.GPS.LatitudeRef";
      v17 = DOUBLE_1_0;
      HSTRINGFromMap = GPSLatLongPropertyHelper::RefStringToDecimal(
                         (const struct Microsoft::WRL::Wrappers::HString *)&string,
                         v13,
                         &v17);
      LatLongUInt32ArrayFromMap = HSTRINGFromMap;
      if ( HSTRINGFromMap >= 0 )
      {
        v16 = 0.0;
        HSTRINGFromMap = GPSLatLongPropertyHelper::GetDecimalFromLatLongRational(
                           (struct GPSLatLongPropertyHelper::LatLongRational *)&v18,
                           &v16);
        LatLongUInt32ArrayFromMap = HSTRINGFromMap;
        if ( HSTRINGFromMap >= 0 )
        {
          LatLongUInt32ArrayFromMap = 0;
          *a3 = v16 * v17;
          goto LABEL_14;
        }
        v12 = 153;
      }
      else
      {
        v12 = 150;
      }
    }
    else
    {
      v12 = 145;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"avcore\\mf\\photography\\components\\geotag\\lib\\geotag.cpp",
      (const char *)(unsigned int)HSTRINGFromMap,
      (int)string);
LABEL_14:
    WindowsDeleteString(string);
    return (unsigned int)LatLongUInt32ArrayFromMap;
  }
  v8 = 141;
LABEL_3:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"avcore\\mf\\photography\\components\\geotag\\lib\\geotag.cpp",
    (const char *)(unsigned int)LatLongUInt32ArrayFromMap,
    (int)string);
  return (unsigned int)LatLongUInt32ArrayFromMap;
}

```

## disassembly

```asm
0x1800464b4  push    rbp
0x1800464b6  push    rbx
0x1800464b7  push    rsi
0x1800464b8  push    rdi
0x1800464b9  push    r14
0x1800464bb  mov     rbp, rsp
0x1800464be  sub     rsp, 80h
0x1800464c5  mov     rax, cs:__security_cookie
0x1800464cc  xor     rax, rsp
0x1800464cf  mov     [rbp+var_10], rax
0x1800464d3  mov     rsi, rdx
0x1800464d6  mov     rdi, rcx
0x1800464d9  mov     rdx, rcx
0x1800464dc  xorps   xmm0, xmm0
0x1800464df  xor     eax, eax
0x1800464e1  lea     rcx, [rbp+var_30]
0x1800464e5  mov     r14, r8
0x1800464e8  mov     [rbp+var_38], rax
0x1800464ec  movups  [rbp+var_48], xmm0
0x1800464f0  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800464f5  lea     r8, [rbp+var_48]
0x1800464f9  mov     rcx, rsi
0x1800464fc  mov     rdx, [rax+18h]
0x180046500  call    ?GetLatLongUInt32ArrayFromMap@GPSLatLongPropertyHelper@@CAJPEAU?$IMapView@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEAUHSTRING__@@PEAII@Z; GPSLatLongPropertyHelper::GetLatLongUInt32ArrayFromMap(Windows::Foundation::Collections::IMapView<HSTRING__ *,IInspectable *> *,HSTRING__ *,uint *,uint)
0x180046505  mov     ebx, eax
0x180046507  test    eax, eax
0x180046509  jns     short loc_180046528
0x18004650b  mov     edx, 8Dh; void *
0x180046510  mov     rcx, [rbp+28h]; this
0x180046514  lea     r8, aAvcoreMfPhotog; "avcore\\mf\\photography\\components\\ge"...
0x18004651b  mov     r9d, ebx; char *
0x18004651e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180046523  jmp     loc_180046619
0x180046528  lea     rdx, [rdi+8]
0x18004652c  lea     rcx, [rbp+var_30]
0x180046530  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180046535  lea     r8, [rbp+var_48+0Ch]
0x180046539  mov     rcx, rsi
0x18004653c  mov     rdx, [rax+18h]
0x180046540  call    ?GetLatLongUInt32ArrayFromMap@GPSLatLongPropertyHelper@@CAJPEAU?$IMapView@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEAUHSTRING__@@PEAII@Z; GPSLatLongPropertyHelper::GetLatLongUInt32ArrayFromMap(Windows::Foundation::Collections::IMapView<HSTRING__ *,IInspectable *> *,HSTRING__ *,uint *,uint)
0x180046545  mov     ebx, eax
0x180046547  test    eax, eax
0x180046549  jns     short loc_180046552
0x18004654b  mov     edx, 8Fh
0x180046550  jmp     short loc_180046510
0x180046552  xor     ecx, ecx; string
0x180046554  mov     [rbp+string], 0
0x18004655c  call    cs:__imp_WindowsDeleteString
0x180046562  lea     rdx, [rdi+10h]
0x180046566  mov     [rbp+string], 0
0x18004656e  lea     rcx, [rbp+var_30]
0x180046572  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180046577  lea     r8, [rbp+string]
0x18004657b  mov     rcx, rsi
0x18004657e  mov     rdx, [rax+18h]
0x180046582  call    ?GetHSTRINGFromMap@@YAJPEAU?$IMapView@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEAUHSTRING__@@PEAPEAU5@@Z; GetHSTRINGFromMap(Windows::Foundation::Collections::IMapView<HSTRING__ *,IInspectable *> *,HSTRING__ *,HSTRING__ * *)
0x180046587  mov     ebx, eax
0x180046589  test    eax, eax
0x18004658b  jns     short loc_180046594
0x18004658d  mov     edx, 91h
0x180046592  jmp     short loc_1800465C7
0x180046594  movsd   xmm0, cs:__real@3ff0000000000000
0x18004659c  lea     rax, aSystemGpsLatit_1; "System.GPS.LatitudeRef"
0x1800465a3  cmp     [rdi+10h], rax
0x1800465a7  lea     r8, [rbp+var_50]; double *
0x1800465ab  lea     rcx, [rbp+string]; struct Microsoft::WRL::Wrappers::HString *
0x1800465af  movsd   [rbp+var_50], xmm0
0x1800465b4  setz    dl; bool
0x1800465b7  call    ?RefStringToDecimal@GPSLatLongPropertyHelper@@CAJAEBVHString@Wrappers@WRL@Microsoft@@_NPEAN@Z; GPSLatLongPropertyHelper::RefStringToDecimal(Microsoft::WRL::Wrappers::HString const &,bool,double *)
0x1800465bc  mov     ebx, eax
0x1800465be  test    eax, eax
0x1800465c0  jns     short loc_1800465DC
0x1800465c2  mov     edx, 96h; void *
0x1800465c7  mov     rcx, [rbp+28h]; this
0x1800465cb  lea     r8, aAvcoreMfPhotog; "avcore\\mf\\photography\\components\\ge"...
0x1800465d2  mov     r9d, eax; char *
0x1800465d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800465da  jmp     short loc_18004660F
0x1800465dc  xorps   xmm0, xmm0
0x1800465df  lea     rdx, [rbp+var_58]; double *
0x1800465e3  lea     rcx, [rbp+var_48]; struct GPSLatLongPropertyHelper::LatLongRational *
0x1800465e7  movsd   [rbp+var_58], xmm0
0x1800465ec  call    ?GetDecimalFromLatLongRational@GPSLatLongPropertyHelper@@CAJPEAULatLongRational@1@PEAN@Z; GPSLatLongPropertyHelper::GetDecimalFromLatLongRational(GPSLatLongPropertyHelper::LatLongRational *,double *)
0x1800465f1  mov     ebx, eax
0x1800465f3  test    eax, eax
0x1800465f5  jns     short loc_1800465FE
0x1800465f7  mov     edx, 99h
0x1800465fc  jmp     short loc_1800465C7
0x1800465fe  movsd   xmm0, [rbp+var_58]
0x180046603  xor     ebx, ebx
0x180046605  mulsd   xmm0, [rbp+var_50]
0x18004660a  movsd   qword ptr [r14], xmm0
0x18004660f  mov     rcx, [rbp+string]; string
0x180046613  call    cs:__imp_WindowsDeleteString
0x180046619  mov     eax, ebx
0x18004661b  mov     rcx, [rbp+var_10]
0x18004661f  xor     rcx, rsp; StackCookie
0x180046622  call    __security_check_cookie
0x180046627  add     rsp, 80h
0x18004662e  pop     r14
0x180046630  pop     rdi
0x180046631  pop     rsi
0x180046632  pop     rbx
0x180046633  pop     rbp
0x180046634  retn
```
