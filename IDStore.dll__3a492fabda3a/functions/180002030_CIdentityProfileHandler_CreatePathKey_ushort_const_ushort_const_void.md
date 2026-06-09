# CIdentityProfileHandler::_CreatePathKey(ushort const *,ushort const *,void * *)

- ea: `0x180002030`
- end: `0x1800022bf`
- name: `?_CreatePathKey@CIdentityProfileHandler@@AEAAJPEBG0PEAPEAX@Z`
- size: `655`
- prototype: `__int64 __fastcall(CIdentityProfileHandler *__hidden this, const unsigned __int16 *, const unsigned __int16 *, void **)`
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800022d0`
- `0x180014de4`
- `0x180015184`

## callees

- `0x180001f9c`
- `0x180002030`
- `0x1800144b4`
- `0x1800144f4`
- `0x1800191ac`
- `0x180019210`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002232`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002232`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000212b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000212b`

## string_xrefs

- `0x1800020fc`: `CIdentityProfileHandler::_CreatePathKey`
- `0x1800021d3`: `CIdentityProfileHandler::_CreatePathKey`
- `0x1800022a9`: `CIdentityProfileHandler::_CreatePathKey`

## pseudocode

```c
__int64 __fastcall CIdentityProfileHandler::_CreatePathKey(
        CIdentityProfileHandler *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        void **a4)
{
  CIdentityProfileHandler *v7; // r10
  __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v10; // r8
  unsigned __int64 v11; // rdx
  unsigned __int64 v12; // rax
  unsigned int v13; // ebx
  __int64 v14; // rdx
  __int64 v15; // r9
  unsigned int v16; // ecx
  unsigned int v17; // esi
  HLOCAL v18; // rax
  int v19; // eax
  bool v21; // sf
  DWORD LastError; // eax

  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, a3, "CIdentityProfileHandler::_CreatePathKey");
    v7 = WPP_GLOBAL_Control;
  }
  v8 = -1;
  v9 = -1;
  do
    ++v9;
  while ( a3[v9] );
  v10 = 0xFFFFFFFFLL;
  v11 = 2LL * (unsigned int)v9;
  if ( v11 > 0xFFFFFFFF )
  {
    v13 = -2147024362;
    if ( v7 == (CIdentityProfileHandler *)&WPP_GLOBAL_Control )
      return v13;
    if ( (*((_BYTE *)v7 + 28) & 4) == 0 )
      goto LABEL_14;
    v14 = 34;
    goto LABEL_12;
  }
  do
    ++v8;
  while ( a2[v8] );
  v12 = 2LL * (unsigned int)v8;
  if ( v12 > 0xFFFFFFFF )
  {
    v13 = -2147024362;
    if ( v7 == (CIdentityProfileHandler *)&WPP_GLOBAL_Control )
      return v13;
    if ( (*((_BYTE *)v7 + 28) & 4) == 0 )
      goto LABEL_14;
    v14 = 35;
LABEL_12:
    v15 = 2147942934LL;
    goto LABEL_13;
  }
  v16 = v11 + 4;
  if ( (unsigned int)v11 >= 0xFFFFFFFC )
  {
    v13 = -2147024362;
    if ( v7 == (CIdentityProfileHandler *)&WPP_GLOBAL_Control )
      return v13;
    if ( (*((_BYTE *)v7 + 28) & 4) == 0 )
      goto LABEL_14;
    v14 = 36;
    goto LABEL_12;
  }
  v17 = v16 + v12;
  if ( v16 + (unsigned int)v12 < v16 )
  {
    v13 = -2147024362;
    if ( v7 == (CIdentityProfileHandler *)&WPP_GLOBAL_Control )
      return v13;
    if ( (*((_BYTE *)v7 + 28) & 4) == 0 )
      goto LABEL_14;
    v14 = 37;
    goto LABEL_12;
  }
  v18 = LocalAlloc(0, v17);
  *a4 = v18;
  if ( !v18 )
  {
    LastError = GetLastError();
    v13 = LastError;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_DD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        38,
        WPP_0955e053d70b3b28b837838791dca877_Traceguids,
        v17,
        LastError);
      v7 = WPP_GLOBAL_Control;
    }
    v21 = (v13 & 0x80000000) != 0;
    if ( (int)v13 > 0 )
    {
      v13 = (unsigned __int16)v13 | 0x80070000;
      v21 = (v13 & 0x80000000) != 0;
    }
    if ( !v21 )
      goto LABEL_24;
    goto LABEL_14;
  }
  v19 = StringCbPrintfW((unsigned __int16 *)v18, v17, L"%s\\%s", a2, a3);
  v13 = v19;
  if ( v19 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control )
      return v13;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_14;
    v14 = 39;
    v15 = (unsigned int)v19;
LABEL_13:
    WPP_SF_d(*((_QWORD *)v7 + 2), v14, WPP_0955e053d70b3b28b837838791dca877_Traceguids, v15);
    v7 = WPP_GLOBAL_Control;
LABEL_14:
    if ( v7 == (CIdentityProfileHandler *)&WPP_GLOBAL_Control )
      return v13;
    if ( (*((_BYTE *)v7 + 28) & 4) == 0 )
      goto LABEL_24;
    WPP_SF_sL(*((_QWORD *)v7 + 2), v11, v10, (unsigned int)"CIdentityProfileHandler::_CreatePathKey", v13);
    goto LABEL_22;
  }
  v13 = 0;
LABEL_22:
  v7 = WPP_GLOBAL_Control;
LABEL_24:
  if ( v7 != (CIdentityProfileHandler *)&WPP_GLOBAL_Control && (*((_DWORD *)v7 + 7) & 0x400) != 0 )
    WPP_SF_s(*((_QWORD *)v7 + 2), 12, v10, "CIdentityProfileHandler::_CreatePathKey");
  return v13;
}

```

## disassembly

```asm
0x180002030  mov     [rsp+arg_10], rbx
0x180002035  push    rdi
0x180002036  push    r14
0x180002038  push    r15
0x18000203a  sub     rsp, 30h
0x18000203e  mov     r14, r9
0x180002041  mov     rbx, r8
0x180002044  mov     rdi, rdx
0x180002047  mov     r10, cs:WPP_GLOBAL_Control
0x18000204e  lea     r15, WPP_GLOBAL_Control
0x180002055  cmp     r10, r15
0x180002058  jz      short loc_180002068
0x18000205a  test    dword ptr [r10+1Ch], 400h
0x180002062  jnz     loc_1800021CF
0x180002068  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000206f  mov     rax, rcx
0x180002072  inc     rax
0x180002075  cmp     word ptr [rbx+rax*2], 0
0x18000207a  jnz     short loc_180002072
0x18000207c  mov     edx, eax
0x18000207e  mov     r8d, 0FFFFFFFFh
0x180002084  add     rdx, rdx
0x180002087  mov     [rsp+48h+arg_0], rbp
0x18000208c  mov     [rsp+48h+arg_8], rsi
0x180002091  cmp     rdx, r8
0x180002094  ja      loc_1800021F0
0x18000209a  nop     word ptr [rax+rax+00h]
0x1800020a0  inc     rcx
0x1800020a3  cmp     word ptr [rdi+rcx*2], 0
0x1800020a8  jnz     short loc_1800020A0
0x1800020aa  mov     eax, ecx
0x1800020ac  add     rax, rax
0x1800020af  cmp     rax, r8
0x1800020b2  jbe     short loc_18000210E
0x1800020b4  mov     ebx, 80070216h
0x1800020b9  cmp     r10, r15
0x1800020bc  jz      loc_180002184
0x1800020c2  test    byte ptr [r10+1Ch], 4
0x1800020c7  jz      short loc_1800020E8
0x1800020c9  mov     edx, 23h ; '#'
0x1800020ce  mov     r9d, ebx
0x1800020d1  mov     rcx, [r10+10h]
0x1800020d5  lea     r8, WPP_0955e053d70b3b28b837838791dca877_Traceguids
0x1800020dc  call    WPP_SF_d
0x1800020e1  mov     r10, cs:WPP_GLOBAL_Control
0x1800020e8  cmp     r10, r15
0x1800020eb  jz      loc_180002184
0x1800020f1  test    byte ptr [r10+1Ch], 4
0x1800020f6  jz      short loc_180002171
0x1800020f8  mov     rcx, [r10+10h]
0x1800020fc  lea     r9, aCidentityprofi_1; "CIdentityProfileHandler::_CreatePathKey"
0x180002103  mov     dword ptr [rsp+48h+var_28], ebx
0x180002107  call    WPP_SF_sL
0x18000210c  jmp     short loc_180002162
0x18000210e  lea     ecx, [rdx+4]
0x180002111  cmp     ecx, 4
0x180002114  jb      loc_18000219F
0x18000211a  lea     esi, [rcx+rax]
0x18000211d  cmp     esi, ecx
0x18000211f  jb      loc_18000220F
0x180002125  mov     edx, esi; uBytes
0x180002127  xor     ecx, ecx; uFlags
0x180002129  mov     ebp, esi
0x18000212b  call    cs:__imp_LocalAlloc
0x180002131  mov     [r14], rax
0x180002134  test    rax, rax
0x180002137  jz      loc_180002232
0x18000213d  mov     r9, rdi
0x180002140  mov     [rsp+48h+var_28], rbx
0x180002145  lea     r8, aSS; "%s\\%s"
0x18000214c  mov     edx, ebp; unsigned __int64
0x18000214e  mov     rcx, rax; unsigned __int16 *
0x180002151  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180002156  mov     ebx, eax
0x180002158  test    eax, eax
0x18000215a  js      loc_18000227D
0x180002160  xor     ebx, ebx
0x180002162  mov     r10, cs:WPP_GLOBAL_Control
0x180002169  jmp     short loc_180002171
0x18000216b  js      loc_1800020E8
0x180002171  cmp     r10, r15
0x180002174  jz      short loc_180002184
0x180002176  test    dword ptr [r10+1Ch], 400h
0x18000217e  jnz     loc_1800022A5
0x180002184  mov     rsi, [rsp+48h+arg_8]
0x180002189  mov     eax, ebx
0x18000218b  mov     rbx, [rsp+48h+arg_10]
0x180002190  mov     rbp, [rsp+48h+arg_0]
0x180002195  add     rsp, 30h
0x180002199  pop     r15
0x18000219b  pop     r14
0x18000219d  pop     rdi
0x18000219e  retn
0x18000219f  mov     ebx, 80070216h
0x1800021a4  cmp     r10, r15
0x1800021a7  jz      short loc_180002184
0x1800021a9  test    byte ptr [r10+1Ch], 4
0x1800021ae  jz      loc_1800020E8
0x1800021b4  mov     edx, 24h ; '$'
0x1800021b9  jmp     loc_1800020CE
0x1800021be  test    ebx, ebx
0x1800021c0  jle     short loc_18000216B
0x1800021c2  movzx   ebx, bx
0x1800021c5  or      ebx, 80070000h
0x1800021cb  test    ebx, ebx
0x1800021cd  jmp     short loc_18000216B
0x1800021cf  mov     rcx, [r10+10h]
0x1800021d3  lea     r9, aCidentityprofi_1; "CIdentityProfileHandler::_CreatePathKey"
0x1800021da  mov     edx, 0Ah
0x1800021df  call    WPP_SF_s
0x1800021e4  mov     r10, cs:WPP_GLOBAL_Control
0x1800021eb  jmp     loc_180002068
0x1800021f0  mov     ebx, 80070216h
0x1800021f5  cmp     r10, r15
0x1800021f8  jz      short loc_180002184
0x1800021fa  test    byte ptr [r10+1Ch], 4
0x1800021ff  jz      loc_1800020E8
0x180002205  mov     edx, 22h ; '"'
0x18000220a  jmp     loc_1800020CE
0x18000220f  mov     ebx, 80070216h
0x180002214  cmp     r10, r15
0x180002217  jz      loc_180002184
0x18000221d  test    byte ptr [r10+1Ch], 4
0x180002222  jz      loc_1800020E8
0x180002228  mov     edx, 25h ; '%'
0x18000222d  jmp     loc_1800020CE
0x180002232  call    cs:__imp_GetLastError
0x180002238  mov     ebx, eax
0x18000223a  mov     r10, cs:WPP_GLOBAL_Control
0x180002241  cmp     r10, r15
0x180002244  jz      loc_1800021BE
0x18000224a  test    byte ptr [r10+1Ch], 4
0x18000224f  jz      loc_1800021BE
0x180002255  mov     rcx, [r10+10h]
0x180002259  lea     r8, WPP_0955e053d70b3b28b837838791dca877_Traceguids
0x180002260  mov     edx, 26h ; '&'
0x180002265  mov     dword ptr [rsp+48h+var_28], eax
0x180002269  mov     r9d, esi
0x18000226c  call    WPP_SF_DD
0x180002271  mov     r10, cs:WPP_GLOBAL_Control
0x180002278  jmp     loc_1800021BE
0x18000227d  mov     r10, cs:WPP_GLOBAL_Control
0x180002284  cmp     r10, r15
0x180002287  jz      loc_180002184
0x18000228d  test    byte ptr [r10+1Ch], 4
0x180002292  jz      loc_1800020E8
0x180002298  mov     edx, 27h ; '''
0x18000229d  mov     r9d, eax
0x1800022a0  jmp     loc_1800020D1
0x1800022a5  mov     rcx, [r10+10h]
0x1800022a9  lea     r9, aCidentityprofi_1; "CIdentityProfileHandler::_CreatePathKey"
0x1800022b0  mov     edx, 0Ch
0x1800022b5  call    WPP_SF_s
0x1800022ba  jmp     loc_180002184
```
