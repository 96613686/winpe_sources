# CExceptionSetup::~CExceptionSetup(void)

- ea: `0x18003c174`
- end: `0x18003c41e`
- name: `??1CExceptionSetup@@QEAA@XZ`
- size: `682`
- prototype: `void __fastcall(CExceptionSetup *__hidden this)`
- caller_count: `4`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x180034d20`
- `0x18006c470`
- `0x1800a2748`
- `0x1800ae0a6`

## callees

- `0x180016258`
- `0x180017858`
- `0x18003c174`
- `0x18003c424`
- `0x18005d838`
- `0x18005d9f4`
- `0x18009e2c2`
- `0x18009e300`
- `0x1800b0010`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x18003c1d7`
- `msvcrt!_resetstkoflw` at `0x18003c1d7`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18003c1b2`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18003c1b2`
- `OLEAUT32!__imp_SysAllocString` at `0x18003c375`
- `OLEAUT32!__imp_SysAllocString` at `0x18003c375`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18003c3dd`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18003c3dd`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x18003c356`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x18003c356`

## string_xrefs

- `0x18003c328`: `Access Violation`

## pseudocode

```c
void __fastcall CExceptionSetup::~CExceptionSetup(CExceptionSetup *this)
{
  int v2; // eax
  int *v3; // rcx
  __int64 v4; // rax
  WCHAR *p_psz; // rsi
  int v6; // ebx
  __int64 v7; // rax
  int v8; // r9d
  unsigned __int16 *v9; // rdx
  HRESULT (__stdcall *SetDescription)(ICreateErrorInfo *, LPOLESTR); // rbx
  BSTR v11; // rax
  ICreateErrorInfo *pperrinfo; // [rsp+30h] [rbp-D0h] BYREF
  IErrorInfo *perrinfo[3]; // [rsp+38h] [rbp-C8h] BYREF
  OLECHAR psz; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v15[236]; // [rsp+52h] [rbp-AEh] BYREF
  __int16 v16; // [rsp+13Eh] [rbp+3Eh]
  unsigned __int16 v17[40]; // [rsp+140h] [rbp+40h] BYREF

  perrinfo[1] = (IErrorInfo *)-2LL;
  perrinfo[2] = (IErrorInfo *)this;
  _set_se_translator(*((void (**)(unsigned int, struct _EXCEPTION_POINTERS *))this + 2));
  if ( !*((_DWORD *)this + 6) )
    goto LABEL_35;
  if ( *((_DWORD *)this + 6) == -1053749245 && *((_DWORD *)this + 7) == -1073741571 )
    _resetstkoflw();
  v2 = *((_DWORD *)this + 6);
  if ( v2 < 0 )
  {
    v3 = (int *)*((_QWORD *)this + 4);
    if ( v3 )
      goto LABEL_9;
  }
  else
  {
    v3 = (int *)*((_QWORD *)this + 5);
    if ( v3 )
    {
      v2 = *((_DWORD *)this + 6) & 0x7FFF;
LABEL_9:
      *v3 = v2;
    }
  }
  v4 = *(_QWORD *)this - *(_QWORD *)&GUID_NULL.Data1;
  if ( *(_QWORD *)this == *(_QWORD *)&GUID_NULL.Data1 )
    v4 = *((_QWORD *)this + 1) - *(_QWORD *)GUID_NULL.Data4;
  if ( v4 )
  {
    psz = 0;
    memset_0(v15, 0, 0xEEu);
    p_psz = &psz;
    v6 = 120;
    if ( *((_DWORD *)this + 18) && *((_QWORD *)this + 7) )
    {
      if ( StringCchPrintfW(&psz, 0x78u, L"%s(%d,%d): ") >= 0 )
      {
        v7 = -1;
        do
          ++v7;
        while ( *(_WORD *)&v15[2 * v7 - 2] );
        v6 = 120 - v7;
        p_psz = (WCHAR *)&v15[2 * v7 - 2];
      }
      v16 = 0;
    }
    CNLException::GetFormatMessage(*((_DWORD *)this + 6), p_psz, v6);
    if ( *((_DWORD *)this + 6) == -1053749245 )
    {
      StringCchCatW(&psz, 0x78u, L"  ");
      v8 = *((_DWORD *)this + 7);
      switch ( v8 )
      {
        case -2147483645:
          v9 = L"Unexpected Exception Breakpoint";
          break;
        case -1073741819:
          v9 = L"Access Violation";
          break;
        case -1073741676:
          v9 = L"Integer divide by zero";
          break;
        case -1073741571:
          v9 = L"Stack overflow: probable infinite recursion";
          break;
        default:
          StringCchPrintfW(v17, 0x28u, L"Unknown %d");
          v17[39] = 0;
          v9 = v17;
          break;
      }
      CMN_WcsTruncateCat(&psz, v9);
    }
    if ( *((int *)this + 6) < 0 )
    {
      pperrinfo = 0;
      if ( CreateErrorInfo(&pperrinfo) >= 0 )
      {
        SetDescription = pperrinfo->lpVtbl->SetDescription;
        v11 = SysAllocString(&psz);
        ((void (__fastcall *)(ICreateErrorInfo *, BSTR))SetDescription)(pperrinfo, v11);
        ((void (__fastcall *)(ICreateErrorInfo *, CExceptionSetup *))pperrinfo->lpVtbl->SetGUID)(pperrinfo, this);
        perrinfo[0] = 0;
        ((void (__fastcall *)(ICreateErrorInfo *, GUID *, IErrorInfo **))pperrinfo->lpVtbl->QueryInterface)(
          pperrinfo,
          &IID_IErrorInfo,
          perrinfo);
        ((void (__fastcall *)(ICreateErrorInfo *))pperrinfo->lpVtbl->Release)(pperrinfo);
        if ( perrinfo[0] )
        {
          SetErrorInfo(0, perrinfo[0]);
          ((void (__fastcall *)(IErrorInfo *))perrinfo[0]->lpVtbl->Release)(perrinfo[0]);
        }
      }
    }
  }
LABEL_35:
  CFileInfo::~CFileInfo((CExceptionSetup *)((char *)this + 56));
}

```

## disassembly

```asm
0x18003c174  push    rbp
0x18003c176  push    rbx
0x18003c177  push    rsi
0x18003c178  push    rdi
0x18003c179  push    r14
0x18003c17b  push    r15
0x18003c17d  lea     rbp, [rsp-0A8h]
0x18003c185  sub     rsp, 1A8h
0x18003c18c  mov     [rsp+1D0h+var_190], 0FFFFFFFFFFFFFFFEh
0x18003c195  mov     rax, cs:__security_cookie
0x18003c19c  xor     rax, rsp
0x18003c19f  mov     [rbp+0D0h+var_40], rax
0x18003c1a6  mov     rdi, rcx
0x18003c1a9  mov     [rsp+1D0h+var_188], rcx
0x18003c1ae  mov     rcx, [rcx+10h]
0x18003c1b2  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x18003c1b8  xor     r14d, r14d
0x18003c1bb  cmp     [rdi+18h], r14d
0x18003c1bf  jz      loc_18003C3F5
0x18003c1c5  cmp     dword ptr [rdi+18h], 0C1311003h
0x18003c1cc  jnz     short loc_18003C1DD
0x18003c1ce  cmp     dword ptr [rdi+1Ch], 0C00000FDh
0x18003c1d5  jnz     short loc_18003C1DD
0x18003c1d7  call    cs:__imp__resetstkoflw
0x18003c1dd  mov     eax, [rdi+18h]
0x18003c1e0  test    eax, eax
0x18003c1e2  js      short loc_18003C1F4
0x18003c1e4  mov     rcx, [rdi+28h]
0x18003c1e8  test    rcx, rcx
0x18003c1eb  jz      short loc_18003C1FF
0x18003c1ed  and     eax, 7FFFh
0x18003c1f2  jmp     short loc_18003C1FD
0x18003c1f4  mov     rcx, [rdi+20h]
0x18003c1f8  test    rcx, rcx
0x18003c1fb  jz      short loc_18003C1FF
0x18003c1fd  mov     [rcx], eax
0x18003c1ff  mov     rax, [rdi]
0x18003c202  sub     rax, qword ptr cs:GUID_NULL.Data1
0x18003c209  jnz     short loc_18003C216
0x18003c20b  mov     rax, [rdi+8]
0x18003c20f  sub     rax, qword ptr cs:GUID_NULL.Data4
0x18003c216  test    rax, rax
0x18003c219  jz      loc_18003C3F5
0x18003c21f  mov     [rsp+1D0h+psz], r14w
0x18003c225  xor     edx, edx; Val
0x18003c227  mov     r8d, 0EEh; Size
0x18003c22d  lea     rcx, [rsp+1D0h+var_17E]; void *
0x18003c232  call    memset_0
0x18003c237  lea     rsi, [rsp+1D0h+psz]
0x18003c23c  mov     r15d, 78h ; 'x'
0x18003c242  mov     ebx, r15d
0x18003c245  mov     ecx, [rdi+48h]
0x18003c248  test    ecx, ecx
0x18003c24a  jz      short loc_18003C29C
0x18003c24c  mov     r9, [rdi+38h]
0x18003c250  test    r9, r9
0x18003c253  jz      short loc_18003C29C
0x18003c255  mov     eax, [rdi+4Ch]
0x18003c258  mov     [rsp+1D0h+var_1A8], eax
0x18003c25c  mov     [rsp+1D0h+var_1B0], ecx
0x18003c260  lea     r8, aSDD; "%s(%d,%d): "
0x18003c267  mov     edx, r15d; unsigned __int64
0x18003c26a  lea     rcx, [rsp+1D0h+psz]; unsigned __int16 *
0x18003c26f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003c274  test    eax, eax
0x18003c276  js      short loc_18003C297
0x18003c278  lea     rcx, [rsp+1D0h+psz]
0x18003c27d  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003c281  inc     rax
0x18003c284  cmp     [rcx+rax*2], r14w
0x18003c289  jnz     short loc_18003C281
0x18003c28b  sub     rbx, rax
0x18003c28e  lea     rsi, [rsp+1D0h+psz]
0x18003c293  lea     rsi, [rsi+rax*2]
0x18003c297  mov     [rbp+0D0h+var_92], r14w
0x18003c29c  mov     r8d, ebx; int
0x18003c29f  mov     rdx, rsi; lpBuffer
0x18003c2a2  mov     ecx, [rdi+18h]; dwMessageId
0x18003c2a5  call    ?GetFormatMessage@CNLException@@SA_NJPEAGH@Z; CNLException::GetFormatMessage(long,ushort *,int)
0x18003c2aa  cmp     dword ptr [rdi+18h], 0C1311003h
0x18003c2b1  jnz     loc_18003C342
0x18003c2b7  lea     r8, asc_1800C05E0; "  "
0x18003c2be  mov     rdx, r15; unsigned __int64
0x18003c2c1  lea     rcx, [rsp+1D0h+psz]; unsigned __int16 *
0x18003c2c6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003c2cb  mov     r9d, [rdi+1Ch]
0x18003c2cf  cmp     r9d, 80000003h
0x18003c2d6  jz      short loc_18003C331
0x18003c2d8  cmp     r9d, 0C0000005h
0x18003c2df  jz      short loc_18003C328
0x18003c2e1  cmp     r9d, 0C0000094h
0x18003c2e8  jz      short loc_18003C31F
0x18003c2ea  cmp     r9d, 0C00000FDh
0x18003c2f1  jz      short loc_18003C316
0x18003c2f3  lea     r8, aUnknownD; "Unknown %d"
0x18003c2fa  mov     edx, 28h ; '('; unsigned __int64
0x18003c2ff  lea     rcx, [rbp+0D0h+var_90]; unsigned __int16 *
0x18003c303  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003c308  mov     [rbp+0D0h+var_42], r14w
0x18003c310  lea     rdx, [rbp+0D0h+var_90]
0x18003c314  jmp     short loc_18003C338
0x18003c316  lea     rdx, aStackOverflowP; "Stack overflow: probable infinite recur"...
0x18003c31d  jmp     short loc_18003C338
0x18003c31f  lea     rdx, aIntegerDivideB; "Integer divide by zero"
0x18003c326  jmp     short loc_18003C338
0x18003c328  lea     rdx, aAccessViolatio; "Access Violation"
0x18003c32f  jmp     short loc_18003C338
0x18003c331  lea     rdx, aUnexpectedExce; "Unexpected Exception Breakpoint"
0x18003c338  lea     rcx, [rsp+1D0h+psz]
0x18003c33d  call    CMN_WcsTruncateCat
0x18003c342  cmp     [rdi+18h], r14d
0x18003c346  jge     loc_18003C3F5
0x18003c34c  mov     [rsp+1D0h+pperrinfo], r14
0x18003c351  lea     rcx, [rsp+1D0h+pperrinfo]; pperrinfo
0x18003c356  call    cs:__imp_CreateErrorInfo
0x18003c35c  test    eax, eax
0x18003c35e  js      loc_18003C3F5
0x18003c364  mov     rax, [rsp+1D0h+pperrinfo]
0x18003c369  mov     rcx, [rax]
0x18003c36c  mov     rbx, [rcx+28h]
0x18003c370  lea     rcx, [rsp+1D0h+psz]; psz
0x18003c375  call    cs:__imp_SysAllocString
0x18003c37b  mov     rdx, rax
0x18003c37e  mov     rcx, [rsp+1D0h+pperrinfo]
0x18003c383  mov     rax, rbx
0x18003c386  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c38b  mov     rcx, [rsp+1D0h+pperrinfo]
0x18003c390  mov     rax, [rcx]
0x18003c393  mov     rdx, rdi
0x18003c396  mov     rax, [rax+18h]
0x18003c39a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c39f  mov     [rsp+1D0h+perrinfo], r14
0x18003c3a4  mov     rcx, [rsp+1D0h+pperrinfo]
0x18003c3a9  mov     rax, [rcx]
0x18003c3ac  lea     r8, [rsp+1D0h+perrinfo]
0x18003c3b1  lea     rdx, IID_IErrorInfo
0x18003c3b8  mov     rax, [rax]
0x18003c3bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c3c0  mov     rcx, [rsp+1D0h+pperrinfo]
0x18003c3c5  mov     rax, [rcx]
0x18003c3c8  mov     rax, [rax+10h]
0x18003c3cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c3d1  mov     rdx, [rsp+1D0h+perrinfo]; perrinfo
0x18003c3d6  test    rdx, rdx
0x18003c3d9  jz      short loc_18003C3F5
0x18003c3db  xor     ecx, ecx; dwReserved
0x18003c3dd  call    cs:__imp_SetErrorInfo
0x18003c3e3  mov     rcx, [rsp+1D0h+perrinfo]
0x18003c3e8  mov     rax, [rcx]
0x18003c3eb  mov     rax, [rax+10h]
0x18003c3ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c3f4  nop
0x18003c3f5  lea     rcx, [rdi+38h]; this
0x18003c3f9  call    ??1CFileInfo@@QEAA@XZ; CFileInfo::~CFileInfo(void)
0x18003c3fe  nop
0x18003c3ff  mov     rcx, [rbp+0D0h+var_40]
0x18003c406  xor     rcx, rsp; StackCookie
0x18003c409  call    __security_check_cookie
0x18003c40e  add     rsp, 1A8h
0x18003c415  pop     r15
0x18003c417  pop     r14
0x18003c419  pop     rdi
0x18003c41a  pop     rsi
0x18003c41b  pop     rbx
0x18003c41c  pop     rbp
0x18003c41d  retn
```
