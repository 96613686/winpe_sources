# _lambda_e714e6538ce61b4c1a38591bc1f4dacf_::operator()

- ea: `0x18003c284`
- end: `0x18003c3d3`
- name: `_lambda_e714e6538ce61b4c1a38591bc1f4dacf_::operator()`
- size: `335`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180068e90`

## callees

- `0x18002d5d0`
- `0x18003c284`
- `0x18003c3dc`
- `0x18003c500`
- `0x18003e210`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003c2c5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003c396`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003c2c5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003c396`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall lambda_e714e6538ce61b4c1a38591bc1f4dacf_::operator()(
        __int64 a1,
        struct IXmlReader *a2,
        const WCHAR *a3)
{
  __int64 v6; // r8
  _QWORD *v7; // rdx
  AppReadiness::Tasks::Store::StoreMetadata *v9; // rcx
  int v10; // [rsp+3Ch] [rbp-3Dh]
  __int64 v11; // [rsp+40h] [rbp-39h] BYREF
  char v12; // [rsp+48h] [rbp-31h]
  __int64 v13; // [rsp+50h] [rbp-29h]
  __int64 v14; // [rsp+58h] [rbp-21h] BYREF
  int v15; // [rsp+64h] [rbp-15h]
  _QWORD v16[2]; // [rsp+70h] [rbp-9h] BYREF
  int v17; // [rsp+80h] [rbp+7h]
  int v18; // [rsp+84h] [rbp+Bh]
  __int64 v19; // [rsp+88h] [rbp+Fh]
  char v20; // [rsp+90h] [rbp+17h]
  __int64 v21; // [rsp+98h] [rbp+1Fh]
  _QWORD *v22; // [rsp+A8h] [rbp+2Fh]

  if ( CompareStringOrdinal(L"Ats", -1, a3, -1, 0) == 2 )
  {
    v14 = **(_QWORD **)(a1 + 8);
    v10 = v15;
    std::tuple<AppReadiness::Tasks::Store::StoreMetadata *,std::_Ph<1>,AppReadiness::Tasks::Store::AppTileInfo *>::tuple<AppReadiness::Tasks::Store::StoreMetadata *,std::_Ph<1>,AppReadiness::Tasks::Store::AppTileInfo *>(
      (int)&v11,
      a1,
      v6,
      (__int64)&v14);
    v16[0] = &std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,void (AppReadiness::Tasks::Store::StoreMetadata::*)(IXmlReader *,AppReadiness::Tasks::Store::StoreProductInfo *),AppReadiness::Tasks::Store::StoreMetadata * const &,std::_Ph<1> const &,AppReadiness::Tasks::Store::StoreProductInfo *>,void,IXmlReader *>::`vftable';
    v16[1] = AppReadiness::Tasks::Store::StoreMetadata::ReadAt;
    v17 = 0;
    v18 = v10;
    v19 = v11;
    v20 = v12;
    v21 = v13;
    v22 = v16;
    AppReadiness::Tasks::Store::ReadArray(a2, L"At", v16);
    if ( v22 )
    {
      v7 = v16;
      LOBYTE(v7) = v22 != v16;
      (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v22 + 32LL))(v22, v7);
    }
    return 0;
  }
  if ( CompareStringOrdinal(L"C", -1, a3, 1, 0) == 2 )
  {
    AppReadiness::Tasks::Store::StoreMetadata::ReadC(
      v9,
      a2,
      **(struct AppReadiness::Tasks::Store::StoreProductInfo ***)(a1 + 8));
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x18003c284  mov     [rsp-8+arg_18], rbx
0x18003c289  push    rbp
0x18003c28a  push    rsi
0x18003c28b  push    rdi
0x18003c28c  lea     rbp, [rsp-47h]
0x18003c291  sub     rsp, 0C0h
0x18003c298  mov     rax, cs:__security_cookie
0x18003c29f  xor     rax, rsp
0x18003c2a2  mov     [rbp+57h+var_20], rax
0x18003c2a6  mov     rsi, r8
0x18003c2a9  mov     rdi, rdx
0x18003c2ac  mov     rbx, rcx
0x18003c2af  mov     [rsp+0D0h+bIgnoreCase], 0; bIgnoreCase
0x18003c2b7  or      r9d, 0FFFFFFFFh; cchCount2
0x18003c2bb  or      edx, r9d; cchCount1
0x18003c2be  lea     rcx, aAts_0; "Ats"
0x18003c2c5  call    cs:__imp_CompareStringOrdinal
0x18003c2cb  cmp     eax, 2
0x18003c2ce  jnz     loc_18003C37B
0x18003c2d4  mov     rax, [rbx+8]
0x18003c2d8  mov     rcx, [rax]
0x18003c2db  mov     [rbp+57h+var_78], rcx
0x18003c2df  lea     rax, ?ReadAt@StoreMetadata@Store@Tasks@AppReadiness@@AEAAXPEAUIXmlReader@@PEAUStoreProductInfo@234@@Z; AppReadiness::Tasks::Store::StoreMetadata::ReadAt(IXmlReader *,AppReadiness::Tasks::Store::StoreProductInfo *)
0x18003c2e6  mov     [rbp+57h+var_A0], rax
0x18003c2ea  mov     [rbp+57h+var_98], 0
0x18003c2f1  mov     eax, [rbp+57h+var_6C]
0x18003c2f4  mov     [rbp+57h+var_94], eax
0x18003c2f7  lea     r9, [rbp+57h+var_78]
0x18003c2fb  mov     rdx, rbx
0x18003c2fe  lea     rcx, [rbp+57h+var_90]
0x18003c302  call    ??$?0AEBQEAVStoreMetadata@Store@Tasks@AppReadiness@@AEBU?$_Ph@$00@std@@PEAUAppTileInfo@123@$0A@@?$tuple@PEAVStoreMetadata@Store@Tasks@AppReadiness@@U?$_Ph@$00@std@@PEAUAppTileInfo@234@@std@@QEAA@AEBQEAVStoreMetadata@Store@Tasks@AppReadiness@@AEBU?$_Ph@$00@1@$$QEAPEAUAppTileInfo@345@@Z; std::tuple<AppReadiness::Tasks::Store::StoreMetadata *,std::_Ph<1>,AppReadiness::Tasks::Store::AppTileInfo *>::tuple<AppReadiness::Tasks::Store::StoreMetadata *,std::_Ph<1>,AppReadiness::Tasks::Store::AppTileInfo *>(AppReadiness::Tasks::Store::StoreMetadata * const &,std::_Ph<1> const &,AppReadiness::Tasks::Store::AppTileInfo * &&)
0x18003c307  lea     rcx, ??_7?$_Func_impl_no_alloc@V?$_Binder@U_Unforced@std@@P8StoreMetadata@Store@Tasks@AppReadiness@@EAAXPEAUIXmlReader@@PEAUStoreProductInfo@456@@ZAEBQEAV3456@AEBU?$_Ph@$00@2@PEAU8456@@std@@XPEAUIXmlReader@@@std@@6B@; const std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,void (AppReadiness::Tasks::Store::StoreMetadata::*)(IXmlReader *,AppReadiness::Tasks::Store::StoreProductInfo *),AppReadiness::Tasks::Store::StoreMetadata * const &,std::_Ph<1> const &,AppReadiness::Tasks::Store::StoreProductInfo *>,void,IXmlReader *>::`vftable'
0x18003c30e  mov     [rbp+57h+var_60], rcx
0x18003c312  mov     rax, [rbp+57h+var_A0]
0x18003c316  mov     [rbp+57h+var_58], rax
0x18003c31a  mov     eax, [rbp+57h+var_98]
0x18003c31d  mov     [rbp+57h+var_50], eax
0x18003c320  mov     eax, [rbp+57h+var_94]
0x18003c323  mov     [rbp+57h+var_4C], eax
0x18003c326  mov     rax, [rbp+57h+var_90]
0x18003c32a  mov     [rbp+57h+var_48], rax
0x18003c32e  mov     al, [rbp+57h+var_88]
0x18003c331  mov     [rbp+57h+var_40], al
0x18003c334  mov     rax, [rbp+57h+var_80]
0x18003c338  mov     [rbp+57h+var_38], rax
0x18003c33c  lea     rax, [rbp+57h+var_60]
0x18003c340  mov     [rbp+57h+var_28], rax
0x18003c344  lea     r8, [rbp+57h+var_60]
0x18003c348  lea     rdx, aAt_0; "At"
0x18003c34f  mov     rcx, rdi
0x18003c352  call    AppReadiness__Tasks__Store__ReadArray
0x18003c357  nop
0x18003c358  mov     rcx, [rbp+57h+var_28]
0x18003c35c  test    rcx, rcx
0x18003c35f  jz      short loc_18003C377
0x18003c361  mov     rax, [rcx]
0x18003c364  lea     rdx, [rbp+57h+var_60]
0x18003c368  cmp     rcx, rdx
0x18003c36b  setnz   dl
0x18003c36e  mov     rax, [rax+20h]
0x18003c372  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c377  xor     al, al
0x18003c379  jmp     short loc_18003C3B4
0x18003c37b  mov     [rsp+0D0h+bIgnoreCase], 0; bIgnoreCase
0x18003c383  mov     r9d, 1; cchCount2
0x18003c389  mov     r8, rsi; lpString2
0x18003c38c  or      edx, 0FFFFFFFFh; cchCount1
0x18003c38f  lea     rcx, aC; "C"
0x18003c396  call    cs:__imp_CompareStringOrdinal
0x18003c39c  cmp     eax, 2
0x18003c39f  jnz     short loc_18003C3B2
0x18003c3a1  mov     r8, [rbx+8]
0x18003c3a5  mov     r8, [r8]; struct AppReadiness::Tasks::Store::StoreProductInfo *
0x18003c3a8  mov     rdx, rdi; struct IXmlReader *
0x18003c3ab  call    ?ReadC@StoreMetadata@Store@Tasks@AppReadiness@@AEAAXPEAUIXmlReader@@PEAUStoreProductInfo@234@@Z; AppReadiness::Tasks::Store::StoreMetadata::ReadC(IXmlReader *,AppReadiness::Tasks::Store::StoreProductInfo *)
0x18003c3b0  jmp     short loc_18003C377
0x18003c3b2  mov     al, 1
0x18003c3b4  mov     rcx, [rbp+57h+var_20]
0x18003c3b8  xor     rcx, rsp; StackCookie
0x18003c3bb  call    __security_check_cookie
0x18003c3c0  mov     rbx, [rsp+0D0h+arg_18]
0x18003c3c8  add     rsp, 0C0h
0x18003c3cf  pop     rdi
0x18003c3d0  pop     rsi
0x18003c3d1  pop     rbp
0x18003c3d2  retn
```
