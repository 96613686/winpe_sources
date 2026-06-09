# SipcPrivateNamespace::GetSecurityDescriptor(void * *)

- ea: `0x18002958c`
- end: `0x1800297ef`
- name: `?GetSecurityDescriptor@SipcPrivateNamespace@@AEAAJPEAPEAX@Z`
- size: `611`
- prototype: `__int64 __fastcall(SipcPrivateNamespace *__hidden this, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180026a4c`

## callees

- `0x18000c11c`
- `0x18002958c`

## import_xrefs

- `ntdll!swprintf_s` at `0x1800296e9`
- `ntdll!swprintf_s` at `0x1800296e9`
- `ntdll!RtlAllocateHeap` at `0x180029683`
- `ntdll!RtlAllocateHeap` at `0x180029683`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800295c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029758`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800295c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029758`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800295f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002960a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800296a0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800296b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002970a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029723`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029783`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800297bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800297d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800295f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002960a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800296a0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800296b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002970a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029723`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029783`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800297bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800297d5`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180029748`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180029748`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800295b6`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180029628`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800295b6`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180029628`

## pseudocode

```c
__int64 __fastcall SipcPrivateNamespace::GetSecurityDescriptor(SipcPrivateNamespace *this, void **a2)
{
  signed int LastError; // eax
  unsigned int v5; // ebx
  __int64 v7; // rax
  __int64 v8; // rcx
  unsigned __int64 v9; // rbx
  SIZE_T v10; // rax
  PVOID ProcessHeap; // rcx
  PVOID Heap; // rdi
  const struct std::nothrow_t *v13; // rdx
  const struct std::nothrow_t *v14; // rdx
  signed int v15; // eax
  const struct std::nothrow_t *v16; // rdx
  HLOCAL hMem; // [rsp+60h] [rbp+30h] BYREF
  LPWSTR StringSid; // [rsp+68h] [rbp+38h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+70h] [rbp+40h] BYREF

  *a2 = 0;
  StringSid = 0;
  hMem = 0;
  if ( !ConvertSidToStringSidW((char *)this + 100, &StringSid)
    || !ConvertSidToStringSidW((char *)this + 168, (LPWSTR *)&hMem) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v5 = -2147418113;
    if ( LastError < 0 )
      v5 = LastError;
    goto LABEL_6;
  }
  v7 = -1;
  do
    ++v7;
  while ( StringSid[v7] );
  v8 = -1;
  do
    ++v8;
  while ( *((_WORD *)hMem + v8) );
  v9 = v8 + v7 + 54;
  v10 = 2 * v9;
  ProcessHeap = NtCurrentPeb()->ProcessHeap;
  if ( !is_mul_ok(v9, 2u) )
    v10 = -1;
  Heap = RtlAllocateHeap(ProcessHeap, 0, v10);
  if ( !Heap )
  {
    if ( hMem )
    {
      LocalFree(hMem);
      hMem = 0;
    }
    if ( StringSid )
      LocalFree(StringSid);
    return 2147942414LL;
  }
  if ( swprintf_s((wchar_t *const)Heap, v9, L"S:(ML;;NW;;;LW)D:(A;;GA;;;WD)(A;;GA;;;%s)(A;;GA;;;%s)", StringSid, hMem) <= 0 )
  {
    operator delete(Heap, v13);
    if ( hMem )
    {
      LocalFree(hMem);
      hMem = 0;
    }
    if ( StringSid )
      LocalFree(StringSid);
    return 2147549183LL;
  }
  SecurityDescriptor = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW((LPCWSTR)Heap, 1u, &SecurityDescriptor, 0) )
  {
    v15 = GetLastError();
    if ( v15 > 0 )
      v15 = (unsigned __int16)v15 | 0x80070000;
    v5 = -2147418113;
    if ( v15 < 0 )
      v5 = v15;
    if ( SecurityDescriptor )
    {
      LocalFree(SecurityDescriptor);
      SecurityDescriptor = 0;
    }
    operator delete(Heap, v16);
LABEL_6:
    if ( hMem )
    {
      LocalFree(hMem);
      hMem = 0;
    }
    if ( StringSid )
      LocalFree(StringSid);
    return v5;
  }
  *a2 = SecurityDescriptor;
  SecurityDescriptor = 0;
  operator delete(Heap, v14);
  if ( hMem )
  {
    LocalFree(hMem);
    hMem = 0;
  }
  if ( StringSid )
    LocalFree(StringSid);
  return 0;
}

```

## disassembly

```asm
0x18002958c  push    rbp
0x18002958e  push    rbx
0x18002958f  push    rsi
0x180029590  push    rdi
0x180029591  push    r14
0x180029593  mov     rbp, rsp
0x180029596  sub     rsp, 30h
0x18002959a  xor     r14d, r14d
0x18002959d  mov     rsi, rdx
0x1800295a0  mov     [rdx], r14
0x1800295a3  mov     rbx, rcx
0x1800295a6  lea     rdx, [rbp+StringSid]; StringSid
0x1800295aa  mov     [rbp+StringSid], r14
0x1800295ae  add     rcx, 64h ; 'd'; Sid
0x1800295b2  mov     [rbp+hMem], r14
0x1800295b6  call    cs:__imp_ConvertSidToStringSidW
0x1800295bd  nop     dword ptr [rax+rax+00h]
0x1800295c2  test    eax, eax
0x1800295c4  jnz     short loc_18002961D
0x1800295c6  call    cs:__imp_GetLastError
0x1800295cd  nop     dword ptr [rax+rax+00h]
0x1800295d2  test    eax, eax
0x1800295d4  jle     short loc_1800295DE
0x1800295d6  movzx   eax, ax
0x1800295d9  or      eax, 80070000h
0x1800295de  test    eax, eax
0x1800295e0  mov     ebx, 8000FFFFh
0x1800295e5  cmovs   ebx, eax
0x1800295e8  mov     rcx, [rbp+hMem]; hMem
0x1800295ec  test    rcx, rcx
0x1800295ef  jz      short loc_180029601
0x1800295f1  call    cs:__imp_LocalFree
0x1800295f8  nop     dword ptr [rax+rax+00h]
0x1800295fd  mov     [rbp+hMem], r14
0x180029601  mov     rcx, [rbp+StringSid]; hMem
0x180029605  test    rcx, rcx
0x180029608  jz      short loc_180029616
0x18002960a  call    cs:__imp_LocalFree
0x180029611  nop     dword ptr [rax+rax+00h]
0x180029616  mov     eax, ebx
0x180029618  jmp     loc_1800297E3
0x18002961d  lea     rcx, [rbx+0A8h]; Sid
0x180029624  lea     rdx, [rbp+hMem]; StringSid
0x180029628  call    cs:__imp_ConvertSidToStringSidW
0x18002962f  nop     dword ptr [rax+rax+00h]
0x180029634  test    eax, eax
0x180029636  jz      short loc_1800295C6
0x180029638  mov     rcx, [rbp+StringSid]
0x18002963c  or      r8, 0FFFFFFFFFFFFFFFFh
0x180029640  mov     rax, r8
0x180029643  inc     rax
0x180029646  cmp     [rcx+rax*2], r14w
0x18002964b  jnz     short loc_180029643
0x18002964d  mov     rdx, [rbp+hMem]
0x180029651  mov     rcx, r8
0x180029654  inc     rcx
0x180029657  cmp     [rdx+rcx*2], r14w
0x18002965c  jnz     short loc_180029654
0x18002965e  lea     rbx, [rax+36h]
0x180029662  mov     eax, 2
0x180029667  add     rbx, rcx
0x18002966a  mov     rcx, gs:60h
0x180029673  mul     rbx
0x180029676  mov     rcx, [rcx+30h]; HeapHandle
0x18002967a  cmovb   rax, r8
0x18002967e  xor     edx, edx; Flags
0x180029680  mov     r8, rax; Size
0x180029683  call    cs:__imp_RtlAllocateHeap
0x18002968a  nop     dword ptr [rax+rax+00h]
0x18002968f  mov     rdi, rax
0x180029692  test    rax, rax
0x180029695  jnz     short loc_1800296CF
0x180029697  mov     rcx, [rbp+hMem]; hMem
0x18002969b  test    rcx, rcx
0x18002969e  jz      short loc_1800296B0
0x1800296a0  call    cs:__imp_LocalFree
0x1800296a7  nop     dword ptr [rax+rax+00h]
0x1800296ac  mov     [rbp+hMem], r14
0x1800296b0  mov     rcx, [rbp+StringSid]; hMem
0x1800296b4  test    rcx, rcx
0x1800296b7  jz      short loc_1800296C5
0x1800296b9  call    cs:__imp_LocalFree
0x1800296c0  nop     dword ptr [rax+rax+00h]
0x1800296c5  mov     eax, 8007000Eh
0x1800296ca  jmp     loc_1800297E3
0x1800296cf  mov     rax, [rbp+hMem]
0x1800296d3  lea     r8, aSMlNwLwDAGaWdA; "S:(ML;;NW;;;LW)D:(A;;GA;;;WD)(A;;GA;;;%"...
0x1800296da  mov     r9, [rbp+StringSid]
0x1800296de  mov     rdx, rbx; BufferCount
0x1800296e1  mov     rcx, rdi; Buffer
0x1800296e4  mov     [rsp+30h+var_10], rax
0x1800296e9  call    cs:__imp_swprintf_s
0x1800296f0  nop     dword ptr [rax+rax+00h]
0x1800296f5  mov     rcx, rdi; P
0x1800296f8  test    eax, eax
0x1800296fa  jg      short loc_180029739
0x1800296fc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180029701  mov     rcx, [rbp+hMem]; hMem
0x180029705  test    rcx, rcx
0x180029708  jz      short loc_18002971A
0x18002970a  call    cs:__imp_LocalFree
0x180029711  nop     dword ptr [rax+rax+00h]
0x180029716  mov     [rbp+hMem], r14
0x18002971a  mov     rcx, [rbp+StringSid]; hMem
0x18002971e  test    rcx, rcx
0x180029721  jz      short loc_18002972F
0x180029723  call    cs:__imp_LocalFree
0x18002972a  nop     dword ptr [rax+rax+00h]
0x18002972f  mov     eax, 8000FFFFh
0x180029734  jmp     loc_1800297E3
0x180029739  xor     r9d, r9d; SecurityDescriptorSize
0x18002973c  mov     [rbp+SecurityDescriptor], r14
0x180029740  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180029744  lea     edx, [r9+1]; StringSDRevision
0x180029748  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18002974f  nop     dword ptr [rax+rax+00h]
0x180029754  test    eax, eax
0x180029756  jnz     short loc_1800297A0
0x180029758  call    cs:__imp_GetLastError
0x18002975f  nop     dword ptr [rax+rax+00h]
0x180029764  test    eax, eax
0x180029766  jle     short loc_180029770
0x180029768  movzx   eax, ax
0x18002976b  or      eax, 80070000h
0x180029770  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x180029774  test    eax, eax
0x180029776  mov     ebx, 8000FFFFh
0x18002977b  cmovs   ebx, eax
0x18002977e  test    rcx, rcx
0x180029781  jz      short loc_180029793
0x180029783  call    cs:__imp_LocalFree
0x18002978a  nop     dword ptr [rax+rax+00h]
0x18002978f  mov     [rbp+SecurityDescriptor], r14
0x180029793  mov     rcx, rdi; P
0x180029796  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002979b  jmp     loc_1800295E8
0x1800297a0  mov     rax, [rbp+SecurityDescriptor]
0x1800297a4  mov     rcx, rdi; P
0x1800297a7  mov     [rsi], rax
0x1800297aa  mov     [rbp+SecurityDescriptor], r14
0x1800297ae  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800297b3  mov     rcx, [rbp+hMem]; hMem
0x1800297b7  test    rcx, rcx
0x1800297ba  jz      short loc_1800297CC
0x1800297bc  call    cs:__imp_LocalFree
0x1800297c3  nop     dword ptr [rax+rax+00h]
0x1800297c8  mov     [rbp+hMem], r14
0x1800297cc  mov     rcx, [rbp+StringSid]; hMem
0x1800297d0  test    rcx, rcx
0x1800297d3  jz      short loc_1800297E1
0x1800297d5  call    cs:__imp_LocalFree
0x1800297dc  nop     dword ptr [rax+rax+00h]
0x1800297e1  xor     eax, eax
0x1800297e3  add     rsp, 30h
0x1800297e7  pop     r14
0x1800297e9  pop     rdi
0x1800297ea  pop     rsi
0x1800297eb  pop     rbx
0x1800297ec  pop     rbp
0x1800297ed  retn
```
