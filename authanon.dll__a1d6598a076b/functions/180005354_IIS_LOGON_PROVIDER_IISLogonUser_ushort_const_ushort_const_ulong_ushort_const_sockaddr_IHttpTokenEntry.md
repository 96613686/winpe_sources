# IIS_LOGON_PROVIDER::IISLogonUser(ushort const *,ushort const *,ulong,ushort const *,sockaddr *,IHttpTokenEntry * *)

- ea: `0x180005354`
- end: `0x180005678`
- name: `?IISLogonUser@IIS_LOGON_PROVIDER@@QEAAJPEBG0K0PEAUsockaddr@@PEAPEAVIHttpTokenEntry@@@Z`
- size: `804`
- prototype: `__int64 __fastcall(IIS_LOGON_PROVIDER *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, const unsigned __int16 *, struct sockaddr *, struct IHttpTokenEntry **)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800043b8`

## callees

- `0x180002530`
- `0x180002978`
- `0x1800041a4`
- `0x180004e6c`
- `0x180005354`
- `0x180005b46`
- `0x180005b70`
- `0x180006010`

## import_xrefs

- `msvcrt!wcschr` at `0x180005477`
- `msvcrt!wcschr` at `0x180005477`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005576`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005592`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005576`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005592`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000561c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000561c`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800053d5`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800053fd`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800053d5`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800053fd`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180005457`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000546b`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180005498`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800054b0`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800054c6`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800054de`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180005529`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180005457`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000546b`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180005498`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800054b0`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800054c6`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800054de`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180005529`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180005643`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000564d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180005643`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000564d`
- `api-ms-win-security-logon-l1-1-0!LogonUserExW` at `0x18000556c`
- `api-ms-win-security-logon-l1-1-0!LogonUserExW` at `0x18000556c`
- `SspiCli!SeciAllocateAndSetIPAddress` at `0x18000550d`
- `SspiCli!SeciAllocateAndSetIPAddress` at `0x18000550d`
- `SspiCli!SeciFreeCallContext` at `0x180005639`
- `SspiCli!SeciFreeCallContext` at `0x180005639`
- `SspiCli!LsaFreeReturnBuffer` at `0x18000562c`
- `SspiCli!LsaFreeReturnBuffer` at `0x18000562c`

## pseudocode

```c
__int64 __fastcall IIS_LOGON_PROVIDER::IISLogonUser(
        IIS_LOGON_PROVIDER *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        const unsigned __int16 *a5,
        struct sockaddr *a6,
        struct IHttpTokenEntry **a7)
{
  const unsigned __int16 *v11; // r8
  int v12; // ebx
  const wchar_t *v13; // rax
  unsigned int v14; // esi
  const WCHAR *Str; // rax
  __int64 v16; // rdx
  unsigned int i; // ebx
  const WCHAR *v18; // rax
  signed int LastError; // eax
  signed int v20; // eax
  TOKEN_ENTRY *v21; // rax
  TOKEN_ENTRY *v22; // rax
  struct IHttpTokenEntry *v23; // rdi
  int v25; // [rsp+50h] [rbp-B0h] BYREF
  int v26; // [rsp+54h] [rbp-ACh] BYREF
  DWORD pdwProfileLength; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE hObject; // [rsp+60h] [rbp-A0h] BYREF
  LPCWSTR lpszDomain; // [rsp+68h] [rbp-98h]
  unsigned __int16 *v30; // [rsp+70h] [rbp-90h]
  PVOID Buffer; // [rsp+78h] [rbp-88h] BYREF
  struct IHttpTokenEntry **v32; // [rsp+80h] [rbp-80h]
  _BYTE v33[56]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v34[64]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v35[256]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int16 v36[256]; // [rsp+300h] [rbp+200h] BYREF

  v32 = a7;
  hObject = 0;
  Buffer = 0;
  pdwProfileLength = 0;
  v30 = 0;
  memset_0(v35, 0, sizeof(v35));
  STRU::STRU((STRU *)v34, v35, 0x100u);
  memset_0(v36, 0, sizeof(v36));
  STRU::STRU((STRU *)v33, v36, 0x100u);
  v26 = 0;
  v25 = 0;
  if ( !a7 )
  {
    v12 = -2147024809;
    goto LABEL_42;
  }
  v12 = IIS_LOGON_PROVIDER::DetermineUserAndDomain(this, a2, v11, (struct STRU *)v34, (struct STRU *)v33, &v26);
  if ( v12 < 0 )
    goto LABEL_36;
  if ( v26 || !*STRU::QueryStr((STRU *)v33) || (v13 = STRU::QueryStr((STRU *)v34), !wcschr(v13, 0x40u)) )
  {
    v14 = 1;
    if ( *STRU::QueryStr((STRU *)v33) )
      Str = STRU::QueryStr((STRU *)v33);
    else
      Str = 0;
    goto LABEL_13;
  }
  v14 = 2;
  if ( *((_DWORD *)this + 641) )
  {
    Str = STRU::QueryStr((STRU *)v33);
    v30 = 0;
LABEL_13:
    lpszDomain = Str;
    goto LABEL_14;
  }
  lpszDomain = 0;
  v30 = STRU::QueryStr((STRU *)v33);
LABEL_14:
  if ( !a6 )
    goto LABEL_20;
  if ( a6->sa_family == 2 )
  {
    v16 = 16;
  }
  else
  {
    if ( a6->sa_family != 23 )
      goto LABEL_20;
    v16 = 28;
  }
  v12 = SeciAllocateAndSetIPAddress(a6, v16, &v25);
  if ( v12 >= 0 )
  {
LABEL_20:
    for ( i = 0; i < v14; ++i )
    {
      v18 = STRU::QueryStr((STRU *)v34);
      if ( LogonUserExW(v18, (&lpszDomain)[i], a3, a4, 0, &hObject, 0, &Buffer, &pdwProfileLength, 0) )
      {
        v21 = (TOKEN_ENTRY *)operator new(0x108u);
        if ( !v21 || (v22 = TOKEN_ENTRY::TOKEN_ENTRY(v21), (v23 = v22) == 0) )
        {
          v12 = -2147024888;
          goto LABEL_36;
        }
        v12 = TOKEN_ENTRY::Create(v22, hObject, a2, a3, a4, 1);
        if ( v12 < 0 )
        {
          (*(void (__fastcall **)(struct IHttpTokenEntry *))(*(_QWORD *)v23 + 16LL))(v23);
          goto LABEL_36;
        }
        *v32 = v23;
        goto LABEL_38;
      }
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      if ( LastError != -2147023570 )
        break;
    }
    v20 = GetLastError();
    v12 = v20;
    if ( v20 > 0 )
      v12 = (unsigned __int16)v20 | 0x80070000;
    if ( v12 >= 0 )
      goto LABEL_38;
  }
LABEL_36:
  if ( hObject )
    CloseHandle(hObject);
LABEL_38:
  if ( Buffer )
    LsaFreeReturnBuffer(Buffer);
  if ( v25 )
    SeciFreeCallContext();
LABEL_42:
  STRU::~STRU((STRU *)v33);
  STRU::~STRU((STRU *)v34);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180005354  push    rbp
0x180005356  push    rbx
0x180005357  push    rsi
0x180005358  push    rdi
0x180005359  push    r12
0x18000535b  push    r13
0x18000535d  push    r14
0x18000535f  push    r15
0x180005361  lea     rbp, [rsp-418h]
0x180005369  sub     rsp, 518h
0x180005370  mov     rax, cs:__security_cookie
0x180005377  xor     rax, rsp
0x18000537a  mov     [rbp+450h+var_50], rax
0x180005381  mov     rbx, [rbp+450h+arg_30]
0x180005388  xor     eax, eax
0x18000538a  mov     rdi, [rbp+450h+arg_28]
0x180005391  mov     r12, r8
0x180005394  mov     r15, rdx
0x180005397  mov     [rbp+450h+var_4D0], rbx
0x18000539b  mov     r14, rcx
0x18000539e  mov     [rsp+550h+hObject], rax
0x1800053a3  xor     edx, edx; Val
0x1800053a5  mov     [rsp+550h+Buffer], rax
0x1800053aa  mov     r8d, 200h; Size
0x1800053b0  mov     [rsp+550h+var_4F8], eax
0x1800053b4  lea     rcx, [rbp+450h+var_450]; void *
0x1800053b8  mov     [rsp+550h+var_4E0], rax
0x1800053bd  mov     r13d, r9d
0x1800053c0  call    memset_0
0x1800053c5  mov     esi, 100h
0x1800053ca  lea     rdx, [rbp+450h+var_450]
0x1800053ce  mov     r8d, esi
0x1800053d1  lea     rcx, [rbp+450h+var_490]
0x1800053d5  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800053db  xor     edx, edx; Val
0x1800053dd  lea     rcx, [rbp+450h+var_250]; void *
0x1800053e4  mov     r8d, 200h; Size
0x1800053ea  call    memset_0
0x1800053ef  mov     r8d, esi
0x1800053f2  lea     rdx, [rbp+450h+var_250]
0x1800053f9  lea     rcx, [rbp+450h+var_4C8]
0x1800053fd  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180005403  xor     esi, esi
0x180005405  mov     [rsp+550h+var_4FC], esi
0x180005409  mov     [rsp+550h+var_500], esi
0x18000540d  test    rbx, rbx
0x180005410  jnz     short loc_18000541C
0x180005412  mov     ebx, 80070057h
0x180005417  jmp     loc_18000563F
0x18000541c  lea     rax, [rsp+550h+var_4FC]
0x180005421  mov     rdx, r15; unsigned __int16 *
0x180005424  mov     [rsp+550h+phToken], rax; int *
0x180005429  lea     r9, [rbp+450h+var_490]; struct STRU *
0x18000542d  lea     rax, [rbp+450h+var_4C8]
0x180005431  mov     rcx, r14; this
0x180005434  mov     qword ptr [rsp+550h+dwLogonProvider], rax; struct STRU *
0x180005439  call    ?DetermineUserAndDomain@IIS_LOGON_PROVIDER@@AEAAJPEBG0PEAVSTRU@@1PEAH@Z; IIS_LOGON_PROVIDER::DetermineUserAndDomain(ushort const *,ushort const *,STRU *,STRU *,int *)
0x18000543e  mov     ebx, eax
0x180005440  test    eax, eax
0x180005442  js      loc_18000560F
0x180005448  mov     ebx, 2
0x18000544d  cmp     [rsp+550h+var_4FC], esi
0x180005451  jnz     short loc_1800054BD
0x180005453  lea     rcx, [rbp+450h+var_4C8]
0x180005457  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000545d  cmp     [rax], si
0x180005460  jz      short loc_1800054BD
0x180005462  lea     rcx, [rbp+450h+var_490]
0x180005466  mov     ebx, 40h ; '@'
0x18000546b  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180005471  mov     rcx, rax; Str
0x180005474  movzx   edx, bx; Ch
0x180005477  call    cs:__imp_wcschr
0x18000547d  mov     ebx, 2
0x180005482  test    rax, rax
0x180005485  jz      short loc_1800054BD
0x180005487  xor     eax, eax
0x180005489  lea     rcx, [rbp+450h+var_4C8]
0x18000548d  mov     esi, ebx
0x18000548f  cmp     [r14+0A04h], eax
0x180005496  jz      short loc_1800054A8
0x180005498  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000549e  xor     r14d, r14d
0x1800054a1  mov     [rsp+550h+var_4E0], r14
0x1800054a6  jmp     short loc_1800054E4
0x1800054a8  xor     r14d, r14d
0x1800054ab  mov     [rsp+550h+lpszDomain], r14
0x1800054b0  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800054b6  mov     [rsp+550h+var_4E0], rax
0x1800054bb  jmp     short loc_1800054E9
0x1800054bd  lea     rcx, [rbp+450h+var_4C8]
0x1800054c1  mov     esi, 1
0x1800054c6  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800054cc  xor     r14d, r14d
0x1800054cf  cmp     [rax], r14w
0x1800054d3  jnz     short loc_1800054DA
0x1800054d5  mov     eax, r14d
0x1800054d8  jmp     short loc_1800054E4
0x1800054da  lea     rcx, [rbp+450h+var_4C8]
0x1800054de  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800054e4  mov     [rsp+550h+lpszDomain], rax
0x1800054e9  test    rdi, rdi
0x1800054ec  jz      short loc_18000551D
0x1800054ee  cmp     [rdi], bx
0x1800054f1  jnz     short loc_1800054FA
0x1800054f3  mov     edx, 10h
0x1800054f8  jmp     short loc_180005505
0x1800054fa  cmp     word ptr [rdi], 17h
0x1800054fe  jnz     short loc_18000551D
0x180005500  mov     edx, 1Ch
0x180005505  lea     r8, [rsp+550h+var_500]
0x18000550a  mov     rcx, rdi
0x18000550d  call    cs:__imp_SeciAllocateAndSetIPAddress
0x180005513  mov     ebx, eax
0x180005515  test    eax, eax
0x180005517  js      loc_180005612
0x18000551d  mov     ebx, r14d
0x180005520  mov     edi, 80070000h
0x180005525  lea     rcx, [rbp+450h+var_490]
0x180005529  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000552f  mov     [rsp+550h+pQuotaLimits], r14; pQuotaLimits
0x180005534  lea     rcx, [rsp+550h+var_4F8]
0x180005539  mov     [rsp+550h+pdwProfileLength], rcx; pdwProfileLength
0x18000553e  mov     r9d, r13d; dwLogonType
0x180005541  lea     rcx, [rsp+550h+Buffer]
0x180005546  mov     edx, ebx
0x180005548  mov     [rsp+550h+ppProfileBuffer], rcx; ppProfileBuffer
0x18000554d  mov     r8, r12; lpszPassword
0x180005550  lea     rcx, [rsp+550h+hObject]
0x180005555  mov     [rsp+550h+ppLogonSid], r14; ppLogonSid
0x18000555a  mov     [rsp+550h+phToken], rcx; phToken
0x18000555f  mov     rcx, rax; lpszUsername
0x180005562  mov     rdx, [rsp+rdx*8+550h+lpszDomain]; lpszDomain
0x180005567  mov     [rsp+550h+dwLogonProvider], r14d; dwLogonProvider
0x18000556c  call    cs:__imp_LogonUserExW
0x180005572  test    eax, eax
0x180005574  jnz     short loc_1800055A9
0x180005576  call    cs:__imp_GetLastError
0x18000557c  test    eax, eax
0x18000557e  jle     short loc_180005585
0x180005580  movzx   eax, ax
0x180005583  or      eax, edi
0x180005585  cmp     eax, 8007052Eh
0x18000558a  jnz     short loc_180005592
0x18000558c  inc     ebx
0x18000558e  cmp     ebx, esi
0x180005590  jb      short loc_180005525
0x180005592  call    cs:__imp_GetLastError
0x180005598  mov     ebx, eax
0x18000559a  test    eax, eax
0x18000559c  jle     short loc_1800055A3
0x18000559e  movzx   ebx, ax
0x1800055a1  or      ebx, edi
0x1800055a3  test    ebx, ebx
0x1800055a5  jns     short loc_180005622
0x1800055a7  jmp     short loc_180005612
0x1800055a9  mov     ecx, 108h; Size
0x1800055ae  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800055b3  test    rax, rax
0x1800055b6  jz      short loc_180005608
0x1800055b8  mov     rcx, rax; this
0x1800055bb  call    ??0TOKEN_ENTRY@@QEAA@XZ; TOKEN_ENTRY::TOKEN_ENTRY(void)
0x1800055c0  mov     rdi, rax
0x1800055c3  test    rax, rax
0x1800055c6  jz      short loc_180005608
0x1800055c8  mov     rdx, [rsp+550h+hObject]; void *
0x1800055cd  mov     r9, r12; unsigned __int16 *
0x1800055d0  mov     dword ptr [rsp+550h+phToken], 1; int
0x1800055d8  mov     r8, r15; unsigned __int16 *
0x1800055db  mov     rcx, rax; this
0x1800055de  mov     [rsp+550h+dwLogonProvider], r13d; unsigned int
0x1800055e3  call    ?Create@TOKEN_ENTRY@@QEAAJPEAXPEBG1KH@Z; TOKEN_ENTRY::Create(void *,ushort const *,ushort const *,ulong,int)
0x1800055e8  mov     ebx, eax
0x1800055ea  test    eax, eax
0x1800055ec  jns     short loc_1800055FF
0x1800055ee  mov     rax, [rdi]
0x1800055f1  mov     rcx, rdi
0x1800055f4  mov     rax, [rax+10h]
0x1800055f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055fd  jmp     short loc_180005612
0x1800055ff  mov     rax, [rbp+450h+var_4D0]
0x180005603  mov     [rax], rdi
0x180005606  jmp     short loc_180005622
0x180005608  mov     ebx, 80070008h
0x18000560d  jmp     short loc_180005612
0x18000560f  xor     r14d, r14d
0x180005612  mov     rcx, [rsp+550h+hObject]; hObject
0x180005617  test    rcx, rcx
0x18000561a  jz      short loc_180005622
0x18000561c  call    cs:__imp_CloseHandle
0x180005622  mov     rcx, [rsp+550h+Buffer]; Buffer
0x180005627  test    rcx, rcx
0x18000562a  jz      short loc_180005632
0x18000562c  call    cs:__imp_LsaFreeReturnBuffer
0x180005632  cmp     [rsp+550h+var_500], r14d
0x180005637  jz      short loc_18000563F
0x180005639  call    cs:__imp_SeciFreeCallContext
0x18000563f  lea     rcx, [rbp+450h+var_4C8]
0x180005643  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180005649  lea     rcx, [rbp+450h+var_490]
0x18000564d  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180005653  mov     eax, ebx
0x180005655  mov     rcx, [rbp+450h+var_50]
0x18000565c  xor     rcx, rsp; StackCookie
0x18000565f  call    __security_check_cookie
0x180005664  add     rsp, 518h
0x18000566b  pop     r15
0x18000566d  pop     r14
0x18000566f  pop     r13
0x180005671  pop     r12
0x180005673  pop     rdi
0x180005674  pop     rsi
0x180005675  pop     rbx
0x180005676  pop     rbp
0x180005677  retn
```
