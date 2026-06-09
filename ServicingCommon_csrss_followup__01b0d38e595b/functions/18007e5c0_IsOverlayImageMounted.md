# IsOverlayImageMounted

- ea: `0x18007e5c0`
- end: `0x18007eb0b`
- name: `IsOverlayImageMounted`
- size: `1355`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18007eb20`
- `0x18007fae0`

## callees

- `0x18001f840`
- `0x180020dc0`
- `0x180026e00`
- `0x180028030`
- `0x18002d2b0`
- `0x180042bac`
- `0x1800735e0`
- `0x18007c9a0`
- `0x18007cb18`
- `0x18007cfe0`
- `0x18007d6f4`
- `0x18007d794`
- `0x18007df88`
- `0x18007e064`
- `0x18007e08c`
- `0x18007e5c0`
- `0x18009e020`

## string_xrefs

- `0x18007e63a`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007e6a5`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007e742`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007e80b`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007e83d`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007ea3f`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007eaaa`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007e6d5`: `ImageRootPath.assign(ImageRoot)`
- `0x18007e654`: `IsOverlayImageMounted`
- `0x18007e6bf`: `IsOverlayImageMounted`
- `0x18007e75b`: `IsOverlayImageMounted`
- `0x18007e822`: `IsOverlayImageMounted`
- `0x18007e854`: `IsOverlayImageMounted`
- `0x18007ea56`: `IsOverlayImageMounted`
- `0x18007eac1`: `IsOverlayImageMounted`
- `0x18007ea6b`: `ScratchRoot.assign(UnionInfo->ScratchRootPath, UnionInfo->ScratchRootLength / sizeof(WCHAR))`

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
0x18007e5c0  mov     [rsp-8+arg_10], rbx
0x18007e5c5  mov     [rsp-8+arg_18], rsi
0x18007e5ca  push    rbp
0x18007e5cb  push    rdi
0x18007e5cc  push    r14
0x18007e5ce  lea     rbp, [rsp-0B0h]
0x18007e5d6  sub     rsp, 1B0h
0x18007e5dd  mov     rax, cs:__security_cookie
0x18007e5e4  xor     rax, rsp
0x18007e5e7  mov     [rbp+0C0h+var_18], rax
0x18007e5ee  mov     r14, rdx
0x18007e5f1  mov     [rbp+0C0h+var_A4], 0
0x18007e5f8  mov     rbx, rcx
0x18007e5fb  mov     dword ptr [rdx], 0
0x18007e601  call    ?InitializeWdscore@Rtl@Implementation@WCP@Windows@@YAXXZ; Windows::WCP::Implementation::Rtl::InitializeWdscore(void)
0x18007e606  lea     rcx, [rsp+1C0h+var_1A0]
0x18007e60b  mov     [rsp+1C0h+var_1A0], 0
0x18007e614  mov     [rsp+1C0h+var_198], 0
0x18007e61d  call    ?GetInitPointer@?$AutoComPtr@UICbsIdentity@@@Windows@@QEAAPEAPEAUICbsIdentity@@XZ; Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(void)
0x18007e622  mov     rdx, rax; HINSTANCE *
0x18007e625  lea     r8, [rsp+1C0h+var_198]; __int64 (**)(void)
0x18007e62a  lea     rcx, aEnumeratefiles; "EnumerateFileSystemUnions"
0x18007e631  call    ?IsOverlayAPISupported@@YA_NQEBDPEAPEAUHINSTANCE__@@PEAP6A_JXZ@Z; IsOverlayAPISupported(char const * const,HINSTANCE__ * *,__int64 (**)(void))
0x18007e636  test    al, al
0x18007e638  jnz     short loc_18007E67F
0x18007e63a  lea     rax, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007e641  mov     [rsp+1C0h+var_178], 154h
0x18007e64a  mov     [rsp+1C0h+var_188], rax
0x18007e64f  lea     rdx, [rsp+1C0h+var_188]
0x18007e654  lea     rax, aIsoverlayimage_1; "IsOverlayImageMounted"
0x18007e65b  mov     [rsp+1C0h+var_170], 0
0x18007e664  mov     r8d, 0C00000BBh
0x18007e66a  mov     [rsp+1C0h+var_180], rax
0x18007e66f  lea     rcx, [rbp+0C0h+var_A4]
0x18007e673  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18007e678  mov     ebx, eax
0x18007e67a  jmp     loc_18007EAFA
0x18007e67f  lea     rax, [rbp+0C0h+var_88]
0x18007e683  mov     rdx, rbx
0x18007e686  mov     [rbp+0C0h+var_98], rax
0x18007e68a  lea     rcx, [rbp+0C0h+var_98]
0x18007e68e  lea     rax, [rbp+0C0h+var_88]
0x18007e692  mov     [rbp+0C0h+var_90], rax
0x18007e696  xor     eax, eax
0x18007e698  mov     [rbp+0C0h+var_88], ax
0x18007e69c  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x18007e6a1  test    al, al
0x18007e6a3  jnz     short loc_18007E6ED
0x18007e6a5  lea     rax, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007e6ac  mov     [rsp+1C0h+var_158], 158h
0x18007e6b5  mov     [rsp+1C0h+var_168], rax
0x18007e6ba  lea     rdx, [rsp+1C0h+var_168]
0x18007e6bf  lea     rax, aIsoverlayimage_1; "IsOverlayImageMounted"
0x18007e6c6  mov     r8d, 0C0000017h
0x18007e6cc  mov     [rsp+1C0h+var_160], rax
0x18007e6d1  lea     rcx, [rbp+0C0h+var_A4]
0x18007e6d5  lea     rax, aImagerootpathA; "ImageRootPath.assign(ImageRoot)"
0x18007e6dc  mov     [rsp+1C0h+var_150], rax
0x18007e6e1  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18007e6e6  mov     ebx, eax
0x18007e6e8  jmp     loc_18007EAF1
0x18007e6ed  mov     rax, [rsp+1C0h+var_198]
0x18007e6f2  lea     r8, [rbp+0C0h+var_A8]
0x18007e6f6  xor     edx, edx
0x18007e6f8  mov     [rbp+0C0h+var_A8], 0
0x18007e6ff  xor     ecx, ecx
0x18007e701  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e706  mov     r8d, eax
0x18007e709  cmp     eax, 80070490h
0x18007e70e  jz      loc_18007E9B0
0x18007e714  mov     esi, 80070002h
0x18007e719  cmp     eax, esi
0x18007e71b  jz      loc_18007E9B0
0x18007e721  cmp     eax, 80004001h
0x18007e726  jz      loc_18007E9B0
0x18007e72c  mov     eax, 80000000h
0x18007e731  lea     ecx, [r8+rax]
0x18007e735  test    eax, ecx
0x18007e737  jnz     short loc_18007E77F
0x18007e739  cmp     r8d, 8007007Ah
0x18007e740  jz      short loc_18007E77F
0x18007e742  lea     rax, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007e749  mov     [rbp+0C0h+var_138], 16Ah
0x18007e751  mov     [rsp+1C0h+var_148], rax
0x18007e756  lea     rdx, [rsp+1C0h+var_148]
0x18007e75b  lea     rax, aIsoverlayimage_1; "IsOverlayImageMounted"
0x18007e762  mov     [rbp+0C0h+var_140], rax
0x18007e766  lea     rcx, [rbp+0C0h+var_A4]
0x18007e76a  lea     rax, aHr_0; "hr"
0x18007e771  mov     [rbp+0C0h+var_130], rax
0x18007e775  call    ?OriginateHResult@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18007e77a  jmp     loc_18007E6E6
0x18007e77f  mov     edx, [rbp+0C0h+var_A8]
0x18007e782  lea     rcx, [rbp+0C0h+var_A0]
0x18007e786  call    ??$make_unique@$$BY0A@E$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@0@_K@Z; utl::make_unique<uchar [0],0>(unsigned __int64)
0x18007e78b  mov     rbx, [rbp+0C0h+var_A0]
0x18007e78f  test    rbx, rbx
0x18007e792  jz      loc_18007EAAA
0x18007e798  mov     ecx, [rbp+0C0h+var_A8]
0x18007e79b  lea     r8, [rbp+0C0h+var_A8]
0x18007e79f  mov     rax, [rsp+1C0h+var_198]
0x18007e7a4  mov     rdx, rbx
0x18007e7a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e7ac  mov     r8d, eax
0x18007e7af  cmp     eax, 80070490h
0x18007e7b4  jz      loc_18007EA94
0x18007e7ba  cmp     eax, esi
0x18007e7bc  jz      loc_18007EA94
0x18007e7c2  test    eax, eax
0x18007e7c4  jns     loc_18007E878
0x18007e7ca  cmp     eax, 8007007Ah
0x18007e7cf  jnz     short loc_18007E83D
0x18007e7d1  mov     edx, [rbp+0C0h+var_A8]
0x18007e7d4  lea     rcx, [rsp+1C0h+var_190]
0x18007e7d9  call    ??$make_unique@$$BY0A@E$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@0@_K@Z; utl::make_unique<uchar [0],0>(unsigned __int64)
0x18007e7de  mov     rcx, rbx; void *
0x18007e7e1  mov     rdi, [rax]
0x18007e7e4  mov     qword ptr [rax], 0
0x18007e7eb  mov     rbx, rdi
0x18007e7ee  mov     [rbp+0C0h+var_A0], rbx
0x18007e7f2  test    rcx, rcx
0x18007e7f5  jz      short loc_18007E7FC
0x18007e7f7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18007e7fc  lea     rcx, [rsp+1C0h+var_190]
0x18007e801  call    ??1?$unique_ptr@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@U?$default_delete@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(void)
0x18007e806  test    rdi, rdi
0x18007e809  jnz     short loc_18007E798
0x18007e80b  lea     rax, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007e812  mov     [rbp+0C0h+var_118], 17Fh
0x18007e81a  mov     [rbp+0C0h+var_128], rax
0x18007e81e  lea     rdx, [rbp+0C0h+var_128]
0x18007e822  lea     rax, aIsoverlayimage_1; "IsOverlayImageMounted"
0x18007e829  mov     [rbp+0C0h+var_120], rax
0x18007e82d  lea     rax, aUnionbuffer; "UnionBuffer"
0x18007e834  mov     [rbp+0C0h+var_110], rax
0x18007e838  jmp     loc_18007EAD7
0x18007e83d  lea     rax, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007e844  mov     [rbp+0C0h+var_F8], 17Ah
0x18007e84c  mov     [rbp+0C0h+var_108], rax
0x18007e850  lea     rdx, [rbp+0C0h+var_108]
0x18007e854  lea     rax, aIsoverlayimage_1; "IsOverlayImageMounted"
0x18007e85b  mov     [rbp+0C0h+var_100], rax
0x18007e85f  lea     rcx, [rbp+0C0h+var_A4]
0x18007e863  lea     rax, aHr_0; "hr"
0x18007e86a  mov     [rbp+0C0h+var_F0], rax
0x18007e86e  call    ?OriginateHResult@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18007e873  jmp     loc_18007EAE6
0x18007e878  lea     rax, [rbp+0C0h+var_28]
0x18007e87f  mov     [rbp+0C0h+String2], rax
0x18007e886  lea     rdx, [rbp+0C0h+String2]
0x18007e88d  lea     rax, [rbp+0C0h+var_28]
0x18007e894  mov     [rbp+0C0h+var_30], rax
0x18007e89b  lea     rcx, [rbp+0C0h+var_98]
0x18007e89f  xor     eax, eax
0x18007e8a1  mov     [rbp+0C0h+var_28], ax
0x18007e8a8  call    ?GetFinalPath@@YAJAEBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAV12@@Z; GetFinalPath(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x18007e8ad  mov     edi, eax
0x18007e8af  test    eax, eax
0x18007e8b1  jns     short loc_18007E8D8
0x18007e8b3  lea     rcx, [rbp+0C0h+String2]
0x18007e8ba  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x18007e8bf  lea     rcx, [rbp+0C0h+var_A0]
0x18007e8c3  call    ??1?$unique_ptr@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@U?$default_delete@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(void)
0x18007e8c8  lea     rcx, [rbp+0C0h+var_98]
0x18007e8cc  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x18007e8d1  mov     ebx, edi
0x18007e8d3  jmp     loc_18007EAFA
0x18007e8d8  xor     edi, edi
0x18007e8da  cmp     [rbp+0C0h+var_A8], edi
0x18007e8dd  jbe     loc_18007E99B
0x18007e8e3  lea     rax, [rbp+0C0h+var_48]
0x18007e8e7  mov     [rbp+0C0h+var_58], rax
0x18007e8eb  lea     rdx, [rdi+1Ah]
0x18007e8ef  lea     rax, [rbp+0C0h+var_48]
0x18007e8f3  add     rdx, rbx
0x18007e8f6  mov     [rbp+0C0h+var_50], rax
0x18007e8fa  lea     rcx, [rbp+0C0h+var_58]
0x18007e8fe  xor     eax, eax
0x18007e900  mov     [rbp+0C0h+var_48], ax
0x18007e904  movzx   r8d, word ptr [rdi+rbx+18h]
0x18007e90a  shr     r8, 1
0x18007e90d  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x18007e912  test    al, al
0x18007e914  jz      loc_18007EA3F
0x18007e91a  lea     rax, [rbp+0C0h+var_68]
0x18007e91e  mov     [rbp+0C0h+String1], rax
0x18007e922  lea     rdx, [rbp+0C0h+String1]
0x18007e926  lea     rax, [rbp+0C0h+var_68]
0x18007e92a  mov     [rbp+0C0h+var_70], rax
0x18007e92e  lea     rcx, [rbp+0C0h+var_58]
0x18007e932  xor     eax, eax
0x18007e934  mov     [rbp+0C0h+var_68], ax
0x18007e938  call    ?GetFinalPath@@YAJAEBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAV12@@Z; GetFinalPath(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x18007e93d  mov     esi, eax
0x18007e93f  test    eax, eax
0x18007e941  js      loc_18007EA08
0x18007e947  mov     r8, [rbp+0C0h+var_70]
0x18007e94b  mov     rcx, [rbp+0C0h+String1]; String1
0x18007e94f  mov     rax, [rbp+0C0h+var_30]
0x18007e956  sub     r8, rcx
0x18007e959  mov     rdx, [rbp+0C0h+String2]; String2
0x18007e960  sub     rax, rdx
0x18007e963  cmp     r8, rax
0x18007e966  jnz     short loc_18007E971
0x18007e968  call    _wcsicmp
0x18007e96d  test    eax, eax
0x18007e96f  jz      short loc_18007E9ED
0x18007e971  cmp     dword ptr [rdi+rbx], 0
0x18007e975  lea     rcx, [rbp+0C0h+String1]
0x18007e979  jz      short loc_18007E9F8
0x18007e97b  mov     eax, [rdi+rbx]
0x18007e97e  add     rdi, rax
0x18007e981  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x18007e986  lea     rcx, [rbp+0C0h+var_58]
0x18007e98a  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x18007e98f  mov     eax, [rbp+0C0h+var_A8]
0x18007e992  cmp     rdi, rax
0x18007e995  jb      loc_18007E8E3
0x18007e99b  lea     rcx, [rbp+0C0h+String2]
0x18007e9a2  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x18007e9a7  lea     rcx, [rbp+0C0h+var_A0]
0x18007e9ab  call    ??1?$unique_ptr@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@U?$default_delete@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(void)
0x18007e9b0  lea     rcx, [rbp+0C0h+var_98]
0x18007e9b4  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x18007e9b9  lea     rcx, [rsp+1C0h+var_1A0]
0x18007e9be  call    ?Close@?$AutoGenericHandleBase@PEAUHINSTANCE__@@$0A@V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(void)
0x18007e9c3  xor     eax, eax
0x18007e9c5  mov     rcx, [rbp+0C0h+var_18]
0x18007e9cc  xor     rcx, rsp; StackCookie
0x18007e9cf  call    __security_check_cookie
0x18007e9d4  lea     r11, [rsp+1C0h+var_10]
0x18007e9dc  mov     rbx, [r11+30h]
0x18007e9e0  mov     rsi, [r11+38h]
0x18007e9e4  mov     rsp, r11
0x18007e9e7  pop     r14
0x18007e9e9  pop     rdi
0x18007e9ea  pop     rbp
0x18007e9eb  retn
0x18007e9ed  mov     dword ptr [r14], 1
0x18007e9f4  lea     rcx, [rbp+0C0h+String1]
0x18007e9f8  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x18007e9fd  lea     rcx, [rbp+0C0h+var_58]
0x18007ea01  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x18007ea06  jmp     short loc_18007E99B
0x18007ea08  lea     rcx, [rbp+0C0h+String1]
0x18007ea0c  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x18007ea11  lea     rcx, [rbp+0C0h+var_58]
0x18007ea15  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x18007ea1a  lea     rcx, [rbp+0C0h+String2]
0x18007ea21  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x18007ea26  lea     rcx, [rbp+0C0h+var_A0]
0x18007ea2a  call    ??1?$unique_ptr@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@U?$default_delete@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(void)
0x18007ea2f  lea     rcx, [rbp+0C0h+var_98]
0x18007ea33  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x18007ea38  mov     ebx, esi
0x18007ea3a  jmp     loc_18007EAFA
0x18007ea3f  lea     rax, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007ea46  mov     [rbp+0C0h+var_D8], 18Dh
0x18007ea4e  mov     [rbp+0C0h+var_E8], rax
0x18007ea52  lea     rdx, [rbp+0C0h+var_E8]
0x18007ea56  lea     rax, aIsoverlayimage_1; "IsOverlayImageMounted"
0x18007ea5d  mov     r8d, 0C0000017h
0x18007ea63  mov     [rbp+0C0h+var_E0], rax
0x18007ea67  lea     rcx, [rbp+0C0h+var_A4]
0x18007ea6b  lea     rax, aScratchrootAss; "ScratchRoot.assign(UnionInfo->ScratchRo"...
0x18007ea72  mov     [rbp+0C0h+var_D0], rax
0x18007ea76  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18007ea7b  lea     rcx, [rbp+0C0h+var_58]
0x18007ea7f  mov     ebx, eax
0x18007ea81  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x18007ea86  lea     rcx, [rbp+0C0h+String2]
0x18007ea8d  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x18007ea92  jmp     short loc_18007EAE8
0x18007ea94  lea     rcx, [rbp+0C0h+var_A0]
0x18007ea98  call    ??1?$unique_ptr@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@U?$default_delete@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(void)
0x18007ea9d  lea     rcx, [rbp+0C0h+var_98]
0x18007eaa1  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x18007eaa6  xor     ebx, ebx
0x18007eaa8  jmp     short loc_18007EAFA
0x18007eaaa  lea     rax, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007eab1  mov     [rbp+0C0h+var_B8], 16Dh
0x18007eab9  mov     [rbp+0C0h+var_C8], rax
0x18007eabd  lea     rdx, [rbp+0C0h+var_C8]
0x18007eac1  lea     rax, aIsoverlayimage_1; "IsOverlayImageMounted"
0x18007eac8  mov     [rbp+0C0h+var_C0], rax
0x18007eacc  lea     rax, aUnionbuffer; "UnionBuffer"
0x18007ead3  mov     [rbp+0C0h+var_B0], rax
0x18007ead7  mov     r8d, 0C0000017h
0x18007eadd  lea     rcx, [rbp+0C0h+var_A4]
0x18007eae1  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18007eae6  mov     ebx, eax
0x18007eae8  lea     rcx, [rbp+0C0h+var_A0]
0x18007eaec  call    ??1?$unique_ptr@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@U?$default_delete@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(void)
0x18007eaf1  lea     rcx, [rbp+0C0h+var_98]
0x18007eaf5  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x18007eafa  lea     rcx, [rsp+1C0h+var_1A0]
0x18007eaff  call    ?Close@?$AutoGenericHandleBase@PEAUHINSTANCE__@@$0A@V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(void)
0x18007eb04  mov     eax, ebx
0x18007eb06  jmp     loc_18007E9C5
```
