# BdeCfgpGetExtendedPartitionExtent(IVdsDisk *,unsigned __int64 *,unsigned __int64 *)

- ea: `0x180006234`
- end: `0x180006345`
- name: `?BdeCfgpGetExtendedPartitionExtent@@YAJPEAUIVdsDisk@@PEA_K1@Z`
- size: `273`
- prototype: `__int64 __fastcall(struct IVdsDisk *, unsigned __int64 *, unsigned __int64 *)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180003580`
- `0x180003bc0`
- `0x180005578`
- `0x180006738`

## callees

- `0x180006234`
- `0x180015010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180006334`
- `ole32!CoTaskMemFree` at `0x180006334`

## pseudocode

```c
__int64 __fastcall BdeCfgpGetExtendedPartitionExtent(struct IVdsDisk *a1, unsigned __int64 *a2, unsigned __int64 *a3)
{
  struct IVdsDiskVtbl *lpVtbl; // rax
  int v7; // ebx
  int v8; // r8d
  _QWORD *v9; // rcx
  char v10; // al
  __int64 v11; // [rsp+20h] [rbp-18h] BYREF
  LPVOID pv[2]; // [rsp+28h] [rbp-10h] BYREF
  int v13; // [rsp+78h] [rbp+40h] BYREF

  v11 = 0;
  pv[0] = 0;
  v13 = 0;
  if ( !g_pService )
    return 3231711254LL;
  lpVtbl = a1->lpVtbl;
  *a2 = 0;
  *a3 = 0;
  v7 = ((__int64 (__fastcall *)(struct IVdsDisk *, GUID *, __int64 *))lpVtbl->QueryInterface)(
         a1,
         &IID_IVdsAdvancedDisk,
         &v11);
  if ( v7 < 0
    || (v7 = (*(__int64 (__fastcall **)(__int64, LPVOID *, int *))(*(_QWORD *)v11 + 32LL))(v11, pv, &v13), v7 < 0)
    || (v8 = 0, v7 = 1, v13 <= 0) )
  {
    v9 = pv[0];
  }
  else
  {
    v9 = pv[0];
    while ( 1 )
    {
      if ( *((_DWORD *)pv[0] + 36 * v8) == 1 )
      {
        v10 = *((_BYTE *)pv[0] + 144 * v8 + 32);
        if ( v10 == 5 || v10 == 15 )
          break;
      }
      if ( ++v8 >= v13 )
        goto LABEL_14;
    }
    v7 = 0;
    *a2 = *((_QWORD *)pv[0] + 18 * v8 + 2);
    *a3 = v9[18 * v8 + 3];
  }
LABEL_14:
  if ( v11 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    v9 = pv[0];
    v11 = 0;
  }
  if ( v9 )
    CoTaskMemFree(v9);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180006234  push    rbp
0x180006236  push    rbx
0x180006237  push    rsi
0x180006238  push    rdi
0x180006239  mov     rbp, rsp
0x18000623c  sub     rsp, 38h
0x180006240  cmp     cs:?g_pService@@3PEAUIVdsService@@EA, 0; IVdsService * g_pService
0x180006248  mov     rdi, r8
0x18000624b  mov     rsi, rdx
0x18000624e  mov     [rbp+var_18], 0
0x180006256  mov     [rbp+pv], 0
0x18000625e  mov     [rbp+arg_18], 0
0x180006265  jnz     short loc_180006271
0x180006267  mov     eax, 0C0A00016h
0x18000626c  jmp     loc_18000633C
0x180006271  mov     rax, [rcx]
0x180006274  mov     qword ptr [rdx], 0
0x18000627b  lea     rdx, IID_IVdsAdvancedDisk
0x180006282  mov     qword ptr [r8], 0
0x180006289  lea     r8, [rbp+var_18]
0x18000628d  mov     rax, [rax]
0x180006290  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006295  mov     ebx, eax
0x180006297  test    eax, eax
0x180006299  js      short loc_180006307
0x18000629b  mov     rcx, [rbp+var_18]
0x18000629f  lea     r8, [rbp+arg_18]
0x1800062a3  lea     rdx, [rbp+pv]
0x1800062a7  mov     rax, [rcx]
0x1800062aa  mov     rax, [rax+20h]
0x1800062ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062b3  mov     ebx, eax
0x1800062b5  test    eax, eax
0x1800062b7  js      short loc_180006307
0x1800062b9  mov     r9d, [rbp+arg_18]
0x1800062bd  xor     r8d, r8d
0x1800062c0  mov     ebx, 1
0x1800062c5  test    r9d, r9d
0x1800062c8  jle     short loc_180006307
0x1800062ca  mov     rcx, [rbp+pv]
0x1800062ce  movsxd  rax, r8d
0x1800062d1  lea     rdx, [rax+rax*8]
0x1800062d5  add     rdx, rdx
0x1800062d8  cmp     [rcx+rdx*8], ebx
0x1800062db  jnz     short loc_1800062E9
0x1800062dd  mov     al, [rcx+rdx*8+20h]
0x1800062e1  cmp     al, 5
0x1800062e3  jz      short loc_1800062F3
0x1800062e5  cmp     al, 0Fh
0x1800062e7  jz      short loc_1800062F3
0x1800062e9  add     r8d, ebx
0x1800062ec  cmp     r8d, r9d
0x1800062ef  jl      short loc_1800062CE
0x1800062f1  jmp     short loc_18000630B
0x1800062f3  mov     rax, [rcx+rdx*8+10h]
0x1800062f8  xor     ebx, ebx
0x1800062fa  mov     [rsi], rax
0x1800062fd  mov     rax, [rcx+rdx*8+18h]
0x180006302  mov     [rdi], rax
0x180006305  jmp     short loc_18000630B
0x180006307  mov     rcx, [rbp+pv]
0x18000630b  mov     rdx, [rbp+var_18]
0x18000630f  test    rdx, rdx
0x180006312  jz      short loc_18000632F
0x180006314  mov     rax, [rdx]
0x180006317  mov     rcx, rdx
0x18000631a  mov     rax, [rax+10h]
0x18000631e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006323  mov     rcx, [rbp+pv]; pv
0x180006327  mov     [rbp+var_18], 0
0x18000632f  test    rcx, rcx
0x180006332  jz      short loc_18000633A
0x180006334  call    cs:__imp_CoTaskMemFree
0x18000633a  mov     eax, ebx
0x18000633c  add     rsp, 38h
0x180006340  pop     rdi
0x180006341  pop     rsi
0x180006342  pop     rbx
0x180006343  pop     rbp
0x180006344  retn
```
