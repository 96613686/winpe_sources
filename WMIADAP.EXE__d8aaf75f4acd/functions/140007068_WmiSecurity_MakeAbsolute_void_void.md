# WmiSecurity::MakeAbsolute(void *,void * *)

- ea: `0x140007068`
- end: `0x140007234`
- name: `?MakeAbsolute@WmiSecurity@@AEAAJPEAXPEAPEAX@Z`
- size: `460`
- prototype: `__int64 __fastcall(WmiSecurity *this, void *, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000653c`

## callees

- `0x140007068`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x140007126`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x140007133`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x140007140`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x14000714d`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x14000715a`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x140007126`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x140007133`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x140007140`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x14000714d`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x14000715a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007114`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000720c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007114`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000720c`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x140007106`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x1400071ef`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x140007106`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x1400071ef`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x140007198`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x140007198`

## pseudocode

```c
__int64 __fastcall WmiSecurity::MakeAbsolute(WmiSecurity *this, void *a2, void **a3)
{
  struct _ACL *v6; // r9
  struct _ACL *pSacl; // rax
  void *v8; // rax
  unsigned __int64 v9; // rcx
  void *v10; // rax
  unsigned __int64 v11; // rcx
  void *v12; // rax
  unsigned __int64 v13; // rcx
  void *v14; // rax
  unsigned __int64 v15; // rcx
  void *v16; // rax
  unsigned int v17; // ebx
  PSID pOwner; // [rsp+38h] [rbp-38h]
  PSID pPrimaryGroup; // [rsp+48h] [rbp-28h]
  DWORD dwSaclSize; // [rsp+60h] [rbp-10h] BYREF
  DWORD dwDaclSize; // [rsp+64h] [rbp-Ch] BYREF
  DWORD dwAbsoluteSecurityDescriptorSize; // [rsp+68h] [rbp-8h] BYREF
  DWORD dwPrimaryGroupSize; // [rsp+98h] [rbp+28h] BYREF
  DWORD dwOwnerSize; // [rsp+A8h] [rbp+38h] BYREF

  if ( !a2 || !a3 || *a3 )
    return (unsigned int)-2147418113;
  v6 = (struct _ACL *)*((_QWORD *)this + 2);
  pPrimaryGroup = (PSID)*((_QWORD *)this + 5);
  pOwner = (PSID)*((_QWORD *)this + 4);
  pSacl = (struct _ACL *)*((_QWORD *)this + 3);
  dwDaclSize = 0;
  dwSaclSize = 0;
  dwOwnerSize = 0;
  dwPrimaryGroupSize = 0;
  dwAbsoluteSecurityDescriptorSize = 0;
  if ( MakeAbsoluteSD(
         a2,
         0,
         &dwAbsoluteSecurityDescriptorSize,
         v6,
         &dwDaclSize,
         pSacl,
         &dwSaclSize,
         pOwner,
         &dwOwnerSize,
         pPrimaryGroup,
         &dwPrimaryGroupSize)
    || GetLastError() != 122 )
  {
    v17 = 0;
    if ( !GetLastError() )
      return v17;
    return (unsigned int)-2147467259;
  }
  v8 = CWin32DefaultArena::WbemMemAlloc(dwDaclSize);
  v9 = dwSaclSize;
  *((_QWORD *)this + 2) = v8;
  v10 = CWin32DefaultArena::WbemMemAlloc(v9);
  v11 = dwOwnerSize;
  *((_QWORD *)this + 3) = v10;
  v12 = CWin32DefaultArena::WbemMemAlloc(v11);
  v13 = dwPrimaryGroupSize;
  *((_QWORD *)this + 4) = v12;
  v14 = CWin32DefaultArena::WbemMemAlloc(v13);
  v15 = dwAbsoluteSecurityDescriptorSize;
  *((_QWORD *)this + 5) = v14;
  v16 = CWin32DefaultArena::WbemMemAlloc(v15);
  *a3 = v16;
  if ( !v16 || !*((_QWORD *)this + 2) || !*((_QWORD *)this + 3) || !*((_QWORD *)this + 4) || !*((_QWORD *)this + 5) )
    return (unsigned int)-2147024882;
  if ( !InitializeSecurityDescriptor(v16, 1u) )
    return (unsigned int)-2147467259;
  return !MakeAbsoluteSD(
            a2,
            *a3,
            &dwAbsoluteSecurityDescriptorSize,
            *((PACL *)this + 2),
            &dwDaclSize,
            *((PACL *)this + 3),
            &dwSaclSize,
            *((PSID *)this + 4),
            &dwOwnerSize,
            *((PSID *)this + 5),
            &dwPrimaryGroupSize)
       ? 0x80004005
       : 0;
}

```

## disassembly

```asm
0x140007068  mov     r11, rsp
0x14000706b  mov     [r11+8], rbx
0x14000706f  push    rbp
0x140007070  push    rsi
0x140007071  push    rdi
0x140007072  mov     rbp, rsp
0x140007075  sub     rsp, 70h
0x140007079  mov     rdi, r8
0x14000707c  mov     rsi, rdx
0x14000707f  mov     rbx, rcx
0x140007082  test    rdx, rdx
0x140007085  jz      loc_14000721D
0x14000708b  test    r8, r8
0x14000708e  jz      loc_14000721D
0x140007094  cmp     qword ptr [r8], 0
0x140007098  jnz     loc_14000721D
0x14000709e  mov     r9, [rcx+10h]; pDacl
0x1400070a2  lea     rax, [rbp+dwPrimaryGroupSize]
0x1400070a6  mov     [r11-38h], rax
0x1400070aa  lea     r8, [rbp+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x1400070ae  mov     rax, [rcx+28h]
0x1400070b2  xor     edx, edx; pAbsoluteSecurityDescriptor
0x1400070b4  mov     [r11-40h], rax
0x1400070b8  lea     rax, [rbp+dwOwnerSize]
0x1400070bc  mov     [r11-48h], rax
0x1400070c0  mov     rax, [rcx+20h]
0x1400070c4  mov     [r11-50h], rax
0x1400070c8  lea     rax, [rbp+dwSaclSize]
0x1400070cc  mov     [r11-58h], rax
0x1400070d0  mov     rax, [rcx+18h]
0x1400070d4  mov     rcx, rsi; pSelfRelativeSecurityDescriptor
0x1400070d7  mov     [r11-60h], rax
0x1400070db  lea     rax, [rbp+dwDaclSize]
0x1400070df  mov     [r11-68h], rax
0x1400070e3  mov     [rbp+dwDaclSize], 0
0x1400070ea  mov     [rbp+dwSaclSize], 0
0x1400070f1  mov     [rbp+dwOwnerSize], 0
0x1400070f8  mov     [rbp+dwPrimaryGroupSize], 0
0x1400070ff  mov     [rbp+dwAbsoluteSecurityDescriptorSize], 0
0x140007106  call    cs:__imp_MakeAbsoluteSD
0x14000710c  test    eax, eax
0x14000710e  jnz     loc_14000720A
0x140007114  call    cs:__imp_GetLastError
0x14000711a  cmp     eax, 7Ah ; 'z'
0x14000711d  jnz     loc_14000720A
0x140007123  mov     ecx, [rbp+dwDaclSize]
0x140007126  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x14000712c  mov     ecx, [rbp+dwSaclSize]
0x14000712f  mov     [rbx+10h], rax
0x140007133  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x140007139  mov     ecx, [rbp+dwOwnerSize]
0x14000713c  mov     [rbx+18h], rax
0x140007140  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x140007146  mov     ecx, [rbp+dwPrimaryGroupSize]
0x140007149  mov     [rbx+20h], rax
0x14000714d  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x140007153  mov     ecx, [rbp+dwAbsoluteSecurityDescriptorSize]
0x140007156  mov     [rbx+28h], rax
0x14000715a  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x140007160  mov     [rdi], rax
0x140007163  test    rax, rax
0x140007166  jz      loc_140007203
0x14000716c  cmp     qword ptr [rbx+10h], 0
0x140007171  jz      loc_140007203
0x140007177  cmp     qword ptr [rbx+18h], 0
0x14000717c  jz      loc_140007203
0x140007182  cmp     qword ptr [rbx+20h], 0
0x140007187  jz      short loc_140007203
0x140007189  cmp     qword ptr [rbx+28h], 0
0x14000718e  jz      short loc_140007203
0x140007190  mov     edx, 1; dwRevision
0x140007195  mov     rcx, rax; pSecurityDescriptor
0x140007198  call    cs:__imp_InitializeSecurityDescriptor
0x14000719e  test    eax, eax
0x1400071a0  jz      short loc_140007216
0x1400071a2  mov     r9, [rbx+10h]; pDacl
0x1400071a6  lea     rax, [rbp+dwPrimaryGroupSize]
0x1400071aa  mov     rdx, [rdi]; pAbsoluteSecurityDescriptor
0x1400071ad  lea     r8, [rbp+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x1400071b1  mov     [rsp+70h+lpdwPrimaryGroupSize], rax; lpdwPrimaryGroupSize
0x1400071b6  mov     rcx, rsi; pSelfRelativeSecurityDescriptor
0x1400071b9  mov     rax, [rbx+28h]
0x1400071bd  mov     [rsp+70h+pPrimaryGroup], rax; pPrimaryGroup
0x1400071c2  lea     rax, [rbp+dwOwnerSize]
0x1400071c6  mov     [rsp+70h+lpdwOwnerSize], rax; lpdwOwnerSize
0x1400071cb  mov     rax, [rbx+20h]
0x1400071cf  mov     [rsp+70h+pOwner], rax; pOwner
0x1400071d4  lea     rax, [rbp+dwSaclSize]
0x1400071d8  mov     [rsp+70h+lpdwSaclSize], rax; lpdwSaclSize
0x1400071dd  mov     rax, [rbx+18h]
0x1400071e1  mov     [rsp+70h+pSacl], rax; pSacl
0x1400071e6  lea     rax, [rbp+dwDaclSize]
0x1400071ea  mov     [rsp+70h+lpdwDaclSize], rax; lpdwDaclSize
0x1400071ef  call    cs:__imp_MakeAbsoluteSD
0x1400071f5  neg     eax
0x1400071f7  sbb     ebx, ebx
0x1400071f9  not     ebx
0x1400071fb  and     ebx, 80004005h
0x140007201  jmp     short loc_140007222
0x140007203  mov     ebx, 8007000Eh
0x140007208  jmp     short loc_140007222
0x14000720a  xor     ebx, ebx
0x14000720c  call    cs:__imp_GetLastError
0x140007212  test    eax, eax
0x140007214  jz      short loc_140007222
0x140007216  mov     ebx, 80004005h
0x14000721b  jmp     short loc_140007222
0x14000721d  mov     ebx, 8000FFFFh
0x140007222  mov     eax, ebx
0x140007224  mov     rbx, [rsp+70h+arg_0]
0x14000722c  add     rsp, 70h
0x140007230  pop     rdi
0x140007231  pop     rsi
0x140007232  pop     rbp
0x140007233  retn
```
