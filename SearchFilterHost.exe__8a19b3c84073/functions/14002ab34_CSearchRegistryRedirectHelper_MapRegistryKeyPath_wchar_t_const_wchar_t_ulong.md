# CSearchRegistryRedirectHelper::MapRegistryKeyPath(wchar_t const *,wchar_t *,ulong)

- ea: `0x14002ab34`
- end: `0x14002acf3`
- name: `?MapRegistryKeyPath@CSearchRegistryRedirectHelper@@QEAAJPEB_WPEA_WK@Z`
- size: `447`
- prototype: `int(CSearchRegistryRedirectHelper *__hidden this, const wchar_t *, wchar_t *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14002aac4`

## callees

- `0x1400030a0`
- `0x140009f14`
- `0x14000a608`
- `0x14000a730`
- `0x140027490`
- `0x14002ab34`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14002ab9f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14002ac6b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14002ab9f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14002ac6b`

## string_xrefs

- `0x14002abc9`: `onecoreuap\base\appmodel\search\common\utils\regredirect.cxx`
- `0x14002ac02`: `onecoreuap\base\appmodel\search\common\utils\regredirect.cxx`

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
  size_t *v10; // r8
  HRESULT v11; // eax
  unsigned __int64 v12; // rdx
  unsigned int v13; // edi
  int v15; // eax
  unsigned int v16; // ebx
  unsigned int v17; // esi
  __int64 v18; // rdx
  const WCHAR *v19; // r8
  int v20; // ecx
  int v21; // r8d
  int v22; // r9d
  int v23; // edi
  BOOL bIgnoreCase[2]; // [rsp+20h] [rbp-78h]
  int bIgnoreCasea; // [rsp+20h] [rbp-78h]
  struct _EVENT_DATA_DESCRIPTOR lpString2; // [rsp+30h] [rbp-68h] BYREF
  const WCHAR *v27; // [rsp+40h] [rbp-58h]
  int v28; // [rsp+48h] [rbp-50h]
  int v29; // [rsp+4Ch] [rbp-4Ch]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v3 = -1;
  v5 = a2;
  v6 = 69LL * *(_QWORD *)this;
  v8 = -1;
  v9 = LODWORD(off_14006A210[v6 + 2]);
  do
    ++v8;
  while ( a2[v8] );
  if ( (unsigned int)v8 >= (unsigned int)v9 && CompareStringOrdinal(a2, v9, off_14006A210[v6 + 1], -1, 1) == 2 )
  {
    v11 = StringCopyWorkerW(a3, 0x104u, v10, this + 4, *(size_t *)bIgnoreCase);
    v13 = v11;
    if ( v11 >= 0 )
    {
      if ( (unsigned int)v8 <= (unsigned int)v9 )
        return 0;
      v15 = StringCchCatW(a3, v12, &v5[v9]);
      v16 = v15;
      if ( v15 >= 0 )
      {
        return 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x49,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\utils\\regredirect.cxx",
          (const char *)(unsigned int)v15,
          bIgnoreCasea);
        return v16;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x46,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\utils\\regredirect.cxx",
        (const char *)(unsigned int)v11,
        bIgnoreCasea);
      return v13;
    }
  }
  else
  {
    v17 = 0;
    lpString2.Ptr = (ULONGLONG)L"Software";
    *(_QWORD *)&lpString2.Size = L"System";
    while ( v17 < 2 )
    {
      v18 = -1;
      v19 = (const WCHAR *)*(&lpString2.Ptr + (int)v17);
      do
        ++v18;
      while ( v19[v18] );
      if ( CompareStringOrdinal(v5, v18, v19, -1, 1) == 2 )
      {
        if ( (byte_14006B842 & 0x20) != 0 )
        {
          if ( v5 )
          {
            do
              ++v3;
            while ( v5[v3] );
            v23 = 2 * v3 + 2;
          }
          else
          {
            v23 = 10;
          }
          v28 = v23;
          v29 = 0;
          if ( !v5 )
            v5 = L"NULL";
          v27 = v5;
          McGenEventWrite_EventWriteTransfer(v20, (int)&MSSearchTraceId_ETWLogging, v21, v22, &lpString2);
        }
        return 2147500037LL;
      }
      ++v17;
    }
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x14002ab34  push    rbx
0x14002ab36  push    rbp
0x14002ab37  push    rsi
0x14002ab38  push    rdi
0x14002ab39  push    r12
0x14002ab3b  push    r14
0x14002ab3d  push    r15
0x14002ab3f  sub     rsp, 60h
0x14002ab43  mov     rax, cs:__security_cookie
0x14002ab4a  xor     rax, rsp
0x14002ab4d  mov     [rsp+98h+var_48], rax
0x14002ab52  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14002ab56  lea     rax, off_14006A210; "WSearch"
0x14002ab5d  mov     r14, r8
0x14002ab60  mov     rbx, rdx
0x14002ab63  imul    r8, [rcx], 228h
0x14002ab6a  mov     r15, rcx
0x14002ab6d  mov     rsi, rdi
0x14002ab70  xor     r12d, r12d
0x14002ab73  mov     ebp, [r8+rax+10h]
0x14002ab78  inc     rsi
0x14002ab7b  cmp     [rdx+rsi*2], r12w
0x14002ab80  jnz     short loc_14002AB78
0x14002ab82  cmp     esi, ebp
0x14002ab84  jb      loc_14002AC24
0x14002ab8a  mov     r8, [r8+rax+8]; lpString2
0x14002ab8f  mov     r9d, edi; cchCount2
0x14002ab92  mov     edx, ebp; cchCount1
0x14002ab94  mov     [rsp+98h+bIgnoreCase], 1; int
0x14002ab9c  mov     rcx, rbx; lpString1
0x14002ab9f  call    cs:__imp_CompareStringOrdinal
0x14002aba5  cmp     eax, 2
0x14002aba8  jnz     short loc_14002AC24
0x14002abaa  lea     r9, [r15+8]; pszSrc
0x14002abae  mov     edx, 104h; cchDest
0x14002abb3  mov     rcx, r14; pszDest
0x14002abb6  call    StringCopyWorkerW
0x14002abbb  mov     edi, eax
0x14002abbd  test    eax, eax
0x14002abbf  jns     short loc_14002ABE4
0x14002abc1  mov     rcx, [rsp+98h]; this
0x14002abc9  lea     r8, aOnecoreuapBase_37; "onecoreuap\\base\\appmodel\\search\\com"...
0x14002abd0  mov     r9d, eax; char *
0x14002abd3  mov     edx, 46h ; 'F'; void *
0x14002abd8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002abdd  mov     eax, edi
0x14002abdf  jmp     loc_14002ACD7
0x14002abe4  cmp     esi, ebp
0x14002abe6  jbe     short loc_14002AC1D
0x14002abe8  lea     r8, [rbx+rbp*2]; wchar_t *
0x14002abec  mov     rcx, r14; wchar_t *
0x14002abef  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x14002abf4  mov     ebx, eax
0x14002abf6  test    eax, eax
0x14002abf8  jns     short loc_14002AC1D
0x14002abfa  mov     rcx, [rsp+98h]; this
0x14002ac02  lea     r8, aOnecoreuapBase_37; "onecoreuap\\base\\appmodel\\search\\com"...
0x14002ac09  mov     r9d, eax; char *
0x14002ac0c  mov     edx, 49h ; 'I'; void *
0x14002ac11  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002ac16  mov     eax, ebx
0x14002ac18  jmp     loc_14002ACD7
0x14002ac1d  xor     eax, eax
0x14002ac1f  jmp     loc_14002ACD7
0x14002ac24  lea     rax, aSoftware; "Software"
0x14002ac2b  mov     esi, r12d
0x14002ac2e  mov     [rsp+98h+lpString2], rax
0x14002ac33  lea     rax, aSystem_0; "System"
0x14002ac3a  mov     [rsp+98h+var_60], rax
0x14002ac3f  cmp     esi, 2
0x14002ac42  jnb     loc_14002ACD2
0x14002ac48  movsxd  rax, esi
0x14002ac4b  mov     rdx, rdi
0x14002ac4e  mov     r8, [rsp+rax*8+98h+lpString2]; lpString2
0x14002ac53  inc     rdx; cchCount1
0x14002ac56  cmp     [r8+rdx*2], r12w
0x14002ac5b  jnz     short loc_14002AC53
0x14002ac5d  mov     r9d, edi; cchCount2
0x14002ac60  mov     [rsp+98h+bIgnoreCase], 1; bIgnoreCase
0x14002ac68  mov     rcx, rbx; lpString1
0x14002ac6b  call    cs:__imp_CompareStringOrdinal
0x14002ac71  cmp     eax, 2
0x14002ac74  jz      short loc_14002AC7A
0x14002ac76  inc     esi
0x14002ac78  jmp     short loc_14002AC3F
0x14002ac7a  test    cs:byte_14006B842, 20h
0x14002ac81  jz      short loc_14002ACD2
0x14002ac83  test    rbx, rbx
0x14002ac86  jz      short loc_14002AC9B
0x14002ac88  inc     rdi
0x14002ac8b  cmp     [rbx+rdi*2], r12w
0x14002ac90  jnz     short loc_14002AC88
0x14002ac92  lea     edi, ds:2[rdi*2]
0x14002ac99  jmp     short loc_14002ACA0
0x14002ac9b  mov     edi, 0Ah
0x14002aca0  test    rbx, rbx
0x14002aca3  mov     [rsp+98h+var_50], edi
0x14002aca7  lea     rax, aNull; "NULL"
0x14002acae  mov     [rsp+98h+var_4C], r12d
0x14002acb3  cmovz   rbx, rax
0x14002acb7  lea     rdx, MSSearchTraceId_ETWLogging; int
0x14002acbe  lea     rax, [rsp+98h+lpString2]
0x14002acc3  mov     [rsp+98h+var_58], rbx
0x14002acc8  mov     qword ptr [rsp+98h+bIgnoreCase], rax; PEVENT_DATA_DESCRIPTOR
0x14002accd  call    McGenEventWrite_EventWriteTransfer
0x14002acd2  mov     eax, 80004005h
0x14002acd7  mov     rcx, [rsp+98h+var_48]
0x14002acdc  xor     rcx, rsp; StackCookie
0x14002acdf  call    __security_check_cookie
0x14002ace4  add     rsp, 60h
0x14002ace8  pop     r15
0x14002acea  pop     r14
0x14002acec  pop     r12
0x14002acee  pop     rdi
0x14002acef  pop     rsi
0x14002acf0  pop     rbp
0x14002acf1  pop     rbx
0x14002acf2  retn
```
