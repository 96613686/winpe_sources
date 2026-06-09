# InitIdentityEntry(IConnectedUser *,_IDENTITY_ENTRY *)

- ea: `0x18000cc10`
- end: `0x18000cedd`
- name: `?InitIdentityEntry@@YAJPEAUIConnectedUser@@PEAU_IDENTITY_ENTRY@@@Z`
- size: `717`
- prototype: `__int64 __fastcall(struct IConnectedUser *, struct _IDENTITY_ENTRY *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800074dc`

## callees

- `0x18000cc10`
- `0x1800144b4`
- `0x1800144f4`
- `0x1800191ac`
- `0x180019210`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ccfa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ccfa`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000ccda`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000ce9d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000ccda`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000ce9d`

## pseudocode

```c
__int64 __fastcall InitIdentityEntry(struct IConnectedUser *a1, struct _IDENTITY_ENTRY *a2, __int64 a3)
{
  int v5; // eax
  int v6; // edx
  __int64 v7; // r8
  CIdentityProfileHandler *v8; // rcx
  CIdentityProfileHandler *v9; // rcx
  __int64 v10; // rax
  __int64 v12; // rdx
  __int64 v13; // rdx
  PROPVARIANT pvar[2]; // [rsp+40h] [rbp-20h] BYREF
  __int64 v15; // [rsp+50h] [rbp-10h]
  int v16; // [rsp+90h] [rbp+30h]
  __int64 v17; // [rsp+A0h] [rbp+40h] BYREF

  v17 = 0;
  *(_OWORD *)pvar = 0;
  v15 = 0;
  if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, a3, "InitIdentityEntry");
  }
  *(_OWORD *)a2 = 0;
  *((_OWORD *)a2 + 1) = 0;
  v5 = (*(__int64 (__fastcall **)(struct IConnectedUser *, __int64 *))(*(_QWORD *)a1 + 24LL))(a1, &v17);
  v16 = v5;
  if ( v5 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      goto LABEL_13;
    }
    v12 = 101;
LABEL_30:
    WPP_SF_d(*((_QWORD *)v9 + 2), v12, WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids, (unsigned int)v5);
    goto LABEL_12;
  }
  *(_OWORD *)pvar = 0;
  v15 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v17 + 40LL))(
         v17,
         &PKEY_Identity_UserName,
         pvar);
  v16 = v5;
  if ( v5 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      goto LABEL_13;
    }
    v12 = 102;
    goto LABEL_30;
  }
  if ( LOWORD(pvar[0]) != 31 )
  {
    PropVariantClear(pvar);
    v16 = -2147024809;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      goto LABEL_8;
    }
    v13 = 103;
    goto LABEL_33;
  }
  *(PROPVARIANT *)a2 = pvar[1];
  *(_OWORD *)pvar = 0;
  v15 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v17 + 40LL))(
         v17,
         &PKEY_Identity_ProviderID,
         pvar);
  v16 = v5;
  if ( v5 >= 0 )
  {
    if ( LOWORD(pvar[0]) != 72 )
    {
      PropVariantClear(pvar);
      v16 = -2147024809;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
        goto LABEL_8;
      }
      v13 = 105;
LABEL_33:
      WPP_SF_DD(*((_QWORD *)v8 + 2), v13, WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids, LOWORD(pvar[0]), -2147024809);
      goto LABEL_12;
    }
    *((PROPVARIANT *)a2 + 1) = pvar[1];
    v10 = v17;
    v17 = 0;
    *((_QWORD *)a2 + 2) = v10;
LABEL_12:
    v9 = WPP_GLOBAL_Control;
    goto LABEL_13;
  }
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v12 = 104;
    goto LABEL_30;
  }
LABEL_13:
  if ( v16 < 0 )
  {
LABEL_8:
    CoTaskMemFree(*(LPVOID *)a2);
    v9 = WPP_GLOBAL_Control;
  }
  if ( v16 < 0 )
  {
    if ( v9 == (CIdentityProfileHandler *)&WPP_GLOBAL_Control )
      goto LABEL_18;
    if ( (*((_BYTE *)v9 + 28) & 4) != 0 )
    {
      WPP_SF_sL(*((_QWORD *)v9 + 2), v6, v7, (unsigned int)"InitIdentityEntry", v16);
      v9 = WPP_GLOBAL_Control;
    }
  }
  if ( v9 != (CIdentityProfileHandler *)&WPP_GLOBAL_Control && (*((_DWORD *)v9 + 7) & 0x400) != 0 )
    WPP_SF_s(*((_QWORD *)v9 + 2), 12, v7, "InitIdentityEntry");
LABEL_18:
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x18000cc10  mov     [rsp-28h+arg_8], rbx
0x18000cc15  push    rbp
0x18000cc16  push    rsi
0x18000cc17  push    rdi
0x18000cc18  push    r14
0x18000cc1a  push    r15
0x18000cc1c  mov     rbp, rsp
0x18000cc1f  sub     rsp, 60h
0x18000cc23  mov     rbx, rdx
0x18000cc26  mov     rdi, rcx
0x18000cc29  xor     r14d, r14d
0x18000cc2c  mov     [rbp+arg_0], r14d
0x18000cc30  mov     [rbp+arg_10], r14
0x18000cc34  xorps   xmm0, xmm0
0x18000cc37  xor     eax, eax
0x18000cc39  movups  xmmword ptr [rbp+pvar], xmm0
0x18000cc3d  mov     [rbp+var_10], rax
0x18000cc41  lea     r15, aInitidentityen; "InitIdentityEntry"
0x18000cc48  mov     [rbp+var_28], r15
0x18000cc4c  lea     rax, [rbp+arg_0]
0x18000cc50  mov     [rbp+var_30], rax
0x18000cc54  lea     rsi, WPP_GLOBAL_Control
0x18000cc5b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cc62  cmp     rcx, rsi
0x18000cc65  jz      short loc_18000CC74
0x18000cc67  test    dword ptr [rcx+1Ch], 400h
0x18000cc6e  jnz     loc_18000CDF1
0x18000cc74  xorps   xmm0, xmm0
0x18000cc77  movups  xmmword ptr [rbx], xmm0
0x18000cc7a  movups  xmmword ptr [rbx+10h], xmm0
0x18000cc7e  mov     rax, [rdi]
0x18000cc81  lea     rdx, [rbp+arg_10]
0x18000cc85  mov     rcx, rdi
0x18000cc88  mov     rax, [rax+18h]
0x18000cc8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc91  mov     [rbp+arg_0], eax
0x18000cc94  test    eax, eax
0x18000cc96  js      loc_18000CE07
0x18000cc9c  xorps   xmm0, xmm0
0x18000cc9f  xor     eax, eax
0x18000cca1  movups  xmmword ptr [rbp+pvar], xmm0
0x18000cca5  mov     [rbp+var_10], rax
0x18000cca9  mov     rcx, [rbp+arg_10]
0x18000ccad  mov     rax, [rcx]
0x18000ccb0  lea     r8, [rbp+pvar]
0x18000ccb4  lea     rdx, PKEY_Identity_UserName
0x18000ccbb  mov     rax, [rax+28h]
0x18000ccbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ccc4  mov     [rbp+arg_0], eax
0x18000ccc7  test    eax, eax
0x18000ccc9  js      loc_18000CDB4
0x18000cccf  cmp     word ptr [rbp+pvar], 1Fh
0x18000ccd4  jz      short loc_18000CD09
0x18000ccd6  lea     rcx, [rbp+pvar]; pvar
0x18000ccda  call    cs:__imp_PropVariantClear
0x18000cce0  mov     [rbp+arg_0], 80070057h
0x18000cce7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ccee  cmp     rcx, rsi
0x18000ccf1  jnz     loc_18000CE45
0x18000ccf7  mov     rcx, [rbx]; pv
0x18000ccfa  call    cs:__imp_CoTaskMemFree
0x18000cd00  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cd07  jmp     short loc_18000CD6F
0x18000cd09  mov     rax, [rbp+pvar+8]
0x18000cd0d  mov     [rbx], rax
0x18000cd10  xorps   xmm0, xmm0
0x18000cd13  xor     eax, eax
0x18000cd15  movups  xmmword ptr [rbp+pvar], xmm0
0x18000cd19  mov     [rbp+var_10], rax
0x18000cd1d  mov     rcx, [rbp+arg_10]
0x18000cd21  mov     rax, [rcx]
0x18000cd24  lea     r8, [rbp+pvar]
0x18000cd28  lea     rdx, PKEY_Identity_ProviderID
0x18000cd2f  mov     rax, [rax+28h]
0x18000cd33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd38  mov     [rbp+arg_0], eax
0x18000cd3b  test    eax, eax
0x18000cd3d  js      loc_18000CE7D
0x18000cd43  cmp     word ptr [rbp+pvar], 48h ; 'H'
0x18000cd48  jnz     loc_18000CE99
0x18000cd4e  mov     rax, [rbp+pvar+8]
0x18000cd52  mov     [rbx+8], rax
0x18000cd56  mov     rax, [rbp+arg_10]
0x18000cd5a  mov     [rbp+arg_10], r14
0x18000cd5e  mov     [rbx+10h], rax
0x18000cd62  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cd69  cmp     [rbp+arg_0], 0
0x18000cd6d  jl      short loc_18000CCF7
0x18000cd6f  mov     ebx, [rbp+arg_0]
0x18000cd72  test    ebx, ebx
0x18000cd74  js      short loc_18000CDCD
0x18000cd76  cmp     rcx, rsi
0x18000cd79  jz      short loc_18000CD88
0x18000cd7b  test    dword ptr [rcx+1Ch], 400h
0x18000cd82  jnz     loc_18000CEC6
0x18000cd88  mov     rcx, [rbp+arg_10]
0x18000cd8c  test    rcx, rcx
0x18000cd8f  jz      short loc_18000CD9E
0x18000cd91  mov     rdx, [rcx]
0x18000cd94  mov     rax, [rdx+10h]
0x18000cd98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd9d  nop
0x18000cd9e  mov     eax, ebx
0x18000cda0  mov     rbx, [rsp+60h+arg_8]
0x18000cda8  add     rsp, 60h
0x18000cdac  pop     r15
0x18000cdae  pop     r14
0x18000cdb0  pop     rdi
0x18000cdb1  pop     rsi
0x18000cdb2  pop     rbp
0x18000cdb3  retn
0x18000cdb4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cdbb  cmp     rcx, rsi
0x18000cdbe  jz      short loc_18000CD69
0x18000cdc0  test    byte ptr [rcx+1Ch], 4
0x18000cdc4  jz      short loc_18000CD69
0x18000cdc6  mov     edx, 66h ; 'f'
0x18000cdcb  jmp     short loc_18000CE2D
0x18000cdcd  cmp     rcx, rsi
0x18000cdd0  jz      short loc_18000CD88
0x18000cdd2  test    byte ptr [rcx+1Ch], 4
0x18000cdd6  jz      short loc_18000CD76
0x18000cdd8  mov     [rsp+60h+var_40], ebx
0x18000cddc  mov     r9, r15
0x18000cddf  mov     rcx, [rcx+10h]
0x18000cde3  call    WPP_SF_sL
0x18000cde8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cdef  jmp     short loc_18000CD76
0x18000cdf1  mov     edx, 0Ah
0x18000cdf6  mov     r9, r15
0x18000cdf9  mov     rcx, [rcx+10h]
0x18000cdfd  call    WPP_SF_s
0x18000ce02  jmp     loc_18000CC74
0x18000ce07  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ce0e  cmp     rcx, rsi
0x18000ce11  jz      loc_18000CD69
0x18000ce17  test    byte ptr [rcx+1Ch], 4
0x18000ce1b  jz      loc_18000CD69
0x18000ce21  mov     edx, 65h ; 'e'
0x18000ce26  jmp     short loc_18000CE2D
0x18000ce28  mov     edx, 68h ; 'h'
0x18000ce2d  mov     r9d, eax
0x18000ce30  lea     r8, WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids
0x18000ce37  mov     rcx, [rcx+10h]
0x18000ce3b  call    WPP_SF_d
0x18000ce40  jmp     loc_18000CD62
0x18000ce45  test    byte ptr [rcx+1Ch], 4
0x18000ce49  jz      loc_18000CCF7
0x18000ce4f  mov     edx, 67h ; 'g'
0x18000ce54  jmp     short loc_18000CE5B
0x18000ce56  mov     edx, 69h ; 'i'
0x18000ce5b  movzx   r9d, word ptr [rbp+pvar]
0x18000ce60  mov     [rsp+60h+var_40], 80070057h
0x18000ce68  lea     r8, WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids
0x18000ce6f  mov     rcx, [rcx+10h]
0x18000ce73  call    WPP_SF_DD
0x18000ce78  jmp     loc_18000CD62
0x18000ce7d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ce84  cmp     rcx, rsi
0x18000ce87  jz      loc_18000CD69
0x18000ce8d  test    byte ptr [rcx+1Ch], 4
0x18000ce91  jz      loc_18000CD69
0x18000ce97  jmp     short loc_18000CE28
0x18000ce99  lea     rcx, [rbp+pvar]; pvar
0x18000ce9d  call    cs:__imp_PropVariantClear
0x18000cea3  mov     [rbp+arg_0], 80070057h
0x18000ceaa  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ceb1  cmp     rcx, rsi
0x18000ceb4  jz      loc_18000CCF7
0x18000ceba  test    byte ptr [rcx+1Ch], 4
0x18000cebe  jz      loc_18000CCF7
0x18000cec4  jmp     short loc_18000CE56
0x18000cec6  mov     edx, 0Ch
0x18000cecb  mov     r9, r15
0x18000cece  mov     rcx, [rcx+10h]
0x18000ced2  call    WPP_SF_s
0x18000ced7  jmp     loc_18000CD88
```
