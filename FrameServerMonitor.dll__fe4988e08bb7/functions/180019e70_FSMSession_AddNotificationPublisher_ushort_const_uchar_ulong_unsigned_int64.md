# FSMSession::AddNotificationPublisher(ushort const *,uchar *,ulong,unsigned __int64 *)

- ea: `0x180019e70`
- end: `0x18001a1a6`
- name: `?AddNotificationPublisher@FSMSession@@UEAAJPEBGPEAEKPEA_K@Z`
- size: `822`
- prototype: `__int64 __fastcall(FSMSession *this, const unsigned __int16 *, unsigned __int8 *, unsigned int, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800060e8`
- `0x1800060f8`
- `0x180006a98`
- `0x180006fc0`
- `0x180019a8c`
- `0x180019e70`
- `0x18001c4c4`
- `0x18001c63c`
- `0x18002ac50`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019f1f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019f1f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019fd9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a0e4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019fd9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a0e4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180019f63`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180019f63`

## pseudocode

```c
__int64 __fastcall FSMSession::AddNotificationPublisher(
        FSMSession *this,
        const unsigned __int16 *a2,
        unsigned __int8 *a3,
        unsigned int a4,
        unsigned __int64 *a5)
{
  char *v7; // rbp
  char v8; // r8
  char v9; // r9
  unsigned __int64 *v10; // r15
  int v11; // esi
  __int64 v12; // rdx
  char *v13; // r9
  unsigned int v14; // eax
  _QWORD *v15; // r12
  __int64 i; // rsi
  __int64 v17; // r13
  __int64 v18; // rcx
  __int64 v19; // rdx
  struct FSMNotification *v20; // rdi
  int v21; // r8d
  __int64 v22; // rcx
  struct FSMNotification *v24; // [rsp+88h] [rbp+10h] BYREF
  unsigned __int8 *v25; // [rsp+90h] [rbp+18h]
  unsigned int v26; // [rsp+98h] [rbp+20h]

  v26 = a4;
  v25 = a3;
  if ( !a2 || !*a2 )
  {
    v11 = -2147024809;
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_34;
    v13 = (char *)(v22 - 40);
    v12 = 28;
LABEL_33:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, &WPP_dda53059c67a34537508687cb55acb7f_Traceguids, v13, v11);
LABEL_34:
    if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        35,
        &WPP_dda53059c67a34537508687cb55acb7f_Traceguids,
        (char *)this - 40,
        v11);
    return (unsigned int)v11;
  }
  v7 = (char *)this - 40;
  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
    WPP_SF_qSqD(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      29,
      (unsigned int)&WPP_dda53059c67a34537508687cb55acb7f_Traceguids,
      (_DWORD)v7,
      (__int64)a2,
      v8,
      v9);
  v10 = a5;
  if ( !a5 )
  {
    v11 = -2147467261;
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_34;
    v12 = 30;
    v13 = v7;
    goto LABEL_33;
  }
  *a5 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v14 = *((_DWORD *)this + 16);
  v15 = (_QWORD *)((char *)this + 56);
  LODWORD(v24) = v14;
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= v14 )
    {
      v24 = 0;
      v11 = FSMNotification::CreateFSMNotification(a2, &v24);
      if ( v11 >= 0 )
      {
        v20 = v24;
        v11 = (*(__int64 (__fastcall **)(char *, unsigned __int8 *, _QWORD))(*((_QWORD *)v24 + 5) + 24LL))(
                (char *)v24 + 40,
                v25,
                v26);
        if ( v11 < 0 )
        {
          if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            goto LABEL_21;
          v19 = 33;
          goto LABEL_20;
        }
        if ( (unsigned int)CTUnkArray<FSMNotification>::Add(v15, v20) )
        {
          _InterlockedIncrement((volatile signed __int32 *)v20 + 8);
          *v10 = *((_QWORD *)v20 + 3);
          wil::com_ptr_t<FSMNotification,wil::err_returncode_policy>::~com_ptr_t<FSMNotification,wil::err_returncode_policy>((__int64 *)&v24);
          goto LABEL_29;
        }
        v11 = -2147024882;
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v19 = 34;
          goto LABEL_20;
        }
      }
      else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v19 = 32;
LABEL_20:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v19, &WPP_dda53059c67a34537508687cb55acb7f_Traceguids, v7, v11);
      }
LABEL_21:
      wil::com_ptr_t<FSMNotification,wil::err_returncode_policy>::~com_ptr_t<FSMNotification,wil::err_returncode_policy>((__int64 *)&v24);
LABEL_15:
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
      goto LABEL_34;
    }
    v17 = (unsigned int)i;
    v15 = (_QWORD *)((char *)this + 56);
    if ( CompareStringOrdinal(a2, -1, *(LPCWCH *)(*(_QWORD *)(*((_QWORD *)this + 7) + 8 * i) + 8LL), -1, 1) == 2 )
      break;
    v14 = (unsigned int)v24;
  }
  _mm_lfence();
  v18 = *(_QWORD *)(*v15 + 8 * i) + 40LL;
  v11 = (*(__int64 (__fastcall **)(__int64, unsigned __int8 *, _QWORD))(*(_QWORD *)v18 + 24LL))(v18, v25, v26);
  if ( v11 < 0 )
  {
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_dda53059c67a34537508687cb55acb7f_Traceguids, v7, v11);
    goto LABEL_15;
  }
  _mm_lfence();
  _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(*v15 + 8 * v17) + 32LL));
  *v10 = *(_QWORD *)(*(_QWORD *)(*v15 + 8 * v17) + 24LL);
LABEL_29:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
    WPP_SF_qDIS(*((_QWORD *)WPP_GLOBAL_Control + 27), 36, v21, (_DWORD)this - 40, v11, *v10, *((_QWORD *)this - 4));
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180019e70  mov     [rsp+arg_0], rbx
0x180019e75  mov     [rsp+arg_18], r9d
0x180019e7a  mov     [rsp+arg_10], r8
0x180019e7f  push    rbp
0x180019e80  push    rsi
0x180019e81  push    rdi
0x180019e82  push    r12
0x180019e84  push    r13
0x180019e86  push    r14
0x180019e88  push    r15
0x180019e8a  sub     rsp, 40h
0x180019e8e  mov     rdi, rdx
0x180019e91  mov     r14, rcx
0x180019e94  test    rdx, rdx
0x180019e97  jz      loc_18001A12A
0x180019e9d  xor     eax, eax
0x180019e9f  cmp     ax, [rdx]
0x180019ea2  jz      loc_18001A12A
0x180019ea8  lea     rbp, [rcx-28h]
0x180019eac  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180019eb1  cmp     al, 8
0x180019eb3  jb      short loc_180019EE6
0x180019eb5  mov     rcx, cs:WPP_GLOBAL_Control
0x180019ebc  mov     edx, 1Dh
0x180019ec1  mov     dword ptr [rsp+78h+var_48], r9d
0x180019ec6  mov     r9, rbp
0x180019ec9  mov     [rsp+78h+var_50], r8
0x180019ece  lea     r8, WPP_dda53059c67a34537508687cb55acb7f_Traceguids
0x180019ed5  mov     qword ptr [rsp+78h+bIgnoreCase], rdi
0x180019eda  mov     rcx, [rcx+0D8h]
0x180019ee1  call    WPP_SF_qSqD
0x180019ee6  mov     r15, [rsp+78h+arg_20]
0x180019eee  test    r15, r15
0x180019ef1  jnz     short loc_180019F11
0x180019ef3  mov     esi, 80004003h
0x180019ef8  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180019efd  cmp     al, 1
0x180019eff  jb      loc_18001A15C
0x180019f05  lea     edx, [r15+1Eh]
0x180019f09  mov     r9, rbp
0x180019f0c  jmp     loc_18001A141
0x180019f11  lea     rbx, [r14+10h]
0x180019f15  mov     qword ptr [r15], 0
0x180019f1c  mov     rcx, rbx; lpCriticalSection
0x180019f1f  call    cs:__imp_EnterCriticalSection
0x180019f25  mov     eax, [r14+40h]
0x180019f29  lea     r12, [r14+38h]
0x180019f2d  mov     dword ptr [rsp+78h+arg_8], eax
0x180019f34  xor     esi, esi
0x180019f36  mov     rcx, rdi; unsigned __int16 *
0x180019f39  cmp     esi, eax
0x180019f3b  jnb     loc_18001A007
0x180019f41  or      r9d, 0FFFFFFFFh; cchCount2
0x180019f45  mov     r13d, esi
0x180019f48  lea     r12, [r14+38h]
0x180019f4c  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x180019f54  mov     rax, [r12]
0x180019f58  or      edx, r9d; cchCount1
0x180019f5b  mov     r8, [rax+rsi*8]
0x180019f5f  mov     r8, [r8+8]; lpString2
0x180019f63  call    cs:__imp_CompareStringOrdinal
0x180019f69  cmp     eax, 2
0x180019f6c  jz      short loc_180019F79
0x180019f6e  mov     eax, dword ptr [rsp+78h+arg_8]
0x180019f75  inc     esi
0x180019f77  jmp     short loc_180019F36
0x180019f79  lfence
0x180019f7c  mov     rax, [r12]
0x180019f80  mov     r8d, [rsp+78h+arg_18]
0x180019f88  mov     rdx, [rsp+78h+arg_10]
0x180019f90  mov     rcx, [rax+rsi*8]
0x180019f94  add     rcx, 28h ; '('
0x180019f98  mov     rax, [rcx]
0x180019f9b  mov     rax, [rax+18h]
0x180019f9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019fa4  mov     esi, eax
0x180019fa6  test    eax, eax
0x180019fa8  jns     short loc_180019FE4
0x180019faa  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180019faf  cmp     al, 1
0x180019fb1  jb      short loc_180019FD6
0x180019fb3  mov     rcx, cs:WPP_GLOBAL_Control
0x180019fba  lea     r8, WPP_dda53059c67a34537508687cb55acb7f_Traceguids
0x180019fc1  mov     edx, 1Fh
0x180019fc6  mov     [rsp+78h+bIgnoreCase], esi
0x180019fca  mov     r9, rbp
0x180019fcd  mov     rcx, [rcx+10h]
0x180019fd1  call    WPP_SF_qD
0x180019fd6  mov     rcx, rbx; lpCriticalSection
0x180019fd9  call    cs:__imp_LeaveCriticalSection
0x180019fdf  jmp     loc_18001A15C
0x180019fe4  lfence
0x180019fe7  mov     rax, [r12]
0x180019feb  mov     rcx, [rax+r13*8]
0x180019fef  lock inc dword ptr [rcx+20h]
0x180019ff3  mov     rax, [r12]
0x180019ff7  mov     rcx, [rax+r13*8]
0x180019ffb  mov     rax, [rcx+18h]
0x180019fff  mov     [r15], rax
0x18001a002  jmp     loc_18001A0E1
0x18001a007  lea     rdx, [rsp+78h+arg_8]; struct FSMNotification **
0x18001a00f  mov     [rsp+78h+arg_8], 0
0x18001a01b  call    ?CreateFSMNotification@FSMNotification@@SAJPEBGPEAPEAV1@@Z; FSMNotification::CreateFSMNotification(ushort const *,FSMNotification * *)
0x18001a020  mov     esi, eax
0x18001a022  test    eax, eax
0x18001a024  jns     short loc_18001A064
0x18001a026  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001a02b  cmp     al, 1
0x18001a02d  jb      short loc_18001A052
0x18001a02f  mov     edx, 20h ; ' '
0x18001a034  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a03b  lea     r8, WPP_dda53059c67a34537508687cb55acb7f_Traceguids
0x18001a042  mov     r9, rbp
0x18001a045  mov     [rsp+78h+bIgnoreCase], esi
0x18001a049  mov     rcx, [rcx+10h]
0x18001a04d  call    WPP_SF_qD
0x18001a052  lea     rcx, [rsp+78h+arg_8]
0x18001a05a  call    ??1?$com_ptr_t@VFSMNotification@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<FSMNotification,wil::err_returncode_policy>::~com_ptr_t<FSMNotification,wil::err_returncode_policy>(void)
0x18001a05f  jmp     loc_180019FD6
0x18001a064  mov     rdi, [rsp+78h+arg_8]
0x18001a06c  mov     r8d, [rsp+78h+arg_18]
0x18001a074  mov     rdx, [rsp+78h+arg_10]
0x18001a07c  lea     rcx, [rdi+28h]
0x18001a080  mov     rax, [rcx]
0x18001a083  mov     rax, [rax+18h]
0x18001a087  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a08c  mov     esi, eax
0x18001a08e  test    eax, eax
0x18001a090  jns     short loc_18001A0A2
0x18001a092  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001a097  cmp     al, 1
0x18001a099  jb      short loc_18001A052
0x18001a09b  mov     edx, 21h ; '!'
0x18001a0a0  jmp     short loc_18001A034
0x18001a0a2  mov     rdx, rdi
0x18001a0a5  mov     rcx, r12
0x18001a0a8  call    ?Add@?$CTUnkArray@VFSMNotification@@@@QEAAHPEAVFSMNotification@@@Z; CTUnkArray<FSMNotification>::Add(FSMNotification *)
0x18001a0ad  test    eax, eax
0x18001a0af  jnz     short loc_18001A0C9
0x18001a0b1  mov     esi, 8007000Eh
0x18001a0b6  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001a0bb  cmp     al, 1
0x18001a0bd  jb      short loc_18001A052
0x18001a0bf  mov     edx, 22h ; '"'
0x18001a0c4  jmp     loc_18001A034
0x18001a0c9  lock inc dword ptr [rdi+20h]
0x18001a0cd  mov     rax, [rdi+18h]
0x18001a0d1  lea     rcx, [rsp+78h+arg_8]
0x18001a0d9  mov     [r15], rax
0x18001a0dc  call    ??1?$com_ptr_t@VFSMNotification@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<FSMNotification,wil::err_returncode_policy>::~com_ptr_t<FSMNotification,wil::err_returncode_policy>(void)
0x18001a0e1  mov     rcx, rbx; lpCriticalSection
0x18001a0e4  call    cs:__imp_LeaveCriticalSection
0x18001a0ea  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x18001a0ef  cmp     al, 8
0x18001a0f1  jb      loc_18001A18C
0x18001a0f7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a0fe  lea     r9, [r14-28h]
0x18001a102  mov     rax, [r9+8]
0x18001a106  mov     edx, 24h ; '$'
0x18001a10b  mov     [rsp+78h+var_48], rax
0x18001a110  mov     rax, [r15]
0x18001a113  mov     rcx, [rcx+0D8h]
0x18001a11a  mov     [rsp+78h+var_50], rax
0x18001a11f  mov     [rsp+78h+bIgnoreCase], esi
0x18001a123  call    WPP_SF_qDIS
0x18001a128  jmp     short loc_18001A18C
0x18001a12a  mov     esi, 80070057h
0x18001a12f  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001a134  cmp     al, 1
0x18001a136  jb      short loc_18001A15C
0x18001a138  lea     r9, [rcx-28h]
0x18001a13c  mov     edx, 1Ch
0x18001a141  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a148  lea     r8, WPP_dda53059c67a34537508687cb55acb7f_Traceguids
0x18001a14f  mov     [rsp+78h+bIgnoreCase], esi
0x18001a153  mov     rcx, [rcx+10h]
0x18001a157  call    WPP_SF_qD
0x18001a15c  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x18001a161  cmp     al, 1
0x18001a163  jb      short loc_18001A18C
0x18001a165  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a16c  lea     r9, [r14-28h]
0x18001a170  mov     edx, 23h ; '#'
0x18001a175  mov     [rsp+78h+bIgnoreCase], esi
0x18001a179  lea     r8, WPP_dda53059c67a34537508687cb55acb7f_Traceguids
0x18001a180  mov     rcx, [rcx+0D8h]
0x18001a187  call    WPP_SF_qD
0x18001a18c  mov     rbx, [rsp+78h+arg_0]
0x18001a194  mov     eax, esi
0x18001a196  add     rsp, 40h
0x18001a19a  pop     r15
0x18001a19c  pop     r14
0x18001a19e  pop     r13
0x18001a1a0  pop     r12
0x18001a1a2  pop     rdi
0x18001a1a3  pop     rsi
0x18001a1a4  pop     rbp
0x18001a1a5  retn
```
