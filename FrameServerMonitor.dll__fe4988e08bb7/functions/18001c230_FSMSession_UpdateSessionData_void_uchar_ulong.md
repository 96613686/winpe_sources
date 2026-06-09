# FSMSession::UpdateSessionData(void *,uchar *,ulong)

- ea: `0x18001c230`
- end: `0x18001c45a`
- name: `?UpdateSessionData@FSMSession@@UEAAJPEAXPEAEK@Z`
- size: `554`
- prototype: `int(FSMSession *__hidden this, void *, unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1800019f0`
- `0x180005f98`
- `0x1800060f8`
- `0x180006a68`
- `0x180006a98`
- `0x18001b660`
- `0x18001c230`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c266`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c266`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c435`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c435`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001c3a6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001c3f0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001c3a6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001c3f0`
- `MFPlat!MFCreateAttributes` at `0x18001c2b6`
- `MFPlat!MFCreateAttributes` at `0x18001c2b6`
- `MFPlat!MFInitAttributesFromBlob` at `0x18001c2e3`
- `MFPlat!MFInitAttributesFromBlob` at `0x18001c2e3`

## pseudocode

```c
__int64 __fastcall FSMSession::UpdateSessionData(FSMSession *this, void *a2, unsigned __int8 *a3, UINT a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // rbx
  FSMSession *v6; // r14
  struct FSMSessionIdentity *SessionByHandle; // r13
  HRESULT v10; // edi
  __int64 v11; // rdx
  unsigned int i; // esi
  __int64 v13; // rdx
  IMFAttributes *ppMFAttributes; // [rsp+30h] [rbp-48h] BYREF
  unsigned int v16; // [rsp+38h] [rbp-40h] BYREF
  PROPVARIANT pvar[2]; // [rsp+40h] [rbp-38h] BYREF
  __int64 v18; // [rsp+50h] [rbp-28h]
  GUID v19; // [rsp+58h] [rbp-20h] BYREF

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  v6 = (FSMSession *)((char *)this - 40);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  ppMFAttributes = 0;
  v16 = 0;
  SessionByHandle = FSMSession::InternalFindSessionByHandle(v6, a2);
  if ( SessionByHandle && a3 && a4 )
  {
    wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&ppMFAttributes);
    v10 = MFCreateAttributes(&ppMFAttributes, 1u);
    if ( v10 >= 0 )
    {
      v10 = MFInitAttributesFromBlob(ppMFAttributes, a3, a4);
      if ( v10 >= 0 )
      {
        v10 = ((__int64 (__fastcall *)(IMFAttributes *, unsigned int *))ppMFAttributes->lpVtbl->GetCount)(
                ppMFAttributes,
                &v16);
        if ( v10 >= 0 )
        {
          for ( i = 0; ; ++i )
          {
            if ( i >= v16 )
              goto LABEL_27;
            v18 = 0;
            v19 = GUID_00000000_0000_0000_0000_000000000000;
            *(_OWORD *)pvar = 0;
            v10 = ((__int64 (__fastcall *)(IMFAttributes *, _QWORD, GUID *, PROPVARIANT *))ppMFAttributes->lpVtbl->GetItemByIndex)(
                    ppMFAttributes,
                    i,
                    &v19,
                    pvar);
            if ( v10 < 0 )
              break;
            v10 = (*(__int64 (__fastcall **)(struct FSMSessionIdentity *, GUID *, PROPVARIANT *))(*(_QWORD *)SessionByHandle
                                                                                                + 144LL))(
                    SessionByHandle,
                    &v19,
                    pvar);
            if ( v10 < 0 )
            {
              if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              {
                v13 = 27;
                goto LABEL_22;
              }
              goto LABEL_23;
            }
            PropVariantClear(pvar);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v13 = 26;
LABEL_22:
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v13,
              &WPP_dda53059c67a34537508687cb55acb7f_Traceguids,
              v6,
              v10);
          }
LABEL_23:
          PropVariantClear(pvar);
          goto LABEL_27;
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v11 = 25;
          goto LABEL_26;
        }
      }
      else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v11 = 24;
        goto LABEL_26;
      }
    }
    else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v11 = 23;
LABEL_26:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, &WPP_dda53059c67a34537508687cb55acb7f_Traceguids, v6, v10);
    }
  }
  else
  {
    v10 = -2147024809;
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v11 = 22;
      goto LABEL_26;
    }
  }
LABEL_27:
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&ppMFAttributes);
  LeaveCriticalSection(v4);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18001c230  push    rbp
0x18001c232  push    rbx
0x18001c233  push    rsi
0x18001c234  push    rdi
0x18001c235  push    r12
0x18001c237  push    r13
0x18001c239  push    r14
0x18001c23b  push    r15
0x18001c23d  mov     rbp, rsp
0x18001c240  sub     rsp, 78h
0x18001c244  mov     rax, cs:__security_cookie
0x18001c24b  xor     rax, rsp
0x18001c24e  mov     [rbp+var_10], rax
0x18001c252  lea     rbx, [rcx+10h]
0x18001c256  mov     r12d, r9d
0x18001c259  lea     r14, [rcx-28h]
0x18001c25d  mov     r15, r8
0x18001c260  mov     rcx, rbx; lpCriticalSection
0x18001c263  mov     rsi, rdx
0x18001c266  call    cs:__imp_EnterCriticalSection
0x18001c26c  mov     rdx, rsi; void *
0x18001c26f  mov     [rbp+ppMFAttributes], 0
0x18001c277  mov     rcx, r14; this
0x18001c27a  call    ?InternalFindSessionByHandle@FSMSession@@IEAAPEAVFSMSessionIdentity@@PEAX@Z; FSMSession::InternalFindSessionByHandle(void *)
0x18001c27f  mov     [rbp+var_40], 0
0x18001c286  mov     r13, rax
0x18001c289  test    rax, rax
0x18001c28c  jz      loc_18001C3F8
0x18001c292  test    r15, r15
0x18001c295  jz      loc_18001C3F8
0x18001c29b  test    r12d, r12d
0x18001c29e  jz      loc_18001C3F8
0x18001c2a4  lea     rcx, [rbp+ppMFAttributes]
0x18001c2a8  call    ?reset@?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(void)
0x18001c2ad  mov     edx, 1; cInitialSize
0x18001c2b2  lea     rcx, [rbp+ppMFAttributes]; ppMFAttributes
0x18001c2b6  call    cs:__imp_MFCreateAttributes
0x18001c2bc  mov     edi, eax
0x18001c2be  test    eax, eax
0x18001c2c0  jns     short loc_18001C2D9
0x18001c2c2  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001c2c7  cmp     al, 1
0x18001c2c9  jb      loc_18001C429
0x18001c2cf  mov     edx, 17h
0x18001c2d4  jmp     loc_18001C40B
0x18001c2d9  mov     rcx, [rbp+ppMFAttributes]; pAttributes
0x18001c2dd  mov     r8d, r12d; cbBufSize
0x18001c2e0  mov     rdx, r15; pBuf
0x18001c2e3  call    cs:__imp_MFInitAttributesFromBlob
0x18001c2e9  mov     edi, eax
0x18001c2eb  test    eax, eax
0x18001c2ed  jns     short loc_18001C306
0x18001c2ef  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001c2f4  cmp     al, 1
0x18001c2f6  jb      loc_18001C429
0x18001c2fc  mov     edx, 18h
0x18001c301  jmp     loc_18001C40B
0x18001c306  mov     rcx, [rbp+ppMFAttributes]
0x18001c30a  lea     rdx, [rbp+var_40]
0x18001c30e  mov     rax, [rcx]
0x18001c311  mov     rax, [rax+0F0h]
0x18001c318  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c31d  mov     edi, eax
0x18001c31f  test    eax, eax
0x18001c321  jns     short loc_18001C33A
0x18001c323  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001c328  cmp     al, 1
0x18001c32a  jb      loc_18001C429
0x18001c330  mov     edx, 19h
0x18001c335  jmp     loc_18001C40B
0x18001c33a  xor     esi, esi
0x18001c33c  cmp     esi, [rbp+var_40]
0x18001c33f  jnb     loc_18001C429
0x18001c345  movups  xmm1, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18001c34c  mov     rcx, [rbp+ppMFAttributes]
0x18001c350  lea     r9, [rbp+pvar]
0x18001c354  xor     eax, eax
0x18001c356  lea     r8, [rbp+var_20]
0x18001c35a  mov     [rbp+var_28], rax
0x18001c35e  xorps   xmm0, xmm0
0x18001c361  movdqu  [rbp+var_20], xmm1
0x18001c366  mov     edx, esi
0x18001c368  movups  xmmword ptr [rbp+pvar], xmm0
0x18001c36c  mov     rax, [rcx]
0x18001c36f  mov     rax, [rax+0F8h]
0x18001c376  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c37b  mov     edi, eax
0x18001c37d  test    eax, eax
0x18001c37f  js      short loc_18001C3C0
0x18001c381  mov     rax, [r13+0]
0x18001c385  lea     r8, [rbp+pvar]
0x18001c389  lea     rdx, [rbp+var_20]
0x18001c38d  mov     rcx, r13
0x18001c390  mov     rax, [rax+90h]
0x18001c397  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c39c  mov     edi, eax
0x18001c39e  test    eax, eax
0x18001c3a0  js      short loc_18001C3B0
0x18001c3a2  lea     rcx, [rbp+pvar]; pvar
0x18001c3a6  call    cs:__imp_PropVariantClear
0x18001c3ac  inc     esi
0x18001c3ae  jmp     short loc_18001C33C
0x18001c3b0  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001c3b5  cmp     al, 1
0x18001c3b7  jb      short loc_18001C3EC
0x18001c3b9  mov     edx, 1Bh
0x18001c3be  jmp     short loc_18001C3CE
0x18001c3c0  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001c3c5  cmp     al, 1
0x18001c3c7  jb      short loc_18001C3EC
0x18001c3c9  mov     edx, 1Ah
0x18001c3ce  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c3d5  lea     r8, WPP_dda53059c67a34537508687cb55acb7f_Traceguids
0x18001c3dc  mov     r9, r14
0x18001c3df  mov     [rsp+78h+var_58], edi
0x18001c3e3  mov     rcx, [rcx+10h]
0x18001c3e7  call    WPP_SF_qD
0x18001c3ec  lea     rcx, [rbp+pvar]; pvar
0x18001c3f0  call    cs:__imp_PropVariantClear
0x18001c3f6  jmp     short loc_18001C429
0x18001c3f8  mov     edi, 80070057h
0x18001c3fd  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001c402  cmp     al, 1
0x18001c404  jb      short loc_18001C429
0x18001c406  mov     edx, 16h
0x18001c40b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c412  lea     r8, WPP_dda53059c67a34537508687cb55acb7f_Traceguids
0x18001c419  mov     r9, r14
0x18001c41c  mov     [rsp+78h+var_58], edi
0x18001c420  mov     rcx, [rcx+10h]
0x18001c424  call    WPP_SF_qD
0x18001c429  lea     rcx, [rbp+ppMFAttributes]
0x18001c42d  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x18001c432  mov     rcx, rbx; lpCriticalSection
0x18001c435  call    cs:__imp_LeaveCriticalSection
0x18001c43b  mov     eax, edi
0x18001c43d  mov     rcx, [rbp+var_10]
0x18001c441  xor     rcx, rsp; StackCookie
0x18001c444  call    __security_check_cookie
0x18001c449  add     rsp, 78h
0x18001c44d  pop     r15
0x18001c44f  pop     r14
0x18001c451  pop     r13
0x18001c453  pop     r12
0x18001c455  pop     rdi
0x18001c456  pop     rsi
0x18001c457  pop     rbx
0x18001c458  pop     rbp
0x18001c459  retn
```
