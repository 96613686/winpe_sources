# CDocInfoPropertyStg::ReadMultiple(ulong,tagPROPSPEC const * const,tagPROPVARIANT * const)

- ea: `0x180002b20`
- end: `0x180002cc4`
- name: `?ReadMultiple@CDocInfoPropertyStg@@UEAAJKQEBUtagPROPSPEC@@QEAUtagPROPVARIANT@@@Z`
- size: `420`
- prototype: `__int64 __fastcall(CDocInfoPropertyStg *__hidden this, unsigned int, const struct tagPROPSPEC *const, struct tagPROPVARIANT *const)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180002498`
- `0x180002b20`
- `0x180007700`
- `0x180024220`

## import_xrefs

- `USER32!LoadStringW` at `0x180002c20`
- `USER32!LoadStringW` at `0x180002c20`
- `OLEAUT32!__imp_SysAllocString` at `0x180002c65`
- `OLEAUT32!__imp_SysAllocString` at `0x180002c65`

## pseudocode

```c
__int64 __fastcall CDocInfoPropertyStg::ReadMultiple(
        CDocInfoPropertyStg *this,
        unsigned int a2,
        const struct tagPROPSPEC *const a3,
        struct tagPROPVARIANT *const a4)
{
  unsigned int v8; // r10d
  int v9; // ebx
  unsigned int i; // edi
  __int64 v11; // rbp
  __int64 v12; // rax
  int v13; // eax
  WCHAR Buffer[64]; // [rsp+20h] [rbp-2C8h] BYREF
  OLECHAR psz[256]; // [rsp+A0h] [rbp-248h] BYREF

  v8 = 1;
  v9 = 0;
  for ( i = 0; i < a2; v9 = v13 )
  {
    v11 = i;
    *(_OWORD *)&a4[v11].vt = 0;
    a4[v11].bstrblobVal.pData = 0;
    if ( a3[i].propid == 6
      && *(_QWORD *)((char *)this + 12) == *(_QWORD *)&FMTID_SummaryInformation.Data1
      && *(_QWORD *)((char *)this + 20) == *(_QWORD *)FMTID_SummaryInformation.Data4 )
    {
      memset(Buffer, 0, sizeof(Buffer));
      memset(psz, 0, sizeof(psz));
      v12 = *((_QWORD *)this + 4);
      if ( !v12 || *(int *)(v12 + 36) < 0 || *(_DWORD *)(v12 + 36) == 68 )
        return 1;
      LoadStringW(g_hInstance, 0x6Eu, Buffer, 64);
      StringCchPrintfW(psz, 0x100u, Buffer, &aVisualStudio60[124 * *(int *)(*((_QWORD *)this + 4) + 36LL)]);
      a4[i].vt = 8;
      a4[i].hVal.QuadPart = (LONGLONG)SysAllocString(psz);
      v8 = 0;
    }
    v13 = v9 + 1;
    if ( v8 )
      v13 = v9;
    ++i;
  }
  if ( v9 )
    return 0;
  return v8;
}

```

## disassembly

```asm
0x180002b20  mov     [rsp+arg_8], rbx
0x180002b25  push    rbp
0x180002b26  push    rsi
0x180002b27  push    rdi
0x180002b28  push    r12
0x180002b2a  push    r13
0x180002b2c  push    r14
0x180002b2e  push    r15
0x180002b30  sub     rsp, 2B0h
0x180002b37  mov     rax, cs:__security_cookie
0x180002b3e  xor     rax, rsp
0x180002b41  mov     [rsp+2E8h+var_48], rax
0x180002b49  xor     r13d, r13d
0x180002b4c  mov     r14, r9
0x180002b4f  mov     r12, r8
0x180002b52  mov     r15d, edx
0x180002b55  mov     rsi, rcx
0x180002b58  mov     r10d, 1
0x180002b5e  mov     ebx, r13d
0x180002b61  mov     edi, r13d
0x180002b64  test    edx, edx
0x180002b66  jz      loc_180002C89
0x180002b6c  mov     eax, edi
0x180002b6e  xor     ecx, ecx
0x180002b70  xorps   xmm0, xmm0
0x180002b73  lea     rbp, [rax+rax*2]
0x180002b77  add     rax, rax
0x180002b7a  movups  xmmword ptr [r14+rbp*8], xmm0
0x180002b7f  mov     [r14+rbp*8+10h], rcx
0x180002b84  cmp     dword ptr [r12+rax*8+8], 6
0x180002b8a  jnz     loc_180002C73
0x180002b90  mov     rax, [rsi+0Ch]
0x180002b94  cmp     rax, qword ptr cs:FMTID_SummaryInformation.Data1
0x180002b9b  jnz     loc_180002C73
0x180002ba1  mov     rax, [rsi+14h]
0x180002ba5  cmp     rax, qword ptr cs:FMTID_SummaryInformation.Data4
0x180002bac  jnz     loc_180002C73
0x180002bb2  lea     r8d, [rcx+7Eh]; Size
0x180002bb6  mov     [rsp+2E8h+Buffer], r13w
0x180002bbc  lea     rcx, [rsp+2E8h+var_2C6]; void *
0x180002bc1  xor     edx, edx; Val
0x180002bc3  call    memset
0x180002bc8  xor     edx, edx; Val
0x180002bca  mov     [rsp+2E8h+psz], r13w
0x180002bd3  mov     r8d, 1FEh; Size
0x180002bd9  lea     rcx, [rsp+2E8h+var_246]; void *
0x180002be1  call    memset
0x180002be6  mov     rax, [rsi+20h]
0x180002bea  test    rax, rax
0x180002bed  jz      loc_180002CBD
0x180002bf3  test    dword ptr [rax+24h], 80000000h
0x180002bfa  jnz     loc_180002CBD
0x180002c00  cmp     dword ptr [rax+24h], 44h ; 'D'
0x180002c04  jz      loc_180002CBD
0x180002c0a  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180002c11  lea     r8, [rsp+2E8h+Buffer]; lpBuffer
0x180002c16  mov     r9d, 40h ; '@'; cchBufferMax
0x180002c1c  lea     edx, [r9+2Eh]; uID
0x180002c20  call    cs:__imp_LoadStringW
0x180002c26  mov     rax, [rsi+20h]
0x180002c2a  lea     r8, [rsp+2E8h+Buffer]; unsigned __int16 *
0x180002c2f  mov     edx, 100h; unsigned __int64
0x180002c34  movsxd  rcx, dword ptr [rax+24h]
0x180002c38  lea     rax, aVisualStudio60; "Visual Studio 6.0"
0x180002c3f  imul    r9, rcx, 0F8h
0x180002c46  lea     rcx, [rsp+2E8h+psz]; Buffer
0x180002c4e  add     r9, rax
0x180002c51  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180002c56  lea     rcx, [rsp+2E8h+psz]; psz
0x180002c5e  mov     word ptr [r14+rbp*8], 8
0x180002c65  call    cs:__imp_SysAllocString
0x180002c6b  mov     [r14+rbp*8+8], rax
0x180002c70  mov     r10d, r13d
0x180002c73  test    r10d, r10d
0x180002c76  lea     eax, [rbx+1]
0x180002c79  cmovnz  eax, ebx
0x180002c7c  inc     edi
0x180002c7e  mov     ebx, eax
0x180002c80  cmp     edi, r15d
0x180002c83  jb      loc_180002B6C
0x180002c89  test    ebx, ebx
0x180002c8b  cmovnz  r10d, r13d
0x180002c8f  mov     eax, r10d
0x180002c92  mov     rcx, [rsp+2E8h+var_48]
0x180002c9a  xor     rcx, rsp; StackCookie
0x180002c9d  call    __security_check_cookie
0x180002ca2  mov     rbx, [rsp+2E8h+arg_8]
0x180002caa  add     rsp, 2B0h
0x180002cb1  pop     r15
0x180002cb3  pop     r14
0x180002cb5  pop     r13
0x180002cb7  pop     r12
0x180002cb9  pop     rdi
0x180002cba  pop     rsi
0x180002cbb  pop     rbp
0x180002cbc  retn
0x180002cbd  mov     eax, 1
0x180002cc2  jmp     short loc_180002C92
```
