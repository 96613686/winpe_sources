# FreeProvisionData(_MVProvisionData *)

- ea: `0x180009354`
- end: `0x180009420`
- name: `?FreeProvisionData@@YAXPEAU_MVProvisionData@@@Z`
- size: `204`
- prototype: `void __fastcall(struct _MVProvisionData *)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008f38`
- `0x18000ccdc`
- `0x18000f5c0`

## callees

- `0x180009354`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800093a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800093ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800093bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800093d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800093e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800093f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009407`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800093a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800093ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800093bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800093d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800093e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800093f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009407`

## pseudocode

```c
void __fastcall FreeProvisionData(struct _MVProvisionData *a1)
{
  _QWORD *v2; // rdi
  unsigned int v3; // ebp
  __int64 i; // rsi
  __int64 v5; // rcx

  if ( a1 )
  {
    v2 = (_QWORD *)*((_QWORD *)a1 + 3);
    if ( v2 )
    {
      v3 = *((_DWORD *)a1 + 8);
      for ( i = 0; (unsigned int)i < v3; i = (unsigned int)(i + 1) )
      {
        v5 = v2[i];
        if ( v5 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
          v2[i] = 0;
        }
      }
      CoTaskMemFree(v2);
    }
    CoTaskMemFree(*((LPVOID *)a1 + 1));
    *((_QWORD *)a1 + 1) = 0;
    CoTaskMemFree(*((LPVOID *)a1 + 2));
    *((_QWORD *)a1 + 2) = 0;
    CoTaskMemFree(*((LPVOID *)a1 + 5));
    *((_QWORD *)a1 + 5) = 0;
    CoTaskMemFree(*((LPVOID *)a1 + 7));
    *((_QWORD *)a1 + 7) = 0;
    CoTaskMemFree(*((LPVOID *)a1 + 8));
    *((_QWORD *)a1 + 8) = 0;
    CoTaskMemFree(*((LPVOID *)a1 + 6));
    *((_QWORD *)a1 + 6) = 0;
  }
}

```

## disassembly

```asm
0x180009354  test    rcx, rcx
0x180009357  jz      locret_18000941F
0x18000935d  push    rbx
0x18000935e  push    rbp
0x18000935f  push    rsi
0x180009360  push    rdi
0x180009361  push    r14
0x180009363  sub     rsp, 20h
0x180009367  mov     rbx, rcx
0x18000936a  mov     rdi, [rcx+18h]
0x18000936e  test    rdi, rdi
0x180009371  jz      short loc_1800093A9
0x180009373  mov     ebp, [rcx+20h]
0x180009376  xor     esi, esi
0x180009378  test    ebp, ebp
0x18000937a  jz      short loc_18000939F
0x18000937c  mov     rcx, [rdi+rsi*8]
0x180009380  test    rcx, rcx
0x180009383  jz      short loc_180009399
0x180009385  mov     rax, [rcx]
0x180009388  mov     rax, [rax+10h]
0x18000938c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009391  mov     qword ptr [rdi+rsi*8], 0
0x180009399  inc     esi
0x18000939b  cmp     esi, ebp
0x18000939d  jb      short loc_18000937C
0x18000939f  mov     rcx, rdi; pv
0x1800093a2  call    cs:__imp_CoTaskMemFree
0x1800093a8  nop
0x1800093a9  mov     rcx, [rbx+8]; pv
0x1800093ad  call    cs:__imp_CoTaskMemFree
0x1800093b3  mov     qword ptr [rbx+8], 0
0x1800093bb  mov     rcx, [rbx+10h]; pv
0x1800093bf  call    cs:__imp_CoTaskMemFree
0x1800093c5  mov     qword ptr [rbx+10h], 0
0x1800093cd  mov     rcx, [rbx+28h]; pv
0x1800093d1  call    cs:__imp_CoTaskMemFree
0x1800093d7  mov     qword ptr [rbx+28h], 0
0x1800093df  mov     rcx, [rbx+38h]; pv
0x1800093e3  call    cs:__imp_CoTaskMemFree
0x1800093e9  mov     qword ptr [rbx+38h], 0
0x1800093f1  mov     rcx, [rbx+40h]; pv
0x1800093f5  call    cs:__imp_CoTaskMemFree
0x1800093fb  mov     qword ptr [rbx+40h], 0
0x180009403  mov     rcx, [rbx+30h]; pv
0x180009407  call    cs:__imp_CoTaskMemFree
0x18000940d  mov     qword ptr [rbx+30h], 0
0x180009415  add     rsp, 20h
0x180009419  pop     r14
0x18000941b  pop     rdi
0x18000941c  pop     rsi
0x18000941d  pop     rbp
0x18000941e  pop     rbx
0x18000941f  retn
```
