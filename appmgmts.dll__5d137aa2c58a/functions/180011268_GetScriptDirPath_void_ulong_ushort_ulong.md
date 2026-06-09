# GetScriptDirPath(void *,ulong,ushort * *,ulong *)

- ea: `0x180011268`
- end: `0x1800114ae`
- name: `?GetScriptDirPath@@YAKPEAXKPEAPEAGPEAK@Z`
- size: `582`
- prototype: `DWORD __fastcall(void *, int, unsigned __int16 **, unsigned int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000ccd4`
- `0x18000df00`

## callees

- `0x1800016d0`
- `0x180002aa0`
- `0x18000cc10`
- `0x180011268`
- `0x180012f30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011300`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011300`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011464`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800114a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011464`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800114a1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800112e1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800113af`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800112e1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800113af`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800112f4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800112f4`
- `ntdll!RtlFreeUnicodeString` at `0x18001148e`
- `ntdll!RtlFreeUnicodeString` at `0x18001148e`
- `ntdll!RtlInitUnicodeString` at `0x1800112c6`
- `ntdll!RtlInitUnicodeString` at `0x18001135e`
- `ntdll!RtlInitUnicodeString` at `0x1800112c6`
- `ntdll!RtlInitUnicodeString` at `0x18001135e`

## pseudocode

```c
DWORD __fastcall GetScriptDirPath(void *a1, int a2, unsigned __int16 **a3, unsigned int *a4)
{
  unsigned __int16 *v8; // rsi
  UINT v9; // ebx
  WCHAR *i; // rcx
  WCHAR *v11; // rax
  UINT SystemDirectoryW; // eax
  UINT v13; // edi
  unsigned int SidString; // ebx
  unsigned int v16; // edx
  unsigned int v17; // ecx
  unsigned int v18; // r12d
  SIZE_T v19; // rax
  __int64 v20; // rbp
  unsigned __int16 *v21; // rax
  int v22; // eax
  unsigned int v23; // r11d
  unsigned __int16 v24; // di
  int v25; // eax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-288h] BYREF
  void *v30; // [rsp+30h] [rbp-278h]
  _BYTE hMem[528]; // [rsp+40h] [rbp-268h] BYREF

  v30 = a1;
  *a3 = 0;
  DestinationString = 0;
  if ( a4 )
    *a4 = 0;
  v8 = (unsigned __int16 *)hMem;
  v9 = 260;
  RtlInitUnicodeString(&DestinationString, 0);
  for ( i = (WCHAR *)hMem; ; i = v11 )
  {
    SystemDirectoryW = GetSystemDirectoryW(i, v9);
    v13 = SystemDirectoryW;
    if ( !SystemDirectoryW )
      return GetLastError();
    if ( SystemDirectoryW < v9 )
      break;
    v9 = SystemDirectoryW + 1;
    v11 = (WCHAR *)LocalAlloc(0, 2LL * (SystemDirectoryW + 1));
    v8 = v11;
    if ( !v11 )
      return 14;
  }
  if ( a1 )
  {
    SidString = GetSidString(a1, &DestinationString);
    if ( SidString )
    {
LABEL_35:
      RtlFreeUnicodeString(&DestinationString);
      goto LABEL_36;
    }
  }
  else
  {
    SidString = 0;
    RtlInitUnicodeString(&DestinationString, L"MACHINE");
  }
  v16 = v13 + (DestinationString.Length >> 1);
  if ( v16 < v13 || (v17 = v16 + a2, v16 + a2 < v16) || v17 + 11 < v17 )
  {
    *a3 = 0;
LABEL_33:
    SidString = 14;
    goto LABEL_34;
  }
  v18 = v17 + 11;
  v19 = 2LL * (v17 + 11);
  v20 = -1;
  if ( !is_mul_ok(v17 + 11, 2u) )
    v19 = -1;
  v21 = (unsigned __int16 *)LocalAlloc(0, v19);
  *a3 = v21;
  if ( !v21 )
    goto LABEL_33;
  v22 = StringCchCopyW(v21, v18, v8);
  v24 = v22;
  if ( v22 < 0 )
    goto LABEL_31;
  if ( v8 )
  {
    do
      ++v20;
    while ( v8[v20] != (_WORD)v23 );
  }
  else
  {
    v20 = v23;
  }
  if ( v8[v20 - 1] != 92 )
  {
    v25 = StringCchCatW(*a3, v18, L"\\");
    v24 = v25;
    if ( v25 < 0 )
      goto LABEL_31;
  }
  v26 = StringCchCatW(*a3, v18, L"appmgmt\\");
  v24 = v26;
  if ( v26 >= 0
    && (v27 = StringCchCatW(*a3, v18, DestinationString.Buffer), v24 = v27, v27 >= 0)
    && (v28 = StringCchCatW(*a3, v18, L"\\"), v24 = v28, v28 >= 0) )
  {
    if ( a4 )
      *a4 = v18;
  }
  else
  {
LABEL_31:
    LocalFree(*a3);
    *a3 = 0;
    SidString = v24;
  }
LABEL_34:
  if ( v30 )
    goto LABEL_35;
LABEL_36:
  if ( v8 != (unsigned __int16 *)hMem )
    LocalFree(v8);
  return SidString;
}

```

## disassembly

```asm
0x180011268  push    rbx
0x18001126a  push    rbp
0x18001126b  push    rsi
0x18001126c  push    rdi
0x18001126d  push    r12
0x18001126f  push    r13
0x180011271  push    r14
0x180011273  push    r15
0x180011275  sub     rsp, 268h
0x18001127c  mov     rax, cs:__security_cookie
0x180011283  xor     rax, rsp
0x180011286  mov     [rsp+2A8h+var_58], rax
0x18001128e  xor     r12d, r12d
0x180011291  mov     [rsp+2A8h+var_278], rcx
0x180011296  mov     [r8], r12
0x180011299  xorps   xmm0, xmm0
0x18001129c  mov     r13, r9
0x18001129f  mov     r14, r8
0x1800112a2  mov     r15d, edx
0x1800112a5  mov     rbp, rcx
0x1800112a8  movups  xmmword ptr [rsp+2A8h+DestinationString.Length], xmm0
0x1800112ad  test    r9, r9
0x1800112b0  jz      short loc_1800112B5
0x1800112b2  mov     [r9], r12d
0x1800112b5  xor     edx, edx; SourceString
0x1800112b7  lea     rcx, [rsp+2A8h+DestinationString]; DestinationString
0x1800112bc  lea     rsi, [rsp+2A8h+hMem]
0x1800112c1  mov     ebx, 104h
0x1800112c6  call    cs:__imp_RtlInitUnicodeString
0x1800112cc  lea     rcx, [rsp+2A8h+hMem]
0x1800112d1  jmp     short loc_1800112F2
0x1800112d3  cmp     edi, ebx
0x1800112d5  jb      short loc_180011331
0x1800112d7  lea     ebx, [rdi+1]
0x1800112da  xor     ecx, ecx; uFlags
0x1800112dc  mov     edx, ebx
0x1800112de  add     rdx, rdx; uBytes
0x1800112e1  call    cs:__imp_LocalAlloc
0x1800112e7  mov     rsi, rax
0x1800112ea  test    rax, rax
0x1800112ed  jz      short loc_18001132A
0x1800112ef  mov     rcx, rax; lpBuffer
0x1800112f2  mov     edx, ebx; uSize
0x1800112f4  call    cs:__imp_GetSystemDirectoryW
0x1800112fa  mov     edi, eax
0x1800112fc  test    eax, eax
0x1800112fe  jnz     short loc_1800112D3
0x180011300  call    cs:__imp_GetLastError
0x180011306  mov     rcx, [rsp+2A8h+var_58]
0x18001130e  xor     rcx, rsp; StackCookie
0x180011311  call    __security_check_cookie
0x180011316  add     rsp, 268h
0x18001131d  pop     r15
0x18001131f  pop     r14
0x180011321  pop     r13
0x180011323  pop     r12
0x180011325  pop     rdi
0x180011326  pop     rsi
0x180011327  pop     rbp
0x180011328  pop     rbx
0x180011329  retn
0x18001132a  mov     eax, 0Eh
0x18001132f  jmp     short loc_180011306
0x180011331  test    rbp, rbp
0x180011334  jz      short loc_18001134F
0x180011336  lea     rdx, [rsp+2A8h+DestinationString]; struct _UNICODE_STRING *
0x18001133b  mov     rcx, rbp; void *
0x18001133e  call    ?GetSidString@@YAKPEAXPEAU_UNICODE_STRING@@@Z; GetSidString(void *,_UNICODE_STRING *)
0x180011343  mov     ebx, eax
0x180011345  test    eax, eax
0x180011347  jnz     loc_180011489
0x18001134d  jmp     short loc_180011364
0x18001134f  lea     rdx, SourceString; "MACHINE"
0x180011356  mov     ebx, r12d
0x180011359  lea     rcx, [rsp+2A8h+DestinationString]; DestinationString
0x18001135e  call    cs:__imp_RtlInitUnicodeString
0x180011364  movzx   edx, [rsp+2A8h+DestinationString.Length]
0x180011369  shr     edx, 1
0x18001136b  add     edx, edi
0x18001136d  cmp     edx, edi
0x18001136f  jb      loc_180011479
0x180011375  lea     ecx, [rdx+r15]
0x180011379  cmp     ecx, edx
0x18001137b  jb      loc_180011479
0x180011381  lea     eax, [rcx+0Bh]
0x180011384  or      r12d, 0FFFFFFFFh
0x180011388  cmp     eax, ecx
0x18001138a  cmovnb  r12d, eax
0x18001138e  jb      loc_180011476
0x180011394  mov     r15d, r12d
0x180011397  mov     eax, 2
0x18001139c  mul     r15
0x18001139f  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x1800113a6  cmovb   rax, rbp
0x1800113aa  xor     ecx, ecx; uFlags
0x1800113ac  mov     rdx, rax; uBytes
0x1800113af  call    cs:__imp_LocalAlloc
0x1800113b5  xor     r11d, r11d
0x1800113b8  mov     [r14], rax
0x1800113bb  test    rax, rax
0x1800113be  jz      loc_18001147C
0x1800113c4  mov     r8, rsi; unsigned __int16 *
0x1800113c7  mov     edx, r15d; unsigned __int64
0x1800113ca  mov     rcx, rax; unsigned __int16 *
0x1800113cd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800113d2  mov     edi, eax
0x1800113d4  test    eax, eax
0x1800113d6  js      loc_180011461
0x1800113dc  test    rsi, rsi
0x1800113df  jnz     short loc_1800113E6
0x1800113e1  mov     ebp, r11d
0x1800113e4  jmp     short loc_1800113F0
0x1800113e6  inc     rbp
0x1800113e9  cmp     [rsi+rbp*2], r11w
0x1800113ee  jnz     short loc_1800113E6
0x1800113f0  cmp     word ptr [rsi+rbp*2-2], 5Ch ; '\'
0x1800113f6  jz      short loc_180011410
0x1800113f8  mov     rcx, [r14]; unsigned __int16 *
0x1800113fb  lea     r8, asc_18002EE30; "\\"
0x180011402  mov     rdx, r15; unsigned __int64
0x180011405  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001140a  mov     edi, eax
0x18001140c  test    eax, eax
0x18001140e  js      short loc_180011461
0x180011410  mov     rcx, [r14]; unsigned __int16 *
0x180011413  lea     r8, aAppmgmt_1; "appmgmt\\"
0x18001141a  mov     rdx, r15; unsigned __int64
0x18001141d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180011422  mov     edi, eax
0x180011424  test    eax, eax
0x180011426  js      short loc_180011461
0x180011428  mov     r8, [rsp+2A8h+DestinationString.Buffer]; unsigned __int16 *
0x18001142d  mov     rdx, r15; unsigned __int64
0x180011430  mov     rcx, [r14]; unsigned __int16 *
0x180011433  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180011438  mov     edi, eax
0x18001143a  test    eax, eax
0x18001143c  js      short loc_180011461
0x18001143e  mov     rcx, [r14]; unsigned __int16 *
0x180011441  lea     r8, asc_18002EE30; "\\"
0x180011448  mov     rdx, r15; unsigned __int64
0x18001144b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180011450  mov     edi, eax
0x180011452  test    eax, eax
0x180011454  js      short loc_180011461
0x180011456  test    r13, r13
0x180011459  jz      short loc_180011481
0x18001145b  mov     [r13+0], r12d
0x18001145f  jmp     short loc_180011481
0x180011461  mov     rcx, [r14]; hMem
0x180011464  call    cs:__imp_LocalFree
0x18001146a  mov     qword ptr [r14], 0
0x180011471  movzx   ebx, di
0x180011474  jmp     short loc_180011481
0x180011476  xor     r12d, r12d
0x180011479  mov     [r14], r12
0x18001147c  mov     ebx, 0Eh
0x180011481  cmp     [rsp+2A8h+var_278], 0
0x180011487  jz      short loc_180011494
0x180011489  lea     rcx, [rsp+2A8h+DestinationString]; UnicodeString
0x18001148e  call    cs:__imp_RtlFreeUnicodeString
0x180011494  lea     rax, [rsp+2A8h+hMem]
0x180011499  cmp     rsi, rax
0x18001149c  jz      short loc_1800114A7
0x18001149e  mov     rcx, rsi; hMem
0x1800114a1  call    cs:__imp_LocalFree
0x1800114a7  mov     eax, ebx
0x1800114a9  jmp     loc_180011306
```
