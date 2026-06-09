# MbbNdisModemLoggingConfigHandler(_MBB_REQUEST_CONTEXT *,int,_MBB_STATUS,uchar *,ulong)

- ea: `0x140030590`
- end: `0x140030826`
- name: `?MbbNdisModemLoggingConfigHandler@@YAHPEAU_MBB_REQUEST_CONTEXT@@HW4_MBB_STATUS@@PEAEK@Z`
- size: `662`
- prototype: `__int64 __fastcall(__int64, int, unsigned int, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callees

- `0x140001db8`
- `0x1400051ac`
- `0x140005644`
- `0x140030590`
- `0x14003f7e4`
- `0x14003f994`
- `0x140047e50`
- `0x140047e90`
- `0x140048340`

## pseudocode

```c
__int64 __fastcall MbbNdisModemLoggingConfigHandler(__int64 a1, int a2, unsigned int a3, __int64 a4, unsigned int a5)
{
  __int64 v9; // rax
  int v10; // edx
  unsigned int v11; // eax
  int v12; // ebx
  __int64 v13; // rdx
  NDIS_HANDLE *v14; // rax
  struct _NDIS_STATUS_INDICATION v16; // [rsp+40h] [rbp-61h] BYREF
  __int128 v17; // [rsp+B0h] [rbp+Fh] BYREF
  __int64 v18; // [rsp+C0h] [rbp+1Fh]

  memset(&v16.Header + 1, 0, 0x6Cu);
  v16.Header = (NDIS_OBJECT_HEADER)7340440;
  v18 = 0;
  v9 = *(_QWORD *)(a1 + 48);
  v17 = 0;
  v16.SourceHandle = *(NDIS_HANDLE *)(**(_QWORD **)(*(_QWORD *)v9 + 1144LL) + 16LL);
  v16.DestinationHandle = *(NDIS_HANDLE *)(a1 + 440);
  v16.RequestId = *(PVOID *)(a1 + 432);
  v16.PortNumber = 0;
  *(_QWORD *)&v16.StatusCode = 1074008136;
  v16.Guid = 0;
  LODWORD(v17) = 1573248;
  MbbUtilMbbToWwanStatus(a3);
  if ( a2 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = 2;
      WPP_RECORDER_SF_DD(
        WPP_GLOBAL_Control->DeviceExtension,
        v10,
        3,
        410,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        *(_DWORD *)(a1 + 16),
        a2);
    }
LABEL_15:
    v12 = -1073479677;
LABEL_16:
    if ( (unsigned int)MbbUtilMbbToWwanStatus(a3) )
      v12 = MbbUtilMbbToWwanStatus(a3);
    goto LABEL_18;
  }
  if ( !a4 || a5 < 0x10 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = 2;
      WPP_RECORDER_SF_Ddd(
        WPP_GLOBAL_Control->DeviceExtension,
        v10,
        3,
        411,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        *(_DWORD *)(a1 + 16),
        a5,
        16,
        *(_QWORD *)&v16.Header.Type);
    }
    goto LABEL_15;
  }
  *((_QWORD *)&v17 + 1) = *(_QWORD *)a4;
  LODWORD(v18) = *(_DWORD *)(a4 + 8);
  v11 = *(_DWORD *)(a4 + 12);
  if ( v11 > 4 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v10,
        9,
        63,
        (__int64)&WPP_36f7929d0c593a29047f269d453c8817_Traceguids,
        v11);
    }
    v12 = -1073676267;
  }
  else
  {
    HIDWORD(v18) = *(_DWORD *)(a4 + 12);
    v12 = 0;
  }
  if ( v12 )
    goto LABEL_16;
LABEL_18:
  DWORD1(v17) = v12;
  v16.StatusBuffer = &v17;
  v16.StatusBufferSize = 24;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v10) = 4;
    WPP_RECORDER_SF_DD(
      WPP_GLOBAL_Control->DeviceExtension,
      v10,
      3,
      412,
      (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
      *(_DWORD *)(a1 + 16),
      v12);
  }
  v13 = *(_QWORD *)(a1 + 104);
  if ( v13 )
    v14 = (NDIS_HANDLE *)((*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01031 + 1616))(
                            WdfDriverGlobals,
                            v13,
                            off_14005DF38)
                        + 24);
  else
    v14 = **(NDIS_HANDLE ***)(**(_QWORD **)(a1 + 48) + 1144LL);
  MbbUtilNdisMiniportIndicateStatusEx(v14, &v16);
  return 0;
}

```

## disassembly

```asm
0x140030590  mov     [rsp-8+arg_8], rbx
0x140030595  mov     [rsp-8+arg_18], rsi
0x14003059a  push    rbp
0x14003059b  push    rdi
0x14003059c  push    r13
0x14003059e  push    r14
0x1400305a0  push    r15
0x1400305a2  lea     rbp, [rsp-2Fh]
0x1400305a7  sub     rsp, 0D0h
0x1400305ae  mov     rax, cs:__security_cookie
0x1400305b5  xor     rax, rsp
0x1400305b8  mov     [rbp+4Fh+var_28], rax
0x1400305bc  mov     r15d, edx
0x1400305bf  mov     r14d, r8d
0x1400305c2  xor     edx, edx; Val
0x1400305c4  mov     rsi, rcx
0x1400305c7  lea     rcx, [rbp+4Fh+var_B0+4]; void *
0x1400305cb  mov     rbx, r9
0x1400305ce  lea     r8d, [rdx+6Ch]; Size
0x1400305d2  call    memset
0x1400305d7  xor     eax, eax
0x1400305d9  mov     dword ptr [rbp+4Fh+var_B0.Header.Type], 700198h
0x1400305e0  mov     [rbp+4Fh+var_30], rax
0x1400305e4  xorps   xmm0, xmm0
0x1400305e7  mov     rax, [rsi+30h]
0x1400305eb  movups  [rbp+4Fh+var_40], xmm0
0x1400305ef  mov     rcx, [rax]
0x1400305f2  mov     rax, [rcx+478h]
0x1400305f9  mov     rcx, [rax]
0x1400305fc  mov     rax, [rcx+10h]
0x140030600  mov     ecx, r14d
0x140030603  mov     [rbp+4Fh+var_B0.SourceHandle], rax
0x140030607  mov     rax, [rsi+1B8h]
0x14003060e  mov     [rbp+4Fh+var_B0.DestinationHandle], rax
0x140030612  mov     rax, [rsi+1B0h]
0x140030619  mov     [rbp+4Fh+var_B0.RequestId], rax
0x14003061d  mov     [rbp+4Fh+var_B0.PortNumber], 0
0x140030624  mov     qword ptr [rbp+4Fh+var_B0.StatusCode], 40041048h
0x14003062c  movups  xmmword ptr [rbp+4Fh+var_B0.Guid.Data1], xmm0
0x140030630  mov     dword ptr [rbp+4Fh+var_40], 180180h
0x140030637  call    ?MbbUtilMbbToWwanStatus@@YAKW4_MBB_STATUS@@@Z; MbbUtilMbbToWwanStatus(_MBB_STATUS)
0x14003063c  lea     r13, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x140030643  test    r15d, r15d
0x140030646  jz      short loc_140030690
0x140030648  lea     rdi, WPP_RECORDER_INITIALIZED
0x14003064f  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140030656  jz      loc_14003074A
0x14003065c  mov     rcx, cs:WPP_GLOBAL_Control
0x140030663  mov     r9d, 19Ah
0x140030669  mov     eax, [rsi+10h]
0x14003066c  mov     r8d, 3
0x140030672  mov     [rsp+0F0h+var_C0], r15d
0x140030677  mov     dl, 2
0x140030679  mov     [rsp+0F0h+var_C8], eax
0x14003067d  mov     rcx, [rcx+40h]
0x140030681  mov     [rsp+0F0h+var_D0], r13
0x140030686  call    WPP_RECORDER_SF_DD
0x14003068b  jmp     loc_14003074A
0x140030690  mov     eax, [rbp+4Fh+arg_20]
0x140030693  test    rbx, rbx
0x140030696  jz      short loc_140030704
0x140030698  cmp     eax, 10h
0x14003069b  jb      short loc_140030704
0x14003069d  mov     eax, [rbx]
0x14003069f  lea     rdi, WPP_RECORDER_INITIALIZED
0x1400306a6  mov     dword ptr [rbp+4Fh+var_40+8], eax
0x1400306a9  mov     eax, [rbx+4]
0x1400306ac  mov     dword ptr [rbp+4Fh+var_40+0Ch], eax
0x1400306af  mov     eax, [rbx+8]
0x1400306b2  mov     dword ptr [rbp+4Fh+var_30], eax
0x1400306b5  mov     eax, [rbx+0Ch]
0x1400306b8  cmp     eax, 4
0x1400306bb  ja      short loc_1400306C4
0x1400306bd  mov     dword ptr [rbp+4Fh+var_30+4], eax
0x1400306c0  xor     ebx, ebx
0x1400306c2  jmp     short loc_1400306FE
0x1400306c4  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400306cb  jz      short loc_1400306F9
0x1400306cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400306d4  mov     r9d, 3Fh ; '?'
0x1400306da  mov     [rsp+0F0h+var_C8], eax
0x1400306de  mov     dl, 2
0x1400306e0  lea     rax, WPP_36f7929d0c593a29047f269d453c8817_Traceguids
0x1400306e7  mov     [rsp+0F0h+var_D0], rax
0x1400306ec  mov     rcx, [rcx+40h]
0x1400306f0  lea     r8d, [r9-36h]
0x1400306f4  call    WPP_RECORDER_SF_d
0x1400306f9  mov     ebx, 0C0010015h
0x1400306fe  test    ebx, ebx
0x140030700  jz      short loc_140030765
0x140030702  jmp     short loc_14003074F
0x140030704  lea     rdi, WPP_RECORDER_INITIALIZED
0x14003070b  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140030712  jz      short loc_14003074A
0x140030714  mov     rcx, cs:WPP_GLOBAL_Control
0x14003071b  mov     r9d, 19Bh
0x140030721  mov     [rsp+0F0h+var_B8], 10h
0x140030729  mov     r8d, 3
0x14003072f  mov     [rsp+0F0h+var_C0], eax
0x140030733  mov     dl, 2
0x140030735  mov     eax, [rsi+10h]
0x140030738  mov     rcx, [rcx+40h]
0x14003073c  mov     [rsp+0F0h+var_C8], eax
0x140030740  mov     [rsp+0F0h+var_D0], r13
0x140030745  call    WPP_RECORDER_SF_Ddd
0x14003074a  mov     ebx, 0C0040003h
0x14003074f  mov     ecx, r14d
0x140030752  call    ?MbbUtilMbbToWwanStatus@@YAKW4_MBB_STATUS@@@Z; MbbUtilMbbToWwanStatus(_MBB_STATUS)
0x140030757  test    eax, eax
0x140030759  jz      short loc_140030765
0x14003075b  mov     ecx, r14d
0x14003075e  call    ?MbbUtilMbbToWwanStatus@@YAKW4_MBB_STATUS@@@Z; MbbUtilMbbToWwanStatus(_MBB_STATUS)
0x140030763  mov     ebx, eax
0x140030765  lea     rax, [rbp+4Fh+var_40]
0x140030769  mov     dword ptr [rbp+4Fh+var_40+4], ebx
0x14003076c  mov     [rbp+4Fh+var_B0.StatusBuffer], rax
0x140030770  mov     [rbp+4Fh+var_B0.StatusBufferSize], 18h
0x140030777  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14003077e  jz      short loc_1400307AE
0x140030780  mov     rcx, cs:WPP_GLOBAL_Control
0x140030787  mov     r9d, 19Ch
0x14003078d  mov     eax, [rsi+10h]
0x140030790  mov     r8d, 3
0x140030796  mov     [rsp+0F0h+var_C0], ebx
0x14003079a  mov     dl, 4
0x14003079c  mov     [rsp+0F0h+var_C8], eax
0x1400307a0  mov     rcx, [rcx+40h]
0x1400307a4  mov     [rsp+0F0h+var_D0], r13
0x1400307a9  call    WPP_RECORDER_SF_DD
0x1400307ae  mov     rdx, [rsi+68h]
0x1400307b2  test    rdx, rdx
0x1400307b5  jz      short loc_1400307DE
0x1400307b7  mov     rax, cs:WdfFunctions_01031
0x1400307be  mov     r8, cs:off_14005DF38
0x1400307c5  mov     rcx, cs:WdfDriverGlobals
0x1400307cc  mov     rax, [rax+650h]
0x1400307d3  call    _guard_dispatch_icall
0x1400307d8  add     rax, 18h
0x1400307dc  jmp     short loc_1400307EF
0x1400307de  mov     rax, [rsi+30h]
0x1400307e2  mov     rcx, [rax]
0x1400307e5  mov     rax, [rcx+478h]
0x1400307ec  mov     rax, [rax]
0x1400307ef  lea     rdx, [rbp+4Fh+var_B0]; struct _NDIS_STATUS_INDICATION *
0x1400307f3  mov     rcx, rax; struct _MINIPORT_INTERFACE_CONTEXT *
0x1400307f6  call    ?MbbUtilNdisMiniportIndicateStatusEx@@YAXPEAU_MINIPORT_INTERFACE_CONTEXT@@PEAU_NDIS_STATUS_INDICATION@@@Z; MbbUtilNdisMiniportIndicateStatusEx(_MINIPORT_INTERFACE_CONTEXT *,_NDIS_STATUS_INDICATION *)
0x1400307fb  xor     eax, eax
0x1400307fd  mov     rcx, [rbp+4Fh+var_28]
0x140030801  xor     rcx, rsp; StackCookie
0x140030804  call    __security_check_cookie
0x140030809  lea     r11, [rsp+0F0h+var_20]
0x140030811  mov     rbx, [r11+38h]
0x140030815  mov     rsi, [r11+48h]
0x140030819  mov     rsp, r11
0x14003081c  pop     r15
0x14003081e  pop     r14
0x140030820  pop     r13
0x140030822  pop     rdi
0x140030823  pop     rbp
0x140030824  retn
```
