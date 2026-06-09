# GetDomainSID(int *,int *,void * *)

- ea: `0x180001760`
- end: `0x180001969`
- name: `?GetDomainSID@@YAJPEAH0PEAPEAX@Z`
- size: `521`
- prototype: `__int64 __fastcall(int *, int *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180001710`

## callees

- `0x180001760`
- `0x18003b7d8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800018e5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800018e5`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180001959`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180001959`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18000194a`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18000194a`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180001840`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180001840`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x180001884`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x180001884`
- `ntdll!RtlLengthSid` at `0x1800018d9`
- `ntdll!RtlLengthSid` at `0x1800018d9`
- `ntdll!RtlGetNtProductType` at `0x1800017c2`
- `ntdll!RtlGetNtProductType` at `0x1800017c2`
- `ntdll!RtlCopySid` at `0x18000192d`
- `ntdll!RtlCopySid` at `0x18000192d`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall GetDomainSID(int *a1, int *a2, void **a3)
{
  NTSTATUS v3; // ebx
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // r9
  void *v7; // rbx
  ULONG v8; // edi
  HLOCAL v9; // rax
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+20h] [rbp-30h] BYREF
  PVOID PolicyHandle; // [rsp+70h] [rbp+20h] BYREF
  PVOID Buffer; // [rsp+78h] [rbp+28h] BYREF
  _NT_PRODUCT_TYPE ProductType; // [rsp+80h] [rbp+30h] BYREF
  int v15; // [rsp+84h] [rbp+34h]

  v15 = HIDWORD(a3);
  ProductType = 0;
  Buffer = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  PolicyHandle = 0;
  VaultGlobals::g_fDomainJoined = 0;
  VaultGlobals::g_fIsDC = 0;
  VaultGlobals::g_DomainSID = 0;
  if ( RtlGetNtProductType(&ProductType) )
  {
    VaultGlobals::g_fIsDC = ProductType == NtProductLanManNt;
    memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
    v3 = LsaOpenPolicy(0, &ObjectAttributes, 0x801u, &PolicyHandle);
    if ( v3 >= 0 )
    {
      v3 = LsaQueryInformationPolicy(PolicyHandle, PolicyPrimaryDomainInformation, &Buffer);
      if ( v3 >= 0 )
      {
        if ( Buffer && *((_QWORD *)Buffer + 2) )
        {
          VaultGlobals::g_fDomainJoined = 1;
          v7 = (void *)*((_QWORD *)Buffer + 2);
          v8 = RtlLengthSid(v7);
          v9 = LocalAlloc(0, v8);
          VaultGlobals::g_DomainSID = v9;
          if ( !v9 )
          {
            v3 = -1073741801;
            v4 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              v5 = 13;
              v6 = 3221225495LL;
              goto LABEL_5;
            }
            goto LABEL_24;
          }
          RtlCopySid(v8, v9, v7);
        }
        else
        {
          VaultGlobals::g_fDomainJoined = 0;
        }
        v3 = 0;
        goto LABEL_24;
      }
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_24;
      v5 = 12;
    }
    else
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_24;
      v5 = 11;
    }
    v6 = (unsigned int)v3;
    goto LABEL_5;
  }
  v3 = -1073741595;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v5 = 10;
    v6 = 3221225701LL;
LABEL_5:
    WPP_SF_d(v4[2], v5, &WPP_df576fef64e13af7ed0e333d0abd1cdb_Traceguids, v6);
  }
LABEL_24:
  if ( Buffer )
    LsaFreeMemory(Buffer);
  if ( PolicyHandle )
    LsaClose(PolicyHandle);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180001760  mov     qword ptr [rsp-18h+ProductType], r8
0x180001765  mov     [rsp-18h+Buffer], rdx
0x18000176a  mov     [rsp-18h+PolicyHandle], rcx
0x18000176f  push    rbp
0x180001770  push    rbx
0x180001771  push    rdi
0x180001772  mov     rbp, rsp
0x180001775  sub     rsp, 50h
0x180001779  xorps   xmm0, xmm0
0x18000177c  mov     [rbp+ProductType], 0
0x180001783  lea     rcx, [rbp+ProductType]; ProductType
0x180001787  mov     [rbp+Buffer], 0
0x18000178f  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180001793  mov     [rbp+PolicyHandle], 0
0x18000179b  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18000179f  mov     cs:?g_fDomainJoined@VaultGlobals@@3HA, 0; int VaultGlobals::g_fDomainJoined
0x1800017a9  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800017ad  mov     cs:?g_fIsDC@VaultGlobals@@3HA, 0; int VaultGlobals::g_fIsDC
0x1800017b7  mov     cs:?g_DomainSID@VaultGlobals@@3PEAXEA, 0; void * VaultGlobals::g_DomainSID
0x1800017c2  call    cs:__imp_RtlGetNtProductType
0x1800017c8  test    al, al
0x1800017ca  jnz     short loc_180001812
0x1800017cc  mov     ebx, 0C00000E5h
0x1800017d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800017d8  lea     rax, WPP_GLOBAL_Control
0x1800017df  cmp     rcx, rax
0x1800017e2  jz      loc_180001941
0x1800017e8  test    byte ptr [rcx+1Ch], 2
0x1800017ec  jz      loc_180001941
0x1800017f2  mov     edx, 0Ah
0x1800017f7  mov     r9d, 0C00000E5h
0x1800017fd  mov     rcx, [rcx+10h]
0x180001801  lea     r8, WPP_df576fef64e13af7ed0e333d0abd1cdb_Traceguids
0x180001808  call    WPP_SF_d
0x18000180d  jmp     loc_180001941
0x180001812  xor     eax, eax
0x180001814  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x180001818  cmp     [rbp+ProductType], 2
0x18000181c  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x180001820  xorps   xmm0, xmm0
0x180001823  mov     r8d, 801h; DesiredAccess
0x180001829  setz    al
0x18000182c  xor     ecx, ecx; SystemName
0x18000182e  mov     cs:?g_fIsDC@VaultGlobals@@3HA, eax; int VaultGlobals::g_fIsDC
0x180001834  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180001838  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18000183c  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180001840  call    cs:__imp_LsaOpenPolicy
0x180001846  mov     ebx, eax
0x180001848  test    eax, eax
0x18000184a  jns     short loc_180001877
0x18000184c  mov     rcx, cs:WPP_GLOBAL_Control
0x180001853  lea     rax, WPP_GLOBAL_Control
0x18000185a  cmp     rcx, rax
0x18000185d  jz      loc_180001941
0x180001863  test    byte ptr [rcx+1Ch], 2
0x180001867  jz      loc_180001941
0x18000186d  mov     edx, 0Bh
0x180001872  mov     r9d, ebx
0x180001875  jmp     short loc_1800017FD
0x180001877  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x18000187b  lea     r8, [rbp+Buffer]; Buffer
0x18000187f  mov     edx, 3; InformationClass
0x180001884  call    cs:__imp_LsaQueryInformationPolicy
0x18000188a  mov     ebx, eax
0x18000188c  test    eax, eax
0x18000188e  jns     short loc_1800018B8
0x180001890  mov     rcx, cs:WPP_GLOBAL_Control
0x180001897  lea     rax, WPP_GLOBAL_Control
0x18000189e  cmp     rcx, rax
0x1800018a1  jz      loc_180001941
0x1800018a7  test    byte ptr [rcx+1Ch], 2
0x1800018ab  jz      loc_180001941
0x1800018b1  mov     edx, 0Ch
0x1800018b6  jmp     short loc_180001872
0x1800018b8  mov     rcx, [rbp+Buffer]
0x1800018bc  test    rcx, rcx
0x1800018bf  jz      short loc_180001935
0x1800018c1  cmp     qword ptr [rcx+10h], 0
0x1800018c6  jz      short loc_180001935
0x1800018c8  mov     cs:?g_fDomainJoined@VaultGlobals@@3HA, 1; int VaultGlobals::g_fDomainJoined
0x1800018d2  mov     rbx, [rcx+10h]
0x1800018d6  mov     rcx, rbx; Sid
0x1800018d9  call    cs:__imp_RtlLengthSid
0x1800018df  mov     edx, eax; uBytes
0x1800018e1  xor     ecx, ecx; uFlags
0x1800018e3  mov     edi, eax
0x1800018e5  call    cs:__imp_LocalAlloc
0x1800018eb  mov     cs:?g_DomainSID@VaultGlobals@@3PEAXEA, rax; void * VaultGlobals::g_DomainSID
0x1800018f2  test    rax, rax
0x1800018f5  jnz     short loc_180001925
0x1800018f7  mov     ebx, 0C0000017h
0x1800018fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180001903  lea     rax, WPP_GLOBAL_Control
0x18000190a  cmp     rcx, rax
0x18000190d  jz      short loc_180001941
0x18000190f  test    byte ptr [rcx+1Ch], 2
0x180001913  jz      short loc_180001941
0x180001915  mov     edx, 0Dh
0x18000191a  mov     r9d, 0C0000017h
0x180001920  jmp     loc_1800017FD
0x180001925  mov     r8, rbx; SourceSid
0x180001928  mov     rdx, rax; DestinationSid
0x18000192b  mov     ecx, edi; DestinationSidLength
0x18000192d  call    cs:__imp_RtlCopySid
0x180001933  jmp     short loc_18000193F
0x180001935  mov     cs:?g_fDomainJoined@VaultGlobals@@3HA, 0; int VaultGlobals::g_fDomainJoined
0x18000193f  xor     ebx, ebx
0x180001941  mov     rcx, [rbp+Buffer]; Buffer
0x180001945  test    rcx, rcx
0x180001948  jz      short loc_180001950
0x18000194a  call    cs:__imp_LsaFreeMemory
0x180001950  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x180001954  test    rcx, rcx
0x180001957  jz      short loc_18000195F
0x180001959  call    cs:__imp_LsaClose
0x18000195f  mov     eax, ebx
0x180001961  add     rsp, 50h
0x180001965  pop     rdi
0x180001966  pop     rbx
0x180001967  pop     rbp
0x180001968  retn
```
