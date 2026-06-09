# Art::BulletGalleryUser::FUpdate(void)

- ea: `0x18020bd40`
- end: `0x18020bffc`
- name: `?FUpdate@BulletGalleryUser@Art@@EEAA_NXZ`
- size: `700`
- prototype: `bool __fastcall(Art::BulletGalleryUser *__hidden this)`
- caller_count: `0`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180009588`
- `0x180025530`
- `0x180125bc0`
- `0x180209c50`
- `0x18020bd40`
- `0x18020bffc`
- `0x180279050`
- `0x18029ab98`
- `0x1802c6534`
- `0x1802c6c60`
- `0x1802c71d8`
- `0x1806bc4f0`
- `0x1806bc6a8`
- `0x1806d19bc`

## import_xrefs

- `Mso98Win32Client!__imp_?GetGalleryDataSource@CMsoGalleryUserDefault@@UEAAAEAVGalleryDSSP@@XZ` at `0x18020be32`
- `Mso98Win32Client!__imp_?GetGalleryDataSource@CMsoGalleryUserDefault@@UEAAAEAVGalleryDSSP@@XZ` at `0x18020bf74`
- `Mso98Win32Client!__imp_?GetGalleryDataSource@CMsoGalleryUserDefault@@UEAAAEAVGalleryDSSP@@XZ` at `0x18020be32`
- `Mso98Win32Client!__imp_?GetGalleryDataSource@CMsoGalleryUserDefault@@UEAAAEAVGalleryDSSP@@XZ` at `0x18020bf74`
- `Mso98Win32Client!__imp_?FUpdate@CMsoGalleryUserDefault@@UEAA_NXZ` at `0x18020bd54`
- `Mso98Win32Client!__imp_?FUpdate@CMsoGalleryUserDefault@@UEAA_NXZ` at `0x18020bd54`
- `mso40uiWin32Client!__imp_?CreateBoolean@FlexValue@FlexUI@@SA_N_NAEAVFlexValueSP@2@@Z` at `0x18020be57`
- `mso40uiWin32Client!__imp_?CreateBoolean@FlexValue@FlexUI@@SA_N_NAEAVFlexValueSP@2@@Z` at `0x18020be57`
- `mso40uiWin32Client!__imp_?CreateImageTcid@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@EI_N1111I1K11@Z` at `0x18020bf6b`
- `mso40uiWin32Client!__imp_?CreateImageTcid@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@EI_N1111I1K11@Z` at `0x18020bf6b`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x18020be8f`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x18020bfcd`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x18020bfe4`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x18020be8f`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x18020bfcd`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x18020bfe4`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18020bf01`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18020bf92`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18020bf01`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18020bf92`

## pseudocode

```c
char __fastcall Art::BulletGalleryUser::FUpdate(struct Ofc::CProxyPtrImpl **this)
{
  char v2; // si
  Art *v3; // rcx
  int Tcid; // r15d
  Art::UserInterface *Checked; // rax
  struct Art::Selection *CurrentSelection; // rax
  char v8; // di
  __int64 v9; // r14
  unsigned __int16 v10; // ax
  unsigned __int16 v11; // dx
  int v12; // eax
  struct GalleryDSSP *GalleryDataSource; // rax
  NetUI::BaseValue *v14; // rcx
  NetUI::BaseValue *v15; // rbx
  __int64 v16; // rdi
  NetUI::BaseValue *v17; // [rsp+A8h] [rbp+10h] BYREF
  NetUI::BaseValue *v18; // [rsp+B0h] [rbp+18h] BYREF
  struct Ofc::CProxyPtrImpl *v19; // [rsp+B8h] [rbp+20h] BYREF

  if ( CMsoGalleryUserDefault::FUpdate((CMsoGalleryUserDefault *)this) )
  {
    v2 = 0;
    Tcid = Art::BulletGalleryUser::GetTcid((Art::BulletGalleryUser *)this);
    if ( !*((_BYTE *)this + 1418) )
    {
      v10 = Art::InstalledLanguage(v3);
      if ( Art::SrIsMELid((Art *)v10, v11) )
      {
        *((_BYTE *)this + 1418) = 1;
        v2 = 1;
      }
    }
    if ( Art::BulletGalleryUser::FEnabled((Art::BulletGalleryUser *)this) )
    {
      LOBYTE(v18) = 0;
      LODWORD(v19) = 0;
      LOBYTE(v17) = 0;
      Art::BulletGalleryUser::Refresh((Art::BulletGalleryUser *)this, 1, (bool *)&v18, (int *)&v19, (bool *)&v17);
      v19 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(this[100]);
      Checked = (Art::UserInterface *)Ofc::CProxyPtrImpl::GetChecked(v19);
      CurrentSelection = Art::UserInterface::GetCurrentSelection(Checked);
      v8 = 0;
      if ( CurrentSelection )
      {
        if ( *((_DWORD *)this + 204) )
          v8 = Art::TextToggleBulletCommand<Art::Bullet::AutonumberBullet>::FSameBulletType(CurrentSelection);
        else
          v8 = Art::TextToggleBulletCommand<Art::Bullet::CharBullet>::FSameBulletType(CurrentSelection);
      }
      v9 = *(_QWORD *)CMsoGalleryUserDefault::GetGalleryDataSource((CMsoGalleryUserDefault *)this);
      if ( v9 )
      {
        v18 = 0;
        FlexUI::FlexValue::CreateBoolean(v8, (struct FlexUI::FlexValueSP *)&v18);
        if ( v18 )
        {
          (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v9 + 48LL))(v9, 0, 1329594533);
          if ( v18 )
            NetUI::BaseValue::Release(v18);
        }
      }
      else
      {
        MsoShipAssertTagProc(7997248);
      }
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v19);
      if ( *((_BYTE *)this + 1418) != (_BYTE)v17 )
      {
        *((_BYTE *)this + 1418) = (_BYTE)v17;
        v2 = 1;
      }
    }
    if ( !v2 )
      return 1;
    v12 = Art::BulletGalleryUser::GetTcid((Art::BulletGalleryUser *)this);
    if ( v12 == Tcid )
      return 1;
    v17 = 0;
    FlexUI::FlexValue::CreateImageTcid(
      v12,
      (struct FlexUI::FlexValueSP *)&v17,
      3u,
      0xFFFFFFFF,
      0,
      0,
      1,
      0,
      1,
      0x10u,
      1,
      0xFF000000,
      0,
      0);
    GalleryDataSource = CMsoGalleryUserDefault::GetGalleryDataSource((CMsoGalleryUserDefault *)this);
    v14 = v17;
    v15 = v17;
    v16 = *(_QWORD *)GalleryDataSource;
    if ( *(_QWORD *)GalleryDataSource )
    {
      if ( !v17 )
        goto LABEL_26;
      NetUI::BaseValue::AddRef(v17);
      (*(void (__fastcall **)(__int64, _QWORD, __int64, NetUI::BaseValue *))(*(_QWORD *)v16 + 48LL))(v16, 0, 3, v15);
      NetUI::BaseValue::Release(v15);
    }
    else
    {
      MsoShipAssertTagProc(7997248);
    }
    v14 = v17;
LABEL_26:
    if ( v14 )
      NetUI::BaseValue::Release(v14);
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x18020bd40  mov     [rsp+arg_0], rbx
0x18020bd45  push    rsi
0x18020bd46  push    rdi
0x18020bd47  push    r12
0x18020bd49  push    r14
0x18020bd4b  push    r15
0x18020bd4d  sub     rsp, 70h
0x18020bd51  mov     rbx, rcx
0x18020bd54  call    cs:__imp_?FUpdate@CMsoGalleryUserDefault@@UEAA_NXZ; CMsoGalleryUserDefault::FUpdate(void)
0x18020bd5a  xor     r12d, r12d
0x18020bd5d  test    al, al
0x18020bd5f  jz      loc_18020BEC4
0x18020bd65  mov     sil, r12b
0x18020bd68  mov     rcx, rbx; this
0x18020bd6b  call    ?GetTcid@BulletGalleryUser@Art@@AEBAHXZ; Art::BulletGalleryUser::GetTcid(void)
0x18020bd70  mov     r15d, eax
0x18020bd73  cmp     [rbx+58Ah], r12b
0x18020bd7a  jz      loc_18020BECB
0x18020bd80  mov     rcx, rbx; this
0x18020bd83  call    ?FEnabled@BulletGalleryUser@Art@@EEAA_NXZ; Art::BulletGalleryUser::FEnabled(void)
0x18020bd88  test    al, al
0x18020bd8a  jnz     short loc_18020BDAC
0x18020bd8c  test    sil, sil
0x18020bd8f  jnz     loc_18020BF09
0x18020bd95  mov     al, 1
0x18020bd97  mov     rbx, [rsp+98h+arg_0]
0x18020bd9f  add     rsp, 70h
0x18020bda3  pop     r15
0x18020bda5  pop     r14
0x18020bda7  pop     r12
0x18020bda9  pop     rdi
0x18020bdaa  pop     rsi
0x18020bdab  retn
0x18020bdac  mov     byte ptr [rsp+98h+arg_10], r12b
0x18020bdb4  mov     dword ptr [rsp+98h+arg_18], r12d
0x18020bdbc  mov     byte ptr [rsp+98h+arg_8], r12b
0x18020bdc4  lea     rax, [rsp+98h+arg_8]
0x18020bdcc  mov     [rsp+98h+var_78], rax; bool *
0x18020bdd1  lea     r9, [rsp+98h+arg_18]; int *
0x18020bdd9  lea     r8, [rsp+98h+arg_10]; bool *
0x18020bde1  mov     dl, 1; bool
0x18020bde3  mov     rcx, rbx; this
0x18020bde6  call    ?Refresh@BulletGalleryUser@Art@@AEAAX_NAEA_NAEAH1@Z; Art::BulletGalleryUser::Refresh(bool,bool &,int &,bool &)
0x18020bdeb  mov     rcx, [rbx+320h]; struct Ofc::CProxyPtrImpl *
0x18020bdf2  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x18020bdf7  mov     [rsp+98h+arg_18], rax
0x18020bdff  mov     rcx, rax; this
0x18020be02  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x18020be07  mov     rcx, rax; this
0x18020be0a  call    ?GetCurrentSelection@UserInterface@Art@@QEAAPEAVSelection@2@XZ; Art::UserInterface::GetCurrentSelection(void)
0x18020be0f  mov     dil, r12b
0x18020be12  test    rax, rax
0x18020be15  jz      short loc_18020BE2F
0x18020be17  mov     rcx, rax
0x18020be1a  cmp     [rbx+330h], r12d
0x18020be21  jnz     loc_18020BEEF
0x18020be27  call    ?FSameBulletType@?$TextToggleBulletCommand@UCharBullet@Bullet@Art@@@Art@@SA_NAEAVSelection@2@@Z; Art::TextToggleBulletCommand<Art::Bullet::CharBullet>::FSameBulletType(Art::Selection &)
0x18020be2c  mov     dil, al
0x18020be2f  mov     rcx, rbx
0x18020be32  call    cs:__imp_?GetGalleryDataSource@CMsoGalleryUserDefault@@UEAAAEAVGalleryDSSP@@XZ; CMsoGalleryUserDefault::GetGalleryDataSource(void)
0x18020be38  mov     r14, [rax]
0x18020be3b  test    r14, r14
0x18020be3e  jz      loc_18020BEFC
0x18020be44  mov     [rsp+98h+arg_10], r12
0x18020be4c  lea     rdx, [rsp+98h+arg_10]
0x18020be54  mov     cl, dil
0x18020be57  call    cs:__imp_?CreateBoolean@FlexValue@FlexUI@@SA_N_NAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateBoolean(bool,FlexUI::FlexValueSP &)
0x18020be5d  mov     r9, [rsp+98h+arg_10]
0x18020be65  test    r9, r9
0x18020be68  jz      short loc_18020BE96
0x18020be6a  mov     rax, [r14]
0x18020be6d  xor     edx, edx
0x18020be6f  mov     r8d, 4F4000A5h
0x18020be75  mov     rcx, r14
0x18020be78  mov     rax, [rax+30h]
0x18020be7c  call    cs:__guard_dispatch_icall_fptr
0x18020be82  mov     rcx, [rsp+98h+arg_10]
0x18020be8a  test    rcx, rcx
0x18020be8d  jz      short loc_18020BE96
0x18020be8f  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x18020be95  nop
0x18020be96  lea     rcx, [rsp+98h+arg_18]; struct Ofc::CProxyPtrImpl **
0x18020be9e  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x18020bea3  mov     al, byte ptr [rsp+98h+arg_8]
0x18020beaa  cmp     [rbx+58Ah], al
0x18020beb0  jz      loc_18020BD8C
0x18020beb6  mov     [rbx+58Ah], al
0x18020bebc  mov     sil, 1
0x18020bebf  jmp     loc_18020BD8C
0x18020bec4  xor     al, al
0x18020bec6  jmp     loc_18020BD97
0x18020becb  call    ?InstalledLanguage@Art@@YAGXZ; Art::InstalledLanguage(void)
0x18020bed0  movzx   ecx, ax; this
0x18020bed3  call    ?SrIsMELid@Art@@YA_NG@Z; Art::SrIsMELid(ushort)
0x18020bed8  test    al, al
0x18020beda  jz      loc_18020BD80
0x18020bee0  mov     byte ptr [rbx+58Ah], 1
0x18020bee7  mov     sil, 1
0x18020beea  jmp     loc_18020BD80
0x18020beef  call    ?FSameBulletType@?$TextToggleBulletCommand@UAutonumberBullet@Bullet@Art@@@Art@@SA_NAEAVSelection@2@@Z; Art::TextToggleBulletCommand<Art::Bullet::AutonumberBullet>::FSameBulletType(Art::Selection &)
0x18020bef4  mov     dil, al
0x18020bef7  jmp     loc_18020BE2F
0x18020befc  mov     ecx, 7A0740h
0x18020bf01  call    cs:__imp_MsoShipAssertTagProc
0x18020bf07  jmp     short loc_18020BE96
0x18020bf09  mov     rcx, rbx; this
0x18020bf0c  call    ?GetTcid@BulletGalleryUser@Art@@AEBAHXZ; Art::BulletGalleryUser::GetTcid(void)
0x18020bf11  cmp     eax, r15d
0x18020bf14  jz      loc_18020BD95
0x18020bf1a  mov     [rsp+98h+arg_8], r12
0x18020bf22  mov     [rsp+98h+var_30], r12b
0x18020bf27  mov     [rsp+98h+var_38], r12b
0x18020bf2c  mov     [rsp+98h+var_40], 0FF000000h
0x18020bf34  mov     [rsp+98h+var_48], 1
0x18020bf39  mov     [rsp+98h+var_50], 10h
0x18020bf41  mov     [rsp+98h+var_58], 1
0x18020bf46  mov     [rsp+98h+var_60], r12b
0x18020bf4b  mov     [rsp+98h+var_68], 1
0x18020bf50  mov     [rsp+98h+var_70], r12b
0x18020bf55  mov     byte ptr [rsp+98h+var_78], r12b
0x18020bf5a  or      r9d, 0FFFFFFFFh
0x18020bf5e  mov     r8b, 3
0x18020bf61  lea     rdx, [rsp+98h+arg_8]
0x18020bf69  mov     ecx, eax
0x18020bf6b  call    cs:__imp_?CreateImageTcid@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@EI_N1111I1K11@Z; FlexUI::FlexValue::CreateImageTcid(int,FlexUI::FlexValueSP &,uchar,uint,bool,bool,bool,bool,bool,uint,bool,ulong,bool,bool)
0x18020bf71  mov     rcx, rbx
0x18020bf74  call    cs:__imp_?GetGalleryDataSource@CMsoGalleryUserDefault@@UEAAAEAVGalleryDSSP@@XZ; CMsoGalleryUserDefault::GetGalleryDataSource(void)
0x18020bf7a  mov     rcx, [rsp+98h+arg_8]; this
0x18020bf82  mov     rbx, rcx
0x18020bf85  mov     rdi, [rax]
0x18020bf88  test    rdi, rdi
0x18020bf8b  jnz     short loc_18020BF9A
0x18020bf8d  mov     ecx, 7A0740h
0x18020bf92  call    cs:__imp_MsoShipAssertTagProc
0x18020bf98  jmp     short loc_18020BFD3
0x18020bf9a  test    rbx, rbx
0x18020bf9d  jz      short loc_18020BFDB
0x18020bf9f  call    ?AddRef@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::AddRef(void)
0x18020bfa4  mov     rcx, [rsp+98h+arg_8]
0x18020bfac  test    rbx, rbx
0x18020bfaf  jz      short loc_18020BFDB
0x18020bfb1  mov     rax, [rdi]
0x18020bfb4  mov     r9, rbx
0x18020bfb7  xor     edx, edx
0x18020bfb9  lea     r8d, [rdx+3]
0x18020bfbd  mov     rcx, rdi
0x18020bfc0  mov     rax, [rax+30h]
0x18020bfc4  call    cs:__guard_dispatch_icall_fptr
0x18020bfca  mov     rcx, rbx
0x18020bfcd  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x18020bfd3  mov     rcx, [rsp+98h+arg_8]
0x18020bfdb  test    rcx, rcx
0x18020bfde  jz      loc_18020BD95
0x18020bfe4  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x18020bfea  jmp     loc_18020BD95
0x18020bfef  mov     al, byte ptr [rsp+98h+arg_8]
0x18020bff6  jmp     loc_18020BD97
```
