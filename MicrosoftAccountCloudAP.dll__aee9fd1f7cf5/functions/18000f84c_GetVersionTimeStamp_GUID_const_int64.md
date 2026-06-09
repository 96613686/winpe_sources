# GetVersionTimeStamp(_GUID const &,__int64 &)

- ea: `0x18000f84c`
- end: `0x18000fa0e`
- name: `?GetVersionTimeStamp@@YAJAEBU_GUID@@AEA_J@Z`
- size: `450`
- prototype: `__int64 __fastcall(const struct _GUID *, __int64 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180013cd4`
- `0x180014ff0`

## callees

- `0x180008440`
- `0x18000baac`
- `0x18000f84c`
- `0x1800267c0`

## string_xrefs

- `0x18000f88e`: `onecoreuap\ds\ext\live\identity\cloudapplugin\utils.cpp`
- `0x18000f8bd`: `onecoreuap\ds\ext\live\identity\cloudapplugin\utils.cpp`
- `0x18000f9a8`: `onecoreuap\ds\ext\live\identity\cloudapplugin\utils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetVersionTimeStamp(const struct _GUID *a1, __int64 *a2)
{
  __int64 Data1; // rcx
  unsigned __int64 v5; // rax
  __int64 v6; // rdx
  int v7; // r8d
  unsigned int v8; // ebx
  __int64 v9; // rbp
  const unsigned __int16 *v11; // [rsp+20h] [rbp-B8h]
  const unsigned __int16 *v12; // [rsp+20h] [rbp-B8h]
  const char *v13; // [rsp+80h] [rbp-58h] BYREF
  int *v14; // [rsp+88h] [rbp-50h]
  __int64 v15; // [rsp+90h] [rbp-48h]
  __int64 v16; // [rsp+98h] [rbp-40h]
  int v17; // [rsp+E0h] [rbp+8h] BYREF

  v17 = 0;
  v14 = &v17;
  v13 = "GetVersionTimeStamp";
  v15 = 0;
  v16 = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\utils.cpp",
    "GetVersionTimeStamp",
    (const char *)0x559,
    0,
    v11);
  Data1 = a1->Data1;
  v5 = 0;
  *a2 = 0;
  while ( v5 < 8 )
  {
    if ( a1->Data4[v5] )
    {
      LODWORD(v12) = a1->Data1;
      TracePrintW(
        2u,
        "onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\utils.cpp",
        0x566u,
        L"Invalid GUID passed to GetVersionTimeStamp. GUID = {%08lX-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X}",
        v12,
        a1->Data2,
        a1->Data3,
        a1->Data4[0],
        a1->Data4[1],
        a1->Data4[2],
        a1->Data4[3],
        a1->Data4[4],
        a1->Data4[5],
        a1->Data4[6],
        a1->Data4[7]);
      v8 = -1073741275;
      v17 = -1073741275;
      goto LABEL_7;
    }
    ++v5;
  }
  v9 = a1->Data3 | ((a1->Data2 | (unsigned __int64)(Data1 << 16)) << 16);
  LODWORD(v12) = a1->Data1;
  TracePrintW(
    5u,
    "onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\utils.cpp",
    0x574u,
    L"GetVersionTimeStamp :: GUID = {%08lX-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X}, Timestamp = %I64d",
    v12,
    a1->Data2,
    a1->Data3,
    a1->Data4[0],
    a1->Data4[1],
    a1->Data4[2],
    a1->Data4[3],
    a1->Data4[4],
    a1->Data4[5],
    a1->Data4[6],
    a1->Data4[7],
    v9,
    v13,
    v14,
    v15,
    v16);
  v8 = v17;
  *a2 = v9;
LABEL_7:
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)&v13, v6, v7);
  return v8;
}

```

## disassembly

```asm
0x18000f84c  mov     r11, rsp
0x18000f84f  push    rbx
0x18000f850  push    rbp
0x18000f851  push    rsi
0x18000f852  push    rdi
0x18000f853  push    r14
0x18000f855  push    r15
0x18000f857  sub     rsp, 0A8h
0x18000f85e  xor     ebx, ebx
0x18000f860  lea     rax, [r11+8]
0x18000f864  mov     r15, rdx
0x18000f867  mov     [r11+8], ebx
0x18000f86b  lea     rdx, aGetversiontime; "GetVersionTimeStamp"
0x18000f872  mov     [r11-50h], rax
0x18000f876  mov     r14, rcx
0x18000f879  mov     [r11-58h], rdx
0x18000f87d  xor     r9d, r9d; unsigned int
0x18000f880  mov     [r11-48h], rbx
0x18000f884  mov     r8d, 559h; char *
0x18000f88a  mov     [r11-40h], rbx
0x18000f88e  lea     rcx, aOnecoreuapDsEx_0; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x18000f895  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18000f89a  mov     ecx, [r14]
0x18000f89d  mov     eax, ebx
0x18000f89f  mov     [r15], rbx
0x18000f8a2  cmp     rax, 8
0x18000f8a6  jnb     loc_18000F94C
0x18000f8ac  cmp     [r14+rax+8], bl
0x18000f8b1  jnz     short loc_18000F8B8
0x18000f8b3  inc     rax
0x18000f8b6  jmp     short loc_18000F8A2
0x18000f8b8  movzx   eax, byte ptr [r14+0Fh]
0x18000f8bd  lea     rdx, aOnecoreuapDsEx_0; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x18000f8c4  movzx   ecx, byte ptr [r14+0Eh]
0x18000f8c9  movzx   r8d, byte ptr [r14+0Dh]
0x18000f8ce  movzx   r9d, byte ptr [r14+0Ch]
0x18000f8d3  movzx   r10d, byte ptr [r14+0Bh]
0x18000f8d8  movzx   r11d, byte ptr [r14+0Ah]
0x18000f8dd  movzx   ebx, byte ptr [r14+9]
0x18000f8e2  movzx   edi, byte ptr [r14+8]
0x18000f8e7  movzx   esi, word ptr [r14+6]
0x18000f8ec  movzx   ebp, word ptr [r14+4]
0x18000f8f1  mov     [rsp+0D8h+var_68], eax
0x18000f8f5  mov     eax, [r14]
0x18000f8f8  mov     [rsp+0D8h+var_70], ecx
0x18000f8fc  mov     ecx, 2; unsigned __int8
0x18000f901  mov     [rsp+0D8h+var_78], r8d
0x18000f906  mov     r8d, 566h; unsigned int
0x18000f90c  mov     [rsp+0D8h+var_80], r9d
0x18000f911  lea     r9, aInvalidGuidPas; "Invalid GUID passed to GetVersionTimeSt"...
0x18000f918  mov     [rsp+0D8h+var_88], r10d
0x18000f91d  mov     [rsp+0D8h+var_90], r11d
0x18000f922  mov     [rsp+0D8h+var_98], ebx
0x18000f926  mov     [rsp+0D8h+var_A0], edi
0x18000f92a  mov     [rsp+0D8h+var_A8], esi
0x18000f92e  mov     [rsp+0D8h+var_B0], ebp
0x18000f932  mov     dword ptr [rsp+0D8h+var_B8], eax
0x18000f936  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000f93b  mov     ebx, 0C0000225h
0x18000f940  mov     [rsp+0D8h+arg_0], ebx
0x18000f947  jmp     loc_18000F9EF
0x18000f94c  movzx   edi, word ptr [r14+4]
0x18000f951  mov     rbp, rcx
0x18000f954  movzx   esi, word ptr [r14+6]
0x18000f959  movzx   eax, byte ptr [r14+0Fh]
0x18000f95e  movzx   ecx, byte ptr [r14+0Eh]
0x18000f963  movzx   edx, byte ptr [r14+0Dh]
0x18000f968  movzx   r8d, byte ptr [r14+0Ch]
0x18000f96d  movzx   r9d, byte ptr [r14+0Bh]
0x18000f972  movzx   r10d, byte ptr [r14+0Ah]
0x18000f977  movzx   r11d, byte ptr [r14+9]
0x18000f97c  movzx   ebx, byte ptr [r14+8]
0x18000f981  shl     rbp, 10h
0x18000f985  or      rbp, rdi
0x18000f988  shl     rbp, 10h
0x18000f98c  or      rbp, rsi
0x18000f98f  mov     [rsp+0D8h+var_60], rbp
0x18000f994  mov     [rsp+0D8h+var_68], eax
0x18000f998  mov     eax, [r14]
0x18000f99b  mov     [rsp+0D8h+var_70], ecx
0x18000f99f  mov     ecx, 5; unsigned __int8
0x18000f9a4  mov     [rsp+0D8h+var_78], edx
0x18000f9a8  lea     rdx, aOnecoreuapDsEx_0; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x18000f9af  mov     [rsp+0D8h+var_80], r8d
0x18000f9b4  mov     r8d, 574h; unsigned int
0x18000f9ba  mov     [rsp+0D8h+var_88], r9d
0x18000f9bf  lea     r9, aGetversiontime_0; "GetVersionTimeStamp :: GUID = {%08lX-%0"...
0x18000f9c6  mov     [rsp+0D8h+var_90], r10d
0x18000f9cb  mov     [rsp+0D8h+var_98], r11d
0x18000f9d0  mov     [rsp+0D8h+var_A0], ebx
0x18000f9d4  mov     [rsp+0D8h+var_A8], esi
0x18000f9d8  mov     [rsp+0D8h+var_B0], edi
0x18000f9dc  mov     dword ptr [rsp+0D8h+var_B8], eax
0x18000f9e0  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000f9e5  mov     ebx, [rsp+0D8h+arg_0]
0x18000f9ec  mov     [r15], rbp
0x18000f9ef  lea     rcx, [rsp+0D8h+var_58]
0x18000f9f7  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18000f9fc  mov     eax, ebx
0x18000f9fe  add     rsp, 0A8h
0x18000fa05  pop     r15
0x18000fa07  pop     r14
0x18000fa09  pop     rdi
0x18000fa0a  pop     rsi
0x18000fa0b  pop     rbp
0x18000fa0c  pop     rbx
0x18000fa0d  retn
```
