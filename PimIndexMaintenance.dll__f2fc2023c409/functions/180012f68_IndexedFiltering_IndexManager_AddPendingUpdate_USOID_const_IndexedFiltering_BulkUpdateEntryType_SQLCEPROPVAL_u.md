# IndexedFiltering::IndexManager::AddPendingUpdate(USOID const &,IndexedFiltering::BulkUpdateEntryType,_SQLCEPROPVAL *,unsigned __int64,int)

- ea: `0x180012f68`
- end: `0x1800130b0`
- name: `?AddPendingUpdate@IndexManager@IndexedFiltering@@AEAAJAEBUUSOID@@W4BulkUpdateEntryType@2@PEAU_SQLCEPROPVAL@@_KH@Z`
- size: `328`
- prototype: `__int64 __fastcall(__int64, int *, int, __int64, __int64, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, installer_update`

## callers

- `0x180014020`
- `0x1800144c0`

## callees

- `0x180002da8`
- `0x1800086a0`
- `0x180012a3c`
- `0x180012f68`
- `0x180021240`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013060`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013060`
- `UserDataTypeHelperUtil!DuplicateCEPROPVALArray` at `0x180012fe8`
- `UserDataTypeHelperUtil!DuplicateCEPROPVALArray` at `0x180012fe8`

## string_xrefs

- `0x180012fae`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\indexmanager.cpp`
- `0x180013095`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\indexmanager.cpp`

## pseudocode

```c
__int64 __fastcall IndexedFiltering::IndexManager::AddPendingUpdate(
        __int64 a1,
        int *a2,
        int a3,
        __int64 a4,
        __int64 a5,
        int a6)
{
  int v6; // ebx
  int v11; // ecx
  __int64 v12; // rax
  __int128 v13; // xmm1
  __int64 v14; // xmm0_8
  HLOCAL hMem; // [rsp+30h] [rbp-40h] BYREF
  _BYTE v17[40]; // [rsp+38h] [rbp-38h] BYREF

  v6 = 0;
  hMem = 0;
  if ( !a4 && a5 )
    Log_AssertionEvent(
      a1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\indexmanager.cpp",
      973);
  if ( *(_DWORD *)(a1 + 128) )
  {
    memset(&v17[4], 0, 36);
    if ( !a5 || (v6 = DuplicateCEPROPVALArray(a4, a5, 0, &hMem), v6 >= 0) )
    {
      if ( a3 == 1 || a5 )
      {
        v11 = *a2;
        *(_QWORD *)&v17[4] = *(_QWORD *)(a2 + 1);
        *(_QWORD *)&v17[16] = hMem;
        *(_DWORD *)v17 = v11;
        *(_DWORD *)&v17[32] = a6;
        v12 = *(_QWORD *)(a1 + 144);
        *(_DWORD *)&v17[12] = a3;
        *(_QWORD *)&v17[24] = a5;
        if ( v12 == *(_QWORD *)(a1 + 152) )
        {
          if ( !utl::vector<IndexedFiltering::BulkUpdateEntry,utl::allocator<IndexedFiltering::BulkUpdateEntry>>::_PushBackOne2<IndexedFiltering::BulkUpdateEntry const &>(
                  (__int64 *)(a1 + 136),
                  (__int64)v17) )
          {
            v6 = -2147467259;
            Log_HREvent(
              2147500037LL,
              1,
              "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\indexmanager.cpp",
              998);
            goto LABEL_12;
          }
        }
        else
        {
          v13 = *(_OWORD *)&v17[16];
          *(_OWORD *)v12 = *(_OWORD *)v17;
          v14 = *(_QWORD *)&v17[32];
          *(_OWORD *)(v12 + 16) = v13;
          *(_QWORD *)(v12 + 32) = v14;
          *(_QWORD *)(a1 + 144) += 40LL;
        }
        hMem = 0;
      }
    }
  }
LABEL_12:
  LocalFree(hMem);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180012f68  push    rbp
0x180012f6a  push    rbx
0x180012f6b  push    rsi
0x180012f6c  push    rdi
0x180012f6d  push    r12
0x180012f6f  push    r14
0x180012f71  push    r15
0x180012f73  mov     rbp, rsp
0x180012f76  sub     rsp, 70h
0x180012f7a  mov     rax, cs:__security_cookie
0x180012f81  xor     rax, rsp
0x180012f84  mov     [rbp+var_10], rax
0x180012f88  mov     rdi, [rbp+arg_20]
0x180012f8c  xor     ebx, ebx
0x180012f8e  mov     [rbp+hMem], rbx
0x180012f92  mov     r15, r9
0x180012f95  mov     r14d, r8d
0x180012f98  mov     r12, rdx
0x180012f9b  mov     rsi, rcx
0x180012f9e  test    r9, r9
0x180012fa1  jnz     short loc_180012FBA
0x180012fa3  test    rdi, rdi
0x180012fa6  jz      short loc_180012FBA
0x180012fa8  mov     r8d, 3CDh
0x180012fae  lea     rdx, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180012fb5  call    Log_AssertionEvent
0x180012fba  cmp     [rsi+80h], ebx
0x180012fc0  jz      loc_18001305C
0x180012fc6  xor     eax, eax
0x180012fc8  xorps   xmm0, xmm0
0x180012fcb  mov     [rbp+var_14], eax
0x180012fce  movups  [rbp+var_38+4], xmm0
0x180012fd2  movups  [rbp+var_24], xmm0
0x180012fd6  test    rdi, rdi
0x180012fd9  jz      short loc_180012FF4
0x180012fdb  lea     r9, [rbp+hMem]
0x180012fdf  xor     r8d, r8d
0x180012fe2  mov     rdx, rdi
0x180012fe5  mov     rcx, r15
0x180012fe8  call    cs:__imp_DuplicateCEPROPVALArray
0x180012fee  mov     ebx, eax
0x180012ff0  test    eax, eax
0x180012ff2  js      short loc_18001305C
0x180012ff4  cmp     r14d, 1
0x180012ff8  jz      short loc_180012FFF
0x180012ffa  test    rdi, rdi
0x180012ffd  jz      short loc_18001305C
0x180012fff  mov     rax, [r12+4]
0x180013004  mov     ecx, [r12]
0x180013008  mov     qword ptr [rbp+var_38+4], rax
0x18001300c  mov     rax, [rbp+hMem]
0x180013010  mov     [rbp-28h], rax
0x180013014  mov     eax, [rbp+arg_28]
0x180013017  mov     dword ptr [rbp+var_38], ecx
0x18001301a  lea     rcx, [rsi+88h]
0x180013021  mov     dword ptr [rbp+var_24+0Ch], eax
0x180013024  mov     rax, [rcx+8]
0x180013028  mov     dword ptr [rbp+var_38+0Ch], r14d
0x18001302c  mov     qword ptr [rbp+var_24+4], rdi
0x180013030  cmp     rax, [rcx+10h]
0x180013034  jz      short loc_180013083
0x180013036  movups  xmm0, [rbp+var_38]
0x18001303a  movups  xmm1, xmmword ptr [rbp-28h]
0x18001303e  movups  xmmword ptr [rax], xmm0
0x180013041  movsd   xmm0, qword ptr [rbp+var_24+0Ch]
0x180013046  movups  xmmword ptr [rax+10h], xmm1
0x18001304a  movsd   qword ptr [rax+20h], xmm0
0x18001304f  add     qword ptr [rcx+8], 28h ; '('
0x180013054  mov     [rbp+hMem], 0
0x18001305c  mov     rcx, [rbp+hMem]; hMem
0x180013060  call    cs:__imp_LocalFree
0x180013066  mov     eax, ebx
0x180013068  mov     rcx, [rbp+var_10]
0x18001306c  xor     rcx, rsp; StackCookie
0x18001306f  call    __security_check_cookie
0x180013074  add     rsp, 70h
0x180013078  pop     r15
0x18001307a  pop     r14
0x18001307c  pop     r12
0x18001307e  pop     rdi
0x18001307f  pop     rsi
0x180013080  pop     rbx
0x180013081  pop     rbp
0x180013082  retn
0x180013083  lea     rdx, [rbp+var_38]
0x180013087  call    ??$_PushBackOne2@AEBUBulkUpdateEntry@IndexedFiltering@@@?$vector@UBulkUpdateEntry@IndexedFiltering@@V?$allocator@UBulkUpdateEntry@IndexedFiltering@@@utl@@@utl@@AEAA_NAEBUBulkUpdateEntry@IndexedFiltering@@@Z; utl::vector<IndexedFiltering::BulkUpdateEntry,utl::allocator<IndexedFiltering::BulkUpdateEntry>>::_PushBackOne2<IndexedFiltering::BulkUpdateEntry const &>(IndexedFiltering::BulkUpdateEntry const &)
0x18001308c  test    al, al
0x18001308e  jnz     short loc_180013054
0x180013090  mov     ebx, 80004005h
0x180013095  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001309c  mov     ecx, ebx
0x18001309e  mov     r9d, 3E6h
0x1800130a4  mov     edx, 1
0x1800130a9  call    Log_HREvent
0x1800130ae  jmp     short loc_18001305C
```
