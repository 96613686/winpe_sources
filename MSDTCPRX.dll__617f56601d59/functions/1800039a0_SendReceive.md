# SendReceive

- ea: `0x1800039a0`
- end: `0x180003cdf`
- name: `SendReceive`
- size: `831`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800039a0`
- `0x180003cf0`
- `0x1800041a0`
- `0x1800045f0`
- `0x180070620`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180003bfc`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180003c6e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180003bfc`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180003c6e`
- `msvcrt!_stricmp` at `0x180003ab4`
- `msvcrt!_stricmp` at `0x180003ab4`

## string_xrefs

- `0x1800039e8`: `com\complus\dtc\dtc\cm\src\iomgrrpc.cpp`
- `0x180003a44`: `com\complus\dtc\dtc\cm\src\iomgrrpc.cpp`
- `0x180003cb4`: `com\complus\dtc\dtc\cm\src\iomgrrpc.cpp`
- `0x180003a88`: `com\complus\dtc\dtc\cm\src\iomgrsrv.cpp`
- `0x180003b25`: `com\complus\dtc\dtc\cm\src\iomgrsrv.cpp`
- `0x180003b7e`: `com\complus\dtc\dtc\cm\src\iomgrsrv.cpp`
- `0x180003bd5`: `com\complus\dtc\dtc\cm\src\iomgrsrv.cpp`

## pseudocode

```c
__int64 __fastcall SendReceive(__int64 a1, unsigned int a2, unsigned int a3, __int64 a4)
{
  unsigned int v8; // edi
  __int64 v9; // rax
  _DWORD *v10; // rsi
  DWORD v11; // ecx
  __int64 v13; // [rsp+28h] [rbp-90h]
  __int64 v14; // [rsp+38h] [rbp-80h]
  __int64 v15; // [rsp+40h] [rbp-78h]
  _DWORD *v16; // [rsp+68h] [rbp-50h]
  int v17; // [rsp+68h] [rbp-50h]

  TraceStringInline(
    1,
    6,
    L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrrpc.cpp",
    1288,
    L"SendReceive",
    0,
    L"RPC: Called SendReceive.");
  if ( !*(_QWORD *)a1 )
    goto LABEL_5;
  if ( !*(_DWORD *)(*(_QWORD *)a1 + 52LL) )
  {
    v8 = -2147483357;
    goto LABEL_25;
  }
  TraceStringInline(
    1,
    5,
    L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrrpc.cpp",
    1302,
    L"SendReceive",
    0,
    L"RPC: Calling pCRpcIOMgrSrvr->Receive; phContext=%p; dwcMessages=%d;dwcbSizeOfBoxCar=%d;rguchBoxCar=%p",
    a1,
    a2,
    a3,
    a4);
  v8 = 0;
  TraceStringInline(
    1,
    6,
    L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp",
    2135,
    L"CRpcIOManagerServer::Receive",
    0,
    L"In");
  v9 = *(_QWORD *)(a1 + 8);
  v16 = (_DWORD *)v9;
  if ( *(_DWORD *)(v9 + 4) && !_stricmp((const char *)(a1 + 16), (const char *)(v9 + 48)) )
  {
    v10 = v16;
    if ( v16[26] != 7 )
    {
      if ( (unsigned int)(v16[25] - 3) <= 1 )
      {
        v8 = -2147483367;
        goto LABEL_25;
      }
      Sleep(0x3E8u);
      if ( v16[26] != 7 )
      {
        v8 = -2147483357;
        goto LABEL_25;
      }
    }
    if ( a2 && a3 >= 0x28 && a4 )
    {
      LODWORD(v15) = a3;
      LODWORD(v14) = a2;
      TraceStringInline(
        1,
        5,
        L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp",
        2207,
        L"CRpcIOManagerServer::Receive",
        0,
        L"dwcMessages=%d;dwcbSizeOfBoxCar=%d,puchBoxCar=%p",
        v14,
        v15,
        a4);
      if ( a2 != 1 || *(_DWORD *)(a4 + 16) != 4 )
      {
        CRWLock::AcquireReaderLock((CRWLock *)(v16 + 288));
        v17 = 2;
        while ( 1 )
        {
          v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64))(**((_QWORD **)v10 + 20) + 16LL))(
                 *((_QWORD *)v10 + 20),
                 a2,
                 a3,
                 a4);
          if ( v8 != -2147483354 )
            break;
          v11 = 2 * v17;
          if ( (unsigned int)(2 * v17) >= 0xEA60 )
            v11 = 60000;
          v17 = v11;
          Sleep(v11);
        }
        CRWLock::ReleaseReaderLock((CRWLock *)(v10 + 288));
      }
      TraceStringInline(
        1,
        6,
        L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp",
        2307,
        L"CRpcIOManagerServer::Receive",
        0,
        L"Out");
    }
    else
    {
      v8 = -2147483367;
      LODWORD(v13) = -2147483367;
      TraceStringInline(
        1,
        1,
        L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp",
        2200,
        L"CRpcIOManagerServer::Receive",
        v13,
        L"BAD BOX CAR CAME THROUGH");
    }
  }
  else
  {
LABEL_5:
    v8 = -2147483352;
  }
LABEL_25:
  TraceStringInline(
    1,
    6,
    L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrrpc.cpp",
    1321,
    L"SendReceive",
    0,
    L"Leaving SendReceive");
  return v8;
}

```

## disassembly

```asm
0x1800039a0  push    rbx
0x1800039a2  push    rsi
0x1800039a3  push    rdi
0x1800039a4  push    r12
0x1800039a6  push    r13
0x1800039a8  push    r14
0x1800039aa  push    r15
0x1800039ac  sub     rsp, 80h
0x1800039b3  mov     r12, r9
0x1800039b6  mov     r13d, r8d
0x1800039b9  mov     r15d, edx
0x1800039bc  mov     rsi, rcx
0x1800039bf  xor     ebx, ebx
0x1800039c1  mov     [rsp+0B8h+var_58], ebx
0x1800039c5  lea     rax, aRpcCalledSendr; "RPC: Called SendReceive."
0x1800039cc  mov     [rsp+0B8h+var_88], rax
0x1800039d1  mov     [rsp+0B8h+var_90], rbx
0x1800039d6  lea     r14, aSendreceive; "SendReceive"
0x1800039dd  mov     [rsp+0B8h+var_98], r14
0x1800039e2  mov     r9d, 508h
0x1800039e8  lea     r8, aComComplusDtcD_14; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrr"...
0x1800039ef  mov     edx, 6
0x1800039f4  mov     ecx, 1
0x1800039f9  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800039fe  nop
0x1800039ff  mov     rax, [rsi]
0x180003a02  test    rax, rax
0x180003a05  jz      loc_180003ABE
0x180003a0b  cmp     [rax+34h], ebx
0x180003a0e  jz      loc_180003BED
0x180003a14  mov     [rsp+0B8h+var_68], r12
0x180003a19  mov     dword ptr [rsp+0B8h+var_70], r13d
0x180003a1e  mov     dword ptr [rsp+0B8h+var_78], r15d
0x180003a23  mov     [rsp+0B8h+var_80], rsi
0x180003a28  lea     rax, aRpcCallingPcrp; "RPC: Calling pCRpcIOMgrSrvr->Receive; p"...
0x180003a2f  mov     [rsp+0B8h+var_88], rax
0x180003a34  mov     [rsp+0B8h+var_90], rbx
0x180003a39  mov     [rsp+0B8h+var_98], r14
0x180003a3e  mov     r9d, 516h
0x180003a44  lea     r8, aComComplusDtcD_14; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrr"...
0x180003a4b  mov     edx, 5
0x180003a50  mov     ecx, 1
0x180003a55  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180003a5a  mov     edi, ebx
0x180003a5c  mov     [rsp+0B8h+var_48], ebx
0x180003a60  mov     [rsp+0B8h+var_50], rbx
0x180003a65  lea     rax, aIn_0; "In"
0x180003a6c  mov     [rsp+0B8h+var_88], rax
0x180003a71  mov     [rsp+0B8h+var_90], rbx
0x180003a76  lea     rax, aCrpciomanagers_12; "CRpcIOManagerServer::Receive"
0x180003a7d  mov     [rsp+0B8h+var_98], rax
0x180003a82  mov     r9d, 857h
0x180003a88  lea     r8, aComComplusDtcD_34; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrs"...
0x180003a8f  mov     edx, 6
0x180003a94  mov     ecx, 1
0x180003a99  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180003a9e  mov     rax, [rsi+8]
0x180003aa2  mov     [rsp+0B8h+var_50], rax
0x180003aa7  cmp     [rax+4], ebx
0x180003aaa  jz      short loc_180003ABE
0x180003aac  lea     rdx, [rax+30h]; String2
0x180003ab0  lea     rcx, [rsi+10h]; String1
0x180003ab4  call    cs:__imp__stricmp
0x180003aba  test    eax, eax
0x180003abc  jz      short loc_180003AC8
0x180003abe  mov     edi, 80000128h
0x180003ac3  jmp     loc_180003C85
0x180003ac8  mov     rsi, [rsp+0B8h+var_50]
0x180003acd  cmp     dword ptr [rsi+68h], 7
0x180003ad1  jnz     loc_180003B99
0x180003ad7  test    r15d, r15d
0x180003ada  jz      loc_180003BAE
0x180003ae0  cmp     r13d, 28h ; '('
0x180003ae4  jb      loc_180003BAE
0x180003aea  test    r12, r12
0x180003aed  jz      loc_180003BAE
0x180003af3  mov     [rsp+0B8h+var_70], r12
0x180003af8  mov     dword ptr [rsp+0B8h+var_78], r13d
0x180003afd  mov     dword ptr [rsp+0B8h+var_80], r15d
0x180003b02  lea     rax, aDwcmessagesDDw; "dwcMessages=%d;dwcbSizeOfBoxCar=%d,puch"...
0x180003b09  mov     [rsp+0B8h+var_88], rax
0x180003b0e  mov     [rsp+0B8h+var_90], rbx
0x180003b13  lea     rax, aCrpciomanagers_12; "CRpcIOManagerServer::Receive"
0x180003b1a  mov     [rsp+0B8h+var_98], rax
0x180003b1f  mov     r9d, 89Fh
0x180003b25  lea     r8, aComComplusDtcD_34; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrs"...
0x180003b2c  mov     edx, 5
0x180003b31  mov     ecx, 1
0x180003b36  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180003b3b  mov     dword ptr [rsp+0B8h+var_50], r15d
0x180003b40  mov     dword ptr [rsp+0B8h+var_50+4], r13d
0x180003b45  cmp     r15d, 1
0x180003b49  jnz     loc_180003C13
0x180003b4f  cmp     dword ptr [r12+10h], 4
0x180003b55  jnz     loc_180003C13
0x180003b5b  lea     rax, aOut; "Out"
0x180003b62  mov     [rsp+0B8h+var_88], rax
0x180003b67  mov     [rsp+0B8h+var_90], rbx
0x180003b6c  lea     rax, aCrpciomanagers_12; "CRpcIOManagerServer::Receive"
0x180003b73  mov     [rsp+0B8h+var_98], rax
0x180003b78  mov     r9d, 903h
0x180003b7e  lea     r8, aComComplusDtcD_34; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrs"...
0x180003b85  mov     edx, 6
0x180003b8a  mov     ecx, 1
0x180003b8f  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180003b94  jmp     loc_180003C85
0x180003b99  mov     eax, [rsi+64h]
0x180003b9c  sub     eax, 3
0x180003b9f  cmp     eax, 1
0x180003ba2  ja      short loc_180003BF7
0x180003ba4  mov     edi, 80000119h
0x180003ba9  jmp     loc_180003C85
0x180003bae  lea     rax, aBadBoxCarCameT; "BAD BOX CAR CAME THROUGH"
0x180003bb5  mov     [rsp+0B8h+var_88], rax
0x180003bba  mov     edi, 80000119h
0x180003bbf  mov     dword ptr [rsp+0B8h+var_90], edi
0x180003bc3  lea     rax, aCrpciomanagers_12; "CRpcIOManagerServer::Receive"
0x180003bca  mov     [rsp+0B8h+var_98], rax
0x180003bcf  mov     r9d, 898h
0x180003bd5  lea     r8, aComComplusDtcD_34; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrs"...
0x180003bdc  mov     edx, 1
0x180003be1  mov     ecx, edx
0x180003be3  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180003be8  jmp     loc_180003C85
0x180003bed  mov     edi, 80000123h
0x180003bf2  jmp     loc_180003C85
0x180003bf7  mov     ecx, 3E8h; dwMilliseconds
0x180003bfc  call    cs:__imp_Sleep
0x180003c02  cmp     dword ptr [rsi+68h], 7
0x180003c06  jz      loc_180003AD7
0x180003c0c  mov     edi, 80000123h
0x180003c11  jmp     short loc_180003C85
0x180003c13  lea     rax, [rsi+480h]
0x180003c1a  mov     [rsp+0B8h+var_40], rax
0x180003c1f  mov     rcx, rax; this
0x180003c22  call    ?AcquireReaderLock@CRWLock@@QEAAJXZ; CRWLock::AcquireReaderLock(void)
0x180003c27  mov     dword ptr [rsp+0B8h+var_50], 2
0x180003c2f  mov     rcx, [rsi+0A0h]
0x180003c36  mov     rax, [rcx]
0x180003c39  mov     r9, r12
0x180003c3c  mov     r8d, r13d
0x180003c3f  mov     edx, r15d
0x180003c42  mov     rax, [rax+10h]
0x180003c46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c4b  mov     edi, eax
0x180003c4d  mov     [rsp+0B8h+var_48], eax
0x180003c51  cmp     eax, 80000126h
0x180003c56  jnz     short loc_180003C76
0x180003c58  mov     eax, dword ptr [rsp+0B8h+var_50]
0x180003c5c  add     eax, eax
0x180003c5e  mov     ecx, eax
0x180003c60  mov     edx, 0EA60h
0x180003c65  cmp     eax, edx
0x180003c67  cmovnb  ecx, edx; dwMilliseconds
0x180003c6a  mov     dword ptr [rsp+0B8h+var_50], ecx
0x180003c6e  call    cs:__imp_Sleep
0x180003c74  jmp     short loc_180003C2F
0x180003c76  mov     rcx, [rsp+0B8h+var_40]; this
0x180003c7b  call    ?ReleaseReaderLock@CRWLock@@QEAAJXZ; CRWLock::ReleaseReaderLock(void)
0x180003c80  jmp     loc_180003B5B
0x180003c85  mov     [rsp+0B8h+var_58], edi
0x180003c89  jmp     short loc_180003C98
0x180003c8b  xor     ebx, ebx
0x180003c8d  lea     r14, aSendreceive; "SendReceive"
0x180003c94  mov     edi, [rsp+0B8h+var_58]
0x180003c98  lea     rax, aLeavingSendrec; "Leaving SendReceive"
0x180003c9f  mov     [rsp+0B8h+var_88], rax
0x180003ca4  mov     [rsp+0B8h+var_90], rbx
0x180003ca9  mov     [rsp+0B8h+var_98], r14
0x180003cae  mov     r9d, 529h
0x180003cb4  lea     r8, aComComplusDtcD_14; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrr"...
0x180003cbb  mov     edx, 6
0x180003cc0  mov     ecx, 1
0x180003cc5  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180003cca  mov     eax, edi
0x180003ccc  add     rsp, 80h
0x180003cd3  pop     r15
0x180003cd5  pop     r14
0x180003cd7  pop     r13
0x180003cd9  pop     r12
0x180003cdb  pop     rdi
0x180003cdc  pop     rsi
0x180003cdd  pop     rbx
0x180003cde  retn
0x180081ef0  push    rbp
0x180081ef2  sub     rsp, 60h
0x180081ef6  mov     rbp, rdx
0x180081ef9  call    ?DtcExceptionFilter@@YAKPEAU_EXCEPTION_POINTERS@@H@Z; DtcExceptionFilter(_EXCEPTION_POINTERS *,int)
0x180081efe  nop
0x180081eff  add     rsp, 60h
0x180081f03  pop     rbp
0x180081f04  retn
```
