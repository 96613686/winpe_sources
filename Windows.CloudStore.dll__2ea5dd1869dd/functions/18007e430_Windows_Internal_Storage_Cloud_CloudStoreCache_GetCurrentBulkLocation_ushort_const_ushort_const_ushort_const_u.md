# Windows::Internal::Storage::Cloud::CloudStoreCache::GetCurrentBulkLocation(ushort const *,ushort const *,ushort const *,ushort * *)

- ea: `0x18007e430`
- end: `0x18007e568`
- name: `?GetCurrentBulkLocation@CloudStoreCache@Cloud@Storage@Internal@Windows@@AEAAJPEBG00PEAPEAG@Z`
- size: `312`
- prototype: `__int64 __fastcall(Windows::Internal::Storage::Cloud::CloudStoreCache *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18007e130`

## callees

- `0x18007ae70`
- `0x18007e430`
- `0x18007e6d8`
- `0x1800c8458`
- `0x180208010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007e4ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007e4f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007e532`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007e4ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007e4f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007e532`

## string_xrefs

- `0x18007e514`: `onecoreuap\shell\cloudstore\store\cache\src\cloudstorecache.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::Storage::Cloud::CloudStoreCache::GetCurrentBulkLocation(
        Windows::Internal::Storage::Cloud::CloudStoreCache *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 **a5)
{
  unsigned __int16 **v5; // rdi
  __int64 *v6; // rcx
  __int64 v7; // rax
  int v8; // ebx
  void *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx
  void *v12; // rcx
  bool v13; // zf
  void *v15; // rcx
  __int64 v16; // rdx
  LPVOID *p_pv; // [rsp+40h] [rbp-20h] BYREF
  void *v18; // [rsp+48h] [rbp-18h] BYREF
  char v19; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]
  LPVOID pv; // [rsp+70h] [rbp+10h] BYREF

  v5 = a5;
  *a5 = 0;
  LODWORD(a5) = 0;
  pv = 0;
  v6 = (__int64 *)*((_QWORD *)this + 2);
  v7 = *v6;
  p_pv = &pv;
  v18 = 0;
  v19 = 1;
  v8 = (*(__int64 (__fastcall **)(__int64 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *))(v7 + 32))(
         v6,
         a2,
         a3,
         a4);
  v9 = *p_pv;
  *p_pv = v18;
  if ( v9 )
    CoTaskMemFree(v9);
  if ( v8 == -2147024894 )
    goto LABEL_8;
  if ( v8 < 0 )
  {
    v16 = 375;
  }
  else
  {
    HIDWORD(v18) = 0;
    v8 = Windows::Internal::Storage::Cloud::CloudStoreMetadata::DeSerialize(
           (Windows::Internal::Storage::Cloud::CloudStoreMetadata *)&p_pv,
           (const unsigned __int8 *)pv,
           (unsigned int)a5);
    if ( v8 >= 0 )
    {
      if ( HIDWORD(v18) == 1 )
      {
        v8 = _AllocString<CTCoAllocPolicy>(v11, v10, (const WCHAR *)pv + 8, v5);
        if ( v8 < 0 )
        {
          v16 = 383;
          goto LABEL_11;
        }
      }
LABEL_8:
      v12 = pv;
      v13 = pv == 0;
      pv = 0;
      if ( !v13 )
        CoTaskMemFree(v12);
      return 0;
    }
    v16 = 378;
  }
LABEL_11:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v16,
    (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudstorecache.cpp",
    (const char *)(unsigned int)v8,
    (int)&v18);
  v15 = pv;
  pv = 0;
  if ( v15 )
    CoTaskMemFree(v15);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18007e430  mov     r11, rsp
0x18007e433  mov     [r11+10h], rbx
0x18007e437  mov     [r11+18h], rdi
0x18007e43b  push    rbp
0x18007e43c  mov     rbp, rsp
0x18007e43f  sub     rsp, 60h
0x18007e443  mov     rdi, [rbp+arg_20]
0x18007e447  mov     qword ptr [rdi], 0
0x18007e44e  mov     dword ptr [rbp+arg_20], 0
0x18007e455  mov     [rbp+pv], 0
0x18007e45d  mov     rcx, [rcx+10h]
0x18007e461  mov     rax, [rcx]
0x18007e464  lea     r10, [rbp+pv]
0x18007e468  mov     [rbp+var_20], r10
0x18007e46c  mov     [rbp+var_18], 0
0x18007e474  mov     [rbp+var_10], 1
0x18007e478  lea     r10, [rbp+arg_20]
0x18007e47c  mov     [r11-40h], r10
0x18007e480  lea     r10, [rbp+var_18]
0x18007e484  mov     [r11-48h], r10
0x18007e488  mov     rax, [rax+20h]
0x18007e48c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e491  mov     ebx, eax
0x18007e493  cmp     [rbp+var_10], 0
0x18007e497  jz      short loc_18007E4B2
0x18007e499  mov     r8, [rbp+var_20]
0x18007e49d  mov     rcx, [r8]; pv
0x18007e4a0  mov     rdx, [rbp+var_18]
0x18007e4a4  mov     [r8], rdx
0x18007e4a7  test    rcx, rcx
0x18007e4aa  jz      short loc_18007E4B2
0x18007e4ac  call    cs:__imp_CoTaskMemFree
0x18007e4b2  cmp     ebx, 80070002h
0x18007e4b8  jz      short loc_18007E4E2
0x18007e4ba  test    ebx, ebx
0x18007e4bc  js      short loc_18007E53C
0x18007e4be  mov     dword ptr [rbp+var_18+4], 0
0x18007e4c5  mov     r8d, dword ptr [rbp+arg_20]; unsigned int
0x18007e4c9  mov     rdx, [rbp+pv]; unsigned __int8 *
0x18007e4cd  lea     rcx, [rbp+var_20]; this
0x18007e4d1  call    ?DeSerialize@CloudStoreMetadata@Cloud@Storage@Internal@Windows@@QEAAJPEBEI@Z; Windows::Internal::Storage::Cloud::CloudStoreMetadata::DeSerialize(uchar const *,uint)
0x18007e4d6  mov     ebx, eax
0x18007e4d8  test    eax, eax
0x18007e4da  js      short loc_18007E543
0x18007e4dc  cmp     dword ptr [rbp+var_18+4], 1
0x18007e4e0  jz      short loc_18007E54A
0x18007e4e2  mov     rcx, [rbp+pv]; pv
0x18007e4e6  test    rcx, rcx
0x18007e4e9  mov     [rbp+pv], 0
0x18007e4f1  jz      short loc_18007E4F9
0x18007e4f3  call    cs:__imp_CoTaskMemFree
0x18007e4f9  xor     eax, eax
0x18007e4fb  lea     r11, [rsp+60h+var_s0]
0x18007e500  mov     rbx, [r11+18h]
0x18007e504  mov     rdi, [r11+20h]
0x18007e508  mov     rsp, r11
0x18007e50b  pop     rbp
0x18007e50c  retn
0x18007e50d  mov     rcx, [rbp+8]; this
0x18007e511  mov     r9d, ebx; char *
0x18007e514  lea     r8, aOnecoreuapShel_56; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x18007e51b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007e520  nop
0x18007e521  mov     rcx, [rbp+pv]; pv
0x18007e525  mov     [rbp+pv], 0
0x18007e52d  test    rcx, rcx
0x18007e530  jz      short loc_18007E538
0x18007e532  call    cs:__imp_CoTaskMemFree
0x18007e538  mov     eax, ebx
0x18007e53a  jmp     short loc_18007E4FB
0x18007e53c  mov     edx, 177h; void *
0x18007e541  jmp     short loc_18007E50D
0x18007e543  mov     edx, 17Ah
0x18007e548  jmp     short loc_18007E50D
0x18007e54a  mov     r8, [rbp+pv]
0x18007e54e  add     r8, 10h
0x18007e552  mov     r9, rdi
0x18007e555  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x18007e55a  mov     ebx, eax
0x18007e55c  test    eax, eax
0x18007e55e  jns     short loc_18007E4E2
0x18007e560  mov     edx, 17Fh
0x18007e565  jmp     short loc_18007E50D
```
