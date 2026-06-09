# Catalog::AddAllowAces(_ACL *,void *,IRequestContext &)

- ea: `0x18007aa20`
- end: `0x18007ac01`
- name: `?AddAllowAces@Catalog@@CA_NPEAU_ACL@@PEAXAEAVIRequestContext@@@Z`
- size: `481`
- prototype: `bool __fastcall(PACL pAcl, PSECURITY_DESCRIPTOR pSecurityDescriptor, struct IRequestContext *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18007a248`

## callees

- `0x18007aa20`
- `0x1801123a8`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007aae9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ab43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ab9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007aae9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ab43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ab9a`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x18007aac2`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x18007aac2`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18007aa8f`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18007aa8f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18007aa68`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18007aa68`

## pseudocode

```c
char __fastcall Catalog::AddAllowAces(PACL pAcl, PSECURITY_DESCRIPTOR pSecurityDescriptor, struct IRequestContext *a3)
{
  signed int i; // ebx
  void (__fastcall *v7)(struct IRequestContext *, _QWORD); // rbx
  DWORD v8; // eax
  unsigned int v9; // eax
  __int64 v10; // rdx
  void (__fastcall *v11)(struct IRequestContext *, _QWORD); // rbx
  DWORD v12; // eax
  void (__fastcall *v13)(struct IRequestContext *, _QWORD); // rbx
  DWORD LastError; // eax
  BOOL v15; // [rsp+30h] [rbp-28h] BYREF
  PACL pAcla; // [rsp+38h] [rbp-20h] BYREF
  LPVOID pAce; // [rsp+40h] [rbp-18h] BYREF
  BOOL v18; // [rsp+78h] [rbp+20h] BYREF

  v15 = 0;
  v18 = 0;
  pAcla = 0;
  pAce = 0;
  if ( GetSecurityDescriptorDacl(pSecurityDescriptor, &v18, &pAcla, &v15) )
  {
    if ( v18 )
    {
      for ( i = 0; i < pAcla->AceCount; ++i )
      {
        if ( !GetAce(pAcla, i, &pAce) )
        {
          v13 = *(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a3 + 72LL);
          LastError = GetLastError();
          v13(a3, LastError);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
          {
            v9 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a3 + 152LL))(a3);
            v10 = 63;
            goto LABEL_19;
          }
          return 0;
        }
        if ( !*(_BYTE *)pAce
          && !AddAccessAllowedAceEx(pAcl, 2u, *((unsigned __int8 *)pAce + 1), *((_DWORD *)pAce + 1), (char *)pAce + 8) )
        {
          v11 = *(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a3 + 72LL);
          v12 = GetLastError();
          v11(a3, v12);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
          {
            v9 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a3 + 152LL))(a3);
            v10 = 64;
            goto LABEL_19;
          }
          return 0;
        }
      }
    }
    return 1;
  }
  else
  {
    v7 = *(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a3 + 72LL);
    v8 = GetLastError();
    v7(a3, v8);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
    {
      v9 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a3 + 152LL))(a3);
      v10 = 62;
LABEL_19:
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, &WPP_da7ed40d09913eb0c9debd1bc41fe78b_Traceguids, v9);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x18007aa20  mov     r11, rsp
0x18007aa23  mov     [r11+8], rbx
0x18007aa27  mov     [r11+10h], rsi
0x18007aa2b  push    rdi
0x18007aa2c  sub     rsp, 50h
0x18007aa30  mov     rax, rdx
0x18007aa33  mov     [rsp+58h+var_28], 0
0x18007aa3b  mov     rdi, r8
0x18007aa3e  mov     [rsp+58h+arg_18], 0
0x18007aa46  mov     rsi, rcx
0x18007aa49  mov     qword ptr [r11-20h], 0
0x18007aa51  mov     rcx, rax; pSecurityDescriptor
0x18007aa54  mov     qword ptr [r11-18h], 0
0x18007aa5c  lea     r9, [r11-28h]; lpbDaclDefaulted
0x18007aa60  lea     r8, [r11-20h]; pDacl
0x18007aa64  lea     rdx, [r11+20h]; lpbDaclPresent
0x18007aa68  call    cs:__imp_GetSecurityDescriptorDacl
0x18007aa6e  test    eax, eax
0x18007aa70  jz      short loc_18007AAE2
0x18007aa72  cmp     [rsp+58h+arg_18], 0
0x18007aa77  jz      short loc_18007AAD0
0x18007aa79  xor     ebx, ebx
0x18007aa7b  mov     rcx, [rsp+58h+pAcl]; pAcl
0x18007aa80  movzx   eax, word ptr [rcx+4]
0x18007aa84  cmp     ebx, eax
0x18007aa86  jge     short loc_18007AAD0
0x18007aa88  lea     r8, [rsp+58h+pAce]; pAce
0x18007aa8d  mov     edx, ebx; dwAceIndex
0x18007aa8f  call    cs:__imp_GetAce
0x18007aa95  test    eax, eax
0x18007aa97  jz      loc_18007AB93
0x18007aa9d  mov     r9, [rsp+58h+pAce]
0x18007aaa2  cmp     byte ptr [r9], 0
0x18007aaa6  jnz     short loc_18007AACC
0x18007aaa8  movzx   r8d, byte ptr [r9+1]; AceFlags
0x18007aaad  lea     rax, [r9+8]
0x18007aab1  mov     r9d, [r9+4]; AccessMask
0x18007aab5  mov     edx, 2; dwAceRevision
0x18007aaba  mov     rcx, rsi; pAcl
0x18007aabd  mov     [rsp+58h+pSid], rax; pSid
0x18007aac2  call    cs:__imp_AddAccessAllowedAceEx
0x18007aac8  test    eax, eax
0x18007aaca  jz      short loc_18007AB3C
0x18007aacc  inc     ebx
0x18007aace  jmp     short loc_18007AA7B
0x18007aad0  mov     al, 1
0x18007aad2  mov     rbx, [rsp+58h+arg_0]
0x18007aad7  mov     rsi, [rsp+58h+arg_8]
0x18007aadc  add     rsp, 50h
0x18007aae0  pop     rdi
0x18007aae1  retn
0x18007aae2  mov     rax, [rdi]
0x18007aae5  mov     rbx, [rax+48h]
0x18007aae9  call    cs:__imp_GetLastError
0x18007aaef  mov     edx, eax
0x18007aaf1  mov     rcx, rdi
0x18007aaf4  mov     rax, rbx
0x18007aaf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007aafc  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ab03  lea     rax, WPP_GLOBAL_Control
0x18007ab0a  cmp     rcx, rax
0x18007ab0d  jz      loc_18007ABFA
0x18007ab13  test    dword ptr [rcx+1Ch], 40000h
0x18007ab1a  jz      loc_18007ABFA
0x18007ab20  mov     rax, [rdi]
0x18007ab23  mov     rcx, rdi
0x18007ab26  mov     rax, [rax+98h]
0x18007ab2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ab32  mov     edx, 3Eh ; '>'
0x18007ab37  jmp     loc_18007ABE0
0x18007ab3c  mov     rax, [rdi]
0x18007ab3f  mov     rbx, [rax+48h]
0x18007ab43  call    cs:__imp_GetLastError
0x18007ab49  mov     edx, eax
0x18007ab4b  mov     rcx, rdi
0x18007ab4e  mov     rax, rbx
0x18007ab51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ab56  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ab5d  lea     rax, WPP_GLOBAL_Control
0x18007ab64  cmp     rcx, rax
0x18007ab67  jz      loc_18007ABFA
0x18007ab6d  test    dword ptr [rcx+1Ch], 40000h
0x18007ab74  jz      loc_18007ABFA
0x18007ab7a  mov     rax, [rdi]
0x18007ab7d  mov     rcx, rdi
0x18007ab80  mov     rax, [rax+98h]
0x18007ab87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ab8c  mov     edx, 40h ; '@'
0x18007ab91  jmp     short loc_18007ABE0
0x18007ab93  mov     rax, [rdi]
0x18007ab96  mov     rbx, [rax+48h]
0x18007ab9a  call    cs:__imp_GetLastError
0x18007aba0  mov     edx, eax
0x18007aba2  mov     rcx, rdi
0x18007aba5  mov     rax, rbx
0x18007aba8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007abad  mov     rcx, cs:WPP_GLOBAL_Control
0x18007abb4  lea     rax, WPP_GLOBAL_Control
0x18007abbb  cmp     rcx, rax
0x18007abbe  jz      short loc_18007ABFA
0x18007abc0  test    dword ptr [rcx+1Ch], 40000h
0x18007abc7  jz      short loc_18007ABFA
0x18007abc9  mov     rax, [rdi]
0x18007abcc  mov     rcx, rdi
0x18007abcf  mov     rax, [rax+98h]
0x18007abd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007abdb  mov     edx, 3Fh ; '?'
0x18007abe0  mov     rcx, cs:WPP_GLOBAL_Control
0x18007abe7  lea     r8, WPP_da7ed40d09913eb0c9debd1bc41fe78b_Traceguids
0x18007abee  mov     r9d, eax
0x18007abf1  mov     rcx, [rcx+10h]
0x18007abf5  call    WPP_SF_d
0x18007abfa  xor     al, al
0x18007abfc  jmp     loc_18007AAD2
```
