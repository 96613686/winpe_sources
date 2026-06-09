# BCryptIumEncapsulate

- ea: `0x14000f0d0`
- end: `0x14000f2f2`
- name: `BCryptIumEncapsulate`
- size: `546`
- prototype: `__int64 __fastcall(__int64, unsigned __int64, __int64, unsigned int, __int64, __int64, int, __int64, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x140002080`
- `0x1400021f0`
- `0x1400083a8`
- `0x14000f0d0`
- `0x14001193c`
- `0x140011964`
- `0x140011b74`
- `0x140037b10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14000f2a9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14000f2a9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14000f265`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14000f265`
- `bcrypt!BCryptEncapsulate` at `0x14000f29d`
- `bcrypt!BCryptEncapsulate` at `0x14000f29d`

## string_xrefs

- `0x14000f24b`: `onecore\ds\security\cryptoapi\ncrypt\ium\trustlet\bcryptiumrpcimpl.cxx`

## pseudocode

```c
__int64 __fastcall BCryptIumEncapsulate(
        __int64 a1,
        unsigned __int64 a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        __int64 a6,
        int a7,
        __int64 a8,
        int a9)
{
  int Context; // eax
  unsigned int v14; // edi
  PVOID *v15; // rcx
  RTL_SRWLOCK *v16; // rax
  __int64 v17; // r8
  RTL_SRWLOCK *v18; // rsi
  _QWORD *v19; // rax
  __int64 v20; // rdx
  struct BCRYPTIUM_CONTEXT *v22; // [rsp+40h] [rbp-48h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 302, &WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids);
  v22 = 0;
  Context = BCryptIumContextManagerGetContext(a1, &v22);
  v14 = Context;
  if ( Context >= 0 )
  {
    v16 = (RTL_SRWLOCK *)LookupBCryptIsoObject(v22, a2, 0x42494F4Bu);
    v18 = v16;
    if ( !v16 )
    {
      v14 = -1073741816;
      v15 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v14;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_26;
      WPP_SF_ID(*((_QWORD *)WPP_GLOBAL_Control + 2), 304, v17, a2, -1073741816);
      goto LABEL_25;
    }
    if ( a5 )
    {
      if ( a8 )
      {
        if ( a9 )
        {
          v14 = -1073741811;
          VBS_ATTEST_TRACE_ERROR_IN(
            3221225485LL,
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\ium\\trustlet\\bcryptiumrpcimpl.cxx",
            3516);
        }
        else
        {
          AcquireSRWLockShared(v16 + 5);
          v14 = BCryptEncapsulate(v18[1].Ptr, a3, a4, a5, a6, a7, a8, 0);
          ReleaseSRWLockShared(v18 + 5);
        }
        goto LABEL_24;
      }
      v14 = -1073741811;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_24:
        BCryptIumDereferenceObject(v18);
        goto LABEL_25;
      }
      v20 = 306;
    }
    else
    {
      v14 = -1073741811;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_24;
      v20 = 305;
    }
    WPP_SF_d(v19[2], v20, &WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids, 3221225485LL);
    goto LABEL_24;
  }
  v15 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v14;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      303,
      &WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids,
      (unsigned int)Context);
LABEL_25:
    v15 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_26:
  if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 4) != 0 )
    WPP_SF_d(v15[2], 309, &WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids, v14);
  return v14;
}

```

## disassembly

```asm
0x14000f0d0  push    rbx
0x14000f0d2  push    rbp
0x14000f0d3  push    rsi
0x14000f0d4  push    rdi
0x14000f0d5  push    r13
0x14000f0d7  push    r14
0x14000f0d9  push    r15
0x14000f0db  sub     rsp, 50h
0x14000f0df  mov     r14d, r9d
0x14000f0e2  mov     r15, r8
0x14000f0e5  mov     rbx, rdx
0x14000f0e8  mov     rdi, rcx
0x14000f0eb  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f0f2  lea     r13, WPP_GLOBAL_Control
0x14000f0f9  cmp     rcx, r13
0x14000f0fc  jz      short loc_14000F119
0x14000f0fe  test    byte ptr [rcx+1Ch], 4
0x14000f102  jz      short loc_14000F119
0x14000f104  mov     rcx, [rcx+10h]
0x14000f108  lea     r8, WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids
0x14000f10f  mov     edx, 12Eh
0x14000f114  call    WPP_SF_
0x14000f119  lea     rdx, [rsp+88h+var_48]
0x14000f11e  mov     [rsp+88h+var_48], 0
0x14000f127  mov     rcx, rdi
0x14000f12a  call    BCryptIumContextManagerGetContext
0x14000f12f  mov     edi, eax
0x14000f131  test    eax, eax
0x14000f133  jns     short loc_14000F16C
0x14000f135  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f13c  cmp     rcx, r13
0x14000f13f  jz      loc_14000F2E1
0x14000f145  test    byte ptr [rcx+1Ch], 4
0x14000f149  jz      loc_14000F2BE
0x14000f14f  mov     rcx, [rcx+10h]
0x14000f153  lea     r8, WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids
0x14000f15a  mov     edx, 12Fh
0x14000f15f  mov     r9d, eax
0x14000f162  call    WPP_SF_d
0x14000f167  jmp     loc_14000F2B7
0x14000f16c  mov     rcx, [rsp+88h+var_48]; struct BCRYPTIUM_CONTEXT *
0x14000f171  mov     r8d, 42494F4Bh; unsigned int
0x14000f177  mov     rdx, rbx; unsigned __int64
0x14000f17a  call    ?LookupBCryptIsoObject@@YAPEAU_BCRYPT_ISO_OBJECT@@PEAUBCRYPTIUM_CONTEXT@@_KK@Z; LookupBCryptIsoObject(BCRYPTIUM_CONTEXT *,unsigned __int64,ulong)
0x14000f17f  mov     rsi, rax
0x14000f182  test    rax, rax
0x14000f185  jnz     short loc_14000F1C0
0x14000f187  mov     edi, 0C0000008h
0x14000f18c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f193  cmp     rcx, r13
0x14000f196  jz      loc_14000F2E1
0x14000f19c  test    byte ptr [rcx+1Ch], 1
0x14000f1a0  jz      loc_14000F2BE
0x14000f1a6  mov     rcx, [rcx+10h]
0x14000f1aa  mov     edx, 130h
0x14000f1af  mov     r9, rbx
0x14000f1b2  mov     dword ptr [rsp+88h+var_68], edi
0x14000f1b6  call    WPP_SF_ID
0x14000f1bb  jmp     loc_14000F2B7
0x14000f1c0  mov     rdi, [rsp+88h+arg_20]
0x14000f1c8  test    rdi, rdi
0x14000f1cb  jnz     short loc_14000F20B
0x14000f1cd  mov     ecx, 0C000000Dh
0x14000f1d2  mov     edi, ecx
0x14000f1d4  mov     rax, cs:WPP_GLOBAL_Control
0x14000f1db  cmp     rax, r13
0x14000f1de  jz      loc_14000F2AF
0x14000f1e4  test    byte ptr [rax+1Ch], 1
0x14000f1e8  jz      loc_14000F2AF
0x14000f1ee  mov     edx, 131h
0x14000f1f3  mov     r9d, ecx
0x14000f1f6  lea     r8, WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids
0x14000f1fd  mov     rcx, [rax+10h]
0x14000f201  call    WPP_SF_d
0x14000f206  jmp     loc_14000F2AF
0x14000f20b  mov     rbp, [rsp+88h+arg_38]
0x14000f213  test    rbp, rbp
0x14000f216  jnz     short loc_14000F23C
0x14000f218  mov     ecx, 0C000000Dh
0x14000f21d  mov     edi, ecx
0x14000f21f  mov     rax, cs:WPP_GLOBAL_Control
0x14000f226  cmp     rax, r13
0x14000f229  jz      loc_14000F2AF
0x14000f22f  test    byte ptr [rax+1Ch], 1
0x14000f233  jz      short loc_14000F2AF
0x14000f235  mov     edx, 132h
0x14000f23a  jmp     short loc_14000F1F3
0x14000f23c  cmp     [rsp+88h+arg_40], 0
0x14000f244  jz      short loc_14000F261
0x14000f246  mov     ecx, 0C000000Dh
0x14000f24b  lea     rdx, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x14000f252  mov     r8d, 0DBCh
0x14000f258  mov     edi, ecx
0x14000f25a  call    VBS_ATTEST_TRACE_ERROR_IN
0x14000f25f  jmp     short loc_14000F2AF
0x14000f261  lea     rcx, [rax+28h]; SRWLock
0x14000f265  call    cs:__imp_AcquireSRWLockShared
0x14000f26b  mov     eax, [rsp+88h+arg_30]
0x14000f272  mov     r9, rdi
0x14000f275  mov     rcx, [rsi+8]
0x14000f279  mov     r8d, r14d
0x14000f27c  mov     [rsp+88h+var_50], 0
0x14000f284  mov     rdx, r15
0x14000f287  mov     [rsp+88h+var_58], rbp
0x14000f28c  mov     [rsp+88h+var_60], eax
0x14000f290  mov     rax, [rsp+88h+arg_28]
0x14000f298  mov     [rsp+88h+var_68], rax
0x14000f29d  call    cs:__imp_BCryptEncapsulate
0x14000f2a3  mov     edi, eax
0x14000f2a5  lea     rcx, [rsi+28h]; SRWLock
0x14000f2a9  call    cs:__imp_ReleaseSRWLockShared
0x14000f2af  mov     rcx, rsi; hMem
0x14000f2b2  call    ?BCryptIumDereferenceObject@@YAXPEAU_BCRYPT_ISO_OBJECT@@@Z; BCryptIumDereferenceObject(_BCRYPT_ISO_OBJECT *)
0x14000f2b7  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f2be  cmp     rcx, r13
0x14000f2c1  jz      short loc_14000F2E1
0x14000f2c3  test    byte ptr [rcx+1Ch], 4
0x14000f2c7  jz      short loc_14000F2E1
0x14000f2c9  mov     rcx, [rcx+10h]
0x14000f2cd  lea     r8, WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids
0x14000f2d4  mov     edx, 135h
0x14000f2d9  mov     r9d, edi
0x14000f2dc  call    WPP_SF_d
0x14000f2e1  mov     eax, edi
0x14000f2e3  add     rsp, 50h
0x14000f2e7  pop     r15
0x14000f2e9  pop     r14
0x14000f2eb  pop     r13
0x14000f2ed  pop     rdi
0x14000f2ee  pop     rsi
0x14000f2ef  pop     rbp
0x14000f2f0  pop     rbx
0x14000f2f1  retn
```
