# CommonBuffer_Create

- ea: `0x140074008`
- end: `0x1400742ff`
- name: `CommonBuffer_Create`
- size: `759`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14007a8f0`

## callees

- `0x14001ad0c`
- `0x140031928`
- `0x140035738`
- `0x1400574dc`
- `0x1400599b0`
- `0x140074008`
- `0x14007feb8`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x140074183`
- `ntoskrnl!KeInitializeSpinLock` at `0x140074183`
- `ntoskrnl!KeInitializeEvent` at `0x1400741b2`
- `ntoskrnl!KeInitializeEvent` at `0x1400741b2`

## pseudocode

```c
__int64 __fastcall CommonBuffer_Create(__int64 a1, char a2, __int64 *a3)
{
  int v6; // eax
  int v7; // edx
  unsigned int v8; // edi
  int v9; // edx
  __int64 v10; // rbx
  int v11; // eax
  int v12; // edx
  __int128 v14; // [rsp+30h] [rbp-50h] BYREF
  __int64 v15; // [rsp+40h] [rbp-40h]
  __int128 v16; // [rsp+48h] [rbp-38h] BYREF
  __int128 v17; // [rsp+58h] [rbp-28h]
  __int128 v18; // [rsp+68h] [rbp-18h]
  __int64 *v19; // [rsp+78h] [rbp-8h]
  __int64 v20; // [rsp+B0h] [rbp+30h] BYREF

  v20 = 0;
  LODWORD(v15) = 0;
  v19 = 0;
  v14 = 0;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  if ( WdfClientVersionHigherThanFramework )
  {
    if ( (unsigned int)WdfStructureCount <= 0x26 )
      LODWORD(v16) = -1;
    else
      LODWORD(v16) = *(_DWORD *)(WdfStructures + 304);
  }
  else
  {
    LODWORD(v16) = 56;
  }
  *((_QWORD *)&v17 + 1) = 0x100000001LL;
  v19 = off_14006C180;
  *(_QWORD *)&v18 = *(_QWORD *)(a1 + 8);
  *((_QWORD *)&v16 + 1) = CommonBuffer_WdfEvtCleanupCallback;
  v6 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int128 *, __int64 *))(WdfFunctions_01033 + 1656))(
         WdfDriverGlobals,
         &v16,
         &v20);
  v8 = v6;
  if ( v6 >= 0 )
  {
    v10 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01033 + 1616))(
            WdfDriverGlobals,
            v20,
            off_14006C180);
    *(_QWORD *)v10 = a1;
    *(_BYTE *)(v10 + 80) = a2;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = 4;
      WPP_RECORDER_SF_q(*(_QWORD *)(a1 + 72), v9, 8, 11, (__int64)WPP_6a5376b16cbf3dbdeb6b8133660a6549_Traceguids, v20);
    }
    KeInitializeSpinLock((PKSPIN_LOCK)(v10 + 48));
    *(_QWORD *)(v10 + 64) = v10 + 56;
    *(_QWORD *)(v10 + 56) = v10 + 56;
    XilCoreCommonBuffer_Create(a1, v10, v10 + 88);
    KeInitializeEvent((PRKEVENT)(v10 + 24), NotificationEvent, 1u);
    if ( !(unsigned __int8)Controller_IsSecureDevice(a1) )
    {
      v19 = 0;
      v16 = 0;
      v17 = 0;
      v18 = 0;
      if ( WdfClientVersionHigherThanFramework )
        LODWORD(v16) = (unsigned int)WdfStructureCount <= 0x26 ? -1 : *(_DWORD *)(WdfStructures + 304);
      else
        LODWORD(v16) = 56;
      *(_QWORD *)&v18 = v20;
      *((_QWORD *)&v17 + 1) = 0x100000001LL;
      v15 = 0;
      v14 = 0;
      if ( WdfClientVersionHigherThanFramework )
        LODWORD(v14) = (unsigned int)WdfStructureCount <= 0x43 ? -1 : *(_DWORD *)(WdfStructures + 536);
      else
        LODWORD(v14) = 24;
      *((_QWORD *)&v14 + 1) = CommonBuffer_RebalanceResourcesWorkItem;
      LOBYTE(v15) = 1;
      v11 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int128 *, __int128 *, __int64))(WdfFunctions_01033 + 3032))(
              WdfDriverGlobals,
              &v14,
              &v16,
              v10 + 72);
      v8 = v11;
      if ( v11 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v12) = 2;
        WPP_RECORDER_SF_d(
          *(_QWORD *)(a1 + 72),
          v12,
          8,
          12,
          (__int64)WPP_6a5376b16cbf3dbdeb6b8133660a6549_Traceguids,
          v11);
      }
    }
    *(_QWORD *)(v10 + 8) = v10 + 288;
    Counter_CreateCommonBufferInstance((PPCW_INSTANCE *)v10);
    *a3 = v10;
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v7) = 2;
    WPP_RECORDER_SF_d(*(_QWORD *)(a1 + 72), v7, 8, 10, (__int64)WPP_6a5376b16cbf3dbdeb6b8133660a6549_Traceguids, v6);
  }
  return v8;
}

```

## disassembly

```asm
0x140074008  mov     [rsp-28h+arg_8], rbx
0x14007400d  mov     [rsp-28h+arg_10], rsi
0x140074012  push    rbp
0x140074013  push    rdi
0x140074014  push    r12
0x140074016  push    r14
0x140074018  push    r15
0x14007401a  mov     rbp, rsp
0x14007401d  sub     rsp, 80h
0x140074024  xor     eax, eax
0x140074026  mov     [rbp+arg_0], 0
0x14007402e  cmp     cs:WdfClientVersionHigherThanFramework, al
0x140074034  xorps   xmm1, xmm1
0x140074037  xorps   xmm0, xmm0
0x14007403a  mov     dword ptr [rbp+var_40], eax
0x14007403d  mov     r12, r8
0x140074040  mov     [rbp+var_8], rax
0x140074044  mov     sil, dl
0x140074047  mov     r14, rcx
0x14007404a  movups  [rbp+var_50], xmm0
0x14007404e  movups  [rbp+var_38], xmm1
0x140074052  movups  [rbp+var_28], xmm1
0x140074056  movups  [rbp+var_18], xmm1
0x14007405a  jz      short loc_140074080
0x14007405c  cmp     cs:WdfStructureCount, 26h ; '&'
0x140074063  jbe     short loc_140074077
0x140074065  mov     rax, cs:WdfStructures
0x14007406c  mov     ecx, [rax+130h]
0x140074072  mov     dword ptr [rbp+var_38], ecx
0x140074075  jmp     short loc_140074087
0x140074077  mov     dword ptr [rbp+var_38], 0FFFFFFFFh
0x14007407e  jmp     short loc_140074087
0x140074080  mov     dword ptr [rbp+var_38], 38h ; '8'
0x140074087  mov     rcx, cs:WdfDriverGlobals
0x14007408e  lea     r8, [rbp+arg_0]
0x140074092  mov     eax, 1
0x140074097  lea     rdx, [rbp+var_38]
0x14007409b  mov     dword ptr [rbp+var_28+8], eax
0x14007409e  mov     dword ptr [rbp+var_28+0Ch], eax
0x1400740a1  mov     rax, cs:off_14006C180
0x1400740a8  mov     [rbp+var_8], rax
0x1400740ac  mov     rax, [r14+8]
0x1400740b0  mov     qword ptr [rbp+var_18], rax
0x1400740b4  lea     rax, CommonBuffer_WdfEvtCleanupCallback
0x1400740bb  mov     qword ptr [rbp+var_38+8], rax
0x1400740bf  mov     rax, cs:WdfFunctions_01033
0x1400740c6  mov     rax, [rax+678h]
0x1400740cd  call    _guard_dispatch_icall
0x1400740d2  mov     edi, eax
0x1400740d4  test    eax, eax
0x1400740d6  jns     short loc_140074116
0x1400740d8  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400740df  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400740e6  jz      loc_1400742E0
0x1400740ec  mov     rcx, [r14+48h]
0x1400740f0  lea     r15, WPP_6a5376b16cbf3dbdeb6b8133660a6549_Traceguids
0x1400740f7  mov     r9d, 0Ah
0x1400740fd  mov     dword ptr [rsp+80h+var_58], eax
0x140074101  mov     dl, 2
0x140074103  mov     [rsp+80h+var_60], r15
0x140074108  lea     r8d, [r9-2]
0x14007410c  call    WPP_RECORDER_SF_d
0x140074111  jmp     loc_1400742E0
0x140074116  mov     rax, cs:WdfFunctions_01033
0x14007411d  mov     r8, cs:off_14006C180
0x140074124  mov     rdx, [rbp+arg_0]
0x140074128  mov     rcx, cs:WdfDriverGlobals
0x14007412f  mov     rax, [rax+650h]
0x140074136  call    _guard_dispatch_icall
0x14007413b  mov     rbx, rax
0x14007413e  mov     [rax], r14
0x140074141  mov     [rax+50h], sil
0x140074145  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14007414c  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140074153  lea     r15, WPP_6a5376b16cbf3dbdeb6b8133660a6549_Traceguids
0x14007415a  jz      short loc_14007417F
0x14007415c  mov     rcx, [rbp+arg_0]
0x140074160  mov     r9d, 0Bh
0x140074166  mov     [rsp+80h+var_58], rcx
0x14007416b  mov     dl, 4
0x14007416d  mov     rcx, [r14+48h]
0x140074171  mov     [rsp+80h+var_60], r15
0x140074176  lea     r8d, [r9-3]
0x14007417a  call    WPP_RECORDER_SF_q
0x14007417f  lea     rcx, [rbx+30h]; SpinLock
0x140074183  call    cs:__imp_KeInitializeSpinLock
0x14007418a  nop     dword ptr [rax+rax+00h]
0x14007418f  lea     rax, [rbx+38h]
0x140074193  mov     rdx, rbx
0x140074196  lea     r8, [rbx+58h]
0x14007419a  mov     [rax+8], rax
0x14007419e  mov     rcx, r14
0x1400741a1  mov     [rax], rax
0x1400741a4  call    XilCoreCommonBuffer_Create
0x1400741a9  lea     rcx, [rbx+18h]; Event
0x1400741ad  mov     r8b, 1; State
0x1400741b0  xor     edx, edx; Type
0x1400741b2  call    cs:__imp_KeInitializeEvent
0x1400741b9  nop     dword ptr [rax+rax+00h]
0x1400741be  mov     rcx, r14
0x1400741c1  call    Controller_IsSecureDevice
0x1400741c6  test    al, al
0x1400741c8  jnz     loc_1400742C9
0x1400741ce  mov     dl, cs:WdfClientVersionHigherThanFramework
0x1400741d4  xorps   xmm0, xmm0
0x1400741d7  xor     eax, eax
0x1400741d9  mov     [rbp+var_8], rax
0x1400741dd  movups  [rbp+var_38], xmm0
0x1400741e1  movups  [rbp+var_28], xmm0
0x1400741e5  movups  [rbp+var_18], xmm0
0x1400741e9  test    dl, dl
0x1400741eb  jz      short loc_140074211
0x1400741ed  cmp     cs:WdfStructureCount, 26h ; '&'
0x1400741f4  jbe     short loc_140074208
0x1400741f6  mov     rax, cs:WdfStructures
0x1400741fd  mov     ecx, [rax+130h]
0x140074203  mov     dword ptr [rbp+var_38], ecx
0x140074206  jmp     short loc_140074218
0x140074208  mov     dword ptr [rbp+var_38], 0FFFFFFFFh
0x14007420f  jmp     short loc_140074218
0x140074211  mov     dword ptr [rbp+var_38], 38h ; '8'
0x140074218  mov     rax, [rbp+arg_0]
0x14007421c  mov     r8d, 1
0x140074222  mov     qword ptr [rbp+var_18], rax
0x140074226  xor     eax, eax
0x140074228  mov     dword ptr [rbp+var_28+8], r8d
0x14007422c  mov     dword ptr [rbp+var_28+0Ch], r8d
0x140074230  mov     [rbp+var_40], rax
0x140074234  movups  [rbp+var_50], xmm0
0x140074238  test    dl, dl
0x14007423a  jz      short loc_140074260
0x14007423c  cmp     cs:WdfStructureCount, 43h ; 'C'
0x140074243  jbe     short loc_140074257
0x140074245  mov     rax, cs:WdfStructures
0x14007424c  mov     ecx, [rax+218h]
0x140074252  mov     dword ptr [rbp+var_50], ecx
0x140074255  jmp     short loc_140074267
0x140074257  mov     dword ptr [rbp+var_50], 0FFFFFFFFh
0x14007425e  jmp     short loc_140074267
0x140074260  mov     dword ptr [rbp+var_50], 18h
0x140074267  mov     rcx, cs:WdfDriverGlobals
0x14007426e  lea     rax, CommonBuffer_RebalanceResourcesWorkItem
0x140074275  mov     qword ptr [rbp+var_50+8], rax
0x140074279  lea     r9, [rbx+48h]
0x14007427d  mov     rax, cs:WdfFunctions_01033
0x140074284  lea     rdx, [rbp+var_50]
0x140074288  mov     byte ptr [rbp+var_40], r8b
0x14007428c  lea     r8, [rbp+var_38]
0x140074290  mov     rax, [rax+0BD8h]
0x140074297  call    _guard_dispatch_icall
0x14007429c  mov     edi, eax
0x14007429e  test    eax, eax
0x1400742a0  jns     short loc_1400742C9
0x1400742a2  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x1400742a9  jz      short loc_1400742C9
0x1400742ab  mov     rcx, [r14+48h]
0x1400742af  mov     r9d, 0Ch
0x1400742b5  mov     dword ptr [rsp+80h+var_58], eax
0x1400742b9  mov     dl, 2
0x1400742bb  mov     [rsp+80h+var_60], r15
0x1400742c0  lea     r8d, [r9-4]
0x1400742c4  call    WPP_RECORDER_SF_d
0x1400742c9  lea     rax, [rbx+120h]
0x1400742d0  mov     rcx, rbx
0x1400742d3  mov     [rbx+8], rax
0x1400742d7  call    Counter_CreateCommonBufferInstance
0x1400742dc  mov     [r12], rbx
0x1400742e0  lea     r11, [rsp+80h+var_s0]
0x1400742e8  mov     eax, edi
0x1400742ea  mov     rbx, [r11+38h]
0x1400742ee  mov     rsi, [r11+40h]
0x1400742f2  mov     rsp, r11
0x1400742f5  pop     r15
0x1400742f7  pop     r14
0x1400742f9  pop     r12
0x1400742fb  pop     rdi
0x1400742fc  pop     rbp
0x1400742fd  retn
```
