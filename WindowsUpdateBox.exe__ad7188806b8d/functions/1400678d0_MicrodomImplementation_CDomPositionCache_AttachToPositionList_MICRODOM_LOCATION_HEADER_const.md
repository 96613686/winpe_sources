# MicrodomImplementation::CDomPositionCache::AttachToPositionList(_MICRODOM_LOCATION_HEADER const *)

- ea: `0x1400678d0`
- end: `0x140067a8c`
- name: `?AttachToPositionList@CDomPositionCache@MicrodomImplementation@@QEAAJPEBU_MICRODOM_LOCATION_HEADER@@@Z`
- size: `444`
- prototype: `__int64 __fastcall(MicrodomImplementation::CDomPositionCache *__hidden this, const struct _MICRODOM_LOCATION_HEADER *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14006ce64`

## callees

- `0x140066b60`
- `0x1400678d0`
- `0x140072764`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1400679f2`
- `KERNEL32!HeapAlloc` at `0x1400679f2`
- `KERNEL32!GetProcessHeap` at `0x1400679de`
- `KERNEL32!GetProcessHeap` at `0x1400679de`
- `ntdll!RtlRaiseStatus` at `0x140067998`
- `ntdll!RtlRaiseStatus` at `0x140067998`

## string_xrefs

- `0x1400678eb`: `onecore\base\xml\udom_microdom.cpp`
- `0x140067935`: `onecore\base\xml\udom_microdom.cpp`
- `0x140067965`: `onecore\base\xml\udom_microdom.cpp`
- `0x140067a3a`: `onecore\base\xml\udom_microdom.cpp`
- `0x1400678fe`: `MicrodomImplementation::CDomPositionCache::AttachToPositionList`
- `0x140067948`: `MicrodomImplementation::CDomPositionCache::AttachToPositionList`
- `0x140067978`: `MicrodomImplementation::CDomPositionCache::AttachToPositionList`
- `0x140067a51`: `MicrodomImplementation::CDomPositionCache::AttachToPositionList`

## pseudocode

```c
__int64 __fastcall MicrodomImplementation::CDomPositionCache::AttachToPositionList(
        MicrodomImplementation::CDomPositionCache *this,
        const struct _MICRODOM_LOCATION_HEADER *a2)
{
  const char *v3; // rax
  unsigned __int64 v5; // rsi
  SIZE_T v6; // rbx
  HANDLE ProcessHeap; // rax
  MicrodomImplementation::CDomPositionCache::CPositionSlot *v8; // rax
  __int64 v9; // rbx
  __int64 v10; // r14
  MicrodomImplementation::CDomPositionCache::CPositionSlot *v11; // r15
  const char *v12; // [rsp+20h] [rbp-20h] BYREF
  const char *v13; // [rsp+28h] [rbp-18h]
  __int64 v14; // [rsp+30h] [rbp-10h]
  const char *v15; // [rsp+38h] [rbp-8h]

  if ( !a2 )
  {
    v14 = 3576;
    v12 = "onecore\\base\\xml\\udom_microdom.cpp";
    v13 = "MicrodomImplementation::CDomPositionCache::AttachToPositionList";
    v3 = "LocationHeader != 0";
LABEL_3:
    v15 = v3;
    RtlReportErrorOrigination(&v12, a2, 3221225485LL);
    return 3221225485LL;
  }
  if ( *(_DWORD *)a2 != 1665950797 )
  {
    v14 = 3577;
    v12 = "onecore\\base\\xml\\udom_microdom.cpp";
    v13 = "MicrodomImplementation::CDomPositionCache::AttachToPositionList";
    v3 = "LocationHeader->Signature == ('cLdM')";
    goto LABEL_3;
  }
  if ( (*((_DWORD *)a2 + 1) & 0xFFFFFFFC) != 0 )
  {
    v14 = 3578;
    v12 = "onecore\\base\\xml\\udom_microdom.cpp";
    v13 = "MicrodomImplementation::CDomPositionCache::AttachToPositionList";
    v3 = "(LocationHeader->ulFlags & ~((0x00000001) | (0x00000002) | (0x00000003))) == 0";
    goto LABEL_3;
  }
  if ( *((_QWORD *)this + 4) )
    RtlRaiseStatus(-1073741595);
  *(_QWORD *)this = a2;
  *((_QWORD *)this + 4) = (char *)a2 + 12;
  *((_DWORD *)this + 7) = *((_DWORD *)a2 + 1) & 3;
  v5 = *((unsigned int *)a2 + 2);
  if ( *((_QWORD *)this + 1) )
    goto LABEL_22;
  if ( *((_DWORD *)a2 + 2) )
  {
    v6 = 8 * v5;
    if ( !is_mul_ok(v5, 8u) )
      v6 = -1;
    ProcessHeap = GetProcessHeap();
    v8 = (MicrodomImplementation::CDomPositionCache::CPositionSlot *)HeapAlloc(ProcessHeap, 0, v6);
    v9 = (__int64)v8;
    if ( v8 )
    {
      v10 = (unsigned int)v5;
      v11 = v8;
      do
      {
        MicrodomImplementation::CDomPositionCache::CPositionSlot::CPositionSlot(v11);
        v11 = (MicrodomImplementation::CDomPositionCache::CPositionSlot *)((char *)v11 + 8);
        --v10;
      }
      while ( v10 );
      *((_QWORD *)this + 1) = v9;
      *((_QWORD *)this + 2) = v5;
    }
    else
    {
      v9 = 0;
    }
  }
  else
  {
    v9 = 4;
  }
  if ( v9 )
    return 0;
LABEL_22:
  v14 = 3586;
  v12 = "onecore\\base\\xml\\udom_microdom.cpp";
  v13 = "MicrodomImplementation::CDomPositionCache::AttachToPositionList";
  v15 = "this->m_PositionList.Allocate(LocationHeader->ulItemCount)";
  RtlReportErrorOrigination(&v12, a2, 3221225495LL);
  return 3221225495LL;
}

```

## disassembly

```asm
0x1400678d0  mov     [rsp-28h+arg_10], rbx
0x1400678d5  push    rbp
0x1400678d6  push    rsi
0x1400678d7  push    rdi
0x1400678d8  push    r14
0x1400678da  push    r15
0x1400678dc  mov     rbp, rsp
0x1400678df  sub     rsp, 40h
0x1400678e3  mov     rdi, rcx
0x1400678e6  test    rdx, rdx
0x1400678e9  jnz     short loc_14006792D
0x1400678eb  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x1400678f2  mov     [rbp+var_10], 0DF8h
0x1400678fa  mov     [rbp+var_20], rax
0x1400678fe  lea     rax, aMicrodomimplem_11; "MicrodomImplementation::CDomPositionCac"...
0x140067905  mov     [rbp+var_18], rax
0x140067909  lea     rax, aLocationheader; "LocationHeader != 0"
0x140067910  mov     r8d, 0C000000Dh
0x140067916  mov     [rbp+var_8], rax
0x14006791a  lea     rcx, [rbp+var_20]
0x14006791e  call    RtlReportErrorOrigination
0x140067923  mov     eax, 0C000000Dh
0x140067928  jmp     loc_140067A77
0x14006792d  cmp     dword ptr [rdx], 634C644Dh
0x140067933  jz      short loc_14006795C
0x140067935  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x14006793c  mov     [rbp+var_10], 0DF9h
0x140067944  mov     [rbp+var_20], rax
0x140067948  lea     rax, aMicrodomimplem_11; "MicrodomImplementation::CDomPositionCac"...
0x14006794f  mov     [rbp+var_18], rax
0x140067953  lea     rax, aLocationheader_1; "LocationHeader->Signature == ('cLdM')"
0x14006795a  jmp     short loc_140067910
0x14006795c  test    dword ptr [rdx+4], 0FFFFFFFCh
0x140067963  jz      short loc_14006798C
0x140067965  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x14006796c  mov     [rbp+var_10], 0DFAh
0x140067974  mov     [rbp+var_20], rax
0x140067978  lea     rax, aMicrodomimplem_11; "MicrodomImplementation::CDomPositionCac"...
0x14006797f  mov     [rbp+var_18], rax
0x140067983  lea     rax, aLocationheader_0; "(LocationHeader->ulFlags & ~((0x0000000"...
0x14006798a  jmp     short loc_140067910
0x14006798c  cmp     qword ptr [rcx+20h], 0
0x140067991  jz      short loc_1400679A5
0x140067993  mov     ecx, 0C00000E5h; Status
0x140067998  call    cs:__imp_RtlRaiseStatus
0x14006799f  nop     dword ptr [rax+rax+00h]
0x1400679a4  int     3; Trap to Debugger
0x1400679a5  mov     [rcx], rdx
0x1400679a8  lea     rax, [rdx+0Ch]
0x1400679ac  mov     [rcx+20h], rax
0x1400679b0  mov     eax, [rdx+4]
0x1400679b3  and     eax, 3
0x1400679b6  mov     [rcx+1Ch], eax
0x1400679b9  cmp     qword ptr [rcx+8], 0
0x1400679be  mov     esi, [rdx+8]
0x1400679c1  jnz     short loc_140067A3A
0x1400679c3  test    rsi, rsi
0x1400679c6  jz      short loc_140067A2C
0x1400679c8  mov     eax, 8
0x1400679cd  mul     rsi
0x1400679d0  mov     rbx, rax
0x1400679d3  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1400679da  cmovb   rbx, rax
0x1400679de  call    cs:__imp_GetProcessHeap
0x1400679e5  nop     dword ptr [rax+rax+00h]
0x1400679ea  mov     r8, rbx; dwBytes
0x1400679ed  xor     edx, edx; dwFlags
0x1400679ef  mov     rcx, rax; hHeap
0x1400679f2  call    cs:__imp_HeapAlloc
0x1400679f9  nop     dword ptr [rax+rax+00h]
0x1400679fe  mov     rbx, rax
0x140067a01  test    rax, rax
0x140067a04  jz      short loc_140067A28
0x140067a06  mov     r14d, esi
0x140067a09  mov     r15, rax
0x140067a0c  mov     rcx, r15; this
0x140067a0f  call    ??0CPositionSlot@CDomPositionCache@MicrodomImplementation@@QEAA@XZ; MicrodomImplementation::CDomPositionCache::CPositionSlot::CPositionSlot(void)
0x140067a14  add     r15, 8
0x140067a18  sub     r14, 1
0x140067a1c  jnz     short loc_140067A0C
0x140067a1e  mov     [rdi+8], rbx
0x140067a22  mov     [rdi+10h], rsi
0x140067a26  jmp     short loc_140067A31
0x140067a28  xor     ebx, ebx
0x140067a2a  jmp     short loc_140067A31
0x140067a2c  mov     ebx, 4
0x140067a31  test    rbx, rbx
0x140067a34  jz      short loc_140067A3A
0x140067a36  xor     eax, eax
0x140067a38  jmp     short loc_140067A77
0x140067a3a  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x140067a41  mov     [rbp+var_10], 0E02h
0x140067a49  mov     [rbp+var_20], rax
0x140067a4d  lea     rcx, [rbp+var_20]
0x140067a51  lea     rax, aMicrodomimplem_11; "MicrodomImplementation::CDomPositionCac"...
0x140067a58  mov     r8d, 0C0000017h
0x140067a5e  mov     [rbp+var_18], rax
0x140067a62  lea     rax, aThisMPositionl; "this->m_PositionList.Allocate(LocationH"...
0x140067a69  mov     [rbp+var_8], rax
0x140067a6d  call    RtlReportErrorOrigination
0x140067a72  mov     eax, 0C0000017h
0x140067a77  mov     rbx, [rsp+40h+arg_10]
0x140067a7f  add     rsp, 40h
0x140067a83  pop     r15
0x140067a85  pop     r14
0x140067a87  pop     rdi
0x140067a88  pop     rsi
0x140067a89  pop     rbp
0x140067a8a  retn
```
