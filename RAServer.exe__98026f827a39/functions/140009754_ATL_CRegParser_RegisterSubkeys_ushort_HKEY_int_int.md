# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x140009754`
- end: `0x140009d2d`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1497`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x140009430`
- `0x140009754`

## callees

- `0x1400046ac`
- `0x140004d30`
- `0x140004da0`
- `0x140004fa8`
- `0x140005134`
- `0x140005dc0`
- `0x140007094`
- `0x1400080e8`
- `0x1400083d0`
- `0x14000931c`
- `0x140009754`
- `0x14000a7e4`
- `0x14000a974`
- `0x140015aa0`
- `0x140015b60`

## import_xrefs

- `ADVAPI32!RegDeleteValueW` at `0x1400099a9`
- `ADVAPI32!RegDeleteValueW` at `0x1400099a9`
- `ADVAPI32!RegCreateKeyExW` at `0x140009a5b`
- `ADVAPI32!RegCreateKeyExW` at `0x140009a5b`
- `KERNEL32!lstrcmpiW` at `0x1400097cf`
- `KERNEL32!lstrcmpiW` at `0x1400097e2`
- `KERNEL32!lstrcmpiW` at `0x1400098b6`
- `KERNEL32!lstrcmpiW` at `0x1400098e5`
- `KERNEL32!lstrcmpiW` at `0x1400097cf`
- `KERNEL32!lstrcmpiW` at `0x1400097e2`
- `KERNEL32!lstrcmpiW` at `0x1400098b6`
- `KERNEL32!lstrcmpiW` at `0x1400098e5`
- `msvcrt!wcsncpy_s` at `0x140009b5a`
- `msvcrt!wcsncpy_s` at `0x140009b5a`

## string_xrefs

- `0x1400097d8`: `ForceRemove`
- `0x1400098ac`: `NoRemove`
- `0x1400097c5`: `Delete`

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
  ATL::CRegParser *v8; // rsi
  int Token; // eax
  int v10; // ebx
  int v11; // r14d
  ATL::CRegParser *v12; // rcx
  int v13; // eax
  int v14; // r12d
  unsigned int v15; // eax
  LSTATUS v16; // ecx
  __int64 v17; // rax
  int v18; // r14d
  int v19; // r15d
  errno_t v20; // eax
  ATL::CRegParser *v21; // rcx
  __int64 v22; // rax
  int HasSubKeys; // r14d
  LSTATUS v24; // eax
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v28; // [rsp+60h] [rbp-A0h]
  __int64 v29; // [rsp+68h] [rbp-98h]
  HKEY v30[3]; // [rsp+70h] [rbp-90h] BYREF
  DWORD dwDisposition; // [rsp+88h] [rbp-78h] BYREF
  HKEY phkResult; // [rsp+90h] [rbp-70h] BYREF
  wchar_t Destination[264]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR ValueName[4096]; // [rsp+2B0h] [rbp+1B0h] BYREF

  v5 = a4;
  v7 = a2;
  v8 = this;
  memset(v30, 0, sizeof(v30));
LABEL_2:
  Token = ATL::CRegParser::NextToken(this, a2);
  while ( 2 )
  {
    v10 = Token;
    if ( Token < 0 )
      goto LABEL_79;
    while ( 1 )
    {
      if ( *v7 == 125 )
        goto LABEL_79;
      v11 = lstrcmpiW(v7, L"Delete");
      if ( !lstrcmpiW(v7, L"ForceRemove") || !v11 )
      {
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_79;
        if ( v5 )
        {
          hKey = 0;
          v28 = 0;
          v29 = 0;
          if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
          {
            ATL::CRegKey::Close(&hKey);
LABEL_78:
            v10 = -2147352567;
            goto LABEL_79;
          }
          if ( (unsigned int)ATL::CRegParser::CanForceRemoveKey(v12, v7) )
          {
            hKey = a3;
            ATL::CRegKey::RecurseDeleteKey(&hKey, v7);
            hKey = 0;
          }
          if ( !v11 )
          {
            v10 = ATL::CRegParser::NextToken(v8, v7);
            if ( v10 < 0 )
              goto LABEL_81;
            v13 = ATL::CRegParser::SkipAssignment(v8, v7);
            v10 = v13;
            goto LABEL_15;
          }
          ATL::CRegKey::Close(&hKey);
        }
      }
      v14 = 1;
      if ( !lstrcmpiW(v7, L"NoRemove") )
      {
        v14 = 0;
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_79;
      }
      if ( !lstrcmpiW(v7, L"Val") )
        break;
      if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
        goto LABEL_78;
      if ( v5 )
      {
        if ( (unsigned int)ATL::CRegKey::Open(v30, a3, v7, 0x2001Fu) )
        {
          if ( (unsigned int)ATL::CRegKey::Open(v30, a3, v7, 0x20019u) )
          {
            dwDisposition = 0;
            phkResult = 0;
            v16 = RegCreateKeyExW(a3, v7, 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition);
            if ( v16 )
              goto LABEL_65;
            v16 = ATL::CRegKey::Close(v30);
            v30[0] = phkResult;
            if ( v16 )
              goto LABEL_65;
          }
        }
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_79;
        if ( *v7 == 61 )
        {
          v10 = ATL::CRegParser::AddValue(v8, v30, 0, v7);
          if ( v10 < 0 )
            goto LABEL_79;
        }
LABEL_41:
        if ( *v7 == 123 )
        {
          v17 = -1;
          do
            ++v17;
          while ( v7[v17] );
          if ( v17 == 1 )
          {
            v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v30[0], v5, 0);
            if ( v10 < 0 )
              goto LABEL_79;
            a2 = v7;
            this = v8;
            goto LABEL_2;
          }
        }
      }
      else
      {
        if ( a5 )
          v18 = 2;
        else
          v18 = ATL::CRegKey::Open(v30, a3, v7, 0x20019u);
        v19 = 1;
        if ( !v18 )
          v19 = a5;
        v20 = wcsncpy_s(Destination, 0x104u, v7, 0xFFFFFFFFFFFFFFFFuLL);
        ATL::AtlCrtErrorCheck(v20);
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_79;
        v10 = ATL::CRegParser::SkipAssignment(v8, v7);
        v21 = 0;
        if ( v10 < 0 )
          goto LABEL_79;
        if ( *v7 == 123 )
        {
          v22 = -1;
          do
            ++v22;
          while ( v7[v22] );
          if ( v22 == 1 )
          {
            v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v30[0], 0, v19);
            if ( v10 < 0 && !v19 )
              goto LABEL_79;
            v10 = ATL::CRegParser::NextToken(v8, v7);
            if ( v10 < 0 )
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
              v16 = v18;
LABEL_65:
              v10 = ATL::AtlHresultFromWin32(v16);
              goto LABEL_79;
            }
          }
          else if ( a5 && ATL::CRegParser::HasSubKeys(v21, v30[0]) )
          {
            if ( (unsigned int)ATL::CRegParser::CanForceRemoveKey(v21, Destination) && v14 )
              ATL::CRegKey::RecurseDeleteKey(v30, Destination);
          }
          else
          {
            HasSubKeys = ATL::CRegParser::HasSubKeys(v21, v30[0]);
            v24 = ATL::CRegKey::Close(v30);
            if ( v24 )
            {
              v16 = v24;
              goto LABEL_65;
            }
            if ( v14 && !HasSubKeys )
            {
              v28 = 0;
              v29 = 0;
              hKey = a3;
              v15 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&hKey, Destination);
              hKey = 0;
              if ( v15 )
                goto LABEL_80;
              ATL::CRegKey::Close(&hKey);
            }
          }
        }
      }
    }
    v10 = ATL::CRegParser::NextToken(v8, ValueName);
    if ( v10 < 0 )
      goto LABEL_79;
    v10 = ATL::CRegParser::NextToken(v8, v7);
    if ( v10 < 0 )
      goto LABEL_79;
    if ( *v7 != 61 )
      goto LABEL_78;
    if ( v5 )
    {
      v28 = 0;
      v29 = 0;
      hKey = a3;
      v13 = ATL::CRegParser::AddValue(v8, &hKey, ValueName, v7);
      v10 = v13;
      hKey = 0;
LABEL_15:
      if ( v13 < 0 )
        goto LABEL_81;
      ATL::CRegKey::Close(&hKey);
      goto LABEL_41;
    }
    if ( a5 || !v14 )
      goto LABEL_31;
    hKey = 0;
    v28 = 0;
    v29 = 0;
    v15 = ATL::CRegKey::Open(&hKey, a3, 0, 0x20006u);
    if ( !v15 )
    {
      v15 = RegDeleteValueW(hKey, ValueName);
      if ( (v15 & 0xFFFFFFFD) == 0 )
      {
        ATL::CRegKey::Close(&hKey);
LABEL_31:
        Token = ATL::CRegParser::SkipAssignment(v8, v7);
        continue;
      }
    }
    break;
  }
LABEL_80:
  v10 = ATL::AtlHresultFromWin32(v15);
LABEL_81:
  ATL::CRegKey::Close(&hKey);
LABEL_79:
  ATL::CRegKey::Close(v30);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140009754  push    rbp
0x140009756  push    rbx
0x140009757  push    rsi
0x140009758  push    rdi
0x140009759  push    r12
0x14000975b  push    r13
0x14000975d  push    r14
0x14000975f  push    r15
0x140009761  lea     rbp, [rsp-21C8h]
0x140009769  mov     eax, 22C8h
0x14000976e  call    _alloca_probe
0x140009773  sub     rsp, rax
0x140009776  mov     rax, cs:__security_cookie
0x14000977d  xor     rax, rsp
0x140009780  mov     [rbp+2200h+var_50], rax
0x140009787  mov     r15d, r9d
0x14000978a  mov     [rsp+2300h+var_22B0], r9d
0x14000978f  mov     r13, r8
0x140009792  mov     rdi, rdx
0x140009795  mov     rsi, rcx
0x140009798  xor     r14d, r14d
0x14000979b  mov     [rsp+2300h+var_2290], r14
0x1400097a0  mov     [rsp+2300h+var_2288], r14
0x1400097a5  mov     [rbp+2200h+var_2280], r14
0x1400097a9  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1400097ae  test    eax, eax
0x1400097b0  mov     ebx, eax
0x1400097b2  js      loc_140009CE1
0x1400097b8  xor     r12d, r12d
0x1400097bb  cmp     word ptr [rdi], 7Dh ; '}'
0x1400097bf  jz      loc_140009CE1
0x1400097c5  lea     rdx, String2; "Delete"
0x1400097cc  mov     rcx, rdi; lpString1
0x1400097cf  call    cs:__imp_lstrcmpiW
0x1400097d5  mov     r14d, eax
0x1400097d8  lea     rdx, aForceremove; "ForceRemove"
0x1400097df  mov     rcx, rdi; lpString1
0x1400097e2  call    cs:__imp_lstrcmpiW
0x1400097e8  test    eax, eax
0x1400097ea  jz      short loc_1400097F5
0x1400097ec  test    r14d, r14d
0x1400097ef  jnz     loc_1400098A6
0x1400097f5  mov     rdx, rdi; unsigned __int16 *
0x1400097f8  mov     rcx, rsi; this
0x1400097fb  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140009800  mov     ebx, eax
0x140009802  test    eax, eax
0x140009804  js      loc_140009CE1
0x14000980a  test    r15d, r15d
0x14000980d  jz      loc_1400098A6
0x140009813  mov     [rsp+2300h+hKey], r12
0x140009818  mov     [rsp+2300h+var_22A0], r12
0x14000981d  mov     [rsp+2300h+var_2298], r12
0x140009822  mov     edx, 5Ch ; '\'; unsigned __int16
0x140009827  mov     rcx, rdi; lpsz
0x14000982a  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x14000982f  test    rax, rax
0x140009832  jnz     loc_140009CD2
0x140009838  mov     rdx, rdi; unsigned __int16 *
0x14000983b  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x140009840  test    eax, eax
0x140009842  jz      short loc_14000985B
0x140009844  mov     [rsp+2300h+hKey], r13
0x140009849  mov     rdx, rdi; unsigned __int16 *
0x14000984c  lea     rcx, [rsp+2300h+hKey]; this
0x140009851  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x140009856  mov     [rsp+2300h+hKey], r12
0x14000985b  test    r14d, r14d
0x14000985e  jnz     short loc_14000989C
0x140009860  mov     rdx, rdi; unsigned __int16 *
0x140009863  mov     rcx, rsi; this
0x140009866  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x14000986b  mov     ebx, eax
0x14000986d  xor     r14d, r14d
0x140009870  test    eax, eax
0x140009872  js      loc_140009D19
0x140009878  mov     rdx, rdi; unsigned __int16 *
0x14000987b  mov     rcx, rsi; this
0x14000987e  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x140009883  mov     ebx, eax
0x140009885  test    eax, eax
0x140009887  lea     rcx, [rsp+2300h+hKey]; this
0x14000988c  js      loc_140009D1E
0x140009892  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x140009897  jmp     loc_140009AC0
0x14000989c  lea     rcx, [rsp+2300h+hKey]; this
0x1400098a1  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1400098a6  mov     r12d, 1
0x1400098ac  lea     rdx, aNoremove; "NoRemove"
0x1400098b3  mov     rcx, rdi; lpString1
0x1400098b6  call    cs:__imp_lstrcmpiW
0x1400098bc  xor     r14d, r14d
0x1400098bf  test    eax, eax
0x1400098c1  jnz     short loc_1400098DB
0x1400098c3  mov     r12d, r14d
0x1400098c6  mov     rdx, rdi; unsigned __int16 *
0x1400098c9  mov     rcx, rsi; this
0x1400098cc  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1400098d1  mov     ebx, eax
0x1400098d3  test    eax, eax
0x1400098d5  js      loc_140009CE1
0x1400098db  lea     rdx, aVal; "Val"
0x1400098e2  mov     rcx, rdi; lpString1
0x1400098e5  call    cs:__imp_lstrcmpiW
0x1400098eb  test    eax, eax
0x1400098ed  jnz     loc_1400099D4
0x1400098f3  lea     rdx, [rbp+2200h+ValueName]; unsigned __int16 *
0x1400098fa  mov     rcx, rsi; this
0x1400098fd  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140009902  mov     ebx, eax
0x140009904  test    eax, eax
0x140009906  js      loc_140009CE1
0x14000990c  mov     rdx, rdi; unsigned __int16 *
0x14000990f  mov     rcx, rsi; this
0x140009912  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140009917  mov     ebx, eax
0x140009919  test    eax, eax
0x14000991b  js      loc_140009CE1
0x140009921  cmp     word ptr [rdi], 3Dh ; '='
0x140009925  jnz     loc_140009CDC
0x14000992b  test    r15d, r15d
0x14000992e  jz      short loc_140009962
0x140009930  mov     [rsp+2300h+var_22A0], r14
0x140009935  mov     [rsp+2300h+var_2298], r14
0x14000993a  mov     [rsp+2300h+hKey], r13
0x14000993f  mov     r9, rdi; unsigned __int16 *
0x140009942  lea     r8, [rbp+2200h+ValueName]; unsigned __int16 *
0x140009949  lea     rdx, [rsp+2300h+hKey]; struct ATL::CRegKey *
0x14000994e  mov     rcx, rsi; this
0x140009951  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x140009956  mov     ebx, eax
0x140009958  mov     [rsp+2300h+hKey], r14
0x14000995d  jmp     loc_140009885
0x140009962  cmp     [rbp+2200h+arg_20], r14d
0x140009969  jnz     short loc_1400099C4
0x14000996b  test    r12d, r12d
0x14000996e  jz      short loc_1400099C4
0x140009970  mov     [rsp+2300h+hKey], r14
0x140009975  mov     [rsp+2300h+var_22A0], r14
0x14000997a  mov     [rsp+2300h+var_2298], r14
0x14000997f  mov     r9d, 20006h; unsigned int
0x140009985  xor     r8d, r8d; lpSubKey
0x140009988  mov     rdx, r13; hKey
0x14000998b  lea     rcx, [rsp+2300h+hKey]; this
0x140009990  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x140009995  test    eax, eax
0x140009997  jnz     loc_140009D10
0x14000999d  lea     rdx, [rbp+2200h+ValueName]; lpValueName
0x1400099a4  mov     rcx, [rsp+2300h+hKey]; hKey
0x1400099a9  call    cs:__imp_RegDeleteValueW
0x1400099af  test    eax, 0FFFFFFFDh
0x1400099b4  jnz     loc_140009D10
0x1400099ba  lea     rcx, [rsp+2300h+hKey]; this
0x1400099bf  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1400099c4  mov     rdx, rdi; unsigned __int16 *
0x1400099c7  mov     rcx, rsi; this
0x1400099ca  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1400099cf  jmp     loc_1400097AE
0x1400099d4  mov     edx, 5Ch ; '\'; unsigned __int16
0x1400099d9  mov     rcx, rdi; lpsz
0x1400099dc  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x1400099e1  test    rax, rax
0x1400099e4  jnz     loc_140009CDC
0x1400099ea  test    r15d, r15d
0x1400099ed  jz      loc_140009B0F
0x1400099f3  mov     ebx, 2001Fh
0x1400099f8  mov     r9d, ebx; unsigned int
0x1400099fb  mov     r8, rdi; lpSubKey
0x1400099fe  mov     rdx, r13; hKey
0x140009a01  lea     rcx, [rsp+2300h+var_2290]; this
0x140009a06  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x140009a0b  test    eax, eax
0x140009a0d  jz      short loc_140009A88
0x140009a0f  lea     r9d, [rbx-6]; unsigned int
0x140009a13  mov     r8, rdi; lpSubKey
0x140009a16  mov     rdx, r13; hKey
0x140009a19  lea     rcx, [rsp+2300h+var_2290]; this
0x140009a1e  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x140009a23  test    eax, eax
0x140009a25  jz      short loc_140009A88
0x140009a27  mov     [rbp+2200h+dwDisposition], r14d
0x140009a2b  mov     [rbp+2200h+var_2270], r14
0x140009a2f  lea     rax, [rbp+2200h+dwDisposition]
0x140009a33  mov     [rsp+2300h+lpdwDisposition], rax; lpdwDisposition
0x140009a38  lea     rax, [rbp+2200h+var_2270]
0x140009a3c  mov     [rsp+2300h+phkResult], rax; phkResult
0x140009a41  mov     [rsp+2300h+lpSecurityAttributes], r14; lpSecurityAttributes
0x140009a46  mov     [rsp+2300h+samDesired], ebx; samDesired
0x140009a4a  mov     [rsp+2300h+dwOptions], r14d; dwOptions
0x140009a4f  xor     r9d, r9d; lpClass
0x140009a52  xor     r8d, r8d; Reserved
0x140009a55  mov     rdx, rdi; lpSubKey
0x140009a58  mov     rcx, r13; hKey
0x140009a5b  call    cs:__imp_RegCreateKeyExW
0x140009a61  mov     ecx, eax
0x140009a63  test    eax, eax
0x140009a65  jnz     loc_140009C0F
0x140009a6b  lea     rcx, [rsp+2300h+var_2290]; this
0x140009a70  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x140009a75  mov     ecx, eax
0x140009a77  mov     rax, [rbp+2200h+var_2270]
0x140009a7b  mov     [rsp+2300h+var_2290], rax
0x140009a80  test    ecx, ecx
0x140009a82  jnz     loc_140009C0F
0x140009a88  mov     rdx, rdi; unsigned __int16 *
0x140009a8b  mov     rcx, rsi; this
0x140009a8e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140009a93  mov     ebx, eax
0x140009a95  test    eax, eax
0x140009a97  js      loc_140009CE1
0x140009a9d  cmp     word ptr [rdi], 3Dh ; '='
0x140009aa1  jnz     short loc_140009AC0
0x140009aa3  mov     r9, rdi; unsigned __int16 *
0x140009aa6  xor     r8d, r8d; unsigned __int16 *
0x140009aa9  lea     rdx, [rsp+2300h+var_2290]; struct ATL::CRegKey *
0x140009aae  mov     rcx, rsi; this
0x140009ab1  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x140009ab6  mov     ebx, eax
0x140009ab8  test    eax, eax
0x140009aba  js      loc_140009CE1
0x140009ac0  cmp     word ptr [rdi], 7Bh ; '{'
0x140009ac4  jnz     loc_1400097B8
0x140009aca  or      rax, 0FFFFFFFFFFFFFFFFh
0x140009ace  inc     rax
0x140009ad1  cmp     [rdi+rax*2], r14w
0x140009ad6  jnz     short loc_140009ACE
0x140009ad8  cmp     rax, 1
0x140009adc  jnz     loc_1400097B8
0x140009ae2  mov     [rsp+2300h+dwOptions], r14d; int
0x140009ae7  mov     r9d, r15d; int
0x140009aea  mov     r8, [rsp+2300h+var_2290]; HKEY
0x140009aef  mov     rdx, rdi; unsigned __int16 *
0x140009af2  mov     rcx, rsi; this
0x140009af5  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x140009afa  mov     ebx, eax
0x140009afc  test    eax, eax
0x140009afe  js      loc_140009CE1
0x140009b04  mov     rdx, rdi
0x140009b07  mov     rcx, rsi
0x140009b0a  jmp     loc_1400097A9
0x140009b0f  cmp     [rbp+2200h+arg_20], r14d
0x140009b16  jnz     short loc_140009B33
0x140009b18  mov     r9d, 20019h; unsigned int
0x140009b1e  mov     r8, rdi; lpSubKey
0x140009b21  mov     rdx, r13; hKey
0x140009b24  lea     rcx, [rsp+2300h+var_2290]; this
0x140009b29  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x140009b2e  mov     r14d, eax
0x140009b31  jmp     short loc_140009B39
0x140009b33  mov     r14d, 2
0x140009b39  mov     r15d, 1
0x140009b3f  test    r14d, r14d
0x140009b42  cmovz   r15d, [rbp+2200h+arg_20]
0x140009b4a  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140009b4e  mov     r8, rdi; Source
0x140009b51  mov     edx, 104h; SizeInWords
0x140009b56  lea     rcx, [rbp+2200h+Destination]; Destination
0x140009b5a  call    cs:__imp_wcsncpy_s
0x140009b60  mov     ecx, eax; int
0x140009b62  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x140009b67  mov     rdx, rdi; unsigned __int16 *
0x140009b6a  mov     rcx, rsi; this
0x140009b6d  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140009b72  mov     ebx, eax
0x140009b74  test    eax, eax
0x140009b76  js      loc_140009CE1
0x140009b7c  mov     rdx, rdi; unsigned __int16 *
0x140009b7f  mov     rcx, rsi; this
0x140009b82  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x140009b87  mov     ebx, eax
0x140009b89  xor     ecx, ecx
0x140009b8b  test    eax, eax
0x140009b8d  js      loc_140009CE1
0x140009b93  cmp     word ptr [rdi], 7Bh ; '{'
0x140009b97  jnz     short loc_140009BE8
0x140009b99  or      rax, 0FFFFFFFFFFFFFFFFh
0x140009b9d  inc     rax
0x140009ba0  cmp     [rdi+rax*2], cx
0x140009ba4  jnz     short loc_140009B9D
0x140009ba6  cmp     rax, 1
0x140009baa  jnz     short loc_140009BE8
0x140009bac  mov     [rsp+2300h+dwOptions], r15d; int
0x140009bb1  xor     r9d, r9d; int
0x140009bb4  mov     r8, [rsp+2300h+var_2290]; HKEY
0x140009bb9  mov     rdx, rdi; unsigned __int16 *
0x140009bbc  mov     rcx, rsi; this
0x140009bbf  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x140009bc4  mov     ebx, eax
0x140009bc6  test    eax, eax
0x140009bc8  jns     short loc_140009BD3
0x140009bca  test    r15d, r15d
0x140009bcd  jz      loc_140009CE1
0x140009bd3  mov     rdx, rdi; unsigned __int16 *
0x140009bd6  mov     rcx, rsi; this
0x140009bd9  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140009bde  mov     ebx, eax
0x140009be0  test    eax, eax
0x140009be2  js      loc_140009CE1
0x140009be8  cmp     r14d, 2
0x140009bec  mov     r15d, [rsp+2300h+var_22B0]
  ... truncated ...
```
