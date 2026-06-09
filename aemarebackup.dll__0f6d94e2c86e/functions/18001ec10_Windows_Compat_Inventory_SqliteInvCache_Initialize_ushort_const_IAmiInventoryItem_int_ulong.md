# Windows::Compat::Inventory::SqliteInvCache::Initialize(ushort const *,IAmiInventoryItem *,int,ulong)

- ea: `0x18001ec10`
- end: `0x18001efae`
- name: `?Initialize@SqliteInvCache@Inventory@Compat@Windows@@QEAAJPEBGPEAVIAmiInventoryItem@@HK@Z`
- size: `926`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::SqliteInvCache *__hidden this, const unsigned __int16 *Src, struct IAmiInventoryItem *, int, unsigned int)`
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x18001efb4`

## callees

- `0x180004ea0`
- `0x18000712e`
- `0x18000f050`
- `0x180010640`
- `0x1800134b8`
- `0x180013a58`
- `0x180017e44`
- `0x180017fd4`
- `0x180018c78`
- `0x18001ec10`
- `0x1800208f8`
- `0x180027038`
- `0x180027cb0`
- `0x18002aa18`
- `0x18004c020`
- `0x18008b0dc`
- `0x1800c4b00`
- `0x1800ec010`

## string_xrefs

- `0x18001ec54`: `TemplateItem cannot be null [%#x]`
- `0x18001ec97`: `TemplateItem must have a property schema defined [%#x]`
- `0x18001ecbe`: `OpenDb failed [%#x]`
- `0x18001eee5`: `CreateReadItemQuery failed [%#x]`
- `0x18001ef06`: `CreateWriteItemQuery failed [%#x]`
- `0x18001ee00`: `Windows::Compat::Inventory::SqliteInvCache::Initialize`
- `0x18001ef11`: `Windows::Compat::Inventory::SqliteInvCache::Initialize`
- `0x18001ef35`: `Windows::Compat::Inventory::SqliteInvCache::Initialize`
- `0x18001ef76`: `Windows::Compat::Inventory::SqliteInvCache::Initialize`
- `0x18001eec8`: `CreateTable failed [%#x]`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Compat::Inventory::SqliteInvCache::Initialize(
        Windows::Compat::Inventory::SqliteInvCache *this,
        const unsigned __int16 *Src,
        struct IAmiInventoryItem *a3,
        int a4)
{
  int Table; // eax
  unsigned int v9; // esi
  __int64 v10; // r8
  const char *v11; // r9
  __int64 *v12; // rax
  __int64 v13; // rdi
  __int64 v14; // rbx
  char **v15; // rax
  __int64 v16; // r8
  void **v17; // r15
  unsigned __int64 v18; // r14
  char *v19; // rbx
  size_t v20; // r14
  unsigned __int64 v21; // r12
  char *v22; // rdx
  void *v23; // rcx
  __int64 v24; // r8
  unsigned __int64 v25; // rdx
  char *v26; // r14
  __int64 v27; // rbx
  __int64 v28; // rax
  __int64 v29; // rdx
  __int64 v30; // r8
  _WORD *v31; // rbx
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 v34; // rdx
  __int64 v35; // r8
  int v36; // ebx
  const char *v37; // rax
  char *Srca; // [rsp+30h] [rbp-98h]
  char *v40[4]; // [rsp+38h] [rbp-90h] BYREF
  char *v41[4]; // [rsp+58h] [rbp-70h] BYREF

  if ( a3 )
  {
    v12 = (__int64 *)(*(__int64 (__fastcall **)(struct IAmiInventoryItem *, char **))(*(_QWORD *)a3 + 64LL))(a3, v40);
    v13 = *v12;
    v14 = v12[1];
    std::vector<IAmiInventoryItem::_CacheItemProperty>::~vector<IAmiInventoryItem::_CacheItemProperty>(v40);
    if ( v13 == v14 )
    {
      Table = -2147024809;
      v9 = -2147024809;
      v10 = 558;
      v11 = "TemplateItem must have a property schema defined [%#x]";
    }
    else
    {
      Table = Windows::Compat::Inventory::SqliteInvCache::OpenDb(Src, (struct sqlite3 **)this + 1, a4);
      v9 = Table;
      if ( Table >= 0 )
      {
        *((_BYTE *)this + 168) = a4 != 0;
        v15 = (char **)(*(__int64 (__fastcall **)(struct IAmiInventoryItem *, char **))(*(_QWORD *)a3 + 64LL))(a3, v40);
        v17 = (void **)((char *)this + 136);
        if ( (char **)((char *)this + 136) != v15 )
        {
          Srca = *v15;
          v18 = (v15[1] - *v15) >> 4;
          v19 = (char *)*v17;
          if ( v18 <= (__int64)(*((_QWORD *)this + 19) - *((_QWORD *)this + 17)) >> 4 )
          {
            v21 = (__int64)(*((_QWORD *)this + 18) - (_QWORD)v19) >> 4;
            v22 = *v15;
            v23 = *v17;
            if ( v18 > v21 )
            {
              memmove_0(v23, v22, 16 * v21);
              v19 = (char *)*((_QWORD *)this + 18);
              v18 -= v21;
              v22 = &Srca[16 * v21];
              v23 = v19;
            }
            v20 = 16 * v18;
            memmove_0(v23, v22, v20);
          }
          else
          {
            std::vector<IAmiInventoryItem::_CacheItemProperty>::_Clear_and_reserve_geometric(
              (void **)this + 17,
              v18,
              v16);
            v19 = (char *)*v17;
            v20 = 16 * v18;
            memmove_0(*v17, Srca, v20);
          }
          *((_QWORD *)this + 18) = &v19[v20];
        }
        std::vector<IAmiInventoryItem::_CacheItemProperty>::~vector<IAmiInventoryItem::_CacheItemProperty>(v40);
        v25 = -1;
        do
          ++v25;
        while ( Src[v25] );
        if ( v25 > *((_QWORD *)this + 12) )
        {
          std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
            (char *)this + 72,
            v25,
            v24,
            Src);
        }
        else
        {
          if ( *((_QWORD *)this + 12) <= 7u )
            v26 = (char *)this + 72;
          else
            v26 = (char *)*((_QWORD *)this + 9);
          *((_QWORD *)this + 11) = v25;
          v27 = 2 * v25;
          memmove_0(v26, Src, 2 * v25);
          *(_WORD *)&v26[v27] = 0;
        }
        if ( !*((_QWORD *)this + 11) )
        {
          AslLogCallPrintf(
            1,
            "Windows::Compat::Inventory::SqliteInvCache::Initialize",
            575,
            "Table name conversion failed");
          return v9;
        }
        v28 = std::to_wstring(v41, 0);
        std::operator+<unsigned short>(v40, v29, v28);
        std::wstring::append((char *)this + 72);
        std::wstring::~wstring(v40);
        std::wstring::~wstring(v41);
        if ( *((_QWORD *)this + 16) < 9u )
        {
          std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
            (char *)this + 104,
            9,
            v30,
            L"Metadata_");
        }
        else
        {
          v31 = (_WORD *)*((_QWORD *)this + 13);
          *((_QWORD *)this + 15) = 9;
          memmove_0(v31, L"Metadata_", 0x12u);
          v31[9] = 0;
        }
        std::to_wstring(v41, 0);
        std::wstring::append((char *)this + 104);
        std::wstring::~wstring(v41);
        Table = Windows::Compat::Inventory::SqliteInvCache::CreateTable(this);
        v9 = Table;
        if ( Table >= 0 )
        {
          Table = Windows::Compat::Inventory::SqliteInvCache::CreateReadItemQuery(this, v32, v33);
          v9 = Table;
          if ( Table >= 0 )
          {
            Table = Windows::Compat::Inventory::SqliteInvCache::CreateWriteItemQuery(this, v34, v35);
            v9 = Table;
            if ( Table >= 0 )
              return v9;
            v10 = 600;
            v11 = "CreateWriteItemQuery failed [%#x]";
          }
          else
          {
            v10 = 593;
            v11 = "CreateReadItemQuery failed [%#x]";
          }
        }
        else
        {
          v10 = 586;
          v11 = "CreateTable failed [%#x]";
        }
      }
      else
      {
        v10 = 565;
        v11 = "OpenDb failed [%#x]";
      }
    }
  }
  else
  {
    Table = -2147024809;
    v9 = -2147024809;
    v10 = 551;
    v11 = "TemplateItem cannot be null [%#x]";
  }
  AslLogCallPrintf(1, "Windows::Compat::Inventory::SqliteInvCache::Initialize", v10, v11, Table);
  if ( *((_QWORD *)this + 1) )
  {
    AslLogCallPrintf(
      3,
      "Windows::Compat::Inventory::SqliteInvCache::Initialize",
      607,
      "closing database due to failure");
    v36 = sqlite3Close(*((_QWORD *)this + 1), 0);
    if ( v36 )
    {
      v37 = (const char *)sqlite3_errmsg(*((_QWORD *)this + 1));
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::SqliteInvCache::Initialize",
        611,
        "sqlite3_close failed: [%d] %hs",
        v36,
        v37);
    }
    *((_QWORD *)this + 1) = 0;
  }
  return v9;
}

```

## disassembly

```asm
0x18001ec10  push    rbx
0x18001ec12  push    rbp
0x18001ec13  push    rsi
0x18001ec14  push    rdi
0x18001ec15  push    r12
0x18001ec17  push    r13
0x18001ec19  push    r14
0x18001ec1b  push    r15
0x18001ec1d  sub     rsp, 88h
0x18001ec24  mov     rax, cs:__security_cookie
0x18001ec2b  xor     rax, rsp
0x18001ec2e  mov     [rsp+0C8h+var_50], rax
0x18001ec33  mov     r15d, r9d
0x18001ec36  mov     r14, r8
0x18001ec39  mov     r13, rdx
0x18001ec3c  mov     rbp, rcx
0x18001ec3f  xor     r12d, r12d
0x18001ec42  test    r8, r8
0x18001ec45  jnz     short loc_18001EC60
0x18001ec47  mov     eax, 80070057h
0x18001ec4c  mov     esi, eax
0x18001ec4e  mov     r8d, 227h
0x18001ec54  lea     r9, aTemplateitemCa; "TemplateItem cannot be null [%#x]"
0x18001ec5b  jmp     loc_18001EF0D
0x18001ec60  mov     rax, [r8]
0x18001ec63  lea     rdx, [rsp+0C8h+var_90]
0x18001ec68  mov     rcx, r14
0x18001ec6b  mov     rax, [rax+40h]
0x18001ec6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec74  mov     rdi, [rax]
0x18001ec77  mov     rbx, [rax+8]
0x18001ec7b  lea     rcx, [rsp+0C8h+var_90]
0x18001ec80  call    ??1?$vector@U_CacheItemProperty@IAmiInventoryItem@@V?$allocator@U_CacheItemProperty@IAmiInventoryItem@@@std@@@std@@QEAA@XZ; std::vector<IAmiInventoryItem::_CacheItemProperty>::~vector<IAmiInventoryItem::_CacheItemProperty>(void)
0x18001ec85  cmp     rdi, rbx
0x18001ec88  jnz     short loc_18001ECA3
0x18001ec8a  mov     eax, 80070057h
0x18001ec8f  mov     esi, eax
0x18001ec91  mov     r8d, 22Eh
0x18001ec97  lea     r9, aTemplateitemMu; "TemplateItem must have a property schem"...
0x18001ec9e  jmp     loc_18001EF0D
0x18001eca3  lea     rdx, [rbp+8]; struct sqlite3 **
0x18001eca7  mov     r8d, r15d; int
0x18001ecaa  mov     rcx, r13; unsigned __int16 *
0x18001ecad  call    ?OpenDb@SqliteInvCache@Inventory@Compat@Windows@@SAJPEBGAEAPEAUsqlite3@@H@Z; Windows::Compat::Inventory::SqliteInvCache::OpenDb(ushort const *,sqlite3 * &,int)
0x18001ecb2  mov     esi, eax
0x18001ecb4  test    eax, eax
0x18001ecb6  jns     short loc_18001ECCA
0x18001ecb8  mov     r8d, 235h
0x18001ecbe  lea     r9, aOpendbFailedX; "OpenDb failed [%#x]"
0x18001ecc5  jmp     loc_18001EF0D
0x18001ecca  test    r15d, r15d
0x18001eccd  setnz   al
0x18001ecd0  mov     [rbp+0A8h], al
0x18001ecd6  mov     rax, [r14]
0x18001ecd9  lea     rdx, [rsp+0C8h+var_90]
0x18001ecde  mov     rcx, r14
0x18001ece1  mov     rax, [rax+40h]
0x18001ece5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ecea  nop
0x18001eceb  lea     r15, [rbp+88h]
0x18001ecf2  cmp     r15, rax
0x18001ecf5  jz      loc_18001ED93
0x18001ecfb  mov     rcx, [rax]
0x18001ecfe  mov     [rsp+0C8h+Src], rcx
0x18001ed03  mov     r14, [rax+8]
0x18001ed07  sub     r14, rcx
0x18001ed0a  sar     r14, 4
0x18001ed0e  mov     rbx, [r15]
0x18001ed11  mov     rax, [r15+10h]
0x18001ed15  sub     rax, rbx
0x18001ed18  sar     rax, 4
0x18001ed1c  cmp     r14, rax
0x18001ed1f  jbe     short loc_18001ED45
0x18001ed21  mov     rdx, r14
0x18001ed24  mov     rcx, r15
0x18001ed27  call    ?_Clear_and_reserve_geometric@?$vector@U_CacheItemProperty@IAmiInventoryItem@@V?$allocator@U_CacheItemProperty@IAmiInventoryItem@@@std@@@std@@AEAAX_K@Z; std::vector<IAmiInventoryItem::_CacheItemProperty>::_Clear_and_reserve_geometric(unsigned __int64)
0x18001ed2c  mov     rbx, [r15]
0x18001ed2f  shl     r14, 4
0x18001ed33  mov     r8, r14; Size
0x18001ed36  mov     rdx, [rsp+0C8h+Src]; Src
0x18001ed3b  mov     rcx, rbx; void *
0x18001ed3e  call    memmove_0
0x18001ed43  jmp     short loc_18001ED8B
0x18001ed45  mov     r12, [r15+8]
0x18001ed49  sub     r12, rbx
0x18001ed4c  sar     r12, 4
0x18001ed50  mov     rdx, rcx; Src
0x18001ed53  mov     rcx, rbx; void *
0x18001ed56  cmp     r14, r12
0x18001ed59  jbe     short loc_18001ED7C
0x18001ed5b  mov     rdi, r12
0x18001ed5e  shl     rdi, 4
0x18001ed62  mov     r8, rdi; Size
0x18001ed65  call    memmove_0
0x18001ed6a  mov     rbx, [r15+8]
0x18001ed6e  sub     r14, r12
0x18001ed71  mov     rdx, [rsp+0C8h+Src]
0x18001ed76  add     rdx, rdi; Src
0x18001ed79  mov     rcx, rbx; void *
0x18001ed7c  shl     r14, 4
0x18001ed80  mov     r8, r14; Size
0x18001ed83  call    memmove_0
0x18001ed88  xor     r12d, r12d
0x18001ed8b  lea     rax, [r14+rbx]
0x18001ed8f  mov     [r15+8], rax
0x18001ed93  lea     rcx, [rsp+0C8h+var_90]
0x18001ed98  call    ??1?$vector@U_CacheItemProperty@IAmiInventoryItem@@V?$allocator@U_CacheItemProperty@IAmiInventoryItem@@@std@@@std@@QEAA@XZ; std::vector<IAmiInventoryItem::_CacheItemProperty>::~vector<IAmiInventoryItem::_CacheItemProperty>(void)
0x18001ed9d  lea     rdi, [rbp+48h]
0x18001eda1  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001eda5  inc     rdx
0x18001eda8  cmp     [r13+rdx*2+0], r12w
0x18001edae  jnz     short loc_18001EDA5
0x18001edb0  cmp     rdx, [rdi+18h]
0x18001edb4  ja      short loc_18001EDE2
0x18001edb6  cmp     qword ptr [rdi+18h], 7
0x18001edbb  jbe     short loc_18001EDC2
0x18001edbd  mov     r14, [rdi]
0x18001edc0  jmp     short loc_18001EDC5
0x18001edc2  mov     r14, rdi
0x18001edc5  mov     [rdi+10h], rdx
0x18001edc9  lea     rbx, [rdx+rdx]
0x18001edcd  mov     r8, rbx; Size
0x18001edd0  mov     rdx, r13; Src
0x18001edd3  mov     rcx, r14; void *
0x18001edd6  call    memmove_0
0x18001eddb  mov     [rbx+r14], r12w
0x18001ede0  jmp     short loc_18001EDED
0x18001ede2  mov     r9, r13
0x18001ede5  mov     rcx, rdi
0x18001ede8  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18001eded  cmp     [rbp+58h], r12
0x18001edf1  jnz     short loc_18001EE16
0x18001edf3  lea     r9, aTableNameConve; "Table name conversion failed"
0x18001edfa  mov     r8d, 23Fh
0x18001ee00  lea     rdx, aWindowsCompatI_13; "Windows::Compat::Inventory::SqliteInvCa"...
0x18001ee07  mov     ecx, 1
0x18001ee0c  call    AslLogCallPrintf
0x18001ee11  jmp     loc_18001EF8B
0x18001ee16  xor     edx, edx
0x18001ee18  lea     rcx, [rsp+0C8h+var_70]
0x18001ee1d  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@K@Z; std::to_wstring(ulong)
0x18001ee22  nop
0x18001ee23  mov     r8, rax
0x18001ee26  lea     rcx, [rsp+0C8h+var_90]
0x18001ee2b  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG$$QEAV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring &&)
0x18001ee30  nop
0x18001ee31  mov     rdx, rax
0x18001ee34  mov     rcx, rdi; Src
0x18001ee37  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18001ee3c  nop
0x18001ee3d  lea     rcx, [rsp+0C8h+var_90]
0x18001ee42  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001ee47  nop
0x18001ee48  lea     rcx, [rsp+0C8h+var_70]
0x18001ee4d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001ee52  lea     rdi, [rbp+68h]
0x18001ee56  mov     edx, 9
0x18001ee5b  cmp     [rdi+18h], rdx
0x18001ee5f  jb      short loc_18001EE82
0x18001ee61  mov     rbx, [rdi]
0x18001ee64  mov     [rdi+10h], rdx
0x18001ee68  lea     r8d, [rdx+9]; Size
0x18001ee6c  lea     rdx, aMetadata; "Metadata_"
0x18001ee73  mov     rcx, rbx; void *
0x18001ee76  call    memmove_0
0x18001ee7b  mov     [rbx+12h], r12w
0x18001ee80  jmp     short loc_18001EE91
0x18001ee82  lea     r9, aMetadata; "Metadata_"
0x18001ee89  mov     rcx, rdi
0x18001ee8c  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18001ee91  xor     edx, edx
0x18001ee93  lea     rcx, [rsp+0C8h+var_70]
0x18001ee98  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@K@Z; std::to_wstring(ulong)
0x18001ee9d  nop
0x18001ee9e  mov     rdx, rax
0x18001eea1  mov     rcx, rdi; Src
0x18001eea4  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18001eea9  nop
0x18001eeaa  lea     rcx, [rsp+0C8h+var_70]
0x18001eeaf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001eeb4  mov     rcx, rbp; this
0x18001eeb7  call    ?CreateTable@SqliteInvCache@Inventory@Compat@Windows@@AEAAJXZ; Windows::Compat::Inventory::SqliteInvCache::CreateTable(void)
0x18001eebc  mov     esi, eax
0x18001eebe  test    eax, eax
0x18001eec0  jns     short loc_18001EED1
0x18001eec2  mov     r8d, 24Ah
0x18001eec8  lea     r9, aCreatetableFai; "CreateTable failed [%#x]"
0x18001eecf  jmp     short loc_18001EF0D
0x18001eed1  mov     rcx, rbp; this
0x18001eed4  call    ?CreateReadItemQuery@SqliteInvCache@Inventory@Compat@Windows@@AEAAJXZ; Windows::Compat::Inventory::SqliteInvCache::CreateReadItemQuery(void)
0x18001eed9  mov     esi, eax
0x18001eedb  test    eax, eax
0x18001eedd  jns     short loc_18001EEEE
0x18001eedf  mov     r8d, 251h
0x18001eee5  lea     r9, aCreatereaditem; "CreateReadItemQuery failed [%#x]"
0x18001eeec  jmp     short loc_18001EF0D
0x18001eeee  mov     rcx, rbp; this
0x18001eef1  call    ?CreateWriteItemQuery@SqliteInvCache@Inventory@Compat@Windows@@AEAAJXZ; Windows::Compat::Inventory::SqliteInvCache::CreateWriteItemQuery(void)
0x18001eef6  mov     esi, eax
0x18001eef8  test    eax, eax
0x18001eefa  jns     loc_18001EF8B
0x18001ef00  mov     r8d, 258h
0x18001ef06  lea     r9, aCreatewriteite; "CreateWriteItemQuery failed [%#x]"
0x18001ef0d  mov     [rsp+0C8h+var_A8], eax
0x18001ef11  lea     rdx, aWindowsCompatI_13; "Windows::Compat::Inventory::SqliteInvCa"...
0x18001ef18  mov     ecx, 1
0x18001ef1d  call    AslLogCallPrintf
0x18001ef22  cmp     [rbp+8], r12
0x18001ef26  jz      short loc_18001EF8B
0x18001ef28  lea     r9, aClosingDatabas; "closing database due to failure"
0x18001ef2f  mov     r8d, 25Fh
0x18001ef35  lea     rdx, aWindowsCompatI_13; "Windows::Compat::Inventory::SqliteInvCa"...
0x18001ef3c  mov     ecx, 3
0x18001ef41  call    AslLogCallPrintf
0x18001ef46  xor     edx, edx
0x18001ef48  mov     rcx, [rbp+8]
0x18001ef4c  call    sqlite3Close
0x18001ef51  mov     ebx, eax
0x18001ef53  test    eax, eax
0x18001ef55  jz      short loc_18001EF87
0x18001ef57  mov     rcx, [rbp+8]
0x18001ef5b  call    sqlite3_errmsg
0x18001ef60  mov     [rsp+0C8h+var_A0], rax
0x18001ef65  mov     [rsp+0C8h+var_A8], ebx
0x18001ef69  lea     r9, aSqlite3CloseFa; "sqlite3_close failed: [%d] %hs"
0x18001ef70  mov     r8d, 263h
0x18001ef76  lea     rdx, aWindowsCompatI_13; "Windows::Compat::Inventory::SqliteInvCa"...
0x18001ef7d  mov     ecx, 1
0x18001ef82  call    AslLogCallPrintf
0x18001ef87  mov     [rbp+8], r12
0x18001ef8b  mov     eax, esi
0x18001ef8d  mov     rcx, [rsp+0C8h+var_50]
0x18001ef92  xor     rcx, rsp; StackCookie
0x18001ef95  call    __security_check_cookie
0x18001ef9a  add     rsp, 88h
0x18001efa1  pop     r15
0x18001efa3  pop     r14
0x18001efa5  pop     r13
0x18001efa7  pop     r12
0x18001efa9  pop     rdi
0x18001efaa  pop     rsi
0x18001efab  pop     rbp
0x18001efac  pop     rbx
0x18001efad  retn
```
