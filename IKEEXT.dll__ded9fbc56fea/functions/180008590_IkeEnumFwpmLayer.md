# IkeEnumFwpmLayer

- ea: `0x180008590`
- end: `0x1800087e0`
- name: `IkeEnumFwpmLayer`
- size: `592`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, int, int, int, UINT32 numEntriesRequested, __int64, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18002f2f0`
- `0x18007bd9c`

## callees

- `0x1800061ec`
- `0x180008388`
- `0x180008590`
- `0x180011680`
- `0x18004890c`
- `0x180050850`
- `0x1800528e4`

## import_xrefs

- `fwpuclnt!FwpmFilterDestroyEnumHandle0` at `0x1800086ba`
- `fwpuclnt!FwpmFilterDestroyEnumHandle0` at `0x1800086ba`
- `fwpuclnt!FwpmFilterEnum0` at `0x180008684`
- `fwpuclnt!FwpmFilterEnum0` at `0x180008684`
- `fwpuclnt!FwpmFilterCreateEnumHandle0` at `0x18000864f`
- `fwpuclnt!FwpmFilterCreateEnumHandle0` at `0x18000864f`

## string_xrefs

- `0x180008701`: `FwpmFilterCreateEnumHandle0`

## pseudocode

```c
__int64 __fastcall IkeEnumFwpmLayer(
        FWPM_FILTER_CONDITION0 *a1,
        UINT32 a2,
        GUID *a3,
        GUID *a4,
        GUID *a5,
        int a6,
        UINT32 a7,
        int a8,
        UINT32 numEntriesRequested,
        FWPM_FILTER0 ***a10,
        UINT32 *a11)
{
  FWPM_PROVIDER_CONTEXT_ENUM_TEMPLATE0 *v11; // rcx
  __m128i v12; // xmm0
  int v13; // eax
  GUID v14; // xmm0
  __int64 v15; // rbx
  int v16; // r8d
  DWORD v17; // eax
  __int64 v18; // rcx
  int TlsPeerAddr; // eax
  int v21; // edx
  int v22; // r8d
  int v23; // [rsp+30h] [rbp-B9h] BYREF
  HANDLE enumHandle; // [rsp+38h] [rbp-B1h] BYREF
  FWPM_FILTER0 **entries; // [rsp+40h] [rbp-A9h] BYREF
  FWPM_FILTER_ENUM_TEMPLATE0 enumTemplate; // [rsp+50h] [rbp-99h] BYREF
  UINT32 numEntriesReturned; // [rsp+A0h] [rbp-49h] BYREF
  __int128 v28; // [rsp+A8h] [rbp-41h] BYREF
  _BYTE v29[16]; // [rsp+B8h] [rbp-31h] BYREF
  const char *v30; // [rsp+C8h] [rbp-21h]
  __int64 v31; // [rsp+D0h] [rbp-19h]
  int *v32; // [rsp+D8h] [rbp-11h]
  __int64 v33; // [rsp+E0h] [rbp-9h]

  v28 = 0;
  enumTemplate.filterCondition = a1;
  v11 = (FWPM_PROVIDER_CONTEXT_ENUM_TEMPLATE0 *)&v28;
  v12 = _mm_srli_si128((__m128i)0LL, 8);
  if ( a6 == 14 )
    v11 = 0;
  v13 = _mm_cvtsi128_si32(v12);
  *a10 = 0;
  v14 = *a3;
  if ( a6 != 14 )
    v13 = a6;
  DWORD2(v28) = v13;
  enumTemplate.flags = a7;
  enumHandle = 0;
  entries = 0;
  numEntriesReturned = 0;
  *(&enumTemplate.numFilterConditions + 1) = 0;
  *(_QWORD *)(&enumTemplate.actionMask + 1) = 0;
  HIDWORD(enumTemplate.calloutKey) = 0;
  enumTemplate.providerKey = a5;
  enumTemplate.enumType = FWP_FILTER_ENUM_FULLY_CONTAINED;
  enumTemplate.actionMask = 4096;
  enumTemplate.numFilterConditions = a2;
  enumTemplate.providerContextTemplate = v11;
  enumTemplate.layerKey = v14;
  if ( a4 )
  {
    enumTemplate.calloutKey = a4;
    enumTemplate.actionMask = 20480;
  }
  LODWORD(v15) = FwpmFilterCreateEnumHandle0(gIkeExtGlobals[68].OwningThread, &enumTemplate, &enumHandle);
  if ( (_DWORD)v15 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      TlsPeerAddr = IkeGetTlsPeerAddr(&WPP_GLOBAL_Control);
      WPP_SF_SsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v21,
        v22,
        TlsPeerAddr,
        (__int64)"FwpmFilterCreateEnumHandle0",
        v15);
    }
    if ( gWfpLogUserModeErrors && (byte_180178161 & 1) != 0 )
    {
      v23 = v15;
      v32 = &v23;
      v30 = "FwpmFilterCreateEnumHandle0";
      v31 = 28;
      v33 = 4;
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
        (unsigned int)WFP_USERMODE_ERROR,
        v16,
        3,
        (__int64)v29);
    }
    if ( (int)v15 > 0 )
      LODWORD(v15) = (unsigned __int16)v15 | 0x80070000;
    v15 = (int)v15;
  }
  else
  {
    v17 = FwpmFilterEnum0(
            gIkeExtGlobals[68].OwningThread,
            enumHandle,
            numEntriesRequested,
            &entries,
            &numEntriesReturned);
    if ( v17 )
    {
      v15 = WfpReportSysErrorAsWinError(v18, "FwpmFilterEnum0", v17, 1);
    }
    else
    {
      v15 = 0;
      *a10 = entries;
      *a11 = numEntriesReturned;
    }
  }
  if ( enumHandle )
    FwpmFilterDestroyEnumHandle0(gIkeExtGlobals[68].OwningThread, enumHandle);
  if ( a8 )
    return v15;
  else
    return IkeReturnError(v15, "IkeEnumFwpmLayer");
}

```

## disassembly

```asm
0x180008590  push    rbp
0x180008592  push    rbx
0x180008593  push    rsi
0x180008594  push    rdi
0x180008595  push    r14
0x180008597  lea     rbp, [rsp-7]
0x18000859c  sub     rsp, 0F0h
0x1800085a3  mov     rax, cs:__security_cookie
0x1800085aa  xor     rax, rsp
0x1800085ad  mov     [rbp+27h+var_28], rax
0x1800085b1  mov     rdi, [rbp+27h+arg_48]
0x1800085b5  xor     r14d, r14d
0x1800085b8  cmp     [rbp+27h+arg_28], 0Eh
0x1800085bc  xorps   xmm0, xmm0
0x1800085bf  mov     r10, [rbp+27h+arg_20]
0x1800085c3  mov     rsi, [rbp+27h+arg_50]
0x1800085ca  movups  [rbp+27h+var_68], xmm0
0x1800085ce  mov     [rbp+27h+enumTemplate.filterCondition], rcx
0x1800085d2  lea     rcx, [rbp+27h+var_68]
0x1800085d6  psrldq  xmm0, 8
0x1800085db  cmovz   rcx, r14
0x1800085df  movd    eax, xmm0
0x1800085e3  mov     [rdi], r14
0x1800085e6  movups  xmm0, xmmword ptr [r8]
0x1800085ea  cmovnz  eax, [rbp+27h+arg_28]
0x1800085ee  mov     dword ptr [rbp+27h+var_68+8], eax
0x1800085f1  mov     eax, [rbp+27h+arg_30]
0x1800085f4  mov     [rbp+27h+enumTemplate.flags], eax
0x1800085f7  mov     [rsp+110h+enumHandle], r14
0x1800085fc  mov     [rsp+110h+entries], r14
0x180008601  mov     [rbp+27h+var_70], r14d
0x180008605  mov     dword ptr [rbp+27h+enumTemplate+2Ch], r14d
0x180008609  mov     qword ptr [rbp+27h+enumTemplate+3Ch], r14
0x18000860d  mov     dword ptr [rbp+27h+enumTemplate.calloutKey+4], r14d
0x180008611  mov     [rsp+110h+enumTemplate.providerKey], r10
0x180008616  mov     [rsp+110h+enumTemplate.enumType], r14d
0x18000861b  mov     [rbp+27h+enumTemplate.actionMask], 1000h
0x180008622  mov     [rbp+27h+enumTemplate.numFilterConditions], edx
0x180008625  mov     [rbp+27h+enumTemplate.providerContextTemplate], rcx
0x180008629  movups  xmmword ptr [rsp+110h+enumTemplate.layerKey.Data1], xmm0
0x18000862e  test    r9, r9
0x180008631  jnz     loc_18000877C
0x180008637  mov     rcx, cs:gIkeExtGlobals
0x18000863e  lea     r8, [rsp+110h+enumHandle]; enumHandle
0x180008643  lea     rdx, [rsp+110h+enumTemplate]; enumTemplate
0x180008648  mov     rcx, [rcx+0AB0h]; engineHandle
0x18000864f  call    cs:__imp_FwpmFilterCreateEnumHandle0
0x180008655  mov     ebx, eax
0x180008657  test    eax, eax
0x180008659  jnz     loc_1800086F3
0x18000865f  mov     rcx, cs:gIkeExtGlobals
0x180008666  lea     rax, [rbp+27h+var_70]
0x18000866a  mov     r8d, [rbp+27h+numEntriesRequested]; numEntriesRequested
0x18000866e  lea     r9, [rsp+110h+entries]; entries
0x180008673  mov     rdx, [rsp+110h+enumHandle]; enumHandle
0x180008678  mov     [rsp+110h+numEntriesReturned], rax; numEntriesReturned
0x18000867d  mov     rcx, [rcx+0AB0h]; engineHandle
0x180008684  call    cs:__imp_FwpmFilterEnum0
0x18000868a  test    eax, eax
0x18000868c  jnz     loc_1800087C3
0x180008692  mov     rax, [rsp+110h+entries]
0x180008697  mov     rbx, r14
0x18000869a  mov     [rdi], rax
0x18000869d  mov     eax, [rbp+27h+var_70]
0x1800086a0  mov     [rsi], eax
0x1800086a2  mov     rdx, [rsp+110h+enumHandle]; enumHandle
0x1800086a7  test    rdx, rdx
0x1800086aa  jz      short loc_1800086C0
0x1800086ac  mov     rcx, cs:gIkeExtGlobals
0x1800086b3  mov     rcx, [rcx+0AB0h]; engineHandle
0x1800086ba  call    cs:__imp_FwpmFilterDestroyEnumHandle0
0x1800086c0  cmp     [rbp+27h+arg_38], r14d
0x1800086c4  jnz     loc_180008774
0x1800086ca  lea     rdx, aIkeenumfwpmlay; "IkeEnumFwpmLayer"
0x1800086d1  mov     rcx, rbx
0x1800086d4  call    IkeReturnError
0x1800086d9  mov     rcx, [rbp+27h+var_28]
0x1800086dd  xor     rcx, rsp; StackCookie
0x1800086e0  call    __security_check_cookie
0x1800086e5  add     rsp, 0F0h
0x1800086ec  pop     r14
0x1800086ee  pop     rdi
0x1800086ef  pop     rsi
0x1800086f0  pop     rbx
0x1800086f1  pop     rbp
0x1800086f2  retn
0x1800086f3  mov     rax, cs:WPP_GLOBAL_Control
0x1800086fa  lea     rcx, WPP_GLOBAL_Control
0x180008701  lea     rdi, aFwpmfiltercrea; "FwpmFilterCreateEnumHandle0"
0x180008708  cmp     rax, rcx
0x18000870b  jz      short loc_180008713
0x18000870d  cmp     byte ptr [rax+19h], 2
0x180008711  jnb     short loc_18000878C
0x180008713  cmp     cs:gWfpLogUserModeErrors, r14d
0x18000871a  jz      short loc_180008768
0x18000871c  test    cs:byte_180178161, 1
0x180008723  jz      short loc_180008768
0x180008725  lea     rax, [rsp+110h+var_E0]
0x18000872a  mov     [rsp+110h+var_E0], ebx
0x18000872e  mov     [rbp+27h+var_38], rax
0x180008732  lea     rdx, WFP_USERMODE_ERROR
0x180008739  lea     rax, [rbp+27h+var_58]
0x18000873d  mov     [rbp+27h+var_48], rdi
0x180008741  mov     r9d, 3
0x180008747  mov     [rsp+110h+numEntriesReturned], rax
0x18000874c  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x180008753  mov     [rbp+27h+var_40], 1Ch
0x18000875b  mov     [rbp+27h+var_30], 4
0x180008763  call    McGenEventWrite_EtwEventWriteTransfer
0x180008768  test    ebx, ebx
0x18000876a  jg      short loc_1800087B8
0x18000876c  movsxd  rbx, ebx
0x18000876f  jmp     loc_1800086A2
0x180008774  mov     rax, rbx
0x180008777  jmp     loc_1800086D9
0x18000877c  mov     [rbp+27h+enumTemplate.calloutKey], r9
0x180008780  mov     [rbp+27h+enumTemplate.actionMask], 5000h
0x180008787  jmp     loc_180008637
0x18000878c  test    byte ptr [rax+1Ch], 1
0x180008790  jz      short loc_180008713
0x180008792  call    IkeGetTlsPeerAddr
0x180008797  mov     rcx, cs:WPP_GLOBAL_Control
0x18000879e  mov     r9, rax
0x1800087a1  mov     [rsp+110h+var_E8], ebx
0x1800087a5  mov     [rsp+110h+numEntriesReturned], rdi
0x1800087aa  mov     rcx, [rcx+10h]
0x1800087ae  call    WPP_SF_SsD
0x1800087b3  jmp     loc_180008713
0x1800087b8  movzx   ebx, bx
0x1800087bb  or      ebx, 80070000h
0x1800087c1  jmp     short loc_18000876C
0x1800087c3  mov     r9d, 1
0x1800087c9  lea     rdx, aFwpmfilterenum_0; "FwpmFilterEnum0"
0x1800087d0  mov     r8d, eax
0x1800087d3  call    WfpReportSysErrorAsWinError
0x1800087d8  mov     rbx, rax
0x1800087db  jmp     loc_1800086A2
```
