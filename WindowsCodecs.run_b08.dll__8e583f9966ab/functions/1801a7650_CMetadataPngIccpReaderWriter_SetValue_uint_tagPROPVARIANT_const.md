# CMetadataPngIccpReaderWriter::SetValue(uint,tagPROPVARIANT const *)

- ea: `0x1801a7650`
- end: `0x1801a77b0`
- name: `?SetValue@CMetadataPngIccpReaderWriter@@MEAAJIPEBUtagPROPVARIANT@@@Z`
- size: `352`
- prototype: `__int64 __fastcall(CMetadataPngIccpReaderWriter *__hidden this, unsigned int, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x180020e14`
- `0x180045650`
- `0x180046350`
- `0x1800469d0`
- `0x1800a98ac`
- `0x1800a98ec`
- `0x1800bb784`
- `0x18017b528`
- `0x1801a7650`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801a76af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801a7751`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801a76af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801a7751`

## pseudocode

```c
__int64 __fastcall CMetadataPngIccpReaderWriter::SetValue(
        CMetadataPngIccpReaderWriter *this,
        int a2,
        const struct tagPROPVARIANT *a3)
{
  int v5; // edx
  unsigned int v6; // ebx
  unsigned __int8 *pData; // rdx
  int v8; // eax
  void *v9; // rax
  size_t ulVal; // r8
  const char *pszVal; // rcx
  int v12; // ecx
  unsigned __int64 v13; // r14
  char *v14; // rax
  unsigned __int64 v16; // [rsp+68h] [rbp+20h] BYREF

  v5 = a2 - 1;
  if ( v5 )
  {
    if ( v5 == 1 )
    {
      pData = a3->bstrblobVal.pData;
      if ( pData )
      {
        if ( a3->lVal )
        {
          v8 = CMetadataPngIccpReaderWriter::HrCheckProfileData(this, pData, a3->ulVal);
          v6 = v8;
          if ( v8 < 0 )
          {
            if ( !(_DWORD)g_doStackCaptures )
              return v6;
            goto LABEL_14;
          }
          CMetadataPngIccpReaderWriter::ClearProfileData(this);
          v9 = CoTaskMemAlloc(a3->ulVal);
          *((_QWORD *)this + 21) = v9;
          if ( v9 )
          {
            ulVal = a3->ulVal;
            *((_QWORD *)this + 22) = ulVal;
            memcpy_0(v9, a3->bstrblobVal.pData, ulVal);
            return v6;
          }
          goto LABEL_18;
        }
      }
    }
LABEL_3:
    v6 = -2147024809;
    goto LABEL_19;
  }
  pszVal = a3->pszVal;
  v16 = 0;
  if ( !pszVal )
    goto LABEL_3;
  v8 = StringCchLengthA(pszVal, 0x7FFFFFFFu, &v16);
  v6 = v8;
  if ( v8 >= 0 )
  {
    v13 = v16;
    if ( v16 - 1 > 0x4E )
      goto LABEL_3;
    v8 = CMetadataPngIccpReaderWriter::HrCheckProfileName(this, a3->pszVal, v16);
    v6 = v8;
    if ( v8 >= 0 )
    {
      CMetadataGifCommentReaderWriter::ClearText(this);
      v14 = (char *)CoTaskMemAlloc(v13 + 1);
      *((_QWORD *)this + 19) = v14;
      if ( v14 )
      {
        v8 = StringCchCopyA(v14, v13 + 1, a3->pszVal);
        v6 = v8;
        if ( v8 >= 0 )
        {
          *((_QWORD *)this + 20) = v13;
          return v6;
        }
        if ( !(_DWORD)g_doStackCaptures )
          return v6;
        goto LABEL_14;
      }
LABEL_18:
      v6 = -2147024882;
LABEL_19:
      if ( (_DWORD)g_doStackCaptures )
      {
        v12 = v6;
        goto LABEL_21;
      }
      return v6;
    }
  }
  if ( (_DWORD)g_doStackCaptures )
  {
LABEL_14:
    v12 = v8;
LABEL_21:
    DoStackCapture(v12);
  }
  return v6;
}

```

## disassembly

```asm
0x1801a7650  push    rbx
0x1801a7652  push    rbp
0x1801a7653  push    rsi
0x1801a7654  push    r14
0x1801a7656  sub     rsp, 28h
0x1801a765a  mov     rsi, r8
0x1801a765d  mov     rbp, rcx
0x1801a7660  sub     edx, 1
0x1801a7663  jz      short loc_1801A76E1
0x1801a7665  cmp     edx, 1
0x1801a7668  jz      short loc_1801A7674
0x1801a766a  mov     ebx, 80070057h
0x1801a766f  jmp     loc_1801A7768
0x1801a7674  mov     rdx, [r8+10h]; unsigned __int8 *
0x1801a7678  test    rdx, rdx
0x1801a767b  jz      short loc_1801A766A
0x1801a767d  cmp     dword ptr [r8+8], 0
0x1801a7682  jz      short loc_1801A766A
0x1801a7684  mov     r8d, [r8+8]; unsigned __int64
0x1801a7688  call    ?HrCheckProfileData@CMetadataPngIccpReaderWriter@@MEAAJQEAE_K@Z; CMetadataPngIccpReaderWriter::HrCheckProfileData(uchar * const,unsigned __int64)
0x1801a768d  mov     ebx, eax
0x1801a768f  test    eax, eax
0x1801a7691  jns     short loc_1801A76A4
0x1801a7693  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1801a769a  jnz     short loc_1801A7719
0x1801a769c  test    eax, eax
0x1801a769e  js      loc_1801A77A4
0x1801a76a4  mov     rcx, rbp; this
0x1801a76a7  call    ?ClearProfileData@CMetadataPngIccpReaderWriter@@IEAAXXZ; CMetadataPngIccpReaderWriter::ClearProfileData(void)
0x1801a76ac  mov     ecx, [rsi+8]; cb
0x1801a76af  call    cs:__imp_CoTaskMemAlloc
0x1801a76b5  mov     [rbp+0A8h], rax
0x1801a76bc  test    rax, rax
0x1801a76bf  jz      loc_1801A7763
0x1801a76c5  mov     r8d, [rsi+8]; Size
0x1801a76c9  mov     rcx, rax; void *
0x1801a76cc  mov     [rbp+0B0h], r8
0x1801a76d3  mov     rdx, [rsi+10h]; Src
0x1801a76d7  call    memcpy_0
0x1801a76dc  jmp     loc_1801A77A4
0x1801a76e1  mov     rcx, [r8+8]; char *
0x1801a76e5  mov     [rsp+48h+arg_18], 0
0x1801a76ee  test    rcx, rcx
0x1801a76f1  jz      loc_1801A766A
0x1801a76f7  lea     r8, [rsp+48h+arg_18]; unsigned __int64 *
0x1801a76fc  mov     edx, 7FFFFFFFh; unsigned __int64
0x1801a7701  call    ?StringCchLengthA@@YAJPEBD_KPEA_K@Z; StringCchLengthA(char const *,unsigned __int64,unsigned __int64 *)
0x1801a7706  mov     ebx, eax
0x1801a7708  test    eax, eax
0x1801a770a  jns     short loc_1801A771D
0x1801a770c  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1801a7713  jz      loc_1801A77A4
0x1801a7719  mov     ecx, eax
0x1801a771b  jmp     short loc_1801A7773
0x1801a771d  mov     r14, [rsp+48h+arg_18]
0x1801a7722  lea     rax, [r14-1]
0x1801a7726  cmp     rax, 4Eh ; 'N'
0x1801a772a  ja      loc_1801A766A
0x1801a7730  mov     rdx, [rsi+8]; char *
0x1801a7734  mov     r8, r14; unsigned __int64
0x1801a7737  mov     rcx, rbp; this
0x1801a773a  call    ?HrCheckProfileName@CMetadataPngIccpReaderWriter@@MEAAJPEBD_K@Z; CMetadataPngIccpReaderWriter::HrCheckProfileName(char const *,unsigned __int64)
0x1801a773f  mov     ebx, eax
0x1801a7741  test    eax, eax
0x1801a7743  js      short loc_1801A770C
0x1801a7745  mov     rcx, rbp; this
0x1801a7748  call    ?ClearText@CMetadataGifCommentReaderWriter@@AEAAXXZ; CMetadataGifCommentReaderWriter::ClearText(void)
0x1801a774d  lea     rcx, [r14+1]; cb
0x1801a7751  call    cs:__imp_CoTaskMemAlloc
0x1801a7757  mov     [rbp+98h], rax
0x1801a775e  test    rax, rax
0x1801a7761  jnz     short loc_1801A777A
0x1801a7763  mov     ebx, 8007000Eh
0x1801a7768  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1801a776f  jz      short loc_1801A77A4
0x1801a7771  mov     ecx, ebx; int
0x1801a7773  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1801a7778  jmp     short loc_1801A77A4
0x1801a777a  mov     r8, [rsi+8]; char *
0x1801a777e  lea     rdx, [r14+1]; unsigned __int64
0x1801a7782  mov     rcx, rax; char *
0x1801a7785  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x1801a778a  mov     ebx, eax
0x1801a778c  test    eax, eax
0x1801a778e  jns     short loc_1801A779D
0x1801a7790  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1801a7797  jnz     short loc_1801A7719
0x1801a7799  test    eax, eax
0x1801a779b  js      short loc_1801A77A4
0x1801a779d  mov     [rbp+0A0h], r14
0x1801a77a4  mov     eax, ebx
0x1801a77a6  add     rsp, 28h
0x1801a77aa  pop     r14
0x1801a77ac  pop     rsi
0x1801a77ad  pop     rbp
0x1801a77ae  pop     rbx
0x1801a77af  retn
```
