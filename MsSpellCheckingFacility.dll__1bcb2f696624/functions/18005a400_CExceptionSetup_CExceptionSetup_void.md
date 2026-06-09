# CExceptionSetup::~CExceptionSetup(void)

- ea: `0x18005a400`
- end: `0x18005a68c`
- name: `??1CExceptionSetup@@QEAA@XZ`
- size: `652`
- prototype: `void __fastcall(CExceptionSetup *__hidden this)`
- caller_count: `4`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x18009cd70`
- `0x18009d110`
- `0x1800beb69`
- `0x1800bebd4`

## callees

- `0x180035dd8`
- `0x18004cdd0`
- `0x18005a400`
- `0x18005a694`
- `0x180061320`
- `0x180062314`
- `0x18009d9dc`
- `0x18009dacc`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__resetstkoflw` at `0x18005a46b`
- `api-ms-win-crt-private-l1-1-0!_o__resetstkoflw` at `0x18005a46b`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18005a64c`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18005a64c`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x18005a5da`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x18005a5da`

## pseudocode

```c
void __fastcall CExceptionSetup::~CExceptionSetup(CExceptionSetup *this)
{
  void (__fastcall *v2)(__int64, _QWORD); // rax
  int v3; // eax
  int *v4; // rcx
  __int64 v5; // rax
  wchar_t *p_Buffer; // rsi
  int v7; // edi
  __int64 v8; // rax
  int v9; // r9d
  wchar_t *v10; // rdx
  ICreateErrorInfo *pperrinfo; // [rsp+30h] [rbp-D0h] BYREF
  IErrorInfo *perrinfo; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t Buffer; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v14[236]; // [rsp+42h] [rbp-BEh] BYREF
  __int16 v15; // [rsp+12Eh] [rbp+2Eh]
  wchar_t v16[40]; // [rsp+130h] [rbp+30h] BYREF

  if ( !*((_DWORD *)this + 6) )
    goto LABEL_37;
  v2 = (void (__fastcall *)(__int64, _QWORD))*((_QWORD *)this + 2);
  if ( v2 && *((_DWORD *)this + 7) == -1073741819 )
    v2(3221225477LL, *((_QWORD *)this + 7));
  if ( *((_DWORD *)this + 6) == -1053749245 && *((_DWORD *)this + 7) == -1073741571 )
    _o__resetstkoflw();
  v3 = *((_DWORD *)this + 6);
  if ( v3 < 0 )
  {
    v4 = (int *)*((_QWORD *)this + 4);
    if ( !v4 )
      goto LABEL_13;
  }
  else
  {
    v4 = (int *)*((_QWORD *)this + 5);
    if ( !v4 )
      goto LABEL_13;
    v3 = *((_DWORD *)this + 6) & 0x7FFF;
  }
  *v4 = v3;
LABEL_13:
  v5 = *(_QWORD *)this - *(_QWORD *)&GUID_NULL.Data1;
  if ( *(_QWORD *)this == *(_QWORD *)&GUID_NULL.Data1 )
    v5 = *((_QWORD *)this + 1) - *(_QWORD *)GUID_NULL.Data4;
  if ( v5 )
  {
    Buffer = 0;
    memset_0(v14, 0, 0xEEu);
    p_Buffer = &Buffer;
    v7 = 120;
    if ( *((_DWORD *)this + 20) && *((_QWORD *)this + 8) )
    {
      if ( (int)StringCchPrintfW(&Buffer, 0x78u, L"%s(%d,%d): ") >= 0 )
      {
        v8 = -1;
        do
          ++v8;
        while ( *(_WORD *)&v14[2 * v8 - 2] );
        v7 = 120 - v8;
        p_Buffer = (wchar_t *)&v14[2 * v8 - 2];
      }
      v15 = 0;
    }
    CNLException::GetFormatMessage(*((_DWORD *)this + 6), p_Buffer, v7);
    if ( *((_DWORD *)this + 6) != -1053749245 )
      goto LABEL_33;
    StringCchCatW(&Buffer, 0x78u, L"  ");
    v9 = *((_DWORD *)this + 7);
    if ( v9 == -2147483645 )
    {
      v10 = L"Unexpected Exception Breakpoint";
      goto LABEL_32;
    }
    if ( v9 != -1073741819 )
    {
      if ( v9 == -1073741676 )
      {
        v10 = L"Integer divide by zero";
        goto LABEL_32;
      }
      if ( v9 == -1073741571 )
      {
        v10 = L"Stack overflow: probable infinite recursion";
LABEL_32:
        CMN_WcsTruncateCat(&Buffer, v10);
LABEL_33:
        if ( *((int *)this + 6) < 0 )
        {
          pperrinfo = 0;
          if ( CreateErrorInfo(&pperrinfo) >= 0 )
          {
            ((void (__fastcall *)(ICreateErrorInfo *, wchar_t *))pperrinfo->lpVtbl->SetDescription)(pperrinfo, &Buffer);
            ((void (__fastcall *)(ICreateErrorInfo *, CExceptionSetup *))pperrinfo->lpVtbl->SetGUID)(pperrinfo, this);
            perrinfo = 0;
            ((void (__fastcall *)(ICreateErrorInfo *, GUID *, IErrorInfo **))pperrinfo->lpVtbl->QueryInterface)(
              pperrinfo,
              &GUID_1cf2b120_547d_101b_8e65_08002b2bd119,
              &perrinfo);
            ((void (__fastcall *)(ICreateErrorInfo *))pperrinfo->lpVtbl->Release)(pperrinfo);
            if ( perrinfo )
            {
              SetErrorInfo(0, perrinfo);
              ((void (__fastcall *)(IErrorInfo *))perrinfo->lpVtbl->Release)(perrinfo);
            }
          }
        }
        goto LABEL_37;
      }
    }
    StringCchPrintfW(v16, 0x28u, L"Unknown %d");
    v16[39] = 0;
    v10 = v16;
    goto LABEL_32;
  }
LABEL_37:
  CFileInfo::~CFileInfo((CExceptionSetup *)((char *)this + 64));
}

```

## disassembly

```asm
0x18005a400  push    rbp
0x18005a402  push    rbx
0x18005a403  push    rsi
0x18005a404  push    rdi
0x18005a405  push    r14
0x18005a407  push    r15
0x18005a409  lea     rbp, [rsp-98h]
0x18005a411  sub     rsp, 198h
0x18005a418  mov     rax, cs:__security_cookie
0x18005a41f  xor     rax, rsp
0x18005a422  mov     [rbp+0C0h+var_40], rax
0x18005a429  mov     rbx, rcx
0x18005a42c  xor     r14d, r14d
0x18005a42f  cmp     [rcx+18h], r14d
0x18005a433  jz      loc_18005A663
0x18005a439  mov     rax, [rcx+10h]
0x18005a43d  test    rax, rax
0x18005a440  jz      short loc_18005A459
0x18005a442  cmp     dword ptr [rcx+1Ch], 0C0000005h
0x18005a449  jnz     short loc_18005A459
0x18005a44b  mov     rdx, [rcx+38h]
0x18005a44f  mov     ecx, 0C0000005h
0x18005a454  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a459  cmp     dword ptr [rbx+18h], 0C1311003h
0x18005a460  jnz     short loc_18005A471
0x18005a462  cmp     dword ptr [rbx+1Ch], 0C00000FDh
0x18005a469  jnz     short loc_18005A471
0x18005a46b  call    cs:__imp__o__resetstkoflw
0x18005a471  mov     eax, [rbx+18h]
0x18005a474  test    eax, eax
0x18005a476  js      short loc_18005A488
0x18005a478  mov     rcx, [rbx+28h]
0x18005a47c  test    rcx, rcx
0x18005a47f  jz      short loc_18005A493
0x18005a481  and     eax, 7FFFh
0x18005a486  jmp     short loc_18005A491
0x18005a488  mov     rcx, [rbx+20h]
0x18005a48c  test    rcx, rcx
0x18005a48f  jz      short loc_18005A493
0x18005a491  mov     [rcx], eax
0x18005a493  mov     rax, [rbx]
0x18005a496  sub     rax, qword ptr cs:GUID_NULL.Data1
0x18005a49d  jnz     short loc_18005A4AA
0x18005a49f  mov     rax, [rbx+8]
0x18005a4a3  sub     rax, qword ptr cs:GUID_NULL.Data4
0x18005a4aa  test    rax, rax
0x18005a4ad  jz      loc_18005A663
0x18005a4b3  mov     [rsp+1C0h+Buffer], r14w
0x18005a4b9  xor     edx, edx; Val
0x18005a4bb  mov     r8d, 0EEh; Size
0x18005a4c1  lea     rcx, [rsp+1C0h+var_17E]; void *
0x18005a4c6  call    memset_0
0x18005a4cb  lea     rsi, [rsp+1C0h+Buffer]
0x18005a4d0  mov     r15d, 78h ; 'x'
0x18005a4d6  mov     edi, r15d
0x18005a4d9  mov     ecx, [rbx+50h]
0x18005a4dc  test    ecx, ecx
0x18005a4de  jz      short loc_18005A530
0x18005a4e0  mov     r9, [rbx+40h]
0x18005a4e4  test    r9, r9
0x18005a4e7  jz      short loc_18005A530
0x18005a4e9  mov     eax, [rbx+54h]
0x18005a4ec  mov     [rsp+1C0h+var_198], eax
0x18005a4f0  mov     [rsp+1C0h+var_1A0], ecx
0x18005a4f4  lea     r8, aSDD; "%s(%d,%d): "
0x18005a4fb  mov     edx, r15d; unsigned __int64
0x18005a4fe  lea     rcx, [rsp+1C0h+Buffer]; Buffer
0x18005a503  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005a508  test    eax, eax
0x18005a50a  js      short loc_18005A52B
0x18005a50c  lea     rcx, [rsp+1C0h+Buffer]
0x18005a511  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005a515  inc     rax
0x18005a518  cmp     [rcx+rax*2], r14w
0x18005a51d  jnz     short loc_18005A515
0x18005a51f  sub     rdi, rax
0x18005a522  lea     rsi, [rsp+1C0h+Buffer]
0x18005a527  lea     rsi, [rsi+rax*2]
0x18005a52b  mov     [rbp+0C0h+var_92], r14w
0x18005a530  mov     r8d, edi; int
0x18005a533  mov     rdx, rsi; lpBuffer
0x18005a536  mov     ecx, [rbx+18h]; dwMessageId
0x18005a539  call    ?GetFormatMessage@CNLException@@SA_NJPEAGH@Z; CNLException::GetFormatMessage(long,ushort *,int)
0x18005a53e  cmp     dword ptr [rbx+18h], 0C1311003h
0x18005a545  jnz     short loc_18005A5C6
0x18005a547  lea     r8, asc_1800EAD60; "  "
0x18005a54e  mov     rdx, r15; unsigned __int64
0x18005a551  lea     rcx, [rsp+1C0h+Buffer]; unsigned __int16 *
0x18005a556  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18005a55b  mov     r9d, [rbx+1Ch]
0x18005a55f  cmp     r9d, 80000003h
0x18005a566  jz      short loc_18005A5B5
0x18005a568  cmp     r9d, 0C0000005h
0x18005a56f  jz      short loc_18005A595
0x18005a571  cmp     r9d, 0C0000094h
0x18005a578  jz      short loc_18005A58C
0x18005a57a  cmp     r9d, 0C00000FDh
0x18005a581  jnz     short loc_18005A595
0x18005a583  lea     rdx, aStackOverflowP; "Stack overflow: probable infinite recur"...
0x18005a58a  jmp     short loc_18005A5BC
0x18005a58c  lea     rdx, aIntegerDivideB; "Integer divide by zero"
0x18005a593  jmp     short loc_18005A5BC
0x18005a595  lea     r8, aUnknownD; "Unknown %d"
0x18005a59c  mov     edx, 28h ; '('; unsigned __int64
0x18005a5a1  lea     rcx, [rbp+0C0h+var_90]; Buffer
0x18005a5a5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005a5aa  mov     [rbp+0C0h+var_42], r14w
0x18005a5af  lea     rdx, [rbp+0C0h+var_90]
0x18005a5b3  jmp     short loc_18005A5BC
0x18005a5b5  lea     rdx, aUnexpectedExce; "Unexpected Exception Breakpoint"
0x18005a5bc  lea     rcx, [rsp+1C0h+Buffer]
0x18005a5c1  call    CMN_WcsTruncateCat
0x18005a5c6  cmp     [rbx+18h], r14d
0x18005a5ca  jge     loc_18005A663
0x18005a5d0  mov     [rsp+1C0h+pperrinfo], r14
0x18005a5d5  lea     rcx, [rsp+1C0h+pperrinfo]; pperrinfo
0x18005a5da  call    cs:__imp_CreateErrorInfo
0x18005a5e0  test    eax, eax
0x18005a5e2  js      short loc_18005A663
0x18005a5e4  mov     rcx, [rsp+1C0h+pperrinfo]
0x18005a5e9  mov     rax, [rcx]
0x18005a5ec  lea     rdx, [rsp+1C0h+Buffer]
0x18005a5f1  mov     rax, [rax+28h]
0x18005a5f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a5fa  mov     rcx, [rsp+1C0h+pperrinfo]
0x18005a5ff  mov     rax, [rcx]
0x18005a602  mov     rdx, rbx
0x18005a605  mov     rax, [rax+18h]
0x18005a609  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a60e  mov     [rsp+1C0h+perrinfo], r14
0x18005a613  mov     rcx, [rsp+1C0h+pperrinfo]
0x18005a618  mov     rax, [rcx]
0x18005a61b  lea     r8, [rsp+1C0h+perrinfo]
0x18005a620  lea     rdx, _GUID_1cf2b120_547d_101b_8e65_08002b2bd119
0x18005a627  mov     rax, [rax]
0x18005a62a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a62f  mov     rcx, [rsp+1C0h+pperrinfo]
0x18005a634  mov     rax, [rcx]
0x18005a637  mov     rax, [rax+10h]
0x18005a63b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a640  mov     rdx, [rsp+1C0h+perrinfo]; perrinfo
0x18005a645  test    rdx, rdx
0x18005a648  jz      short loc_18005A663
0x18005a64a  xor     ecx, ecx; dwReserved
0x18005a64c  call    cs:__imp_SetErrorInfo
0x18005a652  mov     rcx, [rsp+1C0h+perrinfo]
0x18005a657  mov     rax, [rcx]
0x18005a65a  mov     rax, [rax+10h]
0x18005a65e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a663  lea     rcx, [rbx+40h]; this
0x18005a667  call    ??1CFileInfo@@QEAA@XZ; CFileInfo::~CFileInfo(void)
0x18005a66c  nop
0x18005a66d  mov     rcx, [rbp+0C0h+var_40]
0x18005a674  xor     rcx, rsp; StackCookie
0x18005a677  call    __security_check_cookie
0x18005a67c  add     rsp, 198h
0x18005a683  pop     r15
0x18005a685  pop     r14
0x18005a687  pop     rdi
0x18005a688  pop     rsi
0x18005a689  pop     rbx
0x18005a68a  pop     rbp
0x18005a68b  retn
```
