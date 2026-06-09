# FSIsUserOptInForWindowsEffects(ushort const *)

- ea: `0x18006f5ec`
- end: `0x18006f7a7`
- name: `?FSIsUserOptInForWindowsEffects@@YA_NPEBG@Z`
- size: `443`
- prototype: `bool __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002eb64`

## callees

- `0x180005fa0`
- `0x180008f9c`
- `0x18001b3d8`
- `0x180028d34`
- `0x18002c008`
- `0x18006f5ec`
- `0x180077010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006f67c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006f67c`
- `MFPlat!MFCreateAttributes` at `0x18006f6b0`
- `MFPlat!MFCreateAttributes` at `0x18006f6b0`

## pseudocode

```c
bool __fastcall FSIsUserOptInForWindowsEffects(const unsigned __int16 *a1)
{
  bool v1; // r14
  HRESULT v3; // eax
  __int64 v4; // rdx
  LPVOID v5; // rdi
  __int64 (__fastcall *v6)(LPVOID, IMFAttributes *, __int64 *); // rbx
  IMFAttributes *ppMFAttributes; // [rsp+50h] [rbp+20h] BYREF
  __int64 v9; // [rsp+58h] [rbp+28h] BYREF
  LPVOID ppv; // [rsp+60h] [rbp+30h] BYREF

  v1 = 0;
  ppv = 0;
  ppMFAttributes = 0;
  v9 = 0;
  if ( !a1 )
  {
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        110,
        &WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids,
        0,
        -2147024809);
    goto LABEL_22;
  }
  wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(&ppv);
  v3 = CoCreateInstance(&CLSID_CameraConfigurationManager, 0, 1u, &GUID_a624f617_4704_4206_8a6d_ebda4a093985, &ppv);
  if ( v3 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_22;
    v4 = 111;
LABEL_8:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v4, &WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids, 0, v3);
    goto LABEL_22;
  }
  wil::com_ptr_t<IMFAttributes,wil::err_returncode_policy>::reset(&ppMFAttributes);
  v3 = MFCreateAttributes(&ppMFAttributes, 1u);
  if ( v3 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_22;
    v4 = 112;
    goto LABEL_8;
  }
  if ( ppMFAttributes )
  {
    v3 = ((__int64 (__fastcall *)(IMFAttributes *, const IID *, const unsigned __int16 *))ppMFAttributes->lpVtbl->SetString)(
           ppMFAttributes,
           &MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE_VIDCAP_SYMBOLIC_LINK,
           a1);
    if ( v3 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_22;
      v4 = 114;
      goto LABEL_8;
    }
    v5 = ppv;
    v6 = *(__int64 (__fastcall **)(LPVOID, IMFAttributes *, __int64 *))(*(_QWORD *)ppv + 24LL);
    wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(&v9);
    v3 = v6(v5, ppMFAttributes, &v9);
    if ( v3 >= 0 )
    {
      v1 = (unsigned int)MFGetAttributeUINT32(v9, MF_DEVSOURCE_ATTRIBUTE_ENABLE_MS_CAMERA_EFFECTS, 0) != 0;
      goto LABEL_22;
    }
    if ( g_wppLevels )
    {
      v4 = 115;
      goto LABEL_8;
    }
  }
  else if ( g_wppLevels )
  {
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (unsigned int)((_DWORD)ppMFAttributes + 113),
      &WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids,
      0,
      -2147024882);
  }
LABEL_22:
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(&v9);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&ppMFAttributes);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&ppv);
  return v1;
}

```

## disassembly

```asm
0x18006f5ec  mov     [rsp-18h+arg_18], rbx
0x18006f5f1  push    rbp
0x18006f5f2  push    rdi
0x18006f5f3  push    r14
0x18006f5f5  mov     rbp, rsp
0x18006f5f8  sub     rsp, 30h
0x18006f5fc  xor     r14b, r14b
0x18006f5ff  mov     [rbp+arg_10], 0
0x18006f607  mov     [rbp+ppMFAttributes], 0
0x18006f60f  mov     rbx, rcx
0x18006f612  mov     [rbp+arg_8], 0
0x18006f61a  test    rcx, rcx
0x18006f61d  jnz     short loc_18006F656
0x18006f61f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006f626  jb      loc_18006F77B
0x18006f62c  lea     edx, [rcx+6Eh]
0x18006f62f  mov     dword ptr [rsp+30h+ppv], 80070057h
0x18006f637  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f63e  lea     r8, WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids
0x18006f645  xor     r9d, r9d
0x18006f648  mov     rcx, [rcx+10h]
0x18006f64c  call    WPP_SF_qD
0x18006f651  jmp     loc_18006F77B
0x18006f656  lea     rcx, [rbp+arg_10]
0x18006f65a  call    ?reset@?$com_ptr_t@UIRelativePanelDirectionTracker@System@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(void)
0x18006f65f  xor     edx, edx; pUnkOuter
0x18006f661  lea     rax, [rbp+arg_10]
0x18006f665  lea     r9, _GUID_a624f617_4704_4206_8a6d_ebda4a093985; riid
0x18006f66c  mov     [rsp+30h+ppv], rax; ppv
0x18006f671  lea     rcx, CLSID_CameraConfigurationManager; rclsid
0x18006f678  lea     r8d, [rdx+1]; dwClsContext
0x18006f67c  call    cs:__imp_CoCreateInstance
0x18006f682  test    eax, eax
0x18006f684  jns     short loc_18006F69E
0x18006f686  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006f68d  jb      loc_18006F77B
0x18006f693  mov     edx, 6Fh ; 'o'
0x18006f698  mov     dword ptr [rsp+30h+ppv], eax
0x18006f69c  jmp     short loc_18006F637
0x18006f69e  lea     rcx, [rbp+ppMFAttributes]
0x18006f6a2  call    ?reset@?$com_ptr_t@UIMFAttributes@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMFAttributes,wil::err_returncode_policy>::reset(void)
0x18006f6a7  mov     edx, 1; cInitialSize
0x18006f6ac  lea     rcx, [rbp+ppMFAttributes]; ppMFAttributes
0x18006f6b0  call    cs:__imp_MFCreateAttributes
0x18006f6b6  test    eax, eax
0x18006f6b8  jns     short loc_18006F6CE
0x18006f6ba  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006f6c1  jb      loc_18006F77B
0x18006f6c7  mov     edx, 70h ; 'p'
0x18006f6cc  jmp     short loc_18006F698
0x18006f6ce  mov     rcx, [rbp+ppMFAttributes]
0x18006f6d2  test    rcx, rcx
0x18006f6d5  jnz     short loc_18006F6F4
0x18006f6d7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006f6de  jb      loc_18006F77B
0x18006f6e4  lea     edx, [rcx+71h]
0x18006f6e7  mov     dword ptr [rsp+30h+ppv], 8007000Eh
0x18006f6ef  jmp     loc_18006F637
0x18006f6f4  mov     rax, [rcx]
0x18006f6f7  lea     rdx, MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE_VIDCAP_SYMBOLIC_LINK
0x18006f6fe  mov     r8, rbx
0x18006f701  mov     rax, [rax+0C8h]
0x18006f708  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f70d  test    eax, eax
0x18006f70f  jns     short loc_18006F724
0x18006f711  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006f718  jb      short loc_18006F77B
0x18006f71a  mov     edx, 72h ; 'r'
0x18006f71f  jmp     loc_18006F698
0x18006f724  mov     rdi, [rbp+arg_10]
0x18006f728  lea     rcx, [rbp+arg_8]
0x18006f72c  mov     rax, [rdi]
0x18006f72f  mov     rbx, [rax+18h]
0x18006f733  call    ?reset@?$com_ptr_t@UIRelativePanelDirectionTracker@System@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(void)
0x18006f738  mov     rdx, [rbp+ppMFAttributes]
0x18006f73c  lea     r8, [rbp+arg_8]
0x18006f740  mov     rcx, rdi
0x18006f743  mov     rax, rbx
0x18006f746  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f74b  test    eax, eax
0x18006f74d  jns     short loc_18006F762
0x18006f74f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006f756  jb      short loc_18006F77B
0x18006f758  mov     edx, 73h ; 's'
0x18006f75d  jmp     loc_18006F698
0x18006f762  mov     rcx, [rbp+arg_8]
0x18006f766  lea     rdx, MF_DEVSOURCE_ATTRIBUTE_ENABLE_MS_CAMERA_EFFECTS
0x18006f76d  xor     r8d, r8d
0x18006f770  call    MFGetAttributeUINT32
0x18006f775  test    eax, eax
0x18006f777  setnz   r14b
0x18006f77b  lea     rcx, [rbp+arg_8]
0x18006f77f  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x18006f784  lea     rcx, [rbp+ppMFAttributes]
0x18006f788  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x18006f78d  lea     rcx, [rbp+arg_10]
0x18006f791  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x18006f796  mov     rbx, [rsp+30h+arg_18]
0x18006f79b  mov     al, r14b
0x18006f79e  add     rsp, 30h
0x18006f7a2  pop     r14
0x18006f7a4  pop     rdi
0x18006f7a5  pop     rbp
0x18006f7a6  retn
```
