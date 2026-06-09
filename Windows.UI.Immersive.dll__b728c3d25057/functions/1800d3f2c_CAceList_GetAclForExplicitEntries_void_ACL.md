# CAceList::GetAclForExplicitEntries(void *,_ACL * *)

- ea: `0x1800d3f2c`
- end: `0x1800d40f6`
- name: `?GetAclForExplicitEntries@CAceList@@QEAAJPEAXPEAPEAU_ACL@@@Z`
- size: `458`
- prototype: `__int64 __fastcall(CAceList *__hidden this, void *, struct _ACL **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800d40fc`

## callees

- `0x1800d3f2c`
- `0x1800d445c`
- `0x1800d465c`
- `0x1800d9470`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d40dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d40dc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800d3f7a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800d3f7a`
- `api-ms-win-security-base-l1-1-0!AddAccessDeniedAceEx` at `0x1800d3fd2`
- `api-ms-win-security-base-l1-1-0!AddAccessDeniedAceEx` at `0x1800d4039`
- `api-ms-win-security-base-l1-1-0!AddAccessDeniedAceEx` at `0x1800d3fd2`
- `api-ms-win-security-base-l1-1-0!AddAccessDeniedAceEx` at `0x1800d4039`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800d3f97`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800d3f97`

## pseudocode

```c
__int64 __fastcall CAceList::GetAclForExplicitEntries(CAceList *this, void *a2, struct _ACL **a3)
{
  int v5; // edi
  int RequiredExplictAclSize; // ebp
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rcx
  DWORD v11; // ebp
  struct _ACL *v12; // rax
  struct _ACL *v13; // rbx
  INT_PTR i; // rbp
  struct _DPA *v15; // rcx
  unsigned __int8 *Ptr; // rax
  INT_PTR v17; // rbp
  struct _DPA *v18; // rcx
  PVOID v19; // rax
  INT_PTR j; // rbp
  struct _DPA *v21; // rcx
  struct CAce *v22; // rax
  INT_PTR v23; // rbp
  struct _DPA *v24; // rcx
  struct CAce *v25; // rax

  v5 = -2147024882;
  RequiredExplictAclSize = CAceList::_GetRequiredExplictAclSize(this, a2, this);
  v11 = CAceList::_GetRequiredExplictAclSize(v8, v7, (char *)this + 8) + RequiredExplictAclSize + 8;
  if ( !*((_QWORD *)this + 3) )
    v11 += CAceList::_GetRequiredExplictAclSize(v10, v9, (char *)this + 16);
  v12 = (struct _ACL *)LocalAlloc(0x40u, v11);
  v13 = v12;
  if ( !v12 )
    goto LABEL_33;
  InitializeAcl(v12, v11, 2u);
  for ( i = 0; ; ++i )
  {
    v15 = *(struct _DPA **)this;
    v5 = 0;
    if ( !*(_QWORD *)this || i >= *(int *)v15 )
      break;
    Ptr = (unsigned __int8 *)g_pfn_DPA_GetPtr(v15, i);
    if ( !AddAccessDeniedAceEx(v13, 2u, Ptr[1], *((_DWORD *)Ptr + 1), *((PSID *)Ptr + 1)) )
    {
      v5 = -2147024882;
      break;
    }
  }
  if ( !*((_DWORD *)this + 6) && !*((_DWORD *)this + 7) )
  {
    v17 = 0;
    if ( v5 >= 0 )
    {
      while ( 1 )
      {
        v18 = (struct _DPA *)*((_QWORD *)this + 2);
        if ( !v18 || v17 >= *(int *)v18 )
          break;
        v19 = g_pfn_DPA_GetPtr(v18, v17);
        if ( (*((_BYTE *)v19 + 28) & 1) == 0
          && !AddAccessDeniedAceEx(v13, 2u, *((_BYTE *)v19 + 1) & 0xEF, *((_DWORD *)v19 + 1), *((PSID *)v19 + 1)) )
        {
          v5 = -2147024882;
          goto LABEL_23;
        }
        ++v17;
      }
    }
  }
  for ( j = 0; v5 >= 0; v5 = CAceList::_AddAllowedAceToAcl(this, v22, 0, v13) )
  {
    v21 = (struct _DPA *)*((_QWORD *)this + 1);
    if ( !v21 )
      break;
    if ( j >= *(int *)v21 )
      break;
    v22 = (struct CAce *)g_pfn_DPA_GetPtr(v21, j++);
  }
LABEL_23:
  if ( *((_DWORD *)this + 6) || *((_DWORD *)this + 7) )
  {
LABEL_31:
    if ( v5 >= 0 )
      goto LABEL_33;
LABEL_32:
    LocalFree(v13);
    v13 = 0;
    goto LABEL_33;
  }
  v23 = 0;
  if ( v5 < 0 )
    goto LABEL_32;
  while ( 1 )
  {
    v24 = (struct _DPA *)*((_QWORD *)this + 2);
    if ( !v24 )
      break;
    if ( v23 < *(int *)v24 )
    {
      v25 = (struct CAce *)g_pfn_DPA_GetPtr(v24, v23);
      if ( (*((_BYTE *)v25 + 28) & 1) != 0 )
        v5 = CAceList::_AddAllowedAceToAcl(this, v25, 1, v13);
      ++v23;
      if ( v5 >= 0 )
        continue;
    }
    goto LABEL_31;
  }
LABEL_33:
  *a3 = v13;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800d3f2c  push    rbx
0x1800d3f2e  push    rbp
0x1800d3f2f  push    rsi
0x1800d3f30  push    rdi
0x1800d3f31  push    r14
0x1800d3f33  push    r15
0x1800d3f35  sub     rsp, 38h
0x1800d3f39  mov     r15, r8
0x1800d3f3c  mov     rsi, rcx
0x1800d3f3f  mov     r8, rcx
0x1800d3f42  mov     edi, 8007000Eh
0x1800d3f47  call    ?_GetRequiredExplictAclSize@CAceList@@AEAAKPEAXAEAV?$CDPA@VCAce@@V?$CTContainer_PolicyUnOwned@VCAce@@@@@@@Z; CAceList::_GetRequiredExplictAclSize(void *,CDPA<CAce,CTContainer_PolicyUnOwned<CAce>> &)
0x1800d3f4c  lea     r8, [rsi+8]
0x1800d3f50  mov     ebp, eax
0x1800d3f52  call    ?_GetRequiredExplictAclSize@CAceList@@AEAAKPEAXAEAV?$CDPA@VCAce@@V?$CTContainer_PolicyUnOwned@VCAce@@@@@@@Z; CAceList::_GetRequiredExplictAclSize(void *,CDPA<CAce,CTContainer_PolicyUnOwned<CAce>> &)
0x1800d3f57  add     ebp, 8
0x1800d3f5a  add     ebp, eax
0x1800d3f5c  cmp     dword ptr [rsi+18h], 0
0x1800d3f60  jnz     short loc_1800D3F73
0x1800d3f62  cmp     dword ptr [rsi+1Ch], 0
0x1800d3f66  jnz     short loc_1800D3F73
0x1800d3f68  lea     r8, [rsi+10h]
0x1800d3f6c  call    ?_GetRequiredExplictAclSize@CAceList@@AEAAKPEAXAEAV?$CDPA@VCAce@@V?$CTContainer_PolicyUnOwned@VCAce@@@@@@@Z; CAceList::_GetRequiredExplictAclSize(void *,CDPA<CAce,CTContainer_PolicyUnOwned<CAce>> &)
0x1800d3f71  add     ebp, eax
0x1800d3f73  mov     edx, ebp; uBytes
0x1800d3f75  mov     ecx, 40h ; '@'; uFlags
0x1800d3f7a  call    cs:__imp_LocalAlloc
0x1800d3f80  mov     rbx, rax
0x1800d3f83  test    rax, rax
0x1800d3f86  jz      loc_1800D40E4
0x1800d3f8c  mov     r8d, 2; dwAclRevision
0x1800d3f92  mov     edx, ebp; nAclLength
0x1800d3f94  mov     rcx, rax; pAcl
0x1800d3f97  call    cs:__imp_InitializeAcl
0x1800d3f9d  xor     ebp, ebp
0x1800d3f9f  mov     rcx, [rsi]; hdpa
0x1800d3fa2  xor     edi, edi
0x1800d3fa4  test    rcx, rcx
0x1800d3fa7  jz      short loc_1800D3FE6
0x1800d3fa9  movsxd  rax, dword ptr [rcx]
0x1800d3fac  cmp     rbp, rax
0x1800d3faf  jge     short loc_1800D3FE6
0x1800d3fb1  mov     rdx, rbp; i
0x1800d3fb4  call    cs:g_pfn_DPA_GetPtr
0x1800d3fba  lea     edx, [rdi+2]; dwAceRevision
0x1800d3fbd  mov     rcx, rbx; pAcl
0x1800d3fc0  mov     r9d, [rax+4]; AccessMask
0x1800d3fc4  movzx   r8d, byte ptr [rax+1]; AceFlags
0x1800d3fc9  mov     rax, [rax+8]
0x1800d3fcd  mov     [rsp+68h+pSid], rax; pSid
0x1800d3fd2  call    cs:__imp_AddAccessDeniedAceEx
0x1800d3fd8  test    eax, eax
0x1800d3fda  jz      short loc_1800D3FE1
0x1800d3fdc  inc     rbp
0x1800d3fdf  jmp     short loc_1800D3F9F
0x1800d3fe1  mov     edi, 8007000Eh
0x1800d3fe6  cmp     dword ptr [rsi+18h], 0
0x1800d3fea  jnz     short loc_1800D404F
0x1800d3fec  cmp     dword ptr [rsi+1Ch], 0
0x1800d3ff0  jnz     short loc_1800D404F
0x1800d3ff2  xor     ebp, ebp
0x1800d3ff4  test    edi, edi
0x1800d3ff6  js      short loc_1800D404F
0x1800d3ff8  mov     rcx, [rsi+10h]; hdpa
0x1800d3ffc  test    rcx, rcx
0x1800d3fff  jz      short loc_1800D404F
0x1800d4001  movsxd  rax, dword ptr [rcx]
0x1800d4004  cmp     rbp, rax
0x1800d4007  jge     short loc_1800D404F
0x1800d4009  mov     rdx, rbp; i
0x1800d400c  call    cs:g_pfn_DPA_GetPtr
0x1800d4012  mov     r9, rax
0x1800d4015  test    byte ptr [rax+1Ch], 1
0x1800d4019  jnz     short loc_1800D4043
0x1800d401b  movzx   r8d, byte ptr [rax+1]
0x1800d4020  mov     edx, 2; dwAceRevision
0x1800d4025  mov     rax, [rax+8]
0x1800d4029  and     r8d, 0FFFFFFEFh; AceFlags
0x1800d402d  mov     r9d, [r9+4]; AccessMask
0x1800d4031  mov     rcx, rbx; pAcl
0x1800d4034  mov     [rsp+68h+pSid], rax; pSid
0x1800d4039  call    cs:__imp_AddAccessDeniedAceEx
0x1800d403f  test    eax, eax
0x1800d4041  jz      short loc_1800D4048
0x1800d4043  inc     rbp
0x1800d4046  jmp     short loc_1800D3FF8
0x1800d4048  mov     edi, 8007000Eh
0x1800d404d  jmp     short loc_1800D4089
0x1800d404f  xor     ebp, ebp
0x1800d4051  test    edi, edi
0x1800d4053  js      short loc_1800D4089
0x1800d4055  mov     rcx, [rsi+8]; hdpa
0x1800d4059  test    rcx, rcx
0x1800d405c  jz      short loc_1800D4089
0x1800d405e  movsxd  rax, dword ptr [rcx]
0x1800d4061  cmp     rbp, rax
0x1800d4064  jge     short loc_1800D4089
0x1800d4066  mov     rdx, rbp; i
0x1800d4069  call    cs:g_pfn_DPA_GetPtr
0x1800d406f  mov     r9, rbx; struct _ACL *
0x1800d4072  xor     r8d, r8d; bool
0x1800d4075  mov     rdx, rax; struct CAce *
0x1800d4078  mov     rcx, rsi; this
0x1800d407b  call    ?_AddAllowedAceToAcl@CAceList@@AEAAJQEAVCAce@@_NPEAU_ACL@@@Z; CAceList::_AddAllowedAceToAcl(CAce * const,bool,_ACL *)
0x1800d4080  inc     rbp
0x1800d4083  mov     edi, eax
0x1800d4085  test    eax, eax
0x1800d4087  jns     short loc_1800D4055
0x1800d4089  cmp     dword ptr [rsi+18h], 0
0x1800d408d  jnz     short loc_1800D40D5
0x1800d408f  cmp     dword ptr [rsi+1Ch], 0
0x1800d4093  jnz     short loc_1800D40D5
0x1800d4095  xor     ebp, ebp
0x1800d4097  test    edi, edi
0x1800d4099  js      short loc_1800D40D9
0x1800d409b  mov     rcx, [rsi+10h]; hdpa
0x1800d409f  test    rcx, rcx
0x1800d40a2  jz      short loc_1800D40E4
0x1800d40a4  movsxd  rax, dword ptr [rcx]
0x1800d40a7  cmp     rbp, rax
0x1800d40aa  jge     short loc_1800D40D5
0x1800d40ac  mov     rdx, rbp; i
0x1800d40af  call    cs:g_pfn_DPA_GetPtr
0x1800d40b5  test    byte ptr [rax+1Ch], 1
0x1800d40b9  jz      short loc_1800D40CE
0x1800d40bb  mov     r9, rbx; struct _ACL *
0x1800d40be  mov     r8b, 1; bool
0x1800d40c1  mov     rdx, rax; struct CAce *
0x1800d40c4  mov     rcx, rsi; this
0x1800d40c7  call    ?_AddAllowedAceToAcl@CAceList@@AEAAJQEAVCAce@@_NPEAU_ACL@@@Z; CAceList::_AddAllowedAceToAcl(CAce * const,bool,_ACL *)
0x1800d40cc  mov     edi, eax
0x1800d40ce  inc     rbp
0x1800d40d1  test    edi, edi
0x1800d40d3  jns     short loc_1800D409B
0x1800d40d5  test    edi, edi
0x1800d40d7  jns     short loc_1800D40E4
0x1800d40d9  mov     rcx, rbx; hMem
0x1800d40dc  call    cs:__imp_LocalFree
0x1800d40e2  xor     ebx, ebx
0x1800d40e4  mov     [r15], rbx
0x1800d40e7  mov     eax, edi
0x1800d40e9  add     rsp, 38h
0x1800d40ed  pop     r15
0x1800d40ef  pop     r14
0x1800d40f1  pop     rdi
0x1800d40f2  pop     rsi
0x1800d40f3  pop     rbp
0x1800d40f4  pop     rbx
0x1800d40f5  retn
```
