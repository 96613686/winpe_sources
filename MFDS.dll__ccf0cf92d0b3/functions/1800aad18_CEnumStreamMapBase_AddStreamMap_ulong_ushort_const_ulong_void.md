# CEnumStreamMapBase::AddStreamMap(ulong,ushort const *,ulong,void *)

- ea: `0x1800aad18`
- end: `0x1800aaeaf`
- name: `?AddStreamMap@CEnumStreamMapBase@@QEAAJKPEBGKPEAX@Z`
- size: `407`
- prototype: `__int64 __fastcall(CEnumStreamMapBase *this, int, const unsigned __int16 *, int, void *Src)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800aa8ac`
- `0x1800aac30`

## callees

- `0x180002820`
- `0x18000b8c0`
- `0x180074a12`
- `0x1800aad18`
- `0x1800ab778`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800aadfb`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800aadfb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800aade4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800aae4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800aae59`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800aade4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800aae4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800aae59`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800aad86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800aadcc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800aae21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800aad86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800aadcc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800aae21`

## pseudocode

```c
__int64 __fastcall CEnumStreamMapBase::AddStreamMap(
        CEnumStreamMapBase *this,
        int a2,
        const unsigned __int16 *a3,
        int a4,
        void *Src)
{
  _DWORD *v9; // rax
  _DWORD *v10; // rbx
  __int64 v12; // rax
  __int64 v13; // r15
  LPVOID v14; // rax
  unsigned int v15; // edi
  void *v16; // rax
  unsigned int v17; // ebx
  _QWORD *v18; // rcx
  _QWORD *v19; // rax
  _BYTE v20[72]; // [rsp+40h] [rbp-48h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v20, "CEnumStreamMapBase::AddStreamMap", 132);
  if ( (unsigned __int8)byte_1800EACCB >= 0x20u )
    WPP_SF_qDqD(
      *((_QWORD *)WPP_GLOBAL_Control + 17),
      13,
      WPP_3461acf4a3093ec85b4914ae9289c173_Traceguids,
      this,
      a2,
      a3,
      a4);
  v9 = CoTaskMemAlloc(0x30u);
  v10 = v9;
  if ( !v9 )
    goto LABEL_4;
  *v9 = a2;
  v9[4] = a4;
  v12 = -1;
  do
    ++v12;
  while ( a3[v12] );
  v13 = v12 + 1;
  v14 = CoTaskMemAlloc(2 * (v12 + 1));
  *((_QWORD *)v10 + 1) = v14;
  if ( !v14 )
  {
    CoTaskMemFree(v10);
LABEL_4:
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v20);
    return 2147942414LL;
  }
  _o_wcscpy_s(v14, v13, a3);
  if ( !Src )
  {
    *((_QWORD *)v10 + 3) = 0;
    goto LABEL_14;
  }
  v15 = a4 == 0 ? 8 : 0;
  v16 = CoTaskMemAlloc(v15);
  *((_QWORD *)v10 + 3) = v16;
  if ( v16 )
  {
    memcpy_0(v16, Src, v15);
LABEL_14:
    v18 = v10 + 8;
    v19 = (_QWORD *)*((_QWORD *)this + 5);
    *((_QWORD *)v10 + 5) = v19;
    v17 = 0;
    *v18 = (char *)this + 32;
    *v19 = v18;
    ++*((_DWORD *)this + 14);
    ++*((_DWORD *)this + 15);
    *((_QWORD *)this + 5) = v18;
    goto LABEL_15;
  }
  CoTaskMemFree(*((LPVOID *)v10 + 1));
  CoTaskMemFree(v10);
  v17 = -2147024882;
LABEL_15:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v20);
  return v17;
}

```

## disassembly

```asm
0x1800aad18  push    rbx
0x1800aad1a  push    rbp
0x1800aad1b  push    rsi
0x1800aad1c  push    rdi
0x1800aad1d  push    r12
0x1800aad1f  push    r14
0x1800aad21  push    r15
0x1800aad23  sub     rsp, 50h
0x1800aad27  mov     r14, r8
0x1800aad2a  mov     ebp, edx
0x1800aad2c  mov     rsi, rcx
0x1800aad2f  lea     rdx, aCenumstreammap_0; "CEnumStreamMapBase::AddStreamMap"
0x1800aad36  mov     r8d, 84h; int
0x1800aad3c  lea     rcx, [rsp+88h+var_48]; this
0x1800aad41  mov     edi, r9d
0x1800aad44  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800aad49  cmp     cs:byte_1800EACCB, 20h ; ' '
0x1800aad50  jb      short loc_1800AAD81
0x1800aad52  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aad59  lea     r8, WPP_3461acf4a3093ec85b4914ae9289c173_Traceguids
0x1800aad60  mov     [rsp+88h+var_58], edi
0x1800aad64  mov     edx, 0Dh
0x1800aad69  mov     [rsp+88h+var_60], r14
0x1800aad6e  mov     r9, rsi
0x1800aad71  mov     [rsp+88h+var_68], ebp
0x1800aad75  mov     rcx, [rcx+88h]
0x1800aad7c  call    WPP_SF_qDqD
0x1800aad81  mov     ecx, 30h ; '0'; cb
0x1800aad86  call    cs:__imp_CoTaskMemAlloc
0x1800aad8d  nop     dword ptr [rax+rax+00h]
0x1800aad92  xor     r12d, r12d
0x1800aad95  mov     rbx, rax
0x1800aad98  test    rax, rax
0x1800aad9b  jnz     short loc_1800AADB1
0x1800aad9d  lea     rcx, [rsp+88h+var_48]; this
0x1800aada2  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800aada7  mov     eax, 8007000Eh
0x1800aadac  jmp     loc_1800AAE9F
0x1800aadb1  mov     [rax], ebp
0x1800aadb3  mov     [rax+10h], edi
0x1800aadb6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800aadba  inc     rax
0x1800aadbd  cmp     [r14+rax*2], r12w
0x1800aadc2  jnz     short loc_1800AADBA
0x1800aadc4  lea     r15, [rax+1]
0x1800aadc8  lea     rcx, [r15+r15]; cb
0x1800aadcc  call    cs:__imp_CoTaskMemAlloc
0x1800aadd3  nop     dword ptr [rax+rax+00h]
0x1800aadd8  mov     [rbx+8], rax
0x1800aaddc  test    rax, rax
0x1800aaddf  jnz     short loc_1800AADF2
0x1800aade1  mov     rcx, rbx; pv
0x1800aade4  call    cs:__imp_CoTaskMemFree
0x1800aadeb  nop     dword ptr [rax+rax+00h]
0x1800aadf0  jmp     short loc_1800AAD9D
0x1800aadf2  mov     r8, r14
0x1800aadf5  mov     rdx, r15
0x1800aadf8  mov     rcx, rax
0x1800aadfb  call    cs:__imp__o_wcscpy_s
0x1800aae02  nop     dword ptr [rax+rax+00h]
0x1800aae07  mov     rbp, [rsp+88h+Src]
0x1800aae0f  test    rbp, rbp
0x1800aae12  jz      short loc_1800AAE6C
0x1800aae14  neg     edi
0x1800aae16  sbb     rdi, rdi
0x1800aae19  not     rdi
0x1800aae1c  and     edi, 8
0x1800aae1f  mov     ecx, edi; cb
0x1800aae21  call    cs:__imp_CoTaskMemAlloc
0x1800aae28  nop     dword ptr [rax+rax+00h]
0x1800aae2d  mov     [rbx+18h], rax
0x1800aae31  test    rax, rax
0x1800aae34  jz      short loc_1800AAE46
0x1800aae36  mov     r8d, edi; Size
0x1800aae39  mov     rdx, rbp; Src
0x1800aae3c  mov     rcx, rax; void *
0x1800aae3f  call    memcpy_0
0x1800aae44  jmp     short loc_1800AAE70
0x1800aae46  mov     rcx, [rbx+8]; pv
0x1800aae4a  call    cs:__imp_CoTaskMemFree
0x1800aae51  nop     dword ptr [rax+rax+00h]
0x1800aae56  mov     rcx, rbx; pv
0x1800aae59  call    cs:__imp_CoTaskMemFree
0x1800aae60  nop     dword ptr [rax+rax+00h]
0x1800aae65  mov     ebx, 8007000Eh
0x1800aae6a  jmp     short loc_1800AAE93
0x1800aae6c  mov     [rbx+18h], r12
0x1800aae70  lea     rcx, [rbx+20h]
0x1800aae74  lea     rdx, [rsi+20h]
0x1800aae78  mov     rax, [rdx+8]
0x1800aae7c  mov     [rbx+28h], rax
0x1800aae80  mov     ebx, r12d
0x1800aae83  mov     [rcx], rdx
0x1800aae86  mov     [rax], rcx
0x1800aae89  inc     dword ptr [rsi+38h]
0x1800aae8c  inc     dword ptr [rsi+3Ch]
0x1800aae8f  mov     [rdx+8], rcx
0x1800aae93  lea     rcx, [rsp+88h+var_48]; this
0x1800aae98  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800aae9d  mov     eax, ebx
0x1800aae9f  add     rsp, 50h
0x1800aaea3  pop     r15
0x1800aaea5  pop     r14
0x1800aaea7  pop     r12
0x1800aaea9  pop     rdi
0x1800aaeaa  pop     rsi
0x1800aaeab  pop     rbp
0x1800aaeac  pop     rbx
0x1800aaead  retn
```
