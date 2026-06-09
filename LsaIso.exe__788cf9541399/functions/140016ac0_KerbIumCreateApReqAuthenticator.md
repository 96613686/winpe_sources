# KerbIumCreateApReqAuthenticator

- ea: `0x140016ac0`
- end: `0x140016e85`
- name: `KerbIumCreateApReqAuthenticator`
- size: `965`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, struct _KERB_ENCRYPTION_KEY *, __int64, __int64, int, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x140004ca8`
- `0x140006720`
- `0x14001212c`
- `0x140014230`
- `0x140014370`
- `0x14001449c`
- `0x140014f38`
- `0x140016ac0`
- `0x14001af0c`
- `0x14001b45c`
- `0x14001b770`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140016b2f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140016b2f`
- `KerbClientShared!KerbClientPackAsn1Buffer` at `0x140016dce`
- `KerbClientShared!KerbClientPackAsn1Buffer` at `0x140016dce`
- `KerbClientShared!KerbClientUnpackAsn1BufferVoid` at `0x140016c9d`
- `KerbClientShared!KerbClientUnpackAsn1BufferVoid` at `0x140016cc9`
- `KerbClientShared!KerbClientUnpackAsn1BufferVoid` at `0x140016c9d`
- `KerbClientShared!KerbClientUnpackAsn1BufferVoid` at `0x140016cc9`
- `ntdll!RtlFreeHeap` at `0x140016e0c`
- `ntdll!RtlFreeHeap` at `0x140016e0c`
- `ntdll!RtlAllocateHeap` at `0x140016cf4`
- `ntdll!RtlAllocateHeap` at `0x140016cf4`

## string_xrefs

- `0x140016b64`: `KerbIumCreateApReqAuthenticator`
- `0x140016e3a`: `KerbIumCreateApReqAuthenticator`

## pseudocode

```c
__int64 __fastcall KerbIumCreateApReqAuthenticator(
        __int64 a1,
        struct _KERB_ENCRYPTION_KEY *a2,
        const struct KerbIumClearKey::AllowUnencryptedInput *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        struct _KERB_ENCRYPTION_KEY *a7,
        __int64 a8,
        __int64 a9,
        int a10,
        __int64 a11,
        struct _KERB_ASN1_DATA *a12,
        int *a13)
{
  struct _KERB_ENCRYPTION_KEY *v16; // r14
  const struct KerbIumClearKey::AllowUnencryptedInput *v17; // r8
  int v18; // ebx
  void *v19; // r15
  __int64 v20; // r12
  __int64 v21; // r13
  struct _KERB_ASN1_DATA *v22; // rdi
  __int64 v23; // rcx
  _WORD *Heap; // rax
  unsigned int v25; // edx
  __int64 v26; // rcx
  __int64 v27; // rdx
  int v28; // eax
  int v29; // eax
  void *v31; // [rsp+60h] [rbp-99h] BYREF
  __int128 v32; // [rsp+68h] [rbp-91h] BYREF
  void *v33[2]; // [rsp+78h] [rbp-81h]
  _BYTE v34[40]; // [rsp+88h] [rbp-71h] BYREF
  int v35; // [rsp+B0h] [rbp-49h]
  char v36; // [rsp+B4h] [rbp-45h]
  int v37; // [rsp+B8h] [rbp-41h]
  _BYTE v38[44]; // [rsp+C0h] [rbp-39h] BYREF
  int v39; // [rsp+ECh] [rbp-Dh]
  __int64 *v40; // [rsp+140h] [rbp+47h] BYREF
  unsigned int v41; // [rsp+150h] [rbp+57h]

  v41 = (unsigned int)a3;
  v40 = 0;
  v31 = 0;
  v32 = 0;
  *(_OWORD *)v33 = 0;
  KerbIumClearKey::KerbIumClearKey((KerbIumClearKey *)v38, a2, a3);
  v16 = a7;
  KerbIumClearKey::KerbIumClearKey((KerbIumClearKey *)v34, a7, v17);
  if ( qword_140052C40 != a1 )
  {
    Sleep(5u);
    v18 = -1073741790;
    goto LABEL_68;
  }
  v19 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      24,
      WPP_d5c6fd37444639aeca2bc0daa2920ffe_Traceguids,
      "KerbIumCreateApReqAuthenticator");
  if ( a2 )
  {
    if ( !a4 )
    {
      v18 = -1073741582;
      goto LABEL_60;
    }
    v20 = a5;
    if ( !a5 )
    {
      v18 = -1073741581;
      goto LABEL_60;
    }
    v21 = a6;
    if ( !a6 )
      goto LABEL_13;
    if ( !a11 )
    {
      v18 = -1073741576;
      goto LABEL_60;
    }
    v22 = a12;
    if ( !a12 )
    {
      v18 = -1073741575;
      goto LABEL_60;
    }
    if ( !a13 )
    {
      v18 = -1073741574;
      goto LABEL_60;
    }
    if ( (int)KerbIumClearKey::Status((KerbIumClearKey *)v38) < 0 )
    {
      v18 = -1073741585;
      goto LABEL_60;
    }
    if ( v16 && (int)KerbIumClearKey::Status((KerbIumClearKey *)v34) < 0 )
    {
LABEL_13:
      v18 = -1073741580;
      goto LABEL_60;
    }
    if ( (v39 & 0x10) != 0 && (v39 & 4) != 0 )
    {
      if ( !v16 )
      {
LABEL_41:
        v18 = -1073741580;
        goto LABEL_68;
      }
    }
    else if ( !v16 )
    {
      goto LABEL_42;
    }
    if ( (v39 & 1) != 0 && (v35 < 0 || !v37 || (v36 & 2) == 0)
      || v35 >= 0 && v37 && (v39 & 2) == 0
      || (v39 & 0x10) != 0 && (v39 & 4) != 0 && v35 >= 0 && v37 && (v36 & 0x20) == 0 )
    {
      goto LABEL_41;
    }
LABEL_42:
    v23 = a8;
    *(_OWORD *)v22 = 0;
    if ( v23 )
    {
      if ( *(_DWORD *)(v23 + 4) )
      {
        v18 = KerbClientUnpackAsn1BufferVoid((const struct _KERB_ASN1_DATA *)v23, 0, (void **)&v40);
        if ( v18 < 0 )
          goto LABEL_60;
      }
    }
    if ( a9 )
    {
      if ( *(_DWORD *)(a9 + 4) )
      {
        v18 = KerbClientUnpackAsn1BufferVoid((const struct _KERB_ASN1_DATA *)a9, 9u, &v31);
        if ( v18 < 0 )
          goto LABEL_60;
      }
    }
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 16 * (*(unsigned __int16 *)(a4 + 2) + 1LL));
    v19 = Heap;
    if ( Heap && (v25 = 0, *Heap = *(_WORD *)a4, (Heap[1] = *(_WORD *)(a4 + 2)) != 0) )
    {
      do
      {
        v26 = v25++;
        *(_OWORD *)&Heap[8 * v26 + 4] = *(_OWORD *)(*(_QWORD *)(a4 + 8) + 16 * v26);
      }
      while ( v25 < *(unsigned __int16 *)(a4 + 2) );
    }
    else if ( !Heap )
    {
      v18 = -1073741801;
      goto LABEL_60;
    }
    if ( v40 )
      v27 = *v40;
    else
      v27 = 0;
    v28 = KerbCreateAuthenticator(
            v38,
            v41,
            a11,
            Heap,
            v20,
            v21,
            (unsigned __int64)v34 & -(__int64)(v16 != 0),
            v27,
            v31,
            a10,
            &v32);
    *a13 = v28;
    if ( v28 )
      v29 = KerbMapKerbError(v28);
    else
      v29 = KerbClientPackAsn1Buffer(&v32, 7u, v22);
    v18 = v29;
    goto LABEL_60;
  }
  v18 = -1073741585;
LABEL_60:
  KerbClientFreeAsn1DecodedData<PKERB_AUTHORIZATION_DATA_s *>(v40);
  if ( v31 )
    KerbFreeData(9);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v19);
  if ( v33[1] )
    SafeAllocaFreeToHeap(v33[1]);
  if ( v18 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      25,
      (unsigned int)WPP_d5c6fd37444639aeca2bc0daa2920ffe_Traceguids,
      (unsigned int)"KerbIumCreateApReqAuthenticator",
      v18);
LABEL_68:
  KerbIumClearKey::~KerbIumClearKey((KerbIumClearKey *)v34);
  KerbIumClearKey::~KerbIumClearKey((KerbIumClearKey *)v38);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x140016ac0  mov     [rsp-8+arg_8], rbx
0x140016ac5  mov     [rsp-8+arg_10], r8d
0x140016aca  push    rbp
0x140016acb  push    rsi
0x140016acc  push    rdi
0x140016acd  push    r12
0x140016acf  push    r13
0x140016ad1  push    r14
0x140016ad3  push    r15
0x140016ad5  lea     rbp, [rsp-7]
0x140016ada  sub     rsp, 100h
0x140016ae1  xorps   xmm0, xmm0
0x140016ae4  mov     [rbp+37h+arg_0], 0
0x140016aec  mov     rbx, rcx
0x140016aef  mov     [rsp+130h+var_D0], 0
0x140016af8  lea     rcx, [rbp+37h+var_70]; this
0x140016afc  mov     rsi, r9
0x140016aff  movups  [rsp+130h+var_C8], xmm0
0x140016b04  mov     rdi, rdx
0x140016b07  movups  xmmword ptr [rsp+130h+var_B8], xmm0
0x140016b0c  call    ??0KerbIumClearKey@@QEAA@PEAU_KERB_ENCRYPTION_KEY@@AEBUAllowUnencryptedInput@0@@Z; KerbIumClearKey::KerbIumClearKey(_KERB_ENCRYPTION_KEY *,KerbIumClearKey::AllowUnencryptedInput const &)
0x140016b11  mov     r14, [rbp+37h+arg_30]
0x140016b15  lea     rcx, [rbp+37h+var_A8]; this
0x140016b19  mov     rdx, r14; struct _KERB_ENCRYPTION_KEY *
0x140016b1c  call    ??0KerbIumClearKey@@QEAA@PEAU_KERB_ENCRYPTION_KEY@@AEBUAllowUnencryptedInput@0@@Z; KerbIumClearKey::KerbIumClearKey(_KERB_ENCRYPTION_KEY *,KerbIumClearKey::AllowUnencryptedInput const &)
0x140016b21  cmp     cs:qword_140052C40, rbx
0x140016b28  jz      short loc_140016B3F
0x140016b2a  mov     ecx, 5; dwMilliseconds
0x140016b2f  call    cs:__imp_Sleep
0x140016b35  mov     ebx, 0C0000022h
0x140016b3a  jmp     loc_140016E56
0x140016b3f  mov     rcx, cs:WPP_GLOBAL_Control
0x140016b46  lea     r12, WPP_GLOBAL_Control
0x140016b4d  xor     r15d, r15d
0x140016b50  mov     bl, 4
0x140016b52  cmp     rcx, r12
0x140016b55  jz      short loc_140016B77
0x140016b57  test    [rcx+1Ch], bl
0x140016b5a  jz      short loc_140016B77
0x140016b5c  mov     rcx, [rcx+10h]
0x140016b60  lea     edx, [r15+18h]
0x140016b64  lea     r9, aKerbiumcreatea; "KerbIumCreateApReqAuthenticator"
0x140016b6b  lea     r8, WPP_d5c6fd37444639aeca2bc0daa2920ffe_Traceguids
0x140016b72  call    WPP_SF_s
0x140016b77  test    rdi, rdi
0x140016b7a  jnz     short loc_140016B86
0x140016b7c  mov     ebx, 0C00000EFh
0x140016b81  jmp     loc_140016DDD
0x140016b86  test    rsi, rsi
0x140016b89  jnz     short loc_140016B95
0x140016b8b  mov     ebx, 0C00000F2h
0x140016b90  jmp     loc_140016DDD
0x140016b95  mov     r12, [rbp+37h+arg_20]
0x140016b99  test    r12, r12
0x140016b9c  jnz     short loc_140016BA8
0x140016b9e  mov     ebx, 0C00000F3h
0x140016ba3  jmp     loc_140016DD6
0x140016ba8  mov     r13, [rbp+37h+arg_28]
0x140016bac  test    r13, r13
0x140016baf  jnz     short loc_140016BBB
0x140016bb1  mov     ebx, 0C00000F4h
0x140016bb6  jmp     loc_140016DD6
0x140016bbb  cmp     [rbp+37h+arg_50], r15
0x140016bc2  jnz     short loc_140016BCE
0x140016bc4  mov     ebx, 0C00000F8h
0x140016bc9  jmp     loc_140016DD6
0x140016bce  mov     rdi, [rbp+37h+arg_58]
0x140016bd5  test    rdi, rdi
0x140016bd8  jnz     short loc_140016BE4
0x140016bda  mov     ebx, 0C00000F9h
0x140016bdf  jmp     loc_140016DD6
0x140016be4  cmp     [rbp+37h+arg_60], r15
0x140016beb  jnz     short loc_140016BF7
0x140016bed  mov     ebx, 0C00000FAh
0x140016bf2  jmp     loc_140016DD6
0x140016bf7  lea     rcx, [rbp+37h+var_70]; this
0x140016bfb  call    ?Status@KerbIumClearKey@@QEBAJXZ; KerbIumClearKey::Status(void)
0x140016c00  test    eax, eax
0x140016c02  jns     short loc_140016C0E
0x140016c04  mov     ebx, 0C00000EFh
0x140016c09  jmp     loc_140016DD6
0x140016c0e  test    r14, r14
0x140016c11  jz      short loc_140016C20
0x140016c13  lea     rcx, [rbp+37h+var_A8]; this
0x140016c17  call    ?Status@KerbIumClearKey@@QEBAJXZ; KerbIumClearKey::Status(void)
0x140016c1c  test    eax, eax
0x140016c1e  js      short loc_140016BB1
0x140016c20  mov     eax, [rbp+37h+var_44]
0x140016c23  mov     r8d, eax
0x140016c26  and     r8d, 10h
0x140016c2a  jz      short loc_140016C37
0x140016c2c  test    bl, al
0x140016c2e  jz      short loc_140016C37
0x140016c30  test    r14, r14
0x140016c33  jz      short loc_140016C77
0x140016c35  jmp     short loc_140016C3C
0x140016c37  test    r14, r14
0x140016c3a  jz      short loc_140016C81
0x140016c3c  mov     edx, [rbp+37h+var_78]
0x140016c3f  mov     ecx, [rbp+37h+var_80]
0x140016c42  test    al, 1
0x140016c44  jz      short loc_140016C54
0x140016c46  test    ecx, ecx
0x140016c48  js      short loc_140016C77
0x140016c4a  test    edx, edx
0x140016c4c  jz      short loc_140016C77
0x140016c4e  test    [rbp+37h+var_7C], 2
0x140016c52  jz      short loc_140016C77
0x140016c54  test    ecx, ecx
0x140016c56  js      short loc_140016C60
0x140016c58  test    edx, edx
0x140016c5a  jz      short loc_140016C60
0x140016c5c  test    al, 2
0x140016c5e  jz      short loc_140016C77
0x140016c60  test    r8d, r8d
0x140016c63  jz      short loc_140016C81
0x140016c65  test    bl, al
0x140016c67  jz      short loc_140016C81
0x140016c69  test    ecx, ecx
0x140016c6b  js      short loc_140016C81
0x140016c6d  test    edx, edx
0x140016c6f  jz      short loc_140016C81
0x140016c71  test    [rbp+37h+var_7C], 20h
0x140016c75  jnz     short loc_140016C81
0x140016c77  mov     ebx, 0C00000F4h
0x140016c7c  jmp     loc_140016E56
0x140016c81  mov     rcx, [rbp+37h+arg_38]
0x140016c85  xorps   xmm0, xmm0
0x140016c88  movdqu  xmmword ptr [rdi], xmm0
0x140016c8c  test    rcx, rcx
0x140016c8f  jz      short loc_140016CAD
0x140016c91  cmp     [rcx+4], r15d
0x140016c95  jbe     short loc_140016CAD
0x140016c97  lea     r8, [rbp+37h+arg_0]
0x140016c9b  xor     edx, edx
0x140016c9d  call    cs:__imp_?KerbClientUnpackAsn1BufferVoid@@YAJAEBU_KERB_ASN1_DATA@@KPEAPEAX@Z; KerbClientUnpackAsn1BufferVoid(_KERB_ASN1_DATA const &,ulong,void * *)
0x140016ca3  mov     ebx, eax
0x140016ca5  test    eax, eax
0x140016ca7  js      loc_140016DD6
0x140016cad  mov     rcx, [rbp+37h+arg_40]
0x140016cb4  test    rcx, rcx
0x140016cb7  jz      short loc_140016CD9
0x140016cb9  cmp     [rcx+4], r15d
0x140016cbd  jbe     short loc_140016CD9
0x140016cbf  lea     r8, [rsp+130h+var_D0]
0x140016cc4  mov     edx, 9
0x140016cc9  call    cs:__imp_?KerbClientUnpackAsn1BufferVoid@@YAJAEBU_KERB_ASN1_DATA@@KPEAPEAX@Z; KerbClientUnpackAsn1BufferVoid(_KERB_ASN1_DATA const &,ulong,void * *)
0x140016ccf  mov     ebx, eax
0x140016cd1  test    eax, eax
0x140016cd3  js      loc_140016DD6
0x140016cd9  mov     rcx, gs:60h
0x140016ce2  xor     edx, edx; Flags
0x140016ce4  movzx   r8d, word ptr [rsi+2]
0x140016ce9  inc     r8
0x140016cec  shl     r8, 4; Size
0x140016cf0  mov     rcx, [rcx+30h]; HeapHandle
0x140016cf4  call    cs:__imp_RtlAllocateHeap
0x140016cfa  mov     r15, rax
0x140016cfd  mov     r9, rax
0x140016d00  test    rax, rax
0x140016d03  jz      short loc_140016D50
0x140016d05  movzx   eax, word ptr [rsi]
0x140016d08  xor     edx, edx
0x140016d0a  mov     [r9], ax
0x140016d0e  movzx   eax, word ptr [rsi+2]
0x140016d12  mov     [r9+2], ax
0x140016d17  xor     eax, eax
0x140016d19  cmp     ax, [rsi+2]
0x140016d1d  jnb     short loc_140016D50
0x140016d1f  mov     rax, [rsi+8]
0x140016d23  mov     ecx, edx
0x140016d25  inc     edx
0x140016d27  add     rcx, rcx
0x140016d2a  movups  xmm0, xmmword ptr [rax+rcx*8]
0x140016d2e  movdqu  xmmword ptr [r15+rcx*8+8], xmm0
0x140016d35  movzx   eax, word ptr [rsi+2]
0x140016d39  cmp     edx, eax
0x140016d3b  jb      short loc_140016D1F
0x140016d3d  mov     rax, [rbp+37h+arg_0]
0x140016d41  mov     r8, [rsp+130h+var_D0]
0x140016d46  test    rax, rax
0x140016d49  jz      short loc_140016D5C
0x140016d4b  mov     rdx, [rax]
0x140016d4e  jmp     short loc_140016D5E
0x140016d50  test    r9, r9
0x140016d53  jnz     short loc_140016D3D
0x140016d55  mov     ebx, 0C0000017h
0x140016d5a  jmp     short loc_140016DD6
0x140016d5c  xor     edx, edx
0x140016d5e  lea     rax, [rbp+37h+var_A8]
0x140016d62  neg     r14
0x140016d65  sbb     rcx, rcx
0x140016d68  and     rcx, rax
0x140016d6b  lea     rax, [rsp+130h+var_C8]
0x140016d70  mov     [rsp+130h+var_E0], rax
0x140016d75  mov     eax, [rbp+37h+arg_48]
0x140016d7b  mov     [rsp+130h+var_E8], eax
0x140016d7f  mov     [rsp+130h+var_F0], r8
0x140016d84  mov     r8, [rbp+37h+arg_50]
0x140016d8b  mov     [rsp+130h+var_F8], rdx
0x140016d90  mov     edx, [rbp+37h+arg_10]
0x140016d93  mov     [rsp+130h+var_100], rcx
0x140016d98  lea     rcx, [rbp+37h+var_70]
0x140016d9c  mov     [rsp+130h+var_108], r13
0x140016da1  mov     [rsp+130h+var_110], r12
0x140016da6  call    KerbCreateAuthenticator
0x140016dab  mov     rcx, [rbp+37h+arg_60]
0x140016db2  mov     [rcx], eax
0x140016db4  test    eax, eax
0x140016db6  jz      short loc_140016DC1
0x140016db8  mov     ecx, eax; int
0x140016dba  call    ?KerbMapKerbError@@YAJJ@Z; KerbMapKerbError(long)
0x140016dbf  jmp     short loc_140016DD4
0x140016dc1  mov     r8, rdi
0x140016dc4  lea     rcx, [rsp+130h+var_C8]
0x140016dc9  mov     edx, 7
0x140016dce  call    cs:__imp_?KerbClientPackAsn1Buffer@@YAJPEAXKPEAU_KERB_ASN1_DATA@@@Z; KerbClientPackAsn1Buffer(void *,ulong,_KERB_ASN1_DATA *)
0x140016dd4  mov     ebx, eax
0x140016dd6  lea     r12, WPP_GLOBAL_Control
0x140016ddd  mov     rcx, [rbp+37h+arg_0]
0x140016de1  call    ??$KerbClientFreeAsn1DecodedData@PEAUPKERB_AUTHORIZATION_DATA_s@@@@YAXPEAPEAUPKERB_AUTHORIZATION_DATA_s@@@Z; KerbClientFreeAsn1DecodedData<PKERB_AUTHORIZATION_DATA_s *>(PKERB_AUTHORIZATION_DATA_s * *)
0x140016de6  mov     rdx, [rsp+130h+var_D0]
0x140016deb  test    rdx, rdx
0x140016dee  jz      short loc_140016DFA
0x140016df0  mov     ecx, 9
0x140016df5  call    KerbFreeData
0x140016dfa  mov     rcx, gs:60h
0x140016e03  mov     r8, r15; P
0x140016e06  xor     edx, edx; Flags
0x140016e08  mov     rcx, [rcx+30h]; HeapHandle
0x140016e0c  call    cs:__imp_RtlFreeHeap
0x140016e12  mov     rcx, [rbp+37h+var_B8+8]; void *
0x140016e16  test    rcx, rcx
0x140016e19  jz      short loc_140016E20
0x140016e1b  call    SafeAllocaFreeToHeap
0x140016e20  test    ebx, ebx
0x140016e22  jns     short loc_140016E56
0x140016e24  mov     rcx, cs:WPP_GLOBAL_Control
0x140016e2b  cmp     rcx, r12
0x140016e2e  jz      short loc_140016E56
0x140016e30  test    byte ptr [rcx+1Ch], 1
0x140016e34  jz      short loc_140016E56
0x140016e36  mov     rcx, [rcx+10h]
0x140016e3a  lea     r9, aKerbiumcreatea; "KerbIumCreateApReqAuthenticator"
0x140016e41  mov     edx, 19h
0x140016e46  mov     dword ptr [rsp+130h+var_110], ebx
0x140016e4a  lea     r8, WPP_d5c6fd37444639aeca2bc0daa2920ffe_Traceguids
0x140016e51  call    WPP_SF_sd
0x140016e56  lea     rcx, [rbp+37h+var_A8]; this
0x140016e5a  call    ??1KerbIumClearKey@@QEAA@XZ; KerbIumClearKey::~KerbIumClearKey(void)
0x140016e5f  lea     rcx, [rbp+37h+var_70]; this
0x140016e63  call    ??1KerbIumClearKey@@QEAA@XZ; KerbIumClearKey::~KerbIumClearKey(void)
0x140016e68  mov     eax, ebx
0x140016e6a  mov     rbx, [rsp+130h+arg_8]
0x140016e72  add     rsp, 100h
0x140016e79  pop     r15
0x140016e7b  pop     r14
0x140016e7d  pop     r13
0x140016e7f  pop     r12
0x140016e81  pop     rdi
0x140016e82  pop     rsi
0x140016e83  pop     rbp
0x140016e84  retn
```
