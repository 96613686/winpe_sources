# KerbIumCreateDHKeyAgreement

- ea: `0x140016e90`
- end: `0x140016fc3`
- name: `KerbIumCreateDHKeyAgreement`
- size: `307`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140004ca8`
- `0x14001212c`
- `0x14001489c`
- `0x140016e90`
- `0x14001d584`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140016eb6`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140016eb6`

## string_xrefs

- `0x140016ee3`: `KerbIumCreateDHKeyAgreement`
- `0x140016f8f`: `KerbIumCreateDHKeyAgreement`

## pseudocode

```c
__int64 __fastcall KerbIumCreateDHKeyAgreement(
        __int64 a1,
        struct _CRYPTOAPI_BLOB *a2,
        struct _CRYPTOAPI_BLOB *a3,
        struct _CRYPTOAPI_BLOB *a4,
        __int64 a5,
        int *a6,
        __int64 a7,
        __int64 a8)
{
  struct KerbKeyAgreement *v12; // rax
  int v13; // ebx

  if ( qword_140052C40 != a1 )
  {
    Sleep(5u);
    return 3221225506LL;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      86,
      WPP_d5c6fd37444639aeca2bc0daa2920ffe_Traceguids,
      "KerbIumCreateDHKeyAgreement");
  if ( a5 && a6 && a7 && a8 )
  {
    v12 = KerbIumDHKeyAgreement::Create(a2, a3, a4, a6);
    if ( v12 )
    {
      v13 = FinishKeyAgreementCreation(v12, (unsigned int)*a6, a5, a7, a8);
      if ( v13 >= 0 )
        return (unsigned int)v13;
    }
    else
    {
      v13 = -1073741801;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        87,
        (unsigned int)WPP_d5c6fd37444639aeca2bc0daa2920ffe_Traceguids,
        (unsigned int)"KerbIumCreateDHKeyAgreement",
        v13);
    return (unsigned int)v13;
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x140016e90  push    rbx
0x140016e92  push    rbp
0x140016e93  push    r12
0x140016e95  push    r13
0x140016e97  push    r14
0x140016e99  push    r15
0x140016e9b  sub     rsp, 38h
0x140016e9f  cmp     cs:qword_140052C40, rcx
0x140016ea6  mov     r14, r9
0x140016ea9  mov     r15, r8
0x140016eac  mov     r12, rdx
0x140016eaf  jz      short loc_140016EC6
0x140016eb1  mov     ecx, 5; dwMilliseconds
0x140016eb6  call    cs:__imp_Sleep
0x140016ebc  mov     eax, 0C0000022h
0x140016ec1  jmp     loc_140016FB4
0x140016ec6  mov     rcx, cs:WPP_GLOBAL_Control
0x140016ecd  lea     r13, WPP_GLOBAL_Control
0x140016ed4  cmp     rcx, r13
0x140016ed7  jz      short loc_140016EFB
0x140016ed9  test    byte ptr [rcx+1Ch], 4
0x140016edd  jz      short loc_140016EFB
0x140016edf  mov     rcx, [rcx+10h]
0x140016ee3  lea     r9, aKerbiumcreated; "KerbIumCreateDHKeyAgreement"
0x140016eea  mov     edx, 56h ; 'V'
0x140016eef  lea     r8, WPP_d5c6fd37444639aeca2bc0daa2920ffe_Traceguids
0x140016ef6  call    WPP_SF_s
0x140016efb  cmp     [rsp+68h+arg_20], 0
0x140016f04  jz      loc_140016FAF
0x140016f0a  mov     rbx, [rsp+68h+arg_28]
0x140016f12  test    rbx, rbx
0x140016f15  jz      loc_140016FAF
0x140016f1b  cmp     [rsp+68h+arg_30], 0
0x140016f24  jz      loc_140016FAF
0x140016f2a  mov     rbp, [rsp+68h+arg_38]
0x140016f32  test    rbp, rbp
0x140016f35  jz      short loc_140016FAF
0x140016f37  mov     r9, rbx; int *
0x140016f3a  mov     r8, r14; struct _CRYPTOAPI_BLOB *
0x140016f3d  mov     rdx, r15; struct _CRYPTOAPI_BLOB *
0x140016f40  mov     rcx, r12; struct _CRYPTOAPI_BLOB *
0x140016f43  call    ?Create@KerbIumDHKeyAgreement@@SAPEAVKerbKeyAgreement@@PEAU_CRYPTOAPI_BLOB@@00PEAJ@Z; KerbIumDHKeyAgreement::Create(_CRYPTOAPI_BLOB *,_CRYPTOAPI_BLOB *,_CRYPTOAPI_BLOB *,long *)
0x140016f48  test    rax, rax
0x140016f4b  jnz     short loc_140016F54
0x140016f4d  mov     ebx, 0C0000017h
0x140016f52  jmp     short loc_140016F79
0x140016f54  mov     r9, [rsp+68h+arg_30]
0x140016f5c  mov     rcx, rax
0x140016f5f  mov     r8, [rsp+68h+arg_20]
0x140016f67  mov     edx, [rbx]
0x140016f69  mov     [rsp+68h+var_48], rbp
0x140016f6e  call    FinishKeyAgreementCreation
0x140016f73  mov     ebx, eax
0x140016f75  test    eax, eax
0x140016f77  jns     short loc_140016FAB
0x140016f79  mov     rcx, cs:WPP_GLOBAL_Control
0x140016f80  cmp     rcx, r13
0x140016f83  jz      short loc_140016FAB
0x140016f85  test    byte ptr [rcx+1Ch], 1
0x140016f89  jz      short loc_140016FAB
0x140016f8b  mov     rcx, [rcx+10h]
0x140016f8f  lea     r9, aKerbiumcreated; "KerbIumCreateDHKeyAgreement"
0x140016f96  mov     edx, 57h ; 'W'
0x140016f9b  mov     dword ptr [rsp+68h+var_48], ebx
0x140016f9f  lea     r8, WPP_d5c6fd37444639aeca2bc0daa2920ffe_Traceguids
0x140016fa6  call    WPP_SF_sd
0x140016fab  mov     eax, ebx
0x140016fad  jmp     short loc_140016FB4
0x140016faf  mov     eax, 0C000000Dh
0x140016fb4  add     rsp, 38h
0x140016fb8  pop     r15
0x140016fba  pop     r14
0x140016fbc  pop     r13
0x140016fbe  pop     r12
0x140016fc0  pop     rbp
0x140016fc1  pop     rbx
0x140016fc2  retn
```
