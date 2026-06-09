# EvtIntGetClassicLogDisplayName

- ea: `0x1800269d0`
- end: `0x180026e26`
- name: `EvtIntGetClassicLogDisplayName`
- size: `1110`
- prototype: `__int64 __fastcall(int, int, int, int, int, void *, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180007940`
- `0x180007aa0`
- `0x18000a0dc`
- `0x180023548`
- `0x1800269d0`
- `0x180038fb4`
- `0x180038fcc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026e07`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026e07`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x180026b3f`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x180026b3f`
- `api-ms-win-core-localization-l1-2-0!GetThreadUILanguage` at `0x180026b26`
- `api-ms-win-core-localization-l1-2-0!GetThreadUILanguage` at `0x180026b26`
- `RPCRT4!NdrClientCall3` at `0x180026b8c`
- `RPCRT4!NdrClientCall3` at `0x180026b8c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall EvtIntGetClassicLogDisplayName(
        __int64 a1,
        __int64 a2,
        LCID a3,
        int a4,
        unsigned int a5,
        void *a6,
        _DWORD *a7)
{
  LCID ThreadUILanguage; // ebx
  unsigned int v9; // edi
  unsigned int Pointer; // ebx
  void *v11; // rdx
  __int64 v12; // rax
  __int64 v13; // r8
  DWORD v14; // ebx
  void *Src; // [rsp+40h] [rbp-148h] BYREF
  __int64 v17; // [rsp+48h] [rbp-140h] BYREF
  _QWORD v18[3]; // [rsp+50h] [rbp-138h] BYREF
  unsigned int v19; // [rsp+68h] [rbp-120h]
  int v20; // [rsp+6Ch] [rbp-11Ch]
  int v21; // [rsp+70h] [rbp-118h]
  char v22; // [rsp+74h] [rbp-114h]
  __int128 pExceptionObject; // [rsp+78h] [rbp-110h] BYREF
  __int64 v24; // [rsp+88h] [rbp-100h]
  int v25; // [rsp+90h] [rbp-F8h]
  int v26; // [rsp+94h] [rbp-F4h]
  int v27; // [rsp+98h] [rbp-F0h]
  __int128 v28; // [rsp+A0h] [rbp-E8h] BYREF
  __int64 v29; // [rsp+B0h] [rbp-D8h]
  int v30; // [rsp+B8h] [rbp-D0h]
  int v31; // [rsp+BCh] [rbp-CCh]
  int v32; // [rsp+C0h] [rbp-C8h]
  __int128 v33; // [rsp+C8h] [rbp-C0h] BYREF
  __int64 v34; // [rsp+D8h] [rbp-B0h]
  int v35; // [rsp+E0h] [rbp-A8h]
  int v36; // [rsp+E4h] [rbp-A4h]
  int v37; // [rsp+E8h] [rbp-A0h]
  __int128 v38; // [rsp+F0h] [rbp-98h] BYREF
  __int64 v39; // [rsp+100h] [rbp-88h]
  int v40; // [rsp+108h] [rbp-80h]
  int v41; // [rsp+10Ch] [rbp-7Ch]
  int v42; // [rsp+110h] [rbp-78h]
  __int128 v43; // [rsp+118h] [rbp-70h] BYREF
  __int64 v44; // [rsp+128h] [rbp-60h]
  int v45; // [rsp+130h] [rbp-58h]
  int v46; // [rsp+134h] [rbp-54h]
  int v47; // [rsp+138h] [rbp-50h]
  EvtException *v48; // [rsp+140h] [rbp-48h] BYREF

  try
  {
    ThreadUILanguage = a3;
    v9 = 0;
    if ( a4 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_50a4b5d3db573bd708b949f391e8ee2a_Traceguids, 87);
      }
      pExceptionObject = 0;
      v24 = 0;
      v25 = 87;
      v26 = -1;
      v27 = 458;
      throw (EvtException *)&pExceptionObject;
    }
    if ( !a2 || !a7 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_50a4b5d3db573bd708b949f391e8ee2a_Traceguids, 87);
      }
      v43 = 0;
      v44 = 0;
      v45 = 87;
      v46 = -1;
      v47 = 463;
      throw (EvtException *)&v43;
    }
    if ( !a6 && a5 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_50a4b5d3db573bd708b949f391e8ee2a_Traceguids, 87);
      }
      v28 = 0;
      v29 = 0;
      v30 = 87;
      v31 = -1;
      v32 = 468;
      throw (EvtException *)&v28;
    }
    if ( !a3 )
    {
      ThreadUILanguage = GetThreadUILanguage();
      if ( ThreadUILanguage == 5120 || ThreadUILanguage == 4096 )
        ThreadUILanguage = GetThreadLocale();
    }
    GetSession(&v17);
    Src = 0;
    Pointer = (unsigned int)NdrClientCall3(
                              (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                              0x1Cu,
                              0,
                              *(_QWORD *)(v17 + 72),
                              a2,
                              ThreadUILanguage,
                              256,
                              &Src).Pointer;
    if ( Pointer )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_50a4b5d3db573bd708b949f391e8ee2a_Traceguids, Pointer);
      }
      v18[0] = &word_18004024A;
      v18[1] = 0;
      v18[2] = 0;
      v19 = Pointer;
      v20 = -1;
      v21 = -1;
      v22 = 0;
      throw (EvtException *)v18;
    }
    v11 = Src;
    if ( !Src )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_50a4b5d3db573bd708b949f391e8ee2a_Traceguids, 13);
      }
      v33 = 0;
      v34 = 0;
      v35 = 13;
      v36 = -1;
      v37 = 504;
      throw (EvtException *)&v33;
    }
    v12 = -1;
    do
      ++v12;
    while ( *((_WORD *)Src + v12) );
    v13 = v12 + 1;
    if ( (unsigned __int64)(v12 + 1) > 0x200000 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_50a4b5d3db573bd708b949f391e8ee2a_Traceguids, 13);
      }
      v38 = 0;
      v39 = 0;
      v40 = 13;
      v41 = -1;
      v42 = 510;
      throw (EvtException *)&v38;
    }
    *a7 = v13;
    if ( (unsigned int)v13 > a5 )
    {
      v14 = 122;
    }
    else
    {
      memcpy_0(a6, v11, 2 * v13);
      v14 = 0;
    }
    utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<unsigned long>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<unsigned long>>>(&Src);
    wmi::AutoRef<Object>::Release(&v17);
  }
  catch ( EvtException *v48 )
  {
    v9 = 0;
    v14 = *((_DWORD *)v48 + 6);
  }
  SetLastError(v14);
  LOBYTE(v9) = v14 == 0;
  return v9;
}

```

## disassembly

```asm
0x1800269d0  push    rbx
0x1800269d2  push    rsi
0x1800269d3  push    rdi
0x1800269d4  push    r12
0x1800269d6  push    r14
0x1800269d8  push    r15
0x1800269da  sub     rsp, 158h
0x1800269e1  mov     ebx, r8d
0x1800269e4  mov     r15, rdx
0x1800269e7  mov     r12, rcx
0x1800269ea  xor     edi, edi
0x1800269ec  test    r9d, r9d
0x1800269ef  jz      short loc_180026A6A
0x1800269f1  lea     rax, WPP_GLOBAL_Control
0x1800269f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800269ff  cmp     rcx, rax
0x180026a02  jz      short loc_180026A27
0x180026a04  test    byte ptr [rcx+1Ch], 1
0x180026a08  jz      short loc_180026A27
0x180026a0a  cmp     byte ptr [rcx+19h], 2
0x180026a0e  jb      short loc_180026A27
0x180026a10  lea     edx, [rdi+13h]
0x180026a13  lea     r9d, [rdi+57h]
0x180026a17  lea     r8, WPP_50a4b5d3db573bd708b949f391e8ee2a_Traceguids
0x180026a1e  mov     rcx, [rcx+10h]
0x180026a22  call    WPP_SF_D
0x180026a27  xorps   xmm0, xmm0
0x180026a2a  movdqu  [rsp+188h+pExceptionObject], xmm0
0x180026a30  mov     [rsp+188h+var_100], rdi
0x180026a38  mov     [rsp+188h+var_F8], 57h ; 'W'
0x180026a43  mov     [rsp+188h+var_F4], 0FFFFFFFFh
0x180026a4e  mov     [rsp+188h+var_F0], 1CAh
0x180026a59  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180026a60  lea     rcx, [rsp+188h+pExceptionObject]; pExceptionObject
0x180026a65  call    _CxxThrowException_0
0x180026a6a  test    r15, r15
0x180026a6d  jz      loc_180026D7A
0x180026a73  mov     r14, [rsp+188h+arg_30]
0x180026a7b  test    r14, r14
0x180026a7e  jz      loc_180026D7A
0x180026a84  mov     esi, [rsp+188h+arg_20]
0x180026a8b  cmp     [rsp+188h+arg_28], rdi
0x180026a93  jnz     loc_180026B22
0x180026a99  test    esi, esi
0x180026a9b  jz      loc_180026B22
0x180026aa1  lea     rax, WPP_GLOBAL_Control
0x180026aa8  mov     rcx, cs:WPP_GLOBAL_Control
0x180026aaf  cmp     rcx, rax
0x180026ab2  jz      short loc_180026AD9
0x180026ab4  test    byte ptr [rcx+1Ch], 1
0x180026ab8  jz      short loc_180026AD9
0x180026aba  cmp     byte ptr [rcx+19h], 2
0x180026abe  jb      short loc_180026AD9
0x180026ac0  mov     edx, 15h
0x180026ac5  lea     r9d, [rdx+42h]
0x180026ac9  lea     r8, WPP_50a4b5d3db573bd708b949f391e8ee2a_Traceguids
0x180026ad0  mov     rcx, [rcx+10h]
0x180026ad4  call    WPP_SF_D
0x180026ad9  xorps   xmm0, xmm0
0x180026adc  movdqu  [rsp+188h+var_E8], xmm0
0x180026ae5  mov     [rsp+188h+var_D8], rdi
0x180026aed  mov     [rsp+188h+var_D0], 57h ; 'W'
0x180026af8  mov     [rsp+188h+var_CC], 0FFFFFFFFh
0x180026b03  mov     [rsp+188h+var_C8], 1D4h
0x180026b0e  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180026b15  lea     rcx, [rsp+188h+var_E8]; pExceptionObject
0x180026b1d  call    _CxxThrowException_0
0x180026b22  test    ebx, ebx
0x180026b24  jnz     short loc_180026B47
0x180026b26  call    cs:__imp_GetThreadUILanguage
0x180026b2c  movzx   ebx, ax
0x180026b2f  cmp     ebx, 1400h
0x180026b35  jz      short loc_180026B3F
0x180026b37  cmp     ebx, 1000h
0x180026b3d  jnz     short loc_180026B47
0x180026b3f  call    cs:__imp_GetThreadLocale
0x180026b45  mov     ebx, eax
0x180026b47  mov     rdx, r12
0x180026b4a  lea     rcx, [rsp+188h+var_140]; void *
0x180026b4f  call    ?GetSession@@YA?AV?$AutoRef@VSession@@@wmi@@PEAX@Z; GetSession(void *)
0x180026b54  nop
0x180026b55  mov     [rsp+188h+Src], rdi
0x180026b5a  lea     rax, [rsp+188h+Src]
0x180026b5f  mov     [rsp+188h+var_150], rax
0x180026b64  mov     [rsp+188h+var_158], 100h
0x180026b6c  mov     [rsp+188h+var_160], ebx
0x180026b70  mov     [rsp+188h+var_168], r15
0x180026b75  mov     r9, [rsp+188h+var_140]
0x180026b7a  mov     r9, [r9+48h]
0x180026b7e  xor     r8d, r8d; pReturnValue
0x180026b81  lea     edx, [r8+1Ch]; nProcNum
0x180026b85  lea     rcx, pProxyInfo; pProxyInfo
0x180026b8c  call    cs:__imp_NdrClientCall3
0x180026b92  mov     rbx, rax
0x180026b95  test    ebx, ebx
0x180026b97  jz      short loc_180026C10
0x180026b99  lea     rax, WPP_GLOBAL_Control
0x180026ba0  mov     rcx, cs:WPP_GLOBAL_Control
0x180026ba7  cmp     rcx, rax
0x180026baa  jz      short loc_180026BD0
0x180026bac  test    byte ptr [rcx+1Ch], 1
0x180026bb0  jz      short loc_180026BD0
0x180026bb2  cmp     byte ptr [rcx+19h], 2
0x180026bb6  jb      short loc_180026BD0
0x180026bb8  mov     edx, 16h
0x180026bbd  mov     r9d, ebx
0x180026bc0  lea     r8, WPP_50a4b5d3db573bd708b949f391e8ee2a_Traceguids
0x180026bc7  mov     rcx, [rcx+10h]
0x180026bcb  call    WPP_SF_D
0x180026bd0  lea     rax, word_18004024A
0x180026bd7  mov     [rsp+188h+var_138], rax
0x180026bdc  mov     [rsp+188h+var_130], rdi
0x180026be1  mov     [rsp+188h+var_128], rdi
0x180026be6  mov     [rsp+188h+var_120], ebx
0x180026bea  mov     [rsp+188h+var_11C], 0FFFFFFFFh
0x180026bf2  or      rax, 0FFFFFFFFFFFFFFFFh
0x180026bf6  mov     [rsp+188h+var_118], eax
0x180026bfa  mov     [rsp+188h+var_114], dil
0x180026bff  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180026c06  lea     rcx, [rsp+188h+var_138]; pExceptionObject
0x180026c0b  call    _CxxThrowException_0
0x180026c10  mov     rdx, [rsp+188h+Src]; Src
0x180026c15  test    rdx, rdx
0x180026c18  jnz     loc_180026C9F
0x180026c1e  lea     rax, WPP_GLOBAL_Control
0x180026c25  mov     rcx, cs:WPP_GLOBAL_Control
0x180026c2c  cmp     rcx, rax
0x180026c2f  jz      short loc_180026C56
0x180026c31  test    byte ptr [rcx+1Ch], 1
0x180026c35  jz      short loc_180026C56
0x180026c37  cmp     byte ptr [rcx+19h], 2
0x180026c3b  jb      short loc_180026C56
0x180026c3d  mov     edx, 17h
0x180026c42  lea     r9d, [rdx-0Ah]
0x180026c46  lea     r8, WPP_50a4b5d3db573bd708b949f391e8ee2a_Traceguids
0x180026c4d  mov     rcx, [rcx+10h]
0x180026c51  call    WPP_SF_D
0x180026c56  xorps   xmm0, xmm0
0x180026c59  movdqu  [rsp+188h+var_C0], xmm0
0x180026c62  mov     [rsp+188h+var_B0], rdi
0x180026c6a  mov     [rsp+188h+var_A8], 0Dh
0x180026c75  mov     [rsp+188h+var_A4], 0FFFFFFFFh
0x180026c80  mov     [rsp+188h+var_A0], 1F8h
0x180026c8b  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180026c92  lea     rcx, [rsp+188h+var_C0]; pExceptionObject
0x180026c9a  call    _CxxThrowException_0
0x180026c9f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180026ca3  inc     rax
0x180026ca6  cmp     [rdx+rax*2], di
0x180026caa  jnz     short loc_180026CA3
0x180026cac  lea     r8, [rax+1]
0x180026cb0  cmp     r8, 200000h
0x180026cb7  jbe     loc_180026D3E
0x180026cbd  lea     rax, WPP_GLOBAL_Control
0x180026cc4  mov     rcx, cs:WPP_GLOBAL_Control
0x180026ccb  cmp     rcx, rax
0x180026cce  jz      short loc_180026CF5
0x180026cd0  test    byte ptr [rcx+1Ch], 1
0x180026cd4  jz      short loc_180026CF5
0x180026cd6  cmp     byte ptr [rcx+19h], 2
0x180026cda  jb      short loc_180026CF5
0x180026cdc  mov     edx, 18h
0x180026ce1  lea     r9d, [rdx-0Bh]
0x180026ce5  lea     r8, WPP_50a4b5d3db573bd708b949f391e8ee2a_Traceguids
0x180026cec  mov     rcx, [rcx+10h]
0x180026cf0  call    WPP_SF_D
0x180026cf5  xorps   xmm0, xmm0
0x180026cf8  movdqu  [rsp+188h+var_98], xmm0
0x180026d01  mov     [rsp+188h+var_88], rdi
0x180026d09  mov     [rsp+188h+var_80], 0Dh
0x180026d14  mov     [rsp+188h+var_7C], 0FFFFFFFFh
0x180026d1f  mov     [rsp+188h+var_78], 1FEh
0x180026d2a  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180026d31  lea     rcx, [rsp+188h+var_98]; pExceptionObject
0x180026d39  call    _CxxThrowException_0
0x180026d3e  mov     [r14], r8d
0x180026d41  cmp     r8d, esi
0x180026d44  ja      short loc_180026D5A
0x180026d46  add     r8, r8; Size
0x180026d49  mov     rcx, [rsp+188h+arg_28]; void *
0x180026d51  call    memcpy_0
0x180026d56  mov     ebx, edi
0x180026d58  jmp     short loc_180026D5F
0x180026d5a  mov     ebx, 7Ah ; 'z'
0x180026d5f  lea     rcx, [rsp+188h+Src]
0x180026d64  call    ??1?$_UninitializedAllocation@V?$allocator@U?$_TreeNode@K@utl@@@utl@@@utl@@QEAA@XZ; utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<ulong>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<ulong>>>(void)
0x180026d69  nop
0x180026d6a  lea     rcx, [rsp+188h+var_140]; void *
0x180026d6f  call    ?Release@?$AutoRef@VObject@@@wmi@@QEAAXXZ; wmi::AutoRef<Object>::Release(void)
0x180026d74  nop
0x180026d75  jmp     loc_180026E05
0x180026d7a  lea     rax, WPP_GLOBAL_Control
0x180026d81  mov     rcx, cs:WPP_GLOBAL_Control
0x180026d88  cmp     rcx, rax
0x180026d8b  jz      short loc_180026DB2
0x180026d8d  test    byte ptr [rcx+1Ch], 1
0x180026d91  jz      short loc_180026DB2
0x180026d93  cmp     byte ptr [rcx+19h], 2
0x180026d97  jb      short loc_180026DB2
0x180026d99  mov     edx, 14h
0x180026d9e  lea     r9d, [rdx+43h]
0x180026da2  lea     r8, WPP_50a4b5d3db573bd708b949f391e8ee2a_Traceguids
0x180026da9  mov     rcx, [rcx+10h]
0x180026dad  call    WPP_SF_D
0x180026db2  xorps   xmm0, xmm0
0x180026db5  movdqu  [rsp+188h+var_70], xmm0
0x180026dbe  mov     [rsp+188h+var_60], rdi
0x180026dc6  mov     [rsp+188h+var_58], 57h ; 'W'
0x180026dd1  mov     [rsp+188h+var_54], 0FFFFFFFFh
0x180026ddc  mov     [rsp+188h+var_50], 1CFh
0x180026de7  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180026dee  lea     rcx, [rsp+188h+var_70]; pExceptionObject
0x180026df6  call    _CxxThrowException_0
0x180026dfc  xor     edi, edi
0x180026dfe  mov     ebx, [rsp+188h+arg_18]
0x180026e05  mov     ecx, ebx; dwErrCode
0x180026e07  call    cs:__imp_SetLastError
0x180026e0d  test    ebx, ebx
0x180026e0f  setz    dil
0x180026e13  mov     eax, edi
0x180026e15  add     rsp, 158h
0x180026e1c  pop     r15
0x180026e1e  pop     r14
0x180026e20  pop     r12
0x180026e22  pop     rdi
0x180026e23  pop     rsi
0x180026e24  pop     rbx
0x180026e25  retn
```
