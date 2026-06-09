# VelocityFeatureMatchingPlugin(int *,void *,_DB *,ulong,ulong,ushort const *,void *)

- ea: `0x1800312b0`
- end: `0x1800315e3`
- name: `?VelocityFeatureMatchingPlugin@@YAHPEAHPEAXPEAU_DB@@KKPEBG1@Z`
- size: `819`
- prototype: `__int64 __fastcall(int *, void *, struct _DB *, unsigned int, unsigned __int16 *, const unsigned __int16 *, void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001cf0`
- `0x18000b720`
- `0x180030684`
- `0x1800312b0`
- `0x18003f0b0`
- `0x1800543c0`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18003154c`
- `KERNEL32!FreeLibrary` at `0x18003154c`
- `KERNEL32!LocalFree` at `0x180031531`
- `KERNEL32!LocalFree` at `0x180031531`

## string_xrefs

- `0x18003136d`: `Enter VelocityFeatureMatchingPlugin.`
- `0x18003137a`: `VelocityFeatureMatchingPlugin`
- `0x1800315a3`: `VelocityFeatureMatchingPlugin`
- `0x180031596`: `VelocityFeatureMatchingPlugin Matched = %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall VelocityFeatureMatchingPlugin(
        int *a1,
        void *a2,
        struct _DB *a3,
        __int64 a4,
        unsigned __int16 *a5,
        const unsigned __int16 *a6,
        void *a7)
{
  unsigned int v7; // r9d
  __int128 *v8; // rdx
  const char *v10; // rax
  int *v11; // [rsp+30h] [rbp-1A8h] BYREF
  int v12; // [rsp+38h] [rbp-1A0h] BYREF
  int v13; // [rsp+3Ch] [rbp-19Ch] BYREF
  int v14; // [rsp+40h] [rbp-198h] BYREF
  int v15; // [rsp+44h] [rbp-194h] BYREF
  int v16; // [rsp+48h] [rbp-190h] BYREF
  int v17; // [rsp+4Ch] [rbp-18Ch] BYREF
  int v18; // [rsp+50h] [rbp-188h] BYREF
  int v19; // [rsp+54h] [rbp-184h] BYREF
  int v20; // [rsp+58h] [rbp-180h] BYREF
  int v21; // [rsp+5Ch] [rbp-17Ch] BYREF
  int v22; // [rsp+60h] [rbp-178h] BYREF
  int v23; // [rsp+64h] [rbp-174h] BYREF
  int v24; // [rsp+68h] [rbp-170h] BYREF
  int v25; // [rsp+6Ch] [rbp-16Ch] BYREF
  int v26; // [rsp+70h] [rbp-168h] BYREF
  int v27; // [rsp+74h] [rbp-164h] BYREF
  int v28; // [rsp+78h] [rbp-160h] BYREF
  int v29; // [rsp+7Ch] [rbp-15Ch] BYREF
  int v30; // [rsp+80h] [rbp-158h] BYREF
  HLOCAL hMem; // [rsp+88h] [rbp-150h] BYREF
  HMODULE hLibModule; // [rsp+90h] [rbp-148h] BYREF
  __int64 v33; // [rsp+98h] [rbp-140h] BYREF
  __int64 v34; // [rsp+A0h] [rbp-138h] BYREF
  __int64 v35; // [rsp+A8h] [rbp-130h] BYREF
  LPCWSTR *v36[29]; // [rsp+B0h] [rbp-128h] BYREF
  const std::exception *v37; // [rsp+198h] [rbp-40h] BYREF
  __int128 v38; // [rsp+1A0h] [rbp-38h] BYREF
  __m128i si128; // [rsp+1B0h] [rbp-28h]

  v36[28] = (LPCWSTR *)-2LL;
  v11 = a1;
  hMem = 0;
  v12 = 0;
  v38 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v38) = 0;
  v33 = 0;
  v13 = 0;
  v15 = 0;
  v25 = 0;
  v17 = 0;
  v19 = 0;
  v21 = 0;
  v23 = 0;
  v14 = 0;
  v26 = 0;
  v24 = 3;
  v16 = 0;
  v30 = 0;
  v18 = 0;
  v27 = 0;
  v20 = 0;
  v28 = 0;
  v22 = 0;
  v29 = 0;
  hLibModule = 0;
  v34 = 0;
  v35 = 0;
  AslLogCallPrintf(3, "VelocityFeatureMatchingPlugin", 159, "Enter VelocityFeatureMatchingPlugin.");
  *v11 = 0;
  v36[0] = &a6;
  v36[1] = (LPCWSTR *)&v38;
  v36[2] = (LPCWSTR *)&v11;
  v36[3] = (LPCWSTR *)&a5;
  v36[4] = (LPCWSTR *)&hMem;
  v36[5] = (LPCWSTR *)&v12;
  v36[6] = (LPCWSTR *)&v33;
  v36[7] = (LPCWSTR *)&v13;
  v36[8] = (LPCWSTR *)&v14;
  v36[9] = (LPCWSTR *)&v15;
  v36[10] = (LPCWSTR *)&v16;
  v36[11] = (LPCWSTR *)&v17;
  v36[12] = (LPCWSTR *)&v18;
  v36[13] = (LPCWSTR *)&v19;
  v36[14] = (LPCWSTR *)&v20;
  v36[15] = (LPCWSTR *)&v21;
  v36[16] = (LPCWSTR *)&v22;
  v36[17] = (LPCWSTR *)&v23;
  v36[18] = (LPCWSTR *)&v24;
  v36[19] = (LPCWSTR *)&v25;
  v36[20] = (LPCWSTR *)&hLibModule;
  v36[21] = (LPCWSTR *)&v34;
  v36[22] = (LPCWSTR *)&v26;
  v36[23] = (LPCWSTR *)&v35;
  v36[24] = (LPCWSTR *)&v27;
  v36[25] = (LPCWSTR *)&v28;
  v36[26] = (LPCWSTR *)&v29;
  v36[27] = (LPCWSTR *)&v30;
  lambda_43e160a371d523193c0f9f0bdc889da7_::operator()(v36);
  if ( hMem )
  {
    LocalFree(hMem);
    hMem = 0;
  }
  if ( hLibModule )
  {
    FreeLibrary(hLibModule);
    hLibModule = 0;
  }
  try
  {
    v8 = &v38;
    if ( si128.m128i_i64[1] > 7uLL )
      LODWORD(v8) = v38;
    AppCompatUtility::AddCacheMatchingPlugin(
      (AppCompatUtility *)(unsigned int)*v11,
      (int)v8,
      (const unsigned __int16 *)(unsigned int)a5,
      v7);
  }
  catch ( const std::exception *v37 )
  {
    v10 = (const char *)(*(__int64 (__fastcall **)(const std::exception *))(*(_QWORD *)v37 + 8LL))(v37);
    AslLogCallPrintf(1, "VelocityFeatureMatchingPlugin", 553, "Exception: %s", v10);
  }
  catch ( ... )
  {
    AslLogCallPrintf(1, "VelocityFeatureMatchingPlugin", 557, "Unhandled exception.");
  }
  AslLogCallPrintf(3, "VelocityFeatureMatchingPlugin", 560, "VelocityFeatureMatchingPlugin Matched = %d", *v11);
  std::wstring::~wstring(&v38);
  return 1;
}

```

## disassembly

```asm
0x1800312b0  mov     r11, rsp
0x1800312b3  push    rbx
0x1800312b4  sub     rsp, 1D0h
0x1800312bb  mov     qword ptr [r11-48h], 0FFFFFFFFFFFFFFFEh
0x1800312c3  mov     rax, cs:__security_cookie
0x1800312ca  xor     rax, rsp
0x1800312cd  mov     [rsp+1D8h+var_18], rax
0x1800312d5  mov     [rsp+1D8h+var_1A8], rcx
0x1800312da  xor     ebx, ebx
0x1800312dc  mov     [r11-150h], rbx
0x1800312e3  mov     [rsp+1D8h+var_1A0], ebx
0x1800312e7  xorps   xmm0, xmm0
0x1800312ea  movups  xmmword ptr [r11-38h], xmm0
0x1800312ef  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800312f7  movdqu  xmmword ptr [r11-28h], xmm1
0x1800312fd  mov     [r11-38h], bx
0x180031302  mov     [r11-140h], rbx
0x180031309  mov     [rsp+1D8h+var_19C], ebx
0x18003130d  mov     [rsp+1D8h+var_194], ebx
0x180031311  mov     [rsp+1D8h+var_16C], ebx
0x180031315  mov     [rsp+1D8h+var_18C], ebx
0x180031319  mov     [rsp+1D8h+var_184], ebx
0x18003131d  mov     [rsp+1D8h+var_17C], ebx
0x180031321  mov     [rsp+1D8h+var_174], ebx
0x180031325  mov     [rsp+1D8h+var_198], ebx
0x180031329  mov     [rsp+1D8h+var_168], ebx
0x18003132d  mov     [rsp+1D8h+var_170], 3
0x180031335  mov     [rsp+1D8h+var_190], ebx
0x180031339  mov     [rsp+1D8h+var_158], ebx
0x180031340  mov     [rsp+1D8h+var_188], ebx
0x180031344  mov     [rsp+1D8h+var_164], ebx
0x180031348  mov     [rsp+1D8h+var_180], ebx
0x18003134c  mov     [rsp+1D8h+var_160], ebx
0x180031350  mov     [rsp+1D8h+var_178], ebx
0x180031354  mov     [rsp+1D8h+var_15C], ebx
0x180031358  mov     [r11-148h], rbx
0x18003135f  mov     [r11-138h], rbx
0x180031366  mov     [r11-130h], rbx
0x18003136d  lea     r9, aEnterVelocityf; "Enter VelocityFeatureMatchingPlugin."
0x180031374  mov     r8d, 9Fh
0x18003137a  lea     rdx, aVelocityfeatur_1; "VelocityFeatureMatchingPlugin"
0x180031381  lea     ecx, [rbx+3]
0x180031384  call    AslLogCallPrintf
0x180031389  mov     rax, [rsp+1D8h+var_1A8]
0x18003138e  mov     [rax], ebx
0x180031390  lea     rax, [rsp+1D8h+arg_28]
0x180031398  mov     [rsp+1D8h+var_128], rax
0x1800313a0  lea     rax, [rsp+1D8h+var_38]
0x1800313a8  mov     [rsp+1D8h+var_120], rax
0x1800313b0  lea     rax, [rsp+1D8h+var_1A8]
0x1800313b5  mov     [rsp+1D8h+var_118], rax
0x1800313bd  lea     rax, [rsp+1D8h+arg_20]
0x1800313c5  mov     [rsp+1D8h+var_110], rax
0x1800313cd  lea     rax, [rsp+1D8h+hMem]
0x1800313d5  mov     [rsp+1D8h+var_108], rax
0x1800313dd  lea     rax, [rsp+1D8h+var_1A0]
0x1800313e2  mov     [rsp+1D8h+var_100], rax
0x1800313ea  lea     rax, [rsp+1D8h+var_140]
0x1800313f2  mov     [rsp+1D8h+var_F8], rax
0x1800313fa  lea     rax, [rsp+1D8h+var_19C]
0x1800313ff  mov     [rsp+1D8h+var_F0], rax
0x180031407  lea     rax, [rsp+1D8h+var_198]
0x18003140c  mov     [rsp+1D8h+var_E8], rax
0x180031414  lea     rax, [rsp+1D8h+var_194]
0x180031419  mov     [rsp+1D8h+var_E0], rax
0x180031421  lea     rax, [rsp+1D8h+var_190]
0x180031426  mov     [rsp+1D8h+var_D8], rax
0x18003142e  lea     rax, [rsp+1D8h+var_18C]
0x180031433  mov     [rsp+1D8h+var_D0], rax
0x18003143b  lea     rax, [rsp+1D8h+var_188]
0x180031440  mov     [rsp+1D8h+var_C8], rax
0x180031448  lea     rax, [rsp+1D8h+var_184]
0x18003144d  mov     [rsp+1D8h+var_C0], rax
0x180031455  lea     rax, [rsp+1D8h+var_180]
0x18003145a  mov     [rsp+1D8h+var_B8], rax
0x180031462  lea     rax, [rsp+1D8h+var_17C]
0x180031467  mov     [rsp+1D8h+var_B0], rax
0x18003146f  lea     rax, [rsp+1D8h+var_178]
0x180031474  mov     [rsp+1D8h+var_A8], rax
0x18003147c  lea     rax, [rsp+1D8h+var_174]
0x180031481  mov     [rsp+1D8h+var_A0], rax
0x180031489  lea     rax, [rsp+1D8h+var_170]
0x18003148e  mov     [rsp+1D8h+var_98], rax
0x180031496  lea     rax, [rsp+1D8h+var_16C]
0x18003149b  mov     [rsp+1D8h+var_90], rax
0x1800314a3  lea     rax, [rsp+1D8h+hLibModule]
0x1800314ab  mov     [rsp+1D8h+var_88], rax
0x1800314b3  lea     rax, [rsp+1D8h+var_138]
0x1800314bb  mov     [rsp+1D8h+var_80], rax
0x1800314c3  lea     rax, [rsp+1D8h+var_168]
0x1800314c8  mov     [rsp+1D8h+var_78], rax
0x1800314d0  lea     rax, [rsp+1D8h+var_130]
0x1800314d8  mov     [rsp+1D8h+var_70], rax
0x1800314e0  lea     rax, [rsp+1D8h+var_164]
0x1800314e5  mov     [rsp+1D8h+var_68], rax
0x1800314ed  lea     rax, [rsp+1D8h+var_160]
0x1800314f2  mov     [rsp+1D8h+var_60], rax
0x1800314fa  lea     rax, [rsp+1D8h+var_15C]
0x1800314ff  mov     [rsp+1D8h+var_58], rax
0x180031507  lea     rax, [rsp+1D8h+var_158]
0x18003150f  mov     [rsp+1D8h+var_50], rax
0x180031517  lea     rcx, [rsp+1D8h+var_128]
0x18003151f  call    _lambda_43e160a371d523193c0f9f0bdc889da7___operator__
0x180031524  mov     rcx, [rsp+1D8h+hMem]; hMem
0x18003152c  test    rcx, rcx
0x18003152f  jz      short loc_18003153F
0x180031531  call    cs:__imp_LocalFree
0x180031537  mov     [rsp+1D8h+hMem], rbx
0x18003153f  mov     rcx, [rsp+1D8h+hLibModule]; hLibModule
0x180031547  test    rcx, rcx
0x18003154a  jz      short loc_18003155A
0x18003154c  call    cs:__imp_FreeLibrary
0x180031552  mov     [rsp+1D8h+hLibModule], rbx
0x18003155a  lea     rdx, [rsp+1D8h+var_38]
0x180031562  cmp     [rsp+1D8h+var_20], 7
0x18003156b  cmova   rdx, qword ptr [rsp+1D8h+var_38]; int
0x180031574  mov     r8d, dword ptr [rsp+1D8h+arg_20]; unsigned __int16 *
0x18003157c  mov     rcx, [rsp+1D8h+var_1A8]
0x180031581  mov     ecx, [rcx]; this
0x180031583  call    ?AddCacheMatchingPlugin@AppCompatUtility@@YAXHPEBGK@Z; AppCompatUtility::AddCacheMatchingPlugin(int,ushort const *,ulong)
0x180031588  nop
0x180031589  mov     rax, [rsp+1D8h+var_1A8]
0x18003158e  mov     r8d, [rax]
0x180031591  mov     [rsp+1D8h+var_1B8], r8d
0x180031596  lea     r9, aVelocityfeatur_0; "VelocityFeatureMatchingPlugin Matched ="...
0x18003159d  mov     r8d, 230h
0x1800315a3  lea     rdx, aVelocityfeatur_1; "VelocityFeatureMatchingPlugin"
0x1800315aa  mov     ecx, 3
0x1800315af  call    AslLogCallPrintf
0x1800315b4  nop
0x1800315b5  lea     rcx, [rsp+1D8h+var_38]; void *
0x1800315bd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800315c2  mov     eax, 1
0x1800315c7  mov     rcx, [rsp+1D8h+var_18]
0x1800315cf  xor     rcx, rsp; StackCookie
0x1800315d2  call    __security_check_cookie
0x1800315d7  add     rsp, 1D0h
0x1800315de  pop     rbx
0x1800315df  retn
0x1800315e0  jmp     short loc_180031589
```
