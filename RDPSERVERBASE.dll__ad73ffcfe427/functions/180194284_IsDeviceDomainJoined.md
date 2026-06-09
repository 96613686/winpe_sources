# IsDeviceDomainJoined

- ea: `0x180194284`
- end: `0x180194314`
- name: `IsDeviceDomainJoined`
- size: `144`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180193bb4`

## callees

- `0x180194284`

## import_xrefs

- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x1801942d0`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x1801942d0`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1801942b9`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1801942b9`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1801942f6`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1801942f6`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180194301`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180194301`

## pseudocode

```c
__int64 IsDeviceDomainJoined()
{
  unsigned int v0; // ebx
  struct _LSA_OBJECT_ATTRIBUTES v2; // [rsp+20h] [rbp-38h] BYREF
  LSA_HANDLE PolicyHandle; // [rsp+60h] [rbp+8h] BYREF
  PVOID Buffer; // [rsp+68h] [rbp+10h] BYREF

  PolicyHandle = 0;
  Buffer = 0;
  v0 = 0;
  memset(&v2, 0, sizeof(v2));
  if ( LsaOpenPolicy(0, &v2, 1u, &PolicyHandle) >= 0 )
  {
    if ( LsaQueryInformationPolicy(PolicyHandle, PolicyDnsDomainInformation, &Buffer) >= 0 )
    {
      if ( *((_WORD *)Buffer + 8) || *((_WORD *)Buffer + 16) || *((_QWORD *)Buffer + 8) )
        v0 = 1;
      LsaFreeMemory(Buffer);
    }
    LsaClose(PolicyHandle);
  }
  return v0;
}

```

## disassembly

```asm
0x180194284  mov     rax, rsp
0x180194287  mov     [rax+18h], rbx
0x18019428b  push    rdi
0x18019428c  sub     rsp, 50h
0x180194290  xor     edi, edi
0x180194292  lea     r9, [rax+8]; PolicyHandle
0x180194296  xorps   xmm0, xmm0
0x180194299  mov     [rax+8], rdi
0x18019429d  lea     rdx, [rax-38h]; ObjectAttributes
0x1801942a1  mov     [rax+10h], rdi
0x1801942a5  xor     ecx, ecx; SystemName
0x1801942a7  mov     ebx, edi
0x1801942a9  lea     r8d, [rdi+1]; DesiredAccess
0x1801942ad  movups  xmmword ptr [rax-38h], xmm0
0x1801942b1  movups  xmmword ptr [rax-28h], xmm0
0x1801942b5  movups  xmmword ptr [rax-18h], xmm0
0x1801942b9  call    cs:__imp_LsaOpenPolicy
0x1801942bf  test    eax, eax
0x1801942c1  js      short loc_180194307
0x1801942c3  mov     rcx, [rsp+58h+PolicyHandle]; PolicyHandle
0x1801942c8  lea     r8, [rsp+58h+Buffer]; Buffer
0x1801942cd  lea     edx, [rdi+0Ch]; InformationClass
0x1801942d0  call    cs:__imp_LsaQueryInformationPolicy
0x1801942d6  test    eax, eax
0x1801942d8  js      short loc_1801942FC
0x1801942da  mov     rcx, [rsp+58h+Buffer]; Buffer
0x1801942df  cmp     [rcx+10h], di
0x1801942e3  jnz     short loc_1801942F1
0x1801942e5  cmp     [rcx+20h], di
0x1801942e9  jnz     short loc_1801942F1
0x1801942eb  cmp     [rcx+40h], rdi
0x1801942ef  jz      short loc_1801942F6
0x1801942f1  mov     ebx, 1
0x1801942f6  call    cs:__imp_LsaFreeMemory
0x1801942fc  mov     rcx, [rsp+58h+PolicyHandle]; ObjectHandle
0x180194301  call    cs:__imp_LsaClose
0x180194307  mov     eax, ebx
0x180194309  mov     rbx, [rsp+58h+arg_10]
0x18019430e  add     rsp, 50h
0x180194312  pop     rdi
0x180194313  retn
```
