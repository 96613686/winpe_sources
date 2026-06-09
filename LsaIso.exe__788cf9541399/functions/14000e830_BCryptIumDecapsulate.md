# BCryptIumDecapsulate

- ea: `0x14000e830`
- end: `0x14000ea35`
- name: `BCryptIumDecapsulate`
- size: `517`
- prototype: `__int64 __fastcall(__int64, unsigned __int64, __int64, unsigned int, __int64, int, __int64, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x140002080`
- `0x1400021f0`
- `0x1400083a8`
- `0x14000e830`
- `0x14001193c`
- `0x140011964`
- `0x140011b74`
- `0x140037b10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14000e9f0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14000e9f0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14000e9b4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14000e9b4`
- `bcrypt!BCryptDecapsulate` at `0x14000e9e4`
- `bcrypt!BCryptDecapsulate` at `0x14000e9e4`

## string_xrefs

- `0x14000e99a`: `onecore\ds\security\cryptoapi\ncrypt\ium\trustlet\bcryptiumrpcimpl.cxx`

## pseudocode

```c
__int64 __fastcall BCryptIumDecapsulate(
        __int64 a1,
        unsigned __int64 a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        int a6,
        __int64 a7,
        int a8)
{
  int Context; // eax
  unsigned int v13; // edi
  PVOID *v14; // rcx
  RTL_SRWLOCK *v15; // rax
  __int64 v16; // r8
  RTL_SRWLOCK *v17; // rsi
  _QWORD *v18; // rax
  __int64 v19; // rdx
  struct BCRYPTIUM_CONTEXT *v21; // [rsp+40h] [rbp-48h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 310, &WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids);
  v21 = 0;
  Context = BCryptIumContextManagerGetContext(a1, &v21);
  v13 = Context;
  if ( Context >= 0 )
  {
    v15 = (RTL_SRWLOCK *)LookupBCryptIsoObject(v21, a2, 0x42494F4Bu);
    v17 = v15;
    if ( !v15 )
    {
      v13 = -1073741816;
      v14 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v13;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_26;
      WPP_SF_ID(*((_QWORD *)WPP_GLOBAL_Control + 2), 312, v16, a2, -1073741816);
      goto LABEL_25;
    }
    if ( a7 )
    {
      if ( a3 )
      {
        if ( a8 )
        {
          v13 = -1073741811;
          VBS_ATTEST_TRACE_ERROR_IN(
            3221225485LL,
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\ium\\trustlet\\bcryptiumrpcimpl.cxx",
            3606);
        }
        else
        {
          AcquireSRWLockShared(v15 + 5);
          v13 = BCryptDecapsulate(v17[1].Ptr, a3, a4, a5, a6, a7, 0);
          ReleaseSRWLockShared(v17 + 5);
        }
        goto LABEL_24;
      }
      v13 = -1073741811;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_24:
        BCryptIumDereferenceObject(v17);
        goto LABEL_25;
      }
      v19 = 314;
    }
    else
    {
      v13 = -1073741811;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_24;
      v19 = 313;
    }
    WPP_SF_d(v18[2], v19, &WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids, 3221225485LL);
    goto LABEL_24;
  }
  v14 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v13;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      311,
      &WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids,
      (unsigned int)Context);
LABEL_25:
    v14 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_26:
  if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 4) != 0 )
    WPP_SF_d(v14[2], 317, &WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids, v13);
  return v13;
}

```

## disassembly

```asm
0x14000e830  push    rbx
0x14000e832  push    rbp
0x14000e833  push    rsi
0x14000e834  push    rdi
0x14000e835  push    r12
0x14000e837  push    r13
0x14000e839  push    r14
0x14000e83b  sub     rsp, 50h
0x14000e83f  mov     r14d, r9d
0x14000e842  mov     rbp, r8
0x14000e845  mov     rbx, rdx
0x14000e848  mov     rdi, rcx
0x14000e84b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e852  lea     r12, WPP_GLOBAL_Control
0x14000e859  lea     r13, WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids
0x14000e860  cmp     rcx, r12
0x14000e863  jz      short loc_14000E87C
0x14000e865  test    byte ptr [rcx+1Ch], 4
0x14000e869  jz      short loc_14000E87C
0x14000e86b  mov     rcx, [rcx+10h]
0x14000e86f  mov     edx, 136h
0x14000e874  mov     r8, r13
0x14000e877  call    WPP_SF_
0x14000e87c  lea     rdx, [rsp+88h+var_48]
0x14000e881  mov     [rsp+88h+var_48], 0
0x14000e88a  mov     rcx, rdi
0x14000e88d  call    BCryptIumContextManagerGetContext
0x14000e892  mov     edi, eax
0x14000e894  test    eax, eax
0x14000e896  jns     short loc_14000E8CB
0x14000e898  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e89f  cmp     rcx, r12
0x14000e8a2  jz      loc_14000EA24
0x14000e8a8  test    byte ptr [rcx+1Ch], 4
0x14000e8ac  jz      loc_14000EA05
0x14000e8b2  mov     rcx, [rcx+10h]
0x14000e8b6  mov     edx, 137h
0x14000e8bb  mov     r9d, eax
0x14000e8be  mov     r8, r13
0x14000e8c1  call    WPP_SF_d
0x14000e8c6  jmp     loc_14000E9FE
0x14000e8cb  mov     rcx, [rsp+88h+var_48]; struct BCRYPTIUM_CONTEXT *
0x14000e8d0  mov     r8d, 42494F4Bh; unsigned int
0x14000e8d6  mov     rdx, rbx; unsigned __int64
0x14000e8d9  call    ?LookupBCryptIsoObject@@YAPEAU_BCRYPT_ISO_OBJECT@@PEAUBCRYPTIUM_CONTEXT@@_KK@Z; LookupBCryptIsoObject(BCRYPTIUM_CONTEXT *,unsigned __int64,ulong)
0x14000e8de  mov     rsi, rax
0x14000e8e1  test    rax, rax
0x14000e8e4  jnz     short loc_14000E91F
0x14000e8e6  mov     edi, 0C0000008h
0x14000e8eb  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e8f2  cmp     rcx, r12
0x14000e8f5  jz      loc_14000EA24
0x14000e8fb  test    byte ptr [rcx+1Ch], 1
0x14000e8ff  jz      loc_14000EA05
0x14000e905  mov     rcx, [rcx+10h]
0x14000e909  mov     edx, 138h
0x14000e90e  mov     r9, rbx
0x14000e911  mov     [rsp+88h+var_68], edi
0x14000e915  call    WPP_SF_ID
0x14000e91a  jmp     loc_14000E9FE
0x14000e91f  mov     rdi, [rsp+88h+arg_30]
0x14000e927  test    rdi, rdi
0x14000e92a  jnz     short loc_14000E966
0x14000e92c  mov     ecx, 0C000000Dh
0x14000e931  mov     edi, ecx
0x14000e933  mov     rax, cs:WPP_GLOBAL_Control
0x14000e93a  cmp     rax, r12
0x14000e93d  jz      loc_14000E9F6
0x14000e943  test    byte ptr [rax+1Ch], 1
0x14000e947  jz      loc_14000E9F6
0x14000e94d  mov     edx, 139h
0x14000e952  mov     r9d, ecx
0x14000e955  mov     r8, r13
0x14000e958  mov     rcx, [rax+10h]
0x14000e95c  call    WPP_SF_d
0x14000e961  jmp     loc_14000E9F6
0x14000e966  test    rbp, rbp
0x14000e969  jnz     short loc_14000E98B
0x14000e96b  mov     ecx, 0C000000Dh
0x14000e970  mov     edi, ecx
0x14000e972  mov     rax, cs:WPP_GLOBAL_Control
0x14000e979  cmp     rax, r12
0x14000e97c  jz      short loc_14000E9F6
0x14000e97e  test    byte ptr [rax+1Ch], 1
0x14000e982  jz      short loc_14000E9F6
0x14000e984  mov     edx, 13Ah
0x14000e989  jmp     short loc_14000E952
0x14000e98b  cmp     [rsp+88h+arg_38], 0
0x14000e993  jz      short loc_14000E9B0
0x14000e995  mov     ecx, 0C000000Dh
0x14000e99a  lea     rdx, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x14000e9a1  mov     r8d, 0E16h
0x14000e9a7  mov     edi, ecx
0x14000e9a9  call    VBS_ATTEST_TRACE_ERROR_IN
0x14000e9ae  jmp     short loc_14000E9F6
0x14000e9b0  lea     rcx, [rax+28h]; SRWLock
0x14000e9b4  call    cs:__imp_AcquireSRWLockShared
0x14000e9ba  mov     eax, [rsp+88h+arg_28]
0x14000e9c1  mov     r8d, r14d
0x14000e9c4  mov     r9, [rsp+88h+arg_20]
0x14000e9cc  mov     rdx, rbp
0x14000e9cf  mov     rcx, [rsi+8]
0x14000e9d3  mov     [rsp+88h+var_58], 0
0x14000e9db  mov     [rsp+88h+var_60], rdi
0x14000e9e0  mov     [rsp+88h+var_68], eax
0x14000e9e4  call    cs:__imp_BCryptDecapsulate
0x14000e9ea  mov     edi, eax
0x14000e9ec  lea     rcx, [rsi+28h]; SRWLock
0x14000e9f0  call    cs:__imp_ReleaseSRWLockShared
0x14000e9f6  mov     rcx, rsi; hMem
0x14000e9f9  call    ?BCryptIumDereferenceObject@@YAXPEAU_BCRYPT_ISO_OBJECT@@@Z; BCryptIumDereferenceObject(_BCRYPT_ISO_OBJECT *)
0x14000e9fe  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ea05  cmp     rcx, r12
0x14000ea08  jz      short loc_14000EA24
0x14000ea0a  test    byte ptr [rcx+1Ch], 4
0x14000ea0e  jz      short loc_14000EA24
0x14000ea10  mov     rcx, [rcx+10h]
0x14000ea14  mov     edx, 13Dh
0x14000ea19  mov     r9d, edi
0x14000ea1c  mov     r8, r13
0x14000ea1f  call    WPP_SF_d
0x14000ea24  mov     eax, edi
0x14000ea26  add     rsp, 50h
0x14000ea2a  pop     r14
0x14000ea2c  pop     r13
0x14000ea2e  pop     r12
0x14000ea30  pop     rdi
0x14000ea31  pop     rsi
0x14000ea32  pop     rbp
0x14000ea33  pop     rbx
0x14000ea34  retn
```
