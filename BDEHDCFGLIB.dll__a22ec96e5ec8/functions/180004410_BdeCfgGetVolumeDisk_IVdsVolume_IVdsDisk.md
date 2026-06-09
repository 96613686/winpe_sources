# BdeCfgGetVolumeDisk(IVdsVolume *,IVdsDisk * *)

- ea: `0x180004410`
- end: `0x180004610`
- name: `?BdeCfgGetVolumeDisk@@YAJPEAUIVdsVolume@@PEAPEAUIVdsDisk@@@Z`
- size: `512`
- prototype: `__int64 __fastcall(struct IVdsVolume *, struct IVdsDisk **)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180003f68`
- `0x18000f430`
- `0x18000fb40`
- `0x1800101a0`

## callees

- `0x180004410`
- `0x180015010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800045f1`
- `ole32!CoTaskMemFree` at `0x1800045f1`

## pseudocode

```c
__int64 __fastcall BdeCfgGetVolumeDisk(struct IVdsVolume *a1, struct IVdsDisk **a2)
{
  int v4; // ebx
  int v5; // eax
  __int64 v6; // rcx
  __int64 v7; // [rsp+30h] [rbp-30h] BYREF
  __int64 v8; // [rsp+38h] [rbp-28h] BYREF
  __int64 v9; // [rsp+40h] [rbp-20h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-18h] BYREF
  __int128 v11; // [rsp+50h] [rbp-10h] BYREF
  int v12; // [rsp+80h] [rbp+20h] BYREF
  int v13; // [rsp+88h] [rbp+28h] BYREF

  pv = 0;
  v9 = 0;
  v7 = 0;
  v8 = 0;
  v13 = 0;
  v12 = 0;
  if ( !g_pService )
    return 3231711254LL;
  v4 = ((__int64 (__fastcall *)(struct IVdsVolume *, __int64 *))a1->lpVtbl->QueryPlexes)(a1, &v9);
  if ( v4 >= 0 )
  {
    v4 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v9 + 24LL))(v9, 1, &v8, &v13);
    if ( v4 >= 0 )
    {
      v4 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v8)(v8, &IID_IVdsVolumePlex, &v7);
      if ( v8 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
        v8 = 0;
      }
      if ( v4 >= 0 )
      {
        v5 = (*(__int64 (__fastcall **)(__int64, LPVOID *, int *))(*(_QWORD *)v7 + 40LL))(v7, &pv, &v12);
        v6 = v7;
        v4 = v5;
        if ( v7 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
          v6 = 0;
          v7 = 0;
        }
        if ( v4 < 0 )
          goto LABEL_17;
        if ( v12 != 1 || !pv )
        {
          v4 = -1063256055;
          goto LABEL_17;
        }
        v11 = *(_OWORD *)pv;
        v4 = ((__int64 (__fastcall *)(struct IVdsService *, __int128 *, __int64, __int64 *))g_pService->lpVtbl->GetObjectA)(
               g_pService,
               &v11,
               13,
               &v8);
        if ( v4 >= 0 )
        {
          v4 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IVdsDisk **))v8)(v8, &IID_IVdsDisk, a2);
          if ( v8 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
            v8 = 0;
          }
        }
      }
    }
  }
  v6 = v7;
LABEL_17:
  if ( v9 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    v6 = v7;
    v9 = 0;
  }
  if ( v6 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    v7 = 0;
  }
  if ( pv )
    CoTaskMemFree(pv);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180004410  mov     [rsp-8+arg_0], rbx
0x180004415  mov     [rsp-8+arg_8], rdi
0x18000441a  push    rbp
0x18000441b  mov     rbp, rsp
0x18000441e  sub     rsp, 60h
0x180004422  cmp     cs:?g_pService@@3PEAUIVdsService@@EA, 0; IVdsService * g_pService
0x18000442a  mov     rdi, rdx
0x18000442d  mov     [rbp+pv], 0
0x180004435  mov     [rbp+var_20], 0
0x18000443d  mov     [rbp+var_30], 0
0x180004445  mov     [rbp+var_28], 0
0x18000444d  mov     [rbp+arg_18], 0
0x180004454  mov     [rbp+arg_10], 0
0x18000445b  jnz     short loc_180004467
0x18000445d  mov     eax, 0C0A00016h
0x180004462  jmp     loc_1800045F9
0x180004467  mov     rax, [rcx]
0x18000446a  lea     rdx, [rbp+var_20]
0x18000446e  mov     rax, [rax+28h]
0x180004472  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004477  mov     ebx, eax
0x180004479  test    eax, eax
0x18000447b  js      loc_1800045A4
0x180004481  mov     rcx, [rbp+var_20]
0x180004485  lea     r9, [rbp+arg_18]
0x180004489  lea     r8, [rbp+var_28]
0x18000448d  mov     edx, 1
0x180004492  mov     rax, [rcx]
0x180004495  mov     rax, [rax+18h]
0x180004499  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000449e  mov     ebx, eax
0x1800044a0  test    eax, eax
0x1800044a2  js      loc_1800045A4
0x1800044a8  mov     rcx, [rbp+var_28]
0x1800044ac  lea     r8, [rbp+var_30]
0x1800044b0  lea     rdx, IID_IVdsVolumePlex
0x1800044b7  mov     rax, [rcx]
0x1800044ba  mov     rax, [rax]
0x1800044bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044c2  mov     rcx, [rbp+var_28]
0x1800044c6  mov     ebx, eax
0x1800044c8  test    rcx, rcx
0x1800044cb  jz      short loc_1800044E1
0x1800044cd  mov     rax, [rcx]
0x1800044d0  mov     rax, [rax+10h]
0x1800044d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044d9  mov     [rbp+var_28], 0
0x1800044e1  test    ebx, ebx
0x1800044e3  js      loc_1800045A4
0x1800044e9  mov     rcx, [rbp+var_30]
0x1800044ed  lea     r8, [rbp+arg_10]
0x1800044f1  lea     rdx, [rbp+pv]
0x1800044f5  mov     rax, [rcx]
0x1800044f8  mov     rax, [rax+28h]
0x1800044fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004501  mov     rcx, [rbp+var_30]
0x180004505  mov     ebx, eax
0x180004507  test    rcx, rcx
0x18000450a  jz      short loc_18000451E
0x18000450c  mov     rax, [rcx]
0x18000450f  mov     rax, [rax+10h]
0x180004513  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004518  xor     ecx, ecx
0x18000451a  mov     [rbp+var_30], rcx
0x18000451e  test    ebx, ebx
0x180004520  js      loc_1800045A8
0x180004526  cmp     [rbp+arg_10], 1
0x18000452a  jnz     loc_180004609
0x180004530  mov     rax, [rbp+pv]
0x180004534  test    rax, rax
0x180004537  jz      loc_180004609
0x18000453d  movups  xmm0, xmmword ptr [rax]
0x180004540  mov     rcx, cs:?g_pService@@3PEAUIVdsService@@EA; IVdsService * g_pService
0x180004547  lea     r9, [rbp+var_28]
0x18000454b  mov     r8d, 0Dh
0x180004551  lea     rdx, [rbp+var_10]
0x180004555  movdqu  [rbp+var_10], xmm0
0x18000455a  mov     rax, [rcx]
0x18000455d  mov     rax, [rax+48h]
0x180004561  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004566  mov     ebx, eax
0x180004568  test    eax, eax
0x18000456a  js      short loc_1800045A4
0x18000456c  mov     rcx, [rbp+var_28]
0x180004570  lea     rdx, IID_IVdsDisk
0x180004577  mov     r8, rdi
0x18000457a  mov     rax, [rcx]
0x18000457d  mov     rax, [rax]
0x180004580  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004585  mov     rcx, [rbp+var_28]
0x180004589  mov     ebx, eax
0x18000458b  test    rcx, rcx
0x18000458e  jz      short loc_1800045A4
0x180004590  mov     rax, [rcx]
0x180004593  mov     rax, [rax+10h]
0x180004597  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000459c  mov     [rbp+var_28], 0
0x1800045a4  mov     rcx, [rbp+var_30]
0x1800045a8  mov     rdx, [rbp+var_20]
0x1800045ac  test    rdx, rdx
0x1800045af  jz      short loc_1800045CC
0x1800045b1  mov     rax, [rdx]
0x1800045b4  mov     rcx, rdx
0x1800045b7  mov     rax, [rax+10h]
0x1800045bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045c0  mov     rcx, [rbp+var_30]
0x1800045c4  mov     [rbp+var_20], 0
0x1800045cc  test    rcx, rcx
0x1800045cf  jz      short loc_1800045E5
0x1800045d1  mov     rax, [rcx]
0x1800045d4  mov     rax, [rax+10h]
0x1800045d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045dd  mov     [rbp+var_30], 0
0x1800045e5  mov     rax, [rbp+pv]
0x1800045e9  test    rax, rax
0x1800045ec  jz      short loc_1800045F7
0x1800045ee  mov     rcx, rax; pv
0x1800045f1  call    cs:__imp_CoTaskMemFree
0x1800045f7  mov     eax, ebx
0x1800045f9  mov     rbx, [rsp+60h+arg_0]
0x1800045fe  mov     rdi, [rsp+60h+arg_8]
0x180004603  add     rsp, 60h
0x180004607  pop     rbp
0x180004608  retn
0x180004609  mov     ebx, 0C0A00009h
0x18000460e  jmp     short loc_1800045A8
```
