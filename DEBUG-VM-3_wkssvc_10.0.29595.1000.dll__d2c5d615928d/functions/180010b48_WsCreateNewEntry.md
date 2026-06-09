# WsCreateNewEntry

- ea: `0x180010b48`
- end: `0x180010d21`
- name: `WsCreateNewEntry`
- size: `473`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000af60`

## callees

- `0x18000abb0`
- `0x180010b48`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180010c4c`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180010c8a`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180010cef`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180010c4c`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180010c8a`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180010cef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010bbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010bbb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010baa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010cc9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010baa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010cc9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010cda`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010cda`

## pseudocode

```c
DWORD __fastcall WsCreateNewEntry(
        HLOCAL *a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        unsigned int a6,
        __int64 a7,
        int a8,
        _OWORD *a9,
        _QWORD *a10,
        _QWORD *a11)
{
  __int64 v15; // rdi
  int v16; // ecx
  _QWORD *v17; // rax
  _QWORD *v18; // rdx
  int v20; // eax
  unsigned __int64 v21; // rcx
  unsigned __int64 v22; // rax
  __int64 v23; // rbp
  unsigned int v24; // edi
  SIZE_T v25; // rdx
  _DWORD *v26; // rax
  _DWORD *v27; // rbx
  _QWORD *v28; // rax
  unsigned int v29; // [rsp+58h] [rbp+20h] BYREF

  if ( a4 <= 0xFFFF )
  {
    v29 = 2 * a4 + 98;
    NetpULongRoundUp(v29, 2, &v29);
    v15 = a7;
    if ( a3 )
      v16 = *(unsigned __int16 *)(a7 + 2);
    else
      v16 = 0;
    v17 = LocalAlloc(0x40u, v16 + v29);
    *a1 = v17;
    v18 = v17;
    if ( !v17 )
      return GetLastError();
    *v17 = 0;
    *((_DWORD *)v17 + 6) = a4;
    *((_DWORD *)v17 + 7) = 1;
    v17[4] = a2;
    v20 = dword_18004E2F0;
    *((_DWORD *)v18 + 10) = dword_18004E2F0;
    *((_DWORD *)v18 + 14) = a8;
    if ( a9 )
      *(_OWORD *)((char *)v18 + 60) = *a9;
    if ( a10 )
      *(_QWORD *)((char *)v18 + 76) = *a10;
    if ( a11 )
      *(_QWORD *)((char *)v18 + 84) = *a11;
    dword_18004E2F0 = (v20 + 1) & 0x7FFFFFFF;
    if ( a3 )
    {
      v18[2] = v18 + 12;
      _o_wcscpy_s(v18 + 12, a4 + 1, a3);
      v21 = (unsigned __int64)*a1 + 2 * a4 + 98;
      if ( v21 + 2 < v21 )
        v22 = -1;
      else
        v22 = (v21 + 1) & 0xFFFFFFFFFFFFFFFEuLL;
      *((_QWORD *)*a1 + 6) = v22;
      _o_wcscpy_s(*((_QWORD *)*a1 + 6), (unsigned __int64)*(unsigned __int16 *)(v15 + 2) >> 1, *(_QWORD *)(v15 + 8));
    }
    else
    {
      v18[2] = 0;
      v18[6] = 0;
    }
    v23 = a5;
    if ( !a5 )
      return 0;
    v24 = a6;
    v25 = 2 * a6 + 18;
    if ( (unsigned int)v25 >= 0x10 && (unsigned int)v25 >> 1 >= a6 )
    {
      v26 = LocalAlloc(0x40u, v25);
      v27 = v26;
      if ( !v26 )
      {
        LocalFree(*a1);
        return GetLastError();
      }
      _o_wcscpy_s(v26 + 2, v24 + 1, v23);
      v28 = *a1;
      v27[1] = v24;
      *v27 = 1;
      v28[1] = v27;
      return 0;
    }
  }
  return 2317;
}

```

## disassembly

```asm
0x180010b48  mov     rax, rsp
0x180010b4b  mov     [rax+8], rbx
0x180010b4f  mov     [rax+10h], rbp
0x180010b53  push    rsi
0x180010b54  push    rdi
0x180010b55  push    r14
0x180010b57  sub     rsp, 20h
0x180010b5b  mov     ebx, r9d
0x180010b5e  mov     rbp, r8
0x180010b61  mov     r14, rdx
0x180010b64  mov     rsi, rcx
0x180010b67  cmp     r9d, 0FFFFh
0x180010b6e  ja      loc_180010D09
0x180010b74  lea     ecx, ds:62h[r9*2]
0x180010b7c  mov     edx, 2
0x180010b81  lea     r8, [rax+20h]
0x180010b85  mov     [rax+20h], ecx
0x180010b88  call    NetpULongRoundUp
0x180010b8d  mov     rdi, [rsp+38h+arg_30]
0x180010b92  test    rbp, rbp
0x180010b95  jz      short loc_180010B9D
0x180010b97  movzx   ecx, word ptr [rdi+2]
0x180010b9b  jmp     short loc_180010B9F
0x180010b9d  xor     ecx, ecx
0x180010b9f  mov     edx, [rsp+38h+arg_18]
0x180010ba3  add     edx, ecx; uBytes
0x180010ba5  mov     ecx, 40h ; '@'; uFlags
0x180010baa  call    cs:__imp_LocalAlloc
0x180010bb0  mov     [rsi], rax
0x180010bb3  mov     rdx, rax
0x180010bb6  test    rax, rax
0x180010bb9  jnz     short loc_180010BC6
0x180010bbb  call    cs:__imp_GetLastError
0x180010bc1  jmp     loc_180010D0E
0x180010bc6  mov     qword ptr [rax], 0
0x180010bcd  mov     [rax+18h], ebx
0x180010bd0  mov     dword ptr [rax+1Ch], 1
0x180010bd7  mov     [rax+20h], r14
0x180010bdb  mov     eax, cs:dword_18004E2F0
0x180010be1  mov     [rdx+28h], eax
0x180010be4  lea     ecx, [rax+1]
0x180010be7  mov     eax, [rsp+38h+arg_38]
0x180010beb  mov     [rdx+38h], eax
0x180010bee  mov     rax, [rsp+38h+arg_40]
0x180010bf6  test    rax, rax
0x180010bf9  jz      short loc_180010C03
0x180010bfb  movups  xmm0, xmmword ptr [rax]
0x180010bfe  movdqu  xmmword ptr [rdx+3Ch], xmm0
0x180010c03  mov     rax, [rsp+38h+arg_48]
0x180010c0b  test    rax, rax
0x180010c0e  jz      short loc_180010C17
0x180010c10  mov     rax, [rax]
0x180010c13  mov     [rdx+4Ch], rax
0x180010c17  mov     rax, [rsp+38h+arg_50]
0x180010c1f  test    rax, rax
0x180010c22  jz      short loc_180010C2B
0x180010c24  mov     rax, [rax]
0x180010c27  mov     [rdx+54h], rax
0x180010c2b  btr     ecx, 1Fh
0x180010c2f  mov     cs:dword_18004E2F0, ecx
0x180010c35  test    rbp, rbp
0x180010c38  jz      short loc_180010C92
0x180010c3a  lea     rcx, [rdx+60h]
0x180010c3e  mov     r8, rbp
0x180010c41  lea     eax, [rbx+1]
0x180010c44  mov     [rdx+10h], rcx
0x180010c48  mov     edx, eax
0x180010c4a  mov     ebx, eax
0x180010c4c  call    cs:__imp__o_wcscpy_s
0x180010c52  mov     rdx, [rsi]
0x180010c55  lea     rcx, [rdx+60h]
0x180010c59  lea     rcx, [rcx+rbx*2]
0x180010c5d  lea     rax, [rcx+2]
0x180010c61  cmp     rax, rcx
0x180010c64  jbe     short loc_180010C70
0x180010c66  lea     rax, [rcx+1]
0x180010c6a  and     rax, 0FFFFFFFFFFFFFFFEh
0x180010c6e  jmp     short loc_180010C74
0x180010c70  or      rax, 0FFFFFFFFFFFFFFFFh
0x180010c74  mov     [rdx+30h], rax
0x180010c78  mov     rcx, [rsi]
0x180010c7b  movzx   edx, word ptr [rdi+2]
0x180010c7f  mov     r8, [rdi+8]
0x180010c83  shr     rdx, 1
0x180010c86  mov     rcx, [rcx+30h]
0x180010c8a  call    cs:__imp__o_wcscpy_s
0x180010c90  jmp     short loc_180010CA2
0x180010c92  mov     qword ptr [rdx+10h], 0
0x180010c9a  mov     qword ptr [rdx+30h], 0
0x180010ca2  mov     rbp, [rsp+38h+arg_20]
0x180010ca7  test    rbp, rbp
0x180010caa  jz      short loc_180010D05
0x180010cac  mov     edi, [rsp+38h+arg_28]
0x180010cb0  lea     edx, ds:12h[rdi*2]; uBytes
0x180010cb7  cmp     edx, 10h
0x180010cba  jb      short loc_180010D09
0x180010cbc  mov     eax, edx
0x180010cbe  shr     eax, 1
0x180010cc0  cmp     eax, edi
0x180010cc2  jb      short loc_180010D09
0x180010cc4  mov     ecx, 40h ; '@'; uFlags
0x180010cc9  call    cs:__imp_LocalAlloc
0x180010ccf  mov     rbx, rax
0x180010cd2  test    rax, rax
0x180010cd5  jnz     short loc_180010CE5
0x180010cd7  mov     rcx, [rsi]; hMem
0x180010cda  call    cs:__imp_LocalFree
0x180010ce0  jmp     loc_180010BBB
0x180010ce5  lea     edx, [rdi+1]
0x180010ce8  mov     r8, rbp
0x180010ceb  lea     rcx, [rax+8]
0x180010cef  call    cs:__imp__o_wcscpy_s
0x180010cf5  mov     rax, [rsi]
0x180010cf8  mov     [rbx+4], edi
0x180010cfb  mov     dword ptr [rbx], 1
0x180010d01  mov     [rax+8], rbx
0x180010d05  xor     eax, eax
0x180010d07  jmp     short loc_180010D0E
0x180010d09  mov     eax, 90Dh
0x180010d0e  mov     rbx, [rsp+38h+arg_0]
0x180010d13  mov     rbp, [rsp+38h+arg_8]
0x180010d18  add     rsp, 20h
0x180010d1c  pop     r14
0x180010d1e  pop     rdi
0x180010d1f  pop     rsi
0x180010d20  retn
```
