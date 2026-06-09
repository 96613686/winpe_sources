# TsiBuildStringSid

- ea: `0x1800052e0`
- end: `0x1800053f1`
- name: `TsiBuildStringSid`
- size: `273`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004db0`

## callees

- `0x1800052e0`
- `0x180005400`
- `0x180010094`
- `0x180010208`
- `0x180014fbc`
- `0x180015068`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800053c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800053c0`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180005313`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180005313`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800053a7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800053a7`

## pseudocode

```c
__int64 __fastcall TsiBuildStringSid(void ***a1, void *a2)
{
  int v3; // ebx
  __int64 v4; // rax
  unsigned int v6; // esi
  void **v7; // rax
  void **v8; // rdi
  const wchar_t *v9; // rax
  size_t v10; // rdx
  size_t v11; // r8
  size_t v12; // rdx
  wchar_t *v13; // rcx
  size_t *v14; // r8
  signed int LastError; // eax
  size_t v17; // [rsp+20h] [rbp-38h]
  LPWSTR StringSid; // [rsp+68h] [rbp+10h] BYREF

  StringSid = 0;
  if ( !a2 || !a1 )
  {
    v3 = -2147467261;
    goto LABEL_11;
  }
  if ( ConvertSidToStringSidW(a2, &StringSid) )
  {
    v3 = -2147467259;
    v4 = -1;
    while ( StringSid[++v4] != 0 )
      ;
    v6 = 2 * v4 + 2;
    if ( 2 * (_DWORD)v4 != -2 )
    {
      v7 = (void **)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
      v8 = v7;
      if ( !v7 )
      {
        v3 = -2147024882;
        goto LABEL_11;
      }
      *((_DWORD *)v7 + 2) = v6;
      v9 = (const wchar_t *)operator new[](v6, (const struct std::nothrow_t *)&std::nothrow);
      v10 = (unsigned __int64)*((unsigned int *)v8 + 2) >> 1;
      *v8 = (void *)v9;
      v3 = StringValidateDestW(v9, v10, v11);
      if ( v3 < 0 )
      {
        if ( v12 )
          *v13 = 0;
      }
      else
      {
        v3 = StringCopyWorkerW(v13, v12, v14, StringSid, v17);
        if ( v3 >= 0 )
        {
          *a1 = v8;
          v3 = 0;
          goto LABEL_11;
        }
      }
      TsiFreeScheduleSid(v8);
    }
  }
  else
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
  }
LABEL_11:
  LocalFree(StringSid);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800052e0  push    rbx
0x1800052e2  push    rsi
0x1800052e3  push    rdi
0x1800052e4  push    r14
0x1800052e6  sub     rsp, 38h
0x1800052ea  mov     [rsp+58h+StringSid], 0
0x1800052f3  mov     rax, rdx
0x1800052f6  mov     r14, rcx
0x1800052f9  test    rdx, rdx
0x1800052fc  jz      loc_1800053EA
0x180005302  test    rcx, rcx
0x180005305  jz      loc_1800053EA
0x18000530b  lea     rdx, [rsp+58h+StringSid]; StringSid
0x180005310  mov     rcx, rax; Sid
0x180005313  call    cs:__imp_ConvertSidToStringSidW
0x180005319  test    eax, eax
0x18000531b  jz      loc_1800053C0
0x180005321  mov     rcx, [rsp+58h+StringSid]
0x180005326  mov     ebx, 80004005h
0x18000532b  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180005332  cmp     word ptr [rcx+rax*2+2], 0
0x180005338  lea     rax, [rax+1]
0x18000533c  jnz     short loc_180005332
0x18000533e  lea     esi, ds:2[rax*2]
0x180005345  test    esi, esi
0x180005347  jz      short loc_1800053A2
0x180005349  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180005350  mov     ecx, 10h; unsigned __int64
0x180005355  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000535a  mov     rdi, rax
0x18000535d  test    rax, rax
0x180005360  jz      short loc_1800053D7
0x180005362  mov     ecx, esi; unsigned __int64
0x180005364  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000536b  mov     [rax+8], esi
0x18000536e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180005373  mov     edx, [rdi+8]
0x180005376  mov     rcx, rax; pszDest
0x180005379  shr     rdx, 1; cchDest
0x18000537c  mov     [rdi], rax
0x18000537f  call    StringValidateDestW
0x180005384  mov     ebx, eax
0x180005386  test    eax, eax
0x180005388  js      short loc_1800053DE
0x18000538a  mov     r9, [rsp+58h+StringSid]; pszSrc
0x18000538f  call    StringCopyWorkerW
0x180005394  mov     ebx, eax
0x180005396  test    eax, eax
0x180005398  jns     short loc_1800053B9
0x18000539a  mov     rcx, rdi; struct _SCHEDULE_SID *
0x18000539d  call    ?TsiFreeScheduleSid@@YAJPEAU_SCHEDULE_SID@@@Z; TsiFreeScheduleSid(_SCHEDULE_SID *)
0x1800053a2  mov     rcx, [rsp+58h+StringSid]; hMem
0x1800053a7  call    cs:__imp_LocalFree
0x1800053ad  mov     eax, ebx
0x1800053af  add     rsp, 38h
0x1800053b3  pop     r14
0x1800053b5  pop     rdi
0x1800053b6  pop     rsi
0x1800053b7  pop     rbx
0x1800053b8  retn
0x1800053b9  mov     [r14], rdi
0x1800053bc  xor     ebx, ebx
0x1800053be  jmp     short loc_1800053A2
0x1800053c0  call    cs:__imp_GetLastError
0x1800053c6  mov     ebx, eax
0x1800053c8  test    eax, eax
0x1800053ca  jle     short loc_1800053A2
0x1800053cc  movzx   ebx, ax
0x1800053cf  or      ebx, 80070000h
0x1800053d5  jmp     short loc_1800053A2
0x1800053d7  mov     ebx, 8007000Eh
0x1800053dc  jmp     short loc_1800053A2
0x1800053de  test    rdx, rdx
0x1800053e1  jz      short loc_18000539A
0x1800053e3  xor     eax, eax
0x1800053e5  mov     [rcx], ax
0x1800053e8  jmp     short loc_18000539A
0x1800053ea  mov     ebx, 80004003h
0x1800053ef  jmp     short loc_1800053A2
```
