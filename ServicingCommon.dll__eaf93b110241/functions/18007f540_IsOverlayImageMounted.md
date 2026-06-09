# IsOverlayImageMounted

- ea: `0x18007f540`
- end: `0x18007fa8b`
- name: `IsOverlayImageMounted`
- size: `1355`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18007faa0`
- `0x180080a50`

## callees

- `0x18001f5d4`
- `0x18001f660`
- `0x180022ef0`
- `0x180024120`
- `0x1800293a0`
- `0x18003e810`
- `0x180073840`
- `0x18007d93c`
- `0x18007dab4`
- `0x18007df6c`
- `0x18007e680`
- `0x18007e720`
- `0x18007ef14`
- `0x18007eff0`
- `0x18007f018`
- `0x18007f540`
- `0x1800a0020`

## string_xrefs

- `0x18007f5ba`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007f625`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007f6c2`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007f78b`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007f7bd`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007f9bf`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007fa2a`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007f655`: `ImageRootPath.assign(ImageRoot)`
- `0x18007f5d4`: `IsOverlayImageMounted`
- `0x18007f63f`: `IsOverlayImageMounted`
- `0x18007f6db`: `IsOverlayImageMounted`
- `0x18007f7a2`: `IsOverlayImageMounted`
- `0x18007f7d4`: `IsOverlayImageMounted`
- `0x18007f9d6`: `IsOverlayImageMounted`
- `0x18007fa41`: `IsOverlayImageMounted`
- `0x18007f9eb`: `ScratchRoot.assign(UnionInfo->ScratchRootPath, UnionInfo->ScratchRootLength / sizeof(WCHAR))`

## pseudocode

```c
__int64 __fastcall IsOverlayImageMounted(Windows::WCP::Implementation::Rtl *a1, _DWORD *a2)
{
  HINSTANCE *InitPointer; // rax
  unsigned int v5; // ebx
  unsigned int v6; // eax
  unsigned int v7; // eax
  char *v8; // rbx
  int v9; // eax
  void **v10; // rax
  const struct std::nothrow_t *v11; // rdx
  void *v12; // rcx
  char *v13; // rdi
  _QWORD *v14; // rdx
  unsigned int v15; // eax
  int FinalPath; // edi
  unsigned __int64 v17; // rdi
  int v18; // esi
  __int64 v20; // [rsp+20h] [rbp-E0h] BYREF
  __int64 (*v21)(void); // [rsp+28h] [rbp-D8h] BYREF
  char v22[8]; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v23[4]; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v24[4]; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v25[4]; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v26[4]; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v27[4]; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v28[4]; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD v29[4]; // [rsp+F8h] [rbp-8h] BYREF
  unsigned int v30; // [rsp+118h] [rbp+18h] BYREF
  int v31; // [rsp+11Ch] [rbp+1Ch] BYREF
  void *v32; // [rsp+120h] [rbp+20h] BYREF
  _QWORD v33[2]; // [rsp+128h] [rbp+28h] BYREF
  _WORD v34[8]; // [rsp+138h] [rbp+38h] BYREF
  wchar_t *String1; // [rsp+148h] [rbp+48h] BYREF
  char *v36; // [rsp+150h] [rbp+50h]
  _WORD v37[8]; // [rsp+158h] [rbp+58h] BYREF
  _QWORD v38[2]; // [rsp+168h] [rbp+68h] BYREF
  _WORD v39[8]; // [rsp+178h] [rbp+78h] BYREF
  wchar_t *String2; // [rsp+188h] [rbp+88h] BYREF
  char *v41; // [rsp+190h] [rbp+90h]
  _WORD v42[8]; // [rsp+198h] [rbp+98h] BYREF

  v31 = 0;
  *a2 = 0;
  Windows::WCP::Implementation::Rtl::InitializeWdscore(a1);
  v20 = 0;
  v21 = 0;
  InitPointer = (HINSTANCE *)Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(&v20);
  if ( IsOverlayAPISupported("EnumerateFileSystemUnions", InitPointer, &v21) )
  {
    v33[0] = v34;
    v33[1] = v34;
    v34[0] = 0;
    if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(v33, a1) )
    {
      v30 = 0;
      v7 = ((__int64 (__fastcall *)(_QWORD, _QWORD, unsigned int *))v21)(0, 0, &v30);
      if ( v7 == -2147023728 || v7 == -2147024894 || v7 == -2147467263 )
      {
LABEL_32:
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(v33);
        Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(&v20);
        return 0;
      }
      if ( (int)(v7 + 0x80000000) < 0 || v7 == -2147024774 )
      {
        utl::make_unique<unsigned char [0],0>(&v32, v30);
        v8 = (char *)v32;
        if ( v32 )
        {
          while ( 1 )
          {
            v9 = ((__int64 (__fastcall *)(_QWORD, char *, unsigned int *))v21)(v30, v8, &v30);
            if ( v9 == -2147023728 || v9 == -2147024894 )
            {
              utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(&v32);
              utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(v33);
              v5 = 0;
              goto LABEL_43;
            }
            if ( v9 >= 0 )
              break;
            if ( v9 != -2147024774 )
            {
              v27[2] = 378;
              v27[0] = "onecore\\base\\servicing\\overlayutil\\mount.cpp";
              v27[1] = "IsOverlayImageMounted";
              v27[3] = "hr";
              v15 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateHResult(
                      &v31,
                      v27,
                      (unsigned int)v9);
              goto LABEL_40;
            }
            v10 = (void **)utl::make_unique<unsigned char [0],0>(v22, v30);
            v12 = v8;
            v13 = (char *)*v10;
            *v10 = 0;
            v8 = v13;
            v32 = v13;
            if ( v12 )
              operator delete(v12, v11);
            utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(v22);
            if ( !v13 )
            {
              v26[2] = 383;
              v26[0] = "onecore\\base\\servicing\\overlayutil\\mount.cpp";
              v14 = v26;
              v26[1] = "IsOverlayImageMounted";
              v26[3] = "UnionBuffer";
              goto LABEL_39;
            }
          }
          String2 = v42;
          v41 = (char *)v42;
          v42[0] = 0;
          FinalPath = GetFinalPath(v33, (__int64)&String2);
          if ( FinalPath < 0 )
          {
            utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(&String2);
            utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(&v32);
            utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(v33);
            v5 = FinalPath;
            goto LABEL_43;
          }
          v17 = 0;
          if ( !v30 )
          {
LABEL_31:
            utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(&String2);
            utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(&v32);
            goto LABEL_32;
          }
          while ( 1 )
          {
            v38[0] = v39;
            v38[1] = v39;
            v39[0] = 0;
            if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                     v38,
                                     &v8[v17 + 26],
                                     (unsigned __int64)*(unsigned __int16 *)&v8[v17 + 24] >> 1) )
              break;
            String1 = v37;
            v36 = (char *)v37;
            v37[0] = 0;
            v18 = GetFinalPath(v38, (__int64)&String1);
            if ( v18 < 0 )
            {
              utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(&String1);
              utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(v38);
              utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(&String2);
              utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(&v32);
              utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(v33);
              v5 = v18;
              goto LABEL_43;
            }
            if ( v36 - (char *)String1 == v41 - (char *)String2 && !wcsicmp(String1, String2) )
            {
              *a2 = 1;
LABEL_34:
              utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(&String1);
              utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(v38);
              goto LABEL_31;
            }
            if ( !*(_DWORD *)&v8[v17] )
              goto LABEL_34;
            v17 += *(unsigned int *)&v8[v17];
            utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(&String1);
            utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(v38);
            if ( v17 >= v30 )
              goto LABEL_31;
          }
          v28[2] = 397;
          v28[0] = "onecore\\base\\servicing\\overlayutil\\mount.cpp";
          v28[1] = "IsOverlayImageMounted";
          v28[3] = "ScratchRoot.assign(UnionInfo->ScratchRootPath, UnionInfo->ScratchRootLength / sizeof(WCHAR))";
          v5 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                 &v31,
                 v28,
                 3221225495LL);
          utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(v38);
          utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(&String2);
        }
        else
        {
          v29[2] = 365;
          v29[0] = "onecore\\base\\servicing\\overlayutil\\mount.cpp";
          v14 = v29;
          v29[1] = "IsOverlayImageMounted";
          v29[3] = "UnionBuffer";
LABEL_39:
          v15 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                  &v31,
                  v14,
                  3221225495LL);
LABEL_40:
          v5 = v15;
        }
        utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(&v32);
        goto LABEL_42;
      }
      v25[2] = 362;
      v25[0] = "onecore\\base\\servicing\\overlayutil\\mount.cpp";
      v25[1] = "IsOverlayImageMounted";
      v25[3] = "hr";
      v6 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateHResult(
             &v31,
             v25,
             v7);
    }
    else
    {
      v24[2] = 344;
      v24[0] = "onecore\\base\\servicing\\overlayutil\\mount.cpp";
      v24[1] = "IsOverlayImageMounted";
      v24[3] = "ImageRootPath.assign(ImageRoot)";
      v6 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
             &v31,
             v24,
             3221225495LL);
    }
    v5 = v6;
LABEL_42:
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(v33);
    goto LABEL_43;
  }
  v23[2] = 340;
  v23[0] = "onecore\\base\\servicing\\overlayutil\\mount.cpp";
  v23[3] = 0;
  v23[1] = "IsOverlayImageMounted";
  v5 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
         &v31,
         v23,
         3221225659LL);
LABEL_43:
  Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(&v20);
  return v5;
}

```

## disassembly

```asm
0x18007f540  mov     [rsp-8+arg_10], rbx
0x18007f545  mov     [rsp-8+arg_18], rsi
0x18007f54a  push    rbp
0x18007f54b  push    rdi
0x18007f54c  push    r14
0x18007f54e  lea     rbp, [rsp-0B0h]
0x18007f556  sub     rsp, 1B0h
0x18007f55d  mov     rax, cs:__security_cookie
0x18007f564  xor     rax, rsp
0x18007f567  mov     [rbp+0C0h+var_18], rax
0x18007f56e  mov     r14, rdx
0x18007f571  mov     [rbp+0C0h+var_A4], 0
0x18007f578  mov     rbx, rcx
0x18007f57b  mov     dword ptr [rdx], 0
0x18007f581  call    ?InitializeWdscore@Rtl@Implementation@WCP@Windows@@YAXXZ; Windows::WCP::Implementation::Rtl::InitializeWdscore(void)
0x18007f586  lea     rcx, [rsp+1C0h+var_1A0]
0x18007f58b  mov     [rsp+1C0h+var_1A0], 0
0x18007f594  mov     [rsp+1C0h+var_198], 0
0x18007f59d  call    ?GetInitPointer@?$AutoComPtr@UICbsIdentity@@@Windows@@QEAAPEAPEAUICbsIdentity@@XZ; Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(void)
0x18007f5a2  mov     rdx, rax; HINSTANCE *
0x18007f5a5  lea     r8, [rsp+1C0h+var_198]; __int64 (**)(void)
0x18007f5aa  lea     rcx, aEnumeratefiles; "EnumerateFileSystemUnions"
0x18007f5b1  call    ?IsOverlayAPISupported@@YA_NQEBDPEAPEAUHINSTANCE__@@PEAP6A_JXZ@Z; IsOverlayAPISupported(char const * const,HINSTANCE__ * *,__int64 (**)(void))
0x18007f5b6  test    al, al
0x18007f5b8  jnz     short loc_18007F5FF
0x18007f5ba  lea     rax, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007f5c1  mov     [rsp+1C0h+var_178], 154h
0x18007f5ca  mov     [rsp+1C0h+var_188], rax
0x18007f5cf  lea     rdx, [rsp+1C0h+var_188]
0x18007f5d4  lea     rax, aIsoverlayimage_1; "IsOverlayImageMounted"
0x18007f5db  mov     [rsp+1C0h+var_170], 0
0x18007f5e4  mov     r8d, 0C00000BBh
0x18007f5ea  mov     [rsp+1C0h+var_180], rax
0x18007f5ef  lea     rcx, [rbp+0C0h+var_A4]
0x18007f5f3  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18007f5f8  mov     ebx, eax
0x18007f5fa  jmp     loc_18007FA7A
0x18007f5ff  lea     rax, [rbp+0C0h+var_88]
0x18007f603  mov     rdx, rbx
0x18007f606  mov     [rbp+0C0h+var_98], rax
0x18007f60a  lea     rcx, [rbp+0C0h+var_98]
0x18007f60e  lea     rax, [rbp+0C0h+var_88]
0x18007f612  mov     [rbp+0C0h+var_90], rax
0x18007f616  xor     eax, eax
0x18007f618  mov     [rbp+0C0h+var_88], ax
0x18007f61c  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x18007f621  test    al, al
0x18007f623  jnz     short loc_18007F66D
0x18007f625  lea     rax, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007f62c  mov     [rsp+1C0h+var_158], 158h
0x18007f635  mov     [rsp+1C0h+var_168], rax
0x18007f63a  lea     rdx, [rsp+1C0h+var_168]
0x18007f63f  lea     rax, aIsoverlayimage_1; "IsOverlayImageMounted"
0x18007f646  mov     r8d, 0C0000017h
0x18007f64c  mov     [rsp+1C0h+var_160], rax
0x18007f651  lea     rcx, [rbp+0C0h+var_A4]
0x18007f655  lea     rax, aImagerootpathA; "ImageRootPath.assign(ImageRoot)"
0x18007f65c  mov     [rsp+1C0h+var_150], rax
0x18007f661  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18007f666  mov     ebx, eax
0x18007f668  jmp     loc_18007FA71
0x18007f66d  mov     rax, [rsp+1C0h+var_198]
0x18007f672  lea     r8, [rbp+0C0h+var_A8]
0x18007f676  xor     edx, edx
0x18007f678  mov     [rbp+0C0h+var_A8], 0
0x18007f67f  xor     ecx, ecx
0x18007f681  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f686  mov     r8d, eax
0x18007f689  cmp     eax, 80070490h
0x18007f68e  jz      loc_18007F930
0x18007f694  mov     esi, 80070002h
0x18007f699  cmp     eax, esi
0x18007f69b  jz      loc_18007F930
0x18007f6a1  cmp     eax, 80004001h
0x18007f6a6  jz      loc_18007F930
0x18007f6ac  mov     eax, 80000000h
0x18007f6b1  lea     ecx, [r8+rax]
0x18007f6b5  test    eax, ecx
0x18007f6b7  jnz     short loc_18007F6FF
0x18007f6b9  cmp     r8d, 8007007Ah
0x18007f6c0  jz      short loc_18007F6FF
0x18007f6c2  lea     rax, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007f6c9  mov     [rbp+0C0h+var_138], 16Ah
0x18007f6d1  mov     [rsp+1C0h+var_148], rax
0x18007f6d6  lea     rdx, [rsp+1C0h+var_148]
0x18007f6db  lea     rax, aIsoverlayimage_1; "IsOverlayImageMounted"
0x18007f6e2  mov     [rbp+0C0h+var_140], rax
0x18007f6e6  lea     rcx, [rbp+0C0h+var_A4]
0x18007f6ea  lea     rax, aHr_0; "hr"
0x18007f6f1  mov     [rbp+0C0h+var_130], rax
0x18007f6f5  call    ?OriginateHResult@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18007f6fa  jmp     loc_18007F666
0x18007f6ff  mov     edx, [rbp+0C0h+var_A8]
0x18007f702  lea     rcx, [rbp+0C0h+var_A0]
0x18007f706  call    ??$make_unique@$$BY0A@E$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@0@_K@Z; utl::make_unique<uchar [0],0>(unsigned __int64)
0x18007f70b  mov     rbx, [rbp+0C0h+var_A0]
0x18007f70f  test    rbx, rbx
0x18007f712  jz      loc_18007FA2A
0x18007f718  mov     ecx, [rbp+0C0h+var_A8]
0x18007f71b  lea     r8, [rbp+0C0h+var_A8]
0x18007f71f  mov     rax, [rsp+1C0h+var_198]
0x18007f724  mov     rdx, rbx
0x18007f727  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f72c  mov     r8d, eax
0x18007f72f  cmp     eax, 80070490h
0x18007f734  jz      loc_18007FA14
0x18007f73a  cmp     eax, esi
0x18007f73c  jz      loc_18007FA14
0x18007f742  test    eax, eax
0x18007f744  jns     loc_18007F7F8
0x18007f74a  cmp     eax, 8007007Ah
0x18007f74f  jnz     short loc_18007F7BD
0x18007f751  mov     edx, [rbp+0C0h+var_A8]
0x18007f754  lea     rcx, [rsp+1C0h+var_190]
0x18007f759  call    ??$make_unique@$$BY0A@E$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@0@_K@Z; utl::make_unique<uchar [0],0>(unsigned __int64)
0x18007f75e  mov     rcx, rbx; void *
0x18007f761  mov     rdi, [rax]
0x18007f764  mov     qword ptr [rax], 0
0x18007f76b  mov     rbx, rdi
0x18007f76e  mov     [rbp+0C0h+var_A0], rbx
0x18007f772  test    rcx, rcx
0x18007f775  jz      short loc_18007F77C
0x18007f777  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18007f77c  lea     rcx, [rsp+1C0h+var_190]
0x18007f781  call    ??1?$unique_ptr@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@U?$default_delete@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(void)
0x18007f786  test    rdi, rdi
0x18007f789  jnz     short loc_18007F718
0x18007f78b  lea     rax, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007f792  mov     [rbp+0C0h+var_118], 17Fh
0x18007f79a  mov     [rbp+0C0h+var_128], rax
0x18007f79e  lea     rdx, [rbp+0C0h+var_128]
0x18007f7a2  lea     rax, aIsoverlayimage_1; "IsOverlayImageMounted"
0x18007f7a9  mov     [rbp+0C0h+var_120], rax
0x18007f7ad  lea     rax, aUnionbuffer; "UnionBuffer"
0x18007f7b4  mov     [rbp+0C0h+var_110], rax
0x18007f7b8  jmp     loc_18007FA57
0x18007f7bd  lea     rax, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007f7c4  mov     [rbp+0C0h+var_F8], 17Ah
0x18007f7cc  mov     [rbp+0C0h+var_108], rax
0x18007f7d0  lea     rdx, [rbp+0C0h+var_108]
0x18007f7d4  lea     rax, aIsoverlayimage_1; "IsOverlayImageMounted"
0x18007f7db  mov     [rbp+0C0h+var_100], rax
0x18007f7df  lea     rcx, [rbp+0C0h+var_A4]
0x18007f7e3  lea     rax, aHr_0; "hr"
0x18007f7ea  mov     [rbp+0C0h+var_F0], rax
0x18007f7ee  call    ?OriginateHResult@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18007f7f3  jmp     loc_18007FA66
0x18007f7f8  lea     rax, [rbp+0C0h+var_28]
0x18007f7ff  mov     [rbp+0C0h+String2], rax
0x18007f806  lea     rdx, [rbp+0C0h+String2]
0x18007f80d  lea     rax, [rbp+0C0h+var_28]
0x18007f814  mov     [rbp+0C0h+var_30], rax
0x18007f81b  lea     rcx, [rbp+0C0h+var_98]
0x18007f81f  xor     eax, eax
0x18007f821  mov     [rbp+0C0h+var_28], ax
0x18007f828  call    ?GetFinalPath@@YAJAEBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAV12@@Z; GetFinalPath(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x18007f82d  mov     edi, eax
0x18007f82f  test    eax, eax
0x18007f831  jns     short loc_18007F858
0x18007f833  lea     rcx, [rbp+0C0h+String2]
0x18007f83a  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x18007f83f  lea     rcx, [rbp+0C0h+var_A0]
0x18007f843  call    ??1?$unique_ptr@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@U?$default_delete@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(void)
0x18007f848  lea     rcx, [rbp+0C0h+var_98]
0x18007f84c  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x18007f851  mov     ebx, edi
0x18007f853  jmp     loc_18007FA7A
0x18007f858  xor     edi, edi
0x18007f85a  cmp     [rbp+0C0h+var_A8], edi
0x18007f85d  jbe     loc_18007F91B
0x18007f863  lea     rax, [rbp+0C0h+var_48]
0x18007f867  mov     [rbp+0C0h+var_58], rax
0x18007f86b  lea     rdx, [rdi+1Ah]
0x18007f86f  lea     rax, [rbp+0C0h+var_48]
0x18007f873  add     rdx, rbx
0x18007f876  mov     [rbp+0C0h+var_50], rax
0x18007f87a  lea     rcx, [rbp+0C0h+var_58]
0x18007f87e  xor     eax, eax
0x18007f880  mov     [rbp+0C0h+var_48], ax
0x18007f884  movzx   r8d, word ptr [rdi+rbx+18h]
0x18007f88a  shr     r8, 1
0x18007f88d  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x18007f892  test    al, al
0x18007f894  jz      loc_18007F9BF
0x18007f89a  lea     rax, [rbp+0C0h+var_68]
0x18007f89e  mov     [rbp+0C0h+String1], rax
0x18007f8a2  lea     rdx, [rbp+0C0h+String1]
0x18007f8a6  lea     rax, [rbp+0C0h+var_68]
0x18007f8aa  mov     [rbp+0C0h+var_70], rax
0x18007f8ae  lea     rcx, [rbp+0C0h+var_58]
0x18007f8b2  xor     eax, eax
0x18007f8b4  mov     [rbp+0C0h+var_68], ax
0x18007f8b8  call    ?GetFinalPath@@YAJAEBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAV12@@Z; GetFinalPath(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x18007f8bd  mov     esi, eax
0x18007f8bf  test    eax, eax
0x18007f8c1  js      loc_18007F988
0x18007f8c7  mov     r8, [rbp+0C0h+var_70]
0x18007f8cb  mov     rcx, [rbp+0C0h+String1]; String1
0x18007f8cf  mov     rax, [rbp+0C0h+var_30]
0x18007f8d6  sub     r8, rcx
0x18007f8d9  mov     rdx, [rbp+0C0h+String2]; String2
0x18007f8e0  sub     rax, rdx
0x18007f8e3  cmp     r8, rax
0x18007f8e6  jnz     short loc_18007F8F1
0x18007f8e8  call    _wcsicmp
0x18007f8ed  test    eax, eax
0x18007f8ef  jz      short loc_18007F96D
0x18007f8f1  cmp     dword ptr [rdi+rbx], 0
0x18007f8f5  lea     rcx, [rbp+0C0h+String1]
0x18007f8f9  jz      short loc_18007F978
0x18007f8fb  mov     eax, [rdi+rbx]
0x18007f8fe  add     rdi, rax
0x18007f901  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x18007f906  lea     rcx, [rbp+0C0h+var_58]
0x18007f90a  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x18007f90f  mov     eax, [rbp+0C0h+var_A8]
0x18007f912  cmp     rdi, rax
0x18007f915  jb      loc_18007F863
0x18007f91b  lea     rcx, [rbp+0C0h+String2]
0x18007f922  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x18007f927  lea     rcx, [rbp+0C0h+var_A0]
0x18007f92b  call    ??1?$unique_ptr@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@U?$default_delete@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(void)
0x18007f930  lea     rcx, [rbp+0C0h+var_98]
0x18007f934  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x18007f939  lea     rcx, [rsp+1C0h+var_1A0]
0x18007f93e  call    ?Close@?$AutoGenericHandleBase@PEAUHINSTANCE__@@$0A@V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(void)
0x18007f943  xor     eax, eax
0x18007f945  mov     rcx, [rbp+0C0h+var_18]
0x18007f94c  xor     rcx, rsp; StackCookie
0x18007f94f  call    __security_check_cookie
0x18007f954  lea     r11, [rsp+1C0h+var_10]
0x18007f95c  mov     rbx, [r11+30h]
0x18007f960  mov     rsi, [r11+38h]
0x18007f964  mov     rsp, r11
0x18007f967  pop     r14
0x18007f969  pop     rdi
0x18007f96a  pop     rbp
0x18007f96b  retn
0x18007f96d  mov     dword ptr [r14], 1
0x18007f974  lea     rcx, [rbp+0C0h+String1]
0x18007f978  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x18007f97d  lea     rcx, [rbp+0C0h+var_58]
0x18007f981  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x18007f986  jmp     short loc_18007F91B
0x18007f988  lea     rcx, [rbp+0C0h+String1]
0x18007f98c  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x18007f991  lea     rcx, [rbp+0C0h+var_58]
0x18007f995  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x18007f99a  lea     rcx, [rbp+0C0h+String2]
0x18007f9a1  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x18007f9a6  lea     rcx, [rbp+0C0h+var_A0]
0x18007f9aa  call    ??1?$unique_ptr@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@U?$default_delete@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(void)
0x18007f9af  lea     rcx, [rbp+0C0h+var_98]
0x18007f9b3  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x18007f9b8  mov     ebx, esi
0x18007f9ba  jmp     loc_18007FA7A
0x18007f9bf  lea     rax, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007f9c6  mov     [rbp+0C0h+var_D8], 18Dh
0x18007f9ce  mov     [rbp+0C0h+var_E8], rax
0x18007f9d2  lea     rdx, [rbp+0C0h+var_E8]
0x18007f9d6  lea     rax, aIsoverlayimage_1; "IsOverlayImageMounted"
0x18007f9dd  mov     r8d, 0C0000017h
0x18007f9e3  mov     [rbp+0C0h+var_E0], rax
0x18007f9e7  lea     rcx, [rbp+0C0h+var_A4]
0x18007f9eb  lea     rax, aScratchrootAss; "ScratchRoot.assign(UnionInfo->ScratchRo"...
0x18007f9f2  mov     [rbp+0C0h+var_D0], rax
0x18007f9f6  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18007f9fb  lea     rcx, [rbp+0C0h+var_58]
0x18007f9ff  mov     ebx, eax
0x18007fa01  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x18007fa06  lea     rcx, [rbp+0C0h+String2]
0x18007fa0d  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x18007fa12  jmp     short loc_18007FA68
0x18007fa14  lea     rcx, [rbp+0C0h+var_A0]
0x18007fa18  call    ??1?$unique_ptr@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@U?$default_delete@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(void)
0x18007fa1d  lea     rcx, [rbp+0C0h+var_98]
0x18007fa21  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x18007fa26  xor     ebx, ebx
0x18007fa28  jmp     short loc_18007FA7A
0x18007fa2a  lea     rax, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007fa31  mov     [rbp+0C0h+var_B8], 16Dh
0x18007fa39  mov     [rbp+0C0h+var_C8], rax
0x18007fa3d  lea     rdx, [rbp+0C0h+var_C8]
0x18007fa41  lea     rax, aIsoverlayimage_1; "IsOverlayImageMounted"
0x18007fa48  mov     [rbp+0C0h+var_C0], rax
0x18007fa4c  lea     rax, aUnionbuffer; "UnionBuffer"
0x18007fa53  mov     [rbp+0C0h+var_B0], rax
0x18007fa57  mov     r8d, 0C0000017h
0x18007fa5d  lea     rcx, [rbp+0C0h+var_A4]
0x18007fa61  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18007fa66  mov     ebx, eax
0x18007fa68  lea     rcx, [rbp+0C0h+var_A0]
0x18007fa6c  call    ??1?$unique_ptr@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@U?$default_delete@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(void)
0x18007fa71  lea     rcx, [rbp+0C0h+var_98]
0x18007fa75  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x18007fa7a  lea     rcx, [rsp+1C0h+var_1A0]
0x18007fa7f  call    ?Close@?$AutoGenericHandleBase@PEAUHINSTANCE__@@$0A@V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(void)
0x18007fa84  mov     eax, ebx
0x18007fa86  jmp     loc_18007F945
```
