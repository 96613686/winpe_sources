# KerbIumFinalizeKeyAgreement

- ea: `0x140017e00`
- end: `0x140018051`
- name: `KerbIumFinalizeKeyAgreement`
- size: `593`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140004ca8`
- `0x14001212c`
- `0x1400144f8`
- `0x140014560`
- `0x140014f1c`
- `0x140017e00`
- `0x14001de00`
- `0x14003a010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140017e50`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140017e50`
- `ntdll!RtlAvlRemoveNode` at `0x140017f05`
- `ntdll!RtlAvlRemoveNode` at `0x140017f05`
- `ntdll!RtlLeaveCriticalSection` at `0x140017f19`
- `ntdll!RtlLeaveCriticalSection` at `0x140017f19`
- `ntdll!RtlEnterCriticalSection` at `0x140017ec5`
- `ntdll!RtlEnterCriticalSection` at `0x140017ec5`

## pseudocode

```c
__int64 __fastcall KerbIumFinalizeKeyAgreement(
        __int64 a1,
        _QWORD *a2,
        unsigned int a3,
        int a4,
        __int64 a5,
        int a6,
        __int64 a7,
        int a8,
        struct _KERB_ENCRYPTION_KEY *a9)
{
  struct _RTL_BALANCED_NODE *v13; // rbx
  int v14; // eax
  int v15; // edi
  int v16; // eax
  _QWORD *v17; // rcx
  int v18; // edx
  unsigned int v19; // edx
  __int128 v20; // [rsp+40h] [rbp-59h] BYREF
  __int128 v21; // [rsp+50h] [rbp-49h] BYREF
  __int128 v22; // [rsp+60h] [rbp-39h]
  __int64 v23; // [rsp+70h] [rbp-29h]
  _OWORD v24[2]; // [rsp+78h] [rbp-21h] BYREF
  __int64 v25; // [rsp+98h] [rbp-1h]

  v23 = 0;
  v25 = 0;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  memset(v24, 0, sizeof(v24));
  if ( qword_140052C40 != a1 )
  {
    Sleep(5u);
    return 3221225506LL;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      98,
      WPP_d5c6fd37444639aeca2bc0daa2920ffe_Traceguids,
      "KerbIumFinalizeKeyAgreement");
  LODWORD(v20) = a6;
  *((_QWORD *)&v20 + 1) = a7;
  if ( a4 )
  {
    DWORD2(v22) = a4;
    LOWORD(v21) = 128;
    v23 = a5;
  }
  RtlEnterCriticalSection(&KeyAgreementTableLock);
  v13 = KeyAgreementTable;
  if ( KeyAgreementTable )
  {
    do
    {
      v14 = KeyAgreementHandleCompare(a2, v13);
      if ( v14 >= 0 )
      {
        if ( v14 <= 0 )
          break;
        v13 = v13->Children[1];
      }
      else
      {
        v13 = v13->Children[0];
      }
    }
    while ( v13 );
    if ( v13 )
    {
      RtlAvlRemoveNode(&KeyAgreementTable, v13);
      *a2 = -1;
    }
  }
  RtlLeaveCriticalSection(&KeyAgreementTableLock);
  if ( !v13 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        99,
        (unsigned int)WPP_d5c6fd37444639aeca2bc0daa2920ffe_Traceguids,
        (unsigned int)"KerbIumFinalizeKeyAgreement",
        *(_DWORD *)a2);
    v15 = -1073741816;
    goto LABEL_30;
  }
  v16 = ((__int64 (__fastcall *)(struct _RTL_BALANCED_NODE *, _QWORD, __int128 *, __int128 *, unsigned int, _OWORD *))v13[1].Children[1]->Children[0][1].Children[1])(
          v13[1].Children[1],
          a3,
          &v20,
          &v21,
          a8 | 2u,
          v24);
  v15 = v16;
  if ( v16 >= 0 )
  {
    v16 = EncryptKeyWithAssert(a8 | 2u, (const struct _KERB_ENCRYPTION_KEY *)v24, a9, 0xA11u);
    v15 = v16;
    if ( v16 >= 0 )
      goto LABEL_30;
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_30;
    v18 = 101;
  }
  else
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_30;
    v18 = 100;
  }
  WPP_SF_sd(
    v17[2],
    v18,
    (unsigned int)WPP_d5c6fd37444639aeca2bc0daa2920ffe_Traceguids,
    (unsigned int)"KerbIumFinalizeKeyAgreement",
    v16);
LABEL_30:
  KerbFreeKey(v24);
  if ( v13 )
    AvlKeyAgreementNode::`scalar deleting destructor'((AvlKeyAgreementNode *)v13, v19);
  if ( v15 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      102,
      (unsigned int)WPP_d5c6fd37444639aeca2bc0daa2920ffe_Traceguids,
      (unsigned int)"KerbIumFinalizeKeyAgreement",
      v15);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x140017e00  push    rbp
0x140017e02  push    rbx
0x140017e03  push    rsi
0x140017e04  push    rdi
0x140017e05  push    r13
0x140017e07  push    r14
0x140017e09  push    r15
0x140017e0b  lea     rbp, [rsp-7]
0x140017e10  sub     rsp, 0A0h
0x140017e17  xor     eax, eax
0x140017e19  xorps   xmm0, xmm0
0x140017e1c  cmp     cs:qword_140052C40, rcx
0x140017e23  xorps   xmm1, xmm1
0x140017e26  mov     ebx, r9d
0x140017e29  mov     [rbp+37h+var_60], rax
0x140017e2d  mov     r14d, r8d
0x140017e30  mov     [rbp+37h+var_38], rax
0x140017e34  mov     rdi, rdx
0x140017e37  movups  [rbp+37h+var_90], xmm0
0x140017e3b  movups  [rbp+37h+var_80], xmm1
0x140017e3f  movups  [rbp+37h+var_70], xmm1
0x140017e43  movups  [rbp+37h+var_58], xmm0
0x140017e47  movups  [rbp+37h+var_48], xmm0
0x140017e4b  jz      short loc_140017E60
0x140017e4d  lea     ecx, [rax+5]; dwMilliseconds
0x140017e50  call    cs:__imp_Sleep
0x140017e56  mov     eax, 0C0000022h
0x140017e5b  jmp     loc_14001803F
0x140017e60  mov     rcx, cs:WPP_GLOBAL_Control
0x140017e67  lea     r15, WPP_GLOBAL_Control
0x140017e6e  lea     r13, aKerbiumfinaliz; "KerbIumFinalizeKeyAgreement"
0x140017e75  cmp     rcx, r15
0x140017e78  jz      short loc_140017E98
0x140017e7a  test    byte ptr [rcx+1Ch], 4
0x140017e7e  jz      short loc_140017E98
0x140017e80  mov     rcx, [rcx+10h]
0x140017e84  lea     r8, WPP_d5c6fd37444639aeca2bc0daa2920ffe_Traceguids
0x140017e8b  mov     edx, 62h ; 'b'
0x140017e90  mov     r9, r13
0x140017e93  call    WPP_SF_s
0x140017e98  mov     eax, [rbp+37h+arg_28]
0x140017e9b  mov     dword ptr [rbp+37h+var_90], eax
0x140017e9e  mov     rax, [rbp+37h+arg_30]
0x140017ea2  mov     qword ptr [rbp+37h+var_90+8], rax
0x140017ea6  test    ebx, ebx
0x140017ea8  jz      short loc_140017EBE
0x140017eaa  mov     eax, 80h
0x140017eaf  mov     dword ptr [rbp+37h+var_70+8], ebx
0x140017eb2  mov     word ptr [rbp+37h+var_80], ax
0x140017eb6  mov     rax, [rbp+37h+arg_20]
0x140017eba  mov     [rbp+37h+var_60], rax
0x140017ebe  lea     rcx, ?KeyAgreementTableLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x140017ec5  call    cs:__imp_RtlEnterCriticalSection
0x140017ecb  mov     rbx, cs:?KeyAgreementTable@@3U_RTL_AVL_TREE@@A; _RTL_AVL_TREE KeyAgreementTable
0x140017ed2  test    rbx, rbx
0x140017ed5  jz      short loc_140017F12
0x140017ed7  mov     rdx, rbx; struct _RTL_BALANCED_NODE *
0x140017eda  mov     rcx, rdi; void *
0x140017edd  call    ?KeyAgreementHandleCompare@@YAJPEAXPEAU_RTL_BALANCED_NODE@@@Z; KeyAgreementHandleCompare(void *,_RTL_BALANCED_NODE *)
0x140017ee2  test    eax, eax
0x140017ee4  jns     short loc_140017EEB
0x140017ee6  mov     rbx, [rbx]
0x140017ee9  jmp     short loc_140017EF1
0x140017eeb  jle     short loc_140017EF6
0x140017eed  mov     rbx, [rbx+8]
0x140017ef1  test    rbx, rbx
0x140017ef4  jnz     short loc_140017ED7
0x140017ef6  test    rbx, rbx
0x140017ef9  jz      short loc_140017F12
0x140017efb  mov     rdx, rbx
0x140017efe  lea     rcx, ?KeyAgreementTable@@3U_RTL_AVL_TREE@@A; _RTL_AVL_TREE KeyAgreementTable
0x140017f05  call    cs:__imp_RtlAvlRemoveNode
0x140017f0b  mov     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x140017f12  lea     rcx, ?KeyAgreementTableLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x140017f19  call    cs:__imp_RtlLeaveCriticalSection
0x140017f1f  test    rbx, rbx
0x140017f22  jnz     short loc_140017F5C
0x140017f24  mov     rcx, cs:WPP_GLOBAL_Control
0x140017f2b  cmp     rcx, r15
0x140017f2e  jz      short loc_140017F52
0x140017f30  test    byte ptr [rcx+1Ch], 1
0x140017f34  jz      short loc_140017F52
0x140017f36  mov     eax, [rdi]
0x140017f38  lea     edx, [rbx+63h]
0x140017f3b  mov     rcx, [rcx+10h]
0x140017f3f  lea     r8, WPP_d5c6fd37444639aeca2bc0daa2920ffe_Traceguids
0x140017f46  mov     r9, r13
0x140017f49  mov     [rsp+0D0h+var_B0], eax
0x140017f4d  call    WPP_SF_sd
0x140017f52  mov     edi, 0C0000008h
0x140017f57  jmp     loc_140017FF5
0x140017f5c  mov     rcx, [rbx+20h]
0x140017f60  lea     rdx, [rbp+37h+var_58]
0x140017f64  mov     esi, [rbp+37h+arg_38]
0x140017f67  lea     r9, [rbp+37h+var_80]
0x140017f6b  mov     [rsp+0D0h+var_A8], rdx
0x140017f70  lea     r8, [rbp+37h+var_90]
0x140017f74  or      esi, 2
0x140017f77  mov     edx, r14d
0x140017f7a  mov     rax, [rcx]
0x140017f7d  mov     [rsp+0D0h+var_B0], esi
0x140017f81  mov     rax, [rax+20h]
0x140017f85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017f8a  mov     edi, eax
0x140017f8c  test    eax, eax
0x140017f8e  jns     short loc_140017FA9
0x140017f90  mov     rcx, cs:WPP_GLOBAL_Control
0x140017f97  cmp     rcx, r15
0x140017f9a  jz      short loc_140017FF5
0x140017f9c  test    byte ptr [rcx+1Ch], 1
0x140017fa0  jz      short loc_140017FF5
0x140017fa2  mov     edx, 64h ; 'd'
0x140017fa7  jmp     short loc_140017FDE
0x140017fa9  mov     r8, [rbp+37h+arg_40]; struct _KERB_ENCRYPTION_KEY *
0x140017fb0  lea     rdx, [rbp+37h+var_58]; struct _KERB_ENCRYPTION_KEY *
0x140017fb4  mov     r9d, 0A11h; unsigned int
0x140017fba  mov     ecx, esi; unsigned int
0x140017fbc  call    ?EncryptKeyWithAssert@@YAJKPEBU_KERB_ENCRYPTION_KEY@@PEAU1@K@Z; EncryptKeyWithAssert(ulong,_KERB_ENCRYPTION_KEY const *,_KERB_ENCRYPTION_KEY *,ulong)
0x140017fc1  mov     edi, eax
0x140017fc3  test    eax, eax
0x140017fc5  jns     short loc_140017FF5
0x140017fc7  mov     rcx, cs:WPP_GLOBAL_Control
0x140017fce  cmp     rcx, r15
0x140017fd1  jz      short loc_140017FF5
0x140017fd3  test    byte ptr [rcx+1Ch], 1
0x140017fd7  jz      short loc_140017FF5
0x140017fd9  mov     edx, 65h ; 'e'
0x140017fde  mov     rcx, [rcx+10h]
0x140017fe2  lea     r8, WPP_d5c6fd37444639aeca2bc0daa2920ffe_Traceguids
0x140017fe9  mov     r9, r13
0x140017fec  mov     [rsp+0D0h+var_B0], eax
0x140017ff0  call    WPP_SF_sd
0x140017ff5  lea     rcx, [rbp+37h+var_58]
0x140017ff9  call    KerbFreeKey
0x140017ffe  test    rbx, rbx
0x140018001  jz      short loc_14001800B
0x140018003  mov     rcx, rbx; this
0x140018006  call    ??_GAvlKeyAgreementNode@@QEAAPEAXI@Z; AvlKeyAgreementNode::`scalar deleting destructor'(uint)
0x14001800b  test    edi, edi
0x14001800d  jns     short loc_14001803D
0x14001800f  mov     rcx, cs:WPP_GLOBAL_Control
0x140018016  cmp     rcx, r15
0x140018019  jz      short loc_14001803D
0x14001801b  test    byte ptr [rcx+1Ch], 1
0x14001801f  jz      short loc_14001803D
0x140018021  mov     rcx, [rcx+10h]
0x140018025  lea     r8, WPP_d5c6fd37444639aeca2bc0daa2920ffe_Traceguids
0x14001802c  mov     edx, 66h ; 'f'
0x140018031  mov     [rsp+0D0h+var_B0], edi
0x140018035  mov     r9, r13
0x140018038  call    WPP_SF_sd
0x14001803d  mov     eax, edi
0x14001803f  add     rsp, 0A0h
0x140018046  pop     r15
0x140018048  pop     r14
0x14001804a  pop     r13
0x14001804c  pop     rdi
0x14001804d  pop     rsi
0x14001804e  pop     rbx
0x14001804f  pop     rbp
0x140018050  retn
```
