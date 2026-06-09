# FileCleanup::DeleteFilesAsNeeded(std::vector<FileCleanup::FileInfo,std::allocator<FileCleanup::FileInfo>> &,unsigned __int64)

- ea: `0x1800b3c24`
- end: `0x1800b3d50`
- name: `?DeleteFilesAsNeeded@FileCleanup@@AEAAIAEAV?$vector@UFileInfo@FileCleanup@@V?$allocator@UFileInfo@FileCleanup@@@std@@@std@@_K@Z`
- size: `300`
- prototype: `__int64 __fastcall(__int64, _QWORD *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800b3b3c`

## callees

- `0x18000d7ec`
- `0x18000e920`
- `0x180028c50`
- `0x1800b3c24`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800b3c9a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800b3c9a`

## pseudocode

```c
__int64 __fastcall FileCleanup::DeleteFilesAsNeeded(__int64 a1, _QWORD *a2, unsigned __int64 a3)
{
  unsigned __int64 v3; // rsi
  __int64 v6; // r15
  __int64 v7; // rcx
  __int64 v8; // rdx
  struct DWrite::RefString::Data *v9; // rbx
  unsigned int v10; // eax
  __int64 v11; // rdx
  unsigned int v12; // edi
  __int64 v13; // rcx
  __int64 v15; // [rsp+40h] [rbp-20h] BYREF
  __int64 v16; // [rsp+48h] [rbp-18h]
  __int64 v17; // [rsp+50h] [rbp-10h]
  __int64 v18; // [rsp+58h] [rbp-8h]
  struct DWrite::RefString::Data *v19; // [rsp+90h] [rbp+30h] BYREF

  v3 = a3;
  while ( v3 > *(unsigned int *)(a1 + 40) )
  {
    v6 = a2[1];
    if ( *a2 == v6 )
      break;
    v7 = *(_QWORD *)(a1 + 32);
    v8 = *(_QWORD *)(v6 - 8);
    v15 = v7 + 8;
    v16 = *(unsigned int *)(v7 + 4);
    v17 = v8 + 8;
    v18 = *(unsigned int *)(v8 + 4);
    DWrite::RefString::RefString(&v19, &v15);
    v9 = v19;
    v10 = DeleteFileW((LPCWSTR)v19 + 4);
    v11 = *(_QWORD *)(v6 - 8);
    v18 = v10;
    v12 = v10;
    v13 = *(unsigned int *)(a1 + 16);
    v16 = v11 + 8;
    v15 = 3;
    v17 = 1;
    EventLogger::LogGenericEvent(v13, 0x70756E61656C4346LL, 0x6574656C6544LL, &v15, 2);
    if ( v12 )
      v3 -= *(_QWORD *)(v6 - 16);
    DWrite::RefString::DecrementRef(*(struct DWrite::RefString::Data **)(a2[1] - 8LL));
    a2[1] -= 24LL;
    DWrite::RefString::DecrementRef(v9);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800b3c24  mov     [rsp-28h+arg_8], rbx
0x1800b3c29  mov     [rsp-28h+arg_10], rsi
0x1800b3c2e  push    rbp
0x1800b3c2f  push    rdi
0x1800b3c30  push    r13
0x1800b3c32  push    r14
0x1800b3c34  push    r15
0x1800b3c36  mov     rbp, rsp
0x1800b3c39  sub     rsp, 60h
0x1800b3c3d  mov     eax, [rcx+28h]
0x1800b3c40  mov     rsi, r8
0x1800b3c43  mov     r14, rdx
0x1800b3c46  mov     r13, rcx
0x1800b3c49  cmp     r8, rax
0x1800b3c4c  jbe     loc_1800B3D35
0x1800b3c52  mov     r15, [r14+8]
0x1800b3c56  cmp     [r14], r15
0x1800b3c59  jz      loc_1800B3D35
0x1800b3c5f  mov     rcx, [r13+20h]
0x1800b3c63  mov     rdx, [r15-8]
0x1800b3c67  lea     rax, [rcx+8]
0x1800b3c6b  mov     [rbp+var_20], rax
0x1800b3c6f  mov     eax, [rcx+4]
0x1800b3c72  lea     rcx, [rbp+arg_0]
0x1800b3c76  mov     [rbp+var_18], rax
0x1800b3c7a  lea     rax, [rdx+8]
0x1800b3c7e  mov     [rbp+var_10], rax
0x1800b3c82  mov     eax, [rdx+4]
0x1800b3c85  lea     rdx, [rbp+var_20]
0x1800b3c89  mov     [rbp+var_8], rax
0x1800b3c8d  call    ??$?0V?$StringSum@PEB_WPEB_W@@@RefString@DWrite@@QEAA@AEBV?$StringExpr@V?$StringSum@PEB_WPEB_W@@@@@Z; DWrite::RefString::RefString(StringExpr<StringSum<wchar_t const *,wchar_t const *>> const &)
0x1800b3c92  mov     rbx, [rbp+arg_0]
0x1800b3c96  lea     rcx, [rbx+8]; lpFileName
0x1800b3c9a  call    cs:__imp_DeleteFileW
0x1800b3ca0  mov     rdx, [r15-8]
0x1800b3ca4  lea     r9, [rbp+var_20]
0x1800b3ca8  xorps   xmm0, xmm0
0x1800b3cab  mov     dword ptr [rbp+var_8], eax
0x1800b3cae  movups  [rbp+var_30], xmm0
0x1800b3cb2  mov     ecx, dword ptr [rbp+var_30+4]
0x1800b3cb5  add     rdx, 8
0x1800b3cb9  mov     dword ptr [rbp+var_20+4], ecx
0x1800b3cbc  mov     edi, eax
0x1800b3cbe  movups  [rbp+var_30], xmm0
0x1800b3cc2  mov     ecx, dword ptr [rbp+var_30+4]
0x1800b3cc5  mov     r8, 6574656C6544h
0x1800b3ccf  mov     eax, dword ptr [rbp+var_30+0Ch]
0x1800b3cd2  mov     dword ptr [rbp+var_10+4], ecx
0x1800b3cd5  mov     ecx, [r13+10h]
0x1800b3cd9  mov     [rbp+var_18], rdx
0x1800b3cdd  mov     rdx, 70756E61656C4346h
0x1800b3ce7  mov     dword ptr [rbp+var_20], 3
0x1800b3cee  mov     dword ptr [rbp+var_10], 1
0x1800b3cf5  mov     dword ptr [rbp+var_8+4], eax
0x1800b3cf8  mov     [rsp+60h+var_40], 2
0x1800b3d01  call    ?LogGenericEvent@EventLogger@@SAXIVEventTag@@0PEBU__MIDL___MIDL_itf_serverinterface_0000_0000_0002@@_K@Z; EventLogger::LogGenericEvent(uint,EventTag,EventTag,__MIDL___MIDL_itf_serverinterface_0000_0000_0002 const *,unsigned __int64)
0x1800b3d06  test    edi, edi
0x1800b3d08  jz      short loc_1800B3D0E
0x1800b3d0a  sub     rsi, [r15-10h]
0x1800b3d0e  mov     rcx, [r14+8]
0x1800b3d12  mov     rcx, [rcx-8]; struct DWrite::RefString::Data *
0x1800b3d16  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x1800b3d1b  add     qword ptr [r14+8], 0FFFFFFFFFFFFFFE8h
0x1800b3d20  mov     rcx, rbx; struct DWrite::RefString::Data *
0x1800b3d23  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x1800b3d28  mov     eax, [r13+28h]
0x1800b3d2c  cmp     rsi, rax
0x1800b3d2f  ja      loc_1800B3C52
0x1800b3d35  lea     r11, [rsp+60h+var_s0]
0x1800b3d3a  mov     eax, esi
0x1800b3d3c  mov     rbx, [r11+38h]
0x1800b3d40  mov     rsi, [r11+40h]
0x1800b3d44  mov     rsp, r11
0x1800b3d47  pop     r15
0x1800b3d49  pop     r14
0x1800b3d4b  pop     r13
0x1800b3d4d  pop     rdi
0x1800b3d4e  pop     rbp
0x1800b3d4f  retn
```
