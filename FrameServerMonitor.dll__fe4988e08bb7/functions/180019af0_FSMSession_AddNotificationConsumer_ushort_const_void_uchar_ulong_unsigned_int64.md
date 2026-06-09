# FSMSession::AddNotificationConsumer(ushort const *,void *,uchar *,ulong,unsigned __int64 *)

- ea: `0x180019af0`
- end: `0x180019e6a`
- name: `?AddNotificationConsumer@FSMSession@@UEAAJPEBGPEAXPEAEKPEA_K@Z`
- size: `890`
- prototype: `__int64 __fastcall(FSMSession *this, const unsigned __int16 *, void *, unsigned __int8 *, unsigned int, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800060e8`
- `0x1800060f8`
- `0x180006a98`
- `0x180006fc0`
- `0x180019a8c`
- `0x180019af0`
- `0x18001c4c4`
- `0x18001c63c`
- `0x18002ac50`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019bd1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019bd1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019c93`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019da6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019c93`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019da6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180019c15`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180019c15`

## pseudocode

```c
__int64 __fastcall FSMSession::AddNotificationConsumer(
        FSMSession *this,
        const unsigned __int16 *a2,
        void *a3,
        unsigned __int8 *a4,
        unsigned int a5,
        unsigned __int64 *a6)
{
  char *v9; // rbp
  char v10; // r9
  int v11; // esi
  int v12; // ecx
  __int64 v13; // rdx
  char *v14; // r9
  unsigned __int64 *v15; // r15
  unsigned int v16; // eax
  _QWORD *v17; // r12
  __int64 i; // rsi
  __int64 v19; // r13
  __int64 v20; // rcx
  __int64 v21; // rdx
  struct FSMNotification *v22; // rdi
  int v23; // r8d
  struct FSMNotification *v25; // [rsp+88h] [rbp+10h] BYREF
  void *v26; // [rsp+90h] [rbp+18h]
  unsigned __int8 *v27; // [rsp+98h] [rbp+20h]

  v27 = a4;
  v26 = a3;
  if ( !a2 || !*a2 )
  {
    v11 = -2147024809;
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_37;
    v14 = (char *)this - 40;
    v13 = 37;
LABEL_36:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, &WPP_dda53059c67a34537508687cb55acb7f_Traceguids, v14, v12);
LABEL_37:
    if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        45,
        &WPP_dda53059c67a34537508687cb55acb7f_Traceguids,
        (char *)this - 40,
        v11);
    return (unsigned int)v11;
  }
  v9 = (char *)this - 40;
  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
    WPP_SF_qSqD(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      38,
      (unsigned int)&WPP_dda53059c67a34537508687cb55acb7f_Traceguids,
      (_DWORD)v9,
      (__int64)a2,
      v10,
      a5);
  if ( !a3 )
  {
    v11 = -2147024809;
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_37;
    v13 = 39;
    v14 = v9;
    goto LABEL_36;
  }
  v15 = a6;
  if ( !a6 )
  {
    v11 = -2147467261;
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        40,
        &WPP_dda53059c67a34537508687cb55acb7f_Traceguids,
        v9,
        -2147467261);
    goto LABEL_37;
  }
  *a6 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v16 = *((_DWORD *)this + 16);
  v17 = (_QWORD *)((char *)this + 56);
  LODWORD(v25) = v16;
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= v16 )
    {
      v25 = 0;
      v11 = FSMNotification::CreateFSMNotification(a2, &v25);
      if ( v11 >= 0 )
      {
        v22 = v25;
        v11 = (*(__int64 (__fastcall **)(char *, void *, unsigned __int8 *, _QWORD))(*((_QWORD *)v25 + 5) + 32LL))(
                (char *)v25 + 40,
                v26,
                v27,
                a5);
        if ( v11 < 0 )
        {
          if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            goto LABEL_24;
          v21 = 43;
          goto LABEL_23;
        }
        if ( (unsigned int)CTUnkArray<FSMNotification>::Add(v17, v22) )
        {
          _InterlockedIncrement((volatile signed __int32 *)v22 + 8);
          *v15 = *((_QWORD *)v22 + 3);
          wil::com_ptr_t<FSMNotification,wil::err_returncode_policy>::~com_ptr_t<FSMNotification,wil::err_returncode_policy>((__int64 *)&v25);
          goto LABEL_32;
        }
        v11 = -2147024882;
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v21 = 44;
          goto LABEL_23;
        }
      }
      else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v21 = 42;
LABEL_23:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v21, &WPP_dda53059c67a34537508687cb55acb7f_Traceguids, v9, v11);
      }
LABEL_24:
      wil::com_ptr_t<FSMNotification,wil::err_returncode_policy>::~com_ptr_t<FSMNotification,wil::err_returncode_policy>((__int64 *)&v25);
LABEL_18:
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
      goto LABEL_37;
    }
    v19 = (unsigned int)i;
    v17 = (_QWORD *)((char *)this + 56);
    if ( CompareStringOrdinal(a2, -1, *(LPCWCH *)(*(_QWORD *)(*((_QWORD *)this + 7) + 8 * i) + 8LL), -1, 1) == 2 )
      break;
    v16 = (unsigned int)v25;
  }
  _mm_lfence();
  v20 = *(_QWORD *)(*v17 + 8 * i) + 40LL;
  v11 = (*(__int64 (__fastcall **)(__int64, void *, unsigned __int8 *, _QWORD))(*(_QWORD *)v20 + 32LL))(
          v20,
          v26,
          v27,
          a5);
  if ( v11 < 0 )
  {
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_dda53059c67a34537508687cb55acb7f_Traceguids, v9, v11);
    goto LABEL_18;
  }
  _mm_lfence();
  _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(*v17 + 8 * v19) + 32LL));
  *v15 = *(_QWORD *)(*(_QWORD *)(*v17 + 8 * v19) + 24LL);
LABEL_32:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
    WPP_SF_qDIS(*((_QWORD *)WPP_GLOBAL_Control + 27), 46, v23, (_DWORD)this - 40, v11, *v15, *((_QWORD *)this - 4));
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180019af0  mov     [rsp+arg_0], rbx
0x180019af5  mov     [rsp+arg_18], r9
0x180019afa  mov     [rsp+arg_10], r8
0x180019aff  push    rbp
0x180019b00  push    rsi
0x180019b01  push    rdi
0x180019b02  push    r12
0x180019b04  push    r13
0x180019b06  push    r14
0x180019b08  push    r15
0x180019b0a  sub     rsp, 40h
0x180019b0e  mov     r13, r8
0x180019b11  mov     rdi, rdx
0x180019b14  mov     r14, rcx
0x180019b17  test    rdx, rdx
0x180019b1a  jz      loc_180019DEC
0x180019b20  xor     eax, eax
0x180019b22  cmp     ax, [rdx]
0x180019b25  jz      loc_180019DEC
0x180019b2b  lea     rbp, [rcx-28h]
0x180019b2f  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180019b34  cmp     al, 8
0x180019b36  jb      short loc_180019B6F
0x180019b38  mov     rcx, cs:WPP_GLOBAL_Control
0x180019b3f  lea     r8, WPP_dda53059c67a34537508687cb55acb7f_Traceguids
0x180019b46  mov     eax, [rsp+78h+arg_20]
0x180019b4d  mov     edx, 26h ; '&'
0x180019b52  mov     dword ptr [rsp+78h+var_48], eax
0x180019b56  mov     [rsp+78h+var_50], r9
0x180019b5b  mov     r9, rbp
0x180019b5e  mov     rcx, [rcx+0D8h]
0x180019b65  mov     qword ptr [rsp+78h+bIgnoreCase], rdi
0x180019b6a  call    WPP_SF_qSqD
0x180019b6f  test    r13, r13
0x180019b72  jnz     short loc_180019B94
0x180019b74  mov     ecx, 80070057h
0x180019b79  mov     esi, ecx
0x180019b7b  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180019b80  cmp     al, 1
0x180019b82  jb      loc_180019E20
0x180019b88  lea     edx, [r13+27h]
0x180019b8c  mov     r9, rbp
0x180019b8f  jmp     loc_180019E05
0x180019b94  mov     r15, [rsp+78h+arg_28]
0x180019b9c  test    r15, r15
0x180019b9f  jnz     short loc_180019BC3
0x180019ba1  mov     esi, 80004003h
0x180019ba6  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180019bab  cmp     al, 1
0x180019bad  jb      loc_180019E20
0x180019bb3  lea     edx, [r15+28h]
0x180019bb7  mov     [rsp+78h+bIgnoreCase], esi
0x180019bbb  mov     r9, rbp
0x180019bbe  jmp     loc_180019E09
0x180019bc3  lea     rbx, [r14+10h]
0x180019bc7  mov     qword ptr [r15], 0
0x180019bce  mov     rcx, rbx; lpCriticalSection
0x180019bd1  call    cs:__imp_EnterCriticalSection
0x180019bd7  mov     eax, [r14+40h]
0x180019bdb  lea     r12, [r14+38h]
0x180019bdf  mov     dword ptr [rsp+78h+arg_8], eax
0x180019be6  xor     esi, esi
0x180019be8  mov     rcx, rdi; unsigned __int16 *
0x180019beb  cmp     esi, eax
0x180019bed  jnb     loc_180019CC1
0x180019bf3  or      r9d, 0FFFFFFFFh; cchCount2
0x180019bf7  mov     r13d, esi
0x180019bfa  lea     r12, [r14+38h]
0x180019bfe  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x180019c06  mov     rax, [r12]
0x180019c0a  or      edx, r9d; cchCount1
0x180019c0d  mov     r8, [rax+rsi*8]
0x180019c11  mov     r8, [r8+8]; lpString2
0x180019c15  call    cs:__imp_CompareStringOrdinal
0x180019c1b  cmp     eax, 2
0x180019c1e  jz      short loc_180019C2B
0x180019c20  mov     eax, dword ptr [rsp+78h+arg_8]
0x180019c27  inc     esi
0x180019c29  jmp     short loc_180019BE8
0x180019c2b  lfence
0x180019c2e  mov     rax, [r12]
0x180019c32  mov     r9d, [rsp+78h+arg_20]
0x180019c3a  mov     r8, [rsp+78h+arg_18]
0x180019c42  mov     rdx, [rsp+78h+arg_10]
0x180019c4a  mov     rcx, [rax+rsi*8]
0x180019c4e  add     rcx, 28h ; '('
0x180019c52  mov     rax, [rcx]
0x180019c55  mov     rax, [rax+20h]
0x180019c59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019c5e  mov     esi, eax
0x180019c60  test    eax, eax
0x180019c62  jns     short loc_180019C9E
0x180019c64  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180019c69  cmp     al, 1
0x180019c6b  jb      short loc_180019C90
0x180019c6d  mov     rcx, cs:WPP_GLOBAL_Control
0x180019c74  lea     r8, WPP_dda53059c67a34537508687cb55acb7f_Traceguids
0x180019c7b  mov     edx, 29h ; ')'
0x180019c80  mov     [rsp+78h+bIgnoreCase], esi
0x180019c84  mov     r9, rbp
0x180019c87  mov     rcx, [rcx+10h]
0x180019c8b  call    WPP_SF_qD
0x180019c90  mov     rcx, rbx; lpCriticalSection
0x180019c93  call    cs:__imp_LeaveCriticalSection
0x180019c99  jmp     loc_180019E20
0x180019c9e  lfence
0x180019ca1  mov     rax, [r12]
0x180019ca5  mov     rcx, [rax+r13*8]
0x180019ca9  lock inc dword ptr [rcx+20h]
0x180019cad  mov     rax, [r12]
0x180019cb1  mov     rcx, [rax+r13*8]
0x180019cb5  mov     rax, [rcx+18h]
0x180019cb9  mov     [r15], rax
0x180019cbc  jmp     loc_180019DA3
0x180019cc1  lea     rdx, [rsp+78h+arg_8]; struct FSMNotification **
0x180019cc9  mov     [rsp+78h+arg_8], 0
0x180019cd5  call    ?CreateFSMNotification@FSMNotification@@SAJPEBGPEAPEAV1@@Z; FSMNotification::CreateFSMNotification(ushort const *,FSMNotification * *)
0x180019cda  mov     esi, eax
0x180019cdc  test    eax, eax
0x180019cde  jns     short loc_180019D1E
0x180019ce0  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180019ce5  cmp     al, 1
0x180019ce7  jb      short loc_180019D0C
0x180019ce9  mov     edx, 2Ah ; '*'
0x180019cee  mov     rcx, cs:WPP_GLOBAL_Control
0x180019cf5  lea     r8, WPP_dda53059c67a34537508687cb55acb7f_Traceguids
0x180019cfc  mov     r9, rbp
0x180019cff  mov     [rsp+78h+bIgnoreCase], esi
0x180019d03  mov     rcx, [rcx+10h]
0x180019d07  call    WPP_SF_qD
0x180019d0c  lea     rcx, [rsp+78h+arg_8]
0x180019d14  call    ??1?$com_ptr_t@VFSMNotification@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<FSMNotification,wil::err_returncode_policy>::~com_ptr_t<FSMNotification,wil::err_returncode_policy>(void)
0x180019d19  jmp     loc_180019C90
0x180019d1e  mov     rdi, [rsp+78h+arg_8]
0x180019d26  mov     r9d, [rsp+78h+arg_20]
0x180019d2e  mov     r8, [rsp+78h+arg_18]
0x180019d36  mov     rdx, [rsp+78h+arg_10]
0x180019d3e  lea     rcx, [rdi+28h]
0x180019d42  mov     rax, [rcx]
0x180019d45  mov     rax, [rax+20h]
0x180019d49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019d4e  mov     esi, eax
0x180019d50  test    eax, eax
0x180019d52  jns     short loc_180019D64
0x180019d54  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180019d59  cmp     al, 1
0x180019d5b  jb      short loc_180019D0C
0x180019d5d  mov     edx, 2Bh ; '+'
0x180019d62  jmp     short loc_180019CEE
0x180019d64  mov     rdx, rdi
0x180019d67  mov     rcx, r12
0x180019d6a  call    ?Add@?$CTUnkArray@VFSMNotification@@@@QEAAHPEAVFSMNotification@@@Z; CTUnkArray<FSMNotification>::Add(FSMNotification *)
0x180019d6f  test    eax, eax
0x180019d71  jnz     short loc_180019D8B
0x180019d73  mov     esi, 8007000Eh
0x180019d78  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180019d7d  cmp     al, 1
0x180019d7f  jb      short loc_180019D0C
0x180019d81  mov     edx, 2Ch ; ','
0x180019d86  jmp     loc_180019CEE
0x180019d8b  lock inc dword ptr [rdi+20h]
0x180019d8f  mov     rax, [rdi+18h]
0x180019d93  lea     rcx, [rsp+78h+arg_8]
0x180019d9b  mov     [r15], rax
0x180019d9e  call    ??1?$com_ptr_t@VFSMNotification@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<FSMNotification,wil::err_returncode_policy>::~com_ptr_t<FSMNotification,wil::err_returncode_policy>(void)
0x180019da3  mov     rcx, rbx; lpCriticalSection
0x180019da6  call    cs:__imp_LeaveCriticalSection
0x180019dac  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180019db1  cmp     al, 8
0x180019db3  jb      loc_180019E50
0x180019db9  mov     rcx, cs:WPP_GLOBAL_Control
0x180019dc0  lea     r9, [r14-28h]
0x180019dc4  mov     rax, [r9+8]
0x180019dc8  mov     edx, 2Eh ; '.'
0x180019dcd  mov     [rsp+78h+var_48], rax
0x180019dd2  mov     rax, [r15]
0x180019dd5  mov     rcx, [rcx+0D8h]
0x180019ddc  mov     [rsp+78h+var_50], rax
0x180019de1  mov     [rsp+78h+bIgnoreCase], esi
0x180019de5  call    WPP_SF_qDIS
0x180019dea  jmp     short loc_180019E50
0x180019dec  mov     ecx, 80070057h
0x180019df1  mov     esi, ecx
0x180019df3  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180019df8  cmp     al, 1
0x180019dfa  jb      short loc_180019E20
0x180019dfc  lea     r9, [r14-28h]
0x180019e00  mov     edx, 25h ; '%'
0x180019e05  mov     [rsp+78h+bIgnoreCase], ecx
0x180019e09  mov     rcx, cs:WPP_GLOBAL_Control
0x180019e10  lea     r8, WPP_dda53059c67a34537508687cb55acb7f_Traceguids
0x180019e17  mov     rcx, [rcx+10h]
0x180019e1b  call    WPP_SF_qD
0x180019e20  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180019e25  cmp     al, 1
0x180019e27  jb      short loc_180019E50
0x180019e29  mov     rcx, cs:WPP_GLOBAL_Control
0x180019e30  lea     r9, [r14-28h]
0x180019e34  mov     edx, 2Dh ; '-'
0x180019e39  mov     [rsp+78h+bIgnoreCase], esi
0x180019e3d  lea     r8, WPP_dda53059c67a34537508687cb55acb7f_Traceguids
0x180019e44  mov     rcx, [rcx+0D8h]
0x180019e4b  call    WPP_SF_qD
0x180019e50  mov     rbx, [rsp+78h+arg_0]
0x180019e58  mov     eax, esi
0x180019e5a  add     rsp, 40h
0x180019e5e  pop     r15
0x180019e60  pop     r14
0x180019e62  pop     r13
0x180019e64  pop     r12
0x180019e66  pop     rdi
0x180019e67  pop     rsi
0x180019e68  pop     rbp
0x180019e69  retn
```
