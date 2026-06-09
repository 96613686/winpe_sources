# GetMDMPolicyIsConfigured(_STORAGE_POLICY,ulong *)

- ea: `0x1800195b4`
- end: `0x18001966b`
- name: `?GetMDMPolicyIsConfigured@@YAJW4_STORAGE_POLICY@@PEAK@Z`
- size: `183`
- prototype: `__int64 __fastcall(int, _DWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800180a0`
- `0x180019c40`

## callees

- `0x1800152d4`
- `0x180017cdc`
- `0x1800195b4`

## import_xrefs

- `ext-ms-win-devmgmt-policy-l1-1-1!PolicyManager_GetPolicy` at `0x180019638`
- `ext-ms-win-devmgmt-policy-l1-1-1!PolicyManager_GetPolicy` at `0x180019638`

## pseudocode

```c
__int64 __fastcall GetMDMPolicyIsConfigured(int a1, _DWORD *a2)
{
  int Policy; // edi
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v7; // [rsp+38h] [rbp+10h] BYREF
  int v8; // [rsp+40h] [rbp+18h] BYREF
  int v9; // [rsp+44h] [rbp+1Ch]

  if ( a2 )
  {
    *a2 = 0;
    if ( ((a1 - 4) & 0xFFFFFFFD) != 0 )
    {
      v8 = 1;
      v9 = 2;
      v7 = 0;
      Policy = PolicyManager_GetPolicy(L"Storage", (&off_18002F7A0)[3 * a1], &v8, &v7);
      if ( Policy >= 0 )
        *a2 = *(_DWORD *)(v7 + 4) == 2;
      wil::details::unique_storage<wil::details::resource_policy<PMPolicyRetrievedInfo *,long (*)(PMPolicyRetrievedInfo *),&long PolicyManager_FreeGetPolicyData(PMPolicyRetrievedInfo *),wistd::integral_constant<unsigned __int64,0>,PMPolicyRetrievedInfo *,PMPolicyRetrievedInfo *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<PMPolicyRetrievedInfo *,long (*)(PMPolicyRetrievedInfo *),&long PolicyManager_FreeGetPolicyData(PMPolicyRetrievedInfo *),wistd::integral_constant<unsigned __int64,0>,PMPolicyRetrievedInfo *,PMPolicyRetrievedInfo *,0,std::nullptr_t>>(&v7);
      return (unsigned int)Policy;
    }
    else
    {
      return 0;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3FA,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\storageusage\\storagegrovelerscans.cpp",
      (const char *)0x80070057LL,
      v5);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x1800195b4  mov     [rsp+arg_0], rbx
0x1800195b9  push    rdi; int
0x1800195ba  sub     rsp, 20h
0x1800195be  mov     rbx, rdx
0x1800195c1  test    rdx, rdx
0x1800195c4  jnz     short loc_1800195E8
0x1800195c6  mov     rcx, [rsp+28h]; this
0x1800195cb  lea     r8, aOnecoreDrivers; "onecore\\drivers\\storage\\storsvc\\sto"...
0x1800195d2  mov     ebx, 80070057h
0x1800195d7  mov     edx, 3FAh; void *
0x1800195dc  mov     r9d, ebx; char *
0x1800195df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800195e4  mov     eax, ebx
0x1800195e6  jmp     short loc_180019660
0x1800195e8  lea     eax, [rcx-4]
0x1800195eb  mov     dword ptr [rdx], 0
0x1800195f1  test    eax, 0FFFFFFFDh
0x1800195f6  jnz     short loc_1800195FC
0x1800195f8  xor     eax, eax
0x1800195fa  jmp     short loc_180019660
0x1800195fc  movsxd  rax, ecx
0x1800195ff  lea     r9, [rsp+28h+arg_8]
0x180019604  lea     r8, [rsp+28h+arg_10]
0x180019609  mov     [rsp+28h+arg_10], 1
0x180019611  lea     rcx, aStorage; "Storage"
0x180019618  mov     [rsp+28h+arg_14], 2
0x180019620  mov     [rsp+28h+arg_8], 0
0x180019629  lea     rdx, [rax+rax*2]
0x18001962d  lea     rax, off_18002F7A0; "AllowStorageSenseGlobal"
0x180019634  mov     rdx, [rax+rdx*8]
0x180019638  call    cs:__imp_PolicyManager_GetPolicy
0x18001963e  mov     edi, eax
0x180019640  test    eax, eax
0x180019642  js      short loc_180019654
0x180019644  mov     rcx, [rsp+28h+arg_8]
0x180019649  xor     edx, edx
0x18001964b  cmp     dword ptr [rcx+4], 2
0x18001964f  setz    dl
0x180019652  mov     [rbx], edx
0x180019654  lea     rcx, [rsp+28h+arg_8]
0x180019659  call    ??1?$unique_storage@U?$resource_policy@PEAUPMPolicyRetrievedInfo@@P6AJPEAU1@@Z$1?PolicyManager_FreeGetPolicyData@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<PMPolicyRetrievedInfo *,long (*)(PMPolicyRetrievedInfo *),&PolicyManager_FreeGetPolicyData(PMPolicyRetrievedInfo *),wistd::integral_constant<unsigned __int64,0>,PMPolicyRetrievedInfo *,PMPolicyRetrievedInfo *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<PMPolicyRetrievedInfo *,long (*)(PMPolicyRetrievedInfo *),&PolicyManager_FreeGetPolicyData(PMPolicyRetrievedInfo *),wistd::integral_constant<unsigned __int64,0>,PMPolicyRetrievedInfo *,PMPolicyRetrievedInfo *,0,std::nullptr_t>>(void)
0x18001965e  mov     eax, edi
0x180019660  mov     rbx, [rsp+28h+arg_0]
0x180019665  add     rsp, 20h
0x180019669  pop     rdi
0x18001966a  retn
```
