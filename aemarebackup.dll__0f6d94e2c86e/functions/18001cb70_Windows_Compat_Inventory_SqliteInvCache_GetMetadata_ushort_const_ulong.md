# Windows::Compat::Inventory::SqliteInvCache::GetMetadata(ushort const *,ulong &)

- ea: `0x18001cb70`
- end: `0x18001ce95`
- name: `?GetMetadata@SqliteInvCache@Inventory@Compat@Windows@@UEBAJPEBGAEAK@Z`
- size: `805`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::SqliteInvCache *__hidden this, const unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x180004ea0`
- `0x18000fb60`
- `0x18001209c`
- `0x1800134b8`
- `0x18001cb70`
- `0x1800276cc`
- `0x180027d3c`
- `0x18004c020`
- `0x180059d64`
- `0x1800a494c`
- `0x1800c2b60`
- `0x1800c4b00`
- `0x1800c5440`
- `0x1800c7810`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18001cde9`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18001cde9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001cdbf`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001cdbf`
- `msvcp_win!?_Xinvalid_argument@std@@YAXPEBD@Z` at `0x18001cdfc`
- `msvcp_win!?_Xinvalid_argument@std@@YAXPEBD@Z` at `0x18001cdfc`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18001ce0f`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18001ce0f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001cd40`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001cd40`

## string_xrefs

- `0x18001ccb2`: `Windows::Compat::Inventory::SqliteInvCache::GetMetadata`
- `0x18001ce3d`: `Windows::Compat::Inventory::SqliteInvCache::GetMetadata`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Windows::Compat::Inventory::SqliteInvCache::GetMetadata(
        Windows::Compat::Inventory::SqliteInvCache *this,
        const unsigned __int16 *a2,
        unsigned int *a3)
{
  int v4; // ebx
  _QWORD *v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // rax
  __int128 *v9; // rdx
  unsigned __int64 v10; // r12
  int v11; // eax
  int v12; // edi
  __int64 v13; // r14
  unsigned int v14; // ebx
  int v15; // eax
  int v16; // esi
  __int64 v17; // rax
  const char *v18; // r9
  __int64 v19; // r8
  int i; // ebx
  _WORD *v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // r8
  _DWORD *v25; // rax
  _DWORD *v26; // rdi
  const wchar_t *v27; // rbx
  unsigned int v28; // eax
  __int64 v30; // [rsp+20h] [rbp-79h]
  __int64 v31; // [rsp+20h] [rbp-79h]
  __int64 v32; // [rsp+28h] [rbp-71h]
  __int64 v33; // [rsp+28h] [rbp-71h]
  __int64 v34; // [rsp+40h] [rbp-59h] BYREF
  wchar_t *EndPtr; // [rsp+48h] [rbp-51h] BYREF
  __int128 v36; // [rsp+50h] [rbp-49h] BYREF
  __int128 v37; // [rsp+60h] [rbp-39h]
  wchar_t *String[2]; // [rsp+70h] [rbp-29h] BYREF
  __int128 v39; // [rsp+80h] [rbp-19h]
  char *Src[4]; // [rsp+90h] [rbp-9h] BYREF

  v4 = (int)a2;
  v6 = (_QWORD *)((char *)this + 104);
  v7 = *((_QWORD *)this + 15);
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v7) < 0x12 )
    std::_Xlen_string();
  if ( v6[3] > 7u )
    v6 = (_QWORD *)*v6;
  std::wstring::wstring(Src, v6, a3, L"SELECT Value FROM ", 18, v6, v7);
  v8 = std::wstring::append(Src, L" WHERE Name = ?;");
  v36 = 0;
  v37 = 0;
  v36 = *(_OWORD *)v8;
  v37 = *(_OWORD *)(v8 + 16);
  *(_QWORD *)(v8 + 16) = 0;
  *(_QWORD *)(v8 + 24) = 7;
  *(_WORD *)v8 = 0;
  std::wstring::~wstring(Src);
  *a3 = 0;
  v34 = 0;
  v9 = &v36;
  if ( *((_QWORD *)&v37 + 1) > 7u )
    LODWORD(v9) = v36;
  v10 = -1;
  v11 = sqlite3Prepare16(*((_QWORD *)this + 1), (_DWORD)v9, -1, 128, (__int64)&v34, 0);
  v12 = v11;
  v13 = v34;
  if ( v11 )
  {
    if ( v11 > 0 )
      v14 = (unsigned __int16)v11 | 0x80070000;
    else
      v14 = v11;
    v33 = sqlite3_errmsg(*((_QWORD *)this + 1));
    LODWORD(v30) = v12;
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCache::GetMetadata",
      999,
      "sqlite3_prepare_v2 failed: [%d] %hs",
      v30,
      v33);
    goto LABEL_39;
  }
  if ( v34 )
  {
    LOBYTE(v32) = 2;
    v15 = bindText(v34, 1, v4, -2, 0, v32);
    v16 = v15;
    if ( v15 )
    {
      if ( v15 > 0 )
        v14 = (unsigned __int16)v15 | 0x80070000;
      else
        v14 = v15;
      v17 = sqlite3_errmsg(*((_QWORD *)this + 1));
      v18 = "sqlite3_bind_text16 failed: [%d] %hs";
      v19 = 1013;
LABEL_18:
      LODWORD(v31) = v16;
      AslLogCallPrintf(1, "Windows::Compat::Inventory::SqliteInvCache::GetMetadata", v19, v18, v31, v17);
      goto LABEL_39;
    }
    for ( i = 0; i < 100; ++i )
    {
      v16 = sqlite3_step(v13);
      if ( (unsigned int)(v16 - 5) > 1 )
        break;
      Sleep(5u);
    }
    if ( v16 == 101 )
    {
      v14 = -2147024894;
    }
    else
    {
      if ( v16 != 100 )
      {
        if ( v16 > 0 )
          v14 = (unsigned __int16)v16 | 0x80070000;
        else
          v14 = v16;
        v17 = sqlite3_errmsg(*((_QWORD *)this + 1));
        v18 = "sqlite3_step failed: [%d] %hs";
        v19 = 1025;
        goto LABEL_18;
      }
      v21 = (_WORD *)sqlite3_column_text16(v13, 0);
      *(_OWORD *)String = 0;
      v39 = 0;
      do
        ++v10;
      while ( v21[v10] );
      std::wstring::_Construct<1,unsigned short const *>((char **)String, v21, v10);
      v25 = (_DWORD *)_o__errno(v23, v22, v24);
      v26 = v25;
      v27 = (const wchar_t *)String;
      if ( *((_QWORD *)&v39 + 1) > 7u )
        v27 = String[0];
      EndPtr = 0;
      *v25 = 0;
      v28 = wcstoul(v27, &EndPtr, 10);
      if ( v27 == EndPtr )
      {
        std::_Xinvalid_argument("invalid stoul argument");
        __debugbreak();
      }
      if ( *v26 == 34 )
      {
        std::_Xout_of_range("stoul argument out of range");
        __debugbreak();
      }
      v14 = 0;
      *a3 = v28;
      std::wstring::~wstring((char **)String);
    }
  }
  else
  {
    v14 = -2147467259;
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCache::GetMetadata",
      1005,
      "sqlite3_prepare_v2 returned a null statement [%#x]",
      -2147467259);
  }
LABEL_39:
  if ( v13 )
    sqlite3_finalize(v13);
  std::wstring::~wstring((char **)&v36);
  return v14;
}

```

## disassembly

```asm
0x18001cb70  mov     [rsp-8+arg_18], rbx
0x18001cb75  push    rbp
0x18001cb76  push    rsi
0x18001cb77  push    rdi
0x18001cb78  push    r12
0x18001cb7a  push    r13
0x18001cb7c  push    r14
0x18001cb7e  push    r15
0x18001cb80  lea     rbp, [rsp-27h]
0x18001cb85  sub     rsp, 0C0h
0x18001cb8c  mov     rax, cs:__security_cookie
0x18001cb93  xor     rax, rsp
0x18001cb96  mov     [rbp+57h+var_40], rax
0x18001cb9a  mov     r13, r8
0x18001cb9d  mov     rbx, rdx
0x18001cba0  mov     r15, rcx
0x18001cba3  xor     esi, esi
0x18001cba5  lea     rdx, [rcx+68h]
0x18001cba9  mov     rcx, [rdx+10h]
0x18001cbad  mov     rax, 7FFFFFFFFFFFFFFEh
0x18001cbb7  sub     rax, rcx
0x18001cbba  cmp     rax, 12h
0x18001cbbe  jb      loc_18001CE8F
0x18001cbc4  cmp     qword ptr [rdx+18h], 7
0x18001cbc9  jbe     short loc_18001CBCE
0x18001cbcb  mov     rdx, [rdx]
0x18001cbce  mov     [rsp+0F0h+var_C0], rcx
0x18001cbd3  mov     [rsp+0F0h+var_C8], rdx
0x18001cbd8  mov     [rsp+0F0h+var_D0], 12h
0x18001cbe1  lea     r9, aSelectValueFro; "SELECT Value FROM "
0x18001cbe8  lea     rcx, [rbp+57h+Src]
0x18001cbec  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18001cbf1  nop
0x18001cbf2  lea     rdx, aWhereName; " WHERE Name = ?;"
0x18001cbf9  lea     rcx, [rbp+57h+Src]; Src
0x18001cbfd  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18001cc02  xorps   xmm0, xmm0
0x18001cc05  movups  [rbp+57h+var_A0], xmm0
0x18001cc09  xorps   xmm1, xmm1
0x18001cc0c  movdqu  [rbp+57h+var_90], xmm1
0x18001cc11  movups  xmm0, xmmword ptr [rax]
0x18001cc14  movups  [rbp+57h+var_A0], xmm0
0x18001cc18  movups  xmm1, xmmword ptr [rax+10h]
0x18001cc1c  movups  [rbp+57h+var_90], xmm1
0x18001cc20  mov     [rax+10h], rsi
0x18001cc24  mov     qword ptr [rax+18h], 7
0x18001cc2c  mov     [rax], si
0x18001cc2f  lea     rcx, [rbp+57h+Src]
0x18001cc33  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001cc38  nop
0x18001cc39  mov     [r13+0], esi
0x18001cc3d  mov     [rbp+57h+var_B0], rsi
0x18001cc41  lea     rdx, [rbp+57h+var_A0]
0x18001cc45  cmp     qword ptr [rbp+57h+var_90+8], 7
0x18001cc4a  cmova   rdx, qword ptr [rbp+57h+var_A0]
0x18001cc4f  mov     [rsp+0F0h+var_C8], rsi
0x18001cc54  lea     rax, [rbp+57h+var_B0]
0x18001cc58  mov     [rsp+0F0h+var_D0], rax
0x18001cc5d  mov     r9d, 80h
0x18001cc63  or      r12, 0FFFFFFFFFFFFFFFFh
0x18001cc67  mov     r8d, r12d
0x18001cc6a  mov     rcx, [r15+8]
0x18001cc6e  call    sqlite3Prepare16
0x18001cc73  mov     edi, eax
0x18001cc75  mov     r14, [rbp+57h+var_B0]
0x18001cc79  test    eax, eax
0x18001cc7b  jz      short loc_18001CCC3
0x18001cc7d  test    eax, eax
0x18001cc7f  jg      short loc_18001CC85
0x18001cc81  mov     ebx, eax
0x18001cc83  jmp     short loc_18001CC8E
0x18001cc85  movzx   ebx, di
0x18001cc88  or      ebx, 80070000h
0x18001cc8e  mov     rcx, [r15+8]
0x18001cc92  call    sqlite3_errmsg
0x18001cc97  mov     [rsp+0F0h+var_C8], rax
0x18001cc9c  mov     dword ptr [rsp+0F0h+var_D0], edi
0x18001cca0  lea     r9, aSqlite3Prepare; "sqlite3_prepare_v2 failed: [%d] %hs"
0x18001cca7  mov     r8d, 3E7h
0x18001ccad  mov     ecx, 1
0x18001ccb2  lea     rdx, aWindowsCompatI_44; "Windows::Compat::Inventory::SqliteInvCa"...
0x18001ccb9  call    AslLogCallPrintf
0x18001ccbe  jmp     loc_18001CE4F
0x18001ccc3  test    r14, r14
0x18001ccc6  jz      loc_18001CE27
0x18001cccc  mov     byte ptr [rsp+0F0h+var_C8], 2
0x18001ccd1  mov     [rsp+0F0h+var_D0], rsi
0x18001ccd6  mov     r9, 0FFFFFFFFFFFFFFFEh
0x18001ccdd  mov     r8, rbx
0x18001cce0  lea     edi, [r9+3]
0x18001cce4  mov     edx, edi
0x18001cce6  mov     rcx, r14
0x18001cce9  call    bindText
0x18001ccee  mov     esi, eax
0x18001ccf0  test    eax, eax
0x18001ccf2  jz      short loc_18001CD28
0x18001ccf4  test    eax, eax
0x18001ccf6  jg      short loc_18001CCFC
0x18001ccf8  mov     ebx, eax
0x18001ccfa  jmp     short loc_18001CD05
0x18001ccfc  movzx   ebx, si
0x18001ccff  or      ebx, 80070000h
0x18001cd05  mov     rcx, [r15+8]
0x18001cd09  call    sqlite3_errmsg
0x18001cd0e  lea     r9, aSqlite3BindTex; "sqlite3_bind_text16 failed: [%d] %hs"
0x18001cd15  mov     r8d, 3F5h
0x18001cd1b  mov     [rsp+0F0h+var_C8], rax
0x18001cd20  mov     dword ptr [rsp+0F0h+var_D0], esi
0x18001cd24  mov     ecx, edi
0x18001cd26  jmp     short loc_18001CCB2
0x18001cd28  xor     ebx, ebx
0x18001cd2a  mov     rcx, r14
0x18001cd2d  call    sqlite3_step
0x18001cd32  mov     esi, eax
0x18001cd34  lea     ecx, [rax-5]
0x18001cd37  cmp     ecx, edi
0x18001cd39  ja      short loc_18001CD4D
0x18001cd3b  mov     ecx, 5; dwMilliseconds
0x18001cd40  call    cs:__imp_Sleep
0x18001cd46  add     ebx, edi
0x18001cd48  cmp     ebx, 64h ; 'd'
0x18001cd4b  jl      short loc_18001CD2A
0x18001cd4d  cmp     esi, 65h ; 'e'
0x18001cd50  jnz     short loc_18001CD5C
0x18001cd52  mov     ebx, 80070002h
0x18001cd57  jmp     loc_18001CE4F
0x18001cd5c  cmp     esi, 64h ; 'd'
0x18001cd5f  jz      short loc_18001CD8A
0x18001cd61  test    esi, esi
0x18001cd63  jg      short loc_18001CD69
0x18001cd65  mov     ebx, esi
0x18001cd67  jmp     short loc_18001CD72
0x18001cd69  movzx   ebx, si
0x18001cd6c  or      ebx, 80070000h
0x18001cd72  mov     rcx, [r15+8]
0x18001cd76  call    sqlite3_errmsg
0x18001cd7b  lea     r9, aSqlite3StepFai; "sqlite3_step failed: [%d] %hs"
0x18001cd82  mov     r8d, 401h
0x18001cd88  jmp     short loc_18001CD1B
0x18001cd8a  xor     edx, edx
0x18001cd8c  mov     rcx, r14
0x18001cd8f  call    sqlite3_column_text16
0x18001cd94  xorps   xmm0, xmm0
0x18001cd97  movups  xmmword ptr [rbp+57h+String], xmm0
0x18001cd9b  xorps   xmm1, xmm1
0x18001cd9e  movdqu  [rbp+57h+var_70], xmm1
0x18001cda3  xor     esi, esi
0x18001cda5  inc     r12
0x18001cda8  cmp     [rax+r12*2], si
0x18001cdad  jnz     short loc_18001CDA5
0x18001cdaf  mov     r8, r12
0x18001cdb2  mov     rdx, rax
0x18001cdb5  lea     rcx, [rbp+57h+String]
0x18001cdb9  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001cdbe  nop
0x18001cdbf  call    cs:__imp__o__errno
0x18001cdc5  mov     rdi, rax
0x18001cdc8  lea     rbx, [rbp+57h+String]
0x18001cdcc  cmp     qword ptr [rbp+57h+var_70+8], 7
0x18001cdd1  cmova   rbx, [rbp+57h+String]
0x18001cdd6  mov     [rbp+57h+EndPtr], rsi
0x18001cdda  mov     [rax], esi
0x18001cddc  mov     r8d, 0Ah; Radix
0x18001cde2  lea     rdx, [rbp+57h+EndPtr]; EndPtr
0x18001cde6  mov     rcx, rbx; String
0x18001cde9  call    cs:__imp_wcstoul
0x18001cdef  cmp     rbx, [rbp+57h+EndPtr]
0x18001cdf3  jnz     short loc_18001CE03
0x18001cdf5  lea     rcx, aInvalidStoulAr; "invalid stoul argument"
0x18001cdfc  call    cs:__imp_?_Xinvalid_argument@std@@YAXPEBD@Z; std::_Xinvalid_argument(char const *)
0x18001ce02  int     3; Trap to Debugger
0x18001ce03  cmp     dword ptr [rdi], 22h ; '"'
0x18001ce06  jnz     short loc_18001CE16
0x18001ce08  lea     rcx, aStoulArgumentO; "stoul argument out of range"
0x18001ce0f  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x18001ce15  int     3; Trap to Debugger
0x18001ce16  mov     ebx, esi
0x18001ce18  mov     [r13+0], eax
0x18001ce1c  lea     rcx, [rbp+57h+String]
0x18001ce20  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001ce25  jmp     short loc_18001CE4F
0x18001ce27  mov     ebx, 80004005h
0x18001ce2c  mov     dword ptr [rsp+0F0h+var_D0], ebx
0x18001ce30  lea     r9, aSqlite3Prepare_0; "sqlite3_prepare_v2 returned a null stat"...
0x18001ce37  mov     r8d, 3EDh
0x18001ce3d  lea     rdx, aWindowsCompatI_44; "Windows::Compat::Inventory::SqliteInvCa"...
0x18001ce44  mov     ecx, 1
0x18001ce49  call    AslLogCallPrintf
0x18001ce4e  nop
0x18001ce4f  test    r14, r14
0x18001ce52  jz      short loc_18001CE5D
0x18001ce54  mov     rcx, r14
0x18001ce57  call    sqlite3_finalize
0x18001ce5c  nop
0x18001ce5d  lea     rcx, [rbp+57h+var_A0]
0x18001ce61  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001ce66  mov     eax, ebx
0x18001ce68  mov     rcx, [rbp+57h+var_40]
0x18001ce6c  xor     rcx, rsp; StackCookie
0x18001ce6f  call    __security_check_cookie
0x18001ce74  mov     rbx, [rsp+0F0h+arg_18]
0x18001ce7c  add     rsp, 0C0h
0x18001ce83  pop     r15
0x18001ce85  pop     r14
0x18001ce87  pop     r13
0x18001ce89  pop     r12
0x18001ce8b  pop     rdi
0x18001ce8c  pop     rsi
0x18001ce8d  pop     rbp
0x18001ce8e  retn
0x18001ce8f  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
