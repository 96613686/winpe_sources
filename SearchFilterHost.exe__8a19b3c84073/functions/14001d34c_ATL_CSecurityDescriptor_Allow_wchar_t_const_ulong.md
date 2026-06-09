# ATL::CSecurityDescriptor::Allow(wchar_t const *,ulong)

- ea: `0x14001d34c`
- end: `0x14001d3cc`
- name: `?Allow@CSecurityDescriptor@ATL@@QEAAJPEB_WK@Z`
- size: `128`
- prototype: `__int64 __fastcall(struct _ACL **this, const wchar_t *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002753c`

## callees

- `0x14001ca4c`
- `0x14001d34c`
- `0x14001d4e8`
- `0x140020cbc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001d3b4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001d3b4`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x14001d39e`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x14001d39e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CSecurityDescriptor::Allow(struct _ACL **this, const wchar_t *a2)
{
  int PrincipalSID; // ebx
  void *Block; // [rsp+48h] [rbp+20h] BYREF

  Block = 0;
  PrincipalSID = ATL::CSecurityDescriptor::GetPrincipalSID(a2, &Block);
  if ( PrincipalSID >= 0 )
  {
    PrincipalSID = ATL::CSecurityDescriptor::AddAccessAllowedACEToACL(this + 3, Block);
    if ( PrincipalSID >= 0 && !SetSecurityDescriptorDacl(*this, 1, this[3], 0) )
      PrincipalSID = ResultFromLastError();
    free(Block);
  }
  return (unsigned int)PrincipalSID;
}

```

## disassembly

```asm
0x14001d34c  mov     r11, rsp
0x14001d34f  mov     [r11+8], rbx
0x14001d353  mov     [r11+10h], rsi
0x14001d357  push    rdi
0x14001d358  sub     rsp, 20h
0x14001d35c  mov     rax, rdx
0x14001d35f  mov     qword ptr [r11+20h], 0
0x14001d367  mov     rsi, rcx
0x14001d36a  lea     rdx, [r11+20h]; void **
0x14001d36e  mov     rcx, rax; lpAccountName
0x14001d371  call    ?GetPrincipalSID@CSecurityDescriptor@ATL@@SAJPEB_WPEAPEAX@Z; ATL::CSecurityDescriptor::GetPrincipalSID(wchar_t const *,void * *)
0x14001d376  mov     ebx, eax
0x14001d378  test    eax, eax
0x14001d37a  js      short loc_14001D3BA
0x14001d37c  mov     rdx, [rsp+28h+Block]; void *
0x14001d381  lea     rcx, [rsi+18h]; struct _ACL **
0x14001d385  call    ?AddAccessAllowedACEToACL@CSecurityDescriptor@ATL@@SAJPEAPEAU_ACL@@PEAXK@Z; ATL::CSecurityDescriptor::AddAccessAllowedACEToACL(_ACL * *,void *,ulong)
0x14001d38a  mov     ebx, eax
0x14001d38c  test    eax, eax
0x14001d38e  js      short loc_14001D3AF
0x14001d390  mov     r8, [rsi+18h]; pDacl
0x14001d394  xor     r9d, r9d; bDaclDefaulted
0x14001d397  mov     rcx, [rsi]; pSecurityDescriptor
0x14001d39a  lea     edx, [r9+1]; bDaclPresent
0x14001d39e  call    cs:__imp_SetSecurityDescriptorDacl
0x14001d3a4  test    eax, eax
0x14001d3a6  jnz     short loc_14001D3AF
0x14001d3a8  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x14001d3ad  mov     ebx, eax
0x14001d3af  mov     rcx, [rsp+28h+Block]; Block
0x14001d3b4  call    cs:__imp_free
0x14001d3ba  mov     rsi, [rsp+28h+arg_8]
0x14001d3bf  mov     eax, ebx
0x14001d3c1  mov     rbx, [rsp+28h+arg_0]
0x14001d3c6  add     rsp, 20h
0x14001d3ca  pop     rdi
0x14001d3cb  retn
```
