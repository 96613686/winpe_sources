# AppxAllUserStore::GetOverrideConfigFullPath(Common::StringBuffer *)

- ea: `0x1800057d4`
- end: `0x180005a05`
- name: `?GetOverrideConfigFullPath@AppxAllUserStore@@YAJPEAVStringBuffer@Common@@@Z`
- size: `561`
- prototype: `__int64 __fastcall(AppxAllUserStore *__hidden this, struct Common::StringBuffer *)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180005374`
- `0x180011dd0`
- `0x180049de4`

## callees

- `0x1800057d4`
- `0x180006510`
- `0x1800068f0`
- `0x180006c00`
- `0x180007a10`
- `0x180017f50`
- `0x180018248`
- `0x18004c972`

## string_xrefs

- `0x180005908`: `OverrideConfig`
- `0x180005961`: `OverrideConfig`
- `0x180005859`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x18000588b`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x18000594b`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x1800059c8`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x1800058d1`: `onecore\admin\appmodel\common\alluserstorepaths.cpp`

## pseudocode

```c
__int64 __fastcall AppxAllUserStore::GetOverrideConfigFullPath(void **this, struct Common::StringBuffer *a2)
{
  const WCHAR *v3; // rax
  __int64 v4; // rdx
  signed int appended; // ebx
  __int64 v6; // rbp
  __int64 v7; // rsi
  int v8; // eax
  __int64 v9; // rdx
  __int64 v11; // rdx
  const unsigned __int16 *v12; // rax
  __int64 v13; // rcx
  const unsigned __int16 *v14; // rax
  int v15[2]; // [rsp+20h] [rbp-48h] BYREF
  void **v16; // [rsp+28h] [rbp-40h]
  void **v17; // [rsp+30h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  Common::GlobalHeap::Free(this[1]);
  v16 = this;
  this[1] = 0;
  *(_QWORD *)v15 = &Common::StringBufferBuilder::`vftable';
  v3 = L"Software\\";
  *(_DWORD *)this = 0;
  *((_DWORD *)this + 4) = 0;
  v4 = 0x3FFFFFFF;
  v17 = this;
  do
  {
    if ( !*v3 )
      break;
    ++v3;
    --v4;
  }
  while ( v4 );
  appended = v4 == 0 ? 0x80070057 : 0;
  v6 = (0x3FFFFFFF - v4) & -(__int64)(v4 != 0);
  if ( !v4 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x35,
      (int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
      (const char *)(unsigned int)appended);
LABEL_10:
    v9 = 238;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\admin\\appmodel\\common\\alluserstorepaths.cpp",
      (const char *)(unsigned int)appended,
      v15[0]);
    return (unsigned int)appended;
  }
  v7 = *(unsigned int *)this;
  v8 = Common::StringBuilder::Insert((Common::StringBuilder *)v15, v7, v6);
  appended = v8;
  if ( v8 >= 0 )
  {
    memcpy_0((char *)v16[1] + 2 * v7, L"Software\\", 2LL * (unsigned int)v6);
    appended = 0;
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x79,
      (int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
      (const char *)(unsigned int)v8);
  }
  if ( appended < 0 )
    goto LABEL_10;
  appended = Common::StringBuilder::AppendString(
               (Common::StringBuilder *)v15,
               AppxAllUserStore::appxAllUserStorePathString);
  if ( appended < 0 )
  {
    v9 = 239;
    goto LABEL_11;
  }
  v11 = 0x3FFFFFFF;
  v12 = L"OverrideConfig";
  do
  {
    if ( !*v12 )
      break;
    ++v12;
    --v11;
  }
  while ( v11 );
  appended = v11 == 0 ? 0x80070057 : 0;
  if ( !v11 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x35,
      (int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
      (const char *)(unsigned int)appended);
LABEL_20:
    v9 = 240;
    goto LABEL_11;
  }
  appended = Common::StringBuilder::AppendChars(
               (Common::StringBuilder *)v15,
               L"OverrideConfig",
               v11 != 0 ? 0x3FFFFFFF - v11 : 0);
  if ( appended < 0 )
    goto LABEL_20;
  v13 = 0x3FFFFFFF;
  v14 = L"\\";
  do
  {
    if ( !*v14 )
      break;
    ++v14;
    --v13;
  }
  while ( v13 );
  appended = v13 == 0 ? 0x80070057 : 0;
  if ( !v13 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x35,
      (int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
      (const char *)(unsigned int)appended);
LABEL_27:
    v9 = 241;
    goto LABEL_11;
  }
  appended = Common::StringBuilder::AppendChars((Common::StringBuilder *)v15, L"\\", v13 != 0 ? 0x3FFFFFFF - v13 : 0);
  if ( appended < 0 )
    goto LABEL_27;
  return 0;
}

```

## disassembly

```asm
0x1800057d4  push    rbx
0x1800057d6  push    rbp
0x1800057d7  push    rsi
0x1800057d8  push    rdi
0x1800057d9  push    r14
0x1800057db  sub     rsp, 40h
0x1800057df  mov     rsi, rcx
0x1800057e2  mov     rcx, [rcx+8]; void *
0x1800057e6  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x1800057eb  xor     r14d, r14d
0x1800057ee  mov     [rsp+68h+var_40], rsi
0x1800057f3  lea     rax, ??_7StringBufferBuilder@Common@@6B@; const Common::StringBufferBuilder::`vftable'
0x1800057fa  mov     [rsi+8], r14
0x1800057fe  mov     edi, 3FFFFFFFh
0x180005803  mov     qword ptr [rsp+68h+var_48], rax; int
0x180005808  lea     rax, aSoftware_1; "Software\\"
0x18000580f  mov     [rsi], r14d
0x180005812  mov     [rsi+10h], r14d
0x180005816  mov     edx, edi
0x180005818  mov     [rsp+68h+var_38], rsi
0x18000581d  cmp     [rax], r14w
0x180005821  jz      short loc_18000582D
0x180005823  add     rax, 2
0x180005827  sub     rdx, 1
0x18000582b  jnz     short loc_18000581D
0x18000582d  mov     rax, rdx
0x180005830  mov     rcx, rdi
0x180005833  neg     rax
0x180005836  mov     rax, rdx
0x180005839  sbb     ebx, ebx
0x18000583b  sub     rcx, rdx
0x18000583e  not     ebx
0x180005840  and     ebx, 80070057h
0x180005846  neg     rax
0x180005849  sbb     rbp, rbp
0x18000584c  and     rbp, rcx
0x18000584f  test    rdx, rdx
0x180005852  jnz     short loc_18000586F
0x180005854  mov     rcx, [rsp+68h]; this
0x180005859  lea     r8, aOnecoreBaseApp_2; "onecore\\base\\appmodel\\common\\string"...
0x180005860  mov     r9d, ebx; char *
0x180005863  mov     edx, 35h ; '5'; void *
0x180005868  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000586d  jmp     short loc_1800058C7
0x18000586f  mov     esi, [rsi]
0x180005871  lea     rcx, [rsp+68h+var_48]; this
0x180005876  mov     edx, esi; unsigned int
0x180005878  mov     r8d, ebp; unsigned int
0x18000587b  call    ?Insert@StringBuilder@Common@@QEAAJKK@Z; Common::StringBuilder::Insert(ulong,ulong)
0x180005880  mov     ebx, eax
0x180005882  test    eax, eax
0x180005884  jns     short loc_1800058A1
0x180005886  mov     rcx, [rsp+68h]; this
0x18000588b  lea     r8, aOnecoreBaseApp_2; "onecore\\base\\appmodel\\common\\string"...
0x180005892  mov     r9d, eax; char *
0x180005895  mov     edx, 79h ; 'y'; void *
0x18000589a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000589f  jmp     short loc_1800058C3
0x1800058a1  mov     rax, [rsp+68h+var_40]
0x1800058a6  lea     rdx, aSoftware_1; "Software\\"
0x1800058ad  mov     r8d, ebp
0x1800058b0  add     r8, r8; Size
0x1800058b3  mov     rcx, [rax+8]
0x1800058b7  lea     rcx, [rcx+rsi*2]; void *
0x1800058bb  call    memcpy_0
0x1800058c0  mov     ebx, r14d
0x1800058c3  test    ebx, ebx
0x1800058c5  jns     short loc_1800058E7
0x1800058c7  mov     edx, 0EEh; void *
0x1800058cc  mov     rcx, [rsp+68h]; this
0x1800058d1  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\common\\allus"...
0x1800058d8  mov     r9d, ebx; char *
0x1800058db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800058e0  mov     eax, ebx
0x1800058e2  jmp     loc_1800059FA
0x1800058e7  mov     rdx, cs:?appxAllUserStorePathString@AppxAllUserStore@@3PEBGEB; unsigned __int16 *
0x1800058ee  lea     rcx, [rsp+68h+var_48]; this
0x1800058f3  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x1800058f8  mov     ebx, eax
0x1800058fa  test    eax, eax
0x1800058fc  jns     short loc_180005905
0x1800058fe  mov     edx, 0EFh
0x180005903  jmp     short loc_1800058CC
0x180005905  mov     rdx, rdi
0x180005908  lea     rax, ?applicationsOverrideConfigString@AppxAllUserStore@@3QBGB; "OverrideConfig"
0x18000590f  cmp     [rax], r14w
0x180005913  jz      short loc_18000591F
0x180005915  add     rax, 2
0x180005919  sub     rdx, 1
0x18000591d  jnz     short loc_18000590F
0x18000591f  mov     rax, rdx
0x180005922  mov     rcx, rdi
0x180005925  neg     rax
0x180005928  mov     rax, rdx
0x18000592b  sbb     ebx, ebx
0x18000592d  sub     rcx, rdx
0x180005930  not     ebx
0x180005932  and     ebx, 80070057h
0x180005938  neg     rax
0x18000593b  sbb     r8, r8
0x18000593e  and     r8, rcx; unsigned int
0x180005941  test    rdx, rdx
0x180005944  jnz     short loc_180005961
0x180005946  mov     rcx, [rsp+68h]; this
0x18000594b  lea     r8, aOnecoreBaseApp_2; "onecore\\base\\appmodel\\common\\string"...
0x180005952  mov     r9d, ebx; char *
0x180005955  mov     edx, 35h ; '5'; void *
0x18000595a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000595f  jmp     short loc_180005978
0x180005961  lea     rdx, ?applicationsOverrideConfigString@AppxAllUserStore@@3QBGB; "OverrideConfig"
0x180005968  lea     rcx, [rsp+68h+var_48]; this
0x18000596d  call    ?AppendChars@StringBuilder@Common@@QEAAJPEBGK@Z; Common::StringBuilder::AppendChars(ushort const *,ulong)
0x180005972  mov     ebx, eax
0x180005974  test    eax, eax
0x180005976  jns     short loc_180005982
0x180005978  mov     edx, 0F0h
0x18000597d  jmp     loc_1800058CC
0x180005982  lea     rdx, asc_18004F868; "\\"
0x180005989  mov     rcx, rdi
0x18000598c  mov     rax, rdx
0x18000598f  cmp     [rax], r14w
0x180005993  jz      short loc_18000599F
0x180005995  add     rax, 2
0x180005999  sub     rcx, 1
0x18000599d  jnz     short loc_18000598F
0x18000599f  mov     rax, rcx
0x1800059a2  neg     rax
0x1800059a5  mov     rax, rcx
0x1800059a8  sbb     ebx, ebx
0x1800059aa  sub     rdi, rcx
0x1800059ad  not     ebx
0x1800059af  and     ebx, 80070057h
0x1800059b5  neg     rax
0x1800059b8  sbb     r8, r8
0x1800059bb  and     r8, rdi; unsigned int
0x1800059be  test    rcx, rcx
0x1800059c1  jnz     short loc_1800059DE
0x1800059c3  mov     rcx, [rsp+68h]; this
0x1800059c8  lea     r8, aOnecoreBaseApp_2; "onecore\\base\\appmodel\\common\\string"...
0x1800059cf  mov     r9d, ebx; char *
0x1800059d2  mov     edx, 35h ; '5'; void *
0x1800059d7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800059dc  jmp     short loc_1800059EE
0x1800059de  lea     rcx, [rsp+68h+var_48]; this
0x1800059e3  call    ?AppendChars@StringBuilder@Common@@QEAAJPEBGK@Z; Common::StringBuilder::AppendChars(ushort const *,ulong)
0x1800059e8  mov     ebx, eax
0x1800059ea  test    eax, eax
0x1800059ec  jns     short loc_1800059F8
0x1800059ee  mov     edx, 0F1h
0x1800059f3  jmp     loc_1800058CC
0x1800059f8  xor     eax, eax
0x1800059fa  add     rsp, 40h
0x1800059fe  pop     r14
0x180005a00  pop     rdi
0x180005a01  pop     rsi
0x180005a02  pop     rbp
0x180005a03  pop     rbx
0x180005a04  retn
```
