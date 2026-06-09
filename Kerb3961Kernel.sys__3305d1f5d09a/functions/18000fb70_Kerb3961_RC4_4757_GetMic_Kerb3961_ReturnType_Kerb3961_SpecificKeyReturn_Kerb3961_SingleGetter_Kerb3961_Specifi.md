# Kerb3961::RC4_4757::GetMic(Kerb3961::ReturnType<Kerb3961::SpecificKeyReturn,&Kerb3961::SingleGetter<Kerb3961::SpecificKeyReturn,16>(Kerb3961::SpecificKeyReturn const &),&Kerb3961::SingleSetter<Kerb3961::SpecificKeyReturn,16>(Kerb3961::SpecificKeyReturn &)> &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x18000fb70`
- end: `0x18000fd47`
- name: `?GetMic@RC4_4757@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEAU?$ReturnType@USpecificKeyReturn@Kerb3961@@$1??$SingleGetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@@Z`
- size: `471`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180003910`
- `0x18000fb70`
- `0x18000fd70`
- `0x18000fe44`
- `0x180011760`
- `0x1800118cc`
- `0x180011b40`
- `0x180012200`

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
  __int64 v20; // [rsp+48h] [rbp-11h]
  char *v21; // [rsp+50h] [rbp-9h]
  _BYTE v22[8]; // [rsp+58h] [rbp-1h] BYREF
  __int64 v23; // [rsp+60h] [rbp+7h]
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
            Kerb3961Free(*((_QWORD *)&v17 + 1));
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
          Kerb3961Free(v23);
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
      Kerb3961Free(v20);
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
0x18000fb70  push    rbp
0x18000fb72  push    rsi
0x18000fb73  push    rdi
0x18000fb74  push    r14
0x18000fb76  push    r15
0x18000fb78  lea     rbp, [rsp-37h]
0x18000fb7d  sub     rsp, 90h
0x18000fb84  mov     rax, cs:__security_cookie
0x18000fb8b  xor     rax, rsp
0x18000fb8e  mov     [rbp+57h+var_30], rax
0x18000fb92  lea     r14, [rcx-8]
0x18000fb96  mov     r15, r9
0x18000fb99  mov     rdi, rdx
0x18000fb9c  cmp     r14, [r8]
0x18000fb9f  jz      short loc_18000FBC8
0x18000fba1  lea     rcx, aThisSpecificke; "this == specificKey.algorithm"
0x18000fba8  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000fbad  mov     qword ptr [rdi], 0
0x18000fbb4  mov     qword ptr [rdi+8], 0
0x18000fbbc  mov     dword ptr [rdi+10h], 0C000000Dh
0x18000fbc3  jmp     loc_18000FD28
0x18000fbc8  mov     r8, [r8+8]
0x18000fbcc  lea     r9, [rbp+57h+var_88]
0x18000fbd0  lea     rdx, [rbp+57h+var_70]
0x18000fbd4  mov     [rbp+57h+var_88], 0Dh
0x18000fbdc  mov     rcx, r14
0x18000fbdf  mov     eax, [r8+18h]
0x18000fbe3  mov     [rbp+57h+var_90], eax
0x18000fbe6  lea     rax, [rbp+57h+var_40]
0x18000fbea  mov     [rbp+57h+var_80], rax
0x18000fbee  mov     dword ptr [rbp+57h+var_40], 6E676973h
0x18000fbf5  mov     dword ptr [rbp+57h+var_40+4], 72757461h
0x18000fbfc  mov     dword ptr [rbp+57h+var_40+8], 79656B65h
0x18000fc03  mov     [rbp+57h+var_40+0Ch], 0
0x18000fc07  call    ?HmacData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::RC4_4757::HmacData(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x18000fc0c  mov     esi, dword ptr [rbp+57h+var_60]
0x18000fc0f  test    esi, esi
0x18000fc11  jns     short loc_18000FC38
0x18000fc13  mov     edx, esi; char *
0x18000fc15  lea     rcx, aKsign; "Ksign"
0x18000fc1c  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000fc21  mov     qword ptr [rdi], 0
0x18000fc28  mov     qword ptr [rdi+8], 0
0x18000fc30  mov     [rdi+10h], esi
0x18000fc33  jmp     loc_18000FD1A
0x18000fc38  mov     eax, 0FFFFFFFBh
0x18000fc3d  cmp     [r15], rax
0x18000fc40  jbe     short loc_18000FC69
0x18000fc42  lea     rcx, aMessageLengthU; "message.length <= utl::numeric_limits<u"...
0x18000fc49  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000fc4e  mov     qword ptr [rdi], 0
0x18000fc55  mov     qword ptr [rdi+8], 0
0x18000fc5d  mov     dword ptr [rdi+10h], 0C000000Dh
0x18000fc64  jmp     loc_18000FD1A
0x18000fc69  lea     rax, [rbp+57h+var_90]
0x18000fc6d  mov     [rbp+57h+var_88], 4
0x18000fc75  mov     r8, r15
0x18000fc78  mov     [rbp+57h+var_80], rax
0x18000fc7c  lea     rdx, [rbp+57h+var_88]
0x18000fc80  lea     rcx, [rbp+57h+var_58]
0x18000fc84  call    ?Concatenate@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@0@Z; Kerb3961::Concatenate(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x18000fc89  mov     esi, dword ptr [rbp+57h+var_48]
0x18000fc8c  test    esi, esi
0x18000fc8e  jns     short loc_18000FCB2
0x18000fc90  mov     edx, esi; char *
0x18000fc92  lea     rcx, aHashdata; "hashData"
0x18000fc99  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000fc9e  mov     qword ptr [rdi], 0
0x18000fca5  mov     qword ptr [rdi+8], 0
0x18000fcad  mov     [rdi+10h], esi
0x18000fcb0  jmp     short loc_18000FD0C
0x18000fcb2  lea     r8, [rbp+57h+var_58]
0x18000fcb6  mov     rcx, r14
0x18000fcb9  lea     rdx, [rbp+57h+var_88]
0x18000fcbd  call    ?HashData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@@Z; Kerb3961::RC4_4757::HashData(Kerb3961::ReadOnlyBinary const &)
0x18000fcc2  mov     esi, dword ptr [rbp+57h+var_78]
0x18000fcc5  test    esi, esi
0x18000fcc7  jns     short loc_18000FCEB
0x18000fcc9  mov     edx, esi; char *
0x18000fccb  lea     rcx, aTmp; "tmp"
0x18000fcd2  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000fcd7  mov     qword ptr [rdi], 0
0x18000fcde  mov     qword ptr [rdi+8], 0
0x18000fce6  mov     [rdi+10h], esi
0x18000fce9  jmp     short loc_18000FCFE
0x18000fceb  lea     r9, [rbp+57h+var_88]
0x18000fcef  mov     rdx, rdi
0x18000fcf2  lea     r8, [rbp+57h+var_70]
0x18000fcf6  mov     rcx, r14
0x18000fcf9  call    ?HmacData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::RC4_4757::HmacData(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x18000fcfe  mov     rcx, [rbp+57h+var_80]
0x18000fd02  test    rcx, rcx
0x18000fd05  jz      short loc_18000FD0C
0x18000fd07  call    Kerb3961Free
0x18000fd0c  mov     rcx, [rbp+57h+var_50]
0x18000fd10  test    rcx, rcx
0x18000fd13  jz      short loc_18000FD1A
0x18000fd15  call    Kerb3961Free
0x18000fd1a  mov     rcx, [rbp+57h+var_68]
0x18000fd1e  test    rcx, rcx
0x18000fd21  jz      short loc_18000FD28
0x18000fd23  call    Kerb3961Free
0x18000fd28  mov     rax, rdi
0x18000fd2b  mov     rcx, [rbp+57h+var_30]
0x18000fd2f  xor     rcx, rsp; StackCookie
0x18000fd32  call    __security_check_cookie
0x18000fd37  add     rsp, 90h
0x18000fd3e  pop     r15
0x18000fd40  pop     r14
0x18000fd42  pop     rdi
0x18000fd43  pop     rsi
0x18000fd44  pop     rbp
0x18000fd45  retn
```
