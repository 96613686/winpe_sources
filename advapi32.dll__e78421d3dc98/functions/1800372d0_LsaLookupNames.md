# LsaLookupNames

- ea: `0x1800372d0`
- end: `0x180037426`
- name: `LsaLookupNames`
- size: `342`
- prototype: `NTSTATUS __stdcall(LSA_HANDLE PolicyHandle, ULONG Count, PLSA_UNICODE_STRING Names, PLSA_REFERENCED_DOMAIN_LIST *ReferencedDomains, PLSA_TRANSLATED_SID *Sids)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting`

## callees

- `0x1800208f0`
- `0x1800372d0`
- `0x18006505a`

## import_xrefs

- `ntdll!RtlSubAuthorityCountSid` at `0x1800373b3`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800373b3`
- `ntdll!RtlSubAuthoritySid` at `0x1800373c3`
- `ntdll!RtlSubAuthoritySid` at `0x1800373c3`
- `KERNELBASE!LocalAlloc` at `0x18003736b`
- `KERNELBASE!LocalAlloc` at `0x18003736b`
- `KERNEL32!LocalFree` at `0x1800373f9`
- `KERNEL32!LocalFree` at `0x180037405`
- `KERNEL32!LocalFree` at `0x1800373f9`
- `KERNEL32!LocalFree` at `0x180037405`

## pseudocode

```c
NTSTATUS __stdcall LsaLookupNames(
        LSA_HANDLE PolicyHandle,
        ULONG Count,
        PLSA_UNICODE_STRING Names,
        PLSA_REFERENCED_DOMAIN_LIST *ReferencedDomains,
        PLSA_TRANSLATED_SID *Sids)
{
  ULONG v5; // r12d
  NTSTATUS v8; // eax
  _DWORD *v9; // rsi
  NTSTATUS v10; // r13d
  struct _LSA_TRANSLATED_SID *v11; // rax
  struct _LSA_TRANSLATED_SID *v12; // rdi
  __int64 v13; // rbx
  __int64 v14; // rcx
  PULONG v15; // rax
  PUCHAR v16; // rax
  LONG v17; // eax
  int v19; // [rsp+50h] [rbp-58h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-50h] BYREF

  v5 = 0;
  v19 = 0;
  hMem = 0;
  if ( !Sids || !ReferencedDomains )
    return -1073741811;
  *Sids = 0;
  *ReferencedDomains = 0;
  v8 = LsaICLookupNames_0(
         (__int64)PolicyHandle,
         0,
         Count,
         (__int64)Names,
         (HLOCAL *)ReferencedDomains,
         &hMem,
         1,
         1,
         (__int64)&v19,
         0);
  v9 = hMem;
  v10 = v8;
  if ( hMem )
  {
    v11 = (struct _LSA_TRANSLATED_SID *)LocalAlloc(0x40u, 12 * Count);
    v12 = v11;
    if ( v11 )
    {
      memset_0(v11, 0, 12 * Count);
      if ( Count )
      {
        v13 = 0;
        do
        {
          v14 = v13;
          v12[v13].Use = v9[6 * v13];
          if ( v9[6 * v13] == 3 )
          {
            LODWORD(v15) = -1;
          }
          else
          {
            v15 = *(PULONG *)&v9[6 * v13 + 2];
            if ( v15 )
            {
              v16 = RtlSubAuthorityCountSid(*(PSID *)&v9[6 * v13 + 2]);
              v15 = RtlSubAuthoritySid(*(PSID *)&v9[6 * v13 + 2], (unsigned int)*v16 - 1);
              v14 = v13;
              LODWORD(v15) = *v15;
            }
          }
          v12[v14].RelativeId = (unsigned int)v15;
          ++v5;
          v17 = v9[6 * v13++ + 4];
          v12[v14].DomainIndex = v17;
        }
        while ( v5 < Count );
      }
      *Sids = v12;
    }
    else
    {
      v10 = -1073741670;
      if ( *ReferencedDomains )
      {
        LocalFree(*ReferencedDomains);
        *ReferencedDomains = 0;
      }
    }
    LocalFree(v9);
  }
  return v10;
}

```

## disassembly

```asm
0x1800372d0  mov     r11, rsp
0x1800372d3  push    rbx
0x1800372d4  push    rbp
0x1800372d5  push    rsi
0x1800372d6  push    rdi
0x1800372d7  push    r12
0x1800372d9  push    r13
0x1800372db  push    r14
0x1800372dd  push    r15
0x1800372df  sub     rsp, 68h
0x1800372e3  mov     r15, [rsp+0A8h+Sids]
0x1800372eb  xor     r12d, r12d
0x1800372ee  mov     [r11-58h], r12d
0x1800372f2  mov     rbx, r9
0x1800372f5  mov     [r11-50h], r12
0x1800372f9  mov     r14d, edx
0x1800372fc  test    r15, r15
0x1800372ff  jz      loc_180037410
0x180037305  test    rbx, rbx
0x180037308  jz      loc_180037410
0x18003730e  mov     [r11-60h], r12
0x180037312  lea     rax, [r11-58h]
0x180037316  mov     [r11-68h], rax
0x18003731a  lea     rax, [r11-50h]
0x18003731e  mov     [rsp+0A8h+var_70], 1
0x180037326  mov     [r15], r12
0x180037329  mov     [r9], r12
0x18003732c  mov     r9, r8
0x18003732f  mov     [rsp+0A8h+var_78], 1
0x180037337  mov     r8d, edx
0x18003733a  mov     [r11-80h], rax
0x18003733e  xor     edx, edx
0x180037340  mov     [rsp+0A8h+var_88], rbx
0x180037345  call    LsaICLookupNames_0
0x18003734a  mov     rsi, [rsp+0A8h+hMem]
0x18003734f  mov     r13d, eax
0x180037352  test    rsi, rsi
0x180037355  jz      loc_18003740B
0x18003735b  lea     ecx, [r14+r14*2]
0x18003735f  shl     ecx, 2
0x180037362  mov     ebp, ecx
0x180037364  mov     edx, ecx; uBytes
0x180037366  lea     ecx, [r12+40h]; uFlags
0x18003736b  call    cs:__imp_LocalAlloc
0x180037371  mov     rdi, rax
0x180037374  test    rax, rax
0x180037377  jz      short loc_1800373EB
0x180037379  mov     r8d, ebp; Size
0x18003737c  xor     edx, edx; Val
0x18003737e  mov     rcx, rax; void *
0x180037381  call    memset_0
0x180037386  test    r14d, r14d
0x180037389  jz      short loc_1800373E6
0x18003738b  xor     ebx, ebx
0x18003738d  lea     rbp, [rbx+rbx*2]
0x180037391  mov     eax, [rsi+rbp*8]
0x180037394  lea     rcx, [rbx+rbx*2]
0x180037398  mov     [rdi+rcx*4], eax
0x18003739b  cmp     dword ptr [rsi+rbp*8], 3
0x18003739f  jnz     short loc_1800373A6
0x1800373a1  or      eax, 0FFFFFFFFh
0x1800373a4  jmp     short loc_1800373CF
0x1800373a6  mov     rax, [rsi+rbp*8+8]
0x1800373ab  test    rax, rax
0x1800373ae  jz      short loc_1800373CF
0x1800373b0  mov     rcx, rax; Sid
0x1800373b3  call    cs:__imp_RtlSubAuthorityCountSid
0x1800373b9  mov     rcx, [rsi+rbp*8+8]; Sid
0x1800373be  movzx   edx, byte ptr [rax]
0x1800373c1  dec     edx; SubAuthority
0x1800373c3  call    cs:__imp_RtlSubAuthoritySid
0x1800373c9  lea     rcx, [rbx+rbx*2]
0x1800373cd  mov     eax, [rax]
0x1800373cf  mov     [rdi+rcx*4+4], eax
0x1800373d3  inc     r12d
0x1800373d6  mov     eax, [rsi+rbp*8+10h]
0x1800373da  inc     rbx
0x1800373dd  mov     [rdi+rcx*4+8], eax
0x1800373e1  cmp     r12d, r14d
0x1800373e4  jb      short loc_18003738D
0x1800373e6  mov     [r15], rdi
0x1800373e9  jmp     short loc_180037402
0x1800373eb  mov     rcx, [rbx]; hMem
0x1800373ee  mov     r13d, 0C000009Ah
0x1800373f4  test    rcx, rcx
0x1800373f7  jz      short loc_180037402
0x1800373f9  call    cs:__imp_LocalFree
0x1800373ff  mov     [rbx], r12
0x180037402  mov     rcx, rsi; hMem
0x180037405  call    cs:__imp_LocalFree
0x18003740b  mov     eax, r13d
0x18003740e  jmp     short loc_180037415
0x180037410  mov     eax, 0C000000Dh
0x180037415  add     rsp, 68h
0x180037419  pop     r15
0x18003741b  pop     r14
0x18003741d  pop     r13
0x18003741f  pop     r12
0x180037421  pop     rdi
0x180037422  pop     rsi
0x180037423  pop     rbp
0x180037424  pop     rbx
0x180037425  retn
```
