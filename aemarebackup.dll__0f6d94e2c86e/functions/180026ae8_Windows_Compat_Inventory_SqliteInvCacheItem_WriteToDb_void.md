# Windows::Compat::Inventory::SqliteInvCacheItem::WriteToDb(void)

- ea: `0x180026ae8`
- end: `0x180026f8c`
- name: `?WriteToDb@SqliteInvCacheItem@Inventory@Compat@Windows@@QEAAJXZ`
- size: `1188`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::SqliteInvCacheItem *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x180021440`

## callees

- `0x180004ea0`
- `0x18000527c`
- `0x180006eac`
- `0x180006f14`
- `0x18000fb60`
- `0x180011fcc`
- `0x1800134b8`
- `0x180026ae8`
- `0x180027714`
- `0x18004c020`
- `0x180059d64`
- `0x1800c17e0`
- `0x1800c18e0`
- `0x1800c4b00`
- `0x1800c7810`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180026e00`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180026e00`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180026eab`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180026eab`

## string_xrefs

- `0x180026c34`: `Unsupported CacheItemPropertyType '%d' for column %d in SqliteInvCacheItem.`
- `0x180026b90`: `Windows::Compat::Inventory::SqliteInvCacheItem::WriteToDb`
- `0x180026c41`: `Windows::Compat::Inventory::SqliteInvCacheItem::WriteToDb`
- `0x180026e65`: `Windows::Compat::Inventory::SqliteInvCacheItem::WriteToDb`
- `0x180026eea`: `Windows::Compat::Inventory::SqliteInvCacheItem::WriteToDb`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Compat::Inventory::SqliteInvCacheItem::WriteToDb(
        Windows::Compat::Inventory::SqliteInvCacheItem *this)
{
  DWORD v2; // esi
  __int64 v3; // rcx
  unsigned int v4; // ebx
  _QWORD *v5; // r8
  __int64 v6; // r8
  int v7; // r14d
  __int64 *v8; // rax
  __int64 v9; // rcx
  const char *v10; // rax
  int v11; // ebx
  __int64 *v12; // rcx
  __int64 v13; // rdx
  unsigned __int64 v14; // r15
  __int64 v15; // r13
  _QWORD *ThreadLocalStoragePointer; // r9
  __int64 v17; // rcx
  __int128 *v18; // r8
  int v19; // eax
  __int64 v20; // rdx
  _OWORD *v21; // rax
  int v22; // esi
  char **v23; // r8
  int v24; // r14d
  __int64 v25; // rax
  __int64 v26; // r8
  __int64 v27; // rcx
  int v28; // eax
  int v29; // esi
  __int64 *v30; // r15
  __int64 v31; // rcx
  __int64 *v32; // rax
  __int64 v33; // rcx
  const char *v34; // rax
  __int64 v35; // rax
  const char *v36; // r9
  __int64 v37; // r8
  int i; // r14d
  __int64 *v39; // rax
  __int64 v40; // rcx
  __int64 v42; // [rsp+20h] [rbp-49h]
  __int64 v43; // [rsp+28h] [rbp-41h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+30h] [rbp-39h] BYREF
  _OWORD v45[2]; // [rsp+38h] [rbp-31h] BYREF
  char *v46[4]; // [rsp+58h] [rbp-11h] BYREF
  char *v47[4]; // [rsp+78h] [rbp+Fh] BYREF

  v2 = 0;
  SystemTimeAsFileTime.dwLowDateTime = 0;
  v3 = *((_QWORD *)this + 5);
  if ( !v3 )
    return 0;
  v4 = 0;
  if ( !*((_BYTE *)this + 80) )
    return v4;
  v5 = (_QWORD *)((char *)this + 8);
  if ( *((_QWORD *)this + 4) > 7u )
    v5 = (_QWORD *)*v5;
  v7 = bindText(v3, 1, (_DWORD)v5, -2, 0, 2, SystemTimeAsFileTime);
  if ( v7 )
  {
    v8 = (__int64 *)*((_QWORD *)this + 5);
    if ( v8 )
      v9 = *v8;
    else
      v9 = 0;
    v10 = (const char *)sqlite3_errmsg(v9);
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCacheItem::WriteToDb",
      324,
      "sqlite3_bind_text16 failed: [%d] %hs",
      v7,
      v10);
    if ( v7 <= 0 )
      return (unsigned int)v7;
    v11 = (unsigned __int16)v7;
    return v11 | 0x80070000;
  }
  v12 = (__int64 *)*((_QWORD *)this + 6);
  v13 = *v12;
  if ( !((v12[1] - *v12) >> 4) )
  {
LABEL_47:
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v29 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))sqlite3_bind_int64)(
            *((_QWORD *)this + 5),
            (unsigned int)((__int64)(*(_QWORD *)(*((_QWORD *)this + 6) + 8LL) - **((_QWORD **)this + 6)) >> 4) + 2,
            SystemTimeAsFileTime);
    v30 = (__int64 *)*((_QWORD *)this + 5);
    if ( v29 )
    {
      if ( v30 )
        v31 = *v30;
      else
        v31 = 0;
      v35 = sqlite3_errmsg(v31);
      v36 = "sqlite3_bind_int64 failed: [%d] %hs";
      v37 = 367;
    }
    else
    {
      for ( i = 0; i < 100; ++i )
      {
        v29 = sqlite3_step(v30);
        if ( (unsigned int)(v29 - 5) > 1 )
          break;
        Sleep(5u);
      }
      if ( v29 == 101 )
        return v4;
      v39 = (__int64 *)*((_QWORD *)this + 5);
      if ( v39 )
        v40 = *v39;
      else
        v40 = 0;
      v35 = sqlite3_errmsg(v40);
      v36 = "sqlite3_step failed: [%d] %hs";
      v37 = 375;
    }
    LODWORD(v42) = v29;
    AslLogCallPrintf(1, "Windows::Compat::Inventory::SqliteInvCacheItem::WriteToDb", v37, v36, v42, v35);
    if ( v29 <= 0 )
      return (unsigned int)v29;
    v11 = (unsigned __int16)v29;
    return v11 | 0x80070000;
  }
  v14 = 0;
  v15 = (unsigned int)tls_index;
  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  while ( 1 )
  {
    if ( (v12[1] - v13) >> 4 <= (unsigned __int64)(int)v14 )
      std::vector<std::wstring>::_Xrange(v12, v13, v6, ThreadLocalStoragePointer);
    if ( *(_DWORD *)(v13 + 16LL * (int)v14 + 8) == 1 )
    {
      v27 = *((_QWORD *)this + 7);
      if ( *(_BYTE *)(104LL * (int)v14 + v27 + 44) )
        v28 = *(_DWORD *)(104LL * (int)v14 + v27 + 40);
      else
        v28 = 0;
      v26 = v28;
      goto LABEL_43;
    }
    if ( *(_DWORD *)(v13 + 16LL * (int)v14 + 8) == 2 )
    {
      v25 = *((_QWORD *)this + 7);
      if ( *(_BYTE *)(v25 + 104LL * (int)v14 + 56) )
        v26 = *(_QWORD *)(v25 + 104LL * (int)v14 + 48);
      else
        v26 = 0;
LABEL_43:
      v19 = sqlite3_bind_int64(*((_QWORD *)this + 5), (unsigned int)(v14 + 2), v26);
LABEL_44:
      v24 = v19;
      goto LABEL_45;
    }
    if ( *(_DWORD *)(v13 + 16LL * (int)v14 + 8) == 3 )
      break;
    if ( *(_DWORD *)(v13 + 16LL * (int)v14 + 8) == 4 )
    {
      if ( __TSS0__BA___WriteToDb_SqliteInvCacheItem_Inventory_Compat_Windows__QEAAJXZ_4HA > *(_DWORD *)(ThreadLocalStoragePointer[v15] + 4LL) )
      {
        Init_thread_header(&__TSS0__BA___WriteToDb_SqliteInvCacheItem_Inventory_Compat_Windows__QEAAJXZ_4HA);
        if ( __TSS0__BA___WriteToDb_SqliteInvCacheItem_Inventory_Compat_Windows__QEAAJXZ_4HA == -1 )
        {
          `Windows::Compat::Inventory::SqliteInvCacheItem::WriteToDb'::`16'::emptyVector = 0;
          qword_18011AB18 = 0;
          atexit((void (__cdecl *)())`Windows::Compat::Inventory::SqliteInvCacheItem::WriteToDb'::`16'::`dynamic atexit destructor for 'emptyVector'');
          Init_thread_footer(&__TSS0__BA___WriteToDb_SqliteInvCacheItem_Inventory_Compat_Windows__QEAAJXZ_4HA);
        }
      }
      v17 = *((_QWORD *)this + 7);
      if ( *(_BYTE *)(v17 + 104LL * (int)v14 + 88) )
      {
        v18 = (__int128 *)(104LL * (int)v14 + v17 + 64);
        if ( !*((_BYTE *)v18 + 24) )
          __int2c();
      }
      else
      {
        v18 = &`Windows::Compat::Inventory::SqliteInvCacheItem::WriteToDb'::`16'::emptyVector;
      }
      v19 = sqlite3_bind_blob(
              *((_QWORD *)this + 5),
              (int)v14 + 2,
              *(_QWORD *)v18,
              *((_DWORD *)v18 + 2) - *(_DWORD *)v18,
              0);
      goto LABEL_44;
    }
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCacheItem::WriteToDb",
      351,
      "Unsupported CacheItemPropertyType '%d' for column %d in SqliteInvCacheItem.",
      *(_DWORD *)(v13 + 16LL * (int)v14 + 8),
      v14);
LABEL_46:
    ++v14;
    v12 = (__int64 *)*((_QWORD *)this + 6);
    v13 = *v12;
    ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
    if ( v14 >= (v12[1] - *v12) >> 4 )
      goto LABEL_47;
  }
  v20 = 104LL * (int)v14 + *((_QWORD *)this + 7);
  if ( *(_BYTE *)(v20 + 32) )
  {
    v21 = (_OWORD *)std::wstring::wstring((__int64)v47, v20);
    v22 = v2 | 1;
  }
  else
  {
    memset(v45, 0, sizeof(v45));
    std::wstring::_Construct<1,unsigned short const *>((char **)v45, &dword_1800F6C3C, 0);
    v21 = v45;
    v22 = v2 | 2;
  }
  std::wstring::wstring((__int64)v46, (__int64)v21);
  v2 = v22 | 4;
  SystemTimeAsFileTime.dwLowDateTime = v2;
  if ( (v2 & 2) != 0 )
  {
    v2 &= ~2u;
    SystemTimeAsFileTime.dwLowDateTime = v2;
    std::wstring::~wstring((char **)v45);
  }
  if ( (v2 & 1) != 0 )
  {
    v2 &= ~1u;
    SystemTimeAsFileTime.dwLowDateTime = v2;
    std::wstring::~wstring(v47);
  }
  v23 = v46;
  if ( v46[3] > (char *)7 )
    LODWORD(v23) = v46[0];
  LOBYTE(v43) = 2;
  v24 = bindText(*((_QWORD *)this + 5), (int)v14 + 2, (_DWORD)v23, -2, 0, v43, SystemTimeAsFileTime);
  std::wstring::~wstring(v46);
LABEL_45:
  if ( !v24 )
    goto LABEL_46;
  v32 = (__int64 *)*((_QWORD *)this + 5);
  if ( v32 )
    v33 = *v32;
  else
    v33 = 0;
  v34 = (const char *)sqlite3_errmsg(v33);
  AslLogCallPrintf(
    1,
    "Windows::Compat::Inventory::SqliteInvCacheItem::WriteToDb",
    356,
    "sqlite3_bind failed: [%d] %hs",
    v24,
    v34);
  return v4;
}

```

## disassembly

```asm
0x180026ae8  mov     [rsp-8+arg_8], rbx
0x180026aed  mov     [rsp-8+arg_10], rsi
0x180026af2  push    rbp
0x180026af3  push    rdi
0x180026af4  push    r13
0x180026af6  push    r14
0x180026af8  push    r15
0x180026afa  lea     rbp, [rsp-37h]
0x180026aff  sub     rsp, 0A0h
0x180026b06  mov     rax, cs:__security_cookie
0x180026b0d  xor     rax, rsp
0x180026b10  mov     [rbp+57h+var_28], rax
0x180026b14  mov     rdi, rcx
0x180026b17  xor     esi, esi
0x180026b19  mov     [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], esi
0x180026b1c  mov     rcx, [rcx+28h]
0x180026b20  test    rcx, rcx
0x180026b23  jz      loc_180026F10
0x180026b29  xor     ebx, ebx
0x180026b2b  cmp     [rdi+50h], bl
0x180026b2e  jz      loc_180026F0C
0x180026b34  lea     r8, [rdi+8]
0x180026b38  cmp     qword ptr [r8+18h], 7
0x180026b3d  jbe     short loc_180026B42
0x180026b3f  mov     r8, [r8]
0x180026b42  mov     byte ptr [rsp+0C0h+var_98], 2
0x180026b47  mov     [rsp+0C0h+var_A0], rbx
0x180026b4c  mov     edx, 1
0x180026b51  mov     r9, 0FFFFFFFFFFFFFFFEh
0x180026b58  call    bindText
0x180026b5d  mov     r14d, eax
0x180026b60  test    eax, eax
0x180026b62  jz      short loc_180026BB7
0x180026b64  mov     rax, [rdi+28h]
0x180026b68  test    rax, rax
0x180026b6b  jz      short loc_180026B72
0x180026b6d  mov     rcx, [rax]
0x180026b70  jmp     short loc_180026B74
0x180026b72  xor     ecx, ecx
0x180026b74  call    sqlite3_errmsg
0x180026b79  mov     [rsp+0C0h+var_98], rax
0x180026b7e  mov     dword ptr [rsp+0C0h+var_A0], r14d
0x180026b83  lea     r9, aSqlite3BindTex; "sqlite3_bind_text16 failed: [%d] %hs"
0x180026b8a  mov     r8d, 144h
0x180026b90  lea     rdx, aWindowsCompatI_6; "Windows::Compat::Inventory::SqliteInvCa"...
0x180026b97  mov     ecx, 1
0x180026b9c  call    AslLogCallPrintf
0x180026ba1  test    r14d, r14d
0x180026ba4  jg      short loc_180026BAE
0x180026ba6  mov     ebx, r14d
0x180026ba9  jmp     loc_180026F0C
0x180026bae  movzx   ebx, r14w
0x180026bb2  jmp     loc_180026F06
0x180026bb7  mov     rcx, [rdi+30h]
0x180026bbb  mov     rdx, [rcx]
0x180026bbe  mov     rax, [rcx+8]
0x180026bc2  sub     rax, rdx
0x180026bc5  sar     rax, 4
0x180026bc9  test    rax, rax
0x180026bcc  jz      loc_180026DF4
0x180026bd2  xor     r15d, r15d
0x180026bd5  mov     r13d, cs:_tls_index
0x180026bdc  mov     r9, gs:58h
0x180026be5  movsxd  r14, r15d
0x180026be8  mov     rax, [rcx+8]
0x180026bec  sub     rax, rdx
0x180026bef  sar     rax, 4
0x180026bf3  cmp     rax, r14
0x180026bf6  jbe     loc_180026F3A
0x180026bfc  mov     rax, r14
0x180026bff  add     rax, rax
0x180026c02  mov     r8d, [rdx+rax*8+8]
0x180026c07  mov     ecx, r8d
0x180026c0a  sub     ecx, 1
0x180026c0d  jz      loc_180026D9E
0x180026c13  sub     ecx, 1
0x180026c16  jz      loc_180026D82
0x180026c1c  sub     ecx, 1
0x180026c1f  jz      loc_180026CBA
0x180026c25  cmp     ecx, 1
0x180026c28  jz      short loc_180026C57
0x180026c2a  mov     dword ptr [rsp+0C0h+var_98], r15d
0x180026c2f  mov     dword ptr [rsp+0C0h+var_A0], r8d
0x180026c34  lea     r9, aUnsupportedCac; "Unsupported CacheItemPropertyType '%d' "...
0x180026c3b  mov     r8d, 15Fh
0x180026c41  lea     rdx, aWindowsCompatI_6; "Windows::Compat::Inventory::SqliteInvCa"...
0x180026c48  mov     ecx, 1
0x180026c4d  call    AslLogCallPrintf
0x180026c52  jmp     loc_180026DCD
0x180026c57  mov     ecx, 4
0x180026c5c  mov     rax, [r9+r13*8]
0x180026c60  mov     ecx, [rcx+rax]
0x180026c63  cmp     cs:?$TSS0@?BA@??WriteToDb@SqliteInvCacheItem@Inventory@Compat@Windows@@QEAAJXZ@4HA, ecx
0x180026c69  jg      loc_180026F40
0x180026c6f  imul    rax, r14, 68h ; 'h'
0x180026c73  mov     rcx, [rdi+38h]
0x180026c77  xor     r10d, r10d
0x180026c7a  cmp     [rcx+rax+58h], r10b
0x180026c7f  jz      short loc_180026C92
0x180026c81  lea     r8, [rcx+40h]
0x180026c85  add     r8, rax
0x180026c88  cmp     [r8+18h], r10b
0x180026c8c  jnz     short loc_180026C99
0x180026c8e  int     2Ch; Windows NT - assertion failure
0x180026c90  jmp     short loc_180026C99
0x180026c92  lea     r8, ?emptyVector@?BA@??WriteToDb@SqliteInvCacheItem@Inventory@Compat@Windows@@QEAAJXZ@4V?$vector@EV?$allocator@E@std@@@std@@A; std::vector<uchar> `Windows::Compat::Inventory::SqliteInvCacheItem::WriteToDb(void)'::`16'::emptyVector
0x180026c99  mov     r9d, [r8+8]
0x180026c9d  sub     r9d, [r8]
0x180026ca0  lea     edx, [r15+2]
0x180026ca4  mov     [rsp+0C0h+var_A0], r10
0x180026ca9  mov     r8, [r8]
0x180026cac  mov     rcx, [rdi+28h]
0x180026cb0  call    sqlite3_bind_blob
0x180026cb5  jmp     loc_180026DC5
0x180026cba  imul    rcx, r14, 68h ; 'h'
0x180026cbe  mov     rdx, [rdi+38h]
0x180026cc2  add     rdx, rcx
0x180026cc5  cmp     byte ptr [rdx+20h], 0
0x180026cc9  jz      short loc_180026CDA
0x180026ccb  lea     rcx, [rbp+57h+var_48]
0x180026ccf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180026cd4  nop
0x180026cd5  or      esi, 1
0x180026cd8  jmp     short loc_180026D03
0x180026cda  xorps   xmm0, xmm0
0x180026cdd  movups  [rbp+57h+var_88], xmm0
0x180026ce1  xorps   xmm1, xmm1
0x180026ce4  movdqu  [rbp+57h+var_78], xmm1
0x180026ce9  xor     r8d, r8d
0x180026cec  lea     rdx, dword_1800F6C3C
0x180026cf3  lea     rcx, [rbp+57h+var_88]
0x180026cf7  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180026cfc  lea     rax, [rbp+57h+var_88]
0x180026d00  or      esi, 2
0x180026d03  mov     [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], esi
0x180026d06  mov     rdx, rax
0x180026d09  lea     rcx, [rbp+57h+var_68]
0x180026d0d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180026d12  or      esi, 4
0x180026d15  mov     [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], esi
0x180026d18  test    sil, 2
0x180026d1c  jz      short loc_180026D2E
0x180026d1e  and     esi, 0FFFFFFFDh
0x180026d21  mov     [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], esi
0x180026d24  lea     rcx, [rbp+57h+var_88]
0x180026d28  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180026d2d  nop
0x180026d2e  test    sil, 1
0x180026d32  jz      short loc_180026D44
0x180026d34  and     esi, 0FFFFFFFEh
0x180026d37  mov     [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], esi
0x180026d3a  lea     rcx, [rbp+57h+var_48]
0x180026d3e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180026d43  nop
0x180026d44  lea     r8, [rbp+57h+var_68]
0x180026d48  cmp     [rbp+57h+var_50], 7
0x180026d4d  cmova   r8, [rbp+57h+var_68]
0x180026d52  lea     edx, [r15+2]
0x180026d56  mov     byte ptr [rsp+0C0h+var_98], 2
0x180026d5b  mov     [rsp+0C0h+var_A0], 0
0x180026d64  mov     r9, 0FFFFFFFFFFFFFFFEh
0x180026d6b  mov     rcx, [rdi+28h]
0x180026d6f  call    bindText
0x180026d74  mov     r14d, eax
0x180026d77  lea     rcx, [rbp+57h+var_68]
0x180026d7b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180026d80  jmp     short loc_180026DC8
0x180026d82  imul    r8, r14, 68h ; 'h'
0x180026d86  mov     rax, [rdi+38h]
0x180026d8a  cmp     byte ptr [rax+r8+38h], 0
0x180026d90  jz      short loc_180026D99
0x180026d92  mov     r8, [rax+r8+30h]
0x180026d97  jmp     short loc_180026DB8
0x180026d99  xor     r8d, r8d
0x180026d9c  jmp     short loc_180026DB8
0x180026d9e  imul    rax, r14, 68h ; 'h'
0x180026da2  mov     rcx, [rdi+38h]
0x180026da6  cmp     byte ptr [rax+rcx+2Ch], 0
0x180026dab  jz      short loc_180026DB3
0x180026dad  mov     eax, [rax+rcx+28h]
0x180026db1  jmp     short loc_180026DB5
0x180026db3  xor     eax, eax
0x180026db5  movsxd  r8, eax
0x180026db8  lea     edx, [r15+2]
0x180026dbc  mov     rcx, [rdi+28h]
0x180026dc0  call    sqlite3_bind_int64
0x180026dc5  mov     r14d, eax
0x180026dc8  test    r14d, r14d
0x180026dcb  jnz     short loc_180026E39
0x180026dcd  inc     r15
0x180026dd0  mov     rcx, [rdi+30h]
0x180026dd4  mov     rdx, [rcx]
0x180026dd7  mov     rax, [rcx+8]
0x180026ddb  sub     rax, rdx
0x180026dde  sar     rax, 4
0x180026de2  cmp     r15, rax
0x180026de5  mov     r9, gs:58h
0x180026dee  jb      loc_180026BE5
0x180026df4  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180026dfc  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180026e00  call    cs:__imp_GetSystemTimeAsFileTime
0x180026e06  mov     rax, [rdi+30h]
0x180026e0a  mov     rdx, [rax+8]
0x180026e0e  sub     rdx, [rax]
0x180026e11  sar     rdx, 4
0x180026e15  add     edx, 2
0x180026e18  mov     r8, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x180026e1c  mov     rcx, [rdi+28h]
0x180026e20  call    sqlite3_bind_int64
0x180026e25  mov     esi, eax
0x180026e27  mov     r15, [rdi+28h]
0x180026e2b  test    eax, eax
0x180026e2d  jz      short loc_180026E91
0x180026e2f  test    r15, r15
0x180026e32  jz      short loc_180026E7B
0x180026e34  mov     rcx, [r15]
0x180026e37  jmp     short loc_180026E7D
0x180026e39  mov     rax, [rdi+28h]
0x180026e3d  test    rax, rax
0x180026e40  jz      short loc_180026E47
0x180026e42  mov     rcx, [rax]
0x180026e45  jmp     short loc_180026E49
0x180026e47  xor     ecx, ecx
0x180026e49  call    sqlite3_errmsg
0x180026e4e  mov     [rsp+0C0h+var_98], rax
0x180026e53  mov     dword ptr [rsp+0C0h+var_A0], r14d
0x180026e58  lea     r9, aSqlite3BindFai; "sqlite3_bind failed: [%d] %hs"
0x180026e5f  mov     r8d, 164h
0x180026e65  lea     rdx, aWindowsCompatI_6; "Windows::Compat::Inventory::SqliteInvCa"...
0x180026e6c  mov     ecx, 1
0x180026e71  call    AslLogCallPrintf
0x180026e76  jmp     loc_180026F0C
0x180026e7b  xor     ecx, ecx
0x180026e7d  call    sqlite3_errmsg
0x180026e82  lea     r9, aSqlite3BindInt; "sqlite3_bind_int64 failed: [%d] %hs"
0x180026e89  mov     r8d, 16Fh
0x180026e8f  jmp     short loc_180026EE1
0x180026e91  xor     r14d, r14d
0x180026e94  mov     rcx, r15
0x180026e97  call    sqlite3_step
0x180026e9c  mov     esi, eax
0x180026e9e  add     eax, 0FFFFFFFBh
0x180026ea1  cmp     eax, 1
0x180026ea4  ja      short loc_180026EBA
0x180026ea6  mov     ecx, 5; dwMilliseconds
0x180026eab  call    cs:__imp_Sleep
0x180026eb1  inc     r14d
0x180026eb4  cmp     r14d, 64h ; 'd'
0x180026eb8  jl      short loc_180026E94
0x180026eba  cmp     esi, 65h ; 'e'
0x180026ebd  jz      short loc_180026F0C
0x180026ebf  mov     rax, [rdi+28h]
0x180026ec3  test    rax, rax
0x180026ec6  jz      short loc_180026ECD
0x180026ec8  mov     rcx, [rax]
0x180026ecb  jmp     short loc_180026ECF
0x180026ecd  xor     ecx, ecx
0x180026ecf  call    sqlite3_errmsg
0x180026ed4  lea     r9, aSqlite3StepFai; "sqlite3_step failed: [%d] %hs"
0x180026edb  mov     r8d, 177h
0x180026ee1  mov     [rsp+0C0h+var_98], rax
0x180026ee6  mov     dword ptr [rsp+0C0h+var_A0], esi
0x180026eea  lea     rdx, aWindowsCompatI_6; "Windows::Compat::Inventory::SqliteInvCa"...
0x180026ef1  mov     ecx, 1
0x180026ef6  call    AslLogCallPrintf
0x180026efb  test    esi, esi
0x180026efd  jg      short loc_180026F03
0x180026eff  mov     ebx, esi
0x180026f01  jmp     short loc_180026F0C
0x180026f03  movzx   ebx, si
0x180026f06  or      ebx, 80070000h
0x180026f0c  mov     eax, ebx
0x180026f0e  jmp     short loc_180026F12
0x180026f10  xor     eax, eax
0x180026f12  mov     rcx, [rbp+57h+var_28]
0x180026f16  xor     rcx, rsp; StackCookie
0x180026f19  call    __security_check_cookie
0x180026f1e  lea     r11, [rsp+0C0h+var_20]
0x180026f26  mov     rbx, [r11+38h]
0x180026f2a  mov     rsi, [r11+40h]
0x180026f2e  mov     rsp, r11
0x180026f31  pop     r15
0x180026f33  pop     r14
0x180026f35  pop     r13
0x180026f37  pop     rdi
0x180026f38  pop     rbp
0x180026f39  retn
0x180026f3a  call    ?_Xrange@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@CAXXZ; std::vector<std::wstring>::_Xrange(void)
0x180026f40  lea     rcx, ?$TSS0@?BA@??WriteToDb@SqliteInvCacheItem@Inventory@Compat@Windows@@QEAAJXZ@4HA
0x180026f47  call    _Init_thread_header
0x180026f4c  cmp     cs:?$TSS0@?BA@??WriteToDb@SqliteInvCacheItem@Inventory@Compat@Windows@@QEAAJXZ@4HA, 0FFFFFFFFh
0x180026f53  jnz     loc_180026C6F
0x180026f59  xorps   xmm0, xmm0
0x180026f5c  movdqu  cs:?emptyVector@?BA@??WriteToDb@SqliteInvCacheItem@Inventory@Compat@Windows@@QEAAJXZ@4V?$vector@EV?$allocator@E@std@@@std@@A, xmm0; std::vector<uchar> `Windows::Compat::Inventory::SqliteInvCacheItem::WriteToDb(void)'::`16'::emptyVector
0x180026f64  mov     cs:qword_18011AB18, 0
0x180026f6f  lea     rcx, ??__FemptyVector@?BA@??WriteToDb@SqliteInvCacheItem@Inventory@Compat@Windows@@QEAAJXZ@YAXXZ; void (__cdecl *)()
0x180026f76  call    atexit
0x180026f7b  lea     rcx, ?$TSS0@?BA@??WriteToDb@SqliteInvCacheItem@Inventory@Compat@Windows@@QEAAJXZ@4HA
0x180026f82  call    _Init_thread_footer
0x180026f87  jmp     loc_180026C6F
  ... truncated ...
```
