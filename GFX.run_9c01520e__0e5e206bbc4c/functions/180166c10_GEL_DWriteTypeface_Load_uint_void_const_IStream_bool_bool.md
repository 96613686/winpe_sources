# GEL::DWriteTypeface::Load(uint,void const *,IStream &,bool &,bool &)

- ea: `0x180166c10`
- end: `0x180166ef7`
- name: `?Load@DWriteTypeface@GEL@@UEAAJIPEBXAEAUIStream@@AEA_N2@Z`
- size: `743`
- prototype: `__int64 __usercall@<rax>(GEL::DWriteTypeface *__hidden this@<rcx>, unsigned int@<edx>, const void *@<r8>, struct IStream *@<r9>, bool *, bool *)`
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update`

## callees

- `0x18000b11c`
- `0x180057e70`
- `0x180092a58`
- `0x1800fb8b4`
- `0x1800fb91c`
- `0x1800fb9d0`
- `0x180166c10`
- `0x180166fb0`
- `0x180172f10`

## import_xrefs

- `mso40uiWin32Client!__imp_?GetResourceManagerInstance@DWriteAssistant@Mso@@YAAEAVResourceManager@12@XZ` at `0x180166c37`
- `mso40uiWin32Client!__imp_?GetResourceManagerInstance@DWriteAssistant@Mso@@YAAEAVResourceManager@12@XZ` at `0x180166c37`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180166e08`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180166e2e`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180166e54`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180166e08`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180166e2e`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180166e54`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall GEL::DWriteTypeface::Load(
        GEL::DWriteTypeface *this,
        unsigned int a2,
        unsigned __int64 a3,
        struct IStream *a4,
        bool *a5,
        bool *a6)
{
  int v6; // ebx
  Mso::DWriteAssistant::ResourceManager *ResourceManagerInstance; // rax
  struct Mso::DWriteAssistant::IFontCollection *FontCollection; // rsi
  unsigned __int64 v12; // rdx
  unsigned int v13; // r8d
  _DWORD *v15; // rax
  unsigned __int64 *RawValGrow; // rax
  unsigned int v17; // ebx
  int (__fastcall *v18)(struct Mso::DWriteAssistant::IFontCollection *, __int64, unsigned int *, int *); // rbx
  __int64 v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rcx
  int v22; // esi
  __int64 v23; // rcx
  unsigned int v24; // ebx
  __int64 v25; // rcx
  unsigned int v26; // eax
  __int64 v27; // rcx
  int v28; // [rsp+40h] [rbp-20h] BYREF
  unsigned int v29; // [rsp+44h] [rbp-1Ch] BYREF
  __int64 v30; // [rsp+48h] [rbp-18h] BYREF
  __int64 v31; // [rsp+50h] [rbp-10h] BYREF
  void (__fastcall ***v32)(_QWORD, __int64); // [rsp+58h] [rbp-8h] BYREF

  v6 = (int)a4;
  ResourceManagerInstance = Mso::DWriteAssistant::GetResourceManagerInstance(this);
  FontCollection = Mso::DWriteAssistant::ResourceManager::GetFontCollection(ResourceManagerInstance);
  if ( GEL::DWriteTypeface::TypefaceInstalled(this) )
    return 0;
  v15 = Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x10, v12, v13);
  if ( v15 )
  {
    v15[3] = 0;
    *(_QWORD *)v15 = &GEL::DWriteEmbeddedFont::`vftable';
    v15[2] = -1;
  }
  v32 = (void (__fastcall ***)(_QWORD, __int64))v15;
  RawValGrow = Ofc::CMapImpl::GetRawValGrow((GEL::DWriteTypeface *)((char *)this + 128), a3);
  v17 = GEL::EmbedData::Load(*RawValGrow, *((_QWORD *)this + 2), a2, v6, (__int64)&v32, (__int64)a5, (__int64)a6);
  if ( v17 )
  {
    if ( v32 )
      (**v32)(v32, 1);
    return v17;
  }
  else
  {
    v28 = 0;
    v29 = 0;
    v18 = *(int (__fastcall **)(struct Mso::DWriteAssistant::IFontCollection *, __int64, unsigned int *, int *))(*(_QWORD *)FontCollection + 40LL);
    v19 = (*(__int64 (__fastcall **)(GEL::DWriteTypeface *, _QWORD, unsigned __int64))(*(_QWORD *)this + 336LL))(
            this,
            a2,
            a3);
    if ( v18(FontCollection, v19, &v29, &v28) >= 0 && v28 )
    {
      v31 = 0;
      if ( (*(int (__fastcall **)(struct Mso::DWriteAssistant::IFontCollection *, _QWORD, __int64 *))(*(_QWORD *)FontCollection + 32LL))(
             FontCollection,
             v29,
             &v31) >= 0 )
      {
        v30 = 0;
        if ( (*(int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v31 + 40LL))(v31, 0, &v30) >= 0 )
        {
          *((_DWORD *)this + 20) = 8;
          v21 = v30;
          if ( !v30 )
            CrashWithRecovery(0x1E3C3840u, 0);
          v22 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 48LL))(v21);
          v23 = v30;
          if ( !v30 )
            CrashWithRecovery(0x1E3C3840u, 0);
          v24 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v23 + 40LL))(v23);
          v25 = v30;
          if ( !v30 )
            CrashWithRecovery(0x1E3C3840u, 0);
          v26 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v25 + 32LL))(v25);
          GEL::DWriteTypeface::SetInfo(this, v31, v26, v24, v22);
          (*(void (__fastcall **)(GEL::DWriteTypeface *))(*(_QWORD *)this + 344LL))(this);
          GEL::DWriteTypeface::SetSupportsFlag(this, a2);
          v27 = v30;
          if ( v30 )
          {
            v30 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
          }
          if ( v31 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
          if ( v32 )
            (**v32)(v32, 1);
          return 0;
        }
        v20 = v30;
        if ( v30 )
        {
          v30 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
        }
      }
      if ( v31 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    }
    if ( v32 )
      (**v32)(v32, 1);
    return 512;
  }
}

```

## disassembly

```asm
0x180166c10  mov     [rsp-18h+arg_0], rbx
0x180166c15  mov     [rsp-18h+arg_8], rsi
0x180166c1a  mov     [rsp-18h+arg_10], rdi
0x180166c1f  push    rbp
0x180166c20  push    r14
0x180166c22  push    r15
0x180166c24  mov     rbp, rsp
0x180166c27  sub     rsp, 60h
0x180166c2b  mov     rbx, r9
0x180166c2e  mov     r14, r8
0x180166c31  mov     r15d, edx
0x180166c34  mov     rdi, rcx
0x180166c37  call    cs:__imp_?GetResourceManagerInstance@DWriteAssistant@Mso@@YAAEAVResourceManager@12@XZ; Mso::DWriteAssistant::GetResourceManagerInstance(void)
0x180166c3d  mov     rcx, rax; this
0x180166c40  call    ?GetFontCollection@ResourceManager@DWriteAssistant@Mso@@UEAAAEAUIFontCollection@23@XZ; Mso::DWriteAssistant::ResourceManager::GetFontCollection(void)
0x180166c45  mov     rsi, rax
0x180166c48  mov     rcx, rdi; this
0x180166c4b  call    ?TypefaceInstalled@DWriteTypeface@GEL@@QEBA_NXZ; GEL::DWriteTypeface::TypefaceInstalled(void)
0x180166c50  test    al, al
0x180166c52  jz      short loc_180166C5B
0x180166c54  xor     eax, eax
0x180166c56  jmp     loc_180166D91
0x180166c5b  mov     ecx, 10h; this
0x180166c60  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x180166c65  test    rax, rax
0x180166c68  jz      short loc_180166C82
0x180166c6a  mov     dword ptr [rax+0Ch], 0
0x180166c71  lea     rcx, ??_7DWriteEmbeddedFont@GEL@@6B@; const GEL::DWriteEmbeddedFont::`vftable'
0x180166c78  mov     [rax], rcx
0x180166c7b  mov     dword ptr [rax+8], 0FFFFFFFFh
0x180166c82  mov     [rbp+var_8], rax
0x180166c86  lea     rcx, [rdi+80h]; this
0x180166c8d  mov     rdx, r14; unsigned __int64
0x180166c90  call    ?GetRawValGrow@CMapImpl@Ofc@@IEAAAEA_K_K@Z; Ofc::CMapImpl::GetRawValGrow(unsigned __int64)
0x180166c95  mov     rcx, [rax]
0x180166c98  mov     rax, [rbp+arg_28]
0x180166c9c  mov     [rsp+60h+var_30], rax
0x180166ca1  mov     rax, [rbp+arg_20]
0x180166ca5  mov     [rsp+60h+var_38], rax
0x180166caa  lea     rax, [rbp+var_8]
0x180166cae  mov     [rsp+60h+var_40], rax
0x180166cb3  mov     r9, rbx
0x180166cb6  mov     r8d, r15d
0x180166cb9  mov     rdx, [rdi+10h]
0x180166cbd  call    ?Load@EmbedData@GEL@@QEAAJPEB_WIAEAUIStream@@AEAV?$TOwnerPtr@VEmbeddedFont@GEL@@@Ofc@@AEA_N3@Z; GEL::EmbedData::Load(wchar_t const *,uint,IStream &,Ofc::TOwnerPtr<GEL::EmbeddedFont> &,bool &,bool &)
0x180166cc2  mov     ebx, eax
0x180166cc4  test    eax, eax
0x180166cc6  jz      short loc_180166CE9
0x180166cc8  mov     rcx, [rbp+var_8]
0x180166ccc  test    rcx, rcx
0x180166ccf  jz      short loc_180166CE2
0x180166cd1  mov     rdx, [rcx]
0x180166cd4  mov     rax, [rdx]
0x180166cd7  mov     edx, 1
0x180166cdc  call    cs:__guard_dispatch_icall_fptr
0x180166ce2  mov     eax, ebx
0x180166ce4  jmp     loc_180166D91
0x180166ce9  mov     [rbp+var_20], 0
0x180166cf0  mov     [rbp+var_1C], 0
0x180166cf7  mov     rax, [rsi]
0x180166cfa  mov     rbx, [rax+28h]
0x180166cfe  mov     rax, [rdi]
0x180166d01  mov     r8, r14
0x180166d04  mov     edx, r15d
0x180166d07  mov     rcx, rdi
0x180166d0a  mov     rax, [rax+150h]
0x180166d11  call    cs:__guard_dispatch_icall_fptr
0x180166d17  lea     r9, [rbp+var_20]
0x180166d1b  lea     r8, [rbp+var_1C]
0x180166d1f  mov     rdx, rax
0x180166d22  mov     rcx, rsi
0x180166d25  mov     rax, rbx
0x180166d28  call    cs:__guard_dispatch_icall_fptr
0x180166d2e  test    eax, eax
0x180166d30  js      short loc_180166D72
0x180166d32  cmp     [rbp+var_20], 0
0x180166d36  jz      short loc_180166D72
0x180166d38  mov     [rbp+var_10], 0
0x180166d40  mov     rax, [rsi]
0x180166d43  lea     r8, [rbp+var_10]
0x180166d47  mov     edx, [rbp+var_1C]
0x180166d4a  mov     rcx, rsi
0x180166d4d  mov     rax, [rax+20h]
0x180166d51  call    cs:__guard_dispatch_icall_fptr
0x180166d57  test    eax, eax
0x180166d59  jns     short loc_180166DAB
0x180166d5b  mov     rcx, [rbp+var_10]
0x180166d5f  test    rcx, rcx
0x180166d62  jz      short loc_180166D72
0x180166d64  mov     rax, [rcx]
0x180166d67  mov     rax, [rax+10h]
0x180166d6b  call    cs:__guard_dispatch_icall_fptr
0x180166d71  nop
0x180166d72  mov     rcx, [rbp+var_8]
0x180166d76  test    rcx, rcx
0x180166d79  jz      short loc_180166D8C
0x180166d7b  mov     rax, [rcx]
0x180166d7e  mov     edx, 1
0x180166d83  mov     rax, [rax]
0x180166d86  call    cs:__guard_dispatch_icall_fptr
0x180166d8c  mov     eax, 200h
0x180166d91  lea     r11, [rsp+60h+var_s0]
0x180166d96  mov     rbx, [r11+20h]
0x180166d9a  mov     rsi, [r11+28h]
0x180166d9e  mov     rdi, [r11+30h]
0x180166da2  mov     rsp, r11
0x180166da5  pop     r15
0x180166da7  pop     r14
0x180166da9  pop     rbp
0x180166daa  retn
0x180166dab  mov     [rbp+var_18], 0
0x180166db3  mov     rcx, [rbp+var_10]
0x180166db7  mov     rax, [rcx]
0x180166dba  lea     r8, [rbp+var_18]
0x180166dbe  xor     edx, edx
0x180166dc0  mov     rax, [rax+28h]
0x180166dc4  call    cs:__guard_dispatch_icall_fptr
0x180166dca  test    eax, eax
0x180166dcc  jns     short loc_180166DF1
0x180166dce  mov     rcx, [rbp+var_18]
0x180166dd2  test    rcx, rcx
0x180166dd5  jz      short loc_180166D5B
0x180166dd7  mov     [rbp+var_18], 0
0x180166ddf  mov     rax, [rcx]
0x180166de2  mov     rax, [rax+10h]
0x180166de6  call    cs:__guard_dispatch_icall_fptr
0x180166dec  jmp     loc_180166D5B
0x180166df1  mov     dword ptr [rdi+50h], 8
0x180166df8  mov     rcx, [rbp+var_18]
0x180166dfc  test    rcx, rcx
0x180166dff  jnz     short loc_180166E0F
0x180166e01  xor     edx, edx
0x180166e03  mov     ecx, 1E3C3840h
0x180166e08  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180166e0e  nop
0x180166e0f  mov     rax, [rcx]
0x180166e12  mov     rax, [rax+30h]
0x180166e16  call    cs:__guard_dispatch_icall_fptr
0x180166e1c  mov     esi, eax
0x180166e1e  mov     rcx, [rbp+var_18]
0x180166e22  test    rcx, rcx
0x180166e25  jnz     short loc_180166E35
0x180166e27  xor     edx, edx
0x180166e29  mov     ecx, 1E3C3840h
0x180166e2e  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180166e34  nop
0x180166e35  mov     rax, [rcx]
0x180166e38  mov     rax, [rax+28h]
0x180166e3c  call    cs:__guard_dispatch_icall_fptr
0x180166e42  mov     ebx, eax
0x180166e44  mov     rcx, [rbp+var_18]
0x180166e48  test    rcx, rcx
0x180166e4b  jnz     short loc_180166E5B
0x180166e4d  xor     edx, edx
0x180166e4f  mov     ecx, 1E3C3840h
0x180166e54  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180166e5a  nop
0x180166e5b  mov     rax, [rcx]
0x180166e5e  mov     rax, [rax+20h]
0x180166e62  call    cs:__guard_dispatch_icall_fptr
0x180166e68  mov     dword ptr [rsp+60h+var_40], esi
0x180166e6c  mov     r9d, ebx
0x180166e6f  mov     r8d, eax
0x180166e72  mov     rdx, [rbp+var_10]
0x180166e76  mov     rcx, rdi
0x180166e79  call    ?SetInfo@DWriteTypeface@GEL@@QEAAXPEAUIDWriteFontFamily@@W4DWRITE_FONT_WEIGHT@@W4DWRITE_FONT_STRETCH@@W4DWRITE_FONT_STYLE@@@Z; GEL::DWriteTypeface::SetInfo(IDWriteFontFamily *,DWRITE_FONT_WEIGHT,DWRITE_FONT_STRETCH,DWRITE_FONT_STYLE)
0x180166e7e  mov     rax, [rdi]
0x180166e81  mov     rcx, rdi
0x180166e84  mov     rax, [rax+158h]
0x180166e8b  call    cs:__guard_dispatch_icall_fptr
0x180166e91  mov     edx, r15d; unsigned int
0x180166e94  mov     rcx, rdi; this
0x180166e97  call    ?SetSupportsFlag@DWriteTypeface@GEL@@QEAAXI@Z; GEL::DWriteTypeface::SetSupportsFlag(uint)
0x180166e9c  nop
0x180166e9d  mov     rcx, [rbp+var_18]
0x180166ea1  test    rcx, rcx
0x180166ea4  jz      short loc_180166EBC
0x180166ea6  mov     [rbp+var_18], 0
0x180166eae  mov     rax, [rcx]
0x180166eb1  mov     rax, [rax+10h]
0x180166eb5  call    cs:__guard_dispatch_icall_fptr
0x180166ebb  nop
0x180166ebc  mov     rcx, [rbp+var_10]
0x180166ec0  test    rcx, rcx
0x180166ec3  jz      short loc_180166ED3
0x180166ec5  mov     rax, [rcx]
0x180166ec8  mov     rax, [rax+10h]
0x180166ecc  call    cs:__guard_dispatch_icall_fptr
0x180166ed2  nop
0x180166ed3  mov     rcx, [rbp+var_8]
0x180166ed7  test    rcx, rcx
0x180166eda  jz      loc_180166C54
0x180166ee0  mov     rax, [rcx]
0x180166ee3  mov     edx, 1
0x180166ee8  mov     rax, [rax]
0x180166eeb  call    cs:__guard_dispatch_icall_fptr
0x180166ef1  jmp     loc_180166C54
```
