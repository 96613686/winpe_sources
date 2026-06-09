# ShaderDiskCacheSQLite::StoreCompilerIdentity(ShaderCacheCompilerIdentity const &)

- ea: `0x18004d590`
- end: `0x18004d787`
- name: `?StoreCompilerIdentity@ShaderDiskCacheSQLite@@QEAAJAEBUShaderCacheCompilerIdentity@@@Z`
- size: `503`
- prototype: `__int64 __fastcall(ShaderDiskCacheSQLite *__hidden this, const struct ShaderCacheCompilerIdentity *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180050c98`

## callees

- `0x18002e150`
- `0x1800334f0`
- `0x1800337f4`
- `0x180039508`
- `0x18003aec0`
- `0x18003c270`
- `0x18003ddbc`
- `0x1800449f0`
- `0x18004d590`
- `0x180092a40`

## string_xrefs

- `0x18004d5ca`: `CREATE TABLE IF NOT EXISTS compiler_id(id INTEGER PRIMARY KEY, abi INTEGER, version INTEGER, family TEXT)`

## pseudocode

```c
__int64 __fastcall ShaderDiskCacheSQLite::StoreCompilerIdentity(
        ShaderDiskCacheSQLite *this,
        const struct ShaderCacheCompilerIdentity *a2)
{
  int v4; // eax
  __int64 result; // rax
  __int64 v6; // rax
  int v7; // eax
  int v8; // edi
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // ebx
  int v13; // eax
  _QWORD v14[2]; // [rsp+40h] [rbp-C0h] BYREF
  _OWORD v15[10]; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v16; // [rsp+F0h] [rbp-10h]

  v4 = sqlite3_exec(
         *((_QWORD *)this + 1),
         (unsigned int)"CREATE TABLE IF NOT EXISTS compiler_id(id INTEGER PRIMARY KEY, abi INTEGER, version INTEGER, family TEXT)",
         0,
         0,
         0);
  result = TranslateSQLiteFailure(v4);
  if ( (int)result >= 0 )
  {
    v14[0] = 0;
    v15[0] = _mm_load_si128((const __m128i *)&_xmm);
    v15[1] = _mm_load_si128((const __m128i *)&_xmm);
    v15[2] = _mm_load_si128((const __m128i *)&_xmm);
    v15[3] = _mm_load_si128((const __m128i *)&_xmm);
    v15[4] = _mm_load_si128((const __m128i *)&_xmm);
    v15[5] = _mm_load_si128((const __m128i *)&_xmm);
    v15[6] = _mm_load_si128((const __m128i *)&_xmm);
    v15[7] = _mm_load_si128((const __m128i *)&_xmm);
    v15[8] = _mm_load_si128((const __m128i *)&_xmm);
    v15[9] = _mm_load_si128((const __m128i *)&_xmm);
    v16 = 121;
    v6 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&int sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>>::put(v14);
    v7 = sqlite3LockAndPrepare(*((_QWORD *)this + 1), (unsigned int)v15, 162, 128, 0, v6, 0);
    v8 = TranslateSQLiteFailure(v7);
    if ( v8 < 0
      || (v9 = sqlite3_bind_int64(v14[0], 1, *(_QWORD *)a2), v8 = TranslateSQLiteFailure(v9), v8 < 0)
      || (v10 = sqlite3_bind_int64(v14[0], 2, *((_QWORD *)a2 + 1)), v8 = TranslateSQLiteFailure(v10), v8 < 0) )
    {
      wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&int sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&int sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>(v14);
      return (unsigned int)v8;
    }
    else
    {
      v11 = bindText(v14[0], 3, *((_QWORD *)a2 + 2), -2, 0, 2);
      v12 = TranslateSQLiteFailure(v11);
      if ( v12 >= 0 )
      {
        v13 = sqlite3_step(v14[0]);
        v12 = TranslateSQLiteFailure(v13);
      }
      wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&int sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&int sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>(v14);
      return (unsigned int)v12;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18004d590  mov     [rsp-8+arg_10], rbx
0x18004d595  mov     [rsp-8+arg_18], rdi
0x18004d59a  push    rbp
0x18004d59b  lea     rbp, [rsp-10h]
0x18004d5a0  sub     rsp, 110h
0x18004d5a7  mov     rax, cs:__security_cookie
0x18004d5ae  xor     rax, rsp
0x18004d5b1  mov     [rbp+10h+var_10], rax
0x18004d5b5  mov     rbx, rdx
0x18004d5b8  mov     rdi, rcx
0x18004d5bb  mov     [rsp+110h+var_F0], 0
0x18004d5c4  xor     r9d, r9d
0x18004d5c7  xor     r8d, r8d
0x18004d5ca  lea     rdx, aCreateTableIfN; "CREATE TABLE IF NOT EXISTS compiler_id("...
0x18004d5d1  mov     rcx, [rcx+8]
0x18004d5d5  call    sqlite3_exec
0x18004d5da  mov     ecx, eax; int
0x18004d5dc  call    ?TranslateSQLiteFailure@@YAJH@Z; TranslateSQLiteFailure(int)
0x18004d5e1  test    eax, eax
0x18004d5e3  js      loc_18004D766
0x18004d5e9  mov     [rsp+110h+var_D0], 0
0x18004d5f2  movdqa  xmm0, cs:__xmm@706d6f63204f544e4920545245534e49
0x18004d5fa  movdqa  [rsp+110h+var_C0], xmm0
0x18004d600  movdqa  xmm1, cs:__xmm@2c696261202c64692864695f72656c69
0x18004d608  movdqa  [rsp+110h+var_B0], xmm1
0x18004d60e  movdqa  xmm0, cs:__xmm@796c696d6166202c6e6f697372657620
0x18004d616  movdqa  [rsp+110h+var_A0], xmm0
0x18004d61c  movdqa  xmm1, cs:__xmm@3f202c3f202c30285345554c41562029
0x18004d624  movdqa  [rbp+10h+var_90], xmm1
0x18004d629  movdqa  xmm0, cs:__xmm@5443494c464e4f43204e4f20293f202c
0x18004d631  movdqa  [rbp+10h+var_80], xmm0
0x18004d636  movdqa  xmm1, cs:__xmm@612054455320455441445055204f4420
0x18004d63e  movdqa  [rbp+10h+var_70], xmm1
0x18004d643  movdqa  xmm0, cs:__xmm@2c6962612e646564756c6378653d6962
0x18004d64b  movdqa  [rbp+10h+var_60], xmm0
0x18004d650  movdqa  xmm1, cs:__xmm@6564756c6378653d6e6f697372657620
0x18004d658  movdqa  [rbp+10h+var_50], xmm1
0x18004d65d  movdqa  xmm0, cs:__xmm@6c696d6166202c6e6f69737265762e64
0x18004d665  movdqa  [rbp+10h+var_40], xmm0
0x18004d66a  movdqa  xmm1, cs:__xmm@6c696d61662e646564756c6378653d79
0x18004d672  movdqa  [rbp+10h+var_30], xmm1
0x18004d677  mov     [rbp+10h+var_20], 79h ; 'y'
0x18004d67d  lea     rcx, [rsp+110h+var_D0]
0x18004d682  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3_stmt@@$$A6AHPEAU1@@Z$1?sqlite3_finalize@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUsqlite3_stmt@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>>::put(void)
0x18004d687  mov     [rsp+110h+var_E0], 0
0x18004d690  mov     [rsp+110h+var_E8], rax
0x18004d695  mov     [rsp+110h+var_F0], 0
0x18004d69e  mov     r9d, 80h
0x18004d6a4  lea     r8d, [r9+22h]
0x18004d6a8  lea     rdx, [rsp+110h+var_C0]
0x18004d6ad  mov     rcx, [rdi+8]
0x18004d6b1  call    sqlite3LockAndPrepare
0x18004d6b6  mov     ecx, eax; int
0x18004d6b8  call    ?TranslateSQLiteFailure@@YAJH@Z; TranslateSQLiteFailure(int)
0x18004d6bd  mov     edi, eax
0x18004d6bf  test    eax, eax
0x18004d6c1  jns     short loc_18004D6D4
0x18004d6c3  lea     rcx, [rsp+110h+var_D0]
0x18004d6c8  call    ??1?$unique_storage@U?$resource_policy@PEAUsqlite3_stmt@@$$A6AHPEAU1@@Z$1?sqlite3_finalize@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>(void)
0x18004d6cd  mov     eax, edi
0x18004d6cf  jmp     loc_18004D766
0x18004d6d4  mov     r8, [rbx]
0x18004d6d7  mov     edx, 1
0x18004d6dc  mov     rcx, [rsp+110h+var_D0]
0x18004d6e1  call    sqlite3_bind_int64
0x18004d6e6  mov     ecx, eax; int
0x18004d6e8  call    ?TranslateSQLiteFailure@@YAJH@Z; TranslateSQLiteFailure(int)
0x18004d6ed  mov     edi, eax
0x18004d6ef  test    eax, eax
0x18004d6f1  js      short loc_18004D6C3
0x18004d6f3  mov     r8, [rbx+8]
0x18004d6f7  mov     edx, 2
0x18004d6fc  mov     rcx, [rsp+110h+var_D0]
0x18004d701  call    sqlite3_bind_int64
0x18004d706  mov     ecx, eax; int
0x18004d708  call    ?TranslateSQLiteFailure@@YAJH@Z; TranslateSQLiteFailure(int)
0x18004d70d  mov     edi, eax
0x18004d70f  test    eax, eax
0x18004d711  js      short loc_18004D6C3
0x18004d713  mov     byte ptr [rsp+110h+var_E8], 2
0x18004d718  mov     [rsp+110h+var_F0], 0
0x18004d721  mov     r9, 0FFFFFFFFFFFFFFFEh
0x18004d728  mov     r8, [rbx+10h]
0x18004d72c  lea     edx, [r9+5]
0x18004d730  mov     rcx, [rsp+110h+var_D0]
0x18004d735  call    bindText
0x18004d73a  mov     ecx, eax; int
0x18004d73c  call    ?TranslateSQLiteFailure@@YAJH@Z; TranslateSQLiteFailure(int)
0x18004d741  mov     ebx, eax
0x18004d743  test    eax, eax
0x18004d745  js      short loc_18004D75A
0x18004d747  mov     rcx, [rsp+110h+var_D0]
0x18004d74c  call    sqlite3_step
0x18004d751  mov     ecx, eax; int
0x18004d753  call    ?TranslateSQLiteFailure@@YAJH@Z; TranslateSQLiteFailure(int)
0x18004d758  mov     ebx, eax
0x18004d75a  lea     rcx, [rsp+110h+var_D0]
0x18004d75f  call    ??1?$unique_storage@U?$resource_policy@PEAUsqlite3_stmt@@$$A6AHPEAU1@@Z$1?sqlite3_finalize@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>(void)
0x18004d764  mov     eax, ebx
0x18004d766  mov     rcx, [rbp+10h+var_10]
0x18004d76a  xor     rcx, rsp; StackCookie
0x18004d76d  call    __security_check_cookie
0x18004d772  lea     r11, [rsp+110h+var_s0]
0x18004d77a  mov     rbx, [r11+20h]
0x18004d77e  mov     rdi, [r11+28h]
0x18004d782  mov     rsp, r11
0x18004d785  pop     rbp
0x18004d786  retn
```
