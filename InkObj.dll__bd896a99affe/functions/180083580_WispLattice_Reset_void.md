# WispLattice::Reset(void)

- ea: `0x180083580`
- end: `0x1800836ab`
- name: `?Reset@WispLattice@@QEAAXXZ`
- size: `299`
- prototype: `void __fastcall(WispLattice *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800405a4`
- `0x18007f918`
- `0x18007fac0`
- `0x18007fb14`
- `0x18007fddc`
- `0x1800a4064`

## callees

- `0x180083580`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180083592`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800835a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800835c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800835de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800835fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008360f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180083621`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180083633`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008363c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180083652`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180083669`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180083680`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180083697`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180083592`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800835a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800835c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800835de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800835fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008360f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180083621`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180083633`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008363c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180083652`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180083669`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180083680`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180083697`

## pseudocode

```c
void __fastcall WispLattice::Reset(WispLattice *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  void *v11; // rcx
  void *v12; // rcx
  void *v13; // rcx

  v2 = (void *)*((_QWORD *)this + 1);
  if ( v2 )
  {
    CoTaskMemFree(v2);
    *((_QWORD *)this + 1) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 2);
  if ( v3 )
  {
    CoTaskMemFree(v3);
    *((_QWORD *)this + 2) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 3);
  if ( v4 )
  {
    CoTaskMemFree(v4);
    *((_QWORD *)this + 3) = 0;
    *((_DWORD *)this + 21) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 6);
  if ( v5 )
  {
    CoTaskMemFree(v5);
    *((_QWORD *)this + 6) = 0;
  }
  if ( *(_QWORD *)this )
  {
    v6 = *(void **)(*(_QWORD *)this + 8LL);
    if ( v6 )
      CoTaskMemFree(v6);
    v7 = *(void **)(*(_QWORD *)this + 40LL);
    if ( v7 )
      CoTaskMemFree(v7);
    v8 = *(void **)(*(_QWORD *)this + 48LL);
    if ( v8 )
      CoTaskMemFree(v8);
    v9 = *(void **)(*(_QWORD *)this + 24LL);
    if ( v9 )
      CoTaskMemFree(v9);
    CoTaskMemFree(*(LPVOID *)this);
    *(_QWORD *)this = 0;
  }
  v10 = (void *)*((_QWORD *)this + 8);
  if ( v10 )
  {
    CoTaskMemFree(v10);
    *((_QWORD *)this + 8) = 0;
  }
  v11 = (void *)*((_QWORD *)this + 9);
  if ( v11 )
  {
    CoTaskMemFree(v11);
    *((_QWORD *)this + 9) = 0;
  }
  v12 = (void *)*((_QWORD *)this + 4);
  if ( v12 )
  {
    CoTaskMemFree(v12);
    *((_QWORD *)this + 4) = 0;
  }
  v13 = (void *)*((_QWORD *)this + 5);
  if ( v13 )
  {
    CoTaskMemFree(v13);
    *((_QWORD *)this + 5) = 0;
  }
}

```

## disassembly

```asm
0x180083580  push    rbx
0x180083582  sub     rsp, 20h
0x180083586  mov     rbx, rcx
0x180083589  mov     rcx, [rcx+8]; pv
0x18008358d  test    rcx, rcx
0x180083590  jz      short loc_1800835A0
0x180083592  call    cs:__imp_CoTaskMemFree
0x180083598  mov     qword ptr [rbx+8], 0
0x1800835a0  mov     rcx, [rbx+10h]; pv
0x1800835a4  test    rcx, rcx
0x1800835a7  jz      short loc_1800835B7
0x1800835a9  call    cs:__imp_CoTaskMemFree
0x1800835af  mov     qword ptr [rbx+10h], 0
0x1800835b7  mov     rcx, [rbx+18h]; pv
0x1800835bb  test    rcx, rcx
0x1800835be  jz      short loc_1800835D5
0x1800835c0  call    cs:__imp_CoTaskMemFree
0x1800835c6  mov     qword ptr [rbx+18h], 0
0x1800835ce  mov     dword ptr [rbx+54h], 0
0x1800835d5  mov     rcx, [rbx+30h]; pv
0x1800835d9  test    rcx, rcx
0x1800835dc  jz      short loc_1800835EC
0x1800835de  call    cs:__imp_CoTaskMemFree
0x1800835e4  mov     qword ptr [rbx+30h], 0
0x1800835ec  mov     rax, [rbx]
0x1800835ef  test    rax, rax
0x1800835f2  jz      short loc_180083649
0x1800835f4  mov     rcx, [rax+8]; pv
0x1800835f8  test    rcx, rcx
0x1800835fb  jz      short loc_180083603
0x1800835fd  call    cs:__imp_CoTaskMemFree
0x180083603  mov     rax, [rbx]
0x180083606  mov     rcx, [rax+28h]; pv
0x18008360a  test    rcx, rcx
0x18008360d  jz      short loc_180083615
0x18008360f  call    cs:__imp_CoTaskMemFree
0x180083615  mov     rax, [rbx]
0x180083618  mov     rcx, [rax+30h]; pv
0x18008361c  test    rcx, rcx
0x18008361f  jz      short loc_180083627
0x180083621  call    cs:__imp_CoTaskMemFree
0x180083627  mov     rax, [rbx]
0x18008362a  mov     rcx, [rax+18h]; pv
0x18008362e  test    rcx, rcx
0x180083631  jz      short loc_180083639
0x180083633  call    cs:__imp_CoTaskMemFree
0x180083639  mov     rcx, [rbx]; pv
0x18008363c  call    cs:__imp_CoTaskMemFree
0x180083642  mov     qword ptr [rbx], 0
0x180083649  mov     rcx, [rbx+40h]; pv
0x18008364d  test    rcx, rcx
0x180083650  jz      short loc_180083660
0x180083652  call    cs:__imp_CoTaskMemFree
0x180083658  mov     qword ptr [rbx+40h], 0
0x180083660  mov     rcx, [rbx+48h]; pv
0x180083664  test    rcx, rcx
0x180083667  jz      short loc_180083677
0x180083669  call    cs:__imp_CoTaskMemFree
0x18008366f  mov     qword ptr [rbx+48h], 0
0x180083677  mov     rcx, [rbx+20h]; pv
0x18008367b  test    rcx, rcx
0x18008367e  jz      short loc_18008368E
0x180083680  call    cs:__imp_CoTaskMemFree
0x180083686  mov     qword ptr [rbx+20h], 0
0x18008368e  mov     rcx, [rbx+28h]; pv
0x180083692  test    rcx, rcx
0x180083695  jz      short loc_1800836A5
0x180083697  call    cs:__imp_CoTaskMemFree
0x18008369d  mov     qword ptr [rbx+28h], 0
0x1800836a5  add     rsp, 20h
0x1800836a9  pop     rbx
0x1800836aa  retn
```
