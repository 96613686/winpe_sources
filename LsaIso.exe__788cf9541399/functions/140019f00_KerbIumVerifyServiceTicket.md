# KerbIumVerifyServiceTicket

- ea: `0x140019f00`
- end: `0x14001a0e2`
- name: `KerbIumVerifyServiceTicket`
- size: `482`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task`

## callees

- `0x14001212c`
- `0x14001431c`
- `0x14001449c`
- `0x140014f38`
- `0x140019f00`
- `0x14001a0e8`
- `0x14001b770`
- `0x14001bc24`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140019f4e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140019f4e`
- `KerbClientShared!KerbClientPackAsn1Buffer` at `0x14001a031`
- `KerbClientShared!KerbClientPackAsn1Buffer` at `0x14001a031`
- `KerbClientShared!KerbClientUnpackAsn1BufferVoid` at `0x140019ff2`
- `KerbClientShared!KerbClientUnpackAsn1BufferVoid` at `0x140019ff2`

## string_xrefs

- `0x140019f7b`: `KerbIumVerifyServiceTicket`
- `0x14001a097`: `KerbIumVerifyServiceTicket`

## pseudocode

```c
__int64 __fastcall KerbIumVerifyServiceTicket(
        __int64 a1,
        const struct _KERB_ASN1_DATA *a2,
        struct _KERB_ENCRYPTION_KEY *a3,
        __int64 a4,
        struct _KERB_ASN1_DATA *a5,
        int *a6)
{
  void *v8; // rsi
  int v11; // ebx
  int *v12; // rdi
  struct _KERB_ASN1_DATA *v13; // r14
  int v14; // edx
  int v15; // r8d
  int v16; // r9d
  int v17; // eax
  int v18; // eax
  void *v20; // [rsp+40h] [rbp-40h] BYREF
  _BYTE v21[56]; // [rsp+48h] [rbp-38h] BYREF
  void *v22; // [rsp+B0h] [rbp+30h] BYREF

  v20 = 0;
  v8 = 0;
  v22 = 0;
  KerbIumClearKey::KerbIumClearKey((KerbIumClearKey *)v21, a3);
  if ( qword_140052C40 != a1 )
  {
    Sleep(5u);
    v11 = -1073741790;
    goto LABEL_31;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      22,
      WPP_d5c6fd37444639aeca2bc0daa2920ffe_Traceguids,
      "KerbIumVerifyServiceTicket");
  v12 = a6;
  if ( a2 )
  {
    if ( a3 )
    {
      v13 = a5;
      if ( !a5 )
      {
        v11 = -1073741582;
        goto LABEL_18;
      }
      if ( !a6 )
      {
        v11 = -1073741581;
        goto LABEL_18;
      }
      if ( (int)KerbIumClearKey::Status((KerbIumClearKey *)v21) >= 0 )
      {
        *(_OWORD *)v13 = 0;
        v11 = KerbClientUnpackAsn1BufferVoid(a2, 0x32u, &v20);
        if ( v11 >= 0 )
        {
          v17 = KerbVerifyTicket((_DWORD)v20, v14, v15, v16, (__int64)v21, a4, (__int64)&v22);
          v8 = v22;
          *v12 = v17;
          if ( !v17 )
            v11 = KerbClientPackAsn1Buffer(v8, 0x33u, v13);
        }
        goto LABEL_18;
      }
    }
    v11 = -1073741584;
  }
  else
  {
    v11 = -1073741585;
  }
LABEL_18:
  if ( v20 )
    KerbFreeData(50);
  if ( v8 )
    KerbFreeData(51);
  if ( (v11 < 0 || v12 && *v12)
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    if ( v12 )
      v18 = *v12;
    else
      LOBYTE(v18) = 0;
    WPP_SF_sDD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      23,
      (unsigned int)WPP_d5c6fd37444639aeca2bc0daa2920ffe_Traceguids,
      (unsigned int)"KerbIumVerifyServiceTicket",
      v11,
      v18);
  }
LABEL_31:
  KerbIumClearKey::~KerbIumClearKey((KerbIumClearKey *)v21);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140019f00  mov     [rsp-28h+arg_8], rbx
0x140019f05  mov     [rsp-28h+arg_10], rsi
0x140019f0a  push    rbp
0x140019f0b  push    rdi
0x140019f0c  push    r12
0x140019f0e  push    r14
0x140019f10  push    r15
0x140019f12  mov     rbp, rsp
0x140019f15  sub     rsp, 80h
0x140019f1c  mov     r15, rdx
0x140019f1f  mov     [rbp+var_40], 0
0x140019f27  mov     rbx, rcx
0x140019f2a  xor     esi, esi
0x140019f2c  mov     rdx, r8; struct _KERB_ENCRYPTION_KEY *
0x140019f2f  mov     [rbp+arg_0], rsi
0x140019f33  lea     rcx, [rbp+var_38]; this
0x140019f37  mov     r12, r9
0x140019f3a  mov     r14, r8
0x140019f3d  call    ??0KerbIumClearKey@@QEAA@PEAU_KERB_ENCRYPTION_KEY@@@Z; KerbIumClearKey::KerbIumClearKey(_KERB_ENCRYPTION_KEY *)
0x140019f42  cmp     cs:qword_140052C40, rbx
0x140019f49  jz      short loc_140019F5E
0x140019f4b  lea     ecx, [rsi+5]; dwMilliseconds
0x140019f4e  call    cs:__imp_Sleep
0x140019f54  mov     ebx, 0C0000022h
0x140019f59  jmp     loc_14001A0BB
0x140019f5e  mov     rax, cs:WPP_GLOBAL_Control
0x140019f65  lea     rcx, WPP_GLOBAL_Control
0x140019f6c  cmp     rax, rcx
0x140019f6f  jz      short loc_140019F93
0x140019f71  test    byte ptr [rax+1Ch], 4
0x140019f75  jz      short loc_140019F93
0x140019f77  mov     rcx, [rax+10h]
0x140019f7b  lea     r9, aKerbiumverifys; "KerbIumVerifyServiceTicket"
0x140019f82  mov     edx, 16h
0x140019f87  lea     r8, WPP_d5c6fd37444639aeca2bc0daa2920ffe_Traceguids
0x140019f8e  call    WPP_SF_s
0x140019f93  mov     rdi, [rbp+arg_28]
0x140019f97  test    r15, r15
0x140019f9a  jnz     short loc_140019FA6
0x140019f9c  mov     ebx, 0C00000EFh
0x140019fa1  jmp     loc_14001A039
0x140019fa6  test    r14, r14
0x140019fa9  jnz     short loc_140019FB5
0x140019fab  mov     ebx, 0C00000F0h
0x140019fb0  jmp     loc_14001A039
0x140019fb5  mov     r14, [rbp+arg_20]
0x140019fb9  test    r14, r14
0x140019fbc  jnz     short loc_140019FC5
0x140019fbe  mov     ebx, 0C00000F2h
0x140019fc3  jmp     short loc_14001A039
0x140019fc5  test    rdi, rdi
0x140019fc8  jnz     short loc_140019FD1
0x140019fca  mov     ebx, 0C00000F3h
0x140019fcf  jmp     short loc_14001A039
0x140019fd1  lea     rcx, [rbp+var_38]; this
0x140019fd5  call    ?Status@KerbIumClearKey@@QEBAJXZ; KerbIumClearKey::Status(void)
0x140019fda  test    eax, eax
0x140019fdc  js      short loc_140019FAB
0x140019fde  xorps   xmm0, xmm0
0x140019fe1  lea     r8, [rbp+var_40]
0x140019fe5  mov     edx, 32h ; '2'
0x140019fea  mov     rcx, r15
0x140019fed  movdqu  xmmword ptr [r14], xmm0
0x140019ff2  call    cs:__imp_?KerbClientUnpackAsn1BufferVoid@@YAJAEBU_KERB_ASN1_DATA@@KPEAPEAX@Z; KerbClientUnpackAsn1BufferVoid(_KERB_ASN1_DATA const &,ulong,void * *)
0x140019ff8  mov     ebx, eax
0x140019ffa  test    eax, eax
0x140019ffc  js      short loc_14001A039
0x140019ffe  mov     rcx, [rbp+var_40]
0x14001a002  lea     rax, [rbp+arg_0]
0x14001a006  mov     [rsp+80h+var_50], rax
0x14001a00b  lea     rax, [rbp+var_38]
0x14001a00f  mov     [rsp+80h+var_58], r12
0x14001a014  mov     [rsp+80h+var_60], rax
0x14001a019  call    KerbVerifyTicket
0x14001a01e  mov     rsi, [rbp+arg_0]
0x14001a022  mov     [rdi], eax
0x14001a024  test    eax, eax
0x14001a026  jnz     short loc_14001A039
0x14001a028  mov     r8, r14
0x14001a02b  lea     edx, [rax+33h]
0x14001a02e  mov     rcx, rsi
0x14001a031  call    cs:__imp_?KerbClientPackAsn1Buffer@@YAJPEAXKPEAU_KERB_ASN1_DATA@@@Z; KerbClientPackAsn1Buffer(void *,ulong,_KERB_ASN1_DATA *)
0x14001a037  mov     ebx, eax
0x14001a039  mov     rdx, [rbp+var_40]
0x14001a03d  test    rdx, rdx
0x14001a040  jz      short loc_14001A04C
0x14001a042  mov     ecx, 32h ; '2'
0x14001a047  call    KerbFreeData
0x14001a04c  test    rsi, rsi
0x14001a04f  jz      short loc_14001A05E
0x14001a051  mov     rdx, rsi
0x14001a054  mov     ecx, 33h ; '3'
0x14001a059  call    KerbFreeData
0x14001a05e  test    ebx, ebx
0x14001a060  js      short loc_14001A06C
0x14001a062  test    rdi, rdi
0x14001a065  jz      short loc_14001A0BB
0x14001a067  cmp     dword ptr [rdi], 0
0x14001a06a  jz      short loc_14001A0BB
0x14001a06c  mov     rax, cs:WPP_GLOBAL_Control
0x14001a073  lea     rcx, WPP_GLOBAL_Control
0x14001a07a  cmp     rax, rcx
0x14001a07d  jz      short loc_14001A0BB
0x14001a07f  test    byte ptr [rax+1Ch], 1
0x14001a083  jz      short loc_14001A0BB
0x14001a085  test    rdi, rdi
0x14001a088  jz      short loc_14001A08E
0x14001a08a  mov     eax, [rdi]
0x14001a08c  jmp     short loc_14001A090
0x14001a08e  xor     eax, eax
0x14001a090  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a097  lea     r9, aKerbiumverifys; "KerbIumVerifyServiceTicket"
0x14001a09e  mov     dword ptr [rsp+80h+var_58], eax
0x14001a0a2  lea     r8, WPP_d5c6fd37444639aeca2bc0daa2920ffe_Traceguids
0x14001a0a9  mov     edx, 17h
0x14001a0ae  mov     dword ptr [rsp+80h+var_60], ebx
0x14001a0b2  mov     rcx, [rcx+10h]
0x14001a0b6  call    WPP_SF_sDD
0x14001a0bb  lea     rcx, [rbp+var_38]; this
0x14001a0bf  call    ??1KerbIumClearKey@@QEAA@XZ; KerbIumClearKey::~KerbIumClearKey(void)
0x14001a0c4  lea     r11, [rsp+80h+var_s0]
0x14001a0cc  mov     eax, ebx
0x14001a0ce  mov     rbx, [r11+38h]
0x14001a0d2  mov     rsi, [r11+40h]
0x14001a0d6  mov     rsp, r11
0x14001a0d9  pop     r15
0x14001a0db  pop     r14
0x14001a0dd  pop     r12
0x14001a0df  pop     rdi
0x14001a0e0  pop     rbp
0x14001a0e1  retn
```
