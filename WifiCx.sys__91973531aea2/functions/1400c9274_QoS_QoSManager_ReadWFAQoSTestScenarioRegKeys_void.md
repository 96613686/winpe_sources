# QoS::QoSManager::ReadWFAQoSTestScenarioRegKeys(void)

- ea: `0x1400c9274`
- end: `0x1400c95e7`
- name: `?ReadWFAQoSTestScenarioRegKeys@QoSManager@QoS@@AEAAXXZ`
- size: `883`
- prototype: `void __fastcall(QoS::QoSManager *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140084068`

## callees

- `0x14000c778`
- `0x14000d054`
- `0x140032580`
- `0x1400c9274`
- `0x1400c9728`
- `0x1400ca8ec`
- `0x1400dc4c8`
- `0x1400dfd00`
- `0x1400e0100`

## string_xrefs

- `0x1400c94fe`: `5_4_1MSCSRemoveRequestTimeout`

## pseudocode

```c
void __fastcall QoS::QoSManager::ReadWFAQoSTestScenarioRegKeys(QoS::QoSManager *this)
{
  __int64 v2; // rdx
  int v3; // edx
  int v4; // r9d
  __int64 v5; // rax
  CAdapter *v6; // rcx
  int v7; // edx
  CAdapter *v8; // rcx
  int v9; // r8d
  unsigned int v10; // r15d
  int v11; // edx
  CAdapter *v12; // rcx
  unsigned int v13; // r15d
  int v14; // edx
  CAdapter *v15; // rcx
  unsigned int v16; // r15d
  int v17; // edx
  unsigned int v18; // r15d
  __int64 v19; // [rsp+28h] [rbp-D8h]
  unsigned int v20; // [rsp+28h] [rbp-D8h]
  unsigned int v21[4]; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t SourceString[264]; // [rsp+40h] [rbp-C0h] BYREF

  v21[0] = 0;
  memset(SourceString, 0, 0x208u);
  if ( (unsigned int)KmWlanStateSeparation_GetMutableRegistryKey(SourceString, v2, L"Software\\Microsoft\\Wlansvc", 0) )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return;
    v4 = 21;
    goto LABEL_4;
  }
  v5 = -1;
  do
    ++v5;
  while ( SourceString[v5] );
  if ( (unsigned int)RtlStringCchPrintfW(&SourceString[v5], 260 - v5, L"\\%s\\%s", L"Test", L"QoSWFATest") )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v4 = 22;
LABEL_4:
      LOBYTE(v3) = 2;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v3,
        1,
        v4,
        (__int64)WPP_0a0141c28d99397fe41f9ee1819414c9_Traceguids);
    }
  }
  else if ( (unsigned int)CAdapter::ReadRegDword(v6, SourceString, L"5_4_1Enable", v21) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v7) = 2;
      WPP_RECORDER_SF_S(
        WPP_GLOBAL_Control->DeviceExtension,
        v7,
        v9,
        24,
        (__int64)WPP_0a0141c28d99397fe41f9ee1819414c9_Traceguids,
        (__int64)SourceString);
    }
  }
  else
  {
    v10 = v21[0];
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v20 = v21[0];
      LOBYTE(v7) = 4;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v7,
        1,
        23,
        (__int64)WPP_0a0141c28d99397fe41f9ee1819414c9_Traceguids,
        v20);
    }
    *((_BYTE *)this + 16) = v10 != 0;
    if ( v10 )
    {
      if ( (unsigned int)CAdapter::ReadRegDword(v8, SourceString, L"5_4_1MSCSRequestTimeout", v21) )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LODWORD(v19) = *((_DWORD *)this + 5);
          LOBYTE(v11) = 4;
          WPP_RECORDER_SF_d(
            WPP_GLOBAL_Control->DeviceExtension,
            v11,
            1,
            26,
            (__int64)WPP_0a0141c28d99397fe41f9ee1819414c9_Traceguids,
            v19);
        }
      }
      else
      {
        v13 = v21[0];
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LODWORD(v19) = v21[0];
          LOBYTE(v11) = 4;
          WPP_RECORDER_SF_d(
            WPP_GLOBAL_Control->DeviceExtension,
            v11,
            1,
            25,
            (__int64)WPP_0a0141c28d99397fe41f9ee1819414c9_Traceguids,
            v19);
        }
        *((_DWORD *)this + 5) = v13;
      }
      if ( (unsigned int)CAdapter::ReadRegDword(v12, SourceString, L"5_4_1MSCSChangeRequestTimeout", v21) )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LODWORD(v19) = *((_DWORD *)this + 6);
          LOBYTE(v14) = 4;
          WPP_RECORDER_SF_d(
            WPP_GLOBAL_Control->DeviceExtension,
            v14,
            1,
            28,
            (__int64)WPP_0a0141c28d99397fe41f9ee1819414c9_Traceguids,
            v19);
        }
      }
      else
      {
        v16 = v21[0];
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LODWORD(v19) = v21[0];
          LOBYTE(v14) = 4;
          WPP_RECORDER_SF_d(
            WPP_GLOBAL_Control->DeviceExtension,
            v14,
            1,
            27,
            (__int64)WPP_0a0141c28d99397fe41f9ee1819414c9_Traceguids,
            v19);
        }
        *((_DWORD *)this + 6) = v16;
      }
      if ( (unsigned int)CAdapter::ReadRegDword(v15, SourceString, L"5_4_1MSCSRemoveRequestTimeout", v21) )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LODWORD(v19) = *((_DWORD *)this + 7);
          LOBYTE(v17) = 4;
          WPP_RECORDER_SF_d(
            WPP_GLOBAL_Control->DeviceExtension,
            v17,
            1,
            30,
            (__int64)WPP_0a0141c28d99397fe41f9ee1819414c9_Traceguids,
            v19);
        }
      }
      else
      {
        v18 = v21[0];
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LODWORD(v19) = v21[0];
          LOBYTE(v17) = 4;
          WPP_RECORDER_SF_d(
            WPP_GLOBAL_Control->DeviceExtension,
            v17,
            1,
            29,
            (__int64)WPP_0a0141c28d99397fe41f9ee1819414c9_Traceguids,
            v19);
        }
        *((_DWORD *)this + 7) = v18;
      }
    }
  }
}

```

## disassembly

```asm
0x1400c9274  mov     [rsp-8+arg_8], rbx
0x1400c9279  mov     [rsp-8+arg_10], rsi
0x1400c927e  push    rbp
0x1400c927f  push    rdi
0x1400c9280  push    r12
0x1400c9282  push    r14
0x1400c9284  push    r15
0x1400c9286  lea     rbp, [rsp-160h]
0x1400c928e  sub     rsp, 260h
0x1400c9295  mov     rax, cs:__security_cookie
0x1400c929c  xor     rax, rsp
0x1400c929f  mov     [rbp+180h+var_30], rax
0x1400c92a6  mov     r14, rcx
0x1400c92a9  xor     r12d, r12d
0x1400c92ac  lea     rcx, [rsp+280h+SourceString]; void *
0x1400c92b1  mov     [rsp+280h+var_250], r12d
0x1400c92b6  xor     edx, edx; Val
0x1400c92b8  mov     r8d, 208h; Size
0x1400c92be  call    memset
0x1400c92c3  xor     r9d, r9d
0x1400c92c6  lea     r8, aSoftwareMicros; "Software\\Microsoft\\Wlansvc"
0x1400c92cd  lea     rcx, [rsp+280h+SourceString]; SourceString
0x1400c92d2  call    KmWlanStateSeparation_GetMutableRegistryKey
0x1400c92d7  test    eax, eax
0x1400c92d9  jz      short loc_1400C931D
0x1400c92db  lea     rbx, WPP_RECORDER_INITIALIZED
0x1400c92e2  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1400c92e9  jz      loc_1400C95BB
0x1400c92ef  lea     r9d, [r12+15h]
0x1400c92f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c92fb  lea     rdi, WPP_0a0141c28d99397fe41f9ee1819414c9_Traceguids
0x1400c9302  mov     r8d, 1
0x1400c9308  mov     [rsp+280h+var_260], rdi
0x1400c930d  mov     dl, 2
0x1400c930f  mov     rcx, [rcx+40h]
0x1400c9313  call    WPP_RECORDER_SF_
0x1400c9318  jmp     loc_1400C95BB
0x1400c931d  lea     rcx, [rsp+280h+SourceString]
0x1400c9322  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400c9326  inc     rax
0x1400c9329  cmp     [rcx+rax*2], r12w
0x1400c932e  jnz     short loc_1400C9326
0x1400c9330  mov     edx, 104h
0x1400c9335  lea     rcx, [rsp+280h+SourceString]
0x1400c933a  sub     rdx, rax; unsigned __int64
0x1400c933d  lea     rcx, [rcx+rax*2]; unsigned __int16 *
0x1400c9341  lea     rax, aQoswfatest; "QoSWFATest"
0x1400c9348  lea     r9, aTest; "Test"
0x1400c934f  mov     [rsp+280h+var_260], rax
0x1400c9354  lea     r8, aSS; "\\%s\\%s"
0x1400c935b  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400c9360  test    eax, eax
0x1400c9362  jz      short loc_1400C9383
0x1400c9364  lea     rbx, WPP_RECORDER_INITIALIZED
0x1400c936b  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1400c9372  jz      loc_1400C95BB
0x1400c9378  mov     r9d, 16h
0x1400c937e  jmp     loc_1400C92F4
0x1400c9383  lea     r9, [rsp+280h+var_250]; unsigned int *
0x1400c9388  lea     r8, a541enable; "5_4_1Enable"
0x1400c938f  lea     rdx, [rsp+280h+SourceString]; unsigned __int16 *
0x1400c9394  call    ?ReadRegDword@CAdapter@@QEAAHPEAG0PEAK@Z; CAdapter::ReadRegDword(ushort *,ushort *,ulong *)
0x1400c9399  test    eax, eax
0x1400c939b  jnz     loc_1400C957D
0x1400c93a1  mov     r15d, [rsp+280h+var_250]
0x1400c93a6  lea     rbx, WPP_RECORDER_INITIALIZED
0x1400c93ad  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1400c93b4  lea     rdi, WPP_0a0141c28d99397fe41f9ee1819414c9_Traceguids
0x1400c93bb  lea     esi, [rax+1]
0x1400c93be  jz      short loc_1400C93E3
0x1400c93c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c93c7  lea     r9d, [rax+17h]
0x1400c93cb  mov     dword ptr [rsp+280h+var_258], r15d
0x1400c93d0  mov     r8d, esi
0x1400c93d3  mov     dl, 4
0x1400c93d5  mov     [rsp+280h+var_260], rdi
0x1400c93da  mov     rcx, [rcx+40h]
0x1400c93de  call    WPP_RECORDER_SF_d
0x1400c93e3  test    r15d, r15d
0x1400c93e6  setnz   al
0x1400c93e9  mov     [r14+10h], al
0x1400c93ed  test    al, al
0x1400c93ef  jz      loc_1400C95BB
0x1400c93f5  lea     r9, [rsp+280h+var_250]; unsigned int *
0x1400c93fa  lea     r8, a541mscsrequest; "5_4_1MSCSRequestTimeout"
0x1400c9401  lea     rdx, [rsp+280h+SourceString]; unsigned __int16 *
0x1400c9406  call    ?ReadRegDword@CAdapter@@QEAAHPEAG0PEAK@Z; CAdapter::ReadRegDword(ushort *,ushort *,ulong *)
0x1400c940b  test    eax, eax
0x1400c940d  jnz     short loc_1400C9446
0x1400c940f  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1400c9416  mov     r15d, [rsp+280h+var_250]
0x1400c941b  jz      short loc_1400C9440
0x1400c941d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c9424  lea     r9d, [rax+19h]
0x1400c9428  mov     dword ptr [rsp+280h+var_258], r15d
0x1400c942d  mov     r8d, esi
0x1400c9430  mov     dl, 4
0x1400c9432  mov     [rsp+280h+var_260], rdi
0x1400c9437  mov     rcx, [rcx+40h]
0x1400c943b  call    WPP_RECORDER_SF_d
0x1400c9440  mov     [r14+14h], r15d
0x1400c9444  jmp     short loc_1400C9477
0x1400c9446  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1400c944d  jz      short loc_1400C9477
0x1400c944f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c9456  mov     r9d, 1Ah
0x1400c945c  mov     eax, [r14+14h]
0x1400c9460  mov     r8d, esi
0x1400c9463  mov     dword ptr [rsp+280h+var_258], eax
0x1400c9467  mov     dl, 4
0x1400c9469  mov     [rsp+280h+var_260], rdi
0x1400c946e  mov     rcx, [rcx+40h]
0x1400c9472  call    WPP_RECORDER_SF_d
0x1400c9477  lea     r9, [rsp+280h+var_250]; unsigned int *
0x1400c947c  lea     r8, a541mscschanger; "5_4_1MSCSChangeRequestTimeout"
0x1400c9483  lea     rdx, [rsp+280h+SourceString]; unsigned __int16 *
0x1400c9488  call    ?ReadRegDword@CAdapter@@QEAAHPEAG0PEAK@Z; CAdapter::ReadRegDword(ushort *,ushort *,ulong *)
0x1400c948d  test    eax, eax
0x1400c948f  jnz     short loc_1400C94C8
0x1400c9491  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1400c9498  mov     r15d, [rsp+280h+var_250]
0x1400c949d  jz      short loc_1400C94C2
0x1400c949f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c94a6  lea     r9d, [rax+1Bh]
0x1400c94aa  mov     dword ptr [rsp+280h+var_258], r15d
0x1400c94af  mov     r8d, esi
0x1400c94b2  mov     dl, 4
0x1400c94b4  mov     [rsp+280h+var_260], rdi
0x1400c94b9  mov     rcx, [rcx+40h]
0x1400c94bd  call    WPP_RECORDER_SF_d
0x1400c94c2  mov     [r14+18h], r15d
0x1400c94c6  jmp     short loc_1400C94F9
0x1400c94c8  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1400c94cf  jz      short loc_1400C94F9
0x1400c94d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c94d8  mov     r9d, 1Ch
0x1400c94de  mov     eax, [r14+18h]
0x1400c94e2  mov     r8d, esi
0x1400c94e5  mov     dword ptr [rsp+280h+var_258], eax
0x1400c94e9  mov     dl, 4
0x1400c94eb  mov     [rsp+280h+var_260], rdi
0x1400c94f0  mov     rcx, [rcx+40h]
0x1400c94f4  call    WPP_RECORDER_SF_d
0x1400c94f9  lea     r9, [rsp+280h+var_250]; unsigned int *
0x1400c94fe  lea     r8, a541mscsremover; "5_4_1MSCSRemoveRequestTimeout"
0x1400c9505  lea     rdx, [rsp+280h+SourceString]; unsigned __int16 *
0x1400c950a  call    ?ReadRegDword@CAdapter@@QEAAHPEAG0PEAK@Z; CAdapter::ReadRegDword(ushort *,ushort *,ulong *)
0x1400c950f  test    eax, eax
0x1400c9511  jnz     short loc_1400C954A
0x1400c9513  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1400c951a  mov     r15d, [rsp+280h+var_250]
0x1400c951f  jz      short loc_1400C9544
0x1400c9521  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c9528  lea     r9d, [rax+1Dh]
0x1400c952c  mov     dword ptr [rsp+280h+var_258], r15d
0x1400c9531  mov     r8d, esi
0x1400c9534  mov     dl, 4
0x1400c9536  mov     [rsp+280h+var_260], rdi
0x1400c953b  mov     rcx, [rcx+40h]
0x1400c953f  call    WPP_RECORDER_SF_d
0x1400c9544  mov     [r14+1Ch], r15d
0x1400c9548  jmp     short loc_1400C95BB
0x1400c954a  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1400c9551  jz      short loc_1400C95BB
0x1400c9553  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c955a  mov     r9d, 1Eh
0x1400c9560  mov     eax, [r14+1Ch]
0x1400c9564  mov     r8d, esi
0x1400c9567  mov     dword ptr [rsp+280h+var_258], eax
0x1400c956b  mov     dl, 4
0x1400c956d  mov     [rsp+280h+var_260], rdi
0x1400c9572  mov     rcx, [rcx+40h]
0x1400c9576  call    WPP_RECORDER_SF_d
0x1400c957b  jmp     short loc_1400C95BB
0x1400c957d  lea     rbx, WPP_RECORDER_INITIALIZED
0x1400c9584  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1400c958b  jz      short loc_1400C95BB
0x1400c958d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c9594  lea     rax, [rsp+280h+SourceString]
0x1400c9599  mov     [rsp+280h+var_258], rax
0x1400c959e  lea     rdi, WPP_0a0141c28d99397fe41f9ee1819414c9_Traceguids
0x1400c95a5  mov     r9d, 18h
0x1400c95ab  mov     [rsp+280h+var_260], rdi
0x1400c95b0  mov     dl, 2
0x1400c95b2  mov     rcx, [rcx+40h]
0x1400c95b6  call    WPP_RECORDER_SF_S
0x1400c95bb  mov     rcx, [rbp+180h+var_30]
0x1400c95c2  xor     rcx, rsp; StackCookie
0x1400c95c5  call    __security_check_cookie
0x1400c95ca  lea     r11, [rsp+280h+var_20]
0x1400c95d2  mov     rbx, [r11+38h]
0x1400c95d6  mov     rsi, [r11+40h]
0x1400c95da  mov     rsp, r11
0x1400c95dd  pop     r15
0x1400c95df  pop     r14
0x1400c95e1  pop     r12
0x1400c95e3  pop     rdi
0x1400c95e4  pop     rbp
0x1400c95e5  retn
```
