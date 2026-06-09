# CWfHelperClass::~CWfHelperClass(void)

- ea: `0x180002880`
- end: `0x1800029dc`
- name: `??1CWfHelperClass@@QEAA@XZ`
- size: `348`
- prototype: `void __fastcall(CWfHelperClass *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180002a80`

## callees

- `0x180002880`
- `0x180003b60`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000293e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002989`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000293e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002989`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800029a5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800029a5`
- `FirewallAPI!FwFree` at `0x1800028e5`
- `FirewallAPI!FwFree` at `0x180002931`
- `FirewallAPI!FwFree` at `0x1800028e5`
- `FirewallAPI!FwFree` at `0x180002931`

## pseudocode

```c
void __fastcall CWfHelperClass::~CWfHelperClass(CWfHelperClass *this)
{
  __int64 v2; // rbp
  unsigned int v3; // r14d
  unsigned int i; // edi
  __int64 v5; // rbx
  __int64 v6; // rcx
  __int64 v7; // rcx

  v2 = *((_QWORD *)this + 20);
  if ( v2 )
  {
    v3 = *((_DWORD *)this + 42);
    for ( i = 0; i < v3; ++i )
    {
      v5 = 152LL * i;
      switch ( *(_DWORD *)(v5 + v2 + 4) )
      {
        case 0:
        case 1:
        case 2:
        case 4:
        case 5:
        case 7:
          FwFree(*(_QWORD *)(v5 + v2 + 16));
          break;
        default:
          break;
      }
      *(_OWORD *)(v5 + v2) = 0;
      *(_OWORD *)(v5 + v2 + 16) = 0;
      *(_OWORD *)(v5 + v2 + 32) = 0;
      *(_OWORD *)(v5 + v2 + 48) = 0;
      *(_OWORD *)(v5 + v2 + 64) = 0;
      *(_OWORD *)(v5 + v2 + 80) = 0;
      *(_OWORD *)(v5 + v2 + 96) = 0;
      *(_OWORD *)(v5 + v2 + 112) = 0;
      *(_OWORD *)(v5 + v2 + 128) = 0;
      *(_QWORD *)(v5 + v2 + 144) = 0;
    }
    FwFree(v2);
  }
  CoTaskMemFree(*((LPVOID *)this + 24));
  v6 = *((_QWORD *)this + 15);
  if ( v6 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    *((_QWORD *)this + 15) = 0;
  }
  v7 = *((_QWORD *)this + 18);
  if ( v7 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    *((_QWORD *)this + 18) = 0;
  }
  _attributes_array_t::FreeElements((CWfHelperClass *)((char *)this + 24));
  CoTaskMemFree(*((LPVOID *)this + 4));
  *((_QWORD *)this + 4) = 0;
  *((_DWORD *)this + 6) = 0;
  if ( *((_BYTE *)this + 112) )
  {
    *((_BYTE *)this + 112) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  }
}

```

## disassembly

```asm
0x180002880  push    rbx
0x180002882  push    rbp
0x180002883  push    rsi
0x180002884  push    rdi
0x180002885  push    r12
0x180002887  push    r14
0x180002889  push    r15
0x18000288b  sub     rsp, 20h
0x18000288f  mov     rsi, rcx
0x180002892  mov     rbp, [rcx+0A0h]
0x180002899  xor     r12d, r12d
0x18000289c  test    rbp, rbp
0x18000289f  jz      loc_180002937
0x1800028a5  mov     r14d, [rcx+0A8h]
0x1800028ac  mov     edi, r12d
0x1800028af  test    r14d, r14d
0x1800028b2  jz      short loc_18000292E
0x1800028b4  lea     r15, cs:180000000h
0x1800028bb  nop     dword ptr [rax+rax+00h]
0x1800028c0  mov     eax, edi
0x1800028c2  imul    rbx, rax, 98h
0x1800028c9  movsxd  rax, dword ptr [rbx+rbp+4]
0x1800028ce  cmp     eax, 7; switch 8 cases
0x1800028d1  ja      short def_1800028DE; jumptable 00000001800028DE default case, cases 3,6
0x1800028d3  mov     ecx, ds:(jpt_1800028DE - 180000000h)[r15+rax*4]
0x1800028db  add     rcx, r15
0x1800028de  jmp     rcx; switch jump
0x1800028e0  mov     rcx, [rbx+rbp+10h]; jumptable 00000001800028DE cases 0-2,4,5,7
0x1800028e5  call    cs:__imp_FwFree
0x1800028eb  xorps   xmm0, xmm0; jumptable 00000001800028DE default case, cases 3,6
0x1800028ee  xor     eax, eax
0x1800028f0  movups  xmmword ptr [rbx+rbp], xmm0
0x1800028f4  movups  xmmword ptr [rbx+rbp+10h], xmm0
0x1800028f9  movups  xmmword ptr [rbx+rbp+20h], xmm0
0x1800028fe  movups  xmmword ptr [rbx+rbp+30h], xmm0
0x180002903  movups  xmmword ptr [rbx+rbp+40h], xmm0
0x180002908  movups  xmmword ptr [rbx+rbp+50h], xmm0
0x18000290d  movups  xmmword ptr [rbx+rbp+60h], xmm0
0x180002912  movups  xmmword ptr [rbx+rbp+70h], xmm0
0x180002917  movups  xmmword ptr [rbx+rbp+80h], xmm0
0x18000291f  mov     [rbx+rbp+90h], rax
0x180002927  inc     edi
0x180002929  cmp     edi, r14d
0x18000292c  jb      short loc_1800028C0
0x18000292e  mov     rcx, rbp
0x180002931  call    cs:__imp_FwFree
0x180002937  mov     rcx, [rsi+0C0h]; pv
0x18000293e  call    cs:__imp_CoTaskMemFree
0x180002944  mov     rcx, [rsi+78h]
0x180002948  test    rcx, rcx
0x18000294b  jz      short loc_18000295D
0x18000294d  mov     rax, [rcx]
0x180002950  mov     rax, [rax+10h]
0x180002954  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002959  mov     [rsi+78h], r12
0x18000295d  mov     rcx, [rsi+90h]
0x180002964  test    rcx, rcx
0x180002967  jz      short loc_18000297C
0x180002969  mov     rax, [rcx]
0x18000296c  mov     rax, [rax+10h]
0x180002970  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002975  mov     [rsi+90h], r12
0x18000297c  lea     rcx, [rsi+18h]; this
0x180002980  call    ?FreeElements@_attributes_array_t@@QEAAXXZ; _attributes_array_t::FreeElements(void)
0x180002985  mov     rcx, [rsi+20h]; pv
0x180002989  call    cs:__imp_CoTaskMemFree
0x18000298f  mov     [rsi+20h], r12
0x180002993  mov     [rsi+18h], r12d
0x180002997  lea     rcx, [rsi+48h]; lpCriticalSection
0x18000299b  cmp     [rcx+28h], r12b
0x18000299f  jz      short loc_1800029AC
0x1800029a1  mov     [rcx+28h], r12b
0x1800029a5  call    cs:__imp_DeleteCriticalSection
0x1800029ab  nop
0x1800029ac  add     rsp, 20h
0x1800029b0  pop     r15
0x1800029b2  pop     r14
0x1800029b4  pop     r12
0x1800029b6  pop     rdi
0x1800029b7  pop     rsi
0x1800029b8  pop     rbp
0x1800029b9  pop     rbx
0x1800029ba  retn
```
