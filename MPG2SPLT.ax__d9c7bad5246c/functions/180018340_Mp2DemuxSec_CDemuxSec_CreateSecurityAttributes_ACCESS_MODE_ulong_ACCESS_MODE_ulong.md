# Mp2DemuxSec::CDemuxSec::CreateSecurityAttributes(_ACCESS_MODE,ulong,_ACCESS_MODE,ulong)

- ea: `0x180018340`
- end: `0x1800184f5`
- name: `?CreateSecurityAttributes@CDemuxSec@Mp2DemuxSec@@IEAAJW4_ACCESS_MODE@@K0K@Z`
- size: `437`
- prototype: `__int64 __fastcall(Mp2DemuxSec::CDemuxSec *__hidden this, enum _ACCESS_MODE, unsigned int, enum _ACCESS_MODE, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800120e0`
- `0x1800155c0`

## callees

- `0x180001048`
- `0x180001054`
- `0x180001e98`
- `0x180018340`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180018485`
- `KERNEL32!GetLastError` at `0x180018485`
- `KERNEL32!LocalAlloc` at `0x180018476`
- `KERNEL32!LocalAlloc` at `0x180018476`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x1800184b2`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x1800184b2`
- `ADVAPI32!SetEntriesInAclW` at `0x180018455`
- `ADVAPI32!SetEntriesInAclW` at `0x180018455`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180018499`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180018499`
- `ADVAPI32!BuildTrusteeWithSidW` at `0x1800183e4`
- `ADVAPI32!BuildTrusteeWithSidW` at `0x18001843f`
- `ADVAPI32!BuildTrusteeWithSidW` at `0x1800183e4`
- `ADVAPI32!BuildTrusteeWithSidW` at `0x18001843f`

## pseudocode

```c
__int64 __fastcall Mp2DemuxSec::CDemuxSec::CreateSecurityAttributes(
        Mp2DemuxSec::CDemuxSec *this,
        unsigned __int64 a2,
        DWORD a3,
        enum _ACCESS_MODE a4,
        DWORD a5)
{
  struct _EXPLICIT_ACCESS_W *v7; // rsi
  unsigned int v8; // ebx
  unsigned int v9; // eax
  __int64 v10; // rbx
  __int64 v11; // rax
  signed int LastError; // eax
  bool v13; // cc
  HLOCAL v14; // rax
  __int64 v15; // rax

  if ( !*((_QWORD *)this + 6) || !*((_QWORD *)this + 8) )
  {
    v7 = 0;
    v8 = -2147418113;
    goto LABEL_16;
  }
  v7 = (struct _EXPLICIT_ACCESS_W *)operator new[](saturated_mul(*((unsigned __int8 *)this + 56) + 1LL, 0x30u));
  if ( v7 )
  {
    memset_0(v7, 0, 48 * (*((unsigned __int8 *)this + 56) + 1LL));
    LOBYTE(v9) = *((_BYTE *)this + 56);
    v10 = 0;
    if ( (_BYTE)v9 )
    {
      do
      {
        v11 = v10;
        v7[v11].grfAccessPermissions = a5;
        *(_QWORD *)&v7[v11].grfAccessMode = 2;
        BuildTrusteeWithSidW(&v7[v10].Trustee, *(PSID *)(*((_QWORD *)this + 6) + 8 * v10));
        v9 = *((unsigned __int8 *)this + 56);
        v10 = (unsigned int)(v10 + 1);
      }
      while ( (unsigned int)v10 < v9 );
    }
    v7[(unsigned __int8)v9].grfAccessPermissions = a3;
    v7[*((unsigned __int8 *)this + 56)].grfAccessMode = SET_ACCESS;
    v7[*((unsigned __int8 *)this + 56)].grfInheritance = 0;
    BuildTrusteeWithSidW(&v7[*((unsigned __int8 *)this + 56)].Trustee, *((PSID *)this + 8));
    LastError = SetEntriesInAclW(*((unsigned __int8 *)this + 56) + 1, v7, 0, (PACL *)this + 9);
    v8 = LastError;
    v13 = LastError <= 0;
    if ( !LastError )
    {
      v14 = LocalAlloc(0x40u, 0x28u);
      *((_QWORD *)this + 1) = v14;
      if ( v14
        && InitializeSecurityDescriptor(v14, 1u)
        && SetSecurityDescriptorDacl(*((PSECURITY_DESCRIPTOR *)this + 1), 1, *((PACL *)this + 9), 0) )
      {
        v15 = *((_QWORD *)this + 1);
        v8 = 0;
        *((_DWORD *)this + 4) = 24;
        *((_QWORD *)this + 3) = v15;
        *((_DWORD *)this + 8) = 0;
        *((_QWORD *)this + 5) = (char *)this + 16;
        goto LABEL_16;
      }
      LastError = GetLastError();
      v8 = LastError;
      v13 = LastError <= 0;
    }
    if ( !v13 )
      v8 = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    v8 = -2147024882;
  }
LABEL_16:
  operator delete(v7, a2);
  return v8;
}

```

## disassembly

```asm
0x180018340  push    rbx
0x180018342  push    rbp
0x180018343  push    rsi
0x180018344  push    rdi
0x180018345  push    r14
0x180018347  sub     rsp, 20h
0x18001834b  cmp     qword ptr [rcx+30h], 0
0x180018350  mov     r14d, r8d
0x180018353  mov     rdi, rcx
0x180018356  jz      loc_1800184D9
0x18001835c  cmp     qword ptr [rcx+40h], 0
0x180018361  jz      loc_1800184D9
0x180018367  movzx   edx, byte ptr [rcx+38h]
0x18001836b  mov     eax, 30h ; '0'
0x180018370  inc     rdx
0x180018373  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001837a  mul     rdx
0x18001837d  cmovb   rax, rcx
0x180018381  mov     rcx, rax; unsigned __int64
0x180018384  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180018389  mov     rsi, rax
0x18001838c  test    rax, rax
0x18001838f  jnz     short loc_18001839B
0x180018391  mov     ebx, 8007000Eh
0x180018396  jmp     loc_1800184E0
0x18001839b  movzx   eax, byte ptr [rdi+38h]
0x18001839f  xor     edx, edx; Val
0x1800183a1  inc     rax
0x1800183a4  mov     rcx, rsi; void *
0x1800183a7  lea     r8, [rax+rax*2]
0x1800183ab  shl     r8, 4; Size
0x1800183af  call    memset_0
0x1800183b4  mov     al, [rdi+38h]
0x1800183b7  xor     ebx, ebx
0x1800183b9  test    al, al
0x1800183bb  jz      short loc_1800183F4
0x1800183bd  mov     ebp, [rsp+48h+arg_20]
0x1800183c1  lea     rax, [rbx+rbx*2]
0x1800183c5  shl     rax, 4
0x1800183c9  lea     rcx, [rsi+10h]
0x1800183cd  add     rcx, rax; pTrustee
0x1800183d0  mov     [rax+rsi], ebp
0x1800183d3  mov     qword ptr [rax+rsi+4], 2
0x1800183dc  mov     rdx, [rdi+30h]
0x1800183e0  mov     rdx, [rdx+rbx*8]; pSid
0x1800183e4  call    cs:__imp_BuildTrusteeWithSidW
0x1800183ea  movzx   eax, byte ptr [rdi+38h]
0x1800183ee  inc     ebx
0x1800183f0  cmp     ebx, eax
0x1800183f2  jb      short loc_1800183C1
0x1800183f4  movzx   eax, al
0x1800183f7  lea     rcx, [rax+rax*2]
0x1800183fb  add     rcx, rcx
0x1800183fe  mov     [rsi+rcx*8], r14d
0x180018402  movzx   eax, byte ptr [rdi+38h]
0x180018406  lea     rcx, [rax+rax*2]
0x18001840a  add     rcx, rcx
0x18001840d  mov     dword ptr [rsi+rcx*8+4], 2
0x180018415  movzx   eax, byte ptr [rdi+38h]
0x180018419  lea     rcx, [rax+rax*2]
0x18001841d  add     rcx, rcx
0x180018420  mov     dword ptr [rsi+rcx*8+8], 0
0x180018428  movzx   eax, byte ptr [rdi+38h]
0x18001842c  mov     rdx, [rdi+40h]; pSid
0x180018430  lea     rcx, [rax+rax*2]
0x180018434  shl     rcx, 4
0x180018438  add     rcx, 10h
0x18001843c  add     rcx, rsi; pTrustee
0x18001843f  call    cs:__imp_BuildTrusteeWithSidW
0x180018445  movzx   ecx, byte ptr [rdi+38h]
0x180018449  lea     r9, [rdi+48h]; NewAcl
0x18001844d  inc     ecx; cCountOfExplicitEntries
0x18001844f  xor     r8d, r8d; OldAcl
0x180018452  mov     rdx, rsi; pListOfExplicitEntries
0x180018455  call    cs:__imp_SetEntriesInAclW
0x18001845b  mov     ebx, eax
0x18001845d  test    eax, eax
0x18001845f  jz      short loc_18001846E
0x180018461  jle     short loc_1800184E0
0x180018463  movzx   ebx, ax
0x180018466  or      ebx, 80070000h
0x18001846c  jmp     short loc_1800184E0
0x18001846e  mov     edx, 28h ; '('; uBytes
0x180018473  lea     ecx, [rdx+18h]; uFlags
0x180018476  call    cs:__imp_LocalAlloc
0x18001847c  mov     [rdi+8], rax
0x180018480  test    rax, rax
0x180018483  jnz     short loc_180018491
0x180018485  call    cs:__imp_GetLastError
0x18001848b  mov     ebx, eax
0x18001848d  test    eax, eax
0x18001848f  jmp     short loc_180018461
0x180018491  mov     edx, 1; dwRevision
0x180018496  mov     rcx, rax; pSecurityDescriptor
0x180018499  call    cs:__imp_InitializeSecurityDescriptor
0x18001849f  test    eax, eax
0x1800184a1  jz      short loc_180018485
0x1800184a3  mov     r8, [rdi+48h]; pDacl
0x1800184a7  xor     r9d, r9d; bDaclDefaulted
0x1800184aa  mov     rcx, [rdi+8]; pSecurityDescriptor
0x1800184ae  lea     edx, [r9+1]; bDaclPresent
0x1800184b2  call    cs:__imp_SetSecurityDescriptorDacl
0x1800184b8  test    eax, eax
0x1800184ba  jz      short loc_180018485
0x1800184bc  mov     rax, [rdi+8]
0x1800184c0  lea     rcx, [rdi+10h]
0x1800184c4  xor     ebx, ebx
0x1800184c6  mov     dword ptr [rcx], 18h
0x1800184cc  mov     [rdi+18h], rax
0x1800184d0  mov     [rdi+20h], ebx
0x1800184d3  mov     [rdi+28h], rcx
0x1800184d7  jmp     short loc_1800184E0
0x1800184d9  xor     esi, esi
0x1800184db  mov     ebx, 8000FFFFh
0x1800184e0  mov     rcx, rsi; void *
0x1800184e3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800184e8  mov     eax, ebx
0x1800184ea  add     rsp, 20h
0x1800184ee  pop     r14
0x1800184f0  pop     rdi
0x1800184f1  pop     rsi
0x1800184f2  pop     rbp
0x1800184f3  pop     rbx
0x1800184f4  retn
```
