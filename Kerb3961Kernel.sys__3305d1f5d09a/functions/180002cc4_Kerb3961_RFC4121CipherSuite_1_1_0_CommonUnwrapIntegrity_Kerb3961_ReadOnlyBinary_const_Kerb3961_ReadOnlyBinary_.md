# Kerb3961::RFC4121CipherSuite<1,1,0>::CommonUnwrapIntegrity(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x180002cc4`
- end: `0x18000300d`
- name: `?CommonUnwrapIntegrity@?$RFC4121CipherSuite@$00$00$0A@@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@00@Z`
- size: `841`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800025e0`
- `0x1800070e0`

## callees

- `0x180001580`
- `0x180001700`
- `0x1800018e8`
- `0x180002cc4`
- `0x1800037e0`
- `0x180003910`
- `0x180003a38`
- `0x180003a54`
- `0x180011760`
- `0x1800118cc`
- `0x180011b40`
- `0x180012200`
- `0x180012240`

## string_xrefs

- `0x180002db1`: `buffer.length >= checksumSize + WrapHeaderSize`

## pseudocode

```c
__int64 __fastcall Kerb3961::RFC4121CipherSuite<1,1,0>::CommonUnwrapIntegrity(
        _QWORD *a1,
        __int64 a2,
        _QWORD *a3,
        _QWORD *a4,
        __int64 a5)
{
  __int64 v8; // rax
  unsigned __int64 v9; // r8
  unsigned __int64 v10; // rtt
  int v11; // r8d
  int v12; // ebx
  __int64 v13; // rcx
  __int64 v14; // rsi
  unsigned __int64 v15; // rdx
  unsigned __int64 v16; // rax
  __int64 v17; // rbx
  const char *v18; // rdx
  __int64 v19; // r8
  _BYTE *v20; // rdx
  __int64 *v21; // rcx
  char v22; // bl
  __int64 v23; // rax
  int v24; // r8d
  __int64 v25; // rcx
  __int64 v26; // rcx
  int v27; // ebx
  int v28; // r8d
  int v29; // ebx
  char *v30; // rcx
  int v31; // ebx
  const unsigned __int16 *v32; // rdx
  int v34[4]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v35; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v36; // [rsp+48h] [rbp-B8h]
  unsigned __int64 v37; // [rsp+50h] [rbp-B0h]
  __int64 v38; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v39; // [rsp+68h] [rbp-98h]
  char *v40; // [rsp+70h] [rbp-90h]
  char *v41[2]; // [rsp+78h] [rbp-88h] BYREF
  char *v42; // [rsp+88h] [rbp-78h]
  unsigned __int64 v43; // [rsp+90h] [rbp-70h] BYREF
  __int64 v44; // [rsp+98h] [rbp-68h]
  char *v45; // [rsp+A0h] [rbp-60h]
  _BYTE v46[16]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v47[16]; // [rsp+B8h] [rbp-48h] BYREF
  char v48[16]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v49[16]; // [rsp+D8h] [rbp-28h] BYREF
  char v50[16]; // [rsp+E8h] [rbp-18h] BYREF

  v34[0] = 0;
  v8 = a3[1];
  v9 = *a3 - 16LL;
  v35 = 16;
  v10 = (unsigned __int16)__ROR2__(*(_WORD *)(v8 + 6), 8);
  v36 = v10 % v9;
  v37 = v9 - v10 % v9;
  Kerb3961::Split<3>((Kerb3961::ReadOnlyBinary *)v46);
  Kerb3961::Concatenate(&v43, v46, v48, v47);
  v12 = (int)v45;
  if ( (int)v45 >= 0 )
  {
    v14 = v44;
    v15 = (unsigned __int16)__ROR2__(*(_WORD *)(v44 + 4), 8);
    v16 = v43;
    *(_WORD *)(v44 + 6) = 0;
    *(_WORD *)(v14 + 4) = 0;
    if ( v16 < v15 + 16 )
    {
      Kerb3961::Logging::Verify::ConditionFailed(
        (Kerb3961::Logging::Verify *)"buffer.length >= checksumSize + WrapHeaderSize",
        (const char *)v15);
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = -2146893041;
      goto LABEL_32;
    }
    v36 = v15;
    v35 = v16 - v15;
    v17 = v16 - v15 - 16;
    Kerb3961::Split<2>(v49, &v43, &v35);
    v35 = 16;
    v36 = v17;
    Kerb3961::Split<2>(v46, v49, &v35);
    v19 = *a4;
    if ( *a4 && v17 )
    {
      Kerb3961::Logging::Verify::ConditionFailed(
        (Kerb3961::Logging::Verify *)"authData.length == 0 || plaintextSize == 0",
        v18);
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = -2146893046;
      goto LABEL_31;
    }
    v20 = v47;
    v21 = (__int64 *)&v43;
    v22 = (v19 != 0) + 1;
    if ( v19 )
      v20 = a4;
    else
      v21 = &v35;
    v23 = Kerb3961::Concatenate(v21, v20, v46);
    LODWORD(v40) = -1073741823;
    LODWORD(v40) = *(_DWORD *)(v23 + 16);
    v25 = *(_QWORD *)v23;
    *(_DWORD *)(v23 + 16) = -1073741823;
    v38 = v25;
    v26 = *(_QWORD *)(v23 + 8);
    *(_QWORD *)v23 = 0;
    v39 = v26;
    *(_QWORD *)(v23 + 8) = 0;
    if ( (v22 & 2) != 0 )
    {
      v22 &= ~2u;
      if ( v44 )
        Kerb3961Free(v44);
    }
    if ( (v22 & 1) != 0 && v36 )
      Kerb3961Free(v36);
    v27 = (int)v40;
    if ( (int)v40 < 0 )
    {
      Kerb3961::Logging::Verify::StatusFailed(
        (Kerb3961::Logging::Verify *)"checksumInput",
        (const char *)(unsigned int)v40,
        v24);
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = v27;
LABEL_29:
      if ( v39 )
        Kerb3961Free(v39);
LABEL_31:
      if ( !v14 )
        return a2;
LABEL_32:
      v13 = v14;
LABEL_33:
      Kerb3961Free(v13);
      return a2;
    }
    (*(void (__fastcall **)(_QWORD *, char **, __int64, __int64, int))(*a1 + 168LL))(
      a1,
      v41,
      a5,
      2LL * ((*(_BYTE *)(v14 + 2) & 1) == 0) + 22,
      2);
    v29 = (int)v42;
    if ( (int)v42 >= 0 )
    {
      v31 = (*(__int64 (__fastcall **)(_QWORD *))(a1[1] + 104LL))(a1 + 1);
      if ( v31 != (*(unsigned int (__fastcall **)(_QWORD *))(*a1 + 224LL))(a1) )
        Kerb3961::ConsistencyFail(
          (Kerb3961 *)L"A cipher suite's included checksum must be the required checksum for the included cipher",
          v32);
      v29 = *(_DWORD *)(*(__int64 (__fastcall **)(_QWORD *, int *, char **, __int64 *, char *))(a1[1] + 96LL))(
                         a1 + 1,
                         v34,
                         v41,
                         &v38,
                         v50);
      if ( v29 >= 0 )
      {
        Kerb3961::CopyBuffer(a2, v47);
LABEL_27:
        if ( v41[1] )
           Kerb3961::EncryptionAlgorithm::`vcall'{160,{flat}}(v41[0]);
        goto LABEL_29;
      }
      v30 = "this->VerifyMic(specificKey, checksumInput, checksumBuffer)";
    }
    else
    {
      v30 = "specificKey";
    }
    Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)v30, (const char *)(unsigned int)v29, v28);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = v29;
    goto LABEL_27;
  }
  Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)"buffer", (const char *)(unsigned int)v45, v11);
  v13 = v44;
  *(_QWORD *)a2 = 0;
  *(_QWORD *)(a2 + 8) = 0;
  *(_DWORD *)(a2 + 16) = v12;
  if ( v13 )
    goto LABEL_33;
  return a2;
}

```

## disassembly

```asm
0x180002cc4  push    rbp
0x180002cc6  push    rbx
0x180002cc7  push    rsi
0x180002cc8  push    rdi
0x180002cc9  push    r12
0x180002ccb  push    r13
0x180002ccd  push    r14
0x180002ccf  push    r15
0x180002cd1  lea     rbp, [rsp-8]
0x180002cd6  sub     rsp, 108h
0x180002cdd  mov     rax, cs:__security_cookie
0x180002ce4  xor     rax, rsp
0x180002ce7  mov     [rbp+40h+var_48], rax
0x180002ceb  mov     r12, [rbp+40h+arg_20]
0x180002cef  mov     r10, r8
0x180002cf2  mov     r15, rcx
0x180002cf5  mov     rdi, rdx
0x180002cf8  xor     edx, edx
0x180002cfa  xor     r13d, r13d
0x180002cfd  mov     [rsp+140h+var_110], r13d
0x180002d02  mov     r14, r9
0x180002d05  mov     r8, [r8]
0x180002d08  mov     rax, [r10+8]
0x180002d0c  add     r8, 0FFFFFFFFFFFFFFF0h
0x180002d10  mov     [rsp+140h+var_100], 10h
0x180002d19  movzx   ecx, word ptr [rax+6]
0x180002d1d  ror     cx, 8
0x180002d21  movzx   eax, cx
0x180002d24  lea     rcx, [rbp+40h+var_98]; this
0x180002d28  div     r8
0x180002d2b  sub     r8, rdx
0x180002d2e  mov     [rsp+140h+var_F8], rdx
0x180002d33  mov     [rsp+140h+var_F0], r8
0x180002d38  mov     rdx, r10
0x180002d3b  lea     r8, [rsp+140h+var_100]
0x180002d40  call    ??$Split@$02@Kerb3961@@YA?BU?$array@$$CBUReadOnlyBinary@Kerb3961@@$02@utl@@AEBUReadOnlyBinary@0@U?$array@_K$02@2@@Z; Kerb3961::Split<3>(Kerb3961::ReadOnlyBinary const &,utl::array<unsigned __int64,3>)
0x180002d45  lea     r9, [rbp+40h+var_88]
0x180002d49  lea     r8, [rbp+40h+var_78]
0x180002d4d  lea     rdx, [rbp+40h+var_98]
0x180002d51  lea     rcx, [rbp+40h+var_B0]
0x180002d55  call    ?Concatenate@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@00@Z; Kerb3961::Concatenate(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x180002d5a  mov     ebx, dword ptr [rbp+40h+var_A0]
0x180002d5d  test    ebx, ebx
0x180002d5f  jns     short loc_180002D8B
0x180002d61  mov     edx, ebx; char *
0x180002d63  lea     rcx, aBuffer; "buffer"
0x180002d6a  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180002d6f  mov     rcx, [rbp+40h+var_A8]
0x180002d73  mov     [rdi], r13
0x180002d76  mov     [rdi+8], r13
0x180002d7a  mov     [rdi+10h], ebx
0x180002d7d  test    rcx, rcx
0x180002d80  jz      loc_180002FDC
0x180002d86  jmp     loc_180002FD7
0x180002d8b  mov     rsi, [rbp+40h+var_A8]
0x180002d8f  movzx   eax, word ptr [rsi+4]
0x180002d93  ror     ax, 8
0x180002d97  movzx   edx, ax; char *
0x180002d9a  mov     rax, [rbp+40h+var_B0]
0x180002d9e  mov     [rsi+6], r13w
0x180002da3  mov     [rsi+4], r13w
0x180002da8  lea     rcx, [rdx+10h]
0x180002dac  cmp     rax, rcx
0x180002daf  jnb     short loc_180002DD0
0x180002db1  lea     rcx, aBufferLengthCh; "buffer.length >= checksumSize + WrapHea"...
0x180002db8  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180002dbd  mov     [rdi], r13
0x180002dc0  mov     [rdi+8], r13
0x180002dc4  mov     dword ptr [rdi+10h], 8009030Fh
0x180002dcb  jmp     loc_180002FD4
0x180002dd0  sub     rax, rdx
0x180002dd3  mov     [rsp+140h+var_F8], rdx
0x180002dd8  lea     r8, [rsp+140h+var_100]
0x180002ddd  mov     [rsp+140h+var_100], rax
0x180002de2  lea     rdx, [rbp+40h+var_B0]
0x180002de6  lea     rcx, [rbp+40h+var_68]
0x180002dea  lea     rbx, [rax-10h]
0x180002dee  call    ??$Split@$01@Kerb3961@@YA?AU?$array@$$CBUMutableBinary@Kerb3961@@$01@utl@@AEBUMutableBinary@0@U?$array@_K$01@2@@Z; Kerb3961::Split<2>(Kerb3961::MutableBinary const &,utl::array<unsigned __int64,2>)
0x180002df3  lea     r8, [rsp+140h+var_100]
0x180002df8  mov     [rsp+140h+var_100], 10h
0x180002e01  lea     rdx, [rbp+40h+var_68]
0x180002e05  mov     [rsp+140h+var_F8], rbx
0x180002e0a  lea     rcx, [rbp+40h+var_98]
0x180002e0e  call    ??$Split@$01@Kerb3961@@YA?AU?$array@$$CBUMutableBinary@Kerb3961@@$01@utl@@AEBUMutableBinary@0@U?$array@_K$01@2@@Z; Kerb3961::Split<2>(Kerb3961::MutableBinary const &,utl::array<unsigned __int64,2>)
0x180002e13  mov     r8, [r14]
0x180002e16  test    r8, r8
0x180002e19  jz      short loc_180002E3F
0x180002e1b  test    rbx, rbx
0x180002e1e  jz      short loc_180002E3F
0x180002e20  lea     rcx, aAuthdataLength_0; "authData.length == 0 || plaintextSize ="...
0x180002e27  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180002e2c  mov     [rdi], r13
0x180002e2f  mov     [rdi+8], r13
0x180002e33  mov     dword ptr [rdi+10h], 8009030Ah
0x180002e3a  jmp     loc_180002FCF
0x180002e3f  mov     rax, r8
0x180002e42  lea     rdx, [rbp+40h+var_88]
0x180002e46  neg     rax
0x180002e49  lea     rcx, [rbp+40h+var_B0]
0x180002e4d  lea     rax, [rsp+140h+var_100]
0x180002e52  sbb     ebx, ebx
0x180002e54  neg     ebx
0x180002e56  inc     ebx
0x180002e58  test    r8, r8
0x180002e5b  lea     r8, [rbp+40h+var_98]
0x180002e5f  cmovnz  rdx, r14
0x180002e63  cmovz   rcx, rax
0x180002e67  call    ?Concatenate@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@0@Z; Kerb3961::Concatenate(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x180002e6c  mov     edx, 0C0000001h
0x180002e71  mov     dword ptr [rsp+140h+var_D0], edx
0x180002e75  mov     ecx, [rax+10h]
0x180002e78  mov     dword ptr [rsp+140h+var_D0], ecx
0x180002e7c  mov     rcx, [rax]
0x180002e7f  mov     [rax+10h], edx
0x180002e82  mov     [rsp+140h+var_E0], rcx
0x180002e87  mov     rcx, [rax+8]
0x180002e8b  mov     [rax], r13
0x180002e8e  mov     [rsp+140h+var_D8], rcx
0x180002e93  mov     [rax+8], r13
0x180002e97  test    bl, 2
0x180002e9a  jz      short loc_180002EAD
0x180002e9c  mov     rcx, [rbp+40h+var_A8]
0x180002ea0  and     ebx, 0FFFFFFFDh
0x180002ea3  test    rcx, rcx
0x180002ea6  jz      short loc_180002EAD
0x180002ea8  call    Kerb3961Free
0x180002ead  test    bl, 1
0x180002eb0  jz      short loc_180002EC1
0x180002eb2  mov     rcx, [rsp+140h+var_F8]
0x180002eb7  test    rcx, rcx
0x180002eba  jz      short loc_180002EC1
0x180002ebc  call    Kerb3961Free
0x180002ec1  mov     ebx, dword ptr [rsp+140h+var_D0]
0x180002ec5  test    ebx, ebx
0x180002ec7  jns     short loc_180002EE6
0x180002ec9  mov     edx, ebx; char *
0x180002ecb  lea     rcx, aChecksuminput; "checksumInput"
0x180002ed2  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180002ed7  mov     [rdi], r13
0x180002eda  mov     [rdi+8], r13
0x180002ede  mov     [rdi+10h], ebx
0x180002ee1  jmp     loc_180002FC0
0x180002ee6  mov     r9b, [rsi+2]
0x180002eea  lea     rdx, [rsp+140h+var_C8]
0x180002eef  mov     rax, [r15]
0x180002ef2  not     r9b
0x180002ef5  and     r9d, 1
0x180002ef9  mov     dword ptr [rsp+140h+var_120], 2
0x180002f01  mov     r8, r12
0x180002f04  mov     rcx, r15
0x180002f07  mov     rax, [rax+0A8h]
0x180002f0e  lea     r9, ds:16h[r9*2]
0x180002f16  call    _guard_dispatch_icall
0x180002f1b  mov     ebx, dword ptr [rbp+40h+var_B8]
0x180002f1e  test    ebx, ebx
0x180002f20  jns     short loc_180002F3C
0x180002f22  lea     rcx, aSpecifickey; "specificKey"
0x180002f29  mov     edx, ebx; char *
0x180002f2b  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180002f30  mov     [rdi], r13
0x180002f33  mov     [rdi+8], r13
0x180002f37  mov     [rdi+10h], ebx
0x180002f3a  jmp     short loc_180002FAD
0x180002f3c  lea     r14, [r15+8]
0x180002f40  mov     rax, [r14]
0x180002f43  mov     rcx, r14
0x180002f46  mov     rax, [rax+68h]
0x180002f4a  call    _guard_dispatch_icall
0x180002f4f  mov     rdx, [r15]
0x180002f52  mov     ebx, eax
0x180002f54  mov     rcx, r15
0x180002f57  mov     rax, [rdx+0E0h]
0x180002f5e  call    _guard_dispatch_icall
0x180002f63  cmp     ebx, eax
0x180002f65  jnz     loc_180003000
0x180002f6b  mov     rax, [r14]
0x180002f6e  lea     rcx, [rbp+40h+var_58]
0x180002f72  mov     [rsp+140h+var_120], rcx
0x180002f77  lea     r9, [rsp+140h+var_E0]
0x180002f7c  lea     r8, [rsp+140h+var_C8]
0x180002f81  mov     rcx, r14
0x180002f84  lea     rdx, [rsp+140h+var_110]
0x180002f89  mov     rax, [rax+60h]
0x180002f8d  call    _guard_dispatch_icall
0x180002f92  mov     ebx, [rax]
0x180002f94  test    ebx, ebx
0x180002f96  jns     short loc_180002FA1
0x180002f98  lea     rcx, aThisVerifymicS; "this->VerifyMic(specificKey, checksumIn"...
0x180002f9f  jmp     short loc_180002F29
0x180002fa1  lea     rdx, [rbp+40h+var_88]
0x180002fa5  mov     rcx, rdi
0x180002fa8  call    ?CopyBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@@Z; Kerb3961::CopyBuffer(Kerb3961::ReadOnlyBinary const &)
0x180002fad  mov     rdx, [rbp+40h+var_C0]
0x180002fb1  test    rdx, rdx
0x180002fb4  jz      short loc_180002FC0
0x180002fb6  mov     rcx, [rsp+140h+var_C8]
0x180002fbb  call    ??_9EncryptionAlgorithm@Kerb3961@@$BKA@AA; [thunk]: Kerb3961::EncryptionAlgorithm::`vcall'{160,{flat}}
0x180002fc0  mov     rcx, [rsp+140h+var_D8]
0x180002fc5  test    rcx, rcx
0x180002fc8  jz      short loc_180002FCF
0x180002fca  call    Kerb3961Free
0x180002fcf  test    rsi, rsi
0x180002fd2  jz      short loc_180002FDC
0x180002fd4  mov     rcx, rsi
0x180002fd7  call    Kerb3961Free
0x180002fdc  mov     rax, rdi
0x180002fdf  mov     rcx, [rbp+40h+var_48]
0x180002fe3  xor     rcx, rsp; StackCookie
0x180002fe6  call    __security_check_cookie
0x180002feb  add     rsp, 108h
0x180002ff2  pop     r15
0x180002ff4  pop     r14
0x180002ff6  pop     r13
0x180002ff8  pop     r12
0x180002ffa  pop     rdi
0x180002ffb  pop     rsi
0x180002ffc  pop     rbx
0x180002ffd  pop     rbp
0x180002ffe  retn
0x180003000  lea     rcx, aACipherSuiteSI; "A cipher suite's included checksum must"...
0x180003007  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
