# LsaLookupNames

- ea: `0x18003b350`
- end: `0x18003b4c5`
- name: `LsaLookupNames`
- size: `373`
- prototype: `NTSTATUS __stdcall(LSA_HANDLE PolicyHandle, ULONG Count, PLSA_UNICODE_STRING Names, PLSA_REFERENCED_DOMAIN_LIST *ReferencedDomains, PLSA_TRANSLATED_SID *Sids)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting`

## callees

- `0x18001f9d4`
- `0x18003b350`
- `0x18007205a`

## import_xrefs

- `ntdll!RtlSubAuthorityCountSid` at `0x18003b439`
- `ntdll!RtlSubAuthorityCountSid` at `0x18003b439`
- `ntdll!RtlSubAuthoritySid` at `0x18003b44f`
- `ntdll!RtlSubAuthoritySid` at `0x18003b44f`
- `KERNELBASE!LocalAlloc` at `0x18003b3eb`
- `KERNELBASE!LocalAlloc` at `0x18003b3eb`
- `KERNEL32!LocalFree` at `0x18003b48b`
- `KERNEL32!LocalFree` at `0x18003b49d`
- `KERNEL32!LocalFree` at `0x18003b48b`
- `KERNEL32!LocalFree` at `0x18003b49d`

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
         &v19,
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
0x18003b350  mov     r11, rsp
0x18003b353  push    rbx
0x18003b354  push    rbp
0x18003b355  push    rsi
0x18003b356  push    rdi
0x18003b357  push    r12
0x18003b359  push    r13
0x18003b35b  push    r14
0x18003b35d  push    r15
0x18003b35f  sub     rsp, 68h
0x18003b363  mov     r15, [rsp+0A8h+Sids]
0x18003b36b  xor     r12d, r12d
0x18003b36e  mov     [r11-58h], r12d
0x18003b372  mov     rbx, r9
0x18003b375  mov     [r11-50h], r12
0x18003b379  mov     r14d, edx
0x18003b37c  test    r15, r15
0x18003b37f  jz      loc_18003B4AE
0x18003b385  test    rbx, rbx
0x18003b388  jz      loc_18003B4AE
0x18003b38e  mov     [r11-60h], r12
0x18003b392  lea     rax, [r11-58h]
0x18003b396  mov     [r11-68h], rax
0x18003b39a  lea     rax, [r11-50h]
0x18003b39e  mov     [rsp+0A8h+var_70], 1
0x18003b3a6  mov     [r15], r12
0x18003b3a9  mov     [r9], r12
0x18003b3ac  mov     r9, r8
0x18003b3af  mov     [rsp+0A8h+var_78], 1
0x18003b3b7  mov     r8d, edx
0x18003b3ba  mov     [r11-80h], rax
0x18003b3be  xor     edx, edx
0x18003b3c0  mov     [rsp+0A8h+var_88], rbx
0x18003b3c5  call    LsaICLookupNames_0
0x18003b3ca  mov     rsi, [rsp+0A8h+hMem]
0x18003b3cf  mov     r13d, eax
0x18003b3d2  test    rsi, rsi
0x18003b3d5  jz      loc_18003B4A9
0x18003b3db  lea     ecx, [r14+r14*2]
0x18003b3df  shl     ecx, 2
0x18003b3e2  mov     ebp, ecx
0x18003b3e4  mov     edx, ecx; uBytes
0x18003b3e6  lea     ecx, [r12+40h]; uFlags
0x18003b3eb  call    cs:__imp_LocalAlloc
0x18003b3f2  nop     dword ptr [rax+rax+00h]
0x18003b3f7  mov     rdi, rax
0x18003b3fa  test    rax, rax
0x18003b3fd  jz      short loc_18003B47D
0x18003b3ff  mov     r8d, ebp; Size
0x18003b402  xor     edx, edx; Val
0x18003b404  mov     rcx, rax; void *
0x18003b407  call    memset_0
0x18003b40c  test    r14d, r14d
0x18003b40f  jz      short loc_18003B478
0x18003b411  xor     ebx, ebx
0x18003b413  lea     rbp, [rbx+rbx*2]
0x18003b417  mov     eax, [rsi+rbp*8]
0x18003b41a  lea     rcx, [rbx+rbx*2]
0x18003b41e  mov     [rdi+rcx*4], eax
0x18003b421  cmp     dword ptr [rsi+rbp*8], 3
0x18003b425  jnz     short loc_18003B42C
0x18003b427  or      eax, 0FFFFFFFFh
0x18003b42a  jmp     short loc_18003B461
0x18003b42c  mov     rax, [rsi+rbp*8+8]
0x18003b431  test    rax, rax
0x18003b434  jz      short loc_18003B461
0x18003b436  mov     rcx, rax; Sid
0x18003b439  call    cs:__imp_RtlSubAuthorityCountSid
0x18003b440  nop     dword ptr [rax+rax+00h]
0x18003b445  mov     rcx, [rsi+rbp*8+8]; Sid
0x18003b44a  movzx   edx, byte ptr [rax]
0x18003b44d  dec     edx; SubAuthority
0x18003b44f  call    cs:__imp_RtlSubAuthoritySid
0x18003b456  nop     dword ptr [rax+rax+00h]
0x18003b45b  lea     rcx, [rbx+rbx*2]
0x18003b45f  mov     eax, [rax]
0x18003b461  mov     [rdi+rcx*4+4], eax
0x18003b465  inc     r12d
0x18003b468  mov     eax, [rsi+rbp*8+10h]
0x18003b46c  inc     rbx
0x18003b46f  mov     [rdi+rcx*4+8], eax
0x18003b473  cmp     r12d, r14d
0x18003b476  jb      short loc_18003B413
0x18003b478  mov     [r15], rdi
0x18003b47b  jmp     short loc_18003B49A
0x18003b47d  mov     rcx, [rbx]; hMem
0x18003b480  mov     r13d, 0C000009Ah
0x18003b486  test    rcx, rcx
0x18003b489  jz      short loc_18003B49A
0x18003b48b  call    cs:__imp_LocalFree
0x18003b492  nop     dword ptr [rax+rax+00h]
0x18003b497  mov     [rbx], r12
0x18003b49a  mov     rcx, rsi; hMem
0x18003b49d  call    cs:__imp_LocalFree
0x18003b4a4  nop     dword ptr [rax+rax+00h]
0x18003b4a9  mov     eax, r13d
0x18003b4ac  jmp     short loc_18003B4B3
0x18003b4ae  mov     eax, 0C000000Dh
0x18003b4b3  add     rsp, 68h
0x18003b4b7  pop     r15
0x18003b4b9  pop     r14
0x18003b4bb  pop     r13
0x18003b4bd  pop     r12
0x18003b4bf  pop     rdi
0x18003b4c0  pop     rsi
0x18003b4c1  pop     rbp
0x18003b4c2  pop     rbx
0x18003b4c3  retn
```
