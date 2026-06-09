# CSearchRegistryRedirectHelper::MapRegistryKeyPath(wchar_t const *,wchar_t *,ulong)

- ea: `0x180084b10`
- end: `0x180084cdc`
- name: `?MapRegistryKeyPath@CSearchRegistryRedirectHelper@@QEAAJPEB_WPEA_WK@Z`
- size: `460`
- prototype: `int(CSearchRegistryRedirectHelper *__hidden this, const wchar_t *, wchar_t *, unsigned int)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800354d4`
- `0x1800390d0`
- `0x18005081c`

## callees

- `0x18002a220`
- `0x18003e5d0`
- `0x180052178`
- `0x18005bec0`
- `0x18005daf0`
- `0x180084b10`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180084b7b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180084c47`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180084b7b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180084c47`

## string_xrefs

- `0x180084ba5`: `onecoreuap\base\appmodel\search\common\utils\regredirect.cxx`
- `0x180084bde`: `onecoreuap\base\appmodel\search\common\utils\regredirect.cxx`

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
  v9 = LODWORD(off_1800B03A0[v6 + 2]);
  do
    ++v8;
  while ( a2[v8] );
  if ( (unsigned int)v8 >= (unsigned int)v9 && CompareStringOrdinal(a2, v9, off_1800B03A0[v6 + 1], -1, 1) == 2 )
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
        if ( (byte_1800B1442 & 0x20) != 0 )
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
0x180084b10  push    rbx
0x180084b12  push    rbp
0x180084b13  push    rsi
0x180084b14  push    rdi
0x180084b15  push    r12
0x180084b17  push    r14
0x180084b19  push    r15
0x180084b1b  sub     rsp, 60h
0x180084b1f  mov     rax, cs:__security_cookie
0x180084b26  xor     rax, rsp
0x180084b29  mov     [rsp+98h+var_48], rax
0x180084b2e  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180084b32  lea     rax, off_1800B03A0; "WSearch"
0x180084b39  mov     r14, r8
0x180084b3c  mov     rbx, rdx
0x180084b3f  imul    r8, [rcx], 228h
0x180084b46  mov     r15, rcx
0x180084b49  mov     rsi, rdi
0x180084b4c  xor     r12d, r12d
0x180084b4f  mov     ebp, [r8+rax+10h]
0x180084b54  inc     rsi
0x180084b57  cmp     [rdx+rsi*2], r12w
0x180084b5c  jnz     short loc_180084B54
0x180084b5e  cmp     esi, ebp
0x180084b60  jb      loc_180084C00
0x180084b66  mov     r8, [r8+rax+8]; lpString2
0x180084b6b  mov     r9d, edi; cchCount2
0x180084b6e  mov     edx, ebp; cchCount1
0x180084b70  mov     [rsp+98h+bIgnoreCase], 1; int
0x180084b78  mov     rcx, rbx; lpString1
0x180084b7b  call    cs:__imp_CompareStringOrdinal
0x180084b81  cmp     eax, 2
0x180084b84  jnz     short loc_180084C00
0x180084b86  lea     r8, [r15+8]; wchar_t *
0x180084b8a  mov     edx, 104h; unsigned __int64
0x180084b8f  mov     rcx, r14; wchar_t *
0x180084b92  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180084b97  mov     edi, eax
0x180084b99  test    eax, eax
0x180084b9b  jns     short loc_180084BC0
0x180084b9d  mov     rcx, [rsp+98h]; this
0x180084ba5  lea     r8, aOnecoreuapBase_11; "onecoreuap\\base\\appmodel\\search\\com"...
0x180084bac  mov     r9d, eax; char *
0x180084baf  mov     edx, 46h ; 'F'; void *
0x180084bb4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180084bb9  mov     eax, edi
0x180084bbb  jmp     loc_180084CC0
0x180084bc0  cmp     esi, ebp
0x180084bc2  jbe     short loc_180084BF9
0x180084bc4  lea     r8, [rbx+rbp*2]; wchar_t *
0x180084bc8  mov     rcx, r14; wchar_t *
0x180084bcb  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180084bd0  mov     ebx, eax
0x180084bd2  test    eax, eax
0x180084bd4  jns     short loc_180084BF9
0x180084bd6  mov     rcx, [rsp+98h]; this
0x180084bde  lea     r8, aOnecoreuapBase_11; "onecoreuap\\base\\appmodel\\search\\com"...
0x180084be5  mov     r9d, eax; char *
0x180084be8  mov     edx, 49h ; 'I'; void *
0x180084bed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180084bf2  mov     eax, ebx
0x180084bf4  jmp     loc_180084CC0
0x180084bf9  xor     eax, eax
0x180084bfb  jmp     loc_180084CC0
0x180084c00  lea     rax, aSoftware; "Software"
0x180084c07  mov     esi, r12d
0x180084c0a  mov     [rsp+98h+lpString2], rax
0x180084c0f  lea     rax, aSystem; "System"
0x180084c16  mov     [rsp+98h+var_60], rax
0x180084c1b  cmp     esi, 2
0x180084c1e  jnb     loc_180084CBB
0x180084c24  movsxd  rax, esi
0x180084c27  mov     rdx, rdi
0x180084c2a  mov     r8, [rsp+rax*8+98h+lpString2]; lpString2
0x180084c2f  inc     rdx; cchCount1
0x180084c32  cmp     [r8+rdx*2], r12w
0x180084c37  jnz     short loc_180084C2F
0x180084c39  mov     r9d, edi; cchCount2
0x180084c3c  mov     [rsp+98h+bIgnoreCase], 1; bIgnoreCase
0x180084c44  mov     rcx, rbx; lpString1
0x180084c47  call    cs:__imp_CompareStringOrdinal
0x180084c4d  cmp     eax, 2
0x180084c50  jz      short loc_180084C56
0x180084c52  inc     esi
0x180084c54  jmp     short loc_180084C1B
0x180084c56  test    cs:byte_1800B1442, 20h
0x180084c5d  jz      short loc_180084CBB
0x180084c5f  test    rbx, rbx
0x180084c62  jz      short loc_180084C77
0x180084c64  inc     rdi
0x180084c67  cmp     [rbx+rdi*2], r12w
0x180084c6c  jnz     short loc_180084C64
0x180084c6e  lea     edi, ds:2[rdi*2]
0x180084c75  jmp     short loc_180084C7C
0x180084c77  mov     edi, 0Ah
0x180084c7c  test    rbx, rbx
0x180084c7f  mov     [rsp+98h+var_50], edi
0x180084c83  lea     rax, aNull_0; "NULL"
0x180084c8a  mov     [rsp+98h+var_4C], r12d
0x180084c8f  cmovz   rbx, rax
0x180084c93  lea     rdx, MSSearchTraceId_ETWLogging
0x180084c9a  lea     rax, [rsp+98h+lpString2]
0x180084c9f  mov     [rsp+98h+var_58], rbx
0x180084ca4  mov     r9d, 2
0x180084caa  mov     qword ptr [rsp+98h+bIgnoreCase], rax
0x180084caf  lea     rcx, Microsoft_Windows_Search_Core_Context
0x180084cb6  call    McGenEventWrite_EventWriteTransfer
0x180084cbb  mov     eax, 80004005h
0x180084cc0  mov     rcx, [rsp+98h+var_48]
0x180084cc5  xor     rcx, rsp; StackCookie
0x180084cc8  call    __security_check_cookie
0x180084ccd  add     rsp, 60h
0x180084cd1  pop     r15
0x180084cd3  pop     r14
0x180084cd5  pop     r12
0x180084cd7  pop     rdi
0x180084cd8  pop     rsi
0x180084cd9  pop     rbp
0x180084cda  pop     rbx
0x180084cdb  retn
```
