# ShaderDiskCacheSQLite::StoreApplicationIdentity(ShaderCacheApplicationIdentity const &)

- ea: `0x18004d23c`
- end: `0x18004d587`
- name: `?StoreApplicationIdentity@ShaderDiskCacheSQLite@@QEAAJAEBUShaderCacheApplicationIdentity@@@Z`
- size: `843`
- prototype: `__int64 __fastcall(ShaderDiskCacheSQLite *__hidden this, const struct ShaderCacheApplicationIdentity *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180042f8c`
- `0x180050a28`

## callees

- `0x18002e150`
- `0x1800334f0`
- `0x1800337f4`
- `0x180039508`
- `0x18003aec0`
- `0x18003c270`
- `0x18003ddbc`
- `0x1800449f0`
- `0x18004d23c`
- `0x180092a40`

## string_xrefs

- `0x18004d27a`: `CREATE TABLE IF NOT EXISTS app_id(id INTEGER PRIMARY KEY, exe_path TEXT, app_name TEXT, engine_name TEXT, app_version INTEGER, engine_version INTEGER, app_profile_version INTEGER)`

## pseudocode

```c
__int64 __fastcall ShaderDiskCacheSQLite::StoreApplicationIdentity(
        ShaderDiskCacheSQLite *this,
        const struct ShaderCacheApplicationIdentity *a2)
{
  int v4; // eax
  __int64 result; // rax
  __int64 v6; // rax
  int v7; // eax
  int v8; // edi
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // ebx
  int v16; // eax
  _QWORD v17[2]; // [rsp+40h] [rbp-C0h] BYREF
  _OWORD v18[23]; // [rsp+50h] [rbp-B0h] BYREF
  char v19[16]; // [rsp+1C0h] [rbp+C0h] BYREF

  v4 = sqlite3_exec(
         *((_QWORD *)this + 1),
         (unsigned int)"CREATE TABLE IF NOT EXISTS app_id(id INTEGER PRIMARY KEY, exe_path TEXT, app_name TEXT, engine_na"
                       "me TEXT, app_version INTEGER, engine_version INTEGER, app_profile_version INTEGER)",
         0,
         0,
         0);
  result = TranslateSQLiteFailure(v4);
  if ( (int)result >= 0 )
  {
    v17[0] = 0;
    v18[0] = _mm_load_si128((const __m128i *)&_xmm);
    v18[1] = _mm_load_si128((const __m128i *)&_xmm);
    v18[2] = _mm_load_si128((const __m128i *)&_xmm);
    v18[3] = _mm_load_si128((const __m128i *)&_xmm);
    v18[4] = _mm_load_si128((const __m128i *)&_xmm);
    v18[5] = _mm_load_si128((const __m128i *)&_xmm);
    v18[6] = _mm_load_si128((const __m128i *)&_xmm);
    v18[7] = _mm_load_si128((const __m128i *)&_xmm);
    v18[8] = _mm_load_si128((const __m128i *)&_xmm);
    v18[9] = _mm_load_si128((const __m128i *)&_xmm);
    v18[10] = _mm_load_si128((const __m128i *)&_xmm);
    v18[11] = _mm_load_si128((const __m128i *)&_xmm);
    v18[12] = _mm_load_si128((const __m128i *)&_xmm);
    v18[13] = _mm_load_si128((const __m128i *)&_xmm);
    v18[14] = _mm_load_si128((const __m128i *)&_xmm);
    v18[15] = _mm_load_si128((const __m128i *)&_xmm);
    v18[16] = _mm_load_si128((const __m128i *)&_xmm);
    v18[17] = _mm_load_si128((const __m128i *)&_xmm);
    v18[18] = _mm_load_si128((const __m128i *)&_xmm);
    v18[19] = _mm_load_si128((const __m128i *)&_xmm);
    v18[20] = _mm_load_si128((const __m128i *)&_xmm);
    v18[21] = _mm_load_si128((const __m128i *)&_xmm);
    v18[22] = _mm_load_si128((const __m128i *)&_xmm);
    strcpy(v19, "sion");
    v6 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&int sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>>::put(v17);
    v7 = sqlite3LockAndPrepare(*((_QWORD *)this + 1), (unsigned int)v18, 373, 128, 0, v6, 0);
    v8 = TranslateSQLiteFailure(v7);
    if ( v8 < 0 )
      goto LABEL_3;
    v9 = bindText(v17[0], 1, *(_QWORD *)a2, -2, 0, 2);
    v8 = TranslateSQLiteFailure(v9);
    if ( v8 < 0 )
      goto LABEL_3;
    v10 = bindText(v17[0], 2, *((_QWORD *)a2 + 1), -2, 0, 2);
    v8 = TranslateSQLiteFailure(v10);
    if ( v8 < 0
      || (v11 = bindText(v17[0], 3, *((_QWORD *)a2 + 2), -2, 0, 2), v8 = TranslateSQLiteFailure(v11), v8 < 0)
      || (v12 = sqlite3_bind_int64(v17[0], 4, *((_QWORD *)a2 + 3)), v8 = TranslateSQLiteFailure(v12), v8 < 0)
      || (v13 = sqlite3_bind_int64(v17[0], 5, *((_QWORD *)a2 + 4)), v8 = TranslateSQLiteFailure(v13), v8 < 0) )
    {
LABEL_3:
      wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&int sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&int sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>(v17);
      return (unsigned int)v8;
    }
    else
    {
      v14 = sqlite3_bind_int64(v17[0], 6, *((_QWORD *)a2 + 5));
      v15 = TranslateSQLiteFailure(v14);
      if ( v15 >= 0 )
      {
        v16 = sqlite3_step(v17[0]);
        v15 = TranslateSQLiteFailure(v16);
      }
      wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&int sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&int sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>(v17);
      return (unsigned int)v15;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18004d23c  mov     [rsp-8+arg_10], rbx
0x18004d241  push    rbp
0x18004d242  push    rdi
0x18004d243  push    r14
0x18004d245  lea     rbp, [rsp-0E0h]
0x18004d24d  sub     rsp, 1E0h
0x18004d254  mov     rax, cs:__security_cookie
0x18004d25b  xor     rax, rsp
0x18004d25e  mov     [rbp+0F0h+var_20], rax
0x18004d265  mov     rbx, rdx
0x18004d268  mov     rdi, rcx
0x18004d26b  mov     [rsp+1F0h+var_1D0], 0
0x18004d274  xor     r9d, r9d
0x18004d277  xor     r8d, r8d
0x18004d27a  lea     rdx, aCreateTableIfN_0; "CREATE TABLE IF NOT EXISTS app_id(id IN"...
0x18004d281  mov     rcx, [rcx+8]
0x18004d285  call    sqlite3_exec
0x18004d28a  mov     ecx, eax; int
0x18004d28c  call    ?TranslateSQLiteFailure@@YAJH@Z; TranslateSQLiteFailure(int)
0x18004d291  test    eax, eax
0x18004d293  js      loc_18004D564
0x18004d299  mov     [rsp+1F0h+var_1B0], 0
0x18004d2a2  movdqa  xmm0, cs:__xmm@5f707061204f544e4920545245534e49
0x18004d2aa  movdqa  [rsp+1F0h+var_1A0], xmm0
0x18004d2b0  movdqa  xmm1, cs:__xmm@2c687461705f657865202c6469286469
0x18004d2b8  movdqa  [rsp+1F0h+var_190], xmm1
0x18004d2be  movdqa  xmm0, cs:__xmm@6e69676e65202c656d616e5f70706120
0x18004d2c6  movdqa  [rsp+1F0h+var_180], xmm0
0x18004d2cc  movdqa  xmm1, cs:__xmm@737265765f707061202c656d616e5f65
0x18004d2d4  movdqa  [rbp+0F0h+var_170], xmm1
0x18004d2d9  movdqa  xmm0, cs:__xmm@737265765f656e69676e65202c6e6f69
0x18004d2e1  movdqa  [rbp+0F0h+var_160], xmm0
0x18004d2e6  movdqa  xmm1, cs:__xmm@656c69666f72705f707061202c6e6f69
0x18004d2ee  movdqa  [rbp+0F0h+var_150], xmm1
0x18004d2f3  movdqa  xmm0, cs:__xmm@5345554c415620296e6f69737265765f
0x18004d2fb  movdqa  [rbp+0F0h+var_140], xmm0
0x18004d300  movdqa  xmm1, cs:__xmm@202c3f202c3f202c3f202c3f202c3028
0x18004d308  movdqa  [rbp+0F0h+var_130], xmm1
0x18004d30d  movdqa  xmm0, cs:__xmm@43494c464e4f43204e4f20293f202c3f
0x18004d315  movdqa  [rbp+0F0h+var_120], xmm0
0x18004d31a  movdqa  xmm1, cs:__xmm@2054455320455441445055204f442054
0x18004d322  movdqa  [rbp+0F0h+var_110], xmm1
0x18004d327  movdqa  xmm0, cs:__xmm@6564756c6378653d687461705f657865
0x18004d32f  movdqa  [rbp+0F0h+var_100], xmm0
0x18004d334  movdqa  xmm1, cs:__xmm@5f707061202c687461705f6578652e64
0x18004d33c  movdqa  [rbp+0F0h+var_F0], xmm1
0x18004d341  movdqa  xmm0, cs:__xmm@70612e646564756c6378653d656d616e
0x18004d349  movdqa  [rbp+0F0h+var_E0], xmm0
0x18004d34e  movdqa  xmm1, cs:__xmm@6e5f656e69676e65202c656d616e5f70
0x18004d356  movdqa  [rbp+0F0h+var_D0], xmm1
0x18004d35b  movdqa  xmm0, cs:__xmm@676e652e646564756c6378653d656d61
0x18004d363  movdqa  [rbp+0F0h+var_C0], xmm0
0x18004d368  movdqa  xmm1, cs:__xmm@65765f707061202c656d616e5f656e69
0x18004d370  movdqa  [rbp+0F0h+var_B0], xmm1
0x18004d375  movdqa  xmm0, cs:__xmm@612e646564756c6378653d6e6f697372
0x18004d37d  movdqa  [rbp+0F0h+var_A0], xmm0
0x18004d382  movdqa  xmm1, cs:__xmm@69676e65202c6e6f69737265765f7070
0x18004d38a  movdqa  [rbp+0F0h+var_90], xmm1
0x18004d38f  movdqa  xmm0, cs:__xmm@756c6378653d6e6f69737265765f656e
0x18004d397  movdqa  [rbp+0F0h+var_80], xmm0
0x18004d39c  movdqa  xmm1, cs:__xmm@69737265765f656e69676e652e646564
0x18004d3a4  movdqa  [rbp+0F0h+var_70], xmm1
0x18004d3ac  movdqa  xmm0, cs:__xmm@5f656c69666f72705f707061202c6e6f
0x18004d3b4  movdqa  [rbp+0F0h+var_60], xmm0
0x18004d3bc  movdqa  xmm1, cs:__xmm@646564756c6378653d6e6f6973726576
0x18004d3c4  movdqa  [rbp+0F0h+var_50], xmm1
0x18004d3cc  movdqa  xmm0, cs:__xmm@7265765f656c69666f72705f7070612e
0x18004d3d4  movdqa  [rbp+0F0h+var_40], xmm0
0x18004d3dc  mov     dword ptr [rbp+0F0h+var_30], 6E6F6973h
0x18004d3e6  mov     [rbp+0F0h+var_30+4], 0
0x18004d3ed  lea     rcx, [rsp+1F0h+var_1B0]
0x18004d3f2  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3_stmt@@$$A6AHPEAU1@@Z$1?sqlite3_finalize@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUsqlite3_stmt@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>>::put(void)
0x18004d3f7  mov     [rsp+1F0h+var_1C0], 0
0x18004d400  mov     [rsp+1F0h+var_1C8], rax
0x18004d405  mov     [rsp+1F0h+var_1D0], 0
0x18004d40e  mov     r9d, 80h
0x18004d414  mov     r8d, 175h
0x18004d41a  lea     rdx, [rsp+1F0h+var_1A0]
0x18004d41f  mov     rcx, [rdi+8]
0x18004d423  call    sqlite3LockAndPrepare
0x18004d428  mov     ecx, eax; int
0x18004d42a  call    ?TranslateSQLiteFailure@@YAJH@Z; TranslateSQLiteFailure(int)
0x18004d42f  mov     edi, eax
0x18004d431  test    eax, eax
0x18004d433  jns     short loc_18004D446
0x18004d435  lea     rcx, [rsp+1F0h+var_1B0]
0x18004d43a  call    ??1?$unique_storage@U?$resource_policy@PEAUsqlite3_stmt@@$$A6AHPEAU1@@Z$1?sqlite3_finalize@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>(void)
0x18004d43f  mov     eax, edi
0x18004d441  jmp     loc_18004D564
0x18004d446  mov     byte ptr [rsp+1F0h+var_1C8], 2
0x18004d44b  mov     [rsp+1F0h+var_1D0], 0
0x18004d454  mov     r14, 0FFFFFFFFFFFFFFFEh
0x18004d45b  mov     r9, r14
0x18004d45e  mov     r8, [rbx]
0x18004d461  lea     edx, [r14+3]
0x18004d465  mov     rcx, [rsp+1F0h+var_1B0]
0x18004d46a  call    bindText
0x18004d46f  mov     ecx, eax; int
0x18004d471  call    ?TranslateSQLiteFailure@@YAJH@Z; TranslateSQLiteFailure(int)
0x18004d476  mov     edi, eax
0x18004d478  test    eax, eax
0x18004d47a  js      short loc_18004D435
0x18004d47c  mov     byte ptr [rsp+1F0h+var_1C8], 2
0x18004d481  mov     [rsp+1F0h+var_1D0], 0
0x18004d48a  mov     r9, r14
0x18004d48d  mov     r8, [rbx+8]
0x18004d491  lea     edx, [r14+4]
0x18004d495  mov     rcx, [rsp+1F0h+var_1B0]
0x18004d49a  call    bindText
0x18004d49f  mov     ecx, eax; int
0x18004d4a1  call    ?TranslateSQLiteFailure@@YAJH@Z; TranslateSQLiteFailure(int)
0x18004d4a6  mov     edi, eax
0x18004d4a8  test    eax, eax
0x18004d4aa  js      short loc_18004D435
0x18004d4ac  mov     byte ptr [rsp+1F0h+var_1C8], 2
0x18004d4b1  mov     [rsp+1F0h+var_1D0], 0
0x18004d4ba  mov     r9, r14
0x18004d4bd  mov     r8, [rbx+10h]
0x18004d4c1  lea     edx, [r14+5]
0x18004d4c5  mov     rcx, [rsp+1F0h+var_1B0]
0x18004d4ca  call    bindText
0x18004d4cf  mov     ecx, eax; int
0x18004d4d1  call    ?TranslateSQLiteFailure@@YAJH@Z; TranslateSQLiteFailure(int)
0x18004d4d6  mov     edi, eax
0x18004d4d8  test    eax, eax
0x18004d4da  js      loc_18004D435
0x18004d4e0  mov     r8, [rbx+18h]
0x18004d4e4  lea     edx, [r14+6]
0x18004d4e8  mov     rcx, [rsp+1F0h+var_1B0]
0x18004d4ed  call    sqlite3_bind_int64
0x18004d4f2  mov     ecx, eax; int
0x18004d4f4  call    ?TranslateSQLiteFailure@@YAJH@Z; TranslateSQLiteFailure(int)
0x18004d4f9  mov     edi, eax
0x18004d4fb  test    eax, eax
0x18004d4fd  js      loc_18004D435
0x18004d503  mov     r8, [rbx+20h]
0x18004d507  lea     edx, [r14+7]
0x18004d50b  mov     rcx, [rsp+1F0h+var_1B0]
0x18004d510  call    sqlite3_bind_int64
0x18004d515  mov     ecx, eax; int
0x18004d517  call    ?TranslateSQLiteFailure@@YAJH@Z; TranslateSQLiteFailure(int)
0x18004d51c  mov     edi, eax
0x18004d51e  test    eax, eax
0x18004d520  js      loc_18004D435
0x18004d526  mov     r8, [rbx+28h]
0x18004d52a  lea     edx, [r14+8]
0x18004d52e  mov     rcx, [rsp+1F0h+var_1B0]
0x18004d533  call    sqlite3_bind_int64
0x18004d538  mov     ecx, eax; int
0x18004d53a  call    ?TranslateSQLiteFailure@@YAJH@Z; TranslateSQLiteFailure(int)
0x18004d53f  mov     ebx, eax
0x18004d541  test    eax, eax
0x18004d543  js      short loc_18004D558
0x18004d545  mov     rcx, [rsp+1F0h+var_1B0]
0x18004d54a  call    sqlite3_step
0x18004d54f  mov     ecx, eax; int
0x18004d551  call    ?TranslateSQLiteFailure@@YAJH@Z; TranslateSQLiteFailure(int)
0x18004d556  mov     ebx, eax
0x18004d558  lea     rcx, [rsp+1F0h+var_1B0]
0x18004d55d  call    ??1?$unique_storage@U?$resource_policy@PEAUsqlite3_stmt@@$$A6AHPEAU1@@Z$1?sqlite3_finalize@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>(void)
0x18004d562  mov     eax, ebx
0x18004d564  mov     rcx, [rbp+0F0h+var_20]
0x18004d56b  xor     rcx, rsp; StackCookie
0x18004d56e  call    __security_check_cookie
0x18004d573  mov     rbx, [rsp+1F0h+arg_10]
0x18004d57b  add     rsp, 1E0h
0x18004d582  pop     r14
0x18004d584  pop     rdi
0x18004d585  pop     rbp
0x18004d586  retn
```
