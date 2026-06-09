# KerbIumDestroyKeyAgreement

- ea: `0x140017be0`
- end: `0x140017cf3`
- name: `KerbIumDestroyKeyAgreement`
- size: `275`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140004ca8`
- `0x14001212c`
- `0x1400144f8`
- `0x140014f1c`
- `0x140017be0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140017bfd`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140017bfd`
- `ntdll!RtlAvlRemoveNode` at `0x140017c8b`
- `ntdll!RtlAvlRemoveNode` at `0x140017c8b`
- `ntdll!RtlLeaveCriticalSection` at `0x140017c98`
- `ntdll!RtlLeaveCriticalSection` at `0x140017c98`
- `ntdll!RtlEnterCriticalSection` at `0x140017c49`
- `ntdll!RtlEnterCriticalSection` at `0x140017c49`

## pseudocode

```c
__int64 __fastcall KerbIumDestroyKeyAgreement(__int64 a1, __int64 a2)
{
  struct _RTL_BALANCED_NODE *v3; // rbx
  int v4; // eax
  unsigned int v5; // edx
  __int64 v6; // [rsp+48h] [rbp+10h] BYREF

  v6 = a2;
  if ( qword_140052C40 == a1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        94,
        WPP_d5c6fd37444639aeca2bc0daa2920ffe_Traceguids,
        "KerbIumDestroyKeyAgreement");
    RtlEnterCriticalSection(&KeyAgreementTableLock);
    v3 = KeyAgreementTable;
    if ( KeyAgreementTable )
    {
      do
      {
        v4 = KeyAgreementHandleCompare(&v6, v3);
        if ( v4 >= 0 )
        {
          if ( v4 <= 0 )
            break;
          v3 = v3->Children[1];
        }
        else
        {
          v3 = v3->Children[0];
        }
      }
      while ( v3 );
      if ( v3 )
        RtlAvlRemoveNode(&KeyAgreementTable, v3);
    }
    RtlLeaveCriticalSection(&KeyAgreementTableLock);
    if ( v3 )
    {
      AvlKeyAgreementNode::`scalar deleting destructor'((AvlKeyAgreementNode *)v3, v5);
      return 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          95,
          (unsigned int)WPP_d5c6fd37444639aeca2bc0daa2920ffe_Traceguids,
          (unsigned int)"KerbIumDestroyKeyAgreement",
          v6);
      return 3221225480LL;
    }
  }
  else
  {
    Sleep(5u);
    return 3221225506LL;
  }
}

```

## disassembly

```asm
0x140017be0  mov     [rsp+arg_0], rbx
0x140017be5  mov     [rsp+arg_8], rdx
0x140017bea  push    rdi
0x140017beb  sub     rsp, 30h
0x140017bef  cmp     cs:qword_140052C40, rcx
0x140017bf6  jz      short loc_140017C0D
0x140017bf8  mov     ecx, 5; dwMilliseconds
0x140017bfd  call    cs:__imp_Sleep
0x140017c03  mov     eax, 0C0000022h
0x140017c08  jmp     loc_140017CE8
0x140017c0d  mov     rcx, cs:WPP_GLOBAL_Control
0x140017c14  lea     rdi, WPP_GLOBAL_Control
0x140017c1b  cmp     rcx, rdi
0x140017c1e  jz      short loc_140017C42
0x140017c20  test    byte ptr [rcx+1Ch], 4
0x140017c24  jz      short loc_140017C42
0x140017c26  mov     rcx, [rcx+10h]
0x140017c2a  lea     r9, aKerbiumdestroy; "KerbIumDestroyKeyAgreement"
0x140017c31  mov     edx, 5Eh ; '^'
0x140017c36  lea     r8, WPP_d5c6fd37444639aeca2bc0daa2920ffe_Traceguids
0x140017c3d  call    WPP_SF_s
0x140017c42  lea     rcx, ?KeyAgreementTableLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x140017c49  call    cs:__imp_RtlEnterCriticalSection
0x140017c4f  mov     rbx, cs:?KeyAgreementTable@@3U_RTL_AVL_TREE@@A; _RTL_AVL_TREE KeyAgreementTable
0x140017c56  test    rbx, rbx
0x140017c59  jz      short loc_140017C91
0x140017c5b  mov     rdx, rbx; struct _RTL_BALANCED_NODE *
0x140017c5e  lea     rcx, [rsp+38h+arg_8]; void *
0x140017c63  call    ?KeyAgreementHandleCompare@@YAJPEAXPEAU_RTL_BALANCED_NODE@@@Z; KeyAgreementHandleCompare(void *,_RTL_BALANCED_NODE *)
0x140017c68  test    eax, eax
0x140017c6a  jns     short loc_140017C71
0x140017c6c  mov     rbx, [rbx]
0x140017c6f  jmp     short loc_140017C77
0x140017c71  jle     short loc_140017C7C
0x140017c73  mov     rbx, [rbx+8]
0x140017c77  test    rbx, rbx
0x140017c7a  jnz     short loc_140017C5B
0x140017c7c  test    rbx, rbx
0x140017c7f  jz      short loc_140017C91
0x140017c81  mov     rdx, rbx
0x140017c84  lea     rcx, ?KeyAgreementTable@@3U_RTL_AVL_TREE@@A; _RTL_AVL_TREE KeyAgreementTable
0x140017c8b  call    cs:__imp_RtlAvlRemoveNode
0x140017c91  lea     rcx, ?KeyAgreementTableLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x140017c98  call    cs:__imp_RtlLeaveCriticalSection
0x140017c9e  test    rbx, rbx
0x140017ca1  jnz     short loc_140017CDE
0x140017ca3  mov     rcx, cs:WPP_GLOBAL_Control
0x140017caa  cmp     rcx, rdi
0x140017cad  jz      short loc_140017CD7
0x140017caf  test    byte ptr [rcx+1Ch], 1
0x140017cb3  jz      short loc_140017CD7
0x140017cb5  mov     eax, dword ptr [rsp+38h+arg_8]
0x140017cb9  lea     edx, [rbx+5Fh]
0x140017cbc  mov     rcx, [rcx+10h]
0x140017cc0  lea     r9, aKerbiumdestroy; "KerbIumDestroyKeyAgreement"
0x140017cc7  lea     r8, WPP_d5c6fd37444639aeca2bc0daa2920ffe_Traceguids
0x140017cce  mov     [rsp+38h+var_18], eax
0x140017cd2  call    WPP_SF_sd
0x140017cd7  mov     eax, 0C0000008h
0x140017cdc  jmp     short loc_140017CE8
0x140017cde  mov     rcx, rbx; this
0x140017ce1  call    ??_GAvlKeyAgreementNode@@QEAAPEAXI@Z; AvlKeyAgreementNode::`scalar deleting destructor'(uint)
0x140017ce6  xor     eax, eax
0x140017ce8  mov     rbx, [rsp+38h+arg_0]
0x140017ced  add     rsp, 30h
0x140017cf1  pop     rdi
0x140017cf2  retn
```
