# FSMLoadPublicDeviceConfigurations

- ea: `0x180039fbc`
- end: `0x18003a2d2`
- name: `FSMLoadPublicDeviceConfigurations`
- size: `790`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800262b4`
- `0x180028670`

## callees

- `0x1800019f0`
- `0x180005f98`
- `0x180006a68`
- `0x180006a98`
- `0x180006cc0`
- `0x18000723c`
- `0x18000d1e0`
- `0x18000d3d8`
- `0x18000d498`
- `0x180039fbc`
- `0x18003cb1c`
- `0x1800407b0`
- `0x18004d010`

## import_xrefs

- `MFPlat!MFCreateCollection` at `0x18003a090`
- `MFPlat!MFCreateCollection` at `0x18003a090`

## pseudocode

```c
__int64 __fastcall FSMLoadPublicDeviceConfigurations(char *a1, __int64 *a2)
{
  const char *v4; // r9
  unsigned int v5; // ebx
  __int64 v6; // rdx
  int v7; // eax
  __int64 v8; // rdx
  unsigned int v9; // esi
  const struct std::nothrow_t *unique; // rax
  unsigned int v11; // r14d
  unsigned int v12; // esi
  const struct _GUID *v13; // r8
  int v14; // eax
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v18; // rdx
  void *v19; // [rsp+30h] [rbp-40h] BYREF
  __int64 v20; // [rsp+38h] [rbp-38h] BYREF
  unsigned __int8 *v21; // [rsp+40h] [rbp-30h] BYREF
  __int64 v22; // [rsp+48h] [rbp-28h] BYREF
  DEVPROPKEY PropertyKey; // [rsp+50h] [rbp-20h] BYREF

  v20 = 0;
  v21 = 0;
  LODWORD(v19) = 0;
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
  {
    v4 = a1;
    if ( !a1 )
      v4 = L"<nullptr>";
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 27), 317, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, v4);
  }
  if ( !a2 )
  {
    v5 = -2147467261;
    if ( !g_wppLevels )
    {
LABEL_36:
      if ( !byte_18005E5A5 )
        goto LABEL_29;
      v16 = 324;
      goto LABEL_28;
    }
    v6 = 318;
LABEL_8:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, 0, v5);
    goto LABEL_36;
  }
  *a2 = 0;
  v20 = 0;
  v7 = MFCreateCollection(&v20);
  v5 = v7;
  if ( v7 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_36;
    v8 = 319;
LABEL_12:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, 0, v7);
    goto LABEL_36;
  }
  PropertyKey.pid = 2;
  PropertyKey.fmtid = FrameServerConfigurationPublicFMTGUID;
  if ( (int)FSGetDeviceInterfaceProperty2((LPCWSTR)a1, &PropertyKey, 0x1003u, 0, 0, (unsigned int *)&v19) >= 0 )
  {
    v9 = (unsigned int)v19;
    if ( (_DWORD)v19 )
    {
      if ( ((unsigned __int8)v19 & 0x3F) == 0 )
      {
        unique = (const struct std::nothrow_t *)wil::make_unique_nothrow<unsigned char [0]>(&v22, (unsigned int)v19);
        wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=(
          (void **)&v21,
          unique);
        wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v22);
        if ( !v21 )
        {
          v5 = -2147024882;
          if ( !g_wppLevels )
            goto LABEL_36;
          v6 = 320;
          goto LABEL_8;
        }
        PropertyKey.pid = 2;
        PropertyKey.fmtid = FrameServerConfigurationPublicFMTGUID;
        v7 = FSGetDeviceInterfaceProperty2((LPCWSTR)a1, &PropertyKey, 0x1003u, v21, v9, (unsigned int *)&v19);
        v5 = v7;
        if ( v7 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_36;
          v8 = 321;
          goto LABEL_12;
        }
        v11 = 0;
        v12 = (unsigned int)v19 >> 6;
        if ( (unsigned int)v19 >> 6 )
        {
          while ( 1 )
          {
            v19 = 0;
            wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v19);
            v14 = FSConfiguration::CreatePublicConfiguration(
                    (GUID *)a1,
                    (void **)&v21[64 * (unsigned __int64)v11],
                    v13,
                    &v19);
            v5 = v14;
            if ( v14 < 0 )
              break;
            v14 = (*(__int64 (__fastcall **)(__int64, void *))(*(_QWORD *)v20 + 40LL))(v20, v19);
            v5 = v14;
            if ( v14 < 0 )
            {
              if ( !g_wppLevels )
                goto LABEL_35;
              v18 = 323;
              goto LABEL_34;
            }
            wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v19);
            if ( ++v11 >= v12 )
              goto LABEL_26;
          }
          if ( !g_wppLevels )
            goto LABEL_35;
          v18 = 322;
LABEL_34:
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, 0, v14);
LABEL_35:
          wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v19);
          goto LABEL_36;
        }
      }
    }
  }
LABEL_26:
  v15 = v20;
  v20 = 0;
  *a2 = v15;
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
  {
    v16 = 325;
LABEL_28:
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), v16, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, v5);
  }
LABEL_29:
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v21);
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(&v20);
  return v5;
}

```

## disassembly

```asm
0x180039fbc  mov     [rsp-28h+arg_10], rbx
0x180039fc1  push    rbp
0x180039fc2  push    rsi
0x180039fc3  push    rdi
0x180039fc4  push    r14
0x180039fc6  push    r15
0x180039fc8  mov     rbp, rsp
0x180039fcb  sub     rsp, 70h
0x180039fcf  mov     rax, cs:__security_cookie
0x180039fd6  xor     rax, rsp
0x180039fd9  mov     [rbp+var_8], rax
0x180039fdd  mov     r15, rcx
0x180039fe0  mov     rdi, rdx
0x180039fe3  xor     ecx, ecx
0x180039fe5  mov     [rbp+var_38], rcx
0x180039fe9  mov     [rbp+var_30], rcx
0x180039fed  mov     dword ptr [rbp+var_40], ecx
0x180039ff0  cmp     cs:byte_18005E5A5, 8
0x180039ff7  jb      short loc_18003A02D
0x180039ff9  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a000  lea     rax, aNullptr; "<nullptr>"
0x18003a007  test    r15, r15
0x18003a00a  lea     r8, WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids
0x18003a011  mov     r9, r15
0x18003a014  mov     edx, 13Dh
0x18003a019  cmovz   r9, rax
0x18003a01d  mov     rcx, [rcx+0D8h]
0x18003a024  call    WPP_SF_S
0x18003a029  mov     rcx, [rbp+var_38]
0x18003a02d  test    rdi, rdi
0x18003a030  jnz     short loc_18003A06C
0x18003a032  mov     ebx, 80004003h
0x18003a037  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003a03e  jb      loc_18003A2BB
0x18003a044  mov     edx, 13Eh
0x18003a049  mov     [rsp+70h+var_50], ebx
0x18003a04d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a054  lea     r8, WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids
0x18003a05b  xor     r9d, r9d
0x18003a05e  mov     rcx, [rcx+10h]
0x18003a062  call    WPP_SF_qD
0x18003a067  jmp     loc_18003A2BB
0x18003a06c  mov     qword ptr [rdi], 0
0x18003a073  mov     [rbp+var_38], 0
0x18003a07b  test    rcx, rcx
0x18003a07e  jz      short loc_18003A08C
0x18003a080  mov     rax, [rcx]
0x18003a083  mov     rax, [rax+10h]
0x18003a087  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a08c  lea     rcx, [rbp+var_38]
0x18003a090  call    cs:__imp_MFCreateCollection
0x18003a096  mov     ebx, eax
0x18003a098  test    eax, eax
0x18003a09a  jns     short loc_18003A0B4
0x18003a09c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003a0a3  jb      loc_18003A2BB
0x18003a0a9  mov     edx, 13Fh
0x18003a0ae  mov     [rsp+70h+var_50], eax
0x18003a0b2  jmp     short loc_18003A04D
0x18003a0b4  movups  xmm0, xmmword ptr cs:?FrameServerConfigurationPublicFMTGUID@@3U_GUID@@B.Data1; _GUID const FrameServerConfigurationPublicFMTGUID ...
0x18003a0bb  lea     rax, [rbp+var_40]
0x18003a0bf  mov     r14d, 2
0x18003a0c5  mov     [rsp+70h+var_48], rax; unsigned int *
0x18003a0ca  lea     rdx, [rbp+PropertyKey]; PropertyKey
0x18003a0ce  xor     r9d, r9d; unsigned __int8 *
0x18003a0d1  mov     [rbp+PropertyKey.pid], r14d
0x18003a0d5  mov     r8d, 1003h; unsigned int
0x18003a0db  mov     [rsp+70h+var_50], 0; unsigned int
0x18003a0e3  mov     rcx, r15; pszDeviceInterface
0x18003a0e6  movdqu  xmmword ptr [rbp+PropertyKey.fmtid.Data1], xmm0
0x18003a0eb  call    ?FSGetDeviceInterfaceProperty2@@YAJPEBGAEBU_DEVPROPKEY@@KPEAEKPEAK@Z; FSGetDeviceInterfaceProperty2(ushort const *,_DEVPROPKEY const &,ulong,uchar *,ulong,ulong *)
0x18003a0f0  test    eax, eax
0x18003a0f2  js      loc_18003A20A
0x18003a0f8  mov     esi, dword ptr [rbp+var_40]
0x18003a0fb  test    esi, esi
0x18003a0fd  jz      loc_18003A20A
0x18003a103  test    sil, 3Fh
0x18003a107  jnz     loc_18003A20A
0x18003a10d  mov     edx, esi
0x18003a10f  lea     rcx, [rbp+var_28]
0x18003a113  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x18003a118  mov     rdx, rax
0x18003a11b  lea     rcx, [rbp+var_30]
0x18003a11f  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x18003a124  lea     rcx, [rbp+var_28]
0x18003a128  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x18003a12d  cmp     [rbp+var_30], 0
0x18003a132  jnz     short loc_18003A150
0x18003a134  mov     ebx, 8007000Eh
0x18003a139  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003a140  jb      loc_18003A2BB
0x18003a146  mov     edx, 140h
0x18003a14b  jmp     loc_18003A049
0x18003a150  movups  xmm0, xmmword ptr cs:?FrameServerConfigurationPublicFMTGUID@@3U_GUID@@B.Data1; _GUID const FrameServerConfigurationPublicFMTGUID ...
0x18003a157  mov     r9, [rbp+var_30]; unsigned __int8 *
0x18003a15b  lea     rax, [rbp+var_40]
0x18003a15f  mov     [rsp+70h+var_48], rax; unsigned int *
0x18003a164  lea     rdx, [rbp+PropertyKey]; PropertyKey
0x18003a168  mov     r8d, 1003h; unsigned int
0x18003a16e  mov     [rbp+PropertyKey.pid], r14d
0x18003a172  mov     rcx, r15; pszDeviceInterface
0x18003a175  mov     [rsp+70h+var_50], esi; unsigned int
0x18003a179  movdqu  xmmword ptr [rbp+PropertyKey.fmtid.Data1], xmm0
0x18003a17e  call    ?FSGetDeviceInterfaceProperty2@@YAJPEBGAEBU_DEVPROPKEY@@KPEAEKPEAK@Z; FSGetDeviceInterfaceProperty2(ushort const *,_DEVPROPKEY const &,ulong,uchar *,ulong,ulong *)
0x18003a183  mov     ebx, eax
0x18003a185  test    eax, eax
0x18003a187  jns     short loc_18003A1A0
0x18003a189  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003a190  jb      loc_18003A2BB
0x18003a196  mov     edx, 141h
0x18003a19b  jmp     loc_18003A0AE
0x18003a1a0  mov     esi, dword ptr [rbp+var_40]
0x18003a1a3  xor     r14d, r14d
0x18003a1a6  shr     esi, 6
0x18003a1a9  test    esi, esi
0x18003a1ab  jz      short loc_18003A20A
0x18003a1ad  lea     rcx, [rbp+var_40]
0x18003a1b1  mov     [rbp+var_40], 0
0x18003a1b9  call    ?reset@?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(void)
0x18003a1be  mov     edx, r14d
0x18003a1c1  lea     r9, [rbp+var_40]; void **
0x18003a1c5  shl     rdx, 6
0x18003a1c9  mov     rcx, r15; unsigned __int16 *
0x18003a1cc  add     rdx, [rbp+var_30]; struct FSCFG_ENTRY2 *
0x18003a1d0  call    ?CreatePublicConfiguration@FSConfiguration@@SAJPEBGAEBUFSCFG_ENTRY2@@AEBU_GUID@@PEAPEAX@Z; FSConfiguration::CreatePublicConfiguration(ushort const *,FSCFG_ENTRY2 const &,_GUID const &,void * *)
0x18003a1d5  mov     ebx, eax
0x18003a1d7  test    eax, eax
0x18003a1d9  js      loc_18003A286
0x18003a1df  mov     rcx, [rbp+var_38]
0x18003a1e3  mov     rdx, [rbp+var_40]
0x18003a1e7  mov     rax, [rcx]
0x18003a1ea  mov     rax, [rax+28h]
0x18003a1ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a1f3  mov     ebx, eax
0x18003a1f5  test    eax, eax
0x18003a1f7  js      short loc_18003A276
0x18003a1f9  lea     rcx, [rbp+var_40]
0x18003a1fd  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x18003a202  inc     r14d
0x18003a205  cmp     r14d, esi
0x18003a208  jb      short loc_18003A1AD
0x18003a20a  mov     rax, [rbp+var_38]
0x18003a20e  xor     ecx, ecx
0x18003a210  mov     [rbp+var_38], rcx
0x18003a214  mov     [rdi], rax
0x18003a217  cmp     cs:byte_18005E5A5, 8
0x18003a21e  jb      short loc_18003A242
0x18003a220  mov     edx, 145h
0x18003a225  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a22c  lea     r8, WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids
0x18003a233  mov     r9d, ebx
0x18003a236  mov     rcx, [rcx+0D8h]
0x18003a23d  call    WPP_SF_d
0x18003a242  lea     rcx, [rbp+var_30]
0x18003a246  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x18003a24b  lea     rcx, [rbp+var_38]
0x18003a24f  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x18003a254  mov     eax, ebx
0x18003a256  mov     rcx, [rbp+var_8]
0x18003a25a  xor     rcx, rsp; StackCookie
0x18003a25d  call    __security_check_cookie
0x18003a262  mov     rbx, [rsp+70h+arg_10]
0x18003a26a  add     rsp, 70h
0x18003a26e  pop     r15
0x18003a270  pop     r14
0x18003a272  pop     rdi
0x18003a273  pop     rsi
0x18003a274  pop     rbp
0x18003a275  retn
0x18003a276  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003a27d  jb      short loc_18003A2B2
0x18003a27f  mov     edx, 143h
0x18003a284  jmp     short loc_18003A294
0x18003a286  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003a28d  jb      short loc_18003A2B2
0x18003a28f  mov     edx, 142h
0x18003a294  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a29b  lea     r8, WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids
0x18003a2a2  xor     r9d, r9d
0x18003a2a5  mov     [rsp+70h+var_50], eax
0x18003a2a9  mov     rcx, [rcx+10h]
0x18003a2ad  call    WPP_SF_qD
0x18003a2b2  lea     rcx, [rbp+var_40]
0x18003a2b6  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x18003a2bb  cmp     cs:byte_18005E5A5, 1
0x18003a2c2  jb      loc_18003A242
0x18003a2c8  mov     edx, 144h
0x18003a2cd  jmp     loc_18003A225
```
