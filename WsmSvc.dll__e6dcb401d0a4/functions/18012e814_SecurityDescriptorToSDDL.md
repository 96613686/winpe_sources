# SecurityDescriptorToSDDL

- ea: `0x18012e814`
- end: `0x18012eb08`
- name: `SecurityDescriptorToSDDL`
- size: `756`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18007965c`
- `0x18012db34`

## callees

- `0x180008920`
- `0x1800621e0`
- `0x18010d8c6`
- `0x180112380`
- `0x1801123a8`
- `0x18012e814`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012e90d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012e9ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012ea87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012e90d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012e9ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012ea87`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18012e983`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18012e983`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18012e8fc`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18012e8fc`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18012e861`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18012e861`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18012ea76`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18012ea76`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
LPWSTR __fastcall SecurityDescriptorToSDDL(__int64 a1, void *a2)
{
  size_t SecurityDescriptorLength; // rsi
  void *v5; // rax
  void *v6; // r14
  void (__fastcall *v8)(__int64, _QWORD); // rbx
  DWORD v9; // eax
  unsigned int v10; // eax
  __int64 v11; // rdx
  struct _ACL *v12; // rcx
  DWORD AceCount; // esi
  DWORD i; // ebx
  int v15; // ecx
  void (__fastcall *v16)(__int64, _QWORD); // rbx
  DWORD LastError; // eax
  unsigned int v18; // eax
  void (__fastcall *v19)(__int64, _QWORD); // rbx
  DWORD v20; // eax
  LPWSTR v21; // rbx
  LPVOID pAce; // [rsp+30h] [rbp-20h] BYREF
  PACL pDacl; // [rsp+38h] [rbp-18h] BYREF
  void *v24; // [rsp+40h] [rbp-10h] BYREF
  LPWSTR StringSecurityDescriptor; // [rsp+48h] [rbp-8h] BYREF
  BOOL bDaclPresent; // [rsp+90h] [rbp+40h] BYREF
  BOOL bDaclDefaulted; // [rsp+98h] [rbp+48h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_da7ed40d09913eb0c9debd1bc41fe78b_Traceguids);
  SecurityDescriptorLength = GetSecurityDescriptorLength(a2);
  v5 = (void *)WSManMemory::Alloc(SecurityDescriptorLength, 0, 0);
  v6 = v5;
  v24 = v5;
  if ( v5 )
  {
    memcpy_0(v5, a2, SecurityDescriptorLength);
    bDaclPresent = 0;
    bDaclDefaulted = 0;
    pDacl = 0;
    if ( GetSecurityDescriptorDacl(v6, &bDaclPresent, &pDacl, &bDaclDefaulted) )
    {
      v12 = pDacl;
      if ( bDaclPresent )
        AceCount = pDacl->AceCount;
      else
        AceCount = 0;
      for ( i = 0; i < AceCount; ++i )
      {
        pAce = 0;
        if ( !GetAce(v12, i, &pAce) )
        {
          v16 = *(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a1 + 72LL);
          LastError = GetLastError();
          v16(a1, LastError);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
          {
            v18 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 152LL))(a1);
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_da7ed40d09913eb0c9debd1bc41fe78b_Traceguids, v18);
          }
          goto LABEL_9;
        }
        if ( *(_BYTE *)pAce <= 1u )
        {
          v15 = *((_DWORD *)pAce + 1);
          *((_DWORD *)pAce + 1) = 0;
          if ( (v15 & 7) == 7 )
          {
            *((_DWORD *)pAce + 1) = 0x10000000;
          }
          else
          {
            if ( (v15 & 1) != 0 )
              *((_DWORD *)pAce + 1) |= 0x80000000;
            if ( (v15 & 2) != 0 )
              *((_DWORD *)pAce + 1) |= 0x40000000u;
            if ( (v15 & 4) != 0 )
              *((_DWORD *)pAce + 1) |= 0x20000000u;
          }
        }
        v12 = pDacl;
      }
      StringSecurityDescriptor = 0;
      if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(v6, 1u, 0xFu, &StringSecurityDescriptor, 0) )
      {
        v21 = StringSecurityDescriptor;
        goto LABEL_40;
      }
      v19 = *(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a1 + 72LL);
      v20 = GetLastError();
      v19(a1, v20);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
      {
        v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 152LL))(a1);
        v11 = 21;
        goto LABEL_37;
      }
    }
    else
    {
      v8 = *(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a1 + 72LL);
      v9 = GetLastError();
      v8(a1, v9);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
      {
        v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 152LL))(a1);
        v11 = 19;
LABEL_37:
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, &WPP_da7ed40d09913eb0c9debd1bc41fe78b_Traceguids, v10);
      }
    }
    v21 = 0;
LABEL_40:
    AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v24);
    return v21;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_da7ed40d09913eb0c9debd1bc41fe78b_Traceguids);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1);
LABEL_9:
    AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v24);
    return 0;
  }
}

```

## disassembly

```asm
0x18012e814  mov     [rsp-28h+arg_0], rbx
0x18012e819  push    rbp
0x18012e81a  push    rsi
0x18012e81b  push    rdi
0x18012e81c  push    r13
0x18012e81e  push    r14
0x18012e820  mov     rbp, rsp
0x18012e823  sub     rsp, 50h
0x18012e827  mov     rbx, rdx
0x18012e82a  mov     rdi, rcx
0x18012e82d  lea     r13, WPP_GLOBAL_Control
0x18012e834  mov     rcx, cs:WPP_GLOBAL_Control
0x18012e83b  cmp     rcx, r13
0x18012e83e  jz      short loc_18012E85E
0x18012e840  test    dword ptr [rcx+1Ch], 20000h
0x18012e847  jz      short loc_18012E85E
0x18012e849  mov     edx, 11h
0x18012e84e  lea     r8, WPP_da7ed40d09913eb0c9debd1bc41fe78b_Traceguids
0x18012e855  mov     rcx, [rcx+10h]
0x18012e859  call    WPP_SF_
0x18012e85e  mov     rcx, rbx; pSecurityDescriptor
0x18012e861  call    cs:__imp_GetSecurityDescriptorLength
0x18012e867  mov     esi, eax
0x18012e869  xor     r8d, r8d
0x18012e86c  xor     edx, edx
0x18012e86e  mov     ecx, eax
0x18012e870  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x18012e875  mov     r14, rax
0x18012e878  mov     [rbp+var_10], rax
0x18012e87c  test    rax, rax
0x18012e87f  jnz     short loc_18012E8C9
0x18012e881  mov     rcx, cs:WPP_GLOBAL_Control
0x18012e888  cmp     rcx, r13
0x18012e88b  jz      short loc_18012E8A9
0x18012e88d  test    dword ptr [rcx+1Ch], 40000h
0x18012e894  jz      short loc_18012E8A9
0x18012e896  lea     edx, [rax+12h]
0x18012e899  lea     r8, WPP_da7ed40d09913eb0c9debd1bc41fe78b_Traceguids
0x18012e8a0  mov     rcx, [rcx+10h]
0x18012e8a4  call    WPP_SF_
0x18012e8a9  mov     rax, [rdi]
0x18012e8ac  mov     rcx, rdi
0x18012e8af  mov     rax, [rax+18h]
0x18012e8b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012e8b8  nop
0x18012e8b9  lea     rcx, [rbp+var_10]
0x18012e8bd  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x18012e8c2  xor     eax, eax
0x18012e8c4  jmp     loc_18012EAF4
0x18012e8c9  mov     r8, rsi; Size
0x18012e8cc  mov     rdx, rbx; Src
0x18012e8cf  mov     rcx, r14; void *
0x18012e8d2  call    memcpy_0
0x18012e8d7  mov     [rbp+bDaclPresent], 0
0x18012e8de  mov     [rbp+bDaclDefaulted], 0
0x18012e8e5  mov     [rbp+pDacl], 0
0x18012e8ed  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x18012e8f1  lea     r8, [rbp+pDacl]; pDacl
0x18012e8f5  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x18012e8f9  mov     rcx, r14; pSecurityDescriptor
0x18012e8fc  call    cs:__imp_GetSecurityDescriptorDacl
0x18012e902  test    eax, eax
0x18012e904  jnz     short loc_18012E959
0x18012e906  mov     rax, [rdi]
0x18012e909  mov     rbx, [rax+48h]
0x18012e90d  call    cs:__imp_GetLastError
0x18012e913  mov     edx, eax
0x18012e915  mov     rcx, rdi
0x18012e918  mov     rax, rbx
0x18012e91b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012e920  mov     rax, cs:WPP_GLOBAL_Control
0x18012e927  cmp     rax, r13
0x18012e92a  jz      loc_18012EAE0
0x18012e930  test    dword ptr [rax+1Ch], 40000h
0x18012e937  jz      loc_18012EAE0
0x18012e93d  mov     rax, [rdi]
0x18012e940  mov     rcx, rdi
0x18012e943  mov     rax, [rax+98h]
0x18012e94a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012e94f  mov     edx, 13h
0x18012e954  jmp     loc_18012EAC6
0x18012e959  mov     rcx, [rbp+pDacl]; pAcl
0x18012e95d  cmp     [rbp+bDaclPresent], 0
0x18012e961  jz      short loc_18012E969
0x18012e963  movzx   esi, word ptr [rcx+4]
0x18012e967  jmp     short loc_18012E96B
0x18012e969  xor     esi, esi
0x18012e96b  xor     ebx, ebx
0x18012e96d  cmp     ebx, esi
0x18012e96f  jnb     loc_18012EA55
0x18012e975  mov     [rbp+pAce], 0
0x18012e97d  lea     r8, [rbp+pAce]; pAce
0x18012e981  mov     edx, ebx; dwAceIndex
0x18012e983  call    cs:__imp_GetAce
0x18012e989  test    eax, eax
0x18012e98b  jz      short loc_18012E9E8
0x18012e98d  mov     rax, [rbp+pAce]
0x18012e991  cmp     byte ptr [rax], 1
0x18012e994  ja      short loc_18012E9E0
0x18012e996  mov     ecx, [rax+4]
0x18012e999  mov     dword ptr [rax+4], 0
0x18012e9a0  mov     eax, ecx
0x18012e9a2  and     eax, 7
0x18012e9a5  cmp     al, 7
0x18012e9a7  jnz     short loc_18012E9B6
0x18012e9a9  mov     rax, [rbp+pAce]
0x18012e9ad  mov     dword ptr [rax+4], 10000000h
0x18012e9b4  jmp     short loc_18012E9E0
0x18012e9b6  test    cl, 1
0x18012e9b9  jz      short loc_18012E9C4
0x18012e9bb  mov     rax, [rbp+pAce]
0x18012e9bf  bts     dword ptr [rax+4], 1Fh
0x18012e9c4  test    cl, 2
0x18012e9c7  jz      short loc_18012E9D2
0x18012e9c9  mov     rax, [rbp+pAce]
0x18012e9cd  bts     dword ptr [rax+4], 1Eh
0x18012e9d2  test    cl, 4
0x18012e9d5  jz      short loc_18012E9E0
0x18012e9d7  mov     rax, [rbp+pAce]
0x18012e9db  bts     dword ptr [rax+4], 1Dh
0x18012e9e0  inc     ebx
0x18012e9e2  mov     rcx, [rbp+pDacl]
0x18012e9e6  jmp     short loc_18012E96D
0x18012e9e8  mov     rax, [rdi]
0x18012e9eb  mov     rbx, [rax+48h]
0x18012e9ef  call    cs:__imp_GetLastError
0x18012e9f5  mov     edx, eax
0x18012e9f7  mov     rcx, rdi
0x18012e9fa  mov     rax, rbx
0x18012e9fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012ea02  mov     rax, cs:WPP_GLOBAL_Control
0x18012ea09  cmp     rax, r13
0x18012ea0c  jz      loc_18012E8B9
0x18012ea12  test    dword ptr [rax+1Ch], 40000h
0x18012ea19  jz      loc_18012E8B9
0x18012ea1f  mov     rax, [rdi]
0x18012ea22  mov     rcx, rdi
0x18012ea25  mov     rax, [rax+98h]
0x18012ea2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012ea31  mov     edx, 14h
0x18012ea36  mov     r9d, eax
0x18012ea39  lea     r8, WPP_da7ed40d09913eb0c9debd1bc41fe78b_Traceguids
0x18012ea40  mov     rcx, cs:WPP_GLOBAL_Control
0x18012ea47  mov     rcx, [rcx+10h]
0x18012ea4b  call    WPP_SF_d
0x18012ea50  jmp     loc_18012E8B9
0x18012ea55  mov     [rbp+StringSecurityDescriptor], 0
0x18012ea5d  mov     [rsp+50h+StringSecurityDescriptorLen], 0; StringSecurityDescriptorLen
0x18012ea66  lea     r9, [rbp+StringSecurityDescriptor]; StringSecurityDescriptor
0x18012ea6a  mov     edx, 1; RequestedStringSDRevision
0x18012ea6f  lea     r8d, [rdx+0Eh]; SecurityInformation
0x18012ea73  mov     rcx, r14; SecurityDescriptor
0x18012ea76  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x18012ea7c  test    eax, eax
0x18012ea7e  jnz     short loc_18012EAE4
0x18012ea80  mov     rax, [rdi]
0x18012ea83  mov     rbx, [rax+48h]
0x18012ea87  call    cs:__imp_GetLastError
0x18012ea8d  mov     edx, eax
0x18012ea8f  mov     rcx, rdi
0x18012ea92  mov     rax, rbx
0x18012ea95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012ea9a  mov     rax, cs:WPP_GLOBAL_Control
0x18012eaa1  cmp     rax, r13
0x18012eaa4  jz      short loc_18012EAE0
0x18012eaa6  test    dword ptr [rax+1Ch], 40000h
0x18012eaad  jz      short loc_18012EAE0
0x18012eaaf  mov     rax, [rdi]
0x18012eab2  mov     rcx, rdi
0x18012eab5  mov     rax, [rax+98h]
0x18012eabc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012eac1  mov     edx, 15h
0x18012eac6  mov     rcx, cs:WPP_GLOBAL_Control
0x18012eacd  mov     r9d, eax
0x18012ead0  lea     r8, WPP_da7ed40d09913eb0c9debd1bc41fe78b_Traceguids
0x18012ead7  mov     rcx, [rcx+10h]
0x18012eadb  call    WPP_SF_d
0x18012eae0  xor     ebx, ebx
0x18012eae2  jmp     short loc_18012EAE8
0x18012eae4  mov     rbx, [rbp+StringSecurityDescriptor]
0x18012eae8  lea     rcx, [rbp+var_10]
0x18012eaec  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x18012eaf1  mov     rax, rbx
0x18012eaf4  mov     rbx, [rsp+50h+arg_0]
0x18012eafc  add     rsp, 50h
0x18012eb00  pop     r14
0x18012eb02  pop     r13
0x18012eb04  pop     rdi
0x18012eb05  pop     rsi
0x18012eb06  pop     rbp
0x18012eb07  retn
```
