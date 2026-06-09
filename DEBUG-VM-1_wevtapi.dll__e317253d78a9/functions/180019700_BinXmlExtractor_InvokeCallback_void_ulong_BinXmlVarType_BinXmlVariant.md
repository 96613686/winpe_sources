# BinXmlExtractor::InvokeCallback(void *,ulong,BinXmlVarType,BinXmlVariant &)

- ea: `0x180019700`
- end: `0x180019926`
- name: `?InvokeCallback@BinXmlExtractor@@AEAAXPEAXKW4BinXmlVarType@@AEAUBinXmlVariant@@@Z`
- size: `550`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180007ae4`

## callees

- `0x18000b6a0`
- `0x18000c404`
- `0x18000f378`
- `0x180019700`
- `0x18001992c`
- `0x180023548`
- `0x180038fb4`
- `0x180038fcc`
- `0x18003c010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001980a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001980a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019818`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019818`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
int __fastcall BinXmlExtractor::InvokeCallback(__int64 a1, __int64 a2, unsigned int a3, unsigned int a4, __int64 a5)
{
  _BYTE *v9; // rax
  int v10; // eax
  bool v11; // zf
  void (__fastcall *v12)(__int64, _QWORD, PSID *); // rax
  PSID *p_Sid; // r8
  void *v14; // rbx
  HANDLE ProcessHeap; // rax
  PSID Sid; // [rsp+20h] [rbp-51h] BYREF
  int v18; // [rsp+28h] [rbp-49h]
  int v19; // [rsp+2Ch] [rbp-45h]
  const wchar_t *v20; // [rsp+30h] [rbp-41h] BYREF
  __int64 v21; // [rsp+38h] [rbp-39h]
  void *lpMem; // [rsp+40h] [rbp-31h] BYREF
  __int64 v23; // [rsp+48h] [rbp-29h]
  _BYTE v24[16]; // [rsp+50h] [rbp-21h] BYREF
  __int128 pExceptionObject; // [rsp+60h] [rbp-11h] BYREF
  __int64 v26; // [rsp+70h] [rbp-1h]
  int v27; // [rsp+78h] [rbp+7h]
  int v28; // [rsp+7Ch] [rbp+Bh]
  int v29; // [rsp+80h] [rbp+Fh]

  if ( a4 && (v10 = *(_DWORD *)(a5 + 12), a4 != v10) && v10 )
  {
    if ( v10 != 1 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_fa1fa1ee6f1f3d0a979a6a95d8de375c_Traceguids, 50);
      }
      pExceptionObject = 0;
      v26 = 0;
      v27 = 50;
      v28 = -1;
      v29 = 391;
      throw (EvtException *)&pExceptionObject;
    }
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&lpMem);
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(
                             &lpMem,
                             *(unsigned int *)(a5 + 8)) )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_fa1fa1ee6f1f3d0a979a6a95d8de375c_Traceguids, 14);
      }
      pExceptionObject = 0;
      v26 = 0;
      v27 = 14;
      v28 = -1;
      v29 = 410;
      throw (EvtException *)&pExceptionObject;
    }
    memcpy_0(lpMem, *(const void **)a5, 2LL * *(unsigned int *)(a5 + 8));
    if ( *((_WORD *)lpMem + ((v23 - (__int64)lpMem) >> 1)) )
      __int2c();
    Sid = 0;
    v18 = -1;
    v19 = 0;
    v20 = (const wchar_t *)lpMem;
    v21 = (v23 - (__int64)lpMem) >> 1;
    v11 = BinXmlVariantHolder::InitFromString(&Sid, a4, &v20) == 0;
    v12 = *(void (__fastcall **)(__int64, _QWORD, PSID *))(a1 + 136);
    if ( v11 )
    {
      v20 = 0;
      v21 = 0xFFFFFFFFLL;
      p_Sid = (PSID *)&v20;
    }
    else
    {
      p_Sid = &Sid;
    }
    v12(a2, a3, p_Sid);
    BinXmlVariantHolder::Clear((BinXmlVariantHolder *)&Sid);
    v9 = v24;
    v14 = lpMem;
    if ( lpMem != v24 )
    {
      ProcessHeap = GetProcessHeap();
      LODWORD(v9) = HeapFree(ProcessHeap, 0, v14);
    }
  }
  else
  {
    LODWORD(v9) = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(a1 + 136))(a2, a3, a5);
  }
  return (int)v9;
}

```

## disassembly

```asm
0x180019700  push    rbp
0x180019702  push    rbx
0x180019703  push    rsi
0x180019704  push    rdi
0x180019705  push    r14
0x180019707  push    r15
0x180019709  lea     rbp, [rsp-27h]
0x18001970e  sub     rsp, 98h
0x180019715  mov     ebx, r9d
0x180019718  mov     r14d, r8d
0x18001971b  mov     r15, rdx
0x18001971e  mov     rsi, rcx
0x180019721  mov     rdi, [rbp+4Fh+arg_20]
0x180019725  test    r9d, r9d
0x180019728  jnz     short loc_18001974F
0x18001972a  mov     r8, rdi
0x18001972d  mov     edx, r14d
0x180019730  mov     rcx, r15
0x180019733  mov     rax, [rsi+88h]
0x18001973a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001973f  add     rsp, 98h
0x180019746  pop     r15
0x180019748  pop     r14
0x18001974a  pop     rdi
0x18001974b  pop     rsi
0x18001974c  pop     rbx
0x18001974d  pop     rbp
0x18001974e  retn
0x18001974f  mov     eax, [rdi+0Ch]
0x180019752  cmp     ebx, eax
0x180019754  jz      short loc_18001972A
0x180019756  test    eax, eax
0x180019758  jz      short loc_18001972A
0x18001975a  cmp     eax, 1
0x18001975d  jnz     loc_180019842
0x180019763  lea     rcx, [rbp+4Fh+lpMem]
0x180019767  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18001976c  nop
0x18001976d  mov     edx, [rdi+8]
0x180019770  lea     rcx, [rbp+4Fh+lpMem]
0x180019774  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x180019779  test    al, al
0x18001977b  jz      loc_1800198B0
0x180019781  mov     r8d, [rdi+8]
0x180019785  add     r8, r8; Size
0x180019788  mov     rdx, [rdi]; Src
0x18001978b  mov     rcx, [rbp+4Fh+lpMem]; void *
0x18001978f  call    memcpy_0
0x180019794  mov     rax, [rbp+4Fh+var_78]
0x180019798  mov     rcx, [rbp+4Fh+lpMem]
0x18001979c  sub     rax, rcx
0x18001979f  sar     rax, 1
0x1800197a2  cmp     word ptr [rcx+rax*2], 0
0x1800197a7  jnz     loc_18001991E
0x1800197ad  xor     edi, edi
0x1800197af  mov     [rbp+4Fh+Sid], rdi
0x1800197b3  mov     [rbp+4Fh+var_98], 0FFFFFFFFh
0x1800197ba  mov     [rbp+4Fh+var_94], edi
0x1800197bd  mov     [rbp+4Fh+var_90], rcx
0x1800197c1  mov     [rbp+4Fh+var_88], rax
0x1800197c5  lea     r8, [rbp+4Fh+var_90]
0x1800197c9  mov     edx, ebx
0x1800197cb  lea     rcx, [rbp+4Fh+Sid]; Sid
0x1800197cf  call    ?InitFromString@BinXmlVariantHolder@@QEAA_NW4BinXmlVarType@@V?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@@Z; BinXmlVariantHolder::InitFromString(BinXmlVarType,tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>)
0x1800197d4  mov     edx, r14d
0x1800197d7  mov     rcx, r15
0x1800197da  test    al, al
0x1800197dc  mov     rax, [rsi+88h]
0x1800197e3  jz      short loc_18001982E
0x1800197e5  lea     r8, [rbp+4Fh+Sid]
0x1800197e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800197ee  nop
0x1800197ef  lea     rcx, [rbp+4Fh+Sid]; this
0x1800197f3  call    ?Clear@BinXmlVariantHolder@@QEAAXXZ; BinXmlVariantHolder::Clear(void)
0x1800197f8  nop
0x1800197f9  lea     rax, [rbp+4Fh+var_70]
0x1800197fd  mov     rbx, [rbp+4Fh+lpMem]
0x180019801  cmp     rbx, rax
0x180019804  jz      loc_18001973F
0x18001980a  call    cs:__imp_GetProcessHeap
0x180019810  mov     rcx, rax; hHeap
0x180019813  mov     r8, rbx; lpMem
0x180019816  xor     edx, edx; dwFlags
0x180019818  call    cs:__imp_HeapFree
0x18001981e  add     rsp, 98h
0x180019825  pop     r15
0x180019827  pop     r14
0x180019829  pop     rdi
0x18001982a  pop     rsi
0x18001982b  pop     rbx
0x18001982c  pop     rbp
0x18001982d  retn
0x18001982e  mov     [rbp+4Fh+var_90], rdi
0x180019832  mov     dword ptr [rbp+4Fh+var_88], 0FFFFFFFFh
0x180019839  mov     dword ptr [rbp+4Fh+var_88+4], edi
0x18001983c  lea     r8, [rbp+4Fh+var_90]
0x180019840  jmp     short loc_1800197E9
0x180019842  lea     rax, WPP_GLOBAL_Control
0x180019849  mov     rcx, cs:WPP_GLOBAL_Control
0x180019850  cmp     rcx, rax
0x180019853  jz      short loc_18001987C
0x180019855  test    byte ptr [rcx+1Ch], 2
0x180019859  jz      short loc_18001987C
0x18001985b  cmp     byte ptr [rcx+19h], 2
0x18001985f  jb      short loc_18001987C
0x180019861  mov     edx, 1Fh
0x180019866  mov     r9d, 32h ; '2'
0x18001986c  lea     r8, WPP_fa1fa1ee6f1f3d0a979a6a95d8de375c_Traceguids
0x180019873  mov     rcx, [rcx+10h]
0x180019877  call    WPP_SF_D
0x18001987c  xorps   xmm0, xmm0
0x18001987f  movdqu  [rbp+4Fh+pExceptionObject], xmm0
0x180019884  xor     edi, edi
0x180019886  mov     [rbp+4Fh+var_50], rdi
0x18001988a  mov     [rbp+4Fh+var_48], 32h ; '2'
0x180019891  mov     [rbp+4Fh+var_44], 0FFFFFFFFh
0x180019898  mov     [rbp+4Fh+var_40], 187h
0x18001989f  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800198a6  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x1800198aa  call    _CxxThrowException_0
0x1800198b0  lea     rax, WPP_GLOBAL_Control
0x1800198b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800198be  cmp     rcx, rax
0x1800198c1  jz      short loc_1800198EA
0x1800198c3  test    byte ptr [rcx+1Ch], 2
0x1800198c7  jz      short loc_1800198EA
0x1800198c9  cmp     byte ptr [rcx+19h], 2
0x1800198cd  jb      short loc_1800198EA
0x1800198cf  mov     edx, 20h ; ' '
0x1800198d4  mov     r9d, 0Eh
0x1800198da  lea     r8, WPP_fa1fa1ee6f1f3d0a979a6a95d8de375c_Traceguids
0x1800198e1  mov     rcx, [rcx+10h]
0x1800198e5  call    WPP_SF_D
0x1800198ea  xorps   xmm0, xmm0
0x1800198ed  movdqu  [rbp+4Fh+pExceptionObject], xmm0
0x1800198f2  xor     edi, edi
0x1800198f4  mov     [rbp+4Fh+var_50], rdi
0x1800198f8  mov     [rbp+4Fh+var_48], 0Eh
0x1800198ff  mov     [rbp+4Fh+var_44], 0FFFFFFFFh
0x180019906  mov     [rbp+4Fh+var_40], 19Ah
0x18001990d  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180019914  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x180019918  call    _CxxThrowException_0
0x18001991e  int     2Ch; Windows NT - assertion failure
0x180019920  jmp     loc_1800197AD
```
