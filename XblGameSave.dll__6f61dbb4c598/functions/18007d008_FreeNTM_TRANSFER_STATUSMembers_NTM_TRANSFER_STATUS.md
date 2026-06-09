# FreeNTM_TRANSFER_STATUSMembers(_NTM_TRANSFER_STATUS *)

- ea: `0x18007d008`
- end: `0x18007d0a1`
- name: `?FreeNTM_TRANSFER_STATUSMembers@@YAXPEAU_NTM_TRANSFER_STATUS@@@Z`
- size: `153`
- prototype: `void __fastcall(struct _NTM_TRANSFER_STATUS *)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180067020`
- `0x18006792c`

## callees

- `0x18007d008`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007d018`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007d022`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007d02f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007d03c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007d05b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007d069`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007d07b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007d089`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007d018`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007d022`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007d02f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007d03c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007d05b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007d069`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007d07b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007d089`

## pseudocode

```c
void __fastcall FreeNTM_TRANSFER_STATUSMembers(LPVOID *a1)
{
  unsigned __int16 i; // bp
  __int64 v3; // rdi

  CoTaskMemFree(a1[8]);
  CoTaskMemFree(a1[9]);
  CoTaskMemFree(a1[718]);
  CoTaskMemFree(a1[719]);
  for ( i = 0; i < *((_WORD *)a1 + 52); ++i )
  {
    v3 = 11LL * i;
    CoTaskMemFree(a1[v3 + 16]);
    CoTaskMemFree(a1[v3 + 17]);
    CoTaskMemFree(a1[11 * i + 22]);
    CoTaskMemFree(a1[v3 + 23]);
  }
}

```

## disassembly

```asm
0x18007d008  push    rbx
0x18007d00a  push    rbp
0x18007d00b  push    rsi
0x18007d00c  push    rdi
0x18007d00d  sub     rsp, 28h
0x18007d011  mov     rsi, rcx
0x18007d014  mov     rcx, [rcx+40h]; pv
0x18007d018  call    cs:__imp_CoTaskMemFree
0x18007d01e  mov     rcx, [rsi+48h]; pv
0x18007d022  call    cs:__imp_CoTaskMemFree
0x18007d028  mov     rcx, [rsi+1670h]; pv
0x18007d02f  call    cs:__imp_CoTaskMemFree
0x18007d035  mov     rcx, [rsi+1678h]; pv
0x18007d03c  call    cs:__imp_CoTaskMemFree
0x18007d042  xor     eax, eax
0x18007d044  xor     ebp, ebp
0x18007d046  cmp     ax, [rsi+68h]
0x18007d04a  jnb     short loc_18007D098
0x18007d04c  movzx   ebx, bp
0x18007d04f  imul    rdi, rbx, 58h ; 'X'
0x18007d053  mov     rcx, [rdi+rsi+80h]; pv
0x18007d05b  call    cs:__imp_CoTaskMemFree
0x18007d061  mov     rcx, [rdi+rsi+88h]; pv
0x18007d069  call    cs:__imp_CoTaskMemFree
0x18007d06f  lea     rax, [rbx+2]
0x18007d073  imul    rcx, rax, 58h ; 'X'
0x18007d077  mov     rcx, [rcx+rsi]; pv
0x18007d07b  call    cs:__imp_CoTaskMemFree
0x18007d081  mov     rcx, [rdi+rsi+0B8h]; pv
0x18007d089  call    cs:__imp_CoTaskMemFree
0x18007d08f  inc     bp
0x18007d092  cmp     bp, [rsi+68h]
0x18007d096  jb      short loc_18007D04C
0x18007d098  add     rsp, 28h
0x18007d09c  pop     rdi
0x18007d09d  pop     rsi
0x18007d09e  pop     rbp
0x18007d09f  pop     rbx
0x18007d0a0  retn
```
