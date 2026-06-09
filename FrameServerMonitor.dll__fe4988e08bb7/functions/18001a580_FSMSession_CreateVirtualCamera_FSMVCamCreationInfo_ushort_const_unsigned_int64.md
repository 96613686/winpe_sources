# FSMSession::CreateVirtualCamera(FSMVCamCreationInfo &,ushort const *,unsigned __int64 *)

- ea: `0x18001a580`
- end: `0x18001a8a7`
- name: `?CreateVirtualCamera@FSMSession@@UEAAJAEAUFSMVCamCreationInfo@@PEBGPEA_K@Z`
- size: `807`
- prototype: `__int64 __fastcall(unsigned __int64 this, struct FSMVCamCreationInfo *, unsigned __int16 *, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x1800019f0`
- `0x180005f98`
- `0x1800060e8`
- `0x1800060f8`
- `0x180006a98`
- `0x18000c8d4`
- `0x18000d4f8`
- `0x18001a580`
- `0x18001b784`
- `0x18001eeb0`
- `0x180044ce8`
- `0x180045db4`
- `0x18004bf44`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a5be`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a5be`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a874`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a874`

## pseudocode

```c
__int64 __fastcall FSMSession::CreateVirtualCamera(
        unsigned __int64 this,
        struct FSMVCamCreationInfo *a2,
        unsigned __int16 *a3,
        unsigned __int64 *a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // rbx
  char *v8; // rsi
  unsigned int v9; // eax
  unsigned __int16 *UserSidString; // r14
  int v11; // edi
  __int64 v12; // rdx
  unsigned int v13; // r14d
  char *v14; // r15
  __int64 v15; // rax
  __int64 v16; // rax
  void *v17; // rcx
  void *v18; // rcx
  __int64 v19; // rbp
  void *v20; // r14
  __int64 v21; // rdx
  struct _GUID *v23; // [rsp+20h] [rbp-A8h]
  void *v24; // [rsp+30h] [rbp-98h] BYREF
  unsigned int v25; // [rsp+38h] [rbp-90h]
  char *v26; // [rsp+40h] [rbp-88h]
  unsigned __int16 *v27; // [rsp+48h] [rbp-80h]
  __int64 v28; // [rsp+50h] [rbp-78h]
  unsigned __int16 *v29; // [rsp+58h] [rbp-70h]
  _OWORD Buf2[2]; // [rsp+60h] [rbp-68h] BYREF

  v4 = (struct _RTL_CRITICAL_SECTION *)(this + 16);
  v29 = a3;
  EnterCriticalSection((LPCRITICAL_SECTION)(this + 16));
  v8 = (char *)(this - 40);
  v9 = *(_DWORD *)(this - 40 + 272);
  memset(Buf2, 0, sizeof(Buf2));
  v25 = v9;
  if ( *((_DWORD *)a2 + 2) )
    UserSidString = 0;
  else
    UserSidString = (unsigned __int16 *)FSMSession::InternalGetUserSidString((FSMSession *)(this - 40));
  v27 = UserSidString;
  v24 = 0;
  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 72, &WPP_dda53059c67a34537508687cb55acb7f_Traceguids, this - 40);
  if ( !a4 )
  {
    v11 = -2147467261;
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_34;
    v12 = 73;
    goto LABEL_33;
  }
  *a4 = 0;
  v11 = FSMValidateVirtualCameraCreationInfo(a2);
  if ( v11 < 0 )
  {
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_34;
    v12 = 74;
    goto LABEL_33;
  }
  if ( !*(_BYTE *)(this + 144) && !*(_BYTE *)(this + 160) )
  {
    v11 = -1072875854;
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_34;
    v12 = 75;
    goto LABEL_33;
  }
  v11 = FSMCreateVirtualCameraHash(a2, UserSidString, Buf2, 32);
  if ( v11 >= 0 )
  {
    v13 = 0;
    v14 = (char *)(this + 224);
    v26 = (char *)(this + 224);
    while ( v13 < v25 )
    {
      v26 = (char *)(this + 224);
      v15 = *(_QWORD *)(this + 224);
      v28 = v13;
      v16 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v15 + 8LL * v13) + 32LL))(*(_QWORD *)(v15 + 8LL * v13));
      if ( !memcmp_0((const void *)(v16 + 24), Buf2, 0x20u) )
      {
        _mm_lfence();
        v17 = *(void **)(*(_QWORD *)v26 + 8 * v28);
        goto LABEL_39;
      }
      ++v13;
    }
    v18 = v24;
    v24 = 0;
    if ( v18 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v18 + 16LL))(v18);
    else
      v14 = v26;
    v11 = FSMVirtualCamera::CreateFSMVirtualCamera(
            a2,
            (struct IFSMSession *)(this & -(__int64)(this != 40)),
            v29,
            v27,
            v23,
            &v24);
    if ( v11 < 0 )
    {
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_34;
      v12 = 77;
      goto LABEL_33;
    }
    v19 = *((unsigned int *)v14 + 2);
    v20 = v24;
    if ( !(unsigned int)CTEntryArray<IFSConfigurationEntry *>::SetSize(v14, (unsigned int)(v19 + 1)) )
    {
      v11 = -2147024882;
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_34;
      v12 = 78;
      goto LABEL_33;
    }
    *(_QWORD *)(*(_QWORD *)v14 + 8 * v19) = v20;
    if ( v20 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v20 + 8LL))(v20);
    v17 = v24;
LABEL_39:
    *a4 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v17 + 24LL))(v17);
    if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() < 8u )
      goto LABEL_42;
    v21 = 80;
    goto LABEL_41;
  }
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v12 = 76;
LABEL_33:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, &WPP_dda53059c67a34537508687cb55acb7f_Traceguids, v8, v11);
  }
LABEL_34:
  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() )
  {
    v21 = 79;
LABEL_41:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), v21, &WPP_dda53059c67a34537508687cb55acb7f_Traceguids, v8, v11);
  }
LABEL_42:
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v24);
  LeaveCriticalSection(v4);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18001a580  mov     [rsp+arg_10], rbx
0x18001a585  push    rbp
0x18001a586  push    rsi
0x18001a587  push    rdi
0x18001a588  push    r12
0x18001a58a  push    r13
0x18001a58c  push    r14
0x18001a58e  push    r15
0x18001a590  sub     rsp, 90h
0x18001a597  mov     rax, cs:__security_cookie
0x18001a59e  xor     rax, rsp
0x18001a5a1  mov     [rsp+0C8h+var_48], rax
0x18001a5a9  lea     rbx, [rcx+10h]
0x18001a5ad  mov     [rsp+0C8h+var_70], r8
0x18001a5b2  mov     rbp, rcx
0x18001a5b5  mov     r12, r9
0x18001a5b8  mov     rcx, rbx; lpCriticalSection
0x18001a5bb  mov     r13, rdx
0x18001a5be  call    cs:__imp_EnterCriticalSection
0x18001a5c4  xorps   xmm0, xmm0
0x18001a5c7  lea     rsi, [rbp-28h]
0x18001a5cb  mov     eax, [rsi+110h]
0x18001a5d1  xor     r15d, r15d
0x18001a5d4  movups  [rsp+0C8h+Buf2], xmm0
0x18001a5d9  mov     [rsp+0C8h+var_90], eax
0x18001a5dd  movups  [rsp+0C8h+var_58], xmm0
0x18001a5e2  cmp     [r13+8], r15d
0x18001a5e6  jnz     short loc_18001A5F5
0x18001a5e8  mov     rcx, rsi; this
0x18001a5eb  call    ?InternalGetUserSidString@FSMSession@@IEAAPEBGXZ; FSMSession::InternalGetUserSidString(void)
0x18001a5f0  mov     r14, rax
0x18001a5f3  jmp     short loc_18001A5F8
0x18001a5f5  mov     r14, r15
0x18001a5f8  mov     [rsp+0C8h+var_80], r14
0x18001a5fd  mov     [rsp+0C8h+var_98], r15
0x18001a602  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x18001a607  cmp     al, 8
0x18001a609  jb      short loc_18001A62D
0x18001a60b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a612  lea     r8, WPP_dda53059c67a34537508687cb55acb7f_Traceguids
0x18001a619  mov     edx, 48h ; 'H'
0x18001a61e  mov     r9, rsi
0x18001a621  mov     rcx, [rcx+0D8h]
0x18001a628  call    WPP_SF_q
0x18001a62d  test    r12, r12
0x18001a630  jnz     short loc_18001A64E
0x18001a632  mov     edi, 80004003h
0x18001a637  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001a63c  cmp     al, 1
0x18001a63e  jb      loc_18001A7F8
0x18001a644  lea     edx, [r12+49h]
0x18001a649  jmp     loc_18001A7DA
0x18001a64e  mov     rcx, r13
0x18001a651  mov     [r12], r15
0x18001a655  call    FSMValidateVirtualCameraCreationInfo
0x18001a65a  mov     edi, eax
0x18001a65c  test    eax, eax
0x18001a65e  jns     short loc_18001A677
0x18001a660  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001a665  cmp     al, 1
0x18001a667  jb      loc_18001A7F8
0x18001a66d  mov     edx, 4Ah ; 'J'
0x18001a672  jmp     loc_18001A7DA
0x18001a677  cmp     [rbp+90h], r15b
0x18001a67e  jnz     short loc_18001A6A5
0x18001a680  cmp     [rbp+0A0h], r15b
0x18001a687  jnz     short loc_18001A6A5
0x18001a689  mov     edi, 0C00D36B2h
0x18001a68e  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001a693  cmp     al, 1
0x18001a695  jb      loc_18001A7F8
0x18001a69b  mov     edx, 4Bh ; 'K'
0x18001a6a0  jmp     loc_18001A7DA
0x18001a6a5  mov     r9d, 20h ; ' '
0x18001a6ab  lea     r8, [rsp+0C8h+Buf2]
0x18001a6b0  mov     rdx, r14
0x18001a6b3  mov     rcx, r13
0x18001a6b6  call    FSMCreateVirtualCameraHash
0x18001a6bb  mov     edi, eax
0x18001a6bd  test    eax, eax
0x18001a6bf  jns     short loc_18001A6D8
0x18001a6c1  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001a6c6  cmp     al, 1
0x18001a6c8  jb      loc_18001A7F8
0x18001a6ce  mov     edx, 4Ch ; 'L'
0x18001a6d3  jmp     loc_18001A7DA
0x18001a6d8  mov     r14d, r15d
0x18001a6db  lea     r15, [rbp+0E0h]
0x18001a6e2  mov     [rsp+0C8h+var_88], r15
0x18001a6e7  cmp     r14d, [rsp+0C8h+var_90]
0x18001a6ec  jnb     short loc_18001A74B
0x18001a6ee  lea     rax, [rbp+0E0h]
0x18001a6f5  mov     ecx, r14d
0x18001a6f8  mov     [rsp+0C8h+var_88], rax
0x18001a6fd  mov     rax, [rax]
0x18001a700  mov     [rsp+0C8h+var_78], rcx
0x18001a705  mov     rcx, [rax+rcx*8]
0x18001a709  mov     rax, [rcx]
0x18001a70c  mov     rax, [rax+20h]
0x18001a710  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a715  mov     r8d, 20h ; ' '; Size
0x18001a71b  lea     rdx, [rsp+0C8h+Buf2]; Buf2
0x18001a720  lea     rcx, [rax+18h]; Buf1
0x18001a724  call    memcmp_0
0x18001a729  test    eax, eax
0x18001a72b  jz      short loc_18001A732
0x18001a72d  inc     r14d
0x18001a730  jmp     short loc_18001A6E7
0x18001a732  lfence
0x18001a735  mov     rax, [rsp+0C8h+var_88]
0x18001a73a  mov     rcx, [rsp+0C8h+var_78]
0x18001a73f  mov     rax, [rax]
0x18001a742  mov     rcx, [rax+rcx*8]
0x18001a746  jmp     loc_18001A828
0x18001a74b  mov     rcx, [rsp+0C8h+var_98]
0x18001a750  mov     [rsp+0C8h+var_98], 0
0x18001a759  test    rcx, rcx
0x18001a75c  jz      short loc_18001A76C
0x18001a75e  mov     rax, [rcx]
0x18001a761  mov     rax, [rax+10h]
0x18001a765  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a76a  jmp     short loc_18001A771
0x18001a76c  mov     r15, [rsp+0C8h+var_88]
0x18001a771  mov     r9, [rsp+0C8h+var_80]; unsigned __int16 *
0x18001a776  mov     rax, rsi
0x18001a779  mov     r8, [rsp+0C8h+var_70]; unsigned __int16 *
0x18001a77e  neg     rax
0x18001a781  lea     rax, [rsp+0C8h+var_98]
0x18001a786  mov     rcx, r13; struct FSMVCamCreationInfo *
0x18001a789  sbb     rdx, rdx
0x18001a78c  mov     [rsp+0C8h+var_A0], rax; void **
0x18001a791  and     rdx, rbp; struct IFSMSession *
0x18001a794  call    ?CreateFSMVirtualCamera@FSMVirtualCamera@@SAJAEBUFSMVCamCreationInfo@@PEAUIFSMSession@@PEBG2AEBU_GUID@@PEAPEAX@Z; FSMVirtualCamera::CreateFSMVirtualCamera(FSMVCamCreationInfo const &,IFSMSession *,ushort const *,ushort const *,_GUID const &,void * *)
0x18001a799  mov     edi, eax
0x18001a79b  test    eax, eax
0x18001a79d  jns     short loc_18001A7AF
0x18001a79f  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001a7a4  cmp     al, 1
0x18001a7a6  jb      short loc_18001A7F8
0x18001a7a8  mov     edx, 4Dh ; 'M'
0x18001a7ad  jmp     short loc_18001A7DA
0x18001a7af  mov     ebp, [r15+8]
0x18001a7b3  mov     rcx, r15
0x18001a7b6  mov     r14, [rsp+0C8h+var_98]
0x18001a7bb  lea     edx, [rbp+1]
0x18001a7be  call    ?SetSize@?$CTEntryArray@PEAUIFSConfigurationEntry@@@@QEAAHKK@Z; CTEntryArray<IFSConfigurationEntry *>::SetSize(ulong,ulong)
0x18001a7c3  test    eax, eax
0x18001a7c5  jnz     short loc_18001A808
0x18001a7c7  mov     edi, 8007000Eh
0x18001a7cc  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001a7d1  cmp     al, 1
0x18001a7d3  jb      short loc_18001A7F8
0x18001a7d5  mov     edx, 4Eh ; 'N'
0x18001a7da  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a7e1  lea     r8, WPP_dda53059c67a34537508687cb55acb7f_Traceguids
0x18001a7e8  mov     r9, rsi
0x18001a7eb  mov     dword ptr [rsp+0C8h+var_A8], edi
0x18001a7ef  mov     rcx, [rcx+10h]
0x18001a7f3  call    WPP_SF_qD
0x18001a7f8  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x18001a7fd  cmp     al, 1
0x18001a7ff  jb      short loc_18001A867
0x18001a801  mov     edx, 4Fh ; 'O'
0x18001a806  jmp     short loc_18001A846
0x18001a808  mov     rax, [r15]
0x18001a80b  mov     [rax+rbp*8], r14
0x18001a80f  test    r14, r14
0x18001a812  jz      short loc_18001A823
0x18001a814  mov     rax, [r14]
0x18001a817  mov     rcx, r14
0x18001a81a  mov     rax, [rax+8]
0x18001a81e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a823  mov     rcx, [rsp+0C8h+var_98]
0x18001a828  mov     rax, [rcx]
0x18001a82b  mov     rax, [rax+18h]
0x18001a82f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a834  mov     [r12], rax
0x18001a838  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x18001a83d  cmp     al, 8
0x18001a83f  jb      short loc_18001A867
0x18001a841  mov     edx, 50h ; 'P'
0x18001a846  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a84d  lea     r8, WPP_dda53059c67a34537508687cb55acb7f_Traceguids
0x18001a854  mov     r9, rsi
0x18001a857  mov     dword ptr [rsp+0C8h+var_A8], edi
0x18001a85b  mov     rcx, [rcx+0D8h]
0x18001a862  call    WPP_SF_qD
0x18001a867  lea     rcx, [rsp+0C8h+var_98]
0x18001a86c  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x18001a871  mov     rcx, rbx; lpCriticalSection
0x18001a874  call    cs:__imp_LeaveCriticalSection
0x18001a87a  mov     eax, edi
0x18001a87c  mov     rcx, [rsp+0C8h+var_48]
0x18001a884  xor     rcx, rsp; StackCookie
0x18001a887  call    __security_check_cookie
0x18001a88c  mov     rbx, [rsp+0C8h+arg_10]
0x18001a894  add     rsp, 90h
0x18001a89b  pop     r15
0x18001a89d  pop     r14
0x18001a89f  pop     r13
0x18001a8a1  pop     r12
0x18001a8a3  pop     rdi
0x18001a8a4  pop     rsi
0x18001a8a5  pop     rbp
0x18001a8a6  retn
```
