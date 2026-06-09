# CDplUser::DoesDplPolicyApplyToAccount(_DPL_ACCOUNT_POLICY_INFO *,ushort const *,int *)

- ea: `0x1800add9c`
- end: `0x1800ae003`
- name: `?DoesDplPolicyApplyToAccount@CDplUser@@AEAAJPEAU_DPL_ACCOUNT_POLICY_INFO@@PEBGPEAH@Z`
- size: `615`
- prototype: `int(CDplUser *__hidden this, struct _DPL_ACCOUNT_POLICY_INFO *, const unsigned __int16 *, int *)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800ab1d8`
- `0x1800b49b4`
- `0x1800b6834`

## callees

- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x1800935b8`
- `0x1800add9c`
- `0x1800d5af8`

## import_xrefs

- `msvcrt!_wcsrev` at `0x1800adf83`
- `msvcrt!_wcsrev` at `0x1800adf83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800adef3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800adfaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800adef3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800adfaa`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800adee5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800adfa0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800adee5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800adfa0`

## pseudocode

```c
__int64 __fastcall CDplUser::DoesDplPolicyApplyToAccount(
        CDplUser *this,
        struct _DPL_ACCOUNT_POLICY_INFO *a2,
        const unsigned __int16 *a3,
        int *a4)
{
  unsigned int TrimmedEntIdString; // ebx
  int v8; // r8d
  CDplServiceImpl *v9; // rcx
  __int64 v10; // rdx
  int v11; // eax
  signed int v12; // eax
  _WORD *v13; // rax
  signed int LastError; // eax
  char bIgnoreCase; // [rsp+20h] [rbp-48h]
  LPCWCH lpString1; // [rsp+70h] [rbp+8h] BYREF
  unsigned __int64 v18; // [rsp+78h] [rbp+10h] BYREF

  lpString1 = 0;
  v18 = 0;
  if ( a4 )
    *a4 = 0;
  if ( !a2 )
  {
    bIgnoreCase = 19;
LABEL_5:
    TrimmedEntIdString = -2147024809;
    v8 = -2147024809;
LABEL_6:
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v8, 40, bIgnoreCase);
    goto LABEL_32;
  }
  if ( !a4 )
  {
    TrimmedEntIdString = -2147467261;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147467261, 40, 20);
    goto LABEL_32;
  }
  TrimmedEntIdString = 0;
  if ( a3 )
  {
    fnEfsLogTrace1Strings((_DWORD)this, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 38);
    TrimmedEntIdString = CDplServiceImpl::GetTrimmedEntIdString(v9, a3, (unsigned __int16 **)&lpString1, &v18);
    if ( (int)fnEfsLogTrace1String1Dword(
                g_hPublisher,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                (unsigned int)&sourceString,
                TrimmedEntIdString,
                40,
                38) >= 0 )
    {
      if ( v18 <= 2 )
      {
        bIgnoreCase = 42;
        goto LABEL_5;
      }
      if ( *(_DWORD *)a2 )
      {
        v13 = (_WORD *)*((_QWORD *)a2 + 3);
        if ( !v13 )
        {
          TrimmedEntIdString = -2147418113;
          fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147418113, 40, 93);
          goto LABEL_32;
        }
        if ( !*v13 )
        {
          fnEfsLogTrace1String1Dword(
            g_hPublisher,
            (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
            (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
            (unsigned int)L"'Match-any' wildcard DPL policy applied",
            0,
            40,
            102);
LABEL_31:
          *a4 = 1;
          goto LABEL_32;
        }
        if ( *((int *)a2 + 8) > (v18 >> 1) - 1 )
          goto LABEL_32;
        _wcsrev((wchar_t *)lpString1);
        v11 = CompareStringOrdinal(lpString1, *((_DWORD *)a2 + 8), *((LPCWCH *)a2 + 3), *((_DWORD *)a2 + 8), 1);
        if ( !v11 )
        {
          LastError = GetLastError();
          TrimmedEntIdString = LastError;
          if ( LastError > 0 )
            TrimmedEntIdString = (unsigned __int16)LastError | 0x80070000;
          bIgnoreCase = -120;
          goto LABEL_29;
        }
      }
      else
      {
        v10 = *((int *)a2 + 4);
        if ( v10 != (v18 >> 1) - 1 )
          goto LABEL_32;
        v11 = CompareStringOrdinal(lpString1, v10, *((LPCWCH *)a2 + 1), v10, 1);
        if ( !v11 )
        {
          v12 = GetLastError();
          TrimmedEntIdString = v12;
          if ( v12 > 0 )
            TrimmedEntIdString = (unsigned __int16)v12 | 0x80070000;
          bIgnoreCase = 70;
LABEL_29:
          v8 = TrimmedEntIdString;
          goto LABEL_6;
        }
      }
      if ( v11 != 2 )
        goto LABEL_32;
      goto LABEL_31;
    }
  }
LABEL_32:
  if ( lpString1 )
    DplibMemFree((void *)lpString1);
  return TrimmedEntIdString;
}

```

## disassembly

```asm
0x1800add9c  mov     rax, rsp
0x1800add9f  mov     [rax+18h], rbx
0x1800adda3  mov     [rax+8], rcx
0x1800adda7  push    rbp
0x1800adda8  push    rsi
0x1800adda9  push    rdi
0x1800addaa  push    r12
0x1800addac  push    r14
0x1800addae  sub     rsp, 40h
0x1800addb2  xor     r12d, r12d
0x1800addb5  mov     r14, r9
0x1800addb8  mov     [rax+8], r12
0x1800addbc  mov     rbp, r8
0x1800addbf  mov     [rax+10h], r12
0x1800addc3  mov     rsi, rdx
0x1800addc6  test    r9, r9
0x1800addc9  jz      short loc_1800ADDD0
0x1800addcb  xor     eax, eax
0x1800addcd  mov     [r9], eax
0x1800addd0  test    rsi, rsi
0x1800addd3  jnz     short loc_1800ADE04
0x1800addd5  mov     dword ptr [rsp+68h+bIgnoreCase], 1613h
0x1800adddd  lea     r9d, [rsi+28h]
0x1800adde1  mov     ebx, 80070057h
0x1800adde6  mov     r8d, 80070057h
0x1800addec  mov     rcx, cs:g_hPublisher
0x1800addf3  lea     rdx, EFS_TRACE_ERROR
0x1800addfa  call    fnEfsLogTrace1
0x1800addff  jmp     loc_1800ADFDE
0x1800ade04  test    r14, r14
0x1800ade07  jnz     short loc_1800ADE22
0x1800ade09  mov     ebx, 80004003h
0x1800ade0e  mov     dword ptr [rsp+68h+bIgnoreCase], 1614h
0x1800ade16  lea     r9d, [r14+28h]
0x1800ade1a  mov     r8d, 80004003h
0x1800ade20  jmp     short loc_1800ADDEC
0x1800ade22  mov     ebx, r12d
0x1800ade25  test    rbp, rbp
0x1800ade28  jz      loc_1800ADFDE
0x1800ade2e  mov     edi, 28h ; '('
0x1800ade33  mov     dword ptr [rsp+68h+bIgnoreCase], 1626h
0x1800ade3b  mov     r9d, edi
0x1800ade3e  lea     r8, sourceString
0x1800ade45  lea     rdx, EFS_TRACE_START_EVENT
0x1800ade4c  call    fnEfsLogTrace1Strings
0x1800ade51  lea     r9, [rsp+68h+arg_8]; unsigned __int64 *
0x1800ade56  mov     rdx, rbp; unsigned __int16 *
0x1800ade59  lea     r8, [rsp+68h+lpString1]; unsigned __int16 **
0x1800ade5e  call    ?GetTrimmedEntIdString@CDplServiceImpl@@AEAAJPEBGPEAPEAGPEA_K@Z; CDplServiceImpl::GetTrimmedEntIdString(ushort const *,ushort * *,unsigned __int64 *)
0x1800ade63  mov     rcx, cs:g_hPublisher
0x1800ade6a  lea     r9, sourceString
0x1800ade71  mov     [rsp+68h+var_38], 1626h
0x1800ade79  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800ade80  mov     [rsp+68h+var_40], edi
0x1800ade84  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800ade8b  mov     dword ptr [rsp+68h+bIgnoreCase], eax
0x1800ade8f  mov     ebx, eax
0x1800ade91  call    fnEfsLogTrace1String1Dword
0x1800ade96  test    eax, eax
0x1800ade98  js      loc_1800ADFDE
0x1800ade9e  mov     rcx, [rsp+68h+arg_8]
0x1800adea3  cmp     rcx, 2
0x1800adea7  ja      short loc_1800ADEB9
0x1800adea9  mov     dword ptr [rsp+68h+bIgnoreCase], 162Ah
0x1800adeb1  mov     r9d, edi
0x1800adeb4  jmp     loc_1800ADDE1
0x1800adeb9  cmp     [rsi], r12d
0x1800adebc  jnz     short loc_1800ADF15
0x1800adebe  movsxd  rdx, dword ptr [rsi+10h]; cchCount1
0x1800adec2  shr     rcx, 1
0x1800adec5  dec     rcx
0x1800adec8  cmp     rdx, rcx
0x1800adecb  jnz     loc_1800ADFDE
0x1800aded1  mov     r8, [rsi+8]; lpString2
0x1800aded5  mov     r9d, edx; cchCount2
0x1800aded8  mov     rcx, [rsp+68h+lpString1]; lpString1
0x1800adedd  mov     dword ptr [rsp+68h+bIgnoreCase], 1; bIgnoreCase
0x1800adee5  call    cs:__imp_CompareStringOrdinal
0x1800adeeb  test    eax, eax
0x1800adeed  jnz     loc_1800ADFD2
0x1800adef3  call    cs:__imp_GetLastError
0x1800adef9  mov     ebx, eax
0x1800adefb  test    eax, eax
0x1800adefd  jle     short loc_1800ADF08
0x1800adeff  movzx   ebx, ax
0x1800adf02  or      ebx, 80070000h
0x1800adf08  mov     dword ptr [rsp+68h+bIgnoreCase], 1646h
0x1800adf10  jmp     loc_1800ADFC7
0x1800adf15  mov     rax, [rsi+18h]
0x1800adf19  test    rax, rax
0x1800adf1c  jnz     short loc_1800ADF39
0x1800adf1e  mov     ebx, 8000FFFFh
0x1800adf23  mov     dword ptr [rsp+68h+bIgnoreCase], 165Dh
0x1800adf2b  mov     r9d, edi
0x1800adf2e  mov     r8d, 8000FFFFh
0x1800adf34  jmp     loc_1800ADDEC
0x1800adf39  cmp     [rax], r12w
0x1800adf3d  jnz     short loc_1800ADF6F
0x1800adf3f  mov     rcx, cs:g_hPublisher
0x1800adf46  lea     rdx, EFS_TRACE_MSG_DWORD_EVENT
0x1800adf4d  mov     [rsp+68h+var_38], 1666h
0x1800adf55  lea     r9, aMatchAnyWildca; "'Match-any' wildcard DPL policy applied"
0x1800adf5c  mov     r8, rdx
0x1800adf5f  mov     [rsp+68h+var_40], edi
0x1800adf63  mov     dword ptr [rsp+68h+bIgnoreCase], r12d
0x1800adf68  call    fnEfsLogTrace1String1Dword
0x1800adf6d  jmp     short loc_1800ADFD7
0x1800adf6f  movsxd  rax, dword ptr [rsi+20h]
0x1800adf73  shr     rcx, 1
0x1800adf76  dec     rcx
0x1800adf79  cmp     rax, rcx
0x1800adf7c  ja      short loc_1800ADFDE
0x1800adf7e  mov     rcx, [rsp+68h+lpString1]; String
0x1800adf83  call    cs:__imp__wcsrev
0x1800adf89  mov     edx, [rsi+20h]; cchCount1
0x1800adf8c  mov     r9d, edx; cchCount2
0x1800adf8f  mov     r8, [rsi+18h]; lpString2
0x1800adf93  mov     rcx, [rsp+68h+lpString1]; lpString1
0x1800adf98  mov     dword ptr [rsp+68h+bIgnoreCase], 1; bIgnoreCase
0x1800adfa0  call    cs:__imp_CompareStringOrdinal
0x1800adfa6  test    eax, eax
0x1800adfa8  jnz     short loc_1800ADFD2
0x1800adfaa  call    cs:__imp_GetLastError
0x1800adfb0  mov     ebx, eax
0x1800adfb2  test    eax, eax
0x1800adfb4  jle     short loc_1800ADFBF
0x1800adfb6  movzx   ebx, ax
0x1800adfb9  or      ebx, 80070000h
0x1800adfbf  mov     dword ptr [rsp+68h+bIgnoreCase], 1688h
0x1800adfc7  mov     r9d, edi
0x1800adfca  mov     r8d, ebx
0x1800adfcd  jmp     loc_1800ADDEC
0x1800adfd2  cmp     eax, 2
0x1800adfd5  jnz     short loc_1800ADFDE
0x1800adfd7  mov     dword ptr [r14], 1
0x1800adfde  mov     rcx, [rsp+68h+lpString1]; void *
0x1800adfe3  test    rcx, rcx
0x1800adfe6  jz      short loc_1800ADFED
0x1800adfe8  call    ?DplibMemFree@@YAJPEAX@Z; DplibMemFree(void *)
0x1800adfed  mov     eax, ebx
0x1800adfef  mov     rbx, [rsp+68h+arg_10]
0x1800adff7  add     rsp, 40h
0x1800adffb  pop     r14
0x1800adffd  pop     r12
0x1800adfff  pop     rdi
0x1800ae000  pop     rsi
0x1800ae001  pop     rbp
0x1800ae002  retn
```
