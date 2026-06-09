# Windows::Compat::Inventory::SqliteInvCache::RemoveItem(ushort const *)

- ea: `0x1800216c0`
- end: `0x1800219d0`
- name: `?RemoveItem@SqliteInvCache@Inventory@Compat@Windows@@UEAAJPEBG@Z`
- size: `784`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::SqliteInvCache *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180004ea0`
- `0x18001209c`
- `0x1800134b8`
- `0x1800216c0`
- `0x1800276cc`
- `0x180027d3c`
- `0x18004c020`
- `0x180059d64`
- `0x1800a494c`
- `0x1800c4b00`
- `0x1800c5440`
- `0x1800c7810`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180021926`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180021926`

## string_xrefs

- `0x18002188d`: `Windows::Compat::Inventory::SqliteInvCache::RemoveItem`
- `0x180021979`: `Windows::Compat::Inventory::SqliteInvCache::RemoveItem`
- `0x18002172c`: `DELETE FROM `

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall Windows::Compat::Inventory::SqliteInvCache::RemoveItem(
        Windows::Compat::Inventory::SqliteInvCache *this,
        const unsigned __int16 *a2,
        __int64 a3)
{
  int v3; // ebx
  _QWORD *v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int128 *v10; // rdx
  int v11; // eax
  int v12; // edi
  unsigned int v13; // ebx
  int v14; // eax
  int v15; // esi
  __int64 v16; // rax
  const char *v17; // r9
  __int64 v18; // r8
  int i; // r12d
  __int64 v21; // [rsp+20h] [rbp-79h]
  __int64 v22; // [rsp+20h] [rbp-79h]
  __int64 v23; // [rsp+28h] [rbp-71h]
  __int64 v24; // [rsp+28h] [rbp-71h]
  __int64 v25; // [rsp+40h] [rbp-59h] BYREF
  __int128 v26; // [rsp+48h] [rbp-51h] BYREF
  __int128 v27; // [rsp+58h] [rbp-41h]
  __int128 v28; // [rsp+68h] [rbp-31h] BYREF
  __int128 v29; // [rsp+78h] [rbp-21h]
  __int128 v30; // [rsp+88h] [rbp-11h] BYREF
  __int128 v31; // [rsp+98h] [rbp-1h]
  char *Src[4]; // [rsp+A8h] [rbp+Fh] BYREF

  v3 = (int)a2;
  v5 = (_QWORD *)((char *)this + 72);
  v6 = *((_QWORD *)this + 11);
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v6) < 0xC )
    std::_Xlen_string();
  if ( v5[3] > 7u )
    v5 = (_QWORD *)*v5;
  std::wstring::wstring(Src, v5, a3, L"DELETE FROM ", 12, v5, v6);
  v7 = std::wstring::append(Src, L" WHERE ");
  v30 = 0;
  v31 = 0;
  v30 = *(_OWORD *)v7;
  v31 = *(_OWORD *)(v7 + 16);
  *(_QWORD *)(v7 + 16) = 0;
  *(_QWORD *)(v7 + 24) = 7;
  *(_WORD *)v7 = 0;
  v8 = std::wstring::append(&v30, L"ItemKey");
  v28 = 0;
  v29 = 0;
  v28 = *(_OWORD *)v8;
  v29 = *(_OWORD *)(v8 + 16);
  *(_QWORD *)(v8 + 16) = 0;
  *(_QWORD *)(v8 + 24) = 7;
  *(_WORD *)v8 = 0;
  v9 = std::wstring::append(&v28, L" = ?;");
  v26 = 0;
  v27 = 0;
  v26 = *(_OWORD *)v9;
  v27 = *(_OWORD *)(v9 + 16);
  *(_QWORD *)(v9 + 16) = 0;
  *(_QWORD *)(v9 + 24) = 7;
  *(_WORD *)v9 = 0;
  std::wstring::~wstring((char **)&v28);
  std::wstring::~wstring((char **)&v30);
  std::wstring::~wstring(Src);
  v25 = 0;
  v10 = &v26;
  if ( *((_QWORD *)&v27 + 1) > 7u )
    LODWORD(v10) = v26;
  v11 = sqlite3Prepare16(*((_QWORD *)this + 1), (_DWORD)v10, -1, 128, (__int64)&v25, 0);
  v12 = v11;
  if ( v11 )
  {
    if ( v11 > 0 )
      v13 = (unsigned __int16)v11 | 0x80070000;
    else
      v13 = v11;
    v24 = sqlite3_errmsg(*((_QWORD *)this + 1));
    LODWORD(v21) = v12;
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCache::RemoveItem",
      719,
      "sqlite3_prepare_v2 failed: [%d] %hs",
      v21,
      v24);
  }
  else if ( v25 )
  {
    LOBYTE(v23) = 2;
    v14 = bindText(v25, 1, v3, -2, 0, v23);
    v15 = v14;
    if ( v14 )
    {
      if ( v14 > 0 )
        v13 = (unsigned __int16)v14 | 0x80070000;
      else
        v13 = v14;
      v16 = sqlite3_errmsg(*((_QWORD *)this + 1));
      v17 = "sqlite3_bind_text16 failed: [%d] %hs";
      v18 = 733;
    }
    else
    {
      v13 = 0;
      for ( i = 0; i < 100; ++i )
      {
        v15 = sqlite3_step(v25);
        if ( (unsigned int)(v15 - 5) > 1 )
          break;
        Sleep(5u);
      }
      if ( v15 == 101 )
        goto LABEL_28;
      if ( v15 > 0 )
        v13 = (unsigned __int16)v15 | 0x80070000;
      else
        v13 = v15;
      v16 = sqlite3_errmsg(*((_QWORD *)this + 1));
      v17 = "sqlite3_step failed: [%d] %hs";
      v18 = 740;
    }
    LODWORD(v22) = v15;
    AslLogCallPrintf(1, "Windows::Compat::Inventory::SqliteInvCache::RemoveItem", v18, v17, v22, v16);
  }
  else
  {
    v13 = -2147467259;
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCache::RemoveItem",
      725,
      "sqlite3_prepare_v2 returned a null statement [%#x]",
      -2147467259);
  }
LABEL_28:
  if ( v25 )
    sqlite3_finalize(v25);
  std::wstring::~wstring((char **)&v26);
  return v13;
}

```

## disassembly

```asm
0x1800216c0  mov     [rsp-8+arg_10], rbx
0x1800216c5  push    rbp
0x1800216c6  push    rsi
0x1800216c7  push    rdi
0x1800216c8  push    r12
0x1800216ca  push    r15
0x1800216cc  lea     rbp, [rsp-37h]
0x1800216d1  sub     rsp, 0D0h
0x1800216d8  mov     rax, cs:__security_cookie
0x1800216df  xor     rax, rsp
0x1800216e2  mov     [rbp+57h+var_28], rax
0x1800216e6  mov     rbx, rdx
0x1800216e9  mov     r15, rcx
0x1800216ec  lea     rdx, [rcx+48h]
0x1800216f0  mov     rcx, [rdx+10h]
0x1800216f4  mov     rax, 7FFFFFFFFFFFFFFEh
0x1800216fe  sub     rax, rcx
0x180021701  cmp     rax, 0Ch
0x180021705  jb      loc_1800219CA
0x18002170b  mov     edi, 7
0x180021710  cmp     [rdx+18h], rdi
0x180021714  jbe     short loc_180021719
0x180021716  mov     rdx, [rdx]
0x180021719  mov     [rsp+0F0h+var_C0], rcx
0x18002171e  mov     [rsp+0F0h+var_C8], rdx
0x180021723  mov     [rsp+0F0h+var_D0], 0Ch
0x18002172c  lea     r9, aDeleteFrom; "DELETE FROM "
0x180021733  lea     rcx, [rbp+57h+Src]
0x180021737  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18002173c  nop
0x18002173d  lea     rdx, aWhere; " WHERE "
0x180021744  lea     rcx, [rbp+57h+Src]; Src
0x180021748  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18002174d  xorps   xmm0, xmm0
0x180021750  movups  [rbp+57h+var_68], xmm0
0x180021754  xorps   xmm1, xmm1
0x180021757  movdqu  [rbp+57h+var_58], xmm1
0x18002175c  movups  xmm0, xmmword ptr [rax]
0x18002175f  movups  [rbp+57h+var_68], xmm0
0x180021763  movups  xmm1, xmmword ptr [rax+10h]
0x180021767  movups  [rbp+57h+var_58], xmm1
0x18002176b  mov     qword ptr [rax+10h], 0
0x180021773  mov     [rax+18h], rdi
0x180021777  xor     ecx, ecx
0x180021779  mov     [rax], cx
0x18002177c  lea     rdx, aItemkey; "ItemKey"
0x180021783  lea     rcx, [rbp+57h+var_68]; Src
0x180021787  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18002178c  xorps   xmm0, xmm0
0x18002178f  movups  [rbp+57h+var_88], xmm0
0x180021793  xorps   xmm1, xmm1
0x180021796  movdqu  [rbp+57h+var_78], xmm1
0x18002179b  movups  xmm0, xmmword ptr [rax]
0x18002179e  movups  [rbp+57h+var_88], xmm0
0x1800217a2  movups  xmm1, xmmword ptr [rax+10h]
0x1800217a6  movups  [rbp+57h+var_78], xmm1
0x1800217aa  mov     qword ptr [rax+10h], 0
0x1800217b2  mov     [rax+18h], rdi
0x1800217b6  xor     ecx, ecx
0x1800217b8  mov     [rax], cx
0x1800217bb  lea     rdx, asc_1800F4DA0; " = ?;"
0x1800217c2  lea     rcx, [rbp+57h+var_88]; Src
0x1800217c6  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800217cb  xorps   xmm0, xmm0
0x1800217ce  movups  [rbp+57h+var_A8], xmm0
0x1800217d2  xorps   xmm1, xmm1
0x1800217d5  movdqu  [rbp+57h+var_98], xmm1
0x1800217da  movups  xmm0, xmmword ptr [rax]
0x1800217dd  movups  [rbp+57h+var_A8], xmm0
0x1800217e1  movups  xmm1, xmmword ptr [rax+10h]
0x1800217e5  movups  [rbp+57h+var_98], xmm1
0x1800217e9  mov     qword ptr [rax+10h], 0
0x1800217f1  mov     [rax+18h], rdi
0x1800217f5  xor     ecx, ecx
0x1800217f7  mov     [rax], cx
0x1800217fa  lea     rcx, [rbp+57h+var_88]
0x1800217fe  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180021803  nop
0x180021804  lea     rcx, [rbp+57h+var_68]
0x180021808  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002180d  nop
0x18002180e  lea     rcx, [rbp+57h+Src]
0x180021812  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180021817  nop
0x180021818  mov     [rbp+57h+var_B0], 0
0x180021820  lea     rdx, [rbp+57h+var_A8]
0x180021824  cmp     qword ptr [rbp+57h+var_98+8], rdi
0x180021828  cmova   rdx, qword ptr [rbp+57h+var_A8]
0x18002182d  mov     [rsp+0F0h+var_C8], 0
0x180021836  lea     rax, [rbp+57h+var_B0]
0x18002183a  mov     [rsp+0F0h+var_D0], rax
0x18002183f  mov     r9d, 80h
0x180021845  or      r8d, 0FFFFFFFFh
0x180021849  mov     rcx, [r15+8]
0x18002184d  call    sqlite3Prepare16
0x180021852  mov     edi, eax
0x180021854  test    eax, eax
0x180021856  jz      short loc_18002189E
0x180021858  test    eax, eax
0x18002185a  jg      short loc_180021860
0x18002185c  mov     ebx, eax
0x18002185e  jmp     short loc_180021869
0x180021860  movzx   ebx, di
0x180021863  or      ebx, 80070000h
0x180021869  mov     rcx, [r15+8]
0x18002186d  call    sqlite3_errmsg
0x180021872  mov     [rsp+0F0h+var_C8], rax
0x180021877  mov     dword ptr [rsp+0F0h+var_D0], edi
0x18002187b  lea     r9, aSqlite3Prepare; "sqlite3_prepare_v2 failed: [%d] %hs"
0x180021882  mov     r8d, 2CFh
0x180021888  mov     ecx, 1
0x18002188d  lea     rdx, aWindowsCompatI_41; "Windows::Compat::Inventory::SqliteInvCa"...
0x180021894  call    AslLogCallPrintf
0x180021899  jmp     loc_18002198B
0x18002189e  cmp     [rbp+57h+var_B0], 0
0x1800218a3  jz      loc_180021963
0x1800218a9  mov     byte ptr [rsp+0F0h+var_C8], 2
0x1800218ae  mov     [rsp+0F0h+var_D0], 0
0x1800218b7  mov     r9, 0FFFFFFFFFFFFFFFEh
0x1800218be  mov     r8, rbx
0x1800218c1  lea     edi, [r9+3]
0x1800218c5  mov     edx, edi
0x1800218c7  mov     rcx, [rbp+57h+var_B0]
0x1800218cb  call    bindText
0x1800218d0  mov     esi, eax
0x1800218d2  test    eax, eax
0x1800218d4  jz      short loc_18002190A
0x1800218d6  test    eax, eax
0x1800218d8  jg      short loc_1800218DE
0x1800218da  mov     ebx, eax
0x1800218dc  jmp     short loc_1800218E7
0x1800218de  movzx   ebx, si
0x1800218e1  or      ebx, 80070000h
0x1800218e7  mov     rcx, [r15+8]
0x1800218eb  call    sqlite3_errmsg
0x1800218f0  lea     r9, aSqlite3BindTex; "sqlite3_bind_text16 failed: [%d] %hs"
0x1800218f7  mov     r8d, 2DDh
0x1800218fd  mov     [rsp+0F0h+var_C8], rax
0x180021902  mov     dword ptr [rsp+0F0h+var_D0], esi
0x180021906  mov     ecx, edi
0x180021908  jmp     short loc_18002188D
0x18002190a  xor     ebx, ebx
0x18002190c  xor     r12d, r12d
0x18002190f  mov     rcx, [rbp+57h+var_B0]
0x180021913  call    sqlite3_step
0x180021918  mov     esi, eax
0x18002191a  lea     ecx, [rax-5]
0x18002191d  cmp     ecx, edi
0x18002191f  ja      short loc_180021935
0x180021921  mov     ecx, 5; dwMilliseconds
0x180021926  call    cs:__imp_Sleep
0x18002192c  add     r12d, edi
0x18002192f  cmp     r12d, 64h ; 'd'
0x180021933  jl      short loc_18002190F
0x180021935  cmp     esi, 65h ; 'e'
0x180021938  jz      short loc_18002198B
0x18002193a  test    esi, esi
0x18002193c  jg      short loc_180021942
0x18002193e  mov     ebx, esi
0x180021940  jmp     short loc_18002194B
0x180021942  movzx   ebx, si
0x180021945  or      ebx, 80070000h
0x18002194b  mov     rcx, [r15+8]
0x18002194f  call    sqlite3_errmsg
0x180021954  lea     r9, aSqlite3StepFai; "sqlite3_step failed: [%d] %hs"
0x18002195b  mov     r8d, 2E4h
0x180021961  jmp     short loc_1800218FD
0x180021963  mov     ebx, 80004005h
0x180021968  mov     dword ptr [rsp+0F0h+var_D0], ebx
0x18002196c  lea     r9, aSqlite3Prepare_0; "sqlite3_prepare_v2 returned a null stat"...
0x180021973  mov     r8d, 2D5h
0x180021979  lea     rdx, aWindowsCompatI_41; "Windows::Compat::Inventory::SqliteInvCa"...
0x180021980  mov     ecx, 1
0x180021985  call    AslLogCallPrintf
0x18002198a  nop
0x18002198b  cmp     [rbp+57h+var_B0], 0
0x180021990  jz      short loc_18002199C
0x180021992  mov     rcx, [rbp+57h+var_B0]
0x180021996  call    sqlite3_finalize
0x18002199b  nop
0x18002199c  lea     rcx, [rbp+57h+var_A8]
0x1800219a0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800219a5  mov     eax, ebx
0x1800219a7  mov     rcx, [rbp+57h+var_28]
0x1800219ab  xor     rcx, rsp; StackCookie
0x1800219ae  call    __security_check_cookie
0x1800219b3  mov     rbx, [rsp+0F0h+arg_10]
0x1800219bb  add     rsp, 0D0h
0x1800219c2  pop     r15
0x1800219c4  pop     r12
0x1800219c6  pop     rdi
0x1800219c7  pop     rsi
0x1800219c8  pop     rbp
0x1800219c9  retn
0x1800219ca  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
