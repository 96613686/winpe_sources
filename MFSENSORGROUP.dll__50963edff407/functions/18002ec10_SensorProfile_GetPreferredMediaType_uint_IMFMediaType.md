# SensorProfile::GetPreferredMediaType(uint,IMFMediaType * *)

- ea: `0x18002ec10`
- end: `0x18002eef8`
- name: `?GetPreferredMediaType@SensorProfile@@UEAAJIPEAPEAUIMFMediaType@@@Z`
- size: `744`
- prototype: `__int64 __fastcall(SensorProfile *__hidden this, unsigned int, struct IMFMediaType **)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180005fa0`
- `0x180008f9c`
- `0x18002ec10`
- `0x180044f30`
- `0x180045900`
- `0x180076274`
- `0x180077010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ec6b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ec6b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ec47`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ec47`
- `MFPlat!MFCreateMediaType` at `0x18002ee04`
- `MFPlat!MFCreateMediaType` at `0x18002ee04`

## pseudocode

```c
__int64 __fastcall SensorProfile::GetPreferredMediaType(SensorProfile *this, int a2, struct IMFMediaType **a3)
{
  unsigned int v5; // r12d
  unsigned int v6; // edi
  __int64 i; // r14
  __int64 v9; // rcx
  __int64 v10; // rax
  HRESULT v11; // eax
  __int64 v12; // rdx
  struct IMFMediaType *v13; // rax
  IMFMediaType *ppMFType[2]; // [rsp+30h] [rbp-39h] BYREF
  _BYTE v15[16]; // [rsp+40h] [rbp-29h] BYREF
  _BYTE v16[16]; // [rsp+50h] [rbp-19h] BYREF
  _BYTE Buf1[16]; // [rsp+60h] [rbp-9h] BYREF
  unsigned int v18; // [rsp+70h] [rbp+7h]
  unsigned int v19; // [rsp+74h] [rbp+Bh]
  __int64 v20; // [rsp+78h] [rbp+Fh]

  LODWORD(ppMFType[0]) = a2;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  if ( a3 )
  {
    v5 = *((_DWORD *)this + 26);
    v6 = 0;
    *a3 = 0;
    for ( i = 0; ; i = (unsigned int)(i + 1) )
    {
      if ( (unsigned int)i >= v5 )
        goto LABEL_4;
      v9 = *(_QWORD *)(*((_QWORD *)this + 12) + 8 * i);
      if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v9 + 40LL))(v9) == LODWORD(ppMFType[0]) )
        break;
    }
    _mm_lfence();
    memset_0(v15, 0, 0x40u);
    v10 = *((_QWORD *)this + 12);
    ppMFType[0] = 0;
    v11 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(v10 + 8 * i) + 24LL))(
            *(_QWORD *)(v10 + 8 * i),
            v15);
    v6 = v11;
    if ( v11 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_15;
      v12 = 74;
      goto LABEL_14;
    }
    if ( !memcmp_0(Buf1, &GUID_00000000_0000_0000_0000_000000000000, 0x10u) )
      goto LABEL_4;
    v11 = MFCreateMediaType(ppMFType);
    v6 = v11;
    if ( v11 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_15;
      v12 = 75;
      goto LABEL_14;
    }
    v11 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, _BYTE *))ppMFType[0]->lpVtbl->SetGUID)(
            ppMFType[0],
            &MF_MT_MAJOR_TYPE,
            v16);
    v6 = v11;
    if ( v11 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_15;
      v12 = 76;
      goto LABEL_14;
    }
    v11 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, _BYTE *))ppMFType[0]->lpVtbl->SetGUID)(
            ppMFType[0],
            &MF_MT_SUBTYPE,
            Buf1);
    v6 = v11;
    if ( v11 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_15;
      v12 = 77;
      goto LABEL_14;
    }
    if ( memcmp_0(v16, &MFMediaType_Image, 0x10u) )
    {
      v11 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, __int64))ppMFType[0]->lpVtbl->SetUINT64)(
              ppMFType[0],
              &MF_MT_FRAME_RATE,
              v20);
      v6 = v11;
      if ( v11 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_15;
        v12 = 78;
        goto LABEL_14;
      }
    }
    v11 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, unsigned __int64))ppMFType[0]->lpVtbl->SetUINT64)(
            ppMFType[0],
            &MF_MT_FRAME_SIZE,
            v19 | ((unsigned __int64)v18 << 32));
    v6 = v11;
    if ( v11 < 0 )
    {
      if ( !g_wppLevels )
      {
LABEL_15:
        wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)ppMFType);
        goto LABEL_4;
      }
      v12 = 79;
LABEL_14:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, &WPP_31927b3ff17c3be32b5b8560ff5597aa_Traceguids, this, v11);
      goto LABEL_15;
    }
    v13 = ppMFType[0];
    ppMFType[0] = 0;
    *a3 = v13;
  }
  else
  {
    v6 = -2147467261;
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        73,
        &WPP_31927b3ff17c3be32b5b8560ff5597aa_Traceguids,
        this,
        -2147467261);
  }
LABEL_4:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  return v6;
}

```

## disassembly

```asm
0x18002ec10  mov     [rsp-8+arg_8], rbx
0x18002ec15  push    rbp
0x18002ec16  push    rsi
0x18002ec17  push    rdi
0x18002ec18  push    r12
0x18002ec1a  push    r13
0x18002ec1c  push    r14
0x18002ec1e  push    r15
0x18002ec20  lea     rbp, [rsp-27h]
0x18002ec25  sub     rsp, 90h
0x18002ec2c  mov     rax, cs:__security_cookie
0x18002ec33  xor     rax, rsp
0x18002ec36  mov     [rbp+57h+var_40], rax
0x18002ec3a  mov     rsi, rcx
0x18002ec3d  mov     dword ptr [rbp+57h+ppMFType], edx
0x18002ec40  add     rcx, 18h; lpCriticalSection
0x18002ec44  mov     r15, r8
0x18002ec47  call    cs:__imp_EnterCriticalSection
0x18002ec4d  test    r15, r15
0x18002ec50  jz      loc_18002EDB6
0x18002ec56  mov     r12d, [rsi+68h]
0x18002ec5a  xor     edi, edi
0x18002ec5c  mov     [r15], rdi
0x18002ec5f  xor     r14d, r14d
0x18002ec62  cmp     r14d, r12d
0x18002ec65  jb      short loc_18002EC9A
0x18002ec67  lea     rcx, [rsi+18h]; lpCriticalSection
0x18002ec6b  call    cs:__imp_LeaveCriticalSection
0x18002ec71  mov     eax, edi
0x18002ec73  mov     rcx, [rbp+57h+var_40]
0x18002ec77  xor     rcx, rsp; StackCookie
0x18002ec7a  call    __security_check_cookie
0x18002ec7f  mov     rbx, [rsp+0C0h+arg_8]
0x18002ec87  add     rsp, 90h
0x18002ec8e  pop     r15
0x18002ec90  pop     r14
0x18002ec92  pop     r13
0x18002ec94  pop     r12
0x18002ec96  pop     rdi
0x18002ec97  pop     rsi
0x18002ec98  pop     rbp
0x18002ec99  retn
0x18002ec9a  mov     rax, [rsi+60h]
0x18002ec9e  mov     rcx, [rax+r14*8]
0x18002eca2  mov     rax, [rcx]
0x18002eca5  mov     rax, [rax+28h]
0x18002eca9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ecae  cmp     eax, dword ptr [rbp+57h+ppMFType]
0x18002ecb1  jz      short loc_18002ECB8
0x18002ecb3  inc     r14d
0x18002ecb6  jmp     short loc_18002EC62
0x18002ecb8  lfence
0x18002ecbb  xor     edx, edx; Val
0x18002ecbd  lea     rcx, [rbp+57h+var_80]; void *
0x18002ecc1  lea     r8d, [rdx+40h]; Size
0x18002ecc5  call    memset_0
0x18002ecca  mov     rax, [rsi+60h]
0x18002ecce  lea     rdx, [rbp+57h+var_80]
0x18002ecd2  mov     [rbp+57h+ppMFType], rdi
0x18002ecd6  mov     rcx, [rax+r14*8]
0x18002ecda  mov     rax, [rcx]
0x18002ecdd  mov     rax, [rax+18h]
0x18002ece1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ece6  mov     edi, eax
0x18002ece8  test    eax, eax
0x18002ecea  js      loc_18002EDF0
0x18002ecf0  mov     r14d, 10h
0x18002ecf6  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; Buf2
0x18002ecfd  mov     r8d, r14d; Size
0x18002ed00  lea     rcx, [rbp+57h+Buf1]; Buf1
0x18002ed04  call    memcmp_0
0x18002ed09  test    eax, eax
0x18002ed0b  jnz     loc_18002EE00
0x18002ed11  mov     rcx, [rbp+57h+ppMFType]
0x18002ed15  test    rcx, rcx
0x18002ed18  jz      loc_18002EC67
0x18002ed1e  mov     rax, [rcx]
0x18002ed21  mov     rax, [rax+10h]
0x18002ed25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ed2a  jmp     loc_18002EC67
0x18002ed2f  mov     r8, r14; Size
0x18002ed32  lea     rdx, MFMediaType_Image; Buf2
0x18002ed39  lea     rcx, [rbp+57h+var_70]; Buf1
0x18002ed3d  call    memcmp_0
0x18002ed42  test    eax, eax
0x18002ed44  jnz     loc_18002EE9D
0x18002ed4a  mov     eax, [rbp+57h+var_4C]
0x18002ed4d  lea     rdx, MF_MT_FRAME_SIZE
0x18002ed54  mov     rcx, [rbp+57h+ppMFType]
0x18002ed58  mov     r8d, [rbp+57h+var_50]
0x18002ed5c  shl     r8, 20h
0x18002ed60  or      r8, rax
0x18002ed63  mov     r9, [rcx]
0x18002ed66  mov     rax, [r9+0B0h]
0x18002ed6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ed72  mov     edi, eax
0x18002ed74  test    eax, eax
0x18002ed76  jns     loc_18002EEE6
0x18002ed7c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002ed83  jb      short loc_18002EDA8
0x18002ed85  mov     edx, 4Fh ; 'O'
0x18002ed8a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ed91  lea     r8, WPP_31927b3ff17c3be32b5b8560ff5597aa_Traceguids
0x18002ed98  mov     r9, rsi
0x18002ed9b  mov     [rsp+0C0h+var_A0], eax
0x18002ed9f  mov     rcx, [rcx+10h]
0x18002eda3  call    WPP_SF_qD
0x18002eda8  lea     rcx, [rbp+57h+ppMFType]
0x18002edac  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x18002edb1  jmp     loc_18002EC67
0x18002edb6  mov     edi, 80004003h
0x18002edbb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002edc2  jb      loc_18002EC67
0x18002edc8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002edcf  lea     r8, WPP_31927b3ff17c3be32b5b8560ff5597aa_Traceguids
0x18002edd6  mov     edx, 49h ; 'I'
0x18002eddb  mov     [rsp+0C0h+var_A0], edi
0x18002eddf  mov     r9, rsi
0x18002ede2  mov     rcx, [rcx+10h]
0x18002ede6  call    WPP_SF_qD
0x18002edeb  jmp     loc_18002EC67
0x18002edf0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002edf7  jb      short loc_18002EDA8
0x18002edf9  mov     edx, 4Ah ; 'J'
0x18002edfe  jmp     short loc_18002ED8A
0x18002ee00  lea     rcx, [rbp+57h+ppMFType]; ppMFType
0x18002ee04  call    cs:__imp_MFCreateMediaType
0x18002ee0a  mov     edi, eax
0x18002ee0c  test    eax, eax
0x18002ee0e  jns     short loc_18002EE23
0x18002ee10  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002ee17  jb      short loc_18002EDA8
0x18002ee19  mov     edx, 4Bh ; 'K'
0x18002ee1e  jmp     loc_18002ED8A
0x18002ee23  mov     rcx, [rbp+57h+ppMFType]
0x18002ee27  lea     r8, [rbp+57h+var_70]
0x18002ee2b  lea     rdx, MF_MT_MAJOR_TYPE
0x18002ee32  mov     rax, [rcx]
0x18002ee35  mov     rax, [rax+0C0h]
0x18002ee3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ee41  mov     edi, eax
0x18002ee43  test    eax, eax
0x18002ee45  jns     short loc_18002EE5E
0x18002ee47  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002ee4e  jb      loc_18002EDA8
0x18002ee54  mov     edx, 4Ch ; 'L'
0x18002ee59  jmp     loc_18002ED8A
0x18002ee5e  mov     rcx, [rbp+57h+ppMFType]
0x18002ee62  lea     r8, [rbp+57h+Buf1]
0x18002ee66  lea     rdx, MF_MT_SUBTYPE
0x18002ee6d  mov     rax, [rcx]
0x18002ee70  mov     rax, [rax+0C0h]
0x18002ee77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ee7c  mov     edi, eax
0x18002ee7e  test    eax, eax
0x18002ee80  jns     loc_18002ED2F
0x18002ee86  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002ee8d  jb      loc_18002EDA8
0x18002ee93  mov     edx, 4Dh ; 'M'
0x18002ee98  jmp     loc_18002ED8A
0x18002ee9d  mov     eax, dword ptr [rbp+57h+var_48]
0x18002eea0  lea     rdx, MF_MT_FRAME_RATE
0x18002eea7  mov     rcx, [rbp+57h+ppMFType]
0x18002eeab  mov     r8d, dword ptr [rbp+57h+var_48+4]
0x18002eeaf  shl     r8, 20h
0x18002eeb3  or      r8, rax
0x18002eeb6  mov     r9, [rcx]
0x18002eeb9  mov     rax, [r9+0B0h]
0x18002eec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eec5  mov     edi, eax
0x18002eec7  test    eax, eax
0x18002eec9  jns     loc_18002ED4A
0x18002eecf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002eed6  jb      loc_18002EDA8
0x18002eedc  mov     edx, 4Eh ; 'N'
0x18002eee1  jmp     loc_18002ED8A
0x18002eee6  mov     rax, [rbp+57h+ppMFType]
0x18002eeea  xor     ecx, ecx
0x18002eeec  mov     [rbp+57h+ppMFType], rcx
0x18002eef0  mov     [r15], rax
0x18002eef3  jmp     loc_18002ED15
```
