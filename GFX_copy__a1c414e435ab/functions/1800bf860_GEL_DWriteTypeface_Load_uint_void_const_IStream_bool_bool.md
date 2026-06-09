# GEL::DWriteTypeface::Load(uint,void const *,IStream &,bool &,bool &)

- ea: `0x1800bf860`
- end: `0x1800bfb47`
- name: `?Load@DWriteTypeface@GEL@@UEAAJIPEBXAEAUIStream@@AEA_N2@Z`
- size: `743`
- prototype: `__int64 __usercall@<rax>(GEL::DWriteTypeface *__hidden this@<rcx>, unsigned int@<edx>, const void *@<r8>, struct IStream *@<r9>, bool *, bool *)`
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update`

## callees

- `0x18000afe8`
- `0x1800573f0`
- `0x1800786fc`
- `0x18008d364`
- `0x18008d400`
- `0x18008d4c0`
- `0x1800be640`
- `0x1800bf860`
- `0x18016eca8`

## import_xrefs

- `mso40uiWin32Client!__imp_?GetResourceManagerInstance@DWriteAssistant@Mso@@YAAEAVResourceManager@12@XZ` at `0x1800bf887`
- `mso40uiWin32Client!__imp_?GetResourceManagerInstance@DWriteAssistant@Mso@@YAAEAVResourceManager@12@XZ` at `0x1800bf887`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800bfa58`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800bfa7e`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800bfaa4`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800bfa58`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800bfa7e`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800bfaa4`

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
0x1800bf860  mov     [rsp-18h+arg_0], rbx
0x1800bf865  mov     [rsp-18h+arg_8], rsi
0x1800bf86a  mov     [rsp-18h+arg_10], rdi
0x1800bf86f  push    rbp
0x1800bf870  push    r14
0x1800bf872  push    r15
0x1800bf874  mov     rbp, rsp
0x1800bf877  sub     rsp, 60h
0x1800bf87b  mov     rbx, r9
0x1800bf87e  mov     r14, r8
0x1800bf881  mov     r15d, edx
0x1800bf884  mov     rdi, rcx
0x1800bf887  call    cs:__imp_?GetResourceManagerInstance@DWriteAssistant@Mso@@YAAEAVResourceManager@12@XZ; Mso::DWriteAssistant::GetResourceManagerInstance(void)
0x1800bf88d  mov     rcx, rax; this
0x1800bf890  call    ?GetFontCollection@ResourceManager@DWriteAssistant@Mso@@UEAAAEAUIFontCollection@23@XZ; Mso::DWriteAssistant::ResourceManager::GetFontCollection(void)
0x1800bf895  mov     rsi, rax
0x1800bf898  mov     rcx, rdi; this
0x1800bf89b  call    ?TypefaceInstalled@DWriteTypeface@GEL@@QEBA_NXZ; GEL::DWriteTypeface::TypefaceInstalled(void)
0x1800bf8a0  test    al, al
0x1800bf8a2  jz      short loc_1800BF8AB
0x1800bf8a4  xor     eax, eax
0x1800bf8a6  jmp     loc_1800BF9E1
0x1800bf8ab  mov     ecx, 10h; this
0x1800bf8b0  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x1800bf8b5  test    rax, rax
0x1800bf8b8  jz      short loc_1800BF8D2
0x1800bf8ba  mov     dword ptr [rax+0Ch], 0
0x1800bf8c1  lea     rcx, ??_7DWriteEmbeddedFont@GEL@@6B@; const GEL::DWriteEmbeddedFont::`vftable'
0x1800bf8c8  mov     [rax], rcx
0x1800bf8cb  mov     dword ptr [rax+8], 0FFFFFFFFh
0x1800bf8d2  mov     [rbp+var_8], rax
0x1800bf8d6  lea     rcx, [rdi+80h]; this
0x1800bf8dd  mov     rdx, r14; unsigned __int64
0x1800bf8e0  call    ?GetRawValGrow@CMapImpl@Ofc@@IEAAAEA_K_K@Z; Ofc::CMapImpl::GetRawValGrow(unsigned __int64)
0x1800bf8e5  mov     rcx, [rax]
0x1800bf8e8  mov     rax, [rbp+arg_28]
0x1800bf8ec  mov     [rsp+60h+var_30], rax
0x1800bf8f1  mov     rax, [rbp+arg_20]
0x1800bf8f5  mov     [rsp+60h+var_38], rax
0x1800bf8fa  lea     rax, [rbp+var_8]
0x1800bf8fe  mov     [rsp+60h+var_40], rax
0x1800bf903  mov     r9, rbx
0x1800bf906  mov     r8d, r15d
0x1800bf909  mov     rdx, [rdi+10h]
0x1800bf90d  call    ?Load@EmbedData@GEL@@QEAAJPEB_WIAEAUIStream@@AEAV?$TOwnerPtr@VEmbeddedFont@GEL@@@Ofc@@AEA_N3@Z; GEL::EmbedData::Load(wchar_t const *,uint,IStream &,Ofc::TOwnerPtr<GEL::EmbeddedFont> &,bool &,bool &)
0x1800bf912  mov     ebx, eax
0x1800bf914  test    eax, eax
0x1800bf916  jz      short loc_1800BF939
0x1800bf918  mov     rcx, [rbp+var_8]
0x1800bf91c  test    rcx, rcx
0x1800bf91f  jz      short loc_1800BF932
0x1800bf921  mov     rdx, [rcx]
0x1800bf924  mov     rax, [rdx]
0x1800bf927  mov     edx, 1
0x1800bf92c  call    cs:__guard_dispatch_icall_fptr
0x1800bf932  mov     eax, ebx
0x1800bf934  jmp     loc_1800BF9E1
0x1800bf939  mov     [rbp+var_20], 0
0x1800bf940  mov     [rbp+var_1C], 0
0x1800bf947  mov     rax, [rsi]
0x1800bf94a  mov     rbx, [rax+28h]
0x1800bf94e  mov     rax, [rdi]
0x1800bf951  mov     r8, r14
0x1800bf954  mov     edx, r15d
0x1800bf957  mov     rcx, rdi
0x1800bf95a  mov     rax, [rax+150h]
0x1800bf961  call    cs:__guard_dispatch_icall_fptr
0x1800bf967  lea     r9, [rbp+var_20]
0x1800bf96b  lea     r8, [rbp+var_1C]
0x1800bf96f  mov     rdx, rax
0x1800bf972  mov     rcx, rsi
0x1800bf975  mov     rax, rbx
0x1800bf978  call    cs:__guard_dispatch_icall_fptr
0x1800bf97e  test    eax, eax
0x1800bf980  js      short loc_1800BF9C2
0x1800bf982  cmp     [rbp+var_20], 0
0x1800bf986  jz      short loc_1800BF9C2
0x1800bf988  mov     [rbp+var_10], 0
0x1800bf990  mov     rax, [rsi]
0x1800bf993  lea     r8, [rbp+var_10]
0x1800bf997  mov     edx, [rbp+var_1C]
0x1800bf99a  mov     rcx, rsi
0x1800bf99d  mov     rax, [rax+20h]
0x1800bf9a1  call    cs:__guard_dispatch_icall_fptr
0x1800bf9a7  test    eax, eax
0x1800bf9a9  jns     short loc_1800BF9FB
0x1800bf9ab  mov     rcx, [rbp+var_10]
0x1800bf9af  test    rcx, rcx
0x1800bf9b2  jz      short loc_1800BF9C2
0x1800bf9b4  mov     rax, [rcx]
0x1800bf9b7  mov     rax, [rax+10h]
0x1800bf9bb  call    cs:__guard_dispatch_icall_fptr
0x1800bf9c1  nop
0x1800bf9c2  mov     rcx, [rbp+var_8]
0x1800bf9c6  test    rcx, rcx
0x1800bf9c9  jz      short loc_1800BF9DC
0x1800bf9cb  mov     rax, [rcx]
0x1800bf9ce  mov     edx, 1
0x1800bf9d3  mov     rax, [rax]
0x1800bf9d6  call    cs:__guard_dispatch_icall_fptr
0x1800bf9dc  mov     eax, 200h
0x1800bf9e1  lea     r11, [rsp+60h+var_s0]
0x1800bf9e6  mov     rbx, [r11+20h]
0x1800bf9ea  mov     rsi, [r11+28h]
0x1800bf9ee  mov     rdi, [r11+30h]
0x1800bf9f2  mov     rsp, r11
0x1800bf9f5  pop     r15
0x1800bf9f7  pop     r14
0x1800bf9f9  pop     rbp
0x1800bf9fa  retn
0x1800bf9fb  mov     [rbp+var_18], 0
0x1800bfa03  mov     rcx, [rbp+var_10]
0x1800bfa07  mov     rax, [rcx]
0x1800bfa0a  lea     r8, [rbp+var_18]
0x1800bfa0e  xor     edx, edx
0x1800bfa10  mov     rax, [rax+28h]
0x1800bfa14  call    cs:__guard_dispatch_icall_fptr
0x1800bfa1a  test    eax, eax
0x1800bfa1c  jns     short loc_1800BFA41
0x1800bfa1e  mov     rcx, [rbp+var_18]
0x1800bfa22  test    rcx, rcx
0x1800bfa25  jz      short loc_1800BF9AB
0x1800bfa27  mov     [rbp+var_18], 0
0x1800bfa2f  mov     rax, [rcx]
0x1800bfa32  mov     rax, [rax+10h]
0x1800bfa36  call    cs:__guard_dispatch_icall_fptr
0x1800bfa3c  jmp     loc_1800BF9AB
0x1800bfa41  mov     dword ptr [rdi+50h], 8
0x1800bfa48  mov     rcx, [rbp+var_18]
0x1800bfa4c  test    rcx, rcx
0x1800bfa4f  jnz     short loc_1800BFA5F
0x1800bfa51  xor     edx, edx
0x1800bfa53  mov     ecx, 1E3C3840h
0x1800bfa58  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800bfa5e  nop
0x1800bfa5f  mov     rax, [rcx]
0x1800bfa62  mov     rax, [rax+30h]
0x1800bfa66  call    cs:__guard_dispatch_icall_fptr
0x1800bfa6c  mov     esi, eax
0x1800bfa6e  mov     rcx, [rbp+var_18]
0x1800bfa72  test    rcx, rcx
0x1800bfa75  jnz     short loc_1800BFA85
0x1800bfa77  xor     edx, edx
0x1800bfa79  mov     ecx, 1E3C3840h
0x1800bfa7e  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800bfa84  nop
0x1800bfa85  mov     rax, [rcx]
0x1800bfa88  mov     rax, [rax+28h]
0x1800bfa8c  call    cs:__guard_dispatch_icall_fptr
0x1800bfa92  mov     ebx, eax
0x1800bfa94  mov     rcx, [rbp+var_18]
0x1800bfa98  test    rcx, rcx
0x1800bfa9b  jnz     short loc_1800BFAAB
0x1800bfa9d  xor     edx, edx
0x1800bfa9f  mov     ecx, 1E3C3840h
0x1800bfaa4  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800bfaaa  nop
0x1800bfaab  mov     rax, [rcx]
0x1800bfaae  mov     rax, [rax+20h]
0x1800bfab2  call    cs:__guard_dispatch_icall_fptr
0x1800bfab8  mov     dword ptr [rsp+60h+var_40], esi
0x1800bfabc  mov     r9d, ebx
0x1800bfabf  mov     r8d, eax
0x1800bfac2  mov     rdx, [rbp+var_10]
0x1800bfac6  mov     rcx, rdi
0x1800bfac9  call    ?SetInfo@DWriteTypeface@GEL@@QEAAXPEAUIDWriteFontFamily@@W4DWRITE_FONT_WEIGHT@@W4DWRITE_FONT_STRETCH@@W4DWRITE_FONT_STYLE@@@Z; GEL::DWriteTypeface::SetInfo(IDWriteFontFamily *,DWRITE_FONT_WEIGHT,DWRITE_FONT_STRETCH,DWRITE_FONT_STYLE)
0x1800bface  mov     rax, [rdi]
0x1800bfad1  mov     rcx, rdi
0x1800bfad4  mov     rax, [rax+158h]
0x1800bfadb  call    cs:__guard_dispatch_icall_fptr
0x1800bfae1  mov     edx, r15d; unsigned int
0x1800bfae4  mov     rcx, rdi; this
0x1800bfae7  call    ?SetSupportsFlag@DWriteTypeface@GEL@@QEAAXI@Z; GEL::DWriteTypeface::SetSupportsFlag(uint)
0x1800bfaec  nop
0x1800bfaed  mov     rcx, [rbp+var_18]
0x1800bfaf1  test    rcx, rcx
0x1800bfaf4  jz      short loc_1800BFB0C
0x1800bfaf6  mov     [rbp+var_18], 0
0x1800bfafe  mov     rax, [rcx]
0x1800bfb01  mov     rax, [rax+10h]
0x1800bfb05  call    cs:__guard_dispatch_icall_fptr
0x1800bfb0b  nop
0x1800bfb0c  mov     rcx, [rbp+var_10]
0x1800bfb10  test    rcx, rcx
0x1800bfb13  jz      short loc_1800BFB23
0x1800bfb15  mov     rax, [rcx]
0x1800bfb18  mov     rax, [rax+10h]
0x1800bfb1c  call    cs:__guard_dispatch_icall_fptr
0x1800bfb22  nop
0x1800bfb23  mov     rcx, [rbp+var_8]
0x1800bfb27  test    rcx, rcx
0x1800bfb2a  jz      loc_1800BF8A4
0x1800bfb30  mov     rax, [rcx]
0x1800bfb33  mov     edx, 1
0x1800bfb38  mov     rax, [rax]
0x1800bfb3b  call    cs:__guard_dispatch_icall_fptr
0x1800bfb41  jmp     loc_1800BF8A4
```
