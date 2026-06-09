# Dynamo::details::ContextEntry::ContextEntry(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&)

- ea: `0x14004741c`
- end: `0x140047581`
- name: `??0ContextEntry@details@Dynamo@@QEAA@PEBG$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `357`
- prototype: `__int64 __fastcall(__int64, char *, _QWORD *, const char *)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140040720`
- `0x140041240`
- `0x1400482d0`

## callees

- `0x14000a6e4`
- `0x14000bb88`
- `0x14003d008`
- `0x1400419a4`
- `0x14004741c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140047524`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140047524`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400474a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400474b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400474a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400474b9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400474e8`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400474e8`

## string_xrefs

- `0x140047557`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall Dynamo::details::ContextEntry::ContextEntry(__int64 a1, char *a2, _QWORD *a3, const char *a4)
{
  const char *v6; // r9
  HLOCAL v7; // rax
  HLOCAL *p_hMem; // rcx
  char v9; // di
  unsigned int v10; // eax
  int lpData; // [rsp+20h] [rbp-20h]
  unsigned int lpDataa; // [rsp+20h] [rbp-20h]
  BYTE Data[16]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  HLOCAL hMem; // [rsp+68h] [rbp+28h] BYREF
  HLOCAL v17; // [rsp+78h] [rbp+38h] BYREF

  LODWORD(hMem) = 0;
  *(_QWORD *)a1 = &Dynamo::details::ContextEntry::`vftable';
  if ( a2 )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v17,
      a2,
      0xFFFFFFFFFFFFFFFFuLL,
      a4);
    LODWORD(hMem) = 8;
    v7 = v17;
    if ( !v17 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0xFF8,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v6);
    p_hMem = &v17;
    v9 = 5;
  }
  else
  {
    p_hMem = &hMem;
    v9 = 2;
    v7 = 0;
  }
  *(_QWORD *)(a1 + 8) = v7;
  *p_hMem = 0;
  if ( (v9 & 2) != 0 )
  {
    v9 &= ~2u;
    if ( hMem )
      LocalFree(hMem);
  }
  if ( (v9 & 1) != 0 && v17 )
    LocalFree(v17);
  *(_QWORD *)(a1 + 16) = *a3;
  *a3 = 0;
  if ( !*(_QWORD *)(a1 + 8) )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xB,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\contextentry.cpp",
      (const char *)0x80070057LL,
      lpData);
  hMem = 0;
  GetSystemTimeAsFileTime((LPFILETIME)&hMem);
  *(_QWORD *)Data = (unsigned int)hMem + ((unsigned __int64)HIDWORD(hMem) << 32);
  v10 = RegSetValueExW(*(HKEY *)(a1 + 16), L"Timestamp", 0, 0xBu, Data, 8u);
  if ( v10 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0xE,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\contextentry.cpp",
      (const char *)v10,
      lpDataa);
  return a1;
}

```

## disassembly

```asm
0x14004741c  mov     [rsp-18h+arg_10], rbx
0x140047421  mov     [rsp-18h+arg_0], rcx
0x140047426  push    rbp
0x140047427  push    rsi
0x140047428  push    rdi
0x140047429  mov     rbp, rsp
0x14004742c  sub     rsp, 40h
0x140047430  mov     rsi, r8
0x140047433  mov     rbx, rcx
0x140047436  mov     dword ptr [rbp+hMem], 0
0x14004743d  lea     rax, ??_7ContextEntry@details@Dynamo@@6B@; const Dynamo::details::ContextEntry::`vftable'
0x140047444  mov     [rcx], rax
0x140047447  test    rdx, rdx
0x14004744a  jz      short loc_14004747C
0x14004744c  or      r8, 0FFFFFFFFFFFFFFFFh
0x140047450  lea     rcx, [rbp+arg_18]
0x140047454  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x140047459  mov     dword ptr [rbp+hMem], 8
0x140047460  mov     rcx, [rbp+18h]; this
0x140047464  mov     rax, [rbp+arg_18]
0x140047468  test    rax, rax
0x14004746b  jz      loc_140047557
0x140047471  lea     rcx, [rbp+arg_18]
0x140047475  mov     edi, 5
0x14004747a  jmp     short loc_140047487
0x14004747c  lea     rcx, [rbp+hMem]
0x140047480  mov     edi, 2
0x140047485  xor     eax, eax
0x140047487  mov     [rbx+8], rax
0x14004748b  mov     qword ptr [rcx], 0
0x140047492  test    dil, 2
0x140047496  jz      short loc_1400474AA
0x140047498  and     edi, 0FFFFFFFDh
0x14004749b  mov     rcx, [rbp+hMem]; hMem
0x14004749f  test    rcx, rcx
0x1400474a2  jz      short loc_1400474AA
0x1400474a4  call    cs:__imp_LocalFree
0x1400474aa  test    dil, 1
0x1400474ae  jz      short loc_1400474BF
0x1400474b0  mov     rcx, [rbp+arg_18]; hMem
0x1400474b4  test    rcx, rcx
0x1400474b7  jz      short loc_1400474BF
0x1400474b9  call    cs:__imp_LocalFree
0x1400474bf  mov     rax, [rsi]
0x1400474c2  mov     [rbx+10h], rax
0x1400474c6  mov     qword ptr [rsi], 0
0x1400474cd  mov     rcx, [rbp+18h]; this
0x1400474d1  cmp     qword ptr [rbx+8], 0
0x1400474d6  jz      loc_140047569
0x1400474dc  mov     [rbp+hMem], 0
0x1400474e4  lea     rcx, [rbp+hMem]; lpSystemTimeAsFileTime
0x1400474e8  call    cs:__imp_GetSystemTimeAsFileTime
0x1400474ee  mov     ecx, dword ptr [rbp+hMem+4]
0x1400474f1  shl     rcx, 20h
0x1400474f5  mov     eax, dword ptr [rbp+hMem]
0x1400474f8  add     rcx, rax
0x1400474fb  mov     qword ptr [rbp+Data], rcx
0x1400474ff  mov     [rsp+40h+cbData], 8; cbData
0x140047507  lea     rax, [rbp+Data]
0x14004750b  mov     [rsp+40h+lpData], rax; unsigned int
0x140047510  mov     r9d, 0Bh; dwType
0x140047516  xor     r8d, r8d; Reserved
0x140047519  lea     rdx, aTimestamp; "Timestamp"
0x140047520  mov     rcx, [rbx+10h]; hKey
0x140047524  call    cs:__imp_RegSetValueExW
0x14004752a  mov     rcx, [rbp+18h]; this
0x14004752e  test    eax, eax
0x140047530  jnz     short loc_140047542
0x140047532  mov     rax, rbx
0x140047535  mov     rbx, [rsp+40h+arg_10]
0x14004753a  add     rsp, 40h
0x14004753e  pop     rdi
0x14004753f  pop     rsi
0x140047540  pop     rbp
0x140047541  retn
0x140047542  mov     r9d, eax; char *
0x140047545  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x14004754c  mov     edx, 0Eh; void *
0x140047551  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x140047557  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14004755e  mov     edx, 0FF8h; void *
0x140047563  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x140047569  mov     r9d, 80070057h; char *
0x14004756f  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x140047576  mov     edx, 0Bh; void *
0x14004757b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
