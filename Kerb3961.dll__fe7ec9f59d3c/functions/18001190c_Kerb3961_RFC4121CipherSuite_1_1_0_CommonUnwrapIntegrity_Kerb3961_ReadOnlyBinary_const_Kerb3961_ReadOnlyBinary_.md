# Kerb3961::RFC4121CipherSuite<1,1,0>::CommonUnwrapIntegrity(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x18001190c`
- end: `0x180011c5c`
- name: `?CommonUnwrapIntegrity@?$RFC4121CipherSuite@$00$00$0A@@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@00@Z`
- size: `848`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1800112d0`
- `0x180019250`

## callees

- `0x180001d40`
- `0x180001d64`
- `0x180002c34`
- `0x180002c64`
- `0x180002fc0`
- `0x1800033f4`
- `0x1800046e0`
- `0x180006ee0`
- `0x18000700c`
- `0x18000712c`
- `0x180010124`
- `0x18001190c`
- `0x18001e010`

## string_xrefs

- `0x1800119f9`: `buffer.length >= checksumSize + WrapHeaderSize`

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
  void *v13; // rcx
  _WORD *v14; // rsi
  char *v15; // rdx
  unsigned __int64 v16; // rax
  void *v17; // rbx
  const char *v18; // rdx
  __int64 v19; // r8
  _BYTE *v20; // rdx
  __int64 *v21; // rcx
  char v22; // bl
  __int64 v23; // rax
  int v24; // r8d
  __int64 v25; // rcx
  void *v26; // rcx
  int v27; // ebx
  int v28; // r8d
  int v29; // ebx
  char *v30; // rcx
  int v31; // ebx
  const unsigned __int16 *v32; // rdx
  _DWORD v34[4]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v35; // [rsp+40h] [rbp-C0h] BYREF
  void *v36; // [rsp+48h] [rbp-B8h]
  unsigned __int64 v37; // [rsp+50h] [rbp-B0h]
  __int64 v38; // [rsp+60h] [rbp-A0h] BYREF
  void *v39; // [rsp+68h] [rbp-98h]
  char *v40; // [rsp+70h] [rbp-90h]
  char *v41[2]; // [rsp+78h] [rbp-88h] BYREF
  char *v42; // [rsp+88h] [rbp-78h]
  unsigned __int64 v43; // [rsp+90h] [rbp-70h] BYREF
  void *v44; // [rsp+98h] [rbp-68h]
  char *v45; // [rsp+A0h] [rbp-60h]
  _BYTE v46[16]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v47[16]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v48[16]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v49[16]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v50[16]; // [rsp+E8h] [rbp-18h] BYREF

  v34[0] = 0;
  v8 = a3[1];
  v9 = *a3 - 16LL;
  v35 = 16;
  v10 = (unsigned __int16)__ROR2__(*(_WORD *)(v8 + 6), 8);
  v36 = (void *)(v10 % v9);
  v37 = v9 - v10 % v9;
  Kerb3961::Split<3>((Kerb3961::ReadOnlyBinary *)v46);
  Kerb3961::Concatenate(&v43, v46, v48, v47);
  v12 = (int)v45;
  if ( (int)v45 >= 0 )
  {
    v14 = v44;
    v15 = (char *)(unsigned __int16)__ROR2__(*((_WORD *)v44 + 2), 8);
    v16 = v43;
    *((_WORD *)v44 + 3) = 0;
    v14[2] = 0;
    if ( v16 < (unsigned __int64)(v15 + 16) )
    {
      Kerb3961::Logging::Verify::ConditionFailed(
        (Kerb3961::Logging::Verify *)"buffer.length >= checksumSize + WrapHeaderSize",
        v15);
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = -2146893041;
      goto LABEL_32;
    }
    v36 = v15;
    v35 = v16 - (_QWORD)v15;
    v17 = (void *)(v16 - (_QWORD)v15 - 16);
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
    v26 = *(void **)(v23 + 8);
    *(_QWORD *)v23 = 0;
    v39 = v26;
    *(_QWORD *)(v23 + 8) = 0;
    if ( (v22 & 2) != 0 )
    {
      v22 &= ~2u;
      if ( v44 )
        operator delete(v44, 0);
    }
    if ( (v22 & 1) != 0 && v36 )
      operator delete(v36, 0);
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
        operator delete(v39, 0);
LABEL_31:
      if ( !v14 )
        return a2;
LABEL_32:
      v13 = v14;
LABEL_33:
      operator delete(v13, 0);
      return a2;
    }
    (*(void (__fastcall **)(_QWORD *, char **, __int64, __int64, int))(*a1 + 168LL))(
      a1,
      v41,
      a5,
      2LL * ((v14[1] & 1) == 0) + 22,
      2);
    v29 = (int)v42;
    if ( (int)v42 >= 0 )
    {
      v31 = (*(__int64 (__fastcall **)(_QWORD *))(a1[1] + 104LL))(a1 + 1);
      if ( v31 != (*(unsigned int (__fastcall **)(_QWORD *))(*a1 + 224LL))(a1) )
        Kerb3961::ConsistencyFail(
          (Kerb3961 *)L"A cipher suite's included checksum must be the required checksum for the included cipher",
          v32);
      v29 = *(_DWORD *)(*(__int64 (__fastcall **)(_QWORD *, _DWORD *, char **, __int64 *, _BYTE *))(a1[1] + 96LL))(
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
0x18001190c  push    rbp
0x18001190e  push    rbx
0x18001190f  push    rsi
0x180011910  push    rdi
0x180011911  push    r12
0x180011913  push    r13
0x180011915  push    r14
0x180011917  push    r15
0x180011919  lea     rbp, [rsp-8]
0x18001191e  sub     rsp, 108h
0x180011925  mov     rax, cs:__security_cookie
0x18001192c  xor     rax, rsp
0x18001192f  mov     [rbp+40h+var_48], rax
0x180011933  mov     r12, [rbp+40h+arg_20]
0x180011937  mov     r10, r8
0x18001193a  mov     r15, rcx
0x18001193d  mov     rdi, rdx
0x180011940  xor     edx, edx
0x180011942  xor     r13d, r13d
0x180011945  mov     [rsp+140h+var_110], r13d
0x18001194a  mov     r14, r9
0x18001194d  mov     r8, [r8]
0x180011950  mov     rax, [r10+8]
0x180011954  add     r8, 0FFFFFFFFFFFFFFF0h
0x180011958  mov     [rsp+140h+var_100], 10h
0x180011961  movzx   ecx, word ptr [rax+6]
0x180011965  ror     cx, 8
0x180011969  movzx   eax, cx
0x18001196c  lea     rcx, [rbp+40h+var_98]; this
0x180011970  div     r8
0x180011973  sub     r8, rdx
0x180011976  mov     [rsp+140h+var_F8], rdx
0x18001197b  mov     [rsp+140h+var_F0], r8
0x180011980  mov     rdx, r10
0x180011983  lea     r8, [rsp+140h+var_100]
0x180011988  call    ??$Split@$02@Kerb3961@@YA?BU?$array@$$CBUReadOnlyBinary@Kerb3961@@$02@utl@@AEBUReadOnlyBinary@0@U?$array@_K$02@2@@Z; Kerb3961::Split<3>(Kerb3961::ReadOnlyBinary const &,utl::array<unsigned __int64,3>)
0x18001198d  lea     r9, [rbp+40h+var_88]
0x180011991  lea     r8, [rbp+40h+var_78]
0x180011995  lea     rdx, [rbp+40h+var_98]
0x180011999  lea     rcx, [rbp+40h+var_B0]
0x18001199d  call    ?Concatenate@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@00@Z; Kerb3961::Concatenate(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x1800119a2  mov     ebx, dword ptr [rbp+40h+var_A0]
0x1800119a5  test    ebx, ebx
0x1800119a7  jns     short loc_1800119D3
0x1800119a9  mov     edx, ebx; char *
0x1800119ab  lea     rcx, aBuffer; "buffer"
0x1800119b2  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800119b7  mov     rcx, [rbp+40h+var_A8]
0x1800119bb  mov     [rdi], r13
0x1800119be  mov     [rdi+8], r13
0x1800119c2  mov     [rdi+10h], ebx
0x1800119c5  test    rcx, rcx
0x1800119c8  jz      loc_180011C2C
0x1800119ce  jmp     loc_180011C25
0x1800119d3  mov     rsi, [rbp+40h+var_A8]
0x1800119d7  movzx   eax, word ptr [rsi+4]
0x1800119db  ror     ax, 8
0x1800119df  movzx   edx, ax; char *
0x1800119e2  mov     rax, [rbp+40h+var_B0]
0x1800119e6  mov     [rsi+6], r13w
0x1800119eb  mov     [rsi+4], r13w
0x1800119f0  lea     rcx, [rdx+10h]
0x1800119f4  cmp     rax, rcx
0x1800119f7  jnb     short loc_180011A18
0x1800119f9  lea     rcx, aBufferLengthCh; "buffer.length >= checksumSize + WrapHea"...
0x180011a00  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180011a05  mov     [rdi], r13
0x180011a08  mov     [rdi+8], r13
0x180011a0c  mov     dword ptr [rdi+10h], 8009030Fh
0x180011a13  jmp     loc_180011C22
0x180011a18  sub     rax, rdx
0x180011a1b  mov     [rsp+140h+var_F8], rdx
0x180011a20  lea     r8, [rsp+140h+var_100]
0x180011a25  mov     [rsp+140h+var_100], rax
0x180011a2a  lea     rdx, [rbp+40h+var_B0]
0x180011a2e  lea     rcx, [rbp+40h+var_68]
0x180011a32  lea     rbx, [rax-10h]
0x180011a36  call    ??$Split@$01@Kerb3961@@YA?AU?$array@$$CBUMutableBinary@Kerb3961@@$01@utl@@AEBUMutableBinary@0@U?$array@_K$01@2@@Z; Kerb3961::Split<2>(Kerb3961::MutableBinary const &,utl::array<unsigned __int64,2>)
0x180011a3b  lea     r8, [rsp+140h+var_100]
0x180011a40  mov     [rsp+140h+var_100], 10h
0x180011a49  lea     rdx, [rbp+40h+var_68]
0x180011a4d  mov     [rsp+140h+var_F8], rbx
0x180011a52  lea     rcx, [rbp+40h+var_98]
0x180011a56  call    ??$Split@$01@Kerb3961@@YA?AU?$array@$$CBUMutableBinary@Kerb3961@@$01@utl@@AEBUMutableBinary@0@U?$array@_K$01@2@@Z; Kerb3961::Split<2>(Kerb3961::MutableBinary const &,utl::array<unsigned __int64,2>)
0x180011a5b  mov     r8, [r14]
0x180011a5e  test    r8, r8
0x180011a61  jz      short loc_180011A87
0x180011a63  test    rbx, rbx
0x180011a66  jz      short loc_180011A87
0x180011a68  lea     rcx, aAuthdataLength_0; "authData.length == 0 || plaintextSize ="...
0x180011a6f  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180011a74  mov     [rdi], r13
0x180011a77  mov     [rdi+8], r13
0x180011a7b  mov     dword ptr [rdi+10h], 8009030Ah
0x180011a82  jmp     loc_180011C1D
0x180011a87  mov     rax, r8
0x180011a8a  lea     rdx, [rbp+40h+var_88]
0x180011a8e  neg     rax
0x180011a91  lea     rcx, [rbp+40h+var_B0]
0x180011a95  lea     rax, [rsp+140h+var_100]
0x180011a9a  sbb     ebx, ebx
0x180011a9c  neg     ebx
0x180011a9e  inc     ebx
0x180011aa0  test    r8, r8
0x180011aa3  lea     r8, [rbp+40h+var_98]
0x180011aa7  cmovnz  rdx, r14
0x180011aab  cmovz   rcx, rax
0x180011aaf  call    ?Concatenate@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@0@Z; Kerb3961::Concatenate(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x180011ab4  mov     edx, 0C0000001h
0x180011ab9  mov     dword ptr [rsp+140h+var_D0], edx
0x180011abd  mov     ecx, [rax+10h]
0x180011ac0  mov     dword ptr [rsp+140h+var_D0], ecx
0x180011ac4  mov     rcx, [rax]
0x180011ac7  mov     [rax+10h], edx
0x180011aca  mov     [rsp+140h+var_E0], rcx
0x180011acf  mov     rcx, [rax+8]
0x180011ad3  mov     [rax], r13
0x180011ad6  mov     [rsp+140h+var_D8], rcx
0x180011adb  mov     [rax+8], r13
0x180011adf  test    bl, 2
0x180011ae2  jz      short loc_180011AF7
0x180011ae4  mov     rcx, [rbp+40h+var_A8]; void *
0x180011ae8  and     ebx, 0FFFFFFFDh
0x180011aeb  test    rcx, rcx
0x180011aee  jz      short loc_180011AF7
0x180011af0  xor     edx, edx; struct std::nothrow_t *
0x180011af2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180011af7  test    bl, 1
0x180011afa  jz      short loc_180011B0D
0x180011afc  mov     rcx, [rsp+140h+var_F8]; void *
0x180011b01  test    rcx, rcx
0x180011b04  jz      short loc_180011B0D
0x180011b06  xor     edx, edx; struct std::nothrow_t *
0x180011b08  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180011b0d  mov     ebx, dword ptr [rsp+140h+var_D0]
0x180011b11  test    ebx, ebx
0x180011b13  jns     short loc_180011B32
0x180011b15  mov     edx, ebx; char *
0x180011b17  lea     rcx, aChecksuminput; "checksumInput"
0x180011b1e  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180011b23  mov     [rdi], r13
0x180011b26  mov     [rdi+8], r13
0x180011b2a  mov     [rdi+10h], ebx
0x180011b2d  jmp     loc_180011C0C
0x180011b32  mov     r9b, [rsi+2]
0x180011b36  lea     rdx, [rsp+140h+var_C8]
0x180011b3b  mov     rax, [r15]
0x180011b3e  not     r9b
0x180011b41  and     r9d, 1
0x180011b45  mov     dword ptr [rsp+140h+var_120], 2
0x180011b4d  mov     r8, r12
0x180011b50  mov     rcx, r15
0x180011b53  mov     rax, [rax+0A8h]
0x180011b5a  lea     r9, ds:16h[r9*2]
0x180011b62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b67  mov     ebx, dword ptr [rbp+40h+var_B8]
0x180011b6a  test    ebx, ebx
0x180011b6c  jns     short loc_180011B88
0x180011b6e  lea     rcx, aSpecifickey; "specificKey"
0x180011b75  mov     edx, ebx; char *
0x180011b77  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180011b7c  mov     [rdi], r13
0x180011b7f  mov     [rdi+8], r13
0x180011b83  mov     [rdi+10h], ebx
0x180011b86  jmp     short loc_180011BF9
0x180011b88  lea     r14, [r15+8]
0x180011b8c  mov     rax, [r14]
0x180011b8f  mov     rcx, r14
0x180011b92  mov     rax, [rax+68h]
0x180011b96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b9b  mov     rdx, [r15]
0x180011b9e  mov     ebx, eax
0x180011ba0  mov     rcx, r15
0x180011ba3  mov     rax, [rdx+0E0h]
0x180011baa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011baf  cmp     ebx, eax
0x180011bb1  jnz     loc_180011C4F
0x180011bb7  mov     rax, [r14]
0x180011bba  lea     rcx, [rbp+40h+var_58]
0x180011bbe  mov     [rsp+140h+var_120], rcx
0x180011bc3  lea     r9, [rsp+140h+var_E0]
0x180011bc8  lea     r8, [rsp+140h+var_C8]
0x180011bcd  mov     rcx, r14
0x180011bd0  lea     rdx, [rsp+140h+var_110]
0x180011bd5  mov     rax, [rax+60h]
0x180011bd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011bde  mov     ebx, [rax]
0x180011be0  test    ebx, ebx
0x180011be2  jns     short loc_180011BED
0x180011be4  lea     rcx, aThisVerifymicS; "this->VerifyMic(specificKey, checksumIn"...
0x180011beb  jmp     short loc_180011B75
0x180011bed  lea     rdx, [rbp+40h+var_88]
0x180011bf1  mov     rcx, rdi
0x180011bf4  call    ?CopyBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@@Z; Kerb3961::CopyBuffer(Kerb3961::ReadOnlyBinary const &)
0x180011bf9  mov     rdx, [rbp+40h+var_C0]
0x180011bfd  test    rdx, rdx
0x180011c00  jz      short loc_180011C0C
0x180011c02  mov     rcx, [rsp+140h+var_C8]
0x180011c07  call    ??_9EncryptionAlgorithm@Kerb3961@@$BKA@AA; [thunk]: Kerb3961::EncryptionAlgorithm::`vcall'{160,{flat}}
0x180011c0c  mov     rcx, [rsp+140h+var_D8]; void *
0x180011c11  test    rcx, rcx
0x180011c14  jz      short loc_180011C1D
0x180011c16  xor     edx, edx; struct std::nothrow_t *
0x180011c18  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180011c1d  test    rsi, rsi
0x180011c20  jz      short loc_180011C2C
0x180011c22  mov     rcx, rsi; void *
0x180011c25  xor     edx, edx; struct std::nothrow_t *
0x180011c27  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180011c2c  mov     rax, rdi
0x180011c2f  mov     rcx, [rbp+40h+var_48]
0x180011c33  xor     rcx, rsp; StackCookie
0x180011c36  call    __security_check_cookie
0x180011c3b  add     rsp, 108h
0x180011c42  pop     r15
0x180011c44  pop     r14
0x180011c46  pop     r13
0x180011c48  pop     r12
0x180011c4a  pop     rdi
0x180011c4b  pop     rsi
0x180011c4c  pop     rbx
0x180011c4d  pop     rbp
0x180011c4e  retn
0x180011c4f  lea     rcx, aACipherSuiteSI; "A cipher suite's included checksum must"...
0x180011c56  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
