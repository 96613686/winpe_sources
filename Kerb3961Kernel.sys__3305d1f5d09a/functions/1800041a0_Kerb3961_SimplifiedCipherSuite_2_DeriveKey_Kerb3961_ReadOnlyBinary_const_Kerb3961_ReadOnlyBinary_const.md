# Kerb3961::SimplifiedCipherSuite<2>::DeriveKey(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x1800041a0`
- end: `0x180004382`
- name: `?DeriveKey@?$SimplifiedCipherSuite@$01@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z`
- size: `482`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x180004390`
- `0x180005c30`

## callees

- `0x1800041a0`
- `0x180005b1c`
- `0x18000b0c8`
- `0x1800118cc`
- `0x180011b40`
- `0x180012240`
- `0x180012300`
- `0x180012600`

## pseudocode

```c
__int64 __fastcall Kerb3961::SimplifiedCipherSuite<2>::DeriveKey(_QWORD *a1, __int64 a2, __int64 a3, size_t *a4)
{
  unsigned __int64 v8; // r14
  int v9; // r8d
  int v10; // esi
  int v11; // r8d
  int v12; // esi
  int v13; // r8d
  int v14; // esi
  unsigned __int64 v15; // rsi
  int v16; // r8d
  int v17; // r15d
  __int64 v19; // [rsp+30h] [rbp-50h] BYREF
  __int64 v20; // [rsp+38h] [rbp-48h]
  char *v21; // [rsp+40h] [rbp-40h]
  _BYTE v22[8]; // [rsp+48h] [rbp-38h] BYREF
  void *v23; // [rsp+50h] [rbp-30h]
  char *v24; // [rsp+58h] [rbp-28h]
  _BYTE v25[8]; // [rsp+60h] [rbp-20h] BYREF
  void *Src; // [rsp+68h] [rbp-18h]
  char *v27; // [rsp+70h] [rbp-10h]
  char v28; // [rsp+B0h] [rbp+30h] BYREF

  v8 = a1[12] + a1[9] - 1LL - (unsigned __int64)(a1[9] - 1LL) % a1[12];
  Kerb3961::MakeBuffer(&v19);
  v10 = (int)v21;
  if ( (int)v21 >= 0 )
  {
    Kerb3961::MakeBuffer(v22);
    v12 = (int)v24;
    if ( (int)v24 >= 0 )
    {
      Kerb3961::Nfold((__int64)v25, a1[12], a4);
      v14 = (int)v27;
      if ( (int)v27 >= 0 )
      {
        v15 = 0;
        if ( v8 )
        {
          while ( 1 )
          {
            memset(v23, 0, a1[12]);
            v17 = *(_DWORD *)(*(__int64 (__fastcall **)(_QWORD *, char *, __int64, _BYTE *, _BYTE *))(*a1 + 432LL))(
                               a1,
                               &v28,
                               a3,
                               v22,
                               v25);
            if ( v17 < 0 )
              break;
            memmove((void *)(v15 + v20), Src, a1[12]);
            v15 += a1[12];
            if ( v15 >= v8 )
              goto LABEL_10;
          }
          Kerb3961::Logging::Verify::StatusFailed(
            (Kerb3961::Logging::Verify *)"BlockEncrypt(baseKey, IV, nfoldConstant)",
            (const char *)(unsigned int)v17,
            v16);
          *(_QWORD *)a2 = 0;
          *(_QWORD *)(a2 + 8) = 0;
          *(_DWORD *)(a2 + 16) = v17;
        }
        else
        {
LABEL_10:
          v19 = a1[9];
          (*(void (__fastcall **)(_QWORD *, __int64, __int64 *))(*a1 + 128LL))(a1, a2, &v19);
        }
      }
      else
      {
        Kerb3961::Logging::Verify::StatusFailed(
          (Kerb3961::Logging::Verify *)"nfoldConstant",
          (const char *)(unsigned int)v27,
          v13);
        *(_QWORD *)a2 = 0;
        *(_QWORD *)(a2 + 8) = 0;
        *(_DWORD *)(a2 + 16) = v14;
      }
      if ( Src )
        Kerb3961Free(Src);
    }
    else
    {
      Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)"IV", (const char *)(unsigned int)v24, v11);
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = v12;
    }
    if ( v23 )
      Kerb3961Free(v23);
  }
  else
  {
    Kerb3961::Logging::Verify::StatusFailed(
      (Kerb3961::Logging::Verify *)"workSpace",
      (const char *)(unsigned int)v21,
      v9);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = v10;
  }
  if ( v20 )
    Kerb3961Free(v20);
  return a2;
}

```

## disassembly

```asm
0x1800041a0  mov     [rsp-28h+arg_8], rbx
0x1800041a5  mov     [rsp-28h+arg_10], rsi
0x1800041aa  push    rbp
0x1800041ab  push    rdi
0x1800041ac  push    r12
0x1800041ae  push    r14
0x1800041b0  push    r15
0x1800041b2  mov     rbp, rsp
0x1800041b5  sub     rsp, 80h
0x1800041bc  mov     r10, [rcx+60h]
0x1800041c0  mov     rbx, rdx
0x1800041c3  mov     r14, [rcx+48h]
0x1800041c7  xor     edx, edx
0x1800041c9  dec     r14
0x1800041cc  mov     rdi, rcx
0x1800041cf  mov     rax, r14
0x1800041d2  lea     rcx, [rbp+var_50]
0x1800041d6  div     r10
0x1800041d9  mov     r15, r9
0x1800041dc  mov     r12, r8
0x1800041df  sub     r14, rdx
0x1800041e2  add     r14, r10
0x1800041e5  mov     rdx, r14
0x1800041e8  call    ?MakeBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@_K@Z; Kerb3961::MakeBuffer(unsigned __int64)
0x1800041ed  mov     esi, dword ptr [rbp+var_40]
0x1800041f0  test    esi, esi
0x1800041f2  jns     short loc_180004219
0x1800041f4  mov     edx, esi; char *
0x1800041f6  lea     rcx, aWorkspace; "workSpace"
0x1800041fd  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180004202  mov     qword ptr [rbx], 0
0x180004209  mov     qword ptr [rbx+8], 0
0x180004211  mov     [rbx+10h], esi
0x180004214  jmp     loc_180004330
0x180004219  mov     rdx, [rdi+60h]
0x18000421d  lea     rcx, [rbp+var_38]
0x180004221  call    ?MakeBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@_K@Z; Kerb3961::MakeBuffer(unsigned __int64)
0x180004226  mov     esi, dword ptr [rbp+var_28]
0x180004229  test    esi, esi
0x18000422b  jns     short loc_180004252
0x18000422d  mov     edx, esi; char *
0x18000422f  lea     rcx, aIv; "IV"
0x180004236  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000423b  mov     qword ptr [rbx], 0
0x180004242  mov     qword ptr [rbx+8], 0
0x18000424a  mov     [rbx+10h], esi
0x18000424d  jmp     loc_180004322
0x180004252  mov     rdx, [rdi+60h]
0x180004256  lea     rcx, [rbp+var_20]
0x18000425a  mov     r8, r15
0x18000425d  call    ?Nfold@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@_KAEBUReadOnlyBinary@1@@Z; Kerb3961::Nfold(unsigned __int64,Kerb3961::ReadOnlyBinary const &)
0x180004262  mov     esi, dword ptr [rbp+var_10]
0x180004265  test    esi, esi
0x180004267  jns     short loc_18000428E
0x180004269  mov     edx, esi; char *
0x18000426b  lea     rcx, aNfoldconstant; "nfoldConstant"
0x180004272  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180004277  mov     qword ptr [rbx], 0
0x18000427e  mov     qword ptr [rbx+8], 0
0x180004286  mov     [rbx+10h], esi
0x180004289  jmp     loc_180004314
0x18000428e  xor     esi, esi
0x180004290  test    r14, r14
0x180004293  jz      short loc_1800042F3
0x180004295  mov     r8, [rdi+60h]; Size
0x180004299  xor     edx, edx; Val
0x18000429b  mov     rcx, [rbp+var_30]; void *
0x18000429f  call    memset
0x1800042a4  mov     rax, [rdi]
0x1800042a7  lea     rcx, [rbp+var_20]
0x1800042ab  mov     [rsp+80h+var_60], rcx
0x1800042b0  lea     r9, [rbp+var_38]
0x1800042b4  mov     r8, r12
0x1800042b7  lea     rdx, [rbp+arg_0]
0x1800042bb  mov     rcx, rdi
0x1800042be  mov     rax, [rax+1B0h]
0x1800042c5  call    _guard_dispatch_icall
0x1800042ca  mov     r15d, [rax]
0x1800042cd  test    r15d, r15d
0x1800042d0  js      loc_18000435E
0x1800042d6  mov     rcx, [rbp+var_48]
0x1800042da  mov     r8, [rdi+60h]; Size
0x1800042de  add     rcx, rsi; void *
0x1800042e1  mov     rdx, [rbp+Src]; Src
0x1800042e5  call    memmove
0x1800042ea  add     rsi, [rdi+60h]
0x1800042ee  cmp     rsi, r14
0x1800042f1  jb      short loc_180004295
0x1800042f3  mov     rax, [rdi+48h]
0x1800042f7  lea     r8, [rbp+var_50]
0x1800042fb  mov     [rbp+var_50], rax
0x1800042ff  mov     rdx, rbx
0x180004302  mov     rax, [rdi]
0x180004305  mov     rcx, rdi
0x180004308  mov     rax, [rax+80h]
0x18000430f  call    _guard_dispatch_icall
0x180004314  mov     rcx, [rbp+Src]
0x180004318  test    rcx, rcx
0x18000431b  jz      short loc_180004322
0x18000431d  call    Kerb3961Free
0x180004322  mov     rcx, [rbp+var_30]
0x180004326  test    rcx, rcx
0x180004329  jz      short loc_180004330
0x18000432b  call    Kerb3961Free
0x180004330  mov     rcx, [rbp+var_48]
0x180004334  test    rcx, rcx
0x180004337  jz      short loc_18000433E
0x180004339  call    Kerb3961Free
0x18000433e  lea     r11, [rsp+80h+var_s0]
0x180004346  mov     rax, rbx
0x180004349  mov     rbx, [r11+38h]
0x18000434d  mov     rsi, [r11+40h]
0x180004351  mov     rsp, r11
0x180004354  pop     r15
0x180004356  pop     r14
0x180004358  pop     r12
0x18000435a  pop     rdi
0x18000435b  pop     rbp
0x18000435c  retn
0x18000435e  mov     edx, r15d; char *
0x180004361  lea     rcx, aBlockencryptBa; "BlockEncrypt(baseKey, IV, nfoldConstant"...
0x180004368  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000436d  mov     qword ptr [rbx], 0
0x180004374  mov     qword ptr [rbx+8], 0
0x18000437c  mov     [rbx+10h], r15d
0x180004380  jmp     short loc_180004314
```
