# GenerateRootKeyAttributes

- ea: `0x180004f9c`
- end: `0x18000527b`
- name: `GenerateRootKeyAttributes`
- size: `735`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004a00`

## callees

- `0x180004f9c`
- `0x1800100d0`
- `0x18001a450`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x180004fde`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18000501f`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x180004fde`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18000501f`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x180005046`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x180005066`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x18000508d`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x180005046`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x180005066`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x18000508d`

## string_xrefs

- `0x180004fed`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdsrootkey.cxx`
- `0x18000510f`: `msKds-CreateTime`
- `0x180005145`: `nTSecurityDescriptor`

## pseudocode

```c
__int64 __fastcall GenerateRootKeyAttributes(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int *a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10)
{
  unsigned __int64 CurrentTimeInULL; // rax
  unsigned int v14; // r9d
  unsigned int v15; // edi
  __int64 v16; // rcx
  __int64 v17; // rcx

  CurrentTimeInULL = GetCurrentTimeInULL();
  if ( (unsigned int)_o__ui64tow_s(CurrentTimeInULL, a10, 21) )
  {
    v14 = 60;
LABEL_3:
    v15 = -2147467259;
    SidKeyDebugTraceError(0x80004005, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsrootkey.cxx", v14);
    return v15;
  }
  if ( (unsigned int)_o__ui64tow_s(a2, a10 + 42, 21) )
  {
    v14 = 68;
    goto LABEL_3;
  }
  if ( (unsigned int)_o__ultow_s(a4[14], a10 + 84, 11, 10) )
  {
    v14 = 76;
    goto LABEL_3;
  }
  if ( (unsigned int)_o__ultow_s(a4[13], a10 + 106, 11, 10) )
  {
    v14 = 84;
    goto LABEL_3;
  }
  if ( (unsigned int)_o__ultow_s(*a4, a10 + 128, 11, 10) )
  {
    v14 = 92;
    goto LABEL_3;
  }
  *(_DWORD *)(a3 + 16) = 0;
  *(_QWORD *)a3 = L"msKds-KDFAlgorithmID";
  v15 = 0;
  *(_QWORD *)(a3 + 8) = *((_QWORD *)a4 + 1);
  *(_QWORD *)(a3 + 24) = L"msKds-RootKeyData";
  v16 = 12;
  *(_QWORD *)(a3 + 32) = a6;
  *(_QWORD *)(a3 + 48) = L"msKds-Version";
  *(_QWORD *)(a3 + 72) = L"msKds-DomainID";
  *(_QWORD *)(a3 + 80) = a1;
  *(_QWORD *)(a3 + 96) = L"objectClass";
  *(_QWORD *)(a3 + 104) = L"msKds-ProvRootKey";
  *(_QWORD *)(a3 + 120) = L"msKds-CreateTime";
  *(_QWORD *)(a3 + 144) = L"msKds-UseStartTime";
  *(_QWORD *)(a3 + 168) = L"cn";
  *(_QWORD *)(a3 + 176) = a5;
  *(_QWORD *)(a3 + 192) = L"nTSecurityDescriptor";
  *(_QWORD *)(a3 + 200) = a7;
  *(_QWORD *)(a3 + 216) = L"msKds-SecretAgreementAlgorithmID";
  *(_DWORD *)(a3 + 20) = 0;
  *(_DWORD *)(a3 + 40) = 0;
  *(_DWORD *)(a3 + 44) = 1;
  *(_QWORD *)(a3 + 64) = 0;
  *(_QWORD *)(a3 + 56) = a10 + 128;
  *(_QWORD *)(a3 + 88) = 0;
  *(_QWORD *)(a3 + 112) = 0;
  *(_QWORD *)(a3 + 136) = 0;
  *(_QWORD *)(a3 + 128) = a10;
  *(_QWORD *)(a3 + 160) = 0;
  *(_QWORD *)(a3 + 152) = a10 + 42;
  *(_QWORD *)(a3 + 184) = 0;
  *(_DWORD *)(a3 + 208) = 0;
  *(_DWORD *)(a3 + 212) = 1;
  *(_DWORD *)(a3 + 232) = 0;
  *(_QWORD *)(a3 + 224) = *((_QWORD *)a4 + 4);
  *(_QWORD *)(a3 + 240) = L"msKds-PublicKeyLength";
  *(_QWORD *)(a3 + 264) = L"msKds-PrivateKeyLength";
  *(_DWORD *)(a3 + 236) = 0;
  *(_QWORD *)(a3 + 256) = 0;
  *(_QWORD *)(a3 + 248) = a10 + 84;
  *(_QWORD *)(a3 + 280) = 0;
  *(_QWORD *)(a3 + 272) = a10 + 106;
  if ( *(_QWORD *)(a9 + 8) )
  {
    *(_DWORD *)(a3 + 304) = 0;
    *(_QWORD *)(a3 + 288) = L"msKds-KDFParam";
    v16 = 13;
    *(_QWORD *)(a3 + 296) = a9;
    *(_DWORD *)(a3 + 308) = 1;
  }
  if ( *(_QWORD *)(a8 + 8) )
  {
    v17 = 3 * v16;
    *(_DWORD *)(a3 + 8 * v17 + 16) = 0;
    *(_QWORD *)(a3 + 8 * v17) = L"msKds-SecretAgreementParam";
    *(_QWORD *)(a3 + 8 * v17 + 8) = a8;
    *(_DWORD *)(a3 + 8 * v17 + 20) = 1;
  }
  return v15;
}

```

## disassembly

```asm
0x180004f9c  mov     [rsp+arg_0], rcx
0x180004fa1  push    rbx
0x180004fa2  push    rbp
0x180004fa3  push    rsi
0x180004fa4  push    rdi
0x180004fa5  push    r12
0x180004fa7  push    r13
0x180004fa9  push    r14
0x180004fab  push    r15
0x180004fad  sub     rsp, 28h
0x180004fb1  mov     rsi, r9
0x180004fb4  mov     rbx, r8
0x180004fb7  mov     rdi, rdx
0x180004fba  call    ?GetCurrentTimeInULL@@YA_KXZ; GetCurrentTimeInULL(void)
0x180004fbf  mov     r13, [rsp+68h+arg_48]
0x180004fc7  mov     r12d, 0Ah
0x180004fcd  mov     r9d, r12d
0x180004fd0  mov     rdx, r13
0x180004fd3  mov     rcx, rax
0x180004fd6  lea     ebp, [r12+0Bh]
0x180004fdb  mov     r8d, ebp
0x180004fde  call    cs:__imp__o__ui64tow_s
0x180004fe4  test    eax, eax
0x180004fe6  jz      short loc_18000500F
0x180004fe8  lea     r9d, [r12+32h]; unsigned int
0x180004fed  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180004ff4  mov     ecx, 80004005h; unsigned int
0x180004ff9  lea     rdx, aHr; "hr"
0x180005000  mov     edi, 80004005h
0x180005005  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000500a  jmp     loc_180005268
0x18000500f  lea     r15, [r13+2Ah]
0x180005013  mov     r9d, r12d
0x180005016  mov     rdx, r15
0x180005019  mov     r8, rbp
0x18000501c  mov     rcx, rdi
0x18000501f  call    cs:__imp__o__ui64tow_s
0x180005025  test    eax, eax
0x180005027  jz      short loc_180005031
0x180005029  mov     r9d, 44h ; 'D'
0x18000502f  jmp     short loc_180004FED
0x180005031  mov     ecx, [rsi+38h]
0x180005034  lea     rbp, [r15+2Ah]
0x180005038  mov     edi, 0Bh
0x18000503d  mov     rdx, rbp
0x180005040  mov     r8d, edi
0x180005043  mov     r9d, r12d
0x180005046  call    cs:__imp__o__ultow_s
0x18000504c  test    eax, eax
0x18000504e  jz      short loc_180005056
0x180005050  lea     r9d, [rdi+41h]
0x180005054  jmp     short loc_180004FED
0x180005056  mov     ecx, [rsi+34h]
0x180005059  lea     r14, [rbp+16h]
0x18000505d  mov     rdx, r14
0x180005060  mov     r9d, r12d
0x180005063  mov     r8, rdi
0x180005066  call    cs:__imp__o__ultow_s
0x18000506c  test    eax, eax
0x18000506e  jz      short loc_18000507B
0x180005070  mov     r9d, 54h ; 'T'
0x180005076  jmp     loc_180004FED
0x18000507b  mov     ecx, [rsi]
0x18000507d  lea     r12, [r14+16h]
0x180005081  mov     rdx, r12
0x180005084  mov     r9d, 0Ah
0x18000508a  mov     r8, rdi
0x18000508d  call    cs:__imp__o__ultow_s
0x180005093  xor     edx, edx
0x180005095  test    eax, eax
0x180005097  jz      short loc_1800050A2
0x180005099  lea     r9d, [rdx+5Ch]
0x18000509d  jmp     loc_180004FED
0x1800050a2  mov     [rbx+10h], edx
0x1800050a5  lea     rax, aMskdsKdfalgori; "msKds-KDFAlgorithmID"
0x1800050ac  mov     [rbx], rax
0x1800050af  mov     r8d, 1
0x1800050b5  mov     rax, [rsi+8]
0x1800050b9  mov     edi, edx
0x1800050bb  mov     [rbx+8], rax
0x1800050bf  lea     rax, aMskdsRootkeyda; "msKds-RootKeyData"
0x1800050c6  mov     [rbx+18h], rax
0x1800050ca  mov     rax, [rsp+68h+arg_28]
0x1800050d2  lea     ecx, [r8+0Bh]
0x1800050d6  mov     [rbx+20h], rax
0x1800050da  lea     rax, aMskdsVersion; "msKds-Version"
0x1800050e1  mov     [rbx+30h], rax
0x1800050e5  lea     rax, aMskdsDomainid; "msKds-DomainID"
0x1800050ec  mov     [rbx+48h], rax
0x1800050f0  mov     rax, [rsp+68h+arg_0]
0x1800050f5  mov     [rbx+50h], rax
0x1800050f9  lea     rax, aObjectclass_0; "objectClass"
0x180005100  mov     [rbx+60h], rax
0x180005104  lea     rax, aMskdsProvrootk; "msKds-ProvRootKey"
0x18000510b  mov     [rbx+68h], rax
0x18000510f  lea     rax, aMskdsCreatetim; "msKds-CreateTime"
0x180005116  mov     [rbx+78h], rax
0x18000511a  lea     rax, aMskdsUsestartt; "msKds-UseStartTime"
0x180005121  mov     [rbx+90h], rax
0x180005128  lea     rax, aCn; "cn"
0x18000512f  mov     [rbx+0A8h], rax
0x180005136  mov     rax, [rsp+68h+arg_20]
0x18000513e  mov     [rbx+0B0h], rax
0x180005145  lea     rax, aNtsecuritydesc; "nTSecurityDescriptor"
0x18000514c  mov     [rbx+0C0h], rax
0x180005153  mov     rax, [rsp+68h+arg_30]
0x18000515b  mov     [rbx+0C8h], rax
0x180005162  lea     rax, aMskdsSecretagr; "msKds-SecretAgreementAlgorithmID"
0x180005169  mov     [rbx+0D8h], rax
0x180005170  mov     [rbx+14h], edx
0x180005173  mov     [rbx+28h], edx
0x180005176  mov     [rbx+2Ch], r8d
0x18000517a  mov     [rbx+40h], rdx
0x18000517e  mov     [rbx+38h], r12
0x180005182  mov     [rbx+58h], rdx
0x180005186  mov     [rbx+70h], rdx
0x18000518a  mov     [rbx+88h], rdx
0x180005191  mov     [rbx+80h], r13
0x180005198  mov     [rbx+0A0h], rdx
0x18000519f  mov     [rbx+98h], r15
0x1800051a6  mov     [rbx+0B8h], rdx
0x1800051ad  mov     [rbx+0D0h], edx
0x1800051b3  mov     [rbx+0D4h], r8d
0x1800051ba  mov     [rbx+0E8h], edx
0x1800051c0  mov     rax, [rsi+20h]
0x1800051c4  mov     [rbx+0E0h], rax
0x1800051cb  lea     rax, aMskdsPublickey; "msKds-PublicKeyLength"
0x1800051d2  mov     [rbx+0F0h], rax
0x1800051d9  lea     rax, aMskdsPrivateke; "msKds-PrivateKeyLength"
0x1800051e0  mov     [rbx+108h], rax
0x1800051e7  mov     rax, [rsp+68h+arg_40]
0x1800051ef  mov     [rbx+0ECh], edx
0x1800051f5  mov     [rbx+100h], rdx
0x1800051fc  mov     [rbx+0F8h], rbp
0x180005203  mov     [rbx+118h], rdx
0x18000520a  mov     [rbx+110h], r14
0x180005211  cmp     [rax+8], rdx
0x180005215  jz      short loc_18000523D
0x180005217  lea     rcx, aMskdsKdfparam; "msKds-KDFParam"
0x18000521e  mov     [rbx+130h], edx
0x180005224  mov     [rbx+120h], rcx
0x18000522b  lea     ecx, [r8+0Ch]
0x18000522f  mov     [rbx+128h], rax
0x180005236  mov     [rbx+134h], r8d
0x18000523d  mov     rax, [rsp+68h+arg_38]
0x180005245  cmp     [rax+8], rdx
0x180005249  jz      short loc_180005268
0x18000524b  lea     rcx, [rcx+rcx*2]
0x18000524f  mov     [rbx+rcx*8+10h], edx
0x180005253  lea     rdx, aMskdsSecretagr_0; "msKds-SecretAgreementParam"
0x18000525a  mov     [rbx+rcx*8], rdx
0x18000525e  mov     [rbx+rcx*8+8], rax
0x180005263  mov     [rbx+rcx*8+14h], r8d
0x180005268  mov     eax, edi
0x18000526a  add     rsp, 28h
0x18000526e  pop     r15
0x180005270  pop     r14
0x180005272  pop     r13
0x180005274  pop     r12
0x180005276  pop     rdi
0x180005277  pop     rsi
0x180005278  pop     rbp
0x180005279  pop     rbx
0x18000527a  retn
```
