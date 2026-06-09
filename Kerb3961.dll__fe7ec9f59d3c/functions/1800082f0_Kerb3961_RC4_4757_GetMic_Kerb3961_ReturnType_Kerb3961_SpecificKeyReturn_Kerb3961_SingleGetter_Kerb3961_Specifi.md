# Kerb3961::RC4_4757::GetMic(Kerb3961::ReturnType<Kerb3961::SpecificKeyReturn,&Kerb3961::SingleGetter<Kerb3961::SpecificKeyReturn,16>(Kerb3961::SpecificKeyReturn const &),&Kerb3961::SingleSetter<Kerb3961::SpecificKeyReturn,16>(Kerb3961::SpecificKeyReturn &)> &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x1800082f0`
- end: `0x1800084cc`
- name: `?GetMic@RC4_4757@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEAU?$ReturnType@USpecificKeyReturn@Kerb3961@@$1??$SingleGetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@@Z`
- size: `476`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001d40`
- `0x180001d64`
- `0x180002c64`
- `0x180002fc0`
- `0x18000700c`
- `0x1800082f0`
- `0x180008500`
- `0x1800085cc`

## pseudocode

```c
__int64 __fastcall Kerb3961::RC4_4757::GetMic(__int64 a1, __int64 a2, _QWORD *a3, __int128 *a4)
{
  __int64 v4; // r14
  __int64 v7; // r8
  const char *v8; // rdx
  int v9; // r8d
  int v10; // esi
  int v11; // r8d
  int v12; // esi
  int v13; // r8d
  int v14; // esi
  int v16; // [rsp+20h] [rbp-39h] BYREF
  __int128 v17; // [rsp+28h] [rbp-31h] BYREF
  char *v18; // [rsp+38h] [rbp-21h]
  __int64 v19; // [rsp+40h] [rbp-19h] BYREF
  void *v20; // [rsp+48h] [rbp-11h]
  char *v21; // [rsp+50h] [rbp-9h]
  _BYTE v22[8]; // [rsp+58h] [rbp-1h] BYREF
  void *v23; // [rsp+60h] [rbp+7h]
  char *v24; // [rsp+68h] [rbp+Fh]
  char v25[16]; // [rsp+70h] [rbp+17h] BYREF

  v4 = a1 - 8;
  if ( a1 - 8 == *a3 )
  {
    v7 = a3[1];
    *(_QWORD *)&v17 = 13;
    v16 = *(_DWORD *)(v7 + 24);
    *((_QWORD *)&v17 + 1) = v25;
    strcpy(v25, "signaturekey");
    Kerb3961::RC4_4757::HmacData(a1 - 8, (__int64)&v19, (_QWORD *)v7, (__int64)&v17);
    v10 = (int)v21;
    if ( (int)v21 >= 0 )
    {
      if ( *(_QWORD *)a4 <= 0xFFFFFFFB )
      {
        *(_QWORD *)&v17 = 4;
        *((_QWORD *)&v17 + 1) = &v16;
        Kerb3961::Concatenate((__int64)v22, &v17, a4);
        v12 = (int)v24;
        if ( (int)v24 >= 0 )
        {
          Kerb3961::RC4_4757::HashData(v4, (__int64)&v17, (__int64)v22);
          v14 = (int)v18;
          if ( (int)v18 >= 0 )
          {
            Kerb3961::RC4_4757::HmacData(v4, a2, &v19, (__int64)&v17);
          }
          else
          {
            Kerb3961::Logging::Verify::StatusFailed(
              (Kerb3961::Logging::Verify *)"tmp",
              (const char *)(unsigned int)v18,
              v13);
            *(_QWORD *)a2 = 0;
            *(_QWORD *)(a2 + 8) = 0;
            *(_DWORD *)(a2 + 16) = v14;
          }
          if ( *((_QWORD *)&v17 + 1) )
            operator delete(*((void **)&v17 + 1), 0);
        }
        else
        {
          Kerb3961::Logging::Verify::StatusFailed(
            (Kerb3961::Logging::Verify *)"hashData",
            (const char *)(unsigned int)v24,
            v11);
          *(_QWORD *)a2 = 0;
          *(_QWORD *)(a2 + 8) = 0;
          *(_DWORD *)(a2 + 16) = v12;
        }
        if ( v23 )
          operator delete(v23, 0);
      }
      else
      {
        Kerb3961::Logging::Verify::ConditionFailed(
          (Kerb3961::Logging::Verify *)"message.length <= utl::numeric_limits<uint32_t>::max() - sizeof(uint32_t)",
          v8);
        *(_QWORD *)a2 = 0;
        *(_QWORD *)(a2 + 8) = 0;
        *(_DWORD *)(a2 + 16) = -1073741811;
      }
    }
    else
    {
      Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)"Ksign", (const char *)(unsigned int)v21, v9);
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = v10;
    }
    if ( v20 )
      operator delete(v20, 0);
  }
  else
  {
    Kerb3961::Logging::Verify::ConditionFailed(
      (Kerb3961::Logging::Verify *)"this == specificKey.algorithm",
      (const char *)a2);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = -1073741811;
  }
  return a2;
}

```

## disassembly

```asm
0x1800082f0  push    rbp
0x1800082f2  push    rsi
0x1800082f3  push    rdi
0x1800082f4  push    r14
0x1800082f6  push    r15
0x1800082f8  lea     rbp, [rsp-37h]
0x1800082fd  sub     rsp, 90h
0x180008304  mov     rax, cs:__security_cookie
0x18000830b  xor     rax, rsp
0x18000830e  mov     [rbp+57h+var_30], rax
0x180008312  lea     r14, [rcx-8]
0x180008316  mov     r15, r9
0x180008319  mov     rdi, rdx
0x18000831c  cmp     r14, [r8]
0x18000831f  jz      short loc_180008348
0x180008321  lea     rcx, aThisSpecificke; "this == specificKey.algorithm"
0x180008328  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000832d  mov     qword ptr [rdi], 0
0x180008334  mov     qword ptr [rdi+8], 0
0x18000833c  mov     dword ptr [rdi+10h], 0C000000Dh
0x180008343  jmp     loc_1800084AE
0x180008348  mov     r8, [r8+8]
0x18000834c  lea     r9, [rbp+57h+var_88]
0x180008350  lea     rdx, [rbp+57h+var_70]
0x180008354  mov     [rbp+57h+var_88], 0Dh
0x18000835c  mov     rcx, r14
0x18000835f  mov     eax, [r8+18h]
0x180008363  mov     [rbp+57h+var_90], eax
0x180008366  lea     rax, [rbp+57h+var_40]
0x18000836a  mov     [rbp+57h+var_80], rax
0x18000836e  mov     dword ptr [rbp+57h+var_40], 6E676973h
0x180008375  mov     dword ptr [rbp+57h+var_40+4], 72757461h
0x18000837c  mov     dword ptr [rbp+57h+var_40+8], 79656B65h
0x180008383  mov     [rbp+57h+var_40+0Ch], 0
0x180008387  call    ?HmacData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::RC4_4757::HmacData(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x18000838c  mov     esi, dword ptr [rbp+57h+var_60]
0x18000838f  test    esi, esi
0x180008391  jns     short loc_1800083B8
0x180008393  mov     edx, esi; char *
0x180008395  lea     rcx, aKsign; "Ksign"
0x18000839c  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800083a1  mov     qword ptr [rdi], 0
0x1800083a8  mov     qword ptr [rdi+8], 0
0x1800083b0  mov     [rdi+10h], esi
0x1800083b3  jmp     loc_18000849E
0x1800083b8  mov     eax, 0FFFFFFFBh
0x1800083bd  cmp     [r15], rax
0x1800083c0  jbe     short loc_1800083E9
0x1800083c2  lea     rcx, aMessageLengthU; "message.length <= utl::numeric_limits<u"...
0x1800083c9  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x1800083ce  mov     qword ptr [rdi], 0
0x1800083d5  mov     qword ptr [rdi+8], 0
0x1800083dd  mov     dword ptr [rdi+10h], 0C000000Dh
0x1800083e4  jmp     loc_18000849E
0x1800083e9  lea     rax, [rbp+57h+var_90]
0x1800083ed  mov     [rbp+57h+var_88], 4
0x1800083f5  mov     r8, r15
0x1800083f8  mov     [rbp+57h+var_80], rax
0x1800083fc  lea     rdx, [rbp+57h+var_88]
0x180008400  lea     rcx, [rbp+57h+var_58]
0x180008404  call    ?Concatenate@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@0@Z; Kerb3961::Concatenate(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x180008409  mov     esi, dword ptr [rbp+57h+var_48]
0x18000840c  test    esi, esi
0x18000840e  jns     short loc_180008432
0x180008410  mov     edx, esi; char *
0x180008412  lea     rcx, aHashdata; "hashData"
0x180008419  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000841e  mov     qword ptr [rdi], 0
0x180008425  mov     qword ptr [rdi+8], 0
0x18000842d  mov     [rdi+10h], esi
0x180008430  jmp     short loc_18000848E
0x180008432  lea     r8, [rbp+57h+var_58]
0x180008436  mov     rcx, r14
0x180008439  lea     rdx, [rbp+57h+var_88]
0x18000843d  call    ?HashData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@@Z; Kerb3961::RC4_4757::HashData(Kerb3961::ReadOnlyBinary const &)
0x180008442  mov     esi, dword ptr [rbp+57h+var_78]
0x180008445  test    esi, esi
0x180008447  jns     short loc_18000846B
0x180008449  mov     edx, esi; char *
0x18000844b  lea     rcx, aTmp; "tmp"
0x180008452  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180008457  mov     qword ptr [rdi], 0
0x18000845e  mov     qword ptr [rdi+8], 0
0x180008466  mov     [rdi+10h], esi
0x180008469  jmp     short loc_18000847E
0x18000846b  lea     r9, [rbp+57h+var_88]
0x18000846f  mov     rdx, rdi
0x180008472  lea     r8, [rbp+57h+var_70]
0x180008476  mov     rcx, r14
0x180008479  call    ?HmacData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::RC4_4757::HmacData(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x18000847e  mov     rcx, [rbp+57h+var_80]; void *
0x180008482  test    rcx, rcx
0x180008485  jz      short loc_18000848E
0x180008487  xor     edx, edx; struct std::nothrow_t *
0x180008489  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000848e  mov     rcx, [rbp+57h+var_50]; void *
0x180008492  test    rcx, rcx
0x180008495  jz      short loc_18000849E
0x180008497  xor     edx, edx; struct std::nothrow_t *
0x180008499  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000849e  mov     rcx, [rbp+57h+var_68]; void *
0x1800084a2  test    rcx, rcx
0x1800084a5  jz      short loc_1800084AE
0x1800084a7  xor     edx, edx; struct std::nothrow_t *
0x1800084a9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800084ae  mov     rax, rdi
0x1800084b1  mov     rcx, [rbp+57h+var_30]
0x1800084b5  xor     rcx, rsp; StackCookie
0x1800084b8  call    __security_check_cookie
0x1800084bd  add     rsp, 90h
0x1800084c4  pop     r15
0x1800084c6  pop     r14
0x1800084c8  pop     rdi
0x1800084c9  pop     rsi
0x1800084ca  pop     rbp
0x1800084cb  retn
```
