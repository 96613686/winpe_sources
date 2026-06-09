# KerbIumComputeTgsChecksum

- ea: `0x140016310`
- end: `0x14001648f`
- name: `KerbIumComputeTgsChecksum`
- size: `383`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x140004ca8`
- `0x14001212c`
- `0x140014370`
- `0x14001449c`
- `0x140014f38`
- `0x140016310`
- `0x14001b770`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140016360`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140016360`
- `KerbClientShared!KerbClientPackAsn1Buffer` at `0x140016419`
- `KerbClientShared!KerbClientPackAsn1Buffer` at `0x140016419`
- `KerbClientShared!KerbClientFree` at `0x140016425`
- `KerbClientShared!KerbClientFree` at `0x140016425`
- `KerbClientShared!KerbClientUnpackAsn1BufferVoid` at `0x1400163e6`
- `KerbClientShared!KerbClientUnpackAsn1BufferVoid` at `0x1400163e6`
- `KerbClientShared!KerbClientComputeTgsChecksum` at `0x140016401`
- `KerbClientShared!KerbClientComputeTgsChecksum` at `0x140016401`

## string_xrefs

- `0x14001638d`: `KerbIumComputeTgsChecksum`
- `0x140016458`: `KerbIumComputeTgsChecksum`

## pseudocode

```c
__int64 __fastcall KerbIumComputeTgsChecksum(
        __int64 a1,
        const struct _KERB_ASN1_DATA *a2,
        struct _KERB_ENCRYPTION_KEY *a3,
        unsigned int a4,
        struct _KERB_ASN1_DATA *a5)
{
  int v9; // ebx
  struct _KERB_ASN1_DATA *v10; // rdi
  __int128 v12; // [rsp+30h] [rbp-31h] BYREF
  void *v13; // [rsp+40h] [rbp-21h]
  _BYTE v14[104]; // [rsp+48h] [rbp-19h] BYREF
  struct KERB_KDC_REQUEST_BODY *v15; // [rsp+C0h] [rbp+5Fh] BYREF

  v15 = 0;
  v13 = 0;
  v12 = 0;
  KerbIumClearKey::KerbIumClearKey((KerbIumClearKey *)v14, a3, a3);
  if ( qword_140052C40 != a1 )
  {
    Sleep(5u);
    v9 = -1073741790;
    goto LABEL_22;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      33,
      WPP_d5c6fd37444639aeca2bc0daa2920ffe_Traceguids,
      "KerbIumComputeTgsChecksum");
  if ( a2 )
  {
    if ( a3 )
    {
      v10 = a5;
      if ( !a5 )
      {
        v9 = -1073741582;
        goto LABEL_16;
      }
      if ( (int)KerbIumClearKey::Status((KerbIumClearKey *)v14) >= 0 )
      {
        v9 = KerbClientUnpackAsn1BufferVoid(a2, 0x48u, (void **)&v15);
        if ( v9 >= 0 )
        {
          v9 = KerbClientComputeTgsChecksum(v15, (struct _KERB_ENCRYPTION_KEY *)v14, a4, (struct KERB_CHECKSUM *)&v12);
          if ( v9 >= 0 )
            v9 = KerbClientPackAsn1Buffer(&v12, 9u, v10);
        }
        goto LABEL_16;
      }
    }
    v9 = -1073741584;
  }
  else
  {
    v9 = -1073741585;
  }
LABEL_16:
  KerbClientFree(v13);
  if ( v15 )
    KerbFreeData(72);
  if ( v9 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      34,
      (unsigned int)WPP_d5c6fd37444639aeca2bc0daa2920ffe_Traceguids,
      (unsigned int)"KerbIumComputeTgsChecksum",
      v9);
LABEL_22:
  KerbIumClearKey::~KerbIumClearKey((KerbIumClearKey *)v14);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140016310  push    rbp
0x140016312  push    rbx
0x140016313  push    rsi
0x140016314  push    rdi
0x140016315  push    r12
0x140016317  push    r14
0x140016319  lea     rbp, [rsp-27h]
0x14001631e  sub     rsp, 88h
0x140016325  mov     rsi, rdx
0x140016328  mov     [rbp+4Fh+arg_0], 0
0x140016330  mov     rbx, rcx
0x140016333  xorps   xmm0, xmm0
0x140016336  xor     eax, eax
0x140016338  lea     rcx, [rbp+4Fh+var_68]; this
0x14001633c  mov     rdx, r8; struct _KERB_ENCRYPTION_KEY *
0x14001633f  mov     [rbp+4Fh+var_70], rax
0x140016343  movups  [rbp+4Fh+var_80], xmm0
0x140016347  mov     r14d, r9d
0x14001634a  mov     rdi, r8
0x14001634d  call    ??0KerbIumClearKey@@QEAA@PEAU_KERB_ENCRYPTION_KEY@@AEBUAllowUnencryptedInput@0@@Z; KerbIumClearKey::KerbIumClearKey(_KERB_ENCRYPTION_KEY *,KerbIumClearKey::AllowUnencryptedInput const &)
0x140016352  cmp     cs:qword_140052C40, rbx
0x140016359  jz      short loc_140016370
0x14001635b  mov     ecx, 5; dwMilliseconds
0x140016360  call    cs:__imp_Sleep
0x140016366  mov     ebx, 0C0000022h
0x14001636b  jmp     loc_140016474
0x140016370  mov     rcx, cs:WPP_GLOBAL_Control
0x140016377  lea     r12, WPP_GLOBAL_Control
0x14001637e  cmp     rcx, r12
0x140016381  jz      short loc_1400163A5
0x140016383  test    byte ptr [rcx+1Ch], 4
0x140016387  jz      short loc_1400163A5
0x140016389  mov     rcx, [rcx+10h]
0x14001638d  lea     r9, aKerbiumcompute; "KerbIumComputeTgsChecksum"
0x140016394  mov     edx, 21h ; '!'
0x140016399  lea     r8, WPP_d5c6fd37444639aeca2bc0daa2920ffe_Traceguids
0x1400163a0  call    WPP_SF_s
0x1400163a5  test    rsi, rsi
0x1400163a8  jnz     short loc_1400163B1
0x1400163aa  mov     ebx, 0C00000EFh
0x1400163af  jmp     short loc_140016421
0x1400163b1  test    rdi, rdi
0x1400163b4  jnz     short loc_1400163BD
0x1400163b6  mov     ebx, 0C00000F0h
0x1400163bb  jmp     short loc_140016421
0x1400163bd  mov     rdi, [rbp+4Fh+arg_20]
0x1400163c1  test    rdi, rdi
0x1400163c4  jnz     short loc_1400163CD
0x1400163c6  mov     ebx, 0C00000F2h
0x1400163cb  jmp     short loc_140016421
0x1400163cd  lea     rcx, [rbp+4Fh+var_68]; this
0x1400163d1  call    ?Status@KerbIumClearKey@@QEBAJXZ; KerbIumClearKey::Status(void)
0x1400163d6  test    eax, eax
0x1400163d8  js      short loc_1400163B6
0x1400163da  lea     r8, [rbp+4Fh+arg_0]
0x1400163de  mov     edx, 48h ; 'H'
0x1400163e3  mov     rcx, rsi
0x1400163e6  call    cs:__imp_?KerbClientUnpackAsn1BufferVoid@@YAJAEBU_KERB_ASN1_DATA@@KPEAPEAX@Z; KerbClientUnpackAsn1BufferVoid(_KERB_ASN1_DATA const &,ulong,void * *)
0x1400163ec  mov     ebx, eax
0x1400163ee  test    eax, eax
0x1400163f0  js      short loc_140016421
0x1400163f2  mov     rcx, [rbp+4Fh+arg_0]
0x1400163f6  lea     r9, [rbp+4Fh+var_80]
0x1400163fa  mov     r8d, r14d
0x1400163fd  lea     rdx, [rbp+4Fh+var_68]
0x140016401  call    cs:__imp_?KerbClientComputeTgsChecksum@@YAJPEAUKERB_KDC_REQUEST_BODY@@PEAU_KERB_ENCRYPTION_KEY@@KPEAUKERB_CHECKSUM@@@Z; KerbClientComputeTgsChecksum(KERB_KDC_REQUEST_BODY *,_KERB_ENCRYPTION_KEY *,ulong,KERB_CHECKSUM *)
0x140016407  mov     ebx, eax
0x140016409  test    eax, eax
0x14001640b  js      short loc_140016421
0x14001640d  mov     r8, rdi
0x140016410  lea     rcx, [rbp+4Fh+var_80]
0x140016414  mov     edx, 9
0x140016419  call    cs:__imp_?KerbClientPackAsn1Buffer@@YAJPEAXKPEAU_KERB_ASN1_DATA@@@Z; KerbClientPackAsn1Buffer(void *,ulong,_KERB_ASN1_DATA *)
0x14001641f  mov     ebx, eax
0x140016421  mov     rcx, [rbp+4Fh+var_70]
0x140016425  call    cs:__imp_?KerbClientFree@@YAXPEAX@Z; KerbClientFree(void *)
0x14001642b  mov     rdx, [rbp+4Fh+arg_0]
0x14001642f  test    rdx, rdx
0x140016432  jz      short loc_14001643E
0x140016434  mov     ecx, 48h ; 'H'
0x140016439  call    KerbFreeData
0x14001643e  test    ebx, ebx
0x140016440  jns     short loc_140016474
0x140016442  mov     rcx, cs:WPP_GLOBAL_Control
0x140016449  cmp     rcx, r12
0x14001644c  jz      short loc_140016474
0x14001644e  test    byte ptr [rcx+1Ch], 1
0x140016452  jz      short loc_140016474
0x140016454  mov     rcx, [rcx+10h]
0x140016458  lea     r9, aKerbiumcompute; "KerbIumComputeTgsChecksum"
0x14001645f  mov     edx, 22h ; '"'
0x140016464  mov     [rsp+0B0h+var_90], ebx
0x140016468  lea     r8, WPP_d5c6fd37444639aeca2bc0daa2920ffe_Traceguids
0x14001646f  call    WPP_SF_sd
0x140016474  lea     rcx, [rbp+4Fh+var_68]; this
0x140016478  call    ??1KerbIumClearKey@@QEAA@XZ; KerbIumClearKey::~KerbIumClearKey(void)
0x14001647d  mov     eax, ebx
0x14001647f  add     rsp, 88h
0x140016486  pop     r14
0x140016488  pop     r12
0x14001648a  pop     rdi
0x14001648b  pop     rsi
0x14001648c  pop     rbx
0x14001648d  pop     rbp
0x14001648e  retn
```
