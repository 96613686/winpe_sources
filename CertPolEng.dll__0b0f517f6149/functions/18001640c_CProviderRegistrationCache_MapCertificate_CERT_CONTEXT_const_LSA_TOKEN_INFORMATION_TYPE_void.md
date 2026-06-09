# CProviderRegistrationCache::MapCertificate(_CERT_CONTEXT const *,_LSA_TOKEN_INFORMATION_TYPE *,void * *)

- ea: `0x18001640c`
- end: `0x1800166e0`
- name: `?MapCertificate@CProviderRegistrationCache@@QEAAJPEBU_CERT_CONTEXT@@PEAW4_LSA_TOKEN_INFORMATION_TYPE@@PEAPEAX@Z`
- size: `724`
- prototype: `__int64 __fastcall(CProviderRegistrationCache *this, const struct _CERT_CONTEXT *, enum _LSA_TOKEN_INFORMATION_TYPE *, void **)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180013ac0`

## callees

- `0x180003dc0`
- `0x180003fb0`
- `0x1800061e0`
- `0x180007b70`
- `0x180007c90`
- `0x180007ea0`
- `0x180009510`
- `0x18000c344`
- `0x18000db54`
- `0x18000e8d6`
- `0x18001640c`
- `0x180017d88`
- `0x18001a342`
- `0x18001a380`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800166a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800166a9`
- `ntdll!RtlAllocateHeap` at `0x180016608`
- `ntdll!RtlAllocateHeap` at `0x180016608`
- `ntdll!RtlReleaseResource` at `0x18001652a`
- `ntdll!RtlReleaseResource` at `0x18001652a`

## string_xrefs

- `0x18001647a`: `CProviderRegistrationCache::MapCertificate`
- `0x1800165c8`: `ConvertIdentityToSid`

## pseudocode

```c
__int64 __fastcall CProviderRegistrationCache::MapCertificate(
        CProviderRegistrationCache *this,
        const struct _CERT_CONTEXT *a2,
        enum _LSA_TOKEN_INFORMATION_TYPE *a3,
        void **a4)
{
  CProviderRegistrationCache *v7; // rbx
  unsigned int ProvFromCertificate; // eax
  __int64 v9; // rdx
  CProviderRegistrationCache *v10; // rcx
  int v11; // ebx
  unsigned int NameFromCert; // eax
  __int64 v13; // rdx
  __int64 v14; // rcx
  unsigned __int16 *v15; // rdi
  const char *v16; // r8
  unsigned int v17; // esi
  unsigned int v18; // eax
  size_t v19; // r12
  _DWORD *Heap; // rax
  _DWORD *v21; // rbx
  unsigned __int16 v23[2]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v24; // [rsp+34h] [rbp-CCh] BYREF
  struct CProviderEntry *v25; // [rsp+38h] [rbp-C8h] BYREF
  HLOCAL hMem; // [rsp+40h] [rbp-C0h] BYREF
  PRTL_RESOURCE Resource; // [rsp+48h] [rbp-B8h] BYREF
  char v28; // [rsp+50h] [rbp-B0h]
  struct _GUID v29; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v30[40]; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int8 Src[112]; // [rsp+90h] [rbp-70h] BYREF

  v7 = g_pProvRegCache;
  v24 = 0;
  v29 = 0;
  v25 = 0;
  hMem = 0;
  v23[0] = 100;
  CLogETWBlock::CLogETWBlock((CLogETWBlock *)v30, "CProviderRegistrationCache::MapCertificate", (int *)a3, 0, &v24);
  if ( !a2 || !a3 || !a4 )
  {
    v11 = -1073741811;
    goto LABEL_31;
  }
  *a3 = LsaTokenInformationNull;
  *a4 = 0;
  CProviderRegistrationCache::RefreshProvCache(v7);
  CAutoRtlLock::CAutoRtlLock(&Resource, (char *)v7 + 16, 0);
  ProvFromCertificate = CProviderRegistrationCache::FindProvFromCertificate(v7, a2, 1, &v25);
  v24 = ProvFromCertificate;
  if ( ProvFromCertificate )
  {
    if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
      McTemplateU0sq_EtwEventWriteTransfer(v10, v9, "FindProvFromCertificate", ProvFromCertificate);
    v11 = -1073741715;
  }
  else
  {
    v11 = 0;
    v29 = *(struct _GUID *)((char *)v25 + 8);
  }
  if ( v28 )
    RtlReleaseResource(Resource);
  if ( v11 >= 0 )
  {
    NameFromCert = CProviderRegistrationCache::GetNameFromCert(
                     v10,
                     a2,
                     1,
                     (unsigned __int16 **)&hMem,
                     (unsigned int *)&v25);
    v24 = NameFromCert;
    v15 = (unsigned __int16 *)hMem;
    if ( NameFromCert )
    {
      if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
      {
        v16 = "GetNameFromCert(Subject)";
LABEL_15:
        McTemplateU0sq_EtwEventWriteTransfer(v14, v13, v16, NameFromCert);
        NameFromCert = v24;
      }
    }
    else
    {
      if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
        McTemplateU0z_EtwEventWriteTransfer(v14, CertSubjectName, hMem);
      NameFromCert = ConvertIdentityToSid(v15, &v29, Src, v23);
      v24 = NameFromCert;
      if ( !NameFromCert )
      {
        v17 = ((v23[0] + 7) & 0xFFFFFFF8) + 64;
        if ( ((v23[0] + 7) & 0xFFFFFFF8) >= 0xFFFFFFC0
          || (v18 = ((v23[0] + 7) & 0xFFFFFFF8) + 88, v18 < ((v23[0] + 7) & 0xFFFFFFF8) + 64) )
        {
          v11 = -1073741675;
        }
        else
        {
          v19 = v18;
          Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v18);
          v21 = Heap;
          if ( Heap )
          {
            memset_0(Heap, 0, v19);
            v21[1] = 0x7FFFFFFF;
            *v21 = -1;
            *((_QWORD *)v21 + 5) = 0;
            *((_QWORD *)v21 + 6) = 0;
            *((_QWORD *)v21 + 7) = 0;
            *((_QWORD *)v21 + 1) = v21 + 16;
            *((_QWORD *)v21 + 3) = (char *)v21 + v17;
            memcpy_0(v21 + 16, Src, v23[0]);
            **((_DWORD **)v21 + 3) = 1;
            *(_QWORD *)(*((_QWORD *)v21 + 3) + 8LL) = *((_QWORD *)v21 + 1);
            *((_QWORD *)v21 + 4) = *((_QWORD *)v21 + 1);
            *a3 = LsaTokenInformationV2;
            *a4 = v21;
            v11 = 0;
          }
          else
          {
            v11 = 8;
          }
        }
        goto LABEL_28;
      }
      if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
      {
        v16 = "ConvertIdentityToSid";
        goto LABEL_15;
      }
    }
    v11 = NetpApiStatusToNtStatus(NameFromCert);
LABEL_28:
    if ( v15 )
      LocalFree(v15);
  }
LABEL_31:
  CLogETWBlock::~CLogETWBlock((CLogETWBlock *)v30);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18001640c  push    rbp
0x18001640e  push    rbx
0x18001640f  push    rsi
0x180016410  push    rdi
0x180016411  push    r12
0x180016413  push    r14
0x180016415  push    r15
0x180016417  lea     rbp, [rsp-10h]
0x18001641c  sub     rsp, 110h
0x180016423  mov     rax, cs:__security_cookie
0x18001642a  xor     rax, rsp
0x18001642d  mov     [rbp+40h+var_40], rax
0x180016431  mov     r15, r9
0x180016434  mov     r14, r8
0x180016437  mov     rdi, rdx
0x18001643a  mov     rbx, cs:?g_pProvRegCache@@3PEAVCProviderRegistrationCache@@EA; CProviderRegistrationCache * g_pProvRegCache
0x180016441  mov     [rsp+140h+var_10C], 0
0x180016449  xorps   xmm0, xmm0
0x18001644c  movups  xmmword ptr [rsp+140h+var_E8.Data1], xmm0
0x180016451  mov     [rsp+140h+var_108], 0
0x18001645a  mov     [rsp+140h+hMem], 0
0x180016463  mov     eax, 64h ; 'd'
0x180016468  mov     [rsp+140h+var_110], ax
0x18001646d  lea     rax, [rsp+140h+var_10C]
0x180016472  mov     [rsp+140h+var_120], rax; unsigned int *
0x180016477  xor     r9d, r9d; int *
0x18001647a  lea     rdx, aCproviderregis_11; "CProviderRegistrationCache::MapCertific"...
0x180016481  lea     rcx, [rsp+140h+var_D8]; this
0x180016486  call    ??0CLogETWBlock@@QEAA@PEBDPEAJ1PEAK@Z; CLogETWBlock::CLogETWBlock(char const *,long *,long *,ulong *)
0x18001648b  nop
0x18001648c  test    rdi, rdi
0x18001648f  jz      loc_1800166B1
0x180016495  test    r14, r14
0x180016498  jz      loc_1800166B1
0x18001649e  test    r15, r15
0x1800164a1  jz      loc_1800166B1
0x1800164a7  mov     dword ptr [r14], 0
0x1800164ae  mov     qword ptr [r15], 0
0x1800164b5  mov     rcx, rbx; this
0x1800164b8  call    ?RefreshProvCache@CProviderRegistrationCache@@AEAAKXZ; CProviderRegistrationCache::RefreshProvCache(void)
0x1800164bd  lea     rdx, [rbx+10h]
0x1800164c1  xor     r8d, r8d
0x1800164c4  lea     rcx, [rsp+140h+Resource]
0x1800164c9  call    ??0CAutoRtlLock@@QEAA@PEAU_RTL_RESOURCE@@W4eRTLLockMode@@@Z; CAutoRtlLock::CAutoRtlLock(_RTL_RESOURCE *,eRTLLockMode)
0x1800164ce  lea     r9, [rsp+140h+var_108]; struct CProviderEntry **
0x1800164d3  mov     esi, 1
0x1800164d8  mov     r8d, esi; int
0x1800164db  mov     rdx, rdi; struct _CERT_CONTEXT *
0x1800164de  mov     rcx, rbx; this
0x1800164e1  call    ?FindProvFromCertificate@CProviderRegistrationCache@@QEAAKPEBU_CERT_CONTEXT@@HPEAPEAVCProviderEntry@@@Z; CProviderRegistrationCache::FindProvFromCertificate(_CERT_CONTEXT const *,int,CProviderEntry * *)
0x1800164e6  mov     [rsp+140h+var_10C], eax
0x1800164ea  test    eax, eax
0x1800164ec  jz      short loc_18001650D
0x1800164ee  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x1800164f5  jz      short loc_180016506
0x1800164f7  mov     r9d, eax
0x1800164fa  lea     r8, aFindprovfromce_0; "FindProvFromCertificate"
0x180016501  call    McTemplateU0sq_EtwEventWriteTransfer
0x180016506  mov     ebx, 0C000006Dh
0x18001650b  jmp     short loc_18001651E
0x18001650d  xor     ebx, ebx
0x18001650f  mov     rax, [rsp+140h+var_108]
0x180016514  movups  xmm0, xmmword ptr [rax+8]
0x180016518  movdqu  xmmword ptr [rsp+140h+var_E8.Data1], xmm0
0x18001651e  cmp     [rsp+140h+var_F0], 0
0x180016523  jz      short loc_180016530
0x180016525  mov     rcx, [rsp+140h+Resource]; Resource
0x18001652a  call    cs:__imp_RtlReleaseResource
0x180016530  test    ebx, ebx
0x180016532  js      loc_1800166B6
0x180016538  lea     rax, [rsp+140h+var_108]
0x18001653d  mov     [rsp+140h+var_120], rax; unsigned int *
0x180016542  lea     r9, [rsp+140h+hMem]; unsigned __int16 **
0x180016547  mov     r8d, esi; int
0x18001654a  mov     rdx, rdi; struct _CERT_CONTEXT *
0x18001654d  call    ?GetNameFromCert@CProviderRegistrationCache@@QEAAKPEBU_CERT_CONTEXT@@HPEAPEAGPEAK@Z; CProviderRegistrationCache::GetNameFromCert(_CERT_CONTEXT const *,int,ushort * *,ulong *)
0x180016552  mov     [rsp+140h+var_10C], eax
0x180016556  mov     rdi, [rsp+140h+hMem]
0x18001655b  test    eax, eax
0x18001655d  jz      short loc_180016589
0x18001655f  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x180016566  jz      short loc_18001657B
0x180016568  lea     r8, aGetnamefromcer_0; "GetNameFromCert(Subject)"
0x18001656f  mov     r9d, eax
0x180016572  call    McTemplateU0sq_EtwEventWriteTransfer
0x180016577  mov     eax, [rsp+140h+var_10C]
0x18001657b  mov     ecx, eax
0x18001657d  call    NetpApiStatusToNtStatus
0x180016582  mov     ebx, eax
0x180016584  jmp     loc_1800166A1
0x180016589  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, sil
0x180016590  jz      short loc_1800165A1
0x180016592  mov     r8, rdi
0x180016595  lea     rdx, CertSubjectName
0x18001659c  call    McTemplateU0z_EtwEventWriteTransfer
0x1800165a1  lea     r9, [rsp+140h+var_110]; unsigned __int16 *
0x1800165a6  lea     r8, [rbp+40h+Src]; unsigned __int8 *
0x1800165aa  lea     rdx, [rsp+140h+var_E8]; struct _GUID *
0x1800165af  mov     rcx, rdi; unsigned __int16 *
0x1800165b2  call    ?ConvertIdentityToSid@@YAKPEBGAEBU_GUID@@PEAEPEAG@Z; ConvertIdentityToSid(ushort const *,_GUID const &,uchar *,ushort *)
0x1800165b7  mov     [rsp+140h+var_10C], eax
0x1800165bb  test    eax, eax
0x1800165bd  jz      short loc_1800165D1
0x1800165bf  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x1800165c6  jz      short loc_18001657B
0x1800165c8  lea     r8, aConvertidentit; "ConvertIdentityToSid"
0x1800165cf  jmp     short loc_18001656F
0x1800165d1  movzx   esi, [rsp+140h+var_110]
0x1800165d6  add     esi, 7
0x1800165d9  and     esi, 0FFFFFFF8h
0x1800165dc  add     esi, 40h ; '@'
0x1800165df  cmp     esi, 40h ; '@'
0x1800165e2  jb      loc_18001669C
0x1800165e8  lea     eax, [rsi+18h]
0x1800165eb  cmp     eax, esi
0x1800165ed  jb      loc_18001669C
0x1800165f3  mov     r12d, eax
0x1800165f6  mov     rcx, gs:60h
0x1800165ff  mov     r8d, eax; Size
0x180016602  xor     edx, edx; Flags
0x180016604  mov     rcx, [rcx+30h]; HeapHandle
0x180016608  call    cs:__imp_RtlAllocateHeap
0x18001660e  mov     rbx, rax
0x180016611  test    rax, rax
0x180016614  jnz     short loc_18001661E
0x180016616  lea     ebx, [rax+8]
0x180016619  jmp     loc_1800166A1
0x18001661e  mov     r8, r12; Size
0x180016621  xor     edx, edx; Val
0x180016623  mov     rcx, rbx; void *
0x180016626  call    memset_0
0x18001662b  mov     dword ptr [rbx+4], 7FFFFFFFh
0x180016632  mov     dword ptr [rbx], 0FFFFFFFFh
0x180016638  mov     qword ptr [rbx+28h], 0
0x180016640  mov     qword ptr [rbx+30h], 0
0x180016648  mov     qword ptr [rbx+38h], 0
0x180016650  lea     rcx, [rbx+40h]; void *
0x180016654  mov     [rbx+8], rcx
0x180016658  mov     eax, esi
0x18001665a  add     rax, rbx
0x18001665d  mov     [rbx+18h], rax
0x180016661  movzx   r8d, [rsp+140h+var_110]; Size
0x180016667  lea     rdx, [rbp+40h+Src]; Src
0x18001666b  call    memcpy_0
0x180016670  mov     rax, [rbx+18h]
0x180016674  mov     dword ptr [rax], 1
0x18001667a  mov     rcx, [rbx+18h]
0x18001667e  mov     rax, [rbx+8]
0x180016682  mov     [rcx+8], rax
0x180016686  mov     rax, [rbx+8]
0x18001668a  mov     [rbx+20h], rax
0x18001668e  mov     dword ptr [r14], 2
0x180016695  mov     [r15], rbx
0x180016698  xor     ebx, ebx
0x18001669a  jmp     short loc_1800166A1
0x18001669c  mov     ebx, 0C0000095h
0x1800166a1  test    rdi, rdi
0x1800166a4  jz      short loc_1800166B6
0x1800166a6  mov     rcx, rdi; hMem
0x1800166a9  call    cs:__imp_LocalFree
0x1800166af  jmp     short loc_1800166B6
0x1800166b1  mov     ebx, 0C000000Dh
0x1800166b6  lea     rcx, [rsp+140h+var_D8]; this
0x1800166bb  call    ??1CLogETWBlock@@QEAA@XZ; CLogETWBlock::~CLogETWBlock(void)
0x1800166c0  mov     eax, ebx
0x1800166c2  mov     rcx, [rbp+40h+var_40]
0x1800166c6  xor     rcx, rsp; StackCookie
0x1800166c9  call    __security_check_cookie
0x1800166ce  add     rsp, 110h
0x1800166d5  pop     r15
0x1800166d7  pop     r14
0x1800166d9  pop     r12
0x1800166db  pop     rdi
0x1800166dc  pop     rsi
0x1800166dd  pop     rbx
0x1800166de  pop     rbp
0x1800166df  retn
```
