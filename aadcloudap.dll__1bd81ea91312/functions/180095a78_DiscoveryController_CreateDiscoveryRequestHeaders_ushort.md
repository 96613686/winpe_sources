# DiscoveryController::CreateDiscoveryRequestHeaders(ushort * *)

- ea: `0x180095a78`
- end: `0x180095cb4`
- name: `?CreateDiscoveryRequestHeaders@DiscoveryController@@AEAAJPEAPEAG@Z`
- size: `572`
- prototype: `__int64 __fastcall(DiscoveryController *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18009699c`

## callees

- `0x180005f24`
- `0x180085ad8`
- `0x180085c44`
- `0x18008a9ec`
- `0x18008aa28`
- `0x18008aa9c`
- `0x180095a78`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180095b53`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180095bb0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180095bf2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180095c34`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180095c7c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180095c85`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180095b53`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180095bb0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180095bf2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180095c34`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180095c7c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180095c85`

## string_xrefs

- `0x180095c5f`: `CopyStringNullSafeW`
- `0x180095ad1`: `DiscoveryController::CreateDiscoveryRequestHeaders`
- `0x180095b31`: `DiscoveryController::CreateDiscoveryRequestHeaders`
- `0x180095b98`: `DiscoveryController::CreateDiscoveryRequestHeaders`
- `0x180095c66`: `DiscoveryController::CreateDiscoveryRequestHeaders`
- `0x180095c8e`: `DiscoveryController::CreateDiscoveryRequestHeaders`
- `0x180095b0d`: `Content-Type: application/json; charset=utf-8\nAccept: application/json; charset=utf-8\nreturn-client-request-id: true\n`
- `0x180095c4a`: `Content-Type: application/json; charset=utf-8\nAccept: application/json; charset=utf-8\nreturn-client-request-id: true\n`

## pseudocode

```c
__int64 __fastcall DiscoveryController::CreateDiscoveryRequestHeaders(DiscoveryController *this, unsigned __int16 **a2)
{
  _WORD *v4; // rax
  void *v5; // rsi
  void *v6; // rdi
  _WORD *v7; // rax
  unsigned int v8; // ebx
  unsigned __int64 v9; // r14
  unsigned __int64 v10; // rcx
  int v11; // eax
  unsigned __int64 v12; // rcx
  int v13; // eax
  const unsigned __int16 *v14; // r9
  unsigned __int64 v15; // r8
  unsigned __int64 v16; // rcx
  int v17; // eax
  void *Block; // [rsp+80h] [rbp+48h] BYREF

  *a2 = 0;
  v4 = (_WORD *)*((_QWORD *)this + 6);
  v5 = 0;
  v6 = 0;
  if ( v4 && *v4 )
  {
    v7 = operator new[](2u, (const struct std::nothrow_t *)std::nothrow);
    Block = v7;
    v6 = v7;
    if ( v7 )
    {
      v9 = -1;
      *v7 = 0;
      v10 = -1;
      do
        ++v10;
      while ( v7[v10] );
      v11 = ConcatenateStringW(
              v10,
              v7,
              0x78u,
              L"Content-Type: application/json; charset=utf-8\r\n"
               "Accept: application/json; charset=utf-8\r\n"
               "return-client-request-id: true\r\n",
              (unsigned __int16 **)&Block);
      v8 = v11;
      if ( v11 >= 0 )
      {
        free(v6);
        v5 = Block;
        v12 = -1;
        do
          ++v12;
        while ( *((_WORD *)Block + v12) );
        v13 = ConcatenateStringW(
                v12,
                (const unsigned __int16 *)Block,
                0x13u,
                L"client-request-id: ",
                (unsigned __int16 **)&Block);
        v8 = v13;
        if ( v13 >= 0 )
        {
          free(v5);
          v14 = (const unsigned __int16 *)*((_QWORD *)this + 6);
          v15 = -1;
          v5 = Block;
          do
            ++v15;
          while ( v14[v15] );
          v16 = -1;
          do
            ++v16;
          while ( *((_WORD *)Block + v16) );
          v13 = ConcatenateStringW(v16, (const unsigned __int16 *)Block, v15, v14, (unsigned __int16 **)&Block);
          v8 = v13;
          if ( v13 >= 0 )
          {
            free(v5);
            v5 = Block;
            do
              ++v9;
            while ( *((_WORD *)Block + v9) );
            v13 = ConcatenateStringW(v9, (const unsigned __int16 *)Block, 2u, L"\r\n", (unsigned __int16 **)&Block);
            v8 = v13;
            if ( v13 >= 0 )
            {
              free(v5);
              v5 = 0;
              *a2 = (unsigned __int16 *)Block;
              v6 = 0;
              goto LABEL_25;
            }
          }
        }
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x.",
          L"DiscoveryController::CreateDiscoveryRequestHeaders",
          L"ConcatenateStringW",
          (unsigned int)v13);
      }
      else
      {
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x.",
          L"DiscoveryController::CreateDiscoveryRequestHeaders",
          L"ConcatenateStringW",
          (unsigned int)v11);
        v5 = v6;
      }
      v6 = Block;
    }
    else
    {
      v8 = -2147024882;
      Logger::TraceCritical(
        L"%s: Out of memory. Allocation failed.",
        L"DiscoveryController::CreateDiscoveryRequestHeaders");
    }
  }
  else
  {
    v17 = CopyStringNullSafeW(
            L"Content-Type: application/json; charset=utf-8\r\n"
             "Accept: application/json; charset=utf-8\r\n"
             "return-client-request-id: true\r\n",
            a2);
    v8 = v17;
    if ( v17 < 0 )
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"DiscoveryController::CreateDiscoveryRequestHeaders",
        L"CopyStringNullSafeW",
        (unsigned int)v17);
  }
LABEL_25:
  free(v5);
  free(v6);
  Logger::TraceVerbose(L"%s - hr: 0x%08x", L"DiscoveryController::CreateDiscoveryRequestHeaders", v8);
  return v8;
}

```

## disassembly

```asm
0x180095a78  push    rbp
0x180095a7a  push    rbx
0x180095a7b  push    rsi
0x180095a7c  push    rdi
0x180095a7d  push    r12
0x180095a7f  push    r13
0x180095a81  push    r14
0x180095a83  push    r15
0x180095a85  mov     rbp, rsp
0x180095a88  sub     rsp, 38h
0x180095a8c  xor     r13d, r13d
0x180095a8f  mov     r12, rdx
0x180095a92  mov     [rdx], r13
0x180095a95  mov     r15, rcx
0x180095a98  mov     rax, [rcx+30h]
0x180095a9c  mov     esi, r13d
0x180095a9f  mov     edi, r13d
0x180095aa2  test    rax, rax
0x180095aa5  jz      loc_180095C4A
0x180095aab  cmp     [rax], r13w
0x180095aaf  jz      loc_180095C4A
0x180095ab5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180095abc  lea     ecx, [r13+2]; unsigned __int64
0x180095ac0  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180095ac5  mov     [rbp+Block], rax
0x180095ac9  mov     rdi, rax
0x180095acc  test    rax, rax
0x180095acf  jnz     short loc_180095AEE
0x180095ad1  lea     rdx, aDiscoverycontr_2; "DiscoveryController::CreateDiscoveryReq"...
0x180095ad8  mov     ebx, 8007000Eh
0x180095add  lea     rcx, aSOutOfMemoryAl_0; "%s: Out of memory. Allocation failed."
0x180095ae4  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x180095ae9  jmp     loc_180095C79
0x180095aee  or      r14, 0FFFFFFFFFFFFFFFFh
0x180095af2  mov     [rax], r13w
0x180095af6  mov     rcx, r14
0x180095af9  inc     rcx; unsigned __int64
0x180095afc  cmp     [rax+rcx*2], r13w
0x180095b01  jnz     short loc_180095AF9
0x180095b03  lea     rax, [rbp+Block]
0x180095b07  mov     r8d, 78h ; 'x'; unsigned __int64
0x180095b0d  lea     r9, aContentTypeApp; "Content-Type: application/json; charset"...
0x180095b14  mov     [rsp+38h+var_18], rax; unsigned __int16 **
0x180095b19  mov     rdx, rdi; unsigned __int16 *
0x180095b1c  call    ?ConcatenateStringW@@YAJ_KPEBG01PEAPEAG@Z; ConcatenateStringW(unsigned __int64,ushort const *,unsigned __int64,ushort const *,ushort * *)
0x180095b21  mov     ebx, eax
0x180095b23  test    eax, eax
0x180095b25  jns     short loc_180095B50
0x180095b27  mov     r9d, eax
0x180095b2a  lea     r8, aConcatenatestr; "ConcatenateStringW"
0x180095b31  lea     rdx, aDiscoverycontr_2; "DiscoveryController::CreateDiscoveryReq"...
0x180095b38  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x180095b3f  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180095b44  mov     rsi, rdi
0x180095b47  mov     rdi, [rbp+Block]
0x180095b4b  jmp     loc_180095C79
0x180095b50  mov     rcx, rdi; Block
0x180095b53  call    cs:__imp_free
0x180095b59  mov     rsi, [rbp+Block]
0x180095b5d  mov     rcx, r14
0x180095b60  inc     rcx; unsigned __int64
0x180095b63  cmp     [rsi+rcx*2], r13w
0x180095b68  jnz     short loc_180095B60
0x180095b6a  lea     rax, [rbp+Block]
0x180095b6e  mov     r8d, 13h; unsigned __int64
0x180095b74  lea     r9, aClientRequestI; "client-request-id: "
0x180095b7b  mov     [rsp+38h+var_18], rax; unsigned __int16 **
0x180095b80  mov     rdx, rsi; unsigned __int16 *
0x180095b83  call    ?ConcatenateStringW@@YAJ_KPEBG01PEAPEAG@Z; ConcatenateStringW(unsigned __int64,ushort const *,unsigned __int64,ushort const *,ushort * *)
0x180095b88  mov     ebx, eax
0x180095b8a  test    eax, eax
0x180095b8c  jns     short loc_180095BAD
0x180095b8e  mov     r9d, eax
0x180095b91  lea     r8, aConcatenatestr; "ConcatenateStringW"
0x180095b98  lea     rdx, aDiscoverycontr_2; "DiscoveryController::CreateDiscoveryReq"...
0x180095b9f  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x180095ba6  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180095bab  jmp     short loc_180095B47
0x180095bad  mov     rcx, rsi; Block
0x180095bb0  call    cs:__imp_free
0x180095bb6  mov     r9, [r15+30h]; unsigned __int16 *
0x180095bba  mov     r8, r14
0x180095bbd  mov     rsi, [rbp+Block]
0x180095bc1  inc     r8; unsigned __int64
0x180095bc4  cmp     [r9+r8*2], r13w
0x180095bc9  jnz     short loc_180095BC1
0x180095bcb  mov     rcx, r14
0x180095bce  inc     rcx; unsigned __int64
0x180095bd1  cmp     [rsi+rcx*2], r13w
0x180095bd6  jnz     short loc_180095BCE
0x180095bd8  lea     rax, [rbp+Block]
0x180095bdc  mov     rdx, rsi; unsigned __int16 *
0x180095bdf  mov     [rsp+38h+var_18], rax; unsigned __int16 **
0x180095be4  call    ?ConcatenateStringW@@YAJ_KPEBG01PEAPEAG@Z; ConcatenateStringW(unsigned __int64,ushort const *,unsigned __int64,ushort const *,ushort * *)
0x180095be9  mov     ebx, eax
0x180095beb  test    eax, eax
0x180095bed  js      short loc_180095B8E
0x180095bef  mov     rcx, rsi; Block
0x180095bf2  call    cs:__imp_free
0x180095bf8  mov     rsi, [rbp+Block]
0x180095bfc  inc     r14
0x180095bff  cmp     [rsi+r14*2], r13w
0x180095c04  jnz     short loc_180095BFC
0x180095c06  lea     rax, [rbp+Block]
0x180095c0a  mov     r8d, 2; unsigned __int64
0x180095c10  lea     r9, asc_1800B545C; "\r\n"
0x180095c17  mov     [rsp+38h+var_18], rax; unsigned __int16 **
0x180095c1c  mov     rdx, rsi; unsigned __int16 *
0x180095c1f  mov     rcx, r14; unsigned __int64
0x180095c22  call    ?ConcatenateStringW@@YAJ_KPEBG01PEAPEAG@Z; ConcatenateStringW(unsigned __int64,ushort const *,unsigned __int64,ushort const *,ushort * *)
0x180095c27  mov     ebx, eax
0x180095c29  test    eax, eax
0x180095c2b  js      loc_180095B8E
0x180095c31  mov     rcx, rsi; Block
0x180095c34  call    cs:__imp_free
0x180095c3a  mov     rax, [rbp+Block]
0x180095c3e  mov     rsi, r13
0x180095c41  mov     [r12], rax
0x180095c45  mov     rdi, r13
0x180095c48  jmp     short loc_180095C79
0x180095c4a  lea     rcx, aContentTypeApp; "Content-Type: application/json; charset"...
0x180095c51  call    ?CopyStringNullSafeW@@YAJPEBGPEAPEAG@Z; CopyStringNullSafeW(ushort const *,ushort * *)
0x180095c56  mov     ebx, eax
0x180095c58  test    eax, eax
0x180095c5a  jns     short loc_180095C79
0x180095c5c  mov     r9d, eax
0x180095c5f  lea     r8, aCopystringnull; "CopyStringNullSafeW"
0x180095c66  lea     rdx, aDiscoverycontr_2; "DiscoveryController::CreateDiscoveryReq"...
0x180095c6d  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x180095c74  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180095c79  mov     rcx, rsi; Block
0x180095c7c  call    cs:__imp_free
0x180095c82  mov     rcx, rdi; Block
0x180095c85  call    cs:__imp_free
0x180095c8b  mov     r8d, ebx
0x180095c8e  lea     rdx, aDiscoverycontr_2; "DiscoveryController::CreateDiscoveryReq"...
0x180095c95  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x180095c9c  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180095ca1  mov     eax, ebx
0x180095ca3  add     rsp, 38h
0x180095ca7  pop     r15
0x180095ca9  pop     r14
0x180095cab  pop     r13
0x180095cad  pop     r12
0x180095caf  pop     rdi
0x180095cb0  pop     rsi
0x180095cb1  pop     rbx
0x180095cb2  pop     rbp
0x180095cb3  retn
```
