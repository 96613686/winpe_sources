# CacheBinaryAutoList(IAutoListDescription *,INamedPropertyStore *)

- ea: `0x1800062b4`
- end: `0x180006472`
- name: `?CacheBinaryAutoList@@YAXPEAUIAutoListDescription@@PEAUINamedPropertyStore@@@Z`
- size: `446`
- prototype: `void __fastcall(struct IAutoListDescription *, struct INamedPropertyStore *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005bf0`

## callees

- `0x1800062b4`
- `0x180006fb8`
- `0x18000713c`
- `0x180071dc0`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000643d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000643d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006448`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006448`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800062f3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800062f3`

## string_xrefs

- `0x1800063be`: `AutolistCacheKey`
- `0x180006311`: `AutolistCacheTime`

## pseudocode

```c
void __fastcall CacheBinaryAutoList(struct IAutoListDescription *a1, struct INamedPropertyStore *a2)
{
  __int64 v4; // rax
  int v5; // [rsp+20h] [rbp-E0h]
  int v6; // [rsp+30h] [rbp-D0h] BYREF
  struct IAutoListCache *v7; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-C0h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+48h] [rbp-B8h] BYREF
  PROPVARIANT pvar[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v11; // [rsp+60h] [rbp-A0h]
  _QWORD v12[3]; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 v13[264]; // [rsp+80h] [rbp-80h] BYREF

  PerformanceCount.QuadPart = 0;
  QueryPerformanceCounter(&PerformanceCount);
  pv = 0;
  v11 = 0;
  pvar[0] = (PROPVARIANT)20;
  pvar[1] = (PROPVARIANT)PerformanceCount.QuadPart;
  if ( ((int (__fastcall *)(struct INamedPropertyStore *, const wchar_t *, PROPVARIANT *))a2->lpVtbl->SetNamedValue)(
         a2,
         L"AutolistCacheTime",
         pvar) >= 0
    && (*(int (__fastcall **)(struct IAutoListDescription *, LPVOID *))(*(_QWORD *)a1 + 24LL))(a1, &pv) >= 0 )
  {
    v4 = *(_QWORD *)a1;
    v6 = 0;
    if ( (*(int (__fastcall **)(struct IAutoListDescription *, int *))(v4 + 120))(a1, &v6) >= 0 )
    {
      v5 = v6;
      if ( (int)StringCchPrintfW(v13, 0x104u, L"%s%x", pv, v5) >= 0 )
      {
        v12[2] = 0;
        v12[0] = 31;
        v12[1] = v13;
        if ( ((int (__fastcall *)(struct INamedPropertyStore *, const wchar_t *, _QWORD *))a2->lpVtbl->SetNamedValue)(
               a2,
               L"AutolistCacheKey",
               v12) >= 0 )
        {
          v7 = 0;
          if ( (int)_GetGlobalAutoListCache(&v7) >= 0 )
          {
            (*(void (__fastcall **)(struct IAutoListCache *, struct IAutoListDescription *, unsigned __int16 *, PROPVARIANT *))(*(_QWORD *)v7 + 48LL))(
              v7,
              a1,
              v13,
              pvar);
            (*(void (__fastcall **)(struct IAutoListCache *))(*(_QWORD *)v7 + 16LL))(v7);
          }
        }
      }
    }
    CoTaskMemFree(pv);
  }
  PropVariantClear(pvar);
}

```

## disassembly

```asm
0x1800062b4  mov     [rsp-8+arg_10], rbx
0x1800062b9  mov     [rsp-8+arg_18], rdi
0x1800062be  push    rbp
0x1800062bf  lea     rbp, [rsp-1A0h]
0x1800062c7  sub     rsp, 2A0h
0x1800062ce  mov     rax, cs:__security_cookie
0x1800062d5  xor     rax, rsp
0x1800062d8  mov     [rbp+1A0h+var_10], rax
0x1800062df  mov     rbx, rcx
0x1800062e2  mov     qword ptr [rsp+2A0h+PerformanceCount], 0
0x1800062eb  lea     rcx, [rsp+2A0h+PerformanceCount]; lpPerformanceCount
0x1800062f0  mov     rdi, rdx
0x1800062f3  call    cs:__imp_QueryPerformanceCounter
0x1800062f9  xor     eax, eax
0x1800062fb  mov     [rsp+2A0h+pv], 0
0x180006304  mov     [rsp+2A0h+var_240], rax
0x180006309  lea     r8, [rsp+2A0h+pvar]
0x18000630e  xorps   xmm0, xmm0
0x180006311  lea     rdx, aAutolistcachet; "AutolistCacheTime"
0x180006318  movups  xmmword ptr [rsp+2A0h+pvar], xmm0
0x18000631d  mov     eax, 14h
0x180006322  mov     rcx, rdi
0x180006325  mov     word ptr [rsp+2A0h+pvar], ax
0x18000632a  mov     rax, qword ptr [rsp+2A0h+PerformanceCount]
0x18000632f  mov     [rsp+2A0h+pvar+8], rax
0x180006334  mov     rax, [rdi]
0x180006337  mov     rax, [rax+20h]
0x18000633b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006340  test    eax, eax
0x180006342  js      loc_180006443
0x180006348  mov     rax, [rbx]
0x18000634b  lea     rdx, [rsp+2A0h+pv]
0x180006350  mov     rcx, rbx
0x180006353  mov     rax, [rax+18h]
0x180006357  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000635c  test    eax, eax
0x18000635e  js      loc_180006443
0x180006364  mov     rax, [rbx]
0x180006367  lea     rdx, [rsp+2A0h+var_270]
0x18000636c  mov     rcx, rbx
0x18000636f  mov     [rsp+2A0h+var_270], 0
0x180006377  mov     rax, [rax+78h]
0x18000637b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006380  test    eax, eax
0x180006382  js      loc_180006438
0x180006388  mov     eax, [rsp+2A0h+var_270]
0x18000638c  lea     r8, aSX; "%s%x"
0x180006393  mov     r9, [rsp+2A0h+pv]
0x180006398  lea     rcx, [rbp+1A0h+var_220]; unsigned __int16 *
0x18000639c  mov     edx, 104h; unsigned __int64
0x1800063a1  mov     [rsp+2A0h+var_280], eax
0x1800063a5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800063aa  test    eax, eax
0x1800063ac  js      loc_180006438
0x1800063b2  xor     eax, eax
0x1800063b4  lea     r8, [rsp+2A0h+var_238]
0x1800063b9  mov     [rsp+2A0h+var_228], rax
0x1800063be  lea     rdx, aAutolistcachek; "AutolistCacheKey"
0x1800063c5  xorps   xmm0, xmm0
0x1800063c8  mov     eax, 1Fh
0x1800063cd  movups  [rsp+2A0h+var_238], xmm0
0x1800063d2  mov     word ptr [rsp+2A0h+var_238], ax
0x1800063d7  mov     rcx, rdi
0x1800063da  lea     rax, [rbp+1A0h+var_220]
0x1800063de  mov     qword ptr [rsp+2A0h+var_238+8], rax
0x1800063e3  mov     rax, [rdi]
0x1800063e6  mov     rax, [rax+20h]
0x1800063ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063ef  test    eax, eax
0x1800063f1  js      short loc_180006438
0x1800063f3  lea     rcx, [rsp+2A0h+var_268]; struct IAutoListCache **
0x1800063f8  mov     [rsp+2A0h+var_268], 0
0x180006401  call    ?_GetGlobalAutoListCache@@YAJPEAPEAUIAutoListCache@@@Z; _GetGlobalAutoListCache(IAutoListCache * *)
0x180006406  test    eax, eax
0x180006408  js      short loc_180006438
0x18000640a  mov     rcx, [rsp+2A0h+var_268]
0x18000640f  lea     r9, [rsp+2A0h+pvar]
0x180006414  lea     r8, [rbp+1A0h+var_220]
0x180006418  mov     rdx, rbx
0x18000641b  mov     rax, [rcx]
0x18000641e  mov     rax, [rax+30h]
0x180006422  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006427  mov     rcx, [rsp+2A0h+var_268]
0x18000642c  mov     rax, [rcx]
0x18000642f  mov     rax, [rax+10h]
0x180006433  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006438  mov     rcx, [rsp+2A0h+pv]; pv
0x18000643d  call    cs:__imp_CoTaskMemFree
0x180006443  lea     rcx, [rsp+2A0h+pvar]; pvar
0x180006448  call    cs:__imp_PropVariantClear
0x18000644e  mov     rcx, [rbp+1A0h+var_10]
0x180006455  xor     rcx, rsp; StackCookie
0x180006458  call    __security_check_cookie
0x18000645d  lea     r11, [rsp+2A0h+var_s0]
0x180006465  mov     rbx, [r11+20h]
0x180006469  mov     rdi, [r11+28h]
0x18000646d  mov     rsp, r11
0x180006470  pop     rbp
0x180006471  retn
```
