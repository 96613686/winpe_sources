# UpdateTokenFromValidationInfo(ILiveIdNtService *,void *,MSACloudAPValidationInfo *)

- ea: `0x1800112f0`
- end: `0x180011433`
- name: `?UpdateTokenFromValidationInfo@@YAJPEAVILiveIdNtService@@PEAXPEAUMSACloudAPValidationInfo@@@Z`
- size: `323`
- prototype: `__int64 __fastcall(struct ILiveIdNtService *, void *, struct MSACloudAPValidationInfo *)`
- caller_count: `4`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task, installer_update`

## callers

- `0x180012be8`
- `0x180013cd4`
- `0x18001495c`
- `0x180015468`

## callees

- `0x180003b14`
- `0x180008440`
- `0x18000baac`
- `0x180010064`
- `0x1800112f0`
- `0x1800267c0`
- `0x180032010`

## string_xrefs

- `0x18001134c`: `onecoreuap\ds\ext\live\identity\cloudapplugin\utils.cpp`
- `0x1800113fa`: `onecoreuap\ds\ext\live\identity\cloudapplugin\utils.cpp`
- `0x180011320`: `UpdateTokenFromValidationInfo`
- `0x1800113ed`: `WLIDCUpdateToken failed with error 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UpdateTokenFromValidationInfo(
        struct ILiveIdNtService *a1,
        void *a2,
        struct MSACloudAPValidationInfo *a3)
{
  __int64 v6; // rdx
  int v7; // r8d
  unsigned int v8; // ebx
  int v9; // eax
  int v10; // ebx
  const unsigned __int16 *v12; // [rsp+20h] [rbp-49h]
  __int64 v13; // [rsp+20h] [rbp-49h]
  _QWORD v14[4]; // [rsp+30h] [rbp-39h] BYREF
  __int64 v15; // [rsp+50h] [rbp-19h] BYREF
  int v16; // [rsp+58h] [rbp-11h]
  const wchar_t *v17; // [rsp+60h] [rbp-9h]
  __int64 v18; // [rsp+68h] [rbp-1h]
  int v19; // [rsp+70h] [rbp+7h]
  __int64 v20; // [rsp+78h] [rbp+Fh]
  int v21; // [rsp+80h] [rbp+17h]
  __int64 v22; // [rsp+88h] [rbp+1Fh]
  __int64 v23; // [rsp+90h] [rbp+27h]
  int v24; // [rsp+E0h] [rbp+77h] BYREF

  v24 = 0;
  memset_0(&v15, 0, 0x48u);
  v14[0] = "UpdateTokenFromValidationInfo";
  v14[1] = &v24;
  v14[2] = 0;
  v14[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\utils.cpp",
    "UpdateTokenFromValidationInfo",
    (const char *)0x5A4,
    0,
    v12);
  if ( a3 )
  {
    v17 = L"http://Passport.NET/tb";
    v16 = 0;
    v18 = *((_QWORD *)a3 + 17);
    v23 = 0;
    v22 = 0;
    v20 = *((_QWORD *)a3 + 20);
    if ( *((_DWORD *)a3 + 1) == 2 )
    {
      v21 = 2;
      v15 |= 1uLL;
    }
    else
    {
      v21 = 1;
    }
    v19 = *((_DWORD *)a3 + 46);
    v9 = (*(__int64 (__fastcall **)(struct ILiveIdNtService *, void *, __int64 *, _QWORD))(*(_QWORD *)a1 + 208LL))(
           a1,
           a2,
           &v15,
           0);
    v10 = v9;
    if ( v9 >= 0 )
    {
      v8 = v24;
    }
    else
    {
      LODWORD(v13) = v9;
      TracePrintW(
        2u,
        "onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\utils.cpp",
        0x5C1u,
        L"WLIDCUpdateToken failed with error 0x%x",
        v13);
      v8 = LiveMapHResultToNtStatus(v10);
      v24 = v8;
    }
  }
  else
  {
    v8 = -1073741811;
    v24 = -1073741811;
  }
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v14, v6, v7);
  return v8;
}

```

## disassembly

```asm
0x1800112f0  push    rbp
0x1800112f2  push    rbx
0x1800112f3  push    rsi
0x1800112f4  push    rdi
0x1800112f5  lea     rbp, [rsp-3Fh]
0x1800112fa  sub     rsp, 0A8h
0x180011301  mov     rbx, r8
0x180011304  mov     rsi, rdx
0x180011307  mov     rdi, rcx
0x18001130a  mov     [rbp+57h+arg_10], 0
0x180011311  xor     edx, edx; Val
0x180011313  lea     r8d, [rdx+48h]; Size
0x180011317  lea     rcx, [rbp+57h+var_70]; void *
0x18001131b  call    memset_0
0x180011320  lea     rdx, aUpdatetokenfro; "UpdateTokenFromValidationInfo"
0x180011327  mov     [rbp+57h+var_90], rdx
0x18001132b  lea     rax, [rbp+57h+arg_10]
0x18001132f  mov     [rbp+57h+var_88], rax
0x180011333  mov     [rbp+57h+var_80], 0
0x18001133b  mov     [rbp+57h+var_78], 0
0x180011343  xor     r9d, r9d; unsigned int
0x180011346  mov     r8d, 5A4h; char *
0x18001134c  lea     rcx, aOnecoreuapDsEx_0; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x180011353  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x180011358  nop
0x180011359  test    rbx, rbx
0x18001135c  jnz     short loc_18001136B
0x18001135e  mov     ebx, 0C000000Dh
0x180011363  mov     [rbp+57h+arg_10], ebx
0x180011366  jmp     loc_18001141C
0x18001136b  lea     rax, aHttpPassportNe; "http://Passport.NET/tb"
0x180011372  mov     [rbp+57h+var_60], rax
0x180011376  mov     [rbp+57h+var_68], 0
0x18001137d  mov     rax, [rbx+88h]
0x180011384  mov     [rbp+57h+var_58], rax
0x180011388  mov     [rbp+57h+var_30], 0
0x180011390  mov     [rbp+57h+var_38], 0
0x180011398  mov     rax, [rbx+0A0h]
0x18001139f  mov     [rbp+57h+var_48], rax
0x1800113a3  cmp     dword ptr [rbx+4], 2
0x1800113a7  jnz     short loc_1800113B7
0x1800113a9  mov     [rbp+57h+var_40], 2
0x1800113b0  or      [rbp+57h+var_70], 1
0x1800113b5  jmp     short loc_1800113BE
0x1800113b7  mov     [rbp+57h+var_40], 1
0x1800113be  mov     eax, [rbx+0B8h]
0x1800113c4  mov     [rbp+57h+var_50], eax
0x1800113c7  mov     rax, [rdi]
0x1800113ca  xor     r9d, r9d
0x1800113cd  lea     r8, [rbp+57h+var_70]
0x1800113d1  mov     rdx, rsi
0x1800113d4  mov     rcx, rdi
0x1800113d7  mov     rax, [rax+0D0h]
0x1800113de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800113e3  mov     ebx, eax
0x1800113e5  test    eax, eax
0x1800113e7  jns     short loc_180011419
0x1800113e9  mov     [rsp+0C0h+var_A0], eax
0x1800113ed  lea     r9, aWlidcupdatetok_0; "WLIDCUpdateToken failed with error 0x%x"
0x1800113f4  mov     r8d, 5C1h; unsigned int
0x1800113fa  lea     rdx, aOnecoreuapDsEx_0; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x180011401  mov     ecx, 2; unsigned __int8
0x180011406  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001140b  mov     ecx, ebx; int
0x18001140d  call    ?LiveMapHResultToNtStatus@@YAJJ@Z; LiveMapHResultToNtStatus(long)
0x180011412  mov     ebx, eax
0x180011414  mov     [rbp+57h+arg_10], eax
0x180011417  jmp     short loc_18001141C
0x180011419  mov     ebx, [rbp+57h+arg_10]
0x18001141c  lea     rcx, [rbp+57h+var_90]
0x180011420  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180011425  mov     eax, ebx
0x180011427  add     rsp, 0A8h
0x18001142e  pop     rdi
0x18001142f  pop     rsi
0x180011430  pop     rbx
0x180011431  pop     rbp
0x180011432  retn
```
