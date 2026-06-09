# FSCreateGlobalConfigurationKey

- ea: `0x18003701c`
- end: `0x1800372f6`
- name: `FSCreateGlobalConfigurationKey`
- size: `730`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `2`
- callee_count: `14`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x180039cb4`
- `0x18003b9a4`

## callees

- `0x1800019f0`
- `0x180002346`
- `0x180005f98`
- `0x180006a98`
- `0x18000723c`
- `0x18000d1e0`
- `0x18000d3d8`
- `0x18000d498`
- `0x18000e25c`
- `0x180032d24`
- `0x18003701c`
- `0x180041474`
- `0x180042988`
- `0x18004d010`

## string_xrefs

- `0x180037124`: `FRAMESERVER_CONFIGURATION_ALL_APPS`
- `0x1800371a5`: `FRAMESERVER_CONFIGURATION_ALL_APPS`

## pseudocode

```c
__int64 __fastcall FSCreateGlobalConfigurationKey(const char *a1, __int64 a2, __int64 a3)
{
  const char *v5; // r9
  unsigned int v6; // edi
  __int64 v7; // rdx
  int v8; // eax
  __int64 v9; // rdx
  const struct std::nothrow_t *unique; // rax
  unsigned __int16 *v11; // rbx
  struct IFSConfigurationKey *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  unsigned int v16; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v17; // [rsp+44h] [rbp-BCh] BYREF
  struct IFSConfigurationKey *v18; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v19; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v20; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 v21[264]; // [rsp+60h] [rbp-A0h] BYREF

  v19 = 0;
  v16 = 0;
  v18 = 0;
  memset_0(v21, 0, 0x208u);
  v17 = 0;
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
  {
    v5 = a1;
    if ( !a1 )
      v5 = L"<nullptr>";
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 27), 333, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, v5);
  }
  if ( !a1 )
  {
    v6 = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_30;
    v7 = 334;
    goto LABEL_8;
  }
  v8 = FSGetUniqueSymbolicName((const unsigned __int16 *)a1, v21, 0x104u, &v17);
  v6 = v8;
  if ( v8 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_30;
    v9 = 335;
LABEL_29:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, 0, v8);
    goto LABEL_30;
  }
  v8 = FSTagPackageFamilyName(L"FRAMESERVER_CONFIGURATION_ALL_APPS", 0, 0, &v16);
  v6 = v8;
  if ( v8 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_30;
    v9 = 336;
    goto LABEL_29;
  }
  unique = (const struct std::nothrow_t *)wil::make_unique_nothrow<unsigned short [0]>(&v20, v16);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=((void **)&v19, unique);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v20);
  v11 = v19;
  if ( !v19 )
  {
    v6 = -2147024882;
    if ( g_wppLevels )
    {
      v7 = 337;
LABEL_8:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, 0, v6);
    }
LABEL_30:
    if ( byte_18005E5A5 )
    {
      v13 = 341;
      v14 = v6;
LABEL_34:
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), v13, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, v14);
      goto LABEL_35;
    }
    goto LABEL_35;
  }
  v8 = FSTagPackageFamilyName(L"FRAMESERVER_CONFIGURATION_ALL_APPS", v19, v16, &v16);
  v6 = v8;
  if ( v8 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_30;
    v9 = 338;
    goto LABEL_29;
  }
  v12 = v18;
  v18 = 0;
  if ( v12 )
    (*(void (__fastcall **)(struct IFSConfigurationKey *))(*(_QWORD *)v12 + 16LL))(v12);
  v8 = FSConfigurationKey::CreateKey(v21, v17, v11, v16, L"S-1-1-0", 8u, &v18);
  v6 = v8;
  if ( v8 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_30;
    v9 = 339;
    goto LABEL_29;
  }
  v8 = (**(__int64 (__fastcall ***)(struct IFSConfigurationKey *, GUID *, __int64))v18)(
         v18,
         &GUID_1cc45e78_17a7_4bce_afd1_07255c4b8744,
         a3);
  v6 = v8;
  if ( v8 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_30;
    v9 = 340;
    goto LABEL_29;
  }
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
  {
    v13 = 342;
    v14 = (unsigned int)v8;
    goto LABEL_34;
  }
LABEL_35:
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v18);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v19);
  return v6;
}

```

## disassembly

```asm
0x18003701c  mov     [rsp-8+arg_8], rbx
0x180037021  mov     [rsp-8+arg_18], rsi
0x180037026  push    rbp
0x180037027  push    rdi
0x180037028  push    r15
0x18003702a  lea     rbp, [rsp-180h]
0x180037032  sub     rsp, 280h
0x180037039  mov     rax, cs:__security_cookie
0x180037040  xor     rax, rsp
0x180037043  mov     [rbp+190h+var_20], rax
0x18003704a  mov     rsi, r8
0x18003704d  mov     [rsp+290h+var_240], 0
0x180037056  mov     rbx, rcx
0x180037059  mov     [rsp+290h+var_250], 0
0x180037061  mov     r8d, 208h; Size
0x180037067  mov     [rsp+290h+var_248], 0
0x180037070  lea     rcx, [rsp+290h+var_230]; void *
0x180037075  xor     edx, edx; Val
0x180037077  call    memset_0
0x18003707c  mov     [rsp+290h+var_24C], 0
0x180037084  cmp     cs:byte_18005E5A5, 8
0x18003708b  lea     r15, WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids
0x180037092  jb      short loc_1800370C0
0x180037094  mov     rcx, cs:WPP_GLOBAL_Control
0x18003709b  lea     rax, aNullptr; "<nullptr>"
0x1800370a2  test    rbx, rbx
0x1800370a5  mov     r9, rbx
0x1800370a8  mov     edx, 14Dh
0x1800370ad  mov     r8, r15
0x1800370b0  cmovz   r9, rax
0x1800370b4  mov     rcx, [rcx+0D8h]
0x1800370bb  call    WPP_SF_S
0x1800370c0  test    rbx, rbx
0x1800370c3  jnz     short loc_1800370E5
0x1800370c5  mov     edi, 80070057h
0x1800370ca  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800370d1  jb      loc_18003727F
0x1800370d7  mov     edx, 14Eh
0x1800370dc  mov     dword ptr [rsp+290h+var_270], edi
0x1800370e0  jmp     loc_180037269
0x1800370e5  lea     r9, [rsp+290h+var_24C]; unsigned int *
0x1800370ea  mov     r8d, 104h; unsigned int
0x1800370f0  lea     rdx, [rsp+290h+var_230]; unsigned __int16 *
0x1800370f5  mov     rcx, rbx; unsigned __int16 *
0x1800370f8  call    ?FSGetUniqueSymbolicName@@YAJPEBGPEAGKPEAK@Z; FSGetUniqueSymbolicName(ushort const *,ushort *,ulong,ulong *)
0x1800370fd  mov     edi, eax
0x1800370ff  test    eax, eax
0x180037101  jns     short loc_18003711A
0x180037103  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003710a  jb      loc_18003727F
0x180037110  mov     edx, 14Fh
0x180037115  jmp     loc_180037265
0x18003711a  lea     r9, [rsp+290h+var_250]; unsigned int *
0x18003711f  xor     r8d, r8d; unsigned int
0x180037122  xor     edx, edx; unsigned __int16 *
0x180037124  lea     rcx, aFrameserverCon; "FRAMESERVER_CONFIGURATION_ALL_APPS"
0x18003712b  call    ?FSTagPackageFamilyName@@YAJPEBGPEAGKPEAK@Z; FSTagPackageFamilyName(ushort const *,ushort *,ulong,ulong *)
0x180037130  mov     edi, eax
0x180037132  test    eax, eax
0x180037134  jns     short loc_18003714D
0x180037136  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003713d  jb      loc_18003727F
0x180037143  mov     edx, 150h
0x180037148  jmp     loc_180037265
0x18003714d  mov     edx, [rsp+290h+var_250]
0x180037151  lea     rcx, [rsp+290h+var_238]
0x180037156  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x18003715b  mov     rdx, rax
0x18003715e  lea     rcx, [rsp+290h+var_240]
0x180037163  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x180037168  lea     rcx, [rsp+290h+var_238]
0x18003716d  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x180037172  mov     rbx, [rsp+290h+var_240]
0x180037177  test    rbx, rbx
0x18003717a  jnz     short loc_180037198
0x18003717c  mov     edi, 8007000Eh
0x180037181  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180037188  jb      loc_18003727F
0x18003718e  mov     edx, 151h
0x180037193  jmp     loc_1800370DC
0x180037198  mov     r8d, [rsp+290h+var_250]; unsigned int
0x18003719d  lea     r9, [rsp+290h+var_250]; unsigned int *
0x1800371a2  mov     rdx, rbx; unsigned __int16 *
0x1800371a5  lea     rcx, aFrameserverCon; "FRAMESERVER_CONFIGURATION_ALL_APPS"
0x1800371ac  call    ?FSTagPackageFamilyName@@YAJPEBGPEAGKPEAK@Z; FSTagPackageFamilyName(ushort const *,ushort *,ulong,ulong *)
0x1800371b1  mov     edi, eax
0x1800371b3  test    eax, eax
0x1800371b5  jns     short loc_1800371CE
0x1800371b7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800371be  jb      loc_18003727F
0x1800371c4  mov     edx, 152h
0x1800371c9  jmp     loc_180037265
0x1800371ce  mov     rcx, [rsp+290h+var_248]
0x1800371d3  mov     [rsp+290h+var_248], 0
0x1800371dc  test    rcx, rcx
0x1800371df  jz      short loc_1800371ED
0x1800371e1  mov     rax, [rcx]
0x1800371e4  mov     rax, [rax+10h]
0x1800371e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800371ed  mov     r9d, [rsp+290h+var_250]; unsigned int
0x1800371f2  lea     rax, [rsp+290h+var_248]
0x1800371f7  mov     edx, [rsp+290h+var_24C]; unsigned int
0x1800371fb  lea     rcx, [rsp+290h+var_230]; unsigned __int16 *
0x180037200  mov     [rsp+290h+var_260], rax; struct IFSConfigurationKey **
0x180037205  mov     r8, rbx; unsigned __int16 *
0x180037208  lea     rax, aS110; "S-1-1-0"
0x18003720f  mov     [rsp+290h+var_268], 8; unsigned int
0x180037217  mov     [rsp+290h+var_270], rax; unsigned __int16 *
0x18003721c  call    ?CreateKey@FSConfigurationKey@@SAJPEBGK0K0KPEAPEAUIFSConfigurationKey@@@Z; FSConfigurationKey::CreateKey(ushort const *,ulong,ushort const *,ulong,ushort const *,ulong,IFSConfigurationKey * *)
0x180037221  mov     edi, eax
0x180037223  test    eax, eax
0x180037225  jns     short loc_180037237
0x180037227  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003722e  jb      short loc_18003727F
0x180037230  mov     edx, 153h
0x180037235  jmp     short loc_180037265
0x180037237  mov     rcx, [rsp+290h+var_248]
0x18003723c  lea     rdx, _GUID_1cc45e78_17a7_4bce_afd1_07255c4b8744
0x180037243  mov     r8, rsi
0x180037246  mov     rax, [rcx]
0x180037249  mov     rax, [rax]
0x18003724c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037251  mov     edi, eax
0x180037253  test    eax, eax
0x180037255  jns     short loc_180037292
0x180037257  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003725e  jb      short loc_18003727F
0x180037260  mov     edx, 154h
0x180037265  mov     dword ptr [rsp+290h+var_270], eax
0x180037269  mov     rcx, cs:WPP_GLOBAL_Control
0x180037270  xor     r9d, r9d
0x180037273  mov     r8, r15
0x180037276  mov     rcx, [rcx+10h]
0x18003727a  call    WPP_SF_qD
0x18003727f  cmp     cs:byte_18005E5A5, 1
0x180037286  jb      short loc_1800372B9
0x180037288  mov     edx, 155h
0x18003728d  mov     r9d, edi
0x180037290  jmp     short loc_1800372A3
0x180037292  cmp     cs:byte_18005E5A5, 8
0x180037299  jb      short loc_1800372B9
0x18003729b  mov     edx, 156h
0x1800372a0  mov     r9d, eax
0x1800372a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800372aa  mov     r8, r15
0x1800372ad  mov     rcx, [rcx+0D8h]
0x1800372b4  call    WPP_SF_d
0x1800372b9  lea     rcx, [rsp+290h+var_248]
0x1800372be  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x1800372c3  lea     rcx, [rsp+290h+var_240]
0x1800372c8  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x1800372cd  mov     eax, edi
0x1800372cf  mov     rcx, [rbp+190h+var_20]
0x1800372d6  xor     rcx, rsp; StackCookie
0x1800372d9  call    __security_check_cookie
0x1800372de  lea     r11, [rsp+290h+var_10]
0x1800372e6  mov     rbx, [r11+28h]
0x1800372ea  mov     rsi, [r11+38h]
0x1800372ee  mov     rsp, r11
0x1800372f1  pop     r15
0x1800372f3  pop     rdi
0x1800372f4  pop     rbp
0x1800372f5  retn
```
