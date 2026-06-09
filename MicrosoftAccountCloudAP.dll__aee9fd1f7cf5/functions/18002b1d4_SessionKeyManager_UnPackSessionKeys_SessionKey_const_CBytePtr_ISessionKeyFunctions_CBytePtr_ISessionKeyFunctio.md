# SessionKeyManager::UnPackSessionKeys(SessionKey const &,CBytePtr &,ISessionKeyFunctions * *,CBytePtr &,ISessionKeyFunctions * *)

- ea: `0x18002b1d4`
- end: `0x18002b502`
- name: `?UnPackSessionKeys@SessionKeyManager@@AEAAJAEBVSessionKey@@AEAVCBytePtr@@PEAPEAVISessionKeyFunctions@@12@Z`
- size: `814`
- prototype: `int(SessionKeyManager *__hidden this, const struct SessionKey *, struct CBytePtr *, struct ISessionKeyFunctions **, struct CBytePtr *, struct ISessionKeyFunctions **)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18002aee0`

## callees

- `0x180007eb8`
- `0x180008440`
- `0x18000baac`
- `0x180026c8c`
- `0x180027fc0`
- `0x180028050`
- `0x18002aeb0`
- `0x18002b1d4`

## string_xrefs

- `0x18002b480`: `hr = SafeCopyMemory(&sessionKey1SizeBytes, sizeof(DWORD), pSessionKey, sizeof(DWORD))`
- `0x18002b4a1`: `hr = SafeCopyMemory(&sessionKey1Type, sizeof(DWORD), pSessionKey, sizeof(DWORD))`
- `0x18002b44c`: `hr = SafeCopyMemory(&sessionKey2SizeBytes, sizeof(DWORD), pSessionKey, sizeof(DWORD))`
- `0x18002b464`: `hr = SafeCopyMemory(&sessionKey2Type, sizeof(DWORD), pSessionKey, sizeof(DWORD))`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SessionKeyManager::UnPackSessionKeys(
        SessionKeyManager *this,
        const struct SessionKey *a2,
        struct CBytePtr *a3,
        struct ISessionKeyFunctions **a4,
        struct CBytePtr *a5,
        struct ISessionKeyFunctions **a6)
{
  bool v10; // r9
  unsigned __int8 *v11; // rdx
  unsigned int v12; // r8d
  int SessionKeyFunctions; // eax
  __int64 v14; // rdx
  int v15; // r8d
  int v16; // r9d
  const char *v17; // rax
  char v18; // r8
  char *v19; // rbx
  char *v20; // rsi
  bool v21; // r9
  __int64 v22; // rbx
  __int64 v23; // rdi
  const char *v24; // rax
  char v25; // r8
  int v26; // r9d
  unsigned __int8 *v27; // rsi
  int v28; // eax
  unsigned __int8 *v29; // rsi
  bool v30; // r9
  int v31; // eax
  unsigned int v32; // ebx
  char *v34; // [rsp+20h] [rbp-89h]
  unsigned int v35; // [rsp+30h] [rbp-79h] BYREF
  unsigned int Destination; // [rsp+34h] [rbp-75h] BYREF
  unsigned int v37; // [rsp+38h] [rbp-71h] BYREF
  unsigned int v38; // [rsp+3Ch] [rbp-6Dh] BYREF
  unsigned int v39; // [rsp+40h] [rbp-69h] BYREF
  void *Source; // [rsp+48h] [rbp-61h]
  int v41; // [rsp+50h] [rbp-59h]
  int v42; // [rsp+58h] [rbp-51h] BYREF
  __int64 v43; // [rsp+60h] [rbp-49h]
  int v44; // [rsp+68h] [rbp-41h]
  int v45; // [rsp+70h] [rbp-39h] BYREF
  __int64 v46; // [rsp+78h] [rbp-31h]
  int v47; // [rsp+80h] [rbp-29h]
  _QWORD v48[13]; // [rsp+88h] [rbp-21h] BYREF
  int v49; // [rsp+108h] [rbp+5Fh] BYREF

  v49 = 0;
  Source = 0;
  v39 = 0;
  v41 = 0;
  v46 = 0;
  v45 = 0;
  v47 = 0;
  Destination = 0;
  v35 = 0;
  v43 = 0;
  v42 = 0;
  v44 = 0;
  v38 = 0;
  v37 = 0;
  v48[0] = "SessionKeyManager::UnPackSessionKeys";
  v48[1] = &v49;
  v48[2] = 0;
  v48[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\sessionkeymanager\\sessionkeymanager.cpp",
    "SessionKeyManager::UnPackSessionKeys",
    (const char *)0x128,
    0,
    (const unsigned __int16 *)v34);
  v11 = (unsigned __int8 *)*((_QWORD *)a2 + 1);
  v12 = *(_DWORD *)a2;
  if ( *((_DWORD *)a2 + 6) != 4 )
  {
    CBytePtr::Attach(a3, v11, v12, v10);
    SessionKeyFunctions = SessionKeyManager::GetSessionKeyFunctions(this, *((unsigned int *)a2 + 6), a4);
    v49 = SessionKeyFunctions;
    if ( SessionKeyFunctions < 0 )
      Telemetry::IfFailExit(
        (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\sessionkeymanager\\sessionkeymanager.cpp",
        "SessionKeyManager::UnPackSessionKeys",
        45,
        SessionKeyFunctions,
        "hr = GetSessionKeyFunctions(sessionKey.GetSessionKeyType(), pSessionKeyFunctions1)");
    goto LABEL_26;
  }
  CBytePtr::Attach((CBytePtr *)&v39, v11, v12, v10);
  if ( v39 <= 0x10 )
  {
    v16 = -2147188620;
    v17 = "bpSessionKey.GetLength() > 4 * sizeof(DWORD)";
    v18 = 52;
    goto LABEL_24;
  }
  v19 = (char *)Source;
  if ( memcpy_s_0(&Destination, 4u, Source, 4u) )
  {
    v16 = -2147418113;
    v17 = "hr = SafeCopyMemory(&sessionKey1Type, sizeof(DWORD), pSessionKey, sizeof(DWORD))";
    v18 = 55;
LABEL_24:
    v49 = v16;
    Telemetry::IfFailExit(
      (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\sessionkeymanager\\sessionkeymanager.cpp",
      "SessionKeyManager::UnPackSessionKeys",
      v18,
      v16,
      v17);
    goto LABEL_26;
  }
  v49 = 0;
  v20 = v19 + 4;
  if ( memcpy_s_0(&v35, 4u, v19 + 4, 4u) )
  {
    v49 = -2147418113;
    Telemetry::IfFailExit(
      (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\sessionkeymanager\\sessionkeymanager.cpp",
      "SessionKeyManager::UnPackSessionKeys",
      58,
      -2147418113,
      "hr = SafeCopyMemory(&sessionKey1SizeBytes, sizeof(DWORD), pSessionKey, sizeof(DWORD))");
    goto LABEL_26;
  }
  v49 = 0;
  v22 = v39;
  v23 = v35;
  if ( v35 >= (unsigned __int64)v39 - 16 )
  {
    v24 = "sessionKey1SizeBytes < (bpSessionKey.GetLength() - (4 * sizeof(DWORD)))";
    v25 = 59;
LABEL_10:
    v26 = -2147188620;
LABEL_11:
    v49 = v26;
    Telemetry::IfFailExit(
      (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\sessionkeymanager\\sessionkeymanager.cpp",
      "SessionKeyManager::UnPackSessionKeys",
      v25,
      v26,
      v24);
    goto LABEL_26;
  }
  v27 = (unsigned __int8 *)(v20 + 4);
  CBytePtr::Attach(a3, v27, v35, v21);
  v28 = SessionKeyManager::GetSessionKeyFunctions(this, Destination, a4);
  v49 = v28;
  if ( v28 < 0 )
  {
    Telemetry::IfFailExit(
      (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\sessionkeymanager\\sessionkeymanager.cpp",
      "SessionKeyManager::UnPackSessionKeys",
      63,
      v28,
      "hr = GetSessionKeyFunctions(sessionKey1Type, pSessionKeyFunctions1)");
    goto LABEL_26;
  }
  v29 = &v27[v23];
  if ( memcpy_s_0(&v38, 4u, v29, 4u) )
  {
    v26 = -2147418113;
    v24 = "hr = SafeCopyMemory(&sessionKey2Type, sizeof(DWORD), pSessionKey, sizeof(DWORD))";
    v25 = 68;
    goto LABEL_11;
  }
  v49 = 0;
  if ( memcpy_s_0(&v37, 4u, v29 + 4, 4u) )
  {
    v26 = -2147418113;
    v24 = "hr = SafeCopyMemory(&sessionKey2SizeBytes, sizeof(DWORD), pSessionKey, sizeof(DWORD))";
    v25 = 71;
    goto LABEL_11;
  }
  v49 = 0;
  if ( v37 != v22 - v23 - 16 )
  {
    v24 = "sessionKey2SizeBytes == (bpSessionKey.GetLength() - (4 * sizeof(DWORD)) - sessionKey1SizeBytes)";
    v25 = 72;
    goto LABEL_10;
  }
  CBytePtr::Attach(a5, v29 + 8, v37, v30);
  v31 = SessionKeyManager::GetSessionKeyFunctions(this, v38, a6);
  v49 = v31;
  if ( v31 < 0 )
    Telemetry::IfFailExit(
      (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\sessionkeymanager\\sessionkeymanager.cpp",
      "SessionKeyManager::UnPackSessionKeys",
      76,
      v31,
      "hr = GetSessionKeyFunctions(sessionKey2Type, pSessionKeyFunctions2)");
LABEL_26:
  v32 = v49;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v48, v14, v15);
  CBytePtr::Empty((CBytePtr *)&v42);
  CBytePtr::Empty((CBytePtr *)&v45);
  CBytePtr::Empty((CBytePtr *)&v39);
  return v32;
}

```

## disassembly

```asm
0x18002b1d4  push    rbp
0x18002b1d6  push    rbx
0x18002b1d7  push    rsi
0x18002b1d8  push    rdi
0x18002b1d9  push    r12
0x18002b1db  push    r13
0x18002b1dd  push    r14
0x18002b1df  push    r15
0x18002b1e1  lea     rbp, [rsp-0Fh]
0x18002b1e6  sub     rsp, 0B8h
0x18002b1ed  mov     r15, r9
0x18002b1f0  mov     r12, r8
0x18002b1f3  mov     rbx, rdx
0x18002b1f6  mov     r14, rcx
0x18002b1f9  xor     r13d, r13d
0x18002b1fc  mov     [rbp+47h+arg_8], r13d
0x18002b200  mov     [rbp+47h+Source], r13
0x18002b204  mov     [rbp+47h+var_B0], r13d
0x18002b208  mov     [rbp+47h+var_A0], r13d
0x18002b20c  mov     [rbp+47h+var_78], r13
0x18002b210  mov     [rbp+47h+var_80], r13d
0x18002b214  mov     [rbp+47h+var_70], r13d
0x18002b218  mov     [rbp+47h+Destination], r13d
0x18002b21c  mov     [rbp+47h+var_C0], r13d
0x18002b220  mov     [rbp+47h+var_90], r13
0x18002b224  mov     [rbp+47h+var_98], r13d
0x18002b228  mov     [rbp+47h+var_88], r13d
0x18002b22c  mov     [rbp+47h+var_B4], r13d
0x18002b230  mov     [rbp+47h+var_B8], r13d
0x18002b234  lea     rdi, aSessionkeymana; "SessionKeyManager::UnPackSessionKeys"
0x18002b23b  mov     [rbp+47h+var_68], rdi
0x18002b23f  lea     rax, [rbp+47h+arg_8]
0x18002b243  mov     [rbp+47h+var_60], rax
0x18002b247  mov     [rbp+47h+var_58], r13
0x18002b24b  mov     [rbp+47h+var_50], r13
0x18002b24f  xor     r9d, r9d; unsigned int
0x18002b252  mov     r8d, 128h; char *
0x18002b258  mov     rdx, rdi; char *
0x18002b25b  lea     rsi, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18002b262  mov     rcx, rsi; this
0x18002b265  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18002b26a  nop
0x18002b26b  mov     rdx, [rbx+8]; unsigned __int8 *
0x18002b26f  mov     r8d, [rbx]; unsigned int
0x18002b272  cmp     dword ptr [rbx+18h], 4
0x18002b276  jz      short loc_18002B2B3
0x18002b278  mov     rcx, r12; this
0x18002b27b  call    ?Attach@CBytePtr@@QEAAXPEAEK_N@Z; CBytePtr::Attach(uchar *,ulong,bool)
0x18002b280  mov     r8, r15
0x18002b283  mov     edx, [rbx+18h]
0x18002b286  mov     rcx, r14
0x18002b289  call    ?GetSessionKeyFunctions@SessionKeyManager@@AEAAJW4Type@SessionKeyTypes@@PEAPEAVISessionKeyFunctions@@@Z; SessionKeyManager::GetSessionKeyFunctions(SessionKeyTypes::Type,ISessionKeyFunctions * *)
0x18002b28e  mov     [rbp+47h+arg_8], eax
0x18002b291  test    eax, eax
0x18002b293  jns     loc_18002B4C2
0x18002b299  lea     r8, aHrGetsessionke_1; "hr = GetSessionKeyFunctions(sessionKey."...
0x18002b2a0  mov     [rsp+0F0h+var_D0], r8
0x18002b2a5  mov     r9d, eax
0x18002b2a8  mov     r8d, 12Dh
0x18002b2ae  jmp     loc_18002B4B7
0x18002b2b3  lea     rcx, [rbp+47h+var_B0]; this
0x18002b2b7  call    ?Attach@CBytePtr@@QEAAXPEAEK_N@Z; CBytePtr::Attach(uchar *,ulong,bool)
0x18002b2bc  cmp     [rbp+47h+var_B0], 10h
0x18002b2c0  ja      short loc_18002B2DA
0x18002b2c2  mov     r9d, 80048074h
0x18002b2c8  lea     rax, aBpsessionkeyGe; "bpSessionKey.GetLength() > 4 * sizeof(D"...
0x18002b2cf  mov     r8d, 134h
0x18002b2d5  jmp     loc_18002B4AE
0x18002b2da  mov     rbx, [rbp+47h+Source]
0x18002b2de  mov     edx, 4; DestinationSize
0x18002b2e3  mov     r9d, edx; SourceSize
0x18002b2e6  mov     r8, rbx; Source
0x18002b2e9  lea     rcx, [rbp+47h+Destination]; Destination
0x18002b2ed  call    memcpy_s_0
0x18002b2f2  test    eax, eax
0x18002b2f4  jnz     loc_18002B49B
0x18002b2fa  mov     [rbp+47h+arg_8], r13d
0x18002b2fe  lea     rsi, [rbx+4]
0x18002b302  mov     eax, 4
0x18002b307  mov     r9d, eax; SourceSize
0x18002b30a  mov     r8, rsi; Source
0x18002b30d  mov     edx, eax; DestinationSize
0x18002b30f  lea     rcx, [rbp+47h+var_C0]; Destination
0x18002b313  call    memcpy_s_0
0x18002b318  test    eax, eax
0x18002b31a  jnz     loc_18002B476
0x18002b320  mov     [rbp+47h+arg_8], r13d
0x18002b324  mov     ebx, [rbp+47h+var_B0]
0x18002b327  mov     r8d, [rbp+47h+var_C0]; unsigned int
0x18002b32b  mov     edi, r8d
0x18002b32e  lea     rax, [rbx-10h]
0x18002b332  cmp     r8, rax
0x18002b335  jb      short loc_18002B366
0x18002b337  lea     rax, aSessionkey1siz; "sessionKey1SizeBytes < (bpSessionKey.Ge"...
0x18002b33e  mov     r8d, 13Bh
0x18002b344  mov     r9d, 80048074h
0x18002b34a  mov     [rsp+0F0h+var_D0], rax
0x18002b34f  mov     [rbp+47h+arg_8], r9d
0x18002b353  lea     rdx, aSessionkeymana; "SessionKeyManager::UnPackSessionKeys"
0x18002b35a  lea     rcx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18002b361  jmp     loc_18002B4BD
0x18002b366  add     rsi, 4
0x18002b36a  mov     rdx, rsi; unsigned __int8 *
0x18002b36d  mov     rcx, r12; this
0x18002b370  call    ?Attach@CBytePtr@@QEAAXPEAEK_N@Z; CBytePtr::Attach(uchar *,ulong,bool)
0x18002b375  mov     r8, r15
0x18002b378  mov     edx, [rbp+47h+Destination]
0x18002b37b  mov     rcx, r14
0x18002b37e  call    ?GetSessionKeyFunctions@SessionKeyManager@@AEAAJW4Type@SessionKeyTypes@@PEAPEAVISessionKeyFunctions@@@Z; SessionKeyManager::GetSessionKeyFunctions(SessionKeyTypes::Type,ISessionKeyFunctions * *)
0x18002b383  mov     [rbp+47h+arg_8], eax
0x18002b386  test    eax, eax
0x18002b388  jns     short loc_18002B3A1
0x18002b38a  lea     rcx, aHrGetsessionke_0; "hr = GetSessionKeyFunctions(sessionKey1"...
0x18002b391  mov     [rsp+0F0h+var_D0], rcx
0x18002b396  mov     r9d, eax
0x18002b399  mov     r8d, 13Fh
0x18002b39f  jmp     short loc_18002B353
0x18002b3a1  add     rsi, rdi
0x18002b3a4  mov     r15d, 4
0x18002b3aa  mov     r9d, r15d; SourceSize
0x18002b3ad  mov     r8, rsi; Source
0x18002b3b0  mov     edx, r15d; DestinationSize
0x18002b3b3  lea     rcx, [rbp+47h+var_B4]; Destination
0x18002b3b7  call    memcpy_s_0
0x18002b3bc  test    eax, eax
0x18002b3be  jnz     loc_18002B45E
0x18002b3c4  mov     [rbp+47h+arg_8], r13d
0x18002b3c8  mov     r9d, r15d; SourceSize
0x18002b3cb  lea     r8, [rsi+4]; Source
0x18002b3cf  mov     edx, r15d; DestinationSize
0x18002b3d2  lea     rcx, [rbp+47h+var_B8]; Destination
0x18002b3d6  call    memcpy_s_0
0x18002b3db  test    eax, eax
0x18002b3dd  jnz     short loc_18002B446
0x18002b3df  mov     [rbp+47h+arg_8], r13d
0x18002b3e3  sub     rbx, rdi
0x18002b3e6  sub     rbx, 10h
0x18002b3ea  mov     r8d, [rbp+47h+var_B8]; unsigned int
0x18002b3ee  cmp     r8, rbx
0x18002b3f1  jz      short loc_18002B405
0x18002b3f3  lea     rax, aSessionkey2siz; "sessionKey2SizeBytes == (bpSessionKey.G"...
0x18002b3fa  mov     r8d, 148h
0x18002b400  jmp     loc_18002B344
0x18002b405  lea     rdx, [rsi+8]; unsigned __int8 *
0x18002b409  mov     rcx, [rbp+47h+arg_20]; this
0x18002b40d  call    ?Attach@CBytePtr@@QEAAXPEAEK_N@Z; CBytePtr::Attach(uchar *,ulong,bool)
0x18002b412  mov     r8, [rbp+47h+arg_28]
0x18002b416  mov     edx, [rbp+47h+var_B4]
0x18002b419  mov     rcx, r14
0x18002b41c  call    ?GetSessionKeyFunctions@SessionKeyManager@@AEAAJW4Type@SessionKeyTypes@@PEAPEAVISessionKeyFunctions@@@Z; SessionKeyManager::GetSessionKeyFunctions(SessionKeyTypes::Type,ISessionKeyFunctions * *)
0x18002b421  mov     [rbp+47h+arg_8], eax
0x18002b424  test    eax, eax
0x18002b426  jns     loc_18002B4C2
0x18002b42c  lea     rcx, aHrGetsessionke; "hr = GetSessionKeyFunctions(sessionKey2"...
0x18002b433  mov     [rsp+0F0h+var_D0], rcx
0x18002b438  mov     r9d, eax
0x18002b43b  mov     r8d, 14Ch
0x18002b441  jmp     loc_18002B353
0x18002b446  mov     r9d, 8000FFFFh
0x18002b44c  lea     rax, aHrSafecopymemo_4; "hr = SafeCopyMemory(&sessionKey2SizeByt"...
0x18002b453  mov     r8d, 147h
0x18002b459  jmp     loc_18002B34A
0x18002b45e  mov     r9d, 8000FFFFh
0x18002b464  lea     rax, aHrSafecopymemo_1; "hr = SafeCopyMemory(&sessionKey2Type, s"...
0x18002b46b  mov     r8d, 144h
0x18002b471  jmp     loc_18002B34A
0x18002b476  mov     r9d, 8000FFFFh
0x18002b47c  mov     [rbp+47h+arg_8], r9d
0x18002b480  lea     rax, aHrSafecopymemo_3; "hr = SafeCopyMemory(&sessionKey1SizeByt"...
0x18002b487  mov     [rsp+0F0h+var_D0], rax
0x18002b48c  mov     r8d, 13Ah
0x18002b492  lea     rcx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18002b499  jmp     short loc_18002B4BA
0x18002b49b  mov     r9d, 8000FFFFh; int
0x18002b4a1  lea     rax, aHrSafecopymemo; "hr = SafeCopyMemory(&sessionKey1Type, s"...
0x18002b4a8  mov     r8d, 137h; unsigned int
0x18002b4ae  mov     [rsp+0F0h+var_D0], rax; char *
0x18002b4b3  mov     [rbp+47h+arg_8], r9d
0x18002b4b7  mov     rcx, rsi; char *
0x18002b4ba  mov     rdx, rdi; char *
0x18002b4bd  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18002b4c2  mov     ebx, [rbp+47h+arg_8]
0x18002b4c5  lea     rcx, [rbp+47h+var_68]
0x18002b4c9  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18002b4ce  nop
0x18002b4cf  lea     rcx, [rbp+47h+var_98]; this
0x18002b4d3  call    ?Empty@CBytePtr@@QEAAXXZ; CBytePtr::Empty(void)
0x18002b4d8  nop
0x18002b4d9  lea     rcx, [rbp+47h+var_80]; this
0x18002b4dd  call    ?Empty@CBytePtr@@QEAAXXZ; CBytePtr::Empty(void)
0x18002b4e2  nop
0x18002b4e3  lea     rcx, [rbp+47h+var_B0]; this
0x18002b4e7  call    ?Empty@CBytePtr@@QEAAXXZ; CBytePtr::Empty(void)
0x18002b4ec  mov     eax, ebx
0x18002b4ee  add     rsp, 0B8h
0x18002b4f5  pop     r15
0x18002b4f7  pop     r14
0x18002b4f9  pop     r13
0x18002b4fb  pop     r12
0x18002b4fd  pop     rdi
0x18002b4fe  pop     rsi
0x18002b4ff  pop     rbx
0x18002b500  pop     rbp
0x18002b501  retn
```
