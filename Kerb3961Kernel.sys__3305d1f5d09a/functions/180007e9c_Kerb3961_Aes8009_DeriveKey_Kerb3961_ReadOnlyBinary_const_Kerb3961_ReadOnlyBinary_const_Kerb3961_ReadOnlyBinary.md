# Kerb3961::Aes8009::DeriveKey(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,unsigned __int64)

- ea: `0x180007e9c`
- end: `0x180008010`
- name: `?DeriveKey@Aes8009@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@00_K@Z`
- size: `372`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: ``

## callers

- `0x180007ad0`
- `0x180008020`
- `0x1800083f0`
- `0x180008f50`

## callees

- `0x180006cc8`
- `0x180007e9c`
- `0x18000a6c0`
- `0x180011760`
- `0x1800118cc`
- `0x180011b40`

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
  __int64 v15; // rcx
  unsigned __int32 v17; // [rsp+30h] [rbp-D0h] BYREF
  char v18; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v19; // [rsp+40h] [rbp-C0h]
  char *v20; // [rsp+48h] [rbp-B8h]
  __int128 v21; // [rsp+50h] [rbp-B0h]
  __int128 v22; // [rsp+70h] [rbp-90h]
  __int128 v23; // [rsp+90h] [rbp-70h]
  _BYTE v24[8]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v25; // [rsp+A8h] [rbp-58h]
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
      Kerb3961Free(v25);
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
        Kerb3961Free(v15);
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
0x180007e9c  mov     [rsp-8+arg_8], rbx
0x180007ea1  mov     [rsp-8+arg_10], rsi
0x180007ea6  push    rbp
0x180007ea7  push    r14
0x180007ea9  push    r15
0x180007eab  lea     rbp, [rsp-10h]
0x180007eb0  sub     rsp, 110h
0x180007eb7  mov     eax, [rcx+0A0h]
0x180007ebd  mov     r15, r8
0x180007ec0  mov     r14, [rbp+20h+arg_28]
0x180007ec4  mov     rbx, rdx
0x180007ec7  mov     rsi, rcx
0x180007eca  cmp     r14, rax
0x180007ecd  jbe     short loc_180007EF6
0x180007ecf  lea     rcx, aResultsizeMChe; "resultSize <= m_checksumLength"
0x180007ed6  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180007edb  mov     qword ptr [rbx], 0
0x180007ee2  mov     qword ptr [rbx+8], 0
0x180007eea  mov     dword ptr [rbx+10h], 0C000000Dh
0x180007ef1  jmp     loc_180007FF3
0x180007ef6  movups  xmm2, xmmword ptr [r9]
0x180007efa  mov     ecx, 4
0x180007eff  mov     qword ptr [rsp+120h+var_B0], 1
0x180007f08  mov     qword ptr [rsp+120h+var_D0], rcx
0x180007f0d  lea     eax, ds:0[r14*8]
0x180007f15  bswap   eax
0x180007f17  mov     [rsp+120h+var_F0], eax
0x180007f1b  lea     rdx, [rbp+20h+var_60]
0x180007f1f  mov     qword ptr [rbp+20h+var_90], rcx
0x180007f23  lea     rax, [rbp+20h+arg_0]
0x180007f27  mov     qword ptr [rsp+120h+var_D0+8], rax
0x180007f2c  lea     rcx, [rbp+20h+var_80]
0x180007f30  movaps  xmm0, [rsp+120h+var_D0]
0x180007f35  lea     rax, [rbp+20h+arg_28]
0x180007f39  mov     qword ptr [rsp+120h+var_B0+8], rax
0x180007f3e  mov     rax, [rbp+20h+arg_20]
0x180007f42  movaps  [rbp+20h+var_60], xmm0
0x180007f46  movaps  xmm0, [rsp+120h+var_B0]
0x180007f4b  movaps  [rbp+20h+var_40], xmm0
0x180007f4f  movups  xmm1, xmmword ptr [rax]
0x180007f52  lea     rax, [rsp+120h+var_F0]
0x180007f57  mov     [rbp+20h+arg_0], 1000000h
0x180007f5e  mov     qword ptr [rbp+20h+var_90+8], rax
0x180007f62  movaps  xmm0, [rbp+20h+var_90]
0x180007f66  movaps  [rbp+20h+var_20], xmm0
0x180007f6a  mov     byte ptr [rbp+20h+arg_28], 0
0x180007f6e  movaps  [rbp+20h+var_50], xmm2
0x180007f72  movaps  [rbp+20h+var_30], xmm1
0x180007f76  call    ??$Concatenate@$04@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@0@U?$array@$$CBUReadOnlyBinary@Kerb3961@@$04@utl@@@Z; Kerb3961::Concatenate<5>(utl::array<Kerb3961::ReadOnlyBinary const,5>)
0x180007f7b  mov     ecx, [rsi+0A0h]
0x180007f81  mov     r9, rax
0x180007f84  mov     rdx, [rsi+98h]
0x180007f8b  mov     r8, r15
0x180007f8e  mov     [rsp+120h+var_100], rcx
0x180007f93  lea     rcx, [rsp+120h+var_E8]
0x180007f98  call    ?GetHmac@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@PEAXAEBUReadOnlyBinary@1@1_K@Z; Kerb3961::GetHmac(void *,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,unsigned __int64)
0x180007f9d  mov     rcx, [rbp+20h+var_78]
0x180007fa1  test    rcx, rcx
0x180007fa4  jz      short loc_180007FAB
0x180007fa6  call    Kerb3961Free
0x180007fab  mov     esi, dword ptr [rsp+120h+var_D8]
0x180007faf  test    esi, esi
0x180007fb1  jns     short loc_180007FE4
0x180007fb3  mov     edx, esi; char *
0x180007fb5  lea     rcx, aHmac; "hmac"
0x180007fbc  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180007fc1  mov     rcx, [rsp+120h+var_E0]
0x180007fc6  mov     qword ptr [rbx], 0
0x180007fcd  mov     qword ptr [rbx+8], 0
0x180007fd5  mov     [rbx+10h], esi
0x180007fd8  test    rcx, rcx
0x180007fdb  jz      short loc_180007FF3
0x180007fdd  call    Kerb3961Free
0x180007fe2  jmp     short loc_180007FF3
0x180007fe4  mov     rax, [rsp+120h+var_E0]
0x180007fe9  mov     [rbx+8], rax
0x180007fed  mov     [rbx+10h], esi
0x180007ff0  mov     [rbx], r14
0x180007ff3  lea     r11, [rsp+120h+var_10]
0x180007ffb  mov     rax, rbx
0x180007ffe  mov     rbx, [r11+28h]
0x180008002  mov     rsi, [r11+30h]
0x180008006  mov     rsp, r11
0x180008009  pop     r15
0x18000800b  pop     r14
0x18000800d  pop     rbp
0x18000800e  retn
```
