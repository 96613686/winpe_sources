# Mp2DemuxSec::CDemuxSec::CreateSecurityAttributes(_ACCESS_MODE,ulong,_ACCESS_MODE,ulong)

- ea: `0x18003b428`
- end: `0x18003b7b6`
- name: `?CreateSecurityAttributes@CDemuxSec@Mp2DemuxSec@@IEAAJW4_ACCESS_MODE@@K0K@Z`
- size: `910`
- prototype: `__int64 __fastcall(Mp2DemuxSec::CDemuxSec *__hidden this, enum _ACCESS_MODE, unsigned int, enum _ACCESS_MODE, unsigned int)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18003b3a0`
- `0x1800b4b40`

## callees

- `0x180002820`
- `0x18000b8c0`
- `0x18002d514`
- `0x18003b428`
- `0x180073d4c`
- `0x180073d58`
- `0x180074a06`
- `0x18009b2fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b5b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b5f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b642`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b5b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b5f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b642`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003b6ed`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003b6ed`
- `api-ms-win-security-trustee-l1-1-0!BuildTrusteeWithSidW` at `0x18003b4cb`
- `api-ms-win-security-trustee-l1-1-0!BuildTrusteeWithSidW` at `0x18003b52e`
- `api-ms-win-security-trustee-l1-1-0!BuildTrusteeWithSidW` at `0x18003b4cb`
- `api-ms-win-security-trustee-l1-1-0!BuildTrusteeWithSidW` at `0x18003b52e`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18003b70e`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18003b70e`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18003b731`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18003b731`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18003b54a`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18003b54a`

## string_xrefs

- `0x18003b573`: `Mp2DemuxSec::CDemuxSec::CreateSecurityAttributes`
- `0x18003b5d6`: `Mp2DemuxSec::CDemuxSec::CreateSecurityAttributes`
- `0x18003b613`: `Mp2DemuxSec::CDemuxSec::CreateSecurityAttributes`
- `0x18003b65c`: `Mp2DemuxSec::CDemuxSec::CreateSecurityAttributes`
- `0x18003b6b2`: `Mp2DemuxSec::CDemuxSec::CreateSecurityAttributes`
- `0x18003b768`: `Mp2DemuxSec::CDemuxSec::CreateSecurityAttributes`

## pseudocode

```c
__int64 __fastcall Mp2DemuxSec::CDemuxSec::CreateSecurityAttributes(
        Mp2DemuxSec::CDemuxSec *this,
        enum _ACCESS_MODE a2,
        DWORD a3,
        enum _ACCESS_MODE a4,
        unsigned int a5)
{
  struct _EXPLICIT_ACCESS_W *v7; // r14
  unsigned int v8; // eax
  __int64 v9; // rbx
  unsigned int v10; // esi
  __int64 v11; // rax
  signed int v12; // eax
  signed int v13; // esi
  unsigned int v14; // ebx
  __int64 v15; // r8
  signed int LastError; // eax
  __int64 v18; // rdx
  signed int v19; // eax
  __int64 v20; // rdx
  signed int v21; // eax
  HLOCAL v22; // rax
  __int64 v23; // rax
  char v24; // [rsp+88h] [rbp+50h] BYREF

  if ( !*((_QWORD *)this + 6) || !*((_QWORD *)this + 8) )
  {
    v7 = 0;
    v14 = -2147418113;
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)&v24,
      "Mp2DemuxSec::CDemuxSec::CreateSecurityAttributes",
      3091);
    if ( !byte_1800EACCB )
      goto LABEL_11;
    v18 = 38;
    goto LABEL_38;
  }
  v7 = (struct _EXPLICIT_ACCESS_W *)operator new[](saturated_mul(*((unsigned __int8 *)this + 56) + 1LL, 0x30u));
  if ( !v7 )
  {
    v14 = -2147024882;
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)&v24,
      "Mp2DemuxSec::CDemuxSec::CreateSecurityAttributes",
      3098);
    if ( !byte_1800EACCB )
      goto LABEL_11;
    v18 = 39;
LABEL_38:
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), v18, &WPP_ea15c8c7cf393e7e63170f2c53fa20e3_Traceguids, this);
    goto LABEL_11;
  }
  memset_0(v7, 0, 48 * (*((unsigned __int8 *)this + 56) + 1LL));
  LOBYTE(v8) = *((_BYTE *)this + 56);
  v9 = 0;
  if ( (_BYTE)v8 )
  {
    v10 = a5;
    do
    {
      v11 = v9;
      v7[v11].grfAccessPermissions = v10;
      *(_QWORD *)&v7[v11].grfAccessMode = 2;
      BuildTrusteeWithSidW(&v7[v9].Trustee, *(PSID *)(*((_QWORD *)this + 6) + 8 * v9));
      v8 = *((unsigned __int8 *)this + 56);
      v9 = (unsigned int)(v9 + 1);
    }
    while ( (unsigned int)v9 < v8 );
  }
  v7[(unsigned __int8)v8].grfAccessPermissions = a3;
  v7[*((unsigned __int8 *)this + 56)].grfAccessMode = SET_ACCESS;
  v7[*((unsigned __int8 *)this + 56)].grfInheritance = 0;
  BuildTrusteeWithSidW(&v7[*((unsigned __int8 *)this + 56)].Trustee, *((PSID *)this + 8));
  v12 = SetEntriesInAclW(*((unsigned __int8 *)this + 56) + 1, v7, 0, (PACL *)this + 9);
  v13 = v12;
  if ( v12 )
  {
    if ( v12 <= 0 )
      v14 = v12;
    else
      v14 = (unsigned __int16)v12 | 0x80070000;
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)&v24,
      "Mp2DemuxSec::CDemuxSec::CreateSecurityAttributes",
      3135);
    if ( !byte_1800EACCB )
      goto LABEL_11;
    v20 = 40;
    goto LABEL_27;
  }
  v22 = LocalAlloc(0x40u, 0x28u);
  *((_QWORD *)this + 1) = v22;
  if ( !v22 )
  {
    LastError = GetLastError();
    v14 = LastError;
    if ( LastError > 0 )
      v14 = (unsigned __int16)LastError | 0x80070000;
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)&v24,
      "Mp2DemuxSec::CDemuxSec::CreateSecurityAttributes",
      3148);
    if ( !byte_1800EACCB )
      goto LABEL_11;
    v18 = 41;
    goto LABEL_38;
  }
  if ( !InitializeSecurityDescriptor(v22, 1u) )
  {
    v19 = GetLastError();
    v13 = v19;
    if ( v19 > 0 )
      v14 = (unsigned __int16)v19 | 0x80070000;
    else
      v14 = v19;
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)&v24,
      "Mp2DemuxSec::CDemuxSec::CreateSecurityAttributes",
      3159);
    if ( !byte_1800EACCB )
      goto LABEL_11;
    v20 = 42;
    goto LABEL_27;
  }
  if ( SetSecurityDescriptorDacl(*((PSECURITY_DESCRIPTOR *)this + 1), 1, *((PACL *)this + 9), 0) )
  {
    v23 = *((_QWORD *)this + 1);
    v14 = 0;
    *((_DWORD *)this + 4) = 24;
    *((_QWORD *)this + 3) = v23;
    *((_DWORD *)this + 8) = 0;
    *((_QWORD *)this + 5) = (char *)this + 16;
    goto LABEL_12;
  }
  v21 = GetLastError();
  v13 = v21;
  if ( v21 > 0 )
    v14 = (unsigned __int16)v21 | 0x80070000;
  else
    v14 = v21;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v24,
    "Mp2DemuxSec::CDemuxSec::CreateSecurityAttributes",
    3174);
  if ( byte_1800EACCB )
  {
    v20 = 43;
LABEL_27:
    WPP_SF_qDd(*((_QWORD *)WPP_GLOBAL_Control + 17), v20, v15, this, v13, v14);
  }
LABEL_11:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v24);
LABEL_12:
  operator delete(v7);
  return v14;
}

```

## disassembly

```asm
0x18003b428  push    rbp
0x18003b42a  push    rbx
0x18003b42b  push    rsi
0x18003b42c  push    rdi
0x18003b42d  push    r14
0x18003b42f  push    r15
0x18003b431  mov     rbp, rsp
0x18003b434  sub     rsp, 38h
0x18003b438  cmp     qword ptr [rcx+30h], 0
0x18003b43d  mov     r15d, r8d
0x18003b440  mov     rdi, rcx
0x18003b443  jz      loc_18003B765
0x18003b449  cmp     qword ptr [rcx+40h], 0
0x18003b44e  jz      loc_18003B765
0x18003b454  movzx   edx, byte ptr [rcx+38h]
0x18003b458  mov     eax, 30h ; '0'
0x18003b45d  inc     rdx
0x18003b460  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18003b467  mul     rdx
0x18003b46a  cmovb   rax, rcx
0x18003b46e  mov     rcx, rax; unsigned __int64
0x18003b471  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18003b476  mov     r14, rax
0x18003b479  test    rax, rax
0x18003b47c  jz      loc_18003B6AC
0x18003b482  movzx   eax, byte ptr [rdi+38h]
0x18003b486  xor     edx, edx; Val
0x18003b488  inc     rax
0x18003b48b  mov     rcx, r14; void *
0x18003b48e  lea     r8, [rax+rax*2]
0x18003b492  shl     r8, 4; Size
0x18003b496  call    memset_0
0x18003b49b  mov     al, [rdi+38h]
0x18003b49e  xor     ebx, ebx
0x18003b4a0  test    al, al
0x18003b4a2  jz      short loc_18003B4E1
0x18003b4a4  mov     esi, [rbp+arg_20]
0x18003b4a7  lea     rax, [rbx+rbx*2]
0x18003b4ab  shl     rax, 4
0x18003b4af  lea     rcx, [r14+10h]
0x18003b4b3  add     rcx, rax; pTrustee
0x18003b4b6  mov     [rax+r14], esi
0x18003b4ba  mov     qword ptr [rax+r14+4], 2
0x18003b4c3  mov     rdx, [rdi+30h]
0x18003b4c7  mov     rdx, [rdx+rbx*8]; pSid
0x18003b4cb  call    cs:__imp_BuildTrusteeWithSidW
0x18003b4d2  nop     dword ptr [rax+rax+00h]
0x18003b4d7  movzx   eax, byte ptr [rdi+38h]
0x18003b4db  inc     ebx
0x18003b4dd  cmp     ebx, eax
0x18003b4df  jb      short loc_18003B4A7
0x18003b4e1  movzx   eax, al
0x18003b4e4  lea     rcx, [rax+rax*2]
0x18003b4e8  add     rcx, rcx
0x18003b4eb  mov     [r14+rcx*8], r15d
0x18003b4ef  movzx   eax, byte ptr [rdi+38h]
0x18003b4f3  lea     rcx, [rax+rax*2]
0x18003b4f7  add     rcx, rcx
0x18003b4fa  mov     dword ptr [r14+rcx*8+4], 2
0x18003b503  movzx   eax, byte ptr [rdi+38h]
0x18003b507  lea     rcx, [rax+rax*2]
0x18003b50b  add     rcx, rcx
0x18003b50e  mov     dword ptr [r14+rcx*8+8], 0
0x18003b517  movzx   eax, byte ptr [rdi+38h]
0x18003b51b  mov     rdx, [rdi+40h]; pSid
0x18003b51f  lea     rcx, [rax+rax*2]
0x18003b523  shl     rcx, 4
0x18003b527  add     rcx, 10h
0x18003b52b  add     rcx, r14; pTrustee
0x18003b52e  call    cs:__imp_BuildTrusteeWithSidW
0x18003b535  nop     dword ptr [rax+rax+00h]
0x18003b53a  movzx   ecx, byte ptr [rdi+38h]
0x18003b53e  lea     r9, [rdi+48h]; NewAcl
0x18003b542  inc     ecx; cCountOfExplicitEntries
0x18003b544  xor     r8d, r8d; OldAcl
0x18003b547  mov     rdx, r14; pListOfExplicitEntries
0x18003b54a  call    cs:__imp_SetEntriesInAclW
0x18003b551  nop     dword ptr [rax+rax+00h]
0x18003b556  mov     esi, eax
0x18003b558  test    eax, eax
0x18003b55a  jz      loc_18003B6E5
0x18003b560  test    eax, eax
0x18003b562  jle     short loc_18003B5B1
0x18003b564  movzx   ebx, si
0x18003b567  or      ebx, 80070000h
0x18003b56d  mov     r8d, 0C3Fh; int
0x18003b573  lea     rdx, aMp2demuxsecCde; "Mp2DemuxSec::CDemuxSec::CreateSecurityA"...
0x18003b57a  lea     rcx, [rbp+arg_18]; this
0x18003b57e  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003b583  cmp     cs:byte_1800EACCB, 1
0x18003b58a  jnb     loc_18003B6DE
0x18003b590  lea     rcx, [rbp+arg_18]; this
0x18003b594  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18003b599  mov     rcx, r14; Block
0x18003b59c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003b5a1  mov     eax, ebx
0x18003b5a3  add     rsp, 38h
0x18003b5a7  pop     r15
0x18003b5a9  pop     r14
0x18003b5ab  pop     rdi
0x18003b5ac  pop     rsi
0x18003b5ad  pop     rbx
0x18003b5ae  pop     rbp
0x18003b5af  retn
0x18003b5b1  mov     ebx, esi
0x18003b5b3  jmp     short loc_18003B56D
0x18003b5b5  call    cs:__imp_GetLastError
0x18003b5bc  nop     dword ptr [rax+rax+00h]
0x18003b5c1  mov     ebx, eax
0x18003b5c3  test    eax, eax
0x18003b5c5  jle     short loc_18003B5D0
0x18003b5c7  movzx   ebx, ax
0x18003b5ca  or      ebx, 80070000h
0x18003b5d0  mov     r8d, 0C4Ch; int
0x18003b5d6  lea     rdx, aMp2demuxsecCde; "Mp2DemuxSec::CDemuxSec::CreateSecurityA"...
0x18003b5dd  lea     rcx, [rbp+arg_18]; this
0x18003b5e1  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003b5e6  cmp     cs:byte_1800EACCB, 1
0x18003b5ed  jb      short loc_18003B590
0x18003b5ef  mov     edx, 29h ; ')'
0x18003b5f4  jmp     loc_18003B794
0x18003b5f9  call    cs:__imp_GetLastError
0x18003b600  nop     dword ptr [rax+rax+00h]
0x18003b605  mov     esi, eax
0x18003b607  test    eax, eax
0x18003b609  jg      short loc_18003B637
0x18003b60b  mov     ebx, eax
0x18003b60d  mov     r8d, 0C57h; int
0x18003b613  lea     rdx, aMp2demuxsecCde; "Mp2DemuxSec::CDemuxSec::CreateSecurityA"...
0x18003b61a  lea     rcx, [rbp+arg_18]; this
0x18003b61e  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003b623  cmp     cs:byte_1800EACCB, 1
0x18003b62a  jb      loc_18003B590
0x18003b630  mov     edx, 2Ah ; '*'
0x18003b635  jmp     short loc_18003B67E
0x18003b637  movzx   ebx, si
0x18003b63a  or      ebx, 80070000h
0x18003b640  jmp     short loc_18003B60D
0x18003b642  call    cs:__imp_GetLastError
0x18003b649  nop     dword ptr [rax+rax+00h]
0x18003b64e  mov     esi, eax
0x18003b650  test    eax, eax
0x18003b652  jg      short loc_18003B6A1
0x18003b654  mov     ebx, eax
0x18003b656  mov     r8d, 0C66h; int
0x18003b65c  lea     rdx, aMp2demuxsecCde; "Mp2DemuxSec::CDemuxSec::CreateSecurityA"...
0x18003b663  lea     rcx, [rbp+arg_18]; this
0x18003b667  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003b66c  cmp     cs:byte_1800EACCB, 1
0x18003b673  jb      loc_18003B590
0x18003b679  mov     edx, 2Bh ; '+'
0x18003b67e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b685  mov     r9, rdi
0x18003b688  mov     [rsp+38h+var_10], ebx
0x18003b68c  mov     [rsp+38h+var_18], esi
0x18003b690  mov     rcx, [rcx+88h]
0x18003b697  call    WPP_SF_qDd
0x18003b69c  jmp     loc_18003B590
0x18003b6a1  movzx   ebx, si
0x18003b6a4  or      ebx, 80070000h
0x18003b6aa  jmp     short loc_18003B656
0x18003b6ac  mov     r8d, 0C1Ah; int
0x18003b6b2  lea     rdx, aMp2demuxsecCde; "Mp2DemuxSec::CDemuxSec::CreateSecurityA"...
0x18003b6b9  lea     rcx, [rbp+arg_18]; this
0x18003b6bd  mov     ebx, 8007000Eh
0x18003b6c2  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003b6c7  cmp     cs:byte_1800EACCB, 1
0x18003b6ce  jb      loc_18003B590
0x18003b6d4  mov     edx, 27h ; '''
0x18003b6d9  jmp     loc_18003B794
0x18003b6de  mov     edx, 28h ; '('
0x18003b6e3  jmp     short loc_18003B67E
0x18003b6e5  mov     edx, 28h ; '('; uBytes
0x18003b6ea  lea     ecx, [rdx+18h]; uFlags
0x18003b6ed  call    cs:__imp_LocalAlloc
0x18003b6f4  nop     dword ptr [rax+rax+00h]
0x18003b6f9  mov     [rdi+8], rax
0x18003b6fd  test    rax, rax
0x18003b700  jz      loc_18003B5B5
0x18003b706  mov     edx, 1; dwRevision
0x18003b70b  mov     rcx, rax; pSecurityDescriptor
0x18003b70e  call    cs:__imp_InitializeSecurityDescriptor
0x18003b715  nop     dword ptr [rax+rax+00h]
0x18003b71a  test    eax, eax
0x18003b71c  jz      loc_18003B5F9
0x18003b722  mov     r8, [rdi+48h]; pDacl
0x18003b726  xor     r9d, r9d; bDaclDefaulted
0x18003b729  mov     rcx, [rdi+8]; pSecurityDescriptor
0x18003b72d  lea     edx, [r9+1]; bDaclPresent
0x18003b731  call    cs:__imp_SetSecurityDescriptorDacl
0x18003b738  nop     dword ptr [rax+rax+00h]
0x18003b73d  test    eax, eax
0x18003b73f  jz      loc_18003B642
0x18003b745  mov     rax, [rdi+8]
0x18003b749  lea     rcx, [rdi+10h]
0x18003b74d  xor     ebx, ebx
0x18003b74f  mov     dword ptr [rcx], 18h
0x18003b755  mov     [rdi+18h], rax
0x18003b759  mov     [rdi+20h], ebx
0x18003b75c  mov     [rdi+28h], rcx
0x18003b760  jmp     loc_18003B599
0x18003b765  xor     r14d, r14d
0x18003b768  lea     rdx, aMp2demuxsecCde; "Mp2DemuxSec::CDemuxSec::CreateSecurityA"...
0x18003b76f  mov     r8d, 0C13h; int
0x18003b775  lea     rcx, [rbp+arg_18]; this
0x18003b779  mov     ebx, 8000FFFFh
0x18003b77e  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003b783  cmp     cs:byte_1800EACCB, 1
0x18003b78a  jb      loc_18003B590
0x18003b790  lea     edx, [r14+26h]
0x18003b794  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b79b  lea     r8, WPP_ea15c8c7cf393e7e63170f2c53fa20e3_Traceguids
0x18003b7a2  mov     r9, rdi
0x18003b7a5  mov     rcx, [rcx+88h]
0x18003b7ac  call    WPP_SF_q
0x18003b7b1  jmp     loc_18003B590
```
