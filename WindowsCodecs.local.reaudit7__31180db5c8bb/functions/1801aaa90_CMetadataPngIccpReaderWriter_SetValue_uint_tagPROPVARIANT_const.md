# CMetadataPngIccpReaderWriter::SetValue(uint,tagPROPVARIANT const *)

- ea: `0x1801aaa90`
- end: `0x1801aac09`
- name: `?SetValue@CMetadataPngIccpReaderWriter@@MEAAJIPEBUtagPROPVARIANT@@@Z`
- size: `377`
- prototype: `__int64 __fastcall(CMetadataPngIccpReaderWriter *__hidden this, unsigned int, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800179b0`
- `0x18004f894`
- `0x180051730`
- `0x180093288`
- `0x1800932cc`
- `0x1800a5864`
- `0x1800bd9d4`
- `0x18017e438`
- `0x1801aaa90`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801aaaf7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801aab9f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801aaaf7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801aab9f`

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
0x1801aaa90  push    rbx
0x1801aaa92  push    rbp
0x1801aaa93  push    rsi
0x1801aaa94  push    r14
0x1801aaa96  sub     rsp, 28h
0x1801aaa9a  mov     rsi, r8
0x1801aaa9d  mov     rbp, rcx
0x1801aaaa0  sub     edx, 1
0x1801aaaa3  jz      loc_1801AAB2F
0x1801aaaa9  cmp     edx, 1
0x1801aaaac  jz      short loc_1801AAAB8
0x1801aaaae  mov     ebx, 80070057h
0x1801aaab3  jmp     loc_1801AABBC
0x1801aaab8  mov     rdx, [r8+10h]; unsigned __int8 *
0x1801aaabc  test    rdx, rdx
0x1801aaabf  jz      short loc_1801AAAAE
0x1801aaac1  cmp     dword ptr [r8+8], 0
0x1801aaac6  jz      short loc_1801AAAAE
0x1801aaac8  mov     r8d, [r8+8]; unsigned __int64
0x1801aaacc  call    ?HrCheckProfileData@CMetadataPngIccpReaderWriter@@MEAAJQEAE_K@Z; CMetadataPngIccpReaderWriter::HrCheckProfileData(uchar * const,unsigned __int64)
0x1801aaad1  mov     ebx, eax
0x1801aaad3  test    eax, eax
0x1801aaad5  jns     short loc_1801AAAEC
0x1801aaad7  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1801aaade  jnz     loc_1801AAB67
0x1801aaae4  test    eax, eax
0x1801aaae6  js      loc_1801AABFC
0x1801aaaec  mov     rcx, rbp; this
0x1801aaaef  call    ?ClearProfileData@CMetadataPngIccpReaderWriter@@IEAAXXZ; CMetadataPngIccpReaderWriter::ClearProfileData(void)
0x1801aaaf4  mov     ecx, [rsi+8]; cb
0x1801aaaf7  call    cs:__imp_CoTaskMemAlloc
0x1801aaafe  nop     dword ptr [rax+rax+00h]
0x1801aab03  mov     [rbp+0A8h], rax
0x1801aab0a  test    rax, rax
0x1801aab0d  jz      loc_1801AABB7
0x1801aab13  mov     r8d, [rsi+8]; Size
0x1801aab17  mov     rcx, rax; void *
0x1801aab1a  mov     [rbp+0B0h], r8
0x1801aab21  mov     rdx, [rsi+10h]; Src
0x1801aab25  call    memcpy_0
0x1801aab2a  jmp     loc_1801AABFC
0x1801aab2f  mov     rcx, [r8+8]; char *
0x1801aab33  mov     [rsp+48h+arg_18], 0
0x1801aab3c  test    rcx, rcx
0x1801aab3f  jz      loc_1801AAAAE
0x1801aab45  lea     r8, [rsp+48h+arg_18]; unsigned __int64 *
0x1801aab4a  mov     edx, 7FFFFFFFh; unsigned __int64
0x1801aab4f  call    ?StringCchLengthA@@YAJPEBD_KPEA_K@Z; StringCchLengthA(char const *,unsigned __int64,unsigned __int64 *)
0x1801aab54  mov     ebx, eax
0x1801aab56  test    eax, eax
0x1801aab58  jns     short loc_1801AAB6B
0x1801aab5a  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1801aab61  jz      loc_1801AABFC
0x1801aab67  mov     ecx, eax
0x1801aab69  jmp     short loc_1801AABC7
0x1801aab6b  mov     r14, [rsp+48h+arg_18]
0x1801aab70  lea     rax, [r14-1]
0x1801aab74  cmp     rax, 4Eh ; 'N'
0x1801aab78  ja      loc_1801AAAAE
0x1801aab7e  mov     rdx, [rsi+8]; char *
0x1801aab82  mov     r8, r14; unsigned __int64
0x1801aab85  mov     rcx, rbp; this
0x1801aab88  call    ?HrCheckProfileName@CMetadataPngIccpReaderWriter@@MEAAJPEBD_K@Z; CMetadataPngIccpReaderWriter::HrCheckProfileName(char const *,unsigned __int64)
0x1801aab8d  mov     ebx, eax
0x1801aab8f  test    eax, eax
0x1801aab91  js      short loc_1801AAB5A
0x1801aab93  mov     rcx, rbp; this
0x1801aab96  call    ?ClearText@CMetadataGifCommentReaderWriter@@AEAAXXZ; CMetadataGifCommentReaderWriter::ClearText(void)
0x1801aab9b  lea     rcx, [r14+1]; cb
0x1801aab9f  call    cs:__imp_CoTaskMemAlloc
0x1801aaba6  nop     dword ptr [rax+rax+00h]
0x1801aabab  mov     [rbp+98h], rax
0x1801aabb2  test    rax, rax
0x1801aabb5  jnz     short loc_1801AABCE
0x1801aabb7  mov     ebx, 8007000Eh
0x1801aabbc  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1801aabc3  jz      short loc_1801AABFC
0x1801aabc5  mov     ecx, ebx; int
0x1801aabc7  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1801aabcc  jmp     short loc_1801AABFC
0x1801aabce  mov     r8, [rsi+8]; char *
0x1801aabd2  lea     rdx, [r14+1]; unsigned __int64
0x1801aabd6  mov     rcx, rax; char *
0x1801aabd9  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x1801aabde  mov     ebx, eax
0x1801aabe0  test    eax, eax
0x1801aabe2  jns     short loc_1801AABF5
0x1801aabe4  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1801aabeb  jnz     loc_1801AAB67
0x1801aabf1  test    eax, eax
0x1801aabf3  js      short loc_1801AABFC
0x1801aabf5  mov     [rbp+0A0h], r14
0x1801aabfc  mov     eax, ebx
0x1801aabfe  add     rsp, 28h
0x1801aac02  pop     r14
0x1801aac04  pop     rsi
0x1801aac05  pop     rbp
0x1801aac06  pop     rbx
0x1801aac07  retn
```
