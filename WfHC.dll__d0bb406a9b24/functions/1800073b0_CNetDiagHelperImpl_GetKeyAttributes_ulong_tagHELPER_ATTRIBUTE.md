# CNetDiagHelperImpl::GetKeyAttributes(ulong *,tagHELPER_ATTRIBUTE * *)

- ea: `0x1800073b0`
- end: `0x1800074d8`
- name: `?GetKeyAttributes@CNetDiagHelperImpl@@UEAAJPEAKPEAPEAUtagHELPER_ATTRIBUTE@@@Z`
- size: `296`
- prototype: `__int64 __fastcall(CNetDiagHelperImpl *__hidden this, unsigned int *, struct tagHELPER_ATTRIBUTE **)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1800031e0`
- `0x180003b60`
- `0x1800073b0`
- `0x18000c168`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000743c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000743c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007424`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007461`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800074ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007424`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007461`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800074ba`

## pseudocode

```c
__int64 __fastcall CNetDiagHelperImpl::GetKeyAttributes(
        CNetDiagHelperImpl *this,
        unsigned int *a2,
        struct tagHELPER_ATTRIBUTE **a3)
{
  __int64 v6; // rbp
  unsigned int v7; // ebx
  __int64 v8; // rsi
  struct tagHELPER_ATTRIBUTE *v9; // rax
  struct tagHELPER_ATTRIBUTE *v10; // rdi
  __int64 i; // rsi
  int v13; // [rsp+20h] [rbp-48h] BYREF
  struct tagHELPER_ATTRIBUTE *v14; // [rsp+28h] [rbp-40h]

  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  if ( *((_DWORD *)this + 4) != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  if ( !a2 || !a3 )
    return (unsigned int)-2147024809;
  v6 = *((unsigned int *)this + 6);
  v13 = 0;
  v14 = 0;
  if ( (unsigned int)v6 > 0x1C71C71 )
  {
    v7 = -2147024362;
LABEL_13:
    _attributes_array_t::FreeElements((_attributes_array_t *)&v13);
    CoTaskMemFree(0);
    return v7;
  }
  _attributes_array_t::FreeElements((_attributes_array_t *)&v13);
  CoTaskMemFree(0);
  v8 = 144 * v6;
  v9 = (struct tagHELPER_ATTRIBUTE *)CoTaskMemAlloc(144 * v6);
  v14 = v9;
  v10 = v9;
  if ( !v9 )
  {
    v7 = -2147024882;
    goto LABEL_13;
  }
  for ( ; v8; --v8 )
  {
    LOBYTE(v9->pwszName) = 0;
    v9 = (struct tagHELPER_ATTRIBUTE *)((char *)v9 + 1);
  }
  for ( i = 0; (unsigned int)i < *((_DWORD *)this + 6); i = (unsigned int)(i + 1) )
    _attribute_t::Copy(&v10[i], (const struct tagHELPER_ATTRIBUTE *)(144 * i + *((_QWORD *)this + 4)));
  *a2 = v6;
  *a3 = v10;
  v14 = 0;
  _attributes_array_t::FreeElements((_attributes_array_t *)&v13);
  CoTaskMemFree(0);
  return 0;
}

```

## disassembly

```asm
0x1800073b0  push    rbx
0x1800073b2  push    rbp
0x1800073b3  push    rsi
0x1800073b4  push    rdi
0x1800073b5  push    r14
0x1800073b7  push    r15
0x1800073b9  sub     rsp, 38h
0x1800073bd  mov     r14, r8
0x1800073c0  mov     r15, rdx
0x1800073c3  mov     rbx, rcx
0x1800073c6  test    rdx, rdx
0x1800073c9  jnz     short loc_1800073D0
0x1800073cb  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800073d0  test    r14, r14
0x1800073d3  jnz     short loc_1800073DA
0x1800073d5  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800073da  cmp     dword ptr [rbx+10h], 1
0x1800073de  jz      short loc_1800073E5
0x1800073e0  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800073e5  test    r15, r15
0x1800073e8  jz      loc_1800074C4
0x1800073ee  test    r14, r14
0x1800073f1  jz      loc_1800074C4
0x1800073f7  mov     ebp, [rbx+18h]
0x1800073fa  xor     edi, edi
0x1800073fc  mov     [rsp+68h+var_48], 0
0x180007404  mov     [rsp+68h+var_40], rdi
0x180007409  cmp     ebp, 1C71C71h
0x18000740f  jbe     short loc_180007418
0x180007411  mov     ebx, 80070216h
0x180007416  jmp     short loc_180007454
0x180007418  lea     rcx, [rsp+68h+var_48]; this
0x18000741d  call    ?FreeElements@_attributes_array_t@@QEAAXXZ; _attributes_array_t::FreeElements(void)
0x180007422  xor     ecx, ecx; pv
0x180007424  call    cs:__imp_CoTaskMemFree
0x18000742a  lea     rsi, ds:0[rbp*8]
0x180007432  add     rsi, rbp
0x180007435  shl     rsi, 4
0x180007439  mov     rcx, rsi; cb
0x18000743c  call    cs:__imp_CoTaskMemAlloc
0x180007442  mov     [rsp+68h+var_40], rax
0x180007447  mov     rdi, rax
0x18000744a  test    rax, rax
0x18000744d  jnz     short loc_180007469
0x18000744f  mov     ebx, 8007000Eh
0x180007454  lea     rcx, [rsp+68h+var_48]; this
0x180007459  call    ?FreeElements@_attributes_array_t@@QEAAXXZ; _attributes_array_t::FreeElements(void)
0x18000745e  mov     rcx, rdi; pv
0x180007461  call    cs:__imp_CoTaskMemFree
0x180007467  jmp     short loc_1800074C9
0x180007469  test    rsi, rsi
0x18000746c  jz      short loc_18000747A
0x18000746e  mov     byte ptr [rax], 0
0x180007471  inc     rax
0x180007474  sub     rsi, 1
0x180007478  jnz     short loc_18000746E
0x18000747a  xor     esi, esi
0x18000747c  cmp     [rbx+18h], esi
0x18000747f  jbe     short loc_18000749F
0x180007481  mov     rdx, [rbx+20h]
0x180007485  lea     rcx, [rsi+rsi*8]
0x180007489  shl     rcx, 4
0x18000748d  add     rdx, rcx; struct tagHELPER_ATTRIBUTE *
0x180007490  add     rcx, rdi; this
0x180007493  call    ?Copy@_attribute_t@@QEAAJPEBUtagHELPER_ATTRIBUTE@@@Z; _attribute_t::Copy(tagHELPER_ATTRIBUTE const *)
0x180007498  inc     esi
0x18000749a  cmp     esi, [rbx+18h]
0x18000749d  jb      short loc_180007481
0x18000749f  mov     [r15], ebp
0x1800074a2  lea     rcx, [rsp+68h+var_48]; this
0x1800074a7  mov     [r14], rdi
0x1800074aa  mov     [rsp+68h+var_40], 0
0x1800074b3  call    ?FreeElements@_attributes_array_t@@QEAAXXZ; _attributes_array_t::FreeElements(void)
0x1800074b8  xor     ecx, ecx; pv
0x1800074ba  call    cs:__imp_CoTaskMemFree
0x1800074c0  xor     ebx, ebx
0x1800074c2  jmp     short loc_1800074C9
0x1800074c4  mov     ebx, 80070057h
0x1800074c9  mov     eax, ebx
0x1800074cb  add     rsp, 38h
0x1800074cf  pop     r15
0x1800074d1  pop     r14
0x1800074d3  pop     rdi
0x1800074d4  pop     rsi
0x1800074d5  pop     rbp
0x1800074d6  pop     rbx
0x1800074d7  retn
```
