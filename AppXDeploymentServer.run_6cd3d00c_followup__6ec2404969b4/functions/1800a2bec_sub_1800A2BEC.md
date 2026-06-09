# sub_1800A2BEC

- ea: `0x1800a2bec`
- end: `0x1800a3065`
- name: `sub_1800A2BEC`
- size: `1145`
- prototype: `__int64 *__fastcall(__int64 *, SC_HANDLE, const WCHAR **)`
- caller_count: `2`
- callee_count: `28`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18011c1fc`
- `0x18011cd14`

## callees

- `0x18001f1a4`
- `0x180042b90`
- `0x180042bd4`
- `0x180042eac`
- `0x180050710`
- `0x180059fa8`
- `0x18005a63c`
- `0x1800a2770`
- `0x1800a2ae8`
- `0x1800a2bec`
- `0x1800a3098`
- `0x1800a30f4`
- `0x18011c998`
- `0x18011ca30`
- `0x18011cfc4`
- `0x18011ea28`
- `0x1801267bc`
- `0x180132494`
- `0x18015d500`
- `0x18015d52c`
- `0x180173c18`
- `0x18017cda0`
- `0x1801c5240`
- `0x18039c4c8`
- `0x18039c5c8`
- `0x18039c748`
- `0x18039c848`
- `0x18039d0c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2d67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2e43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2d67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2e43`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a2f4c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a2f4c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a2ccb`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a2ccb`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800a2d35`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800a2d35`
- `api-ms-win-service-core-l1-1-1!EnumDependentServicesW` at `0x1800a2e35`
- `api-ms-win-service-core-l1-1-1!EnumDependentServicesW` at `0x1800a2e95`
- `api-ms-win-service-core-l1-1-1!EnumDependentServicesW` at `0x1800a2e35`
- `api-ms-win-service-core-l1-1-1!EnumDependentServicesW` at `0x1800a2e95`

## string_xrefs

- `0x1800a2cb2`: `onecore\base\appmodel\common\impersonationcontext.cpp`
- `0x1800a2cf7`: `onecore\admin\appmodel\common\servicehelpers.cpp`
- `0x1800a2d86`: `onecore\admin\appmodel\common\servicehelpers.cpp`
- `0x1800a2da5`: `onecore\admin\appmodel\common\servicehelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 *__fastcall sub_1800A2BEC(__int64 *a1, SC_HANDLE a2, const WCHAR **a3)
{
  SC_HANDLE v4; // r15
  unsigned __int64 v6; // r13
  signed int v7; // eax
  int v8; // ebx
  const WCHAR *v9; // rsi
  __int64 *v10; // rdi
  const WCHAR *v11; // rdx
  SC_HANDLE v12; // rbx
  signed int LastError; // eax
  unsigned int v14; // ebx
  __int64 v15; // rdx
  const WCHAR *v16; // r9
  const WCHAR *v17; // rax
  LPENUM_SERVICE_STATUSW v18; // r15
  __int64 v19; // rbx
  __int64 v20; // rax
  bool v21; // si
  unsigned __int64 v22; // rbx
  const WCHAR *v23; // r9
  const WCHAR *v24; // rcx
  _QWORD *v25; // rcx
  DWORD ServicesReturned; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbBufSize; // [rsp+34h] [rbp-CCh] BYREF
  SC_HANDLE hService; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v30; // [rsp+40h] [rbp-C0h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-B8h] BYREF
  __int64 *v32; // [rsp+50h] [rbp-B0h] BYREF
  SC_HANDLE v33; // [rsp+58h] [rbp-A8h] BYREF
  LPENUM_SERVICE_STATUSW lpServices; // [rsp+60h] [rbp-A0h] BYREF
  SC_HANDLE v35; // [rsp+68h] [rbp-98h]
  int v36; // [rsp+70h] [rbp-90h] BYREF
  __int64 v37; // [rsp+78h] [rbp-88h] BYREF
  __int64 v38; // [rsp+80h] [rbp-80h]
  _BYTE v39[24]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v40; // [rsp+A0h] [rbp-60h]
  __int64 v41; // [rsp+A8h] [rbp-58h]
  _BYTE v42[16]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v43[16]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v44[24]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v45[64]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v46[32]; // [rsp+130h] [rbp+30h] BYREF
  void *retaddr; // [rsp+198h] [rbp+98h]

  v4 = a2;
  v35 = a2;
  v32 = a1;
  v6 = 0;
  v37 = 0;
  v38 = 0;
  sub_18015D500(&v37);
  sub_180050710(v39);
  v40 = 7;
  v41 = 8;
  v36 = 1065353216;
  sub_1800A2AE8(v39, 16, v37);
  ServicesReturned = 0;
  sub_18015D52C(v45, &ServicesReturned);
  v30 = 0;
  TokenHandle = 0;
  v7 = sub_180059FA8(&TokenHandle);
  v8 = v7;
  if ( v7 >= 0 )
  {
    if ( TokenHandle && !RevertToSelf() )
    {
      sub_18017CDA0(2);
      __debugbreak();
    }
    LODWORD(v30) = 1;
    v8 = 0;
  }
  else
  {
    sub_18001F1A4(retaddr, 46, "onecore\\base\\appmodel\\common\\impersonationcontext.cpp", (unsigned int)v7);
  }
  if ( v8 < 0 )
    sub_180132494(retaddr, 82, "onecore\\admin\\appmodel\\common\\servicehelpers.cpp", (unsigned int)v8);
  v9 = *a3;
  v10 = (__int64 *)a3[1];
  v32 = v10;
  while ( v9 != (const WCHAR *)v10 )
  {
    hService = 0;
    v11 = v9;
    if ( *((_QWORD *)v9 + 3) > 7u )
      v11 = *(const WCHAR **)v9;
    v33 = OpenServiceW(v4, v11, 8u);
    sub_18011CFC4(&hService, &v33);
    sub_1800A2770(&v33);
    v12 = hService;
    if ( hService )
    {
      cbBufSize = 0;
      ServicesReturned = 0;
      if ( !EnumDependentServicesW(hService, 3u, 0, 0, &cbBufSize, &ServicesReturned) && GetLastError() == 234 )
      {
        sub_18039C848(&lpServices, cbBufSize);
        v18 = lpServices;
        if ( lpServices && EnumDependentServicesW(v12, 3u, lpServices, cbBufSize, &cbBufSize, &ServicesReturned) )
        {
          if ( ServicesReturned )
          {
            do
            {
              v19 = *(_QWORD *)sub_18039C5C8(v45, v43, v9);
              sub_180042BD4(v46, v18[v6].lpServiceName);
              sub_180042EAC(v19 + 48, v44, v46);
              sub_180042B90(v46);
              sub_180042BD4(v46, v18[v6].lpServiceName);
              v20 = sub_18039C748(&v36, v42, v46);
              ++*(_DWORD *)(*(_QWORD *)v20 + 48LL);
              sub_180042B90(v46);
              ++v6;
            }
            while ( v6 < ServicesReturned );
            v10 = v32;
          }
          v6 = 0;
        }
        lpServices = 0;
        if ( v18 )
          LocalFree(v18);
        v4 = v35;
      }
    }
    else
    {
      LastError = GetLastError();
      v14 = LastError;
      if ( LastError > 0 )
        v14 = (unsigned __int16)LastError | 0x80070000;
      sub_18011EA28(retaddr, 93, "onecore\\admin\\appmodel\\common\\servicehelpers.cpp");
      if ( (v14 & 0x80000000) != 0 )
        sub_18001F1A4(retaddr, 94, "onecore\\admin\\appmodel\\common\\servicehelpers.cpp", v14);
      if ( (byte_18056AF0B & 2) != 0 )
      {
        v16 = v9;
        if ( *((_QWORD *)v9 + 3) > 7u )
          v16 = *(const WCHAR **)v9;
        sub_18011C998(&qword_180563000, qword_180434AE0, v14, v16);
      }
      v17 = v9;
      if ( *((_QWORD *)v9 + 3) > 7u )
        v17 = *(const WCHAR **)v9;
      sub_18011CA30(v14, v15, qword_180434AE0, v14, v17);
    }
    sub_1800A2770(&hService);
    v9 += 16;
  }
  v21 = v38 != 0;
  v22 = 0;
  v23 = a3[1];
  v24 = *a3;
  if ( ((char *)v23 - (char *)*a3) >> 5 )
  {
    do
    {
      v25 = (_QWORD *)sub_18039D0C4(&v36, &v32, &v24[16 * v22]);
      if ( *v25 == v37 )
        *(_DWORD *)(*(_QWORD *)sub_18039C4C8(&v36, v42, &(*a3)[16 * v22]) + 48LL) = 0;
      ++v22;
      v23 = a3[1];
      v24 = *a3;
    }
    while ( v22 < ((char *)v23 - (char *)*a3) >> 5 );
  }
  if ( v21 )
    sub_1800A30F4(a1, v45, &v36, ((char *)v23 - (char *)v24) >> 5);
  else
    sub_180173C18(a1, a3);
  if ( (_DWORD)v30 )
    sub_18005A63C((__int64)&v30);
  sub_1801267BC(v45);
  sub_1800A3098(&v36);
  return a1;
}

```

## disassembly

```asm
0x1800a2bec  mov     [rsp-8+arg_18], rbx
0x1800a2bf1  push    rbp
0x1800a2bf2  push    rsi
0x1800a2bf3  push    rdi
0x1800a2bf4  push    r12
0x1800a2bf6  push    r13
0x1800a2bf8  push    r14
0x1800a2bfa  push    r15
0x1800a2bfc  lea     rbp, [rsp-60h]
0x1800a2c01  sub     rsp, 160h
0x1800a2c08  mov     rax, cs:__security_cookie
0x1800a2c0f  xor     rax, rsp
0x1800a2c12  mov     [rbp+90h+var_40], rax
0x1800a2c16  mov     r14, r8
0x1800a2c19  mov     r15, rdx
0x1800a2c1c  mov     [rsp+190h+var_128], rdx
0x1800a2c21  mov     r12, rcx
0x1800a2c24  mov     [rsp+190h+var_140], rcx
0x1800a2c29  xor     r13d, r13d
0x1800a2c2c  mov     [rsp+190h+var_120], r13d
0x1800a2c31  mov     [rsp+190h+var_118], r13
0x1800a2c36  mov     [rbp+90h+var_110], r13
0x1800a2c3a  lea     rcx, [rsp+190h+var_118]
0x1800a2c3f  call    sub_18015D500
0x1800a2c44  nop
0x1800a2c45  lea     rcx, [rbp+90h+var_108]
0x1800a2c49  call    sub_180050710
0x1800a2c4e  nop
0x1800a2c4f  mov     [rbp+90h+var_F0], 7
0x1800a2c57  mov     [rbp+90h+var_E8], 8
0x1800a2c5f  mov     [rsp+190h+var_120], 3F800000h
0x1800a2c67  mov     r8, [rsp+190h+var_118]
0x1800a2c6c  lea     edx, [r13+10h]
0x1800a2c70  lea     rcx, [rbp+90h+var_108]
0x1800a2c74  call    sub_1800A2AE8
0x1800a2c79  nop
0x1800a2c7a  mov     [rsp+190h+ServicesReturned], r13d
0x1800a2c7f  lea     rdx, [rsp+190h+ServicesReturned]
0x1800a2c84  lea     rcx, [rbp+90h+var_A0]
0x1800a2c88  call    sub_18015D52C
0x1800a2c8d  nop
0x1800a2c8e  mov     [rsp+190h+var_150], r13
0x1800a2c93  mov     [rsp+190h+TokenHandle], r13
0x1800a2c98  lea     rcx, [rsp+190h+TokenHandle]; TokenHandle
0x1800a2c9d  call    sub_180059FA8
0x1800a2ca2  mov     ebx, eax
0x1800a2ca4  mov     rcx, [rbp+98h]
0x1800a2cab  test    eax, eax
0x1800a2cad  jns     short loc_1800A2CC4
0x1800a2caf  mov     r9d, eax
0x1800a2cb2  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\common\\impers"...
0x1800a2cb9  lea     edx, [r13+2Eh]
0x1800a2cbd  call    sub_18001F1A4
0x1800a2cc2  jmp     short loc_1800A2CE9
0x1800a2cc4  cmp     [rsp+190h+TokenHandle], r13
0x1800a2cc9  jz      short loc_1800A2CDE
0x1800a2ccb  call    cs:RevertToSelf
0x1800a2cd1  test    eax, eax
0x1800a2cd3  jnz     short loc_1800A2CDE
0x1800a2cd5  lea     ecx, [rax+2]
0x1800a2cd8  call    sub_18017CDA0
0x1800a2cdd  int     3; Trap to Debugger
0x1800a2cde  mov     dword ptr [rsp+190h+var_150], 1
0x1800a2ce6  mov     ebx, r13d
0x1800a2ce9  mov     rcx, [rbp+98h]
0x1800a2cf0  test    ebx, ebx
0x1800a2cf2  jns     short loc_1800A2D09
0x1800a2cf4  mov     r9d, ebx
0x1800a2cf7  lea     r8, aOnecoreAdminAp_118; "onecore\\admin\\appmodel\\common\\servi"...
0x1800a2cfe  mov     edx, 52h ; 'R'
0x1800a2d03  call    sub_180132494
0x1800a2d09  mov     rsi, [r14]
0x1800a2d0c  mov     rdi, [r14+8]
0x1800a2d10  mov     [rsp+190h+var_140], rdi
0x1800a2d15  jmp     loc_1800A2F65
0x1800a2d1a  mov     [rsp+190h+hService], r13
0x1800a2d1f  mov     rdx, rsi
0x1800a2d22  cmp     qword ptr [rsi+18h], 7
0x1800a2d27  jbe     short loc_1800A2D2C
0x1800a2d29  mov     rdx, [rsi]; lpServiceName
0x1800a2d2c  mov     r8d, 8; dwDesiredAccess
0x1800a2d32  mov     rcx, r15; hSCManager
0x1800a2d35  call    cs:OpenServiceW
0x1800a2d3b  mov     [rsp+190h+var_138], rax
0x1800a2d40  lea     rdx, [rsp+190h+var_138]
0x1800a2d45  lea     rcx, [rsp+190h+hService]
0x1800a2d4a  call    sub_18011CFC4
0x1800a2d4f  lea     rcx, [rsp+190h+var_138]
0x1800a2d54  call    sub_1800A2770
0x1800a2d59  mov     rbx, [rsp+190h+hService]
0x1800a2d5e  test    rbx, rbx
0x1800a2d61  jnz     loc_1800A2E0A
0x1800a2d67  call    cs:GetLastError
0x1800a2d6d  mov     ebx, eax
0x1800a2d6f  test    eax, eax
0x1800a2d71  jle     short loc_1800A2D7C
0x1800a2d73  movzx   ebx, ax
0x1800a2d76  or      ebx, 80070000h
0x1800a2d7c  mov     rcx, [rbp+98h]
0x1800a2d83  mov     r9d, ebx
0x1800a2d86  lea     r8, aOnecoreAdminAp_118; "onecore\\admin\\appmodel\\common\\servi"...
0x1800a2d8d  mov     edx, 5Dh ; ']'
0x1800a2d92  call    sub_18011EA28
0x1800a2d97  mov     rcx, [rbp+98h]
0x1800a2d9e  test    ebx, ebx
0x1800a2da0  jns     short loc_1800A2DB6
0x1800a2da2  mov     r9d, ebx
0x1800a2da5  lea     r8, aOnecoreAdminAp_118; "onecore\\admin\\appmodel\\common\\servi"...
0x1800a2dac  mov     edx, 5Eh ; '^'
0x1800a2db1  call    sub_18001F1A4
0x1800a2db6  test    cs:byte_18056AF0B, 2
0x1800a2dbd  jz      short loc_1800A2DE2
0x1800a2dbf  mov     r9, rsi
0x1800a2dc2  cmp     qword ptr [rsi+18h], 7
0x1800a2dc7  jbe     short loc_1800A2DCC
0x1800a2dc9  mov     r9, [rsi]
0x1800a2dcc  mov     r8d, ebx
0x1800a2dcf  lea     rdx, qword_180434AE0
0x1800a2dd6  lea     rcx, qword_180563000
0x1800a2ddd  call    sub_18011C998
0x1800a2de2  mov     rax, rsi
0x1800a2de5  cmp     qword ptr [rsi+18h], 7
0x1800a2dea  jbe     short loc_1800A2DEF
0x1800a2dec  mov     rax, [rsi]
0x1800a2def  mov     [rsp+190h+pcbBytesNeeded], rax
0x1800a2df4  mov     r9d, ebx
0x1800a2df7  lea     r8, qword_180434AE0
0x1800a2dfe  mov     ecx, ebx
0x1800a2e00  call    sub_18011CA30
0x1800a2e05  jmp     loc_1800A2F57
0x1800a2e0a  mov     [rsp+190h+cbBufSize], r13d
0x1800a2e0f  mov     [rsp+190h+ServicesReturned], r13d
0x1800a2e14  lea     rax, [rsp+190h+ServicesReturned]
0x1800a2e19  mov     [rsp+190h+lpServicesReturned], rax; lpServicesReturned
0x1800a2e1e  lea     rax, [rsp+190h+cbBufSize]
0x1800a2e23  mov     [rsp+190h+pcbBytesNeeded], rax; pcbBytesNeeded
0x1800a2e28  xor     r9d, r9d; cbBufSize
0x1800a2e2b  xor     r8d, r8d; lpServices
0x1800a2e2e  lea     edx, [r9+3]; dwServiceState
0x1800a2e32  mov     rcx, rbx; hService
0x1800a2e35  call    cs:EnumDependentServicesW
0x1800a2e3b  test    eax, eax
0x1800a2e3d  jnz     loc_1800A2F57
0x1800a2e43  call    cs:GetLastError
0x1800a2e49  cmp     eax, 0EAh
0x1800a2e4e  jnz     loc_1800A2F57
0x1800a2e54  mov     edx, [rsp+190h+cbBufSize]
0x1800a2e58  lea     rcx, [rsp+190h+lpServices]
0x1800a2e5d  call    sub_18039C848
0x1800a2e62  nop
0x1800a2e63  mov     r15, [rsp+190h+lpServices]
0x1800a2e68  test    r15, r15
0x1800a2e6b  jz      loc_1800A2F3F
0x1800a2e71  lea     rax, [rsp+190h+ServicesReturned]
0x1800a2e76  mov     [rsp+190h+lpServicesReturned], rax; lpServicesReturned
0x1800a2e7b  lea     rax, [rsp+190h+cbBufSize]
0x1800a2e80  mov     [rsp+190h+pcbBytesNeeded], rax; pcbBytesNeeded
0x1800a2e85  mov     r9d, [rsp+190h+cbBufSize]; cbBufSize
0x1800a2e8a  mov     r8, r15; lpServices
0x1800a2e8d  mov     edx, 3; dwServiceState
0x1800a2e92  mov     rcx, rbx; hService
0x1800a2e95  call    cs:EnumDependentServicesW
0x1800a2e9b  test    eax, eax
0x1800a2e9d  jz      loc_1800A2F3F
0x1800a2ea3  cmp     [rsp+190h+ServicesReturned], 0
0x1800a2ea8  jbe     loc_1800A2F3C
0x1800a2eae  mov     r8, rsi
0x1800a2eb1  lea     rdx, [rbp+90h+var_C8]
0x1800a2eb5  lea     rcx, [rbp+90h+var_A0]
0x1800a2eb9  call    sub_18039C5C8
0x1800a2ebe  mov     rbx, [rax]
0x1800a2ec1  lea     rdi, ds:0[r13*2]
0x1800a2ec9  add     rdi, r13
0x1800a2ecc  add     rdi, rdi
0x1800a2ecf  mov     rdx, [r15+rdi*8]
0x1800a2ed3  lea     rcx, [rbp+90h+var_60]
0x1800a2ed7  call    sub_180042BD4
0x1800a2edc  nop
0x1800a2edd  lea     r8, [rbp+90h+var_60]
0x1800a2ee1  lea     rdx, [rbp+90h+var_B8]
0x1800a2ee5  lea     rcx, [rbx+30h]
0x1800a2ee9  call    sub_180042EAC
0x1800a2eee  nop
0x1800a2eef  lea     rcx, [rbp+90h+var_60]
0x1800a2ef3  call    sub_180042B90
0x1800a2ef8  mov     rdx, [r15+rdi*8]
0x1800a2efc  lea     rcx, [rbp+90h+var_60]
0x1800a2f00  call    sub_180042BD4
0x1800a2f05  nop
0x1800a2f06  lea     r8, [rbp+90h+var_60]
0x1800a2f0a  lea     rdx, [rbp+90h+var_D8]
0x1800a2f0e  lea     rcx, [rsp+190h+var_120]
0x1800a2f13  call    sub_18039C748
0x1800a2f18  mov     rcx, [rax]
0x1800a2f1b  inc     dword ptr [rcx+30h]
0x1800a2f1e  lea     rcx, [rbp+90h+var_60]
0x1800a2f22  call    sub_180042B90
0x1800a2f27  inc     r13
0x1800a2f2a  mov     eax, [rsp+190h+ServicesReturned]
0x1800a2f2e  cmp     r13, rax
0x1800a2f31  jb      loc_1800A2EAE
0x1800a2f37  mov     rdi, [rsp+190h+var_140]
0x1800a2f3c  xor     r13d, r13d
0x1800a2f3f  mov     [rsp+190h+lpServices], r13
0x1800a2f44  test    r15, r15
0x1800a2f47  jz      short loc_1800A2F52
0x1800a2f49  mov     rcx, r15; hMem
0x1800a2f4c  call    cs:__imp_LocalFree
0x1800a2f52  mov     r15, [rsp+190h+var_128]
0x1800a2f57  lea     rcx, [rsp+190h+hService]
0x1800a2f5c  call    sub_1800A2770
0x1800a2f61  add     rsi, 20h ; ' '
0x1800a2f65  cmp     rsi, rdi
0x1800a2f68  jnz     loc_1800A2D1A
0x1800a2f6e  cmp     [rbp+90h+var_110], r13
0x1800a2f72  setnz   sil
0x1800a2f76  mov     rbx, r13
0x1800a2f79  mov     r9, [r14+8]
0x1800a2f7d  mov     rcx, [r14]
0x1800a2f80  mov     rax, r9
0x1800a2f83  sub     rax, rcx
0x1800a2f86  sar     rax, 5
0x1800a2f8a  test    rax, rax
0x1800a2f8d  jz      short loc_1800A2FEA
0x1800a2f8f  mov     rdi, rbx
0x1800a2f92  shl     rdi, 5
0x1800a2f96  lea     r8, [rdi+rcx]
0x1800a2f9a  lea     rdx, [rsp+190h+var_140]
0x1800a2f9f  lea     rcx, [rsp+190h+var_120]
0x1800a2fa4  call    sub_18039D0C4
0x1800a2fa9  mov     rcx, rax
0x1800a2fac  mov     rax, [rsp+190h+var_118]
0x1800a2fb1  cmp     [rcx], rax
0x1800a2fb4  jnz     short loc_1800A2FD1
0x1800a2fb6  mov     r8, [r14]
0x1800a2fb9  add     r8, rdi
0x1800a2fbc  lea     rdx, [rbp+90h+var_D8]
0x1800a2fc0  lea     rcx, [rsp+190h+var_120]
0x1800a2fc5  call    sub_18039C4C8
0x1800a2fca  mov     rcx, [rax]
0x1800a2fcd  mov     [rcx+30h], r13d
0x1800a2fd1  inc     rbx
0x1800a2fd4  mov     r9, [r14+8]
0x1800a2fd8  mov     rcx, [r14]
0x1800a2fdb  mov     rax, r9
0x1800a2fde  sub     rax, rcx
0x1800a2fe1  sar     rax, 5
0x1800a2fe5  cmp     rbx, rax
0x1800a2fe8  jb      short loc_1800A2F8F
0x1800a2fea  test    sil, sil
0x1800a2fed  jz      short loc_1800A3009
0x1800a2fef  sub     r9, rcx
0x1800a2ff2  sar     r9, 5
0x1800a2ff6  lea     r8, [rsp+190h+var_120]
0x1800a2ffb  lea     rdx, [rbp+90h+var_A0]
0x1800a2fff  mov     rcx, r12
0x1800a3002  call    sub_1800A30F4
0x1800a3007  jmp     short loc_1800A3015
0x1800a3009  mov     rdx, r14
0x1800a300c  mov     rcx, r12
0x1800a300f  call    sub_180173C18
0x1800a3014  nop
0x1800a3015  cmp     dword ptr [rsp+190h+var_150], r13d
0x1800a301a  jz      short loc_1800A3027
0x1800a301c  lea     rcx, [rsp+190h+var_150]
0x1800a3021  call    sub_18005A63C
0x1800a3026  nop
0x1800a3027  lea     rcx, [rbp+90h+var_A0]
0x1800a302b  call    sub_1801267BC
0x1800a3030  nop
0x1800a3031  lea     rcx, [rsp+190h+var_120]
0x1800a3036  call    sub_1800A3098
0x1800a303b  mov     rax, r12
0x1800a303e  mov     rcx, [rbp+90h+var_40]
0x1800a3042  xor     rcx, rsp; StackCookie
0x1800a3045  call    __security_check_cookie
0x1800a304a  mov     rbx, [rsp+190h+arg_18]
0x1800a3052  add     rsp, 160h
0x1800a3059  pop     r15
0x1800a305b  pop     r14
0x1800a305d  pop     r13
0x1800a305f  pop     r12
0x1800a3061  pop     rdi
0x1800a3062  pop     rsi
0x1800a3063  pop     rbp
0x1800a3064  retn
```
