# Windows::Compat::Inventory::MareApplication::Insert(Windows::Compat::Inventory::InventoryCacheItem *)

- ea: `0x18002fba0`
- end: `0x18002fde9`
- name: `?Insert@MareApplication@Inventory@Compat@Windows@@UEAAKPEAVInventoryCacheItem@234@@Z`
- size: `585`
- prototype: `unsigned int __fastcall(Windows::Compat::Inventory::MareApplication *__hidden this, struct Windows::Compat::Inventory::InventoryCacheItem *)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180004ea0`
- `0x180010738`
- `0x180011fcc`
- `0x1800134b8`
- `0x180027cb0`
- `0x18002aa18`
- `0x18002f100`
- `0x18002fba0`
- `0x18004c020`
- `0x1800ec010`

## string_xrefs

- `0x18002fbfc`: `InventoryCacheItem::SetItemProperty failed [%#x]`
- `0x18002fc56`: `InventoryCacheItem::SetItemProperty failed [%#x]`
- `0x18002fd9a`: `InventoryCacheItem::SetItemProperty failed [%#x]`
- `0x18002fc09`: `Windows::Compat::Inventory::MareApplication::Insert`
- `0x18002fc63`: `Windows::Compat::Inventory::MareApplication::Insert`
- `0x18002fda7`: `Windows::Compat::Inventory::MareApplication::Insert`
- `0x18002fd7a`: `SidState`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Compat::Inventory::MareApplication::Insert(
        Windows::Compat::Inventory::MareApplication *this,
        struct Windows::Compat::Inventory::InventoryCacheItem *a2)
{
  __int64 (__fastcall *v4)(struct Windows::Compat::Inventory::InventoryCacheItem *, const wchar_t *, unsigned __int64); // rbx
  unsigned __int64 JsonHash; // rax
  int v6; // eax
  int v7; // eax
  unsigned __int64 v8; // rcx
  __int64 v9; // rbx
  __int64 v10; // rdi
  unsigned __int64 v11; // rdx
  __int128 *p_Src; // rcx
  unsigned __int64 v13; // rdx
  __int128 *v14; // rcx
  __int128 *v15; // r8
  int v16; // eax
  unsigned __int16 v17; // bx
  char *v19[4]; // [rsp+30h] [rbp-39h] BYREF
  unsigned int v20; // [rsp+50h] [rbp-19h]
  __int128 Src; // [rsp+58h] [rbp-11h] BYREF
  unsigned __int64 v22; // [rsp+68h] [rbp-1h]
  unsigned __int64 v23; // [rsp+70h] [rbp+7h]
  char *v24[4]; // [rsp+78h] [rbp+Fh] BYREF

  v4 = *(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, const wchar_t *, unsigned __int64))(*(_QWORD *)a2 + 144LL);
  JsonHash = Windows::Compat::Inventory::MareApplication::GetJsonHash((Windows::Compat::Inventory::MareApplication *)((char *)this - 8));
  v6 = v4(a2, L"Hash", JsonHash);
  if ( v6 < 0 )
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::MareApplication::Insert",
      504,
      "InventoryCacheItem::SetItemProperty failed [%#x]",
      v6);
  if ( *((_QWORD *)this + 30) )
  {
    v7 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, const wchar_t *))(*(_QWORD *)a2 + 136LL))(
           a2,
           L"Aumids");
    if ( v7 < 0 )
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::MareApplication::Insert",
        512,
        "InventoryCacheItem::SetItemProperty failed [%#x]",
        v7);
  }
  Src = 0;
  v22 = 0;
  v8 = 7;
  v23 = 7;
  LOWORD(Src) = 0;
  v9 = *((_QWORD *)this + 9);
  v10 = *((_QWORD *)this + 10);
  if ( v9 != v10 )
  {
    do
    {
      std::wstring::wstring((__int64)v19, v9);
      v20 = *(_DWORD *)(v9 + 32);
      std::wstring::append(&Src);
      v11 = v22;
      p_Src = &Src;
      if ( v22 >= v23 )
      {
        std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(&Src);
      }
      else
      {
        ++v22;
        if ( v23 > 7 )
          p_Src = (__int128 *)Src;
        *(_DWORD *)((char *)p_Src + 2 * v11) = 58;
      }
      std::to_wstring(v24, v20);
      std::wstring::append(&Src);
      std::wstring::~wstring(v24);
      v13 = v22;
      v14 = &Src;
      if ( v22 >= v23 )
      {
        std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(&Src);
      }
      else
      {
        ++v22;
        if ( v23 > 7 )
          v14 = (__int128 *)Src;
        *(_DWORD *)((char *)v14 + 2 * v13) = 124;
      }
      std::wstring::~wstring(v19);
      v9 += 40;
    }
    while ( v9 != v10 );
    v8 = v23;
  }
  v15 = &Src;
  if ( v8 > 7 )
    v15 = (__int128 *)Src;
  v16 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCacheItem *, const wchar_t *, __int128 *))(*(_QWORD *)a2 + 136LL))(
          a2,
          L"SidState",
          v15);
  v17 = v16;
  if ( v16 < 0 )
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::MareApplication::Insert",
      529,
      "InventoryCacheItem::SetItemProperty failed [%#x]",
      v16);
  std::wstring::~wstring((char **)&Src);
  return v17;
}

```

## disassembly

```asm
0x18002fba0  mov     [rsp-8+arg_10], rbx
0x18002fba5  push    rbp
0x18002fba6  push    rsi
0x18002fba7  push    rdi
0x18002fba8  push    r12
0x18002fbaa  push    r15
0x18002fbac  lea     rbp, [rsp-37h]
0x18002fbb1  sub     rsp, 0A0h
0x18002fbb8  mov     rax, cs:__security_cookie
0x18002fbbf  xor     rax, rsp
0x18002fbc2  mov     [rbp+57h+var_28], rax
0x18002fbc6  mov     rsi, rdx
0x18002fbc9  mov     rdi, rcx
0x18002fbcc  mov     rax, [rdx]
0x18002fbcf  mov     rbx, [rax+90h]
0x18002fbd6  add     rcx, 0FFFFFFFFFFFFFFF8h; this
0x18002fbda  call    ?GetJsonHash@MareApplication@Inventory@Compat@Windows@@QEAA_KXZ; Windows::Compat::Inventory::MareApplication::GetJsonHash(void)
0x18002fbdf  mov     r8, rax
0x18002fbe2  lea     rdx, aHash; "Hash"
0x18002fbe9  mov     rcx, rsi
0x18002fbec  mov     rax, rbx
0x18002fbef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fbf4  test    eax, eax
0x18002fbf6  jns     short loc_18002FC1A
0x18002fbf8  mov     [rsp+0C0h+var_A0], eax
0x18002fbfc  lea     r9, aInventorycache_8; "InventoryCacheItem::SetItemProperty fai"...
0x18002fc03  mov     r8d, 1F8h
0x18002fc09  lea     rdx, aWindowsCompatI_34; "Windows::Compat::Inventory::MareApplica"...
0x18002fc10  mov     ecx, 1
0x18002fc15  call    AslLogCallPrintf
0x18002fc1a  cmp     qword ptr [rdi+0F0h], 0
0x18002fc22  jz      short loc_18002FC74
0x18002fc24  mov     rax, [rsi]
0x18002fc27  lea     r8, [rdi+0E0h]
0x18002fc2e  cmp     qword ptr [r8+18h], 7
0x18002fc33  jbe     short loc_18002FC38
0x18002fc35  mov     r8, [r8]
0x18002fc38  lea     rdx, aAumids; "Aumids"
0x18002fc3f  mov     rcx, rsi
0x18002fc42  mov     rax, [rax+88h]
0x18002fc49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fc4e  test    eax, eax
0x18002fc50  jns     short loc_18002FC74
0x18002fc52  mov     [rsp+0C0h+var_A0], eax
0x18002fc56  lea     r9, aInventorycache_8; "InventoryCacheItem::SetItemProperty fai"...
0x18002fc5d  mov     r8d, 200h
0x18002fc63  lea     rdx, aWindowsCompatI_34; "Windows::Compat::Inventory::MareApplica"...
0x18002fc6a  mov     ecx, 1
0x18002fc6f  call    AslLogCallPrintf
0x18002fc74  xorps   xmm0, xmm0
0x18002fc77  movups  [rbp+57h+Src], xmm0
0x18002fc7b  mov     [rbp+57h+var_58], 0
0x18002fc83  mov     ecx, 7
0x18002fc88  mov     [rbp+57h+var_50], rcx
0x18002fc8c  xor     eax, eax
0x18002fc8e  mov     word ptr [rbp+57h+Src], ax
0x18002fc92  mov     rbx, [rdi+48h]
0x18002fc96  mov     rdi, [rdi+50h]
0x18002fc9a  cmp     rbx, rdi
0x18002fc9d  jz      loc_18002FD6A
0x18002fca3  lea     r15d, [rcx+33h]
0x18002fca7  lea     r12d, [rcx+75h]
0x18002fcab  mov     rdx, rbx
0x18002fcae  lea     rcx, [rbp+57h+var_90]
0x18002fcb2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002fcb7  mov     eax, [rbx+20h]
0x18002fcba  mov     [rbp+57h+var_70], eax
0x18002fcbd  lea     rdx, [rbp+57h+var_90]
0x18002fcc1  lea     rcx, [rbp+57h+Src]; Src
0x18002fcc5  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18002fcca  mov     rdx, [rbp+57h+var_58]
0x18002fcce  lea     rcx, [rbp+57h+Src]; Src
0x18002fcd2  cmp     rdx, [rbp+57h+var_50]
0x18002fcd6  jnb     short loc_18002FCF3
0x18002fcd8  lea     rax, [rdx+1]
0x18002fcdc  mov     [rbp+57h+var_58], rax
0x18002fce0  cmp     [rbp+57h+var_50], 7
0x18002fce5  cmova   rcx, qword ptr [rbp+57h+Src]
0x18002fcea  mov     dword ptr [rcx+rdx*2], 3Ah ; ':'
0x18002fcf1  jmp     short loc_18002FCFB
0x18002fcf3  mov     r9d, r15d
0x18002fcf6  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x18002fcfb  mov     edx, [rbp+57h+var_70]
0x18002fcfe  lea     rcx, [rbp+57h+var_48]
0x18002fd02  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@K@Z; std::to_wstring(ulong)
0x18002fd07  nop
0x18002fd08  mov     rdx, rax
0x18002fd0b  lea     rcx, [rbp+57h+Src]; Src
0x18002fd0f  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18002fd14  nop
0x18002fd15  lea     rcx, [rbp+57h+var_48]
0x18002fd19  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002fd1e  mov     rdx, [rbp+57h+var_58]
0x18002fd22  lea     rcx, [rbp+57h+Src]; Src
0x18002fd26  cmp     rdx, [rbp+57h+var_50]
0x18002fd2a  jnb     short loc_18002FD47
0x18002fd2c  lea     rax, [rdx+1]
0x18002fd30  mov     [rbp+57h+var_58], rax
0x18002fd34  cmp     [rbp+57h+var_50], 7
0x18002fd39  cmova   rcx, qword ptr [rbp+57h+Src]
0x18002fd3e  mov     dword ptr [rcx+rdx*2], 7Ch ; '|'
0x18002fd45  jmp     short loc_18002FD50
0x18002fd47  mov     r9d, r12d
0x18002fd4a  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x18002fd4f  nop
0x18002fd50  lea     rcx, [rbp+57h+var_90]
0x18002fd54  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002fd59  add     rbx, 28h ; '('
0x18002fd5d  cmp     rbx, rdi
0x18002fd60  jnz     loc_18002FCAB
0x18002fd66  mov     rcx, [rbp+57h+var_50]
0x18002fd6a  mov     rax, [rsi]
0x18002fd6d  lea     r8, [rbp+57h+Src]
0x18002fd71  cmp     rcx, 7
0x18002fd75  cmova   r8, qword ptr [rbp+57h+Src]
0x18002fd7a  lea     rdx, aSidstate; "SidState"
0x18002fd81  mov     rcx, rsi
0x18002fd84  mov     rax, [rax+88h]
0x18002fd8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fd90  mov     ebx, eax
0x18002fd92  test    eax, eax
0x18002fd94  jns     short loc_18002FDB8
0x18002fd96  mov     [rsp+0C0h+var_A0], eax
0x18002fd9a  lea     r9, aInventorycache_8; "InventoryCacheItem::SetItemProperty fai"...
0x18002fda1  mov     r8d, 211h
0x18002fda7  lea     rdx, aWindowsCompatI_34; "Windows::Compat::Inventory::MareApplica"...
0x18002fdae  mov     ecx, 1
0x18002fdb3  call    AslLogCallPrintf
0x18002fdb8  movzx   ebx, bx
0x18002fdbb  lea     rcx, [rbp+57h+Src]
0x18002fdbf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002fdc4  mov     eax, ebx
0x18002fdc6  mov     rcx, [rbp+57h+var_28]
0x18002fdca  xor     rcx, rsp; StackCookie
0x18002fdcd  call    __security_check_cookie
0x18002fdd2  mov     rbx, [rsp+0C0h+arg_10]
0x18002fdda  add     rsp, 0A0h
0x18002fde1  pop     r15
0x18002fde3  pop     r12
0x18002fde5  pop     rdi
0x18002fde6  pop     rsi
0x18002fde7  pop     rbp
0x18002fde8  retn
```
