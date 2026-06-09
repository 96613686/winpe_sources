# Kerb3961::Aes8009::DeriveKey(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,unsigned __int64)

- ea: `0x180012ab8`
- end: `0x180012c2f`
- name: `?DeriveKey@Aes8009@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@00_K@Z`
- size: `375`
- prototype: ``
- caller_count: `5`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800126e0`
- `0x180012c40`
- `0x1800130b0`
- `0x180014d90`
- `0x180016e60`

## callees

- `0x180001d64`
- `0x180002c64`
- `0x180002fc0`
- `0x18000f908`
- `0x18000fc10`
- `0x180012ab8`

## pseudocode

```c
__int64 __fastcall Kerb3961::Aes8009::DeriveKey(
        __int64 a1,
        __int64 a2,
        int a3,
        __int128 *a4,
        __int128 *a5,
        unsigned __int64 a6)
{
  unsigned __int64 v7; // r14
  __int128 v10; // xmm2
  __int128 v11; // xmm1
  int v12; // eax
  int v13; // r8d
  int v14; // esi
  void *v15; // rcx
  unsigned __int32 v17; // [rsp+30h] [rbp-D0h] BYREF
  char v18; // [rsp+38h] [rbp-C8h] BYREF
  void *v19; // [rsp+40h] [rbp-C0h]
  char *v20; // [rsp+48h] [rbp-B8h]
  __int128 v21; // [rsp+50h] [rbp-B0h]
  __int128 v22; // [rsp+70h] [rbp-90h]
  __int128 v23; // [rsp+90h] [rbp-70h]
  _BYTE v24[8]; // [rsp+A0h] [rbp-60h] BYREF
  void *v25; // [rsp+A8h] [rbp-58h]
  _OWORD v26[5]; // [rsp+C0h] [rbp-40h] BYREF
  int v27; // [rsp+130h] [rbp+30h] BYREF

  v7 = a6;
  if ( a6 <= *(unsigned int *)(a1 + 160) )
  {
    v10 = *a4;
    *(_QWORD *)&v22 = 1;
    *(_QWORD *)&v21 = 4;
    v17 = _byteswap_ulong(8 * a6);
    *(_QWORD *)&v23 = 4;
    *((_QWORD *)&v21 + 1) = &v27;
    *((_QWORD *)&v22 + 1) = &a6;
    v26[0] = v21;
    v26[2] = v22;
    v11 = *a5;
    v27 = 0x1000000;
    *((_QWORD *)&v23 + 1) = &v17;
    v26[4] = v23;
    LOBYTE(a6) = 0;
    v26[1] = v10;
    v26[3] = v11;
    v12 = Kerb3961::Concatenate<5>(v24, v26);
    Kerb3961::GetHmac((unsigned int)&v18, *(_QWORD *)(a1 + 152), a3, v12, *(unsigned int *)(a1 + 160));
    if ( v25 )
      operator delete(v25, 0);
    v14 = (int)v20;
    if ( (int)v20 >= 0 )
    {
      *(_QWORD *)(a2 + 8) = v19;
      *(_DWORD *)(a2 + 16) = v14;
      *(_QWORD *)a2 = v7;
    }
    else
    {
      Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)"hmac", (const char *)(unsigned int)v20, v13);
      v15 = v19;
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = v14;
      if ( v15 )
        operator delete(v15, 0);
    }
  }
  else
  {
    Kerb3961::Logging::Verify::ConditionFailed(
      (Kerb3961::Logging::Verify *)"resultSize <= m_checksumLength",
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
0x180012ab8  mov     [rsp-8+arg_8], rbx
0x180012abd  mov     [rsp-8+arg_10], rsi
0x180012ac2  push    rbp
0x180012ac3  push    r14
0x180012ac5  push    r15
0x180012ac7  lea     rbp, [rsp-10h]
0x180012acc  sub     rsp, 110h
0x180012ad3  mov     eax, [rcx+0A0h]
0x180012ad9  mov     r15, r8
0x180012adc  mov     r14, [rbp+20h+arg_28]
0x180012ae0  mov     rbx, rdx
0x180012ae3  mov     rsi, rcx
0x180012ae6  cmp     r14, rax
0x180012ae9  jbe     short loc_180012B12
0x180012aeb  lea     rcx, aResultsizeMChe; "resultSize <= m_checksumLength"
0x180012af2  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180012af7  mov     qword ptr [rbx], 0
0x180012afe  mov     qword ptr [rbx+8], 0
0x180012b06  mov     dword ptr [rbx+10h], 0C000000Dh
0x180012b0d  jmp     loc_180012C13
0x180012b12  movups  xmm2, xmmword ptr [r9]
0x180012b16  mov     ecx, 4
0x180012b1b  mov     qword ptr [rsp+120h+var_B0], 1
0x180012b24  mov     qword ptr [rsp+120h+var_D0], rcx
0x180012b29  lea     eax, ds:0[r14*8]
0x180012b31  bswap   eax
0x180012b33  mov     [rsp+120h+var_F0], eax
0x180012b37  lea     rdx, [rbp+20h+var_60]
0x180012b3b  mov     qword ptr [rbp+20h+var_90], rcx
0x180012b3f  lea     rax, [rbp+20h+arg_0]
0x180012b43  mov     qword ptr [rsp+120h+var_D0+8], rax
0x180012b48  lea     rcx, [rbp+20h+var_80]
0x180012b4c  movaps  xmm0, [rsp+120h+var_D0]
0x180012b51  lea     rax, [rbp+20h+arg_28]
0x180012b55  mov     qword ptr [rsp+120h+var_B0+8], rax
0x180012b5a  mov     rax, [rbp+20h+arg_20]
0x180012b5e  movaps  [rbp+20h+var_60], xmm0
0x180012b62  movaps  xmm0, [rsp+120h+var_B0]
0x180012b67  movaps  [rbp+20h+var_40], xmm0
0x180012b6b  movups  xmm1, xmmword ptr [rax]
0x180012b6e  lea     rax, [rsp+120h+var_F0]
0x180012b73  mov     [rbp+20h+arg_0], 1000000h
0x180012b7a  mov     qword ptr [rbp+20h+var_90+8], rax
0x180012b7e  movaps  xmm0, [rbp+20h+var_90]
0x180012b82  movaps  [rbp+20h+var_20], xmm0
0x180012b86  mov     byte ptr [rbp+20h+arg_28], 0
0x180012b8a  movaps  [rbp+20h+var_50], xmm2
0x180012b8e  movaps  [rbp+20h+var_30], xmm1
0x180012b92  call    ??$Concatenate@$04@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@0@U?$array@$$CBUReadOnlyBinary@Kerb3961@@$04@utl@@@Z; Kerb3961::Concatenate<5>(utl::array<Kerb3961::ReadOnlyBinary const,5>)
0x180012b97  mov     ecx, [rsi+0A0h]
0x180012b9d  mov     r9, rax
0x180012ba0  mov     rdx, [rsi+98h]
0x180012ba7  mov     r8, r15
0x180012baa  mov     [rsp+120h+var_100], rcx
0x180012baf  lea     rcx, [rsp+120h+var_E8]
0x180012bb4  call    ?GetHmac@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@PEAXAEBUReadOnlyBinary@1@1_K@Z; Kerb3961::GetHmac(void *,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,unsigned __int64)
0x180012bb9  mov     rcx, [rbp+20h+var_78]; void *
0x180012bbd  test    rcx, rcx
0x180012bc0  jz      short loc_180012BC9
0x180012bc2  xor     edx, edx; struct std::nothrow_t *
0x180012bc4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180012bc9  mov     esi, dword ptr [rsp+120h+var_D8]
0x180012bcd  test    esi, esi
0x180012bcf  jns     short loc_180012C04
0x180012bd1  mov     edx, esi; char *
0x180012bd3  lea     rcx, aHmac; "hmac"
0x180012bda  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180012bdf  mov     rcx, [rsp+120h+var_E0]; void *
0x180012be4  mov     qword ptr [rbx], 0
0x180012beb  mov     qword ptr [rbx+8], 0
0x180012bf3  mov     [rbx+10h], esi
0x180012bf6  test    rcx, rcx
0x180012bf9  jz      short loc_180012C13
0x180012bfb  xor     edx, edx; struct std::nothrow_t *
0x180012bfd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180012c02  jmp     short loc_180012C13
0x180012c04  mov     rax, [rsp+120h+var_E0]
0x180012c09  mov     [rbx+8], rax
0x180012c0d  mov     [rbx+10h], esi
0x180012c10  mov     [rbx], r14
0x180012c13  lea     r11, [rsp+120h+var_10]
0x180012c1b  mov     rax, rbx
0x180012c1e  mov     rbx, [r11+28h]
0x180012c22  mov     rsi, [r11+30h]
0x180012c26  mov     rsp, r11
0x180012c29  pop     r15
0x180012c2b  pop     r14
0x180012c2d  pop     rbp
0x180012c2e  retn
```
