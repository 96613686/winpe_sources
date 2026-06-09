# KerbIumCreateECDHKeyAgreement

- ea: `0x140016fd0`
- end: `0x1400170cb`
- name: `KerbIumCreateECDHKeyAgreement`
- size: `251`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140004ca8`
- `0x14001212c`
- `0x14001489c`
- `0x140016fd0`
- `0x14001debc`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140016ff4`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140016ff4`

## string_xrefs

- `0x140017021`: `KerbIumCreateECDHKeyAgreement`
- `0x140017099`: `KerbIumCreateECDHKeyAgreement`

## pseudocode

```c
__int64 __fastcall KerbIumCreateECDHKeyAgreement(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        int *a4,
        __int64 a5,
        __int64 a6)
{
  struct KerbCredIsoApi *v10; // rcx
  struct KerbKeyAgreement *KerbECDHKeyAgreement; // rax
  int v12; // eax
  unsigned int v13; // ebx

  if ( qword_140052C40 == a1 )
  {
    v10 = (struct KerbCredIsoApi *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        84,
        WPP_d5c6fd37444639aeca2bc0daa2920ffe_Traceguids,
        "KerbIumCreateECDHKeyAgreement");
    if ( a3 && a4 && a5 && a6 )
    {
      KerbECDHKeyAgreement = CreateKerbECDHKeyAgreement(v10, a2, a4);
      v12 = FinishKeyAgreementCreation(KerbECDHKeyAgreement, (unsigned int)*a4, a3, a5, a6);
      v13 = v12;
      if ( v12 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          85,
          (unsigned int)WPP_d5c6fd37444639aeca2bc0daa2920ffe_Traceguids,
          (unsigned int)"KerbIumCreateECDHKeyAgreement",
          v12);
      return v13;
    }
    else
    {
      return 3221225485LL;
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
0x140016fd0  push    rbx
0x140016fd2  push    rbp
0x140016fd3  push    rsi
0x140016fd4  push    rdi
0x140016fd5  push    r14
0x140016fd7  push    r15
0x140016fd9  sub     rsp, 38h
0x140016fdd  cmp     cs:qword_140052C40, rcx
0x140016fe4  mov     rdi, r9
0x140016fe7  mov     rbp, r8
0x140016fea  mov     r14d, edx
0x140016fed  jz      short loc_140017004
0x140016fef  mov     ecx, 5; dwMilliseconds
0x140016ff4  call    cs:__imp_Sleep
0x140016ffa  mov     eax, 0C0000022h
0x140016fff  jmp     loc_1400170BE
0x140017004  mov     rcx, cs:WPP_GLOBAL_Control
0x14001700b  lea     r15, WPP_GLOBAL_Control
0x140017012  cmp     rcx, r15
0x140017015  jz      short loc_140017039
0x140017017  test    byte ptr [rcx+1Ch], 4
0x14001701b  jz      short loc_140017039
0x14001701d  mov     rcx, [rcx+10h]
0x140017021  lea     r9, aKerbiumcreatee; "KerbIumCreateECDHKeyAgreement"
0x140017028  mov     edx, 54h ; 'T'
0x14001702d  lea     r8, WPP_d5c6fd37444639aeca2bc0daa2920ffe_Traceguids
0x140017034  call    WPP_SF_s
0x140017039  test    rbp, rbp
0x14001703c  jz      short loc_1400170B9
0x14001703e  test    rdi, rdi
0x140017041  jz      short loc_1400170B9
0x140017043  mov     rbx, [rsp+68h+arg_20]
0x14001704b  test    rbx, rbx
0x14001704e  jz      short loc_1400170B9
0x140017050  mov     rsi, [rsp+68h+arg_28]
0x140017058  test    rsi, rsi
0x14001705b  jz      short loc_1400170B9
0x14001705d  mov     r8, rdi; int *
0x140017060  mov     edx, r14d; unsigned int
0x140017063  call    ?CreateKerbECDHKeyAgreement@@YAPEAVKerbKeyAgreement@@PEAVKerbCredIsoApi@@KPEAJ@Z; CreateKerbECDHKeyAgreement(KerbCredIsoApi *,ulong,long *)
0x140017068  mov     edx, [rdi]
0x14001706a  mov     r9, rbx
0x14001706d  mov     r8, rbp
0x140017070  mov     [rsp+68h+var_48], rsi
0x140017075  mov     rcx, rax
0x140017078  call    FinishKeyAgreementCreation
0x14001707d  mov     ebx, eax
0x14001707f  test    eax, eax
0x140017081  jns     short loc_1400170B5
0x140017083  mov     rcx, cs:WPP_GLOBAL_Control
0x14001708a  cmp     rcx, r15
0x14001708d  jz      short loc_1400170B5
0x14001708f  test    byte ptr [rcx+1Ch], 1
0x140017093  jz      short loc_1400170B5
0x140017095  mov     rcx, [rcx+10h]
0x140017099  lea     r9, aKerbiumcreatee; "KerbIumCreateECDHKeyAgreement"
0x1400170a0  mov     edx, 55h ; 'U'
0x1400170a5  mov     dword ptr [rsp+68h+var_48], eax
0x1400170a9  lea     r8, WPP_d5c6fd37444639aeca2bc0daa2920ffe_Traceguids
0x1400170b0  call    WPP_SF_sd
0x1400170b5  mov     eax, ebx
0x1400170b7  jmp     short loc_1400170BE
0x1400170b9  mov     eax, 0C000000Dh
0x1400170be  add     rsp, 38h
0x1400170c2  pop     r15
0x1400170c4  pop     r14
0x1400170c6  pop     rdi
0x1400170c7  pop     rsi
0x1400170c8  pop     rbp
0x1400170c9  pop     rbx
0x1400170ca  retn
```
