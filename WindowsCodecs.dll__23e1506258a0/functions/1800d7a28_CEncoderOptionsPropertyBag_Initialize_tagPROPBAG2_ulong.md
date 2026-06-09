# CEncoderOptionsPropertyBag::Initialize(tagPROPBAG2 *,ulong)

- ea: `0x1800d7a28`
- end: `0x1800d7c45`
- name: `?Initialize@CEncoderOptionsPropertyBag@@QEAAJPEAUtagPROPBAG2@@K@Z`
- size: `541`
- prototype: `__int64 __fastcall(CEncoderOptionsPropertyBag *__hidden this, struct tagPROPBAG2 *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800d7930`

## callees

- `0x18001dd10`
- `0x180032d50`
- `0x180041898`
- `0x180067e88`
- `0x1800787a0`
- `0x1800bb784`
- `0x1800d7a28`
- `0x18017b528`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d7bd7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d7bd7`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800d7b1e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800d7b1e`

## pseudocode

```c
__int64 __fastcall CEncoderOptionsPropertyBag::Initialize(
        CEncoderOptionsPropertyBag *this,
        struct tagPROPBAG2 *a2,
        unsigned int a3)
{
  unsigned int v6; // ebx
  bool v7; // zf
  char *v8; // rcx
  HRESULT v9; // eax
  int v10; // ecx
  ULONGLONG v11; // rdi
  unsigned int i; // r15d
  unsigned int j; // ebp
  const unsigned __int16 *pstrName; // rcx
  ULONGLONG v15; // rcx
  int v16; // r9d
  void *v17; // rax
  ULONGLONG pullResult; // [rsp+50h] [rbp+8h] BYREF
  char *v20; // [rsp+68h] [rbp+20h] BYREF

  pullResult = 0;
  v20 = (char *)this + 16;
  CMTALock::Enter((CEncoderOptionsPropertyBag *)((char *)this + 16));
  if ( a3 && !a2 )
  {
    v6 = -2147024809;
LABEL_4:
    v7 = (_DWORD)g_doStackCaptures == 0;
LABEL_33:
    if ( !v7 )
    {
      v10 = v6;
LABEL_35:
      DoStackCapture(v10);
      goto LABEL_36;
    }
    goto LABEL_36;
  }
  v8 = (char *)this + 80;
  if ( *((_DWORD *)this + 26) )
  {
    v6 = -2003292412;
    goto LABEL_4;
  }
  v6 = 0;
  if ( a3 )
  {
    v9 = DynArrayImpl<1>::AddMultiple(v8, 72, a3, &pullResult);
    v6 = v9;
    if ( v9 < 0 )
    {
      if ( !(_DWORD)g_doStackCaptures )
        goto LABEL_36;
LABEL_10:
      v10 = v9;
      goto LABEL_35;
    }
    v11 = pullResult;
    for ( i = 0; i < a3; ++i )
    {
      *(_OWORD *)v11 = *(_OWORD *)&a2->dwType;
      *(_OWORD *)(v11 + 16) = *(_OWORD *)&a2->pstrName;
      *(_QWORD *)(v11 + 32) = *(_QWORD *)a2->clsid.Data4;
      *(_QWORD *)(v11 + 16) = 0;
      if ( a2->pstrName )
      {
        for ( j = 1; j < 0x11; ++j )
        {
          if ( !lstrcmpW(a2->pstrName, (LPCWSTR)qword_1801CF7F0[5 * j + 2]) )
          {
            *(_OWORD *)v11 = *(_OWORD *)&qword_1801CF7F0[5 * j];
            *(_OWORD *)(v11 + 16) = *(_OWORD *)&qword_1801CF7F0[5 * j + 2];
            *(_QWORD *)(v11 + 32) = qword_1801CF7F0[5 * j + 4];
            *(_DWORD *)(v11 + 64) = 1;
            break;
          }
        }
        if ( !*(_QWORD *)(v11 + 16) )
        {
          pstrName = a2->pstrName;
          pullResult = 0;
          v9 = StringCchLengthW(pstrName, 0x7FFFFFFFu, &pullResult);
          v6 = v9;
          if ( v9 < 0 )
          {
            if ( (_DWORD)g_doStackCaptures )
              goto LABEL_10;
            break;
          }
          v15 = pullResult + 1;
          if ( pullResult + 1 < pullResult )
          {
            v6 = -2147024362;
            v7 = (_DWORD)g_doStackCaptures == 0;
            goto LABEL_33;
          }
          ++pullResult;
          v9 = ULongLongMult(v15, 2u, &pullResult);
          v6 = v9;
          if ( v9 < 0 )
          {
            if ( v16 )
              goto LABEL_10;
            break;
          }
          v17 = CoTaskMemAlloc(pullResult);
          *(_QWORD *)(v11 + 16) = v17;
          if ( !v17 )
          {
            v6 = -2147024882;
            goto LABEL_4;
          }
          memcpy_0(v17, a2->pstrName, pullResult);
        }
      }
      ++a2;
      v11 += 72LL;
    }
  }
LABEL_36:
  CGuard<CMTALock>::~CGuard<CMTALock>(&v20);
  return v6;
}

```

## disassembly

```asm
0x1800d7a28  mov     rax, rsp
0x1800d7a2b  mov     [rax+10h], rbx
0x1800d7a2f  mov     [rax+18h], rbp
0x1800d7a33  push    rsi
0x1800d7a34  push    rdi
0x1800d7a35  push    r12
0x1800d7a37  push    r14
0x1800d7a39  push    r15
0x1800d7a3b  sub     rsp, 20h
0x1800d7a3f  mov     rbx, rcx
0x1800d7a42  mov     qword ptr [rax+8], 0
0x1800d7a4a  add     rcx, 10h; this
0x1800d7a4e  mov     r14d, r8d
0x1800d7a51  mov     [rax+20h], rcx
0x1800d7a55  mov     rsi, rdx
0x1800d7a58  call    ?Enter@CMTALock@@QEAAXXZ; CMTALock::Enter(void)
0x1800d7a5d  test    r14d, r14d
0x1800d7a60  jz      short loc_1800D7A78
0x1800d7a62  test    rsi, rsi
0x1800d7a65  jnz     short loc_1800D7A78
0x1800d7a67  mov     ebx, 80070057h
0x1800d7a6c  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800d7a73  jmp     loc_1800D7C19
0x1800d7a78  lea     rcx, [rbx+50h]
0x1800d7a7c  cmp     dword ptr [rcx+18h], 0
0x1800d7a80  jbe     short loc_1800D7A89
0x1800d7a82  mov     ebx, 88982F04h
0x1800d7a87  jmp     short loc_1800D7A6C
0x1800d7a89  xor     ebx, ebx
0x1800d7a8b  test    r14d, r14d
0x1800d7a8e  jz      loc_1800D7C22
0x1800d7a94  lea     r9, [rsp+48h+pullResult]
0x1800d7a99  mov     r8d, r14d
0x1800d7a9c  lea     edx, [rbx+48h]
0x1800d7a9f  call    ?AddMultiple@?$DynArrayImpl@$00@@IEAAJIIPEAPEAX@Z; DynArrayImpl<1>::AddMultiple(uint,uint,void * *)
0x1800d7aa4  mov     ebx, eax
0x1800d7aa6  test    eax, eax
0x1800d7aa8  jns     short loc_1800D7AC2
0x1800d7aaa  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800d7ab1  jz      short loc_1800D7ABA
0x1800d7ab3  mov     ecx, eax
0x1800d7ab5  jmp     loc_1800D7C1D
0x1800d7aba  test    eax, eax
0x1800d7abc  js      loc_1800D7C22
0x1800d7ac2  mov     rdi, [rsp+48h+pullResult]
0x1800d7ac7  xor     r15d, r15d
0x1800d7aca  lea     rcx, qword_1801CF7F0
0x1800d7ad1  cmp     r15d, r14d
0x1800d7ad4  jnb     loc_1800D7C22
0x1800d7ada  movups  xmm0, xmmword ptr [rsi]
0x1800d7add  movups  xmmword ptr [rdi], xmm0
0x1800d7ae0  movups  xmm1, xmmword ptr [rsi+10h]
0x1800d7ae4  movups  xmmword ptr [rdi+10h], xmm1
0x1800d7ae8  movsd   xmm0, qword ptr [rsi+20h]
0x1800d7aed  movsd   qword ptr [rdi+20h], xmm0
0x1800d7af2  mov     qword ptr [rdi+10h], 0
0x1800d7afa  cmp     qword ptr [rsi+10h], 0
0x1800d7aff  jz      loc_1800D7BF7
0x1800d7b05  mov     ebp, 1
0x1800d7b0a  cmp     ebp, 11h
0x1800d7b0d  jnb     short loc_1800D7B58
0x1800d7b0f  mov     eax, ebp
0x1800d7b11  lea     r12, [rax+rax*4]
0x1800d7b15  mov     rdx, [rcx+r12*8+10h]; lpString2
0x1800d7b1a  mov     rcx, [rsi+10h]; lpString1
0x1800d7b1e  call    cs:__imp_lstrcmpW
0x1800d7b24  lea     rcx, qword_1801CF7F0
0x1800d7b2b  test    eax, eax
0x1800d7b2d  jz      short loc_1800D7B33
0x1800d7b2f  inc     ebp
0x1800d7b31  jmp     short loc_1800D7B0A
0x1800d7b33  movups  xmm0, xmmword ptr [rcx+r12*8]
0x1800d7b38  movups  xmmword ptr [rdi], xmm0
0x1800d7b3b  movups  xmm1, xmmword ptr [rcx+r12*8+10h]
0x1800d7b41  movups  xmmword ptr [rdi+10h], xmm1
0x1800d7b45  movsd   xmm0, qword ptr [rcx+r12*8+20h]
0x1800d7b4c  movsd   qword ptr [rdi+20h], xmm0
0x1800d7b51  mov     dword ptr [rdi+40h], 1
0x1800d7b58  cmp     qword ptr [rdi+10h], 0
0x1800d7b5d  jnz     loc_1800D7BF7
0x1800d7b63  mov     rcx, [rsi+10h]; unsigned __int16 *
0x1800d7b67  lea     r8, [rsp+48h+pullResult]; unsigned __int64 *
0x1800d7b6c  mov     edx, 7FFFFFFFh; unsigned __int64
0x1800d7b71  mov     [rsp+48h+pullResult], 0
0x1800d7b7a  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800d7b7f  mov     r9d, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x1800d7b86  mov     ebx, eax
0x1800d7b88  test    eax, eax
0x1800d7b8a  jns     short loc_1800D7B9D
0x1800d7b8c  test    r9d, r9d
0x1800d7b8f  jnz     loc_1800D7AB3
0x1800d7b95  test    eax, eax
0x1800d7b97  js      loc_1800D7C22
0x1800d7b9d  mov     rax, [rsp+48h+pullResult]
0x1800d7ba2  lea     rcx, [rax+1]; ullMultiplicand
0x1800d7ba6  cmp     rcx, rax
0x1800d7ba9  jb      short loc_1800D7C11
0x1800d7bab  lea     r8, [rsp+48h+pullResult]; pullResult
0x1800d7bb0  mov     [rsp+48h+pullResult], rcx
0x1800d7bb5  mov     edx, 2; ullMultiplier
0x1800d7bba  call    ULongLongMult
0x1800d7bbf  mov     ebx, eax
0x1800d7bc1  test    eax, eax
0x1800d7bc3  jns     short loc_1800D7BD2
0x1800d7bc5  test    r9d, r9d
0x1800d7bc8  jnz     loc_1800D7AB3
0x1800d7bce  test    eax, eax
0x1800d7bd0  js      short loc_1800D7C22
0x1800d7bd2  mov     rcx, [rsp+48h+pullResult]; cb
0x1800d7bd7  call    cs:__imp_CoTaskMemAlloc
0x1800d7bdd  mov     [rdi+10h], rax
0x1800d7be1  test    rax, rax
0x1800d7be4  jz      short loc_1800D7C07
0x1800d7be6  mov     r8, [rsp+48h+pullResult]; Size
0x1800d7beb  mov     rcx, rax; void *
0x1800d7bee  mov     rdx, [rsi+10h]; Src
0x1800d7bf2  call    memcpy_0
0x1800d7bf7  inc     r15d
0x1800d7bfa  add     rsi, 28h ; '('
0x1800d7bfe  add     rdi, 48h ; 'H'
0x1800d7c02  jmp     loc_1800D7ACA
0x1800d7c07  mov     ebx, 8007000Eh
0x1800d7c0c  jmp     loc_1800D7A6C
0x1800d7c11  mov     ebx, 80070216h
0x1800d7c16  test    r9d, r9d
0x1800d7c19  jz      short loc_1800D7C22
0x1800d7c1b  mov     ecx, ebx; int
0x1800d7c1d  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800d7c22  lea     rcx, [rsp+48h+arg_18]
0x1800d7c27  call    ??1?$CGuard@VCMTALock@@@@QEAA@XZ; CGuard<CMTALock>::~CGuard<CMTALock>(void)
0x1800d7c2c  mov     rbp, [rsp+48h+arg_10]
0x1800d7c31  mov     eax, ebx
0x1800d7c33  mov     rbx, [rsp+48h+arg_8]
0x1800d7c38  add     rsp, 20h
0x1800d7c3c  pop     r15
0x1800d7c3e  pop     r14
0x1800d7c40  pop     r12
0x1800d7c42  pop     rdi
0x1800d7c43  pop     rsi
0x1800d7c44  retn
```
