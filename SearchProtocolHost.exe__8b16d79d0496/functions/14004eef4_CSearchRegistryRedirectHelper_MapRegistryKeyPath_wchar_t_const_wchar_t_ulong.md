# CSearchRegistryRedirectHelper::MapRegistryKeyPath(wchar_t const *,wchar_t *,ulong)

- ea: `0x14004eef4`
- end: `0x14004f047`
- name: `?MapRegistryKeyPath@CSearchRegistryRedirectHelper@@QEAAJPEB_WPEA_WK@Z`
- size: `339`
- prototype: `int(CSearchRegistryRedirectHelper *__hidden this, const wchar_t *, wchar_t *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14004ee84`

## callees

- `0x140028044`
- `0x1400299fc`
- `0x140029a48`
- `0x140039e10`
- `0x14004eef4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14004ef50`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14004f00c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14004ef50`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14004f00c`

## string_xrefs

- `0x14004ef77`: `onecoreuap\base\appmodel\search\common\utils\regredirect.cxx`
- `0x14004efad`: `onecoreuap\base\appmodel\search\common\utils\regredirect.cxx`

## pseudocode

```c
__int64 __fastcall CSearchRegistryRedirectHelper::MapRegistryKeyPath(
        const wchar_t *this,
        const wchar_t *a2,
        wchar_t *a3)
{
  __int64 v5; // r8
  __int64 v7; // rbx
  __int64 v8; // rbp
  int v9; // eax
  unsigned __int64 v10; // rdx
  unsigned int v11; // edi
  int v13; // eax
  unsigned int v14; // ebx
  unsigned int v15; // ebx
  __int64 v16; // rdx
  const WCHAR *v17; // r8
  __int64 v18; // rcx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-58h]
  LPCWCH lpString2[9]; // [rsp+30h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v5 = 69LL * *(_QWORD *)this;
  v7 = -1;
  v8 = LODWORD(off_140096310[v5 + 2]);
  do
    ++v7;
  while ( a2[v7] );
  if ( (unsigned int)v7 >= (unsigned int)v8 && CompareStringOrdinal(a2, v8, off_140096310[v5 + 1], -1, 1) == 2 )
  {
    v9 = StringCchCopyW(a3, 0x104u, this + 4);
    v11 = v9;
    if ( v9 >= 0 )
    {
      if ( (unsigned int)v7 <= (unsigned int)v8 )
        return 0;
      v13 = StringCchCatW(a3, v10, &a2[v8]);
      v14 = v13;
      if ( v13 >= 0 )
      {
        return 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x49,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\utils\\regredirect.cxx",
          (const char *)(unsigned int)v13,
          bIgnoreCase);
        return v14;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x46,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\utils\\regredirect.cxx",
        (const char *)(unsigned int)v9,
        bIgnoreCase);
      return v11;
    }
  }
  else
  {
    v15 = 0;
    lpString2[0] = L"Software";
    lpString2[1] = L"System";
    while ( v15 < 2 )
    {
      v16 = -1;
      v17 = lpString2[v15];
      do
        ++v16;
      while ( v17[v16] );
      if ( CompareStringOrdinal(a2, v16, v17, -1, 1) == 2 )
      {
        if ( (byte_140097A02 & 0x20) != 0 )
          McTemplateU0z_EventWriteTransfer(v18, &MSSearchTraceId_ETWLogging, a2);
        return 2147500037LL;
      }
      ++v15;
    }
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x14004eef4  push    rbx
0x14004eef6  push    rbp
0x14004eef7  push    rsi
0x14004eef8  push    rdi
0x14004eef9  push    r13
0x14004eefb  push    r14
0x14004eefd  push    r15
0x14004eeff  sub     rsp, 40h
0x14004ef03  or      r13, 0FFFFFFFFFFFFFFFFh
0x14004ef07  lea     rax, off_140096310; "WSearch"
0x14004ef0e  mov     r14, r8
0x14004ef11  mov     rsi, rdx
0x14004ef14  imul    r8, [rcx], 228h
0x14004ef1b  mov     rdi, rcx
0x14004ef1e  mov     rbx, r13
0x14004ef21  xor     r15d, r15d
0x14004ef24  mov     ebp, [r8+rax+10h]
0x14004ef29  inc     rbx
0x14004ef2c  cmp     [rdx+rbx*2], r15w
0x14004ef31  jnz     short loc_14004EF29
0x14004ef33  cmp     ebx, ebp
0x14004ef35  jb      loc_14004EFC9
0x14004ef3b  mov     r8, [r8+rax+8]; lpString2
0x14004ef40  mov     r9d, r13d; cchCount2
0x14004ef43  mov     edx, ebp; cchCount1
0x14004ef45  mov     [rsp+78h+bIgnoreCase], 1; int
0x14004ef4d  mov     rcx, rsi; lpString1
0x14004ef50  call    cs:__imp_CompareStringOrdinal
0x14004ef56  cmp     eax, 2
0x14004ef59  jnz     short loc_14004EFC9
0x14004ef5b  lea     r8, [rdi+8]; wchar_t *
0x14004ef5f  mov     edx, 104h; unsigned __int64
0x14004ef64  mov     rcx, r14; wchar_t *
0x14004ef67  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x14004ef6c  mov     edi, eax
0x14004ef6e  test    eax, eax
0x14004ef70  jns     short loc_14004EF92
0x14004ef72  mov     rcx, [rsp+78h]; this
0x14004ef77  lea     r8, aOnecoreuapBase_53; "onecoreuap\\base\\appmodel\\search\\com"...
0x14004ef7e  mov     r9d, eax; char *
0x14004ef81  mov     edx, 46h ; 'F'; void *
0x14004ef86  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004ef8b  mov     eax, edi
0x14004ef8d  jmp     loc_14004F038
0x14004ef92  cmp     ebx, ebp
0x14004ef94  jbe     short loc_14004EFC5
0x14004ef96  lea     r8, [rsi+rbp*2]; wchar_t *
0x14004ef9a  mov     rcx, r14; wchar_t *
0x14004ef9d  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x14004efa2  mov     ebx, eax
0x14004efa4  test    eax, eax
0x14004efa6  jns     short loc_14004EFC5
0x14004efa8  mov     rcx, [rsp+78h]; this
0x14004efad  lea     r8, aOnecoreuapBase_53; "onecoreuap\\base\\appmodel\\search\\com"...
0x14004efb4  mov     r9d, eax; char *
0x14004efb7  mov     edx, 49h ; 'I'; void *
0x14004efbc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004efc1  mov     eax, ebx
0x14004efc3  jmp     short loc_14004F038
0x14004efc5  xor     eax, eax
0x14004efc7  jmp     short loc_14004F038
0x14004efc9  lea     rax, aSoftware; "Software"
0x14004efd0  mov     ebx, r15d
0x14004efd3  mov     [rsp+78h+lpString2], rax
0x14004efd8  lea     rax, aSystem_0; "System"
0x14004efdf  mov     [rsp+78h+var_40], rax
0x14004efe4  cmp     ebx, 2
0x14004efe7  jnb     short loc_14004F033
0x14004efe9  movsxd  rax, ebx
0x14004efec  mov     rdx, r13
0x14004efef  mov     r8, [rsp+rax*8+78h+lpString2]; lpString2
0x14004eff4  inc     rdx; cchCount1
0x14004eff7  cmp     [r8+rdx*2], r15w
0x14004effc  jnz     short loc_14004EFF4
0x14004effe  mov     r9d, r13d; cchCount2
0x14004f001  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x14004f009  mov     rcx, rsi; lpString1
0x14004f00c  call    cs:__imp_CompareStringOrdinal
0x14004f012  cmp     eax, 2
0x14004f015  jz      short loc_14004F01B
0x14004f017  inc     ebx
0x14004f019  jmp     short loc_14004EFE4
0x14004f01b  test    cs:byte_140097A02, 20h
0x14004f022  jz      short loc_14004F033
0x14004f024  mov     r8, rsi
0x14004f027  lea     rdx, MSSearchTraceId_ETWLogging
0x14004f02e  call    McTemplateU0z_EventWriteTransfer
0x14004f033  mov     eax, 80004005h
0x14004f038  add     rsp, 40h
0x14004f03c  pop     r15
0x14004f03e  pop     r14
0x14004f040  pop     r13
0x14004f042  pop     rdi
0x14004f043  pop     rsi
0x14004f044  pop     rbp
0x14004f045  pop     rbx
0x14004f046  retn
```
