# CGenerate::GenerateFile_h(ushort const *,int,int)

- ea: `0x14000b9c8`
- end: `0x14000c108`
- name: `?GenerateFile_h@CGenerate@@QEAAJPEBGHH@Z`
- size: `1856`
- prototype: `__int64 __fastcall(CGenerate *this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x140007c10`

## callees

- `0x140006284`
- `0x1400075f8`
- `0x140008b28`
- `0x14000a460`
- `0x14000a5f0`
- `0x14000a614`
- `0x14000a67c`
- `0x14000a828`
- `0x14000a96c`
- `0x14000ac48`
- `0x14000ad50`
- `0x14000b9c8`
- `0x14000c110`
- `0x14000f4ac`
- `0x14000f528`
- `0x14000f590`

## import_xrefs

- `msvcrt!wcslen` at `0x14000ba1e`
- `msvcrt!wcslen` at `0x14000c014`
- `msvcrt!wcslen` at `0x14000ba1e`
- `msvcrt!wcslen` at `0x14000c014`
- `wbemcomn!Throttle` at `0x14000bf5e`
- `wbemcomn!Throttle` at `0x14000bf5e`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x14000bdb3`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x14000be01`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x14000befb`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x14000c0b1`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x14000c0e9`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x14000bdb3`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x14000be01`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x14000befb`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x14000c0b1`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x14000c0e9`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x14000ba38`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x14000c034`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x14000ba38`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x14000c034`
- `OLEAUT32!__imp_SysFreeString` at `0x14000bb6c`
- `OLEAUT32!__imp_SysFreeString` at `0x14000bb6c`

## string_xrefs

- `0x14000bac9`: `Copyright (C) 2000 Microsoft Corporation`

## pseudocode

```c
__int64 __fastcall CGenerate::GenerateFile_h(CGenerate *this, const unsigned __int16 *a2, int a3)
{
  CGenerate *v3; // r15
  void **v4; // r13
  unsigned __int64 v5; // rbx
  unsigned __int64 v6; // rax
  unsigned __int16 *v7; // rax
  __int64 v8; // rcx
  unsigned __int16 *v9; // r14
  int appended; // edi
  unsigned int v11; // r12d
  __int64 v12; // rax
  __int64 v13; // rax
  const unsigned __int16 *NameInd; // rax
  unsigned __int16 *v15; // r12
  const unsigned __int16 *Index; // rax
  unsigned __int16 *v17; // r12
  unsigned int i; // r13d
  __int64 v19; // rax
  const unsigned __int16 *v20; // rax
  const unsigned __int16 *v21; // rax
  unsigned __int16 *v22; // r12
  __int64 j; // rax
  __int64 v24; // rbx
  unsigned __int64 v25; // r12
  unsigned __int16 *v26; // rax
  unsigned __int16 *v27; // rbx
  int v29; // [rsp+30h] [rbp-68h]
  unsigned __int16 *v30; // [rsp+30h] [rbp-68h]
  unsigned __int16 *v31; // [rsp+38h] [rbp-60h]
  unsigned __int16 *v32; // [rsp+38h] [rbp-60h]
  __int64 v33; // [rsp+40h] [rbp-58h]
  void **v34; // [rsp+48h] [rbp-50h] BYREF
  BSTR bstrString; // [rsp+50h] [rbp-48h]
  void **v37; // [rsp+A8h] [rbp+10h]
  unsigned int v39; // [rsp+B8h] [rbp+20h]

  v3 = this;
  if ( aWmiaprpl[0] && (v4 = (void **)((char *)this + 80), v37 = (void **)((char *)this + 80), *((_DWORD *)this + 20)) )
  {
    v5 = (unsigned int)wcslen(L"WmiApRpl") + 8;
    v6 = 2 * v5;
    if ( !is_mul_ok(v5, 2u) )
      v6 = -1;
    try
    {
      v7 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(v6);
      v9 = v7;
      v31 = v7;
      if ( v7 )
      {
        appended = StringCchCopyW(v7, v5, L"WmiApRpl");
        if ( appended >= 0 )
        {
          appended = StringCchCatW(v9, v5, L"_new.h");
          if ( appended >= 0 )
          {
            appended = CGenerate::FileCreate(v3, v9);
            if ( appended >= 0 )
            {
              v34 = &CGenerateComment::`vftable';
              bstrString = 0;
              CGenerateComment::AddHeader((CGenerateComment *)&v34);
              CGenerateComment::AddLine((CGenerateComment *)&v34, 0);
              CGenerateComment::AddLine((CGenerateComment *)&v34, L"Copyright (C) 2000 Microsoft Corporation");
              CGenerateComment::AddLine((CGenerateComment *)&v34, 0);
              CGenerateComment::AddLine((CGenerateComment *)&v34, L"Module Name:");
              CGenerateComment::AddLine((CGenerateComment *)&v34, L"WmiApRpl");
              CGenerateComment::AddLine((CGenerateComment *)&v34, 0);
              CGenerateComment::AddLine((CGenerateComment *)&v34, L"Abstract:");
              CGenerateComment::AddLine((CGenerateComment *)&v34, 0);
              CGenerateComment::AddLine((CGenerateComment *)&v34, L"Include file for object and counters definitions.");
              CGenerateComment::AddLine((CGenerateComment *)&v34, 0);
              CGenerateComment::AddFooter((CGenerateComment *)&v34);
              appended = CGenerate::WriteToFile((HANDLE *)v3, bstrString);
              SysFreeString(bstrString);
            }
          }
        }
      }
      else
      {
        appended = -2147024882;
      }
    }
    catch ( ... )
    {
      v3 = this;
      appended = -2147467259;
      v9 = v31;
      goto LABEL_83;
    }
    if ( appended < 0 )
      goto LABEL_83;
    appended = CGenerate::AppendString(v3, L"\r\n", 0);
    if ( appended < 0 )
      goto LABEL_83;
    appended = CGenerate::AppendString(v3, L"#define\t", 0);
    if ( appended < 0 )
      goto LABEL_83;
    appended = CGenerate::AppendString(v3, L"WMI_Objects", 0);
    if ( appended < 0 )
      goto LABEL_83;
    appended = CGenerate::AppendString(v3, L"\t0", 0);
    if ( appended < 0 )
      goto LABEL_83;
    appended = CGenerate::AppendString(v3, L"\r\n", 0);
    if ( appended < 0 )
      goto LABEL_83;
    appended = CGenerate::AppendString(v3, L"#define\t", 0);
    if ( appended < 0 )
      goto LABEL_83;
    appended = CGenerate::AppendString(v3, L"HiPerf_Classes", 0);
    if ( appended < 0 )
      goto LABEL_83;
    appended = CGenerate::AppendString(v3, L"\t2", 0);
    if ( appended < 0 )
      goto LABEL_83;
    appended = CGenerate::AppendString(v3, L"\r\n", 0);
    if ( appended < 0 )
      goto LABEL_83;
    appended = CGenerate::AppendString(v3, L"#define\t", 0);
    if ( appended < 0 )
      goto LABEL_83;
    appended = CGenerate::AppendString(v3, L"HiPerf_Validity", 0);
    if ( appended < 0 )
      goto LABEL_83;
    appended = CGenerate::AppendString(v3, L"\t4", 0);
    if ( appended < 0 )
      goto LABEL_83;
    appended = CGenerate::AppendString(v3, L"\r\n", 0);
    if ( appended < 0 )
      goto LABEL_83;
    v34 = v4;
    dword_140024FBC = 3;
    v11 = 0;
    v39 = 0;
    v12 = 0;
    v32 = v9;
    while ( 1 )
    {
      v29 = v12;
      if ( (unsigned int)v12 >= *(_DWORD *)v4 )
        break;
      if ( appended < 0 )
        goto LABEL_83;
      v13 = 5 * v12;
      v33 = v13;
      if ( *((_QWORD *)v3 + v13 + 4) )
      {
        try
        {
          v24 = **((_QWORD **)v3 + v13 + 3);
          while ( 1 )
          {
            if ( v24 == *((_QWORD *)v3 + v13 + 3) || appended < 0 )
              goto LABEL_95;
            appended = CGenerate::AppendString(v3, L"\r\n", 0);
            if ( appended < 0 )
              goto LABEL_58;
            appended = CGenerate::AppendString(v3, L"#define\t", 0);
            if ( appended < 0 )
              goto LABEL_58;
            NameInd = CGenerate::GenerateNameInd(
                        (CGenerate *)v8,
                        *(const unsigned __int16 **)(*(_QWORD *)(v24 + 40) + 8LL),
                        v11);
            v15 = (unsigned __int16 *)NameInd;
            if ( !NameInd )
              goto LABEL_56;
            appended = CGenerate::AppendString(v3, NameInd, 0);
            CWin32DefaultArena::WbemMemFree(v15);
            if ( appended < 0 )
              goto LABEL_57;
            appended = CGenerate::AppendString(v3, L"\t", 0);
            if ( appended < 0 )
              goto LABEL_57;
            Index = CGenerate::GenerateIndex((CGenerate *)v8);
            v17 = (unsigned __int16 *)Index;
            if ( !Index )
            {
LABEL_56:
              appended = -2147024882;
              goto LABEL_57;
            }
            appended = CGenerate::AppendString(v3, Index, 0);
            CWin32DefaultArena::WbemMemFree(v17);
            if ( appended < 0 )
              goto LABEL_57;
            appended = CGenerate::AppendString(v3, L"\r\n", 0);
            if ( appended < 0 )
              goto LABEL_57;
            for ( i = 0; ; ++i )
            {
              v19 = *(_QWORD *)(v24 + 40);
              if ( i >= *(_DWORD *)(v19 + 56) )
                break;
              if ( appended < 0 )
                goto LABEL_57;
              v8 = *(_QWORD *)(*(_QWORD *)(v19 + 48) + 8LL * i);
              if ( *(_QWORD *)(v8 + 32) )
              {
                appended = CGenerate::AppendString(v3, L"\r\n", 0);
                if ( appended >= 0 )
                {
                  appended = CGenerate::AppendString(v3, L"#define\t", 0);
                  if ( appended >= 0 )
                  {
                    v20 = CGenerate::GenerateNameInd(
                            *(CGenerate **)(*(_QWORD *)(v24 + 40) + 48LL),
                            *(const unsigned __int16 **)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v24 + 40) + 48LL) + 8LL * i)
                                                       + 8LL),
                            v39);
                    if ( !v20 )
                      goto LABEL_52;
                    appended = CGenerate::AppendString(v3, v20, 0);
                    if ( appended >= 0 )
                    {
                      appended = CGenerate::AppendString(v3, L"\t", 0);
                      if ( appended >= 0 )
                      {
                        v21 = CGenerate::GenerateIndex((CGenerate *)v8);
                        v22 = (unsigned __int16 *)v21;
                        if ( v21 )
                        {
                          appended = CGenerate::AppendString(v3, v21, 0);
                          CWin32DefaultArena::WbemMemFree(v22);
                          continue;
                        }
LABEL_52:
                        appended = -2147024882;
                        continue;
                      }
                    }
                  }
                }
              }
            }
            if ( appended >= 0 )
              appended = CGenerate::AppendString(v3, L"\r\n", 0);
LABEL_57:
            v11 = v39;
LABEL_58:
            if ( a3 && appended >= 0 )
              Throttle(3u, 0x3E8u, 0x64u, 0xAu, 0xBB8u);
            if ( !*(_BYTE *)(v24 + 25) )
            {
              v8 = *(_QWORD *)(v24 + 16);
              if ( *(_BYTE *)(v8 + 25) )
              {
                for ( j = *(_QWORD *)(v24 + 8); !*(_BYTE *)(j + 25) && v24 == *(_QWORD *)(j + 16); j = *(_QWORD *)(j + 8) )
                  v24 = j;
              }
              else
              {
                j = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned short * const,CObject *>>>::_Min();
              }
              v24 = j;
            }
            v39 = ++v11;
            v13 = v33;
          }
        }
        catch ( ... )
        {
          v3 = this;
          appended = -2147418113;
          v9 = v32;
          v4 = v34;
          v37 = v34;
          v11 = v39;
          goto LABEL_71;
        }
LABEL_95:
        v4 = v37;
      }
LABEL_71:
      v12 = (unsigned int)(v29 + 1);
    }
    if ( appended < 0 )
      goto LABEL_83;
    appended = CGenerate::ContentWrite(v3, 0);
    if ( appended < 0 )
      goto LABEL_83;
    try
    {
      v25 = (unsigned int)wcslen(L"WmiApRpl") + 4;
      v26 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v25, 2u));
      v27 = v26;
      v30 = v26;
      if ( v26 )
      {
        appended = StringCchCopyW(v26, v25, L"WmiApRpl");
        if ( appended >= 0 )
        {
          appended = StringCchCatW(v27, v25, L".h");
          if ( appended >= 0 )
            appended = CGenerate::FileMove(v3, v9, v27);
        }
      }
      else
      {
        appended = -2147024882;
      }
    }
    catch ( ... )
    {
      v3 = this;
      appended = -2147467259;
      v9 = v32;
      v27 = v30;
    }
    if ( v27 )
      CWin32DefaultArena::WbemMemFree(v27);
    if ( appended < 0 )
    {
LABEL_83:
      CGenerate::ContentDelete((CGenerate *)v8);
      CGenerate::FileDelete(v3, v9);
    }
    if ( v9 )
      CWin32DefaultArena::WbemMemFree(v9);
  }
  else
  {
    return (unsigned int)-2147418113;
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x14000b9c8  mov     rax, rsp
0x14000b9cb  mov     [rax+20h], r9d
0x14000b9cf  mov     [rax+18h], r8d
0x14000b9d3  mov     [rax+10h], rdx
0x14000b9d7  mov     [rax+8], rcx
0x14000b9db  push    rbx
0x14000b9dc  push    rsi
0x14000b9dd  push    rdi
0x14000b9de  push    r12
0x14000b9e0  push    r13
0x14000b9e2  push    r14
0x14000b9e4  push    r15
0x14000b9e6  sub     rsp, 60h
0x14000b9ea  mov     r15, rcx
0x14000b9ed  xor     esi, esi
0x14000b9ef  cmp     word ptr cs:aWmiaprpl, si; "WmiApRpl"
0x14000b9f6  jz      loc_14000C0F1
0x14000b9fc  lea     r13, [rcx+50h]
0x14000ba00  mov     [rsp+98h+arg_8], r13
0x14000ba08  cmp     [r13+0], esi
0x14000ba0c  jz      loc_14000C0F1
0x14000ba12  mov     [rsp+98h+var_60], rsi
0x14000ba17  lea     rcx, aWmiaprpl; "WmiApRpl"
0x14000ba1e  call    cs:__imp_wcslen
0x14000ba24  lea     ebx, [rax+8]
0x14000ba27  lea     eax, [rsi+2]
0x14000ba2a  mul     rbx
0x14000ba2d  lea     rcx, [rsi-1]
0x14000ba31  cmovb   rax, rcx
0x14000ba35  mov     rcx, rax
0x14000ba38  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x14000ba3e  mov     r14, rax
0x14000ba41  mov     [rsp+98h+var_60], rax
0x14000ba46  test    rax, rax
0x14000ba49  jnz     short loc_14000BA55
0x14000ba4b  mov     edi, 8007000Eh
0x14000ba50  jmp     loc_14000BB73
0x14000ba55  lea     r8, aWmiaprpl; "WmiApRpl"
0x14000ba5c  mov     rdx, rbx; unsigned __int64
0x14000ba5f  mov     rcx, r14; unsigned __int16 *
0x14000ba62  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14000ba67  mov     edi, eax
0x14000ba69  test    eax, eax
0x14000ba6b  js      loc_14000BB73
0x14000ba71  lea     r8, aNewH; "_new.h"
0x14000ba78  mov     rdx, rbx; unsigned __int64
0x14000ba7b  mov     rcx, r14; unsigned __int16 *
0x14000ba7e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000ba83  mov     edi, eax
0x14000ba85  test    eax, eax
0x14000ba87  js      loc_14000BB73
0x14000ba8d  mov     rdx, r14; unsigned __int16 *
0x14000ba90  mov     rcx, r15; this
0x14000ba93  call    ?FileCreate@CGenerate@@AEAAJPEBG@Z; CGenerate::FileCreate(ushort const *)
0x14000ba98  mov     edi, eax
0x14000ba9a  test    eax, eax
0x14000ba9c  js      loc_14000BB73
0x14000baa2  lea     rax, ??_7CGenerateComment@@6B@; const CGenerateComment::`vftable'
0x14000baa9  mov     [rsp+98h+var_50], rax
0x14000baae  mov     [rsp+98h+bstrString], rsi
0x14000bab3  lea     rcx, [rsp+98h+var_50]; this
0x14000bab8  call    ?AddHeader@CGenerateComment@@QEAAJXZ; CGenerateComment::AddHeader(void)
0x14000babd  xor     edx, edx; unsigned __int16 *
0x14000babf  lea     rcx, [rsp+98h+var_50]; this
0x14000bac4  call    ?AddLine@CGenerateComment@@QEAAJPEBG@Z; CGenerateComment::AddLine(ushort const *)
0x14000bac9  lea     rdx, aCopyrightC2000; "Copyright (C) 2000 Microsoft Corporatio"...
0x14000bad0  lea     rcx, [rsp+98h+var_50]; this
0x14000bad5  call    ?AddLine@CGenerateComment@@QEAAJPEBG@Z; CGenerateComment::AddLine(ushort const *)
0x14000bada  xor     edx, edx; unsigned __int16 *
0x14000badc  lea     rcx, [rsp+98h+var_50]; this
0x14000bae1  call    ?AddLine@CGenerateComment@@QEAAJPEBG@Z; CGenerateComment::AddLine(ushort const *)
0x14000bae6  lea     rdx, aModuleName; "Module Name:"
0x14000baed  lea     rcx, [rsp+98h+var_50]; this
0x14000baf2  call    ?AddLine@CGenerateComment@@QEAAJPEBG@Z; CGenerateComment::AddLine(ushort const *)
0x14000baf7  lea     rdx, aWmiaprpl; "WmiApRpl"
0x14000bafe  lea     rcx, [rsp+98h+var_50]; this
0x14000bb03  call    ?AddLine@CGenerateComment@@QEAAJPEBG@Z; CGenerateComment::AddLine(ushort const *)
0x14000bb08  xor     edx, edx; unsigned __int16 *
0x14000bb0a  lea     rcx, [rsp+98h+var_50]; this
0x14000bb0f  call    ?AddLine@CGenerateComment@@QEAAJPEBG@Z; CGenerateComment::AddLine(ushort const *)
0x14000bb14  lea     rdx, aAbstract; "Abstract:"
0x14000bb1b  lea     rcx, [rsp+98h+var_50]; this
0x14000bb20  call    ?AddLine@CGenerateComment@@QEAAJPEBG@Z; CGenerateComment::AddLine(ushort const *)
0x14000bb25  xor     edx, edx; unsigned __int16 *
0x14000bb27  lea     rcx, [rsp+98h+var_50]; this
0x14000bb2c  call    ?AddLine@CGenerateComment@@QEAAJPEBG@Z; CGenerateComment::AddLine(ushort const *)
0x14000bb31  lea     rdx, aIncludeFileFor; "Include file for object and counters de"...
0x14000bb38  lea     rcx, [rsp+98h+var_50]; this
0x14000bb3d  call    ?AddLine@CGenerateComment@@QEAAJPEBG@Z; CGenerateComment::AddLine(ushort const *)
0x14000bb42  xor     edx, edx; unsigned __int16 *
0x14000bb44  lea     rcx, [rsp+98h+var_50]; this
0x14000bb49  call    ?AddLine@CGenerateComment@@QEAAJPEBG@Z; CGenerateComment::AddLine(ushort const *)
0x14000bb4e  lea     rcx, [rsp+98h+var_50]; this
0x14000bb53  call    ?AddFooter@CGenerateComment@@QEAAJXZ; CGenerateComment::AddFooter(void)
0x14000bb58  mov     rdx, [rsp+98h+bstrString]; unsigned __int16 *
0x14000bb5d  mov     rcx, r15; this
0x14000bb60  call    ?WriteToFile@CGenerate@@AEAAJPEBG@Z; CGenerate::WriteToFile(ushort const *)
0x14000bb65  mov     edi, eax
0x14000bb67  mov     rcx, [rsp+98h+bstrString]; bstrString
0x14000bb6c  call    cs:__imp_SysFreeString
0x14000bb72  nop
0x14000bb73  test    edi, edi
0x14000bb75  js      loc_14000C0D1
0x14000bb7b  xor     r8d, r8d; int
0x14000bb7e  lea     rdx, asc_14001B440; "\r\n"
0x14000bb85  mov     rcx, r15; this
0x14000bb88  call    ?AppendString@CGenerate@@AEAAJPEBGH@Z; CGenerate::AppendString(ushort const *,int)
0x14000bb8d  mov     edi, eax
0x14000bb8f  test    eax, eax
0x14000bb91  js      loc_14000C0D1
0x14000bb97  xor     r8d, r8d; int
0x14000bb9a  lea     rdx, aDefine; "#define\t"
0x14000bba1  mov     rcx, r15; this
0x14000bba4  call    ?AppendString@CGenerate@@AEAAJPEBGH@Z; CGenerate::AppendString(ushort const *,int)
0x14000bba9  mov     edi, eax
0x14000bbab  test    eax, eax
0x14000bbad  js      loc_14000C0D1
0x14000bbb3  xor     r8d, r8d; int
0x14000bbb6  lea     rdx, aWmiObjects; "WMI_Objects"
0x14000bbbd  mov     rcx, r15; this
0x14000bbc0  call    ?AppendString@CGenerate@@AEAAJPEBGH@Z; CGenerate::AppendString(ushort const *,int)
0x14000bbc5  mov     edi, eax
0x14000bbc7  test    eax, eax
0x14000bbc9  js      loc_14000C0D1
0x14000bbcf  xor     r8d, r8d; int
0x14000bbd2  lea     rdx, a0; "\t0"
0x14000bbd9  mov     rcx, r15; this
0x14000bbdc  call    ?AppendString@CGenerate@@AEAAJPEBGH@Z; CGenerate::AppendString(ushort const *,int)
0x14000bbe1  mov     edi, eax
0x14000bbe3  test    eax, eax
0x14000bbe5  js      loc_14000C0D1
0x14000bbeb  xor     r8d, r8d; int
0x14000bbee  lea     rdx, asc_14001B440; "\r\n"
0x14000bbf5  mov     rcx, r15; this
0x14000bbf8  call    ?AppendString@CGenerate@@AEAAJPEBGH@Z; CGenerate::AppendString(ushort const *,int)
0x14000bbfd  mov     edi, eax
0x14000bbff  test    eax, eax
0x14000bc01  js      loc_14000C0D1
0x14000bc07  xor     r8d, r8d; int
0x14000bc0a  lea     rdx, aDefine; "#define\t"
0x14000bc11  mov     rcx, r15; this
0x14000bc14  call    ?AppendString@CGenerate@@AEAAJPEBGH@Z; CGenerate::AppendString(ushort const *,int)
0x14000bc19  mov     edi, eax
0x14000bc1b  test    eax, eax
0x14000bc1d  js      loc_14000C0D1
0x14000bc23  xor     r8d, r8d; int
0x14000bc26  lea     rdx, aHiperfClasses; "HiPerf_Classes"
0x14000bc2d  mov     rcx, r15; this
0x14000bc30  call    ?AppendString@CGenerate@@AEAAJPEBGH@Z; CGenerate::AppendString(ushort const *,int)
0x14000bc35  mov     edi, eax
0x14000bc37  test    eax, eax
0x14000bc39  js      loc_14000C0D1
0x14000bc3f  xor     r8d, r8d; int
0x14000bc42  lea     rdx, a2; "\t2"
0x14000bc49  mov     rcx, r15; this
0x14000bc4c  call    ?AppendString@CGenerate@@AEAAJPEBGH@Z; CGenerate::AppendString(ushort const *,int)
0x14000bc51  mov     edi, eax
0x14000bc53  test    eax, eax
0x14000bc55  js      loc_14000C0D1
0x14000bc5b  xor     r8d, r8d; int
0x14000bc5e  lea     rdx, asc_14001B440; "\r\n"
0x14000bc65  mov     rcx, r15; this
0x14000bc68  call    ?AppendString@CGenerate@@AEAAJPEBGH@Z; CGenerate::AppendString(ushort const *,int)
0x14000bc6d  mov     edi, eax
0x14000bc6f  test    eax, eax
0x14000bc71  js      loc_14000C0D1
0x14000bc77  xor     r8d, r8d; int
0x14000bc7a  lea     rdx, aDefine; "#define\t"
0x14000bc81  mov     rcx, r15; this
0x14000bc84  call    ?AppendString@CGenerate@@AEAAJPEBGH@Z; CGenerate::AppendString(ushort const *,int)
0x14000bc89  mov     edi, eax
0x14000bc8b  test    eax, eax
0x14000bc8d  js      loc_14000C0D1
0x14000bc93  xor     r8d, r8d; int
0x14000bc96  lea     rdx, aHiperfValidity; "HiPerf_Validity"
0x14000bc9d  mov     rcx, r15; this
0x14000bca0  call    ?AppendString@CGenerate@@AEAAJPEBGH@Z; CGenerate::AppendString(ushort const *,int)
0x14000bca5  mov     edi, eax
0x14000bca7  test    eax, eax
0x14000bca9  js      loc_14000C0D1
0x14000bcaf  xor     r8d, r8d; int
0x14000bcb2  lea     rdx, a4; "\t4"
0x14000bcb9  mov     rcx, r15; this
0x14000bcbc  call    ?AppendString@CGenerate@@AEAAJPEBGH@Z; CGenerate::AppendString(ushort const *,int)
0x14000bcc1  mov     edi, eax
0x14000bcc3  test    eax, eax
0x14000bcc5  js      loc_14000C0D1
0x14000bccb  xor     r8d, r8d; int
0x14000bcce  lea     rdx, asc_14001B440; "\r\n"
0x14000bcd5  mov     rcx, r15; this
0x14000bcd8  call    ?AppendString@CGenerate@@AEAAJPEBGH@Z; CGenerate::AppendString(ushort const *,int)
0x14000bcdd  mov     edi, eax
0x14000bcdf  test    eax, eax
0x14000bce1  js      loc_14000C0D1
0x14000bce7  mov     [rsp+98h+var_50], r13
0x14000bcec  mov     cs:dword_140024FBC, 3
0x14000bcf6  mov     r12d, esi
0x14000bcf9  mov     [rsp+98h+arg_18], esi
0x14000bd00  mov     eax, esi
0x14000bd02  mov     [rsp+98h+var_60], r14
0x14000bd07  mov     dword ptr [rsp+98h+var_68], eax
0x14000bd0b  cmp     eax, [r13+0]
0x14000bd0f  jnb     loc_14000BFEC
0x14000bd15  test    edi, edi
0x14000bd17  js      loc_14000C0D1
0x14000bd1d  lea     rax, [rax+rax*4]
0x14000bd21  mov     [rsp+98h+var_58], rax
0x14000bd26  cmp     [r15+rax*8+20h], rsi
0x14000bd2b  jz      loc_14000BFE1
0x14000bd31  mov     rbx, [r15+rax*8+18h]
0x14000bd36  mov     rbx, [rbx]
0x14000bd39  cmp     rbx, [r15+rax*8+18h]
0x14000bd3e  jz      loc_14000BFAC
0x14000bd44  test    edi, edi
0x14000bd46  js      loc_14000BFAC
0x14000bd4c  xor     r8d, r8d; int
0x14000bd4f  lea     rdx, asc_14001B440; "\r\n"
0x14000bd56  mov     rcx, r15; this
0x14000bd59  call    ?AppendString@CGenerate@@AEAAJPEBGH@Z; CGenerate::AppendString(ushort const *,int)
0x14000bd5e  mov     edi, eax
0x14000bd60  test    eax, eax
0x14000bd62  js      loc_14000BF37
0x14000bd68  xor     r8d, r8d; int
0x14000bd6b  lea     rdx, aDefine; "#define\t"
0x14000bd72  mov     rcx, r15; this
0x14000bd75  call    ?AppendString@CGenerate@@AEAAJPEBGH@Z; CGenerate::AppendString(ushort const *,int)
0x14000bd7a  mov     edi, eax
0x14000bd7c  test    eax, eax
0x14000bd7e  js      loc_14000BF37
0x14000bd84  mov     rdx, [rbx+28h]
0x14000bd88  mov     r8d, r12d; unsigned int
0x14000bd8b  mov     rdx, [rdx+8]; unsigned __int16 *
0x14000bd8f  call    ?GenerateNameInd@CGenerate@@AEAAPEAGPEBGK@Z; CGenerate::GenerateNameInd(ushort const *,ulong)
0x14000bd94  mov     r12, rax
0x14000bd97  test    rax, rax
0x14000bd9a  jz      loc_14000BF2A
0x14000bda0  xor     r8d, r8d; int
0x14000bda3  mov     rdx, rax; unsigned __int16 *
0x14000bda6  mov     rcx, r15; this
0x14000bda9  call    ?AppendString@CGenerate@@AEAAJPEBGH@Z; CGenerate::AppendString(ushort const *,int)
0x14000bdae  mov     edi, eax
0x14000bdb0  mov     rcx, r12
0x14000bdb3  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x14000bdb9  test    edi, edi
0x14000bdbb  js      loc_14000BF2F
0x14000bdc1  xor     r8d, r8d; int
0x14000bdc4  lea     rdx, asc_14001B448; "\t"
0x14000bdcb  mov     rcx, r15; this
0x14000bdce  call    ?AppendString@CGenerate@@AEAAJPEBGH@Z; CGenerate::AppendString(ushort const *,int)
0x14000bdd3  mov     edi, eax
0x14000bdd5  test    eax, eax
0x14000bdd7  js      loc_14000BF2F
0x14000bddd  call    ?GenerateIndex@CGenerate@@AEAAPEAGXZ; CGenerate::GenerateIndex(void)
0x14000bde2  mov     r12, rax
0x14000bde5  test    rax, rax
0x14000bde8  jz      loc_14000BF2A
0x14000bdee  xor     r8d, r8d; int
0x14000bdf1  mov     rdx, rax; unsigned __int16 *
0x14000bdf4  mov     rcx, r15; this
0x14000bdf7  call    ?AppendString@CGenerate@@AEAAJPEBGH@Z; CGenerate::AppendString(ushort const *,int)
0x14000bdfc  mov     edi, eax
0x14000bdfe  mov     rcx, r12
0x14000be01  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x14000be07  test    edi, edi
0x14000be09  js      loc_14000BF2F
0x14000be0f  xor     r8d, r8d; int
0x14000be12  lea     rdx, asc_14001B440; "\r\n"
0x14000be19  mov     rcx, r15; this
0x14000be1c  call    ?AppendString@CGenerate@@AEAAJPEBGH@Z; CGenerate::AppendString(ushort const *,int)
0x14000be21  mov     edi, eax
0x14000be23  test    eax, eax
0x14000be25  js      loc_14000BF2F
0x14000be2b  mov     r13d, esi
0x14000be2e  mov     rax, [rbx+28h]
0x14000be32  cmp     r13d, [rax+38h]
0x14000be36  jnb     loc_14000BF10
0x14000be3c  test    edi, edi
0x14000be3e  js      loc_14000BF2F
0x14000be44  mov     r12d, r13d
0x14000be47  mov     rax, [rax+30h]
0x14000be4b  mov     rcx, [rax+r12*8]
0x14000be4f  cmp     [rcx+20h], rsi
0x14000be53  jz      loc_14000BF08
0x14000be59  xor     r8d, r8d; int
0x14000be5c  lea     rdx, asc_14001B440; "\r\n"
0x14000be63  mov     rcx, r15; this
0x14000be66  call    ?AppendString@CGenerate@@AEAAJPEBGH@Z; CGenerate::AppendString(ushort const *,int)
0x14000be6b  mov     edi, eax
0x14000be6d  test    eax, eax
0x14000be6f  js      loc_14000BF08
0x14000be75  xor     r8d, r8d; int
0x14000be78  lea     rdx, aDefine; "#define\t"
0x14000be7f  mov     rcx, r15; this
0x14000be82  call    ?AppendString@CGenerate@@AEAAJPEBGH@Z; CGenerate::AppendString(ushort const *,int)
0x14000be87  mov     edi, eax
0x14000be89  test    eax, eax
0x14000be8b  js      short loc_14000BF08
0x14000be8d  mov     rax, [rbx+28h]
0x14000be91  mov     rcx, [rax+30h]; this
0x14000be95  mov     rdx, [rcx+r12*8]
  ... truncated ...
```
