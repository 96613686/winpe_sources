# CXMLReader::AddReservedSymbol(ushort *,ulong,SYMBOL_TYPE)

- ea: `0x180023500`
- end: `0x18002361f`
- name: `?AddReservedSymbol@CXMLReader@@AEAAJPEAGKW4SYMBOL_TYPE@@@Z`
- size: `287`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180026efc`

## callees

- `0x180018874`
- `0x18001a6c8`
- `0x180023500`
- `0x180023628`
- `0x18002cd54`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800235ff`
- `OLEAUT32!__imp_SysFreeString` at `0x1800235ff`
- `OLEAUT32!__imp_SysStringLen` at `0x180023591`
- `OLEAUT32!__imp_SysStringLen` at `0x180023591`

## string_xrefs

- `0x180023575`: `update`
- `0x18002356c`: `delete`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CXMLReader::AddReservedSymbol(__int64 a1, const unsigned __int16 *a2, int a3, int a4)
{
  unsigned int v6; // esi
  int v7; // r8d
  unsigned __int16 near **v8; // rdx
  UINT v9; // eax
  int v10; // edi
  __int64 *v12; // rdx
  __int64 v13; // [rsp+0h] [rbp-48h] BYREF
  __int64 v14; // [rsp+30h] [rbp-18h] BYREF
  struct CSymbol *v15; // [rsp+38h] [rbp-10h] BYREF
  BSTR pbstr; // [rsp+50h] [rbp+8h] BYREF
  unsigned int v17; // [rsp+68h] [rbp+20h]

  v6 = 0;
  pbstr = 0;
  v15 = 0;
  ATL::CComBSTR::Append((ATL::CComBSTR *)&pbstr, a2, a3);
  ATL::CComBSTR::Append((ATL::CComBSTR *)&pbstr, L":", 1);
  switch ( a4 )
  {
    case 4:
      v8 = (unsigned __int16 near **)wszUpdate;
      goto LABEL_9;
    case 5:
      v8 = &wszDelete;
      goto LABEL_9;
    case 6:
      v8 = &wszInsert;
LABEL_9:
      v7 = 6;
      goto LABEL_10;
  }
  if ( a4 != 7 )
    goto LABEL_11;
  v7 = 8;
  v8 = &wszOriginal;
LABEL_10:
  ATL::CComBSTR::Append((ATL::CComBSTR *)&pbstr, (const unsigned __int16 *)v8, v7);
LABEL_11:
  v9 = SysStringLen(pbstr);
  v10 = CScope::AddSymbol((CScope *)(a1 + 80), pbstr, v9, &v15);
  if ( v10 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 && off_180048C90[0] )
      bidTraceW(off_180048208[0], 2927616, off_180048C90[0], (unsigned int)v10, 2859);
    try
    {
      ThrowHR(v10);
    }
    catch ( long v14 )
    {
      v12 = &v13;
      *((_DWORD *)v12 + 26) = *((_DWORD *)v12 + 12);
      return v17;
    }
  }
  *(_DWORD *)v15 = a4;
  SysFreeString(pbstr);
  return v6;
}

```

## disassembly

```asm
0x180023500  mov     rax, rsp
0x180023503  mov     [rax+10h], rsi
0x180023507  mov     [rax+18h], rdi
0x18002350b  push    r14
0x18002350d  sub     rsp, 40h
0x180023511  mov     r14d, r9d
0x180023514  mov     rdi, rcx
0x180023517  xor     esi, esi
0x180023519  mov     [rax+8], rsi
0x18002351d  mov     [rax-10h], rsi
0x180023521  lea     rcx, [rax+8]; this
0x180023525  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x18002352a  lea     r8d, [rsi+1]; int
0x18002352e  lea     rdx, asc_180039394; ":"
0x180023535  lea     rcx, [rsp+48h+pbstr]; this
0x18002353a  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x18002353f  mov     ecx, r14d
0x180023542  sub     ecx, 4
0x180023545  jz      short loc_180023575
0x180023547  sub     ecx, 1
0x18002354a  jz      short loc_18002356C
0x18002354c  sub     ecx, 1
0x18002354f  jz      short loc_180023563
0x180023551  cmp     ecx, 1
0x180023554  jnz     short loc_18002358C
0x180023556  lea     r8d, [rsi+8]
0x18002355a  lea     rdx, ?wszOriginal@@3PAGA; "original"
0x180023561  jmp     short loc_180023582
0x180023563  lea     rdx, ?wszInsert@@3PAGA; "insert"
0x18002356a  jmp     short loc_18002357C
0x18002356c  lea     rdx, ?wszDelete@@3PAGA; "delete"
0x180023573  jmp     short loc_18002357C
0x180023575  lea     rdx, ?wszUpdate@@3PAGA; "update"
0x18002357c  mov     r8d, 6; int
0x180023582  lea     rcx, [rsp+48h+pbstr]; this
0x180023587  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x18002358c  mov     rcx, [rsp+48h+pbstr]; pbstr
0x180023591  call    cs:__imp_SysStringLen
0x180023597  lea     rcx, [rdi+50h]; this
0x18002359b  lea     r9, [rsp+48h+var_10]; struct CSymbol **
0x1800235a0  mov     r8d, eax; unsigned int
0x1800235a3  mov     rdx, [rsp+48h+pbstr]; unsigned __int16 *
0x1800235a8  call    ?AddSymbol@CScope@@QEAAJPEAGKPEAPEAVCSymbol@@@Z; CScope::AddSymbol(ushort *,ulong,CSymbol * *)
0x1800235ad  mov     edi, eax
0x1800235af  test    eax, eax
0x1800235b1  jns     short loc_1800235F2
0x1800235b3  test    byte ptr cs:_bidGblFlags, 2
0x1800235ba  jz      short loc_1800235EB
0x1800235bc  mov     rax, cs:off_180048C90; "<CXMLReader::AddReservedSymbol|ADO|ERR>"...
0x1800235c3  test    rax, rax
0x1800235c6  jz      short loc_1800235EB
0x1800235c8  mov     [rsp+48h+var_28], 0B2Bh
0x1800235d0  mov     r9d, edi
0x1800235d3  mov     r8, cs:off_180048C90; "<CXMLReader::AddReservedSymbol|ADO|ERR>"...
0x1800235da  mov     edx, 2CAC00h
0x1800235df  mov     rcx, cs:off_180048208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800235e6  call    _bidTraceW
0x1800235eb  mov     ecx, edi; int
0x1800235ed  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800235f2  mov     rax, [rsp+48h+var_10]
0x1800235f7  mov     [rax], r14d
0x1800235fa  mov     rcx, [rsp+48h+pbstr]; bstrString
0x1800235ff  call    cs:__imp_SysFreeString
0x180023605  nop
0x180023606  jmp     short loc_18002360C
0x180023608  mov     esi, [rsp+48h+arg_18]
0x18002360c  mov     eax, esi
0x18002360e  mov     rsi, [rsp+48h+arg_8]
0x180023613  mov     rdi, [rsp+48h+arg_10]
0x180023618  add     rsp, 40h
0x18002361c  pop     r14
0x18002361e  retn
```
