# MbbNdisSmsConfigurationStatusHandler(_MBB_REQUEST_CONTEXT *,int,_MBB_STATUS,uchar *,ulong)

- ea: `0x1400367e0`
- end: `0x140036bcf`
- name: `?MbbNdisSmsConfigurationStatusHandler@@YAHPEAU_MBB_REQUEST_CONTEXT@@HW4_MBB_STATUS@@PEAEK@Z`
- size: `1007`
- prototype: `__int64 __fastcall(__int64, int IsVariableFieldValid, unsigned int, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, loader_planting`

## callees

- `0x1400051ac`
- `0x140005644`
- `0x14002f228`
- `0x1400367e0`
- `0x14003df70`
- `0x14003f7e4`
- `0x14003f994`
- `0x140047e50`
- `0x140047e90`
- `0x140048340`

## import_xrefs

- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x1400369da`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x1400369da`

## pseudocode

```c
__int64 __fastcall MbbNdisSmsConfigurationStatusHandler(
        __int64 a1,
        int IsVariableFieldValid,
        unsigned int a3,
        __int64 a4,
        unsigned int a5)
{
  __int64 v9; // r8
  int v10; // r9d
  __int64 v11; // rax
  int v12; // edx
  int v13; // edi
  int v14; // edx
  int v15; // edx
  NTSTATUS v16; // eax
  int v17; // edx
  int v18; // ecx
  int v19; // eax
  _BYTE *v20; // rax
  __int64 v21; // rdx
  NDIS_HANDLE *v22; // rax
  struct _STRING DestinationString; // [rsp+40h] [rbp-A1h] BYREF
  UNICODE_STRING SourceString; // [rsp+50h] [rbp-91h] BYREF
  struct _NDIS_STATUS_INDICATION v26; // [rsp+60h] [rbp-81h] BYREF
  _OWORD v27[2]; // [rsp+D0h] [rbp-11h] BYREF
  __int64 v28; // [rsp+F0h] [rbp+Fh]

  memset(&v26.Header + 1, 0, 0x6Cu);
  v26.Header = (NDIS_OBJECT_HEADER)7340440;
  v28 = 0;
  v11 = *(_QWORD *)(a1 + 48);
  v12 = 40;
  memset(v27, 0, sizeof(v27));
  v26.SourceHandle = *(NDIS_HANDLE *)(**(_QWORD **)(*(_QWORD *)v11 + 1144LL) + 16LL);
  v26.DestinationHandle = *(NDIS_HANDLE *)(a1 + 440);
  v26.RequestId = *(PVOID *)(a1 + 432);
  v26.PortNumber = 0;
  *(_QWORD *)&v26.StatusCode = 1074008078;
  LODWORD(v27[0]) = 2622080;
  v26.Guid = 0;
  if ( !IsVariableFieldValid )
  {
    v13 = MbbUtilMbbToWwanStatus(a3);
    if ( v13 )
    {
LABEL_5:
      IsVariableFieldValid = -1073741823;
      goto LABEL_29;
    }
    if ( !a4 || a5 < 0x18 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v14) = 2;
        WPP_RECORDER_SF_Ddd(
          WPP_GLOBAL_Control->DeviceExtension,
          v14,
          3,
          154,
          (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
          *(_DWORD *)(a1 + 16),
          a5,
          16);
      }
      IsVariableFieldValid = -1073676267;
      goto LABEL_28;
    }
    if ( *(_DWORD *)a4 != 1 )
    {
      v13 = -1073479678;
      goto LABEL_5;
    }
    IsVariableFieldValid = MbbIsVariableFieldValid(a5, *(_DWORD *)(a4 + 16), *(_DWORD *)(a4 + 20), 0x14u, 2u, 1);
    if ( IsVariableFieldValid )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v15) = 2;
        WPP_RECORDER_SF_Ddd(
          WPP_GLOBAL_Control->DeviceExtension,
          v15,
          1,
          155,
          (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
          *(_DWORD *)(a1 + 16),
          *(_DWORD *)(a4 + 16),
          *(_DWORD *)(a4 + 20));
      }
LABEL_28:
      v13 = -1073479677;
      goto LABEL_29;
    }
    *(_QWORD *)&DestinationString.Length = 1310720;
    DestinationString.Buffer = (char *)v27 + 8;
    *(_DWORD *)(&SourceString.MaximumLength + 1) = 0;
    if ( a5 > 0x18 )
    {
      SourceString.Buffer = (wchar_t *)(a4 + *(unsigned int *)(a4 + 16));
      SourceString.Length = *(_WORD *)(a4 + 20);
      SourceString.MaximumLength = SourceString.Length;
      v16 = RtlUnicodeStringToAnsiString(&DestinationString, &SourceString, 0);
      if ( !v16 )
      {
        *((_BYTE *)v27 + DestinationString.Length + 8) = 0;
        goto LABEL_18;
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v17) = 2;
        WPP_RECORDER_SF_DD(
          WPP_GLOBAL_Control->DeviceExtension,
          v17,
          9,
          43,
          (__int64)&WPP_36f7929d0c593a29047f269d453c8817_Traceguids,
          *(_DWORD *)(a4 + 20),
          v16);
      }
    }
    BYTE8(v27[0]) = 0;
LABEL_18:
    v18 = *(_DWORD *)(a4 + 4);
    if ( v18 )
    {
      if ( v18 == 1 )
        v19 = 4;
      else
        v19 = 5;
    }
    else
    {
      v19 = 0;
    }
    LODWORD(v28) = v19;
    HIDWORD(v28) = *(_DWORD *)(a4 + 8);
    goto LABEL_29;
  }
  v13 = -1073479677;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v12) = 2;
    WPP_RECORDER_SF_DD(
      WPP_GLOBAL_Control->DeviceExtension,
      v12,
      3,
      153,
      (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
      *(_DWORD *)(a1 + 16),
      IsVariableFieldValid);
LABEL_29:
    v12 = 40;
  }
  if ( *(_QWORD *)(a1 + 424) || (v20 = (_BYTE *)(a1 + 576), *(_BYTE *)(a1 + 576)) )
  {
    DWORD1(v27[0]) = v13;
    v26.StatusBuffer = v27;
    v26.StatusBufferSize = 40;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v12) = 4;
      WPP_RECORDER_SF_DD(
        WPP_GLOBAL_Control->DeviceExtension,
        v12,
        3,
        156,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        *(_DWORD *)(a1 + 16),
        v13);
    }
    v21 = *(_QWORD *)(a1 + 104);
    if ( v21 )
      v22 = (NDIS_HANDLE *)((*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01031
                                                                                               + 1616))(
                              WdfDriverGlobals,
                              v21,
                              off_14005DF38)
                          + 24);
    else
      v22 = **(NDIS_HANDLE ***)(**(_QWORD **)(a1 + 48) + 1144LL);
    MbbUtilNdisMiniportIndicateStatusEx(v22, &v26);
    v20 = (_BYTE *)(a1 + 576);
  }
  if ( !*(_QWORD *)(a1 + 424) && !*v20 || *v20 == 1 && !IsVariableFieldValid )
  {
    *(_DWORD *)(a1 + 728) |= 2u;
    *(_BYTE *)(a1 + 748) = 0;
    if ( !IsVariableFieldValid )
      *(_BYTE *)(a1 + 748) = *(_BYTE *)(a4 + 12);
    MbbNdisIndicateReadyInfo((struct _MBB_REQUEST_CONTEXT *)a1, 0, v9, v10);
  }
  return 0;
}

```

## disassembly

```asm
0x1400367e0  push    rbp
0x1400367e2  push    rbx
0x1400367e3  push    rsi
0x1400367e4  push    rdi
0x1400367e5  push    r13
0x1400367e7  push    r14
0x1400367e9  push    r15
0x1400367eb  lea     rbp, [rsp-1Fh]
0x1400367f0  sub     rsp, 100h
0x1400367f7  mov     rax, cs:__security_cookie
0x1400367fe  xor     rax, rsp
0x140036801  mov     [rbp+4Fh+var_38], rax
0x140036805  mov     r14d, edx
0x140036808  mov     edi, r8d
0x14003680b  xor     edx, edx; Val
0x14003680d  mov     rbx, rcx
0x140036810  lea     rcx, [rbp+4Fh+var_D0+4]; void *
0x140036814  mov     rsi, r9
0x140036817  lea     r8d, [rdx+6Ch]; Size
0x14003681b  call    memset
0x140036820  xor     eax, eax
0x140036822  mov     dword ptr [rsp+130h+var_D0.Header.Type], 700198h
0x14003682a  mov     [rbp+4Fh+var_40], rax
0x14003682e  xorps   xmm0, xmm0
0x140036831  mov     rax, [rbx+30h]
0x140036835  mov     edx, 28h ; '('
0x14003683a  lea     r13, WPP_RECORDER_INITIALIZED
0x140036841  movups  [rbp+4Fh+var_60], xmm0
0x140036845  movups  [rbp+4Fh+var_50], xmm0
0x140036849  mov     rcx, [rax]
0x14003684c  mov     rax, [rcx+478h]
0x140036853  mov     rcx, [rax]
0x140036856  mov     rax, [rcx+10h]
0x14003685a  lea     rcx, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x140036861  mov     [rbp+4Fh+var_D0.SourceHandle], rax
0x140036865  mov     rax, [rbx+1B8h]
0x14003686c  mov     [rbp+4Fh+var_D0.DestinationHandle], rax
0x140036870  mov     rax, [rbx+1B0h]
0x140036877  mov     [rbp+4Fh+var_D0.RequestId], rax
0x14003687b  mov     [rbp+4Fh+var_D0.PortNumber], 0
0x140036882  mov     qword ptr [rbp+4Fh+var_D0.StatusCode], 4004100Eh
0x14003688a  mov     dword ptr [rbp+4Fh+var_60], 280280h
0x140036891  movups  xmmword ptr [rbp+4Fh+var_D0.Guid.Data1], xmm0
0x140036895  test    r14d, r14d
0x140036898  jz      short loc_1400368DC
0x14003689a  mov     edi, 0C0040003h
0x14003689f  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400368a6  jz      loc_140036ABB
0x1400368ac  mov     eax, [rbx+10h]
0x1400368af  lea     r9d, [rdx+71h]
0x1400368b3  mov     [rsp+130h+var_100], r14d
0x1400368b8  lea     r8d, [rdx-25h]
0x1400368bc  mov     [rsp+130h+var_108], eax
0x1400368c0  mov     dl, 2
0x1400368c2  mov     qword ptr [rsp+130h+var_110], rcx
0x1400368c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400368ce  mov     rcx, [rcx+40h]
0x1400368d2  call    WPP_RECORDER_SF_DD
0x1400368d7  jmp     loc_140036AAF
0x1400368dc  mov     ecx, edi
0x1400368de  call    ?MbbUtilMbbToWwanStatus@@YAKW4_MBB_STATUS@@@Z; MbbUtilMbbToWwanStatus(_MBB_STATUS)
0x1400368e3  mov     edi, eax
0x1400368e5  test    eax, eax
0x1400368e7  jz      short loc_1400368F4
0x1400368e9  mov     r14d, 0C0000001h
0x1400368ef  jmp     loc_140036AAF
0x1400368f4  mov     r15d, [rbp+4Fh+arg_20]
0x1400368f8  test    rsi, rsi
0x1400368fb  jz      loc_140036A5D
0x140036901  cmp     r15d, 18h
0x140036905  jb      loc_140036A5D
0x14003690b  cmp     dword ptr [rsi], 1
0x14003690e  jz      short loc_140036917
0x140036910  mov     edi, 0C0040002h
0x140036915  jmp     short loc_1400368E9
0x140036917  mov     r8d, [rsi+14h]; unsigned int
0x14003691b  mov     r9d, 14h; unsigned int
0x140036921  mov     edx, [rsi+10h]; unsigned int
0x140036924  mov     ecx, r15d; unsigned int
0x140036927  mov     [rsp+130h+var_108], 1; int
0x14003692f  mov     [rsp+130h+var_110], 2; unsigned int
0x140036937  call    ?MbbIsVariableFieldValid@@YAJKKKKKH@Z; MbbIsVariableFieldValid(ulong,ulong,ulong,ulong,ulong,int)
0x14003693c  mov     r14d, eax
0x14003693f  test    eax, eax
0x140036941  jz      short loc_140036994
0x140036943  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14003694a  jz      loc_140036AAA
0x140036950  mov     eax, [rsi+14h]
0x140036953  mov     r9d, 9Bh
0x140036959  mov     rcx, cs:WPP_GLOBAL_Control
0x140036960  mov     r8d, 1
0x140036966  mov     [rsp+130h+var_F8], eax
0x14003696a  mov     dl, 2
0x14003696c  mov     eax, [rsi+10h]
0x14003696f  mov     [rsp+130h+var_100], eax
0x140036973  mov     eax, [rbx+10h]
0x140036976  mov     rcx, [rcx+40h]
0x14003697a  mov     [rsp+130h+var_108], eax
0x14003697e  lea     rax, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x140036985  mov     qword ptr [rsp+130h+var_110], rax
0x14003698a  call    WPP_RECORDER_SF_Ddd
0x14003698f  jmp     loc_140036AAA
0x140036994  mov     qword ptr [rsp+130h+DestinationString.Length], 140000h
0x14003699d  lea     rax, [rbp+4Fh+var_60+8]
0x1400369a1  mov     [rsp+130h+DestinationString.Buffer], rax
0x1400369a6  mov     dword ptr [rsp+130h+SourceString+4], 0
0x1400369ae  cmp     r15d, 18h
0x1400369b2  jbe     short loc_140036A26
0x1400369b4  mov     eax, [rsi+10h]
0x1400369b7  lea     rdx, [rsp+130h+SourceString]; SourceString
0x1400369bc  add     rax, rsi
0x1400369bf  lea     rcx, [rsp+130h+DestinationString]; DestinationString
0x1400369c4  mov     [rsp+130h+SourceString.Buffer], rax
0x1400369c9  xor     r8d, r8d; AllocateDestinationString
0x1400369cc  movzx   eax, word ptr [rsi+14h]
0x1400369d0  mov     [rsp+130h+SourceString.Length], ax
0x1400369d5  mov     [rsp+130h+SourceString.MaximumLength], ax
0x1400369da  call    cs:__imp_RtlUnicodeStringToAnsiString
0x1400369e1  nop     dword ptr [rax+rax+00h]
0x1400369e6  test    eax, eax
0x1400369e8  jz      short loc_140036A3D
0x1400369ea  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400369f1  jz      short loc_140036A26
0x1400369f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400369fa  mov     r9d, 2Bh ; '+'
0x140036a00  mov     [rsp+130h+var_100], eax
0x140036a04  mov     dl, 2
0x140036a06  mov     eax, [rsi+14h]
0x140036a09  mov     [rsp+130h+var_108], eax
0x140036a0d  lea     rax, WPP_36f7929d0c593a29047f269d453c8817_Traceguids
0x140036a14  mov     rcx, [rcx+40h]
0x140036a18  lea     r8d, [r9-22h]
0x140036a1c  mov     qword ptr [rsp+130h+var_110], rax
0x140036a21  call    WPP_RECORDER_SF_DD
0x140036a26  mov     byte ptr [rbp+4Fh+var_60+8], 0
0x140036a2a  mov     ecx, [rsi+4]
0x140036a2d  test    ecx, ecx
0x140036a2f  jz      short loc_140036A50
0x140036a31  cmp     ecx, 1
0x140036a34  jz      short loc_140036A49
0x140036a36  mov     eax, 5
0x140036a3b  jmp     short loc_140036A52
0x140036a3d  movzx   eax, [rsp+130h+DestinationString.Length]
0x140036a42  mov     byte ptr [rbp+rax+4Fh+var_60+8], 0
0x140036a47  jmp     short loc_140036A2A
0x140036a49  mov     eax, 4
0x140036a4e  jmp     short loc_140036A52
0x140036a50  xor     eax, eax
0x140036a52  mov     dword ptr [rbp+4Fh+var_40], eax
0x140036a55  mov     eax, [rsi+8]
0x140036a58  mov     dword ptr [rbp+4Fh+var_40+4], eax
0x140036a5b  jmp     short loc_140036AAF
0x140036a5d  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140036a64  jz      short loc_140036AA4
0x140036a66  mov     eax, [rbx+10h]
0x140036a69  mov     r9d, 9Ah
0x140036a6f  mov     rcx, cs:WPP_GLOBAL_Control
0x140036a76  mov     r8d, 3
0x140036a7c  mov     [rsp+130h+var_F8], 10h
0x140036a84  mov     dl, 2
0x140036a86  mov     [rsp+130h+var_100], r15d
0x140036a8b  mov     [rsp+130h+var_108], eax
0x140036a8f  lea     rax, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x140036a96  mov     rcx, [rcx+40h]
0x140036a9a  mov     qword ptr [rsp+130h+var_110], rax
0x140036a9f  call    WPP_RECORDER_SF_Ddd
0x140036aa4  mov     r14d, 0C0010015h
0x140036aaa  mov     edi, 0C0040003h
0x140036aaf  mov     edx, 28h ; '('
0x140036ab4  lea     rcx, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x140036abb  cmp     qword ptr [rbx+1A8h], 0
0x140036ac3  jnz     short loc_140036AD5
0x140036ac5  lea     rax, [rbx+240h]
0x140036acc  cmp     byte ptr [rax], 0
0x140036acf  jz      loc_140036B6F
0x140036ad5  lea     rax, [rbp+4Fh+var_60]
0x140036ad9  mov     dword ptr [rbp+4Fh+var_60+4], edi
0x140036adc  mov     [rbp+4Fh+var_D0.StatusBuffer], rax
0x140036ae0  mov     [rbp+4Fh+var_D0.StatusBufferSize], edx
0x140036ae3  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140036aea  jz      short loc_140036B1A
0x140036aec  mov     eax, [rbx+10h]
0x140036aef  mov     r9d, 9Ch
0x140036af5  mov     [rsp+130h+var_100], edi
0x140036af9  mov     r8d, 3
0x140036aff  mov     [rsp+130h+var_108], eax
0x140036b03  mov     dl, 4
0x140036b05  mov     qword ptr [rsp+130h+var_110], rcx
0x140036b0a  mov     rcx, cs:WPP_GLOBAL_Control
0x140036b11  mov     rcx, [rcx+40h]
0x140036b15  call    WPP_RECORDER_SF_DD
0x140036b1a  mov     rdx, [rbx+68h]
0x140036b1e  test    rdx, rdx
0x140036b21  jz      short loc_140036B4A
0x140036b23  mov     rax, cs:WdfFunctions_01031
0x140036b2a  mov     r8, cs:off_14005DF38
0x140036b31  mov     rcx, cs:WdfDriverGlobals
0x140036b38  mov     rax, [rax+650h]
0x140036b3f  call    _guard_dispatch_icall
0x140036b44  add     rax, 18h
0x140036b48  jmp     short loc_140036B5B
0x140036b4a  mov     rax, [rbx+30h]
0x140036b4e  mov     rcx, [rax]
0x140036b51  mov     rax, [rcx+478h]
0x140036b58  mov     rax, [rax]
0x140036b5b  lea     rdx, [rsp+130h+var_D0]; struct _NDIS_STATUS_INDICATION *
0x140036b60  mov     rcx, rax; struct _MINIPORT_INTERFACE_CONTEXT *
0x140036b63  call    ?MbbUtilNdisMiniportIndicateStatusEx@@YAXPEAU_MINIPORT_INTERFACE_CONTEXT@@PEAU_NDIS_STATUS_INDICATION@@@Z; MbbUtilNdisMiniportIndicateStatusEx(_MINIPORT_INTERFACE_CONTEXT *,_NDIS_STATUS_INDICATION *)
0x140036b68  lea     rax, [rbx+240h]
0x140036b6f  cmp     qword ptr [rbx+1A8h], 0
0x140036b77  jnz     short loc_140036B7E
0x140036b79  cmp     byte ptr [rax], 0
0x140036b7c  jz      short loc_140036B88
0x140036b7e  cmp     byte ptr [rax], 1
0x140036b81  jnz     short loc_140036BAE
0x140036b83  test    r14d, r14d
0x140036b86  jnz     short loc_140036BAE
0x140036b88  or      dword ptr [rbx+2D8h], 2
0x140036b8f  mov     byte ptr [rbx+2ECh], 0
0x140036b96  test    r14d, r14d
0x140036b99  jnz     short loc_140036BA4
0x140036b9b  mov     al, [rsi+0Ch]
0x140036b9e  mov     [rbx+2ECh], al
0x140036ba4  xor     edx, edx; int
0x140036ba6  mov     rcx, rbx; struct _MBB_REQUEST_CONTEXT *
0x140036ba9  call    ?MbbNdisIndicateReadyInfo@@YAXPEAU_MBB_REQUEST_CONTEXT@@H@Z; MbbNdisIndicateReadyInfo(_MBB_REQUEST_CONTEXT *,int)
0x140036bae  xor     eax, eax
0x140036bb0  mov     rcx, [rbp+4Fh+var_38]
0x140036bb4  xor     rcx, rsp; StackCookie
0x140036bb7  call    __security_check_cookie
0x140036bbc  add     rsp, 100h
0x140036bc3  pop     r15
0x140036bc5  pop     r14
0x140036bc7  pop     r13
0x140036bc9  pop     rdi
0x140036bca  pop     rsi
0x140036bcb  pop     rbx
0x140036bcc  pop     rbp
0x140036bcd  retn
```
