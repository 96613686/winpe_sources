# MpCreateServiceSid(wchar_t *,void * *)

- ea: `0x140022ac4`
- end: `0x140022bff`
- name: `?MpCreateServiceSid@@YAJPEA_WPEAPEAX@Z`
- size: `315`
- prototype: `__int64 __fastcall(wchar_t **, PSID *pSid)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140022568`

## callees

- `0x140003054`
- `0x14000429c`
- `0x1400050f8`
- `0x140005c20`
- `0x140005c40`
- `0x14000c1e0`
- `0x140022ac4`

## import_xrefs

- `ADVAPI32!AllocateAndInitializeSid` at `0x140022bbb`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140022bbb`

## pseudocode

```c
__int64 __fastcall MpCreateServiceSid(wchar_t **a1, PSID *pSid, const wchar_t *a3)
{
  unsigned __int64 v6; // rdx
  int v7; // esi
  __int64 v8; // rdi
  wchar_t *v9; // rbx
  unsigned int v10; // eax
  int v11; // edx
  unsigned __int64 v12; // rdx
  unsigned int v13; // edi
  wchar_t *String; // [rsp+60h] [rbp+7h] BYREF
  DWORD nSubAuthority1[4]; // [rsp+68h] [rbp+Fh] BYREF
  DWORD nSubAuthority5; // [rsp+78h] [rbp+1Fh]

  nSubAuthority5 = 0;
  *(_OWORD *)nSubAuthority1 = 0;
  if ( !a1 )
    return 3221225485LL;
  String = 0;
  v7 = CommonUtil::HrDuplicateStringW((CommonUtil *)&String, a1, a3);
  v8 = -1;
  do
    ++v8;
  while ( *((_WORD *)a1 + v8) );
  if ( v7 >= 0 )
  {
    v9 = String;
    v10 = wcsupr_s(String, v8 + 1);
    if ( v10 )
    {
      v13 = CommonUtil::HrFromErrno((CommonUtil *)v10, v11);
    }
    else
    {
      MpHashSha1(nSubAuthority1, 2 * v8, v9);
      LODWORD(String) = 0;
      WORD2(String) = 1280;
      v13 = !AllocateAndInitializeSid(
               (PSID_IDENTIFIER_AUTHORITY)&String,
               6u,
               0x50u,
               nSubAuthority1[0],
               nSubAuthority1[1],
               nSubAuthority1[2],
               nSubAuthority1[3],
               nSubAuthority5,
               0,
               0,
               pSid)
          ? 0x80004005
          : 0;
    }
    if ( v9 )
      operator delete(v9, v12);
    return v13;
  }
  else
  {
    if ( String )
      operator delete(String, v6);
    return (unsigned int)v7;
  }
}

```

## disassembly

```asm
0x140022ac4  mov     [rsp-8+arg_10], rbx
0x140022ac9  push    rbp
0x140022aca  push    rsi
0x140022acb  push    rdi
0x140022acc  push    r14
0x140022ace  push    r15
0x140022ad0  lea     rbp, [rsp-37h]
0x140022ad5  sub     rsp, 90h
0x140022adc  mov     rax, cs:__security_cookie
0x140022ae3  xor     rax, rsp
0x140022ae6  mov     [rbp+57h+var_30], rax
0x140022aea  xor     eax, eax
0x140022aec  xor     r15d, r15d
0x140022aef  mov     [rbp+57h+var_38], eax
0x140022af2  xorps   xmm0, xmm0
0x140022af5  mov     r14, rdx
0x140022af8  mov     rbx, rcx
0x140022afb  movups  xmmword ptr [rbp+57h+nSubAuthority1], xmm0
0x140022aff  test    rcx, rcx
0x140022b02  jnz     short loc_140022B0E
0x140022b04  mov     eax, 0C000000Dh
0x140022b09  jmp     loc_140022BDC
0x140022b0e  mov     rdx, rbx; wchar_t **
0x140022b11  mov     [rbp+57h+String], r15
0x140022b15  lea     rcx, [rbp+57h+String]; this
0x140022b19  call    ?HrDuplicateStringW@CommonUtil@@YAJPEAPEA_WPEB_W@Z; CommonUtil::HrDuplicateStringW(wchar_t * *,wchar_t const *)
0x140022b1e  mov     esi, eax
0x140022b20  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140022b24  inc     rdi
0x140022b27  cmp     [rbx+rdi*2], r15w
0x140022b2c  jnz     short loc_140022B24
0x140022b2e  test    esi, esi
0x140022b30  jns     short loc_140022B47
0x140022b32  mov     rcx, [rbp+57h+String]; void *
0x140022b36  test    rcx, rcx
0x140022b39  jz      short loc_140022B40
0x140022b3b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140022b40  mov     eax, esi
0x140022b42  jmp     loc_140022BDC
0x140022b47  mov     rbx, [rbp+57h+String]
0x140022b4b  lea     rdx, [rdi+1]; Size
0x140022b4f  mov     rcx, rbx; String
0x140022b52  call    _wcsupr_s
0x140022b57  test    eax, eax
0x140022b59  jz      short loc_140022B66
0x140022b5b  mov     ecx, eax; this
0x140022b5d  call    ?HrFromErrno@CommonUtil@@YAJH@Z; CommonUtil::HrFromErrno(int)
0x140022b62  mov     edi, eax
0x140022b64  jmp     short loc_140022BCD
0x140022b66  lea     rdx, [rdi+rdi]
0x140022b6a  mov     r8, rbx
0x140022b6d  lea     rcx, [rbp+57h+nSubAuthority1]
0x140022b71  call    MpHashSha1
0x140022b76  mov     eax, [rbp+57h+var_38]
0x140022b79  lea     rcx, [rbp+57h+String]; pIdentifierAuthority
0x140022b7d  mov     r9d, [rbp+57h+nSubAuthority1]; nSubAuthority1
0x140022b81  mov     r8d, 50h ; 'P'; nSubAuthority0
0x140022b87  mov     [rsp+0B0h+pSid], r14; pSid
0x140022b8c  mov     dl, 6; nSubAuthorityCount
0x140022b8e  mov     [rsp+0B0h+nSubAuthority7], r15d; nSubAuthority7
0x140022b93  mov     [rsp+0B0h+nSubAuthority6], r15d; nSubAuthority6
0x140022b98  mov     [rsp+0B0h+nSubAuthority5], eax; nSubAuthority5
0x140022b9c  mov     eax, [rbp+57h+nSubAuthority1+0Ch]
0x140022b9f  mov     [rsp+0B0h+nSubAuthority4], eax; nSubAuthority4
0x140022ba3  mov     eax, [rbp+57h+nSubAuthority1+8]
0x140022ba6  mov     [rsp+0B0h+nSubAuthority3], eax; nSubAuthority3
0x140022baa  mov     eax, [rbp+57h+nSubAuthority1+4]
0x140022bad  mov     [rsp+0B0h+nSubAuthority2], eax; nSubAuthority2
0x140022bb1  mov     dword ptr [rbp+57h+String], r15d
0x140022bb5  mov     word ptr [rbp+57h+String+4], 500h
0x140022bbb  call    cs:__imp_AllocateAndInitializeSid
0x140022bc1  neg     eax
0x140022bc3  sbb     edi, edi
0x140022bc5  not     edi
0x140022bc7  and     edi, 80004005h
0x140022bcd  test    rbx, rbx
0x140022bd0  jz      short loc_140022BDA
0x140022bd2  mov     rcx, rbx; void *
0x140022bd5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140022bda  mov     eax, edi
0x140022bdc  mov     rcx, [rbp+57h+var_30]
0x140022be0  xor     rcx, rsp; StackCookie
0x140022be3  call    __security_check_cookie
0x140022be8  mov     rbx, [rsp+0B0h+arg_10]
0x140022bf0  add     rsp, 90h
0x140022bf7  pop     r15
0x140022bf9  pop     r14
0x140022bfb  pop     rdi
0x140022bfc  pop     rsi
0x140022bfd  pop     rbp
0x140022bfe  retn
```
