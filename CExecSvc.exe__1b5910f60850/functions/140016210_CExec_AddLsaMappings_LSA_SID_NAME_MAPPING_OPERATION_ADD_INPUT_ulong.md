# CExec::AddLsaMappings(_LSA_SID_NAME_MAPPING_OPERATION_ADD_INPUT *,ulong)

- ea: `0x140016210`
- end: `0x1400162f4`
- name: `?AddLsaMappings@CExec@@YAXPEAU_LSA_SID_NAME_MAPPING_OPERATION_ADD_INPUT@@K@Z`
- size: `228`
- prototype: `void __fastcall(CExec *this, struct _LSA_SID_NAME_MAPPING_OPERATION_ADD_INPUT *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1400183f8`

## callees

- `0x140002310`
- `0x140014f3c`
- `0x140016210`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001628e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400162b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001628e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400162b8`
- `api-ms-win-security-lsalookup-l2-1-1!LsaManageSidNameMapping` at `0x14001626d`
- `api-ms-win-security-lsalookup-l2-1-1!LsaManageSidNameMapping` at `0x14001626d`

## string_xrefs

- `0x1400162e2`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`

## pseudocode

```c
void __fastcall CExec::AddLsaMappings(CExec *this, struct _LSA_SID_NAME_MAPPING_OPERATION_ADD_INPUT *a2)
{
  int v2; // ebx
  HLOCAL v3; // rcx
  HLOCAL v4; // rcx
  void *v5; // [rsp+28h] [rbp-58h] BYREF
  char v6; // [rsp+30h] [rbp-50h]
  _QWORD v7[2]; // [rsp+38h] [rbp-48h] BYREF
  __int128 v8; // [rsp+48h] [rbp-38h]
  __int128 v9; // [rsp+58h] [rbp-28h]
  HLOCAL hMem; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  v8 = 0;
  v9 = 0;
  v7[0] = (unsigned int)a2;
  v7[1] = this;
  hMem = 0;
  v5 = 0;
  v6 = 1;
  v2 = LsaManageSidNameMapping(2, v7, &v5);
  if ( v6 )
  {
    v3 = hMem;
    hMem = v5;
    if ( v3 )
      LocalFree(v3);
  }
  v4 = hMem;
  if ( v2 < 0 && (!hMem || (unsigned int)(*(_DWORD *)hMem - 2) > 1) )
    wil::details::in1diag3::Throw_NtStatus(
      retaddr,
      (void *)0x558,
      (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
      (const char *)(unsigned int)v2,
      (int)&hMem);
  hMem = 0;
  if ( v4 )
    LocalFree(v4);
}

```

## disassembly

```asm
0x140016210  mov     [rsp-8+arg_10], rbx
0x140016215  push    rbp
0x140016216  mov     rbp, rsp
0x140016219  sub     rsp, 80h
0x140016220  mov     rax, cs:__security_cookie
0x140016227  xor     rax, rsp
0x14001622a  mov     [rbp+var_10], rax
0x14001622e  xorps   xmm0, xmm0
0x140016231  movups  [rbp+var_48], xmm0
0x140016235  movups  [rbp+var_38], xmm0
0x140016239  movups  [rbp+var_28], xmm0
0x14001623d  mov     dword ptr [rbp+var_48], edx
0x140016240  mov     qword ptr [rbp+var_48+8], rcx
0x140016244  mov     [rbp+hMem], 0
0x14001624c  lea     rax, [rbp+hMem]
0x140016250  mov     [rbp+var_60], rax
0x140016254  mov     [rbp+var_58], 0
0x14001625c  mov     [rbp+var_50], 1
0x140016260  lea     r8, [rbp+var_58]
0x140016264  lea     rdx, [rbp+var_48]
0x140016268  mov     ecx, 2
0x14001626d  call    cs:__imp_LsaManageSidNameMapping
0x140016273  mov     ebx, eax
0x140016275  cmp     [rbp+var_50], 0
0x140016279  jz      short loc_140016294
0x14001627b  mov     r8, [rbp+var_60]
0x14001627f  mov     rcx, [r8]; hMem
0x140016282  mov     rdx, [rbp+var_58]
0x140016286  mov     [r8], rdx
0x140016289  test    rcx, rcx
0x14001628c  jz      short loc_140016294
0x14001628e  call    cs:__imp_LocalFree
0x140016294  mov     rcx, [rbp+hMem]; hMem
0x140016298  test    ebx, ebx
0x14001629a  jns     short loc_1400162AB
0x14001629c  test    rcx, rcx
0x14001629f  jz      short loc_1400162DB
0x1400162a1  mov     eax, [rcx]
0x1400162a3  sub     eax, 2
0x1400162a6  cmp     eax, 1
0x1400162a9  ja      short loc_1400162DB
0x1400162ab  mov     [rbp+hMem], 0
0x1400162b3  test    rcx, rcx
0x1400162b6  jz      short loc_1400162BE
0x1400162b8  call    cs:__imp_LocalFree
0x1400162be  mov     rcx, [rbp+var_10]
0x1400162c2  xor     rcx, rsp; StackCookie
0x1400162c5  call    __security_check_cookie
0x1400162ca  mov     rbx, [rsp+80h+arg_10]
0x1400162d2  add     rsp, 80h
0x1400162d9  pop     rbp
0x1400162da  retn
0x1400162db  mov     rcx, [rbp+8]; this
0x1400162df  mov     r9d, ebx; char *
0x1400162e2  lea     r8, aOnecoreVmCompu_2; "onecore\\vm\\compute\\service\\cexec\\l"...
0x1400162e9  mov     edx, 558h; void *
0x1400162ee  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
```
