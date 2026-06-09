# HandleIsConnected(ICloudAPContext *,void *,void *,int *)

- ea: `0x1800146e4`
- end: `0x1800148b6`
- name: `?HandleIsConnected@@YAJPEAVICloudAPContext@@PEAX1PEAH@Z`
- size: `466`
- prototype: `__int64 __fastcall(struct ICloudAPContext *, void *, void *, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180009ec0`

## callees

- `0x180008440`
- `0x18000baac`
- `0x18000d91c`
- `0x180010064`
- `0x1800146e4`
- `0x1800267c0`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800147be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800147c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800147d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800147be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800147c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800147d0`

## string_xrefs

- `0x18001477f`: `onecoreuap\ds\ext\live\identity\cloudapplugin\logon.cpp`
- `0x180014850`: `onecoreuap\ds\ext\live\identity\cloudapplugin\logon.cpp`

## pseudocode

```c
__int64 __fastcall HandleIsConnected(struct ICloudAPContext *a1, void *a2, void *a3, int *a4)
{
  __int64 v6; // rbx
  __int64 v7; // rsi
  __int64 v8; // rbx
  __int64 v9; // rdx
  int v10; // r8d
  signed int LastError; // eax
  int v12; // eax
  int v13; // ebx
  unsigned int v14; // ebx
  const unsigned __int16 *v16; // [rsp+20h] [rbp-60h]
  __int64 v17; // [rsp+20h] [rbp-60h]
  _QWORD v18[3]; // [rsp+30h] [rbp-50h] BYREF
  _QWORD v19[3]; // [rsp+48h] [rbp-38h] BYREF
  _QWORD v20[4]; // [rsp+60h] [rbp-20h] BYREF
  int v21; // [rsp+B0h] [rbp+30h] BYREF
  int v22; // [rsp+B8h] [rbp+38h] BYREF
  int v23; // [rsp+BCh] [rbp+3Ch]

  v23 = HIDWORD(a2);
  v22 = 0;
  memset(v18, 0, sizeof(v18));
  memset(v19, 0, sizeof(v19));
  v21 = 0;
  v6 = (*(__int64 (__fastcall **)(struct ICloudAPContext *))(*(_QWORD *)a1 + 8LL))(a1);
  v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 24LL))(v6);
  v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 48LL))(v6);
  v20[0] = "HandleIsConnected";
  v20[1] = &v22;
  v20[2] = 0;
  v20[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\logon.cpp",
    "HandleIsConnected",
    (const char *)0x1B4,
    0,
    v16);
  if ( !a3 || !a4 )
  {
    v22 = -1073741811;
    goto LABEL_15;
  }
  *a4 = 0;
  if ( (*(unsigned int (__fastcall **)(__int64, void *, _QWORD *))(*(_QWORD *)v7 + 192LL))(v7, a3, v18)
    || ((int)GetLastError() > 0
      ? (LastError = (unsigned __int16)GetLastError() | 0xC0070000)
      : (LastError = GetLastError()),
        v22 = LastError,
        LastError >= 0) )
  {
    (*(void (__fastcall **)(__int64, _QWORD, int *, _QWORD))(*(_QWORD *)v8 + 16LL))(v8, v18[0], &v21, 0);
    if ( !v21 )
    {
LABEL_13:
      *a4 = v21;
      goto LABEL_15;
    }
    v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, const unsigned __int16 *, _QWORD *, _QWORD))(*(_QWORD *)v8 + 24LL))(
            v8,
            v18[0],
            L"DefaultCredSaved",
            v19,
            0);
    v13 = v12;
    if ( v12 == -2147023728 )
    {
      v21 = 0;
      goto LABEL_13;
    }
    if ( v12 >= 0 )
      goto LABEL_13;
    LODWORD(v17) = v12;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\logon.cpp",
      0x1DDu,
      L"Unable to query user's PPCRL_CREDPROPERTY_DEFAULTCREDSAVED value with error 0x%x",
      v17);
    v22 = LiveMapHResultToNtStatus(v13);
    if ( v22 >= 0 )
      goto LABEL_13;
  }
LABEL_15:
  v14 = v22;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v20, v9, v10);
  Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>((__int64)v19);
  Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>((__int64)v18);
  return v14;
}

```

## disassembly

```asm
0x1800146e4  mov     [rsp-28h+arg_10], rbx
0x1800146e9  mov     [rsp-28h+arg_8], rdx
0x1800146ee  push    rbp
0x1800146ef  push    rsi
0x1800146f0  push    rdi
0x1800146f1  push    r14
0x1800146f3  push    r15
0x1800146f5  mov     rbp, rsp
0x1800146f8  sub     rsp, 80h
0x1800146ff  mov     rdi, r9
0x180014702  mov     r14, r8
0x180014705  xor     r15d, r15d
0x180014708  mov     dword ptr [rbp+arg_8], r15d
0x18001470c  mov     [rbp+var_50], r15
0x180014710  mov     [rbp+var_40], r15
0x180014714  mov     [rbp+var_48], r15
0x180014718  mov     [rbp+var_38], r15
0x18001471c  mov     [rbp+var_28], r15
0x180014720  mov     [rbp+var_30], r15
0x180014724  mov     [rbp+arg_0], r15d
0x180014728  mov     rax, [rcx]
0x18001472b  mov     rax, [rax+8]
0x18001472f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014734  mov     rbx, rax
0x180014737  mov     rcx, [rax]
0x18001473a  mov     rax, [rcx+18h]
0x18001473e  mov     rcx, rbx
0x180014741  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014746  mov     rsi, rax
0x180014749  mov     rcx, [rbx]
0x18001474c  mov     rax, [rcx+30h]
0x180014750  mov     rcx, rbx
0x180014753  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014758  mov     rbx, rax
0x18001475b  lea     rdx, aHandleisconnec; "HandleIsConnected"
0x180014762  mov     [rbp+var_20], rdx
0x180014766  lea     rax, [rbp+arg_8]
0x18001476a  mov     [rbp+var_18], rax
0x18001476e  mov     [rbp+var_10], r15
0x180014772  mov     [rbp+var_8], r15
0x180014776  xor     r9d, r9d; unsigned int
0x180014779  mov     r8d, 1B4h; char *
0x18001477f  lea     rcx, aOnecoreuapDsEx_5; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x180014786  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18001478b  nop
0x18001478c  test    r14, r14
0x18001478f  jz      loc_180014876
0x180014795  test    rdi, rdi
0x180014798  jz      loc_180014876
0x18001479e  mov     [rdi], r15d
0x1800147a1  mov     rax, [rsi]
0x1800147a4  lea     r8, [rbp+var_50]
0x1800147a8  mov     rdx, r14
0x1800147ab  mov     rcx, rsi
0x1800147ae  mov     rax, [rax+0C0h]
0x1800147b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800147ba  test    eax, eax
0x1800147bc  jnz     short loc_1800147E9
0x1800147be  call    cs:__imp_GetLastError
0x1800147c4  test    eax, eax
0x1800147c6  jg      short loc_1800147D0
0x1800147c8  call    cs:__imp_GetLastError
0x1800147ce  jmp     short loc_1800147DE
0x1800147d0  call    cs:__imp_GetLastError
0x1800147d6  movzx   eax, ax
0x1800147d9  or      eax, 0C0070000h
0x1800147de  mov     dword ptr [rbp+arg_8], eax
0x1800147e1  test    eax, eax
0x1800147e3  js      loc_18001487D
0x1800147e9  mov     rax, [rbx]
0x1800147ec  xor     r9d, r9d
0x1800147ef  lea     r8, [rbp+arg_0]
0x1800147f3  mov     rdx, [rbp+var_50]
0x1800147f7  mov     rcx, rbx
0x1800147fa  mov     rax, [rax+10h]
0x1800147fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014803  cmp     [rbp+arg_0], r15d
0x180014807  jz      short loc_18001486F
0x180014809  mov     rax, [rbx]
0x18001480c  mov     [rsp+80h+var_60], r15
0x180014811  lea     r9, [rbp+var_38]
0x180014815  lea     r8, aDefaultcredsav; "DefaultCredSaved"
0x18001481c  mov     rdx, [rbp+var_50]
0x180014820  mov     rcx, rbx
0x180014823  mov     rax, [rax+18h]
0x180014827  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001482c  mov     ebx, eax
0x18001482e  cmp     eax, 80070490h
0x180014833  jnz     short loc_18001483B
0x180014835  mov     [rbp+arg_0], r15d
0x180014839  jmp     short loc_18001486F
0x18001483b  test    ebx, ebx
0x18001483d  jns     short loc_18001486F
0x18001483f  mov     dword ptr [rsp+80h+var_60], ebx
0x180014843  lea     r9, aUnableToQueryU_0; "Unable to query user's PPCRL_CREDPROPER"...
0x18001484a  mov     r8d, 1DDh; unsigned int
0x180014850  lea     rdx, aOnecoreuapDsEx_5; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x180014857  mov     ecx, 2; unsigned __int8
0x18001485c  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180014861  mov     ecx, ebx; int
0x180014863  call    ?LiveMapHResultToNtStatus@@YAJJ@Z; LiveMapHResultToNtStatus(long)
0x180014868  mov     dword ptr [rbp+arg_8], eax
0x18001486b  test    eax, eax
0x18001486d  js      short loc_18001487D
0x18001486f  mov     eax, [rbp+arg_0]
0x180014872  mov     [rdi], eax
0x180014874  jmp     short loc_18001487D
0x180014876  mov     dword ptr [rbp+arg_8], 0C000000Dh
0x18001487d  mov     ebx, dword ptr [rbp+arg_8]
0x180014880  lea     rcx, [rbp+var_20]
0x180014884  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180014889  nop
0x18001488a  lea     rcx, [rbp+var_38]
0x18001488e  call    ??1?$Auto@PEAPEAXV?$LocalAllocFunctor@PEAPEAX@@VDummyContext@@@@QEAA@XZ; Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>(void)
0x180014893  nop
0x180014894  lea     rcx, [rbp+var_50]
0x180014898  call    ??1?$Auto@PEAPEAXV?$LocalAllocFunctor@PEAPEAX@@VDummyContext@@@@QEAA@XZ; Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>(void)
0x18001489d  mov     eax, ebx
0x18001489f  mov     rbx, [rsp+80h+arg_10]
0x1800148a7  add     rsp, 80h
0x1800148ae  pop     r15
0x1800148b0  pop     r14
0x1800148b2  pop     rdi
0x1800148b3  pop     rsi
0x1800148b4  pop     rbp
0x1800148b5  retn
```
