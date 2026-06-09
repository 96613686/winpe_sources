# SetHttpSysSSLData(addrinfoW *,SSL_DATA *,ABO_NODE *,ushort const *)

- ea: `0x180028f20`
- end: `0x18002910a`
- name: `?SetHttpSysSSLData@@YAJPEAUaddrinfoW@@PEAUSSL_DATA@@PEAVABO_NODE@@PEBG@Z`
- size: `490`
- prototype: `__int64 __fastcall(struct addrinfoW *, struct SSL_DATA *, struct ABO_NODE *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180016200`
- `0x1800165d0`

## callees

- `0x180001f90`
- `0x18000341a`
- `0x180003460`
- `0x1800278cc`
- `0x180028f20`

## import_xrefs

- `HTTPAPI!HttpTerminate` at `0x1800290db`
- `HTTPAPI!HttpTerminate` at `0x1800290db`
- `HTTPAPI!HttpSetServiceConfiguration` at `0x1800290ab`
- `HTTPAPI!HttpSetServiceConfiguration` at `0x1800290ab`
- `HTTPAPI!HttpInitialize` at `0x180028f88`
- `HTTPAPI!HttpInitialize` at `0x180028f88`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180028ff7`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180028ff7`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180029004`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002902d`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002903e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180029004`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002902d`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002903e`

## pseudocode

```c
__int64 __fastcall SetHttpSysSSLData(
        struct addrinfoW *a1,
        struct SSL_DATA *a2,
        struct ABO_NODE *a3,
        const unsigned __int16 *a4)
{
  signed int v8; // eax
  unsigned int SSLProperties; // ebx
  int v10; // edi
  int v11; // eax
  bool v12; // zf
  BOOL v13; // ebx
  signed int v14; // eax
  struct sockaddr *pConfigInformation; // [rsp+30h] [rbp-59h] BYREF
  int v17; // [rsp+38h] [rbp-51h] BYREF
  void *Ptr; // [rsp+40h] [rbp-49h]
  __int128 v19; // [rsp+48h] [rbp-41h]
  unsigned __int16 *Str; // [rsp+58h] [rbp-31h]
  int v21; // [rsp+60h] [rbp-29h]
  int v22; // [rsp+64h] [rbp-25h]
  int v23; // [rsp+68h] [rbp-21h]
  unsigned __int64 v24; // [rsp+70h] [rbp-19h]
  unsigned __int64 v25; // [rsp+78h] [rbp-11h]
  int v26; // [rsp+80h] [rbp-9h]

  pConfigInformation = 0;
  memset_0(&v17, 0, 0x50u);
  if ( a1 && a2 )
  {
    v8 = HttpInitialize(g_Version, 2u, 0);
    SSLProperties = v8;
    if ( v8 > 0 )
      SSLProperties = (unsigned __int16)v8 | 0x80070000;
    if ( (SSLProperties & 0x80000000) == 0 )
    {
      v10 = -(*((_DWORD *)a2 + 56) != 0);
      pConfigInformation = a1->ai_addr;
      v11 = *((_DWORD *)a2 + 59);
      v12 = *((_DWORD *)a2 + 55) == 0;
      v19 = xmmword_180034F38;
      v13 = !v12;
      v17 = v11;
      Ptr = BUFFER::QueryPtr((struct SSL_DATA *)((char *)a2 + 56));
      Str = STRU::QueryStr(a2);
      v21 = *((_DWORD *)a2 + 54);
      v22 = *((_DWORD *)a2 + 57);
      v23 = *((_DWORD *)a2 + 58);
      v24 = (unsigned __int64)STRU::QueryStr((struct SSL_DATA *)((char *)a2 + 104));
      v25 = (unsigned __int64)STRU::QueryStr((struct SSL_DATA *)((char *)a2 + 160));
      v26 = v13 | v10 & 2;
      if ( v24 )
        v24 &= -(__int64)(*(_WORD *)v24 != 0);
      if ( v25 )
        v25 &= -(__int64)(*(_WORD *)v25 != 0);
      v14 = HttpSetServiceConfiguration(0, HttpServiceConfigSSLCertInfo, &pConfigInformation, 0x58u, 0);
      SSLProperties = v14;
      if ( v14 == 183 )
      {
        SSLProperties = GenerateSSLProperties(a3, a4);
      }
      else if ( v14 > 0 )
      {
        SSLProperties = (unsigned __int16)v14 | 0x80070000;
      }
      HttpTerminate(2u, 0);
    }
    else
    {
      ABO_MAPPER_LOG::WriteLogEntry(g_pAboLog, L"HttpInitialize failed err=%X\n", SSLProperties);
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return SSLProperties;
}

```

## disassembly

```asm
0x180028f20  push    rbp
0x180028f22  push    rbx
0x180028f23  push    rsi
0x180028f24  push    rdi
0x180028f25  push    r12
0x180028f27  push    r13
0x180028f29  push    r14
0x180028f2b  push    r15
0x180028f2d  lea     rbp, [rsp-1Fh]
0x180028f32  sub     rsp, 0A8h
0x180028f39  mov     rax, cs:__security_cookie
0x180028f40  xor     rax, rsp
0x180028f43  mov     [rbp+57h+var_50], rax
0x180028f47  xor     r13d, r13d
0x180028f4a  mov     r15, r8
0x180028f4d  mov     rsi, rdx
0x180028f50  mov     [rbp+57h+pConfigInformation], r13
0x180028f54  mov     r14, rcx
0x180028f57  xor     edx, edx; Val
0x180028f59  lea     rcx, [rbp+57h+var_A8]; void *
0x180028f5d  mov     r12, r9
0x180028f60  lea     r8d, [r13+50h]; Size
0x180028f64  call    memset_0
0x180028f69  test    r14, r14
0x180028f6c  jz      loc_1800290E3
0x180028f72  test    rsi, rsi
0x180028f75  jz      loc_1800290E3
0x180028f7b  mov     ecx, dword ptr cs:?g_Version@@3U_HTTPAPI_VERSION@@A.HttpApiMajorVersion; Version
0x180028f81  lea     edx, [r13+2]; Flags
0x180028f85  xor     r8d, r8d; pReserved
0x180028f88  call    cs:__imp_HttpInitialize
0x180028f8e  mov     ebx, eax
0x180028f90  test    eax, eax
0x180028f92  jle     short loc_180028F9D
0x180028f94  movzx   ebx, ax
0x180028f97  or      ebx, 80070000h
0x180028f9d  test    ebx, ebx
0x180028f9f  jns     short loc_180028FBC
0x180028fa1  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x180028fa8  lea     rdx, aHttpinitialize; "HttpInitialize failed err=%X\n"
0x180028faf  mov     r8d, ebx
0x180028fb2  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x180028fb7  jmp     loc_1800290E8
0x180028fbc  mov     eax, [rsi+0E0h]
0x180028fc2  lea     rcx, [rsi+38h]
0x180028fc6  movups  xmm0, cs:xmmword_180034F38
0x180028fcd  neg     eax
0x180028fcf  mov     ebx, r13d
0x180028fd2  mov     rax, [r14+20h]
0x180028fd6  sbb     edi, edi
0x180028fd8  mov     [rbp+57h+pConfigInformation], rax
0x180028fdc  mov     eax, [rsi+0ECh]
0x180028fe2  and     edi, 2
0x180028fe5  cmp     [rsi+0DCh], r13d
0x180028fec  movdqu  [rbp+57h+var_98], xmm0
0x180028ff1  setnz   bl
0x180028ff4  mov     [rbp+57h+var_A8], eax
0x180028ff7  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180028ffd  mov     rcx, rsi
0x180029000  mov     [rbp+57h+var_A0], rax
0x180029004  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18002900a  mov     [rbp+57h+var_88], rax
0x18002900e  lea     rcx, [rsi+68h]
0x180029012  mov     eax, [rsi+0D8h]
0x180029018  mov     [rbp+57h+var_80], eax
0x18002901b  mov     eax, [rsi+0E4h]
0x180029021  mov     [rbp+57h+var_7C], eax
0x180029024  mov     eax, [rsi+0E8h]
0x18002902a  mov     [rbp+57h+var_78], eax
0x18002902d  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180029033  lea     rcx, [rsi+0A0h]
0x18002903a  mov     [rbp+57h+var_70], rax
0x18002903e  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180029044  mov     rdx, [rbp+57h+var_70]
0x180029048  or      edi, ebx
0x18002904a  mov     [rbp+57h+var_68], rax
0x18002904e  mov     rcx, rax
0x180029051  mov     [rbp+57h+var_60], edi
0x180029054  test    rdx, rdx
0x180029057  jz      short loc_180029075
0x180029059  cmp     [rdx], r13w
0x18002905d  jnz     short loc_180029064
0x18002905f  mov     eax, r13d
0x180029062  jmp     short loc_180029069
0x180029064  sbb     eax, eax
0x180029066  or      eax, 1
0x180029069  neg     eax
0x18002906b  sbb     rax, rax
0x18002906e  and     rax, rdx
0x180029071  mov     [rbp+57h+var_70], rax
0x180029075  test    rcx, rcx
0x180029078  jz      short loc_180029096
0x18002907a  cmp     [rcx], r13w
0x18002907e  jnz     short loc_180029085
0x180029080  mov     eax, r13d
0x180029083  jmp     short loc_18002908A
0x180029085  sbb     eax, eax
0x180029087  or      eax, 1
0x18002908a  neg     eax
0x18002908c  sbb     rax, rax
0x18002908f  and     rax, rcx
0x180029092  mov     [rbp+57h+var_68], rax
0x180029096  mov     r9d, 58h ; 'X'; ConfigInformationLength
0x18002909c  mov     [rsp+0E0h+pOverlapped], r13; pOverlapped
0x1800290a1  lea     r8, [rbp+57h+pConfigInformation]; pConfigInformation
0x1800290a5  xor     ecx, ecx; ServiceHandle
0x1800290a7  lea     edx, [r9-57h]; ConfigId
0x1800290ab  call    cs:__imp_HttpSetServiceConfiguration
0x1800290b1  mov     ebx, eax
0x1800290b3  cmp     eax, 0B7h
0x1800290b8  jnz     short loc_1800290C9
0x1800290ba  mov     rdx, r12; unsigned __int16 *
0x1800290bd  mov     rcx, r15; struct ABO_NODE *
0x1800290c0  call    ?GenerateSSLProperties@@YAJPEAVABO_NODE@@PEBG@Z; GenerateSSLProperties(ABO_NODE *,ushort const *)
0x1800290c5  mov     ebx, eax
0x1800290c7  jmp     short loc_1800290D6
0x1800290c9  test    eax, eax
0x1800290cb  jle     short loc_1800290D6
0x1800290cd  movzx   ebx, ax
0x1800290d0  or      ebx, 80070000h
0x1800290d6  xor     edx, edx; pReserved
0x1800290d8  lea     ecx, [rdx+2]; Flags
0x1800290db  call    cs:__imp_HttpTerminate
0x1800290e1  jmp     short loc_1800290E8
0x1800290e3  mov     ebx, 80070057h
0x1800290e8  mov     eax, ebx
0x1800290ea  mov     rcx, [rbp+57h+var_50]
0x1800290ee  xor     rcx, rsp; StackCookie
0x1800290f1  call    __security_check_cookie
0x1800290f6  add     rsp, 0A8h
0x1800290fd  pop     r15
0x1800290ff  pop     r14
0x180029101  pop     r13
0x180029103  pop     r12
0x180029105  pop     rdi
0x180029106  pop     rsi
0x180029107  pop     rbx
0x180029108  pop     rbp
0x180029109  retn
```
