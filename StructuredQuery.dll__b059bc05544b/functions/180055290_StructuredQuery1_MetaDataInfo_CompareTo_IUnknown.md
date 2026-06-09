# StructuredQuery1::MetaDataInfo::CompareTo(IUnknown *)

- ea: `0x180055290`
- end: `0x18005537f`
- name: `?CompareTo@MetaDataInfo@StructuredQuery1@@UEAAHPEAUIUnknown@@@Z`
- size: `239`
- prototype: `__int64 __fastcall(StructuredQuery1::MetaDataInfo *__hidden this, struct IUnknown *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180055290`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005530e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180055359`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005530e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180055359`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::MetaDataInfo::CompareTo(StructuredQuery1::MetaDataInfo *this, struct IUnknown *a2)
{
  struct IUnknownVtbl *lpVtbl; // rax
  unsigned int v4; // ebx
  const WCHAR *lpString2; // rbx
  const WCHAR *v6; // rax
  const WCHAR *v7; // rbx
  const WCHAR *v8; // rax
  __int64 v10; // [rsp+48h] [rbp+10h] BYREF

  lpVtbl = a2->lpVtbl;
  v10 = 0;
  v4 = 3;
  if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))lpVtbl->QueryInterface)(
         a2,
         &GUID_58d2317e_2aeb_439d_8514_ad3bc6814578,
         &v10) >= 0 )
  {
    lpString2 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 32LL))(v10);
    v6 = (const WCHAR *)(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this - 1) + 32LL))((char *)this - 8);
    v4 = CompareStringW(0x7Fu, 0, v6, -1, lpString2, -1);
    if ( v4 == 2 )
    {
      v7 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 48LL))(v10);
      v8 = (const WCHAR *)(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this - 1) + 48LL))((char *)this - 8);
      v4 = CompareStringW(0x7Fu, 0, v8, -1, v7, -1);
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
  return v4;
}

```

## disassembly

```asm
0x180055290  mov     [rsp+arg_0], rbx
0x180055295  push    rdi
0x180055296  sub     rsp, 30h
0x18005529a  mov     rax, [rdx]
0x18005529d  lea     r8, [rsp+38h+arg_8]
0x1800552a2  mov     r9, rdx
0x1800552a5  mov     [rsp+38h+arg_8], 0
0x1800552ae  mov     rdi, rcx
0x1800552b1  lea     rdx, _GUID_58d2317e_2aeb_439d_8514_ad3bc6814578
0x1800552b8  mov     rcx, r9
0x1800552bb  mov     ebx, 3
0x1800552c0  mov     rax, [rax]
0x1800552c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800552c8  test    eax, eax
0x1800552ca  js      loc_180055372
0x1800552d0  mov     rcx, [rsp+38h+arg_8]
0x1800552d5  mov     rax, [rcx]
0x1800552d8  mov     rax, [rax+20h]
0x1800552dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800552e1  mov     rbx, rax
0x1800552e4  lea     rcx, [rdi-8]
0x1800552e8  mov     rax, [rdi-8]
0x1800552ec  mov     rax, [rax+20h]
0x1800552f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800552f5  xor     edx, edx; dwCmpFlags
0x1800552f7  mov     [rsp+38h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800552ff  or      r9d, 0FFFFFFFFh; cchCount1
0x180055303  mov     [rsp+38h+lpString2], rbx; lpString2
0x180055308  mov     r8, rax; lpString1
0x18005530b  lea     ecx, [rdx+7Fh]; Locale
0x18005530e  call    cs:__imp_CompareStringW
0x180055314  mov     ebx, eax
0x180055316  cmp     eax, 2
0x180055319  jnz     short loc_180055361
0x18005531b  mov     rcx, [rsp+38h+arg_8]
0x180055320  mov     rax, [rcx]
0x180055323  mov     rax, [rax+30h]
0x180055327  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005532c  mov     rdx, [rdi-8]
0x180055330  lea     rcx, [rdi-8]
0x180055334  mov     rbx, rax
0x180055337  mov     rax, [rdx+30h]
0x18005533b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055340  xor     edx, edx; dwCmpFlags
0x180055342  mov     [rsp+38h+cchCount2], 0FFFFFFFFh; cchCount2
0x18005534a  or      r9d, 0FFFFFFFFh; cchCount1
0x18005534e  mov     [rsp+38h+lpString2], rbx; lpString2
0x180055353  mov     r8, rax; lpString1
0x180055356  lea     ecx, [rdx+7Fh]; Locale
0x180055359  call    cs:__imp_CompareStringW
0x18005535f  mov     ebx, eax
0x180055361  mov     rcx, [rsp+38h+arg_8]
0x180055366  mov     rax, [rcx]
0x180055369  mov     rax, [rax+10h]
0x18005536d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055372  mov     eax, ebx
0x180055374  mov     rbx, [rsp+38h+arg_0]
0x180055379  add     rsp, 30h
0x18005537d  pop     rdi
0x18005537e  retn
```
