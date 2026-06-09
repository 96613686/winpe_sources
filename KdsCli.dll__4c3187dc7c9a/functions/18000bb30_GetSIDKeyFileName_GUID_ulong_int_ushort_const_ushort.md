# GetSIDKeyFileName(_GUID,ulong,int,ushort const *,ushort * *)

- ea: `0x18000bb30`
- end: `0x18000bd04`
- name: `?GetSIDKeyFileName@@YAJU_GUID@@KHPEBGPEAPEAG@Z`
- size: `468`
- prototype: `int(struct _GUID *__struct_ptr, unsigned int, int, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000aef0`
- `0x18000ce40`

## callees

- `0x180001630`
- `0x180001f34`
- `0x18000bb30`
- `0x180010920`
- `0x18001a450`
- `0x18001a6ac`

## import_xrefs

- `RPCRT4!UuidToStringW` at `0x18000bb86`
- `RPCRT4!UuidToStringW` at `0x18000bb86`
- `RPCRT4!RpcStringFreeW` at `0x18000bcd7`
- `RPCRT4!RpcStringFreeW` at `0x18000bcd7`

## string_xrefs

- `0x18000bb98`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyfilecache.cxx`

## pseudocode

```c
__int64 __fastcall GetSIDKeyFileName(
        struct _GUID *a1,
        unsigned int a2,
        int a3,
        const unsigned __int16 *a4,
        unsigned __int16 **a5)
{
  __int64 v5; // rbx
  __int64 v6; // rbp
  __int64 v7; // rsi
  RPC_STATUS v10; // eax
  signed int v11; // edi
  size_t v12; // r14
  __int64 v13; // rax
  size_t v14; // rbp
  size_t v15; // r15
  unsigned __int16 *v16; // rax
  unsigned __int16 *v17; // rsi
  size_t v18; // rcx
  __int64 v19; // rax
  size_t v20; // rbx
  RPC_WSTR StringUuid; // [rsp+20h] [rbp-88h] BYREF
  unsigned __int16 **v23; // [rsp+28h] [rbp-80h]
  _WORD Src[24]; // [rsp+30h] [rbp-78h] BYREF

  v5 = -1;
  v6 = a2;
  v7 = -1;
  v23 = a5;
  StringUuid = 0;
  do
    ++v7;
  while ( a4[v7] );
  v10 = UuidToStringW(a1, &StringUuid);
  v11 = v10;
  if ( v10 )
  {
    SidKeyDebugTraceError(
      v10,
      "rpcStatus",
      "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyfilecache.cxx",
      0x1B8u);
    if ( v11 > 0 )
      v11 = (unsigned __int16)v11 | 0x80070000;
  }
  else
  {
    v12 = v7;
    o__ui64tow_s_0(v6, Src, 21);
    v13 = -1;
    do
      ++v13;
    while ( Src[v13] );
    v14 = 2 * v13;
    do
      ++v5;
    while ( StringUuid[v5] );
    v15 = 2 * v5;
    v16 = (unsigned __int16 *)SIDKeyProvAlloc(v12 * 2 + v14
                                                      + 2 * v5
                                                      + (-(__int64)(a3 != 0) & 0xFFFFFFFFFFFFFFFEuLL)
                                                      + 28);
    v17 = v16;
    if ( v16 )
    {
      v11 = 0;
      memcpy_0(v16, a4, v12 * 2);
      v18 = (size_t)&v17[v12 + 1];
      v17[v12] = asc_18001CD7C[0];
      if ( a3 )
      {
        *(_OWORD *)v18 = *(_OWORD *)L"PublicKey\\";
        *(_DWORD *)(v18 + 16) = *(_DWORD *)L"y\\";
        v19 = 20;
      }
      else
      {
        v19 = 22;
        *(_OWORD *)v18 = *(_OWORD *)L"PrivateKey\\";
        *(_QWORD *)(v18 + 14) = *(_QWORD *)L"Key\\";
      }
      v20 = v18 + v19;
      memcpy_0((void *)(v18 + v19), Src, v14);
      *(_WORD *)(v20 + v14) = 45;
      memcpy_0((void *)(v14 + v20 + 2), StringUuid, v15);
      *v23 = v17;
    }
    else
    {
      v11 = -2147024882;
    }
  }
  if ( StringUuid )
    RpcStringFreeW(&StringUuid);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18000bb30  mov     [rsp+arg_10], rbx
0x18000bb35  push    rbp
0x18000bb36  push    rsi
0x18000bb37  push    rdi
0x18000bb38  push    r12
0x18000bb3a  push    r13
0x18000bb3c  push    r14
0x18000bb3e  push    r15
0x18000bb40  sub     rsp, 70h
0x18000bb44  mov     rax, cs:__security_cookie
0x18000bb4b  xor     rax, rsp
0x18000bb4e  mov     [rsp+0A8h+var_48], rax
0x18000bb53  mov     rax, [rsp+0A8h+arg_20]
0x18000bb5b  xor     r15d, r15d
0x18000bb5e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000bb62  mov     ebp, edx
0x18000bb64  mov     rsi, rbx
0x18000bb67  mov     [rsp+0A8h+var_80], rax
0x18000bb6c  mov     r12, r9
0x18000bb6f  mov     [rsp+0A8h+StringUuid], r15
0x18000bb74  mov     r13d, r8d
0x18000bb77  inc     rsi
0x18000bb7a  cmp     [r9+rsi*2], r15w
0x18000bb7f  jnz     short loc_18000BB77
0x18000bb81  lea     rdx, [rsp+0A8h+StringUuid]; StringUuid
0x18000bb86  call    cs:__imp_UuidToStringW
0x18000bb8c  mov     edi, eax
0x18000bb8e  test    eax, eax
0x18000bb90  jz      short loc_18000BBC3
0x18000bb92  mov     r9d, 1B8h; unsigned int
0x18000bb98  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000bb9f  lea     rdx, aRpcstatus; "rpcStatus"
0x18000bba6  mov     ecx, eax; unsigned int
0x18000bba8  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000bbad  test    edi, edi
0x18000bbaf  jle     loc_18000BCCB
0x18000bbb5  movzx   edi, di
0x18000bbb8  or      edi, 80070000h
0x18000bbbe  jmp     loc_18000BCCB
0x18000bbc3  mov     r9d, 0Ah
0x18000bbc9  lea     rdx, [rsp+0A8h+Src]
0x18000bbce  mov     rcx, rbp
0x18000bbd1  lea     r14, [rsi+rsi]
0x18000bbd5  lea     r8d, [r9+0Bh]
0x18000bbd9  call    _o__ui64tow_s_0
0x18000bbde  lea     rcx, [rsp+0A8h+Src]
0x18000bbe3  mov     rax, rbx
0x18000bbe6  inc     rax
0x18000bbe9  cmp     [rcx+rax*2], r15w
0x18000bbee  jnz     short loc_18000BBE6
0x18000bbf0  lea     rbp, [rax+rax]
0x18000bbf4  mov     rax, [rsp+0A8h+StringUuid]
0x18000bbf9  inc     rbx
0x18000bbfc  cmp     [rax+rbx*2], r15w
0x18000bc01  jnz     short loc_18000BBF9
0x18000bc03  mov     eax, r13d
0x18000bc06  lea     r15, [rbx+rbx]
0x18000bc0a  neg     eax
0x18000bc0c  sbb     rcx, rcx
0x18000bc0f  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18000bc13  add     rcx, 1Ch
0x18000bc17  add     rcx, r15
0x18000bc1a  add     rcx, rbp
0x18000bc1d  add     rcx, r14; unsigned __int64
0x18000bc20  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x18000bc25  mov     rsi, rax
0x18000bc28  test    rax, rax
0x18000bc2b  jnz     short loc_18000BC37
0x18000bc2d  mov     edi, 8007000Eh
0x18000bc32  jmp     loc_18000BCC8
0x18000bc37  mov     r8, r14; Size
0x18000bc3a  mov     rdx, r12; Src
0x18000bc3d  mov     rcx, rsi; void *
0x18000bc40  xor     edi, edi
0x18000bc42  call    memcpy_0
0x18000bc47  mov     eax, dword ptr cs:asc_18001CD7C; "\\"
0x18000bc4d  lea     rcx, [rsi+2]
0x18000bc51  add     rcx, r14
0x18000bc54  mov     [r14+rsi], ax
0x18000bc59  test    r13d, r13d
0x18000bc5c  jz      short loc_18000BC76
0x18000bc5e  movups  xmm0, xmmword ptr cs:aPublickey; "PublicKey\\"
0x18000bc65  movups  xmmword ptr [rcx], xmm0
0x18000bc68  mov     eax, dword ptr cs:aPublickey+10h; "y\\"
0x18000bc6e  mov     [rcx+10h], eax
0x18000bc71  lea     eax, [rdi+14h]
0x18000bc74  jmp     short loc_18000BC92
0x18000bc76  movups  xmm0, xmmword ptr cs:aPrivatekey; "PrivateKey\\"
0x18000bc7d  mov     eax, 16h
0x18000bc82  movups  xmmword ptr [rcx], xmm0
0x18000bc85  movsd   xmm1, qword ptr cs:aPrivatekey+0Eh; "Key\\"
0x18000bc8d  movsd   qword ptr [rcx+0Eh], xmm1
0x18000bc92  lea     rbx, [rcx+rax]
0x18000bc96  mov     r8, rbp; Size
0x18000bc99  mov     rcx, rbx; void *
0x18000bc9c  lea     rdx, [rsp+0A8h+Src]; Src
0x18000bca1  call    memcpy_0
0x18000bca6  mov     word ptr [rbx+rbp], 2Dh ; '-'
0x18000bcac  lea     rcx, [rbx+2]
0x18000bcb0  mov     rdx, [rsp+0A8h+StringUuid]; Src
0x18000bcb5  add     rcx, rbp; void *
0x18000bcb8  mov     r8, r15; Size
0x18000bcbb  call    memcpy_0
0x18000bcc0  mov     rax, [rsp+0A8h+var_80]
0x18000bcc5  mov     [rax], rsi
0x18000bcc8  xor     r15d, r15d
0x18000bccb  cmp     [rsp+0A8h+StringUuid], r15
0x18000bcd0  jz      short loc_18000BCDD
0x18000bcd2  lea     rcx, [rsp+0A8h+StringUuid]; String
0x18000bcd7  call    cs:__imp_RpcStringFreeW
0x18000bcdd  mov     eax, edi
0x18000bcdf  mov     rcx, [rsp+0A8h+var_48]
0x18000bce4  xor     rcx, rsp; StackCookie
0x18000bce7  call    __security_check_cookie
0x18000bcec  mov     rbx, [rsp+0A8h+arg_10]
0x18000bcf4  add     rsp, 70h
0x18000bcf8  pop     r15
0x18000bcfa  pop     r14
0x18000bcfc  pop     r13
0x18000bcfe  pop     r12
0x18000bd00  pop     rdi
0x18000bd01  pop     rsi
0x18000bd02  pop     rbp
0x18000bd03  retn
```
