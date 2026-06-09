# Microsoft::DiagnosticsHub::GraphPoints::CreateTimeGraphPoints(Microsoft::DiagnosticsHub::GraphPoints::TimeDataPoints const &,Microsoft::DiagnosticsHub::GraphPoints::CurrentTimeState &,uint &,ATL::CComHeapPtr<CollectorGraphPoint> &)

- ea: `0x1800293a8`
- end: `0x1800296c4`
- name: `?CreateTimeGraphPoints@GraphPoints@DiagnosticsHub@Microsoft@@YAJAEBUTimeDataPoints@123@AEAUCurrentTimeState@123@AEAIAEAV?$CComHeapPtr@UCollectorGraphPoint@@@ATL@@@Z`
- size: `796`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180012408`

## callees

- `0x1800293a8`
- `0x18003d864`
- `0x180049b50`
- `0x18004b640`

## import_xrefs

- `VCRUNTIME140!memset` at `0x18002941f`
- `VCRUNTIME140!memset` at `0x18002941f`
- `ole32!CoTaskMemRealloc` at `0x180029665`
- `ole32!CoTaskMemRealloc` at `0x180029665`
- `ole32!CoTaskMemAlloc` at `0x180029405`
- `ole32!CoTaskMemAlloc` at `0x180029405`
- `MSVCP140!?_Xbad_function_call@std@@YAXXZ` at `0x18002968f`
- `MSVCP140!?_Xbad_function_call@std@@YAXXZ` at `0x18002968f`

## pseudocode

```c
__int64 __fastcall Microsoft::DiagnosticsHub::GraphPoints::CreateTimeGraphPoints(
        __int64 *a1,
        char *a2,
        unsigned int *a3,
        LPVOID *a4)
{
  unsigned __int64 v7; // rax
  size_t v8; // rbx
  void *v9; // rax
  unsigned int v10; // r13d
  unsigned int v11; // ebp
  char v12; // r9
  __int64 v13; // r10
  __int64 v14; // r11
  char v15; // r12
  __int64 *v16; // rbx
  double v17; // xmm6_8
  __int64 v18; // r8
  __int64 v19; // rax
  int v20; // edx
  unsigned __int64 v21; // rdi
  char v22; // si
  int v23; // eax
  const unsigned __int16 *v24; // r8
  bool v25; // zf
  __int64 v26; // rcx
  char v27; // al
  __int64 v28; // rcx
  double v29; // xmm0_8
  unsigned int v30; // ebx
  __int64 v31; // rdx
  unsigned __int64 v32; // rcx
  LPVOID v33; // rax
  __int64 v35; // [rsp+20h] [rbp-B8h]
  bool v36; // [rsp+30h] [rbp-A8h]
  __int64 v37; // [rsp+38h] [rbp-A0h]
  __int64 v38; // [rsp+40h] [rbp-98h]
  unsigned int v39; // [rsp+48h] [rbp-90h]
  unsigned __int64 v40; // [rsp+50h] [rbp-88h]
  unsigned __int64 v43; // [rsp+68h] [rbp-70h] BYREF

  v39 = *((_DWORD *)a1 + 6) + 1 + *(_DWORD *)a1[4];
  if ( v39 )
  {
    if ( 0xFFFFFFFFFFFFFFFFuLL / v39 < 0x20 )
      return 2147942414LL;
    v7 = 32LL * v39;
    v8 = v7;
    if ( v7 > 0x7FFFFFFF )
    {
      v9 = 0;
      goto LABEL_4;
    }
  }
  else
  {
    LODWORD(v7) = 0;
    v8 = 0;
  }
  v9 = CoTaskMemAlloc((unsigned int)v7);
LABEL_4:
  *a4 = v9;
  if ( !v9 )
    return 2147942414LL;
  memset(v9, 0, v8);
  v10 = 0;
  v11 = 0;
  v12 = a2[1];
  v13 = *((_QWORD *)_logger + 8);
  v14 = *((_QWORD *)_logger + 7);
  v15 = *a2;
  v16 = *(__int64 **)a1[2];
  v17 = DOUBLE_NaN;
  v37 = v13;
  v38 = v14;
  v40 = *a1;
  v36 = v12;
  while ( v16 != (__int64 *)a1[2] )
  {
    v18 = a1[4];
    if ( v11 >= *(_DWORD *)v18 || *(_QWORD *)(*(_QWORD *)(v18 + 8) + 16LL * v11) >= (unsigned __int64)v16[2] )
    {
      v21 = v16[2];
      v22 = *((_BYTE *)v16 + 24);
      v16 = (__int64 *)*v16;
      if ( !v12 )
      {
        if ( v14 == v13 )
          goto LABEL_24;
        v23 = 0;
        v24 = L"DebugEvent,%llu,%d";
        v25 = v22 == 0;
LABEL_23:
        LOBYTE(v23) = !v25;
        LODWORD(v35) = v23;
        DiagHubCommon::LogStream::Write(
          (DiagHubCommon::LogStream *)((char *)_logger + 56),
          L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\GraphPointGenerators.cpp",
          v24,
          v21,
          v35);
LABEL_24:
        v26 = a1[12];
        v43 = v21;
        if ( !v26 )
        {
          std::_Xbad_function_call();
          __debugbreak();
        }
        v27 = (*(__int64 (__fastcall **)(__int64, unsigned __int64 *))(*(_QWORD *)v26 + 16LL))(v26, &v43);
        v12 = v36;
        v13 = v37;
        v14 = v38;
        if ( v27 )
        {
          v15 = 1;
        }
        else
        {
          v15 = v22;
          if ( v21 >= v40 )
          {
            v28 = 32LL * v10;
            v40 = v21;
            *(_QWORD *)((char *)*a4 + v28) = v21;
            if ( v22 )
              v29 = DOUBLE_NaN;
            else
              v29 = 0.0;
            ++v10;
            *(double *)((char *)*a4 + v28 + 8) = v29;
          }
        }
      }
    }
    else
    {
LABEL_14:
      v19 = *(_QWORD *)(v18 + 8);
      v20 = *(_DWORD *)(v19 + 16LL * v11 + 8);
      v21 = *(_QWORD *)(v19 + 16LL * v11);
      v22 = v20 != 0;
      if ( v12 != (v20 != 0) )
      {
        ++v11;
        v36 = v20 != 0;
        if ( v14 == v13 )
          goto LABEL_24;
        v23 = 0;
        v24 = L"DebugOverheadEvent,%llu,%d";
        v25 = v20 == 0;
        goto LABEL_23;
      }
      if ( v14 != v13 )
      {
        LODWORD(v35) = v20 != 0;
        DiagHubCommon::LogStream::Write(
          (DiagHubCommon::LogStream *)((char *)_logger + 112),
          L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\GraphPointGenerators.cpp",
          L"Dropping DebugOverheadEvent,%llu,%d",
          v21,
          v35);
        v12 = v36;
        v13 = v37;
        v14 = v38;
      }
      ++v11;
    }
  }
  if ( v11 < *(_DWORD *)a1[4] )
  {
    v18 = a1[4];
    goto LABEL_14;
  }
  if ( !v15 )
    v17 = 0.0;
  v30 = v10 + 1;
  v31 = 32LL * v10;
  *(double *)((char *)*a4 + v31 + 8) = v17;
  *(_QWORD *)((char *)*a4 + v31) = a1[1];
  if ( v10 + 1 == v39 )
  {
LABEL_41:
    *a3 = v30;
    *a2 = v15;
    a2[1] = v12;
    return 0;
  }
  else
  {
    if ( v10 == -1 )
    {
      LODWORD(v32) = 0;
      goto LABEL_39;
    }
    if ( 0xFFFFFFFFFFFFFFFFuLL / v30 >= 0x20 )
    {
      v32 = 32LL * v30;
      if ( v32 <= 0x7FFFFFFF )
      {
LABEL_39:
        v33 = CoTaskMemRealloc(*a4, (unsigned int)v32);
        if ( v33 )
        {
          v12 = v36;
          *a4 = v33;
          goto LABEL_41;
        }
      }
    }
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x1800293a8  mov     rax, rsp
0x1800293ab  push    rbx
0x1800293ac  push    rbp
0x1800293ad  push    rsi
0x1800293ae  push    rdi
0x1800293af  push    r12
0x1800293b1  push    r13
0x1800293b3  push    r14
0x1800293b5  push    r15
0x1800293b7  sub     rsp, 98h
0x1800293be  movaps  xmmword ptr [rax-58h], xmm6
0x1800293c2  mov     rax, cs:__security_cookie
0x1800293c9  xor     rax, rsp
0x1800293cc  mov     [rsp+0D8h+var_68], rax
0x1800293d1  mov     rax, [rcx+20h]
0x1800293d5  mov     rdi, rdx
0x1800293d8  mov     [rsp+0D8h+var_78], rdx
0x1800293dd  mov     r14, r9
0x1800293e0  mov     edx, [rcx+18h]
0x1800293e3  mov     r15, rcx
0x1800293e6  inc     edx
0x1800293e8  mov     [rsp+0D8h+var_80], r8
0x1800293ed  mov     eax, [rax]
0x1800293ef  add     eax, edx
0x1800293f1  mov     [rsp+0D8h+var_90], eax
0x1800293f5  mov     ebx, eax
0x1800293f7  jnz     loc_18002947D
0x1800293fd  xor     eax, eax
0x1800293ff  shl     rbx, 5
0x180029403  mov     ecx, eax; cb
0x180029405  call    cs:__imp_CoTaskMemAlloc
0x18002940b  mov     [r14], rax
0x18002940e  test    rax, rax
0x180029411  jz      loc_180029696
0x180029417  mov     r8, rbx; Size
0x18002941a  xor     edx, edx; Val
0x18002941c  mov     rcx, rax; void *
0x18002941f  call    cs:__imp_memset
0x180029425  mov     rax, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18002942c  xor     r13d, r13d
0x18002942f  mov     rbx, [r15+10h]
0x180029433  xor     ebp, ebp
0x180029435  mov     rdx, [r15]
0x180029438  mov     r9b, [rdi+1]
0x18002943c  mov     r10, [rax+40h]
0x180029440  mov     r11, [rax+38h]
0x180029444  mov     r12b, [rdi]
0x180029447  mov     rbx, [rbx]
0x18002944a  movsd   xmm6, cs:__real@7ff8000000000000
0x180029452  mov     [rsp+0D8h+var_A0], r10
0x180029457  mov     [rsp+0D8h+var_98], r11
0x18002945c  mov     [rsp+0D8h+var_88], rdx
0x180029461  mov     [rsp+0D8h+var_A8], r9b
0x180029466  cmp     rbx, [r15+10h]
0x18002946a  jnz     short loc_1800294AD
0x18002946c  mov     rax, [r15+20h]
0x180029470  cmp     ebp, [rax]
0x180029472  jnb     loc_18002960D
0x180029478  mov     r8, rax
0x18002947b  jmp     short loc_1800294CD
0x18002947d  xor     edx, edx
0x18002947f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180029483  div     rbx
0x180029486  cmp     rax, 20h ; ' '
0x18002948a  jb      loc_180029696
0x180029490  mov     rax, rbx
0x180029493  shl     rax, 5
0x180029497  mov     rbx, rax
0x18002949a  cmp     rax, 7FFFFFFFh
0x1800294a0  jbe     loc_180029403
0x1800294a6  xor     eax, eax
0x1800294a8  jmp     loc_18002940B
0x1800294ad  mov     r8, [r15+20h]
0x1800294b1  cmp     ebp, [r8]
0x1800294b4  jnb     loc_180029549
0x1800294ba  mov     rcx, [r8+8]
0x1800294be  mov     rax, [rbx+10h]
0x1800294c2  mov     edx, ebp
0x1800294c4  add     rdx, rdx
0x1800294c7  cmp     [rcx+rdx*8], rax
0x1800294cb  jnb     short loc_180029549
0x1800294cd  mov     rax, [r8+8]
0x1800294d1  mov     ecx, ebp
0x1800294d3  add     rcx, rcx
0x1800294d6  mov     edx, [rax+rcx*8+8]
0x1800294da  test    edx, edx
0x1800294dc  mov     rdi, [rax+rcx*8]
0x1800294e0  setnz   sil
0x1800294e4  cmp     r9b, sil
0x1800294e7  jnz     short loc_180029530
0x1800294e9  cmp     r11, r10
0x1800294ec  jz      short loc_180029529
0x1800294ee  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x1800294f5  lea     r8, aDroppingDebugo; "Dropping DebugOverheadEvent,%llu,%d"
0x1800294fc  xor     eax, eax
0x1800294fe  mov     r9, rdi
0x180029501  test    edx, edx
0x180029503  lea     rdx, aDAWork1SSource_4; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18002950a  setnz   al
0x18002950d  add     rcx, 70h ; 'p'; this
0x180029511  mov     [rsp+0D8h+var_B8], eax
0x180029515  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18002951a  mov     r9b, [rsp+0D8h+var_A8]
0x18002951f  mov     r10, [rsp+0D8h+var_A0]
0x180029524  mov     r11, [rsp+0D8h+var_98]
0x180029529  inc     ebp
0x18002952b  jmp     loc_180029466
0x180029530  inc     ebp
0x180029532  mov     [rsp+0D8h+var_A8], sil
0x180029537  cmp     r11, r10
0x18002953a  jz      short loc_18002958F
0x18002953c  xor     eax, eax
0x18002953e  lea     r8, aDebugoverheade; "DebugOverheadEvent,%llu,%d"
0x180029545  test    edx, edx
0x180029547  jmp     short loc_18002956E
0x180029549  mov     rdi, [rbx+10h]
0x18002954d  mov     sil, [rbx+18h]
0x180029551  mov     rbx, [rbx]
0x180029554  test    r9b, r9b
0x180029557  jnz     loc_180029466
0x18002955d  cmp     r11, r10
0x180029560  jz      short loc_18002958F
0x180029562  xor     eax, eax
0x180029564  lea     r8, aDebugeventLluD; "DebugEvent,%llu,%d"
0x18002956b  test    sil, sil
0x18002956e  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x180029575  lea     rdx, aDAWork1SSource_4; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18002957c  setnz   al
0x18002957f  mov     r9, rdi
0x180029582  add     rcx, 38h ; '8'; this
0x180029586  mov     [rsp+0D8h+var_B8], eax
0x18002958a  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18002958f  mov     rcx, [r15+60h]
0x180029593  mov     [rsp+0D8h+var_70], rdi
0x180029598  test    rcx, rcx
0x18002959b  jz      loc_18002968F
0x1800295a1  mov     rax, [rcx]
0x1800295a4  lea     rdx, [rsp+0D8h+var_70]
0x1800295a9  mov     rax, [rax+10h]
0x1800295ad  call    cs:__guard_dispatch_icall_fptr
0x1800295b3  mov     r9b, [rsp+0D8h+var_A8]
0x1800295b8  mov     r10, [rsp+0D8h+var_A0]
0x1800295bd  mov     r11, [rsp+0D8h+var_98]
0x1800295c2  test    al, al
0x1800295c4  jz      short loc_1800295CE
0x1800295c6  mov     r12b, 1
0x1800295c9  jmp     loc_180029466
0x1800295ce  mov     r12b, sil
0x1800295d1  cmp     rdi, [rsp+0D8h+var_88]
0x1800295d6  jb      loc_180029466
0x1800295dc  mov     rax, [r14]
0x1800295df  mov     ecx, r13d
0x1800295e2  shl     rcx, 5
0x1800295e6  mov     [rsp+0D8h+var_88], rdi
0x1800295eb  mov     [rcx+rax], rdi
0x1800295ef  test    sil, sil
0x1800295f2  jz      short loc_1800295F9
0x1800295f4  movaps  xmm0, xmm6
0x1800295f7  jmp     short loc_1800295FC
0x1800295f9  xorps   xmm0, xmm0
0x1800295fc  mov     rax, [r14]
0x1800295ff  inc     r13d
0x180029602  movsd   qword ptr [rax+rcx+8], xmm0
0x180029608  jmp     loc_180029466
0x18002960d  test    r12b, r12b
0x180029610  jnz     short loc_180029615
0x180029612  xorps   xmm6, xmm6
0x180029615  mov     rax, [r14]
0x180029618  lea     ebx, [r13+1]
0x18002961c  mov     edx, r13d
0x18002961f  shl     rdx, 5
0x180029623  movsd   qword ptr [rdx+rax+8], xmm6
0x180029629  mov     rcx, [r14]
0x18002962c  mov     rax, [r15+8]
0x180029630  mov     [rdx+rcx], rax
0x180029634  cmp     ebx, [rsp+0D8h+var_90]
0x180029638  jz      short loc_180029678
0x18002963a  test    ebx, ebx
0x18002963c  jnz     short loc_180029642
0x18002963e  xor     ecx, ecx
0x180029640  jmp     short loc_180029660
0x180029642  xor     edx, edx
0x180029644  mov     ecx, ebx
0x180029646  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002964a  div     rcx
0x18002964d  cmp     rax, 20h ; ' '
0x180029651  jb      short loc_180029696
0x180029653  shl     rcx, 5
0x180029657  cmp     rcx, 7FFFFFFFh
0x18002965e  ja      short loc_180029696
0x180029660  mov     edx, ecx; cb
0x180029662  mov     rcx, [r14]; pv
0x180029665  call    cs:__imp_CoTaskMemRealloc
0x18002966b  test    rax, rax
0x18002966e  jz      short loc_180029696
0x180029670  mov     r9b, [rsp+0D8h+var_A8]
0x180029675  mov     [r14], rax
0x180029678  mov     rax, [rsp+0D8h+var_80]
0x18002967d  mov     [rax], ebx
0x18002967f  mov     rax, [rsp+0D8h+var_78]
0x180029684  mov     [rax], r12b
0x180029687  mov     [rax+1], r9b
0x18002968b  xor     eax, eax
0x18002968d  jmp     short loc_18002969B
0x18002968f  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x180029695  int     3; Trap to Debugger
0x180029696  mov     eax, 8007000Eh
0x18002969b  mov     rcx, [rsp+0D8h+var_68]
0x1800296a0  xor     rcx, rsp; StackCookie
0x1800296a3  call    __security_check_cookie
0x1800296a8  movaps  xmm6, [rsp+0D8h+var_58]
0x1800296b0  add     rsp, 98h
0x1800296b7  pop     r15
0x1800296b9  pop     r14
0x1800296bb  pop     r13
0x1800296bd  pop     r12
0x1800296bf  pop     rdi
0x1800296c0  pop     rsi
0x1800296c1  pop     rbp
0x1800296c2  pop     rbx
0x1800296c3  retn
```
