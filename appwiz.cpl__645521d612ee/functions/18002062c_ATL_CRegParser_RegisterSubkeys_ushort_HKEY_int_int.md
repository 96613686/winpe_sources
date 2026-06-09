# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x18002062c`
- end: `0x180020c29`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1533`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x1800202fc`
- `0x18002062c`

## callees

- `0x18001f0a0`
- `0x18001f664`
- `0x18001f6d4`
- `0x18001f71c`
- `0x18001f800`
- `0x18001f8d4`
- `0x18001fc9c`
- `0x18001fda4`
- `0x18001ff04`
- `0x1800201e8`
- `0x18002062c`
- `0x1800216c4`
- `0x180021794`
- `0x1800582e0`
- `0x1800583a0`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180020a46`
- `msvcrt!wcsncpy_s` at `0x180020a46`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180020947`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180020947`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180020887`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180020887`
- `KERNEL32!lstrcmpiW` at `0x18002069f`
- `KERNEL32!lstrcmpiW` at `0x1800206b2`
- `KERNEL32!lstrcmpiW` at `0x180020796`
- `KERNEL32!lstrcmpiW` at `0x1800207c5`
- `KERNEL32!lstrcmpiW` at `0x18002069f`
- `KERNEL32!lstrcmpiW` at `0x1800206b2`
- `KERNEL32!lstrcmpiW` at `0x180020796`
- `KERNEL32!lstrcmpiW` at `0x1800207c5`

## string_xrefs

- `0x1800206a5`: `ForceRemove`
- `0x180020786`: `NoRemove`
- `0x180020695`: `Delete`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterSubkeys(
        ATL::CRegParser *this,
        unsigned __int16 *a2,
        HKEY a3,
        int a4,
        int a5)
{
  int v5; // r15d
  unsigned __int16 *v7; // rdi
  ATL::CRegParser *i; // rsi
  int Token; // eax
  int v10; // r14d
  int v11; // ebx
  ATL::CRegParser *v12; // rcx
  int v13; // eax
  int v14; // r12d
  LSTATUS v15; // eax
  LSTATUS v16; // ebx
  __int64 v17; // rax
  unsigned int v18; // r14d
  int v19; // r15d
  errno_t v20; // eax
  int v21; // eax
  ATL::CRegParser *v22; // rcx
  __int64 v23; // rax
  int HasSubKeys; // r15d
  unsigned int v25; // r14d
  unsigned int v27; // ecx
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v30; // [rsp+60h] [rbp-A0h]
  __int64 v31; // [rsp+68h] [rbp-98h]
  HKEY v32[3]; // [rsp+70h] [rbp-90h] BYREF
  DWORD dwDisposition; // [rsp+88h] [rbp-78h] BYREF
  HKEY phkResult; // [rsp+90h] [rbp-70h] BYREF
  wchar_t Destination[264]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR ValueName[4096]; // [rsp+2B0h] [rbp+1B0h] BYREF

  memset(v32, 0, sizeof(v32));
  v5 = a4;
  v7 = a2;
  for ( i = this; ; this = i )
  {
    Token = ATL::CRegParser::NextToken(this, a2);
LABEL_31:
    v11 = Token;
    if ( Token < 0 )
      break;
    while ( 1 )
    {
      while ( 1 )
      {
        if ( *v7 == 125 )
          goto LABEL_79;
        v10 = lstrcmpiW(v7, L"Delete");
        if ( !lstrcmpiW(v7, L"ForceRemove") || !v10 )
        {
          v11 = ATL::CRegParser::NextToken(i, v7);
          if ( v11 < 0 )
            goto LABEL_79;
          if ( v5 )
          {
            hKey = 0;
            v30 = 0;
            v31 = 0;
            if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
            {
              ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_78:
              v11 = -2147352567;
              goto LABEL_79;
            }
            if ( ATL::CRegParser::CanForceRemoveKey(v12, v7) )
            {
              hKey = a3;
              ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)&hKey, v7);
              hKey = 0;
            }
            if ( !v10 )
            {
              v11 = ATL::CRegParser::NextToken(i, v7);
              if ( v11 < 0 )
                goto LABEL_81;
              v13 = ATL::CRegParser::SkipAssignment(i, v7);
LABEL_14:
              v11 = v13;
              if ( v13 < 0 )
                goto LABEL_81;
              ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
              goto LABEL_42;
            }
            ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
          }
        }
        v14 = 1;
        if ( !lstrcmpiW(v7, L"NoRemove") )
        {
          v14 = 0;
          v11 = ATL::CRegParser::NextToken(i, v7);
          if ( v11 < 0 )
            goto LABEL_79;
        }
        if ( !lstrcmpiW(v7, L"Val") )
        {
          v11 = ATL::CRegParser::NextToken(i, ValueName);
          if ( v11 < 0 )
            goto LABEL_79;
          v11 = ATL::CRegParser::NextToken(i, v7);
          if ( v11 < 0 )
            goto LABEL_79;
          if ( *v7 != 61 )
            goto LABEL_78;
          if ( !v5 )
          {
            if ( a5 || !v14 )
              goto LABEL_30;
            hKey = 0;
            v30 = 0;
            v31 = 0;
            v15 = ATL::CRegKey::Open((ATL::CRegKey *)&hKey, a3, 0, 0x20006u);
            if ( !v15 )
            {
              v15 = RegDeleteValueW(hKey, ValueName);
              if ( (v15 & 0xFFFFFFFD) == 0 )
              {
                ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_30:
                Token = ATL::CRegParser::SkipAssignment(i, v7);
                goto LABEL_31;
              }
            }
LABEL_80:
            v11 = ATL::AtlHresultFromWin32(v15);
LABEL_81:
            ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
            goto LABEL_79;
          }
          v30 = 0;
          v31 = 0;
          hKey = a3;
          v13 = ATL::CRegParser::AddValue(i, &hKey, ValueName, v7);
          hKey = 0;
          goto LABEL_14;
        }
        if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
          goto LABEL_78;
        if ( v5 )
          break;
        if ( a5 )
          v18 = 2;
        else
          v18 = ATL::CRegKey::Open((ATL::CRegKey *)v32, a3, v7, 0x20019u);
        v19 = 1;
        if ( !v18 )
          v19 = a5;
        v20 = wcsncpy_s(Destination, 0x104u, v7, 0xFFFFFFFFFFFFFFFFuLL);
        ATL::AtlCrtErrorCheck(v20);
        v11 = ATL::CRegParser::NextToken(i, v7);
        if ( v11 < 0 )
          goto LABEL_79;
        v21 = ATL::CRegParser::SkipAssignment(i, v7);
        v22 = 0;
        v11 = v21;
        if ( v21 < 0 )
          goto LABEL_79;
        if ( *v7 == 123 )
        {
          v23 = -1;
          do
            ++v23;
          while ( v7[v23] );
          if ( v23 == 1 )
          {
            v11 = ATL::CRegParser::RegisterSubkeys(i, v7, v32[0], 0, v19);
            if ( v11 < 0 && !v19 )
              goto LABEL_79;
            v11 = ATL::CRegParser::NextToken(i, v7);
            if ( v11 < 0 )
              goto LABEL_79;
          }
        }
        v5 = a4;
        if ( v18 != 2 )
        {
          if ( v18 )
          {
            if ( !a5 )
            {
              v11 = ATL::AtlHresultFromWin32(v18);
              goto LABEL_79;
            }
          }
          else if ( a5 && ATL::CRegParser::HasSubKeys(v22, v32[0]) )
          {
            if ( ATL::CRegParser::CanForceRemoveKey(v22, Destination) && v14 )
              ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v32, Destination);
          }
          else
          {
            HasSubKeys = ATL::CRegParser::HasSubKeys(v22, v32[0]);
            v25 = ATL::CRegKey::Close((ATL::CRegKey *)v32);
            if ( v25 )
            {
              ATL::CRegKey::Close((ATL::CRegKey *)v32);
              v27 = v25;
              return ATL::AtlHresultFromWin32(v27);
            }
            if ( v14 && !HasSubKeys )
            {
              v30 = 0;
              v31 = 0;
              hKey = a3;
              v15 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&hKey, Destination);
              hKey = 0;
              if ( v15 )
                goto LABEL_80;
              ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
            }
            v5 = a4;
          }
        }
      }
      if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v32, a3, v7, 0x2001Fu) )
      {
        if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v32, a3, v7, 0x20019u) )
        {
          dwDisposition = 0;
          phkResult = 0;
          v16 = RegCreateKeyExW(a3, v7, 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition);
          if ( v16 || (v16 = ATL::CRegKey::Close((ATL::CRegKey *)v32), v32[0] = phkResult, v16) )
          {
            ATL::CRegKey::Close((ATL::CRegKey *)v32);
            v27 = v16;
            return ATL::AtlHresultFromWin32(v27);
          }
        }
      }
      v11 = ATL::CRegParser::NextToken(i, v7);
      if ( v11 < 0 )
        goto LABEL_79;
      if ( *v7 == 61 )
      {
        v11 = ATL::CRegParser::AddValue(i, v32, 0, v7);
        if ( v11 < 0 )
          goto LABEL_79;
      }
LABEL_42:
      if ( *v7 == 123 )
      {
        v17 = -1;
        do
          ++v17;
        while ( v7[v17] );
        if ( v17 == 1 )
          break;
      }
    }
    v11 = ATL::CRegParser::RegisterSubkeys(i, v7, v32[0], v5, 0);
    if ( v11 < 0 )
      break;
    a2 = v7;
  }
LABEL_79:
  ATL::CRegKey::Close((ATL::CRegKey *)v32);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18002062c  push    rbp
0x18002062e  push    rbx
0x18002062f  push    rsi
0x180020630  push    rdi
0x180020631  push    r12
0x180020633  push    r13
0x180020635  push    r14
0x180020637  push    r15
0x180020639  lea     rbp, [rsp-21C8h]
0x180020641  mov     eax, 22C8h
0x180020646  call    _alloca_probe
0x18002064b  sub     rsp, rax
0x18002064e  mov     rax, cs:__security_cookie
0x180020655  xor     rax, rsp
0x180020658  mov     [rbp+2200h+var_50], rax
0x18002065f  xor     r14d, r14d
0x180020662  mov     [rsp+2300h+var_22B0], r9d
0x180020667  mov     [rsp+2300h+var_2290], r14
0x18002066c  mov     r15d, r9d
0x18002066f  mov     [rsp+2300h+var_2288], r14
0x180020674  mov     r13, r8
0x180020677  mov     [rbp+2200h+var_2280], r14
0x18002067b  mov     rdi, rdx
0x18002067e  mov     rsi, rcx
0x180020681  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180020686  jmp     loc_1800208AD
0x18002068b  cmp     word ptr [rdi], 7Dh ; '}'
0x18002068f  jz      loc_180020BC3
0x180020695  lea     rdx, aDelete; "Delete"
0x18002069c  mov     rcx, rdi; lpString1
0x18002069f  call    cs:__imp_lstrcmpiW
0x1800206a5  lea     rdx, aForceremove; "ForceRemove"
0x1800206ac  mov     rcx, rdi; lpString1
0x1800206af  mov     r14d, eax
0x1800206b2  call    cs:__imp_lstrcmpiW
0x1800206b8  test    eax, eax
0x1800206ba  jz      short loc_1800206C5
0x1800206bc  test    r14d, r14d
0x1800206bf  jnz     loc_180020786
0x1800206c5  mov     rdx, rdi; unsigned __int16 *
0x1800206c8  mov     rcx, rsi; this
0x1800206cb  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800206d0  mov     ebx, eax
0x1800206d2  test    eax, eax
0x1800206d4  js      loc_180020BC3
0x1800206da  test    r15d, r15d
0x1800206dd  jz      loc_180020786
0x1800206e3  mov     edx, 5Ch ; '\'; unsigned __int16
0x1800206e8  mov     [rsp+2300h+hKey], 0
0x1800206f1  mov     rcx, rdi; lpsz
0x1800206f4  mov     [rsp+2300h+var_22A0], 0
0x1800206fd  mov     [rsp+2300h+var_2298], 0
0x180020706  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18002070b  test    rax, rax
0x18002070e  jnz     loc_180020BB4
0x180020714  mov     rdx, rdi; unsigned __int16 *
0x180020717  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x18002071c  test    eax, eax
0x18002071e  jz      short loc_18002073B
0x180020720  mov     rdx, rdi; unsigned __int16 *
0x180020723  mov     [rsp+2300h+hKey], r13
0x180020728  lea     rcx, [rsp+2300h+hKey]; this
0x18002072d  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180020732  mov     [rsp+2300h+hKey], 0
0x18002073b  test    r14d, r14d
0x18002073e  jnz     short loc_18002077C
0x180020740  mov     rdx, rdi; unsigned __int16 *
0x180020743  mov     rcx, rsi; this
0x180020746  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002074b  xor     r14d, r14d
0x18002074e  mov     ebx, eax
0x180020750  test    eax, eax
0x180020752  js      loc_180020BFB
0x180020758  mov     rdx, rdi; unsigned __int16 *
0x18002075b  mov     rcx, rsi; this
0x18002075e  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180020763  lea     rcx, [rsp+2300h+hKey]; this
0x180020768  mov     ebx, eax
0x18002076a  test    eax, eax
0x18002076c  js      loc_180020C00
0x180020772  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180020777  jmp     loc_1800209AC
0x18002077c  lea     rcx, [rsp+2300h+hKey]; this
0x180020781  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180020786  lea     rdx, aNoremove; "NoRemove"
0x18002078d  mov     rcx, rdi; lpString1
0x180020790  mov     r12d, 1
0x180020796  call    cs:__imp_lstrcmpiW
0x18002079c  xor     r14d, r14d
0x18002079f  test    eax, eax
0x1800207a1  jnz     short loc_1800207BB
0x1800207a3  mov     rdx, rdi; unsigned __int16 *
0x1800207a6  mov     rcx, rsi; this
0x1800207a9  mov     r12d, r14d
0x1800207ac  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800207b1  mov     ebx, eax
0x1800207b3  test    eax, eax
0x1800207b5  js      loc_180020BC3
0x1800207bb  lea     rdx, aVal; "Val"
0x1800207c2  mov     rcx, rdi; lpString1
0x1800207c5  call    cs:__imp_lstrcmpiW
0x1800207cb  test    eax, eax
0x1800207cd  jnz     loc_1800208BC
0x1800207d3  lea     rdx, [rbp+2200h+ValueName]; unsigned __int16 *
0x1800207da  mov     rcx, rsi; this
0x1800207dd  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800207e2  mov     ebx, eax
0x1800207e4  test    eax, eax
0x1800207e6  js      loc_180020BC3
0x1800207ec  mov     rdx, rdi; unsigned __int16 *
0x1800207ef  mov     rcx, rsi; this
0x1800207f2  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800207f7  mov     ebx, eax
0x1800207f9  test    eax, eax
0x1800207fb  js      loc_180020BC3
0x180020801  cmp     word ptr [rdi], 3Dh ; '='
0x180020805  jnz     loc_180020BBE
0x18002080b  test    r15d, r15d
0x18002080e  jz      short loc_180020840
0x180020810  mov     r9, rdi; unsigned __int16 *
0x180020813  mov     [rsp+2300h+var_22A0], r14
0x180020818  lea     r8, [rbp+2200h+ValueName]; unsigned __int16 *
0x18002081f  mov     [rsp+2300h+var_2298], r14
0x180020824  lea     rdx, [rsp+2300h+hKey]; struct ATL::CRegKey *
0x180020829  mov     [rsp+2300h+hKey], r13
0x18002082e  mov     rcx, rsi; this
0x180020831  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180020836  mov     [rsp+2300h+hKey], r14
0x18002083b  jmp     loc_180020763
0x180020840  cmp     [rbp+2200h+arg_20], r14d
0x180020847  jnz     short loc_1800208A2
0x180020849  test    r12d, r12d
0x18002084c  jz      short loc_1800208A2
0x18002084e  mov     r9d, 20006h; unsigned int
0x180020854  mov     [rsp+2300h+hKey], r14
0x180020859  xor     r8d, r8d; lpSubKey
0x18002085c  mov     [rsp+2300h+var_22A0], r14
0x180020861  mov     rdx, r13; hKey
0x180020864  mov     [rsp+2300h+var_2298], r14
0x180020869  lea     rcx, [rsp+2300h+hKey]; this
0x18002086e  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180020873  test    eax, eax
0x180020875  jnz     loc_180020BF2
0x18002087b  mov     rcx, [rsp+2300h+hKey]; hKey
0x180020880  lea     rdx, [rbp+2200h+ValueName]; lpValueName
0x180020887  call    cs:__imp_RegDeleteValueW
0x18002088d  test    eax, 0FFFFFFFDh
0x180020892  jnz     loc_180020BF2
0x180020898  lea     rcx, [rsp+2300h+hKey]; this
0x18002089d  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800208a2  mov     rdx, rdi; unsigned __int16 *
0x1800208a5  mov     rcx, rsi; this
0x1800208a8  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1800208ad  mov     ebx, eax
0x1800208af  test    eax, eax
0x1800208b1  jns     loc_18002068B
0x1800208b7  jmp     loc_180020BC3
0x1800208bc  mov     edx, 5Ch ; '\'; unsigned __int16
0x1800208c1  mov     rcx, rdi; lpsz
0x1800208c4  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x1800208c9  test    rax, rax
0x1800208cc  jnz     loc_180020BBE
0x1800208d2  test    r15d, r15d
0x1800208d5  jz      loc_1800209FB
0x1800208db  mov     r9d, 2001Fh; unsigned int
0x1800208e1  lea     rcx, [rsp+2300h+var_2290]; this
0x1800208e6  mov     r8, rdi; lpSubKey
0x1800208e9  mov     rdx, r13; hKey
0x1800208ec  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800208f1  test    eax, eax
0x1800208f3  jz      short loc_180020974
0x1800208f5  mov     r9d, 20019h; unsigned int
0x1800208fb  lea     rcx, [rsp+2300h+var_2290]; this
0x180020900  mov     r8, rdi; lpSubKey
0x180020903  mov     rdx, r13; hKey
0x180020906  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18002090b  test    eax, eax
0x18002090d  jz      short loc_180020974
0x18002090f  lea     rax, [rbp+2200h+dwDisposition]
0x180020913  mov     [rbp+2200h+dwDisposition], r14d
0x180020917  mov     [rsp+2300h+lpdwDisposition], rax; lpdwDisposition
0x18002091c  xor     r9d, r9d; lpClass
0x18002091f  lea     rax, [rbp+2200h+var_2270]
0x180020923  mov     [rbp+2200h+var_2270], r14
0x180020927  mov     [rsp+2300h+phkResult], rax; phkResult
0x18002092c  xor     r8d, r8d; Reserved
0x18002092f  mov     [rsp+2300h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180020934  mov     rdx, rdi; lpSubKey
0x180020937  mov     [rsp+2300h+samDesired], 2001Fh; samDesired
0x18002093f  mov     rcx, r13; hKey
0x180020942  mov     [rsp+2300h+dwOptions], r14d; dwOptions
0x180020947  call    cs:__imp_RegCreateKeyExW
0x18002094d  mov     ebx, eax
0x18002094f  test    eax, eax
0x180020951  jnz     loc_180020C07
0x180020957  lea     rcx, [rsp+2300h+var_2290]; this
0x18002095c  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180020961  mov     ebx, eax
0x180020963  mov     rax, [rbp+2200h+var_2270]
0x180020967  mov     [rsp+2300h+var_2290], rax
0x18002096c  test    ebx, ebx
0x18002096e  jnz     loc_180020C07
0x180020974  mov     rdx, rdi; unsigned __int16 *
0x180020977  mov     rcx, rsi; this
0x18002097a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002097f  mov     ebx, eax
0x180020981  test    eax, eax
0x180020983  js      loc_180020BC3
0x180020989  cmp     word ptr [rdi], 3Dh ; '='
0x18002098d  jnz     short loc_1800209AC
0x18002098f  mov     r9, rdi; unsigned __int16 *
0x180020992  lea     rdx, [rsp+2300h+var_2290]; struct ATL::CRegKey *
0x180020997  xor     r8d, r8d; unsigned __int16 *
0x18002099a  mov     rcx, rsi; this
0x18002099d  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x1800209a2  mov     ebx, eax
0x1800209a4  test    eax, eax
0x1800209a6  js      loc_180020BC3
0x1800209ac  cmp     word ptr [rdi], 7Bh ; '{'
0x1800209b0  jnz     loc_18002068B
0x1800209b6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800209ba  inc     rax
0x1800209bd  cmp     [rdi+rax*2], r14w
0x1800209c2  jnz     short loc_1800209BA
0x1800209c4  cmp     rax, 1
0x1800209c8  jnz     loc_18002068B
0x1800209ce  mov     r8, [rsp+2300h+var_2290]; HKEY
0x1800209d3  mov     r9d, r15d; int
0x1800209d6  mov     rdx, rdi; unsigned __int16 *
0x1800209d9  mov     [rsp+2300h+dwOptions], r14d; int
0x1800209de  mov     rcx, rsi; this
0x1800209e1  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800209e6  mov     ebx, eax
0x1800209e8  test    eax, eax
0x1800209ea  js      loc_180020BC3
0x1800209f0  mov     rdx, rdi
0x1800209f3  mov     rcx, rsi
0x1800209f6  jmp     loc_180020681
0x1800209fb  cmp     [rbp+2200h+arg_20], r14d
0x180020a02  jnz     short loc_180020A1F
0x180020a04  mov     r9d, 20019h; unsigned int
0x180020a0a  lea     rcx, [rsp+2300h+var_2290]; this
0x180020a0f  mov     r8, rdi; lpSubKey
0x180020a12  mov     rdx, r13; hKey
0x180020a15  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180020a1a  mov     r14d, eax
0x180020a1d  jmp     short loc_180020A25
0x180020a1f  mov     r14d, 2
0x180020a25  test    r14d, r14d
0x180020a28  lea     rcx, [rbp+2200h+Destination]; Destination
0x180020a2c  mov     r15d, 1
0x180020a32  mov     r8, rdi; Source
0x180020a35  cmovz   r15d, [rbp+2200h+arg_20]
0x180020a3d  mov     edx, 104h; SizeInWords
0x180020a42  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180020a46  call    cs:__imp_wcsncpy_s
0x180020a4c  mov     ecx, eax; int
0x180020a4e  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180020a53  mov     rdx, rdi; unsigned __int16 *
0x180020a56  mov     rcx, rsi; this
0x180020a59  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180020a5e  mov     ebx, eax
0x180020a60  test    eax, eax
0x180020a62  js      loc_180020BC3
0x180020a68  mov     rdx, rdi; unsigned __int16 *
0x180020a6b  mov     rcx, rsi; this
0x180020a6e  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180020a73  xor     ecx, ecx
0x180020a75  mov     ebx, eax
0x180020a77  test    eax, eax
0x180020a79  js      loc_180020BC3
0x180020a7f  cmp     word ptr [rdi], 7Bh ; '{'
0x180020a83  jnz     short loc_180020AD4
0x180020a85  or      rax, 0FFFFFFFFFFFFFFFFh
0x180020a89  inc     rax
0x180020a8c  cmp     [rdi+rax*2], cx
0x180020a90  jnz     short loc_180020A89
0x180020a92  cmp     rax, 1
0x180020a96  jnz     short loc_180020AD4
0x180020a98  mov     r8, [rsp+2300h+var_2290]; HKEY
0x180020a9d  xor     r9d, r9d; int
0x180020aa0  mov     rdx, rdi; unsigned __int16 *
0x180020aa3  mov     [rsp+2300h+dwOptions], r15d; int
0x180020aa8  mov     rcx, rsi; this
0x180020aab  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180020ab0  mov     ebx, eax
0x180020ab2  test    eax, eax
0x180020ab4  jns     short loc_180020ABF
0x180020ab6  test    r15d, r15d
0x180020ab9  jz      loc_180020BC3
0x180020abf  mov     rdx, rdi; unsigned __int16 *
0x180020ac2  mov     rcx, rsi; this
0x180020ac5  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180020aca  mov     ebx, eax
0x180020acc  test    eax, eax
0x180020ace  js      loc_180020BC3
0x180020ad4  mov     r15d, [rsp+2300h+var_22B0]
0x180020ad9  cmp     r14d, 2
0x180020add  jz      loc_18002068B
0x180020ae3  test    r14d, r14d
  ... truncated ...
```
