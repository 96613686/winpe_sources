# AppxAllUserStore::GetConfigFullPath(Common::StringBuffer *)

- ea: `0x1800062c4`
- end: `0x180006509`
- name: `?GetConfigFullPath@AppxAllUserStore@@YAJPEAVStringBuffer@Common@@@Z`
- size: `581`
- prototype: `__int64 __fastcall(AppxAllUserStore *__hidden this, struct Common::StringBuffer *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011c44`
- `0x180015540`

## callees

- `0x1800062c4`
- `0x180006510`
- `0x1800068f0`
- `0x180006c00`
- `0x180007a10`
- `0x180017f50`
- `0x180018248`
- `0x18004c972`

## string_xrefs

- `0x1800063ab`: `Config`
- `0x1800063ed`: `Config`
- `0x180006473`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x1800064ae`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x1800064ce`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x1800064ee`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x180006496`: `onecore\admin\appmodel\common\alluserstorepaths.cpp`

## pseudocode

```c
__int64 __fastcall AppxAllUserStore::GetConfigFullPath(void **this, struct Common::StringBuffer *a2)
{
  const WCHAR *v3; // rax
  __int64 v4; // rdx
  signed int appended; // ebx
  __int64 v6; // rbp
  __int64 v7; // rsi
  int v8; // eax
  __int64 v9; // rdx
  const unsigned __int16 *v10; // rax
  __int64 v11; // rcx
  const unsigned __int16 *v12; // rax
  __int64 v14; // rdx
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
LABEL_24:
    v14 = 218;
    goto LABEL_22;
  }
  v7 = *(unsigned int *)this;
  v8 = Common::StringBuilder::Insert((Common::StringBuilder *)v15, v7, v6);
  appended = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x79,
      (int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
      (const char *)(unsigned int)v8);
  }
  else
  {
    memcpy_0((char *)v16[1] + 2 * v7, L"Software\\", 2LL * (unsigned int)v6);
    appended = 0;
  }
  if ( appended < 0 )
    goto LABEL_24;
  appended = Common::StringBuilder::AppendString(
               (Common::StringBuilder *)v15,
               AppxAllUserStore::appxAllUserStorePathString);
  if ( appended < 0 )
  {
    v14 = 219;
    goto LABEL_22;
  }
  v9 = 0x3FFFFFFF;
  v10 = L"Config";
  do
  {
    if ( !*v10 )
      break;
    ++v10;
    --v9;
  }
  while ( v9 );
  appended = v9 == 0 ? 0x80070057 : 0;
  if ( !v9 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x35,
      (int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
      (const char *)(unsigned int)appended);
    goto LABEL_26;
  }
  appended = Common::StringBuilder::AppendChars((Common::StringBuilder *)v15, L"Config", v9 != 0 ? 0x3FFFFFFF - v9 : 0);
  if ( appended < 0 )
  {
LABEL_26:
    v14 = 220;
    goto LABEL_22;
  }
  v11 = 0x3FFFFFFF;
  v12 = L"\\";
  do
  {
    if ( !*v12 )
      break;
    ++v12;
    --v11;
  }
  while ( v11 );
  appended = v11 == 0 ? 0x80070057 : 0;
  if ( v11 )
  {
    appended = Common::StringBuilder::AppendChars((Common::StringBuilder *)v15, L"\\", v11 != 0 ? 0x3FFFFFFF - v11 : 0);
    if ( appended >= 0 )
      return 0;
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x35,
      (int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
      (const char *)(unsigned int)appended);
  }
  v14 = 221;
LABEL_22:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v14,
    (unsigned int)"onecore\\admin\\appmodel\\common\\alluserstorepaths.cpp",
    (const char *)(unsigned int)appended,
    v15[0]);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x1800062c4  push    rbx
0x1800062c6  push    rbp
0x1800062c7  push    rsi
0x1800062c8  push    rdi
0x1800062c9  push    r14
0x1800062cb  sub     rsp, 40h
0x1800062cf  mov     rsi, rcx
0x1800062d2  mov     rcx, [rcx+8]; void *
0x1800062d6  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x1800062db  xor     r14d, r14d
0x1800062de  mov     [rsp+68h+var_40], rsi
0x1800062e3  lea     rax, ??_7StringBufferBuilder@Common@@6B@; const Common::StringBufferBuilder::`vftable'
0x1800062ea  mov     [rsi+8], r14
0x1800062ee  mov     edi, 3FFFFFFFh
0x1800062f3  mov     qword ptr [rsp+68h+var_48], rax; int
0x1800062f8  lea     rax, aSoftware_1; "Software\\"
0x1800062ff  mov     [rsi], r14d
0x180006302  mov     [rsi+10h], r14d
0x180006306  mov     edx, edi
0x180006308  mov     [rsp+68h+var_38], rsi
0x18000630d  cmp     [rax], r14w
0x180006311  jz      short loc_18000631D
0x180006313  add     rax, 2
0x180006317  sub     rdx, 1
0x18000631b  jnz     short loc_18000630D
0x18000631d  mov     rax, rdx
0x180006320  mov     rcx, rdi
0x180006323  neg     rax
0x180006326  mov     rax, rdx
0x180006329  sbb     ebx, ebx
0x18000632b  sub     rcx, rdx
0x18000632e  not     ebx
0x180006330  and     ebx, 80070057h
0x180006336  neg     rax
0x180006339  sbb     rbp, rbp
0x18000633c  and     rbp, rcx
0x18000633f  test    rdx, rdx
0x180006342  jz      loc_1800064A9
0x180006348  mov     esi, [rsi]
0x18000634a  lea     rcx, [rsp+68h+var_48]; this
0x18000634f  mov     edx, esi; unsigned int
0x180006351  mov     r8d, ebp; unsigned int
0x180006354  call    ?Insert@StringBuilder@Common@@QEAAJKK@Z; Common::StringBuilder::Insert(ulong,ulong)
0x180006359  mov     ebx, eax
0x18000635b  test    eax, eax
0x18000635d  js      loc_18000646E
0x180006363  mov     rax, [rsp+68h+var_40]
0x180006368  lea     rdx, aSoftware_1; "Software\\"
0x18000636f  mov     r8d, ebp
0x180006372  add     r8, r8; Size
0x180006375  mov     rcx, [rax+8]
0x180006379  lea     rcx, [rcx+rsi*2]; void *
0x18000637d  call    memcpy_0
0x180006382  mov     ebx, r14d
0x180006385  test    ebx, ebx
0x180006387  js      loc_1800064C2
0x18000638d  mov     rdx, cs:?appxAllUserStorePathString@AppxAllUserStore@@3PEBGEB; unsigned __int16 *
0x180006394  lea     rcx, [rsp+68h+var_48]; this
0x180006399  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x18000639e  mov     ebx, eax
0x1800063a0  test    eax, eax
0x1800063a2  js      loc_18000648C
0x1800063a8  mov     rdx, rdi
0x1800063ab  lea     rax, ?applicationsConfigString@AppxAllUserStore@@3QBGB; "Config"
0x1800063b2  cmp     [rax], r14w
0x1800063b6  jz      short loc_1800063C2
0x1800063b8  add     rax, 2
0x1800063bc  sub     rdx, 1
0x1800063c0  jnz     short loc_1800063B2
0x1800063c2  mov     rax, rdx
0x1800063c5  mov     rcx, rdi
0x1800063c8  neg     rax
0x1800063cb  mov     rax, rdx
0x1800063ce  sbb     ebx, ebx
0x1800063d0  sub     rcx, rdx
0x1800063d3  not     ebx
0x1800063d5  and     ebx, 80070057h
0x1800063db  neg     rax
0x1800063de  sbb     r8, r8
0x1800063e1  and     r8, rcx; unsigned int
0x1800063e4  test    rdx, rdx
0x1800063e7  jz      loc_1800064C9
0x1800063ed  lea     rdx, ?applicationsConfigString@AppxAllUserStore@@3QBGB; "Config"
0x1800063f4  lea     rcx, [rsp+68h+var_48]; this
0x1800063f9  call    ?AppendChars@StringBuilder@Common@@QEAAJPEBGK@Z; Common::StringBuilder::AppendChars(ushort const *,ulong)
0x1800063fe  mov     ebx, eax
0x180006400  test    eax, eax
0x180006402  js      loc_1800064E2
0x180006408  lea     rdx, asc_18004F868; "\\"
0x18000640f  mov     rcx, rdi
0x180006412  mov     rax, rdx
0x180006415  cmp     [rax], r14w
0x180006419  jz      short loc_180006425
0x18000641b  add     rax, 2
0x18000641f  sub     rcx, 1
0x180006423  jnz     short loc_180006415
0x180006425  mov     rax, rcx
0x180006428  neg     rax
0x18000642b  mov     rax, rcx
0x18000642e  sbb     ebx, ebx
0x180006430  sub     rdi, rcx
0x180006433  not     ebx
0x180006435  and     ebx, 80070057h
0x18000643b  neg     rax
0x18000643e  sbb     r8, r8
0x180006441  and     r8, rdi; unsigned int
0x180006444  test    rcx, rcx
0x180006447  jz      loc_1800064E9
0x18000644d  lea     rcx, [rsp+68h+var_48]; this
0x180006452  call    ?AppendChars@StringBuilder@Common@@QEAAJPEBGK@Z; Common::StringBuilder::AppendChars(ushort const *,ulong)
0x180006457  mov     ebx, eax
0x180006459  test    eax, eax
0x18000645b  js      loc_180006502
0x180006461  xor     eax, eax
0x180006463  add     rsp, 40h
0x180006467  pop     r14
0x180006469  pop     rdi
0x18000646a  pop     rsi
0x18000646b  pop     rbp
0x18000646c  pop     rbx
0x18000646d  retn
0x18000646e  mov     rcx, [rsp+68h]; this
0x180006473  lea     r8, aOnecoreBaseApp_2; "onecore\\base\\appmodel\\common\\string"...
0x18000647a  mov     r9d, eax; char *
0x18000647d  mov     edx, 79h ; 'y'; void *
0x180006482  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180006487  jmp     loc_180006385
0x18000648c  mov     edx, 0DBh; void *
0x180006491  mov     rcx, [rsp+68h]; this
0x180006496  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\common\\allus"...
0x18000649d  mov     r9d, ebx; char *
0x1800064a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800064a5  mov     eax, ebx
0x1800064a7  jmp     short loc_180006463
0x1800064a9  mov     rcx, [rsp+68h]; this
0x1800064ae  lea     r8, aOnecoreBaseApp_2; "onecore\\base\\appmodel\\common\\string"...
0x1800064b5  mov     r9d, ebx; char *
0x1800064b8  mov     edx, 35h ; '5'; void *
0x1800064bd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800064c2  mov     edx, 0DAh
0x1800064c7  jmp     short loc_180006491
0x1800064c9  mov     rcx, [rsp+68h]; this
0x1800064ce  lea     r8, aOnecoreBaseApp_2; "onecore\\base\\appmodel\\common\\string"...
0x1800064d5  mov     r9d, ebx; char *
0x1800064d8  mov     edx, 35h ; '5'; void *
0x1800064dd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800064e2  mov     edx, 0DCh
0x1800064e7  jmp     short loc_180006491
0x1800064e9  mov     rcx, [rsp+68h]; this
0x1800064ee  lea     r8, aOnecoreBaseApp_2; "onecore\\base\\appmodel\\common\\string"...
0x1800064f5  mov     r9d, ebx; char *
0x1800064f8  mov     edx, 35h ; '5'; void *
0x1800064fd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180006502  mov     edx, 0DDh
0x180006507  jmp     short loc_180006491
```
