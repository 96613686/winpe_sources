# CMsmqVssWriter::VerifyRestoreLocation(wchar_t const *,ulong,ulong *)

- ea: `0x18009422c`
- end: `0x1800944c0`
- name: `?VerifyRestoreLocation@CMsmqVssWriter@@AEAAJPEB_WKPEAK@Z`
- size: `660`
- prototype: `__int64 __fastcall(CMsmqVssWriter *__hidden this, const wchar_t *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180090d40`

## callees

- `0x18000bb04`
- `0x18002c61c`
- `0x18008ffc0`
- `0x18009422c`
- `0x18009bd1c`

## import_xrefs

- `msvcrt!free` at `0x1800942a4`
- `msvcrt!free` at `0x1800942eb`
- `msvcrt!free` at `0x180094332`
- `msvcrt!free` at `0x180094374`
- `msvcrt!free` at `0x1800943c9`
- `msvcrt!free` at `0x180094408`
- `msvcrt!free` at `0x18009445d`
- `msvcrt!free` at `0x18009449b`
- `msvcrt!free` at `0x1800944aa`
- `msvcrt!free` at `0x1800942a4`
- `msvcrt!free` at `0x1800942eb`
- `msvcrt!free` at `0x180094332`
- `msvcrt!free` at `0x180094374`
- `msvcrt!free` at `0x1800943c9`
- `msvcrt!free` at `0x180094408`
- `msvcrt!free` at `0x18009445d`
- `msvcrt!free` at `0x18009449b`
- `msvcrt!free` at `0x1800944aa`

## string_xrefs

- `0x180094292`: `writer/mqwriter`
- `0x1800942d4`: `writer/mqwriter`
- `0x18009431b`: `writer/mqwriter`
- `0x18009435d`: `writer/mqwriter`
- `0x1800943b7`: `writer/mqwriter`
- `0x1800943f1`: `writer/mqwriter`
- `0x18009444b`: `writer/mqwriter`
- `0x180094484`: `writer/mqwriter`
- `0x18009425f`: `config`
- `0x180094341`: `msmqwebacl.bkp`
- `0x1800943d5`: `*.xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CMsmqVssWriter::VerifyRestoreLocation(
        CMsmqVssWriter *this,
        const wchar_t *a2,
        char a3,
        unsigned int *a4)
{
  wchar_t *v7; // rbx
  int v8; // eax
  CMsmqVssWriter *v9; // rcx
  unsigned int v10; // ebp
  int v12; // eax
  CMsmqVssWriter *v13; // rcx
  int v14; // eax
  CMsmqVssWriter *v15; // rcx
  unsigned int v16; // esi

  *a4 = 0;
  v7 = (wchar_t *)MmAllocate(0x20Au);
  v8 = StringCchPrintfW(v7, 0x105u, L"%s\\%s", a2, L"config");
  v10 = v8;
  if ( v8 < 0 )
  {
    LogMsgHR(v8, (wchar_t *)L"writer/mqwriter", 0xFA0u);
    free(v7);
    return v10;
  }
  if ( (a3 & 1) != 0 && !CMsmqVssWriter::GetFileCount(v9, v7, L"msmqreg.bkp") )
  {
    *a4 |= 1u;
    LogMsgHR(-1072824319, (wchar_t *)L"writer/mqwriter", 0xFA2u);
    free(v7);
    return 3222142977LL;
  }
  if ( (a3 & 2) != 0 && !CMsmqVssWriter::GetFileCount(v9, v7, L"0*.*") )
  {
    *a4 |= 2u;
    LogMsgHR(-1072824319, (wchar_t *)L"writer/mqwriter", 0xFA4u);
    free(v7);
    return 3222142977LL;
  }
  if ( (a3 & 8) != 0 && !CMsmqVssWriter::GetFileCount(v9, v7, L"msmqwebacl.bkp") )
  {
    *a4 |= 8u;
    LogMsgHR(-1072824319, (wchar_t *)L"writer/mqwriter", 0xFA6u);
    free(v7);
    return 3222142977LL;
  }
  if ( (a3 & 4) != 0 )
  {
    v12 = StringCchPrintfW(v7, 0x105u, L"%s\\%s", a2, L"mapping");
    v10 = v12;
    if ( v12 < 0 )
    {
      LogMsgHR(v12, (wchar_t *)L"writer/mqwriter", 0xFA8u);
      free(v7);
      return v10;
    }
    if ( !CMsmqVssWriter::GetFileCount(v13, v7, L"*.xml") )
    {
      *a4 |= 4u;
      LogMsgHR(-1072824319, (wchar_t *)L"writer/mqwriter", 0xFB6u);
      free(v7);
      return 3222142977LL;
    }
  }
  if ( (a3 & 0x10) != 0 )
  {
    v14 = StringCchPrintfW(v7, 0x105u, L"%s\\%s", a2, L"queue");
    v16 = v14;
    if ( v14 < 0 )
    {
      LogMsgHR(v14, (wchar_t *)L"writer/mqwriter", 0xFACu);
      free(v7);
      return v16;
    }
    if ( !CMsmqVssWriter::GetFileCount(v15, v7, L"*") )
    {
      *a4 |= 0x10u;
      LogMsgHR(-1072824319, (wchar_t *)L"writer/mqwriter", 0xFAEu);
      free(v7);
      return 3222142977LL;
    }
  }
  free(v7);
  return 0;
}

```

## disassembly

```asm
0x18009422c  mov     [rsp+arg_0], rcx
0x180094231  push    rbx
0x180094232  push    rbp
0x180094233  push    rsi
0x180094234  push    rdi
0x180094235  push    r12
0x180094237  push    r14
0x180094239  sub     rsp, 38h
0x18009423d  mov     rdi, r9
0x180094240  mov     esi, r8d
0x180094243  mov     r14, rdx
0x180094246  mov     dword ptr [r9], 0
0x18009424d  mov     ecx, 20Ah; unsigned __int64
0x180094252  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180094257  mov     rbx, rax
0x18009425a  mov     [rsp+68h+arg_0], rax
0x18009425f  lea     rax, aConfig; "config"
0x180094266  mov     [rsp+68h+var_48], rax
0x18009426b  mov     r9, r14
0x18009426e  lea     r8, aSS_3; "%s\\%s"
0x180094275  mov     r12d, 105h
0x18009427b  mov     edx, r12d; unsigned __int64
0x18009427e  mov     rcx, rbx; wchar_t *
0x180094281  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180094286  mov     ebp, eax
0x180094288  test    eax, eax
0x18009428a  jns     short loc_1800942B2
0x18009428c  mov     r8d, 0FA0h; unsigned __int16
0x180094292  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x180094299  mov     ecx, eax; int
0x18009429b  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x1800942a0  nop
0x1800942a1  mov     rcx, rbx; Block
0x1800942a4  call    cs:__imp_free
0x1800942aa  nop
0x1800942ab  mov     eax, ebp
0x1800942ad  jmp     loc_1800944B3
0x1800942b2  test    sil, 1
0x1800942b6  jz      short loc_1800942F9
0x1800942b8  lea     r8, aMsmqregBkp; "msmqreg.bkp"
0x1800942bf  mov     rdx, rbx; wchar_t *
0x1800942c2  call    ?GetFileCount@CMsmqVssWriter@@AEAAKPEB_W0@Z; CMsmqVssWriter::GetFileCount(wchar_t const *,wchar_t const *)
0x1800942c7  test    eax, eax
0x1800942c9  jnz     short loc_1800942F9
0x1800942cb  or      dword ptr [rdi], 1
0x1800942ce  mov     r8d, 0FA2h; unsigned __int16
0x1800942d4  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x1800942db  mov     edi, 0C00E0001h
0x1800942e0  mov     ecx, edi; int
0x1800942e2  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x1800942e7  nop
0x1800942e8  mov     rcx, rbx; Block
0x1800942eb  call    cs:__imp_free
0x1800942f1  nop
0x1800942f2  mov     eax, edi
0x1800942f4  jmp     loc_1800944B3
0x1800942f9  test    sil, 2
0x1800942fd  jz      short loc_18009433B
0x1800942ff  lea     r8, a0; "0*.*"
0x180094306  mov     rdx, rbx; wchar_t *
0x180094309  call    ?GetFileCount@CMsmqVssWriter@@AEAAKPEB_W0@Z; CMsmqVssWriter::GetFileCount(wchar_t const *,wchar_t const *)
0x18009430e  test    eax, eax
0x180094310  jnz     short loc_18009433B
0x180094312  or      dword ptr [rdi], 2
0x180094315  mov     r8d, 0FA4h; unsigned __int16
0x18009431b  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x180094322  mov     edi, 0C00E0001h
0x180094327  mov     ecx, edi; int
0x180094329  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18009432e  nop
0x18009432f  mov     rcx, rbx; Block
0x180094332  call    cs:__imp_free
0x180094338  nop
0x180094339  jmp     short loc_1800942F2
0x18009433b  test    sil, 8
0x18009433f  jz      short loc_180094380
0x180094341  lea     r8, aMsmqwebaclBkp; "msmqwebacl.bkp"
0x180094348  mov     rdx, rbx; wchar_t *
0x18009434b  call    ?GetFileCount@CMsmqVssWriter@@AEAAKPEB_W0@Z; CMsmqVssWriter::GetFileCount(wchar_t const *,wchar_t const *)
0x180094350  test    eax, eax
0x180094352  jnz     short loc_180094380
0x180094354  or      dword ptr [rdi], 8
0x180094357  mov     r8d, 0FA6h; unsigned __int16
0x18009435d  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x180094364  mov     edi, 0C00E0001h
0x180094369  mov     ecx, edi; int
0x18009436b  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180094370  nop
0x180094371  mov     rcx, rbx; Block
0x180094374  call    cs:__imp_free
0x18009437a  nop
0x18009437b  jmp     loc_1800942F2
0x180094380  test    sil, 4
0x180094384  jz      loc_180094414
0x18009438a  lea     rax, aMapping; "mapping"
0x180094391  mov     [rsp+68h+var_48], rax
0x180094396  mov     r9, r14
0x180094399  lea     r8, aSS_3; "%s\\%s"
0x1800943a0  mov     rdx, r12; unsigned __int64
0x1800943a3  mov     rcx, rbx; wchar_t *
0x1800943a6  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800943ab  mov     ebp, eax
0x1800943ad  test    eax, eax
0x1800943af  jns     short loc_1800943D5
0x1800943b1  mov     r8d, 0FA8h; unsigned __int16
0x1800943b7  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x1800943be  mov     ecx, eax; int
0x1800943c0  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x1800943c5  nop
0x1800943c6  mov     rcx, rbx; Block
0x1800943c9  call    cs:__imp_free
0x1800943cf  nop
0x1800943d0  jmp     loc_1800942AB
0x1800943d5  lea     r8, aXml_0; "*.xml"
0x1800943dc  mov     rdx, rbx; wchar_t *
0x1800943df  call    ?GetFileCount@CMsmqVssWriter@@AEAAKPEB_W0@Z; CMsmqVssWriter::GetFileCount(wchar_t const *,wchar_t const *)
0x1800943e4  test    eax, eax
0x1800943e6  jnz     short loc_180094414
0x1800943e8  or      dword ptr [rdi], 4
0x1800943eb  mov     r8d, 0FB6h; unsigned __int16
0x1800943f1  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x1800943f8  mov     edi, 0C00E0001h
0x1800943fd  mov     ecx, edi; int
0x1800943ff  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180094404  nop
0x180094405  mov     rcx, rbx; Block
0x180094408  call    cs:__imp_free
0x18009440e  nop
0x18009440f  jmp     loc_1800942F2
0x180094414  test    sil, 10h
0x180094418  jz      loc_1800944A7
0x18009441e  lea     rax, aQueue; "queue"
0x180094425  mov     [rsp+68h+var_48], rax
0x18009442a  mov     r9, r14
0x18009442d  lea     r8, aSS_3; "%s\\%s"
0x180094434  mov     rdx, r12; unsigned __int64
0x180094437  mov     rcx, rbx; wchar_t *
0x18009443a  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18009443f  mov     esi, eax
0x180094441  test    eax, eax
0x180094443  jns     short loc_180094468
0x180094445  mov     r8d, 0FACh; unsigned __int16
0x18009444b  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x180094452  mov     ecx, eax; int
0x180094454  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180094459  nop
0x18009445a  mov     rcx, rbx; Block
0x18009445d  call    cs:__imp_free
0x180094463  nop
0x180094464  mov     eax, esi
0x180094466  jmp     short loc_1800944B3
0x180094468  lea     r8, asc_180104F98; "*"
0x18009446f  mov     rdx, rbx; wchar_t *
0x180094472  call    ?GetFileCount@CMsmqVssWriter@@AEAAKPEB_W0@Z; CMsmqVssWriter::GetFileCount(wchar_t const *,wchar_t const *)
0x180094477  test    eax, eax
0x180094479  jnz     short loc_1800944A7
0x18009447b  or      dword ptr [rdi], 10h
0x18009447e  mov     r8d, 0FAEh; unsigned __int16
0x180094484  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18009448b  mov     edi, 0C00E0001h
0x180094490  mov     ecx, edi; int
0x180094492  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180094497  nop
0x180094498  mov     rcx, rbx; Block
0x18009449b  call    cs:__imp_free
0x1800944a1  nop
0x1800944a2  jmp     loc_1800942F2
0x1800944a7  mov     rcx, rbx; Block
0x1800944aa  call    cs:__imp_free
0x1800944b0  nop
0x1800944b1  xor     eax, eax
0x1800944b3  add     rsp, 38h
0x1800944b7  pop     r14
0x1800944b9  pop     r12
0x1800944bb  pop     rdi
0x1800944bc  pop     rsi
0x1800944bd  pop     rbp
0x1800944be  pop     rbx
0x1800944bf  retn
```
