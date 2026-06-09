# CVaultFileStore::DeleteVault(uchar)

- ea: `0x1800398d0`
- end: `0x180039c9f`
- name: `?DeleteVault@CVaultFileStore@@UEAAKE@Z`
- size: `975`
- prototype: `__int64 __fastcall(CVaultFileStore *this, unsigned __int8)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, reparse_path, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180003140`
- `0x18000eb30`
- `0x180011110`
- `0x180011a94`
- `0x18001b5a0`
- `0x18002e2e0`
- `0x1800311f4`
- `0x1800398d0`
- `0x180039cb0`
- `0x18003b7d8`
- `0x180040cc0`
- `0x18004d010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180039941`
- `ntdll!RtlReleaseResource` at `0x180039965`
- `ntdll!RtlReleaseResource` at `0x1800399df`
- `ntdll!RtlReleaseResource` at `0x180039a28`
- `ntdll!RtlReleaseResource` at `0x180039a75`
- `ntdll!RtlReleaseResource` at `0x180039abc`
- `ntdll!RtlReleaseResource` at `0x180039b00`
- `ntdll!RtlReleaseResource` at `0x180039b51`
- `ntdll!RtlReleaseResource` at `0x180039b9e`
- `ntdll!RtlReleaseResource` at `0x180039bee`
- `ntdll!RtlReleaseResource` at `0x180039c37`
- `ntdll!RtlReleaseResource` at `0x180039c75`
- `ntdll!RtlReleaseResource` at `0x180039941`
- `ntdll!RtlReleaseResource` at `0x180039965`
- `ntdll!RtlReleaseResource` at `0x1800399df`
- `ntdll!RtlReleaseResource` at `0x180039a28`
- `ntdll!RtlReleaseResource` at `0x180039a75`
- `ntdll!RtlReleaseResource` at `0x180039abc`
- `ntdll!RtlReleaseResource` at `0x180039b00`
- `ntdll!RtlReleaseResource` at `0x180039b51`
- `ntdll!RtlReleaseResource` at `0x180039b9e`
- `ntdll!RtlReleaseResource` at `0x180039bee`
- `ntdll!RtlReleaseResource` at `0x180039c37`
- `ntdll!RtlReleaseResource` at `0x180039c75`

## pseudocode

```c
__int64 __fastcall CVaultFileStore::DeleteVault(CVaultFileStore *this, unsigned __int8 a2)
{
  char *v4; // rbx
  __int64 v5; // rbx
  __int64 v7; // rcx
  ULONG v8; // ebx
  struct IVaultFileSystem *v9; // rbx
  unsigned int v10; // esi
  PRTL_RESOURCE v11; // [rsp+20h] [rbp-58h] BYREF
  char v12; // [rsp+28h] [rbp-50h]
  PRTL_RESOURCE Resource; // [rsp+30h] [rbp-48h] BYREF
  char v14; // [rsp+38h] [rbp-40h]
  __int64 v15; // [rsp+40h] [rbp-38h] BYREF
  unsigned __int16 *v16; // [rsp+48h] [rbp-30h] BYREF
  int v17; // [rsp+50h] [rbp-28h]
  __int64 (__fastcall *v18)(_QWORD); // [rsp+58h] [rbp-20h] BYREF
  struct IVaultFileSystem *v19; // [rsp+60h] [rbp-18h] BYREF
  int v20; // [rsp+68h] [rbp-10h]
  __int64 ThreadInformation; // [rsp+B0h] [rbp+38h] BYREF

  v18 = AutoDereference<IVaultKeyManager>;
  v19 = 0;
  v20 = 0;
  v16 = 0;
  v17 = 0;
  v15 = 0;
  v4 = (char *)this + 192;
  CVaultRtlLock::CVaultRtlLock(&v11, (char *)this + 192, 1);
  ThreadInformation = 0;
  CVaultRtlLock::CVaultRtlLock(&Resource, v4, 0);
  v5 = *((_QWORD *)this + 4);
  if ( v14 )
    RtlReleaseResource(Resource);
  if ( !v5 || a2 )
  {
    v8 = CVaultIntegrityLevel::Elevate((CVaultIntegrityLevel *)&ThreadInformation);
    if ( v8 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_c304bf9ddc9a325b3ef15398c2399f48_Traceguids, v8);
      CVaultIntegrityLevel::~CVaultIntegrityLevel(&ThreadInformation);
      if ( v12 )
        RtlReleaseResource(v11);
    }
    else
    {
      v8 = CVaultFactory::CreateVaultFileSystem(v7, *((unsigned int *)this + 76), &v19);
      if ( !v8 )
      {
        v9 = v19;
        v10 = (*(__int64 (__fastcall **)(struct IVaultFileSystem *))(*(_QWORD *)v19 + 16LL))(v19);
        if ( v10 )
        {
          CVaultIntegrityLevel::~CVaultIntegrityLevel(&ThreadInformation);
          if ( v12 )
            RtlReleaseResource(v11);
        }
        else
        {
          v10 = CVaultFileStore::DeleteAllCredentials(this, v9);
          if ( v10 )
          {
            CVaultIntegrityLevel::~CVaultIntegrityLevel(&ThreadInformation);
            if ( v12 )
              RtlReleaseResource(v11);
          }
          else
          {
            v10 = CVaultFileStore::InitializeOrDeleteSchema(this, 1u, v9);
            if ( v10 )
            {
              CVaultIntegrityLevel::~CVaultIntegrityLevel(&ThreadInformation);
              if ( v12 )
                RtlReleaseResource(v11);
            }
            else
            {
              v10 = PathCombine(*((wchar_t **)this + 39), (wchar_t *)L"Policy.vpol", &v16);
              if ( v10 )
              {
                CVaultIntegrityLevel::~CVaultIntegrityLevel(&ThreadInformation);
                if ( v12 )
                  RtlReleaseResource(v11);
              }
              else
              {
                v10 = (*(__int64 (__fastcall **)(struct IVaultFileSystem *, unsigned __int16 *))(*(_QWORD *)v9 + 56LL))(
                        v9,
                        v16);
                if ( v10 )
                {
                  CVaultIntegrityLevel::~CVaultIntegrityLevel(&ThreadInformation);
                  if ( v12 )
                    RtlReleaseResource(v11);
                }
                else
                {
                  v10 = (*(__int64 (__fastcall **)(struct IVaultFileSystem *, _QWORD))(*(_QWORD *)v9 + 64LL))(
                          v9,
                          *((_QWORD *)this + 39));
                  if ( !v10 )
                  {
                    v8 = (*(__int64 (__fastcall **)(struct IVaultFileSystem *))(*(_QWORD *)v9 + 24LL))(v9);
                    if ( v8 )
                    {
                      CVaultIntegrityLevel::~CVaultIntegrityLevel(&ThreadInformation);
                      if ( v12 )
                        RtlReleaseResource(v11);
                    }
                    else
                    {
                      v8 = CVaultMemoryStore::DeleteVault(this, a2);
                      CVaultIntegrityLevel::~CVaultIntegrityLevel(&ThreadInformation);
                      if ( v12 )
                        RtlReleaseResource(v11);
                    }
                    goto LABEL_49;
                  }
                  CVaultIntegrityLevel::~CVaultIntegrityLevel(&ThreadInformation);
                  if ( v12 )
                    RtlReleaseResource(v11);
                }
              }
            }
          }
        }
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v15);
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v18);
        return v10;
      }
      CVaultIntegrityLevel::~CVaultIntegrityLevel(&ThreadInformation);
      if ( v12 )
        RtlReleaseResource(v11);
    }
LABEL_49:
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v15);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v18);
    return v8;
  }
  CVaultIntegrityLevel::~CVaultIntegrityLevel(&ThreadInformation);
  if ( v12 )
    RtlReleaseResource(v11);
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v15);
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v18);
  return 4307;
}

```

## disassembly

```asm
0x1800398d0  push    rbp
0x1800398d2  push    rbx
0x1800398d3  push    rsi
0x1800398d4  push    rdi
0x1800398d5  push    r14
0x1800398d7  push    r15
0x1800398d9  mov     rbp, rsp
0x1800398dc  sub     rsp, 78h
0x1800398e0  mov     r14b, dl
0x1800398e3  mov     rdi, rcx
0x1800398e6  lea     rax, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x1800398ed  mov     [rbp+var_20], rax
0x1800398f1  xor     r15d, r15d
0x1800398f4  mov     [rbp+var_18], r15
0x1800398f8  mov     [rbp+var_10], r15d
0x1800398fc  mov     [rbp+var_30], r15
0x180039900  mov     [rbp+var_28], r15d
0x180039904  mov     [rbp+var_38], r15
0x180039908  lea     rbx, [rcx+0C0h]
0x18003990f  lea     r8d, [r15+1]
0x180039913  mov     rdx, rbx
0x180039916  lea     rcx, [rbp+var_58]
0x18003991a  call    ??0CVaultRtlLock@@QEAA@PEAU_RTL_RESOURCE@@W4eVaultLock@@@Z; CVaultRtlLock::CVaultRtlLock(_RTL_RESOURCE *,eVaultLock)
0x18003991f  nop
0x180039920  mov     [rbp+ThreadInformation], r15
0x180039924  xor     r8d, r8d
0x180039927  mov     rdx, rbx
0x18003992a  lea     rcx, [rbp+Resource]
0x18003992e  call    ??0CVaultRtlLock@@QEAA@PEAU_RTL_RESOURCE@@W4eVaultLock@@@Z; CVaultRtlLock::CVaultRtlLock(_RTL_RESOURCE *,eVaultLock)
0x180039933  mov     rbx, [rdi+20h]
0x180039937  cmp     [rbp+var_40], r15b
0x18003993b  jz      short loc_180039947
0x18003993d  mov     rcx, [rbp+Resource]; Resource
0x180039941  call    cs:__imp_RtlReleaseResource
0x180039947  test    rbx, rbx
0x18003994a  jz      short loc_18003998A
0x18003994c  test    r14b, r14b
0x18003994f  jnz     short loc_18003998A
0x180039951  lea     rcx, [rbp+ThreadInformation]; ThreadInformation
0x180039955  call    ??1CVaultIntegrityLevel@@QEAA@XZ; CVaultIntegrityLevel::~CVaultIntegrityLevel(void)
0x18003995a  nop
0x18003995b  cmp     [rbp+var_50], r15b
0x18003995f  jz      short loc_18003996C
0x180039961  mov     rcx, [rbp+var_58]; Resource
0x180039965  call    cs:__imp_RtlReleaseResource
0x18003996b  nop
0x18003996c  lea     rcx, [rbp+var_38]
0x180039970  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180039975  nop
0x180039976  lea     rcx, [rbp+var_20]
0x18003997a  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003997f  nop
0x180039980  mov     eax, 10D3h
0x180039985  jmp     loc_180039C92
0x18003998a  lea     rcx, [rbp+ThreadInformation]; this
0x18003998e  call    ?Elevate@CVaultIntegrityLevel@@QEAAKXZ; CVaultIntegrityLevel::Elevate(void)
0x180039993  mov     ebx, eax
0x180039995  test    eax, eax
0x180039997  jz      short loc_1800399FF
0x180039999  lea     rax, WPP_GLOBAL_Control
0x1800399a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800399a7  cmp     rcx, rax
0x1800399aa  jz      short loc_1800399CB
0x1800399ac  test    byte ptr [rcx+1Ch], 2
0x1800399b0  jz      short loc_1800399CB
0x1800399b2  mov     edx, 2Eh ; '.'
0x1800399b7  mov     r9d, ebx
0x1800399ba  lea     r8, WPP_c304bf9ddc9a325b3ef15398c2399f48_Traceguids
0x1800399c1  mov     rcx, [rcx+10h]
0x1800399c5  call    WPP_SF_d
0x1800399ca  nop
0x1800399cb  lea     rcx, [rbp+ThreadInformation]; ThreadInformation
0x1800399cf  call    ??1CVaultIntegrityLevel@@QEAA@XZ; CVaultIntegrityLevel::~CVaultIntegrityLevel(void)
0x1800399d4  nop
0x1800399d5  cmp     [rbp+var_50], r15b
0x1800399d9  jz      short loc_1800399E6
0x1800399db  mov     rcx, [rbp+var_58]; Resource
0x1800399df  call    cs:__imp_RtlReleaseResource
0x1800399e5  nop
0x1800399e6  lea     rcx, [rbp+var_38]
0x1800399ea  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800399ef  nop
0x1800399f0  lea     rcx, [rbp+var_20]
0x1800399f4  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800399f9  nop
0x1800399fa  jmp     loc_180039C90
0x1800399ff  lea     r8, [rbp+var_18]
0x180039a03  mov     edx, [rdi+130h]
0x180039a09  call    ?CreateVaultFileSystem@CVaultFactory@@QEAAKW4eFileSystemType@@PEAPEAUIVaultFileSystem@@@Z; CVaultFactory::CreateVaultFileSystem(eFileSystemType,IVaultFileSystem * *)
0x180039a0e  mov     ebx, eax
0x180039a10  test    eax, eax
0x180039a12  jz      short loc_180039A48
0x180039a14  lea     rcx, [rbp+ThreadInformation]; ThreadInformation
0x180039a18  call    ??1CVaultIntegrityLevel@@QEAA@XZ; CVaultIntegrityLevel::~CVaultIntegrityLevel(void)
0x180039a1d  nop
0x180039a1e  cmp     [rbp+var_50], r15b
0x180039a22  jz      short loc_180039A2F
0x180039a24  mov     rcx, [rbp+var_58]; Resource
0x180039a28  call    cs:__imp_RtlReleaseResource
0x180039a2e  nop
0x180039a2f  lea     rcx, [rbp+var_38]
0x180039a33  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180039a38  nop
0x180039a39  lea     rcx, [rbp+var_20]
0x180039a3d  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180039a42  nop
0x180039a43  jmp     loc_180039C90
0x180039a48  mov     rbx, [rbp+var_18]
0x180039a4c  mov     rax, [rbx]
0x180039a4f  mov     rcx, rbx
0x180039a52  mov     rax, [rax+10h]
0x180039a56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039a5b  mov     esi, eax
0x180039a5d  test    eax, eax
0x180039a5f  jz      short loc_180039A97
0x180039a61  lea     rcx, [rbp+ThreadInformation]; ThreadInformation
0x180039a65  call    ??1CVaultIntegrityLevel@@QEAA@XZ; CVaultIntegrityLevel::~CVaultIntegrityLevel(void)
0x180039a6a  nop
0x180039a6b  cmp     [rbp+var_50], r15b
0x180039a6f  jz      short loc_180039A7C
0x180039a71  mov     rcx, [rbp+var_58]; Resource
0x180039a75  call    cs:__imp_RtlReleaseResource
0x180039a7b  nop
0x180039a7c  lea     rcx, [rbp+var_38]
0x180039a80  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180039a85  nop
0x180039a86  lea     rcx, [rbp+var_20]
0x180039a8a  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180039a8f  nop
0x180039a90  mov     eax, esi
0x180039a92  jmp     loc_180039C92
0x180039a97  mov     rdx, rbx; struct IVaultFileSystem *
0x180039a9a  mov     rcx, rdi; this
0x180039a9d  call    ?DeleteAllCredentials@CVaultFileStore@@AEAAKPEAUIVaultFileSystem@@@Z; CVaultFileStore::DeleteAllCredentials(IVaultFileSystem *)
0x180039aa2  mov     esi, eax
0x180039aa4  test    eax, eax
0x180039aa6  jz      short loc_180039AD9
0x180039aa8  lea     rcx, [rbp+ThreadInformation]; ThreadInformation
0x180039aac  call    ??1CVaultIntegrityLevel@@QEAA@XZ; CVaultIntegrityLevel::~CVaultIntegrityLevel(void)
0x180039ab1  nop
0x180039ab2  cmp     [rbp+var_50], r15b
0x180039ab6  jz      short loc_180039AC3
0x180039ab8  mov     rcx, [rbp+var_58]; Resource
0x180039abc  call    cs:__imp_RtlReleaseResource
0x180039ac2  nop
0x180039ac3  lea     rcx, [rbp+var_38]
0x180039ac7  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180039acc  nop
0x180039acd  lea     rcx, [rbp+var_20]
0x180039ad1  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180039ad6  nop
0x180039ad7  jmp     short loc_180039A90
0x180039ad9  mov     r8, rbx; struct IVaultFileSystem *
0x180039adc  mov     dl, 1; unsigned __int8
0x180039ade  mov     rcx, rdi; this
0x180039ae1  call    ?InitializeOrDeleteSchema@CVaultFileStore@@AEAAKEPEAUIVaultFileSystem@@@Z; CVaultFileStore::InitializeOrDeleteSchema(uchar,IVaultFileSystem *)
0x180039ae6  mov     esi, eax
0x180039ae8  test    eax, eax
0x180039aea  jz      short loc_180039B20
0x180039aec  lea     rcx, [rbp+ThreadInformation]; ThreadInformation
0x180039af0  call    ??1CVaultIntegrityLevel@@QEAA@XZ; CVaultIntegrityLevel::~CVaultIntegrityLevel(void)
0x180039af5  nop
0x180039af6  cmp     [rbp+var_50], r15b
0x180039afa  jz      short loc_180039B07
0x180039afc  mov     rcx, [rbp+var_58]; Resource
0x180039b00  call    cs:__imp_RtlReleaseResource
0x180039b06  nop
0x180039b07  lea     rcx, [rbp+var_38]
0x180039b0b  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180039b10  nop
0x180039b11  lea     rcx, [rbp+var_20]
0x180039b15  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180039b1a  nop
0x180039b1b  jmp     loc_180039A90
0x180039b20  lea     r8, [rbp+var_30]; unsigned __int16 **
0x180039b24  lea     rdx, aPolicyVpol; "Policy.vpol"
0x180039b2b  mov     rcx, [rdi+138h]; Source
0x180039b32  call    ?PathCombine@@YAKPEBG0PEAPEAG@Z; PathCombine(ushort const *,ushort const *,ushort * *)
0x180039b37  mov     esi, eax
0x180039b39  test    eax, eax
0x180039b3b  jz      short loc_180039B71
0x180039b3d  lea     rcx, [rbp+ThreadInformation]; ThreadInformation
0x180039b41  call    ??1CVaultIntegrityLevel@@QEAA@XZ; CVaultIntegrityLevel::~CVaultIntegrityLevel(void)
0x180039b46  nop
0x180039b47  cmp     [rbp+var_50], r15b
0x180039b4b  jz      short loc_180039B58
0x180039b4d  mov     rcx, [rbp+var_58]; Resource
0x180039b51  call    cs:__imp_RtlReleaseResource
0x180039b57  nop
0x180039b58  lea     rcx, [rbp+var_38]
0x180039b5c  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180039b61  nop
0x180039b62  lea     rcx, [rbp+var_20]
0x180039b66  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180039b6b  nop
0x180039b6c  jmp     loc_180039A90
0x180039b71  mov     rax, [rbx]
0x180039b74  mov     rdx, [rbp+var_30]
0x180039b78  mov     rcx, rbx
0x180039b7b  mov     rax, [rax+38h]
0x180039b7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039b84  mov     esi, eax
0x180039b86  test    eax, eax
0x180039b88  jz      short loc_180039BBE
0x180039b8a  lea     rcx, [rbp+ThreadInformation]; ThreadInformation
0x180039b8e  call    ??1CVaultIntegrityLevel@@QEAA@XZ; CVaultIntegrityLevel::~CVaultIntegrityLevel(void)
0x180039b93  nop
0x180039b94  cmp     [rbp+var_50], r15b
0x180039b98  jz      short loc_180039BA5
0x180039b9a  mov     rcx, [rbp+var_58]; Resource
0x180039b9e  call    cs:__imp_RtlReleaseResource
0x180039ba4  nop
0x180039ba5  lea     rcx, [rbp+var_38]
0x180039ba9  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180039bae  nop
0x180039baf  lea     rcx, [rbp+var_20]
0x180039bb3  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180039bb8  nop
0x180039bb9  jmp     loc_180039A90
0x180039bbe  mov     rax, [rbx]
0x180039bc1  mov     rdx, [rdi+138h]
0x180039bc8  mov     rcx, rbx
0x180039bcb  mov     rax, [rax+40h]
0x180039bcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039bd4  mov     esi, eax
0x180039bd6  test    eax, eax
0x180039bd8  jz      short loc_180039C0E
0x180039bda  lea     rcx, [rbp+ThreadInformation]; ThreadInformation
0x180039bde  call    ??1CVaultIntegrityLevel@@QEAA@XZ; CVaultIntegrityLevel::~CVaultIntegrityLevel(void)
0x180039be3  nop
0x180039be4  cmp     [rbp+var_50], r15b
0x180039be8  jz      short loc_180039BF5
0x180039bea  mov     rcx, [rbp+var_58]; Resource
0x180039bee  call    cs:__imp_RtlReleaseResource
0x180039bf4  nop
0x180039bf5  lea     rcx, [rbp+var_38]
0x180039bf9  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180039bfe  nop
0x180039bff  lea     rcx, [rbp+var_20]
0x180039c03  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180039c08  nop
0x180039c09  jmp     loc_180039A90
0x180039c0e  mov     rax, [rbx]
0x180039c11  mov     rcx, rbx
0x180039c14  mov     rax, [rax+18h]
0x180039c18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039c1d  mov     ebx, eax
0x180039c1f  test    eax, eax
0x180039c21  jz      short loc_180039C54
0x180039c23  lea     rcx, [rbp+ThreadInformation]; ThreadInformation
0x180039c27  call    ??1CVaultIntegrityLevel@@QEAA@XZ; CVaultIntegrityLevel::~CVaultIntegrityLevel(void)
0x180039c2c  nop
0x180039c2d  cmp     [rbp+var_50], r15b
0x180039c31  jz      short loc_180039C3E
0x180039c33  mov     rcx, [rbp+var_58]; Resource
0x180039c37  call    cs:__imp_RtlReleaseResource
0x180039c3d  nop
0x180039c3e  lea     rcx, [rbp+var_38]
0x180039c42  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180039c47  nop
0x180039c48  lea     rcx, [rbp+var_20]
0x180039c4c  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180039c51  nop
0x180039c52  jmp     short loc_180039C90
0x180039c54  mov     dl, r14b; unsigned __int8
0x180039c57  mov     rcx, rdi; this
0x180039c5a  call    ?DeleteVault@CVaultMemoryStore@@UEAAKE@Z; CVaultMemoryStore::DeleteVault(uchar)
0x180039c5f  mov     ebx, eax
0x180039c61  lea     rcx, [rbp+ThreadInformation]; ThreadInformation
0x180039c65  call    ??1CVaultIntegrityLevel@@QEAA@XZ; CVaultIntegrityLevel::~CVaultIntegrityLevel(void)
0x180039c6a  nop
0x180039c6b  cmp     [rbp+var_50], r15b
0x180039c6f  jz      short loc_180039C7C
0x180039c71  mov     rcx, [rbp+var_58]; Resource
0x180039c75  call    cs:__imp_RtlReleaseResource
0x180039c7b  nop
0x180039c7c  lea     rcx, [rbp+var_38]
0x180039c80  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180039c85  nop
0x180039c86  lea     rcx, [rbp+var_20]
0x180039c8a  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180039c8f  nop
0x180039c90  mov     eax, ebx
0x180039c92  add     rsp, 78h
0x180039c96  pop     r15
0x180039c98  pop     r14
0x180039c9a  pop     rdi
0x180039c9b  pop     rsi
0x180039c9c  pop     rbx
0x180039c9d  pop     rbp
0x180039c9e  retn
```
