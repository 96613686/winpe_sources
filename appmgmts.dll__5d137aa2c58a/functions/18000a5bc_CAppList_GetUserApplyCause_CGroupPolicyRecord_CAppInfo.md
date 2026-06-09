# CAppList::GetUserApplyCause(CGroupPolicyRecord *,CAppInfo *)

- ea: `0x18000a5bc`
- end: `0x18000a6de`
- name: `?GetUserApplyCause@CAppList@@AEAAJPEAVCGroupPolicyRecord@@PEAVCAppInfo@@@Z`
- size: `290`
- prototype: `int __fastcall(CAppList *this, struct CGroupPolicyRecord *, struct CAppInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000aeb4`

## callees

- `0x18000a5bc`
- `0x180029d60`
- `0x180029e18`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a6a2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a6a2`

## string_xrefs

- `0x18000a64e`: `OnDemandFileExtension`
- `0x18000a645`: `OnDemandClsid`

## pseudocode

```c
int __fastcall CAppList::GetUserApplyCause(CAppList *this, struct CGroupPolicyRecord *a2, struct CAppInfo *a3)
{
  int result; // eax
  int v6; // r9d
  const unsigned __int16 **v7; // rbx
  int v8; // r9d
  int v9; // r9d
  const unsigned __int16 *v10; // rdx
  SIZE_T v11; // rax
  unsigned __int16 *v12; // rax
  int v13; // [rsp+30h] [rbp+8h] BYREF
  int v14; // [rsp+34h] [rbp+Ch]

  v14 = HIDWORD(this);
  v13 = 0;
  result = CGroupPolicyRecord::GetValue(a2, L"ApplyCause", &v13);
  if ( result >= 0 )
  {
    v6 = v13;
    if ( v13 )
    {
      v7 = (const unsigned __int16 **)((char *)a3 + 448);
      if ( !*((_QWORD *)a3 + 56) )
      {
        *((_DWORD *)a3 + 109) = v13;
        v8 = v6 - 4;
        if ( v8 )
        {
          v9 = v8 - 1;
          if ( v9 )
          {
            if ( v9 != 2 )
            {
              *v7 = 0;
              return result;
            }
            v10 = L"OnDemandProgid";
          }
          else
          {
            v10 = L"OnDemandClsid";
          }
        }
        else
        {
          v10 = L"OnDemandFileExtension";
        }
        *v7 = v10;
        if ( !*((_QWORD *)a3 + 55) )
        {
          v13 = 0;
          result = CGroupPolicyRecord::GetValue(a2, v10, 0, &v13);
          if ( result == 1 )
          {
            v11 = 2LL * v13;
            if ( !is_mul_ok(v13, 2u) )
              v11 = -1;
            v12 = (unsigned __int16 *)LocalAlloc(0, v11);
            *((_QWORD *)a3 + 55) = v12;
            if ( v12 )
              return CGroupPolicyRecord::GetValue(a2, *v7, v12, &v13);
            else
              return -2147024882;
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000a5bc  mov     rax, rsp
0x18000a5bf  mov     [rax+10h], rbx
0x18000a5c3  mov     [rax+18h], rsi
0x18000a5c7  mov     [rax+8], rcx
0x18000a5cb  push    rdi
0x18000a5cc  sub     rsp, 20h
0x18000a5d0  mov     rsi, rdx
0x18000a5d3  mov     dword ptr [rax+8], 0
0x18000a5da  mov     rdi, r8
0x18000a5dd  lea     rdx, aApplycause; "ApplyCause"
0x18000a5e4  mov     rcx, rsi; this
0x18000a5e7  lea     r8, [rax+8]; int *
0x18000a5eb  call    ?GetValue@CGroupPolicyRecord@@QEAAJPEBGPEAJ@Z; CGroupPolicyRecord::GetValue(ushort const *,long *)
0x18000a5f0  test    eax, eax
0x18000a5f2  js      loc_18000A6CE
0x18000a5f8  mov     r9d, [rsp+28h+arg_0]
0x18000a5fd  test    r9d, r9d
0x18000a600  jz      loc_18000A6CE
0x18000a606  lea     rbx, [rdi+1C0h]
0x18000a60d  cmp     qword ptr [rbx], 0
0x18000a611  jnz     loc_18000A6CE
0x18000a617  mov     [rdi+1B4h], r9d
0x18000a61e  sub     r9d, 4
0x18000a622  jz      short loc_18000A64E
0x18000a624  sub     r9d, 1
0x18000a628  jz      short loc_18000A645
0x18000a62a  cmp     r9d, 2
0x18000a62e  jz      short loc_18000A63C
0x18000a630  mov     qword ptr [rbx], 0
0x18000a637  jmp     loc_18000A6CE
0x18000a63c  lea     rdx, aOndemandprogid; "OnDemandProgid"
0x18000a643  jmp     short loc_18000A655
0x18000a645  lea     rdx, aOndemandclsid; "OnDemandClsid"
0x18000a64c  jmp     short loc_18000A655
0x18000a64e  lea     rdx, aOndemandfileex; "OnDemandFileExtension"
0x18000a655  mov     [rbx], rdx
0x18000a658  mov     rcx, rdx
0x18000a65b  cmp     qword ptr [rdi+1B8h], 0
0x18000a663  mov     r8, rbx
0x18000a666  jnz     short loc_18000A6CE
0x18000a668  lea     r9, [rsp+28h+arg_0]; int *
0x18000a66d  mov     [rsp+28h+arg_0], 0
0x18000a675  xor     r8d, r8d; unsigned __int16 *
0x18000a678  mov     rcx, rsi; this
0x18000a67b  call    ?GetValue@CGroupPolicyRecord@@QEAAJPEBGPEAGPEAJ@Z; CGroupPolicyRecord::GetValue(ushort const *,ushort *,long *)
0x18000a680  cmp     eax, 1
0x18000a683  jnz     short loc_18000A6CE
0x18000a685  movsxd  rcx, [rsp+28h+arg_0]
0x18000a68a  mov     eax, 2
0x18000a68f  mul     rcx
0x18000a692  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000a699  cmovb   rax, rcx
0x18000a69d  xor     ecx, ecx; uFlags
0x18000a69f  mov     rdx, rax; uBytes
0x18000a6a2  call    cs:__imp_LocalAlloc
0x18000a6a8  mov     [rdi+1B8h], rax
0x18000a6af  test    rax, rax
0x18000a6b2  jz      short loc_18000A6C9
0x18000a6b4  mov     rdx, [rbx]; unsigned __int16 *
0x18000a6b7  lea     r9, [rsp+28h+arg_0]; int *
0x18000a6bc  mov     r8, rax; unsigned __int16 *
0x18000a6bf  mov     rcx, rsi; this
0x18000a6c2  call    ?GetValue@CGroupPolicyRecord@@QEAAJPEBGPEAGPEAJ@Z; CGroupPolicyRecord::GetValue(ushort const *,ushort *,long *)
0x18000a6c7  jmp     short loc_18000A6CE
0x18000a6c9  mov     eax, 8007000Eh
0x18000a6ce  mov     rbx, [rsp+28h+arg_8]
0x18000a6d3  mov     rsi, [rsp+28h+arg_10]
0x18000a6d8  add     rsp, 20h
0x18000a6dc  pop     rdi
0x18000a6dd  retn
```
