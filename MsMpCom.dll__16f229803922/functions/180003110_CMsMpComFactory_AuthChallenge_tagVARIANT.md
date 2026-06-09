# CMsMpComFactory::AuthChallenge(tagVARIANT *)

- ea: `0x180003110`
- end: `0x1800031f9`
- name: `?AuthChallenge@CMsMpComFactory@@UEAAJPEAUtagVARIANT@@@Z`
- size: `233`
- prototype: `__int64 __fastcall(CMsMpComFactory *this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180002b54`
- `0x180003110`
- `0x180005cd8`
- `0x180009440`
- `0x18000a010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18000314e`
- `OLEAUT32!__imp_VariantInit` at `0x18000314e`
- `OLEAUT32!__imp_VariantClear` at `0x1800031b2`
- `OLEAUT32!__imp_VariantClear` at `0x1800031b2`
- `mpclient!MpUtilsExportFunctions` at `0x18000315b`
- `mpclient!MpUtilsExportFunctions` at `0x18000315b`

## pseudocode

```c
__int64 __fastcall CMsMpComFactory::AuthChallenge(CMsMpComFactory *this, struct tagVARIANT *a2)
{
  __int64 result; // rax
  __int64 v5; // rax
  const struct _GUID *v6; // r8
  int v7; // edi
  IRecordInfo *pRecInfo; // xmm1_8
  __int128 v9; // xmm0
  VARIANTARG pvarg; // [rsp+20h] [rbp-40h] BYREF
  __int128 v11; // [rsp+38h] [rbp-28h] BYREF
  struct _GUID v12; // [rsp+48h] [rbp-18h] BYREF

  if ( !a2 )
    return 2147500035LL;
  VariantInit(a2);
  v12 = 0;
  v5 = MpUtilsExportFunctions();
  result = (*(__int64 (__fastcall **)(__int64, struct _GUID *))(v5 + 80))(16, &v12);
  if ( (int)result >= 0 )
  {
    v11 = 0;
    result = ComUtils::MpCoGetResponseFromChallenge((ComUtils *)&v11, &v12, v6);
    if ( (int)result >= 0 )
    {
      pvarg.vt = 0;
      v7 = CommonUtil::SerializeToVariantBinaryBuffer<_GUID>(&pvarg, &v12);
      if ( v7 >= 0 )
      {
        result = 0;
        pRecInfo = pvarg.pRecInfo;
        *(_OWORD *)&a2->vt = *(_OWORD *)&pvarg.vt;
        v9 = v11;
        a2->pRecInfo = pRecInfo;
        *((_OWORD *)this + 1) = v9;
      }
      else
      {
        if ( pvarg.vt )
          VariantClear(&pvarg);
        return (unsigned int)v7;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180003110  mov     [rsp-18h+arg_10], rbx
0x180003115  mov     [rsp-18h+arg_18], rsi
0x18000311a  push    rbp
0x18000311b  push    rdi
0x18000311c  push    r14
0x18000311e  mov     rbp, rsp
0x180003121  sub     rsp, 60h
0x180003125  mov     rax, cs:__security_cookie
0x18000312c  xor     rax, rsp
0x18000312f  mov     [rbp+var_8], rax
0x180003133  xor     r14d, r14d
0x180003136  mov     rbx, rdx
0x180003139  mov     rsi, rcx
0x18000313c  test    rdx, rdx
0x18000313f  jnz     short loc_18000314B
0x180003141  mov     eax, 80004003h
0x180003146  jmp     loc_1800031D8
0x18000314b  mov     rcx, rbx; pvarg
0x18000314e  call    cs:__imp_VariantInit
0x180003154  xorps   xmm0, xmm0
0x180003157  movups  xmmword ptr [rbp+var_18.Data1], xmm0
0x18000315b  call    cs:__imp_MpUtilsExportFunctions
0x180003161  lea     rdx, [rbp+var_18]
0x180003165  mov     ecx, 10h
0x18000316a  mov     rax, [rax+50h]
0x18000316e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003173  test    eax, eax
0x180003175  js      short loc_1800031D8
0x180003177  xorps   xmm0, xmm0
0x18000317a  lea     rdx, [rbp+var_18]; struct _GUID *
0x18000317e  lea     rcx, [rbp+var_28]; this
0x180003182  movups  [rbp+var_28], xmm0
0x180003186  call    ?MpCoGetResponseFromChallenge@ComUtils@@YAJPEAU_GUID@@AEBU2@@Z; ComUtils::MpCoGetResponseFromChallenge(_GUID *,_GUID const &)
0x18000318b  test    eax, eax
0x18000318d  js      short loc_1800031D8
0x18000318f  lea     rdx, [rbp+var_18]
0x180003193  mov     word ptr [rbp+pvarg], r14w
0x180003198  lea     rcx, [rbp+pvarg]
0x18000319c  call    ??$SerializeToVariantBinaryBuffer@U_GUID@@@CommonUtil@@YAJPEAUtagVARIANT@@AEBU_GUID@@@Z; CommonUtil::SerializeToVariantBinaryBuffer<_GUID>(tagVARIANT *,_GUID const &)
0x1800031a1  mov     edi, eax
0x1800031a3  test    eax, eax
0x1800031a5  jns     short loc_1800031BC
0x1800031a7  cmp     word ptr [rbp+pvarg], r14w
0x1800031ac  jz      short loc_1800031B8
0x1800031ae  lea     rcx, [rbp+pvarg]; pvarg
0x1800031b2  call    cs:__imp_VariantClear
0x1800031b8  mov     eax, edi
0x1800031ba  jmp     short loc_1800031D8
0x1800031bc  movups  xmm0, xmmword ptr [rbp+pvarg]
0x1800031c0  xor     eax, eax
0x1800031c2  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x1800031c7  movups  xmmword ptr [rbx], xmm0
0x1800031ca  movups  xmm0, [rbp+var_28]
0x1800031ce  movsd   qword ptr [rbx+10h], xmm1
0x1800031d3  movdqu  xmmword ptr [rsi+10h], xmm0
0x1800031d8  mov     rcx, [rbp+var_8]
0x1800031dc  xor     rcx, rsp; StackCookie
0x1800031df  call    __security_check_cookie
0x1800031e4  lea     r11, [rsp+60h+var_s0]
0x1800031e9  mov     rbx, [r11+30h]
0x1800031ed  mov     rsi, [r11+38h]
0x1800031f1  mov     rsp, r11
0x1800031f4  pop     r14
0x1800031f6  pop     rdi
0x1800031f7  pop     rbp
0x1800031f8  retn
```
