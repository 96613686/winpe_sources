# FreeCDPComDeviceInfo

- ea: `0x1800337e0`
- end: `0x180033906`
- name: `FreeCDPComDeviceInfo`
- size: `294`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180033b10`

## callees

- `0x1800337e0`
- `0x18003390c`
- `0x180033994`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800337f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033806`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033818`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003382a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003383c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033871`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800338ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800338c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800338d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800338e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800337f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033806`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033818`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003382a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003383c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033871`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800338ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800338c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800338d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800338e8`

## pseudocode

```c
void __fastcall FreeCDPComDeviceInfo(__int64 a1)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  __int64 v6; // rax
  __int64 v7; // rdi
  __int64 v8; // rsi
  __int64 v9; // rdi
  __int64 v10; // rax
  __int64 v11; // rsi
  void *v12; // rcx
  void *v13; // rcx
  void *v14; // rcx

  CoTaskMemFree(*(LPVOID *)a1);
  v2 = *(void **)(a1 + 8);
  *(_QWORD *)a1 = 0;
  CoTaskMemFree(v2);
  v3 = *(void **)(a1 + 40);
  *(_QWORD *)(a1 + 8) = 0;
  CoTaskMemFree(v3);
  v4 = *(void **)(a1 + 64);
  *(_QWORD *)(a1 + 40) = 0;
  CoTaskMemFree(v4);
  v5 = *(void **)(a1 + 72);
  *(_QWORD *)(a1 + 64) = 0;
  CoTaskMemFree(v5);
  v6 = *(unsigned __int16 *)(a1 + 24);
  v7 = *(_QWORD *)(a1 + 16);
  *(_QWORD *)(a1 + 72) = 0;
  v8 = v7 + 40 * v6;
  while ( v7 != v8 )
  {
    FreeCDPComEndpoint(v7);
    v7 += 40;
  }
  CoTaskMemFree(*(LPVOID *)(a1 + 16));
  v9 = *(_QWORD *)(a1 + 88);
  *(_WORD *)(a1 + 24) = 0;
  v10 = *(unsigned __int16 *)(a1 + 96);
  *(_QWORD *)(a1 + 16) = 0;
  v11 = v9 + 40 * v10;
  while ( v9 != v11 )
  {
    FreeCDPComResource(v9);
    v9 += 40;
  }
  CoTaskMemFree(*(LPVOID *)(a1 + 88));
  v12 = *(void **)(a1 + 104);
  *(_WORD *)(a1 + 96) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  CoTaskMemFree(v12);
  v13 = *(void **)(a1 + 80);
  *(_QWORD *)(a1 + 104) = 0;
  CoTaskMemFree(v13);
  v14 = *(void **)(a1 + 112);
  *(_QWORD *)(a1 + 80) = 0;
  CoTaskMemFree(v14);
  *(_QWORD *)(a1 + 112) = 0;
}

```

## disassembly

```asm
0x1800337e0  mov     [rsp+arg_0], rbx
0x1800337e5  mov     [rsp+arg_8], rsi
0x1800337ea  push    rdi
0x1800337eb  sub     rsp, 20h
0x1800337ef  mov     rbx, rcx
0x1800337f2  mov     rcx, [rcx]; pv
0x1800337f5  call    cs:__imp_CoTaskMemFree
0x1800337fb  mov     rcx, [rbx+8]; pv
0x1800337ff  mov     qword ptr [rbx], 0
0x180033806  call    cs:__imp_CoTaskMemFree
0x18003380c  mov     rcx, [rbx+28h]; pv
0x180033810  mov     qword ptr [rbx+8], 0
0x180033818  call    cs:__imp_CoTaskMemFree
0x18003381e  mov     rcx, [rbx+40h]; pv
0x180033822  mov     qword ptr [rbx+28h], 0
0x18003382a  call    cs:__imp_CoTaskMemFree
0x180033830  mov     rcx, [rbx+48h]; pv
0x180033834  mov     qword ptr [rbx+40h], 0
0x18003383c  call    cs:__imp_CoTaskMemFree
0x180033842  movzx   eax, word ptr [rbx+18h]
0x180033846  mov     rdi, [rbx+10h]
0x18003384a  mov     qword ptr [rbx+48h], 0
0x180033852  lea     rcx, [rax+rax*4]
0x180033856  lea     rsi, [rdi+rcx*8]
0x18003385a  jmp     short loc_180033868
0x18003385c  mov     rcx, rdi
0x18003385f  call    FreeCDPComEndpoint
0x180033864  add     rdi, 28h ; '('
0x180033868  cmp     rdi, rsi
0x18003386b  jnz     short loc_18003385C
0x18003386d  mov     rcx, [rbx+10h]; pv
0x180033871  call    cs:__imp_CoTaskMemFree
0x180033877  mov     rdi, [rbx+58h]
0x18003387b  xor     eax, eax
0x18003387d  mov     [rbx+18h], ax
0x180033881  movzx   eax, word ptr [rbx+60h]
0x180033885  mov     qword ptr [rbx+10h], 0
0x18003388d  lea     rcx, [rax+rax*4]
0x180033891  lea     rsi, [rdi+rcx*8]
0x180033895  jmp     short loc_1800338A3
0x180033897  mov     rcx, rdi
0x18003389a  call    FreeCDPComResource
0x18003389f  add     rdi, 28h ; '('
0x1800338a3  cmp     rdi, rsi
0x1800338a6  jnz     short loc_180033897
0x1800338a8  mov     rcx, [rbx+58h]; pv
0x1800338ac  call    cs:__imp_CoTaskMemFree
0x1800338b2  mov     rcx, [rbx+68h]; pv
0x1800338b6  xor     eax, eax
0x1800338b8  mov     [rbx+60h], ax
0x1800338bc  mov     qword ptr [rbx+58h], 0
0x1800338c4  call    cs:__imp_CoTaskMemFree
0x1800338ca  mov     rcx, [rbx+50h]; pv
0x1800338ce  mov     qword ptr [rbx+68h], 0
0x1800338d6  call    cs:__imp_CoTaskMemFree
0x1800338dc  mov     rcx, [rbx+70h]; pv
0x1800338e0  mov     qword ptr [rbx+50h], 0
0x1800338e8  call    cs:__imp_CoTaskMemFree
0x1800338ee  mov     rsi, [rsp+28h+arg_8]
0x1800338f3  mov     qword ptr [rbx+70h], 0
0x1800338fb  mov     rbx, [rsp+28h+arg_0]
0x180033900  add     rsp, 20h
0x180033904  pop     rdi
0x180033905  retn
```
