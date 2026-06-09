# FSMonitorService::CreateVirtualCamera(IFSMSession *,FSMVCamCreationInfo &,unsigned __int64 *)

- ea: `0x180007a80`
- end: `0x180007bfa`
- name: `?CreateVirtualCamera@FSMonitorService@@UEAAJPEAUIFSMSession@@AEAUFSMVCamCreationInfo@@PEA_K@Z`
- size: `378`
- prototype: `__int64 __fastcall(FSMonitorService *__hidden this, struct IFSMSession *, struct FSMVCamCreationInfo *, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task`

## callees

- `0x1800060e8`
- `0x1800060f8`
- `0x180006a98`
- `0x180007a80`
- `0x18000d088`
- `0x18000d62c`
- `0x180045a30`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007aa4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007aa4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007be4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007be4`

## pseudocode

```c
__int64 __fastcall FSMonitorService::CreateVirtualCamera(
        FSMonitorService *this,
        struct IFSMSession *a2,
        struct FSMVCamCreationInfo *a3,
        unsigned __int64 *a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // rbp
  __int64 v9; // rcx
  int v10; // ebx
  __int64 v11; // rdx
  __int64 *v12; // rbx
  __int64 v13; // rdx
  int v14; // ecx

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 272);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 272));
  if ( a2 )
  {
    v12 = (__int64 *)((char *)this + 312);
    if ( *((_QWORD *)this + 39) != *((_QWORD *)this + 40) )
      goto LABEL_13;
    v13 = *((unsigned int *)this + 86);
    if ( (_DWORD)v13 != -1
      && (int)FSMLoadResourceString(v9, v13, (char *)this + 312) < 0
      && _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() )
    {
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), 112, &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids, this, v14);
    }
    if ( *v12 == *((_QWORD *)this + 40)
      && !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                             (char *)this + 312,
                             L"Windows Test Virtual Camera",
                             27) )
    {
      v10 = -2147024882;
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v11 = 113;
        goto LABEL_18;
      }
    }
    else
    {
LABEL_13:
      if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
        WPP_SF_qS(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          114,
          (unsigned int)&WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids,
          (_DWORD)this,
          *v12);
      v10 = (*(__int64 (__fastcall **)(struct IFSMSession *, struct FSMVCamCreationInfo *, __int64, unsigned __int64 *))(*(_QWORD *)a2 + 176LL))(
              a2,
              a3,
              *v12,
              a4);
      if ( v10 < 0 && _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v11 = 115;
        goto LABEL_18;
      }
    }
  }
  else
  {
    v10 = -2147024809;
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v11 = 111;
LABEL_18:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids, this, v10);
    }
  }
  LeaveCriticalSection(v4);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180007a80  push    rbx
0x180007a82  push    rbp
0x180007a83  push    rdi
0x180007a84  push    r12
0x180007a86  push    r14
0x180007a88  push    r15
0x180007a8a  sub     rsp, 38h
0x180007a8e  lea     rbp, [rcx+110h]
0x180007a95  mov     rdi, rcx
0x180007a98  mov     rcx, rbp; lpCriticalSection
0x180007a9b  mov     r15, r9
0x180007a9e  mov     r12, r8
0x180007aa1  mov     r14, rdx
0x180007aa4  call    cs:__imp_EnterCriticalSection
0x180007aaa  test    r14, r14
0x180007aad  jnz     short loc_180007ACA
0x180007aaf  mov     ebx, 80070057h
0x180007ab4  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180007ab9  cmp     al, 1
0x180007abb  jb      loc_180007BE1
0x180007ac1  lea     edx, [r14+6Fh]
0x180007ac5  jmp     loc_180007BC3
0x180007aca  lea     rbx, [rdi+138h]
0x180007ad1  mov     rax, [rbx+8]
0x180007ad5  cmp     [rbx], rax
0x180007ad8  jnz     loc_180007B61
0x180007ade  mov     edx, [rdi+158h]
0x180007ae4  cmp     edx, 0FFFFFFFFh
0x180007ae7  jz      short loc_180007B26
0x180007ae9  mov     r8, rbx
0x180007aec  call    FSMLoadResourceString
0x180007af1  mov     ecx, eax
0x180007af3  test    eax, eax
0x180007af5  jns     short loc_180007B26
0x180007af7  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180007afc  cmp     al, 1
0x180007afe  jb      short loc_180007B26
0x180007b00  mov     dword ptr [rsp+68h+var_48], ecx
0x180007b04  lea     r8, WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids
0x180007b0b  mov     rcx, cs:WPP_GLOBAL_Control
0x180007b12  mov     edx, 70h ; 'p'
0x180007b17  mov     r9, rdi
0x180007b1a  mov     rcx, [rcx+0D8h]
0x180007b21  call    WPP_SF_qD
0x180007b26  mov     rax, [rbx+8]
0x180007b2a  cmp     [rbx], rax
0x180007b2d  jnz     short loc_180007B61
0x180007b2f  mov     r8d, 1Bh
0x180007b35  lea     rdx, aWindowsTestVir; "Windows Test Virtual Camera"
0x180007b3c  mov     rcx, rbx
0x180007b3f  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180007b44  test    al, al
0x180007b46  jnz     short loc_180007B61
0x180007b48  mov     ebx, 8007000Eh
0x180007b4d  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180007b52  cmp     al, 1
0x180007b54  jb      loc_180007BE1
0x180007b5a  mov     edx, 71h ; 'q'
0x180007b5f  jmp     short loc_180007BC3
0x180007b61  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180007b66  cmp     al, 8
0x180007b68  jb      short loc_180007B94
0x180007b6a  mov     rcx, cs:WPP_GLOBAL_Control
0x180007b71  lea     r8, WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids
0x180007b78  mov     rax, [rbx]
0x180007b7b  mov     edx, 72h ; 'r'
0x180007b80  mov     r9, rdi
0x180007b83  mov     [rsp+68h+var_48], rax
0x180007b88  mov     rcx, [rcx+0D8h]
0x180007b8f  call    WPP_SF_qS
0x180007b94  mov     rax, [r14]
0x180007b97  mov     r9, r15
0x180007b9a  mov     r8, [rbx]
0x180007b9d  mov     rdx, r12
0x180007ba0  mov     rcx, r14
0x180007ba3  mov     rax, [rax+0B0h]
0x180007baa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007baf  mov     ebx, eax
0x180007bb1  test    eax, eax
0x180007bb3  jns     short loc_180007BE1
0x180007bb5  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180007bba  cmp     al, 1
0x180007bbc  jb      short loc_180007BE1
0x180007bbe  mov     edx, 73h ; 's'
0x180007bc3  mov     rcx, cs:WPP_GLOBAL_Control
0x180007bca  lea     r8, WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids
0x180007bd1  mov     r9, rdi
0x180007bd4  mov     dword ptr [rsp+68h+var_48], ebx
0x180007bd8  mov     rcx, [rcx+10h]
0x180007bdc  call    WPP_SF_qD
0x180007be1  mov     rcx, rbp; lpCriticalSection
0x180007be4  call    cs:__imp_LeaveCriticalSection
0x180007bea  mov     eax, ebx
0x180007bec  add     rsp, 38h
0x180007bf0  pop     r15
0x180007bf2  pop     r14
0x180007bf4  pop     r12
0x180007bf6  pop     rdi
0x180007bf7  pop     rbp
0x180007bf8  pop     rbx
0x180007bf9  retn
```
