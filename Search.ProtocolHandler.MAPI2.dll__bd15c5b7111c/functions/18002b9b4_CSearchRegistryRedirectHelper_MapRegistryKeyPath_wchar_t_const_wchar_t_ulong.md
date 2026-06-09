# CSearchRegistryRedirectHelper::MapRegistryKeyPath(wchar_t const *,wchar_t *,ulong)

- ea: `0x18002b9b4`
- end: `0x18002bb80`
- name: `?MapRegistryKeyPath@CSearchRegistryRedirectHelper@@QEAAJPEB_WPEA_WK@Z`
- size: `460`
- prototype: `int(CSearchRegistryRedirectHelper *__hidden this, const wchar_t *, wchar_t *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002b944`

## callees

- `0x180002300`
- `0x18000835c`
- `0x180008a20`
- `0x180008a9c`
- `0x180017894`
- `0x18002b9b4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002ba1f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002baeb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002ba1f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002baeb`

## string_xrefs

- `0x18002ba49`: `onecoreuap\base\appmodel\search\common\utils\regredirect.cxx`
- `0x18002ba82`: `onecoreuap\base\appmodel\search\common\utils\regredirect.cxx`

## pseudocode

```c
__int64 __fastcall CSearchRegistryRedirectHelper::MapRegistryKeyPath(
        const wchar_t *this,
        const wchar_t *a2,
        wchar_t *a3)
{
  __int64 v3; // rdi
  const WCHAR *v5; // rbx
  __int64 v6; // r8
  __int64 v8; // rsi
  __int64 v9; // rbp
  int v10; // eax
  unsigned __int64 v11; // rdx
  unsigned int v12; // edi
  int v14; // eax
  unsigned int v15; // ebx
  unsigned int v16; // esi
  __int64 v17; // rdx
  const WCHAR *v18; // r8
  __int64 v19; // r8
  int v20; // edi
  int bIgnoreCase; // [rsp+20h] [rbp-78h]
  LPCWCH lpString2[3]; // [rsp+30h] [rbp-68h] BYREF
  int v23; // [rsp+48h] [rbp-50h]
  int v24; // [rsp+4Ch] [rbp-4Ch]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v3 = -1;
  v5 = a2;
  v6 = 69LL * *(_QWORD *)this;
  v8 = -1;
  v9 = LODWORD(off_1800588E0[v6 + 2]);
  do
    ++v8;
  while ( a2[v8] );
  if ( (unsigned int)v8 >= (unsigned int)v9 && CompareStringOrdinal(a2, v9, off_1800588E0[v6 + 1], -1, 1) == 2 )
  {
    v10 = StringCchCopyW(a3, 0x104u, this + 4);
    v12 = v10;
    if ( v10 >= 0 )
    {
      if ( (unsigned int)v8 <= (unsigned int)v9 )
        return 0;
      v14 = StringCchCatW(a3, v11, &v5[v9]);
      v15 = v14;
      if ( v14 >= 0 )
      {
        return 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x49,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\utils\\regredirect.cxx",
          (const char *)(unsigned int)v14,
          bIgnoreCase);
        return v15;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x46,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\utils\\regredirect.cxx",
        (const char *)(unsigned int)v10,
        bIgnoreCase);
      return v12;
    }
  }
  else
  {
    v16 = 0;
    lpString2[0] = L"Software";
    lpString2[1] = L"System";
    while ( v16 < 2 )
    {
      v17 = -1;
      v18 = lpString2[v16];
      do
        ++v17;
      while ( v18[v17] );
      if ( CompareStringOrdinal(v5, v17, v18, -1, 1) == 2 )
      {
        if ( (byte_180059F02 & 0x20) != 0 )
        {
          if ( v5 )
          {
            do
              ++v3;
            while ( v5[v3] );
            v20 = 2 * v3 + 2;
          }
          else
          {
            v20 = 10;
          }
          v23 = v20;
          v24 = 0;
          if ( !v5 )
            v5 = L"NULL";
          lpString2[2] = v5;
          McGenEventWrite_EventWriteTransfer(
            Microsoft_Windows_Search_Core_Context,
            MSSearchTraceId_ETWLogging,
            v19,
            2,
            lpString2);
        }
        return 2147500037LL;
      }
      ++v16;
    }
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x18002b9b4  push    rbx
0x18002b9b6  push    rbp
0x18002b9b7  push    rsi
0x18002b9b8  push    rdi
0x18002b9b9  push    r12
0x18002b9bb  push    r14
0x18002b9bd  push    r15
0x18002b9bf  sub     rsp, 60h
0x18002b9c3  mov     rax, cs:__security_cookie
0x18002b9ca  xor     rax, rsp
0x18002b9cd  mov     [rsp+98h+var_48], rax
0x18002b9d2  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002b9d6  lea     rax, off_1800588E0; "WSearch"
0x18002b9dd  mov     r14, r8
0x18002b9e0  mov     rbx, rdx
0x18002b9e3  imul    r8, [rcx], 228h
0x18002b9ea  mov     r15, rcx
0x18002b9ed  mov     rsi, rdi
0x18002b9f0  xor     r12d, r12d
0x18002b9f3  mov     ebp, [r8+rax+10h]
0x18002b9f8  inc     rsi
0x18002b9fb  cmp     [rdx+rsi*2], r12w
0x18002ba00  jnz     short loc_18002B9F8
0x18002ba02  cmp     esi, ebp
0x18002ba04  jb      loc_18002BAA4
0x18002ba0a  mov     r8, [r8+rax+8]; lpString2
0x18002ba0f  mov     r9d, edi; cchCount2
0x18002ba12  mov     edx, ebp; cchCount1
0x18002ba14  mov     [rsp+98h+bIgnoreCase], 1; int
0x18002ba1c  mov     rcx, rbx; lpString1
0x18002ba1f  call    cs:__imp_CompareStringOrdinal
0x18002ba25  cmp     eax, 2
0x18002ba28  jnz     short loc_18002BAA4
0x18002ba2a  lea     r8, [r15+8]; wchar_t *
0x18002ba2e  mov     edx, 104h; unsigned __int64
0x18002ba33  mov     rcx, r14; wchar_t *
0x18002ba36  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18002ba3b  mov     edi, eax
0x18002ba3d  test    eax, eax
0x18002ba3f  jns     short loc_18002BA64
0x18002ba41  mov     rcx, [rsp+98h]; this
0x18002ba49  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\appmodel\\search\\com"...
0x18002ba50  mov     r9d, eax; char *
0x18002ba53  mov     edx, 46h ; 'F'; void *
0x18002ba58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ba5d  mov     eax, edi
0x18002ba5f  jmp     loc_18002BB64
0x18002ba64  cmp     esi, ebp
0x18002ba66  jbe     short loc_18002BA9D
0x18002ba68  lea     r8, [rbx+rbp*2]; wchar_t *
0x18002ba6c  mov     rcx, r14; wchar_t *
0x18002ba6f  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18002ba74  mov     ebx, eax
0x18002ba76  test    eax, eax
0x18002ba78  jns     short loc_18002BA9D
0x18002ba7a  mov     rcx, [rsp+98h]; this
0x18002ba82  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\appmodel\\search\\com"...
0x18002ba89  mov     r9d, eax; char *
0x18002ba8c  mov     edx, 49h ; 'I'; void *
0x18002ba91  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ba96  mov     eax, ebx
0x18002ba98  jmp     loc_18002BB64
0x18002ba9d  xor     eax, eax
0x18002ba9f  jmp     loc_18002BB64
0x18002baa4  lea     rax, aSoftware; "Software"
0x18002baab  mov     esi, r12d
0x18002baae  mov     [rsp+98h+lpString2], rax
0x18002bab3  lea     rax, aSystem_0; "System"
0x18002baba  mov     [rsp+98h+var_60], rax
0x18002babf  cmp     esi, 2
0x18002bac2  jnb     loc_18002BB5F
0x18002bac8  movsxd  rax, esi
0x18002bacb  mov     rdx, rdi
0x18002bace  mov     r8, [rsp+rax*8+98h+lpString2]; lpString2
0x18002bad3  inc     rdx; cchCount1
0x18002bad6  cmp     [r8+rdx*2], r12w
0x18002badb  jnz     short loc_18002BAD3
0x18002badd  mov     r9d, edi; cchCount2
0x18002bae0  mov     [rsp+98h+bIgnoreCase], 1; bIgnoreCase
0x18002bae8  mov     rcx, rbx; lpString1
0x18002baeb  call    cs:__imp_CompareStringOrdinal
0x18002baf1  cmp     eax, 2
0x18002baf4  jz      short loc_18002BAFA
0x18002baf6  inc     esi
0x18002baf8  jmp     short loc_18002BABF
0x18002bafa  test    cs:byte_180059F02, 20h
0x18002bb01  jz      short loc_18002BB5F
0x18002bb03  test    rbx, rbx
0x18002bb06  jz      short loc_18002BB1B
0x18002bb08  inc     rdi
0x18002bb0b  cmp     [rbx+rdi*2], r12w
0x18002bb10  jnz     short loc_18002BB08
0x18002bb12  lea     edi, ds:2[rdi*2]
0x18002bb19  jmp     short loc_18002BB20
0x18002bb1b  mov     edi, 0Ah
0x18002bb20  test    rbx, rbx
0x18002bb23  mov     [rsp+98h+var_50], edi
0x18002bb27  lea     rax, aNull; "NULL"
0x18002bb2e  mov     [rsp+98h+var_4C], r12d
0x18002bb33  cmovz   rbx, rax
0x18002bb37  lea     rdx, MSSearchTraceId_ETWLogging
0x18002bb3e  lea     rax, [rsp+98h+lpString2]
0x18002bb43  mov     [rsp+98h+var_58], rbx
0x18002bb48  mov     r9d, 2
0x18002bb4e  mov     qword ptr [rsp+98h+bIgnoreCase], rax
0x18002bb53  lea     rcx, Microsoft_Windows_Search_Core_Context
0x18002bb5a  call    McGenEventWrite_EventWriteTransfer
0x18002bb5f  mov     eax, 80004005h
0x18002bb64  mov     rcx, [rsp+98h+var_48]
0x18002bb69  xor     rcx, rsp; StackCookie
0x18002bb6c  call    __security_check_cookie
0x18002bb71  add     rsp, 60h
0x18002bb75  pop     r15
0x18002bb77  pop     r14
0x18002bb79  pop     r12
0x18002bb7b  pop     rdi
0x18002bb7c  pop     rsi
0x18002bb7d  pop     rbp
0x18002bb7e  pop     rbx
0x18002bb7f  retn
```
